# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005f44`
- end: `0x180006001`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005850`

## callees

- `0x180004e58`
- `0x180005f44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f9e`

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
0x180005f44  mov     [rsp+arg_0], rbx
0x180005f49  push    rdi
0x180005f4a  sub     rsp, 20h
0x180005f4e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005f55  xor     ebx, ebx
0x180005f57  test    rdi, rdi
0x180005f5a  jz      loc_180005FF3
0x180005f60  cmp     [rdi+8], rbx
0x180005f64  jnz     short loc_180005F8B
0x180005f66  mov     rcx, [rdi]
0x180005f69  lea     rdx, [rsp+28h+arg_8]
0x180005f6e  mov     [rsp+28h+arg_8], rbx
0x180005f73  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005f78  test    eax, eax
0x180005f7a  js      short loc_180005F8B
0x180005f7c  cmp     [rdi+8], rbx
0x180005f80  jnz     short loc_180005F8B
0x180005f82  mov     rax, [rsp+28h+arg_8]
0x180005f87  mov     [rdi+8], rax
0x180005f8b  mov     rax, [rdi+8]
0x180005f8f  lea     rcx, [rax+20h]
0x180005f93  neg     rax
0x180005f96  sbb     rdi, rdi
0x180005f99  and     rdi, rcx
0x180005f9c  jz      short loc_180005FF3
0x180005f9e  call    cs:__imp_GetCurrentThreadId
0x180005fa4  mov     r8d, eax
0x180005fa7  mov     r9d, eax
0x180005faa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005fb4  shr     r8, 2
0x180005fb8  mul     r8
0x180005fbb  shr     rdx, 3
0x180005fbf  lea     rcx, [rdx+rdx*4]
0x180005fc3  add     rcx, rcx
0x180005fc6  sub     r8, rcx
0x180005fc9  mov     rbx, [rdi+r8*8+8]
0x180005fce  test    rbx, rbx
0x180005fd1  jz      short loc_180005FF3
0x180005fd3  cmp     [rbx], r9d
0x180005fd6  jz      short loc_180005FDE
0x180005fd8  mov     rbx, [rbx+8]
0x180005fdc  jmp     short loc_180005FCE
0x180005fde  add     rbx, 10h
0x180005fe2  jz      short loc_180005FF3
0x180005fe4  cmp     qword ptr [rbx+8], 0
0x180005fe9  jnz     short loc_180005FF3
0x180005feb  lea     rax, [rdi+4]
0x180005fef  mov     [rbx+8], rax
0x180005ff3  mov     rax, rbx
0x180005ff6  mov     rbx, [rsp+28h+arg_0]
0x180005ffb  add     rsp, 20h
0x180005fff  pop     rdi
0x180006000  retn
```
