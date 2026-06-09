# sub_1400BBC2C

- ea: `0x1400bbc2c`
- end: `0x1400bc2fd`
- name: `sub_1400BBC2C`
- size: `1745`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `24`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14008403c`

## callees

- `0x14000c2c8`
- `0x14000fc44`
- `0x140011860`
- `0x140012d2c`
- `0x140036780`
- `0x1400367a0`
- `0x140046040`
- `0x1400751c8`
- `0x14007537c`
- `0x14007f16c`
- `0x14007f288`
- `0x1400805b4`
- `0x140081420`
- `0x140081450`
- `0x140081848`
- `0x140091968`
- `0x1400bb2d4`
- `0x1400bb924`
- `0x1400bbc2c`
- `0x1400bc300`
- `0x1400eb460`
- `0x1400ed030`
- `0x1400ed07c`
- `0x1401148fc`

## import_xrefs

- `MpClient!MpDynamicSignatureEnumerate` at `0x1400bbd88`
- `MpClient!MpDynamicSignatureEnumerate` at `0x1400bbd88`
- `MpClient!MpDynamicSignatureOpen` at `0x1400bbd3f`
- `MpClient!MpDynamicSignatureOpen` at `0x1400bbd3f`
- `MpClient!MpAddDynamicSignatureFile` at `0x1400bc11f`
- `MpClient!MpAddDynamicSignatureFile` at `0x1400bc11f`
- `MpClient!MpFreeMemory` at `0x1400bbd6d`
- `MpClient!MpFreeMemory` at `0x1400bbd76`
- `MpClient!MpFreeMemory` at `0x1400bc0fe`
- `MpClient!MpFreeMemory` at `0x1400bc107`
- `MpClient!MpFreeMemory` at `0x1400bc1e3`
- `MpClient!MpFreeMemory` at `0x1400bc1ec`
- `MpClient!MpFreeMemory` at `0x1400bbd6d`
- `MpClient!MpFreeMemory` at `0x1400bbd76`
- `MpClient!MpFreeMemory` at `0x1400bc0fe`
- `MpClient!MpFreeMemory` at `0x1400bc107`
- `MpClient!MpFreeMemory` at `0x1400bc1e3`
- `MpClient!MpFreeMemory` at `0x1400bc1ec`
- `MpClient!MpHandleClose` at `0x1400bc1fc`
- `MpClient!MpHandleClose` at `0x1400bc20c`
- `MpClient!MpHandleClose` at `0x1400bc1fc`
- `MpClient!MpHandleClose` at `0x1400bc20c`
- `MpClient!MpManagerOpen` at `0x1400bbd23`
- `MpClient!MpManagerOpen` at `0x1400bbd23`

## string_xrefs

- `0x1400bbe4f`: `%temp%`
- `0x1400bbd4d`: `Enumerating installed dynamic signatures ...\n`
- `0x1400bbcff`: `%zu blob paths found.\n`
- `0x1400bc06d`: `Dynamic signature already loaded by engine: %ls\n`

## pseudocode

```c
__int64 sub_1400BBC2C()
{
  int v0; // eax
  int v1; // eax
  unsigned int v2; // ebx
  int v3; // eax
  int v4; // eax
  _QWORD *v5; // rbx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rax
  __int128 *v11; // rdx
  int v12; // eax
  _QWORD *j; // r15
  _QWORD *v14; // rdx
  __int128 *v15; // rdx
  __int128 *v16; // rcx
  __int128 *v17; // rdx
  unsigned __int64 v18; // r8
  __int128 *v19; // r14
  int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  void *v23; // rdi
  void *v24; // rbx
  int v25; // eax
  _QWORD *v26; // rsi
  void *v27; // rdi
  _QWORD *v28; // rcx
  _QWORD *v29; // rdx
  int v30; // eax
  __int64 v31; // rax
  int v32; // eax
  void *v33; // rsi
  void *v34; // r14
  _QWORD *v35; // r12
  int v36; // eax
  _QWORD *v37; // rbx
  void *Block[2]; // [rsp+38h] [rbp-99h] BYREF
  __int64 v40; // [rsp+48h] [rbp-89h]
  void *v41; // [rsp+50h] [rbp-81h] BYREF
  _QWORD *i; // [rsp+58h] [rbp-79h] BYREF
  void *v43; // [rsp+60h] [rbp-71h] BYREF
  __int64 v44; // [rsp+68h] [rbp-69h] BYREF
  __int128 v45; // [rsp+70h] [rbp-61h] BYREF
  __int64 v46; // [rsp+80h] [rbp-51h]
  __int128 v47; // [rsp+88h] [rbp-49h] BYREF
  __int64 v48; // [rsp+98h] [rbp-39h]
  __int64 v49; // [rsp+A0h] [rbp-31h] BYREF
  __int128 v50; // [rsp+A8h] [rbp-29h] BYREF
  __int128 v51; // [rsp+B8h] [rbp-19h]
  __int128 v52; // [rsp+C8h] [rbp-9h] BYREF
  __int128 v53; // [rsp+D8h] [rbp+7h]
  void *v54; // [rsp+E8h] [rbp+17h] BYREF
  void *v55; // [rsp+F0h] [rbp+1Fh] BYREF
  void *v56; // [rsp+F8h] [rbp+27h] BYREF

  if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 8) != 0 )
    sub_140081420(*((_QWORD *)off_14018DE50 + 2), 23, qword_1401636B0);
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v0 = sub_1400EB460(&v47, 0);
  if ( v0 < 0 )
  {
    if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 4) != 0 )
      sub_140081450(*((_QWORD *)off_14018DE50 + 2), 44, qword_140168950, (unsigned int)v0);
    v1 = sub_1400EB460(&v47, 1);
    v2 = v1;
    if ( v1 < 0 )
    {
      if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
        sub_140081450(*((_QWORD *)off_14018DE50 + 2), 45, qword_140168950, (unsigned int)v1);
      sub_14000FC44(v2);
    }
  }
  sub_1400ED07C(L"%zu blob paths found.\n", (__int64)(*((_QWORD *)&v47 + 1) - v47) >> 5);
  if ( *((_QWORD *)&v47 + 1) != (_QWORD)v47 )
  {
    v44 = 0;
    v3 = MpManagerOpen(0, &v44);
    if ( v3 < 0 )
      sub_14000FC44((unsigned int)v3);
    v49 = 0;
    v4 = MpDynamicSignatureOpen(v44, 0, &v49);
    if ( v4 < 0 )
      sub_14000FC44((unsigned int)v4);
    sub_1400ED030(L"Enumerating installed dynamic signatures ...\n");
    v5 = 0;
    for ( i = 0; ; v5 = i )
    {
      if ( v5 )
      {
        if ( *v5 )
          MpFreeMemory(*v5);
        MpFreeMemory(v5);
        i = 0;
      }
      v6 = MpDynamicSignatureEnumerate(v49, &i);
      v7 = v6;
      if ( v6 )
        break;
      if ( !i )
        goto LABEL_28;
      v8 = *i;
      v52 = 0;
      v53 = 0;
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)(v8 + 2 * v9) );
      sub_1400751C8(&v52, v8, v9);
      v10 = *((_QWORD *)&v45 + 1);
      if ( *((_QWORD *)&v45 + 1) == v46 )
      {
        sub_140091968(&v45, *((_QWORD *)&v45 + 1), &v52);
      }
      else
      {
        **((_OWORD **)&v45 + 1) = 0;
        *(_QWORD *)(v10 + 16) = 0;
        *(_QWORD *)(v10 + 24) = 0;
        v11 = &v52;
        if ( *((_QWORD *)&v53 + 1) > 7u )
          v11 = (__int128 *)v52;
        sub_14007537C(v10, v11, v53);
        *((_QWORD *)&v45 + 1) += 32LL;
      }
      sub_14007F288(&v52);
    }
    if ( v6 < 0 )
    {
      if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
        sub_140081450(*((_QWORD *)off_14018DE50 + 2), 24, qword_1401636B0, (unsigned int)v6);
      sub_1400ED030(L"ERROR: MpDynamicSignatureEnumerate failed with hr=%#lx\n", v7);
      sub_14000FC44(v7);
    }
