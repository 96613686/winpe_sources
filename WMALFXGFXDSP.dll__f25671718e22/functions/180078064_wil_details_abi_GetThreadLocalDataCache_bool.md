# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180078064`
- end: `0x180078121`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180014cc4`

## callees

- `0x1800770c8`
- `0x180078064`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800780be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800780be`

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
0x180078064  mov     [rsp+arg_0], rbx
0x180078069  push    rdi
0x18007806a  sub     rsp, 20h
0x18007806e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180078075  xor     ebx, ebx
0x180078077  test    rdi, rdi
0x18007807a  jz      loc_180078113
0x180078080  cmp     [rdi+8], rbx
0x180078084  jnz     short loc_1800780AB
0x180078086  mov     rcx, [rdi]
0x180078089  lea     rdx, [rsp+28h+arg_8]
0x18007808e  mov     [rsp+28h+arg_8], rbx
0x180078093  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180078098  test    eax, eax
0x18007809a  js      short loc_1800780AB
0x18007809c  cmp     [rdi+8], rbx
0x1800780a0  jnz     short loc_1800780AB
0x1800780a2  mov     rax, [rsp+28h+arg_8]
0x1800780a7  mov     [rdi+8], rax
0x1800780ab  mov     rax, [rdi+8]
0x1800780af  lea     rcx, [rax+20h]
0x1800780b3  neg     rax
0x1800780b6  sbb     rdi, rdi
0x1800780b9  and     rdi, rcx
0x1800780bc  jz      short loc_180078113
0x1800780be  call    cs:__imp_GetCurrentThreadId
0x1800780c4  mov     r8d, eax
0x1800780c7  mov     r9d, eax
0x1800780ca  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800780d4  shr     r8, 2
0x1800780d8  mul     r8
0x1800780db  shr     rdx, 3
0x1800780df  lea     rcx, [rdx+rdx*4]
0x1800780e3  add     rcx, rcx
0x1800780e6  sub     r8, rcx
0x1800780e9  mov     rbx, [rdi+r8*8+8]
0x1800780ee  test    rbx, rbx
0x1800780f1  jz      short loc_180078113
0x1800780f3  cmp     [rbx], r9d
0x1800780f6  jz      short loc_1800780FE
0x1800780f8  mov     rbx, [rbx+8]
0x1800780fc  jmp     short loc_1800780EE
0x1800780fe  add     rbx, 10h
0x180078102  jz      short loc_180078113
0x180078104  cmp     qword ptr [rbx+8], 0
0x180078109  jnz     short loc_180078113
0x18007810b  lea     rax, [rdi+4]
0x18007810f  mov     [rbx+8], rax
0x180078113  mov     rax, rbx
0x180078116  mov     rbx, [rsp+28h+arg_0]
0x18007811b  add     rsp, 20h
0x18007811f  pop     rdi
0x180078120  retn
```
