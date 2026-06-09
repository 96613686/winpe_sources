# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000cef0`
- end: `0x18000cfad`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c2b0`

## callees

- `0x18000ad4c`
- `0x18000cef0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cf4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cf4a`

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
0x18000cef0  mov     [rsp+arg_0], rbx
0x18000cef5  push    rdi
0x18000cef6  sub     rsp, 20h
0x18000cefa  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000cf01  xor     ebx, ebx
0x18000cf03  test    rdi, rdi
0x18000cf06  jz      loc_18000CF9F
0x18000cf0c  cmp     [rdi+8], rbx
0x18000cf10  jnz     short loc_18000CF37
0x18000cf12  mov     rcx, [rdi]
0x18000cf15  lea     rdx, [rsp+28h+arg_8]
0x18000cf1a  mov     [rsp+28h+arg_8], rbx
0x18000cf1f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000cf24  test    eax, eax
0x18000cf26  js      short loc_18000CF37
0x18000cf28  cmp     [rdi+8], rbx
0x18000cf2c  jnz     short loc_18000CF37
0x18000cf2e  mov     rax, [rsp+28h+arg_8]
0x18000cf33  mov     [rdi+8], rax
0x18000cf37  mov     rax, [rdi+8]
0x18000cf3b  lea     rcx, [rax+20h]
0x18000cf3f  neg     rax
0x18000cf42  sbb     rdi, rdi
0x18000cf45  and     rdi, rcx
0x18000cf48  jz      short loc_18000CF9F
0x18000cf4a  call    cs:__imp_GetCurrentThreadId
0x18000cf50  mov     r8d, eax
0x18000cf53  mov     r9d, eax
0x18000cf56  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000cf60  shr     r8, 2
0x18000cf64  mul     r8
0x18000cf67  shr     rdx, 3
0x18000cf6b  lea     rcx, [rdx+rdx*4]
0x18000cf6f  add     rcx, rcx
0x18000cf72  sub     r8, rcx
0x18000cf75  mov     rbx, [rdi+r8*8+8]
0x18000cf7a  test    rbx, rbx
0x18000cf7d  jz      short loc_18000CF9F
0x18000cf7f  cmp     [rbx], r9d
0x18000cf82  jz      short loc_18000CF8A
0x18000cf84  mov     rbx, [rbx+8]
0x18000cf88  jmp     short loc_18000CF7A
0x18000cf8a  add     rbx, 10h
0x18000cf8e  jz      short loc_18000CF9F
0x18000cf90  cmp     qword ptr [rbx+8], 0
0x18000cf95  jnz     short loc_18000CF9F
0x18000cf97  lea     rax, [rdi+4]
0x18000cf9b  mov     [rbx+8], rax
0x18000cf9f  mov     rax, rbx
0x18000cfa2  mov     rbx, [rsp+28h+arg_0]
0x18000cfa7  add     rsp, 20h
0x18000cfab  pop     rdi
0x18000cfac  retn
```
