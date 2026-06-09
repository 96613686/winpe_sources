# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140006d7c`
- end: `0x140006e39`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140006320`

## callees

- `0x140004030`
- `0x140006d7c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140006dd6`
- `KERNEL32!GetCurrentThreadId` at `0x140006dd6`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  void *v7; // [rsp+38h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  i = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v3 = *(_QWORD *)wil::details_abi::g_pProcessLocalData;
      v7 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v3, &v7) >= 0
        && !*(_QWORD *)(v1 + 8) )
      {
        *(_QWORD *)(v1 + 8) = v7;
      }
    }
    v4 = (*(_QWORD *)(v1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v1 + 8) != 0);
    if ( v4 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v4 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          i += 16;
          if ( i && !*(_QWORD *)(i + 8) )
            *(_QWORD *)(i + 8) = v4 + 4;
          return (struct wil::details_abi::ThreadLocalData *)i;
        }
      }
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)i;
}

```

## disassembly

```asm
0x140006d7c  mov     [rsp+arg_0], rbx
0x140006d81  push    rdi
0x140006d82  sub     rsp, 20h
0x140006d86  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140006d8d  xor     ebx, ebx
0x140006d8f  test    rdi, rdi
0x140006d92  jz      loc_140006E2B
0x140006d98  cmp     [rdi+8], rbx
0x140006d9c  jnz     short loc_140006DC3
0x140006d9e  mov     rcx, [rdi]
0x140006da1  lea     rdx, [rsp+28h+arg_8]
0x140006da6  mov     [rsp+28h+arg_8], rbx
0x140006dab  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140006db0  test    eax, eax
0x140006db2  js      short loc_140006DC3
0x140006db4  cmp     [rdi+8], rbx
0x140006db8  jnz     short loc_140006DC3
0x140006dba  mov     rax, [rsp+28h+arg_8]
0x140006dbf  mov     [rdi+8], rax
0x140006dc3  mov     rax, [rdi+8]
0x140006dc7  lea     rcx, [rax+20h]
0x140006dcb  neg     rax
0x140006dce  sbb     rdi, rdi
0x140006dd1  and     rdi, rcx
0x140006dd4  jz      short loc_140006E2B
0x140006dd6  call    cs:__imp_GetCurrentThreadId
0x140006ddc  mov     r8d, eax
0x140006ddf  mov     r9d, eax
0x140006de2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140006dec  shr     r8, 2
0x140006df0  mul     r8
0x140006df3  shr     rdx, 3
0x140006df7  lea     rcx, [rdx+rdx*4]
0x140006dfb  add     rcx, rcx
0x140006dfe  sub     r8, rcx
0x140006e01  mov     rbx, [rdi+r8*8+8]
0x140006e06  test    rbx, rbx
0x140006e09  jz      short loc_140006E2B
0x140006e0b  cmp     [rbx], r9d
0x140006e0e  jz      short loc_140006E16
0x140006e10  mov     rbx, [rbx+8]
0x140006e14  jmp     short loc_140006E06
0x140006e16  add     rbx, 10h
0x140006e1a  jz      short loc_140006E2B
0x140006e1c  cmp     qword ptr [rbx+8], 0
0x140006e21  jnz     short loc_140006E2B
0x140006e23  lea     rax, [rdi+4]
0x140006e27  mov     [rbx+8], rax
0x140006e2b  mov     rax, rbx
0x140006e2e  mov     rbx, [rsp+28h+arg_0]
0x140006e33  add     rsp, 20h
0x140006e37  pop     rdi
0x140006e38  retn
```
