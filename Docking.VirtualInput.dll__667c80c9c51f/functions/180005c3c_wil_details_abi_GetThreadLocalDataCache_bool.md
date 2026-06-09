# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005c3c`
- end: `0x180005cf9`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005570`

## callees

- `0x1800050c8`
- `0x180005c3c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005c96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005c96`

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
0x180005c3c  mov     [rsp+arg_0], rbx
0x180005c41  push    rdi
0x180005c42  sub     rsp, 20h
0x180005c46  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005c4d  xor     ebx, ebx
0x180005c4f  test    rdi, rdi
0x180005c52  jz      loc_180005CEB
0x180005c58  cmp     [rdi+8], rbx
0x180005c5c  jnz     short loc_180005C83
0x180005c5e  mov     rcx, [rdi]
0x180005c61  lea     rdx, [rsp+28h+arg_8]
0x180005c66  mov     [rsp+28h+arg_8], rbx
0x180005c6b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005c70  test    eax, eax
0x180005c72  js      short loc_180005C83
0x180005c74  cmp     [rdi+8], rbx
0x180005c78  jnz     short loc_180005C83
0x180005c7a  mov     rax, [rsp+28h+arg_8]
0x180005c7f  mov     [rdi+8], rax
0x180005c83  mov     rax, [rdi+8]
0x180005c87  lea     rcx, [rax+20h]
0x180005c8b  neg     rax
0x180005c8e  sbb     rdi, rdi
0x180005c91  and     rdi, rcx
0x180005c94  jz      short loc_180005CEB
0x180005c96  call    cs:__imp_GetCurrentThreadId
0x180005c9c  mov     r8d, eax
0x180005c9f  mov     r9d, eax
0x180005ca2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005cac  shr     r8, 2
0x180005cb0  mul     r8
0x180005cb3  shr     rdx, 3
0x180005cb7  lea     rcx, [rdx+rdx*4]
0x180005cbb  add     rcx, rcx
0x180005cbe  sub     r8, rcx
0x180005cc1  mov     rbx, [rdi+r8*8+8]
0x180005cc6  test    rbx, rbx
0x180005cc9  jz      short loc_180005CEB
0x180005ccb  cmp     [rbx], r9d
0x180005cce  jz      short loc_180005CD6
0x180005cd0  mov     rbx, [rbx+8]
0x180005cd4  jmp     short loc_180005CC6
0x180005cd6  add     rbx, 10h
0x180005cda  jz      short loc_180005CEB
0x180005cdc  cmp     qword ptr [rbx+8], 0
0x180005ce1  jnz     short loc_180005CEB
0x180005ce3  lea     rax, [rdi+4]
0x180005ce7  mov     [rbx+8], rax
0x180005ceb  mov     rax, rbx
0x180005cee  mov     rbx, [rsp+28h+arg_0]
0x180005cf3  add     rsp, 20h
0x180005cf7  pop     rdi
0x180005cf8  retn
```
