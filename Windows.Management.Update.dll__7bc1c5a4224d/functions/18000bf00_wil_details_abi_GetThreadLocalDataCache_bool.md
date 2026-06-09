# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000bf00`
- end: `0x18000bfbb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b720`

## callees

- `0x18000a1f8`
- `0x18000bf00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bf56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bf56`

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
0x18000bf00  mov     [rsp+arg_0], rbx
0x18000bf05  push    rdi
0x18000bf06  sub     rsp, 20h
0x18000bf0a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000bf11  xor     ebx, ebx
0x18000bf13  test    rdi, rdi
0x18000bf16  jz      short loc_18000BF96
0x18000bf18  cmp     [rdi+8], rbx
0x18000bf1c  jnz     short loc_18000BF43
0x18000bf1e  mov     rcx, [rdi]
0x18000bf21  lea     rdx, [rsp+28h+arg_8]
0x18000bf26  mov     [rsp+28h+arg_8], rbx
0x18000bf2b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000bf30  test    eax, eax
0x18000bf32  js      short loc_18000BF43
0x18000bf34  cmp     [rdi+8], rbx
0x18000bf38  jnz     short loc_18000BF43
0x18000bf3a  mov     rax, [rsp+28h+arg_8]
0x18000bf3f  mov     [rdi+8], rax
0x18000bf43  mov     rax, [rdi+8]
0x18000bf47  lea     rcx, [rax+20h]
0x18000bf4b  neg     rax
0x18000bf4e  sbb     rdi, rdi
0x18000bf51  and     rdi, rcx
0x18000bf54  jz      short loc_18000BF96
0x18000bf56  call    cs:__imp_GetCurrentThreadId
0x18000bf5c  mov     r8d, eax
0x18000bf5f  mov     r9d, eax
0x18000bf62  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000bf6c  shr     r8, 2
0x18000bf70  mul     r8
0x18000bf73  shr     rdx, 3
0x18000bf77  lea     rcx, [rdx+rdx*4]
0x18000bf7b  add     rcx, rcx
0x18000bf7e  sub     r8, rcx
0x18000bf81  mov     rbx, [rdi+r8*8+8]
0x18000bf86  jmp     short loc_18000BF91
0x18000bf88  cmp     [rbx], r9d
0x18000bf8b  jz      short loc_18000BFA4
0x18000bf8d  mov     rbx, [rbx+8]
0x18000bf91  test    rbx, rbx
0x18000bf94  jnz     short loc_18000BF88
0x18000bf96  mov     rax, rbx
0x18000bf99  mov     rbx, [rsp+28h+arg_0]
0x18000bf9e  add     rsp, 20h
0x18000bfa2  pop     rdi
0x18000bfa3  retn
0x18000bfa4  add     rbx, 10h
0x18000bfa8  jz      short loc_18000BF96
0x18000bfaa  cmp     qword ptr [rbx+8], 0
0x18000bfaf  jnz     short loc_18000BF96
0x18000bfb1  lea     rax, [rdi+4]
0x18000bfb5  mov     [rbx+8], rax
0x18000bfb9  jmp     short loc_18000BF96
```
