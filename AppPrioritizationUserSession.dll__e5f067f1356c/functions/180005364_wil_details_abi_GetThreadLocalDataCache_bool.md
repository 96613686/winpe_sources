# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005364`
- end: `0x18000541f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004b30`

## callees

- `0x1800042e8`
- `0x180005364`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800053ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800053ba`

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
0x180005364  mov     [rsp+arg_0], rbx
0x180005369  push    rdi
0x18000536a  sub     rsp, 20h
0x18000536e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005375  xor     ebx, ebx
0x180005377  test    rdi, rdi
0x18000537a  jz      short loc_1800053FA
0x18000537c  cmp     [rdi+8], rbx
0x180005380  jnz     short loc_1800053A7
0x180005382  mov     rcx, [rdi]
0x180005385  lea     rdx, [rsp+28h+arg_8]
0x18000538a  mov     [rsp+28h+arg_8], rbx
0x18000538f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005394  test    eax, eax
0x180005396  js      short loc_1800053A7
0x180005398  cmp     [rdi+8], rbx
0x18000539c  jnz     short loc_1800053A7
0x18000539e  mov     rax, [rsp+28h+arg_8]
0x1800053a3  mov     [rdi+8], rax
0x1800053a7  mov     rax, [rdi+8]
0x1800053ab  lea     rcx, [rax+20h]
0x1800053af  neg     rax
0x1800053b2  sbb     rdi, rdi
0x1800053b5  and     rdi, rcx
0x1800053b8  jz      short loc_1800053FA
0x1800053ba  call    cs:__imp_GetCurrentThreadId
0x1800053c0  mov     r8d, eax
0x1800053c3  mov     r9d, eax
0x1800053c6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800053d0  shr     r8, 2
0x1800053d4  mul     r8
0x1800053d7  shr     rdx, 3
0x1800053db  lea     rcx, [rdx+rdx*4]
0x1800053df  add     rcx, rcx
0x1800053e2  sub     r8, rcx
0x1800053e5  mov     rbx, [rdi+r8*8+8]
0x1800053ea  jmp     short loc_1800053F5
0x1800053ec  cmp     [rbx], r9d
0x1800053ef  jz      short loc_180005408
0x1800053f1  mov     rbx, [rbx+8]
0x1800053f5  test    rbx, rbx
0x1800053f8  jnz     short loc_1800053EC
0x1800053fa  mov     rax, rbx
0x1800053fd  mov     rbx, [rsp+28h+arg_0]
0x180005402  add     rsp, 20h
0x180005406  pop     rdi
0x180005407  retn
0x180005408  add     rbx, 10h
0x18000540c  jz      short loc_1800053FA
0x18000540e  cmp     qword ptr [rbx+8], 0
0x180005413  jnz     short loc_1800053FA
0x180005415  lea     rax, [rdi+4]
0x180005419  mov     [rbx+8], rax
0x18000541d  jmp     short loc_1800053FA
```
