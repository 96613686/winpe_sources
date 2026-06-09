# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18002adb4`
- end: `0x18002ae6f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002a5f0`

## callees

- `0x180028a60`
- `0x18002adb4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ae0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ae0a`

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
0x18002adb4  mov     [rsp+arg_0], rbx
0x18002adb9  push    rdi
0x18002adba  sub     rsp, 20h
0x18002adbe  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18002adc5  xor     ebx, ebx
0x18002adc7  test    rdi, rdi
0x18002adca  jz      short loc_18002AE4A
0x18002adcc  cmp     [rdi+8], rbx
0x18002add0  jnz     short loc_18002ADF7
0x18002add2  mov     rcx, [rdi]
0x18002add5  lea     rdx, [rsp+28h+arg_8]
0x18002adda  mov     [rsp+28h+arg_8], rbx
0x18002addf  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18002ade4  test    eax, eax
0x18002ade6  js      short loc_18002ADF7
0x18002ade8  cmp     [rdi+8], rbx
0x18002adec  jnz     short loc_18002ADF7
0x18002adee  mov     rax, [rsp+28h+arg_8]
0x18002adf3  mov     [rdi+8], rax
0x18002adf7  mov     rax, [rdi+8]
0x18002adfb  lea     rcx, [rax+20h]
0x18002adff  neg     rax
0x18002ae02  sbb     rdi, rdi
0x18002ae05  and     rdi, rcx
0x18002ae08  jz      short loc_18002AE4A
0x18002ae0a  call    cs:__imp_GetCurrentThreadId
0x18002ae10  mov     r8d, eax
0x18002ae13  mov     r9d, eax
0x18002ae16  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002ae20  shr     r8, 2
0x18002ae24  mul     r8
0x18002ae27  shr     rdx, 3
0x18002ae2b  lea     rcx, [rdx+rdx*4]
0x18002ae2f  add     rcx, rcx
0x18002ae32  sub     r8, rcx
0x18002ae35  mov     rbx, [rdi+r8*8+8]
0x18002ae3a  jmp     short loc_18002AE45
0x18002ae3c  cmp     [rbx], r9d
0x18002ae3f  jz      short loc_18002AE58
0x18002ae41  mov     rbx, [rbx+8]
0x18002ae45  test    rbx, rbx
0x18002ae48  jnz     short loc_18002AE3C
0x18002ae4a  mov     rax, rbx
0x18002ae4d  mov     rbx, [rsp+28h+arg_0]
0x18002ae52  add     rsp, 20h
0x18002ae56  pop     rdi
0x18002ae57  retn
0x18002ae58  add     rbx, 10h
0x18002ae5c  jz      short loc_18002AE4A
0x18002ae5e  cmp     qword ptr [rbx+8], 0
0x18002ae63  jnz     short loc_18002AE4A
0x18002ae65  lea     rax, [rdi+4]
0x18002ae69  mov     [rbx+8], rax
0x18002ae6d  jmp     short loc_18002AE4A
```
