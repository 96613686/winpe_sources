# Microsoft::Windows::Autopilot::CspUtils::SetTargetUserSid(IConfigManager2 *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18019c340`
- end: `0x18019c44f`
- name: `?SetTargetUserSid@CspUtils@Autopilot@Windows@Microsoft@@SAJPEAUIConfigManager2@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `271`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18019c0f0`
- `0x18019c458`

## callees

- `0x180067a54`
- `0x18008019c`
- `0x1800841e8`
- `0x18008939c`
- `0x18019c340`
- `0x1801fa010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18019c393`
- `OLEAUT32!__imp_SysAllocString` at `0x18019c393`
- `OLEAUT32!__imp_VariantInit` at `0x18019c378`
- `OLEAUT32!__imp_VariantInit` at `0x18019c378`
- `OLEAUT32!__imp_VariantClear` at `0x18019c413`
- `OLEAUT32!__imp_VariantClear` at `0x18019c42b`
- `OLEAUT32!__imp_VariantClear` at `0x18019c413`
- `OLEAUT32!__imp_VariantClear` at `0x18019c42b`

## string_xrefs

- `0x18019c363`: `OMADM::TargetedUserSID`
- `0x18019c3ae`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\csputils.cpp`
- `0x18019c3fd`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\csputils.cpp`

## pseudocode

```c

```
