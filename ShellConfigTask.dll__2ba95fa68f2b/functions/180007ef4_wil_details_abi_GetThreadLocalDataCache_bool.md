# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180007ef4`
- end: `0x180007faf`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800076c0`

## callees

- `0x180005a58`
- `0x180007ef4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007f4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007f4a`

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
0x180007ef4  mov     [rsp+arg_0], rbx
0x180007ef9  push    rdi
0x180007efa  sub     rsp, 20h
0x180007efe  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180007f05  xor     ebx, ebx
0x180007f07  test    rdi, rdi
0x180007f0a  jz      short loc_180007F8A
0x180007f0c  cmp     [rdi+8], rbx
0x180007f10  jnz     short loc_180007F37
0x180007f12  mov     rcx, [rdi]
0x180007f15  lea     rdx, [rsp+28h+arg_8]
0x180007f1a  mov     [rsp+28h+arg_8], rbx
0x180007f1f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180007f24  test    eax, eax
0x180007f26  js      short loc_180007F37
0x180007f28  cmp     [rdi+8], rbx
0x180007f2c  jnz     short loc_180007F37
0x180007f2e  mov     rax, [rsp+28h+arg_8]
0x180007f33  mov     [rdi+8], rax
0x180007f37  mov     rax, [rdi+8]
0x180007f3b  lea     rcx, [rax+20h]
0x180007f3f  neg     rax
0x180007f42  sbb     rdi, rdi
0x180007f45  and     rdi, rcx
0x180007f48  jz      short loc_180007F8A
0x180007f4a  call    cs:__imp_GetCurrentThreadId
0x180007f50  mov     r8d, eax
0x180007f53  mov     r9d, eax
0x180007f56  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007f60  shr     r8, 2
0x180007f64  mul     r8
0x180007f67  shr     rdx, 3
0x180007f6b  lea     rcx, [rdx+rdx*4]
0x180007f6f  add     rcx, rcx
0x180007f72  sub     r8, rcx
0x180007f75  mov     rbx, [rdi+r8*8+8]
0x180007f7a  jmp     short loc_180007F85
0x180007f7c  cmp     [rbx], r9d
0x180007f7f  jz      short loc_180007F98
0x180007f81  mov     rbx, [rbx+8]
0x180007f85  test    rbx, rbx
0x180007f88  jnz     short loc_180007F7C
0x180007f8a  mov     rax, rbx
0x180007f8d  mov     rbx, [rsp+28h+arg_0]
0x180007f92  add     rsp, 20h
0x180007f96  pop     rdi
0x180007f97  retn
0x180007f98  add     rbx, 10h
0x180007f9c  jz      short loc_180007F8A
0x180007f9e  cmp     qword ptr [rbx+8], 0
0x180007fa3  jnz     short loc_180007F8A
0x180007fa5  lea     rax, [rdi+4]
0x180007fa9  mov     [rbx+8], rax
0x180007fad  jmp     short loc_180007F8A
```
