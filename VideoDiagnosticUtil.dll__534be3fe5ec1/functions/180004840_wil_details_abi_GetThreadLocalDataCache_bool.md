# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004840`
- end: `0x180004906`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `198`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800041a0`

## callees

- `0x180003354`
- `0x180004840`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000489a`
- `KERNEL32!GetCurrentThreadId` at `0x18000489a`

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
0x180004840  mov     [rsp+arg_0], rbx
0x180004845  push    rdi
0x180004846  sub     rsp, 20h
0x18000484a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004851  xor     ebx, ebx
0x180004853  test    rdi, rdi
0x180004856  jz      loc_1800048E0
0x18000485c  cmp     [rdi+8], rbx
0x180004860  jnz     short loc_180004887
0x180004862  mov     rcx, [rdi]
0x180004865  lea     rdx, [rsp+28h+arg_8]
0x18000486a  mov     [rsp+28h+arg_8], rbx
0x18000486f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180004874  test    eax, eax
0x180004876  js      short loc_180004887
0x180004878  cmp     [rdi+8], rbx
0x18000487c  jnz     short loc_180004887
0x18000487e  mov     rax, [rsp+28h+arg_8]
0x180004883  mov     [rdi+8], rax
0x180004887  mov     rax, [rdi+8]
0x18000488b  lea     rcx, [rax+20h]
0x18000488f  neg     rax
0x180004892  sbb     rdi, rdi
0x180004895  and     rdi, rcx
0x180004898  jz      short loc_1800048E0
0x18000489a  call    cs:__imp_GetCurrentThreadId
0x1800048a1  nop     dword ptr [rax+rax+00h]
0x1800048a6  mov     r8d, eax
0x1800048a9  mov     r9d, eax
0x1800048ac  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800048b6  shr     r8, 2
0x1800048ba  mul     r8
0x1800048bd  shr     rdx, 3
0x1800048c1  lea     rcx, [rdx+rdx*4]
0x1800048c5  add     rcx, rcx
0x1800048c8  sub     r8, rcx
0x1800048cb  mov     rbx, [rdi+r8*8+8]
0x1800048d0  jmp     short loc_1800048DB
0x1800048d2  cmp     [rbx], r9d
0x1800048d5  jz      short loc_1800048EF
0x1800048d7  mov     rbx, [rbx+8]
0x1800048db  test    rbx, rbx
0x1800048de  jnz     short loc_1800048D2
0x1800048e0  mov     rax, rbx
0x1800048e3  mov     rbx, [rsp+28h+arg_0]
0x1800048e8  add     rsp, 20h
0x1800048ec  pop     rdi
0x1800048ed  retn
0x1800048ef  add     rbx, 10h
0x1800048f3  jz      short loc_1800048E0
0x1800048f5  cmp     qword ptr [rbx+8], 0
0x1800048fa  jnz     short loc_1800048E0
0x1800048fc  lea     rax, [rdi+4]
0x180004900  mov     [rbx+8], rax
0x180004904  jmp     short loc_1800048E0
```
