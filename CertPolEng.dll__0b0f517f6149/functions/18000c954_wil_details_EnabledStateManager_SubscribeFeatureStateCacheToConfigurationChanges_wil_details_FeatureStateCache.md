# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000c954`
- end: `0x18000c9dd`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `137`
- prototype: `void __fastcall(__int64, volatile signed __int32 *, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180009220`
- `0x180018924`

## callees

- `0x18000c954`
- `0x180012990`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c978`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c978`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c9cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c9cc`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        __int64 a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  RTL_SRWLOCK *v8; // rbx
  _DWORD v9[2]; // [rsp+20h] [rbp-38h] BYREF
  volatile signed __int32 *v10; // [rsp+28h] [rbp-30h]

  if ( *(_DWORD *)a1 )
  {
    v8 = (RTL_SRWLOCK *)(a1 + 8);
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
    if ( !a4
      || a4 != *(_DWORD *)(a1 + 28)
      || (v9[1] = 0,
          v9[0] = a3,
          v10 = a2,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(a1 + 64), v9, 0x10u)) )
    {
      _InterlockedAnd(a2, a3 != 0 ? -5 : -2111);
    }
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
  }
}

```

## disassembly

```asm
0x18000c954  push    rbx
0x18000c956  push    rbp
0x18000c957  push    rsi
0x18000c958  push    rdi
0x18000c959  push    r14
0x18000c95b  sub     rsp, 30h
0x18000c95f  mov     eax, [rcx]
0x18000c961  mov     ebp, r9d
0x18000c964  mov     edi, r8d
0x18000c967  mov     rsi, rdx
0x18000c96a  mov     r14, rcx
0x18000c96d  test    eax, eax
0x18000c96f  jz      short loc_18000C9D2
0x18000c971  lea     rbx, [rcx+8]
0x18000c975  mov     rcx, rbx; SRWLock
0x18000c978  call    cs:__imp_AcquireSRWLockExclusive
0x18000c97e  mov     eax, [r14+1Ch]
0x18000c982  test    ebp, ebp
0x18000c984  jz      short loc_18000C9B3
0x18000c986  cmp     ebp, eax
0x18000c988  jnz     short loc_18000C9B3
0x18000c98a  lea     rcx, [r14+40h]; this
0x18000c98e  mov     [rsp+58h+var_34], 0
0x18000c996  mov     r8d, 10h; unsigned __int64
0x18000c99c  mov     [rsp+58h+var_38], edi
0x18000c9a0  lea     rdx, [rsp+58h+var_38]; void *
0x18000c9a5  mov     [rsp+58h+var_30], rsi
0x18000c9aa  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000c9af  test    al, al
0x18000c9b1  jnz     short loc_18000C9C4
0x18000c9b3  neg     edi
0x18000c9b5  sbb     eax, eax
0x18000c9b7  and     eax, 83Ah
0x18000c9bc  add     eax, 0FFFFF7C1h
0x18000c9c1  lock and [rsi], eax
0x18000c9c4  test    rbx, rbx
0x18000c9c7  jz      short loc_18000C9D2
0x18000c9c9  mov     rcx, rbx; SRWLock
0x18000c9cc  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c9d2  add     rsp, 30h
0x18000c9d6  pop     r14
0x18000c9d8  pop     rdi
0x18000c9d9  pop     rsi
0x18000c9da  pop     rbp
0x18000c9db  pop     rbx
0x18000c9dc  retn
```
