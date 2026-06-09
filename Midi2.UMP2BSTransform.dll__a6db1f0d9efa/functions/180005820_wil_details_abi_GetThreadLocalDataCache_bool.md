# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005820`
- end: `0x1800058db`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005040`

## callees

- `0x180003978`
- `0x180005820`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005876`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005876`

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
0x180005820  mov     [rsp+arg_0], rbx
0x180005825  push    rdi
0x180005826  sub     rsp, 20h
0x18000582a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005831  xor     ebx, ebx
0x180005833  test    rdi, rdi
0x180005836  jz      short loc_1800058B6
0x180005838  cmp     [rdi+8], rbx
0x18000583c  jnz     short loc_180005863
0x18000583e  mov     rcx, [rdi]
0x180005841  lea     rdx, [rsp+28h+arg_8]
0x180005846  mov     [rsp+28h+arg_8], rbx
0x18000584b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005850  test    eax, eax
0x180005852  js      short loc_180005863
0x180005854  cmp     [rdi+8], rbx
0x180005858  jnz     short loc_180005863
0x18000585a  mov     rax, [rsp+28h+arg_8]
0x18000585f  mov     [rdi+8], rax
0x180005863  mov     rax, [rdi+8]
0x180005867  lea     rcx, [rax+20h]
0x18000586b  neg     rax
0x18000586e  sbb     rdi, rdi
0x180005871  and     rdi, rcx
0x180005874  jz      short loc_1800058B6
0x180005876  call    cs:__imp_GetCurrentThreadId
0x18000587c  mov     r8d, eax
0x18000587f  mov     r9d, eax
0x180005882  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000588c  shr     r8, 2
0x180005890  mul     r8
0x180005893  shr     rdx, 3
0x180005897  lea     rcx, [rdx+rdx*4]
0x18000589b  add     rcx, rcx
0x18000589e  sub     r8, rcx
0x1800058a1  mov     rbx, [rdi+r8*8+8]
0x1800058a6  jmp     short loc_1800058B1
0x1800058a8  cmp     [rbx], r9d
0x1800058ab  jz      short loc_1800058C4
0x1800058ad  mov     rbx, [rbx+8]
0x1800058b1  test    rbx, rbx
0x1800058b4  jnz     short loc_1800058A8
0x1800058b6  mov     rax, rbx
0x1800058b9  mov     rbx, [rsp+28h+arg_0]
0x1800058be  add     rsp, 20h
0x1800058c2  pop     rdi
0x1800058c3  retn
0x1800058c4  add     rbx, 10h
0x1800058c8  jz      short loc_1800058B6
0x1800058ca  cmp     qword ptr [rbx+8], 0
0x1800058cf  jnz     short loc_1800058B6
0x1800058d1  lea     rax, [rdi+4]
0x1800058d5  mov     [rbx+8], rax
0x1800058d9  jmp     short loc_1800058B6
```
