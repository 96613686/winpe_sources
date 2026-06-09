# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005c54`
- end: `0x180005d0f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005280`

## callees

- `0x1800048d8`
- `0x180005c54`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005caa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005caa`

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
0x180005c54  mov     [rsp+arg_0], rbx
0x180005c59  push    rdi
0x180005c5a  sub     rsp, 20h
0x180005c5e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005c65  xor     ebx, ebx
0x180005c67  test    rdi, rdi
0x180005c6a  jz      short loc_180005CEA
0x180005c6c  cmp     [rdi+8], rbx
0x180005c70  jnz     short loc_180005C97
0x180005c72  mov     rcx, [rdi]
0x180005c75  lea     rdx, [rsp+28h+arg_8]
0x180005c7a  mov     [rsp+28h+arg_8], rbx
0x180005c7f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005c84  test    eax, eax
0x180005c86  js      short loc_180005C97
0x180005c88  cmp     [rdi+8], rbx
0x180005c8c  jnz     short loc_180005C97
0x180005c8e  mov     rax, [rsp+28h+arg_8]
0x180005c93  mov     [rdi+8], rax
0x180005c97  mov     rax, [rdi+8]
0x180005c9b  lea     rcx, [rax+20h]
0x180005c9f  neg     rax
0x180005ca2  sbb     rdi, rdi
0x180005ca5  and     rdi, rcx
0x180005ca8  jz      short loc_180005CEA
0x180005caa  call    cs:__imp_GetCurrentThreadId
0x180005cb0  mov     r8d, eax
0x180005cb3  mov     r9d, eax
0x180005cb6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005cc0  shr     r8, 2
0x180005cc4  mul     r8
0x180005cc7  shr     rdx, 3
0x180005ccb  lea     rcx, [rdx+rdx*4]
0x180005ccf  add     rcx, rcx
0x180005cd2  sub     r8, rcx
0x180005cd5  mov     rbx, [rdi+r8*8+8]
0x180005cda  jmp     short loc_180005CE5
0x180005cdc  cmp     [rbx], r9d
0x180005cdf  jz      short loc_180005CF8
0x180005ce1  mov     rbx, [rbx+8]
0x180005ce5  test    rbx, rbx
0x180005ce8  jnz     short loc_180005CDC
0x180005cea  mov     rax, rbx
0x180005ced  mov     rbx, [rsp+28h+arg_0]
0x180005cf2  add     rsp, 20h
0x180005cf6  pop     rdi
0x180005cf7  retn
0x180005cf8  add     rbx, 10h
0x180005cfc  jz      short loc_180005CEA
0x180005cfe  cmp     qword ptr [rbx+8], 0
0x180005d03  jnz     short loc_180005CEA
0x180005d05  lea     rax, [rdi+4]
0x180005d09  mov     [rbx+8], rax
0x180005d0d  jmp     short loc_180005CEA
```
