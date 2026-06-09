# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000d940`
- end: `0x18000da06`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d0e0`

## callees

- `0x18000b8cc`
- `0x18000d940`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d99a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d99a`

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
0x18000d940  mov     [rsp+arg_0], rbx
0x18000d945  push    rdi
0x18000d946  sub     rsp, 20h
0x18000d94a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000d951  xor     ebx, ebx
0x18000d953  test    rdi, rdi
0x18000d956  jz      loc_18000D9E0
0x18000d95c  cmp     [rdi+8], rbx
0x18000d960  jnz     short loc_18000D987
0x18000d962  mov     rcx, [rdi]
0x18000d965  lea     rdx, [rsp+28h+arg_8]
0x18000d96a  mov     [rsp+28h+arg_8], rbx
0x18000d96f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000d974  test    eax, eax
0x18000d976  js      short loc_18000D987
0x18000d978  cmp     [rdi+8], rbx
0x18000d97c  jnz     short loc_18000D987
0x18000d97e  mov     rax, [rsp+28h+arg_8]
0x18000d983  mov     [rdi+8], rax
0x18000d987  mov     rax, [rdi+8]
0x18000d98b  lea     rcx, [rax+20h]
0x18000d98f  neg     rax
0x18000d992  sbb     rdi, rdi
0x18000d995  and     rdi, rcx
0x18000d998  jz      short loc_18000D9E0
0x18000d99a  call    cs:__imp_GetCurrentThreadId
0x18000d9a1  nop     dword ptr [rax+rax+00h]
0x18000d9a6  mov     r8d, eax
0x18000d9a9  mov     r9d, eax
0x18000d9ac  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d9b6  shr     r8, 2
0x18000d9ba  mul     r8
0x18000d9bd  shr     rdx, 3
0x18000d9c1  lea     rcx, [rdx+rdx*4]
0x18000d9c5  add     rcx, rcx
0x18000d9c8  sub     r8, rcx
0x18000d9cb  mov     rbx, [rdi+r8*8+8]
0x18000d9d0  jmp     short loc_18000D9DB
0x18000d9d2  cmp     [rbx], r9d
0x18000d9d5  jz      short loc_18000D9EF
0x18000d9d7  mov     rbx, [rbx+8]
0x18000d9db  test    rbx, rbx
0x18000d9de  jnz     short loc_18000D9D2
0x18000d9e0  mov     rax, rbx
0x18000d9e3  mov     rbx, [rsp+28h+arg_0]
0x18000d9e8  add     rsp, 20h
0x18000d9ec  pop     rdi
0x18000d9ed  retn
0x18000d9ef  add     rbx, 10h
0x18000d9f3  jz      short loc_18000D9E0
0x18000d9f5  cmp     qword ptr [rbx+8], 0
0x18000d9fa  jnz     short loc_18000D9E0
0x18000d9fc  lea     rax, [rdi+4]
0x18000da00  mov     [rbx+8], rax
0x18000da04  jmp     short loc_18000D9E0
```
