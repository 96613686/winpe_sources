# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180006d08`
- end: `0x180006dc5`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800063f0`

## callees

- `0x180004da8`
- `0x180006d08`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006d62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006d62`

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
0x180006d08  mov     [rsp+arg_0], rbx
0x180006d0d  push    rdi
0x180006d0e  sub     rsp, 20h
0x180006d12  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180006d19  xor     ebx, ebx
0x180006d1b  test    rdi, rdi
0x180006d1e  jz      loc_180006DB7
0x180006d24  cmp     [rdi+8], rbx
0x180006d28  jnz     short loc_180006D4F
0x180006d2a  mov     rcx, [rdi]
0x180006d2d  lea     rdx, [rsp+28h+arg_8]
0x180006d32  mov     [rsp+28h+arg_8], rbx
0x180006d37  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180006d3c  test    eax, eax
0x180006d3e  js      short loc_180006D4F
0x180006d40  cmp     [rdi+8], rbx
0x180006d44  jnz     short loc_180006D4F
0x180006d46  mov     rax, [rsp+28h+arg_8]
0x180006d4b  mov     [rdi+8], rax
0x180006d4f  mov     rax, [rdi+8]
0x180006d53  lea     rcx, [rax+20h]
0x180006d57  neg     rax
0x180006d5a  sbb     rdi, rdi
0x180006d5d  and     rdi, rcx
0x180006d60  jz      short loc_180006DB7
0x180006d62  call    cs:__imp_GetCurrentThreadId
0x180006d68  mov     r8d, eax
0x180006d6b  mov     r9d, eax
0x180006d6e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006d78  shr     r8, 2
0x180006d7c  mul     r8
0x180006d7f  shr     rdx, 3
0x180006d83  lea     rcx, [rdx+rdx*4]
0x180006d87  add     rcx, rcx
0x180006d8a  sub     r8, rcx
0x180006d8d  mov     rbx, [rdi+r8*8+8]
0x180006d92  test    rbx, rbx
0x180006d95  jz      short loc_180006DB7
0x180006d97  cmp     [rbx], r9d
0x180006d9a  jz      short loc_180006DA2
0x180006d9c  mov     rbx, [rbx+8]
0x180006da0  jmp     short loc_180006D92
0x180006da2  add     rbx, 10h
0x180006da6  jz      short loc_180006DB7
0x180006da8  cmp     qword ptr [rbx+8], 0
0x180006dad  jnz     short loc_180006DB7
0x180006daf  lea     rax, [rdi+4]
0x180006db3  mov     [rbx+8], rax
0x180006db7  mov     rax, rbx
0x180006dba  mov     rbx, [rsp+28h+arg_0]
0x180006dbf  add     rsp, 20h
0x180006dc3  pop     rdi
0x180006dc4  retn
```
