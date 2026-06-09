# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140005f54`
- end: `0x140006011`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400059c0`

## callees

- `0x140005508`
- `0x140005f54`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005fae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005fae`

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
0x140005f54  mov     [rsp+arg_0], rbx
0x140005f59  push    rdi
0x140005f5a  sub     rsp, 20h
0x140005f5e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140005f65  xor     ebx, ebx
0x140005f67  test    rdi, rdi
0x140005f6a  jz      loc_140006003
0x140005f70  cmp     [rdi+8], rbx
0x140005f74  jnz     short loc_140005F9B
0x140005f76  mov     rcx, [rdi]
0x140005f79  lea     rdx, [rsp+28h+arg_8]
0x140005f7e  mov     [rsp+28h+arg_8], rbx
0x140005f83  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140005f88  test    eax, eax
0x140005f8a  js      short loc_140005F9B
0x140005f8c  cmp     [rdi+8], rbx
0x140005f90  jnz     short loc_140005F9B
0x140005f92  mov     rax, [rsp+28h+arg_8]
0x140005f97  mov     [rdi+8], rax
0x140005f9b  mov     rax, [rdi+8]
0x140005f9f  lea     rcx, [rax+20h]
0x140005fa3  neg     rax
0x140005fa6  sbb     rdi, rdi
0x140005fa9  and     rdi, rcx
0x140005fac  jz      short loc_140006003
0x140005fae  call    cs:__imp_GetCurrentThreadId
0x140005fb4  mov     r8d, eax
0x140005fb7  mov     r9d, eax
0x140005fba  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140005fc4  shr     r8, 2
0x140005fc8  mul     r8
0x140005fcb  shr     rdx, 3
0x140005fcf  lea     rcx, [rdx+rdx*4]
0x140005fd3  add     rcx, rcx
0x140005fd6  sub     r8, rcx
0x140005fd9  mov     rbx, [rdi+r8*8+8]
0x140005fde  test    rbx, rbx
0x140005fe1  jz      short loc_140006003
0x140005fe3  cmp     [rbx], r9d
0x140005fe6  jz      short loc_140005FEE
0x140005fe8  mov     rbx, [rbx+8]
0x140005fec  jmp     short loc_140005FDE
0x140005fee  add     rbx, 10h
0x140005ff2  jz      short loc_140006003
0x140005ff4  cmp     qword ptr [rbx+8], 0
0x140005ff9  jnz     short loc_140006003
0x140005ffb  lea     rax, [rdi+4]
0x140005fff  mov     [rbx+8], rax
0x140006003  mov     rax, rbx
0x140006006  mov     rbx, [rsp+28h+arg_0]
0x14000600b  add     rsp, 20h
0x14000600f  pop     rdi
0x140006010  retn
```
