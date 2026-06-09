# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180007c08`
- end: `0x180007cc3`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006f30`

## callees

- `0x180006128`
- `0x180007c08`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007c5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007c5e`

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
0x180007c08  mov     [rsp+arg_0], rbx
0x180007c0d  push    rdi
0x180007c0e  sub     rsp, 20h
0x180007c12  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180007c19  xor     ebx, ebx
0x180007c1b  test    rdi, rdi
0x180007c1e  jz      short loc_180007C9E
0x180007c20  cmp     [rdi+8], rbx
0x180007c24  jnz     short loc_180007C4B
0x180007c26  mov     rcx, [rdi]
0x180007c29  lea     rdx, [rsp+28h+arg_8]
0x180007c2e  mov     [rsp+28h+arg_8], rbx
0x180007c33  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180007c38  test    eax, eax
0x180007c3a  js      short loc_180007C4B
0x180007c3c  cmp     [rdi+8], rbx
0x180007c40  jnz     short loc_180007C4B
0x180007c42  mov     rax, [rsp+28h+arg_8]
0x180007c47  mov     [rdi+8], rax
0x180007c4b  mov     rax, [rdi+8]
0x180007c4f  lea     rcx, [rax+20h]
0x180007c53  neg     rax
0x180007c56  sbb     rdi, rdi
0x180007c59  and     rdi, rcx
0x180007c5c  jz      short loc_180007C9E
0x180007c5e  call    cs:__imp_GetCurrentThreadId
0x180007c64  mov     r8d, eax
0x180007c67  mov     r9d, eax
0x180007c6a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007c74  shr     r8, 2
0x180007c78  mul     r8
0x180007c7b  shr     rdx, 3
0x180007c7f  lea     rcx, [rdx+rdx*4]
0x180007c83  add     rcx, rcx
0x180007c86  sub     r8, rcx
0x180007c89  mov     rbx, [rdi+r8*8+8]
0x180007c8e  jmp     short loc_180007C99
0x180007c90  cmp     [rbx], r9d
0x180007c93  jz      short loc_180007CAC
0x180007c95  mov     rbx, [rbx+8]
0x180007c99  test    rbx, rbx
0x180007c9c  jnz     short loc_180007C90
0x180007c9e  mov     rax, rbx
0x180007ca1  mov     rbx, [rsp+28h+arg_0]
0x180007ca6  add     rsp, 20h
0x180007caa  pop     rdi
0x180007cab  retn
0x180007cac  add     rbx, 10h
0x180007cb0  jz      short loc_180007C9E
0x180007cb2  cmp     qword ptr [rbx+8], 0
0x180007cb7  jnz     short loc_180007C9E
0x180007cb9  lea     rax, [rdi+4]
0x180007cbd  mov     [rbx+8], rax
0x180007cc1  jmp     short loc_180007C9E
```
