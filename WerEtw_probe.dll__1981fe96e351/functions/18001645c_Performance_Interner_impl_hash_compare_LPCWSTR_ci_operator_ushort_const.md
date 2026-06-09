# Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *)

- ea: `0x18001645c`
- end: `0x1800164d9`
- name: `??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_KPEBG@Z`
- size: `125`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180017afc`
- `0x180018550`
- `0x18001877c`

## callees

- `0x18001645c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180016488`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180016488`

## pseudocode

```c
__int64 __fastcall Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(__int64 a1, unsigned __int16 *a2)
{
  __int64 v2; // rax
  unsigned __int16 *v3; // rbx
  unsigned __int16 *v4; // rsi
  int v5; // edi
  unsigned __int16 v6; // ax
  int v7; // ecx
  __int64 result; // rax

  v2 = -1;
  v3 = a2;
  do
    ++v2;
  while ( a2[v2] );
  v4 = &a2[v2];
  v5 = -2128831035;
  if ( a2 != v4 )
  {
    do
    {
      v6 = _o_towlower(*v3++);
      v5 = v6 ^ (16777619 * v5);
    }
    while ( v3 != v4 );
  }
  v7 = 16807 * v5 - 0x7FFFFFFF * (v5 / 127773);
  LODWORD(result) = v7 + 0x7FFFFFFF;
  if ( v7 >= 0 )
    LODWORD(result) = 16807 * v5 - 0x7FFFFFFF * (v5 / 127773);
  return (int)result;
}

```

## disassembly

```asm
0x18001645c  push    rbx
0x18001645e  push    rbp
0x18001645f  push    rsi
0x180016460  push    rdi
0x180016461  sub     rsp, 28h
0x180016465  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016469  mov     rbx, rdx
0x18001646c  xor     ebp, ebp
0x18001646e  inc     rax
0x180016471  cmp     [rdx+rax*2], bp
0x180016475  jnz     short loc_18001646E
0x180016477  lea     rsi, [rdx+rax*2]
0x18001647b  mov     edi, 811C9DC5h
0x180016480  cmp     rdx, rsi
0x180016483  jz      short loc_1800164A4
0x180016485  movzx   ecx, word ptr [rbx]
0x180016488  call    cs:__imp__o_towlower
0x18001648e  imul    rdi, 1000193h
0x180016495  movzx   ecx, ax
0x180016498  add     rbx, 2
0x18001649c  xor     rdi, rcx
0x18001649f  cmp     rbx, rsi
0x1800164a2  jnz     short loc_180016485
0x1800164a4  mov     eax, 834E0B5Fh
0x1800164a9  imul    ecx, edi, 41A7h
0x1800164af  imul    edi
0x1800164b1  add     edx, edi
0x1800164b3  sar     edx, 10h
0x1800164b6  mov     eax, edx
0x1800164b8  shr     eax, 1Fh
0x1800164bb  add     edx, eax
0x1800164bd  imul    eax, edx, 7FFFFFFFh
0x1800164c3  sub     ecx, eax
0x1800164c5  lea     eax, [rcx+7FFFFFFFh]
0x1800164cb  cmovns  eax, ecx
0x1800164ce  cdqe
0x1800164d0  add     rsp, 28h
0x1800164d4  pop     rdi
0x1800164d5  pop     rsi
0x1800164d6  pop     rbp
0x1800164d7  pop     rbx
0x1800164d8  retn
```
