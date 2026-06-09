# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180006530`
- end: `0x1800065ed`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005e70`

## callees

- `0x180005968`
- `0x180006530`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000658a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000658a`

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
0x180006530  mov     [rsp+arg_0], rbx
0x180006535  push    rdi
0x180006536  sub     rsp, 20h
0x18000653a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180006541  xor     ebx, ebx
0x180006543  test    rdi, rdi
0x180006546  jz      loc_1800065DF
0x18000654c  cmp     [rdi+8], rbx
0x180006550  jnz     short loc_180006577
0x180006552  mov     rcx, [rdi]
0x180006555  lea     rdx, [rsp+28h+arg_8]
0x18000655a  mov     [rsp+28h+arg_8], rbx
0x18000655f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180006564  test    eax, eax
0x180006566  js      short loc_180006577
0x180006568  cmp     [rdi+8], rbx
0x18000656c  jnz     short loc_180006577
0x18000656e  mov     rax, [rsp+28h+arg_8]
0x180006573  mov     [rdi+8], rax
0x180006577  mov     rax, [rdi+8]
0x18000657b  lea     rcx, [rax+20h]
0x18000657f  neg     rax
0x180006582  sbb     rdi, rdi
0x180006585  and     rdi, rcx
0x180006588  jz      short loc_1800065DF
0x18000658a  call    cs:__imp_GetCurrentThreadId
0x180006590  mov     r8d, eax
0x180006593  mov     r9d, eax
0x180006596  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800065a0  shr     r8, 2
0x1800065a4  mul     r8
0x1800065a7  shr     rdx, 3
0x1800065ab  lea     rcx, [rdx+rdx*4]
0x1800065af  add     rcx, rcx
0x1800065b2  sub     r8, rcx
0x1800065b5  mov     rbx, [rdi+r8*8+8]
0x1800065ba  test    rbx, rbx
0x1800065bd  jz      short loc_1800065DF
0x1800065bf  cmp     [rbx], r9d
0x1800065c2  jz      short loc_1800065CA
0x1800065c4  mov     rbx, [rbx+8]
0x1800065c8  jmp     short loc_1800065BA
0x1800065ca  add     rbx, 10h
0x1800065ce  jz      short loc_1800065DF
0x1800065d0  cmp     qword ptr [rbx+8], 0
0x1800065d5  jnz     short loc_1800065DF
0x1800065d7  lea     rax, [rdi+4]
0x1800065db  mov     [rbx+8], rax
0x1800065df  mov     rax, rbx
0x1800065e2  mov     rbx, [rsp+28h+arg_0]
0x1800065e7  add     rsp, 20h
0x1800065eb  pop     rdi
0x1800065ec  retn
```
