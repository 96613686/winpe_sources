# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::RegisterModel

- ea: `0x2ad0`
- end: `0x2b85`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::RegisterModel`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x11c0`

## string_xrefs

- `0x2afc`: `DeleteItems`
- `0x2b0b`: `CatalogItemPaths`
- `0x2b3c`: `CatalogItemPaths`
- `0x2b21`: `MoveItems`
- `0x2b31`: `TargetPath`
- `0x2b4d`: `AccessToken`

## pseudocode

```c

```

## disassembly

```asm
0x2ad0  ldarg.0
0x2ad1  callvirt T0x2B00004C
0x2ad6  pop
0x2ad7  ldarg.0
0x2ad8  callvirt T0x2B00004D
0x2add  pop
0x2ade  ldarg.0
0x2adf  callvirt T0x2B00004E
0x2ae4  pop
0x2ae5  ldarg.0
0x2ae6  ldstr    aCatalogitems// "CatalogItems"
0x2aeb  callvirt T0x2B00004F
0x2af0  pop
0x2af1  ldarg.0
0x2af2  callvirt T0x2B000050
0x2af7  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityCollectionConfiguration`1<var<u1>> class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::get_Collection()
0x2afc  ldstr    aDeleteitems// "DeleteItems"
0x2b01  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityCollectionConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::Action(string)
0x2b06  callvirt T0x2B000051
0x2b0b  ldstr    aCatalogitempat// "CatalogItemPaths"
0x2b10  callvirt T0x2B000052
0x2b15  pop
0x2b16  ldarg.0
0x2b17  callvirt T0x2B000050
0x2b1c  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityCollectionConfiguration`1<var<u1>> class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::get_Collection()
0x2b21  ldstr    aMoveitems// "MoveItems"
0x2b26  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityCollectionConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::Action(string)
0x2b2b  callvirt T0x2B000051
0x2b30  dup
0x2b31  ldstr    aTargetpath// "TargetPath"
0x2b36  callvirt T0x2B000031
0x2b3b  pop
0x2b3c  ldstr    aCatalogitempat// "CatalogItemPaths"
0x2b41  callvirt T0x2B000052
0x2b46  pop
0x2b47  ldarg.0
0x2b48  callvirt T0x2B000050
0x2b4d  ldstr    aAccesstoken// "AccessToken"
0x2b52  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.FunctionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::Function(string)
0x2b57  callvirt T0x2B000053
0x2b5c  pop
0x2b5d  ldarg.0
0x2b5e  callvirt T0x2B000054
0x2b63  pop
0x2b64  ldarg.0
0x2b65  callvirt T0x2B000050
0x2b6a  ldstr    aGetcontenttrus// "GetContentTrusted"
0x2b6f  callvirt instance class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.ActionConfiguration class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Builder.EntityTypeConfiguration`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::Action(string)
0x2b74  callvirt T0x2B000055
0x2b79  ldsfld   string class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::TrustedProcessTokenString
0x2b7e  callvirt T0x2B000031
0x2b83  pop
0x2b84  ret
```
