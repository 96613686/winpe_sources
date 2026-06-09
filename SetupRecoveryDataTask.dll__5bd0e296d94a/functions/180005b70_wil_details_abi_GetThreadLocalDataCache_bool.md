# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005b70`
- end: `0x180005c2b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800052e0`

## callees

- `0x180003940`
- `0x180005b70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005bc6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005bc6`

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
0x180005b70  mov     [rsp+arg_0], rbx
0x180005b75  push    rdi
0x180005b76  sub     rsp, 20h
0x180005b7a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005b81  xor     ebx, ebx
0x180005b83  test    rdi, rdi
0x180005b86  jz      short loc_180005C06
0x180005b88  cmp     [rdi+8], rbx
0x180005b8c  jnz     short loc_180005BB3
0x180005b8e  mov     rcx, [rdi]
0x180005b91  lea     rdx, [rsp+28h+arg_8]
0x180005b96  mov     [rsp+28h+arg_8], rbx
0x180005b9b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005ba0  test    eax, eax
0x180005ba2  js      short loc_180005BB3
0x180005ba4  cmp     [rdi+8], rbx
0x180005ba8  jnz     short loc_180005BB3
0x180005baa  mov     rax, [rsp+28h+arg_8]
0x180005baf  mov     [rdi+8], rax
0x180005bb3  mov     rax, [rdi+8]
0x180005bb7  lea     rcx, [rax+20h]
0x180005bbb  neg     rax
0x180005bbe  sbb     rdi, rdi
0x180005bc1  and     rdi, rcx
0x180005bc4  jz      short loc_180005C06
0x180005bc6  call    cs:__imp_GetCurrentThreadId
0x180005bcc  mov     r8d, eax
0x180005bcf  mov     r9d, eax
0x180005bd2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005bdc  shr     r8, 2
0x180005be0  mul     r8
0x180005be3  shr     rdx, 3
0x180005be7  lea     rcx, [rdx+rdx*4]
0x180005beb  add     rcx, rcx
0x180005bee  sub     r8, rcx
0x180005bf1  mov     rbx, [rdi+r8*8+8]
0x180005bf6  jmp     short loc_180005C01
0x180005bf8  cmp     [rbx], r9d
0x180005bfb  jz      short loc_180005C14
0x180005bfd  mov     rbx, [rbx+8]
0x180005c01  test    rbx, rbx
0x180005c04  jnz     short loc_180005BF8
0x180005c06  mov     rax, rbx
0x180005c09  mov     rbx, [rsp+28h+arg_0]
0x180005c0e  add     rsp, 20h
0x180005c12  pop     rdi
0x180005c13  retn
0x180005c14  add     rbx, 10h
0x180005c18  jz      short loc_180005C06
0x180005c1a  cmp     qword ptr [rbx+8], 0
0x180005c1f  jnz     short loc_180005C06
0x180005c21  lea     rax, [rdi+4]
0x180005c25  mov     [rbx+8], rax
0x180005c29  jmp     short loc_180005C06
```
