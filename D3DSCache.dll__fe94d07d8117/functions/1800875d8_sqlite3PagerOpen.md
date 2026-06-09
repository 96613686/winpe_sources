# sqlite3PagerOpen

- ea: `0x1800875d8`
- end: `0x180087b4c`
- name: `sqlite3PagerOpen`
- size: `1396`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800379c8`

## callees

- `0x180012470`
- `0x180020d70`
- `0x1800283fc`
- `0x18002b81c`
- `0x180032e10`
- `0x180035b00`
- `0x1800396b0`
- `0x18003a860`
- `0x180041688`
- `0x180042bb0`
- `0x180045374`
- `0x180070510`
- `0x1800762e0`
- `0x180076450`
- `0x180086b70`
- `0x1800875d8`
- `0x180087df0`
- `0x180087f90`
- `0x180088940`
- `0x1800a6d08`
- `0x1800a8010`

## string_xrefs

- `0x180087759`: `cannot open file`

## pseudocode

```c
__int64 __fastcall sqlite3PagerOpen(__int64 a1, __int64 *a2, _BYTE *a3, __int64 a4, char a5, int a6, int a7)
{
  const void *v7; // rsi
  unsigned int v8; // r14d
  _BYTE *v9; // rbp
  int v11; // eax
  int v12; // ebx
  bool v13; // zf
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  int v17; // r15d
  unsigned int v18; // edi
  unsigned int v19; // ebx
  _BYTE *v20; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // r8
  _BYTE *v26; // r12
  _BYTE *i; // rbx
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rax
  _BYTE *v31; // rcx
  __int64 v32; // rax
  __int64 v33; // r14
  __int64 v34; // rax
  size_t v35; // rbx
  int v36; // r12d
  unsigned __int64 v37; // rax
  unsigned __int64 v38; // rcx
  char *v39; // rax
  char *v40; // rbx
  char *v41; // rbx
  char *v42; // rbx
  __int64 v43; // r8
  __int64 v44; // rdx
  __int16 v45; // bx
  unsigned int v46; // ecx
  char v47; // bp
  __int64 v48; // rsi
  int v49; // r13d
  __int64 (__fastcall *v50)(); // rdi
  unsigned int v51; // ebx
  char v52; // bl
  int v53; // ebx
  int v54; // [rsp+30h] [rbp-58h]
  signed int v55; // [rsp+30h] [rbp-58h]
  char *v56; // [rsp+30h] [rbp-58h]
  size_t v57; // [rsp+38h] [rbp-50h]
  void *Src; // [rsp+40h] [rbp-48h]
  size_t Size; // [rsp+48h] [rbp-40h]
  unsigned int v60; // [rsp+90h] [rbp+8h] BYREF
  __int64 *v61; // [rsp+98h] [rbp+10h]
  unsigned int v62; // [rsp+A8h] [rbp+20h] BYREF

  v61 = a2;
  v7 = 0;
  v62 = 4096;
  v8 = 0;
  a7 = 0;
  v9 = a3;
  v60 = 0;
  v11 = 80;
  v12 = 1;
  if ( *(int *)(a1 + 4) > 80 )
    v11 = *(_DWORD *)(a1 + 4);
  v13 = (a5 & 2) == 0;
  v54 = v11;
  *a2 = 0;
  if ( !v13 )
  {
    a7 = 1;
    if ( a3 )
    {
      if ( *a3 )
      {
        v14 = sqlite3DbStrDup(0, a3);
        v7 = (const void *)v14;
        if ( !v14 )
          return 7;
        v8 = sqlite3Strlen30(v14, v15, v16);
        v60 = v8;
        v9 = 0;
      }
    }
  }
  v17 = a6;
  v18 = 0;
  Src = 0;
  if ( v9 && *v9 )
  {
    v19 = *(_DWORD *)(a1 + 8) + 1;
    v20 = (_BYTE *)sqlite3Malloc((int)(2 * v19));
    v7 = v20;
    if ( !v20 )
      return 7;
    *v20 = 0;
    v18 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, _BYTE *))(a1 + 64))(a1, v9, v19, v20);
    if ( v18 == 512 )
      v18 = (v17 & 0x1000000) != 0 ? 0x60E : 0;
    v60 = sqlite3Strlen30(v7, v22, v23);
    v8 = v60;
    v26 = &v9[(int)sqlite3Strlen30(v9, v24, v25) + 1];
    Src = v26;
    for ( i = v26; *i; i = &v31[v30 + 1] )
    {
      v28 = -1;
      do
        ++v28;
      while ( i[v28] );
      v29 = v28 + 1;
      v30 = -1;
      v31 = &i[v29];
      do
        ++v30;
      while ( v31[v30] );
    }
    if ( v18 )
      goto LABEL_25;
    v12 = (_DWORD)i - (_DWORD)v26 + 1;
    if ( (signed int)(v8 + 8) > *(_DWORD *)(a1 + 8) )
    {
      v18 = sqlite3ReportError(14, 61897, "cannot open file");
      if ( v18 )
        goto LABEL_25;
    }
  }
  v55 = (v54 + 7) & 0xFFFFFFF8;
  Size = v12;
  v57 = (int)v8;
  v32 = sqlite3MallocZero(
          (int)v8
        + 2 * ((int)v8 + 211LL)
        + ((*(int *)(a1 + 4) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL)
        + v12
        + (__int64)(2 * v55));
  v33 = v32;
  if ( !v32 )
  {
    v18 = 7;
LABEL_25:
    sqlite3DbFree(0, v7);
    return v18;
  }
  v34 = v32 + 312;
  v35 = (int)v60;
  v36 = 0;
  *(_QWORD *)(v33 + 288) = v34;
  *(_QWORD *)(v33 + 72) = v34 + 80;
  v37 = v34 + 80 + ((*(int *)(a1 + 4) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL);
  *(_QWORD *)(v33 + 88) = v37;
  v38 = v55 + v37;
  *(_QWORD *)(v33 + 80) = v38;
  v39 = (char *)(v38 + v55 + 12LL);
  *(_QWORD *)(v55 + v38) = v33;
  v56 = v39;
  *(_QWORD *)(v33 + 216) = v39;
  if ( (int)v35 > 0 )
  {
    memcpy_0(v39, v7, v35);
    v40 = &v56[(int)v35 + 1];
    if ( Src )
    {
      memcpy_0(v40, Src, Size);
      v41 = &v40[Size];
    }
    else
    {
      v41 = v40 + 1;
    }
    *(_QWORD *)(v33 + 224) = v41;
    memcpy_0(v41, v7, v57);
    *(_QWORD *)&v41[v57] = 0x6C616E72756F6A2DLL;
    v42 = &v41[v57 + 9];
    *(_QWORD *)(v33 + 304) = v42;
    memcpy_0(v42, v7, v57);
    *(_DWORD *)&v42[v57] = 1818326829;
    goto LABEL_32;
  }
  *(_QWORD *)(v33 + 224) = 0;
  *(_QWORD *)(v33 + 304) = 0;
  if ( (_DWORD)v35 )
LABEL_32:
    sqlite3DbFree(0, v7);
  *(_QWORD *)v33 = a1;
  *(_DWORD *)(v33 + 180) = v17;
  if ( !v9 || !*v9 )
    goto LABEL_44;
  v43 = *(_QWORD *)(v33 + 72);
  v44 = *(_QWORD *)(v33 + 216);
  v60 = 0;
  v18 = sqlite3OsOpen(a1, v44, v43, v17, (__int64)&v60);
  v17 = v60 & 1;
  v36 = (v60 >> 7) & 1;
  *(_BYTE *)(v33 + 20) = (v60 & 0x80) != 0;
  if ( !v18 )
  {
    v45 = sqlite3OsDeviceCharacteristics(*(_QWORD *)(v33 + 72));
    if ( !v17 )
    {
      setSectorSize(v33);
      v46 = *(_DWORD *)(v33 + 184);
      if ( v62 < v46 )
      {
        if ( v46 > 0x2000 )
          v46 = 0x2000;
        v62 = v46;
      }
    }
    *(_BYTE *)(v33 + 17) = sqlite3_uri_boolean(*(_QWORD *)(v33 + 216), "nolock", 0);
    if ( (v45 & 0x2000) != 0 || (unsigned int)sqlite3_uri_boolean(*(_QWORD *)(v33 + 216), "immutable", 0) )
    {
      LOBYTE(v17) = 1;
LABEL_44:
      *(_WORD *)(v33 + 21) = 1025;
      LOBYTE(v17) = v17 & 1;
      *(_BYTE *)(v33 + 17) = 1;
      v47 = 1;
      goto LABEL_45;
    }
  }
  v47 = 0;
LABEL_45:
  if ( v18 )
    goto LABEL_57;
  v18 = sqlite3PagerSetPagesize(v33, &v62, 0xFFFFFFFFLL);
  if ( v18 )
    goto LABEL_57;
  v48 = *(_QWORD *)(v33 + 288);
  v49 = a7;
  v50 = 0;
  v51 = v62;
  if ( !a7 )
    v50 = pagerStress;
  memset_0(*(void **)(v33 + 288), 0, 0x50u);
  *(_DWORD *)(v48 + 44) = 136;
  *(_DWORD *)(v48 + 40) = 1;
  *(_DWORD *)(v48 + 36) = 1;
  *(_BYTE *)(v48 + 48) = v49 ^ 1;
  *(_BYTE *)(v48 + 49) = 2;
  *(_QWORD *)(v48 + 56) = v50;
  *(_QWORD *)(v48 + 64) = v33;
  *(_DWORD *)(v48 + 32) = 100;
  v18 = sqlite3PcacheSetPageSize(v48, v51);
  if ( v18 )
  {
LABEL_57:
    sqlite3OsClose(*(_QWORD *)(v33 + 72));
    pcache1Free(*(_QWORD *)(v33 + 280));
    sqlite3_free(v33);
    return v18;
  }
  v52 = ~a5;
  *(_DWORD *)(v33 + 188) = -2;
  v53 = v52 & 1;
  *(_BYTE *)(v33 + 16) = v47;
  *(_BYTE *)(v33 + 10) = v53;
  *(_BYTE *)(v33 + 8) = v47;
  *(_BYTE *)(v33 + 23) = v47;
  *(_BYTE *)(v33 + 19) = v49;
  *(_BYTE *)(v33 + 18) = v17;
  sqlite3PagerSetFlags(v33, 35);
  *(_WORD *)(v33 + 176) = 136;
  *(_QWORD *)(v33 + 208) = -1;
  setSectorSize(v33);
  if ( v53 )
  {
    if ( v49 || v36 )
      *(_BYTE *)(v33 + 9) = 4;
  }
  else
  {
    *(_BYTE *)(v33 + 9) = 2;
  }
  *(_QWORD *)(v33 + 264) = pageReinit;
  setGetterMethod(v33);
  *v61 = v33;
  return 0;
}

```

## disassembly

```asm
0x1800875d8  mov     r11, rsp
0x1800875db  mov     [r11+18h], rbx
0x1800875df  mov     [r11+20h], r9d
0x1800875e3  mov     [r11+10h], rdx
0x1800875e7  push    rbp
0x1800875e8  push    rsi
0x1800875e9  push    rdi
0x1800875ea  push    r12
0x1800875ec  push    r13
0x1800875ee  push    r14
0x1800875f0  push    r15
0x1800875f2  sub     rsp, 50h
0x1800875f6  xor     esi, esi
0x1800875f8  mov     dword ptr [r11+20h], 1000h
0x180087600  xor     eax, eax
0x180087602  xor     r14d, r14d
0x180087605  mov     [rsp+88h+arg_30], eax
0x18008760c  mov     rbp, r8
0x18008760f  mov     r13, rcx
0x180087612  mov     [rsp+88h+arg_0], r14d
0x18008761a  lea     eax, [rsi+50h]
0x18008761d  cmp     [rcx+4], eax
0x180087620  lea     ebx, [rsi+1]
0x180087623  cmovg   eax, [rcx+4]
0x180087627  test    [rsp+88h+arg_20], 2
0x18008762f  mov     dword ptr [rsp+88h+var_58], eax
0x180087633  mov     [rdx], rsi
0x180087636  jz      short loc_18008766F
0x180087638  mov     [rsp+88h+arg_30], ebx
0x18008763f  test    r8, r8
0x180087642  jz      short loc_18008766F
0x180087644  cmp     [r8], sil
0x180087647  jz      short loc_18008766F
0x180087649  mov     rdx, r8
0x18008764c  xor     ecx, ecx
0x18008764e  call    sqlite3DbStrDup
0x180087653  mov     rsi, rax
0x180087656  test    rax, rax
0x180087659  jz      short loc_1800876AA
0x18008765b  mov     rcx, rax
0x18008765e  call    sqlite3Strlen30
0x180087663  mov     r14d, eax
0x180087666  mov     [rsp+88h+arg_0], eax
0x18008766d  xor     ebp, ebp
0x18008766f  mov     r15d, [rsp+88h+arg_28]
0x180087677  xor     edi, edi
0x180087679  mov     [rsp+88h+Src], rdi
0x18008767e  test    rbp, rbp
0x180087681  jz      loc_180087773
0x180087687  cmp     [rbp+0], dil
0x18008768b  jz      loc_180087773
0x180087691  mov     ebx, [r13+8]
0x180087695  inc     ebx
0x180087697  lea     eax, [rbx+rbx]
0x18008769a  movsxd  rcx, eax
0x18008769d  call    sqlite3Malloc
0x1800876a2  mov     rsi, rax
0x1800876a5  test    rax, rax
0x1800876a8  jnz     short loc_1800876B4
0x1800876aa  mov     eax, 7
0x1800876af  jmp     loc_180087B34
0x1800876b4  mov     [rax], dil
0x1800876b7  mov     r9, rsi
0x1800876ba  mov     rax, [r13+40h]
0x1800876be  mov     r8d, ebx
0x1800876c1  mov     rdx, rbp
0x1800876c4  mov     rcx, r13
0x1800876c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800876cc  mov     edi, eax
0x1800876ce  cmp     eax, 200h
0x1800876d3  jnz     short loc_1800876E7
0x1800876d5  mov     eax, r15d
0x1800876d8  and     eax, 1000000h
0x1800876dd  neg     eax
0x1800876df  sbb     edi, edi
0x1800876e1  and     edi, 60Eh
0x1800876e7  mov     rcx, rsi
0x1800876ea  call    sqlite3Strlen30
0x1800876ef  mov     rcx, rbp
0x1800876f2  mov     [rsp+88h+arg_0], eax
0x1800876f9  mov     r14d, eax
0x1800876fc  call    sqlite3Strlen30
0x180087701  movsxd  r12, eax
0x180087704  xor     edx, edx
0x180087706  inc     r12
0x180087709  add     r12, rbp
0x18008770c  mov     [rsp+88h+Src], r12
0x180087711  mov     rbx, r12
0x180087714  cmp     [r12], dl
0x180087718  jz      short loc_180087746
0x18008771a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18008771e  mov     rax, r8
0x180087721  inc     rax
0x180087724  cmp     [rbx+rax], dl
0x180087727  jnz     short loc_180087721
0x180087729  lea     rcx, [rax+1]
0x18008772d  mov     rax, r8
0x180087730  add     rcx, rbx
0x180087733  inc     rax
0x180087736  cmp     [rcx+rax], dl
0x180087739  jnz     short loc_180087733
0x18008773b  lea     rbx, [rax+1]
0x18008773f  add     rbx, rcx
0x180087742  cmp     [rbx], dl
0x180087744  jnz     short loc_18008771E
0x180087746  test    edi, edi
0x180087748  jnz     short loc_1800877C6
0x18008774a  sub     ebx, r12d
0x18008774d  lea     eax, [r14+8]
0x180087751  inc     ebx
0x180087753  cmp     eax, [r13+8]
0x180087757  jle     short loc_180087773
0x180087759  lea     r8, aCannotOpenFile; "cannot open file"
0x180087760  mov     edx, 0F1C9h
0x180087765  lea     ecx, [rdi+0Eh]
0x180087768  call    sqlite3ReportError
0x18008776d  mov     edi, eax
0x18008776f  test    eax, eax
0x180087771  jnz     short loc_1800877C6
0x180087773  mov     eax, dword ptr [rsp+88h+var_58]
0x180087777  movsxd  rdx, dword ptr [r13+4]
0x18008777b  add     eax, 7
0x18008777e  and     eax, 0FFFFFFF8h
0x180087781  movsxd  r8, r14d
0x180087784  mov     dword ptr [rsp+88h+var_58], eax
0x180087788  add     rdx, 7
0x18008778c  add     eax, eax
0x18008778e  movsxd  r9, ebx
0x180087791  movsxd  rcx, eax
0x180087794  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180087798  add     rcx, r9
0x18008779b  mov     [rsp+88h+Size], r9
0x1800877a0  lea     rax, [r8+0D3h]
0x1800877a7  mov     [rsp+88h+var_50], r8
0x1800877ac  add     rcx, rdx
0x1800877af  lea     rax, [r8+rax*2]
0x1800877b3  add     rcx, rax; Size
0x1800877b6  call    sqlite3MallocZero
0x1800877bb  mov     r14, rax
0x1800877be  test    rax, rax
0x1800877c1  jnz     short loc_1800877D5
0x1800877c3  lea     edi, [rax+7]
0x1800877c6  mov     rdx, rsi
0x1800877c9  xor     ecx, ecx
0x1800877cb  call    sqlite3DbFree
0x1800877d0  jmp     loc_180087B32
0x1800877d5  movsxd  rdx, dword ptr [rsp+88h+var_58]
0x1800877da  add     rax, 138h
0x1800877e0  movsxd  rbx, [rsp+88h+arg_0]
0x1800877e8  xor     r12d, r12d
0x1800877eb  mov     [r14+120h], rax
0x1800877f2  lea     rcx, [rax+50h]
0x1800877f6  mov     [r14+48h], rcx
0x1800877fa  movsxd  rax, dword ptr [r13+4]
0x1800877fe  add     rax, 7
0x180087802  and     rax, 0FFFFFFFFFFFFFFF8h
0x180087806  add     rax, rcx
0x180087809  mov     [r14+58h], rax
0x18008780d  lea     rcx, [rdx+rax]
0x180087811  lea     rax, [rdx+0Ch]
0x180087815  mov     [r14+50h], rcx
0x180087819  add     rax, rcx
0x18008781c  mov     [rdx+rcx], r14
0x180087820  mov     [rsp+88h+var_58], rax
0x180087825  mov     [r14+0D8h], rax
0x18008782c  test    ebx, ebx
0x18008782e  jle     loc_1800878C5
0x180087834  mov     r8, rbx; Size
0x180087837  mov     rdx, rsi; Src
0x18008783a  mov     rcx, rax; void *
0x18008783d  call    memcpy_0
0x180087842  lea     eax, [rbx+1]
0x180087845  movsxd  rbx, eax
0x180087848  add     rbx, [rsp+88h+var_58]
0x18008784d  mov     rax, [rsp+88h+Src]
0x180087852  test    rax, rax
0x180087855  jz      short loc_18008786E
0x180087857  mov     r8, [rsp+88h+Size]; Size
0x18008785c  mov     rdx, rax; Src
0x18008785f  mov     rcx, rbx; void *
0x180087862  call    memcpy_0
0x180087867  add     rbx, [rsp+88h+Size]
0x18008786c  jmp     short loc_180087871
0x18008786e  inc     rbx
0x180087871  mov     r8, [rsp+88h+var_50]; Size
0x180087876  mov     rdx, rsi; Src
0x180087879  mov     rcx, rbx; void *
0x18008787c  mov     [r14+0E0h], rbx
0x180087883  call    memcpy_0
0x180087888  mov     rax, [rsp+88h+var_50]
0x18008788d  mov     rcx, 6C616E72756F6A2Dh
0x180087897  mov     r8, rax; Size
0x18008789a  mov     rdx, rsi; Src
0x18008789d  mov     [rax+rbx], rcx
0x1800878a1  add     rbx, 9
0x1800878a5  add     rbx, rax
0x1800878a8  mov     rcx, rbx; void *
0x1800878ab  mov     [r14+130h], rbx
0x1800878b2  call    memcpy_0
0x1800878b7  mov     rax, [rsp+88h+var_50]
0x1800878bc  mov     dword ptr [rbx+rax], 6C61772Dh
0x1800878c3  jmp     short loc_1800878D7
0x1800878c5  mov     [r14+0E0h], r12
0x1800878cc  mov     [r14+130h], r12
0x1800878d3  test    ebx, ebx
0x1800878d5  jz      short loc_1800878E1
0x1800878d7  mov     rdx, rsi
0x1800878da  xor     ecx, ecx
0x1800878dc  call    sqlite3DbFree
0x1800878e1  mov     [r14], r13
0x1800878e4  mov     [r14+0B4h], r15d
0x1800878eb  test    rbp, rbp
0x1800878ee  jz      loc_1800879C9
0x1800878f4  cmp     [rbp+0], r12b
0x1800878f8  jz      loc_1800879C9
0x1800878fe  mov     r8, [r14+48h]
0x180087902  lea     rax, [rsp+88h+arg_0]
0x18008790a  mov     rdx, [r14+0D8h]
0x180087911  mov     r9d, r15d
0x180087914  mov     rcx, r13
0x180087917  mov     [rsp+88h+var_68], rax
0x18008791c  mov     [rsp+88h+arg_0], r12d
0x180087924  call    sqlite3OsOpen
0x180087929  mov     r15d, [rsp+88h+arg_0]
0x180087931  mov     edi, eax
0x180087933  mov     r12d, r15d
0x180087936  and     r15d, 1
0x18008793a  shr     r12d, 7
0x18008793e  and     r12d, 1
0x180087942  mov     [r14+14h], r12b
0x180087946  test    eax, eax
0x180087948  jnz     loc_180087AD9
0x18008794e  mov     rcx, [r14+48h]
0x180087952  call    sqlite3OsDeviceCharacteristics
0x180087957  mov     ebx, eax
0x180087959  mov     esi, 2000h
0x18008795e  test    r15d, r15d
0x180087961  jnz     short loc_180087987
0x180087963  mov     rcx, r14
0x180087966  call    setSectorSize
0x18008796b  mov     ecx, [r14+0B8h]
0x180087972  cmp     [rsp+88h+arg_18], ecx
0x180087979  jnb     short loc_180087987
0x18008797b  cmp     ecx, esi
0x18008797d  cmova   ecx, esi
0x180087980  mov     [rsp+88h+arg_18], ecx
0x180087987  mov     rcx, [r14+0D8h]
0x18008798e  lea     rdx, aNolock; "nolock"
0x180087995  xor     r8d, r8d
0x180087998  call    sqlite3_uri_boolean
0x18008799d  mov     [r14+11h], al
0x1800879a1  test    esi, ebx
0x1800879a3  jnz     short loc_1800879C3
0x1800879a5  mov     rcx, [r14+0D8h]
0x1800879ac  lea     rdx, aImmutable; "immutable"
0x1800879b3  xor     r8d, r8d
0x1800879b6  call    sqlite3_uri_boolean
0x1800879bb  test    eax, eax
0x1800879bd  jz      loc_180087AD9
0x1800879c3  mov     r15d, 1
0x1800879c9  mov     word ptr [r14+15h], 401h
0x1800879d0  and     r15d, 1
0x1800879d4  mov     byte ptr [r14+11h], 1
0x1800879d9  mov     bpl, 1
0x1800879dc  test    edi, edi
0x1800879de  jnz     loc_180087B15
0x1800879e4  or      r8d, 0FFFFFFFFh
0x1800879e8  lea     rdx, [rsp+88h+arg_18]
0x1800879f0  mov     rcx, r14
0x1800879f3  call    sqlite3PagerSetPagesize
0x1800879f8  mov     edi, eax
0x1800879fa  test    eax, eax
0x1800879fc  jnz     loc_180087B15
0x180087a02  mov     rsi, [r14+120h]
0x180087a09  lea     rax, pagerStress
0x180087a10  mov     r13d, [rsp+88h+arg_30]
0x180087a18  xor     edi, edi
0x180087a1a  mov     ebx, [rsp+88h+arg_18]
0x180087a21  test    r13d, r13d
0x180087a24  mov     rcx, rsi; void *
0x180087a27  cmovz   rdi, rax
0x180087a2b  xor     edx, edx; Val
0x180087a2d  lea     r8d, [rdx+50h]; Size
0x180087a31  call    memset_0
0x180087a36  mov     ecx, 1
0x180087a3b  mov     dword ptr [rsi+2Ch], 88h
0x180087a42  mov     al, r13b
0x180087a45  mov     [rsi+28h], ecx
0x180087a48  xor     al, cl
0x180087a4a  mov     [rsi+24h], ecx
0x180087a4d  mov     rcx, rsi
0x180087a50  mov     [rsi+30h], al
0x180087a53  mov     edx, ebx
0x180087a55  mov     byte ptr [rsi+31h], 2
0x180087a59  mov     [rsi+38h], rdi
0x180087a5d  mov     [rsi+40h], r14
0x180087a61  mov     dword ptr [rsi+20h], 64h ; 'd'
0x180087a68  call    sqlite3PcacheSetPageSize
0x180087a6d  mov     edi, eax
0x180087a6f  test    eax, eax
  ... truncated ...
```
