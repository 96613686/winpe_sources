# tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>::Release(void)

- ea: `0x18001a54c`
- end: `0x18001a584`
- name: `?Release@?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012594`
- `0x180012d64`
- `0x18001ffe4`

## callees

- `0x1800126a4`
- `0x18001a54c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a571`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a571`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 70);
  if ( !v2 )
  {
    tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>::~merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>((__int64)pv);
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x18001a54c  mov     [rsp+arg_0], rbx
0x18001a551  push    rdi
0x18001a552  sub     rsp, 20h
0x18001a556  mov     rdi, rcx
0x18001a559  or      ebx, 0FFFFFFFFh
0x18001a55c  lock xadd [rcx+118h], ebx
0x18001a564  sub     ebx, 1
0x18001a567  jnz     short loc_18001A577
0x18001a569  call    ??1?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>::~merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>(void)
0x18001a56e  mov     rcx, rdi; pv
0x18001a571  call    cs:__imp_CoTaskMemFree
0x18001a577  mov     eax, ebx
0x18001a579  mov     rbx, [rsp+28h+arg_0]
0x18001a57e  add     rsp, 20h
0x18001a582  pop     rdi
0x18001a583  retn
```
