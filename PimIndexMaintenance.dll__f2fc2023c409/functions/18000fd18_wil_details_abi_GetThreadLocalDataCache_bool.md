# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000fd18`
- end: `0x18000fdd5`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f3c0`

## callees

- `0x18000eb28`
- `0x18000fd18`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fd72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fd72`

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
0x18000fd18  mov     [rsp+arg_0], rbx
0x18000fd1d  push    rdi
0x18000fd1e  sub     rsp, 20h
0x18000fd22  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000fd29  xor     ebx, ebx
0x18000fd2b  test    rdi, rdi
0x18000fd2e  jz      loc_18000FDC7
0x18000fd34  cmp     [rdi+8], rbx
0x18000fd38  jnz     short loc_18000FD5F
0x18000fd3a  mov     rcx, [rdi]
0x18000fd3d  lea     rdx, [rsp+28h+arg_8]
0x18000fd42  mov     [rsp+28h+arg_8], rbx
0x18000fd47  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000fd4c  test    eax, eax
0x18000fd4e  js      short loc_18000FD5F
0x18000fd50  cmp     [rdi+8], rbx
0x18000fd54  jnz     short loc_18000FD5F
0x18000fd56  mov     rax, [rsp+28h+arg_8]
0x18000fd5b  mov     [rdi+8], rax
0x18000fd5f  mov     rax, [rdi+8]
0x18000fd63  lea     rcx, [rax+20h]
0x18000fd67  neg     rax
0x18000fd6a  sbb     rdi, rdi
0x18000fd6d  and     rdi, rcx
0x18000fd70  jz      short loc_18000FDC7
0x18000fd72  call    cs:__imp_GetCurrentThreadId
0x18000fd78  mov     r8d, eax
0x18000fd7b  mov     r9d, eax
0x18000fd7e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000fd88  shr     r8, 2
0x18000fd8c  mul     r8
0x18000fd8f  shr     rdx, 3
0x18000fd93  lea     rcx, [rdx+rdx*4]
0x18000fd97  add     rcx, rcx
0x18000fd9a  sub     r8, rcx
0x18000fd9d  mov     rbx, [rdi+r8*8+8]
0x18000fda2  test    rbx, rbx
0x18000fda5  jz      short loc_18000FDC7
0x18000fda7  cmp     [rbx], r9d
0x18000fdaa  jz      short loc_18000FDB2
0x18000fdac  mov     rbx, [rbx+8]
0x18000fdb0  jmp     short loc_18000FDA2
0x18000fdb2  add     rbx, 10h
0x18000fdb6  jz      short loc_18000FDC7
0x18000fdb8  cmp     qword ptr [rbx+8], 0
0x18000fdbd  jnz     short loc_18000FDC7
0x18000fdbf  lea     rax, [rdi+4]
0x18000fdc3  mov     [rbx+8], rax
0x18000fdc7  mov     rax, rbx
0x18000fdca  mov     rbx, [rsp+28h+arg_0]
0x18000fdcf  add     rsp, 20h
0x18000fdd3  pop     rdi
0x18000fdd4  retn
```
