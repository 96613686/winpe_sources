# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000a0c8`
- end: `0x18000a185`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009ae0`

## callees

- `0x18000966c`
- `0x18000a0c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a122`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a122`

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
0x18000a0c8  mov     [rsp+arg_0], rbx
0x18000a0cd  push    rdi
0x18000a0ce  sub     rsp, 20h
0x18000a0d2  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000a0d9  xor     ebx, ebx
0x18000a0db  test    rdi, rdi
0x18000a0de  jz      loc_18000A177
0x18000a0e4  cmp     [rdi+8], rbx
0x18000a0e8  jnz     short loc_18000A10F
0x18000a0ea  mov     rcx, [rdi]
0x18000a0ed  lea     rdx, [rsp+28h+arg_8]
0x18000a0f2  mov     [rsp+28h+arg_8], rbx
0x18000a0f7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000a0fc  test    eax, eax
0x18000a0fe  js      short loc_18000A10F
0x18000a100  cmp     [rdi+8], rbx
0x18000a104  jnz     short loc_18000A10F
0x18000a106  mov     rax, [rsp+28h+arg_8]
0x18000a10b  mov     [rdi+8], rax
0x18000a10f  mov     rax, [rdi+8]
0x18000a113  lea     rcx, [rax+20h]
0x18000a117  neg     rax
0x18000a11a  sbb     rdi, rdi
0x18000a11d  and     rdi, rcx
0x18000a120  jz      short loc_18000A177
0x18000a122  call    cs:__imp_GetCurrentThreadId
0x18000a128  mov     r8d, eax
0x18000a12b  mov     r9d, eax
0x18000a12e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000a138  shr     r8, 2
0x18000a13c  mul     r8
0x18000a13f  shr     rdx, 3
0x18000a143  lea     rcx, [rdx+rdx*4]
0x18000a147  add     rcx, rcx
0x18000a14a  sub     r8, rcx
0x18000a14d  mov     rbx, [rdi+r8*8+8]
0x18000a152  test    rbx, rbx
0x18000a155  jz      short loc_18000A177
0x18000a157  cmp     [rbx], r9d
0x18000a15a  jz      short loc_18000A162
0x18000a15c  mov     rbx, [rbx+8]
0x18000a160  jmp     short loc_18000A152
0x18000a162  add     rbx, 10h
0x18000a166  jz      short loc_18000A177
0x18000a168  cmp     qword ptr [rbx+8], 0
0x18000a16d  jnz     short loc_18000A177
0x18000a16f  lea     rax, [rdi+4]
0x18000a173  mov     [rbx+8], rax
0x18000a177  mov     rax, rbx
0x18000a17a  mov     rbx, [rsp+28h+arg_0]
0x18000a17f  add     rsp, 20h
0x18000a183  pop     rdi
0x18000a184  retn
```
