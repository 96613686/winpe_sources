# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140006680`
- end: `0x14000673d`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005ff0`

## callees

- `0x1400052f8`
- `0x140006680`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400066da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400066da`

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
0x140006680  mov     [rsp+arg_0], rbx
0x140006685  push    rdi
0x140006686  sub     rsp, 20h
0x14000668a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140006691  xor     ebx, ebx
0x140006693  test    rdi, rdi
0x140006696  jz      loc_14000672F
0x14000669c  cmp     [rdi+8], rbx
0x1400066a0  jnz     short loc_1400066C7
0x1400066a2  mov     rcx, [rdi]
0x1400066a5  lea     rdx, [rsp+28h+arg_8]
0x1400066aa  mov     [rsp+28h+arg_8], rbx
0x1400066af  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1400066b4  test    eax, eax
0x1400066b6  js      short loc_1400066C7
0x1400066b8  cmp     [rdi+8], rbx
0x1400066bc  jnz     short loc_1400066C7
0x1400066be  mov     rax, [rsp+28h+arg_8]
0x1400066c3  mov     [rdi+8], rax
0x1400066c7  mov     rax, [rdi+8]
0x1400066cb  lea     rcx, [rax+20h]
0x1400066cf  neg     rax
0x1400066d2  sbb     rdi, rdi
0x1400066d5  and     rdi, rcx
0x1400066d8  jz      short loc_14000672F
0x1400066da  call    cs:__imp_GetCurrentThreadId
0x1400066e0  mov     r8d, eax
0x1400066e3  mov     r9d, eax
0x1400066e6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400066f0  shr     r8, 2
0x1400066f4  mul     r8
0x1400066f7  shr     rdx, 3
0x1400066fb  lea     rcx, [rdx+rdx*4]
0x1400066ff  add     rcx, rcx
0x140006702  sub     r8, rcx
0x140006705  mov     rbx, [rdi+r8*8+8]
0x14000670a  test    rbx, rbx
0x14000670d  jz      short loc_14000672F
0x14000670f  cmp     [rbx], r9d
0x140006712  jz      short loc_14000671A
0x140006714  mov     rbx, [rbx+8]
0x140006718  jmp     short loc_14000670A
0x14000671a  add     rbx, 10h
0x14000671e  jz      short loc_14000672F
0x140006720  cmp     qword ptr [rbx+8], 0
0x140006725  jnz     short loc_14000672F
0x140006727  lea     rax, [rdi+4]
0x14000672b  mov     [rbx+8], rax
0x14000672f  mov     rax, rbx
0x140006732  mov     rbx, [rsp+28h+arg_0]
0x140006737  add     rsp, 20h
0x14000673b  pop     rdi
0x14000673c  retn
```
