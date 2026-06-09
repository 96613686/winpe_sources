# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005930`
- end: `0x1800059eb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005150`

## callees

- `0x180003a88`
- `0x180005930`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005986`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005986`

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
0x180005930  mov     [rsp+arg_0], rbx
0x180005935  push    rdi
0x180005936  sub     rsp, 20h
0x18000593a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005941  xor     ebx, ebx
0x180005943  test    rdi, rdi
0x180005946  jz      short loc_1800059C6
0x180005948  cmp     [rdi+8], rbx
0x18000594c  jnz     short loc_180005973
0x18000594e  mov     rcx, [rdi]
0x180005951  lea     rdx, [rsp+28h+arg_8]
0x180005956  mov     [rsp+28h+arg_8], rbx
0x18000595b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005960  test    eax, eax
0x180005962  js      short loc_180005973
0x180005964  cmp     [rdi+8], rbx
0x180005968  jnz     short loc_180005973
0x18000596a  mov     rax, [rsp+28h+arg_8]
0x18000596f  mov     [rdi+8], rax
0x180005973  mov     rax, [rdi+8]
0x180005977  lea     rcx, [rax+20h]
0x18000597b  neg     rax
0x18000597e  sbb     rdi, rdi
0x180005981  and     rdi, rcx
0x180005984  jz      short loc_1800059C6
0x180005986  call    cs:__imp_GetCurrentThreadId
0x18000598c  mov     r8d, eax
0x18000598f  mov     r9d, eax
0x180005992  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000599c  shr     r8, 2
0x1800059a0  mul     r8
0x1800059a3  shr     rdx, 3
0x1800059a7  lea     rcx, [rdx+rdx*4]
0x1800059ab  add     rcx, rcx
0x1800059ae  sub     r8, rcx
0x1800059b1  mov     rbx, [rdi+r8*8+8]
0x1800059b6  jmp     short loc_1800059C1
0x1800059b8  cmp     [rbx], r9d
0x1800059bb  jz      short loc_1800059D4
0x1800059bd  mov     rbx, [rbx+8]
0x1800059c1  test    rbx, rbx
0x1800059c4  jnz     short loc_1800059B8
0x1800059c6  mov     rax, rbx
0x1800059c9  mov     rbx, [rsp+28h+arg_0]
0x1800059ce  add     rsp, 20h
0x1800059d2  pop     rdi
0x1800059d3  retn
0x1800059d4  add     rbx, 10h
0x1800059d8  jz      short loc_1800059C6
0x1800059da  cmp     qword ptr [rbx+8], 0
0x1800059df  jnz     short loc_1800059C6
0x1800059e1  lea     rax, [rdi+4]
0x1800059e5  mov     [rbx+8], rax
0x1800059e9  jmp     short loc_1800059C6
```
