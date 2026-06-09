# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800548f0`
- end: `0x1800549b4`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `196`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180053e70`

## callees

- `0x180052fc0`
- `0x1800548f0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18005494a`
- `KERNEL32!GetCurrentThreadId` at `0x18005494a`

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
0x1800548f0  mov     [rsp+arg_0], rbx
0x1800548f5  push    rdi
0x1800548f6  sub     rsp, 20h
0x1800548fa  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180054901  xor     ebx, ebx
0x180054903  test    rdi, rdi
0x180054906  jz      loc_1800549A5
0x18005490c  cmp     [rdi+8], rbx
0x180054910  jnz     short loc_180054937
0x180054912  mov     rcx, [rdi]
0x180054915  lea     rdx, [rsp+28h+arg_8]
0x18005491a  mov     [rsp+28h+arg_8], rbx
0x18005491f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180054924  test    eax, eax
0x180054926  js      short loc_180054937
0x180054928  cmp     [rdi+8], rbx
0x18005492c  jnz     short loc_180054937
0x18005492e  mov     rax, [rsp+28h+arg_8]
0x180054933  mov     [rdi+8], rax
0x180054937  mov     rax, [rdi+8]
0x18005493b  lea     rcx, [rax+20h]
0x18005493f  neg     rax
0x180054942  sbb     rdi, rdi
0x180054945  and     rdi, rcx
0x180054948  jz      short loc_1800549A5
0x18005494a  call    cs:__imp_GetCurrentThreadId
0x180054951  nop     dword ptr [rax+rax+00h]
0x180054956  mov     r8d, eax
0x180054959  mov     r9d, eax
0x18005495c  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180054966  shr     r8, 2
0x18005496a  mul     r8
0x18005496d  shr     rdx, 3
0x180054971  lea     rcx, [rdx+rdx*4]
0x180054975  add     rcx, rcx
0x180054978  sub     r8, rcx
0x18005497b  mov     rbx, [rdi+r8*8+8]
0x180054980  test    rbx, rbx
0x180054983  jz      short loc_1800549A5
0x180054985  cmp     [rbx], r9d
0x180054988  jz      short loc_180054990
0x18005498a  mov     rbx, [rbx+8]
0x18005498e  jmp     short loc_180054980
0x180054990  add     rbx, 10h
0x180054994  jz      short loc_1800549A5
0x180054996  cmp     qword ptr [rbx+8], 0
0x18005499b  jnz     short loc_1800549A5
0x18005499d  lea     rax, [rdi+4]
0x1800549a1  mov     [rbx+8], rax
0x1800549a5  mov     rax, rbx
0x1800549a8  mov     rbx, [rsp+28h+arg_0]
0x1800549ad  add     rsp, 20h
0x1800549b1  pop     rdi
0x1800549b2  retn
```
