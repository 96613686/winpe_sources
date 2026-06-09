# EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::SetTargetUserSid(IConfigManager2 *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800cc964`
- end: `0x1800cca75`
- name: `?SetTargetUserSid@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CAJPEAUIConfigManager2@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `273`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x1800cb75c`
- `0x1800cd4a4`

## callees

- `0x180067a54`
- `0x18008019c`
- `0x1800841e8`
- `0x18008939c`
- `0x1800cc964`
- `0x1801fa010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800cc9b7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800cc9b7`
- `OLEAUT32!__imp_VariantInit` at `0x1800cc99c`
- `OLEAUT32!__imp_VariantInit` at `0x1800cc99c`
- `OLEAUT32!__imp_VariantClear` at `0x1800cca39`
- `OLEAUT32!__imp_VariantClear` at `0x1800cca51`
- `OLEAUT32!__imp_VariantClear` at `0x1800cca39`
- `OLEAUT32!__imp_VariantClear` at `0x1800cca51`

## string_xrefs

- `0x1800cc987`: `OMADM::TargetedUserSID`
- `0x1800cc9d2`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cca23`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`

## pseudocode

```c

```
