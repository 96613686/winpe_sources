# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140003f68`
- end: `0x140004025`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400038f0`

## callees

- `0x140003440`
- `0x140003f68`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003fc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003fc2`

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
0x140003f68  mov     [rsp+arg_0], rbx
0x140003f6d  push    rdi
0x140003f6e  sub     rsp, 20h
0x140003f72  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140003f79  xor     ebx, ebx
0x140003f7b  test    rdi, rdi
0x140003f7e  jz      loc_140004017
0x140003f84  cmp     [rdi+8], rbx
0x140003f88  jnz     short loc_140003FAF
0x140003f8a  mov     rcx, [rdi]
0x140003f8d  lea     rdx, [rsp+28h+arg_8]
0x140003f92  mov     [rsp+28h+arg_8], rbx
0x140003f97  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140003f9c  test    eax, eax
0x140003f9e  js      short loc_140003FAF
0x140003fa0  cmp     [rdi+8], rbx
0x140003fa4  jnz     short loc_140003FAF
0x140003fa6  mov     rax, [rsp+28h+arg_8]
0x140003fab  mov     [rdi+8], rax
0x140003faf  mov     rax, [rdi+8]
0x140003fb3  lea     rcx, [rax+20h]
0x140003fb7  neg     rax
0x140003fba  sbb     rdi, rdi
0x140003fbd  and     rdi, rcx
0x140003fc0  jz      short loc_140004017
0x140003fc2  call    cs:__imp_GetCurrentThreadId
0x140003fc8  mov     r8d, eax
0x140003fcb  mov     r9d, eax
0x140003fce  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140003fd8  shr     r8, 2
0x140003fdc  mul     r8
0x140003fdf  shr     rdx, 3
0x140003fe3  lea     rcx, [rdx+rdx*4]
0x140003fe7  add     rcx, rcx
0x140003fea  sub     r8, rcx
0x140003fed  mov     rbx, [rdi+r8*8+8]
0x140003ff2  test    rbx, rbx
0x140003ff5  jz      short loc_140004017
0x140003ff7  cmp     [rbx], r9d
0x140003ffa  jz      short loc_140004002
0x140003ffc  mov     rbx, [rbx+8]
0x140004000  jmp     short loc_140003FF2
0x140004002  add     rbx, 10h
0x140004006  jz      short loc_140004017
0x140004008  cmp     qword ptr [rbx+8], 0
0x14000400d  jnz     short loc_140004017
0x14000400f  lea     rax, [rdi+4]
0x140004013  mov     [rbx+8], rax
0x140004017  mov     rax, rbx
0x14000401a  mov     rbx, [rsp+28h+arg_0]
0x14000401f  add     rsp, 20h
0x140004023  pop     rdi
0x140004024  retn
```
