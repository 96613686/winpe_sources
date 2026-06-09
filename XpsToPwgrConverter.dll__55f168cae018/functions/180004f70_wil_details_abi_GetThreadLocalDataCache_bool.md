# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004f70`
- end: `0x18000502b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004790`

## callees

- `0x180003818`
- `0x180004f70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004fc6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004fc6`

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
0x180004f70  mov     [rsp+arg_0], rbx
0x180004f75  push    rdi
0x180004f76  sub     rsp, 20h
0x180004f7a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004f81  xor     ebx, ebx
0x180004f83  test    rdi, rdi
0x180004f86  jz      short loc_180005006
0x180004f88  cmp     [rdi+8], rbx
0x180004f8c  jnz     short loc_180004FB3
0x180004f8e  mov     rcx, [rdi]
0x180004f91  lea     rdx, [rsp+28h+arg_8]
0x180004f96  mov     [rsp+28h+arg_8], rbx
0x180004f9b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004fa0  test    eax, eax
0x180004fa2  js      short loc_180004FB3
0x180004fa4  cmp     [rdi+8], rbx
0x180004fa8  jnz     short loc_180004FB3
0x180004faa  mov     rax, [rsp+28h+arg_8]
0x180004faf  mov     [rdi+8], rax
0x180004fb3  mov     rax, [rdi+8]
0x180004fb7  lea     rcx, [rax+20h]
0x180004fbb  neg     rax
0x180004fbe  sbb     rdi, rdi
0x180004fc1  and     rdi, rcx
0x180004fc4  jz      short loc_180005006
0x180004fc6  call    cs:__imp_GetCurrentThreadId
0x180004fcc  mov     r8d, eax
0x180004fcf  mov     r9d, eax
0x180004fd2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004fdc  shr     r8, 2
0x180004fe0  mul     r8
0x180004fe3  shr     rdx, 3
0x180004fe7  lea     rcx, [rdx+rdx*4]
0x180004feb  add     rcx, rcx
0x180004fee  sub     r8, rcx
0x180004ff1  mov     rbx, [rdi+r8*8+8]
0x180004ff6  jmp     short loc_180005001
0x180004ff8  cmp     [rbx], r9d
0x180004ffb  jz      short loc_180005014
0x180004ffd  mov     rbx, [rbx+8]
0x180005001  test    rbx, rbx
0x180005004  jnz     short loc_180004FF8
0x180005006  mov     rax, rbx
0x180005009  mov     rbx, [rsp+28h+arg_0]
0x18000500e  add     rsp, 20h
0x180005012  pop     rdi
0x180005013  retn
0x180005014  add     rbx, 10h
0x180005018  jz      short loc_180005006
0x18000501a  cmp     qword ptr [rbx+8], 0
0x18000501f  jnz     short loc_180005006
0x180005021  lea     rax, [rdi+4]
0x180005025  mov     [rbx+8], rax
0x180005029  jmp     short loc_180005006
```
