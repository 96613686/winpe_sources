# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180007f4c`
- end: `0x180008007`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007a90`

## callees

- `0x1800073b8`
- `0x180007f4c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007fa2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007fa2`

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
0x180007f4c  mov     [rsp+arg_0], rbx
0x180007f51  push    rdi
0x180007f52  sub     rsp, 20h
0x180007f56  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180007f5d  xor     ebx, ebx
0x180007f5f  test    rdi, rdi
0x180007f62  jz      short loc_180007FE2
0x180007f64  cmp     [rdi+8], rbx
0x180007f68  jnz     short loc_180007F8F
0x180007f6a  mov     rcx, [rdi]
0x180007f6d  lea     rdx, [rsp+28h+arg_8]
0x180007f72  mov     [rsp+28h+arg_8], rbx
0x180007f77  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180007f7c  test    eax, eax
0x180007f7e  js      short loc_180007F8F
0x180007f80  cmp     [rdi+8], rbx
0x180007f84  jnz     short loc_180007F8F
0x180007f86  mov     rax, [rsp+28h+arg_8]
0x180007f8b  mov     [rdi+8], rax
0x180007f8f  mov     rax, [rdi+8]
0x180007f93  lea     rcx, [rax+20h]
0x180007f97  neg     rax
0x180007f9a  sbb     rdi, rdi
0x180007f9d  and     rdi, rcx
0x180007fa0  jz      short loc_180007FE2
0x180007fa2  call    cs:__imp_GetCurrentThreadId
0x180007fa8  mov     r8d, eax
0x180007fab  mov     r9d, eax
0x180007fae  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007fb8  shr     r8, 2
0x180007fbc  mul     r8
0x180007fbf  shr     rdx, 3
0x180007fc3  lea     rcx, [rdx+rdx*4]
0x180007fc7  add     rcx, rcx
0x180007fca  sub     r8, rcx
0x180007fcd  mov     rbx, [rdi+r8*8+8]
0x180007fd2  jmp     short loc_180007FDD
0x180007fd4  cmp     [rbx], r9d
0x180007fd7  jz      short loc_180007FF0
0x180007fd9  mov     rbx, [rbx+8]
0x180007fdd  test    rbx, rbx
0x180007fe0  jnz     short loc_180007FD4
0x180007fe2  mov     rax, rbx
0x180007fe5  mov     rbx, [rsp+28h+arg_0]
0x180007fea  add     rsp, 20h
0x180007fee  pop     rdi
0x180007fef  retn
0x180007ff0  add     rbx, 10h
0x180007ff4  jz      short loc_180007FE2
0x180007ff6  cmp     qword ptr [rbx+8], 0
0x180007ffb  jnz     short loc_180007FE2
0x180007ffd  lea     rax, [rdi+4]
0x180008001  mov     [rbx+8], rax
0x180008005  jmp     short loc_180007FE2
```
