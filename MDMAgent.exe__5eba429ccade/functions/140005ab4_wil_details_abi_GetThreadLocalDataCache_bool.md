# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140005ab4`
- end: `0x140005b71`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400052f0`

## callees

- `0x140004d88`
- `0x140005ab4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005b0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005b0e`

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
0x140005ab4  mov     [rsp+arg_0], rbx
0x140005ab9  push    rdi
0x140005aba  sub     rsp, 20h
0x140005abe  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140005ac5  xor     ebx, ebx
0x140005ac7  test    rdi, rdi
0x140005aca  jz      loc_140005B63
0x140005ad0  cmp     [rdi+8], rbx
0x140005ad4  jnz     short loc_140005AFB
0x140005ad6  mov     rcx, [rdi]
0x140005ad9  lea     rdx, [rsp+28h+arg_8]
0x140005ade  mov     [rsp+28h+arg_8], rbx
0x140005ae3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140005ae8  test    eax, eax
0x140005aea  js      short loc_140005AFB
0x140005aec  cmp     [rdi+8], rbx
0x140005af0  jnz     short loc_140005AFB
0x140005af2  mov     rax, [rsp+28h+arg_8]
0x140005af7  mov     [rdi+8], rax
0x140005afb  mov     rax, [rdi+8]
0x140005aff  lea     rcx, [rax+20h]
0x140005b03  neg     rax
0x140005b06  sbb     rdi, rdi
0x140005b09  and     rdi, rcx
0x140005b0c  jz      short loc_140005B63
0x140005b0e  call    cs:__imp_GetCurrentThreadId
0x140005b14  mov     r8d, eax
0x140005b17  mov     r9d, eax
0x140005b1a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140005b24  shr     r8, 2
0x140005b28  mul     r8
0x140005b2b  shr     rdx, 3
0x140005b2f  lea     rcx, [rdx+rdx*4]
0x140005b33  add     rcx, rcx
0x140005b36  sub     r8, rcx
0x140005b39  mov     rbx, [rdi+r8*8+8]
0x140005b3e  test    rbx, rbx
0x140005b41  jz      short loc_140005B63
0x140005b43  cmp     [rbx], r9d
0x140005b46  jz      short loc_140005B4E
0x140005b48  mov     rbx, [rbx+8]
0x140005b4c  jmp     short loc_140005B3E
0x140005b4e  add     rbx, 10h
0x140005b52  jz      short loc_140005B63
0x140005b54  cmp     qword ptr [rbx+8], 0
0x140005b59  jnz     short loc_140005B63
0x140005b5b  lea     rax, [rdi+4]
0x140005b5f  mov     [rbx+8], rax
0x140005b63  mov     rax, rbx
0x140005b66  mov     rbx, [rsp+28h+arg_0]
0x140005b6b  add     rsp, 20h
0x140005b6f  pop     rdi
0x140005b70  retn
```
