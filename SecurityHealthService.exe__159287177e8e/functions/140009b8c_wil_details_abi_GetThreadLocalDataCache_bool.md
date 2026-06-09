# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140009b8c`
- end: `0x140009c47`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400096d0`

## callees

- `0x140008718`
- `0x140009b8c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140009be2`
- `KERNEL32!GetCurrentThreadId` at `0x140009be2`

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
0x140009b8c  mov     [rsp+arg_0], rbx
0x140009b91  push    rdi
0x140009b92  sub     rsp, 20h
0x140009b96  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140009b9d  xor     ebx, ebx
0x140009b9f  test    rdi, rdi
0x140009ba2  jz      short loc_140009C22
0x140009ba4  cmp     [rdi+8], rbx
0x140009ba8  jnz     short loc_140009BCF
0x140009baa  mov     rcx, [rdi]
0x140009bad  lea     rdx, [rsp+28h+arg_8]
0x140009bb2  mov     [rsp+28h+arg_8], rbx
0x140009bb7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140009bbc  test    eax, eax
0x140009bbe  js      short loc_140009BCF
0x140009bc0  cmp     [rdi+8], rbx
0x140009bc4  jnz     short loc_140009BCF
0x140009bc6  mov     rax, [rsp+28h+arg_8]
0x140009bcb  mov     [rdi+8], rax
0x140009bcf  mov     rax, [rdi+8]
0x140009bd3  lea     rcx, [rax+20h]
0x140009bd7  neg     rax
0x140009bda  sbb     rdi, rdi
0x140009bdd  and     rdi, rcx
0x140009be0  jz      short loc_140009C22
0x140009be2  call    cs:__imp_GetCurrentThreadId
0x140009be8  mov     r8d, eax
0x140009beb  mov     r9d, eax
0x140009bee  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140009bf8  shr     r8, 2
0x140009bfc  mul     r8
0x140009bff  shr     rdx, 3
0x140009c03  lea     rcx, [rdx+rdx*4]
0x140009c07  add     rcx, rcx
0x140009c0a  sub     r8, rcx
0x140009c0d  mov     rbx, [rdi+r8*8+8]
0x140009c12  jmp     short loc_140009C1D
0x140009c14  cmp     [rbx], r9d
0x140009c17  jz      short loc_140009C30
0x140009c19  mov     rbx, [rbx+8]
0x140009c1d  test    rbx, rbx
0x140009c20  jnz     short loc_140009C14
0x140009c22  mov     rax, rbx
0x140009c25  mov     rbx, [rsp+28h+arg_0]
0x140009c2a  add     rsp, 20h
0x140009c2e  pop     rdi
0x140009c2f  retn
0x140009c30  add     rbx, 10h
0x140009c34  jz      short loc_140009C22
0x140009c36  cmp     qword ptr [rbx+8], 0
0x140009c3b  jnz     short loc_140009C22
0x140009c3d  lea     rax, [rdi+4]
0x140009c41  mov     [rbx+8], rax
0x140009c45  jmp     short loc_140009C22
```
