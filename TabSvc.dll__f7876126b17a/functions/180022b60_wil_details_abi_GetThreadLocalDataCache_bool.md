# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180022b60`
- end: `0x180022c1d`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180021a60`

## callees

- `0x18001f5fc`
- `0x180022b60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022bba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022bba`

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
0x180022b60  mov     [rsp+arg_0], rbx
0x180022b65  push    rdi
0x180022b66  sub     rsp, 20h
0x180022b6a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180022b71  xor     ebx, ebx
0x180022b73  test    rdi, rdi
0x180022b76  jz      loc_180022C0F
0x180022b7c  cmp     [rdi+8], rbx
0x180022b80  jnz     short loc_180022BA7
0x180022b82  mov     rcx, [rdi]
0x180022b85  lea     rdx, [rsp+28h+arg_8]
0x180022b8a  mov     [rsp+28h+arg_8], rbx
0x180022b8f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180022b94  test    eax, eax
0x180022b96  js      short loc_180022BA7
0x180022b98  cmp     [rdi+8], rbx
0x180022b9c  jnz     short loc_180022BA7
0x180022b9e  mov     rax, [rsp+28h+arg_8]
0x180022ba3  mov     [rdi+8], rax
0x180022ba7  mov     rax, [rdi+8]
0x180022bab  lea     rcx, [rax+20h]
0x180022baf  neg     rax
0x180022bb2  sbb     rdi, rdi
0x180022bb5  and     rdi, rcx
0x180022bb8  jz      short loc_180022C0F
0x180022bba  call    cs:__imp_GetCurrentThreadId
0x180022bc0  mov     r8d, eax
0x180022bc3  mov     r9d, eax
0x180022bc6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180022bd0  shr     r8, 2
0x180022bd4  mul     r8
0x180022bd7  shr     rdx, 3
0x180022bdb  lea     rcx, [rdx+rdx*4]
0x180022bdf  add     rcx, rcx
0x180022be2  sub     r8, rcx
0x180022be5  mov     rbx, [rdi+r8*8+8]
0x180022bea  test    rbx, rbx
0x180022bed  jz      short loc_180022C0F
0x180022bef  cmp     [rbx], r9d
0x180022bf2  jz      short loc_180022BFA
0x180022bf4  mov     rbx, [rbx+8]
0x180022bf8  jmp     short loc_180022BEA
0x180022bfa  add     rbx, 10h
0x180022bfe  jz      short loc_180022C0F
0x180022c00  cmp     qword ptr [rbx+8], 0
0x180022c05  jnz     short loc_180022C0F
0x180022c07  lea     rax, [rdi+4]
0x180022c0b  mov     [rbx+8], rax
0x180022c0f  mov     rax, rbx
0x180022c12  mov     rbx, [rsp+28h+arg_0]
0x180022c17  add     rsp, 20h
0x180022c1b  pop     rdi
0x180022c1c  retn
```
