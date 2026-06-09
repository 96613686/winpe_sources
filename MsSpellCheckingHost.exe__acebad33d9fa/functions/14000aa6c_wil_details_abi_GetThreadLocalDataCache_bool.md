# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x14000aa6c`
- end: `0x14000ab27`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a310`

## callees

- `0x140009088`
- `0x14000aa6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000aac2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000aac2`

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
0x14000aa6c  mov     [rsp+arg_0], rbx
0x14000aa71  push    rdi
0x14000aa72  sub     rsp, 20h
0x14000aa76  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x14000aa7d  xor     ebx, ebx
0x14000aa7f  test    rdi, rdi
0x14000aa82  jz      short loc_14000AB02
0x14000aa84  cmp     [rdi+8], rbx
0x14000aa88  jnz     short loc_14000AAAF
0x14000aa8a  mov     rcx, [rdi]
0x14000aa8d  lea     rdx, [rsp+28h+arg_8]
0x14000aa92  mov     [rsp+28h+arg_8], rbx
0x14000aa97  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x14000aa9c  test    eax, eax
0x14000aa9e  js      short loc_14000AAAF
0x14000aaa0  cmp     [rdi+8], rbx
0x14000aaa4  jnz     short loc_14000AAAF
0x14000aaa6  mov     rax, [rsp+28h+arg_8]
0x14000aaab  mov     [rdi+8], rax
0x14000aaaf  mov     rax, [rdi+8]
0x14000aab3  lea     rcx, [rax+20h]
0x14000aab7  neg     rax
0x14000aaba  sbb     rdi, rdi
0x14000aabd  and     rdi, rcx
0x14000aac0  jz      short loc_14000AB02
0x14000aac2  call    cs:__imp_GetCurrentThreadId
0x14000aac8  mov     r8d, eax
0x14000aacb  mov     r9d, eax
0x14000aace  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000aad8  shr     r8, 2
0x14000aadc  mul     r8
0x14000aadf  shr     rdx, 3
0x14000aae3  lea     rcx, [rdx+rdx*4]
0x14000aae7  add     rcx, rcx
0x14000aaea  sub     r8, rcx
0x14000aaed  mov     rbx, [rdi+r8*8+8]
0x14000aaf2  jmp     short loc_14000AAFD
0x14000aaf4  cmp     [rbx], r9d
0x14000aaf7  jz      short loc_14000AB10
0x14000aaf9  mov     rbx, [rbx+8]
0x14000aafd  test    rbx, rbx
0x14000ab00  jnz     short loc_14000AAF4
0x14000ab02  mov     rax, rbx
0x14000ab05  mov     rbx, [rsp+28h+arg_0]
0x14000ab0a  add     rsp, 20h
0x14000ab0e  pop     rdi
0x14000ab0f  retn
0x14000ab10  add     rbx, 10h
0x14000ab14  jz      short loc_14000AB02
0x14000ab16  cmp     qword ptr [rbx+8], 0
0x14000ab1b  jnz     short loc_14000AB02
0x14000ab1d  lea     rax, [rdi+4]
0x14000ab21  mov     [rbx+8], rax
0x14000ab25  jmp     short loc_14000AB02
```
