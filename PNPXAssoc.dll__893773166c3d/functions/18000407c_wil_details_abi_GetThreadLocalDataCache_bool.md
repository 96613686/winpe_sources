# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000407c`
- end: `0x180004137`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800038a0`

## callees

- `0x18000314c`
- `0x18000407c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800040d2`
- `KERNEL32!GetCurrentThreadId` at `0x1800040d2`

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
0x18000407c  mov     [rsp+arg_0], rbx
0x180004081  push    rdi
0x180004082  sub     rsp, 20h
0x180004086  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000408d  xor     ebx, ebx
0x18000408f  test    rdi, rdi
0x180004092  jz      short loc_180004112
0x180004094  cmp     [rdi+8], rbx
0x180004098  jnz     short loc_1800040BF
0x18000409a  mov     rcx, [rdi]
0x18000409d  lea     rdx, [rsp+28h+arg_8]
0x1800040a2  mov     [rsp+28h+arg_8], rbx
0x1800040a7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800040ac  test    eax, eax
0x1800040ae  js      short loc_1800040BF
0x1800040b0  cmp     [rdi+8], rbx
0x1800040b4  jnz     short loc_1800040BF
0x1800040b6  mov     rax, [rsp+28h+arg_8]
0x1800040bb  mov     [rdi+8], rax
0x1800040bf  mov     rax, [rdi+8]
0x1800040c3  lea     rcx, [rax+20h]
0x1800040c7  neg     rax
0x1800040ca  sbb     rdi, rdi
0x1800040cd  and     rdi, rcx
0x1800040d0  jz      short loc_180004112
0x1800040d2  call    cs:__imp_GetCurrentThreadId
0x1800040d8  mov     r8d, eax
0x1800040db  mov     r9d, eax
0x1800040de  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800040e8  shr     r8, 2
0x1800040ec  mul     r8
0x1800040ef  shr     rdx, 3
0x1800040f3  lea     rcx, [rdx+rdx*4]
0x1800040f7  add     rcx, rcx
0x1800040fa  sub     r8, rcx
0x1800040fd  mov     rbx, [rdi+r8*8+8]
0x180004102  jmp     short loc_18000410D
0x180004104  cmp     [rbx], r9d
0x180004107  jz      short loc_180004120
0x180004109  mov     rbx, [rbx+8]
0x18000410d  test    rbx, rbx
0x180004110  jnz     short loc_180004104
0x180004112  mov     rax, rbx
0x180004115  mov     rbx, [rsp+28h+arg_0]
0x18000411a  add     rsp, 20h
0x18000411e  pop     rdi
0x18000411f  retn
0x180004120  add     rbx, 10h
0x180004124  jz      short loc_180004112
0x180004126  cmp     qword ptr [rbx+8], 0
0x18000412b  jnz     short loc_180004112
0x18000412d  lea     rax, [rdi+4]
0x180004131  mov     [rbx+8], rax
0x180004135  jmp     short loc_180004112
```
