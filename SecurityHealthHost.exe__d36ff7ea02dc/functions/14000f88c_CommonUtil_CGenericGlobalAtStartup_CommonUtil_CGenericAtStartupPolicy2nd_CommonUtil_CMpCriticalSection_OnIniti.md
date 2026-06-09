# CommonUtil::CGenericGlobalAtStartup<CommonUtil::CGenericAtStartupPolicy2nd<CommonUtil::CMpCriticalSection>>::OnInitializeCallback(void *)

- ea: `0x14000f88c`
- end: `0x14000f8a6`
- name: `?OnInitializeCallback@?$CGenericGlobalAtStartup@U?$CGenericAtStartupPolicy2nd@VCMpCriticalSection@CommonUtil@@@CommonUtil@@@CommonUtil@@CAJPEAX@Z`
- size: `26`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000f8ac`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x14000f899`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x14000f899`

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
0x14000f88c  sub     rsp, 28h
0x14000f890  xor     edx, edx; dwSpinCount
0x14000f892  mov     dword ptr [rcx+0Ch], 0
0x14000f899  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14000f89f  xor     eax, eax
0x14000f8a1  add     rsp, 28h
0x14000f8a5  retn
```
