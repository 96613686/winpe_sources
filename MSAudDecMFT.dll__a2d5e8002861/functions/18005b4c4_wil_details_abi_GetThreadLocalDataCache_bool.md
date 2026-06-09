# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18005b4c4`
- end: `0x18005b58b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `199`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18005ac30`

## callees

- `0x180058c34`
- `0x18005b4c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005b51e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005b51e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 i; // rbx
  __int64 v2; // rdi
  __int64 v3; // rdi
  DWORD CurrentThreadId; // r9d
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  i = 0;
  v2 = wil::details_abi::g_pProcessLocalData;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v6 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
                  *(_QWORD *)wil::details_abi::g_pProcessLocalData,
                  &v6) >= 0
        && !*(_QWORD *)(v2 + 8) )
      {
        *(_QWORD *)(v2 + 8) = v6;
      }
    }
    v3 = (*(_QWORD *)(v2 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v2 + 8) != 0);
    if ( v3 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v3 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          i += 16;
          break;
        }
      }
      if ( i && !*(_QWORD *)(i + 8) )
        *(_QWORD *)(i + 8) = v3 + 4;
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)i;
}

```

## disassembly

```asm
0x18005b4c4  mov     [rsp+arg_0], rbx
0x18005b4c9  push    rdi
0x18005b4ca  sub     rsp, 20h
0x18005b4ce  xor     ebx, ebx
0x18005b4d0  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18005b4d7  test    rdi, rdi
0x18005b4da  jz      loc_18005B57C
0x18005b4e0  cmp     [rdi+8], rbx
0x18005b4e4  jnz     short loc_18005B50B
0x18005b4e6  mov     [rsp+28h+arg_8], rbx
0x18005b4eb  lea     rdx, [rsp+28h+arg_8]
0x18005b4f0  mov     rcx, [rdi]
0x18005b4f3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18005b4f8  test    eax, eax
0x18005b4fa  js      short loc_18005B50B
0x18005b4fc  cmp     [rdi+8], rbx
0x18005b500  jnz     short loc_18005B50B
0x18005b502  mov     rax, [rsp+28h+arg_8]
0x18005b507  mov     [rdi+8], rax
0x18005b50b  mov     rcx, [rdi+8]
0x18005b50f  lea     rax, [rcx+20h]
0x18005b513  neg     rcx
0x18005b516  sbb     rdi, rdi
0x18005b519  and     rdi, rax
0x18005b51c  jz      short loc_18005B57C
0x18005b51e  call    cs:__imp_GetCurrentThreadId
0x18005b525  nop     dword ptr [rax+rax+00h]
0x18005b52a  mov     r9d, eax
0x18005b52d  mov     r8d, eax
0x18005b530  shr     r8, 2
0x18005b534  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18005b53e  mul     r8
0x18005b541  shr     rdx, 3
0x18005b545  lea     rcx, [rdx+rdx*4]
0x18005b549  add     rcx, rcx
0x18005b54c  sub     r8, rcx
0x18005b54f  mov     rbx, [rdi+r8*8+8]
0x18005b554  test    rbx, rbx
0x18005b557  jz      short loc_18005B568
0x18005b559  cmp     [rbx], r9d
0x18005b55c  jz      short loc_18005B564
0x18005b55e  mov     rbx, [rbx+8]
0x18005b562  jmp     short loc_18005B554
0x18005b564  add     rbx, 10h
0x18005b568  test    rbx, rbx
0x18005b56b  jz      short loc_18005B57C
0x18005b56d  cmp     qword ptr [rbx+8], 0
0x18005b572  jnz     short loc_18005B57C
0x18005b574  lea     rcx, [rdi+4]
0x18005b578  mov     [rbx+8], rcx
0x18005b57c  mov     rax, rbx
0x18005b57f  mov     rbx, [rsp+28h+arg_0]
0x18005b584  add     rsp, 20h
0x18005b588  pop     rdi
0x18005b589  retn
```
