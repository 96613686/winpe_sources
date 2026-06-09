# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000b738`
- end: `0x18000b7f5`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b0c0`

## callees

- `0x18000ac28`
- `0x18000b738`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000b792`
- `KERNEL32!GetCurrentThreadId` at `0x18000b792`

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
0x18000b738  mov     [rsp+arg_0], rbx
0x18000b73d  push    rdi
0x18000b73e  sub     rsp, 20h
0x18000b742  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000b749  xor     ebx, ebx
0x18000b74b  test    rdi, rdi
0x18000b74e  jz      loc_18000B7E7
0x18000b754  cmp     [rdi+8], rbx
0x18000b758  jnz     short loc_18000B77F
0x18000b75a  mov     rcx, [rdi]
0x18000b75d  lea     rdx, [rsp+28h+arg_8]
0x18000b762  mov     [rsp+28h+arg_8], rbx
0x18000b767  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000b76c  test    eax, eax
0x18000b76e  js      short loc_18000B77F
0x18000b770  cmp     [rdi+8], rbx
0x18000b774  jnz     short loc_18000B77F
0x18000b776  mov     rax, [rsp+28h+arg_8]
0x18000b77b  mov     [rdi+8], rax
0x18000b77f  mov     rax, [rdi+8]
0x18000b783  lea     rcx, [rax+20h]
0x18000b787  neg     rax
0x18000b78a  sbb     rdi, rdi
0x18000b78d  and     rdi, rcx
0x18000b790  jz      short loc_18000B7E7
0x18000b792  call    cs:__imp_GetCurrentThreadId
0x18000b798  mov     r8d, eax
0x18000b79b  mov     r9d, eax
0x18000b79e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000b7a8  shr     r8, 2
0x18000b7ac  mul     r8
0x18000b7af  shr     rdx, 3
0x18000b7b3  lea     rcx, [rdx+rdx*4]
0x18000b7b7  add     rcx, rcx
0x18000b7ba  sub     r8, rcx
0x18000b7bd  mov     rbx, [rdi+r8*8+8]
0x18000b7c2  test    rbx, rbx
0x18000b7c5  jz      short loc_18000B7E7
0x18000b7c7  cmp     [rbx], r9d
0x18000b7ca  jz      short loc_18000B7D2
0x18000b7cc  mov     rbx, [rbx+8]
0x18000b7d0  jmp     short loc_18000B7C2
0x18000b7d2  add     rbx, 10h
0x18000b7d6  jz      short loc_18000B7E7
0x18000b7d8  cmp     qword ptr [rbx+8], 0
0x18000b7dd  jnz     short loc_18000B7E7
0x18000b7df  lea     rax, [rdi+4]
0x18000b7e3  mov     [rbx+8], rax
0x18000b7e7  mov     rax, rbx
0x18000b7ea  mov     rbx, [rsp+28h+arg_0]
0x18000b7ef  add     rsp, 20h
0x18000b7f3  pop     rdi
0x18000b7f4  retn
```
