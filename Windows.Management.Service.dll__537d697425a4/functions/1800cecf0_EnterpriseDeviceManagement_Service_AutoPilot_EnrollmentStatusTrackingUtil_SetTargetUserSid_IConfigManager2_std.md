# EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::SetTargetUserSid(IConfigManager2 *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800cecf0`
- end: `0x1800cee1a`
- name: `?SetTargetUserSid@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CAJPEAUIConfigManager2@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `298`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x1800cdaac`
- `0x1800cf888`

## callees

- `0x180067e54`
- `0x180080bac`
- `0x180084d5c`
- `0x18008a26c`
- `0x1800cecf0`
- `0x180200010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800ced49`
- `OLEAUT32!__imp_SysAllocString` at `0x1800ced49`
- `OLEAUT32!__imp_VariantInit` at `0x1800ced28`
- `OLEAUT32!__imp_VariantInit` at `0x1800ced28`
- `OLEAUT32!__imp_VariantClear` at `0x1800cedd1`
- `OLEAUT32!__imp_VariantClear` at `0x1800cedef`
- `OLEAUT32!__imp_VariantClear` at `0x1800cedd1`
- `OLEAUT32!__imp_VariantClear` at `0x1800cedef`

## string_xrefs

- `0x1800ced13`: `OMADM::TargetedUserSID`
- `0x1800ced6a`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cedbb`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`

## pseudocode

```c

```
