# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18002ad94`
- end: `0x18002ae51`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002a7e0`

## callees

- `0x180029de4`
- `0x18002ad94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002adee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002adee`

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
0x18002ad94  mov     [rsp+arg_0], rbx
0x18002ad99  push    rdi
0x18002ad9a  sub     rsp, 20h
0x18002ad9e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18002ada5  xor     ebx, ebx
0x18002ada7  test    rdi, rdi
0x18002adaa  jz      loc_18002AE43
0x18002adb0  cmp     [rdi+8], rbx
0x18002adb4  jnz     short loc_18002ADDB
0x18002adb6  mov     rcx, [rdi]
0x18002adb9  lea     rdx, [rsp+28h+arg_8]
0x18002adbe  mov     [rsp+28h+arg_8], rbx
0x18002adc3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18002adc8  test    eax, eax
0x18002adca  js      short loc_18002ADDB
0x18002adcc  cmp     [rdi+8], rbx
0x18002add0  jnz     short loc_18002ADDB
0x18002add2  mov     rax, [rsp+28h+arg_8]
0x18002add7  mov     [rdi+8], rax
0x18002addb  mov     rax, [rdi+8]
0x18002addf  lea     rcx, [rax+20h]
0x18002ade3  neg     rax
0x18002ade6  sbb     rdi, rdi
0x18002ade9  and     rdi, rcx
0x18002adec  jz      short loc_18002AE43
0x18002adee  call    cs:__imp_GetCurrentThreadId
0x18002adf4  mov     r8d, eax
0x18002adf7  mov     r9d, eax
0x18002adfa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002ae04  shr     r8, 2
0x18002ae08  mul     r8
0x18002ae0b  shr     rdx, 3
0x18002ae0f  lea     rcx, [rdx+rdx*4]
0x18002ae13  add     rcx, rcx
0x18002ae16  sub     r8, rcx
0x18002ae19  mov     rbx, [rdi+r8*8+8]
0x18002ae1e  test    rbx, rbx
0x18002ae21  jz      short loc_18002AE43
0x18002ae23  cmp     [rbx], r9d
0x18002ae26  jz      short loc_18002AE2E
0x18002ae28  mov     rbx, [rbx+8]
0x18002ae2c  jmp     short loc_18002AE1E
0x18002ae2e  add     rbx, 10h
0x18002ae32  jz      short loc_18002AE43
0x18002ae34  cmp     qword ptr [rbx+8], 0
0x18002ae39  jnz     short loc_18002AE43
0x18002ae3b  lea     rax, [rdi+4]
0x18002ae3f  mov     [rbx+8], rax
0x18002ae43  mov     rax, rbx
0x18002ae46  mov     rbx, [rsp+28h+arg_0]
0x18002ae4b  add     rsp, 20h
0x18002ae4f  pop     rdi
0x18002ae50  retn
```
