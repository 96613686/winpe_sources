# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004a3c`
- end: `0x180004af7`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004260`

## callees

- `0x18000321c`
- `0x180004a3c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a92`

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
0x180004a3c  mov     [rsp+arg_0], rbx
0x180004a41  push    rdi
0x180004a42  sub     rsp, 20h
0x180004a46  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004a4d  xor     ebx, ebx
0x180004a4f  test    rdi, rdi
0x180004a52  jz      short loc_180004AD2
0x180004a54  cmp     [rdi+8], rbx
0x180004a58  jnz     short loc_180004A7F
0x180004a5a  mov     rcx, [rdi]
0x180004a5d  lea     rdx, [rsp+28h+arg_8]
0x180004a62  mov     [rsp+28h+arg_8], rbx
0x180004a67  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004a6c  test    eax, eax
0x180004a6e  js      short loc_180004A7F
0x180004a70  cmp     [rdi+8], rbx
0x180004a74  jnz     short loc_180004A7F
0x180004a76  mov     rax, [rsp+28h+arg_8]
0x180004a7b  mov     [rdi+8], rax
0x180004a7f  mov     rax, [rdi+8]
0x180004a83  lea     rcx, [rax+20h]
0x180004a87  neg     rax
0x180004a8a  sbb     rdi, rdi
0x180004a8d  and     rdi, rcx
0x180004a90  jz      short loc_180004AD2
0x180004a92  call    cs:__imp_GetCurrentThreadId
0x180004a98  mov     r8d, eax
0x180004a9b  mov     r9d, eax
0x180004a9e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004aa8  shr     r8, 2
0x180004aac  mul     r8
0x180004aaf  shr     rdx, 3
0x180004ab3  lea     rcx, [rdx+rdx*4]
0x180004ab7  add     rcx, rcx
0x180004aba  sub     r8, rcx
0x180004abd  mov     rbx, [rdi+r8*8+8]
0x180004ac2  jmp     short loc_180004ACD
0x180004ac4  cmp     [rbx], r9d
0x180004ac7  jz      short loc_180004AE0
0x180004ac9  mov     rbx, [rbx+8]
0x180004acd  test    rbx, rbx
0x180004ad0  jnz     short loc_180004AC4
0x180004ad2  mov     rax, rbx
0x180004ad5  mov     rbx, [rsp+28h+arg_0]
0x180004ada  add     rsp, 20h
0x180004ade  pop     rdi
0x180004adf  retn
0x180004ae0  add     rbx, 10h
0x180004ae4  jz      short loc_180004AD2
0x180004ae6  cmp     qword ptr [rbx+8], 0
0x180004aeb  jnz     short loc_180004AD2
0x180004aed  lea     rax, [rdi+4]
0x180004af1  mov     [rbx+8], rax
0x180004af5  jmp     short loc_180004AD2
```
