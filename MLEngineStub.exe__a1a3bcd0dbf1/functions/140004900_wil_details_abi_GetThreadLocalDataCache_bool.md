# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140004900`
- end: `0x1400049bb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004120`

## callees

- `0x140003a38`
- `0x140004900`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004956`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004956`

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
0x140004900  mov     [rsp+arg_0], rbx
0x140004905  push    rdi
0x140004906  sub     rsp, 20h
0x14000490a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140004911  xor     ebx, ebx
0x140004913  test    rdi, rdi
0x140004916  jz      short loc_140004996
0x140004918  cmp     [rdi+8], rbx
0x14000491c  jnz     short loc_140004943
0x14000491e  mov     rcx, [rdi]
0x140004921  lea     rdx, [rsp+28h+arg_8]
0x140004926  mov     [rsp+28h+arg_8], rbx
0x14000492b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140004930  test    eax, eax
0x140004932  js      short loc_140004943
0x140004934  cmp     [rdi+8], rbx
0x140004938  jnz     short loc_140004943
0x14000493a  mov     rax, [rsp+28h+arg_8]
0x14000493f  mov     [rdi+8], rax
0x140004943  mov     rax, [rdi+8]
0x140004947  lea     rcx, [rax+20h]
0x14000494b  neg     rax
0x14000494e  sbb     rdi, rdi
0x140004951  and     rdi, rcx
0x140004954  jz      short loc_140004996
0x140004956  call    cs:__imp_GetCurrentThreadId
0x14000495c  mov     r8d, eax
0x14000495f  mov     r9d, eax
0x140004962  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000496c  shr     r8, 2
0x140004970  mul     r8
0x140004973  shr     rdx, 3
0x140004977  lea     rcx, [rdx+rdx*4]
0x14000497b  add     rcx, rcx
0x14000497e  sub     r8, rcx
0x140004981  mov     rbx, [rdi+r8*8+8]
0x140004986  jmp     short loc_140004991
0x140004988  cmp     [rbx], r9d
0x14000498b  jz      short loc_1400049A4
0x14000498d  mov     rbx, [rbx+8]
0x140004991  test    rbx, rbx
0x140004994  jnz     short loc_140004988
0x140004996  mov     rax, rbx
0x140004999  mov     rbx, [rsp+28h+arg_0]
0x14000499e  add     rsp, 20h
0x1400049a2  pop     rdi
0x1400049a3  retn
0x1400049a4  add     rbx, 10h
0x1400049a8  jz      short loc_140004996
0x1400049aa  cmp     qword ptr [rbx+8], 0
0x1400049af  jnz     short loc_140004996
0x1400049b1  lea     rax, [rdi+4]
0x1400049b5  mov     [rbx+8], rax
0x1400049b9  jmp     short loc_140004996
```
