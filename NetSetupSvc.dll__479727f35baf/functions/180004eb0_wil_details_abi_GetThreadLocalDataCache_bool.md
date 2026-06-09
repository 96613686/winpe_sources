# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004eb0`
- end: `0x180004f6d`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800047f0`

## callees

- `0x180004338`
- `0x180004eb0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f0a`

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
0x180004eb0  mov     [rsp+arg_0], rbx
0x180004eb5  push    rdi
0x180004eb6  sub     rsp, 20h
0x180004eba  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004ec1  xor     ebx, ebx
0x180004ec3  test    rdi, rdi
0x180004ec6  jz      loc_180004F5F
0x180004ecc  cmp     [rdi+8], rbx
0x180004ed0  jnz     short loc_180004EF7
0x180004ed2  mov     rcx, [rdi]
0x180004ed5  lea     rdx, [rsp+28h+arg_8]
0x180004eda  mov     [rsp+28h+arg_8], rbx
0x180004edf  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004ee4  test    eax, eax
0x180004ee6  js      short loc_180004EF7
0x180004ee8  cmp     [rdi+8], rbx
0x180004eec  jnz     short loc_180004EF7
0x180004eee  mov     rax, [rsp+28h+arg_8]
0x180004ef3  mov     [rdi+8], rax
0x180004ef7  mov     rax, [rdi+8]
0x180004efb  lea     rcx, [rax+20h]
0x180004eff  neg     rax
0x180004f02  sbb     rdi, rdi
0x180004f05  and     rdi, rcx
0x180004f08  jz      short loc_180004F5F
0x180004f0a  call    cs:__imp_GetCurrentThreadId
0x180004f10  mov     r8d, eax
0x180004f13  mov     r9d, eax
0x180004f16  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004f20  shr     r8, 2
0x180004f24  mul     r8
0x180004f27  shr     rdx, 3
0x180004f2b  lea     rcx, [rdx+rdx*4]
0x180004f2f  add     rcx, rcx
0x180004f32  sub     r8, rcx
0x180004f35  mov     rbx, [rdi+r8*8+8]
0x180004f3a  test    rbx, rbx
0x180004f3d  jz      short loc_180004F5F
0x180004f3f  cmp     [rbx], r9d
0x180004f42  jz      short loc_180004F4A
0x180004f44  mov     rbx, [rbx+8]
0x180004f48  jmp     short loc_180004F3A
0x180004f4a  add     rbx, 10h
0x180004f4e  jz      short loc_180004F5F
0x180004f50  cmp     qword ptr [rbx+8], 0
0x180004f55  jnz     short loc_180004F5F
0x180004f57  lea     rax, [rdi+4]
0x180004f5b  mov     [rbx+8], rax
0x180004f5f  mov     rax, rbx
0x180004f62  mov     rbx, [rsp+28h+arg_0]
0x180004f67  add     rsp, 20h
0x180004f6b  pop     rdi
0x180004f6c  retn
```
