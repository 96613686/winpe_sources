# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004090`
- end: `0x18000414b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800038b0`

## callees

- `0x180003168`
- `0x180004090`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800040e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800040e6`

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
0x180004090  mov     [rsp+arg_0], rbx
0x180004095  push    rdi
0x180004096  sub     rsp, 20h
0x18000409a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800040a1  xor     ebx, ebx
0x1800040a3  test    rdi, rdi
0x1800040a6  jz      short loc_180004126
0x1800040a8  cmp     [rdi+8], rbx
0x1800040ac  jnz     short loc_1800040D3
0x1800040ae  mov     rcx, [rdi]
0x1800040b1  lea     rdx, [rsp+28h+arg_8]
0x1800040b6  mov     [rsp+28h+arg_8], rbx
0x1800040bb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800040c0  test    eax, eax
0x1800040c2  js      short loc_1800040D3
0x1800040c4  cmp     [rdi+8], rbx
0x1800040c8  jnz     short loc_1800040D3
0x1800040ca  mov     rax, [rsp+28h+arg_8]
0x1800040cf  mov     [rdi+8], rax
0x1800040d3  mov     rax, [rdi+8]
0x1800040d7  lea     rcx, [rax+20h]
0x1800040db  neg     rax
0x1800040de  sbb     rdi, rdi
0x1800040e1  and     rdi, rcx
0x1800040e4  jz      short loc_180004126
0x1800040e6  call    cs:__imp_GetCurrentThreadId
0x1800040ec  mov     r8d, eax
0x1800040ef  mov     r9d, eax
0x1800040f2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800040fc  shr     r8, 2
0x180004100  mul     r8
0x180004103  shr     rdx, 3
0x180004107  lea     rcx, [rdx+rdx*4]
0x18000410b  add     rcx, rcx
0x18000410e  sub     r8, rcx
0x180004111  mov     rbx, [rdi+r8*8+8]
0x180004116  jmp     short loc_180004121
0x180004118  cmp     [rbx], r9d
0x18000411b  jz      short loc_180004134
0x18000411d  mov     rbx, [rbx+8]
0x180004121  test    rbx, rbx
0x180004124  jnz     short loc_180004118
0x180004126  mov     rax, rbx
0x180004129  mov     rbx, [rsp+28h+arg_0]
0x18000412e  add     rsp, 20h
0x180004132  pop     rdi
0x180004133  retn
0x180004134  add     rbx, 10h
0x180004138  jz      short loc_180004126
0x18000413a  cmp     qword ptr [rbx+8], 0
0x18000413f  jnz     short loc_180004126
0x180004141  lea     rax, [rdi+4]
0x180004145  mov     [rbx+8], rax
0x180004149  jmp     short loc_180004126
```
