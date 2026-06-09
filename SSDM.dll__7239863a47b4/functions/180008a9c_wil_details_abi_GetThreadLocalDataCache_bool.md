# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180008a9c`
- end: `0x180008b57`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800086a0`

## callees

- `0x180008080`
- `0x180008a9c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008af2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008af2`

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
0x180008a9c  mov     [rsp+arg_0], rbx
0x180008aa1  push    rdi
0x180008aa2  sub     rsp, 20h
0x180008aa6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180008aad  xor     ebx, ebx
0x180008aaf  test    rdi, rdi
0x180008ab2  jz      short loc_180008B32
0x180008ab4  cmp     [rdi+8], rbx
0x180008ab8  jnz     short loc_180008ADF
0x180008aba  mov     rcx, [rdi]
0x180008abd  lea     rdx, [rsp+28h+arg_8]
0x180008ac2  mov     [rsp+28h+arg_8], rbx
0x180008ac7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180008acc  test    eax, eax
0x180008ace  js      short loc_180008ADF
0x180008ad0  cmp     [rdi+8], rbx
0x180008ad4  jnz     short loc_180008ADF
0x180008ad6  mov     rax, [rsp+28h+arg_8]
0x180008adb  mov     [rdi+8], rax
0x180008adf  mov     rax, [rdi+8]
0x180008ae3  lea     rcx, [rax+20h]
0x180008ae7  neg     rax
0x180008aea  sbb     rdi, rdi
0x180008aed  and     rdi, rcx
0x180008af0  jz      short loc_180008B32
0x180008af2  call    cs:__imp_GetCurrentThreadId
0x180008af8  mov     r8d, eax
0x180008afb  mov     r9d, eax
0x180008afe  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008b08  shr     r8, 2
0x180008b0c  mul     r8
0x180008b0f  shr     rdx, 3
0x180008b13  lea     rcx, [rdx+rdx*4]
0x180008b17  add     rcx, rcx
0x180008b1a  sub     r8, rcx
0x180008b1d  mov     rbx, [rdi+r8*8+8]
0x180008b22  jmp     short loc_180008B2D
0x180008b24  cmp     [rbx], r9d
0x180008b27  jz      short loc_180008B40
0x180008b29  mov     rbx, [rbx+8]
0x180008b2d  test    rbx, rbx
0x180008b30  jnz     short loc_180008B24
0x180008b32  mov     rax, rbx
0x180008b35  mov     rbx, [rsp+28h+arg_0]
0x180008b3a  add     rsp, 20h
0x180008b3e  pop     rdi
0x180008b3f  retn
0x180008b40  add     rbx, 10h
0x180008b44  jz      short loc_180008B32
0x180008b46  cmp     qword ptr [rbx+8], 0
0x180008b4b  jnz     short loc_180008B32
0x180008b4d  lea     rax, [rdi+4]
0x180008b51  mov     [rbx+8], rax
0x180008b55  jmp     short loc_180008B32
```
