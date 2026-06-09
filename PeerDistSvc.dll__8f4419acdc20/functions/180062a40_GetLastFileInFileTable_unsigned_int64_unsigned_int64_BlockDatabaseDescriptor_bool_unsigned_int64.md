# GetLastFileInFileTable(unsigned __int64,unsigned __int64,_BlockDatabaseDescriptor *,bool *,unsigned __int64 *)

- ea: `0x180062a40`
- end: `0x180062d15`
- name: `?GetLastFileInFileTable@@YAK_K0PEAU_BlockDatabaseDescriptor@@PEA_NPEA_K@Z`
- size: `725`
- prototype: `unsigned int __usercall@<eax>(JET_SESID sesid@<rcx>, JET_TABLEID tableid@<rdx>, struct _BlockDatabaseDescriptor *@<r8>, bool *@<r9>, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1800468e4`

## callees

- `0x180004374`
- `0x1800082d0`
- `0x18000ceac`
- `0x180051e9c`
- `0x180062a40`
- `0x18013ab7c`

## import_xrefs

- `ESENT!JetRetrieveColumns` at `0x180062c20`
- `ESENT!JetRetrieveColumns` at `0x180062c20`
- `ESENT!JetMove` at `0x180062b4b`
- `ESENT!JetMove` at `0x180062b4b`
- `ESENT!JetSetCurrentIndexW` at `0x180062acd`
- `ESENT!JetSetCurrentIndexW` at `0x180062acd`

## pseudocode

```c
__int64 __fastcall GetLastFileInFileTable(
        JET_SESID sesid,
        JET_TABLEID tableid,
        struct _BlockDatabaseDescriptor *a3,
        bool *a4,
        unsigned __int64 *a5)
{
  unsigned __int64 *v9; // r15
  JET_ERR v10; // ecx
  unsigned int v11; // ebx
  CHostedCacheMsgEncoding *v12; // r10
  __int64 v13; // rdx
  bool v14; // di
  JET_ERR v15; // ecx
  JET_COLUMNID v16; // eax
  JET_ERR v17; // ecx
  const wchar_t *v18; // r9
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v21; // [rsp+A8h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 81, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids);
  }
  v9 = a5;
  v21 = 0;
  *(_OWORD *)&pretrievecolumn.columnid = 0;
  *a5 = 0;
  *(_OWORD *)&pretrievecolumn.cbData = 0;
  *a4 = 0;
  *(_OWORD *)&pretrievecolumn.itagSequence = 0;
  v10 = JetSetCurrentIndexW(sesid, tableid, L"FileIdIndex");
  if ( !v10 )
  {
    v14 = 1;
    v15 = JetMove(sesid, tableid, 0x7FFFFFFF, 1u);
    if ( v15 == -1603 )
    {
      v14 = 0;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 83, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids);
        v12 = WPP_GLOBAL_Control;
      }
      v21 = 0;
    }
    else
    {
      if ( v15 )
      {
        v11 = TranslateJetError(v15);
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
          return v11;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0 || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
          goto LABEL_32;
        v13 = 84;
        goto LABEL_10;
      }
      v16 = *((_DWORD *)a3 + 158);
      *(&pretrievecolumn.columnid + 1) = 0;
      pretrievecolumn.columnid = v16;
      memset(&pretrievecolumn.cbData, 0, 32);
      pretrievecolumn.pvData = &v21;
      pretrievecolumn.cbData = 8;
      pretrievecolumn.itagSequence = 1;
      v17 = JetRetrieveColumns(sesid, tableid, &pretrievecolumn, 1u);
      if ( v17 )
      {
        v11 = TranslateJetError(v17);
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
          return v11;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0 || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
          goto LABEL_32;
        v13 = 85;
        goto LABEL_10;
      }
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 86, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids);
        v12 = WPP_GLOBAL_Control;
      }
    }
    v11 = 0;
    *v9 = v21;
    *a4 = v14;
    goto LABEL_32;
  }
  v11 = TranslateJetError(v10);
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    return v11;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v13 = 82;
LABEL_10:
    WPP_SF_Dd(*((_QWORD *)v12 + 12), v13, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids);
    v12 = WPP_GLOBAL_Control;
  }
LABEL_32:
  if ( v12 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)v12 + 108) & 4) != 0
    && *((_BYTE *)v12 + 105) >= 4u )
  {
    v18 = L"Y";
    if ( !*a4 )
      v18 = (const wchar_t *)L"N";
    WPP_SF_SID(
      *((_QWORD *)v12 + 12),
      87,
      (unsigned int)WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids,
      (_DWORD)v18,
      *v9,
      v11);
  }
  return v11;
}

```

## disassembly

