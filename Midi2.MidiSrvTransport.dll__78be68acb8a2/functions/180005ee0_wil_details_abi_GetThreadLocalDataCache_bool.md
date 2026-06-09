# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005ee0`
- end: `0x180005f9b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005700`

## callees

- `0x180004038`
- `0x180005ee0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f36`

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
0x180005ee0  mov     [rsp+arg_0], rbx
0x180005ee5  push    rdi
0x180005ee6  sub     rsp, 20h
0x180005eea  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005ef1  xor     ebx, ebx
0x180005ef3  test    rdi, rdi
0x180005ef6  jz      short loc_180005F76
0x180005ef8  cmp     [rdi+8], rbx
0x180005efc  jnz     short loc_180005F23
0x180005efe  mov     rcx, [rdi]
0x180005f01  lea     rdx, [rsp+28h+arg_8]
0x180005f06  mov     [rsp+28h+arg_8], rbx
0x180005f0b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005f10  test    eax, eax
0x180005f12  js      short loc_180005F23
0x180005f14  cmp     [rdi+8], rbx
0x180005f18  jnz     short loc_180005F23
0x180005f1a  mov     rax, [rsp+28h+arg_8]
0x180005f1f  mov     [rdi+8], rax
0x180005f23  mov     rax, [rdi+8]
0x180005f27  lea     rcx, [rax+20h]
0x180005f2b  neg     rax
0x180005f2e  sbb     rdi, rdi
0x180005f31  and     rdi, rcx
0x180005f34  jz      short loc_180005F76
0x180005f36  call    cs:__imp_GetCurrentThreadId
0x180005f3c  mov     r8d, eax
0x180005f3f  mov     r9d, eax
0x180005f42  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005f4c  shr     r8, 2
0x180005f50  mul     r8
0x180005f53  shr     rdx, 3
0x180005f57  lea     rcx, [rdx+rdx*4]
0x180005f5b  add     rcx, rcx
0x180005f5e  sub     r8, rcx
0x180005f61  mov     rbx, [rdi+r8*8+8]
0x180005f66  jmp     short loc_180005F71
0x180005f68  cmp     [rbx], r9d
0x180005f6b  jz      short loc_180005F84
0x180005f6d  mov     rbx, [rbx+8]
0x180005f71  test    rbx, rbx
0x180005f74  jnz     short loc_180005F68
0x180005f76  mov     rax, rbx
0x180005f79  mov     rbx, [rsp+28h+arg_0]
0x180005f7e  add     rsp, 20h
0x180005f82  pop     rdi
0x180005f83  retn
0x180005f84  add     rbx, 10h
0x180005f88  jz      short loc_180005F76
0x180005f8a  cmp     qword ptr [rbx+8], 0
0x180005f8f  jnz     short loc_180005F76
0x180005f91  lea     rax, [rdi+4]
0x180005f95  mov     [rbx+8], rax
0x180005f99  jmp     short loc_180005F76
```
