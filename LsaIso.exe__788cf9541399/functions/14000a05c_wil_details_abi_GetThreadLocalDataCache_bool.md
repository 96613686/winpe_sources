# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x14000a05c`
- end: `0x14000a119`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400099b0`

## callees

- `0x140007b30`
- `0x14000a05c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a0b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a0b6`

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
0x14000a05c  mov     [rsp+arg_0], rbx
0x14000a061  push    rdi
0x14000a062  sub     rsp, 20h
0x14000a066  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x14000a06d  xor     ebx, ebx
0x14000a06f  test    rdi, rdi
0x14000a072  jz      loc_14000A10B
0x14000a078  cmp     [rdi+8], rbx
0x14000a07c  jnz     short loc_14000A0A3
0x14000a07e  mov     rcx, [rdi]
0x14000a081  lea     rdx, [rsp+28h+arg_8]
0x14000a086  mov     [rsp+28h+arg_8], rbx
0x14000a08b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x14000a090  test    eax, eax
0x14000a092  js      short loc_14000A0A3
0x14000a094  cmp     [rdi+8], rbx
0x14000a098  jnz     short loc_14000A0A3
0x14000a09a  mov     rax, [rsp+28h+arg_8]
0x14000a09f  mov     [rdi+8], rax
0x14000a0a3  mov     rax, [rdi+8]
0x14000a0a7  lea     rcx, [rax+20h]
0x14000a0ab  neg     rax
0x14000a0ae  sbb     rdi, rdi
0x14000a0b1  and     rdi, rcx
0x14000a0b4  jz      short loc_14000A10B
0x14000a0b6  call    cs:__imp_GetCurrentThreadId
0x14000a0bc  mov     r8d, eax
0x14000a0bf  mov     r9d, eax
0x14000a0c2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000a0cc  shr     r8, 2
0x14000a0d0  mul     r8
0x14000a0d3  shr     rdx, 3
0x14000a0d7  lea     rcx, [rdx+rdx*4]
0x14000a0db  add     rcx, rcx
0x14000a0de  sub     r8, rcx
0x14000a0e1  mov     rbx, [rdi+r8*8+8]
0x14000a0e6  test    rbx, rbx
0x14000a0e9  jz      short loc_14000A10B
0x14000a0eb  cmp     [rbx], r9d
0x14000a0ee  jz      short loc_14000A0F6
0x14000a0f0  mov     rbx, [rbx+8]
0x14000a0f4  jmp     short loc_14000A0E6
0x14000a0f6  add     rbx, 10h
0x14000a0fa  jz      short loc_14000A10B
0x14000a0fc  cmp     qword ptr [rbx+8], 0
0x14000a101  jnz     short loc_14000A10B
0x14000a103  lea     rax, [rdi+4]
0x14000a107  mov     [rbx+8], rax
0x14000a10b  mov     rax, rbx
0x14000a10e  mov     rbx, [rsp+28h+arg_0]
0x14000a113  add     rsp, 20h
0x14000a117  pop     rdi
0x14000a118  retn
```
