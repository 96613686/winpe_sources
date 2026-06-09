# CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy2nd<CommonUtil::CMpCriticalSection>>::OnInitializeCallback(void *)

- ea: `0x140011cd0`
- end: `0x140011cea`
- name: `?OnInitializeCallback@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy2nd@VCMpCriticalSection@CommonUtil@@@CommonUtil@@@CommonUtil@@CAJPEAX@Z`
- size: `26`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x140011cdd`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x140011cdd`

## pseudocode

```c
__int64 __fastcall CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy2nd<CommonUtil::CMpCriticalSection>>::OnInitializeCallback(
        struct _RTL_CRITICAL_SECTION *a1)
{
  a1->RecursionCount = 0;
  InitializeCriticalSectionAndSpinCount(a1, 0);
  return 0;
}

```

## disassembly

```asm
0x140011cd0  sub     rsp, 28h
0x140011cd4  xor     edx, edx; dwSpinCount
0x140011cd6  mov     dword ptr [rcx+0Ch], 0
0x140011cdd  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x140011ce3  xor     eax, eax
0x140011ce5  add     rsp, 28h
0x140011ce9  retn
```
