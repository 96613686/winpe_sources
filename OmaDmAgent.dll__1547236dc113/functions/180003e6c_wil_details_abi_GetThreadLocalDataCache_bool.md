# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180003e6c`
- end: `0x180003f30`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `196`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800037b0`

## callees

- `0x180002e64`
- `0x180003e6c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180003ec6`
- `KERNEL32!GetCurrentThreadId` at `0x180003ec6`

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
0x180003e6c  mov     [rsp+arg_0], rbx
0x180003e71  push    rdi
0x180003e72  sub     rsp, 20h
0x180003e76  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180003e7d  xor     ebx, ebx
0x180003e7f  test    rdi, rdi
0x180003e82  jz      loc_180003F21
0x180003e88  cmp     [rdi+8], rbx
0x180003e8c  jnz     short loc_180003EB3
0x180003e8e  mov     rcx, [rdi]
0x180003e91  lea     rdx, [rsp+28h+arg_8]
0x180003e96  mov     [rsp+28h+arg_8], rbx
0x180003e9b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180003ea0  test    eax, eax
0x180003ea2  js      short loc_180003EB3
0x180003ea4  cmp     [rdi+8], rbx
0x180003ea8  jnz     short loc_180003EB3
0x180003eaa  mov     rax, [rsp+28h+arg_8]
0x180003eaf  mov     [rdi+8], rax
0x180003eb3  mov     rax, [rdi+8]
0x180003eb7  lea     rcx, [rax+20h]
0x180003ebb  neg     rax
0x180003ebe  sbb     rdi, rdi
0x180003ec1  and     rdi, rcx
0x180003ec4  jz      short loc_180003F21
0x180003ec6  call    cs:__imp_GetCurrentThreadId
0x180003ecd  nop     dword ptr [rax+rax+00h]
0x180003ed2  mov     r8d, eax
0x180003ed5  mov     r9d, eax
0x180003ed8  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003ee2  shr     r8, 2
0x180003ee6  mul     r8
0x180003ee9  shr     rdx, 3
0x180003eed  lea     rcx, [rdx+rdx*4]
0x180003ef1  add     rcx, rcx
0x180003ef4  sub     r8, rcx
0x180003ef7  mov     rbx, [rdi+r8*8+8]
0x180003efc  test    rbx, rbx
0x180003eff  jz      short loc_180003F21
0x180003f01  cmp     [rbx], r9d
0x180003f04  jz      short loc_180003F0C
0x180003f06  mov     rbx, [rbx+8]
0x180003f0a  jmp     short loc_180003EFC
0x180003f0c  add     rbx, 10h
0x180003f10  jz      short loc_180003F21
0x180003f12  cmp     qword ptr [rbx+8], 0
0x180003f17  jnz     short loc_180003F21
0x180003f19  lea     rax, [rdi+4]
0x180003f1d  mov     [rbx+8], rax
0x180003f21  mov     rax, rbx
0x180003f24  mov     rbx, [rsp+28h+arg_0]
0x180003f29  add     rsp, 20h
0x180003f2d  pop     rdi
0x180003f2e  retn
```
