# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180009af0`
- end: `0x180009bad`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800091b0`

## callees

- `0x180008118`
- `0x180009af0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009b4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009b4a`

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
0x180009af0  mov     [rsp+arg_0], rbx
0x180009af5  push    rdi
0x180009af6  sub     rsp, 20h
0x180009afa  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180009b01  xor     ebx, ebx
0x180009b03  test    rdi, rdi
0x180009b06  jz      loc_180009B9F
0x180009b0c  cmp     [rdi+8], rbx
0x180009b10  jnz     short loc_180009B37
0x180009b12  mov     rcx, [rdi]
0x180009b15  lea     rdx, [rsp+28h+arg_8]
0x180009b1a  mov     [rsp+28h+arg_8], rbx
0x180009b1f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180009b24  test    eax, eax
0x180009b26  js      short loc_180009B37
0x180009b28  cmp     [rdi+8], rbx
0x180009b2c  jnz     short loc_180009B37
0x180009b2e  mov     rax, [rsp+28h+arg_8]
0x180009b33  mov     [rdi+8], rax
0x180009b37  mov     rax, [rdi+8]
0x180009b3b  lea     rcx, [rax+20h]
0x180009b3f  neg     rax
0x180009b42  sbb     rdi, rdi
0x180009b45  and     rdi, rcx
0x180009b48  jz      short loc_180009B9F
0x180009b4a  call    cs:__imp_GetCurrentThreadId
0x180009b50  mov     r8d, eax
0x180009b53  mov     r9d, eax
0x180009b56  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180009b60  shr     r8, 2
0x180009b64  mul     r8
0x180009b67  shr     rdx, 3
0x180009b6b  lea     rcx, [rdx+rdx*4]
0x180009b6f  add     rcx, rcx
0x180009b72  sub     r8, rcx
0x180009b75  mov     rbx, [rdi+r8*8+8]
0x180009b7a  test    rbx, rbx
0x180009b7d  jz      short loc_180009B9F
0x180009b7f  cmp     [rbx], r9d
0x180009b82  jz      short loc_180009B8A
0x180009b84  mov     rbx, [rbx+8]
0x180009b88  jmp     short loc_180009B7A
0x180009b8a  add     rbx, 10h
0x180009b8e  jz      short loc_180009B9F
0x180009b90  cmp     qword ptr [rbx+8], 0
0x180009b95  jnz     short loc_180009B9F
0x180009b97  lea     rax, [rdi+4]
0x180009b9b  mov     [rbx+8], rax
0x180009b9f  mov     rax, rbx
0x180009ba2  mov     rbx, [rsp+28h+arg_0]
0x180009ba7  add     rsp, 20h
0x180009bab  pop     rdi
0x180009bac  retn
```
