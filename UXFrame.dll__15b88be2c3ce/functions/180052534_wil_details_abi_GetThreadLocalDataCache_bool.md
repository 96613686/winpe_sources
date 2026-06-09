# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180052534`
- end: `0x1800525f1`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800521e0`

## callees

- `0x180051558`
- `0x180052534`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005258e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005258e`

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
0x180052534  mov     [rsp+arg_0], rbx
0x180052539  push    rdi
0x18005253a  sub     rsp, 20h
0x18005253e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180052545  xor     ebx, ebx
0x180052547  test    rdi, rdi
0x18005254a  jz      loc_1800525E3
0x180052550  cmp     [rdi+8], rbx
0x180052554  jnz     short loc_18005257B
0x180052556  mov     rcx, [rdi]
0x180052559  lea     rdx, [rsp+28h+arg_8]
0x18005255e  mov     [rsp+28h+arg_8], rbx
0x180052563  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180052568  test    eax, eax
0x18005256a  js      short loc_18005257B
0x18005256c  cmp     [rdi+8], rbx
0x180052570  jnz     short loc_18005257B
0x180052572  mov     rax, [rsp+28h+arg_8]
0x180052577  mov     [rdi+8], rax
0x18005257b  mov     rax, [rdi+8]
0x18005257f  lea     rcx, [rax+20h]
0x180052583  neg     rax
0x180052586  sbb     rdi, rdi
0x180052589  and     rdi, rcx
0x18005258c  jz      short loc_1800525E3
0x18005258e  call    cs:__imp_GetCurrentThreadId
0x180052594  mov     r8d, eax
0x180052597  mov     r9d, eax
0x18005259a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800525a4  shr     r8, 2
0x1800525a8  mul     r8
0x1800525ab  shr     rdx, 3
0x1800525af  lea     rcx, [rdx+rdx*4]
0x1800525b3  add     rcx, rcx
0x1800525b6  sub     r8, rcx
0x1800525b9  mov     rbx, [rdi+r8*8+8]
0x1800525be  test    rbx, rbx
0x1800525c1  jz      short loc_1800525E3
0x1800525c3  cmp     [rbx], r9d
0x1800525c6  jz      short loc_1800525CE
0x1800525c8  mov     rbx, [rbx+8]
0x1800525cc  jmp     short loc_1800525BE
0x1800525ce  add     rbx, 10h
0x1800525d2  jz      short loc_1800525E3
0x1800525d4  cmp     qword ptr [rbx+8], 0
0x1800525d9  jnz     short loc_1800525E3
0x1800525db  lea     rax, [rdi+4]
0x1800525df  mov     [rbx+8], rax
0x1800525e3  mov     rax, rbx
0x1800525e6  mov     rbx, [rsp+28h+arg_0]
0x1800525eb  add     rsp, 20h
0x1800525ef  pop     rdi
0x1800525f0  retn
```
