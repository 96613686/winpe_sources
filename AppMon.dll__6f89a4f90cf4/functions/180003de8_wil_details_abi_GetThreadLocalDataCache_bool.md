# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180003de8`
- end: `0x180003ea5`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003770`

## callees

- `0x1800032f8`
- `0x180003de8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e42`

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
0x180003de8  mov     [rsp+arg_0], rbx
0x180003ded  push    rdi
0x180003dee  sub     rsp, 20h
0x180003df2  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180003df9  xor     ebx, ebx
0x180003dfb  test    rdi, rdi
0x180003dfe  jz      loc_180003E97
0x180003e04  cmp     [rdi+8], rbx
0x180003e08  jnz     short loc_180003E2F
0x180003e0a  mov     rcx, [rdi]
0x180003e0d  lea     rdx, [rsp+28h+arg_8]
0x180003e12  mov     [rsp+28h+arg_8], rbx
0x180003e17  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180003e1c  test    eax, eax
0x180003e1e  js      short loc_180003E2F
0x180003e20  cmp     [rdi+8], rbx
0x180003e24  jnz     short loc_180003E2F
0x180003e26  mov     rax, [rsp+28h+arg_8]
0x180003e2b  mov     [rdi+8], rax
0x180003e2f  mov     rax, [rdi+8]
0x180003e33  lea     rcx, [rax+20h]
0x180003e37  neg     rax
0x180003e3a  sbb     rdi, rdi
0x180003e3d  and     rdi, rcx
0x180003e40  jz      short loc_180003E97
0x180003e42  call    cs:__imp_GetCurrentThreadId
0x180003e48  mov     r8d, eax
0x180003e4b  mov     r9d, eax
0x180003e4e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003e58  shr     r8, 2
0x180003e5c  mul     r8
0x180003e5f  shr     rdx, 3
0x180003e63  lea     rcx, [rdx+rdx*4]
0x180003e67  add     rcx, rcx
0x180003e6a  sub     r8, rcx
0x180003e6d  mov     rbx, [rdi+r8*8+8]
0x180003e72  test    rbx, rbx
0x180003e75  jz      short loc_180003E97
0x180003e77  cmp     [rbx], r9d
0x180003e7a  jz      short loc_180003E82
0x180003e7c  mov     rbx, [rbx+8]
0x180003e80  jmp     short loc_180003E72
0x180003e82  add     rbx, 10h
0x180003e86  jz      short loc_180003E97
0x180003e88  cmp     qword ptr [rbx+8], 0
0x180003e8d  jnz     short loc_180003E97
0x180003e8f  lea     rax, [rdi+4]
0x180003e93  mov     [rbx+8], rax
0x180003e97  mov     rax, rbx
0x180003e9a  mov     rbx, [rsp+28h+arg_0]
0x180003e9f  add     rsp, 20h
0x180003ea3  pop     rdi
0x180003ea4  retn
```
