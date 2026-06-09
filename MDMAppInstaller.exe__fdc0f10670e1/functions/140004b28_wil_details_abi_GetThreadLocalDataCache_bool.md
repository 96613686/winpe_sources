# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140004b28`
- end: `0x140004be5`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400044b0`

## callees

- `0x140003e28`
- `0x140004b28`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140004b82`
- `KERNEL32!GetCurrentThreadId` at `0x140004b82`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  void *v7; // [rsp+38h] [rbp+10h] BYREF

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
0x140004b28  mov     [rsp+arg_0], rbx
0x140004b2d  push    rdi
0x140004b2e  sub     rsp, 20h
0x140004b32  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140004b39  xor     ebx, ebx
0x140004b3b  test    rdi, rdi
0x140004b3e  jz      loc_140004BD7
0x140004b44  cmp     [rdi+8], rbx
0x140004b48  jnz     short loc_140004B6F
0x140004b4a  mov     rcx, [rdi]
0x140004b4d  lea     rdx, [rsp+28h+arg_8]
0x140004b52  mov     [rsp+28h+arg_8], rbx
0x140004b57  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140004b5c  test    eax, eax
0x140004b5e  js      short loc_140004B6F
0x140004b60  cmp     [rdi+8], rbx
0x140004b64  jnz     short loc_140004B6F
0x140004b66  mov     rax, [rsp+28h+arg_8]
0x140004b6b  mov     [rdi+8], rax
0x140004b6f  mov     rax, [rdi+8]
0x140004b73  lea     rcx, [rax+20h]
0x140004b77  neg     rax
0x140004b7a  sbb     rdi, rdi
0x140004b7d  and     rdi, rcx
0x140004b80  jz      short loc_140004BD7
0x140004b82  call    cs:__imp_GetCurrentThreadId
0x140004b88  mov     r8d, eax
0x140004b8b  mov     r9d, eax
0x140004b8e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004b98  shr     r8, 2
0x140004b9c  mul     r8
0x140004b9f  shr     rdx, 3
0x140004ba3  lea     rcx, [rdx+rdx*4]
0x140004ba7  add     rcx, rcx
0x140004baa  sub     r8, rcx
0x140004bad  mov     rbx, [rdi+r8*8+8]
0x140004bb2  test    rbx, rbx
0x140004bb5  jz      short loc_140004BD7
0x140004bb7  cmp     [rbx], r9d
0x140004bba  jz      short loc_140004BC2
0x140004bbc  mov     rbx, [rbx+8]
0x140004bc0  jmp     short loc_140004BB2
0x140004bc2  add     rbx, 10h
0x140004bc6  jz      short loc_140004BD7
0x140004bc8  cmp     qword ptr [rbx+8], 0
0x140004bcd  jnz     short loc_140004BD7
0x140004bcf  lea     rax, [rdi+4]
0x140004bd3  mov     [rbx+8], rax
0x140004bd7  mov     rax, rbx
0x140004bda  mov     rbx, [rsp+28h+arg_0]
0x140004bdf  add     rsp, 20h
0x140004be3  pop     rdi
0x140004be4  retn
```
