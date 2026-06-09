# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005350`
- end: `0x18000540b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004b70`

## callees

- `0x180003bf8`
- `0x180005350`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800053a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800053a6`

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
0x180005350  mov     [rsp+arg_0], rbx
0x180005355  push    rdi
0x180005356  sub     rsp, 20h
0x18000535a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005361  xor     ebx, ebx
0x180005363  test    rdi, rdi
0x180005366  jz      short loc_1800053E6
0x180005368  cmp     [rdi+8], rbx
0x18000536c  jnz     short loc_180005393
0x18000536e  mov     rcx, [rdi]
0x180005371  lea     rdx, [rsp+28h+arg_8]
0x180005376  mov     [rsp+28h+arg_8], rbx
0x18000537b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005380  test    eax, eax
0x180005382  js      short loc_180005393
0x180005384  cmp     [rdi+8], rbx
0x180005388  jnz     short loc_180005393
0x18000538a  mov     rax, [rsp+28h+arg_8]
0x18000538f  mov     [rdi+8], rax
0x180005393  mov     rax, [rdi+8]
0x180005397  lea     rcx, [rax+20h]
0x18000539b  neg     rax
0x18000539e  sbb     rdi, rdi
0x1800053a1  and     rdi, rcx
0x1800053a4  jz      short loc_1800053E6
0x1800053a6  call    cs:__imp_GetCurrentThreadId
0x1800053ac  mov     r8d, eax
0x1800053af  mov     r9d, eax
0x1800053b2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800053bc  shr     r8, 2
0x1800053c0  mul     r8
0x1800053c3  shr     rdx, 3
0x1800053c7  lea     rcx, [rdx+rdx*4]
0x1800053cb  add     rcx, rcx
0x1800053ce  sub     r8, rcx
0x1800053d1  mov     rbx, [rdi+r8*8+8]
0x1800053d6  jmp     short loc_1800053E1
0x1800053d8  cmp     [rbx], r9d
0x1800053db  jz      short loc_1800053F4
0x1800053dd  mov     rbx, [rbx+8]
0x1800053e1  test    rbx, rbx
0x1800053e4  jnz     short loc_1800053D8
0x1800053e6  mov     rax, rbx
0x1800053e9  mov     rbx, [rsp+28h+arg_0]
0x1800053ee  add     rsp, 20h
0x1800053f2  pop     rdi
0x1800053f3  retn
0x1800053f4  add     rbx, 10h
0x1800053f8  jz      short loc_1800053E6
0x1800053fa  cmp     qword ptr [rbx+8], 0
0x1800053ff  jnz     short loc_1800053E6
0x180005401  lea     rax, [rdi+4]
0x180005405  mov     [rbx+8], rax
0x180005409  jmp     short loc_1800053E6
```
