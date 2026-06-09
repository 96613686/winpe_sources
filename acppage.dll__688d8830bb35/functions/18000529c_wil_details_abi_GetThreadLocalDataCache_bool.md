# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000529c`
- end: `0x180005357`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004a30`

## callees

- `0x1800038a8`
- `0x18000529c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800052f2`
- `KERNEL32!GetCurrentThreadId` at `0x1800052f2`

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
0x18000529c  mov     [rsp+arg_0], rbx
0x1800052a1  push    rdi
0x1800052a2  sub     rsp, 20h
0x1800052a6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800052ad  xor     ebx, ebx
0x1800052af  test    rdi, rdi
0x1800052b2  jz      short loc_180005332
0x1800052b4  cmp     [rdi+8], rbx
0x1800052b8  jnz     short loc_1800052DF
0x1800052ba  mov     rcx, [rdi]
0x1800052bd  lea     rdx, [rsp+28h+arg_8]
0x1800052c2  mov     [rsp+28h+arg_8], rbx
0x1800052c7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800052cc  test    eax, eax
0x1800052ce  js      short loc_1800052DF
0x1800052d0  cmp     [rdi+8], rbx
0x1800052d4  jnz     short loc_1800052DF
0x1800052d6  mov     rax, [rsp+28h+arg_8]
0x1800052db  mov     [rdi+8], rax
0x1800052df  mov     rax, [rdi+8]
0x1800052e3  lea     rcx, [rax+20h]
0x1800052e7  neg     rax
0x1800052ea  sbb     rdi, rdi
0x1800052ed  and     rdi, rcx
0x1800052f0  jz      short loc_180005332
0x1800052f2  call    cs:__imp_GetCurrentThreadId
0x1800052f8  mov     r8d, eax
0x1800052fb  mov     r9d, eax
0x1800052fe  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005308  shr     r8, 2
0x18000530c  mul     r8
0x18000530f  shr     rdx, 3
0x180005313  lea     rcx, [rdx+rdx*4]
0x180005317  add     rcx, rcx
0x18000531a  sub     r8, rcx
0x18000531d  mov     rbx, [rdi+r8*8+8]
0x180005322  jmp     short loc_18000532D
0x180005324  cmp     [rbx], r9d
0x180005327  jz      short loc_180005340
0x180005329  mov     rbx, [rbx+8]
0x18000532d  test    rbx, rbx
0x180005330  jnz     short loc_180005324
0x180005332  mov     rax, rbx
0x180005335  mov     rbx, [rsp+28h+arg_0]
0x18000533a  add     rsp, 20h
0x18000533e  pop     rdi
0x18000533f  retn
0x180005340  add     rbx, 10h
0x180005344  jz      short loc_180005332
0x180005346  cmp     qword ptr [rbx+8], 0
0x18000534b  jnz     short loc_180005332
0x18000534d  lea     rax, [rdi+4]
0x180005351  mov     [rbx+8], rax
0x180005355  jmp     short loc_180005332
```
