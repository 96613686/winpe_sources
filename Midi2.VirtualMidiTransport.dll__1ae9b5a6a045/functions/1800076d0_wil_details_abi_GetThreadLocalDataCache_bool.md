# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800076d0`
- end: `0x18000778b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006ef0`

## callees

- `0x180005828`
- `0x1800076d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007726`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007726`

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
0x1800076d0  mov     [rsp+arg_0], rbx
0x1800076d5  push    rdi
0x1800076d6  sub     rsp, 20h
0x1800076da  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800076e1  xor     ebx, ebx
0x1800076e3  test    rdi, rdi
0x1800076e6  jz      short loc_180007766
0x1800076e8  cmp     [rdi+8], rbx
0x1800076ec  jnz     short loc_180007713
0x1800076ee  mov     rcx, [rdi]
0x1800076f1  lea     rdx, [rsp+28h+arg_8]
0x1800076f6  mov     [rsp+28h+arg_8], rbx
0x1800076fb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180007700  test    eax, eax
0x180007702  js      short loc_180007713
0x180007704  cmp     [rdi+8], rbx
0x180007708  jnz     short loc_180007713
0x18000770a  mov     rax, [rsp+28h+arg_8]
0x18000770f  mov     [rdi+8], rax
0x180007713  mov     rax, [rdi+8]
0x180007717  lea     rcx, [rax+20h]
0x18000771b  neg     rax
0x18000771e  sbb     rdi, rdi
0x180007721  and     rdi, rcx
0x180007724  jz      short loc_180007766
0x180007726  call    cs:__imp_GetCurrentThreadId
0x18000772c  mov     r8d, eax
0x18000772f  mov     r9d, eax
0x180007732  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000773c  shr     r8, 2
0x180007740  mul     r8
0x180007743  shr     rdx, 3
0x180007747  lea     rcx, [rdx+rdx*4]
0x18000774b  add     rcx, rcx
0x18000774e  sub     r8, rcx
0x180007751  mov     rbx, [rdi+r8*8+8]
0x180007756  jmp     short loc_180007761
0x180007758  cmp     [rbx], r9d
0x18000775b  jz      short loc_180007774
0x18000775d  mov     rbx, [rbx+8]
0x180007761  test    rbx, rbx
0x180007764  jnz     short loc_180007758
0x180007766  mov     rax, rbx
0x180007769  mov     rbx, [rsp+28h+arg_0]
0x18000776e  add     rsp, 20h
0x180007772  pop     rdi
0x180007773  retn
0x180007774  add     rbx, 10h
0x180007778  jz      short loc_180007766
0x18000777a  cmp     qword ptr [rbx+8], 0
0x18000777f  jnz     short loc_180007766
0x180007781  lea     rax, [rdi+4]
0x180007785  mov     [rbx+8], rax
0x180007789  jmp     short loc_180007766
```
