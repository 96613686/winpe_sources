# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180043b64`
- end: `0x180043c21`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800435e0`

## callees

- `0x1800430fc`
- `0x180043b64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043bbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043bbe`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
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
0x180043b64  mov     [rsp+arg_0], rbx
0x180043b69  push    rdi
0x180043b6a  sub     rsp, 20h
0x180043b6e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180043b75  xor     ebx, ebx
0x180043b77  test    rdi, rdi
0x180043b7a  jz      loc_180043C13
0x180043b80  cmp     [rdi+8], rbx
0x180043b84  jnz     short loc_180043BAB
0x180043b86  mov     rcx, [rdi]
0x180043b89  lea     rdx, [rsp+28h+arg_8]
0x180043b8e  mov     [rsp+28h+arg_8], rbx
0x180043b93  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180043b98  test    eax, eax
0x180043b9a  js      short loc_180043BAB
0x180043b9c  cmp     [rdi+8], rbx
0x180043ba0  jnz     short loc_180043BAB
0x180043ba2  mov     rax, [rsp+28h+arg_8]
0x180043ba7  mov     [rdi+8], rax
0x180043bab  mov     rax, [rdi+8]
0x180043baf  lea     rcx, [rax+20h]
0x180043bb3  neg     rax
0x180043bb6  sbb     rdi, rdi
0x180043bb9  and     rdi, rcx
0x180043bbc  jz      short loc_180043C13
0x180043bbe  call    cs:__imp_GetCurrentThreadId
0x180043bc4  mov     r8d, eax
0x180043bc7  mov     r9d, eax
0x180043bca  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180043bd4  shr     r8, 2
0x180043bd8  mul     r8
0x180043bdb  shr     rdx, 3
0x180043bdf  lea     rcx, [rdx+rdx*4]
0x180043be3  add     rcx, rcx
0x180043be6  sub     r8, rcx
0x180043be9  mov     rbx, [rdi+r8*8+8]
0x180043bee  test    rbx, rbx
0x180043bf1  jz      short loc_180043C13
0x180043bf3  cmp     [rbx], r9d
0x180043bf6  jz      short loc_180043BFE
0x180043bf8  mov     rbx, [rbx+8]
0x180043bfc  jmp     short loc_180043BEE
0x180043bfe  add     rbx, 10h
0x180043c02  jz      short loc_180043C13
0x180043c04  cmp     qword ptr [rbx+8], 0
0x180043c09  jnz     short loc_180043C13
0x180043c0b  lea     rax, [rdi+4]
0x180043c0f  mov     [rbx+8], rax
0x180043c13  mov     rax, rbx
0x180043c16  mov     rbx, [rsp+28h+arg_0]
0x180043c1b  add     rsp, 20h
0x180043c1f  pop     rdi
0x180043c20  retn
```
