# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180008100`
- end: `0x1800081bb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007920`

## callees

- `0x180006238`
- `0x180008100`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008156`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008156`

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
0x180008100  mov     [rsp+arg_0], rbx
0x180008105  push    rdi
0x180008106  sub     rsp, 20h
0x18000810a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180008111  xor     ebx, ebx
0x180008113  test    rdi, rdi
0x180008116  jz      short loc_180008196
0x180008118  cmp     [rdi+8], rbx
0x18000811c  jnz     short loc_180008143
0x18000811e  mov     rcx, [rdi]
0x180008121  lea     rdx, [rsp+28h+arg_8]
0x180008126  mov     [rsp+28h+arg_8], rbx
0x18000812b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180008130  test    eax, eax
0x180008132  js      short loc_180008143
0x180008134  cmp     [rdi+8], rbx
0x180008138  jnz     short loc_180008143
0x18000813a  mov     rax, [rsp+28h+arg_8]
0x18000813f  mov     [rdi+8], rax
0x180008143  mov     rax, [rdi+8]
0x180008147  lea     rcx, [rax+20h]
0x18000814b  neg     rax
0x18000814e  sbb     rdi, rdi
0x180008151  and     rdi, rcx
0x180008154  jz      short loc_180008196
0x180008156  call    cs:__imp_GetCurrentThreadId
0x18000815c  mov     r8d, eax
0x18000815f  mov     r9d, eax
0x180008162  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000816c  shr     r8, 2
0x180008170  mul     r8
0x180008173  shr     rdx, 3
0x180008177  lea     rcx, [rdx+rdx*4]
0x18000817b  add     rcx, rcx
0x18000817e  sub     r8, rcx
0x180008181  mov     rbx, [rdi+r8*8+8]
0x180008186  jmp     short loc_180008191
0x180008188  cmp     [rbx], r9d
0x18000818b  jz      short loc_1800081A4
0x18000818d  mov     rbx, [rbx+8]
0x180008191  test    rbx, rbx
0x180008194  jnz     short loc_180008188
0x180008196  mov     rax, rbx
0x180008199  mov     rbx, [rsp+28h+arg_0]
0x18000819e  add     rsp, 20h
0x1800081a2  pop     rdi
0x1800081a3  retn
0x1800081a4  add     rbx, 10h
0x1800081a8  jz      short loc_180008196
0x1800081aa  cmp     qword ptr [rbx+8], 0
0x1800081af  jnz     short loc_180008196
0x1800081b1  lea     rax, [rdi+4]
0x1800081b5  mov     [rbx+8], rax
0x1800081b9  jmp     short loc_180008196
```
