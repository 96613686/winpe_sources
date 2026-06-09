# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800072ac`
- end: `0x180007369`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006b60`

## callees

- `0x180006198`
- `0x1800072ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007306`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007306`

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
0x1800072ac  mov     [rsp+arg_0], rbx
0x1800072b1  push    rdi
0x1800072b2  sub     rsp, 20h
0x1800072b6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800072bd  xor     ebx, ebx
0x1800072bf  test    rdi, rdi
0x1800072c2  jz      loc_18000735B
0x1800072c8  cmp     [rdi+8], rbx
0x1800072cc  jnz     short loc_1800072F3
0x1800072ce  mov     rcx, [rdi]
0x1800072d1  lea     rdx, [rsp+28h+arg_8]
0x1800072d6  mov     [rsp+28h+arg_8], rbx
0x1800072db  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800072e0  test    eax, eax
0x1800072e2  js      short loc_1800072F3
0x1800072e4  cmp     [rdi+8], rbx
0x1800072e8  jnz     short loc_1800072F3
0x1800072ea  mov     rax, [rsp+28h+arg_8]
0x1800072ef  mov     [rdi+8], rax
0x1800072f3  mov     rax, [rdi+8]
0x1800072f7  lea     rcx, [rax+20h]
0x1800072fb  neg     rax
0x1800072fe  sbb     rdi, rdi
0x180007301  and     rdi, rcx
0x180007304  jz      short loc_18000735B
0x180007306  call    cs:__imp_GetCurrentThreadId
0x18000730c  mov     r8d, eax
0x18000730f  mov     r9d, eax
0x180007312  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000731c  shr     r8, 2
0x180007320  mul     r8
0x180007323  shr     rdx, 3
0x180007327  lea     rcx, [rdx+rdx*4]
0x18000732b  add     rcx, rcx
0x18000732e  sub     r8, rcx
0x180007331  mov     rbx, [rdi+r8*8+8]
0x180007336  test    rbx, rbx
0x180007339  jz      short loc_18000735B
0x18000733b  cmp     [rbx], r9d
0x18000733e  jz      short loc_180007346
0x180007340  mov     rbx, [rbx+8]
0x180007344  jmp     short loc_180007336
0x180007346  add     rbx, 10h
0x18000734a  jz      short loc_18000735B
0x18000734c  cmp     qword ptr [rbx+8], 0
0x180007351  jnz     short loc_18000735B
0x180007353  lea     rax, [rdi+4]
0x180007357  mov     [rbx+8], rax
0x18000735b  mov     rax, rbx
0x18000735e  mov     rbx, [rsp+28h+arg_0]
0x180007363  add     rsp, 20h
0x180007367  pop     rdi
0x180007368  retn
```
