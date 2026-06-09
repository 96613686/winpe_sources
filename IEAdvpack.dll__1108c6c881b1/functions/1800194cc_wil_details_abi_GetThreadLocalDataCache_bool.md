# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800194cc`
- end: `0x180019588`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `188`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180018f80`

## callees

- `0x180001be2`
- `0x180018a30`
- `0x1800194cc`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId_0; // r9d
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

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
      CurrentThreadId_0 = GetCurrentThreadId_0();
      for ( i = *(_QWORD *)(v4 + 8 * (((unsigned __int64)CurrentThreadId_0 >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId_0 )
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
0x1800194cc  mov     [rsp+arg_0], rbx
0x1800194d1  push    rdi
0x1800194d2  sub     rsp, 20h
0x1800194d6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800194dd  xor     ebx, ebx
0x1800194df  test    rdi, rdi
0x1800194e2  jz      loc_18001957A
0x1800194e8  cmp     [rdi+8], rbx
0x1800194ec  jnz     short loc_180019513
0x1800194ee  mov     rcx, [rdi]
0x1800194f1  lea     rdx, [rsp+28h+arg_8]
0x1800194f6  mov     [rsp+28h+arg_8], rbx
0x1800194fb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180019500  test    eax, eax
0x180019502  js      short loc_180019513
0x180019504  cmp     [rdi+8], rbx
0x180019508  jnz     short loc_180019513
0x18001950a  mov     rax, [rsp+28h+arg_8]
0x18001950f  mov     [rdi+8], rax
0x180019513  mov     rax, [rdi+8]
0x180019517  lea     rcx, [rax+20h]
0x18001951b  neg     rax
0x18001951e  sbb     rdi, rdi
0x180019521  and     rdi, rcx
0x180019524  jz      short loc_18001957A
0x180019526  call    GetCurrentThreadId_0
0x18001952b  mov     r8d, eax
0x18001952e  mov     r9d, eax
0x180019531  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001953b  shr     r8, 2
0x18001953f  mul     r8
0x180019542  shr     rdx, 3
0x180019546  lea     rcx, [rdx+rdx*4]
0x18001954a  add     rcx, rcx
0x18001954d  sub     r8, rcx
0x180019550  mov     rbx, [rdi+r8*8+8]
0x180019555  test    rbx, rbx
0x180019558  jz      short loc_18001957A
0x18001955a  cmp     [rbx], r9d
0x18001955d  jz      short loc_180019565
0x18001955f  mov     rbx, [rbx+8]
0x180019563  jmp     short loc_180019555
0x180019565  add     rbx, 10h
0x180019569  jz      short loc_18001957A
0x18001956b  cmp     qword ptr [rbx+8], 0
0x180019570  jnz     short loc_18001957A
0x180019572  lea     rax, [rdi+4]
0x180019576  mov     [rbx+8], rax
0x18001957a  mov     rax, rbx
0x18001957d  mov     rbx, [rsp+28h+arg_0]
0x180019582  add     rsp, 20h
0x180019586  pop     rdi
0x180019587  retn
```
