# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180003ee0`
- end: `0x180003f9b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003700`

## callees

- `0x180003018`
- `0x180003ee0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003f36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003f36`

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
0x180003ee0  mov     [rsp+arg_0], rbx
0x180003ee5  push    rdi
0x180003ee6  sub     rsp, 20h
0x180003eea  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180003ef1  xor     ebx, ebx
0x180003ef3  test    rdi, rdi
0x180003ef6  jz      short loc_180003F76
0x180003ef8  cmp     [rdi+8], rbx
0x180003efc  jnz     short loc_180003F23
0x180003efe  mov     rcx, [rdi]
0x180003f01  lea     rdx, [rsp+28h+arg_8]
0x180003f06  mov     [rsp+28h+arg_8], rbx
0x180003f0b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180003f10  test    eax, eax
0x180003f12  js      short loc_180003F23
0x180003f14  cmp     [rdi+8], rbx
0x180003f18  jnz     short loc_180003F23
0x180003f1a  mov     rax, [rsp+28h+arg_8]
0x180003f1f  mov     [rdi+8], rax
0x180003f23  mov     rax, [rdi+8]
0x180003f27  lea     rcx, [rax+20h]
0x180003f2b  neg     rax
0x180003f2e  sbb     rdi, rdi
0x180003f31  and     rdi, rcx
0x180003f34  jz      short loc_180003F76
0x180003f36  call    cs:__imp_GetCurrentThreadId
0x180003f3c  mov     r8d, eax
0x180003f3f  mov     r9d, eax
0x180003f42  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003f4c  shr     r8, 2
0x180003f50  mul     r8
0x180003f53  shr     rdx, 3
0x180003f57  lea     rcx, [rdx+rdx*4]
0x180003f5b  add     rcx, rcx
0x180003f5e  sub     r8, rcx
0x180003f61  mov     rbx, [rdi+r8*8+8]
0x180003f66  jmp     short loc_180003F71
0x180003f68  cmp     [rbx], r9d
0x180003f6b  jz      short loc_180003F84
0x180003f6d  mov     rbx, [rbx+8]
0x180003f71  test    rbx, rbx
0x180003f74  jnz     short loc_180003F68
0x180003f76  mov     rax, rbx
0x180003f79  mov     rbx, [rsp+28h+arg_0]
0x180003f7e  add     rsp, 20h
0x180003f82  pop     rdi
0x180003f83  retn
0x180003f84  add     rbx, 10h
0x180003f88  jz      short loc_180003F76
0x180003f8a  cmp     qword ptr [rbx+8], 0
0x180003f8f  jnz     short loc_180003F76
0x180003f91  lea     rax, [rdi+4]
0x180003f95  mov     [rbx+8], rax
0x180003f99  jmp     short loc_180003F76
```
