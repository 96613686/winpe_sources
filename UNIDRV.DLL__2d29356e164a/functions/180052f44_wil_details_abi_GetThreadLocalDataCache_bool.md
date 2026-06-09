# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180052f44`
- end: `0x180053001`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180052520`

## callees

- `0x180051770`
- `0x180052f44`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180052f9e`
- `KERNEL32!GetCurrentThreadId` at `0x180052f9e`

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
0x180052f44  mov     [rsp+arg_0], rbx
0x180052f49  push    rdi
0x180052f4a  sub     rsp, 20h
0x180052f4e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180052f55  xor     ebx, ebx
0x180052f57  test    rdi, rdi
0x180052f5a  jz      loc_180052FF3
0x180052f60  cmp     [rdi+8], rbx
0x180052f64  jnz     short loc_180052F8B
0x180052f66  mov     rcx, [rdi]
0x180052f69  lea     rdx, [rsp+28h+arg_8]
0x180052f6e  mov     [rsp+28h+arg_8], rbx
0x180052f73  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180052f78  test    eax, eax
0x180052f7a  js      short loc_180052F8B
0x180052f7c  cmp     [rdi+8], rbx
0x180052f80  jnz     short loc_180052F8B
0x180052f82  mov     rax, [rsp+28h+arg_8]
0x180052f87  mov     [rdi+8], rax
0x180052f8b  mov     rax, [rdi+8]
0x180052f8f  lea     rcx, [rax+20h]
0x180052f93  neg     rax
0x180052f96  sbb     rdi, rdi
0x180052f99  and     rdi, rcx
0x180052f9c  jz      short loc_180052FF3
0x180052f9e  call    cs:__imp_GetCurrentThreadId
0x180052fa4  mov     r8d, eax
0x180052fa7  mov     r9d, eax
0x180052faa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180052fb4  shr     r8, 2
0x180052fb8  mul     r8
0x180052fbb  shr     rdx, 3
0x180052fbf  lea     rcx, [rdx+rdx*4]
0x180052fc3  add     rcx, rcx
0x180052fc6  sub     r8, rcx
0x180052fc9  mov     rbx, [rdi+r8*8+8]
0x180052fce  test    rbx, rbx
0x180052fd1  jz      short loc_180052FF3
0x180052fd3  cmp     [rbx], r9d
0x180052fd6  jz      short loc_180052FDE
0x180052fd8  mov     rbx, [rbx+8]
0x180052fdc  jmp     short loc_180052FCE
0x180052fde  add     rbx, 10h
0x180052fe2  jz      short loc_180052FF3
0x180052fe4  cmp     qword ptr [rbx+8], 0
0x180052fe9  jnz     short loc_180052FF3
0x180052feb  lea     rax, [rdi+4]
0x180052fef  mov     [rbx+8], rax
0x180052ff3  mov     rax, rbx
0x180052ff6  mov     rbx, [rsp+28h+arg_0]
0x180052ffb  add     rsp, 20h
0x180052fff  pop     rdi
0x180053000  retn
```
