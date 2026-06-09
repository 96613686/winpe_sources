# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000c2d0`
- end: `0x18000c38d`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bb70`

## callees

- `0x18000af98`
- `0x18000c2d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c32a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c32a`

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
0x18000c2d0  mov     [rsp+arg_0], rbx
0x18000c2d5  push    rdi
0x18000c2d6  sub     rsp, 20h
0x18000c2da  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000c2e1  xor     ebx, ebx
0x18000c2e3  test    rdi, rdi
0x18000c2e6  jz      loc_18000C37F
0x18000c2ec  cmp     [rdi+8], rbx
0x18000c2f0  jnz     short loc_18000C317
0x18000c2f2  mov     rcx, [rdi]
0x18000c2f5  lea     rdx, [rsp+28h+arg_8]
0x18000c2fa  mov     [rsp+28h+arg_8], rbx
0x18000c2ff  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000c304  test    eax, eax
0x18000c306  js      short loc_18000C317
0x18000c308  cmp     [rdi+8], rbx
0x18000c30c  jnz     short loc_18000C317
0x18000c30e  mov     rax, [rsp+28h+arg_8]
0x18000c313  mov     [rdi+8], rax
0x18000c317  mov     rax, [rdi+8]
0x18000c31b  lea     rcx, [rax+20h]
0x18000c31f  neg     rax
0x18000c322  sbb     rdi, rdi
0x18000c325  and     rdi, rcx
0x18000c328  jz      short loc_18000C37F
0x18000c32a  call    cs:__imp_GetCurrentThreadId
0x18000c330  mov     r8d, eax
0x18000c333  mov     r9d, eax
0x18000c336  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000c340  shr     r8, 2
0x18000c344  mul     r8
0x18000c347  shr     rdx, 3
0x18000c34b  lea     rcx, [rdx+rdx*4]
0x18000c34f  add     rcx, rcx
0x18000c352  sub     r8, rcx
0x18000c355  mov     rbx, [rdi+r8*8+8]
0x18000c35a  test    rbx, rbx
0x18000c35d  jz      short loc_18000C37F
0x18000c35f  cmp     [rbx], r9d
0x18000c362  jz      short loc_18000C36A
0x18000c364  mov     rbx, [rbx+8]
0x18000c368  jmp     short loc_18000C35A
0x18000c36a  add     rbx, 10h
0x18000c36e  jz      short loc_18000C37F
0x18000c370  cmp     qword ptr [rbx+8], 0
0x18000c375  jnz     short loc_18000C37F
0x18000c377  lea     rax, [rdi+4]
0x18000c37b  mov     [rbx+8], rax
0x18000c37f  mov     rax, rbx
0x18000c382  mov     rbx, [rsp+28h+arg_0]
0x18000c387  add     rsp, 20h
0x18000c38b  pop     rdi
0x18000c38c  retn
```
