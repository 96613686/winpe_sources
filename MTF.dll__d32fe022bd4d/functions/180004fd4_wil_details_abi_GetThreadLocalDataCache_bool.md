# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004fd4`
- end: `0x18000508f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004810`

## callees

- `0x180004010`
- `0x180004fd4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000502a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000502a`

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
0x180004fd4  mov     [rsp+arg_0], rbx
0x180004fd9  push    rdi
0x180004fda  sub     rsp, 20h
0x180004fde  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004fe5  xor     ebx, ebx
0x180004fe7  test    rdi, rdi
0x180004fea  jz      short loc_18000506A
0x180004fec  cmp     [rdi+8], rbx
0x180004ff0  jnz     short loc_180005017
0x180004ff2  mov     rcx, [rdi]
0x180004ff5  lea     rdx, [rsp+28h+arg_8]
0x180004ffa  mov     [rsp+28h+arg_8], rbx
0x180004fff  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005004  test    eax, eax
0x180005006  js      short loc_180005017
0x180005008  cmp     [rdi+8], rbx
0x18000500c  jnz     short loc_180005017
0x18000500e  mov     rax, [rsp+28h+arg_8]
0x180005013  mov     [rdi+8], rax
0x180005017  mov     rax, [rdi+8]
0x18000501b  lea     rcx, [rax+20h]
0x18000501f  neg     rax
0x180005022  sbb     rdi, rdi
0x180005025  and     rdi, rcx
0x180005028  jz      short loc_18000506A
0x18000502a  call    cs:__imp_GetCurrentThreadId
0x180005030  mov     r8d, eax
0x180005033  mov     r9d, eax
0x180005036  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005040  shr     r8, 2
0x180005044  mul     r8
0x180005047  shr     rdx, 3
0x18000504b  lea     rcx, [rdx+rdx*4]
0x18000504f  add     rcx, rcx
0x180005052  sub     r8, rcx
0x180005055  mov     rbx, [rdi+r8*8+8]
0x18000505a  jmp     short loc_180005065
0x18000505c  cmp     [rbx], r9d
0x18000505f  jz      short loc_180005078
0x180005061  mov     rbx, [rbx+8]
0x180005065  test    rbx, rbx
0x180005068  jnz     short loc_18000505C
0x18000506a  mov     rax, rbx
0x18000506d  mov     rbx, [rsp+28h+arg_0]
0x180005072  add     rsp, 20h
0x180005076  pop     rdi
0x180005077  retn
0x180005078  add     rbx, 10h
0x18000507c  jz      short loc_18000506A
0x18000507e  cmp     qword ptr [rbx+8], 0
0x180005083  jnz     short loc_18000506A
0x180005085  lea     rax, [rdi+4]
0x180005089  mov     [rbx+8], rax
0x18000508d  jmp     short loc_18000506A
```
