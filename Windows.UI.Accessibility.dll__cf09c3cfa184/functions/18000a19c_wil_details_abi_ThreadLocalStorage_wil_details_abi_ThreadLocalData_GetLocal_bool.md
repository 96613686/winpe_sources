# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x18000a19c`
- end: `0x18000a24a`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a4ec`

## callees

- `0x18000a19c`
- `0x18000af64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a1ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a1ab`

## pseudocode

```c
signed __int64 __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(
        __int64 a1,
        char a2)
{
  DWORD CurrentThreadId; // esi
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // r8
  unsigned __int64 v7; // rbx
  __int64 i; // rax
  DWORD *v10; // rax
  signed __int64 v11; // rcx
  signed __int64 v12; // rax

  CurrentThreadId = GetCurrentThreadId();
  v5 = (unsigned __int64)CurrentThreadId >> 2;
  v6 = 10 * (v5 / 0xA);
  v7 = v5 % 0xA;
  for ( i = *(_QWORD *)(a1 + 8 * v7); i; i = *(_QWORD *)(i + 8) )
  {
    if ( *(_DWORD *)i == CurrentThreadId )
      return i + 16;
  }
  if ( !a2 )
    return 0;
  v10 = (DWORD *)wil::details::ProcessHeapAlloc(0, 0x38u, v6);
  v11 = (signed __int64)v10;
  if ( !v10 )
    return 0;
  *v10 = CurrentThreadId;
  v10[1] = 0;
  *((_QWORD *)v10 + 1) = 0;
  *((_QWORD *)v10 + 2) = 40;
  *((_QWORD *)v10 + 3) = 0;
  *((_QWORD *)v10 + 4) = 0;
  *((_QWORD *)v10 + 5) = 0;
  *((_QWORD *)v10 + 6) = 0;
  do
  {
    v12 = *(_QWORD *)(a1 + 8 * v7);
    *(_QWORD *)(v11 + 8) = v12;
  }
  while ( v12 != _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 8 * v7), v11, v12) );
  return v11 + 16;
}

```

## disassembly

```asm
0x18000a19c  push    rbx
0x18000a19e  push    rbp
0x18000a19f  push    rsi
0x18000a1a0  push    rdi
0x18000a1a1  sub     rsp, 28h
0x18000a1a5  mov     bpl, dl
0x18000a1a8  mov     rdi, rcx
0x18000a1ab  call    cs:__imp_GetCurrentThreadId
0x18000a1b1  mov     ebx, eax
0x18000a1b3  mov     esi, eax
0x18000a1b5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000a1bf  shr     rbx, 2
0x18000a1c3  mul     rbx
0x18000a1c6  shr     rdx, 3
0x18000a1ca  lea     r8, [rdx+rdx*4]
0x18000a1ce  add     r8, r8; unsigned __int64
0x18000a1d1  sub     rbx, r8
0x18000a1d4  mov     rax, [rdi+rbx*8]
0x18000a1d8  test    rax, rax
0x18000a1db  jz      short loc_18000A1ED
0x18000a1dd  cmp     [rax], esi
0x18000a1df  jz      short loc_18000A1E7
0x18000a1e1  mov     rax, [rax+8]
0x18000a1e5  jmp     short loc_18000A1D8
0x18000a1e7  add     rax, 10h
0x18000a1eb  jmp     short loc_18000A241
0x18000a1ed  test    bpl, bpl
0x18000a1f0  jz      short loc_18000A23F
0x18000a1f2  mov     edx, 38h ; '8'; dwBytes
0x18000a1f7  xor     ecx, ecx; dwFlags
0x18000a1f9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a1fe  mov     rcx, rax
0x18000a201  test    rax, rax
0x18000a204  jz      short loc_18000A23F
0x18000a206  mov     [rax], esi
0x18000a208  xor     eax, eax
0x18000a20a  mov     [rcx+4], eax
0x18000a20d  mov     [rcx+8], rax
0x18000a211  mov     qword ptr [rcx+10h], 28h ; '('
0x18000a219  mov     [rcx+18h], rax
0x18000a21d  mov     [rcx+20h], rax
0x18000a221  mov     [rcx+28h], rax
0x18000a225  mov     [rcx+30h], rax
0x18000a229  mov     rax, [rdi+rbx*8]
0x18000a22d  mov     [rcx+8], rax
0x18000a231  lock cmpxchg [rdi+rbx*8], rcx
0x18000a237  jnz     short loc_18000A229
0x18000a239  lea     rax, [rcx+10h]
0x18000a23d  jmp     short loc_18000A241
0x18000a23f  xor     eax, eax
0x18000a241  add     rsp, 28h
0x18000a245  pop     rdi
0x18000a246  pop     rsi
0x18000a247  pop     rbp
0x18000a248  pop     rbx
0x18000a249  retn
```
