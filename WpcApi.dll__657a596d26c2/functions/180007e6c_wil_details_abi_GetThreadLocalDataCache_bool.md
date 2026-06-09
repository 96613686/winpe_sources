# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180007e6c`
- end: `0x180007f27`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007490`

## callees

- `0x1800064a8`
- `0x180007e6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007ec2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007ec2`

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
0x180007e6c  mov     [rsp+arg_0], rbx
0x180007e71  push    rdi
0x180007e72  sub     rsp, 20h
0x180007e76  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180007e7d  xor     ebx, ebx
0x180007e7f  test    rdi, rdi
0x180007e82  jz      short loc_180007F02
0x180007e84  cmp     [rdi+8], rbx
0x180007e88  jnz     short loc_180007EAF
0x180007e8a  mov     rcx, [rdi]
0x180007e8d  lea     rdx, [rsp+28h+arg_8]
0x180007e92  mov     [rsp+28h+arg_8], rbx
0x180007e97  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180007e9c  test    eax, eax
0x180007e9e  js      short loc_180007EAF
0x180007ea0  cmp     [rdi+8], rbx
0x180007ea4  jnz     short loc_180007EAF
0x180007ea6  mov     rax, [rsp+28h+arg_8]
0x180007eab  mov     [rdi+8], rax
0x180007eaf  mov     rax, [rdi+8]
0x180007eb3  lea     rcx, [rax+20h]
0x180007eb7  neg     rax
0x180007eba  sbb     rdi, rdi
0x180007ebd  and     rdi, rcx
0x180007ec0  jz      short loc_180007F02
0x180007ec2  call    cs:__imp_GetCurrentThreadId
0x180007ec8  mov     r8d, eax
0x180007ecb  mov     r9d, eax
0x180007ece  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007ed8  shr     r8, 2
0x180007edc  mul     r8
0x180007edf  shr     rdx, 3
0x180007ee3  lea     rcx, [rdx+rdx*4]
0x180007ee7  add     rcx, rcx
0x180007eea  sub     r8, rcx
0x180007eed  mov     rbx, [rdi+r8*8+8]
0x180007ef2  jmp     short loc_180007EFD
0x180007ef4  cmp     [rbx], r9d
0x180007ef7  jz      short loc_180007F10
0x180007ef9  mov     rbx, [rbx+8]
0x180007efd  test    rbx, rbx
0x180007f00  jnz     short loc_180007EF4
0x180007f02  mov     rax, rbx
0x180007f05  mov     rbx, [rsp+28h+arg_0]
0x180007f0a  add     rsp, 20h
0x180007f0e  pop     rdi
0x180007f0f  retn
0x180007f10  add     rbx, 10h
0x180007f14  jz      short loc_180007F02
0x180007f16  cmp     qword ptr [rbx+8], 0
0x180007f1b  jnz     short loc_180007F02
0x180007f1d  lea     rax, [rdi+4]
0x180007f21  mov     [rbx+8], rax
0x180007f25  jmp     short loc_180007F02
```
