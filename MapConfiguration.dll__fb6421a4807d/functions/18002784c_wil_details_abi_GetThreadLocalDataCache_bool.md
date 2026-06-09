# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18002784c`
- end: `0x180027909`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180027490`

## callees

- `0x180027028`
- `0x18002784c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800278a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800278a6`

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
0x18002784c  mov     [rsp+arg_0], rbx
0x180027851  push    rdi
0x180027852  sub     rsp, 20h
0x180027856  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18002785d  xor     ebx, ebx
0x18002785f  test    rdi, rdi
0x180027862  jz      loc_1800278FB
0x180027868  cmp     [rdi+8], rbx
0x18002786c  jnz     short loc_180027893
0x18002786e  mov     rcx, [rdi]
0x180027871  lea     rdx, [rsp+28h+arg_8]
0x180027876  mov     [rsp+28h+arg_8], rbx
0x18002787b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180027880  test    eax, eax
0x180027882  js      short loc_180027893
0x180027884  cmp     [rdi+8], rbx
0x180027888  jnz     short loc_180027893
0x18002788a  mov     rax, [rsp+28h+arg_8]
0x18002788f  mov     [rdi+8], rax
0x180027893  mov     rax, [rdi+8]
0x180027897  lea     rcx, [rax+20h]
0x18002789b  neg     rax
0x18002789e  sbb     rdi, rdi
0x1800278a1  and     rdi, rcx
0x1800278a4  jz      short loc_1800278FB
0x1800278a6  call    cs:__imp_GetCurrentThreadId
0x1800278ac  mov     r8d, eax
0x1800278af  mov     r9d, eax
0x1800278b2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800278bc  shr     r8, 2
0x1800278c0  mul     r8
0x1800278c3  shr     rdx, 3
0x1800278c7  lea     rcx, [rdx+rdx*4]
0x1800278cb  add     rcx, rcx
0x1800278ce  sub     r8, rcx
0x1800278d1  mov     rbx, [rdi+r8*8+8]
0x1800278d6  test    rbx, rbx
0x1800278d9  jz      short loc_1800278FB
0x1800278db  cmp     [rbx], r9d
0x1800278de  jz      short loc_1800278E6
0x1800278e0  mov     rbx, [rbx+8]
0x1800278e4  jmp     short loc_1800278D6
0x1800278e6  add     rbx, 10h
0x1800278ea  jz      short loc_1800278FB
0x1800278ec  cmp     qword ptr [rbx+8], 0
0x1800278f1  jnz     short loc_1800278FB
0x1800278f3  lea     rax, [rdi+4]
0x1800278f7  mov     [rbx+8], rax
0x1800278fb  mov     rax, rbx
0x1800278fe  mov     rbx, [rsp+28h+arg_0]
0x180027903  add     rsp, 20h
0x180027907  pop     rdi
0x180027908  retn
```
