# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000d914`
- end: `0x18000d9cf`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d030`

## callees

- `0x18000b848`
- `0x18000d914`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d96a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d96a`

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
0x18000d914  mov     [rsp+arg_0], rbx
0x18000d919  push    rdi
0x18000d91a  sub     rsp, 20h
0x18000d91e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000d925  xor     ebx, ebx
0x18000d927  test    rdi, rdi
0x18000d92a  jz      short loc_18000D9AA
0x18000d92c  cmp     [rdi+8], rbx
0x18000d930  jnz     short loc_18000D957
0x18000d932  mov     rcx, [rdi]
0x18000d935  lea     rdx, [rsp+28h+arg_8]
0x18000d93a  mov     [rsp+28h+arg_8], rbx
0x18000d93f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000d944  test    eax, eax
0x18000d946  js      short loc_18000D957
0x18000d948  cmp     [rdi+8], rbx
0x18000d94c  jnz     short loc_18000D957
0x18000d94e  mov     rax, [rsp+28h+arg_8]
0x18000d953  mov     [rdi+8], rax
0x18000d957  mov     rax, [rdi+8]
0x18000d95b  lea     rcx, [rax+20h]
0x18000d95f  neg     rax
0x18000d962  sbb     rdi, rdi
0x18000d965  and     rdi, rcx
0x18000d968  jz      short loc_18000D9AA
0x18000d96a  call    cs:__imp_GetCurrentThreadId
0x18000d970  mov     r8d, eax
0x18000d973  mov     r9d, eax
0x18000d976  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d980  shr     r8, 2
0x18000d984  mul     r8
0x18000d987  shr     rdx, 3
0x18000d98b  lea     rcx, [rdx+rdx*4]
0x18000d98f  add     rcx, rcx
0x18000d992  sub     r8, rcx
0x18000d995  mov     rbx, [rdi+r8*8+8]
0x18000d99a  jmp     short loc_18000D9A5
0x18000d99c  cmp     [rbx], r9d
0x18000d99f  jz      short loc_18000D9B8
0x18000d9a1  mov     rbx, [rbx+8]
0x18000d9a5  test    rbx, rbx
0x18000d9a8  jnz     short loc_18000D99C
0x18000d9aa  mov     rax, rbx
0x18000d9ad  mov     rbx, [rsp+28h+arg_0]
0x18000d9b2  add     rsp, 20h
0x18000d9b6  pop     rdi
0x18000d9b7  retn
0x18000d9b8  add     rbx, 10h
0x18000d9bc  jz      short loc_18000D9AA
0x18000d9be  cmp     qword ptr [rbx+8], 0
0x18000d9c3  jnz     short loc_18000D9AA
0x18000d9c5  lea     rax, [rdi+4]
0x18000d9c9  mov     [rbx+8], rax
0x18000d9cd  jmp     short loc_18000D9AA
```
