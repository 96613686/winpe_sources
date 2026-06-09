# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140009458`
- end: `0x140009513`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140008bc0`

## callees

- `0x140008448`
- `0x140009458`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400094ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400094ae`

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
0x140009458  mov     [rsp+arg_0], rbx
0x14000945d  push    rdi
0x14000945e  sub     rsp, 20h
0x140009462  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140009469  xor     ebx, ebx
0x14000946b  test    rdi, rdi
0x14000946e  jz      short loc_1400094EE
0x140009470  cmp     [rdi+8], rbx
0x140009474  jnz     short loc_14000949B
0x140009476  mov     rcx, [rdi]
0x140009479  lea     rdx, [rsp+28h+arg_8]
0x14000947e  mov     [rsp+28h+arg_8], rbx
0x140009483  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140009488  test    eax, eax
0x14000948a  js      short loc_14000949B
0x14000948c  cmp     [rdi+8], rbx
0x140009490  jnz     short loc_14000949B
0x140009492  mov     rax, [rsp+28h+arg_8]
0x140009497  mov     [rdi+8], rax
0x14000949b  mov     rax, [rdi+8]
0x14000949f  lea     rcx, [rax+20h]
0x1400094a3  neg     rax
0x1400094a6  sbb     rdi, rdi
0x1400094a9  and     rdi, rcx
0x1400094ac  jz      short loc_1400094EE
0x1400094ae  call    cs:__imp_GetCurrentThreadId
0x1400094b4  mov     r8d, eax
0x1400094b7  mov     r9d, eax
0x1400094ba  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400094c4  shr     r8, 2
0x1400094c8  mul     r8
0x1400094cb  shr     rdx, 3
0x1400094cf  lea     rcx, [rdx+rdx*4]
0x1400094d3  add     rcx, rcx
0x1400094d6  sub     r8, rcx
0x1400094d9  mov     rbx, [rdi+r8*8+8]
0x1400094de  jmp     short loc_1400094E9
0x1400094e0  cmp     [rbx], r9d
0x1400094e3  jz      short loc_1400094FC
0x1400094e5  mov     rbx, [rbx+8]
0x1400094e9  test    rbx, rbx
0x1400094ec  jnz     short loc_1400094E0
0x1400094ee  mov     rax, rbx
0x1400094f1  mov     rbx, [rsp+28h+arg_0]
0x1400094f6  add     rsp, 20h
0x1400094fa  pop     rdi
0x1400094fb  retn
0x1400094fc  add     rbx, 10h
0x140009500  jz      short loc_1400094EE
0x140009502  cmp     qword ptr [rbx+8], 0
0x140009507  jnz     short loc_1400094EE
0x140009509  lea     rax, [rdi+4]
0x14000950d  mov     [rbx+8], rax
0x140009511  jmp     short loc_1400094EE
```
