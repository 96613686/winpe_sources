# CommonUtil::_dynamic_initializer_for__gs_aClientLibraryHolder__

- ea: `0x140001250`
- end: `0x14000127e`
- name: `CommonUtil::_dynamic_initializer_for__gs_aClientLibraryHolder__`
- size: `46`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140011110`

## pseudocode

```c
__int64 CommonUtil::_dynamic_initializer_for__gs_aClientLibraryHolder__()
{
  __int64 result; // rax

  result = MpRegisterForInitializationAtStartup(
             qword_14001BA08,
             CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy2nd<CommonUtil::CMpCriticalSection>>::OnInitialize,
             CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy2nd<CommonUtil::CMpCriticalSection>>::OnDestroy);
  xmmword_14001BA30 = 0;
  return result;
}

```

## disassembly

```asm
0x140001250  sub     rsp, 28h
0x140001254  lea     r8, ?OnDestroy@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy2nd@VCMpCriticalSection@CommonUtil@@@CommonUtil@@@CommonUtil@@CAXPEAUtagMP_AT_STARTUP_TYPE@@@Z; CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy2nd<CommonUtil::CMpCriticalSection>>::OnDestroy(tagMP_AT_STARTUP_TYPE *)
0x14000125b  lea     rdx, ?OnInitialize@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy2nd@VCMpCriticalSection@CommonUtil@@@CommonUtil@@@CommonUtil@@CAJPEAUtagMP_AT_STARTUP_TYPE@@@Z; CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy2nd<CommonUtil::CMpCriticalSection>>::OnInitialize(tagMP_AT_STARTUP_TYPE *)
0x140001262  lea     rcx, qword_14001BA08
0x140001269  call    MpRegisterForInitializationAtStartup
0x14000126e  xorps   xmm0, xmm0
0x140001271  movdqa  cs:xmmword_14001BA30, xmm0
0x140001279  add     rsp, 28h
0x14000127d  retn
```
