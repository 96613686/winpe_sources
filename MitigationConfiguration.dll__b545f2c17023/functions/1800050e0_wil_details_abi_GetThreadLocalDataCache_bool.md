# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800050e0`
- end: `0x18000519b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004900`

## callees

- `0x1800038c8`
- `0x1800050e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005136`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005136`

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
0x1800050e0  mov     [rsp+arg_0], rbx
0x1800050e5  push    rdi
0x1800050e6  sub     rsp, 20h
0x1800050ea  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800050f1  xor     ebx, ebx
0x1800050f3  test    rdi, rdi
0x1800050f6  jz      short loc_180005176
0x1800050f8  cmp     [rdi+8], rbx
0x1800050fc  jnz     short loc_180005123
0x1800050fe  mov     rcx, [rdi]
0x180005101  lea     rdx, [rsp+28h+arg_8]
0x180005106  mov     [rsp+28h+arg_8], rbx
0x18000510b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005110  test    eax, eax
0x180005112  js      short loc_180005123
0x180005114  cmp     [rdi+8], rbx
0x180005118  jnz     short loc_180005123
0x18000511a  mov     rax, [rsp+28h+arg_8]
0x18000511f  mov     [rdi+8], rax
0x180005123  mov     rax, [rdi+8]
0x180005127  lea     rcx, [rax+20h]
0x18000512b  neg     rax
0x18000512e  sbb     rdi, rdi
0x180005131  and     rdi, rcx
0x180005134  jz      short loc_180005176
0x180005136  call    cs:__imp_GetCurrentThreadId
0x18000513c  mov     r8d, eax
0x18000513f  mov     r9d, eax
0x180005142  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000514c  shr     r8, 2
0x180005150  mul     r8
0x180005153  shr     rdx, 3
0x180005157  lea     rcx, [rdx+rdx*4]
0x18000515b  add     rcx, rcx
0x18000515e  sub     r8, rcx
0x180005161  mov     rbx, [rdi+r8*8+8]
0x180005166  jmp     short loc_180005171
0x180005168  cmp     [rbx], r9d
0x18000516b  jz      short loc_180005184
0x18000516d  mov     rbx, [rbx+8]
0x180005171  test    rbx, rbx
0x180005174  jnz     short loc_180005168
0x180005176  mov     rax, rbx
0x180005179  mov     rbx, [rsp+28h+arg_0]
0x18000517e  add     rsp, 20h
0x180005182  pop     rdi
0x180005183  retn
0x180005184  add     rbx, 10h
0x180005188  jz      short loc_180005176
0x18000518a  cmp     qword ptr [rbx+8], 0
0x18000518f  jnz     short loc_180005176
0x180005191  lea     rax, [rdi+4]
0x180005195  mov     [rbx+8], rax
0x180005199  jmp     short loc_180005176
```
