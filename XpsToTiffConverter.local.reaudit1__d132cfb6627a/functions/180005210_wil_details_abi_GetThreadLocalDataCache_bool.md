# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180005210`
- end: `0x1800052cb`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004a30`

## callees

- `0x180003ab8`
- `0x180005210`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005266`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005266`

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
0x180005210  mov     [rsp+arg_0], rbx
0x180005215  push    rdi
0x180005216  sub     rsp, 20h
0x18000521a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180005221  xor     ebx, ebx
0x180005223  test    rdi, rdi
0x180005226  jz      short loc_1800052A6
0x180005228  cmp     [rdi+8], rbx
0x18000522c  jnz     short loc_180005253
0x18000522e  mov     rcx, [rdi]
0x180005231  lea     rdx, [rsp+28h+arg_8]
0x180005236  mov     [rsp+28h+arg_8], rbx
0x18000523b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005240  test    eax, eax
0x180005242  js      short loc_180005253
0x180005244  cmp     [rdi+8], rbx
0x180005248  jnz     short loc_180005253
0x18000524a  mov     rax, [rsp+28h+arg_8]
0x18000524f  mov     [rdi+8], rax
0x180005253  mov     rax, [rdi+8]
0x180005257  lea     rcx, [rax+20h]
0x18000525b  neg     rax
0x18000525e  sbb     rdi, rdi
0x180005261  and     rdi, rcx
0x180005264  jz      short loc_1800052A6
0x180005266  call    cs:__imp_GetCurrentThreadId
0x18000526c  mov     r8d, eax
0x18000526f  mov     r9d, eax
0x180005272  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000527c  shr     r8, 2
0x180005280  mul     r8
0x180005283  shr     rdx, 3
0x180005287  lea     rcx, [rdx+rdx*4]
0x18000528b  add     rcx, rcx
0x18000528e  sub     r8, rcx
0x180005291  mov     rbx, [rdi+r8*8+8]
0x180005296  jmp     short loc_1800052A1
0x180005298  cmp     [rbx], r9d
0x18000529b  jz      short loc_1800052B4
0x18000529d  mov     rbx, [rbx+8]
0x1800052a1  test    rbx, rbx
0x1800052a4  jnz     short loc_180005298
0x1800052a6  mov     rax, rbx
0x1800052a9  mov     rbx, [rsp+28h+arg_0]
0x1800052ae  add     rsp, 20h
0x1800052b2  pop     rdi
0x1800052b3  retn
0x1800052b4  add     rbx, 10h
0x1800052b8  jz      short loc_1800052A6
0x1800052ba  cmp     qword ptr [rbx+8], 0
0x1800052bf  jnz     short loc_1800052A6
0x1800052c1  lea     rax, [rdi+4]
0x1800052c5  mov     [rbx+8], rax
0x1800052c9  jmp     short loc_1800052A6
```
