# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004c74`
- end: `0x180004d2f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004500`

## callees

- `0x180003ad0`
- `0x180004c74`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004cca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004cca`

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
0x180004c74  mov     [rsp+arg_0], rbx
0x180004c79  push    rdi
0x180004c7a  sub     rsp, 20h
0x180004c7e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004c85  xor     ebx, ebx
0x180004c87  test    rdi, rdi
0x180004c8a  jz      short loc_180004D0A
0x180004c8c  cmp     [rdi+8], rbx
0x180004c90  jnz     short loc_180004CB7
0x180004c92  mov     rcx, [rdi]
0x180004c95  lea     rdx, [rsp+28h+arg_8]
0x180004c9a  mov     [rsp+28h+arg_8], rbx
0x180004c9f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004ca4  test    eax, eax
0x180004ca6  js      short loc_180004CB7
0x180004ca8  cmp     [rdi+8], rbx
0x180004cac  jnz     short loc_180004CB7
0x180004cae  mov     rax, [rsp+28h+arg_8]
0x180004cb3  mov     [rdi+8], rax
0x180004cb7  mov     rax, [rdi+8]
0x180004cbb  lea     rcx, [rax+20h]
0x180004cbf  neg     rax
0x180004cc2  sbb     rdi, rdi
0x180004cc5  and     rdi, rcx
0x180004cc8  jz      short loc_180004D0A
0x180004cca  call    cs:__imp_GetCurrentThreadId
0x180004cd0  mov     r8d, eax
0x180004cd3  mov     r9d, eax
0x180004cd6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004ce0  shr     r8, 2
0x180004ce4  mul     r8
0x180004ce7  shr     rdx, 3
0x180004ceb  lea     rcx, [rdx+rdx*4]
0x180004cef  add     rcx, rcx
0x180004cf2  sub     r8, rcx
0x180004cf5  mov     rbx, [rdi+r8*8+8]
0x180004cfa  jmp     short loc_180004D05
0x180004cfc  cmp     [rbx], r9d
0x180004cff  jz      short loc_180004D18
0x180004d01  mov     rbx, [rbx+8]
0x180004d05  test    rbx, rbx
0x180004d08  jnz     short loc_180004CFC
0x180004d0a  mov     rax, rbx
0x180004d0d  mov     rbx, [rsp+28h+arg_0]
0x180004d12  add     rsp, 20h
0x180004d16  pop     rdi
0x180004d17  retn
0x180004d18  add     rbx, 10h
0x180004d1c  jz      short loc_180004D0A
0x180004d1e  cmp     qword ptr [rbx+8], 0
0x180004d23  jnz     short loc_180004D0A
0x180004d25  lea     rax, [rdi+4]
0x180004d29  mov     [rbx+8], rax
0x180004d2d  jmp     short loc_180004D0A
```
