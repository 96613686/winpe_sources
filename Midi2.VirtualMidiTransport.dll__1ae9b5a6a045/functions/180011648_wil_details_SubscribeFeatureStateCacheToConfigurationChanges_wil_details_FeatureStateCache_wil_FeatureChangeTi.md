# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180011648`
- end: `0x1800116d8`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `144`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000ef14`
- `0x18000f0e8`
- `0x18000f25c`
- `0x18000f3d0`
- `0x18000f544`
- `0x18000f6b8`
- `0x18000f82c`
- `0x18000f9a0`
- `0x18000fa80`
- `0x18000fb60`
- `0x18000fc40`
- `0x18000fd20`
- `0x18000fe00`
- `0x18000fee0`

## callees

- `0x180011648`
- `0x180011ec4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011670`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011670`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800116c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800116c2`

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
      || a3 != dword_18002D714
      || (v7[1] = 0,
          v7[0] = a2,
          v8 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002D738, v7, v6)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x180011648  mov     [rsp+arg_0], rbx
0x18001164d  mov     [rsp+arg_8], rsi
0x180011652  push    rdi
0x180011653  sub     rsp, 30h
0x180011657  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001165d  mov     esi, r8d
0x180011660  mov     ebx, edx
0x180011662  mov     rdi, rcx
0x180011665  test    eax, eax
0x180011667  jz      short loc_1800116C8
0x180011669  lea     rcx, SRWLock; SRWLock
0x180011670  call    cs:__imp_AcquireSRWLockExclusive
0x180011676  mov     eax, cs:dword_18002D714
0x18001167c  test    esi, esi
0x18001167e  jz      short loc_1800116AA
0x180011680  cmp     esi, eax
0x180011682  jnz     short loc_1800116AA
0x180011684  lea     rdx, [rsp+38h+var_18]; void *
0x180011689  mov     [rsp+38h+var_14], 0
0x180011691  lea     rcx, qword_18002D738; this
0x180011698  mov     [rsp+38h+var_18], ebx
0x18001169c  mov     [rsp+38h+var_10], rdi
0x1800116a1  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800116a6  test    al, al
0x1800116a8  jnz     short loc_1800116BB
0x1800116aa  neg     ebx
0x1800116ac  sbb     eax, eax
0x1800116ae  and     eax, 83Ah
0x1800116b3  add     eax, 0FFFFF7C1h
0x1800116b8  lock and [rdi], eax
0x1800116bb  lea     rcx, SRWLock; SRWLock
0x1800116c2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800116c8  mov     rbx, [rsp+38h+arg_0]
0x1800116cd  mov     rsi, [rsp+38h+arg_8]
0x1800116d2  add     rsp, 30h
0x1800116d6  pop     rdi
0x1800116d7  retn
```
