# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1400078bc`
- end: `0x140007979`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140007170`

## callees

- `0x1400066d8`
- `0x1400078bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007916`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007916`

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
0x1400078bc  mov     [rsp+arg_0], rbx
0x1400078c1  push    rdi
0x1400078c2  sub     rsp, 20h
0x1400078c6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1400078cd  xor     ebx, ebx
0x1400078cf  test    rdi, rdi
0x1400078d2  jz      loc_14000796B
0x1400078d8  cmp     [rdi+8], rbx
0x1400078dc  jnz     short loc_140007903
0x1400078de  mov     rcx, [rdi]
0x1400078e1  lea     rdx, [rsp+28h+arg_8]
0x1400078e6  mov     [rsp+28h+arg_8], rbx
0x1400078eb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1400078f0  test    eax, eax
0x1400078f2  js      short loc_140007903
0x1400078f4  cmp     [rdi+8], rbx
0x1400078f8  jnz     short loc_140007903
0x1400078fa  mov     rax, [rsp+28h+arg_8]
0x1400078ff  mov     [rdi+8], rax
0x140007903  mov     rax, [rdi+8]
0x140007907  lea     rcx, [rax+20h]
0x14000790b  neg     rax
0x14000790e  sbb     rdi, rdi
0x140007911  and     rdi, rcx
0x140007914  jz      short loc_14000796B
0x140007916  call    cs:__imp_GetCurrentThreadId
0x14000791c  mov     r8d, eax
0x14000791f  mov     r9d, eax
0x140007922  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000792c  shr     r8, 2
0x140007930  mul     r8
0x140007933  shr     rdx, 3
0x140007937  lea     rcx, [rdx+rdx*4]
0x14000793b  add     rcx, rcx
0x14000793e  sub     r8, rcx
0x140007941  mov     rbx, [rdi+r8*8+8]
0x140007946  test    rbx, rbx
0x140007949  jz      short loc_14000796B
0x14000794b  cmp     [rbx], r9d
0x14000794e  jz      short loc_140007956
0x140007950  mov     rbx, [rbx+8]
0x140007954  jmp     short loc_140007946
0x140007956  add     rbx, 10h
0x14000795a  jz      short loc_14000796B
0x14000795c  cmp     qword ptr [rbx+8], 0
0x140007961  jnz     short loc_14000796B
0x140007963  lea     rax, [rdi+4]
0x140007967  mov     [rbx+8], rax
0x14000796b  mov     rax, rbx
0x14000796e  mov     rbx, [rsp+28h+arg_0]
0x140007973  add     rsp, 20h
0x140007977  pop     rdi
0x140007978  retn
```
