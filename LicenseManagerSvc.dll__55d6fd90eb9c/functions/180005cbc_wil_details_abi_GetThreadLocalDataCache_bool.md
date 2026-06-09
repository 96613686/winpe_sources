# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005cbc`
- end: `0x180005d79`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800056e0`

## callees

- `0x18000279c`
- `0x180005cbc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005d16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005d16`

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
0x180005cbc  mov     [rsp+arg_0], rbx
0x180005cc1  push    rdi
0x180005cc2  sub     rsp, 20h
0x180005cc6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005ccd  xor     ebx, ebx
0x180005ccf  test    rdi, rdi
0x180005cd2  jz      loc_180005D6B
0x180005cd8  cmp     [rdi+8], rbx
0x180005cdc  jnz     short loc_180005D03
0x180005cde  mov     rcx, [rdi]
0x180005ce1  lea     rdx, [rsp+28h+arg_8]
0x180005ce6  mov     [rsp+28h+arg_8], rbx
0x180005ceb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005cf0  test    eax, eax
0x180005cf2  js      short loc_180005D03
0x180005cf4  cmp     [rdi+8], rbx
0x180005cf8  jnz     short loc_180005D03
0x180005cfa  mov     rax, [rsp+28h+arg_8]
0x180005cff  mov     [rdi+8], rax
0x180005d03  mov     rax, [rdi+8]
0x180005d07  lea     rcx, [rax+20h]
0x180005d0b  neg     rax
0x180005d0e  sbb     rdi, rdi
0x180005d11  and     rdi, rcx
0x180005d14  jz      short loc_180005D6B
0x180005d16  call    cs:__imp_GetCurrentThreadId
0x180005d1c  mov     r8d, eax
0x180005d1f  mov     r9d, eax
0x180005d22  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005d2c  shr     r8, 2
0x180005d30  mul     r8
0x180005d33  shr     rdx, 3
0x180005d37  lea     rcx, [rdx+rdx*4]
0x180005d3b  add     rcx, rcx
0x180005d3e  sub     r8, rcx
0x180005d41  mov     rbx, [rdi+r8*8+8]
0x180005d46  test    rbx, rbx
0x180005d49  jz      short loc_180005D6B
0x180005d4b  cmp     [rbx], r9d
0x180005d4e  jz      short loc_180005D56
0x180005d50  mov     rbx, [rbx+8]
0x180005d54  jmp     short loc_180005D46
0x180005d56  add     rbx, 10h
0x180005d5a  jz      short loc_180005D6B
0x180005d5c  cmp     qword ptr [rbx+8], 0
0x180005d61  jnz     short loc_180005D6B
0x180005d63  lea     rax, [rdi+4]
0x180005d67  mov     [rbx+8], rax
0x180005d6b  mov     rax, rbx
0x180005d6e  mov     rbx, [rsp+28h+arg_0]
0x180005d73  add     rsp, 20h
0x180005d77  pop     rdi
0x180005d78  retn
```
