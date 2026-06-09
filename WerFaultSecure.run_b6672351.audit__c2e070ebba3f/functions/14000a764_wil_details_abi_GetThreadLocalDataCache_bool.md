# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x14000a764`
- end: `0x14000a81f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a3b0`

## callees

- `0x140008f9c`
- `0x14000a764`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a7ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a7ba`

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
0x14000a764  mov     [rsp+arg_0], rbx
0x14000a769  push    rdi
0x14000a76a  sub     rsp, 20h
0x14000a76e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x14000a775  xor     ebx, ebx
0x14000a777  test    rdi, rdi
0x14000a77a  jz      short loc_14000A7FA
0x14000a77c  cmp     [rdi+8], rbx
0x14000a780  jnz     short loc_14000A7A7
0x14000a782  mov     rcx, [rdi]
0x14000a785  lea     rdx, [rsp+28h+arg_8]
0x14000a78a  mov     [rsp+28h+arg_8], rbx
0x14000a78f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x14000a794  test    eax, eax
0x14000a796  js      short loc_14000A7A7
0x14000a798  cmp     [rdi+8], rbx
0x14000a79c  jnz     short loc_14000A7A7
0x14000a79e  mov     rax, [rsp+28h+arg_8]
0x14000a7a3  mov     [rdi+8], rax
0x14000a7a7  mov     rax, [rdi+8]
0x14000a7ab  lea     rcx, [rax+20h]
0x14000a7af  neg     rax
0x14000a7b2  sbb     rdi, rdi
0x14000a7b5  and     rdi, rcx
0x14000a7b8  jz      short loc_14000A7FA
0x14000a7ba  call    cs:__imp_GetCurrentThreadId
0x14000a7c0  mov     r8d, eax
0x14000a7c3  mov     r9d, eax
0x14000a7c6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000a7d0  shr     r8, 2
0x14000a7d4  mul     r8
0x14000a7d7  shr     rdx, 3
0x14000a7db  lea     rcx, [rdx+rdx*4]
0x14000a7df  add     rcx, rcx
0x14000a7e2  sub     r8, rcx
0x14000a7e5  mov     rbx, [rdi+r8*8+8]
0x14000a7ea  jmp     short loc_14000A7F5
0x14000a7ec  cmp     [rbx], r9d
0x14000a7ef  jz      short loc_14000A808
0x14000a7f1  mov     rbx, [rbx+8]
0x14000a7f5  test    rbx, rbx
0x14000a7f8  jnz     short loc_14000A7EC
0x14000a7fa  mov     rax, rbx
0x14000a7fd  mov     rbx, [rsp+28h+arg_0]
0x14000a802  add     rsp, 20h
0x14000a806  pop     rdi
0x14000a807  retn
0x14000a808  add     rbx, 10h
0x14000a80c  jz      short loc_14000A7FA
0x14000a80e  cmp     qword ptr [rbx+8], 0
0x14000a813  jnz     short loc_14000A7FA
0x14000a815  lea     rax, [rdi+4]
0x14000a819  mov     [rbx+8], rax
0x14000a81d  jmp     short loc_14000A7FA
```
