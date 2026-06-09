# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000801c`
- end: `0x1800080d9`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007ce0`

## callees

- `0x18000755c`
- `0x18000801c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008076`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008076`

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
0x18000801c  mov     [rsp+arg_0], rbx
0x180008021  push    rdi
0x180008022  sub     rsp, 20h
0x180008026  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000802d  xor     ebx, ebx
0x18000802f  test    rdi, rdi
0x180008032  jz      loc_1800080CB
0x180008038  cmp     [rdi+8], rbx
0x18000803c  jnz     short loc_180008063
0x18000803e  mov     rcx, [rdi]
0x180008041  lea     rdx, [rsp+28h+arg_8]
0x180008046  mov     [rsp+28h+arg_8], rbx
0x18000804b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180008050  test    eax, eax
0x180008052  js      short loc_180008063
0x180008054  cmp     [rdi+8], rbx
0x180008058  jnz     short loc_180008063
0x18000805a  mov     rax, [rsp+28h+arg_8]
0x18000805f  mov     [rdi+8], rax
0x180008063  mov     rax, [rdi+8]
0x180008067  lea     rcx, [rax+20h]
0x18000806b  neg     rax
0x18000806e  sbb     rdi, rdi
0x180008071  and     rdi, rcx
0x180008074  jz      short loc_1800080CB
0x180008076  call    cs:__imp_GetCurrentThreadId
0x18000807c  mov     r8d, eax
0x18000807f  mov     r9d, eax
0x180008082  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000808c  shr     r8, 2
0x180008090  mul     r8
0x180008093  shr     rdx, 3
0x180008097  lea     rcx, [rdx+rdx*4]
0x18000809b  add     rcx, rcx
0x18000809e  sub     r8, rcx
0x1800080a1  mov     rbx, [rdi+r8*8+8]
0x1800080a6  test    rbx, rbx
0x1800080a9  jz      short loc_1800080CB
0x1800080ab  cmp     [rbx], r9d
0x1800080ae  jz      short loc_1800080B6
0x1800080b0  mov     rbx, [rbx+8]
0x1800080b4  jmp     short loc_1800080A6
0x1800080b6  add     rbx, 10h
0x1800080ba  jz      short loc_1800080CB
0x1800080bc  cmp     qword ptr [rbx+8], 0
0x1800080c1  jnz     short loc_1800080CB
0x1800080c3  lea     rax, [rdi+4]
0x1800080c7  mov     [rbx+8], rax
0x1800080cb  mov     rax, rbx
0x1800080ce  mov     rbx, [rsp+28h+arg_0]
0x1800080d3  add     rsp, 20h
0x1800080d7  pop     rdi
0x1800080d8  retn
```
