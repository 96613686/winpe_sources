# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000ab20`
- end: `0x18000abe4`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `196`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a3f0`

## callees

- `0x180007b34`
- `0x18000ab20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ab7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ab7a`

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
0x18000ab20  mov     [rsp+arg_0], rbx
0x18000ab25  push    rdi
0x18000ab26  sub     rsp, 20h
0x18000ab2a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000ab31  xor     ebx, ebx
0x18000ab33  test    rdi, rdi
0x18000ab36  jz      loc_18000ABD5
0x18000ab3c  cmp     [rdi+8], rbx
0x18000ab40  jnz     short loc_18000AB67
0x18000ab42  mov     rcx, [rdi]
0x18000ab45  lea     rdx, [rsp+28h+arg_8]
0x18000ab4a  mov     [rsp+28h+arg_8], rbx
0x18000ab4f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000ab54  test    eax, eax
0x18000ab56  js      short loc_18000AB67
0x18000ab58  cmp     [rdi+8], rbx
0x18000ab5c  jnz     short loc_18000AB67
0x18000ab5e  mov     rax, [rsp+28h+arg_8]
0x18000ab63  mov     [rdi+8], rax
0x18000ab67  mov     rax, [rdi+8]
0x18000ab6b  lea     rcx, [rax+20h]
0x18000ab6f  neg     rax
0x18000ab72  sbb     rdi, rdi
0x18000ab75  and     rdi, rcx
0x18000ab78  jz      short loc_18000ABD5
0x18000ab7a  call    cs:__imp_GetCurrentThreadId
0x18000ab81  nop     dword ptr [rax+rax+00h]
0x18000ab86  mov     r8d, eax
0x18000ab89  mov     r9d, eax
0x18000ab8c  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000ab96  shr     r8, 2
0x18000ab9a  mul     r8
0x18000ab9d  shr     rdx, 3
0x18000aba1  lea     rcx, [rdx+rdx*4]
0x18000aba5  add     rcx, rcx
0x18000aba8  sub     r8, rcx
0x18000abab  mov     rbx, [rdi+r8*8+8]
0x18000abb0  test    rbx, rbx
0x18000abb3  jz      short loc_18000ABD5
0x18000abb5  cmp     [rbx], r9d
0x18000abb8  jz      short loc_18000ABC0
0x18000abba  mov     rbx, [rbx+8]
0x18000abbe  jmp     short loc_18000ABB0
0x18000abc0  add     rbx, 10h
0x18000abc4  jz      short loc_18000ABD5
0x18000abc6  cmp     qword ptr [rbx+8], 0
0x18000abcb  jnz     short loc_18000ABD5
0x18000abcd  lea     rax, [rdi+4]
0x18000abd1  mov     [rbx+8], rax
0x18000abd5  mov     rax, rbx
0x18000abd8  mov     rbx, [rsp+28h+arg_0]
0x18000abdd  add     rsp, 20h
0x18000abe1  pop     rdi
0x18000abe2  retn
```
