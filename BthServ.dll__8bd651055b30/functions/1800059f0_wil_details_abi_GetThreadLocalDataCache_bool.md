# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800059f0`
- end: `0x180005aab`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005210`

## callees

- `0x180004148`
- `0x1800059f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a46`

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
0x1800059f0  mov     [rsp+arg_0], rbx
0x1800059f5  push    rdi
0x1800059f6  sub     rsp, 20h
0x1800059fa  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005a01  xor     ebx, ebx
0x180005a03  test    rdi, rdi
0x180005a06  jz      short loc_180005A86
0x180005a08  cmp     [rdi+8], rbx
0x180005a0c  jnz     short loc_180005A33
0x180005a0e  mov     rcx, [rdi]
0x180005a11  lea     rdx, [rsp+28h+arg_8]
0x180005a16  mov     [rsp+28h+arg_8], rbx
0x180005a1b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005a20  test    eax, eax
0x180005a22  js      short loc_180005A33
0x180005a24  cmp     [rdi+8], rbx
0x180005a28  jnz     short loc_180005A33
0x180005a2a  mov     rax, [rsp+28h+arg_8]
0x180005a2f  mov     [rdi+8], rax
0x180005a33  mov     rax, [rdi+8]
0x180005a37  lea     rcx, [rax+20h]
0x180005a3b  neg     rax
0x180005a3e  sbb     rdi, rdi
0x180005a41  and     rdi, rcx
0x180005a44  jz      short loc_180005A86
0x180005a46  call    cs:__imp_GetCurrentThreadId
0x180005a4c  mov     r8d, eax
0x180005a4f  mov     r9d, eax
0x180005a52  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005a5c  shr     r8, 2
0x180005a60  mul     r8
0x180005a63  shr     rdx, 3
0x180005a67  lea     rcx, [rdx+rdx*4]
0x180005a6b  add     rcx, rcx
0x180005a6e  sub     r8, rcx
0x180005a71  mov     rbx, [rdi+r8*8+8]
0x180005a76  jmp     short loc_180005A81
0x180005a78  cmp     [rbx], r9d
0x180005a7b  jz      short loc_180005A94
0x180005a7d  mov     rbx, [rbx+8]
0x180005a81  test    rbx, rbx
0x180005a84  jnz     short loc_180005A78
0x180005a86  mov     rax, rbx
0x180005a89  mov     rbx, [rsp+28h+arg_0]
0x180005a8e  add     rsp, 20h
0x180005a92  pop     rdi
0x180005a93  retn
0x180005a94  add     rbx, 10h
0x180005a98  jz      short loc_180005A86
0x180005a9a  cmp     qword ptr [rbx+8], 0
0x180005a9f  jnz     short loc_180005A86
0x180005aa1  lea     rax, [rdi+4]
0x180005aa5  mov     [rbx+8], rax
0x180005aa9  jmp     short loc_180005A86
```
