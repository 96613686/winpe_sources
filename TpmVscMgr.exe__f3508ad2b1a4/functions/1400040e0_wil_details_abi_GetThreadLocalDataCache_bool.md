# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1400040e0`
- end: `0x14000419b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003900`

## callees

- `0x140003258`
- `0x1400040e0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140004136`
- `KERNEL32!GetCurrentThreadId` at `0x140004136`

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
0x1400040e0  mov     [rsp+arg_0], rbx
0x1400040e5  push    rdi
0x1400040e6  sub     rsp, 20h
0x1400040ea  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1400040f1  xor     ebx, ebx
0x1400040f3  test    rdi, rdi
0x1400040f6  jz      short loc_140004176
0x1400040f8  cmp     [rdi+8], rbx
0x1400040fc  jnz     short loc_140004123
0x1400040fe  mov     rcx, [rdi]
0x140004101  lea     rdx, [rsp+28h+arg_8]
0x140004106  mov     [rsp+28h+arg_8], rbx
0x14000410b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140004110  test    eax, eax
0x140004112  js      short loc_140004123
0x140004114  cmp     [rdi+8], rbx
0x140004118  jnz     short loc_140004123
0x14000411a  mov     rax, [rsp+28h+arg_8]
0x14000411f  mov     [rdi+8], rax
0x140004123  mov     rax, [rdi+8]
0x140004127  lea     rcx, [rax+20h]
0x14000412b  neg     rax
0x14000412e  sbb     rdi, rdi
0x140004131  and     rdi, rcx
0x140004134  jz      short loc_140004176
0x140004136  call    cs:__imp_GetCurrentThreadId
0x14000413c  mov     r8d, eax
0x14000413f  mov     r9d, eax
0x140004142  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000414c  shr     r8, 2
0x140004150  mul     r8
0x140004153  shr     rdx, 3
0x140004157  lea     rcx, [rdx+rdx*4]
0x14000415b  add     rcx, rcx
0x14000415e  sub     r8, rcx
0x140004161  mov     rbx, [rdi+r8*8+8]
0x140004166  jmp     short loc_140004171
0x140004168  cmp     [rbx], r9d
0x14000416b  jz      short loc_140004184
0x14000416d  mov     rbx, [rbx+8]
0x140004171  test    rbx, rbx
0x140004174  jnz     short loc_140004168
0x140004176  mov     rax, rbx
0x140004179  mov     rbx, [rsp+28h+arg_0]
0x14000417e  add     rsp, 20h
0x140004182  pop     rdi
0x140004183  retn
0x140004184  add     rbx, 10h
0x140004188  jz      short loc_140004176
0x14000418a  cmp     qword ptr [rbx+8], 0
0x14000418f  jnz     short loc_140004176
0x140004191  lea     rax, [rdi+4]
0x140004195  mov     [rbx+8], rax
0x140004199  jmp     short loc_140004176
```