```asm
0x180062a40  mov     [rsp-28h+arg_0], rbx
0x180062a45  mov     [rsp-28h+arg_8], rsi
0x180062a4a  push    rbp
0x180062a4b  push    rdi
0x180062a4c  push    r12
0x180062a4e  push    r14
0x180062a50  push    r15
0x180062a52  mov     rbp, rsp
0x180062a55  sub     rsp, 60h
0x180062a59  mov     r12, r9
0x180062a5c  mov     r14, r8
0x180062a5f  mov     rbx, rdx
0x180062a62  mov     rsi, rcx
0x180062a65  mov     rcx, cs:WPP_GLOBAL_Control
0x180062a6c  lea     rax, WPP_GLOBAL_Control
0x180062a73  cmp     rcx, rax
0x180062a76  jz      short loc_180062A99
0x180062a78  test    byte ptr [rcx+6Ch], 4
0x180062a7c  jz      short loc_180062A99
0x180062a7e  cmp     byte ptr [rcx+69h], 4
0x180062a82  jb      short loc_180062A99
0x180062a84  mov     rcx, [rcx+60h]
0x180062a88  lea     r8, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids
0x180062a8f  mov     edx, 51h ; 'Q'
0x180062a94  call    WPP_SF_
0x180062a99  mov     r15, [rbp+arg_20]
0x180062a9d  xorps   xmm0, xmm0
0x180062aa0  mov     r8, cs:off_180161538; szIndexName
0x180062aa7  mov     rdx, rbx; tableid
0x180062aaa  mov     rcx, rsi; sesid
0x180062aad  mov     [rbp+arg_18], 0
0x180062ab5  movups  xmmword ptr [rbp+pretrievecolumn.columnid], xmm0
0x180062ab9  mov     qword ptr [r15], 0
0x180062ac0  movups  xmmword ptr [rbp+pretrievecolumn.cbData], xmm0
0x180062ac4  mov     byte ptr [r12], 0
0x180062ac9  movups  xmmword ptr [rbp+pretrievecolumn.itagSequence], xmm0
0x180062acd  call    cs:__imp_JetSetCurrentIndexW
0x180062ad3  mov     ecx, eax; int
0x180062ad5  test    eax, eax
0x180062ad7  jz      short loc_180062B37
0x180062ad9  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180062ade  mov     ebx, eax
0x180062ae0  mov     r10, cs:WPP_GLOBAL_Control
0x180062ae7  lea     rsi, WPP_GLOBAL_Control
0x180062aee  cmp     r10, rsi
0x180062af1  jz      loc_180062CFA
0x180062af7  test    byte ptr [r10+6Ch], 4
0x180062afc  jz      loc_180062CAF
0x180062b02  mov     edi, 1
0x180062b07  cmp     [r10+69h], dil
0x180062b0b  jb      loc_180062CAF
0x180062b11  lea     edx, [rdi+51h]
0x180062b14  mov     r9d, ecx
0x180062b17  mov     dword ptr [rsp+60h+var_40], eax
0x180062b1b  mov     rcx, [r10+60h]
0x180062b1f  lea     r8, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids
0x180062b26  call    WPP_SF_Dd
0x180062b2b  mov     r10, cs:WPP_GLOBAL_Control
0x180062b32  jmp     loc_180062CAF
0x180062b37  mov     edi, 1
0x180062b3c  mov     r8d, 7FFFFFFFh; cRow
0x180062b42  mov     r9d, edi; grbit
0x180062b45  mov     rdx, rbx; tableid
0x180062b48  mov     rcx, rsi; sesid
0x180062b4b  call    cs:__imp_JetMove
0x180062b51  mov     ecx, eax; int
0x180062b53  cmp     eax, 0FFFFF9BDh
0x180062b58  jnz     short loc_180062BA7
0x180062b5a  xor     dil, dil
0x180062b5d  mov     r10, cs:WPP_GLOBAL_Control
0x180062b64  lea     rsi, WPP_GLOBAL_Control
0x180062b6b  cmp     r10, rsi
0x180062b6e  jz      short loc_180062B9A
0x180062b70  test    byte ptr [r10+6Ch], 4
0x180062b75  jz      short loc_180062B9A
0x180062b77  cmp     byte ptr [r10+69h], 4
0x180062b7c  jb      short loc_180062B9A
0x180062b7e  mov     rcx, [r10+60h]
0x180062b82  lea     r8, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids
0x180062b89  mov     edx, 53h ; 'S'
0x180062b8e  call    WPP_SF_
0x180062b93  mov     r10, cs:WPP_GLOBAL_Control
0x180062b9a  mov     [rbp+arg_18], 0
0x180062ba2  jmp     loc_180062CA2
0x180062ba7  test    ecx, ecx
0x180062ba9  jz      short loc_180062BE8
0x180062bab  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180062bb0  mov     ebx, eax
0x180062bb2  mov     r10, cs:WPP_GLOBAL_Control
0x180062bb9  lea     rsi, WPP_GLOBAL_Control
0x180062bc0  cmp     r10, rsi
0x180062bc3  jz      loc_180062CFA
0x180062bc9  test    byte ptr [r10+6Ch], 4
0x180062bce  jz      loc_180062CAF
0x180062bd4  cmp     [r10+69h], dil
0x180062bd8  jb      loc_180062CAF
0x180062bde  mov     edx, 54h ; 'T'
0x180062be3  jmp     loc_180062B14
0x180062be8  mov     eax, [r14+278h]
0x180062bef  lea     r8, [rbp+pretrievecolumn]; pretrievecolumn
0x180062bf3  xorps   xmm0, xmm0
0x180062bf6  mov     r9d, edi; cretrievecolumn
0x180062bf9  movups  xmmword ptr [rbp+pretrievecolumn.columnid], xmm0
0x180062bfd  mov     [rbp+pretrievecolumn.columnid], eax
0x180062c00  mov     rdx, rbx; tableid
0x180062c03  lea     rax, [rbp+arg_18]
0x180062c07  mov     rcx, rsi; sesid
0x180062c0a  movups  xmmword ptr [rbp+pretrievecolumn.cbData], xmm0
0x180062c0e  mov     [rbp+pretrievecolumn.pvData], rax
0x180062c12  movups  xmmword ptr [rbp+pretrievecolumn.itagSequence], xmm0
0x180062c16  mov     [rbp+pretrievecolumn.cbData], 8
0x180062c1d  mov     [rbp+pretrievecolumn.itagSequence], edi
0x180062c20  call    cs:__imp_JetRetrieveColumns
0x180062c26  mov     ecx, eax; int
0x180062c28  test    eax, eax
0x180062c2a  jz      short loc_180062C61
0x180062c2c  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180062c31  mov     ebx, eax
0x180062c33  mov     r10, cs:WPP_GLOBAL_Control
0x180062c3a  lea     rsi, WPP_GLOBAL_Control
0x180062c41  cmp     r10, rsi
0x180062c44  jz      loc_180062CFA
0x180062c4a  test    byte ptr [r10+6Ch], 4
0x180062c4f  jz      short loc_180062CAF
0x180062c51  cmp     [r10+69h], dil
0x180062c55  jb      short loc_180062CAF
0x180062c57  mov     edx, 55h ; 'U'
0x180062c5c  jmp     loc_180062B14
0x180062c61  mov     r10, cs:WPP_GLOBAL_Control
0x180062c68  lea     rsi, WPP_GLOBAL_Control
0x180062c6f  cmp     r10, rsi
0x180062c72  jz      short loc_180062CA2
0x180062c74  test    byte ptr [r10+6Ch], 4
0x180062c79  jz      short loc_180062CA2
0x180062c7b  cmp     byte ptr [r10+69h], 4
0x180062c80  jb      short loc_180062CA2
0x180062c82  mov     r9, [rbp+arg_18]
0x180062c86  lea     r8, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids
0x180062c8d  mov     rcx, [r10+60h]
0x180062c91  mov     edx, 56h ; 'V'
0x180062c96  call    WPP_SF_q
0x180062c9b  mov     r10, cs:WPP_GLOBAL_Control
0x180062ca2  mov     rax, [rbp+arg_18]
0x180062ca6  xor     ebx, ebx
0x180062ca8  mov     [r15], rax
0x180062cab  mov     [r12], dil
0x180062caf  cmp     r10, rsi
0x180062cb2  jz      short loc_180062CFA
0x180062cb4  test    byte ptr [r10+6Ch], 4
0x180062cb9  jz      short loc_180062CFA
0x180062cbb  cmp     byte ptr [r10+69h], 4
0x180062cc0  jb      short loc_180062CFA
0x180062cc2  mov     rcx, [r15]
0x180062cc5  lea     rax, aN; "N"
0x180062ccc  cmp     byte ptr [r12], 0
0x180062cd1  lea     r9, aY; "Y"
0x180062cd8  mov     [rsp+60h+var_38], ebx
0x180062cdc  lea     r8, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids
0x180062ce3  mov     [rsp+60h+var_40], rcx
0x180062ce8  cmovz   r9, rax
0x180062cec  mov     rcx, [r10+60h]
0x180062cf0  mov     edx, 57h ; 'W'
0x180062cf5  call    WPP_SF_SID
0x180062cfa  lea     r11, [rsp+60h+var_s0]
0x180062cff  mov     eax, ebx
0x180062d01  mov     rbx, [r11+30h]
0x180062d05  mov     rsi, [r11+38h]
0x180062d09  mov     rsp, r11
0x180062d0c  pop     r15
0x180062d0e  pop     r14
0x180062d10  pop     r12
0x180062d12  pop     rdi
0x180062d13  pop     rbp
0x180062d14  retn
```
