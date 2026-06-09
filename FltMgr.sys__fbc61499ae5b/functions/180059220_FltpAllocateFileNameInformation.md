# FltpAllocateFileNameInformation

- ea: `0x180059220`
- end: `0x180059463`
- name: `FltpAllocateFileNameInformation`
- size: `579`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180058a30`
- `0x180058e80`
- `0x18005e010`

## callees

- `0x180024c40`
- `0x180059220`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800593c8`
- `ntoskrnl!ExAllocatePool2` at `0x1800593c8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180059321`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180059321`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180059258`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180059258`

## pseudocode

```c
__int64 __fastcall FltpAllocateFileNameInformation(__int64 a1)
{
  __int64 v2; // rsi
  unsigned __int64 v3; // rbp
  PVOID v4; // rax
  __int64 Pool2; // rdi
  int v6; // esi
  char v7; // bp
  __int16 v8; // ax
  unsigned __int64 v9; // rax
  __int64 v10; // rdi
  __int64 v11; // rax
  unsigned __int16 *v12; // rdx
  int v13; // edx
  __int64 v14; // r8
  int v15; // ecx
  _WORD *v16; // rax
  __int16 v17; // dx
  unsigned __int16 v18; // ax
  __int64 v19; // rcx
  __int64 v21; // rax
  unsigned __int16 *v22; // rax
  __int64 v23; // r9
  unsigned __int16 v24; // r9

  v2 = (unsigned int)**(unsigned __int16 **)(a1 + 112) + 210;
  if ( (unsigned int)v2 > 0x150 )
  {
    v3 = (unsigned __int64)(v2 - 273) >> 6;
    if ( (unsigned __int16)v3 >= 7u )
    {
      v7 = 0;
      Pool2 = ExAllocatePool2(256, (unsigned int)v2, 846089542);
      if ( Pool2 )
        goto LABEL_5;
      return 3221225626LL;
    }
  }
  else
  {
    LOWORD(v3) = 0;
  }
  v4 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)&qword_18003FA40[16
                                                                              * (unsigned __int64)(unsigned __int16)v3]);
  Pool2 = (__int64)v4;
  if ( !v4 )
    return 3221225626LL;
  memset(v4, 0, 0xD0u);
  v6 = (unsigned __int16)v3;
  v7 = 1;
  LODWORD(v2) = (v6 << 6) + 336;
LABEL_5:
  *(_QWORD *)(Pool2 + 8) = *(_QWORD *)(a1 + 136);
  *(_QWORD *)(Pool2 + 16) = *(_QWORD *)(a1 + 144);
  *(_DWORD *)(Pool2 + 200) = 1;
  if ( v7 )
    *(_DWORD *)(Pool2 + 72) |= 0x1000u;
  if ( (*(_DWORD *)(a1 + 40) & 0x20) != 0 )
    *(_DWORD *)(Pool2 + 72) |= 2u;
  *(_WORD *)Pool2 = -3580;
  v8 = v2;
  if ( (unsigned int)v2 > 0xFFFF )
    v8 = -1;
  *(_WORD *)(Pool2 + 2) = v8;
  *(_OWORD *)(Pool2 + 88) = 0;
  v9 = (unsigned int)v2 - 208LL;
  if ( v9 > 0xFFFE )
    LOWORD(v9) = -2;
  *(_WORD *)(Pool2 + 90) = v9;
  *(_QWORD *)(Pool2 + 96) = Pool2 + 208;
  v10 = Pool2 + 80;
  *(_WORD *)v10 = 120;
  *(_DWORD *)(v10 + 4) = (unsigned __int8)*(_DWORD *)(a1 + 108);
  RtlCopyUnicodeString((PUNICODE_STRING)(v10 + 8), *(PCUNICODE_STRING *)(a1 + 112));
  if ( *(_DWORD *)(v10 + 4) != 3 )
  {
    v11 = *(_QWORD *)(a1 + 24);
    if ( v11 )
      v12 = (unsigned __int16 *)(v11 + 112);
    else
      v12 = (unsigned __int16 *)(*(_QWORD *)(a1 + 32) + 8LL);
    v13 = *v12;
    v14 = *(_QWORD *)(v10 + 16);
    *(_WORD *)(v10 + 26) = v13;
    *(_WORD *)(v10 + 24) = v13;
    *(_QWORD *)(v10 + 32) = v14;
    v15 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 112) + 24LL);
    if ( (_WORD)v15 )
    {
      *(_WORD *)(v10 + 42) = v15;
      *(_WORD *)(v10 + 40) = v15;
      v21 = *(_QWORD *)(a1 + 24);
      if ( v21 )
        v22 = (unsigned __int16 *)(v21 + 112);
      else
        v22 = (unsigned __int16 *)(*(_QWORD *)(a1 + 32) + 8LL);
      v23 = *(unsigned __int16 *)(v10 + 8);
      *(_QWORD *)(v10 + 48) = v14 + *v22;
      if ( v13 + v15 == (_DWORD)v23 && v23 + 2 <= (unsigned __int64)*(unsigned __int16 *)(v10 + 10) )
      {
        v24 = v23 + 2;
        *(_WORD *)(v10 + 8) = v24;
        *(_WORD *)(v14 + 2 * ((unsigned __int64)v24 >> 1) - 2) = 92;
      }
    }
    v16 = *(_WORD **)(a1 + 112);
    v17 = v16[13];
    if ( v17 )
    {
      v18 = *v16 - v17;
      *(_WORD *)(v10 + 74) = v17;
      v19 = *(_QWORD *)(v10 + 16) + v18;
      *(_WORD *)(v10 + 2) |= 4u;
      *(_QWORD *)(v10 + 80) = v19;
      *(_WORD *)(v10 + 72) = v17;
    }
  }
  *(_QWORD *)(a1 + 120) = v10;
  return 0;
}

