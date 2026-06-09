# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1400040ac`
- end: `0x140004167`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400038d0`

## callees

- `0x1400030b0`
- `0x1400040ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004102`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004102`

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
0x1400040ac  mov     [rsp+arg_0], rbx
0x1400040b1  push    rdi
0x1400040b2  sub     rsp, 20h
0x1400040b6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1400040bd  xor     ebx, ebx
0x1400040bf  test    rdi, rdi
0x1400040c2  jz      short loc_140004142
0x1400040c4  cmp     [rdi+8], rbx
0x1400040c8  jnz     short loc_1400040EF
0x1400040ca  mov     rcx, [rdi]
0x1400040cd  lea     rdx, [rsp+28h+arg_8]
0x1400040d2  mov     [rsp+28h+arg_8], rbx
0x1400040d7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1400040dc  test    eax, eax
0x1400040de  js      short loc_1400040EF
0x1400040e0  cmp     [rdi+8], rbx
0x1400040e4  jnz     short loc_1400040EF
0x1400040e6  mov     rax, [rsp+28h+arg_8]
0x1400040eb  mov     [rdi+8], rax
0x1400040ef  mov     rax, [rdi+8]
0x1400040f3  lea     rcx, [rax+20h]
0x1400040f7  neg     rax
0x1400040fa  sbb     rdi, rdi
0x1400040fd  and     rdi, rcx
0x140004100  jz      short loc_140004142
0x140004102  call    cs:__imp_GetCurrentThreadId
0x140004108  mov     r8d, eax
0x14000410b  mov     r9d, eax
0x14000410e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004118  shr     r8, 2
0x14000411c  mul     r8
0x14000411f  shr     rdx, 3
0x140004123  lea     rcx, [rdx+rdx*4]
0x140004127  add     rcx, rcx
0x14000412a  sub     r8, rcx
0x14000412d  mov     rbx, [rdi+r8*8+8]
0x140004132  jmp     short loc_14000413D
0x140004134  cmp     [rbx], r9d
0x140004137  jz      short loc_140004150
0x140004139  mov     rbx, [rbx+8]
0x14000413d  test    rbx, rbx
0x140004140  jnz     short loc_140004134
0x140004142  mov     rax, rbx
0x140004145  mov     rbx, [rsp+28h+arg_0]
0x14000414a  add     rsp, 20h
0x14000414e  pop     rdi
0x14000414f  retn
0x140004150  add     rbx, 10h
0x140004154  jz      short loc_140004142
0x140004156  cmp     qword ptr [rbx+8], 0
0x14000415b  jnz     short loc_140004142
0x14000415d  lea     rax, [rdi+4]
0x140004161  mov     [rbx+8], rax
0x140004165  jmp     short loc_140004142
```
