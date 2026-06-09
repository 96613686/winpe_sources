# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180008ce8`
- end: `0x180008d71`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `137`
- prototype: `void __fastcall(__int64, volatile signed __int32 *, int, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007de0`
- `0x180007f50`
- `0x1800083a0`
- `0x180008e80`

## callees

- `0x180008ce8`
- `0x18000ba60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008d60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008d60`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008d0c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008d0c`

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
0x180008ce8  push    rbx
0x180008cea  push    rbp
0x180008ceb  push    rsi
0x180008cec  push    rdi
0x180008ced  push    r14
0x180008cef  sub     rsp, 30h
0x180008cf3  mov     eax, [rcx]
0x180008cf5  mov     ebp, r9d
0x180008cf8  mov     edi, r8d
0x180008cfb  mov     rsi, rdx
0x180008cfe  mov     r14, rcx
0x180008d01  test    eax, eax
0x180008d03  jz      short loc_180008D66
0x180008d05  lea     rbx, [rcx+8]
0x180008d09  mov     rcx, rbx; SRWLock
0x180008d0c  call    cs:__imp_AcquireSRWLockExclusive
0x180008d12  mov     eax, [r14+1Ch]
0x180008d16  test    ebp, ebp
0x180008d18  jz      short loc_180008D47
0x180008d1a  cmp     ebp, eax
0x180008d1c  jnz     short loc_180008D47
0x180008d1e  lea     rcx, [r14+40h]; this
0x180008d22  mov     [rsp+58h+var_34], 0
0x180008d2a  mov     r8d, 10h; unsigned __int64
0x180008d30  mov     [rsp+58h+var_38], edi
0x180008d34  lea     rdx, [rsp+58h+var_38]; void *
0x180008d39  mov     [rsp+58h+var_30], rsi
0x180008d3e  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180008d43  test    al, al
0x180008d45  jnz     short loc_180008D58
0x180008d47  neg     edi
0x180008d49  sbb     eax, eax
0x180008d4b  and     eax, 83Ah
0x180008d50  add     eax, 0FFFFF7C1h
0x180008d55  lock and [rsi], eax
0x180008d58  test    rbx, rbx
0x180008d5b  jz      short loc_180008D66
0x180008d5d  mov     rcx, rbx; SRWLock
0x180008d60  call    cs:__imp_ReleaseSRWLockExclusive
0x180008d66  add     rsp, 30h
0x180008d6a  pop     r14
0x180008d6c  pop     rdi
0x180008d6d  pop     rsi
0x180008d6e  pop     rbp
0x180008d6f  pop     rbx
0x180008d70  retn
```
