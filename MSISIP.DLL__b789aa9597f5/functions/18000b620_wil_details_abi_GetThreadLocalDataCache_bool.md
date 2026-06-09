# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000b620`
- end: `0x18000b6dd`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009540`

## callees

- `0x1800077a8`
- `0x18000b620`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b67a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b67a`

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
0x18000b620  mov     [rsp+arg_0], rbx
0x18000b625  push    rdi
0x18000b626  sub     rsp, 20h
0x18000b62a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000b631  xor     ebx, ebx
0x18000b633  test    rdi, rdi
0x18000b636  jz      loc_18000B6CF
0x18000b63c  cmp     [rdi+8], rbx
0x18000b640  jnz     short loc_18000B667
0x18000b642  mov     rcx, [rdi]
0x18000b645  lea     rdx, [rsp+28h+arg_8]
0x18000b64a  mov     [rsp+28h+arg_8], rbx
0x18000b64f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000b654  test    eax, eax
0x18000b656  js      short loc_18000B667
0x18000b658  cmp     [rdi+8], rbx
0x18000b65c  jnz     short loc_18000B667
0x18000b65e  mov     rax, [rsp+28h+arg_8]
0x18000b663  mov     [rdi+8], rax
0x18000b667  mov     rax, [rdi+8]
0x18000b66b  lea     rcx, [rax+20h]
0x18000b66f  neg     rax
0x18000b672  sbb     rdi, rdi
0x18000b675  and     rdi, rcx
0x18000b678  jz      short loc_18000B6CF
0x18000b67a  call    cs:__imp_GetCurrentThreadId
0x18000b680  mov     r8d, eax
0x18000b683  mov     r9d, eax
0x18000b686  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000b690  shr     r8, 2
0x18000b694  mul     r8
0x18000b697  shr     rdx, 3
0x18000b69b  lea     rcx, [rdx+rdx*4]
0x18000b69f  add     rcx, rcx
0x18000b6a2  sub     r8, rcx
0x18000b6a5  mov     rbx, [rdi+r8*8+8]
0x18000b6aa  test    rbx, rbx
0x18000b6ad  jz      short loc_18000B6CF
0x18000b6af  cmp     [rbx], r9d
0x18000b6b2  jz      short loc_18000B6BA
0x18000b6b4  mov     rbx, [rbx+8]
0x18000b6b8  jmp     short loc_18000B6AA
0x18000b6ba  add     rbx, 10h
0x18000b6be  jz      short loc_18000B6CF
0x18000b6c0  cmp     qword ptr [rbx+8], 0
0x18000b6c5  jnz     short loc_18000B6CF
0x18000b6c7  lea     rax, [rdi+4]
0x18000b6cb  mov     [rbx+8], rax
0x18000b6cf  mov     rax, rbx
0x18000b6d2  mov     rbx, [rsp+28h+arg_0]
0x18000b6d7  add     rsp, 20h
0x18000b6db  pop     rdi
0x18000b6dc  retn
```
