# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140008dd4`
- end: `0x140008e8f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400088b0`

## callees

- `0x1400078ec`
- `0x140008dd4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140008e2a`
- `KERNEL32!GetCurrentThreadId` at `0x140008e2a`

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
0x140008dd4  mov     [rsp+arg_0], rbx
0x140008dd9  push    rdi
0x140008dda  sub     rsp, 20h
0x140008dde  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140008de5  xor     ebx, ebx
0x140008de7  test    rdi, rdi
0x140008dea  jz      short loc_140008E6A
0x140008dec  cmp     [rdi+8], rbx
0x140008df0  jnz     short loc_140008E17
0x140008df2  mov     rcx, [rdi]
0x140008df5  lea     rdx, [rsp+28h+arg_8]
0x140008dfa  mov     [rsp+28h+arg_8], rbx
0x140008dff  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140008e04  test    eax, eax
0x140008e06  js      short loc_140008E17
0x140008e08  cmp     [rdi+8], rbx
0x140008e0c  jnz     short loc_140008E17
0x140008e0e  mov     rax, [rsp+28h+arg_8]
0x140008e13  mov     [rdi+8], rax
0x140008e17  mov     rax, [rdi+8]
0x140008e1b  lea     rcx, [rax+20h]
0x140008e1f  neg     rax
0x140008e22  sbb     rdi, rdi
0x140008e25  and     rdi, rcx
0x140008e28  jz      short loc_140008E6A
0x140008e2a  call    cs:__imp_GetCurrentThreadId
0x140008e30  mov     r8d, eax
0x140008e33  mov     r9d, eax
0x140008e36  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140008e40  shr     r8, 2
0x140008e44  mul     r8
0x140008e47  shr     rdx, 3
0x140008e4b  lea     rcx, [rdx+rdx*4]
0x140008e4f  add     rcx, rcx
0x140008e52  sub     r8, rcx
0x140008e55  mov     rbx, [rdi+r8*8+8]
0x140008e5a  jmp     short loc_140008E65
0x140008e5c  cmp     [rbx], r9d
0x140008e5f  jz      short loc_140008E78
0x140008e61  mov     rbx, [rbx+8]
0x140008e65  test    rbx, rbx
0x140008e68  jnz     short loc_140008E5C
0x140008e6a  mov     rax, rbx
0x140008e6d  mov     rbx, [rsp+28h+arg_0]
0x140008e72  add     rsp, 20h
0x140008e76  pop     rdi
0x140008e77  retn
0x140008e78  add     rbx, 10h
0x140008e7c  jz      short loc_140008E6A
0x140008e7e  cmp     qword ptr [rbx+8], 0
0x140008e83  jnz     short loc_140008E6A
0x140008e85  lea     rax, [rdi+4]
0x140008e89  mov     [rbx+8], rax
0x140008e8d  jmp     short loc_140008E6A
```
