# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x14000516c`
- end: `0x140005230`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `196`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004420`

## callees

- `0x140003874`
- `0x14000516c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400051c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400051c6`

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
0x14000516c  mov     [rsp+arg_0], rbx
0x140005171  push    rdi
0x140005172  sub     rsp, 20h
0x140005176  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x14000517d  xor     ebx, ebx
0x14000517f  test    rdi, rdi
0x140005182  jz      loc_140005221
0x140005188  cmp     [rdi+8], rbx
0x14000518c  jnz     short loc_1400051B3
0x14000518e  mov     rcx, [rdi]
0x140005191  lea     rdx, [rsp+28h+arg_8]
0x140005196  mov     [rsp+28h+arg_8], rbx
0x14000519b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1400051a0  test    eax, eax
0x1400051a2  js      short loc_1400051B3
0x1400051a4  cmp     [rdi+8], rbx
0x1400051a8  jnz     short loc_1400051B3
0x1400051aa  mov     rax, [rsp+28h+arg_8]
0x1400051af  mov     [rdi+8], rax
0x1400051b3  mov     rax, [rdi+8]
0x1400051b7  lea     rcx, [rax+20h]
0x1400051bb  neg     rax
0x1400051be  sbb     rdi, rdi
0x1400051c1  and     rdi, rcx
0x1400051c4  jz      short loc_140005221
0x1400051c6  call    cs:__imp_GetCurrentThreadId
0x1400051cd  nop     dword ptr [rax+rax+00h]
0x1400051d2  mov     r8d, eax
0x1400051d5  mov     r9d, eax
0x1400051d8  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400051e2  shr     r8, 2
0x1400051e6  mul     r8
0x1400051e9  shr     rdx, 3
0x1400051ed  lea     rcx, [rdx+rdx*4]
0x1400051f1  add     rcx, rcx
0x1400051f4  sub     r8, rcx
0x1400051f7  mov     rbx, [rdi+r8*8+8]
0x1400051fc  test    rbx, rbx
0x1400051ff  jz      short loc_140005221
0x140005201  cmp     [rbx], r9d
0x140005204  jz      short loc_14000520C
0x140005206  mov     rbx, [rbx+8]
0x14000520a  jmp     short loc_1400051FC
0x14000520c  add     rbx, 10h
0x140005210  jz      short loc_140005221
0x140005212  cmp     qword ptr [rbx+8], 0
0x140005217  jnz     short loc_140005221
0x140005219  lea     rax, [rdi+4]
0x14000521d  mov     [rbx+8], rax
0x140005221  mov     rax, rbx
0x140005224  mov     rbx, [rsp+28h+arg_0]
0x140005229  add     rsp, 20h
0x14000522d  pop     rdi
0x14000522e  retn
```
