# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140005c7c`
- end: `0x140005d40`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `196`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005470`

## callees

- `0x140004e2c`
- `0x140005c7c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005cd6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005cd6`

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
0x140005c7c  mov     [rsp+arg_0], rbx
0x140005c81  push    rdi
0x140005c82  sub     rsp, 20h
0x140005c86  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140005c8d  xor     ebx, ebx
0x140005c8f  test    rdi, rdi
0x140005c92  jz      loc_140005D31
0x140005c98  cmp     [rdi+8], rbx
0x140005c9c  jnz     short loc_140005CC3
0x140005c9e  mov     rcx, [rdi]
0x140005ca1  lea     rdx, [rsp+28h+arg_8]
0x140005ca6  mov     [rsp+28h+arg_8], rbx
0x140005cab  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140005cb0  test    eax, eax
0x140005cb2  js      short loc_140005CC3
0x140005cb4  cmp     [rdi+8], rbx
0x140005cb8  jnz     short loc_140005CC3
0x140005cba  mov     rax, [rsp+28h+arg_8]
0x140005cbf  mov     [rdi+8], rax
0x140005cc3  mov     rax, [rdi+8]
0x140005cc7  lea     rcx, [rax+20h]
0x140005ccb  neg     rax
0x140005cce  sbb     rdi, rdi
0x140005cd1  and     rdi, rcx
0x140005cd4  jz      short loc_140005D31
0x140005cd6  call    cs:__imp_GetCurrentThreadId
0x140005cdd  nop     dword ptr [rax+rax+00h]
0x140005ce2  mov     r8d, eax
0x140005ce5  mov     r9d, eax
0x140005ce8  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140005cf2  shr     r8, 2
0x140005cf6  mul     r8
0x140005cf9  shr     rdx, 3
0x140005cfd  lea     rcx, [rdx+rdx*4]
0x140005d01  add     rcx, rcx
0x140005d04  sub     r8, rcx
0x140005d07  mov     rbx, [rdi+r8*8+8]
0x140005d0c  test    rbx, rbx
0x140005d0f  jz      short loc_140005D31
0x140005d11  cmp     [rbx], r9d
0x140005d14  jz      short loc_140005D1C
0x140005d16  mov     rbx, [rbx+8]
0x140005d1a  jmp     short loc_140005D0C
0x140005d1c  add     rbx, 10h
0x140005d20  jz      short loc_140005D31
0x140005d22  cmp     qword ptr [rbx+8], 0
0x140005d27  jnz     short loc_140005D31
0x140005d29  lea     rax, [rdi+4]
0x140005d2d  mov     [rbx+8], rax
0x140005d31  mov     rax, rbx
0x140005d34  mov     rbx, [rsp+28h+arg_0]
0x140005d39  add     rsp, 20h
0x140005d3d  pop     rdi
0x140005d3e  retn
```
