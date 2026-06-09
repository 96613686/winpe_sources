# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004fb0`
- end: `0x18000506b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800047d0`

## callees

- `0x1800040e8`
- `0x180004fb0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005006`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005006`

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
0x180004fb0  mov     [rsp+arg_0], rbx
0x180004fb5  push    rdi
0x180004fb6  sub     rsp, 20h
0x180004fba  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004fc1  xor     ebx, ebx
0x180004fc3  test    rdi, rdi
0x180004fc6  jz      short loc_180005046
0x180004fc8  cmp     [rdi+8], rbx
0x180004fcc  jnz     short loc_180004FF3
0x180004fce  mov     rcx, [rdi]
0x180004fd1  lea     rdx, [rsp+28h+arg_8]
0x180004fd6  mov     [rsp+28h+arg_8], rbx
0x180004fdb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004fe0  test    eax, eax
0x180004fe2  js      short loc_180004FF3
0x180004fe4  cmp     [rdi+8], rbx
0x180004fe8  jnz     short loc_180004FF3
0x180004fea  mov     rax, [rsp+28h+arg_8]
0x180004fef  mov     [rdi+8], rax
0x180004ff3  mov     rax, [rdi+8]
0x180004ff7  lea     rcx, [rax+20h]
0x180004ffb  neg     rax
0x180004ffe  sbb     rdi, rdi
0x180005001  and     rdi, rcx
0x180005004  jz      short loc_180005046
0x180005006  call    cs:__imp_GetCurrentThreadId
0x18000500c  mov     r8d, eax
0x18000500f  mov     r9d, eax
0x180005012  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000501c  shr     r8, 2
0x180005020  mul     r8
0x180005023  shr     rdx, 3
0x180005027  lea     rcx, [rdx+rdx*4]
0x18000502b  add     rcx, rcx
0x18000502e  sub     r8, rcx
0x180005031  mov     rbx, [rdi+r8*8+8]
0x180005036  jmp     short loc_180005041
0x180005038  cmp     [rbx], r9d
0x18000503b  jz      short loc_180005054
0x18000503d  mov     rbx, [rbx+8]
0x180005041  test    rbx, rbx
0x180005044  jnz     short loc_180005038
0x180005046  mov     rax, rbx
0x180005049  mov     rbx, [rsp+28h+arg_0]
0x18000504e  add     rsp, 20h
0x180005052  pop     rdi
0x180005053  retn
0x180005054  add     rbx, 10h
0x180005058  jz      short loc_180005046
0x18000505a  cmp     qword ptr [rbx+8], 0
0x18000505f  jnz     short loc_180005046
0x180005061  lea     rax, [rdi+4]
0x180005065  mov     [rbx+8], rax
0x180005069  jmp     short loc_180005046
```
