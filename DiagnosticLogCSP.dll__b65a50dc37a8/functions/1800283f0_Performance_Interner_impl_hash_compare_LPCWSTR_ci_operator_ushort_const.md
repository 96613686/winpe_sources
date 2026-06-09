# Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *)

- ea: `0x1800283f0`
- end: `0x180028474`
- name: `??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_KPEBG@Z`
- size: `132`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180029af0`
- `0x18002a528`
- `0x18002a768`

## callees

- `0x1800283f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18002841c`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18002841c`

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
0x1800283f0  push    rbx
0x1800283f2  push    rbp
0x1800283f3  push    rsi
0x1800283f4  push    rdi
0x1800283f5  sub     rsp, 28h
0x1800283f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800283fd  mov     rbx, rdx
0x180028400  xor     ebp, ebp
0x180028402  inc     rax
0x180028405  cmp     [rdx+rax*2], bp
0x180028409  jnz     short loc_180028402
0x18002840b  lea     rsi, [rdx+rax*2]
0x18002840f  mov     edi, 811C9DC5h
0x180028414  cmp     rdx, rsi
0x180028417  jz      short loc_18002843E
0x180028419  movzx   ecx, word ptr [rbx]
0x18002841c  call    cs:__imp__o_towlower
0x180028423  nop     dword ptr [rax+rax+00h]
0x180028428  imul    rdi, 1000193h
0x18002842f  movzx   ecx, ax
0x180028432  add     rbx, 2
0x180028436  xor     rdi, rcx
0x180028439  cmp     rbx, rsi
0x18002843c  jnz     short loc_180028419
0x18002843e  mov     eax, 834E0B5Fh
0x180028443  imul    ecx, edi, 41A7h
0x180028449  imul    edi
0x18002844b  add     edx, edi
0x18002844d  sar     edx, 10h
0x180028450  mov     eax, edx
0x180028452  shr     eax, 1Fh
0x180028455  add     edx, eax
0x180028457  imul    eax, edx, 7FFFFFFFh
0x18002845d  sub     ecx, eax
0x18002845f  lea     eax, [rcx+7FFFFFFFh]
0x180028465  cmovns  eax, ecx
0x180028468  cdqe
0x18002846a  add     rsp, 28h
0x18002846e  pop     rdi
0x18002846f  pop     rsi
0x180028470  pop     rbp
0x180028471  pop     rbx
0x180028472  retn
```
