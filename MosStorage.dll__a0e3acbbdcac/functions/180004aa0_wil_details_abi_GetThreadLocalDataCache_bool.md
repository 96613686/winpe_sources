# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004aa0`
- end: `0x180004b5b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800042c0`

## callees

- `0x180003c14`
- `0x180004aa0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004af6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004af6`

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
0x180004aa0  mov     [rsp+arg_0], rbx
0x180004aa5  push    rdi
0x180004aa6  sub     rsp, 20h
0x180004aaa  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004ab1  xor     ebx, ebx
0x180004ab3  test    rdi, rdi
0x180004ab6  jz      short loc_180004B36
0x180004ab8  cmp     [rdi+8], rbx
0x180004abc  jnz     short loc_180004AE3
0x180004abe  mov     rcx, [rdi]
0x180004ac1  lea     rdx, [rsp+28h+arg_8]
0x180004ac6  mov     [rsp+28h+arg_8], rbx
0x180004acb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004ad0  test    eax, eax
0x180004ad2  js      short loc_180004AE3
0x180004ad4  cmp     [rdi+8], rbx
0x180004ad8  jnz     short loc_180004AE3
0x180004ada  mov     rax, [rsp+28h+arg_8]
0x180004adf  mov     [rdi+8], rax
0x180004ae3  mov     rax, [rdi+8]
0x180004ae7  lea     rcx, [rax+20h]
0x180004aeb  neg     rax
0x180004aee  sbb     rdi, rdi
0x180004af1  and     rdi, rcx
0x180004af4  jz      short loc_180004B36
0x180004af6  call    cs:__imp_GetCurrentThreadId
0x180004afc  mov     r8d, eax
0x180004aff  mov     r9d, eax
0x180004b02  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004b0c  shr     r8, 2
0x180004b10  mul     r8
0x180004b13  shr     rdx, 3
0x180004b17  lea     rcx, [rdx+rdx*4]
0x180004b1b  add     rcx, rcx
0x180004b1e  sub     r8, rcx
0x180004b21  mov     rbx, [rdi+r8*8+8]
0x180004b26  jmp     short loc_180004B31
0x180004b28  cmp     [rbx], r9d
0x180004b2b  jz      short loc_180004B44
0x180004b2d  mov     rbx, [rbx+8]
0x180004b31  test    rbx, rbx
0x180004b34  jnz     short loc_180004B28
0x180004b36  mov     rax, rbx
0x180004b39  mov     rbx, [rsp+28h+arg_0]
0x180004b3e  add     rsp, 20h
0x180004b42  pop     rdi
0x180004b43  retn
0x180004b44  add     rbx, 10h
0x180004b48  jz      short loc_180004B36
0x180004b4a  cmp     qword ptr [rbx+8], 0
0x180004b4f  jnz     short loc_180004B36
0x180004b51  lea     rax, [rdi+4]
0x180004b55  mov     [rbx+8], rax
0x180004b59  jmp     short loc_180004B36
```