LABEL_28:
    sub_1400ED07C(L"%zu signatures found.\n", (__int64)(*((_QWORD *)&v45 + 1) - v45) >> 5);
    v43 = 0;
    v12 = sub_14000C2C8(&v43, L"%temp%");
    if ( v12 < 0 )
      sub_14000FC44((unsigned int)v12);
    for ( j = (_QWORD *)v47; ; j += 4 )
    {
      if ( j == *((_QWORD **)&v47 + 1) )
      {
        if ( v43 )
          j_j_j__free_base(v43);
        v37 = i;
        if ( i )
        {
          if ( *i )
            MpFreeMemory(*i);
          MpFreeMemory(v37);
        }
        if ( v49 )
          MpHandleClose(v49);
        if ( v44 )
          MpHandleClose(v44);
        goto LABEL_99;
      }
      if ( j[2] >= 8u && !sub_1400805B4(j, L"https://") )
        break;
LABEL_88:
      ;
    }
    v50 = 0;
    v51 = 0;
    v14 = j;
    if ( j[3] > 7u )
      v14 = (_QWORD *)*j;
    sub_14007537C(&v50, v14, j[2]);
    v15 = &v50;
    if ( *((_QWORD *)&v51 + 1) > 7u )
      v15 = (__int128 *)v50;
    sub_1400ED030(L"Trying %ls ...\n", v15);
    v16 = &v50;
    v17 = (__int128 *)v50;
    v18 = *((_QWORD *)&v51 + 1);
    if ( *((_QWORD *)&v51 + 1) > 7u )
      v16 = (__int128 *)v50;
    if ( *((_WORD *)v16 + v51 - 1) != 47 )
    {
      sub_1400BC300(&v50, 1, 47);
      v18 = *((_QWORD *)&v51 + 1);
      v17 = (__int128 *)v50;
    }
    v19 = &v50;
    if ( v18 > 7 )
      v19 = v17;
    v54 = 0;
    v20 = sub_140011860(&v54, L"%lslatest.sha1", v19);
    if ( v20 < 0 )
      sub_14000FC44((unsigned int)v20);
    v41 = 0;
    v21 = sub_140012D2C();
    v22 = sub_140011860(&v41, L"%ls\\latest.sha1-%I64d.txt", v43, v21);
    if ( v22 < 0 )
      sub_14000FC44((unsigned int)v22);
    v23 = v41;
    v24 = v54;
    if ( (int)sub_1400BB2D4(v54, v41) >= 0 )
    {
      Block[1] = v23;
      v40 = 0;
      Block[0] = 0;
      v25 = sub_1400BB924(&v41, Block);
      if ( v25 >= 0 )
      {
        v26 = (_QWORD *)v45;
        v27 = Block[0];
        while ( v26 != *((_QWORD **)&v45 + 1) )
        {
          v28 = v26;
          if ( v26[3] > 7u )
            v28 = (_QWORD *)*v26;
          if ( !(unsigned int)sub_140046040(v28, v27) )
          {
            sub_1400ED030(L"Dynamic signature already loaded by engine: %ls\n", v27);
            goto LABEL_81;
          }
          v29 = v26;
          if ( v26[3] > 7u )
            v29 = (_QWORD *)*v26;
          sub_1400ED030(L"%ls - not match\n", v29);
          v26 += 4;
        }
        v56 = 0;
        v30 = sub_140011860(&v56, L"%ls%ls", v19, v27);
        if ( v30 < 0 )
          sub_14000FC44((unsigned int)v30);
        v55 = 0;
        v31 = sub_140012D2C();
        v32 = sub_140011860(&v55, L"%ls\\%ls-%I64d.txt", v43, v27, v31);
        if ( v32 < 0 )
          sub_14000FC44((unsigned int)v32);
        v33 = v55;
        v34 = v56;
        if ( (int)sub_1400BB2D4(v56, v55) >= 0 )
        {
          v52 = (unsigned __int64)v33;
          v35 = i;
          if ( i )
          {
            if ( *i )
              MpFreeMemory(*i);
            MpFreeMemory(v35);
            i = 0;
          }
          v36 = MpAddDynamicSignatureFile(v44, v33, &i, 0);
          if ( v36 >= 0 )
            sub_1400ED07C(L"MpAddDynamicSignatureFile %ls finished successfully.\n", v33);
          else
            sub_1400ED07C(L"MpAddDynamicSignatureFile %ls failed with %#lx. Ignored.\n", v33, (unsigned int)v36);
          sub_1401148FC(&v52);
        }
        if ( v33 )
          j_j_j__free_base(v33);
        if ( v34 )
          j_j_j__free_base(v34);
LABEL_81:
        if ( v27 )
          j_j_j__free_base(v27);
        sub_1401148FC(&Block[1]);
        if ( v41 )
          j_j_j__free_base(v41);
        if ( !v24 )
          goto LABEL_87;
LABEL_86:
        j_j_j__free_base(v24);
LABEL_87:
        sub_14007F288(&v50);
        goto LABEL_88;
      }
      v23 = v41;
      if ( off_14018DE50 != (_UNKNOWN *)&off_14018DE50 && (*((_BYTE *)off_14018DE50 + 28) & 1) != 0 )
        sub_140081848(*((_QWORD *)off_14018DE50 + 2), 25, (unsigned int)qword_1401636B0, (_DWORD)v41, v25);
      if ( Block[0] )
        j_j_j__free_base(Block[0]);
      sub_1401148FC(&Block[1]);
    }
    if ( v23 )
      j_j_j__free_base(v23);
    if ( !v24 )
      goto LABEL_87;
    goto LABEL_86;
  }
