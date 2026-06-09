# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140005d2c`
- end: `0x140005de9`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005680`

## callees

- `0x140004a3c`
- `0x140005d2c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140005d86`
- `KERNEL32!GetCurrentThreadId` at `0x140005d86`

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
0x140005d2c  mov     [rsp+arg_0], rbx
0x140005d31  push    rdi
0x140005d32  sub     rsp, 20h
0x140005d36  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140005d3d  xor     ebx, ebx
0x140005d3f  test    rdi, rdi
0x140005d42  jz      loc_140005DDB
0x140005d48  cmp     [rdi+8], rbx
0x140005d4c  jnz     short loc_140005D73
0x140005d4e  mov     rcx, [rdi]
0x140005d51  lea     rdx, [rsp+28h+arg_8]
0x140005d56  mov     [rsp+28h+arg_8], rbx
0x140005d5b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140005d60  test    eax, eax
0x140005d62  js      short loc_140005D73
0x140005d64  cmp     [rdi+8], rbx
0x140005d68  jnz     short loc_140005D73
0x140005d6a  mov     rax, [rsp+28h+arg_8]
0x140005d6f  mov     [rdi+8], rax
0x140005d73  mov     rax, [rdi+8]
0x140005d77  lea     rcx, [rax+20h]
0x140005d7b  neg     rax
0x140005d7e  sbb     rdi, rdi
0x140005d81  and     rdi, rcx
0x140005d84  jz      short loc_140005DDB
0x140005d86  call    cs:__imp_GetCurrentThreadId
0x140005d8c  mov     r8d, eax
0x140005d8f  mov     r9d, eax
0x140005d92  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140005d9c  shr     r8, 2
0x140005da0  mul     r8
0x140005da3  shr     rdx, 3
0x140005da7  lea     rcx, [rdx+rdx*4]
0x140005dab  add     rcx, rcx
0x140005dae  sub     r8, rcx
0x140005db1  mov     rbx, [rdi+r8*8+8]
0x140005db6  test    rbx, rbx
0x140005db9  jz      short loc_140005DDB
0x140005dbb  cmp     [rbx], r9d
0x140005dbe  jz      short loc_140005DC6
0x140005dc0  mov     rbx, [rbx+8]
0x140005dc4  jmp     short loc_140005DB6
0x140005dc6  add     rbx, 10h
0x140005dca  jz      short loc_140005DDB
0x140005dcc  cmp     qword ptr [rbx+8], 0
0x140005dd1  jnz     short loc_140005DDB
0x140005dd3  lea     rax, [rdi+4]
0x140005dd7  mov     [rbx+8], rax
0x140005ddb  mov     rax, rbx
0x140005dde  mov     rbx, [rsp+28h+arg_0]
0x140005de3  add     rsp, 20h
0x140005de7  pop     rdi
0x140005de8  retn
```
