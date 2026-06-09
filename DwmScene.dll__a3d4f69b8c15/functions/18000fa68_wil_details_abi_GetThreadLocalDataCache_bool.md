# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000fa68`
- end: `0x18000fb25`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f400`

## callees

- `0x18000ef04`
- `0x18000fa68`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fac2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fac2`

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
0x18000fa68  mov     [rsp+arg_0], rbx
0x18000fa6d  push    rdi
0x18000fa6e  sub     rsp, 20h
0x18000fa72  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000fa79  xor     ebx, ebx
0x18000fa7b  test    rdi, rdi
0x18000fa7e  jz      loc_18000FB17
0x18000fa84  cmp     [rdi+8], rbx
0x18000fa88  jnz     short loc_18000FAAF
0x18000fa8a  mov     rcx, [rdi]
0x18000fa8d  lea     rdx, [rsp+28h+arg_8]
0x18000fa92  mov     [rsp+28h+arg_8], rbx
0x18000fa97  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000fa9c  test    eax, eax
0x18000fa9e  js      short loc_18000FAAF
0x18000faa0  cmp     [rdi+8], rbx
0x18000faa4  jnz     short loc_18000FAAF
0x18000faa6  mov     rax, [rsp+28h+arg_8]
0x18000faab  mov     [rdi+8], rax
0x18000faaf  mov     rax, [rdi+8]
0x18000fab3  lea     rcx, [rax+20h]
0x18000fab7  neg     rax
0x18000faba  sbb     rdi, rdi
0x18000fabd  and     rdi, rcx
0x18000fac0  jz      short loc_18000FB17
0x18000fac2  call    cs:__imp_GetCurrentThreadId
0x18000fac8  mov     r8d, eax
0x18000facb  mov     r9d, eax
0x18000face  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000fad8  shr     r8, 2
0x18000fadc  mul     r8
0x18000fadf  shr     rdx, 3
0x18000fae3  lea     rcx, [rdx+rdx*4]
0x18000fae7  add     rcx, rcx
0x18000faea  sub     r8, rcx
0x18000faed  mov     rbx, [rdi+r8*8+8]
0x18000faf2  test    rbx, rbx
0x18000faf5  jz      short loc_18000FB17
0x18000faf7  cmp     [rbx], r9d
0x18000fafa  jz      short loc_18000FB02
0x18000fafc  mov     rbx, [rbx+8]
0x18000fb00  jmp     short loc_18000FAF2
0x18000fb02  add     rbx, 10h
0x18000fb06  jz      short loc_18000FB17
0x18000fb08  cmp     qword ptr [rbx+8], 0
0x18000fb0d  jnz     short loc_18000FB17
0x18000fb0f  lea     rax, [rdi+4]
0x18000fb13  mov     [rbx+8], rax
0x18000fb17  mov     rax, rbx
0x18000fb1a  mov     rbx, [rsp+28h+arg_0]
0x18000fb1f  add     rsp, 20h
0x18000fb23  pop     rdi
0x18000fb24  retn
```
