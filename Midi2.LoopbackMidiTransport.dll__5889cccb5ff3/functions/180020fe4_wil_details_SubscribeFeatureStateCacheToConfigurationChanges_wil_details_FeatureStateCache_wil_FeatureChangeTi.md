# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180020fe4`
- end: `0x180021074`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `144`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001e720`
- `0x18001e8f4`
- `0x18001ea68`
- `0x18001ebdc`
- `0x18001ed50`
- `0x18001eec4`
- `0x18001f038`
- `0x18001f1ac`
- `0x18001f28c`
- `0x18001f36c`
- `0x18001f44c`
- `0x18001f52c`
- `0x18001f60c`
- `0x18001f6ec`

## callees

- `0x180020fe4`
- `0x180021770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002105e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002105e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002100c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002100c`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  unsigned __int64 v6; // r8
  _DWORD v7[2]; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v8; // [rsp+28h] [rbp-10h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !a3
      || a3 != dword_18005F794
      || (v7[1] = 0,
          v7[0] = a2,
          v8 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18005F7B8, v7, v6)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x180020fe4  mov     [rsp+arg_0], rbx
0x180020fe9  mov     [rsp+arg_8], rsi
0x180020fee  push    rdi
0x180020fef  sub     rsp, 30h
0x180020ff3  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180020ff9  mov     esi, r8d
0x180020ffc  mov     ebx, edx
0x180020ffe  mov     rdi, rcx
0x180021001  test    eax, eax
0x180021003  jz      short loc_180021064
0x180021005  lea     rcx, SRWLock; SRWLock
0x18002100c  call    cs:__imp_AcquireSRWLockExclusive
0x180021012  mov     eax, cs:dword_18005F794
0x180021018  test    esi, esi
0x18002101a  jz      short loc_180021046
0x18002101c  cmp     esi, eax
0x18002101e  jnz     short loc_180021046
0x180021020  lea     rdx, [rsp+38h+var_18]; void *
0x180021025  mov     [rsp+38h+var_14], 0
0x18002102d  lea     rcx, qword_18005F7B8; this
0x180021034  mov     [rsp+38h+var_18], ebx
0x180021038  mov     [rsp+38h+var_10], rdi
0x18002103d  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180021042  test    al, al
0x180021044  jnz     short loc_180021057
0x180021046  neg     ebx
0x180021048  sbb     eax, eax
0x18002104a  and     eax, 83Ah
0x18002104f  add     eax, 0FFFFF7C1h
0x180021054  lock and [rdi], eax
0x180021057  lea     rcx, SRWLock; SRWLock
0x18002105e  call    cs:__imp_ReleaseSRWLockExclusive
0x180021064  mov     rbx, [rsp+38h+arg_0]
0x180021069  mov     rsi, [rsp+38h+arg_8]
0x18002106e  add     rsp, 30h
0x180021072  pop     rdi
0x180021073  retn
```
