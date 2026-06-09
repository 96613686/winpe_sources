# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000acc8`
- end: `0x18000ad85`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a1e0`

## callees

- `0x180008f18`
- `0x18000acc8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ad22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ad22`

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
0x18000acc8  mov     [rsp+arg_0], rbx
0x18000accd  push    rdi
0x18000acce  sub     rsp, 20h
0x18000acd2  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000acd9  xor     ebx, ebx
0x18000acdb  test    rdi, rdi
0x18000acde  jz      loc_18000AD77
0x18000ace4  cmp     [rdi+8], rbx
0x18000ace8  jnz     short loc_18000AD0F
0x18000acea  mov     rcx, [rdi]
0x18000aced  lea     rdx, [rsp+28h+arg_8]
0x18000acf2  mov     [rsp+28h+arg_8], rbx
0x18000acf7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000acfc  test    eax, eax
0x18000acfe  js      short loc_18000AD0F
0x18000ad00  cmp     [rdi+8], rbx
0x18000ad04  jnz     short loc_18000AD0F
0x18000ad06  mov     rax, [rsp+28h+arg_8]
0x18000ad0b  mov     [rdi+8], rax
0x18000ad0f  mov     rax, [rdi+8]
0x18000ad13  lea     rcx, [rax+20h]
0x18000ad17  neg     rax
0x18000ad1a  sbb     rdi, rdi
0x18000ad1d  and     rdi, rcx
0x18000ad20  jz      short loc_18000AD77
0x18000ad22  call    cs:__imp_GetCurrentThreadId
0x18000ad28  mov     r8d, eax
0x18000ad2b  mov     r9d, eax
0x18000ad2e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000ad38  shr     r8, 2
0x18000ad3c  mul     r8
0x18000ad3f  shr     rdx, 3
0x18000ad43  lea     rcx, [rdx+rdx*4]
0x18000ad47  add     rcx, rcx
0x18000ad4a  sub     r8, rcx
0x18000ad4d  mov     rbx, [rdi+r8*8+8]
0x18000ad52  test    rbx, rbx
0x18000ad55  jz      short loc_18000AD77
0x18000ad57  cmp     [rbx], r9d
0x18000ad5a  jz      short loc_18000AD62
0x18000ad5c  mov     rbx, [rbx+8]
0x18000ad60  jmp     short loc_18000AD52
0x18000ad62  add     rbx, 10h
0x18000ad66  jz      short loc_18000AD77
0x18000ad68  cmp     qword ptr [rbx+8], 0
0x18000ad6d  jnz     short loc_18000AD77
0x18000ad6f  lea     rax, [rdi+4]
0x18000ad73  mov     [rbx+8], rax
0x18000ad77  mov     rax, rbx
0x18000ad7a  mov     rbx, [rsp+28h+arg_0]
0x18000ad7f  add     rsp, 20h
0x18000ad83  pop     rdi
0x18000ad84  retn
```
