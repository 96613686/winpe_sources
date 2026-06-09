# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180052dac`
- end: `0x180052e69`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800522b0`

## callees

- `0x1800515e8`
- `0x180052dac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052e06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052e06`

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
0x180052dac  mov     [rsp+arg_0], rbx
0x180052db1  push    rdi
0x180052db2  sub     rsp, 20h
0x180052db6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180052dbd  xor     ebx, ebx
0x180052dbf  test    rdi, rdi
0x180052dc2  jz      loc_180052E5B
0x180052dc8  cmp     [rdi+8], rbx
0x180052dcc  jnz     short loc_180052DF3
0x180052dce  mov     rcx, [rdi]
0x180052dd1  lea     rdx, [rsp+28h+arg_8]
0x180052dd6  mov     [rsp+28h+arg_8], rbx
0x180052ddb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180052de0  test    eax, eax
0x180052de2  js      short loc_180052DF3
0x180052de4  cmp     [rdi+8], rbx
0x180052de8  jnz     short loc_180052DF3
0x180052dea  mov     rax, [rsp+28h+arg_8]
0x180052def  mov     [rdi+8], rax
0x180052df3  mov     rax, [rdi+8]
0x180052df7  lea     rcx, [rax+20h]
0x180052dfb  neg     rax
0x180052dfe  sbb     rdi, rdi
0x180052e01  and     rdi, rcx
0x180052e04  jz      short loc_180052E5B
0x180052e06  call    cs:__imp_GetCurrentThreadId
0x180052e0c  mov     r8d, eax
0x180052e0f  mov     r9d, eax
0x180052e12  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180052e1c  shr     r8, 2
0x180052e20  mul     r8
0x180052e23  shr     rdx, 3
0x180052e27  lea     rcx, [rdx+rdx*4]
0x180052e2b  add     rcx, rcx
0x180052e2e  sub     r8, rcx
0x180052e31  mov     rbx, [rdi+r8*8+8]
0x180052e36  test    rbx, rbx
0x180052e39  jz      short loc_180052E5B
0x180052e3b  cmp     [rbx], r9d
0x180052e3e  jz      short loc_180052E46
0x180052e40  mov     rbx, [rbx+8]
0x180052e44  jmp     short loc_180052E36
0x180052e46  add     rbx, 10h
0x180052e4a  jz      short loc_180052E5B
0x180052e4c  cmp     qword ptr [rbx+8], 0
0x180052e51  jnz     short loc_180052E5B
0x180052e53  lea     rax, [rdi+4]
0x180052e57  mov     [rbx+8], rax
0x180052e5b  mov     rax, rbx
0x180052e5e  mov     rbx, [rsp+28h+arg_0]
0x180052e63  add     rsp, 20h
0x180052e67  pop     rdi
0x180052e68  retn
```
