# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180025808`
- end: `0x1800258c5`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800251d0`

## callees

- `0x180024438`
- `0x180025808`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025862`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025862`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  void *v7; // [rsp+38h] [rbp+10h] BYREF

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
0x180025808  mov     [rsp+arg_0], rbx
0x18002580d  push    rdi
0x18002580e  sub     rsp, 20h
0x180025812  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180025819  xor     ebx, ebx
0x18002581b  test    rdi, rdi
0x18002581e  jz      loc_1800258B7
0x180025824  cmp     [rdi+8], rbx
0x180025828  jnz     short loc_18002584F
0x18002582a  mov     rcx, [rdi]
0x18002582d  lea     rdx, [rsp+28h+arg_8]
0x180025832  mov     [rsp+28h+arg_8], rbx
0x180025837  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18002583c  test    eax, eax
0x18002583e  js      short loc_18002584F
0x180025840  cmp     [rdi+8], rbx
0x180025844  jnz     short loc_18002584F
0x180025846  mov     rax, [rsp+28h+arg_8]
0x18002584b  mov     [rdi+8], rax
0x18002584f  mov     rax, [rdi+8]
0x180025853  lea     rcx, [rax+20h]
0x180025857  neg     rax
0x18002585a  sbb     rdi, rdi
0x18002585d  and     rdi, rcx
0x180025860  jz      short loc_1800258B7
0x180025862  call    cs:__imp_GetCurrentThreadId
0x180025868  mov     r8d, eax
0x18002586b  mov     r9d, eax
0x18002586e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180025878  shr     r8, 2
0x18002587c  mul     r8
0x18002587f  shr     rdx, 3
0x180025883  lea     rcx, [rdx+rdx*4]
0x180025887  add     rcx, rcx
0x18002588a  sub     r8, rcx
0x18002588d  mov     rbx, [rdi+r8*8+8]
0x180025892  test    rbx, rbx
0x180025895  jz      short loc_1800258B7
0x180025897  cmp     [rbx], r9d
0x18002589a  jz      short loc_1800258A2
0x18002589c  mov     rbx, [rbx+8]
0x1800258a0  jmp     short loc_180025892
0x1800258a2  add     rbx, 10h
0x1800258a6  jz      short loc_1800258B7
0x1800258a8  cmp     qword ptr [rbx+8], 0
0x1800258ad  jnz     short loc_1800258B7
0x1800258af  lea     rax, [rdi+4]
0x1800258b3  mov     [rbx+8], rax
0x1800258b7  mov     rax, rbx
0x1800258ba  mov     rbx, [rsp+28h+arg_0]
0x1800258bf  add     rsp, 20h
0x1800258c3  pop     rdi
0x1800258c4  retn
```
