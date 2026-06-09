# Microsoft::Windows::Autopilot::CspUtils::SetTargetUserSid(IConfigManager2 *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1801a1714`
- end: `0x1801a183c`
- name: `?SetTargetUserSid@CspUtils@Autopilot@Windows@Microsoft@@SAJPEAUIConfigManager2@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `296`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801a14bc`
- `0x1801a1844`

## callees

- `0x180067e54`
- `0x180080bac`
- `0x180084d5c`
- `0x18008a26c`
- `0x1801a1714`
- `0x180200010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1801a176d`
- `OLEAUT32!__imp_SysAllocString` at `0x1801a176d`
- `OLEAUT32!__imp_VariantInit` at `0x1801a174c`
- `OLEAUT32!__imp_VariantInit` at `0x1801a174c`
- `OLEAUT32!__imp_VariantClear` at `0x1801a17f3`
- `OLEAUT32!__imp_VariantClear` at `0x1801a1811`
- `OLEAUT32!__imp_VariantClear` at `0x1801a17f3`
- `OLEAUT32!__imp_VariantClear` at `0x1801a1811`

## string_xrefs

- `0x1801a1737`: `OMADM::TargetedUserSID`
- `0x1801a178e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\csputils.cpp`
- `0x1801a17dd`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\csputils.cpp`

## pseudocode

```c

```
