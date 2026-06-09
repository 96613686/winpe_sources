# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800098ac`
- end: `0x180009969`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009230`

## callees

- `0x180008d8c`
- `0x1800098ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009906`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009906`

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
0x1800098ac  mov     [rsp+arg_0], rbx
0x1800098b1  push    rdi
0x1800098b2  sub     rsp, 20h
0x1800098b6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800098bd  xor     ebx, ebx
0x1800098bf  test    rdi, rdi
0x1800098c2  jz      loc_18000995B
0x1800098c8  cmp     [rdi+8], rbx
0x1800098cc  jnz     short loc_1800098F3
0x1800098ce  mov     rcx, [rdi]
0x1800098d1  lea     rdx, [rsp+28h+arg_8]
0x1800098d6  mov     [rsp+28h+arg_8], rbx
0x1800098db  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800098e0  test    eax, eax
0x1800098e2  js      short loc_1800098F3
0x1800098e4  cmp     [rdi+8], rbx
0x1800098e8  jnz     short loc_1800098F3
0x1800098ea  mov     rax, [rsp+28h+arg_8]
0x1800098ef  mov     [rdi+8], rax
0x1800098f3  mov     rax, [rdi+8]
0x1800098f7  lea     rcx, [rax+20h]
0x1800098fb  neg     rax
0x1800098fe  sbb     rdi, rdi
0x180009901  and     rdi, rcx
0x180009904  jz      short loc_18000995B
0x180009906  call    cs:__imp_GetCurrentThreadId
0x18000990c  mov     r8d, eax
0x18000990f  mov     r9d, eax
0x180009912  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000991c  shr     r8, 2
0x180009920  mul     r8
0x180009923  shr     rdx, 3
0x180009927  lea     rcx, [rdx+rdx*4]
0x18000992b  add     rcx, rcx
0x18000992e  sub     r8, rcx
0x180009931  mov     rbx, [rdi+r8*8+8]
0x180009936  test    rbx, rbx
0x180009939  jz      short loc_18000995B
0x18000993b  cmp     [rbx], r9d
0x18000993e  jz      short loc_180009946
0x180009940  mov     rbx, [rbx+8]
0x180009944  jmp     short loc_180009936
0x180009946  add     rbx, 10h
0x18000994a  jz      short loc_18000995B
0x18000994c  cmp     qword ptr [rbx+8], 0
0x180009951  jnz     short loc_18000995B
0x180009953  lea     rax, [rdi+4]
0x180009957  mov     [rbx+8], rax
0x18000995b  mov     rax, rbx
0x18000995e  mov     rbx, [rsp+28h+arg_0]
0x180009963  add     rsp, 20h
0x180009967  pop     rdi
0x180009968  retn
```