```

## disassembly

```asm
0x180059220  push    rbx
0x180059222  push    rbp
0x180059223  push    rsi
0x180059224  push    rdi
0x180059225  sub     rsp, 28h
0x180059229  mov     rax, [rcx+70h]
0x18005922d  mov     rbx, rcx
0x180059230  movzx   esi, word ptr [rax]
0x180059233  add     esi, 0D2h
0x180059239  cmp     esi, 150h
0x18005923f  ja      loc_1800593A3
0x180059245  xor     ebp, ebp
0x180059247  lea     rax, qword_18003FA40
0x18005924e  movzx   ecx, bp
0x180059251  shl     rcx, 7
0x180059255  add     rcx, rax; Lookaside
0x180059258  call    cs:__imp_ExAllocateFromPagedLookasideList
0x18005925f  nop     dword ptr [rax+rax+00h]
0x180059264  mov     rdi, rax
0x180059267  test    rax, rax
0x18005926a  jz      loc_1800593E0
0x180059270  xor     edx, edx; Val
0x180059272  mov     r8d, 0D0h; Size
0x180059278  mov     rcx, rax; void *
0x18005927b  call    memset
0x180059280  movzx   esi, bp
0x180059283  mov     bpl, 1
0x180059286  shl     esi, 6
0x180059289  add     esi, 150h
0x18005928f  mov     rax, [rbx+88h]
0x180059296  mov     [rdi+8], rax
0x18005929a  mov     rax, [rbx+90h]
0x1800592a1  mov     [rdi+10h], rax
0x1800592a5  mov     dword ptr [rdi+0C8h], 1
0x1800592af  test    bpl, bpl
0x1800592b2  jz      short loc_1800592BB
0x1800592b4  or      dword ptr [rdi+48h], 1000h
0x1800592bb  mov     eax, [rbx+28h]
0x1800592be  test    al, 20h
0x1800592c0  jz      short loc_1800592C6
0x1800592c2  or      dword ptr [rdi+48h], 2
0x1800592c6  mov     word ptr [rdi], 0F204h
0x1800592cb  mov     ecx, 0FFFFh
0x1800592d0  cmp     esi, ecx
0x1800592d2  movzx   eax, si
0x1800592d5  xorps   xmm0, xmm0
0x1800592d8  cmova   ax, cx
0x1800592dc  mov     ecx, 0FFFEh
0x1800592e1  mov     [rdi+2], ax
0x1800592e5  movups  xmmword ptr [rdi+58h], xmm0
0x1800592e9  mov     eax, esi
0x1800592eb  add     rax, 0FFFFFFFFFFFFFF30h
0x1800592f1  cmp     rax, rcx
0x1800592f4  cmova   rax, rcx
0x1800592f8  mov     [rdi+5Ah], ax
0x1800592fc  lea     rax, [rdi+0D0h]
0x180059303  mov     [rdi+60h], rax
0x180059307  add     rdi, 50h ; 'P'
0x18005930b  mov     word ptr [rdi], 78h ; 'x'
0x180059310  mov     eax, [rbx+6Ch]
0x180059313  movzx   ecx, al
0x180059316  mov     [rdi+4], ecx
0x180059319  lea     rcx, [rdi+8]; DestinationString
0x18005931d  mov     rdx, [rbx+70h]; SourceString
0x180059321  call    cs:__imp_RtlCopyUnicodeString
0x180059328  nop     dword ptr [rax+rax+00h]
0x18005932d  cmp     dword ptr [rdi+4], 3
0x180059331  jz      short loc_180059393
0x180059333  mov     rax, [rbx+18h]
0x180059337  test    rax, rax
0x18005933a  jz      loc_180059456
0x180059340  lea     rdx, [rax+70h]
0x180059344  movzx   edx, word ptr [rdx]
0x180059347  mov     r8, [rdi+10h]
0x18005934b  mov     [rdi+1Ah], dx
0x18005934f  mov     [rdi+18h], dx
0x180059353  mov     [rdi+20h], r8
0x180059357  mov     rax, [rbx+70h]
0x18005935b  movzx   ecx, word ptr [rax+18h]
0x18005935f  test    cx, cx
0x180059362  jnz     loc_1800593EF
0x180059368  mov     rax, [rbx+70h]
0x18005936c  movzx   edx, word ptr [rax+1Ah]
0x180059370  test    dx, dx
0x180059373  jz      short loc_180059393
0x180059375  movzx   eax, word ptr [rax]
0x180059378  sub     ax, dx
0x18005937b  mov     [rdi+4Ah], dx
0x18005937f  movzx   ecx, ax
0x180059382  add     rcx, [rdi+10h]
0x180059386  or      word ptr [rdi+2], 4
0x18005938b  mov     [rdi+50h], rcx
0x18005938f  mov     [rdi+48h], dx
0x180059393  mov     [rbx+78h], rdi
0x180059397  xor     eax, eax
0x180059399  add     rsp, 28h
0x18005939d  pop     rdi
0x18005939e  pop     rsi
0x18005939f  pop     rbp
0x1800593a0  pop     rbx
0x1800593a1  retn
0x1800593a3  lea     rbp, [rsi-111h]
0x1800593aa  mov     edx, esi
0x1800593ac  shr     rbp, 6
0x1800593b0  cmp     bp, 7
0x1800593b4  jb      loc_180059247
0x1800593ba  mov     ecx, 100h
0x1800593bf  mov     r8d, 326E4D46h
0x1800593c5  xor     bpl, bpl
0x1800593c8  call    cs:__imp_ExAllocatePool2
0x1800593cf  nop     dword ptr [rax+rax+00h]
0x1800593d4  mov     rdi, rax
0x1800593d7  test    rax, rax
0x1800593da  jnz     loc_18005928F
0x1800593e0  mov     eax, 0C000009Ah
0x1800593e5  add     rsp, 28h
0x1800593e9  pop     rdi
0x1800593ea  pop     rsi
0x1800593eb  pop     rbp
0x1800593ec  pop     rbx
0x1800593ed  retn
0x1800593ef  mov     [rdi+2Ah], cx
0x1800593f3  mov     [rdi+28h], cx
0x1800593f7  mov     rax, [rbx+18h]
0x1800593fb  test    rax, rax
0x1800593fe  jz      short loc_18005944C
0x180059400  add     rax, 70h ; 'p'
0x180059404  movzx   eax, word ptr [rax]
0x180059407  add     ecx, edx
0x180059409  movzx   r9d, word ptr [rdi+8]
0x18005940e  add     rax, r8
0x180059411  mov     [rdi+30h], rax
0x180059415  cmp     ecx, r9d
0x180059418  jnz     loc_180059368
0x18005941e  movzx   eax, word ptr [rdi+0Ah]
0x180059422  lea     rcx, [r9+2]
0x180059426  cmp     rcx, rax
0x180059429  ja      loc_180059368
0x18005942f  add     r9w, 2
0x180059434  movzx   eax, r9w
0x180059438  mov     [rdi+8], ax
0x18005943c  shr     rax, 1
0x18005943f  mov     word ptr [r8+rax*2-2], 5Ch ; '\'
0x180059447  jmp     loc_180059368
0x18005944c  mov     rax, [rbx+20h]
0x180059450  add     rax, 8
0x180059454  jmp     short loc_180059404
0x180059456  mov     rdx, [rbx+20h]
0x18005945a  add     rdx, 8
0x18005945e  jmp     loc_180059344
```
