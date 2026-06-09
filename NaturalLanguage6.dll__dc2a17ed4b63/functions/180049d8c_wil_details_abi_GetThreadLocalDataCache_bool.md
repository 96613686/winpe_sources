# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180049d8c`
- end: `0x180049e49`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180049860`

## callees

- `0x1800380d4`
- `0x180049d8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049de6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049de6`

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
0x180049d8c  mov     [rsp+arg_0], rbx
0x180049d91  push    rdi
0x180049d92  sub     rsp, 20h
0x180049d96  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180049d9d  xor     ebx, ebx
0x180049d9f  test    rdi, rdi
0x180049da2  jz      loc_180049E3B
0x180049da8  cmp     [rdi+8], rbx
0x180049dac  jnz     short loc_180049DD3
0x180049dae  mov     rcx, [rdi]
0x180049db1  lea     rdx, [rsp+28h+arg_8]
0x180049db6  mov     [rsp+28h+arg_8], rbx
0x180049dbb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180049dc0  test    eax, eax
0x180049dc2  js      short loc_180049DD3
0x180049dc4  cmp     [rdi+8], rbx
0x180049dc8  jnz     short loc_180049DD3
0x180049dca  mov     rax, [rsp+28h+arg_8]
0x180049dcf  mov     [rdi+8], rax
0x180049dd3  mov     rax, [rdi+8]
0x180049dd7  lea     rcx, [rax+20h]
0x180049ddb  neg     rax
0x180049dde  sbb     rdi, rdi
0x180049de1  and     rdi, rcx
0x180049de4  jz      short loc_180049E3B
0x180049de6  call    cs:__imp_GetCurrentThreadId
0x180049dec  mov     r8d, eax
0x180049def  mov     r9d, eax
0x180049df2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180049dfc  shr     r8, 2
0x180049e00  mul     r8
0x180049e03  shr     rdx, 3
0x180049e07  lea     rcx, [rdx+rdx*4]
0x180049e0b  add     rcx, rcx
0x180049e0e  sub     r8, rcx
0x180049e11  mov     rbx, [rdi+r8*8+8]
0x180049e16  test    rbx, rbx
0x180049e19  jz      short loc_180049E3B
0x180049e1b  cmp     [rbx], r9d
0x180049e1e  jz      short loc_180049E26
0x180049e20  mov     rbx, [rbx+8]
0x180049e24  jmp     short loc_180049E16
0x180049e26  add     rbx, 10h
0x180049e2a  jz      short loc_180049E3B
0x180049e2c  cmp     qword ptr [rbx+8], 0
0x180049e31  jnz     short loc_180049E3B
0x180049e33  lea     rax, [rdi+4]
0x180049e37  mov     [rbx+8], rax
0x180049e3b  mov     rax, rbx
0x180049e3e  mov     rbx, [rsp+28h+arg_0]
0x180049e43  add     rsp, 20h
0x180049e47  pop     rdi
0x180049e48  retn
```
