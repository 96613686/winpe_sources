# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140004ed4`
- end: `0x140004f91`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400041c0`

## callees

- `0x1400037d0`
- `0x140004ed4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004f2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004f2e`

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
0x140004ed4  mov     [rsp+arg_0], rbx
0x140004ed9  push    rdi
0x140004eda  sub     rsp, 20h
0x140004ede  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140004ee5  xor     ebx, ebx
0x140004ee7  test    rdi, rdi
0x140004eea  jz      loc_140004F83
0x140004ef0  cmp     [rdi+8], rbx
0x140004ef4  jnz     short loc_140004F1B
0x140004ef6  mov     rcx, [rdi]
0x140004ef9  lea     rdx, [rsp+28h+arg_8]
0x140004efe  mov     [rsp+28h+arg_8], rbx
0x140004f03  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140004f08  test    eax, eax
0x140004f0a  js      short loc_140004F1B
0x140004f0c  cmp     [rdi+8], rbx
0x140004f10  jnz     short loc_140004F1B
0x140004f12  mov     rax, [rsp+28h+arg_8]
0x140004f17  mov     [rdi+8], rax
0x140004f1b  mov     rax, [rdi+8]
0x140004f1f  lea     rcx, [rax+20h]
0x140004f23  neg     rax
0x140004f26  sbb     rdi, rdi
0x140004f29  and     rdi, rcx
0x140004f2c  jz      short loc_140004F83
0x140004f2e  call    cs:__imp_GetCurrentThreadId
0x140004f34  mov     r8d, eax
0x140004f37  mov     r9d, eax
0x140004f3a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004f44  shr     r8, 2
0x140004f48  mul     r8
0x140004f4b  shr     rdx, 3
0x140004f4f  lea     rcx, [rdx+rdx*4]
0x140004f53  add     rcx, rcx
0x140004f56  sub     r8, rcx
0x140004f59  mov     rbx, [rdi+r8*8+8]
0x140004f5e  test    rbx, rbx
0x140004f61  jz      short loc_140004F83
0x140004f63  cmp     [rbx], r9d
0x140004f66  jz      short loc_140004F6E
0x140004f68  mov     rbx, [rbx+8]
0x140004f6c  jmp     short loc_140004F5E
0x140004f6e  add     rbx, 10h
0x140004f72  jz      short loc_140004F83
0x140004f74  cmp     qword ptr [rbx+8], 0
0x140004f79  jnz     short loc_140004F83
0x140004f7b  lea     rax, [rdi+4]
0x140004f7f  mov     [rbx+8], rax
0x140004f83  mov     rax, rbx
0x140004f86  mov     rbx, [rsp+28h+arg_0]
0x140004f8b  add     rsp, 20h
0x140004f8f  pop     rdi
0x140004f90  retn
```
