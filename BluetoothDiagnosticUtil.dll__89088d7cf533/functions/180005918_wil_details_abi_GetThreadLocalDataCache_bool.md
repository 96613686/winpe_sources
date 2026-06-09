# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005918`
- end: `0x1800059de`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005160`

## callees

- `0x180004cb4`
- `0x180005918`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180005972`
- `KERNEL32!GetCurrentThreadId` at `0x180005972`

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
0x180005918  mov     [rsp+arg_0], rbx
0x18000591d  push    rdi
0x18000591e  sub     rsp, 20h
0x180005922  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005929  xor     ebx, ebx
0x18000592b  test    rdi, rdi
0x18000592e  jz      loc_1800059B8
0x180005934  cmp     [rdi+8], rbx
0x180005938  jnz     short loc_18000595F
0x18000593a  mov     rcx, [rdi]
0x18000593d  lea     rdx, [rsp+28h+arg_8]
0x180005942  mov     [rsp+28h+arg_8], rbx
0x180005947  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000594c  test    eax, eax
0x18000594e  js      short loc_18000595F
0x180005950  cmp     [rdi+8], rbx
0x180005954  jnz     short loc_18000595F
0x180005956  mov     rax, [rsp+28h+arg_8]
0x18000595b  mov     [rdi+8], rax
0x18000595f  mov     rax, [rdi+8]
0x180005963  lea     rcx, [rax+20h]
0x180005967  neg     rax
0x18000596a  sbb     rdi, rdi
0x18000596d  and     rdi, rcx
0x180005970  jz      short loc_1800059B8
0x180005972  call    cs:__imp_GetCurrentThreadId
0x180005979  nop     dword ptr [rax+rax+00h]
0x18000597e  mov     r8d, eax
0x180005981  mov     r9d, eax
0x180005984  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000598e  shr     r8, 2
0x180005992  mul     r8
0x180005995  shr     rdx, 3
0x180005999  lea     rcx, [rdx+rdx*4]
0x18000599d  add     rcx, rcx
0x1800059a0  sub     r8, rcx
0x1800059a3  mov     rbx, [rdi+r8*8+8]
0x1800059a8  jmp     short loc_1800059B3
0x1800059aa  cmp     [rbx], r9d
0x1800059ad  jz      short loc_1800059C7
0x1800059af  mov     rbx, [rbx+8]
0x1800059b3  test    rbx, rbx
0x1800059b6  jnz     short loc_1800059AA
0x1800059b8  mov     rax, rbx
0x1800059bb  mov     rbx, [rsp+28h+arg_0]
0x1800059c0  add     rsp, 20h
0x1800059c4  pop     rdi
0x1800059c5  retn
0x1800059c7  add     rbx, 10h
0x1800059cb  jz      short loc_1800059B8
0x1800059cd  cmp     qword ptr [rbx+8], 0
0x1800059d2  jnz     short loc_1800059B8
0x1800059d4  lea     rax, [rdi+4]
0x1800059d8  mov     [rbx+8], rax
0x1800059dc  jmp     short loc_1800059B8
```
