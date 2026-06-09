# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x180007290`
- end: `0x18000733e`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007560`

## callees

- `0x180007290`
- `0x180007ee8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000729f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000729f`

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
0x180007290  push    rbx
0x180007292  push    rbp
0x180007293  push    rsi
0x180007294  push    rdi
0x180007295  sub     rsp, 28h
0x180007299  mov     bpl, dl
0x18000729c  mov     rdi, rcx
0x18000729f  call    cs:__imp_GetCurrentThreadId
0x1800072a5  mov     ebx, eax
0x1800072a7  mov     esi, eax
0x1800072a9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800072b3  shr     rbx, 2
0x1800072b7  mul     rbx
0x1800072ba  shr     rdx, 3
0x1800072be  lea     r8, [rdx+rdx*4]
0x1800072c2  add     r8, r8; unsigned __int64
0x1800072c5  sub     rbx, r8
0x1800072c8  mov     rax, [rdi+rbx*8]
0x1800072cc  test    rax, rax
0x1800072cf  jz      short loc_1800072E1
0x1800072d1  cmp     [rax], esi
0x1800072d3  jz      short loc_1800072DB
0x1800072d5  mov     rax, [rax+8]
0x1800072d9  jmp     short loc_1800072CC
0x1800072db  add     rax, 10h
0x1800072df  jmp     short loc_180007335
0x1800072e1  test    bpl, bpl
0x1800072e4  jz      short loc_180007333
0x1800072e6  mov     edx, 38h ; '8'; dwBytes
0x1800072eb  xor     ecx, ecx; dwFlags
0x1800072ed  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800072f2  mov     rcx, rax
0x1800072f5  test    rax, rax
0x1800072f8  jz      short loc_180007333
0x1800072fa  mov     [rax], esi
0x1800072fc  xor     eax, eax
0x1800072fe  mov     [rcx+4], eax
0x180007301  mov     [rcx+8], rax
0x180007305  mov     qword ptr [rcx+10h], 28h ; '('
0x18000730d  mov     [rcx+18h], rax
0x180007311  mov     [rcx+20h], rax
0x180007315  mov     [rcx+28h], rax
0x180007319  mov     [rcx+30h], rax
0x18000731d  mov     rax, [rdi+rbx*8]
0x180007321  mov     [rcx+8], rax
0x180007325  lock cmpxchg [rdi+rbx*8], rcx
0x18000732b  jnz     short loc_18000731D
0x18000732d  lea     rax, [rcx+10h]
0x180007331  jmp     short loc_180007335
0x180007333  xor     eax, eax
0x180007335  add     rsp, 28h
0x180007339  pop     rdi
0x18000733a  pop     rsi
0x18000733b  pop     rbp
0x18000733c  pop     rbx
0x18000733d  retn
```
