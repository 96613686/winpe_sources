# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180006890`
- end: `0x18000694b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800060b0`

## callees

- `0x180004e58`
- `0x180006890`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800068e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800068e6`

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
0x180006890  mov     [rsp+arg_0], rbx
0x180006895  push    rdi
0x180006896  sub     rsp, 20h
0x18000689a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800068a1  xor     ebx, ebx
0x1800068a3  test    rdi, rdi
0x1800068a6  jz      short loc_180006926
0x1800068a8  cmp     [rdi+8], rbx
0x1800068ac  jnz     short loc_1800068D3
0x1800068ae  mov     rcx, [rdi]
0x1800068b1  lea     rdx, [rsp+28h+arg_8]
0x1800068b6  mov     [rsp+28h+arg_8], rbx
0x1800068bb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800068c0  test    eax, eax
0x1800068c2  js      short loc_1800068D3
0x1800068c4  cmp     [rdi+8], rbx
0x1800068c8  jnz     short loc_1800068D3
0x1800068ca  mov     rax, [rsp+28h+arg_8]
0x1800068cf  mov     [rdi+8], rax
0x1800068d3  mov     rax, [rdi+8]
0x1800068d7  lea     rcx, [rax+20h]
0x1800068db  neg     rax
0x1800068de  sbb     rdi, rdi
0x1800068e1  and     rdi, rcx
0x1800068e4  jz      short loc_180006926
0x1800068e6  call    cs:__imp_GetCurrentThreadId
0x1800068ec  mov     r8d, eax
0x1800068ef  mov     r9d, eax
0x1800068f2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800068fc  shr     r8, 2
0x180006900  mul     r8
0x180006903  shr     rdx, 3
0x180006907  lea     rcx, [rdx+rdx*4]
0x18000690b  add     rcx, rcx
0x18000690e  sub     r8, rcx
0x180006911  mov     rbx, [rdi+r8*8+8]
0x180006916  jmp     short loc_180006921
0x180006918  cmp     [rbx], r9d
0x18000691b  jz      short loc_180006934
0x18000691d  mov     rbx, [rbx+8]
0x180006921  test    rbx, rbx
0x180006924  jnz     short loc_180006918
0x180006926  mov     rax, rbx
0x180006929  mov     rbx, [rsp+28h+arg_0]
0x18000692e  add     rsp, 20h
0x180006932  pop     rdi
0x180006933  retn
0x180006934  add     rbx, 10h
0x180006938  jz      short loc_180006926
0x18000693a  cmp     qword ptr [rbx+8], 0
0x18000693f  jnz     short loc_180006926
0x180006941  lea     rax, [rdi+4]
0x180006945  mov     [rbx+8], rax
0x180006949  jmp     short loc_180006926
```
