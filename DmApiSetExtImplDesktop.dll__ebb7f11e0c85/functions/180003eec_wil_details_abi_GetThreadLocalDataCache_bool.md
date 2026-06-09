# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180003eec`
- end: `0x180003fb0`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `196`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003830`

## callees

- `0x1800031e4`
- `0x180003eec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003f46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003f46`

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
0x180003eec  mov     [rsp+arg_0], rbx
0x180003ef1  push    rdi
0x180003ef2  sub     rsp, 20h
0x180003ef6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180003efd  xor     ebx, ebx
0x180003eff  test    rdi, rdi
0x180003f02  jz      loc_180003FA1
0x180003f08  cmp     [rdi+8], rbx
0x180003f0c  jnz     short loc_180003F33
0x180003f0e  mov     rcx, [rdi]
0x180003f11  lea     rdx, [rsp+28h+arg_8]
0x180003f16  mov     [rsp+28h+arg_8], rbx
0x180003f1b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180003f20  test    eax, eax
0x180003f22  js      short loc_180003F33
0x180003f24  cmp     [rdi+8], rbx
0x180003f28  jnz     short loc_180003F33
0x180003f2a  mov     rax, [rsp+28h+arg_8]
0x180003f2f  mov     [rdi+8], rax
0x180003f33  mov     rax, [rdi+8]
0x180003f37  lea     rcx, [rax+20h]
0x180003f3b  neg     rax
0x180003f3e  sbb     rdi, rdi
0x180003f41  and     rdi, rcx
0x180003f44  jz      short loc_180003FA1
0x180003f46  call    cs:__imp_GetCurrentThreadId
0x180003f4d  nop     dword ptr [rax+rax+00h]
0x180003f52  mov     r8d, eax
0x180003f55  mov     r9d, eax
0x180003f58  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003f62  shr     r8, 2
0x180003f66  mul     r8
0x180003f69  shr     rdx, 3
0x180003f6d  lea     rcx, [rdx+rdx*4]
0x180003f71  add     rcx, rcx
0x180003f74  sub     r8, rcx
0x180003f77  mov     rbx, [rdi+r8*8+8]
0x180003f7c  test    rbx, rbx
0x180003f7f  jz      short loc_180003FA1
0x180003f81  cmp     [rbx], r9d
0x180003f84  jz      short loc_180003F8C
0x180003f86  mov     rbx, [rbx+8]
0x180003f8a  jmp     short loc_180003F7C
0x180003f8c  add     rbx, 10h
0x180003f90  jz      short loc_180003FA1
0x180003f92  cmp     qword ptr [rbx+8], 0
0x180003f97  jnz     short loc_180003FA1
0x180003f99  lea     rax, [rdi+4]
0x180003f9d  mov     [rbx+8], rax
0x180003fa1  mov     rax, rbx
0x180003fa4  mov     rbx, [rsp+28h+arg_0]
0x180003fa9  add     rsp, 20h
0x180003fad  pop     rdi
0x180003fae  retn
```
