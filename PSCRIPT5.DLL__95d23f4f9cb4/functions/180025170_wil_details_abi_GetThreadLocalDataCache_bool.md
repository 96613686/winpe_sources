# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180025170`
- end: `0x18002522b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800248d0`

## callees

- `0x1800238d4`
- `0x180025170`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800251c6`
- `KERNEL32!GetCurrentThreadId` at `0x1800251c6`

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
0x180025170  mov     [rsp+arg_0], rbx
0x180025175  push    rdi
0x180025176  sub     rsp, 20h
0x18002517a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180025181  xor     ebx, ebx
0x180025183  test    rdi, rdi
0x180025186  jz      short loc_180025206
0x180025188  cmp     [rdi+8], rbx
0x18002518c  jnz     short loc_1800251B3
0x18002518e  mov     rcx, [rdi]
0x180025191  lea     rdx, [rsp+28h+arg_8]
0x180025196  mov     [rsp+28h+arg_8], rbx
0x18002519b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800251a0  test    eax, eax
0x1800251a2  js      short loc_1800251B3
0x1800251a4  cmp     [rdi+8], rbx
0x1800251a8  jnz     short loc_1800251B3
0x1800251aa  mov     rax, [rsp+28h+arg_8]
0x1800251af  mov     [rdi+8], rax
0x1800251b3  mov     rax, [rdi+8]
0x1800251b7  lea     rcx, [rax+20h]
0x1800251bb  neg     rax
0x1800251be  sbb     rdi, rdi
0x1800251c1  and     rdi, rcx
0x1800251c4  jz      short loc_180025206
0x1800251c6  call    cs:__imp_GetCurrentThreadId
0x1800251cc  mov     r8d, eax
0x1800251cf  mov     r9d, eax
0x1800251d2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800251dc  shr     r8, 2
0x1800251e0  mul     r8
0x1800251e3  shr     rdx, 3
0x1800251e7  lea     rcx, [rdx+rdx*4]
0x1800251eb  add     rcx, rcx
0x1800251ee  sub     r8, rcx
0x1800251f1  mov     rbx, [rdi+r8*8+8]
0x1800251f6  jmp     short loc_180025201
0x1800251f8  cmp     [rbx], r9d
0x1800251fb  jz      short loc_180025214
0x1800251fd  mov     rbx, [rbx+8]
0x180025201  test    rbx, rbx
0x180025204  jnz     short loc_1800251F8
0x180025206  mov     rax, rbx
0x180025209  mov     rbx, [rsp+28h+arg_0]
0x18002520e  add     rsp, 20h
0x180025212  pop     rdi
0x180025213  retn
0x180025214  add     rbx, 10h
0x180025218  jz      short loc_180025206
0x18002521a  cmp     qword ptr [rbx+8], 0
0x18002521f  jnz     short loc_180025206
0x180025221  lea     rax, [rdi+4]
0x180025225  mov     [rbx+8], rax
0x180025229  jmp     short loc_180025206
```
