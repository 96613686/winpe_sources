# OSIntegration::DEH::CapabilityAuthorizationHandler::GetXboxCapabilities(OSIntegration::Package const *,Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>> &)

- ea: `0x180015214`
- end: `0x180015e60`
- name: `?GetXboxCapabilities@CapabilityAuthorizationHandler@DEH@OSIntegration@@AEAAJPEBVPackage@3@AEAV?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@Common@@@Z`
- size: `3148`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801321e0`

## callees

- `0x18000b3bc`
- `0x18000bd80`
- `0x18000e6e0`
- `0x18000fed0`
- `0x180015214`
- `0x18003f7e0`
- `0x18006a98c`
- `0x180098bf4`
- `0x1800f0700`
- `0x18014d9e4`
- `0x180211010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180015d98`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180015d98`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800153f0`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180015506`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800153f0`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180015506`
- `OLEAUT32!__imp_SysFreeString` at `0x180015387`
- `OLEAUT32!__imp_SysFreeString` at `0x1800154a5`
- `OLEAUT32!__imp_SysFreeString` at `0x180015544`
- `OLEAUT32!__imp_SysFreeString` at `0x180015582`
- `OLEAUT32!__imp_SysFreeString` at `0x1800155ee`
- `OLEAUT32!__imp_SysFreeString` at `0x180015667`
- `OLEAUT32!__imp_SysFreeString` at `0x1800156a5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800156f6`
- `OLEAUT32!__imp_SysFreeString` at `0x180015734`
- `OLEAUT32!__imp_SysFreeString` at `0x180015790`
- `OLEAUT32!__imp_SysFreeString` at `0x180015e05`
- `OLEAUT32!__imp_SysFreeString` at `0x180015e24`
- `OLEAUT32!__imp_SysFreeString` at `0x180015387`
- `OLEAUT32!__imp_SysFreeString` at `0x1800154a5`
- `OLEAUT32!__imp_SysFreeString` at `0x180015544`
- `OLEAUT32!__imp_SysFreeString` at `0x180015582`
- `OLEAUT32!__imp_SysFreeString` at `0x1800155ee`
- `OLEAUT32!__imp_SysFreeString` at `0x180015667`
- `OLEAUT32!__imp_SysFreeString` at `0x1800156a5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800156f6`
- `OLEAUT32!__imp_SysFreeString` at `0x180015734`
- `OLEAUT32!__imp_SysFreeString` at `0x180015790`
- `OLEAUT32!__imp_SysFreeString` at `0x180015e05`
- `OLEAUT32!__imp_SysFreeString` at `0x180015e24`

## string_xrefs

- `0x1800157c3`: `onecore\admin\appmodel\osim\src\deh\appx\common\tools.cpp`
- `0x1800158a4`: `onecore\admin\appmodel\osim\src\deh\appx\common\tools.cpp`
- `0x1800154bb`: `/m:Package/m:Applications/m:Application/m:Extensions/mx:Extension/mx:XboxSystemResources`
- `0x1800154ff`: `/m:Package/m:Applications/m:Application/m:Extensions/mx:Extension/mx:XboxSystemResources`
- `0x18001539b`: `/*[local-name()='Package']/*[local-name()='Capabilities']/*[local-name()='Capability' and namespace-uri()='http://schemas.microsoft.com/appx/2013/xbox/manifest']`
- `0x1800153e9`: `/*[local-name()='Package']/*[local-name()='Capabilities']/*[local-name()='Capability' and namespace-uri()='http://schemas.microsoft.com/appx/2013/xbox/manifest']`
- `0x180015a2e`: `constrainedImpersonation`
- `0x180015bef`: `constrainedImpersonation`

## pseudocode

```c

```
