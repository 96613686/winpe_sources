# sqlite3PagerOpen

- ea: `0x180001840`
- end: `0x180001d91`
- name: `sqlite3PagerOpen`
- size: `1361`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000126c`

## callees

- `0x180001840`
- `0x180001e24`
- `0x180005810`
- `0x180007680`
- `0x180008204`
- `0x1800084bc`
- `0x180008684`
- `0x18000a9e0`
- `0x18000aac0`
- `0x18000b0ac`
- `0x18000bd44`
- `0x18000bd90`
- `0x18003fe98`
- `0x18004a48c`
- `0x180059a60`
- `0x180060134`
- `0x1800683ec`
- `0x180099814`
- `0x18009a010`

## string_xrefs

- `0x1800019bd`: `cannot open file`

## pseudocode

```c
__int64 __fastcall sqlite3PagerOpen(__int64 a1, __int64 *a2, _BYTE *a3, __int64 a4, char a5, int a6, int a7)
{
  unsigned int v7; // edi
  const void *v8; // r14
  _BYTE *v9; // rbp
  int v11; // eax
  int v12; // ebx
  bool v13; // zf
  __int64 v14; // rax
  int v15; // r15d
  unsigned int v16; // esi
  unsigned int v17; // ebx
  _BYTE *v18; // rax
  __int64 result; // rax
  _BYTE *v20; // r12
  _BYTE *i; // rbx
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rax
  _BYTE *v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rdi
  __int64 v28; // rax
  size_t v29; // rbx
  int v30; // r12d
  unsigned __int64 v31; // rax
  unsigned __int64 v32; // rcx
  char *v33; // rax
  char *v34; // rbx
  char *v35; // rbx
  char *v36; // rbx
  __int64 v37; // r8
  __int64 v38; // rdx
  __int16 v39; // bx
  unsigned int v40; // ecx
  char v41; // bl
  int v42; // edx
  int v43; // ebp
  __int64 (__fastcall *v44)(); // r9
  char v45; // si
  unsigned __int8 v46; // al
  BOOL v47; // esi
  char v48; // bl
  int v49; // [rsp+30h] [rbp-58h]
  signed int v50; // [rsp+30h] [rbp-58h]
  char *v51; // [rsp+30h] [rbp-58h]
  size_t v52; // [rsp+38h] [rbp-50h]
  void *Src; // [rsp+40h] [rbp-48h]
  size_t Size; // [rsp+48h] [rbp-40h]
  int v55; // [rsp+90h] [rbp+8h] BYREF
  __int64 *v56; // [rsp+98h] [rbp+10h]
  unsigned int v57; // [rsp+A8h] [rbp+20h] BYREF

  v56 = a2;
  v7 = 0;
  v55 = 4096;
  v57 = 0;
  a7 = 0;
  v8 = 0;
  v9 = a3;
  v11 = 80;
  v12 = 1;
  if ( *(int *)(a1 + 4) > 80 )
    v11 = *(_DWORD *)(a1 + 4);
  v13 = (a5 & 2) == 0;
  v49 = v11;
  *a2 = 0;
  if ( !v13 )
  {
    a7 = 1;
    if ( a3 )
    {
      if ( *a3 )
      {
        v14 = sqlite3DbStrDup(0, a3);
        v8 = (const void *)v14;
        if ( !v14 )
          return 7;
        v7 = sqlite3Strlen30(v14);
        v57 = v7;
        v9 = 0;
      }
    }
  }
  v15 = a6;
  v16 = 0;
  Src = 0;
  if ( v9 && *v9 )
  {
    v17 = *(_DWORD *)(a1 + 8) + 1;
    v18 = (_BYTE *)sqlite3Malloc((int)(2 * v17));
    v8 = v18;
    if ( !v18 )
      return 7;
    *v18 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, _BYTE *))(a1 + 64))(a1, v9, v17, v18);
    if ( v16 == 512 )
      v16 = (v15 & 0x1000000) != 0 ? 0x60E : 0;
    v57 = sqlite3Strlen30(v8);
    v7 = v57;
    v20 = &v9[(int)sqlite3Strlen30(v9) + 1];
    Src = v20;
    for ( i = v20; *i; i = &v25[v24 + 1] )
    {
      v22 = -1;
      do
        ++v22;
      while ( i[v22] );
      v23 = v22 + 1;
      v24 = -1;
      v25 = &i[v23];
      do
        ++v24;
      while ( v25[v24] );
    }
    if ( v16 )
      goto LABEL_25;
    v12 = (_DWORD)i - (_DWORD)v20 + 1;
    if ( (signed int)(v7 + 8) > *(_DWORD *)(a1 + 8) )
    {
      v16 = sqlite3ReportError(14, 62005, "cannot open file");
      if ( v16 )
        goto LABEL_25;
    }
  }
  v50 = (v49 + 7) & 0xFFFFFFF8;
  Size = v12;
  v52 = (int)v7;
  v26 = sqlite3MallocZero(
          (int)v7
        + 2 * ((int)v7 + 211LL)
        + ((*(int *)(a1 + 4) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL)
        + v12
        + (__int64)(2 * v50));
  v27 = v26;
  if ( !v26 )
  {
    v16 = 7;
LABEL_25:
    sqlite3DbFree(0, v8);
    return v16;
  }
  v28 = v26 + 312;
  v29 = (int)v57;
  v30 = 0;
  *(_QWORD *)(v27 + 288) = v28;
  *(_QWORD *)(v27 + 72) = v28 + 80;
  v31 = v28 + 80 + ((*(int *)(a1 + 4) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL);
  *(_QWORD *)(v27 + 88) = v31;
  v32 = v31 + v50;
  *(_QWORD *)(v27 + 80) = v32;
  v33 = (char *)(v32 + v50 + 12LL);
  *(_QWORD *)(v50 + v32) = v27;
  v51 = v33;
  *(_QWORD *)(v27 + 216) = v33;
  if ( (int)v29 > 0 )
  {
    memcpy_0(v33, v8, v29);
    v34 = &v51[(int)v29 + 1];
    if ( Src )
    {
      memcpy_0(v34, Src, Size);
      v35 = &v34[Size];
    }
    else
    {
      v35 = v34 + 1;
    }
    *(_QWORD *)(v27 + 224) = v35;
    memcpy_0(v35, v8, v52);
    *(_QWORD *)&v35[v52] = 0x6C616E72756F6A2DLL;
    v36 = &v35[v52 + 9];
    *(_QWORD *)(v27 + 304) = v36;
    memcpy_0(v36, v8, v52);
    *(_DWORD *)&v36[v52] = 1818326829;
    goto LABEL_32;
  }
  *(_QWORD *)(v27 + 224) = 0;
  *(_QWORD *)(v27 + 304) = 0;
  if ( (_DWORD)v29 )
LABEL_32:
    sqlite3DbFree(0, v8);
  *(_QWORD *)v27 = a1;
  *(_DWORD *)(v27 + 180) = v15;
  if ( !v9 || !*v9 )
    goto LABEL_44;
  v37 = *(_QWORD *)(v27 + 72);
  v38 = *(_QWORD *)(v27 + 216);
  v57 = 0;
  v16 = sqlite3OsOpen(a1, v38, v37, v15, (__int64)&v57);
  v15 = v57 & 1;
  v30 = (v57 >> 7) & 1;
  *(_BYTE *)(v27 + 20) = (v57 & 0x80) != 0;
  if ( !v16 )
  {
    v39 = sqlite3OsDeviceCharacteristics(*(_QWORD *)(v27 + 72));
    if ( !v15 )
    {
      setSectorSize(v27);
      v40 = *(_DWORD *)(v27 + 184);
      if ( v40 > 0x1000 )
      {
        if ( v40 > 0x2000 )
          v40 = 0x2000;
        v55 = v40;
      }
    }
    *(_BYTE *)(v27 + 17) = sqlite3_uri_boolean(*(_QWORD *)(v27 + 216), "nolock", 0);
    if ( (v39 & 0x2000) != 0 || (unsigned int)sqlite3_uri_boolean(*(_QWORD *)(v27 + 216), "immutable", 0) )
    {
      LOBYTE(v15) = 1;
LABEL_44:
      *(_WORD *)(v27 + 21) = 1025;
      LOBYTE(v15) = v15 & 1;
      *(_BYTE *)(v27 + 17) = 1;
      v41 = 1;
      goto LABEL_45;
    }
  }
  v41 = 0;
LABEL_45:
  if ( v16 )
    goto LABEL_59;
  v16 = sqlite3PagerSetPagesize(v27, &v55, 0xFFFFFFFFLL);
  if ( v16 )
    goto LABEL_59;
  v43 = a7;
  v44 = pagerStress;
  if ( a7 )
    LODWORD(v44) = 0;
  v16 = sqlite3PcacheOpen(v55, v42, a7 ^ 1u, (int)v44, v27, *(void **)(v27 + 288));
  if ( v16 )
  {
LABEL_59:
    sqlite3OsClose(*(_QWORD *)(v27 + 72));
    pcache1Free(*(_QWORD **)(v27 + 280));
    sqlite3_free(v27);
    return v16;
  }
  v45 = a5;
  *(_BYTE *)(v27 + 16) = v41;
  v46 = v41 ^ 1;
  *(_BYTE *)(v27 + 8) = v41;
  *(_BYTE *)(v27 + 23) = v41;
  v47 = (v45 & 1) == 0;
  *(_BYTE *)(v27 + 10) = v47;
  *(_DWORD *)(v27 + 188) = -2;
  *(_BYTE *)(v27 + 19) = v43;
  *(_BYTE *)(v27 + 18) = v15;
  *(_BYTE *)(v27 + 11) = v41;
  v48 = 2 * (v41 ^ 1);
  *(_WORD *)(v27 + 12) = v46;
  *(_BYTE *)(v27 + 14) = v48;
  *(_BYTE *)(v27 + 15) = 4 * v48;
  if ( v46 )
    *(_BYTE *)(v27 + 15) = v48 | (4 * v48);
  *(_BYTE *)(v27 + 25) &= ~1u;
  *(_WORD *)(v27 + 176) = 136;
  *(_QWORD *)(v27 + 208) = -1;
  setSectorSize(v27);
  if ( v47 )
  {
    if ( v43 || v30 )
      *(_BYTE *)(v27 + 9) = 4;
  }
  else
  {
    *(_BYTE *)(v27 + 9) = 2;
  }
  *(_QWORD *)(v27 + 264) = pageReinit;
  setGetterMethod(v27);
  result = 0;
  *v56 = v27;
  return result;
}

```

## disassembly

```asm
0x180001840  mov     r11, rsp
0x180001843  mov     [r11+18h], rbx
0x180001847  mov     [r11+20h], r9d
0x18000184b  mov     [r11+10h], rdx
0x18000184f  push    rbp
0x180001850  push    rsi
0x180001851  push    rdi
0x180001852  push    r12
0x180001854  push    r13
0x180001856  push    r14
0x180001858  push    r15
0x18000185a  sub     rsp, 50h
0x18000185e  xor     edi, edi
0x180001860  mov     dword ptr [r11+8], 1000h
0x180001868  xor     eax, eax
0x18000186a  mov     [rsp+88h+arg_18], edi
0x180001871  mov     [rsp+88h+arg_30], eax
0x180001878  xor     r14d, r14d
0x18000187b  mov     rbp, r8
0x18000187e  mov     r13, rcx
0x180001881  lea     eax, [rdi+50h]
0x180001884  cmp     [rcx+4], eax
0x180001887  lea     ebx, [rdi+1]
0x18000188a  cmovg   eax, [rcx+4]
0x18000188e  test    [rsp+88h+arg_20], 2
0x180001896  mov     dword ptr [rsp+88h+var_58], eax
0x18000189a  mov     [rdx], rdi
0x18000189d  jz      short loc_1800018D5
0x18000189f  mov     [rsp+88h+arg_30], ebx
0x1800018a6  test    r8, r8
0x1800018a9  jz      short loc_1800018D5
0x1800018ab  cmp     [r8], dil
0x1800018ae  jz      short loc_1800018D5
0x1800018b0  mov     rdx, r8
0x1800018b3  xor     ecx, ecx
0x1800018b5  call    sqlite3DbStrDup
0x1800018ba  mov     r14, rax
0x1800018bd  test    rax, rax
0x1800018c0  jz      short loc_180001910
0x1800018c2  mov     rcx, rax
0x1800018c5  call    sqlite3Strlen30
0x1800018ca  mov     edi, eax
0x1800018cc  mov     [rsp+88h+arg_18], eax
0x1800018d3  xor     ebp, ebp
0x1800018d5  mov     r15d, [rsp+88h+arg_28]
0x1800018dd  xor     esi, esi
0x1800018df  mov     [rsp+88h+Src], rsi
0x1800018e4  test    rbp, rbp
0x1800018e7  jz      loc_1800019D7
0x1800018ed  cmp     [rbp+0], sil
0x1800018f1  jz      loc_1800019D7
0x1800018f7  mov     ebx, [r13+8]
0x1800018fb  inc     ebx
0x1800018fd  lea     eax, [rbx+rbx]
0x180001900  movsxd  rcx, eax
0x180001903  call    sqlite3Malloc
0x180001908  mov     r14, rax
0x18000190b  test    rax, rax
0x18000190e  jnz     short loc_18000191A
0x180001910  mov     eax, 7
0x180001915  jmp     loc_180001D79
0x18000191a  mov     [rax], sil
0x18000191d  mov     r9, r14
0x180001920  mov     rax, [r13+40h]
0x180001924  mov     r8d, ebx
0x180001927  mov     rdx, rbp
0x18000192a  mov     rcx, r13
0x18000192d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001932  mov     esi, eax
0x180001934  cmp     eax, 200h
0x180001939  jnz     short loc_18000194D
0x18000193b  mov     eax, r15d
0x18000193e  and     eax, 1000000h
0x180001943  neg     eax
0x180001945  sbb     esi, esi
0x180001947  and     esi, 60Eh
0x18000194d  mov     rcx, r14
0x180001950  call    sqlite3Strlen30
0x180001955  mov     rcx, rbp
0x180001958  mov     [rsp+88h+arg_18], eax
0x18000195f  mov     edi, eax
0x180001961  call    sqlite3Strlen30
0x180001966  movsxd  r12, eax
0x180001969  xor     edx, edx
0x18000196b  inc     r12
0x18000196e  add     r12, rbp
0x180001971  mov     [rsp+88h+Src], r12
0x180001976  mov     rbx, r12
0x180001979  cmp     [r12], dl
0x18000197d  jz      short loc_1800019AB
0x18000197f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180001983  mov     rax, r8
0x180001986  inc     rax
0x180001989  cmp     [rbx+rax], dl
0x18000198c  jnz     short loc_180001986
0x18000198e  lea     rcx, [rax+1]
0x180001992  mov     rax, r8
0x180001995  add     rcx, rbx
0x180001998  inc     rax
0x18000199b  cmp     [rcx+rax], dl
0x18000199e  jnz     short loc_180001998
0x1800019a0  lea     rbx, [rax+1]
0x1800019a4  add     rbx, rcx
0x1800019a7  cmp     [rbx], dl
0x1800019a9  jnz     short loc_180001983
0x1800019ab  test    esi, esi
0x1800019ad  jnz     short loc_180001A2A
0x1800019af  sub     ebx, r12d
0x1800019b2  lea     eax, [rdi+8]
0x1800019b5  inc     ebx
0x1800019b7  cmp     eax, [r13+8]
0x1800019bb  jle     short loc_1800019D7
0x1800019bd  lea     r8, aCannotOpenFile; "cannot open file"
0x1800019c4  mov     edx, 0F235h
0x1800019c9  lea     ecx, [rsi+0Eh]
0x1800019cc  call    sqlite3ReportError
0x1800019d1  mov     esi, eax
0x1800019d3  test    eax, eax
0x1800019d5  jnz     short loc_180001A2A
0x1800019d7  mov     eax, dword ptr [rsp+88h+var_58]
0x1800019db  movsxd  rdx, dword ptr [r13+4]
0x1800019df  add     eax, 7
0x1800019e2  and     eax, 0FFFFFFF8h
0x1800019e5  movsxd  r8, edi
0x1800019e8  mov     dword ptr [rsp+88h+var_58], eax
0x1800019ec  add     rdx, 7
0x1800019f0  add     eax, eax
0x1800019f2  movsxd  r9, ebx
0x1800019f5  movsxd  rcx, eax
0x1800019f8  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800019fc  add     rcx, r9
0x1800019ff  mov     [rsp+88h+Size], r9
0x180001a04  lea     rax, [r8+0D3h]
0x180001a0b  mov     [rsp+88h+var_50], r8
0x180001a10  add     rcx, rdx
0x180001a13  lea     rax, [r8+rax*2]
0x180001a17  add     rcx, rax; Size
0x180001a1a  call    sqlite3MallocZero
0x180001a1f  mov     rdi, rax
0x180001a22  test    rax, rax
0x180001a25  jnz     short loc_180001A39
0x180001a27  lea     esi, [rax+7]
0x180001a2a  mov     rdx, r14
0x180001a2d  xor     ecx, ecx
0x180001a2f  call    sqlite3DbFree
0x180001a34  jmp     loc_180001D77
0x180001a39  movsxd  rdx, dword ptr [rsp+88h+var_58]
0x180001a3e  add     rax, 138h
0x180001a44  movsxd  rbx, [rsp+88h+arg_18]
0x180001a4c  xor     r12d, r12d
0x180001a4f  mov     [rdi+120h], rax
0x180001a56  lea     rcx, [rax+50h]
0x180001a5a  mov     [rdi+48h], rcx
0x180001a5e  movsxd  rax, dword ptr [r13+4]
0x180001a62  add     rax, 7
0x180001a66  and     rax, 0FFFFFFFFFFFFFFF8h
0x180001a6a  add     rax, rcx
0x180001a6d  mov     [rdi+58h], rax
0x180001a71  lea     rcx, [rax+rdx]
0x180001a75  lea     rax, [rdx+0Ch]
0x180001a79  mov     [rdi+50h], rcx
0x180001a7d  add     rax, rcx
0x180001a80  mov     [rdx+rcx], rdi
0x180001a84  mov     [rsp+88h+var_58], rax
0x180001a89  mov     [rdi+0D8h], rax
0x180001a90  test    ebx, ebx
0x180001a92  jle     loc_180001B29
0x180001a98  mov     r8, rbx; Size
0x180001a9b  mov     rdx, r14; Src
0x180001a9e  mov     rcx, rax; void *
0x180001aa1  call    memcpy_0
0x180001aa6  lea     eax, [rbx+1]
0x180001aa9  movsxd  rbx, eax
0x180001aac  add     rbx, [rsp+88h+var_58]
0x180001ab1  mov     rax, [rsp+88h+Src]
0x180001ab6  test    rax, rax
0x180001ab9  jz      short loc_180001AD2
0x180001abb  mov     r8, [rsp+88h+Size]; Size
0x180001ac0  mov     rdx, rax; Src
0x180001ac3  mov     rcx, rbx; void *
0x180001ac6  call    memcpy_0
0x180001acb  add     rbx, [rsp+88h+Size]
0x180001ad0  jmp     short loc_180001AD5
0x180001ad2  inc     rbx
0x180001ad5  mov     r8, [rsp+88h+var_50]; Size
0x180001ada  mov     rdx, r14; Src
0x180001add  mov     rcx, rbx; void *
0x180001ae0  mov     [rdi+0E0h], rbx
0x180001ae7  call    memcpy_0
0x180001aec  mov     rax, [rsp+88h+var_50]
0x180001af1  mov     rcx, 6C616E72756F6A2Dh
0x180001afb  mov     r8, rax; Size
0x180001afe  mov     rdx, r14; Src
0x180001b01  mov     [rax+rbx], rcx
0x180001b05  add     rbx, 9
0x180001b09  add     rbx, rax
0x180001b0c  mov     rcx, rbx; void *
0x180001b0f  mov     [rdi+130h], rbx
0x180001b16  call    memcpy_0
0x180001b1b  mov     rax, [rsp+88h+var_50]
0x180001b20  mov     dword ptr [rbx+rax], 6C61772Dh
0x180001b27  jmp     short loc_180001B3B
0x180001b29  mov     [rdi+0E0h], r12
0x180001b30  mov     [rdi+130h], r12
0x180001b37  test    ebx, ebx
0x180001b39  jz      short loc_180001B45
0x180001b3b  mov     rdx, r14
0x180001b3e  xor     ecx, ecx
0x180001b40  call    sqlite3DbFree
0x180001b45  xor     r14d, r14d
0x180001b48  mov     [rdi], r13
0x180001b4b  mov     [rdi+0B4h], r15d
0x180001b52  test    rbp, rbp
0x180001b55  jz      loc_180001C2D
0x180001b5b  cmp     [rbp+0], r14b
0x180001b5f  jz      loc_180001C2D
0x180001b65  mov     r8, [rdi+48h]
0x180001b69  lea     rax, [rsp+88h+arg_18]
0x180001b71  mov     rdx, [rdi+0D8h]
0x180001b78  mov     r9d, r15d
0x180001b7b  mov     rcx, r13
0x180001b7e  mov     [rsp+88h+var_68], rax
0x180001b83  mov     [rsp+88h+arg_18], r14d
0x180001b8b  call    sqlite3OsOpen
0x180001b90  mov     r15d, [rsp+88h+arg_18]
0x180001b98  mov     esi, eax
0x180001b9a  mov     r12d, r15d
0x180001b9d  and     r15d, 1
0x180001ba1  shr     r12d, 7
0x180001ba5  and     r12d, 1
0x180001ba9  mov     [rdi+14h], r12b
0x180001bad  test    eax, eax
0x180001baf  jnz     loc_180001D20
0x180001bb5  mov     rcx, [rdi+48h]
0x180001bb9  call    sqlite3OsDeviceCharacteristics
0x180001bbe  mov     ebx, eax
0x180001bc0  mov     ebp, 2000h
0x180001bc5  test    r15d, r15d
0x180001bc8  jnz     short loc_180001BEC
0x180001bca  mov     rcx, rdi
0x180001bcd  call    setSectorSize
0x180001bd2  mov     ecx, [rdi+0B8h]
0x180001bd8  cmp     ecx, 1000h
0x180001bde  jbe     short loc_180001BEC
0x180001be0  cmp     ecx, ebp
0x180001be2  cmova   ecx, ebp
0x180001be5  mov     [rsp+88h+arg_0], ecx
0x180001bec  mov     rcx, [rdi+0D8h]
0x180001bf3  lea     rdx, aNolock; "nolock"
0x180001bfa  xor     r8d, r8d
0x180001bfd  call    sqlite3_uri_boolean
0x180001c02  mov     [rdi+11h], al
0x180001c05  test    ebp, ebx
0x180001c07  jnz     short loc_180001C27
0x180001c09  mov     rcx, [rdi+0D8h]
0x180001c10  lea     rdx, aImmutable; "immutable"
0x180001c17  xor     r8d, r8d
0x180001c1a  call    sqlite3_uri_boolean
0x180001c1f  test    eax, eax
0x180001c21  jz      loc_180001D20
0x180001c27  mov     r15d, 1
0x180001c2d  mov     word ptr [rdi+15h], 401h
0x180001c33  and     r15d, 1
0x180001c37  mov     byte ptr [rdi+11h], 1
0x180001c3b  mov     bl, 1
0x180001c3d  test    esi, esi
0x180001c3f  jnz     loc_180001D5A
0x180001c45  or      r13, 0FFFFFFFFFFFFFFFFh
0x180001c49  lea     rdx, [rsp+88h+arg_0]
0x180001c51  mov     r8d, r13d
0x180001c54  mov     rcx, rdi
0x180001c57  call    sqlite3PagerSetPagesize
0x180001c5c  mov     esi, eax
0x180001c5e  test    eax, eax
0x180001c60  jnz     loc_180001D5A
0x180001c66  mov     ebp, [rsp+88h+arg_30]
0x180001c6d  lea     r9, pagerStress
0x180001c74  mov     rax, [rdi+120h]
0x180001c7b  mov     r8d, ebp
0x180001c7e  mov     ecx, [rsp+88h+arg_0]; int
0x180001c85  test    ebp, ebp
0x180001c87  mov     [rsp+88h+var_60], rax; void *
0x180001c8c  cmovnz  r9, r14; int
0x180001c90  mov     [rsp+88h+var_68], rdi; __int64
0x180001c95  xor     r8d, 1; int
0x180001c99  call    sqlite3PcacheOpen
0x180001c9e  mov     esi, eax
0x180001ca0  test    eax, eax
0x180001ca2  jnz     loc_180001D5A
0x180001ca8  mov     esi, dword ptr [rsp+88h+arg_20]
0x180001caf  mov     al, bl
0x180001cb1  mov     [rdi+10h], bl
0x180001cb4  xor     al, 1
0x180001cb6  mov     [rdi+8], bl
0x180001cb9  not     esi
0x180001cbb  mov     [rdi+17h], bl
0x180001cbe  and     esi, 1
0x180001cc1  mov     [rdi+0Ah], sil
0x180001cc5  mov     dword ptr [rdi+0BCh], 0FFFFFFFEh
0x180001ccf  mov     [rdi+13h], bpl
  ... truncated ...
```
