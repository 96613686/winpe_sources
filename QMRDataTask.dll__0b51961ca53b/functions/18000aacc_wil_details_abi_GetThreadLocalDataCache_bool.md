# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000aacc`
- end: `0x18000ab87`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800089f0`

## callees

- `0x180006108`
- `0x18000aacc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000ab22`
- `KERNEL32!GetCurrentThreadId` at `0x18000ab22`

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
0x18000aacc  mov     [rsp+arg_0], rbx
0x18000aad1  push    rdi
0x18000aad2  sub     rsp, 20h
0x18000aad6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000aadd  xor     ebx, ebx
0x18000aadf  test    rdi, rdi
0x18000aae2  jz      short loc_18000AB62
0x18000aae4  cmp     [rdi+8], rbx
0x18000aae8  jnz     short loc_18000AB0F
0x18000aaea  mov     rcx, [rdi]
0x18000aaed  lea     rdx, [rsp+28h+arg_8]
0x18000aaf2  mov     [rsp+28h+arg_8], rbx
0x18000aaf7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000aafc  test    eax, eax
0x18000aafe  js      short loc_18000AB0F
0x18000ab00  cmp     [rdi+8], rbx
0x18000ab04  jnz     short loc_18000AB0F
0x18000ab06  mov     rax, [rsp+28h+arg_8]
0x18000ab0b  mov     [rdi+8], rax
0x18000ab0f  mov     rax, [rdi+8]
0x18000ab13  lea     rcx, [rax+20h]
0x18000ab17  neg     rax
0x18000ab1a  sbb     rdi, rdi
0x18000ab1d  and     rdi, rcx
0x18000ab20  jz      short loc_18000AB62
0x18000ab22  call    cs:__imp_GetCurrentThreadId
0x18000ab28  mov     r8d, eax
0x18000ab2b  mov     r9d, eax
0x18000ab2e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000ab38  shr     r8, 2
0x18000ab3c  mul     r8
0x18000ab3f  shr     rdx, 3
0x18000ab43  lea     rcx, [rdx+rdx*4]
0x18000ab47  add     rcx, rcx
0x18000ab4a  sub     r8, rcx
0x18000ab4d  mov     rbx, [rdi+r8*8+8]
0x18000ab52  jmp     short loc_18000AB5D
0x18000ab54  cmp     [rbx], r9d
0x18000ab57  jz      short loc_18000AB70
0x18000ab59  mov     rbx, [rbx+8]
0x18000ab5d  test    rbx, rbx
0x18000ab60  jnz     short loc_18000AB54
0x18000ab62  mov     rax, rbx
0x18000ab65  mov     rbx, [rsp+28h+arg_0]
0x18000ab6a  add     rsp, 20h
0x18000ab6e  pop     rdi
0x18000ab6f  retn
0x18000ab70  add     rbx, 10h
0x18000ab74  jz      short loc_18000AB62
0x18000ab76  cmp     qword ptr [rbx+8], 0
0x18000ab7b  jnz     short loc_18000AB62
0x18000ab7d  lea     rax, [rdi+4]
0x18000ab81  mov     [rbx+8], rax
0x18000ab85  jmp     short loc_18000AB62
```
