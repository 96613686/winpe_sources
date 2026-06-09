# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18001d210`
- end: `0x18001d2cb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ca30`

## callees

- `0x18001be2c`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d266`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d266`

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
          if ( i && !*(_QWORD *)(i + 8) )
            *(_QWORD *)(i + 8) = v3 + 4;
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
0x18001d210  mov     [rsp+arg_0], rbx
0x18001d215  push    rdi
0x18001d216  sub     rsp, 20h
0x18001d21a  xor     ebx, ebx
0x18001d21c  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18001d223  test    rdi, rdi
0x18001d226  jz      short loc_18001D2A6
0x18001d228  cmp     [rdi+8], rbx
0x18001d22c  jnz     short loc_18001D253
0x18001d22e  mov     [rsp+28h+arg_8], rbx
0x18001d233  lea     rdx, [rsp+28h+arg_8]
0x18001d238  mov     rcx, [rdi]
0x18001d23b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18001d240  test    eax, eax
0x18001d242  js      short loc_18001D253
0x18001d244  cmp     [rdi+8], rbx
0x18001d248  jnz     short loc_18001D253
0x18001d24a  mov     rax, [rsp+28h+arg_8]
0x18001d24f  mov     [rdi+8], rax
0x18001d253  mov     rcx, [rdi+8]
0x18001d257  lea     rax, [rcx+20h]
0x18001d25b  neg     rcx
0x18001d25e  sbb     rdi, rdi
0x18001d261  and     rdi, rax
0x18001d264  jz      short loc_18001D2A6
0x18001d266  call    cs:__imp_GetCurrentThreadId
0x18001d26c  mov     r9d, eax
0x18001d26f  mov     r8d, eax
0x18001d272  shr     r8, 2
0x18001d276  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001d280  mul     r8
0x18001d283  shr     rdx, 3
0x18001d287  lea     rcx, [rdx+rdx*4]
0x18001d28b  add     rcx, rcx
0x18001d28e  sub     r8, rcx
0x18001d291  mov     rbx, [rdi+r8*8+8]
0x18001d296  jmp     short loc_18001D2A1
0x18001d298  cmp     [rbx], r9d
0x18001d29b  jz      short loc_18001D2B4
0x18001d29d  mov     rbx, [rbx+8]
0x18001d2a1  test    rbx, rbx
0x18001d2a4  jnz     short loc_18001D298
0x18001d2a6  mov     rax, rbx
0x18001d2a9  mov     rbx, [rsp+28h+arg_0]
0x18001d2ae  add     rsp, 20h
0x18001d2b2  pop     rdi
0x18001d2b3  retn
0x18001d2b4  add     rbx, 10h
0x18001d2b8  jz      short loc_18001D2A6
0x18001d2ba  cmp     qword ptr [rbx+8], 0
0x18001d2bf  jnz     short loc_18001D2A6
0x18001d2c1  lea     rax, [rdi+4]
0x18001d2c5  mov     [rbx+8], rax
0x18001d2c9  jmp     short loc_18001D2A6
```
