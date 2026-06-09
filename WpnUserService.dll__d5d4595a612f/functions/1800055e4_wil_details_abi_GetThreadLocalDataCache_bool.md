# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800055e4`
- end: `0x18000569f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004d60`

## callees

- `0x1800045b8`
- `0x1800055e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000563a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000563a`

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
0x1800055e4  mov     [rsp+arg_0], rbx
0x1800055e9  push    rdi
0x1800055ea  sub     rsp, 20h
0x1800055ee  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800055f5  xor     ebx, ebx
0x1800055f7  test    rdi, rdi
0x1800055fa  jz      short loc_18000567A
0x1800055fc  cmp     [rdi+8], rbx
0x180005600  jnz     short loc_180005627
0x180005602  mov     rcx, [rdi]
0x180005605  lea     rdx, [rsp+28h+arg_8]
0x18000560a  mov     [rsp+28h+arg_8], rbx
0x18000560f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180005614  test    eax, eax
0x180005616  js      short loc_180005627
0x180005618  cmp     [rdi+8], rbx
0x18000561c  jnz     short loc_180005627
0x18000561e  mov     rax, [rsp+28h+arg_8]
0x180005623  mov     [rdi+8], rax
0x180005627  mov     rax, [rdi+8]
0x18000562b  lea     rcx, [rax+20h]
0x18000562f  neg     rax
0x180005632  sbb     rdi, rdi
0x180005635  and     rdi, rcx
0x180005638  jz      short loc_18000567A
0x18000563a  call    cs:__imp_GetCurrentThreadId
0x180005640  mov     r8d, eax
0x180005643  mov     r9d, eax
0x180005646  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005650  shr     r8, 2
0x180005654  mul     r8
0x180005657  shr     rdx, 3
0x18000565b  lea     rcx, [rdx+rdx*4]
0x18000565f  add     rcx, rcx
0x180005662  sub     r8, rcx
0x180005665  mov     rbx, [rdi+r8*8+8]
0x18000566a  jmp     short loc_180005675
0x18000566c  cmp     [rbx], r9d
0x18000566f  jz      short loc_180005688
0x180005671  mov     rbx, [rbx+8]
0x180005675  test    rbx, rbx
0x180005678  jnz     short loc_18000566C
0x18000567a  mov     rax, rbx
0x18000567d  mov     rbx, [rsp+28h+arg_0]
0x180005682  add     rsp, 20h
0x180005686  pop     rdi
0x180005687  retn
0x180005688  add     rbx, 10h
0x18000568c  jz      short loc_18000567A
0x18000568e  cmp     qword ptr [rbx+8], 0
0x180005693  jnz     short loc_18000567A
0x180005695  lea     rax, [rdi+4]
0x180005699  mov     [rbx+8], rax
0x18000569d  jmp     short loc_18000567A
```
