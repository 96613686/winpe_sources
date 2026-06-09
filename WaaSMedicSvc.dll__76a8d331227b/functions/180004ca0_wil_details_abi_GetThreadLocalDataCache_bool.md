# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004ca0`
- end: `0x180004d5b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800044c0`

## callees

- `0x180003dd8`
- `0x180004ca0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004cf6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004cf6`

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
0x180004ca0  mov     [rsp+arg_0], rbx
0x180004ca5  push    rdi
0x180004ca6  sub     rsp, 20h
0x180004caa  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004cb1  xor     ebx, ebx
0x180004cb3  test    rdi, rdi
0x180004cb6  jz      short loc_180004D36
0x180004cb8  cmp     [rdi+8], rbx
0x180004cbc  jnz     short loc_180004CE3
0x180004cbe  mov     rcx, [rdi]
0x180004cc1  lea     rdx, [rsp+28h+arg_8]
0x180004cc6  mov     [rsp+28h+arg_8], rbx
0x180004ccb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004cd0  test    eax, eax
0x180004cd2  js      short loc_180004CE3
0x180004cd4  cmp     [rdi+8], rbx
0x180004cd8  jnz     short loc_180004CE3
0x180004cda  mov     rax, [rsp+28h+arg_8]
0x180004cdf  mov     [rdi+8], rax
0x180004ce3  mov     rax, [rdi+8]
0x180004ce7  lea     rcx, [rax+20h]
0x180004ceb  neg     rax
0x180004cee  sbb     rdi, rdi
0x180004cf1  and     rdi, rcx
0x180004cf4  jz      short loc_180004D36
0x180004cf6  call    cs:__imp_GetCurrentThreadId
0x180004cfc  mov     r8d, eax
0x180004cff  mov     r9d, eax
0x180004d02  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004d0c  shr     r8, 2
0x180004d10  mul     r8
0x180004d13  shr     rdx, 3
0x180004d17  lea     rcx, [rdx+rdx*4]
0x180004d1b  add     rcx, rcx
0x180004d1e  sub     r8, rcx
0x180004d21  mov     rbx, [rdi+r8*8+8]
0x180004d26  jmp     short loc_180004D31
0x180004d28  cmp     [rbx], r9d
0x180004d2b  jz      short loc_180004D44
0x180004d2d  mov     rbx, [rbx+8]
0x180004d31  test    rbx, rbx
0x180004d34  jnz     short loc_180004D28
0x180004d36  mov     rax, rbx
0x180004d39  mov     rbx, [rsp+28h+arg_0]
0x180004d3e  add     rsp, 20h
0x180004d42  pop     rdi
0x180004d43  retn
0x180004d44  add     rbx, 10h
0x180004d48  jz      short loc_180004D36
0x180004d4a  cmp     qword ptr [rbx+8], 0
0x180004d4f  jnz     short loc_180004D36
0x180004d51  lea     rax, [rdi+4]
0x180004d55  mov     [rbx+8], rax
0x180004d59  jmp     short loc_180004D36
```
