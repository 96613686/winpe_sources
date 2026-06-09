# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800054bc`
- end: `0x180005577`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004ce0`

## callees

- `0x1800039e4`
- `0x1800054bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005512`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005512`

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
0x1800054bc  mov     [rsp+arg_0], rbx
0x1800054c1  push    rdi
0x1800054c2  sub     rsp, 20h
0x1800054c6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800054cd  xor     ebx, ebx
0x1800054cf  test    rdi, rdi
0x1800054d2  jz      short loc_180005552
0x1800054d4  cmp     [rdi+8], rbx
0x1800054d8  jnz     short loc_1800054FF
0x1800054da  mov     rcx, [rdi]
0x1800054dd  lea     rdx, [rsp+28h+arg_8]
0x1800054e2  mov     [rsp+28h+arg_8], rbx
0x1800054e7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800054ec  test    eax, eax
0x1800054ee  js      short loc_1800054FF
0x1800054f0  cmp     [rdi+8], rbx
0x1800054f4  jnz     short loc_1800054FF
0x1800054f6  mov     rax, [rsp+28h+arg_8]
0x1800054fb  mov     [rdi+8], rax
0x1800054ff  mov     rax, [rdi+8]
0x180005503  lea     rcx, [rax+20h]
0x180005507  neg     rax
0x18000550a  sbb     rdi, rdi
0x18000550d  and     rdi, rcx
0x180005510  jz      short loc_180005552
0x180005512  call    cs:__imp_GetCurrentThreadId
0x180005518  mov     r8d, eax
0x18000551b  mov     r9d, eax
0x18000551e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005528  shr     r8, 2
0x18000552c  mul     r8
0x18000552f  shr     rdx, 3
0x180005533  lea     rcx, [rdx+rdx*4]
0x180005537  add     rcx, rcx
0x18000553a  sub     r8, rcx
0x18000553d  mov     rbx, [rdi+r8*8+8]
0x180005542  jmp     short loc_18000554D
0x180005544  cmp     [rbx], r9d
0x180005547  jz      short loc_180005560
0x180005549  mov     rbx, [rbx+8]
0x18000554d  test    rbx, rbx
0x180005550  jnz     short loc_180005544
0x180005552  mov     rax, rbx
0x180005555  mov     rbx, [rsp+28h+arg_0]
0x18000555a  add     rsp, 20h
0x18000555e  pop     rdi
0x18000555f  retn
0x180005560  add     rbx, 10h
0x180005564  jz      short loc_180005552
0x180005566  cmp     qword ptr [rbx+8], 0
0x18000556b  jnz     short loc_180005552
0x18000556d  lea     rax, [rdi+4]
0x180005571  mov     [rbx+8], rax
0x180005575  jmp     short loc_180005552
```
