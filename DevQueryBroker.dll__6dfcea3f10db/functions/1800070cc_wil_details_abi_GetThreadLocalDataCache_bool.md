# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800070cc`
- end: `0x180007187`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800068f0`

## callees

- `0x18000596c`
- `0x1800070cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007122`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007122`

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
0x1800070cc  mov     [rsp+arg_0], rbx
0x1800070d1  push    rdi
0x1800070d2  sub     rsp, 20h
0x1800070d6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800070dd  xor     ebx, ebx
0x1800070df  test    rdi, rdi
0x1800070e2  jz      short loc_180007162
0x1800070e4  cmp     [rdi+8], rbx
0x1800070e8  jnz     short loc_18000710F
0x1800070ea  mov     rcx, [rdi]
0x1800070ed  lea     rdx, [rsp+28h+arg_8]
0x1800070f2  mov     [rsp+28h+arg_8], rbx
0x1800070f7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800070fc  test    eax, eax
0x1800070fe  js      short loc_18000710F
0x180007100  cmp     [rdi+8], rbx
0x180007104  jnz     short loc_18000710F
0x180007106  mov     rax, [rsp+28h+arg_8]
0x18000710b  mov     [rdi+8], rax
0x18000710f  mov     rax, [rdi+8]
0x180007113  lea     rcx, [rax+20h]
0x180007117  neg     rax
0x18000711a  sbb     rdi, rdi
0x18000711d  and     rdi, rcx
0x180007120  jz      short loc_180007162
0x180007122  call    cs:__imp_GetCurrentThreadId
0x180007128  mov     r8d, eax
0x18000712b  mov     r9d, eax
0x18000712e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007138  shr     r8, 2
0x18000713c  mul     r8
0x18000713f  shr     rdx, 3
0x180007143  lea     rcx, [rdx+rdx*4]
0x180007147  add     rcx, rcx
0x18000714a  sub     r8, rcx
0x18000714d  mov     rbx, [rdi+r8*8+8]
0x180007152  jmp     short loc_18000715D
0x180007154  cmp     [rbx], r9d
0x180007157  jz      short loc_180007170
0x180007159  mov     rbx, [rbx+8]
0x18000715d  test    rbx, rbx
0x180007160  jnz     short loc_180007154
0x180007162  mov     rax, rbx
0x180007165  mov     rbx, [rsp+28h+arg_0]
0x18000716a  add     rsp, 20h
0x18000716e  pop     rdi
0x18000716f  retn
0x180007170  add     rbx, 10h
0x180007174  jz      short loc_180007162
0x180007176  cmp     qword ptr [rbx+8], 0
0x18000717b  jnz     short loc_180007162
0x18000717d  lea     rax, [rdi+4]
0x180007181  mov     [rbx+8], rax
0x180007185  jmp     short loc_180007162
```
