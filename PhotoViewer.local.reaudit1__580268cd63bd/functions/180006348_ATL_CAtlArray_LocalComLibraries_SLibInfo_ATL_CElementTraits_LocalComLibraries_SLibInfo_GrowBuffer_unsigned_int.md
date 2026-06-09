# ATL::CAtlArray<LocalComLibraries::SLibInfo,ATL::CElementTraits<LocalComLibraries::SLibInfo>>::GrowBuffer(unsigned __int64)

- ea: `0x180006348`
- end: `0x180006410`
- name: `?GrowBuffer@?$CAtlArray@USLibInfo@LocalComLibraries@@V?$CElementTraits@USLibInfo@LocalComLibraries@@@ATL@@@ATL@@AEAA_N_K@Z`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002cbc0`

## callees

- `0x1800046f8`
- `0x180006348`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x1800063e1`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x1800063e1`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180006383`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800063be`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180006383`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800063be`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800063f1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800063f1`

## pseudocode

```c
char __fastcall ATL::CAtlArray<LocalComLibraries::SLibInfo,ATL::CElementTraits<LocalComLibraries::SLibInfo>>::GrowBuffer(
        __int64 a1,
        size_t a2)
{
  size_t v4; // rdx
  size_t v5; // rcx
  void *v6; // rax
  void *v7; // rax
  void *v8; // rsi
  errno_t v10; // eax

  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 <= v4 )
    return 1;
  v5 = *(int *)(a1 + 24);
  if ( !*(_QWORD *)a1 )
  {
    if ( v5 > a2 )
      a2 = v5;
    v6 = calloc(a2, 0x10u);
    *(_QWORD *)a1 = v6;
    if ( v6 )
      goto LABEL_15;
    return 0;
  }
  if ( !v5 )
  {
    v5 = v4 >> 1;
    if ( a2 - v4 > v4 >> 1 )
      v5 = a2 - v4;
  }
  if ( a2 < v4 + v5 )
    a2 = v4 + v5;
  v7 = calloc(a2, 0x10u);
  v8 = v7;
  if ( !v7 )
    return 0;
  v10 = memmove_s(v7, 16LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 16LL * *(_QWORD *)(a1 + 8));
  ATL::AtlCrtErrorCheck(v10);
  free(*(void **)a1);
  *(_QWORD *)a1 = v8;
LABEL_15:
  *(_QWORD *)(a1 + 16) = a2;
  return 1;
}

```

## disassembly

```asm
0x180006348  mov     [rsp+arg_0], rbx
0x18000634d  mov     [rsp+arg_8], rsi
0x180006352  push    rdi
0x180006353  sub     rsp, 20h
0x180006357  mov     rdi, rdx
0x18000635a  mov     rbx, rcx
0x18000635d  mov     rdx, [rcx+10h]
0x180006361  cmp     rdi, rdx
0x180006364  jbe     loc_1800063FE
0x18000636a  cmp     qword ptr [rbx], 0
0x18000636e  movsxd  rcx, dword ptr [rcx+18h]
0x180006372  jnz     short loc_180006393
0x180006374  cmp     rcx, rdi
0x180006377  mov     edx, 10h; Size
0x18000637c  cmova   rdi, rcx
0x180006380  mov     rcx, rdi; Count
0x180006383  call    cs:__imp_calloc
0x180006389  mov     [rbx], rax
0x18000638c  test    rax, rax
0x18000638f  jz      short loc_1800063CC
0x180006391  jmp     short loc_1800063FA
0x180006393  test    rcx, rcx
0x180006396  jnz     short loc_1800063AB
0x180006398  mov     rcx, rdx
0x18000639b  mov     rax, rdi
0x18000639e  shr     rcx, 1
0x1800063a1  sub     rax, rdx
0x1800063a4  cmp     rax, rcx
0x1800063a7  cmova   rcx, rax
0x1800063ab  lea     rax, [rdx+rcx]
0x1800063af  mov     edx, 10h; Size
0x1800063b4  cmp     rdi, rax
0x1800063b7  cmovb   rdi, rax
0x1800063bb  mov     rcx, rdi; Count
0x1800063be  call    cs:__imp_calloc
0x1800063c4  mov     rsi, rax
0x1800063c7  test    rax, rax
0x1800063ca  jnz     short loc_1800063D0
0x1800063cc  xor     al, al
0x1800063ce  jmp     short loc_180006400
0x1800063d0  mov     rdx, [rbx+8]
0x1800063d4  mov     rcx, rsi; Destination
0x1800063d7  mov     r8, [rbx]; Source
0x1800063da  shl     rdx, 4; DestinationSize
0x1800063de  mov     r9, rdx; SourceSize
0x1800063e1  call    cs:__imp_memmove_s
0x1800063e7  mov     ecx, eax; int
0x1800063e9  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800063ee  mov     rcx, [rbx]; Block
0x1800063f1  call    cs:__imp_free
0x1800063f7  mov     [rbx], rsi
0x1800063fa  mov     [rbx+10h], rdi
0x1800063fe  mov     al, 1
0x180006400  mov     rbx, [rsp+28h+arg_0]
0x180006405  mov     rsi, [rsp+28h+arg_8]
0x18000640a  add     rsp, 20h
0x18000640e  pop     rdi
0x18000640f  retn
```
