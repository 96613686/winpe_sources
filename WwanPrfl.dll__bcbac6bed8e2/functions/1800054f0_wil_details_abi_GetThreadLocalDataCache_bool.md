# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800054f0`
- end: `0x1800055ab`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004d10`

## callees

- `0x180003b08`
- `0x1800054f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005546`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005546`

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
0x1800054f0  mov     [rsp+arg_0], rbx
0x1800054f5  push    rdi
0x1800054f6  sub     rsp, 20h
0x1800054fa  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005501  xor     ebx, ebx
0x180005503  test    rdi, rdi
0x180005506  jz      short loc_180005586
0x180005508  cmp     [rdi+8], rbx
0x18000550c  jnz     short loc_180005533
0x18000550e  mov     rcx, [rdi]
0x180005511  lea     rdx, [rsp+28h+arg_8]
0x180005516  mov     [rsp+28h+arg_8], rbx
0x18000551b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005520  test    eax, eax
0x180005522  js      short loc_180005533
0x180005524  cmp     [rdi+8], rbx
0x180005528  jnz     short loc_180005533
0x18000552a  mov     rax, [rsp+28h+arg_8]
0x18000552f  mov     [rdi+8], rax
0x180005533  mov     rax, [rdi+8]
0x180005537  lea     rcx, [rax+20h]
0x18000553b  neg     rax
0x18000553e  sbb     rdi, rdi
0x180005541  and     rdi, rcx
0x180005544  jz      short loc_180005586
0x180005546  call    cs:__imp_GetCurrentThreadId
0x18000554c  mov     r8d, eax
0x18000554f  mov     r9d, eax
0x180005552  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000555c  shr     r8, 2
0x180005560  mul     r8
0x180005563  shr     rdx, 3
0x180005567  lea     rcx, [rdx+rdx*4]
0x18000556b  add     rcx, rcx
0x18000556e  sub     r8, rcx
0x180005571  mov     rbx, [rdi+r8*8+8]
0x180005576  jmp     short loc_180005581
0x180005578  cmp     [rbx], r9d
0x18000557b  jz      short loc_180005594
0x18000557d  mov     rbx, [rbx+8]
0x180005581  test    rbx, rbx
0x180005584  jnz     short loc_180005578
0x180005586  mov     rax, rbx
0x180005589  mov     rbx, [rsp+28h+arg_0]
0x18000558e  add     rsp, 20h
0x180005592  pop     rdi
0x180005593  retn
0x180005594  add     rbx, 10h
0x180005598  jz      short loc_180005586
0x18000559a  cmp     qword ptr [rbx+8], 0
0x18000559f  jnz     short loc_180005586
0x1800055a1  lea     rax, [rdi+4]
0x1800055a5  mov     [rbx+8], rax
0x1800055a9  jmp     short loc_180005586
```
