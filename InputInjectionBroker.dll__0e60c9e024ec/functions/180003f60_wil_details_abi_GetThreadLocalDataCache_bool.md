# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180003f60`
- end: `0x18000401b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003840`

## callees

- `0x1800030a0`
- `0x180003f60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003fb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003fb6`

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
0x180003f60  mov     [rsp+arg_0], rbx
0x180003f65  push    rdi
0x180003f66  sub     rsp, 20h
0x180003f6a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180003f71  xor     ebx, ebx
0x180003f73  test    rdi, rdi
0x180003f76  jz      short loc_180003FF6
0x180003f78  cmp     [rdi+8], rbx
0x180003f7c  jnz     short loc_180003FA3
0x180003f7e  mov     rcx, [rdi]
0x180003f81  lea     rdx, [rsp+28h+arg_8]
0x180003f86  mov     [rsp+28h+arg_8], rbx
0x180003f8b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180003f90  test    eax, eax
0x180003f92  js      short loc_180003FA3
0x180003f94  cmp     [rdi+8], rbx
0x180003f98  jnz     short loc_180003FA3
0x180003f9a  mov     rax, [rsp+28h+arg_8]
0x180003f9f  mov     [rdi+8], rax
0x180003fa3  mov     rax, [rdi+8]
0x180003fa7  lea     rcx, [rax+20h]
0x180003fab  neg     rax
0x180003fae  sbb     rdi, rdi
0x180003fb1  and     rdi, rcx
0x180003fb4  jz      short loc_180003FF6
0x180003fb6  call    cs:__imp_GetCurrentThreadId
0x180003fbc  mov     r8d, eax
0x180003fbf  mov     r9d, eax
0x180003fc2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003fcc  shr     r8, 2
0x180003fd0  mul     r8
0x180003fd3  shr     rdx, 3
0x180003fd7  lea     rcx, [rdx+rdx*4]
0x180003fdb  add     rcx, rcx
0x180003fde  sub     r8, rcx
0x180003fe1  mov     rbx, [rdi+r8*8+8]
0x180003fe6  jmp     short loc_180003FF1
0x180003fe8  cmp     [rbx], r9d
0x180003feb  jz      short loc_180004004
0x180003fed  mov     rbx, [rbx+8]
0x180003ff1  test    rbx, rbx
0x180003ff4  jnz     short loc_180003FE8
0x180003ff6  mov     rax, rbx
0x180003ff9  mov     rbx, [rsp+28h+arg_0]
0x180003ffe  add     rsp, 20h
0x180004002  pop     rdi
0x180004003  retn
0x180004004  add     rbx, 10h
0x180004008  jz      short loc_180003FF6
0x18000400a  cmp     qword ptr [rbx+8], 0
0x18000400f  jnz     short loc_180003FF6
0x180004011  lea     rax, [rdi+4]
0x180004015  mov     [rbx+8], rax
0x180004019  jmp     short loc_180003FF6
```
