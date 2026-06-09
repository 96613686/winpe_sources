# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005988`
- end: `0x180005a45`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005340`

## callees

- `0x180004d48`
- `0x180005988`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800059e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800059e2`

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
0x180005988  mov     [rsp+arg_0], rbx
0x18000598d  push    rdi
0x18000598e  sub     rsp, 20h
0x180005992  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005999  xor     ebx, ebx
0x18000599b  test    rdi, rdi
0x18000599e  jz      loc_180005A37
0x1800059a4  cmp     [rdi+8], rbx
0x1800059a8  jnz     short loc_1800059CF
0x1800059aa  mov     rcx, [rdi]
0x1800059ad  lea     rdx, [rsp+28h+arg_8]
0x1800059b2  mov     [rsp+28h+arg_8], rbx
0x1800059b7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800059bc  test    eax, eax
0x1800059be  js      short loc_1800059CF
0x1800059c0  cmp     [rdi+8], rbx
0x1800059c4  jnz     short loc_1800059CF
0x1800059c6  mov     rax, [rsp+28h+arg_8]
0x1800059cb  mov     [rdi+8], rax
0x1800059cf  mov     rax, [rdi+8]
0x1800059d3  lea     rcx, [rax+20h]
0x1800059d7  neg     rax
0x1800059da  sbb     rdi, rdi
0x1800059dd  and     rdi, rcx
0x1800059e0  jz      short loc_180005A37
0x1800059e2  call    cs:__imp_GetCurrentThreadId
0x1800059e8  mov     r8d, eax
0x1800059eb  mov     r9d, eax
0x1800059ee  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800059f8  shr     r8, 2
0x1800059fc  mul     r8
0x1800059ff  shr     rdx, 3
0x180005a03  lea     rcx, [rdx+rdx*4]
0x180005a07  add     rcx, rcx
0x180005a0a  sub     r8, rcx
0x180005a0d  mov     rbx, [rdi+r8*8+8]
0x180005a12  test    rbx, rbx
0x180005a15  jz      short loc_180005A37
0x180005a17  cmp     [rbx], r9d
0x180005a1a  jz      short loc_180005A22
0x180005a1c  mov     rbx, [rbx+8]
0x180005a20  jmp     short loc_180005A12
0x180005a22  add     rbx, 10h
0x180005a26  jz      short loc_180005A37
0x180005a28  cmp     qword ptr [rbx+8], 0
0x180005a2d  jnz     short loc_180005A37
0x180005a2f  lea     rax, [rdi+4]
0x180005a33  mov     [rbx+8], rax
0x180005a37  mov     rax, rbx
0x180005a3a  mov     rbx, [rsp+28h+arg_0]
0x180005a3f  add     rsp, 20h
0x180005a43  pop     rdi
0x180005a44  retn
```
