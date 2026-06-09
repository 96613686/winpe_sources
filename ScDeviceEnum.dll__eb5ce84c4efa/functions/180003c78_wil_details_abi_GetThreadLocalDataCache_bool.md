# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180003c78`
- end: `0x180003d35`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003600`

## callees

- `0x180003160`
- `0x180003c78`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003cd2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003cd2`

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
0x180003c78  mov     [rsp+arg_0], rbx
0x180003c7d  push    rdi
0x180003c7e  sub     rsp, 20h
0x180003c82  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180003c89  xor     ebx, ebx
0x180003c8b  test    rdi, rdi
0x180003c8e  jz      loc_180003D27
0x180003c94  cmp     [rdi+8], rbx
0x180003c98  jnz     short loc_180003CBF
0x180003c9a  mov     rcx, [rdi]
0x180003c9d  lea     rdx, [rsp+28h+arg_8]
0x180003ca2  mov     [rsp+28h+arg_8], rbx
0x180003ca7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180003cac  test    eax, eax
0x180003cae  js      short loc_180003CBF
0x180003cb0  cmp     [rdi+8], rbx
0x180003cb4  jnz     short loc_180003CBF
0x180003cb6  mov     rax, [rsp+28h+arg_8]
0x180003cbb  mov     [rdi+8], rax
0x180003cbf  mov     rax, [rdi+8]
0x180003cc3  lea     rcx, [rax+20h]
0x180003cc7  neg     rax
0x180003cca  sbb     rdi, rdi
0x180003ccd  and     rdi, rcx
0x180003cd0  jz      short loc_180003D27
0x180003cd2  call    cs:__imp_GetCurrentThreadId
0x180003cd8  mov     r8d, eax
0x180003cdb  mov     r9d, eax
0x180003cde  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003ce8  shr     r8, 2
0x180003cec  mul     r8
0x180003cef  shr     rdx, 3
0x180003cf3  lea     rcx, [rdx+rdx*4]
0x180003cf7  add     rcx, rcx
0x180003cfa  sub     r8, rcx
0x180003cfd  mov     rbx, [rdi+r8*8+8]
0x180003d02  test    rbx, rbx
0x180003d05  jz      short loc_180003D27
0x180003d07  cmp     [rbx], r9d
0x180003d0a  jz      short loc_180003D12
0x180003d0c  mov     rbx, [rbx+8]
0x180003d10  jmp     short loc_180003D02
0x180003d12  add     rbx, 10h
0x180003d16  jz      short loc_180003D27
0x180003d18  cmp     qword ptr [rbx+8], 0
0x180003d1d  jnz     short loc_180003D27
0x180003d1f  lea     rax, [rdi+4]
0x180003d23  mov     [rbx+8], rax
0x180003d27  mov     rax, rbx
0x180003d2a  mov     rbx, [rsp+28h+arg_0]
0x180003d2f  add     rsp, 20h
0x180003d33  pop     rdi
0x180003d34  retn
```
