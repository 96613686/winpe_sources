# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004e4c`
- end: `0x180004f07`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004670`

## callees

- `0x1800036f4`
- `0x180004e4c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ea2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ea2`

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
0x180004e4c  mov     [rsp+arg_0], rbx
0x180004e51  push    rdi
0x180004e52  sub     rsp, 20h
0x180004e56  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004e5d  xor     ebx, ebx
0x180004e5f  test    rdi, rdi
0x180004e62  jz      short loc_180004EE2
0x180004e64  cmp     [rdi+8], rbx
0x180004e68  jnz     short loc_180004E8F
0x180004e6a  mov     rcx, [rdi]
0x180004e6d  lea     rdx, [rsp+28h+arg_8]
0x180004e72  mov     [rsp+28h+arg_8], rbx
0x180004e77  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004e7c  test    eax, eax
0x180004e7e  js      short loc_180004E8F
0x180004e80  cmp     [rdi+8], rbx
0x180004e84  jnz     short loc_180004E8F
0x180004e86  mov     rax, [rsp+28h+arg_8]
0x180004e8b  mov     [rdi+8], rax
0x180004e8f  mov     rax, [rdi+8]
0x180004e93  lea     rcx, [rax+20h]
0x180004e97  neg     rax
0x180004e9a  sbb     rdi, rdi
0x180004e9d  and     rdi, rcx
0x180004ea0  jz      short loc_180004EE2
0x180004ea2  call    cs:__imp_GetCurrentThreadId
0x180004ea8  mov     r8d, eax
0x180004eab  mov     r9d, eax
0x180004eae  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004eb8  shr     r8, 2
0x180004ebc  mul     r8
0x180004ebf  shr     rdx, 3
0x180004ec3  lea     rcx, [rdx+rdx*4]
0x180004ec7  add     rcx, rcx
0x180004eca  sub     r8, rcx
0x180004ecd  mov     rbx, [rdi+r8*8+8]
0x180004ed2  jmp     short loc_180004EDD
0x180004ed4  cmp     [rbx], r9d
0x180004ed7  jz      short loc_180004EF0
0x180004ed9  mov     rbx, [rbx+8]
0x180004edd  test    rbx, rbx
0x180004ee0  jnz     short loc_180004ED4
0x180004ee2  mov     rax, rbx
0x180004ee5  mov     rbx, [rsp+28h+arg_0]
0x180004eea  add     rsp, 20h
0x180004eee  pop     rdi
0x180004eef  retn
0x180004ef0  add     rbx, 10h
0x180004ef4  jz      short loc_180004EE2
0x180004ef6  cmp     qword ptr [rbx+8], 0
0x180004efb  jnz     short loc_180004EE2
0x180004efd  lea     rax, [rdi+4]
0x180004f01  mov     [rbx+8], rax
0x180004f05  jmp     short loc_180004EE2
```
