# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004f74`
- end: `0x18000502f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004800`

## callees

- `0x180003df0`
- `0x180004f74`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004fca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004fca`

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
0x180004f74  mov     [rsp+arg_0], rbx
0x180004f79  push    rdi
0x180004f7a  sub     rsp, 20h
0x180004f7e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004f85  xor     ebx, ebx
0x180004f87  test    rdi, rdi
0x180004f8a  jz      short loc_18000500A
0x180004f8c  cmp     [rdi+8], rbx
0x180004f90  jnz     short loc_180004FB7
0x180004f92  mov     rcx, [rdi]
0x180004f95  lea     rdx, [rsp+28h+arg_8]
0x180004f9a  mov     [rsp+28h+arg_8], rbx
0x180004f9f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004fa4  test    eax, eax
0x180004fa6  js      short loc_180004FB7
0x180004fa8  cmp     [rdi+8], rbx
0x180004fac  jnz     short loc_180004FB7
0x180004fae  mov     rax, [rsp+28h+arg_8]
0x180004fb3  mov     [rdi+8], rax
0x180004fb7  mov     rax, [rdi+8]
0x180004fbb  lea     rcx, [rax+20h]
0x180004fbf  neg     rax
0x180004fc2  sbb     rdi, rdi
0x180004fc5  and     rdi, rcx
0x180004fc8  jz      short loc_18000500A
0x180004fca  call    cs:__imp_GetCurrentThreadId
0x180004fd0  mov     r8d, eax
0x180004fd3  mov     r9d, eax
0x180004fd6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004fe0  shr     r8, 2
0x180004fe4  mul     r8
0x180004fe7  shr     rdx, 3
0x180004feb  lea     rcx, [rdx+rdx*4]
0x180004fef  add     rcx, rcx
0x180004ff2  sub     r8, rcx
0x180004ff5  mov     rbx, [rdi+r8*8+8]
0x180004ffa  jmp     short loc_180005005
0x180004ffc  cmp     [rbx], r9d
0x180004fff  jz      short loc_180005018
0x180005001  mov     rbx, [rbx+8]
0x180005005  test    rbx, rbx
0x180005008  jnz     short loc_180004FFC
0x18000500a  mov     rax, rbx
0x18000500d  mov     rbx, [rsp+28h+arg_0]
0x180005012  add     rsp, 20h
0x180005016  pop     rdi
0x180005017  retn
0x180005018  add     rbx, 10h
0x18000501c  jz      short loc_18000500A
0x18000501e  cmp     qword ptr [rbx+8], 0
0x180005023  jnz     short loc_18000500A
0x180005025  lea     rax, [rdi+4]
0x180005029  mov     [rbx+8], rax
0x18000502d  jmp     short loc_18000500A
```
