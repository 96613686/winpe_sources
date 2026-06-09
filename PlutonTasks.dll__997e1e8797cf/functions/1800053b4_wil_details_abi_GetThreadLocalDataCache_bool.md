# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800053b4`
- end: `0x180005471`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004cc0`

## callees

- `0x180003d18`
- `0x1800053b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000540e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000540e`

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
0x1800053b4  mov     [rsp+arg_0], rbx
0x1800053b9  push    rdi
0x1800053ba  sub     rsp, 20h
0x1800053be  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800053c5  xor     ebx, ebx
0x1800053c7  test    rdi, rdi
0x1800053ca  jz      loc_180005463
0x1800053d0  cmp     [rdi+8], rbx
0x1800053d4  jnz     short loc_1800053FB
0x1800053d6  mov     rcx, [rdi]
0x1800053d9  lea     rdx, [rsp+28h+arg_8]
0x1800053de  mov     [rsp+28h+arg_8], rbx
0x1800053e3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800053e8  test    eax, eax
0x1800053ea  js      short loc_1800053FB
0x1800053ec  cmp     [rdi+8], rbx
0x1800053f0  jnz     short loc_1800053FB
0x1800053f2  mov     rax, [rsp+28h+arg_8]
0x1800053f7  mov     [rdi+8], rax
0x1800053fb  mov     rax, [rdi+8]
0x1800053ff  lea     rcx, [rax+20h]
0x180005403  neg     rax
0x180005406  sbb     rdi, rdi
0x180005409  and     rdi, rcx
0x18000540c  jz      short loc_180005463
0x18000540e  call    cs:__imp_GetCurrentThreadId
0x180005414  mov     r8d, eax
0x180005417  mov     r9d, eax
0x18000541a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005424  shr     r8, 2
0x180005428  mul     r8
0x18000542b  shr     rdx, 3
0x18000542f  lea     rcx, [rdx+rdx*4]
0x180005433  add     rcx, rcx
0x180005436  sub     r8, rcx
0x180005439  mov     rbx, [rdi+r8*8+8]
0x18000543e  test    rbx, rbx
0x180005441  jz      short loc_180005463
0x180005443  cmp     [rbx], r9d
0x180005446  jz      short loc_18000544E
0x180005448  mov     rbx, [rbx+8]
0x18000544c  jmp     short loc_18000543E
0x18000544e  add     rbx, 10h
0x180005452  jz      short loc_180005463
0x180005454  cmp     qword ptr [rbx+8], 0
0x180005459  jnz     short loc_180005463
0x18000545b  lea     rax, [rdi+4]
0x18000545f  mov     [rbx+8], rax
0x180005463  mov     rax, rbx
0x180005466  mov     rbx, [rsp+28h+arg_0]
0x18000546b  add     rsp, 20h
0x18000546f  pop     rdi
0x180005470  retn
```
