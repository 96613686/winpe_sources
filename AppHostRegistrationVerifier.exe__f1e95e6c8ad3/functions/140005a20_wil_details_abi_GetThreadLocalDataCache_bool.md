# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140005a20`
- end: `0x140005add`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005300`

## callees

- `0x140004e08`
- `0x140005a20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005a7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005a7a`

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
0x140005a20  mov     [rsp+arg_0], rbx
0x140005a25  push    rdi
0x140005a26  sub     rsp, 20h
0x140005a2a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140005a31  xor     ebx, ebx
0x140005a33  test    rdi, rdi
0x140005a36  jz      loc_140005ACF
0x140005a3c  cmp     [rdi+8], rbx
0x140005a40  jnz     short loc_140005A67
0x140005a42  mov     rcx, [rdi]
0x140005a45  lea     rdx, [rsp+28h+arg_8]
0x140005a4a  mov     [rsp+28h+arg_8], rbx
0x140005a4f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140005a54  test    eax, eax
0x140005a56  js      short loc_140005A67
0x140005a58  cmp     [rdi+8], rbx
0x140005a5c  jnz     short loc_140005A67
0x140005a5e  mov     rax, [rsp+28h+arg_8]
0x140005a63  mov     [rdi+8], rax
0x140005a67  mov     rax, [rdi+8]
0x140005a6b  lea     rcx, [rax+20h]
0x140005a6f  neg     rax
0x140005a72  sbb     rdi, rdi
0x140005a75  and     rdi, rcx
0x140005a78  jz      short loc_140005ACF
0x140005a7a  call    cs:__imp_GetCurrentThreadId
0x140005a80  mov     r8d, eax
0x140005a83  mov     r9d, eax
0x140005a86  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140005a90  shr     r8, 2
0x140005a94  mul     r8
0x140005a97  shr     rdx, 3
0x140005a9b  lea     rcx, [rdx+rdx*4]
0x140005a9f  add     rcx, rcx
0x140005aa2  sub     r8, rcx
0x140005aa5  mov     rbx, [rdi+r8*8+8]
0x140005aaa  test    rbx, rbx
0x140005aad  jz      short loc_140005ACF
0x140005aaf  cmp     [rbx], r9d
0x140005ab2  jz      short loc_140005ABA
0x140005ab4  mov     rbx, [rbx+8]
0x140005ab8  jmp     short loc_140005AAA
0x140005aba  add     rbx, 10h
0x140005abe  jz      short loc_140005ACF
0x140005ac0  cmp     qword ptr [rbx+8], 0
0x140005ac5  jnz     short loc_140005ACF
0x140005ac7  lea     rax, [rdi+4]
0x140005acb  mov     [rbx+8], rax
0x140005acf  mov     rax, rbx
0x140005ad2  mov     rbx, [rsp+28h+arg_0]
0x140005ad7  add     rsp, 20h
0x140005adb  pop     rdi
0x140005adc  retn
```
