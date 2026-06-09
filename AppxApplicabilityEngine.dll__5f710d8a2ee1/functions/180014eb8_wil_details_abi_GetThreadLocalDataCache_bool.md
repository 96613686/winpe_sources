# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180014eb8`
- end: `0x180014f75`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800148d0`

## callees

- `0x180014438`
- `0x180014eb8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014f12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014f12`

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
0x180014eb8  mov     [rsp+arg_0], rbx
0x180014ebd  push    rdi
0x180014ebe  sub     rsp, 20h
0x180014ec2  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180014ec9  xor     ebx, ebx
0x180014ecb  test    rdi, rdi
0x180014ece  jz      loc_180014F67
0x180014ed4  cmp     [rdi+8], rbx
0x180014ed8  jnz     short loc_180014EFF
0x180014eda  mov     rcx, [rdi]
0x180014edd  lea     rdx, [rsp+28h+arg_8]
0x180014ee2  mov     [rsp+28h+arg_8], rbx
0x180014ee7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180014eec  test    eax, eax
0x180014eee  js      short loc_180014EFF
0x180014ef0  cmp     [rdi+8], rbx
0x180014ef4  jnz     short loc_180014EFF
0x180014ef6  mov     rax, [rsp+28h+arg_8]
0x180014efb  mov     [rdi+8], rax
0x180014eff  mov     rax, [rdi+8]
0x180014f03  lea     rcx, [rax+20h]
0x180014f07  neg     rax
0x180014f0a  sbb     rdi, rdi
0x180014f0d  and     rdi, rcx
0x180014f10  jz      short loc_180014F67
0x180014f12  call    cs:__imp_GetCurrentThreadId
0x180014f18  mov     r8d, eax
0x180014f1b  mov     r9d, eax
0x180014f1e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180014f28  shr     r8, 2
0x180014f2c  mul     r8
0x180014f2f  shr     rdx, 3
0x180014f33  lea     rcx, [rdx+rdx*4]
0x180014f37  add     rcx, rcx
0x180014f3a  sub     r8, rcx
0x180014f3d  mov     rbx, [rdi+r8*8+8]
0x180014f42  test    rbx, rbx
0x180014f45  jz      short loc_180014F67
0x180014f47  cmp     [rbx], r9d
0x180014f4a  jz      short loc_180014F52
0x180014f4c  mov     rbx, [rbx+8]
0x180014f50  jmp     short loc_180014F42
0x180014f52  add     rbx, 10h
0x180014f56  jz      short loc_180014F67
0x180014f58  cmp     qword ptr [rbx+8], 0
0x180014f5d  jnz     short loc_180014F67
0x180014f5f  lea     rax, [rdi+4]
0x180014f63  mov     [rbx+8], rax
0x180014f67  mov     rax, rbx
0x180014f6a  mov     rbx, [rsp+28h+arg_0]
0x180014f6f  add     rsp, 20h
0x180014f73  pop     rdi
0x180014f74  retn
```
