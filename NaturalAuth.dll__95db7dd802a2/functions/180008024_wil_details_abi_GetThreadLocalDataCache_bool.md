# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180008024`
- end: `0x1800080e1`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007940`

## callees

- `0x180007298`
- `0x180008024`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000807e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000807e`

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
0x180008024  mov     [rsp+arg_0], rbx
0x180008029  push    rdi
0x18000802a  sub     rsp, 20h
0x18000802e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180008035  xor     ebx, ebx
0x180008037  test    rdi, rdi
0x18000803a  jz      loc_1800080D3
0x180008040  cmp     [rdi+8], rbx
0x180008044  jnz     short loc_18000806B
0x180008046  mov     rcx, [rdi]
0x180008049  lea     rdx, [rsp+28h+arg_8]
0x18000804e  mov     [rsp+28h+arg_8], rbx
0x180008053  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180008058  test    eax, eax
0x18000805a  js      short loc_18000806B
0x18000805c  cmp     [rdi+8], rbx
0x180008060  jnz     short loc_18000806B
0x180008062  mov     rax, [rsp+28h+arg_8]
0x180008067  mov     [rdi+8], rax
0x18000806b  mov     rax, [rdi+8]
0x18000806f  lea     rcx, [rax+20h]
0x180008073  neg     rax
0x180008076  sbb     rdi, rdi
0x180008079  and     rdi, rcx
0x18000807c  jz      short loc_1800080D3
0x18000807e  call    cs:__imp_GetCurrentThreadId
0x180008084  mov     r8d, eax
0x180008087  mov     r9d, eax
0x18000808a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008094  shr     r8, 2
0x180008098  mul     r8
0x18000809b  shr     rdx, 3
0x18000809f  lea     rcx, [rdx+rdx*4]
0x1800080a3  add     rcx, rcx
0x1800080a6  sub     r8, rcx
0x1800080a9  mov     rbx, [rdi+r8*8+8]
0x1800080ae  test    rbx, rbx
0x1800080b1  jz      short loc_1800080D3
0x1800080b3  cmp     [rbx], r9d
0x1800080b6  jz      short loc_1800080BE
0x1800080b8  mov     rbx, [rbx+8]
0x1800080bc  jmp     short loc_1800080AE
0x1800080be  add     rbx, 10h
0x1800080c2  jz      short loc_1800080D3
0x1800080c4  cmp     qword ptr [rbx+8], 0
0x1800080c9  jnz     short loc_1800080D3
0x1800080cb  lea     rax, [rdi+4]
0x1800080cf  mov     [rbx+8], rax
0x1800080d3  mov     rax, rbx
0x1800080d6  mov     rbx, [rsp+28h+arg_0]
0x1800080db  add     rsp, 20h
0x1800080df  pop     rdi
0x1800080e0  retn
```
