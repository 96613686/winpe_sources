# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004c84`
- end: `0x180004d4a`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004480`

## callees

- `0x1800040b4`
- `0x180004c84`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180004cde`
- `KERNEL32!GetCurrentThreadId` at `0x180004cde`

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
0x180004c84  mov     [rsp+arg_0], rbx
0x180004c89  push    rdi
0x180004c8a  sub     rsp, 20h
0x180004c8e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004c95  xor     ebx, ebx
0x180004c97  test    rdi, rdi
0x180004c9a  jz      loc_180004D24
0x180004ca0  cmp     [rdi+8], rbx
0x180004ca4  jnz     short loc_180004CCB
0x180004ca6  mov     rcx, [rdi]
0x180004ca9  lea     rdx, [rsp+28h+arg_8]
0x180004cae  mov     [rsp+28h+arg_8], rbx
0x180004cb3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004cb8  test    eax, eax
0x180004cba  js      short loc_180004CCB
0x180004cbc  cmp     [rdi+8], rbx
0x180004cc0  jnz     short loc_180004CCB
0x180004cc2  mov     rax, [rsp+28h+arg_8]
0x180004cc7  mov     [rdi+8], rax
0x180004ccb  mov     rax, [rdi+8]
0x180004ccf  lea     rcx, [rax+20h]
0x180004cd3  neg     rax
0x180004cd6  sbb     rdi, rdi
0x180004cd9  and     rdi, rcx
0x180004cdc  jz      short loc_180004D24
0x180004cde  call    cs:__imp_GetCurrentThreadId
0x180004ce5  nop     dword ptr [rax+rax+00h]
0x180004cea  mov     r8d, eax
0x180004ced  mov     r9d, eax
0x180004cf0  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004cfa  shr     r8, 2
0x180004cfe  mul     r8
0x180004d01  shr     rdx, 3
0x180004d05  lea     rcx, [rdx+rdx*4]
0x180004d09  add     rcx, rcx
0x180004d0c  sub     r8, rcx
0x180004d0f  mov     rbx, [rdi+r8*8+8]
0x180004d14  jmp     short loc_180004D1F
0x180004d16  cmp     [rbx], r9d
0x180004d19  jz      short loc_180004D33
0x180004d1b  mov     rbx, [rbx+8]
0x180004d1f  test    rbx, rbx
0x180004d22  jnz     short loc_180004D16
0x180004d24  mov     rax, rbx
0x180004d27  mov     rbx, [rsp+28h+arg_0]
0x180004d2c  add     rsp, 20h
0x180004d30  pop     rdi
0x180004d31  retn
0x180004d33  add     rbx, 10h
0x180004d37  jz      short loc_180004D24
0x180004d39  cmp     qword ptr [rbx+8], 0
0x180004d3e  jnz     short loc_180004D24
0x180004d40  lea     rax, [rdi+4]
0x180004d44  mov     [rbx+8], rax
0x180004d48  jmp     short loc_180004D24
```
