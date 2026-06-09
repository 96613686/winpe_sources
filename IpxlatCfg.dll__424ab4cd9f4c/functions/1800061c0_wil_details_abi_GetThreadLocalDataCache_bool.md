# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800061c0`
- end: `0x18000627b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800059e0`

## callees

- `0x180004988`
- `0x1800061c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006216`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006216`

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
0x1800061c0  mov     [rsp+arg_0], rbx
0x1800061c5  push    rdi
0x1800061c6  sub     rsp, 20h
0x1800061ca  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800061d1  xor     ebx, ebx
0x1800061d3  test    rdi, rdi
0x1800061d6  jz      short loc_180006256
0x1800061d8  cmp     [rdi+8], rbx
0x1800061dc  jnz     short loc_180006203
0x1800061de  mov     rcx, [rdi]
0x1800061e1  lea     rdx, [rsp+28h+arg_8]
0x1800061e6  mov     [rsp+28h+arg_8], rbx
0x1800061eb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800061f0  test    eax, eax
0x1800061f2  js      short loc_180006203
0x1800061f4  cmp     [rdi+8], rbx
0x1800061f8  jnz     short loc_180006203
0x1800061fa  mov     rax, [rsp+28h+arg_8]
0x1800061ff  mov     [rdi+8], rax
0x180006203  mov     rax, [rdi+8]
0x180006207  lea     rcx, [rax+20h]
0x18000620b  neg     rax
0x18000620e  sbb     rdi, rdi
0x180006211  and     rdi, rcx
0x180006214  jz      short loc_180006256
0x180006216  call    cs:__imp_GetCurrentThreadId
0x18000621c  mov     r8d, eax
0x18000621f  mov     r9d, eax
0x180006222  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000622c  shr     r8, 2
0x180006230  mul     r8
0x180006233  shr     rdx, 3
0x180006237  lea     rcx, [rdx+rdx*4]
0x18000623b  add     rcx, rcx
0x18000623e  sub     r8, rcx
0x180006241  mov     rbx, [rdi+r8*8+8]
0x180006246  jmp     short loc_180006251
0x180006248  cmp     [rbx], r9d
0x18000624b  jz      short loc_180006264
0x18000624d  mov     rbx, [rbx+8]
0x180006251  test    rbx, rbx
0x180006254  jnz     short loc_180006248
0x180006256  mov     rax, rbx
0x180006259  mov     rbx, [rsp+28h+arg_0]
0x18000625e  add     rsp, 20h
0x180006262  pop     rdi
0x180006263  retn
0x180006264  add     rbx, 10h
0x180006268  jz      short loc_180006256
0x18000626a  cmp     qword ptr [rbx+8], 0
0x18000626f  jnz     short loc_180006256
0x180006271  lea     rax, [rdi+4]
0x180006275  mov     [rbx+8], rax
0x180006279  jmp     short loc_180006256
```
