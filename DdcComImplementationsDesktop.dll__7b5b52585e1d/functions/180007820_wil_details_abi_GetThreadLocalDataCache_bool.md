# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180007820`
- end: `0x1800078db`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007040`

## callees

- `0x1800060bc`
- `0x180007820`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007876`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007876`

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
0x180007820  mov     [rsp+arg_0], rbx
0x180007825  push    rdi
0x180007826  sub     rsp, 20h
0x18000782a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180007831  xor     ebx, ebx
0x180007833  test    rdi, rdi
0x180007836  jz      short loc_1800078B6
0x180007838  cmp     [rdi+8], rbx
0x18000783c  jnz     short loc_180007863
0x18000783e  mov     rcx, [rdi]
0x180007841  lea     rdx, [rsp+28h+arg_8]
0x180007846  mov     [rsp+28h+arg_8], rbx
0x18000784b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180007850  test    eax, eax
0x180007852  js      short loc_180007863
0x180007854  cmp     [rdi+8], rbx
0x180007858  jnz     short loc_180007863
0x18000785a  mov     rax, [rsp+28h+arg_8]
0x18000785f  mov     [rdi+8], rax
0x180007863  mov     rax, [rdi+8]
0x180007867  lea     rcx, [rax+20h]
0x18000786b  neg     rax
0x18000786e  sbb     rdi, rdi
0x180007871  and     rdi, rcx
0x180007874  jz      short loc_1800078B6
0x180007876  call    cs:__imp_GetCurrentThreadId
0x18000787c  mov     r8d, eax
0x18000787f  mov     r9d, eax
0x180007882  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000788c  shr     r8, 2
0x180007890  mul     r8
0x180007893  shr     rdx, 3
0x180007897  lea     rcx, [rdx+rdx*4]
0x18000789b  add     rcx, rcx
0x18000789e  sub     r8, rcx
0x1800078a1  mov     rbx, [rdi+r8*8+8]
0x1800078a6  jmp     short loc_1800078B1
0x1800078a8  cmp     [rbx], r9d
0x1800078ab  jz      short loc_1800078C4
0x1800078ad  mov     rbx, [rbx+8]
0x1800078b1  test    rbx, rbx
0x1800078b4  jnz     short loc_1800078A8
0x1800078b6  mov     rax, rbx
0x1800078b9  mov     rbx, [rsp+28h+arg_0]
0x1800078be  add     rsp, 20h
0x1800078c2  pop     rdi
0x1800078c3  retn
0x1800078c4  add     rbx, 10h
0x1800078c8  jz      short loc_1800078B6
0x1800078ca  cmp     qword ptr [rbx+8], 0
0x1800078cf  jnz     short loc_1800078B6
0x1800078d1  lea     rax, [rdi+4]
0x1800078d5  mov     [rbx+8], rax
0x1800078d9  jmp     short loc_1800078B6
```
