# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1400042a0`
- end: `0x14000435d`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003be0`

## callees

- `0x140003728`
- `0x1400042a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400042fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400042fa`

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
0x1400042a0  mov     [rsp+arg_0], rbx
0x1400042a5  push    rdi
0x1400042a6  sub     rsp, 20h
0x1400042aa  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1400042b1  xor     ebx, ebx
0x1400042b3  test    rdi, rdi
0x1400042b6  jz      loc_14000434F
0x1400042bc  cmp     [rdi+8], rbx
0x1400042c0  jnz     short loc_1400042E7
0x1400042c2  mov     rcx, [rdi]
0x1400042c5  lea     rdx, [rsp+28h+arg_8]
0x1400042ca  mov     [rsp+28h+arg_8], rbx
0x1400042cf  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1400042d4  test    eax, eax
0x1400042d6  js      short loc_1400042E7
0x1400042d8  cmp     [rdi+8], rbx
0x1400042dc  jnz     short loc_1400042E7
0x1400042de  mov     rax, [rsp+28h+arg_8]
0x1400042e3  mov     [rdi+8], rax
0x1400042e7  mov     rax, [rdi+8]
0x1400042eb  lea     rcx, [rax+20h]
0x1400042ef  neg     rax
0x1400042f2  sbb     rdi, rdi
0x1400042f5  and     rdi, rcx
0x1400042f8  jz      short loc_14000434F
0x1400042fa  call    cs:__imp_GetCurrentThreadId
0x140004300  mov     r8d, eax
0x140004303  mov     r9d, eax
0x140004306  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004310  shr     r8, 2
0x140004314  mul     r8
0x140004317  shr     rdx, 3
0x14000431b  lea     rcx, [rdx+rdx*4]
0x14000431f  add     rcx, rcx
0x140004322  sub     r8, rcx
0x140004325  mov     rbx, [rdi+r8*8+8]
0x14000432a  test    rbx, rbx
0x14000432d  jz      short loc_14000434F
0x14000432f  cmp     [rbx], r9d
0x140004332  jz      short loc_14000433A
0x140004334  mov     rbx, [rbx+8]
0x140004338  jmp     short loc_14000432A
0x14000433a  add     rbx, 10h
0x14000433e  jz      short loc_14000434F
0x140004340  cmp     qword ptr [rbx+8], 0
0x140004345  jnz     short loc_14000434F
0x140004347  lea     rax, [rdi+4]
0x14000434b  mov     [rbx+8], rax
0x14000434f  mov     rax, rbx
0x140004352  mov     rbx, [rsp+28h+arg_0]
0x140004357  add     rsp, 20h
0x14000435b  pop     rdi
0x14000435c  retn
```
