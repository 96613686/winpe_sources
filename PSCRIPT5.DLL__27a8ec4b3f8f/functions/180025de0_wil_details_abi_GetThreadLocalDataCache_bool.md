# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180025de0`
- end: `0x180025ea6`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800254e0`

## callees

- `0x180024584`
- `0x180025de0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180025e3a`
- `KERNEL32!GetCurrentThreadId` at `0x180025e3a`

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
      if ( wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v3, &v7) >= 0
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
0x180025de0  mov     [rsp+arg_0], rbx
0x180025de5  push    rdi
0x180025de6  sub     rsp, 20h
0x180025dea  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180025df1  xor     ebx, ebx
0x180025df3  test    rdi, rdi
0x180025df6  jz      loc_180025E80
0x180025dfc  cmp     [rdi+8], rbx
0x180025e00  jnz     short loc_180025E27
0x180025e02  mov     rcx, [rdi]
0x180025e05  lea     rdx, [rsp+28h+arg_8]
0x180025e0a  mov     [rsp+28h+arg_8], rbx
0x180025e0f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180025e14  test    eax, eax
0x180025e16  js      short loc_180025E27
0x180025e18  cmp     [rdi+8], rbx
0x180025e1c  jnz     short loc_180025E27
0x180025e1e  mov     rax, [rsp+28h+arg_8]
0x180025e23  mov     [rdi+8], rax
0x180025e27  mov     rax, [rdi+8]
0x180025e2b  lea     rcx, [rax+20h]
0x180025e2f  neg     rax
0x180025e32  sbb     rdi, rdi
0x180025e35  and     rdi, rcx
0x180025e38  jz      short loc_180025E80
0x180025e3a  call    cs:__imp_GetCurrentThreadId
0x180025e41  nop     dword ptr [rax+rax+00h]
0x180025e46  mov     r8d, eax
0x180025e49  mov     r9d, eax
0x180025e4c  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180025e56  shr     r8, 2
0x180025e5a  mul     r8
0x180025e5d  shr     rdx, 3
0x180025e61  lea     rcx, [rdx+rdx*4]
0x180025e65  add     rcx, rcx
0x180025e68  sub     r8, rcx
0x180025e6b  mov     rbx, [rdi+r8*8+8]
0x180025e70  jmp     short loc_180025E7B
0x180025e72  cmp     [rbx], r9d
0x180025e75  jz      short loc_180025E8F
0x180025e77  mov     rbx, [rbx+8]
0x180025e7b  test    rbx, rbx
0x180025e7e  jnz     short loc_180025E72
0x180025e80  mov     rax, rbx
0x180025e83  mov     rbx, [rsp+28h+arg_0]
0x180025e88  add     rsp, 20h
0x180025e8c  pop     rdi
0x180025e8d  retn
0x180025e8f  add     rbx, 10h
0x180025e93  jz      short loc_180025E80
0x180025e95  cmp     qword ptr [rbx+8], 0
0x180025e9a  jnz     short loc_180025E80
0x180025e9c  lea     rax, [rdi+4]
0x180025ea0  mov     [rbx+8], rax
0x180025ea4  jmp     short loc_180025E80
```
