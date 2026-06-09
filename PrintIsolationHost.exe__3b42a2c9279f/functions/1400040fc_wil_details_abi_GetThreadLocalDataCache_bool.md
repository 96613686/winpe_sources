# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1400040fc`
- end: `0x1400041b7`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003920`

## callees

- `0x14000323c`
- `0x1400040fc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140004152`
- `KERNEL32!GetCurrentThreadId` at `0x140004152`

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
0x1400040fc  mov     [rsp+arg_0], rbx
0x140004101  push    rdi
0x140004102  sub     rsp, 20h
0x140004106  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x14000410d  xor     ebx, ebx
0x14000410f  test    rdi, rdi
0x140004112  jz      short loc_140004192
0x140004114  cmp     [rdi+8], rbx
0x140004118  jnz     short loc_14000413F
0x14000411a  mov     rcx, [rdi]
0x14000411d  lea     rdx, [rsp+28h+arg_8]
0x140004122  mov     [rsp+28h+arg_8], rbx
0x140004127  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x14000412c  test    eax, eax
0x14000412e  js      short loc_14000413F
0x140004130  cmp     [rdi+8], rbx
0x140004134  jnz     short loc_14000413F
0x140004136  mov     rax, [rsp+28h+arg_8]
0x14000413b  mov     [rdi+8], rax
0x14000413f  mov     rax, [rdi+8]
0x140004143  lea     rcx, [rax+20h]
0x140004147  neg     rax
0x14000414a  sbb     rdi, rdi
0x14000414d  and     rdi, rcx
0x140004150  jz      short loc_140004192
0x140004152  call    cs:__imp_GetCurrentThreadId
0x140004158  mov     r8d, eax
0x14000415b  mov     r9d, eax
0x14000415e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004168  shr     r8, 2
0x14000416c  mul     r8
0x14000416f  shr     rdx, 3
0x140004173  lea     rcx, [rdx+rdx*4]
0x140004177  add     rcx, rcx
0x14000417a  sub     r8, rcx
0x14000417d  mov     rbx, [rdi+r8*8+8]
0x140004182  jmp     short loc_14000418D
0x140004184  cmp     [rbx], r9d
0x140004187  jz      short loc_1400041A0
0x140004189  mov     rbx, [rbx+8]
0x14000418d  test    rbx, rbx
0x140004190  jnz     short loc_140004184
0x140004192  mov     rax, rbx
0x140004195  mov     rbx, [rsp+28h+arg_0]
0x14000419a  add     rsp, 20h
0x14000419e  pop     rdi
0x14000419f  retn
0x1400041a0  add     rbx, 10h
0x1400041a4  jz      short loc_140004192
0x1400041a6  cmp     qword ptr [rbx+8], 0
0x1400041ab  jnz     short loc_140004192
0x1400041ad  lea     rax, [rdi+4]
0x1400041b1  mov     [rbx+8], rax
0x1400041b5  jmp     short loc_140004192
```
