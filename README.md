# MobileFirst-Helper
Utility class for native iOS MobileFirst/Worklight applications.  To use, just include the .h and .m files in your project, import the header, then start coding.


# invokeProcedure


Utility function to invoke a MobileFirst/Worklight procedure using code blocks instead of defining delegate classes. *This is for MobileFirst Platform Foundation Server 6 and newer, for native iOS applications. You can also use code blocks using the [WLResourceRequest](https://www-01.ibm.com/support/knowledgecenter/SSHSCD_7.0.0/com.ibm.worklight.apiref.doc/html/refobjc-worklight-ios/html/interface_w_l_resource_request.html?cp=SSHSCD_7.0.0%2F8-0-0-2-0-51) API in MobileFirst Platform Foundation Server 7.*

Sample:
``` 
WLProcedureInvocationData *invocationData =
	[[WLProcedureInvocationData alloc]
		initWithAdapterName:@"StockAdapter"
			  procedureName:@"getList"];
	
[WLClientHelper invokeProcedure:invocationData successCallback:^(WLResponse *successResponse) {
	//handle the response	
} errorCallback:^(WLFailResponse *errorResponse) {
	//handle the error response
}];
```


# getLoggerForInstance*

Utility function to get an OClogger instance with the package matching the class name of the instance passed in.

Sample:
```
OCLogger *logger = [WLClientHelper getLoggerForInstance:self];
```