# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140004ce4`
- end: `0x140004d9f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004450`

## callees

- `0x140003c20`
- `0x140004ce4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140004d3a`
- `KERNEL32!GetCurrentThreadId` at `0x140004d3a`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  char *v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  i = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v3 = *(char **)wil::details_abi::g_pProcessLocalData;
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
0x140004ce4  mov     [rsp+arg_0], rbx
0x140004ce9  push    rdi
0x140004cea  sub     rsp, 20h
0x140004cee  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140004cf5  xor     ebx, ebx
0x140004cf7  test    rdi, rdi
0x140004cfa  jz      short loc_140004D7A
0x140004cfc  cmp     [rdi+8], rbx
0x140004d00  jnz     short loc_140004D27
0x140004d02  mov     rcx, [rdi]; char *
0x140004d05  lea     rdx, [rsp+28h+arg_8]
0x140004d0a  mov     [rsp+28h+arg_8], rbx
0x140004d0f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140004d14  test    eax, eax
0x140004d16  js      short loc_140004D27
0x140004d18  cmp     [rdi+8], rbx
0x140004d1c  jnz     short loc_140004D27
0x140004d1e  mov     rax, [rsp+28h+arg_8]
0x140004d23  mov     [rdi+8], rax
0x140004d27  mov     rax, [rdi+8]
0x140004d2b  lea     rcx, [rax+20h]
0x140004d2f  neg     rax
0x140004d32  sbb     rdi, rdi
0x140004d35  and     rdi, rcx
0x140004d38  jz      short loc_140004D7A
0x140004d3a  call    cs:__imp_GetCurrentThreadId
0x140004d40  mov     r8d, eax
0x140004d43  mov     r9d, eax
0x140004d46  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004d50  shr     r8, 2
0x140004d54  mul     r8
0x140004d57  shr     rdx, 3
0x140004d5b  lea     rcx, [rdx+rdx*4]
0x140004d5f  add     rcx, rcx
0x140004d62  sub     r8, rcx
0x140004d65  mov     rbx, [rdi+r8*8+8]
0x140004d6a  jmp     short loc_140004D75
0x140004d6c  cmp     [rbx], r9d
0x140004d6f  jz      short loc_140004D88
0x140004d71  mov     rbx, [rbx+8]
0x140004d75  test    rbx, rbx
0x140004d78  jnz     short loc_140004D6C
0x140004d7a  mov     rax, rbx
0x140004d7d  mov     rbx, [rsp+28h+arg_0]
0x140004d82  add     rsp, 20h
0x140004d86  pop     rdi
0x140004d87  retn
0x140004d88  add     rbx, 10h
0x140004d8c  jz      short loc_140004D7A
0x140004d8e  cmp     qword ptr [rbx+8], 0
0x140004d93  jnz     short loc_140004D7A
0x140004d95  lea     rax, [rdi+4]
0x140004d99  mov     [rbx+8], rax
0x140004d9d  jmp     short loc_140004D7A
```
