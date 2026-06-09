# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800081a8`
- end: `0x18000825f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `183`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008370`

## callees

- `0x1800081a8`
- `0x180009ac4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800081fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800081fe`

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
      for ( i = *(_QWORD *)(v4 + 8 * (CurrentThreadId % 0xAuLL) + 8); i; i = *(_QWORD *)(i + 8) )
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
0x1800081a8  mov     [rsp+arg_0], rbx
0x1800081ad  push    rdi
0x1800081ae  sub     rsp, 20h
0x1800081b2  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800081b9  xor     ebx, ebx
0x1800081bb  test    rdi, rdi
0x1800081be  jz      short loc_18000823A
0x1800081c0  cmp     [rdi+8], rbx
0x1800081c4  jnz     short loc_1800081EB
0x1800081c6  mov     rcx, [rdi]
0x1800081c9  lea     rdx, [rsp+28h+arg_8]
0x1800081ce  mov     [rsp+28h+arg_8], rbx
0x1800081d3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800081d8  test    eax, eax
0x1800081da  js      short loc_1800081EB
0x1800081dc  cmp     [rdi+8], rbx
0x1800081e0  jnz     short loc_1800081EB
0x1800081e2  mov     rax, [rsp+28h+arg_8]
0x1800081e7  mov     [rdi+8], rax
0x1800081eb  mov     rax, [rdi+8]
0x1800081ef  lea     rcx, [rax+20h]
0x1800081f3  neg     rax
0x1800081f6  sbb     rdi, rdi
0x1800081f9  and     rdi, rcx
0x1800081fc  jz      short loc_18000823A
0x1800081fe  call    cs:__imp_GetCurrentThreadId
0x180008204  mov     r8d, eax
0x180008207  mov     r9d, eax
0x18000820a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008214  mul     r9
0x180008217  shr     rdx, 3
0x18000821b  lea     rcx, [rdx+rdx*4]
0x18000821f  add     rcx, rcx
0x180008222  sub     r8, rcx
0x180008225  mov     rbx, [rdi+r8*8+8]
0x18000822a  jmp     short loc_180008235
0x18000822c  cmp     [rbx], r9d
0x18000822f  jz      short loc_180008248
0x180008231  mov     rbx, [rbx+8]
0x180008235  test    rbx, rbx
0x180008238  jnz     short loc_18000822C
0x18000823a  mov     rax, rbx
0x18000823d  mov     rbx, [rsp+28h+arg_0]
0x180008242  add     rsp, 20h
0x180008246  pop     rdi
0x180008247  retn
0x180008248  add     rbx, 10h
0x18000824c  jz      short loc_18000823A
0x18000824e  cmp     qword ptr [rbx+8], 0
0x180008253  jnz     short loc_18000823A
0x180008255  lea     rax, [rdi+4]
0x180008259  mov     [rbx+8], rax
0x18000825d  jmp     short loc_18000823A
```
