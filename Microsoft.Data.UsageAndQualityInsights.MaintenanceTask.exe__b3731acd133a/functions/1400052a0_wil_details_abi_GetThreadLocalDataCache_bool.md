# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1400052a0`
- end: `0x14000535b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004ac0`

## callees

- `0x140003a78`
- `0x1400052a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400052f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400052f6`

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
0x1400052a0  mov     [rsp+arg_0], rbx
0x1400052a5  push    rdi
0x1400052a6  sub     rsp, 20h
0x1400052aa  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1400052b1  xor     ebx, ebx
0x1400052b3  test    rdi, rdi
0x1400052b6  jz      short loc_140005336
0x1400052b8  cmp     [rdi+8], rbx
0x1400052bc  jnz     short loc_1400052E3
0x1400052be  mov     rcx, [rdi]
0x1400052c1  lea     rdx, [rsp+28h+arg_8]
0x1400052c6  mov     [rsp+28h+arg_8], rbx
0x1400052cb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1400052d0  test    eax, eax
0x1400052d2  js      short loc_1400052E3
0x1400052d4  cmp     [rdi+8], rbx
0x1400052d8  jnz     short loc_1400052E3
0x1400052da  mov     rax, [rsp+28h+arg_8]
0x1400052df  mov     [rdi+8], rax
0x1400052e3  mov     rax, [rdi+8]
0x1400052e7  lea     rcx, [rax+20h]
0x1400052eb  neg     rax
0x1400052ee  sbb     rdi, rdi
0x1400052f1  and     rdi, rcx
0x1400052f4  jz      short loc_140005336
0x1400052f6  call    cs:__imp_GetCurrentThreadId
0x1400052fc  mov     r8d, eax
0x1400052ff  mov     r9d, eax
0x140005302  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000530c  shr     r8, 2
0x140005310  mul     r8
0x140005313  shr     rdx, 3
0x140005317  lea     rcx, [rdx+rdx*4]
0x14000531b  add     rcx, rcx
0x14000531e  sub     r8, rcx
0x140005321  mov     rbx, [rdi+r8*8+8]
0x140005326  jmp     short loc_140005331
0x140005328  cmp     [rbx], r9d
0x14000532b  jz      short loc_140005344
0x14000532d  mov     rbx, [rbx+8]
0x140005331  test    rbx, rbx
0x140005334  jnz     short loc_140005328
0x140005336  mov     rax, rbx
0x140005339  mov     rbx, [rsp+28h+arg_0]
0x14000533e  add     rsp, 20h
0x140005342  pop     rdi
0x140005343  retn
0x140005344  add     rbx, 10h
0x140005348  jz      short loc_140005336
0x14000534a  cmp     qword ptr [rbx+8], 0
0x14000534f  jnz     short loc_140005336
0x140005351  lea     rax, [rdi+4]
0x140005355  mov     [rbx+8], rax
0x140005359  jmp     short loc_140005336
```
