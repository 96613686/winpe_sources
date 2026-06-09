# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005b88`
- end: `0x180005c45`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005510`

## callees

- `0x180005064`
- `0x180005b88`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005be2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005be2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180005b88  mov     [rsp+arg_0], rbx
0x180005b8d  push    rdi
0x180005b8e  sub     rsp, 20h
0x180005b92  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005b99  xor     ebx, ebx
0x180005b9b  test    rdi, rdi
0x180005b9e  jz      loc_180005C37
0x180005ba4  cmp     [rdi+8], rbx
0x180005ba8  jnz     short loc_180005BCF
0x180005baa  mov     rcx, [rdi]
0x180005bad  lea     rdx, [rsp+28h+arg_8]
0x180005bb2  mov     [rsp+28h+arg_8], rbx
0x180005bb7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005bbc  test    eax, eax
0x180005bbe  js      short loc_180005BCF
0x180005bc0  cmp     [rdi+8], rbx
0x180005bc4  jnz     short loc_180005BCF
0x180005bc6  mov     rax, [rsp+28h+arg_8]
0x180005bcb  mov     [rdi+8], rax
0x180005bcf  mov     rax, [rdi+8]
0x180005bd3  lea     rcx, [rax+20h]
0x180005bd7  neg     rax
0x180005bda  sbb     rdi, rdi
0x180005bdd  and     rdi, rcx
0x180005be0  jz      short loc_180005C37
0x180005be2  call    cs:__imp_GetCurrentThreadId
0x180005be8  mov     r8d, eax
0x180005beb  mov     r9d, eax
0x180005bee  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005bf8  shr     r8, 2
0x180005bfc  mul     r8
0x180005bff  shr     rdx, 3
0x180005c03  lea     rcx, [rdx+rdx*4]
0x180005c07  add     rcx, rcx
0x180005c0a  sub     r8, rcx
0x180005c0d  mov     rbx, [rdi+r8*8+8]
0x180005c12  test    rbx, rbx
0x180005c15  jz      short loc_180005C37
0x180005c17  cmp     [rbx], r9d
0x180005c1a  jz      short loc_180005C22
0x180005c1c  mov     rbx, [rbx+8]
0x180005c20  jmp     short loc_180005C12
0x180005c22  add     rbx, 10h
0x180005c26  jz      short loc_180005C37
0x180005c28  cmp     qword ptr [rbx+8], 0
0x180005c2d  jnz     short loc_180005C37
0x180005c2f  lea     rax, [rdi+4]
0x180005c33  mov     [rbx+8], rax
0x180005c37  mov     rax, rbx
0x180005c3a  mov     rbx, [rsp+28h+arg_0]
0x180005c3f  add     rsp, 20h
0x180005c43  pop     rdi
0x180005c44  retn
```
