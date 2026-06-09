# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004fa8`
- end: `0x180005065`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004930`

## callees

- `0x180004488`
- `0x180004fa8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005002`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005002`

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
0x180004fa8  mov     [rsp+arg_0], rbx
0x180004fad  push    rdi
0x180004fae  sub     rsp, 20h
0x180004fb2  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004fb9  xor     ebx, ebx
0x180004fbb  test    rdi, rdi
0x180004fbe  jz      loc_180005057
0x180004fc4  cmp     [rdi+8], rbx
0x180004fc8  jnz     short loc_180004FEF
0x180004fca  mov     rcx, [rdi]
0x180004fcd  lea     rdx, [rsp+28h+arg_8]
0x180004fd2  mov     [rsp+28h+arg_8], rbx
0x180004fd7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004fdc  test    eax, eax
0x180004fde  js      short loc_180004FEF
0x180004fe0  cmp     [rdi+8], rbx
0x180004fe4  jnz     short loc_180004FEF
0x180004fe6  mov     rax, [rsp+28h+arg_8]
0x180004feb  mov     [rdi+8], rax
0x180004fef  mov     rax, [rdi+8]
0x180004ff3  lea     rcx, [rax+20h]
0x180004ff7  neg     rax
0x180004ffa  sbb     rdi, rdi
0x180004ffd  and     rdi, rcx
0x180005000  jz      short loc_180005057
0x180005002  call    cs:__imp_GetCurrentThreadId
0x180005008  mov     r8d, eax
0x18000500b  mov     r9d, eax
0x18000500e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005018  shr     r8, 2
0x18000501c  mul     r8
0x18000501f  shr     rdx, 3
0x180005023  lea     rcx, [rdx+rdx*4]
0x180005027  add     rcx, rcx
0x18000502a  sub     r8, rcx
0x18000502d  mov     rbx, [rdi+r8*8+8]
0x180005032  test    rbx, rbx
0x180005035  jz      short loc_180005057
0x180005037  cmp     [rbx], r9d
0x18000503a  jz      short loc_180005042
0x18000503c  mov     rbx, [rbx+8]
0x180005040  jmp     short loc_180005032
0x180005042  add     rbx, 10h
0x180005046  jz      short loc_180005057
0x180005048  cmp     qword ptr [rbx+8], 0
0x18000504d  jnz     short loc_180005057
0x18000504f  lea     rax, [rdi+4]
0x180005053  mov     [rbx+8], rax
0x180005057  mov     rax, rbx
0x18000505a  mov     rbx, [rsp+28h+arg_0]
0x18000505f  add     rsp, 20h
0x180005063  pop     rdi
0x180005064  retn
```
