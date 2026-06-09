# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180009c24`
- end: `0x180009ce1`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009520`

## callees

- `0x180008bc8`
- `0x180009c24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009c7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009c7e`

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
0x180009c24  mov     [rsp+arg_0], rbx
0x180009c29  push    rdi
0x180009c2a  sub     rsp, 20h
0x180009c2e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180009c35  xor     ebx, ebx
0x180009c37  test    rdi, rdi
0x180009c3a  jz      loc_180009CD3
0x180009c40  cmp     [rdi+8], rbx
0x180009c44  jnz     short loc_180009C6B
0x180009c46  mov     rcx, [rdi]
0x180009c49  lea     rdx, [rsp+28h+arg_8]
0x180009c4e  mov     [rsp+28h+arg_8], rbx
0x180009c53  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180009c58  test    eax, eax
0x180009c5a  js      short loc_180009C6B
0x180009c5c  cmp     [rdi+8], rbx
0x180009c60  jnz     short loc_180009C6B
0x180009c62  mov     rax, [rsp+28h+arg_8]
0x180009c67  mov     [rdi+8], rax
0x180009c6b  mov     rax, [rdi+8]
0x180009c6f  lea     rcx, [rax+20h]
0x180009c73  neg     rax
0x180009c76  sbb     rdi, rdi
0x180009c79  and     rdi, rcx
0x180009c7c  jz      short loc_180009CD3
0x180009c7e  call    cs:__imp_GetCurrentThreadId
0x180009c84  mov     r8d, eax
0x180009c87  mov     r9d, eax
0x180009c8a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180009c94  shr     r8, 2
0x180009c98  mul     r8
0x180009c9b  shr     rdx, 3
0x180009c9f  lea     rcx, [rdx+rdx*4]
0x180009ca3  add     rcx, rcx
0x180009ca6  sub     r8, rcx
0x180009ca9  mov     rbx, [rdi+r8*8+8]
0x180009cae  test    rbx, rbx
0x180009cb1  jz      short loc_180009CD3
0x180009cb3  cmp     [rbx], r9d
0x180009cb6  jz      short loc_180009CBE
0x180009cb8  mov     rbx, [rbx+8]
0x180009cbc  jmp     short loc_180009CAE
0x180009cbe  add     rbx, 10h
0x180009cc2  jz      short loc_180009CD3
0x180009cc4  cmp     qword ptr [rbx+8], 0
0x180009cc9  jnz     short loc_180009CD3
0x180009ccb  lea     rax, [rdi+4]
0x180009ccf  mov     [rbx+8], rax
0x180009cd3  mov     rax, rbx
0x180009cd6  mov     rbx, [rsp+28h+arg_0]
0x180009cdb  add     rsp, 20h
0x180009cdf  pop     rdi
0x180009ce0  retn
```
