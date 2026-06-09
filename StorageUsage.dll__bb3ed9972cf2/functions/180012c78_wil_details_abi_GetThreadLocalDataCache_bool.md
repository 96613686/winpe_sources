# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180012c78`
- end: `0x180012d35`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011ab0`

## callees

- `0x180010d30`
- `0x180012c78`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012cd2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012cd2`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 i; // rbx
  __int64 v2; // rdi
  __int64 v3; // rdi
  DWORD CurrentThreadId; // r9d
  void *v6; // [rsp+38h] [rbp+10h] BYREF

  i = 0;
  v2 = wil::details_abi::g_pProcessLocalData;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v6 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
                  *(_QWORD *)wil::details_abi::g_pProcessLocalData,
                  &v6) >= 0
        && !*(_QWORD *)(v2 + 8) )
      {
        *(_QWORD *)(v2 + 8) = v6;
      }
    }
    v3 = (*(_QWORD *)(v2 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v2 + 8) != 0);
    if ( v3 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v3 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          i += 16;
          if ( i && !*(_QWORD *)(i + 8) )
            *(_QWORD *)(i + 8) = v3 + 4;
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
0x180012c78  mov     [rsp+arg_0], rbx
0x180012c7d  push    rdi
0x180012c7e  sub     rsp, 20h
0x180012c82  xor     ebx, ebx
0x180012c84  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180012c8b  test    rdi, rdi
0x180012c8e  jz      loc_180012D27
0x180012c94  cmp     [rdi+8], rbx
0x180012c98  jnz     short loc_180012CBF
0x180012c9a  mov     [rsp+28h+arg_8], rbx
0x180012c9f  lea     rdx, [rsp+28h+arg_8]
0x180012ca4  mov     rcx, [rdi]
0x180012ca7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180012cac  test    eax, eax
0x180012cae  js      short loc_180012CBF
0x180012cb0  cmp     [rdi+8], rbx
0x180012cb4  jnz     short loc_180012CBF
0x180012cb6  mov     rax, [rsp+28h+arg_8]
0x180012cbb  mov     [rdi+8], rax
0x180012cbf  mov     rcx, [rdi+8]
0x180012cc3  lea     rax, [rcx+20h]
0x180012cc7  neg     rcx
0x180012cca  sbb     rdi, rdi
0x180012ccd  and     rdi, rax
0x180012cd0  jz      short loc_180012D27
0x180012cd2  call    cs:__imp_GetCurrentThreadId
0x180012cd8  mov     r9d, eax
0x180012cdb  mov     r8d, eax
0x180012cde  shr     r8, 2
0x180012ce2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180012cec  mul     r8
0x180012cef  shr     rdx, 3
0x180012cf3  lea     rcx, [rdx+rdx*4]
0x180012cf7  add     rcx, rcx
0x180012cfa  sub     r8, rcx
0x180012cfd  mov     rbx, [rdi+r8*8+8]
0x180012d02  test    rbx, rbx
0x180012d05  jz      short loc_180012D27
0x180012d07  cmp     [rbx], r9d
0x180012d0a  jz      short loc_180012D12
0x180012d0c  mov     rbx, [rbx+8]
0x180012d10  jmp     short loc_180012D02
0x180012d12  add     rbx, 10h
0x180012d16  jz      short loc_180012D27
0x180012d18  cmp     qword ptr [rbx+8], 0
0x180012d1d  jnz     short loc_180012D27
0x180012d1f  lea     rax, [rdi+4]
0x180012d23  mov     [rbx+8], rax
0x180012d27  mov     rax, rbx
0x180012d2a  mov     rbx, [rsp+28h+arg_0]
0x180012d2f  add     rsp, 20h
0x180012d33  pop     rdi
0x180012d34  retn
```
