# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800063c8`
- end: `0x18000648c`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `196`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005c80`

## callees

- `0x180004ce0`
- `0x1800063c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006422`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006422`

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
0x1800063c8  mov     [rsp+arg_0], rbx
0x1800063cd  push    rdi
0x1800063ce  sub     rsp, 20h
0x1800063d2  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800063d9  xor     ebx, ebx
0x1800063db  test    rdi, rdi
0x1800063de  jz      loc_18000647D
0x1800063e4  cmp     [rdi+8], rbx
0x1800063e8  jnz     short loc_18000640F
0x1800063ea  mov     rcx, [rdi]
0x1800063ed  lea     rdx, [rsp+28h+arg_8]
0x1800063f2  mov     [rsp+28h+arg_8], rbx
0x1800063f7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800063fc  test    eax, eax
0x1800063fe  js      short loc_18000640F
0x180006400  cmp     [rdi+8], rbx
0x180006404  jnz     short loc_18000640F
0x180006406  mov     rax, [rsp+28h+arg_8]
0x18000640b  mov     [rdi+8], rax
0x18000640f  mov     rax, [rdi+8]
0x180006413  lea     rcx, [rax+20h]
0x180006417  neg     rax
0x18000641a  sbb     rdi, rdi
0x18000641d  and     rdi, rcx
0x180006420  jz      short loc_18000647D
0x180006422  call    cs:__imp_GetCurrentThreadId
0x180006429  nop     dword ptr [rax+rax+00h]
0x18000642e  mov     r8d, eax
0x180006431  mov     r9d, eax
0x180006434  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000643e  shr     r8, 2
0x180006442  mul     r8
0x180006445  shr     rdx, 3
0x180006449  lea     rcx, [rdx+rdx*4]
0x18000644d  add     rcx, rcx
0x180006450  sub     r8, rcx
0x180006453  mov     rbx, [rdi+r8*8+8]
0x180006458  test    rbx, rbx
0x18000645b  jz      short loc_18000647D
0x18000645d  cmp     [rbx], r9d
0x180006460  jz      short loc_180006468
0x180006462  mov     rbx, [rbx+8]
0x180006466  jmp     short loc_180006458
0x180006468  add     rbx, 10h
0x18000646c  jz      short loc_18000647D
0x18000646e  cmp     qword ptr [rbx+8], 0
0x180006473  jnz     short loc_18000647D
0x180006475  lea     rax, [rdi+4]
0x180006479  mov     [rbx+8], rax
0x18000647d  mov     rax, rbx
0x180006480  mov     rbx, [rsp+28h+arg_0]
0x180006485  add     rsp, 20h
0x180006489  pop     rdi
0x18000648a  retn
```
