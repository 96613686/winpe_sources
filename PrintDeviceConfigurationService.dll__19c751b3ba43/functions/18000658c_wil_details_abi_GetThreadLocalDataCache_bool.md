# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000658c`
- end: `0x180006649`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005ee0`

## callees

- `0x180005498`
- `0x18000658c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800065e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800065e6`

## pseudocode

```c
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
0x18000658c  mov     [rsp+arg_0], rbx
0x180006591  push    rdi
0x180006592  sub     rsp, 20h
0x180006596  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000659d  xor     ebx, ebx
0x18000659f  test    rdi, rdi
0x1800065a2  jz      loc_18000663B
0x1800065a8  cmp     [rdi+8], rbx
0x1800065ac  jnz     short loc_1800065D3
0x1800065ae  mov     rcx, [rdi]
0x1800065b1  lea     rdx, [rsp+28h+arg_8]
0x1800065b6  mov     [rsp+28h+arg_8], rbx
0x1800065bb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800065c0  test    eax, eax
0x1800065c2  js      short loc_1800065D3
0x1800065c4  cmp     [rdi+8], rbx
0x1800065c8  jnz     short loc_1800065D3
0x1800065ca  mov     rax, [rsp+28h+arg_8]
0x1800065cf  mov     [rdi+8], rax
0x1800065d3  mov     rax, [rdi+8]
0x1800065d7  lea     rcx, [rax+20h]
0x1800065db  neg     rax
0x1800065de  sbb     rdi, rdi
0x1800065e1  and     rdi, rcx
0x1800065e4  jz      short loc_18000663B
0x1800065e6  call    cs:__imp_GetCurrentThreadId
0x1800065ec  mov     r8d, eax
0x1800065ef  mov     r9d, eax
0x1800065f2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800065fc  shr     r8, 2
0x180006600  mul     r8
0x180006603  shr     rdx, 3
0x180006607  lea     rcx, [rdx+rdx*4]
0x18000660b  add     rcx, rcx
0x18000660e  sub     r8, rcx
0x180006611  mov     rbx, [rdi+r8*8+8]
0x180006616  test    rbx, rbx
0x180006619  jz      short loc_18000663B
0x18000661b  cmp     [rbx], r9d
0x18000661e  jz      short loc_180006626
0x180006620  mov     rbx, [rbx+8]
0x180006624  jmp     short loc_180006616
0x180006626  add     rbx, 10h
0x18000662a  jz      short loc_18000663B
0x18000662c  cmp     qword ptr [rbx+8], 0
0x180006631  jnz     short loc_18000663B
0x180006633  lea     rax, [rdi+4]
0x180006637  mov     [rbx+8], rax
0x18000663b  mov     rax, rbx
0x18000663e  mov     rbx, [rsp+28h+arg_0]
0x180006643  add     rsp, 20h
0x180006647  pop     rdi
0x180006648  retn
```
