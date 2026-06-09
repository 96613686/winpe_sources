# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18001ce60`
- end: `0x18001cf1b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001cb70`

## callees

- `0x18001c7b4`
- `0x18001ce60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ceb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ceb6`

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
0x18001ce60  mov     [rsp+arg_0], rbx
0x18001ce65  push    rdi
0x18001ce66  sub     rsp, 20h
0x18001ce6a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18001ce71  xor     ebx, ebx
0x18001ce73  test    rdi, rdi
0x18001ce76  jz      short loc_18001CEF6
0x18001ce78  cmp     [rdi+8], rbx
0x18001ce7c  jnz     short loc_18001CEA3
0x18001ce7e  mov     rcx, [rdi]
0x18001ce81  lea     rdx, [rsp+28h+arg_8]
0x18001ce86  mov     [rsp+28h+arg_8], rbx
0x18001ce8b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18001ce90  test    eax, eax
0x18001ce92  js      short loc_18001CEA3
0x18001ce94  cmp     [rdi+8], rbx
0x18001ce98  jnz     short loc_18001CEA3
0x18001ce9a  mov     rax, [rsp+28h+arg_8]
0x18001ce9f  mov     [rdi+8], rax
0x18001cea3  mov     rax, [rdi+8]
0x18001cea7  lea     rcx, [rax+20h]
0x18001ceab  neg     rax
0x18001ceae  sbb     rdi, rdi
0x18001ceb1  and     rdi, rcx
0x18001ceb4  jz      short loc_18001CEF6
0x18001ceb6  call    cs:__imp_GetCurrentThreadId
0x18001cebc  mov     r8d, eax
0x18001cebf  mov     r9d, eax
0x18001cec2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001cecc  shr     r8, 2
0x18001ced0  mul     r8
0x18001ced3  shr     rdx, 3
0x18001ced7  lea     rcx, [rdx+rdx*4]
0x18001cedb  add     rcx, rcx
0x18001cede  sub     r8, rcx
0x18001cee1  mov     rbx, [rdi+r8*8+8]
0x18001cee6  jmp     short loc_18001CEF1
0x18001cee8  cmp     [rbx], r9d
0x18001ceeb  jz      short loc_18001CF04
0x18001ceed  mov     rbx, [rbx+8]
0x18001cef1  test    rbx, rbx
0x18001cef4  jnz     short loc_18001CEE8
0x18001cef6  mov     rax, rbx
0x18001cef9  mov     rbx, [rsp+28h+arg_0]
0x18001cefe  add     rsp, 20h
0x18001cf02  pop     rdi
0x18001cf03  retn
0x18001cf04  add     rbx, 10h
0x18001cf08  jz      short loc_18001CEF6
0x18001cf0a  cmp     qword ptr [rbx+8], 0
0x18001cf0f  jnz     short loc_18001CEF6
0x18001cf11  lea     rax, [rdi+4]
0x18001cf15  mov     [rbx+8], rax
0x18001cf19  jmp     short loc_18001CEF6
```
