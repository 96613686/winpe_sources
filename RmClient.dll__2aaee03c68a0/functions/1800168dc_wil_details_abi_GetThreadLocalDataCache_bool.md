# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800168dc`
- end: `0x180016999`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180016300`

## callees

- `0x1800128e0`
- `0x1800168dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016936`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016936`

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
0x1800168dc  mov     [rsp+arg_0], rbx
0x1800168e1  push    rdi
0x1800168e2  sub     rsp, 20h
0x1800168e6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800168ed  xor     ebx, ebx
0x1800168ef  test    rdi, rdi
0x1800168f2  jz      loc_18001698B
0x1800168f8  cmp     [rdi+8], rbx
0x1800168fc  jnz     short loc_180016923
0x1800168fe  mov     rcx, [rdi]
0x180016901  lea     rdx, [rsp+28h+arg_8]
0x180016906  mov     [rsp+28h+arg_8], rbx
0x18001690b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180016910  test    eax, eax
0x180016912  js      short loc_180016923
0x180016914  cmp     [rdi+8], rbx
0x180016918  jnz     short loc_180016923
0x18001691a  mov     rax, [rsp+28h+arg_8]
0x18001691f  mov     [rdi+8], rax
0x180016923  mov     rax, [rdi+8]
0x180016927  lea     rcx, [rax+20h]
0x18001692b  neg     rax
0x18001692e  sbb     rdi, rdi
0x180016931  and     rdi, rcx
0x180016934  jz      short loc_18001698B
0x180016936  call    cs:__imp_GetCurrentThreadId
0x18001693c  mov     r8d, eax
0x18001693f  mov     r9d, eax
0x180016942  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001694c  shr     r8, 2
0x180016950  mul     r8
0x180016953  shr     rdx, 3
0x180016957  lea     rcx, [rdx+rdx*4]
0x18001695b  add     rcx, rcx
0x18001695e  sub     r8, rcx
0x180016961  mov     rbx, [rdi+r8*8+8]
0x180016966  test    rbx, rbx
0x180016969  jz      short loc_18001698B
0x18001696b  cmp     [rbx], r9d
0x18001696e  jz      short loc_180016976
0x180016970  mov     rbx, [rbx+8]
0x180016974  jmp     short loc_180016966
0x180016976  add     rbx, 10h
0x18001697a  jz      short loc_18001698B
0x18001697c  cmp     qword ptr [rbx+8], 0
0x180016981  jnz     short loc_18001698B
0x180016983  lea     rax, [rdi+4]
0x180016987  mov     [rbx+8], rax
0x18001698b  mov     rax, rbx
0x18001698e  mov     rbx, [rsp+28h+arg_0]
0x180016993  add     rsp, 20h
0x180016997  pop     rdi
0x180016998  retn
```
