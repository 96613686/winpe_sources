# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140004948`
- end: `0x140004a05`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400042d0`

## callees

- `0x140003e24`
- `0x140004948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400049a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400049a2`

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
0x140004948  mov     [rsp+arg_0], rbx
0x14000494d  push    rdi
0x14000494e  sub     rsp, 20h
0x140004952  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140004959  xor     ebx, ebx
0x14000495b  test    rdi, rdi
0x14000495e  jz      loc_1400049F7
0x140004964  cmp     [rdi+8], rbx
0x140004968  jnz     short loc_14000498F
0x14000496a  mov     rcx, [rdi]
0x14000496d  lea     rdx, [rsp+28h+arg_8]
0x140004972  mov     [rsp+28h+arg_8], rbx
0x140004977  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x14000497c  test    eax, eax
0x14000497e  js      short loc_14000498F
0x140004980  cmp     [rdi+8], rbx
0x140004984  jnz     short loc_14000498F
0x140004986  mov     rax, [rsp+28h+arg_8]
0x14000498b  mov     [rdi+8], rax
0x14000498f  mov     rax, [rdi+8]
0x140004993  lea     rcx, [rax+20h]
0x140004997  neg     rax
0x14000499a  sbb     rdi, rdi
0x14000499d  and     rdi, rcx
0x1400049a0  jz      short loc_1400049F7
0x1400049a2  call    cs:__imp_GetCurrentThreadId
0x1400049a8  mov     r8d, eax
0x1400049ab  mov     r9d, eax
0x1400049ae  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400049b8  shr     r8, 2
0x1400049bc  mul     r8
0x1400049bf  shr     rdx, 3
0x1400049c3  lea     rcx, [rdx+rdx*4]
0x1400049c7  add     rcx, rcx
0x1400049ca  sub     r8, rcx
0x1400049cd  mov     rbx, [rdi+r8*8+8]
0x1400049d2  test    rbx, rbx
0x1400049d5  jz      short loc_1400049F7
0x1400049d7  cmp     [rbx], r9d
0x1400049da  jz      short loc_1400049E2
0x1400049dc  mov     rbx, [rbx+8]
0x1400049e0  jmp     short loc_1400049D2
0x1400049e2  add     rbx, 10h
0x1400049e6  jz      short loc_1400049F7
0x1400049e8  cmp     qword ptr [rbx+8], 0
0x1400049ed  jnz     short loc_1400049F7
0x1400049ef  lea     rax, [rdi+4]
0x1400049f3  mov     [rbx+8], rax
0x1400049f7  mov     rax, rbx
0x1400049fa  mov     rbx, [rsp+28h+arg_0]
0x1400049ff  add     rsp, 20h
0x140004a03  pop     rdi
0x140004a04  retn
```
