# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140009d20`
- end: `0x140009ddb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009570`

## callees

- `0x140008a58`
- `0x140009d20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009d76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009d76`

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
0x140009d20  mov     [rsp+arg_0], rbx
0x140009d25  push    rdi
0x140009d26  sub     rsp, 20h
0x140009d2a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140009d31  xor     ebx, ebx
0x140009d33  test    rdi, rdi
0x140009d36  jz      short loc_140009DB6
0x140009d38  cmp     [rdi+8], rbx
0x140009d3c  jnz     short loc_140009D63
0x140009d3e  mov     rcx, [rdi]
0x140009d41  lea     rdx, [rsp+28h+arg_8]
0x140009d46  mov     [rsp+28h+arg_8], rbx
0x140009d4b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140009d50  test    eax, eax
0x140009d52  js      short loc_140009D63
0x140009d54  cmp     [rdi+8], rbx
0x140009d58  jnz     short loc_140009D63
0x140009d5a  mov     rax, [rsp+28h+arg_8]
0x140009d5f  mov     [rdi+8], rax
0x140009d63  mov     rax, [rdi+8]
0x140009d67  lea     rcx, [rax+20h]
0x140009d6b  neg     rax
0x140009d6e  sbb     rdi, rdi
0x140009d71  and     rdi, rcx
0x140009d74  jz      short loc_140009DB6
0x140009d76  call    cs:__imp_GetCurrentThreadId
0x140009d7c  mov     r8d, eax
0x140009d7f  mov     r9d, eax
0x140009d82  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140009d8c  shr     r8, 2
0x140009d90  mul     r8
0x140009d93  shr     rdx, 3
0x140009d97  lea     rcx, [rdx+rdx*4]
0x140009d9b  add     rcx, rcx
0x140009d9e  sub     r8, rcx
0x140009da1  mov     rbx, [rdi+r8*8+8]
0x140009da6  jmp     short loc_140009DB1
0x140009da8  cmp     [rbx], r9d
0x140009dab  jz      short loc_140009DC4
0x140009dad  mov     rbx, [rbx+8]
0x140009db1  test    rbx, rbx
0x140009db4  jnz     short loc_140009DA8
0x140009db6  mov     rax, rbx
0x140009db9  mov     rbx, [rsp+28h+arg_0]
0x140009dbe  add     rsp, 20h
0x140009dc2  pop     rdi
0x140009dc3  retn
0x140009dc4  add     rbx, 10h
0x140009dc8  jz      short loc_140009DB6
0x140009dca  cmp     qword ptr [rbx+8], 0
0x140009dcf  jnz     short loc_140009DB6
0x140009dd1  lea     rax, [rdi+4]
0x140009dd5  mov     [rbx+8], rax
0x140009dd9  jmp     short loc_140009DB6
```
