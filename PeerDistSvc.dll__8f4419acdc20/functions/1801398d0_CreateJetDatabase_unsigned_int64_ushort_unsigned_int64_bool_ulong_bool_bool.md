# CreateJetDatabase(unsigned __int64 &,ushort *,unsigned __int64,bool,ulong *,bool *,bool *)

- ea: `0x1801398d0`
- end: `0x180139cb4`
- name: `?CreateJetDatabase@@YAKAEA_KPEAG_K_NPEAKPEA_N5@Z`
- size: `996`
- prototype: `unsigned int(unsigned __int64 *, unsigned __int16 *, unsigned __int64, bool, unsigned int *, bool *, bool *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180040de0`
- `0x180056a0c`
- `0x180132954`

## callees

- `0x180004374`
- `0x180008290`
- `0x180018340`
- `0x1801398d0`
- `0x18013ab7c`
- `0x18013ac7c`

## import_xrefs

- `ESENT!JetCreateDatabase2W` at `0x180139975`
- `ESENT!JetCreateDatabase2W` at `0x180139bc2`
- `ESENT!JetCreateDatabase2W` at `0x180139975`
- `ESENT!JetCreateDatabase2W` at `0x180139bc2`
- `ESENT!JetAttachDatabase2W` at `0x1801399cb`
- `ESENT!JetAttachDatabase2W` at `0x1801399cb`
- `ESENT!JetOpenDatabaseW` at `0x180139a92`
- `ESENT!JetOpenDatabaseW` at `0x180139a92`
- `ESENT!JetCloseDatabase` at `0x180139c9b`
- `ESENT!JetCloseDatabase` at `0x180139c9b`

## pseudocode

```c
__int64 __fastcall CreateJetDatabase(
        unsigned __int64 *a1,
        unsigned __int16 *a2,
        unsigned __int64 a3,
        char a4,
        unsigned int *a5,
        bool *a6,
        bool *a7)
{
  bool *v10; // r12
  bool *v11; // r14
  unsigned int *v12; // r13
  char v13; // bp
  unsigned __int64 v14; // rsi
  unsigned int v15; // ebx
  unsigned int v16; // eax
  CHostedCacheMsgEncoding *v17; // rcx
  __int64 v18; // rdx
  unsigned int v19; // eax
  __int64 v20; // r9
  CHostedCacheMsgEncoding *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r9
  unsigned int v24; // ebx
  JET_DBID pdbid; // [rsp+98h] [rbp+20h] BYREF

  LOBYTE(pdbid) = a4;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_SSI(*((_QWORD *)WPP_GLOBAL_Control + 12), (_DWORD)a2, a3, (_DWORD)a2, (__int64)L"False", a3);
  }
  v10 = a6;
  v11 = a7;
  v12 = a5;
  pdbid = -1;
  *a6 = 0;
  v13 = 0;
  *v11 = 0;
  *v12 = -1;
  v14 = a3 >> 15;
  v15 = JetCreateDatabase2W(*a1, a2, v14, &pdbid, 0);
  if ( v15 != -1201 )
  {
    v23 = 4294966268LL;
    if ( v15 != -1028 )
    {
      if ( v15 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v18 = 19;
          goto LABEL_62;
        }
        goto LABEL_64;
      }
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 18, WPP_56cbd0d645bd32a542104af81e195d6e_Traceguids);
      }
      goto LABEL_57;
    }
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
      goto LABEL_47;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0 || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      goto LABEL_43;
    v22 = 17;
    goto LABEL_42;
  }
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 11, WPP_56cbd0d645bd32a542104af81e195d6e_Traceguids, a2);
  }
  v16 = JetAttachDatabase2W(*a1, a2, v14, 0);
  v15 = v16;
  if ( v16 == -1206 || v16 == -550 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
      goto LABEL_47;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0 || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
LABEL_43:
      if ( v21 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)v21 + 108) & 4) != 0
        && *((_BYTE *)v21 + 105) >= 4u )
      {
        WPP_SF_(*((_QWORD *)v21 + 12), 20, WPP_56cbd0d645bd32a542104af81e195d6e_Traceguids);
      }
LABEL_47:
      v15 = JetCreateDatabase2W(*a1, a2, v14, &pdbid, 0x200u);
      if ( v15 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v18 = 21;
          goto LABEL_62;
        }
        goto LABEL_64;
      }
      goto LABEL_57;
    }
    v22 = 12;
    v23 = v16;
LABEL_42:
    WPP_SF_d(*((_QWORD *)v21 + 12), v22, WPP_56cbd0d645bd32a542104af81e195d6e_Traceguids, v23);
    v21 = WPP_GLOBAL_Control;
    goto LABEL_43;
  }
  if ( v16 != -1202 && v16 != -1032 )
  {
    if ( v16 && v16 != 1007 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v18 = 14;
LABEL_62:
        v20 = v15;
        goto LABEL_63;
      }
      goto LABEL_64;
    }
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 15, WPP_56cbd0d645bd32a542104af81e195d6e_Traceguids, a2);
    }
    v13 = 1;
    v19 = JetOpenDatabaseW(*a1, a2, 0, &pdbid, 0);
    v15 = v19;
    if ( v19 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v18 = 16;
        v20 = v19;
LABEL_63:
        WPP_SF_d(*((_QWORD *)v17 + 12), v18, WPP_56cbd0d645bd32a542104af81e195d6e_Traceguids, v20);
        goto LABEL_64;
      }
      goto LABEL_64;
    }
LABEL_57:
    v24 = 0;
    *v12 = pdbid;
    *v10 = v13;
    return v24;
  }
  *v11 = 1;
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v18 = 13;
    goto LABEL_62;
  }
LABEL_64:
  v24 = TranslateJetError(v15);
  if ( pdbid != -1 )
    JetCloseDatabase(*a1, pdbid, 0);
  return v24;
}

```

