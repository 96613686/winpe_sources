# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180006324`
- end: `0x1800063e1`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005c20`

## callees

- `0x1800051e8`
- `0x180006324`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000637e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000637e`

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
0x180006324  mov     [rsp+arg_0], rbx
0x180006329  push    rdi
0x18000632a  sub     rsp, 20h
0x18000632e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180006335  xor     ebx, ebx
0x180006337  test    rdi, rdi
0x18000633a  jz      loc_1800063D3
0x180006340  cmp     [rdi+8], rbx
0x180006344  jnz     short loc_18000636B
0x180006346  mov     rcx, [rdi]
0x180006349  lea     rdx, [rsp+28h+arg_8]
0x18000634e  mov     [rsp+28h+arg_8], rbx
0x180006353  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180006358  test    eax, eax
0x18000635a  js      short loc_18000636B
0x18000635c  cmp     [rdi+8], rbx
0x180006360  jnz     short loc_18000636B
0x180006362  mov     rax, [rsp+28h+arg_8]
0x180006367  mov     [rdi+8], rax
0x18000636b  mov     rax, [rdi+8]
0x18000636f  lea     rcx, [rax+20h]
0x180006373  neg     rax
0x180006376  sbb     rdi, rdi
0x180006379  and     rdi, rcx
0x18000637c  jz      short loc_1800063D3
0x18000637e  call    cs:__imp_GetCurrentThreadId
0x180006384  mov     r8d, eax
0x180006387  mov     r9d, eax
0x18000638a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006394  shr     r8, 2
0x180006398  mul     r8
0x18000639b  shr     rdx, 3
0x18000639f  lea     rcx, [rdx+rdx*4]
0x1800063a3  add     rcx, rcx
0x1800063a6  sub     r8, rcx
0x1800063a9  mov     rbx, [rdi+r8*8+8]
0x1800063ae  test    rbx, rbx
0x1800063b1  jz      short loc_1800063D3
0x1800063b3  cmp     [rbx], r9d
0x1800063b6  jz      short loc_1800063BE
0x1800063b8  mov     rbx, [rbx+8]
0x1800063bc  jmp     short loc_1800063AE
0x1800063be  add     rbx, 10h
0x1800063c2  jz      short loc_1800063D3
0x1800063c4  cmp     qword ptr [rbx+8], 0
0x1800063c9  jnz     short loc_1800063D3
0x1800063cb  lea     rax, [rdi+4]
0x1800063cf  mov     [rbx+8], rax
0x1800063d3  mov     rax, rbx
0x1800063d6  mov     rbx, [rsp+28h+arg_0]
0x1800063db  add     rsp, 20h
0x1800063df  pop     rdi
0x1800063e0  retn
```
