# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180003dd0`
- end: `0x180003e8b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800035f0`

## callees

- `0x180002f08`
- `0x180003dd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e26`

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
0x180003dd0  mov     [rsp+arg_0], rbx
0x180003dd5  push    rdi
0x180003dd6  sub     rsp, 20h
0x180003dda  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180003de1  xor     ebx, ebx
0x180003de3  test    rdi, rdi
0x180003de6  jz      short loc_180003E66
0x180003de8  cmp     [rdi+8], rbx
0x180003dec  jnz     short loc_180003E13
0x180003dee  mov     rcx, [rdi]
0x180003df1  lea     rdx, [rsp+28h+arg_8]
0x180003df6  mov     [rsp+28h+arg_8], rbx
0x180003dfb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180003e00  test    eax, eax
0x180003e02  js      short loc_180003E13
0x180003e04  cmp     [rdi+8], rbx
0x180003e08  jnz     short loc_180003E13
0x180003e0a  mov     rax, [rsp+28h+arg_8]
0x180003e0f  mov     [rdi+8], rax
0x180003e13  mov     rax, [rdi+8]
0x180003e17  lea     rcx, [rax+20h]
0x180003e1b  neg     rax
0x180003e1e  sbb     rdi, rdi
0x180003e21  and     rdi, rcx
0x180003e24  jz      short loc_180003E66
0x180003e26  call    cs:__imp_GetCurrentThreadId
0x180003e2c  mov     r8d, eax
0x180003e2f  mov     r9d, eax
0x180003e32  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003e3c  shr     r8, 2
0x180003e40  mul     r8
0x180003e43  shr     rdx, 3
0x180003e47  lea     rcx, [rdx+rdx*4]
0x180003e4b  add     rcx, rcx
0x180003e4e  sub     r8, rcx
0x180003e51  mov     rbx, [rdi+r8*8+8]
0x180003e56  jmp     short loc_180003E61
0x180003e58  cmp     [rbx], r9d
0x180003e5b  jz      short loc_180003E74
0x180003e5d  mov     rbx, [rbx+8]
0x180003e61  test    rbx, rbx
0x180003e64  jnz     short loc_180003E58
0x180003e66  mov     rax, rbx
0x180003e69  mov     rbx, [rsp+28h+arg_0]
0x180003e6e  add     rsp, 20h
0x180003e72  pop     rdi
0x180003e73  retn
0x180003e74  add     rbx, 10h
0x180003e78  jz      short loc_180003E66
0x180003e7a  cmp     qword ptr [rbx+8], 0
0x180003e7f  jnz     short loc_180003E66
0x180003e81  lea     rax, [rdi+4]
0x180003e85  mov     [rbx+8], rax
0x180003e89  jmp     short loc_180003E66
```