## disassembly

```asm
0x1801398d0  mov     byte ptr [rsp+pdbid], r9b
0x1801398d5  push    rbx
0x1801398d6  push    rbp
0x1801398d7  push    rsi
0x1801398d8  push    rdi
0x1801398d9  push    r12
0x1801398db  push    r13
0x1801398dd  push    r14
0x1801398df  push    r15
0x1801398e1  sub     rsp, 38h
0x1801398e5  mov     rsi, r8
0x1801398e8  mov     rdi, rdx
0x1801398eb  mov     r15, rcx
0x1801398ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1801398f5  lea     rax, WPP_GLOBAL_Control
0x1801398fc  cmp     rcx, rax
0x1801398ff  jz      short loc_18013992A
0x180139901  test    byte ptr [rcx+6Ch], 4
0x180139905  jz      short loc_18013992A
0x180139907  cmp     byte ptr [rcx+69h], 4
0x18013990b  jb      short loc_18013992A
0x18013990d  mov     rcx, [rcx+60h]
0x180139911  lea     rax, aFalse_1; "False"
0x180139918  mov     [rsp+78h+var_50], r8
0x18013991d  mov     r9, rdx
0x180139920  mov     qword ptr [rsp+78h+grbit], rax
0x180139925  call    WPP_SF_SSI
0x18013992a  mov     r12, [rsp+78h+arg_28]
0x180139932  lea     r9, [rsp+78h+pdbid]; pdbid
0x18013993a  mov     r14, [rsp+78h+arg_30]
0x180139942  xor     eax, eax
0x180139944  mov     r13, [rsp+78h+arg_20]
0x18013994c  or      ecx, 0FFFFFFFFh
0x18013994f  mov     [rsp+78h+pdbid], ecx
0x180139956  mov     rdx, rdi; szFilename
0x180139959  mov     [r12], al
0x18013995d  mov     bpl, al
0x180139960  mov     [r14], al
0x180139963  mov     [r13+0], ecx
0x180139967  mov     rcx, [r15]; sesid
0x18013996a  shr     rsi, 0Fh
0x18013996e  mov     r8d, esi; cpgDatabaseSizeMax
0x180139971  mov     [rsp+78h+grbit], eax; grbit
0x180139975  call    cs:__imp_JetCreateDatabase2W
0x18013997b  mov     ebx, eax
0x18013997d  cmp     eax, 0FFFFFB4Fh
0x180139982  jnz     loc_180139B39
0x180139988  mov     rcx, cs:WPP_GLOBAL_Control
0x18013998f  lea     rax, WPP_GLOBAL_Control
0x180139996  cmp     rcx, rax
0x180139999  jz      short loc_1801399BF
0x18013999b  test    byte ptr [rcx+6Ch], 4
0x18013999f  jz      short loc_1801399BF
0x1801399a1  cmp     byte ptr [rcx+69h], 4
0x1801399a5  jb      short loc_1801399BF
0x1801399a7  mov     rcx, [rcx+60h]
0x1801399ab  lea     r8, WPP_56cbd0d645bd32a542104af81e195d6e_Traceguids
0x1801399b2  mov     edx, 0Bh
0x1801399b7  mov     r9, rdi
0x1801399ba  call    WPP_SF_S
0x1801399bf  mov     rcx, [r15]; sesid
0x1801399c2  xor     r9d, r9d; grbit
0x1801399c5  mov     r8d, esi; cpgDatabaseSizeMax
0x1801399c8  mov     rdx, rdi; szFilename
0x1801399cb  call    cs:__imp_JetAttachDatabase2W
0x1801399d1  mov     ebx, eax
0x1801399d3  cmp     eax, 0FFFFFB4Ah
0x1801399d8  jz      loc_180139B0C
0x1801399de  cmp     eax, 0FFFFFDDAh
0x1801399e3  jz      loc_180139B0C
0x1801399e9  cmp     eax, 0FFFFFB4Eh
0x1801399ee  jz      loc_180139AD3
0x1801399f4  cmp     eax, 0FFFFFBF8h
0x1801399f9  jz      loc_180139AD3
0x1801399ff  test    eax, eax
0x180139a01  jz      short loc_180139A3F
0x180139a03  cmp     eax, 3EFh
0x180139a08  jz      short loc_180139A3F
0x180139a0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180139a11  lea     rax, WPP_GLOBAL_Control
0x180139a18  cmp     rcx, rax
0x180139a1b  jz      loc_180139C80
0x180139a21  test    byte ptr [rcx+6Ch], 4
0x180139a25  jz      loc_180139C80
0x180139a2b  cmp     byte ptr [rcx+69h], 1
0x180139a2f  jb      loc_180139C80
0x180139a35  mov     edx, 0Eh
0x180139a3a  jmp     loc_180139C6D
0x180139a3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180139a46  lea     rsi, WPP_GLOBAL_Control
0x180139a4d  cmp     rcx, rsi
0x180139a50  jz      short loc_180139A76
0x180139a52  test    byte ptr [rcx+6Ch], 4
0x180139a56  jz      short loc_180139A76
0x180139a58  cmp     byte ptr [rcx+69h], 4
0x180139a5c  jb      short loc_180139A76
0x180139a5e  mov     rcx, [rcx+60h]
0x180139a62  lea     r8, WPP_56cbd0d645bd32a542104af81e195d6e_Traceguids
0x180139a69  mov     edx, 0Fh
0x180139a6e  mov     r9, rdi
0x180139a71  call    WPP_SF_S
0x180139a76  mov     rcx, [r15]; sesid
0x180139a79  lea     r9, [rsp+78h+pdbid]; pdbid
0x180139a81  xor     r8d, r8d; szConnect
0x180139a84  mov     [rsp+78h+grbit], 0; grbit
0x180139a8c  mov     rdx, rdi; szFilename
0x180139a8f  mov     bpl, 1
0x180139a92  call    cs:__imp_JetOpenDatabaseW
0x180139a98  mov     ebx, eax
0x180139a9a  test    eax, eax
0x180139a9c  jz      loc_180139C36
0x180139aa2  mov     rcx, cs:WPP_GLOBAL_Control
0x180139aa9  cmp     rcx, rsi
0x180139aac  jz      loc_180139C80
0x180139ab2  test    byte ptr [rcx+6Ch], 4
0x180139ab6  jz      loc_180139C80
0x180139abc  cmp     [rcx+69h], bpl
0x180139ac0  jb      loc_180139C80
0x180139ac6  mov     edx, 10h
0x180139acb  mov     r9d, eax
0x180139ace  jmp     loc_180139C70
0x180139ad3  mov     byte ptr [r14], 1
0x180139ad7  mov     rcx, cs:WPP_GLOBAL_Control
0x180139ade  lea     rax, WPP_GLOBAL_Control
0x180139ae5  cmp     rcx, rax
0x180139ae8  jz      loc_180139C80
0x180139aee  test    byte ptr [rcx+6Ch], 4
0x180139af2  jz      loc_180139C80
0x180139af8  cmp     byte ptr [rcx+69h], 1
0x180139afc  jb      loc_180139C80
0x180139b02  mov     edx, 0Dh
0x180139b07  jmp     loc_180139C6D
0x180139b0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180139b13  lea     r14, WPP_GLOBAL_Control
0x180139b1a  cmp     rcx, r14
0x180139b1d  jz      loc_180139BA9
0x180139b23  test    byte ptr [rcx+6Ch], 4
0x180139b27  jz      short loc_180139B83
0x180139b29  cmp     byte ptr [rcx+69h], 1
0x180139b2d  jb      short loc_180139B83
0x180139b2f  mov     edx, 0Ch
0x180139b34  mov     r9d, ebx
0x180139b37  jmp     short loc_180139B6C
0x180139b39  mov     r9d, 0FFFFFBFCh
0x180139b3f  cmp     ebx, r9d
0x180139b42  jnz     loc_180139C00
0x180139b48  mov     rcx, cs:WPP_GLOBAL_Control
0x180139b4f  lea     r14, WPP_GLOBAL_Control
0x180139b56  cmp     rcx, r14
0x180139b59  jz      short loc_180139BA9
0x180139b5b  test    byte ptr [rcx+6Ch], 4
0x180139b5f  jz      short loc_180139B83
0x180139b61  cmp     byte ptr [rcx+69h], 1
0x180139b65  jb      short loc_180139B83
0x180139b67  mov     edx, 11h
0x180139b6c  mov     rcx, [rcx+60h]
0x180139b70  lea     r8, WPP_56cbd0d645bd32a542104af81e195d6e_Traceguids
0x180139b77  call    WPP_SF_d
0x180139b7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180139b83  cmp     rcx, r14
0x180139b86  jz      short loc_180139BA9
0x180139b88  test    byte ptr [rcx+6Ch], 4
0x180139b8c  jz      short loc_180139BA9
0x180139b8e  cmp     byte ptr [rcx+69h], 4
0x180139b92  jb      short loc_180139BA9
0x180139b94  mov     rcx, [rcx+60h]
0x180139b98  lea     r8, WPP_56cbd0d645bd32a542104af81e195d6e_Traceguids
0x180139b9f  mov     edx, 14h
0x180139ba4  call    WPP_SF_
0x180139ba9  mov     rcx, [r15]; sesid
0x180139bac  lea     r9, [rsp+78h+pdbid]; pdbid
0x180139bb4  mov     r8d, esi; cpgDatabaseSizeMax
0x180139bb7  mov     [rsp+78h+grbit], 200h; grbit
0x180139bbf  mov     rdx, rdi; szFilename
0x180139bc2  call    cs:__imp_JetCreateDatabase2W
0x180139bc8  mov     ebx, eax
0x180139bca  test    eax, eax
0x180139bcc  jz      short loc_180139C36
0x180139bce  mov     rcx, cs:WPP_GLOBAL_Control
0x180139bd5  lea     rax, WPP_GLOBAL_Control
0x180139bdc  cmp     rcx, rax
0x180139bdf  jz      loc_180139C80
0x180139be5  test    byte ptr [rcx+6Ch], 4
0x180139be9  jz      loc_180139C80
0x180139bef  cmp     byte ptr [rcx+69h], 1
0x180139bf3  jb      loc_180139C80
0x180139bf9  mov     edx, 15h
0x180139bfe  jmp     short loc_180139C6D
0x180139c00  test    ebx, ebx
0x180139c02  jnz     short loc_180139C49
0x180139c04  mov     rcx, cs:WPP_GLOBAL_Control
0x180139c0b  lea     rax, WPP_GLOBAL_Control
0x180139c12  cmp     rcx, rax
0x180139c15  jz      short loc_180139C36
0x180139c17  test    byte ptr [rcx+6Ch], 4
0x180139c1b  jz      short loc_180139C36
0x180139c1d  cmp     byte ptr [rcx+69h], 4
0x180139c21  jb      short loc_180139C36
0x180139c23  mov     rcx, [rcx+60h]
0x180139c27  lea     edx, [rbx+12h]
0x180139c2a  lea     r8, WPP_56cbd0d645bd32a542104af81e195d6e_Traceguids
0x180139c31  call    WPP_SF_
0x180139c36  mov     eax, [rsp+78h+pdbid]
0x180139c3d  xor     ebx, ebx
0x180139c3f  mov     [r13+0], eax
0x180139c43  mov     [r12], bpl
0x180139c47  jmp     short loc_180139CA1
0x180139c49  mov     rcx, cs:WPP_GLOBAL_Control
0x180139c50  lea     rax, WPP_GLOBAL_Control
0x180139c57  cmp     rcx, rax
0x180139c5a  jz      short loc_180139C80
0x180139c5c  test    byte ptr [rcx+6Ch], 4
0x180139c60  jz      short loc_180139C80
0x180139c62  cmp     byte ptr [rcx+69h], 1
0x180139c66  jb      short loc_180139C80
0x180139c68  mov     edx, 13h
0x180139c6d  mov     r9d, ebx
0x180139c70  mov     rcx, [rcx+60h]
0x180139c74  lea     r8, WPP_56cbd0d645bd32a542104af81e195d6e_Traceguids
0x180139c7b  call    WPP_SF_d
0x180139c80  mov     ecx, ebx; int
0x180139c82  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180139c87  mov     edx, [rsp+78h+pdbid]; dbid
0x180139c8e  mov     ebx, eax
0x180139c90  cmp     edx, 0FFFFFFFFh
0x180139c93  jz      short loc_180139CA1
0x180139c95  mov     rcx, [r15]; sesid
0x180139c98  xor     r8d, r8d; grbit
0x180139c9b  call    cs:__imp_JetCloseDatabase
0x180139ca1  mov     eax, ebx
0x180139ca3  add     rsp, 38h
0x180139ca7  pop     r15
0x180139ca9  pop     r14
0x180139cab  pop     r13
0x180139cad  pop     r12
0x180139caf  pop     rdi
0x180139cb0  pop     rsi
0x180139cb1  pop     rbp
0x180139cb2  pop     rbx
0x180139cb3  retn
```
