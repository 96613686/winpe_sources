# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140003c00`
- end: `0x140003cbb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003420`

## callees

- `0x140002d28`
- `0x140003c00`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140003c56`
- `KERNEL32!GetCurrentThreadId` at `0x140003c56`

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
0x140003c00  mov     [rsp+arg_0], rbx
0x140003c05  push    rdi
0x140003c06  sub     rsp, 20h
0x140003c0a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140003c11  xor     ebx, ebx
0x140003c13  test    rdi, rdi
0x140003c16  jz      short loc_140003C96
0x140003c18  cmp     [rdi+8], rbx
0x140003c1c  jnz     short loc_140003C43
0x140003c1e  mov     rcx, [rdi]
0x140003c21  lea     rdx, [rsp+28h+arg_8]
0x140003c26  mov     [rsp+28h+arg_8], rbx
0x140003c2b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140003c30  test    eax, eax
0x140003c32  js      short loc_140003C43
0x140003c34  cmp     [rdi+8], rbx
0x140003c38  jnz     short loc_140003C43
0x140003c3a  mov     rax, [rsp+28h+arg_8]
0x140003c3f  mov     [rdi+8], rax
0x140003c43  mov     rax, [rdi+8]
0x140003c47  lea     rcx, [rax+20h]
0x140003c4b  neg     rax
0x140003c4e  sbb     rdi, rdi
0x140003c51  and     rdi, rcx
0x140003c54  jz      short loc_140003C96
0x140003c56  call    cs:__imp_GetCurrentThreadId
0x140003c5c  mov     r8d, eax
0x140003c5f  mov     r9d, eax
0x140003c62  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140003c6c  shr     r8, 2
0x140003c70  mul     r8
0x140003c73  shr     rdx, 3
0x140003c77  lea     rcx, [rdx+rdx*4]
0x140003c7b  add     rcx, rcx
0x140003c7e  sub     r8, rcx
0x140003c81  mov     rbx, [rdi+r8*8+8]
0x140003c86  jmp     short loc_140003C91
0x140003c88  cmp     [rbx], r9d
0x140003c8b  jz      short loc_140003CA4
0x140003c8d  mov     rbx, [rbx+8]
0x140003c91  test    rbx, rbx
0x140003c94  jnz     short loc_140003C88
0x140003c96  mov     rax, rbx
0x140003c99  mov     rbx, [rsp+28h+arg_0]
0x140003c9e  add     rsp, 20h
0x140003ca2  pop     rdi
0x140003ca3  retn
0x140003ca4  add     rbx, 10h
0x140003ca8  jz      short loc_140003C96
0x140003caa  cmp     qword ptr [rbx+8], 0
0x140003caf  jnz     short loc_140003C96
0x140003cb1  lea     rax, [rdi+4]
0x140003cb5  mov     [rbx+8], rax
0x140003cb9  jmp     short loc_140003C96
```
