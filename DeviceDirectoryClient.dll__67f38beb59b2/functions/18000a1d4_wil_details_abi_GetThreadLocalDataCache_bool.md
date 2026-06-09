# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000a1d4`
- end: `0x18000a291`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009ad0`

## callees

- `0x180008e8c`
- `0x18000a1d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a22e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a22e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000a1d4  mov     [rsp+arg_0], rbx
0x18000a1d9  push    rdi
0x18000a1da  sub     rsp, 20h
0x18000a1de  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000a1e5  xor     ebx, ebx
0x18000a1e7  test    rdi, rdi
0x18000a1ea  jz      loc_18000A283
0x18000a1f0  cmp     [rdi+8], rbx
0x18000a1f4  jnz     short loc_18000A21B
0x18000a1f6  mov     rcx, [rdi]
0x18000a1f9  lea     rdx, [rsp+28h+arg_8]
0x18000a1fe  mov     [rsp+28h+arg_8], rbx
0x18000a203  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000a208  test    eax, eax
0x18000a20a  js      short loc_18000A21B
0x18000a20c  cmp     [rdi+8], rbx
0x18000a210  jnz     short loc_18000A21B
0x18000a212  mov     rax, [rsp+28h+arg_8]
0x18000a217  mov     [rdi+8], rax
0x18000a21b  mov     rax, [rdi+8]
0x18000a21f  lea     rcx, [rax+20h]
0x18000a223  neg     rax
0x18000a226  sbb     rdi, rdi
0x18000a229  and     rdi, rcx
0x18000a22c  jz      short loc_18000A283
0x18000a22e  call    cs:__imp_GetCurrentThreadId
0x18000a234  mov     r8d, eax
0x18000a237  mov     r9d, eax
0x18000a23a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000a244  shr     r8, 2
0x18000a248  mul     r8
0x18000a24b  shr     rdx, 3
0x18000a24f  lea     rcx, [rdx+rdx*4]
0x18000a253  add     rcx, rcx
0x18000a256  sub     r8, rcx
0x18000a259  mov     rbx, [rdi+r8*8+8]
0x18000a25e  test    rbx, rbx
0x18000a261  jz      short loc_18000A283
0x18000a263  cmp     [rbx], r9d
0x18000a266  jz      short loc_18000A26E
0x18000a268  mov     rbx, [rbx+8]
0x18000a26c  jmp     short loc_18000A25E
0x18000a26e  add     rbx, 10h
0x18000a272  jz      short loc_18000A283
0x18000a274  cmp     qword ptr [rbx+8], 0
0x18000a279  jnz     short loc_18000A283
0x18000a27b  lea     rax, [rdi+4]
0x18000a27f  mov     [rbx+8], rax
0x18000a283  mov     rax, rbx
0x18000a286  mov     rbx, [rsp+28h+arg_0]
0x18000a28b  add     rsp, 20h
0x18000a28f  pop     rdi
0x18000a290  retn
```
