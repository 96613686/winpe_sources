# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18002544c`
- end: `0x18002550f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `195`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180024b40`

## callees

- `0x180023ca0`
- `0x18002544c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800254a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800254a6`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rbx
  __int64 v2; // rdi
  __int64 v3; // rcx
  __int64 v4; // rbx
  DWORD CurrentThreadId; // r9d
  __int64 i; // rcx
  bool v7; // zf
  __int64 v8; // rcx
  void *v10; // [rsp+38h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  v2 = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v3 = *(_QWORD *)wil::details_abi::g_pProcessLocalData;
      v10 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v3, &v10) >= 0
        && !*(_QWORD *)(v1 + 8) )
      {
        *(_QWORD *)(v1 + 8) = v10;
      }
    }
    v4 = (*(_QWORD *)(v1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v1 + 8) != 0);
    if ( v4 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v4 + 8 * (CurrentThreadId % 0xAuLL) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          v7 = i == -16;
          v8 = i + 16;
          v2 = v8;
          if ( !v7 && !*(_QWORD *)(v8 + 8) )
            *(_QWORD *)(v8 + 8) = v4 + 4;
          return (struct wil::details_abi::ThreadLocalData *)v2;
        }
      }
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)v2;
}

```

## disassembly

```asm
0x18002544c  mov     [rsp+arg_0], rbx
0x180025451  push    rdi
0x180025452  sub     rsp, 20h
0x180025456  mov     rbx, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18002545d  xor     edi, edi
0x18002545f  test    rbx, rbx
0x180025462  jz      loc_180025500
0x180025468  cmp     [rbx+8], rdi
0x18002546c  jnz     short loc_180025493
0x18002546e  mov     rcx, [rbx]
0x180025471  lea     rdx, [rsp+28h+arg_8]
0x180025476  and     [rsp+28h+arg_8], rdi
0x18002547b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180025480  test    eax, eax
0x180025482  js      short loc_180025493
0x180025484  cmp     [rbx+8], rdi
0x180025488  jnz     short loc_180025493
0x18002548a  mov     rax, [rsp+28h+arg_8]
0x18002548f  mov     [rbx+8], rax
0x180025493  mov     rax, [rbx+8]
0x180025497  lea     rcx, [rax+20h]
0x18002549b  neg     rax
0x18002549e  sbb     rbx, rbx
0x1800254a1  and     rbx, rcx
0x1800254a4  jz      short loc_180025500
0x1800254a6  call    cs:__imp_GetCurrentThreadId
0x1800254ad  nop     dword ptr [rax+rax+00h]
0x1800254b2  mov     r8d, eax
0x1800254b5  mov     r9d, eax
0x1800254b8  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800254c2  mul     r9
0x1800254c5  shr     rdx, 3
0x1800254c9  lea     rcx, [rdx+rdx*4]
0x1800254cd  add     rcx, rcx
0x1800254d0  sub     r8, rcx
0x1800254d3  mov     rcx, [rbx+r8*8+8]
0x1800254d8  test    rcx, rcx
0x1800254db  jz      short loc_180025500
0x1800254dd  cmp     [rcx], r9d
0x1800254e0  jz      short loc_1800254E8
0x1800254e2  mov     rcx, [rcx+8]
0x1800254e6  jmp     short loc_1800254D8
0x1800254e8  add     rcx, 10h
0x1800254ec  mov     rdi, rcx
0x1800254ef  jz      short loc_180025500
0x1800254f1  cmp     qword ptr [rcx+8], 0
0x1800254f6  jnz     short loc_180025500
0x1800254f8  lea     rax, [rbx+4]
0x1800254fc  mov     [rcx+8], rax
0x180025500  mov     rbx, [rsp+28h+arg_0]
0x180025505  mov     rax, rdi
0x180025508  add     rsp, 20h
0x18002550c  pop     rdi
0x18002550d  retn
```
