# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180007c44`
- end: `0x180007cff`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007390`

## callees

- `0x1800061c8`
- `0x180007c44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007c9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007c9a`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
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
0x180007c44  mov     [rsp+arg_0], rbx
0x180007c49  push    rdi
0x180007c4a  sub     rsp, 20h
0x180007c4e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180007c55  xor     ebx, ebx
0x180007c57  test    rdi, rdi
0x180007c5a  jz      short loc_180007CDA
0x180007c5c  cmp     [rdi+8], rbx
0x180007c60  jnz     short loc_180007C87
0x180007c62  mov     rcx, [rdi]
0x180007c65  lea     rdx, [rsp+28h+arg_8]
0x180007c6a  mov     [rsp+28h+arg_8], rbx
0x180007c6f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180007c74  test    eax, eax
0x180007c76  js      short loc_180007C87
0x180007c78  cmp     [rdi+8], rbx
0x180007c7c  jnz     short loc_180007C87
0x180007c7e  mov     rax, [rsp+28h+arg_8]
0x180007c83  mov     [rdi+8], rax
0x180007c87  mov     rax, [rdi+8]
0x180007c8b  lea     rcx, [rax+20h]
0x180007c8f  neg     rax
0x180007c92  sbb     rdi, rdi
0x180007c95  and     rdi, rcx
0x180007c98  jz      short loc_180007CDA
0x180007c9a  call    cs:__imp_GetCurrentThreadId
0x180007ca0  mov     r8d, eax
0x180007ca3  mov     r9d, eax
0x180007ca6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007cb0  shr     r8, 2
0x180007cb4  mul     r8
0x180007cb7  shr     rdx, 3
0x180007cbb  lea     rcx, [rdx+rdx*4]
0x180007cbf  add     rcx, rcx
0x180007cc2  sub     r8, rcx
0x180007cc5  mov     rbx, [rdi+r8*8+8]
0x180007cca  jmp     short loc_180007CD5
0x180007ccc  cmp     [rbx], r9d
0x180007ccf  jz      short loc_180007CE8
0x180007cd1  mov     rbx, [rbx+8]
0x180007cd5  test    rbx, rbx
0x180007cd8  jnz     short loc_180007CCC
0x180007cda  mov     rax, rbx
0x180007cdd  mov     rbx, [rsp+28h+arg_0]
0x180007ce2  add     rsp, 20h
0x180007ce6  pop     rdi
0x180007ce7  retn
0x180007ce8  add     rbx, 10h
0x180007cec  jz      short loc_180007CDA
0x180007cee  cmp     qword ptr [rbx+8], 0
0x180007cf3  jnz     short loc_180007CDA
0x180007cf5  lea     rax, [rdi+4]
0x180007cf9  mov     [rbx+8], rax
0x180007cfd  jmp     short loc_180007CDA
```
