# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180018900`
- end: `0x1800189c6`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180018470`

## callees

- `0x1800180dc`
- `0x180018900`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001895a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001895a`

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
0x180018900  mov     [rsp+arg_0], rbx
0x180018905  push    rdi
0x180018906  sub     rsp, 20h
0x18001890a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180018911  xor     ebx, ebx
0x180018913  test    rdi, rdi
0x180018916  jz      loc_1800189A0
0x18001891c  cmp     [rdi+8], rbx
0x180018920  jnz     short loc_180018947
0x180018922  mov     rcx, [rdi]
0x180018925  lea     rdx, [rsp+28h+arg_8]
0x18001892a  mov     [rsp+28h+arg_8], rbx
0x18001892f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180018934  test    eax, eax
0x180018936  js      short loc_180018947
0x180018938  cmp     [rdi+8], rbx
0x18001893c  jnz     short loc_180018947
0x18001893e  mov     rax, [rsp+28h+arg_8]
0x180018943  mov     [rdi+8], rax
0x180018947  mov     rax, [rdi+8]
0x18001894b  lea     rcx, [rax+20h]
0x18001894f  neg     rax
0x180018952  sbb     rdi, rdi
0x180018955  and     rdi, rcx
0x180018958  jz      short loc_1800189A0
0x18001895a  call    cs:__imp_GetCurrentThreadId
0x180018961  nop     dword ptr [rax+rax+00h]
0x180018966  mov     r8d, eax
0x180018969  mov     r9d, eax
0x18001896c  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180018976  shr     r8, 2
0x18001897a  mul     r8
0x18001897d  shr     rdx, 3
0x180018981  lea     rcx, [rdx+rdx*4]
0x180018985  add     rcx, rcx
0x180018988  sub     r8, rcx
0x18001898b  mov     rbx, [rdi+r8*8+8]
0x180018990  jmp     short loc_18001899B
0x180018992  cmp     [rbx], r9d
0x180018995  jz      short loc_1800189AF
0x180018997  mov     rbx, [rbx+8]
0x18001899b  test    rbx, rbx
0x18001899e  jnz     short loc_180018992
0x1800189a0  mov     rax, rbx
0x1800189a3  mov     rbx, [rsp+28h+arg_0]
0x1800189a8  add     rsp, 20h
0x1800189ac  pop     rdi
0x1800189ad  retn
0x1800189af  add     rbx, 10h
0x1800189b3  jz      short loc_1800189A0
0x1800189b5  cmp     qword ptr [rbx+8], 0
0x1800189ba  jnz     short loc_1800189A0
0x1800189bc  lea     rax, [rdi+4]
0x1800189c0  mov     [rbx+8], rax
0x1800189c4  jmp     short loc_1800189A0
```
