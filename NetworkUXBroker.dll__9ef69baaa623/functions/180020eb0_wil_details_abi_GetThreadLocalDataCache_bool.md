# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180020eb0`
- end: `0x180020f6d`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180020c40`

## callees

- `0x18002086c`
- `0x180020eb0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020f0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020f0a`

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
0x180020eb0  mov     [rsp+arg_0], rbx
0x180020eb5  push    rdi
0x180020eb6  sub     rsp, 20h
0x180020eba  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180020ec1  xor     ebx, ebx
0x180020ec3  test    rdi, rdi
0x180020ec6  jz      loc_180020F5F
0x180020ecc  cmp     [rdi+8], rbx
0x180020ed0  jnz     short loc_180020EF7
0x180020ed2  mov     rcx, [rdi]
0x180020ed5  lea     rdx, [rsp+28h+arg_8]
0x180020eda  mov     [rsp+28h+arg_8], rbx
0x180020edf  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180020ee4  test    eax, eax
0x180020ee6  js      short loc_180020EF7
0x180020ee8  cmp     [rdi+8], rbx
0x180020eec  jnz     short loc_180020EF7
0x180020eee  mov     rax, [rsp+28h+arg_8]
0x180020ef3  mov     [rdi+8], rax
0x180020ef7  mov     rax, [rdi+8]
0x180020efb  lea     rcx, [rax+20h]
0x180020eff  neg     rax
0x180020f02  sbb     rdi, rdi
0x180020f05  and     rdi, rcx
0x180020f08  jz      short loc_180020F5F
0x180020f0a  call    cs:__imp_GetCurrentThreadId
0x180020f10  mov     r8d, eax
0x180020f13  mov     r9d, eax
0x180020f16  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180020f20  shr     r8, 2
0x180020f24  mul     r8
0x180020f27  shr     rdx, 3
0x180020f2b  lea     rcx, [rdx+rdx*4]
0x180020f2f  add     rcx, rcx
0x180020f32  sub     r8, rcx
0x180020f35  mov     rbx, [rdi+r8*8+8]
0x180020f3a  test    rbx, rbx
0x180020f3d  jz      short loc_180020F5F
0x180020f3f  cmp     [rbx], r9d
0x180020f42  jz      short loc_180020F4A
0x180020f44  mov     rbx, [rbx+8]
0x180020f48  jmp     short loc_180020F3A
0x180020f4a  add     rbx, 10h
0x180020f4e  jz      short loc_180020F5F
0x180020f50  cmp     qword ptr [rbx+8], 0
0x180020f55  jnz     short loc_180020F5F
0x180020f57  lea     rax, [rdi+4]
0x180020f5b  mov     [rbx+8], rax
0x180020f5f  mov     rax, rbx
0x180020f62  mov     rbx, [rsp+28h+arg_0]
0x180020f67  add     rsp, 20h
0x180020f6b  pop     rdi
0x180020f6c  retn
```
