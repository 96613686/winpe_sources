# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005160`
- end: `0x18000521b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004980`

## callees

- `0x180003fd0`
- `0x180005160`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051b6`

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
0x180005160  mov     [rsp+arg_0], rbx
0x180005165  push    rdi
0x180005166  sub     rsp, 20h
0x18000516a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005171  xor     ebx, ebx
0x180005173  test    rdi, rdi
0x180005176  jz      short loc_1800051F6
0x180005178  cmp     [rdi+8], rbx
0x18000517c  jnz     short loc_1800051A3
0x18000517e  mov     rcx, [rdi]
0x180005181  lea     rdx, [rsp+28h+arg_8]
0x180005186  mov     [rsp+28h+arg_8], rbx
0x18000518b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005190  test    eax, eax
0x180005192  js      short loc_1800051A3
0x180005194  cmp     [rdi+8], rbx
0x180005198  jnz     short loc_1800051A3
0x18000519a  mov     rax, [rsp+28h+arg_8]
0x18000519f  mov     [rdi+8], rax
0x1800051a3  mov     rax, [rdi+8]
0x1800051a7  lea     rcx, [rax+20h]
0x1800051ab  neg     rax
0x1800051ae  sbb     rdi, rdi
0x1800051b1  and     rdi, rcx
0x1800051b4  jz      short loc_1800051F6
0x1800051b6  call    cs:__imp_GetCurrentThreadId
0x1800051bc  mov     r8d, eax
0x1800051bf  mov     r9d, eax
0x1800051c2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800051cc  shr     r8, 2
0x1800051d0  mul     r8
0x1800051d3  shr     rdx, 3
0x1800051d7  lea     rcx, [rdx+rdx*4]
0x1800051db  add     rcx, rcx
0x1800051de  sub     r8, rcx
0x1800051e1  mov     rbx, [rdi+r8*8+8]
0x1800051e6  jmp     short loc_1800051F1
0x1800051e8  cmp     [rbx], r9d
0x1800051eb  jz      short loc_180005204
0x1800051ed  mov     rbx, [rbx+8]
0x1800051f1  test    rbx, rbx
0x1800051f4  jnz     short loc_1800051E8
0x1800051f6  mov     rax, rbx
0x1800051f9  mov     rbx, [rsp+28h+arg_0]
0x1800051fe  add     rsp, 20h
0x180005202  pop     rdi
0x180005203  retn
0x180005204  add     rbx, 10h
0x180005208  jz      short loc_1800051F6
0x18000520a  cmp     qword ptr [rbx+8], 0
0x18000520f  jnz     short loc_1800051F6
0x180005211  lea     rax, [rdi+4]
0x180005215  mov     [rbx+8], rax
0x180005219  jmp     short loc_1800051F6
```
