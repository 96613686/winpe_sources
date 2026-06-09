# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800060fc`
- end: `0x1800061b9`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800059e0`

## callees

- `0x180005018`
- `0x1800060fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006156`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006156`

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
0x1800060fc  mov     [rsp+arg_0], rbx
0x180006101  push    rdi
0x180006102  sub     rsp, 20h
0x180006106  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000610d  xor     ebx, ebx
0x18000610f  test    rdi, rdi
0x180006112  jz      loc_1800061AB
0x180006118  cmp     [rdi+8], rbx
0x18000611c  jnz     short loc_180006143
0x18000611e  mov     rcx, [rdi]
0x180006121  lea     rdx, [rsp+28h+arg_8]
0x180006126  mov     [rsp+28h+arg_8], rbx
0x18000612b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180006130  test    eax, eax
0x180006132  js      short loc_180006143
0x180006134  cmp     [rdi+8], rbx
0x180006138  jnz     short loc_180006143
0x18000613a  mov     rax, [rsp+28h+arg_8]
0x18000613f  mov     [rdi+8], rax
0x180006143  mov     rax, [rdi+8]
0x180006147  lea     rcx, [rax+20h]
0x18000614b  neg     rax
0x18000614e  sbb     rdi, rdi
0x180006151  and     rdi, rcx
0x180006154  jz      short loc_1800061AB
0x180006156  call    cs:__imp_GetCurrentThreadId
0x18000615c  mov     r8d, eax
0x18000615f  mov     r9d, eax
0x180006162  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000616c  shr     r8, 2
0x180006170  mul     r8
0x180006173  shr     rdx, 3
0x180006177  lea     rcx, [rdx+rdx*4]
0x18000617b  add     rcx, rcx
0x18000617e  sub     r8, rcx
0x180006181  mov     rbx, [rdi+r8*8+8]
0x180006186  test    rbx, rbx
0x180006189  jz      short loc_1800061AB
0x18000618b  cmp     [rbx], r9d
0x18000618e  jz      short loc_180006196
0x180006190  mov     rbx, [rbx+8]
0x180006194  jmp     short loc_180006186
0x180006196  add     rbx, 10h
0x18000619a  jz      short loc_1800061AB
0x18000619c  cmp     qword ptr [rbx+8], 0
0x1800061a1  jnz     short loc_1800061AB
0x1800061a3  lea     rax, [rdi+4]
0x1800061a7  mov     [rbx+8], rax
0x1800061ab  mov     rax, rbx
0x1800061ae  mov     rbx, [rsp+28h+arg_0]
0x1800061b3  add     rsp, 20h
0x1800061b7  pop     rdi
0x1800061b8  retn
```