LABEL_99:
  sub_14007F16C(&v47);
  return sub_14007F16C(&v45);
}

```

## disassembly

```asm
0x1400bbc2c  mov     rax, rsp
0x1400bbc2f  mov     [rax+8], rbx
0x1400bbc33  mov     [rax+10h], rsi
0x1400bbc37  mov     [rax+18h], rdi
0x1400bbc3b  push    rbp
0x1400bbc3c  push    r12
0x1400bbc3e  push    r13
0x1400bbc40  push    r14
0x1400bbc42  push    r15
0x1400bbc44  lea     rbp, [rax-5Fh]
0x1400bbc48  sub     rsp, 100h
0x1400bbc4f  mov     rax, cs:__security_cookie
0x1400bbc56  xor     rax, rsp
0x1400bbc59  mov     [rbp+57h+var_28], rax
0x1400bbc5d  lea     rsi, off_14018DE50
0x1400bbc64  mov     rcx, cs:off_14018DE50
0x1400bbc6b  cmp     rcx, rsi
0x1400bbc6e  jz      short loc_1400BBC8B
0x1400bbc70  test    byte ptr [rcx+1Ch], 8
0x1400bbc74  jz      short loc_1400BBC8B
0x1400bbc76  mov     edx, 17h
0x1400bbc7b  lea     r8, qword_1401636B0
0x1400bbc82  mov     rcx, [rcx+10h]
0x1400bbc86  call    sub_140081420
0x1400bbc8b  xorps   xmm1, xmm1
0x1400bbc8e  movdqu  [rbp+57h+var_B8], xmm1
0x1400bbc93  xor     r13d, r13d
0x1400bbc96  mov     [rbp+57h+var_A8], r13
0x1400bbc9a  movdqu  [rbp+57h+var_A0], xmm1
0x1400bbc9f  mov     [rbp+57h+var_90], r13
0x1400bbca3  xor     edx, edx
0x1400bbca5  lea     rcx, [rbp+57h+var_A0]
0x1400bbca9  call    sub_1400EB460
0x1400bbcae  test    eax, eax
0x1400bbcb0  jns     short loc_1400BBCF3
0x1400bbcb2  mov     rcx, cs:off_14018DE50
0x1400bbcb9  cmp     rcx, rsi
0x1400bbcbc  jz      short loc_1400BBCDB
0x1400bbcbe  test    byte ptr [rcx+1Ch], 4
0x1400bbcc2  jz      short loc_1400BBCDB
0x1400bbcc4  lea     edx, [r13+2Ch]
0x1400bbcc8  mov     r9d, eax
0x1400bbccb  lea     r8, qword_140168950
0x1400bbcd2  mov     rcx, [rcx+10h]
0x1400bbcd6  call    sub_140081450
0x1400bbcdb  mov     edx, 1
0x1400bbce0  lea     rcx, [rbp+57h+var_A0]
0x1400bbce4  call    sub_1400EB460
0x1400bbce9  mov     ebx, eax
0x1400bbceb  test    eax, eax
0x1400bbced  js      loc_1400BC25B
0x1400bbcf3  mov     rdx, qword ptr [rbp+57h+var_A0+8]
0x1400bbcf7  sub     rdx, qword ptr [rbp+57h+var_A0]
0x1400bbcfb  sar     rdx, 5
0x1400bbcff  lea     rcx, aZuBlobPathsFou; "%zu blob paths found.\n"
0x1400bbd06  call    sub_1400ED07C
0x1400bbd0b  mov     rax, qword ptr [rbp+57h+var_A0+8]
0x1400bbd0f  cmp     rax, qword ptr [rbp+57h+var_A0]
0x1400bbd13  jz      loc_1400BC213
0x1400bbd19  mov     [rbp+57h+var_C0], r13
0x1400bbd1d  lea     rdx, [rbp+57h+var_C0]
0x1400bbd21  xor     ecx, ecx
0x1400bbd23  call    cs:MpManagerOpen
0x1400bbd29  test    eax, eax
0x1400bbd2b  js      loc_1400BC28D
0x1400bbd31  mov     [rbp+57h+var_88], r13
0x1400bbd35  lea     r8, [rbp+57h+var_88]
0x1400bbd39  xor     edx, edx
0x1400bbd3b  mov     rcx, [rbp+57h+var_C0]
0x1400bbd3f  call    cs:MpDynamicSignatureOpen
0x1400bbd45  test    eax, eax
0x1400bbd47  js      loc_1400BC295
0x1400bbd4d  lea     rcx, aEnumeratingIns; "Enumerating installed dynamic signature"...
0x1400bbd54  call    sub_1400ED030
0x1400bbd59  mov     rbx, r13
0x1400bbd5c  mov     [rbp+57h+var_D0], rbx
0x1400bbd60  test    rbx, rbx
0x1400bbd63  jz      short loc_1400BBD80
0x1400bbd65  mov     rcx, [rbx]
0x1400bbd68  test    rcx, rcx
0x1400bbd6b  jz      short loc_1400BBD73
0x1400bbd6d  call    cs:__imp_MpFreeMemory
0x1400bbd73  mov     rcx, rbx
0x1400bbd76  call    cs:__imp_MpFreeMemory
0x1400bbd7c  mov     [rbp+57h+var_D0], r13
0x1400bbd80  lea     rdx, [rbp+57h+var_D0]
0x1400bbd84  mov     rcx, [rbp+57h+var_88]
0x1400bbd88  call    cs:MpDynamicSignatureEnumerate
0x1400bbd8e  mov     ebx, eax
0x1400bbd90  test    eax, eax
0x1400bbd92  jnz     loc_1400BBE2B
0x1400bbd98  mov     rax, [rbp+57h+var_D0]
0x1400bbd9c  test    rax, rax
0x1400bbd9f  jz      loc_1400BBE33
0x1400bbda5  mov     rdx, [rax]
0x1400bbda8  xorps   xmm0, xmm0
0x1400bbdab  movups  [rbp+57h+var_60], xmm0
0x1400bbdaf  xorps   xmm1, xmm1
0x1400bbdb2  movdqu  [rbp+57h+var_50], xmm1
0x1400bbdb7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400bbdbb  inc     r8
0x1400bbdbe  cmp     [rdx+r8*2], r13w
0x1400bbdc3  jnz     short loc_1400BBDBB
0x1400bbdc5  lea     rcx, [rbp+57h+var_60]
0x1400bbdc9  call    sub_1400751C8
0x1400bbdce  nop
0x1400bbdcf  mov     rax, qword ptr [rbp+57h+var_B8+8]
0x1400bbdd3  cmp     rax, [rbp+57h+var_A8]
0x1400bbdd7  jz      short loc_1400BBE08
0x1400bbdd9  xorps   xmm0, xmm0
0x1400bbddc  movups  xmmword ptr [rax], xmm0
0x1400bbddf  mov     [rax+10h], r13
0x1400bbde3  mov     [rax+18h], r13
0x1400bbde7  lea     rdx, [rbp+57h+var_60]
0x1400bbdeb  cmp     qword ptr [rbp+57h+var_50+8], 7
0x1400bbdf0  cmova   rdx, qword ptr [rbp+57h+var_60]
0x1400bbdf5  mov     r8, qword ptr [rbp+57h+var_50]
0x1400bbdf9  mov     rcx, rax
0x1400bbdfc  call    sub_14007537C
0x1400bbe01  add     qword ptr [rbp+57h+var_B8+8], 20h ; ' '
0x1400bbe06  jmp     short loc_1400BBE19
0x1400bbe08  lea     r8, [rbp+57h+var_60]
0x1400bbe0c  mov     rdx, rax
0x1400bbe0f  lea     rcx, [rbp+57h+var_B8]
0x1400bbe13  call    sub_140091968
0x1400bbe18  nop
0x1400bbe19  lea     rcx, [rbp+57h+var_60]
0x1400bbe1d  call    sub_14007F288
0x1400bbe22  mov     rbx, [rbp+57h+var_D0]
0x1400bbe26  jmp     loc_1400BBD60
0x1400bbe2b  test    ebx, ebx
0x1400bbe2d  js      loc_1400BC29D
0x1400bbe33  mov     rdx, qword ptr [rbp+57h+var_B8+8]
0x1400bbe37  sub     rdx, qword ptr [rbp+57h+var_B8]
0x1400bbe3b  sar     rdx, 5
0x1400bbe3f  lea     rcx, aZuSignaturesFo; "%zu signatures found.\n"
0x1400bbe46  call    sub_1400ED07C
0x1400bbe4b  mov     [rbp+57h+var_C8], r13
0x1400bbe4f  lea     rdx, aTemp; "%temp%"
0x1400bbe56  lea     rcx, [rbp+57h+var_C8]
0x1400bbe5a  call    sub_14000C2C8
0x1400bbe5f  test    eax, eax
0x1400bbe61  js      loc_1400BC2DD
0x1400bbe67  mov     r15, qword ptr [rbp+57h+var_A0]
0x1400bbe6b  mov     ebx, 2Fh ; '/'
0x1400bbe70  cmp     r15, qword ptr [rbp+57h+var_A0+8]
0x1400bbe74  jz      loc_1400BC1C3
0x1400bbe7a  cmp     qword ptr [r15+10h], 8
0x1400bbe7f  jb      loc_1400BC1BA
0x1400bbe85  lea     rdx, aHttps; "https://"
0x1400bbe8c  mov     rcx, r15
0x1400bbe8f  call    sub_1400805B4
0x1400bbe94  test    rax, rax
0x1400bbe97  jnz     loc_1400BC1BA
0x1400bbe9d  xorps   xmm0, xmm0
0x1400bbea0  movups  [rbp+57h+var_80], xmm0
0x1400bbea4  xorps   xmm1, xmm1
0x1400bbea7  movdqu  [rbp+57h+var_70], xmm1
0x1400bbeac  mov     rdx, r15
0x1400bbeaf  cmp     qword ptr [r15+18h], 7
0x1400bbeb4  jbe     short loc_1400BBEB9
0x1400bbeb6  mov     rdx, [r15]
0x1400bbeb9  mov     r8, [r15+10h]
0x1400bbebd  lea     rcx, [rbp+57h+var_80]
0x1400bbec1  call    sub_14007537C
0x1400bbec6  nop
0x1400bbec7  lea     rdx, [rbp+57h+var_80]
0x1400bbecb  cmp     qword ptr [rbp+57h+var_70+8], 7
0x1400bbed0  cmova   rdx, qword ptr [rbp+57h+var_80]
0x1400bbed5  lea     rcx, aTryingLs; "Trying %ls ...\n"
0x1400bbedc  call    sub_1400ED030
0x1400bbee1  lea     rcx, [rbp+57h+var_80]
0x1400bbee5  mov     rdx, qword ptr [rbp+57h+var_80]
0x1400bbee9  mov     r8, qword ptr [rbp+57h+var_70+8]
0x1400bbeed  cmp     r8, 7
0x1400bbef1  cmova   rcx, rdx
0x1400bbef5  mov     rax, qword ptr [rbp+57h+var_70]
0x1400bbef9  cmp     [rcx+rax*2-2], bx
0x1400bbefe  jz      short loc_1400BBF19
0x1400bbf00  mov     r8d, ebx
0x1400bbf03  mov     edx, 1
0x1400bbf08  lea     rcx, [rbp+57h+var_80]
0x1400bbf0c  call    sub_1400BC300
0x1400bbf11  mov     r8, qword ptr [rbp+57h+var_70+8]
0x1400bbf15  mov     rdx, qword ptr [rbp+57h+var_80]
0x1400bbf19  lea     r14, [rbp+57h+var_80]
0x1400bbf1d  cmp     r8, 7
0x1400bbf21  cmova   r14, rdx
0x1400bbf25  mov     [rbp+57h+var_40], r13
0x1400bbf29  mov     r8, r14
0x1400bbf2c  lea     rdx, aLslatestSha1; "%lslatest.sha1"
0x1400bbf33  lea     rcx, [rbp+57h+var_40]
0x1400bbf37  call    sub_140011860
0x1400bbf3c  test    eax, eax
0x1400bbf3e  js      loc_1400BC253
0x1400bbf44  mov     [rsp+120h+var_D8], r13
0x1400bbf49  call    sub_140012D2C
0x1400bbf4e  mov     r9, rax
0x1400bbf51  mov     r8, [rbp+57h+var_C8]
0x1400bbf55  lea     rdx, aLsLatestSha1I6; "%ls\\latest.sha1-%I64d.txt"
0x1400bbf5c  lea     rcx, [rsp+120h+var_D8]
0x1400bbf61  call    sub_140011860
0x1400bbf66  test    eax, eax
0x1400bbf68  js      loc_1400BC2F5
0x1400bbf6e  mov     rdi, [rsp+120h+var_D8]
0x1400bbf73  mov     rdx, rdi
0x1400bbf76  mov     rbx, [rbp+57h+var_40]
0x1400bbf7a  mov     rcx, rbx
0x1400bbf7d  call    sub_1400BB2D4
0x1400bbf82  test    eax, eax
0x1400bbf84  js      short loc_1400BBFFF
0x1400bbf86  xorps   xmm0, xmm0
0x1400bbf89  movups  xmmword ptr [rsp+120h+Block+8], xmm0
0x1400bbf8e  mov     [rsp+120h+Block+8], rdi
0x1400bbf93  mov     [rsp+120h+var_E0], r13
0x1400bbf98  mov     [rsp+120h+Block], r13
0x1400bbf9d  lea     rdx, [rsp+120h+Block]
0x1400bbfa2  lea     rcx, [rsp+120h+var_D8]
0x1400bbfa7  call    sub_1400BB924
0x1400bbfac  test    eax, eax
0x1400bbfae  jns     short loc_1400BC023
0x1400bbfb0  mov     rdi, [rsp+120h+var_D8]
0x1400bbfb5  mov     rcx, cs:off_14018DE50
0x1400bbfbc  cmp     rcx, rsi
0x1400bbfbf  jz      short loc_1400BBFE4
0x1400bbfc1  test    byte ptr [rcx+1Ch], 1
0x1400bbfc5  jz      short loc_1400BBFE4
0x1400bbfc7  mov     edx, 19h
0x1400bbfcc  mov     dword ptr [rsp+120h+var_100], eax
0x1400bbfd0  mov     r9, rdi
0x1400bbfd3  lea     r8, qword_1401636B0
0x1400bbfda  mov     rcx, [rcx+10h]
0x1400bbfde  call    sub_140081848
0x1400bbfe3  nop
0x1400bbfe4  mov     rcx, [rsp+120h+Block]; Block
0x1400bbfe9  test    rcx, rcx
0x1400bbfec  jz      short loc_1400BBFF4
0x1400bbfee  call    j_j_j__free_base
0x1400bbff3  nop
0x1400bbff4  lea     rcx, [rsp+120h+Block+8]
0x1400bbff9  call    sub_1401148FC
0x1400bbffe  nop
0x1400bbfff  test    rdi, rdi
0x1400bc002  jz      short loc_1400BC00D
0x1400bc004  mov     rcx, rdi; Block
0x1400bc007  call    j_j_j__free_base
0x1400bc00c  nop
0x1400bc00d  test    rbx, rbx
0x1400bc010  jz      loc_1400BC1AC
0x1400bc016  mov     rcx, rbx; Block
0x1400bc019  call    j_j_j__free_base
0x1400bc01e  jmp     loc_1400BC1AC
0x1400bc023  mov     rsi, qword ptr [rbp+57h+var_B8]
0x1400bc027  mov     rdi, [rsp+120h+Block]
0x1400bc02c  cmp     rsi, qword ptr [rbp+57h+var_B8+8]
0x1400bc030  jz      short loc_1400BC07E
0x1400bc032  mov     rcx, rsi
0x1400bc035  cmp     qword ptr [rsi+18h], 7
0x1400bc03a  jbe     short loc_1400BC03F
0x1400bc03c  mov     rcx, [rsi]
0x1400bc03f  mov     rdx, rdi
0x1400bc042  call    sub_140046040
0x1400bc047  test    eax, eax
0x1400bc049  jz      short loc_1400BC06A
0x1400bc04b  mov     rdx, rsi
0x1400bc04e  cmp     qword ptr [rsi+18h], 7
0x1400bc053  jbe     short loc_1400BC058
0x1400bc055  mov     rdx, [rsi]
0x1400bc058  lea     rcx, aLsNotMatch; "%ls - not match\n"
0x1400bc05f  call    sub_1400ED030
0x1400bc064  add     rsi, 20h ; ' '
0x1400bc068  jmp     short loc_1400BC02C
0x1400bc06a  mov     rdx, rdi
0x1400bc06d  lea     rcx, aDynamicSignatu_3; "Dynamic signature already loaded by eng"...
0x1400bc074  call    sub_1400ED030
0x1400bc079  jmp     loc_1400BC16F
0x1400bc07e  mov     [rbp+57h+var_30], r13
0x1400bc082  mov     r9, rdi
0x1400bc085  mov     r8, r14
0x1400bc088  lea     rdx, aLsLs_2; "%ls%ls"
0x1400bc08f  lea     rcx, [rbp+57h+var_30]
0x1400bc093  call    sub_140011860
0x1400bc098  test    eax, eax
0x1400bc09a  js      loc_1400BC2ED
0x1400bc0a0  mov     [rbp+57h+var_38], r13
0x1400bc0a4  call    sub_140012D2C
0x1400bc0a9  mov     [rsp+120h+var_100], rax
0x1400bc0ae  mov     r9, rdi
0x1400bc0b1  mov     r8, [rbp+57h+var_C8]
0x1400bc0b5  lea     rdx, aLsLsI64dTxt; "%ls\\%ls-%I64d.txt"
0x1400bc0bc  lea     rcx, [rbp+57h+var_38]
0x1400bc0c0  call    sub_140011860
0x1400bc0c5  test    eax, eax
0x1400bc0c7  js      loc_1400BC2E5
0x1400bc0cd  mov     rsi, [rbp+57h+var_38]
0x1400bc0d1  mov     rdx, rsi
0x1400bc0d4  mov     r14, [rbp+57h+var_30]
0x1400bc0d8  mov     rcx, r14
0x1400bc0db  call    sub_1400BB2D4
0x1400bc0e0  test    eax, eax
  ... truncated ...
```
