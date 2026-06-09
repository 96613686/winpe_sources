# CreateJetTable(unsigned __int64 &,ulong &,PEERDIST_TABLE_INFO const &,bool,ulong *,bool *,ushort const *)

- ea: `0x180139cbc`
- end: `0x18013a20c`
- name: `?CreateJetTable@@YAKAEA_KAEAKAEBUPEERDIST_TABLE_INFO@@_NPEAKPEA_NPEBG@Z`
- size: `1360`
- prototype: `unsigned int __usercall@<eax>(unsigned __int64 *@<rcx>, unsigned int *@<rdx>, const struct PEERDIST_TABLE_INFO *@<r8>, bool@<r9b>, unsigned int *, bool *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x1800410fc`
- `0x18004153c`
- `0x180056c80`
- `0x180132b98`

## callees

- `0x1800024f0`
- `0x180004374`
- `0x180008290`
- `0x18000cf48`
- `0x180018340`
- `0x1800183a0`
- `0x180139428`
- `0x180139cbc`
- `0x18013a214`
- `0x18013a680`
- `0x18013a770`
- `0x18013ab7c`
- `0x180144882`
- `0x1801448c0`

## import_xrefs

- `ESENT!JetCreateTableColumnIndex3W` at `0x18013a05d`
- `ESENT!JetCreateTableColumnIndex3W` at `0x18013a05d`
- `ESENT!JetCloseTable` at `0x18013a141`
- `ESENT!JetCloseTable` at `0x18013a141`
- `ESENT!JetDeleteTableW` at `0x180139e64`
- `ESENT!JetDeleteTableW` at `0x180139e64`

## string_xrefs

- `0x180139f91`: `Error opening the table indicates the table does not exist already, Create new table`
- `0x180139f8a`: `Create new table`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateJetTable(
        unsigned __int64 *a1,
        unsigned int *a2,
        const struct PEERDIST_TABLE_INFO *a3,
        char a4,
        unsigned int *a5,
        bool *a6,
        JET_PCWSTR szTableName)
{
  WCHAR *v9; // r15
  const wchar_t *v11; // rax
  JET_DBID *v12; // r12
  JET_ERR v13; // eax
  JET_ERR v14; // ebx
  int v15; // ecx
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // ebx
  CHostedCacheMsgEncoding *v19; // rcx
  __int64 v20; // rdx
  const wchar_t *v21; // r9
  CHostedCacheMsgEncoding *v22; // rcx
  int v23; // edx
  int v24; // r9d
  unsigned int v25; // r12d
  CHostedCacheMsgEncoding *v26; // rcx
  __int64 v27; // rdx
  unsigned int v28; // r9d
  __int64 v29; // r8
  unsigned int *v30; // r10
  char cColumns; // [rsp+20h] [rbp-E0h]
  JET_TABLEID v33; // [rsp+48h] [rbp-B8h] BYREF
  struct PEERDIST_TABLE_INFO *v34; // [rsp+50h] [rbp-B0h]
  unsigned int *v35; // [rsp+58h] [rbp-A8h]
  JET_TABLECREATE3_W ptablecreate; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v37[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int16 v38; // [rsp+F0h] [rbp-10h]
  __m128i si128; // [rsp+F4h] [rbp-Ch]
  __m128i v40; // [rsp+104h] [rbp+4h]
  int v41; // [rsp+114h] [rbp+14h]
  _BYTE v42[256]; // [rsp+118h] [rbp+18h] BYREF
  int v43; // [rsp+218h] [rbp+118h]

  v34 = a3;
  v35 = a5;
  v9 = (WCHAR *)szTableName;
  if ( !*(_QWORD *)a3 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 105) )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 25, WPP_56cbd0d645bd32a542104af81e195d6e_Traceguids);
    }
    return 87;
  }
  if ( !szTableName )
    v9 = *(WCHAR **)(*(_QWORD *)a3 + 8LL);
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    v11 = L"True";
    if ( !a4 )
      v11 = L"False";
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      26,
      (unsigned int)WPP_56cbd0d645bd32a542104af81e195d6e_Traceguids,
      (_DWORD)v9,
      (__int64)v11);
  }
  v33 = -1;
  memset_0(&ptablecreate, 0, sizeof(ptablecreate));
  v37[0] = &CTnoJetSession::`vftable';
  v37[1] = *a1;
  v38 = 0;
  v41 = 0;
  v43 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v40 = si128;
  memset_0(v42, -1, sizeof(v42));
  *a6 = 0;
  if ( a4 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 27, WPP_56cbd0d645bd32a542104af81e195d6e_Traceguids, v9);
    }
    v12 = a2;
    v13 = JetDeleteTableW(*a1, *a2, v9);
    v14 = v13;
    if ( v13 != -1305 && v13 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          28,
          (unsigned int)WPP_56cbd0d645bd32a542104af81e195d6e_Traceguids,
          (_DWORD)v9,
          v13);
      }
      v15 = v14;
      goto LABEL_86;
    }
    v16 = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 29, WPP_56cbd0d645bd32a542104af81e195d6e_Traceguids, v9);
    }
    v16 = CTnoJetSession::OpenTable((CTnoJetSession *)v37, *a2, v9, 0, 0, 0, &v33);
    if ( v16 != 1168 )
    {
      v17 = QueryJetTableColumnInfo(a1, &v33, v34, v35);
      v18 = v17;
      if ( !v17 )
      {
        *a6 = 1;
        goto LABEL_87;
      }
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_87;
      }
      v20 = 38;
      goto LABEL_51;
    }
    v12 = a2;
  }
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    v21 = L"Error opening the table indicates the table does not exist already, Create new table";
    if ( v16 != 1168 )
      v21 = L"Create new table";
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      30,
      (unsigned int)WPP_56cbd0d645bd32a542104af81e195d6e_Traceguids,
      (_DWORD)v21,
      (__int64)v9);
  }
  v17 = InitializeTableFromSchema(v34, &ptablecreate);
  v18 = v17;
  if ( v17 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_87;
    }
    v20 = 31;
LABEL_51:
    WPP_SF_d(*((_QWORD *)v19 + 12), v20, WPP_56cbd0d645bd32a542104af81e195d6e_Traceguids, v17);
    goto LABEL_87;
  }
  ptablecreate.szTableName = v9;
  if ( ptablecreate.cColumns > 0x20 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_58;
    }
    v23 = 32;
    cColumns = ptablecreate.cColumns;
    v24 = (int)v9;
LABEL_57:
    WPP_SF_Sd(*((_QWORD *)v22 + 12), v23, (unsigned int)WPP_56cbd0d645bd32a542104af81e195d6e_Traceguids, v24, cColumns);
LABEL_58:
    v18 = 774;
    goto LABEL_87;
  }
  v25 = JetCreateTableColumnIndex3W(*a1, *v12, &ptablecreate);
  if ( !v25 )
  {
    v28 = ptablecreate.cColumns;
    if ( ptablecreate.cCreated == ptablecreate.cColumns + ptablecreate.cIndexes + 1 )
    {
      v29 = 0;
      if ( !ptablecreate.cColumns )
        goto LABEL_79;
      v30 = v35;
      do
      {
        if ( (unsigned int)v29 >= 0x20 )
          break;
        v30[v29] = ptablecreate.rgcolumncreate[(unsigned int)v29].columnid;
        v29 = (unsigned int)(v29 + 1);
      }
      while ( (unsigned int)v29 < v28 );
      if ( (unsigned int)v29 >= v28 )
      {
LABEL_79:
        v25 = JetCloseTable(*a1, ptablecreate.tableid);
        if ( !v25 )
          goto LABEL_87;
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          goto LABEL_85;
        }
        v27 = 36;
        goto LABEL_84;
      }
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_58;
      }
      v23 = 35;
      cColumns = v28;
    }
    else
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_58;
      }
      v23 = 34;
      cColumns = ptablecreate.cCreated;
    }
    v24 = (int)ptablecreate.szTableName;
    goto LABEL_57;
  }
  v26 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
    || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    goto LABEL_85;
  }
  v27 = 33;
LABEL_84:
  WPP_SF_d(*((_QWORD *)v26 + 12), v27, WPP_56cbd0d645bd32a542104af81e195d6e_Traceguids, v25);
LABEL_85:
  v15 = v25;
LABEL_86:
  v18 = TranslateJetError(v15);
LABEL_87:
  operator delete(ptablecreate.rgcolumncreate);
  ptablecreate.rgcolumncreate = 0;
  operator delete(ptablecreate.rgindexcreate);
  ptablecreate.rgindexcreate = 0;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      39,
      (unsigned int)WPP_56cbd0d645bd32a542104af81e195d6e_Traceguids,
      (_DWORD)v9,
      v18);
  }
  CTnoJetSession::~CTnoJetSession((CTnoJetSession *)v37);
  return v18;
}

```

## disassembly

```asm
0x180139cbc  mov     [rsp-8+arg_18], rbx
0x180139cc1  push    rbp
0x180139cc2  push    rsi
0x180139cc3  push    rdi
0x180139cc4  push    r12
0x180139cc6  push    r13
0x180139cc8  push    r14
0x180139cca  push    r15
0x180139ccc  lea     rbp, [rsp-130h]
0x180139cd4  sub     rsp, 230h
0x180139cdb  mov     rax, cs:__security_cookie
0x180139ce2  xor     rax, rsp
0x180139ce5  mov     [rbp+160h+var_40], rax
0x180139cec  mov     bl, r9b
0x180139cef  mov     [rsp+260h+var_210], r8
0x180139cf4  mov     [rsp+260h+var_220], rdx
0x180139cf9  mov     r13, rcx
0x180139cfc  mov     rcx, [rbp+160h+arg_20]
0x180139d03  mov     [rsp+260h+var_208], rcx
0x180139d08  mov     r12, [rbp+160h+arg_28]
0x180139d0f  mov     r15, [rbp+160h+szTableName]
0x180139d16  mov     rax, [r8]
0x180139d19  test    rax, rax
0x180139d1c  jnz     short loc_180139D5D
0x180139d1e  lea     rsi, WPP_GLOBAL_Control
0x180139d25  mov     rcx, cs:WPP_GLOBAL_Control
0x180139d2c  cmp     rcx, rsi
0x180139d2f  jz      short loc_180139D53
0x180139d31  mov     dil, 4
0x180139d34  test    [rcx+6Ch], dil
0x180139d38  jz      short loc_180139D53
0x180139d3a  cmp     byte ptr [rcx+69h], 1
0x180139d3e  jb      short loc_180139D53
0x180139d40  lea     edx, [rax+19h]
0x180139d43  lea     r8, WPP_56cbd0d645bd32a542104af81e195d6e_Traceguids
0x180139d4a  mov     rcx, [rcx+60h]
0x180139d4e  call    WPP_SF_
0x180139d53  mov     eax, 57h ; 'W'
0x180139d58  jmp     loc_18013A1E2
0x180139d5d  test    r15, r15
0x180139d60  jnz     short loc_180139D66
0x180139d62  mov     r15, [rax+8]
0x180139d66  lea     rsi, WPP_GLOBAL_Control
0x180139d6d  lea     r14, WPP_56cbd0d645bd32a542104af81e195d6e_Traceguids
0x180139d74  mov     dil, 4
0x180139d77  mov     rcx, cs:WPP_GLOBAL_Control
0x180139d7e  cmp     rcx, rsi
0x180139d81  jz      short loc_180139DBC
0x180139d83  test    [rcx+6Ch], dil
0x180139d87  jz      short loc_180139DBC
0x180139d89  cmp     [rcx+69h], dil
0x180139d8d  jb      short loc_180139DBC
0x180139d8f  lea     rdx, aFalse_1; "False"
0x180139d96  lea     rax, aTrue_1; "True"
0x180139d9d  test    bl, bl
0x180139d9f  cmovz   rax, rdx
0x180139da3  mov     edx, 1Ah
0x180139da8  mov     qword ptr [rsp+260h+var_240], rax
0x180139dad  mov     r9, r15
0x180139db0  mov     r8, r14
0x180139db3  mov     rcx, [rcx+60h]
0x180139db7  call    WPP_SF_SS
0x180139dbc  mov     [rsp+260h+var_218], 0FFFFFFFFFFFFFFFFh
0x180139dc5  xor     edx, edx; Val
0x180139dc7  lea     r8d, [rdx+78h]; Size
0x180139dcb  lea     rcx, [rsp+260h+ptablecreate]; void *
0x180139dd0  call    memset_0
0x180139dd5  lea     rax, ??_7CTnoJetSession@@6B@; const CTnoJetSession::`vftable'
0x180139ddc  mov     [rbp+160h+var_180], rax
0x180139de0  mov     rax, [r13+0]
0x180139de4  mov     [rbp+160h+var_178], rax
0x180139de8  xor     eax, eax
0x180139dea  mov     [rbp+160h+var_170], ax
0x180139dee  mov     [rbp+160h+var_14C], eax
0x180139df1  mov     [rbp+160h+var_48], eax
0x180139df7  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180139dff  movups  [rbp+160h+var_16C], xmm0
0x180139e03  movups  [rbp+160h+var_15C], xmm0
0x180139e07  mov     r8d, 100h; Size
0x180139e0d  or      rdx, 0FFFFFFFFFFFFFFFFh; Val
0x180139e11  lea     rcx, [rbp+160h+var_148]; void *
0x180139e15  call    memset_0
0x180139e1a  nop
0x180139e1b  mov     byte ptr [r12], 0
0x180139e20  test    bl, bl
0x180139e22  jz      loc_180139EB5
0x180139e28  mov     rcx, cs:WPP_GLOBAL_Control
0x180139e2f  cmp     rcx, rsi
0x180139e32  jz      short loc_180139E54
0x180139e34  test    [rcx+6Ch], dil
0x180139e38  jz      short loc_180139E54
0x180139e3a  cmp     [rcx+69h], dil
0x180139e3e  jb      short loc_180139E54
0x180139e40  mov     edx, 1Bh
0x180139e45  mov     r9, r15
0x180139e48  mov     r8, r14
0x180139e4b  mov     rcx, [rcx+60h]
0x180139e4f  call    WPP_SF_S
0x180139e54  mov     r8, r15; szTableName
0x180139e57  mov     r12, [rsp+260h+var_220]
0x180139e5c  mov     edx, [r12]; dbid
0x180139e60  mov     rcx, [r13+0]; sesid
0x180139e64  call    cs:__imp_JetDeleteTableW
0x180139e6a  mov     ebx, eax
0x180139e6c  cmp     eax, 0FFFFFAE7h
0x180139e71  jz      short loc_180139EAE
0x180139e73  test    eax, eax
0x180139e75  jz      short loc_180139EAE
0x180139e77  mov     rcx, cs:WPP_GLOBAL_Control
0x180139e7e  cmp     rcx, rsi
0x180139e81  jz      short loc_180139EA7
0x180139e83  test    [rcx+6Ch], dil
0x180139e87  jz      short loc_180139EA7
0x180139e89  cmp     byte ptr [rcx+69h], 1
0x180139e8d  jb      short loc_180139EA7
0x180139e8f  mov     edx, 1Ch
0x180139e94  mov     [rsp+260h+var_240], eax
0x180139e98  mov     r9, r15
0x180139e9b  mov     r8, r14
0x180139e9e  mov     rcx, [rcx+60h]
0x180139ea2  call    WPP_SF_Sd
0x180139ea7  mov     ecx, ebx
0x180139ea9  jmp     loc_18013A17D
0x180139eae  xor     eax, eax
0x180139eb0  jmp     loc_180139F72
0x180139eb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180139ebc  cmp     rcx, rsi
0x180139ebf  jz      short loc_180139EE1
0x180139ec1  test    [rcx+6Ch], dil
0x180139ec5  jz      short loc_180139EE1
0x180139ec7  cmp     [rcx+69h], dil
0x180139ecb  jb      short loc_180139EE1
0x180139ecd  mov     edx, 1Dh
0x180139ed2  mov     r9, r15
0x180139ed5  mov     r8, r14
0x180139ed8  mov     rcx, [rcx+60h]
0x180139edc  call    WPP_SF_S
0x180139ee1  lea     rax, [rsp+260h+var_218]
0x180139ee6  mov     [rsp+260h+var_230], rax; JET_TABLEID *
0x180139eeb  mov     [rsp+260h+var_238], 0; JET_GRBIT
0x180139ef3  mov     [rsp+260h+var_240], 0; unsigned int
0x180139efb  xor     r9d, r9d; void *
0x180139efe  mov     r8, r15; unsigned __int16 *
0x180139f01  mov     rdx, [rsp+260h+var_220]
0x180139f06  mov     edx, [rdx]; unsigned int
0x180139f08  lea     rcx, [rbp+160h+var_180]; this
0x180139f0c  call    ?OpenTable@CTnoJetSession@@UEAAKKPEBGPEBXKKPEA_K@Z; CTnoJetSession::OpenTable(ulong,ushort const *,void const *,ulong,ulong,unsigned __int64 *)
0x180139f11  cmp     eax, 490h
0x180139f16  jz      short loc_180139F6D
0x180139f18  mov     r9, [rsp+260h+var_208]; unsigned int *
0x180139f1d  mov     r8, [rsp+260h+var_210]; struct PEERDIST_TABLE_INFO *
0x180139f22  lea     rdx, [rsp+260h+var_218]; unsigned __int64 *
0x180139f27  mov     rcx, r13; unsigned __int64 *
0x180139f2a  call    ?QueryJetTableColumnInfo@@YAKAEA_K0AEBUPEERDIST_TABLE_INFO@@PEAK@Z; QueryJetTableColumnInfo(unsigned __int64 &,unsigned __int64 &,PEERDIST_TABLE_INFO const &,ulong *)
0x180139f2f  mov     ebx, eax
0x180139f31  test    eax, eax
0x180139f33  jz      short loc_180139F63
0x180139f35  mov     rcx, cs:WPP_GLOBAL_Control
0x180139f3c  cmp     rcx, rsi
0x180139f3f  jz      loc_18013A184
0x180139f45  test    [rcx+6Ch], dil
0x180139f49  jz      loc_18013A184
0x180139f4f  cmp     byte ptr [rcx+69h], 1
0x180139f53  jb      loc_18013A184
0x180139f59  mov     edx, 26h ; '&'
0x180139f5e  jmp     loc_180139FF5
0x180139f63  mov     byte ptr [r12], 1
0x180139f68  jmp     loc_18013A184
0x180139f6d  mov     r12, [rsp+260h+var_220]
0x180139f72  mov     rcx, cs:WPP_GLOBAL_Control
0x180139f79  cmp     rcx, rsi
0x180139f7c  jz      short loc_180139FB7
0x180139f7e  test    [rcx+6Ch], dil
0x180139f82  jz      short loc_180139FB7
0x180139f84  cmp     [rcx+69h], dil
0x180139f88  jb      short loc_180139FB7
0x180139f8a  lea     rdx, aCreateNewTable; "Create new table"
0x180139f91  lea     r9, aErrorOpeningTh; "Error opening the table indicates the t"...
0x180139f98  cmp     eax, 490h
0x180139f9d  cmovnz  r9, rdx
0x180139fa1  mov     edx, 1Eh
0x180139fa6  mov     qword ptr [rsp+260h+var_240], r15
0x180139fab  mov     r8, r14
0x180139fae  mov     rcx, [rcx+60h]
0x180139fb2  call    WPP_SF_SS
0x180139fb7  lea     rdx, [rsp+260h+ptablecreate]; struct tagJET_TABLECREATE3_W *
0x180139fbc  mov     rcx, [rsp+260h+var_210]; struct PEERDIST_TABLE_INFO *
0x180139fc1  call    ?InitializeTableFromSchema@@YAKAEBUPEERDIST_TABLE_INFO@@PEAUtagJET_TABLECREATE3_W@@@Z; InitializeTableFromSchema(PEERDIST_TABLE_INFO const &,tagJET_TABLECREATE3_W *)
0x180139fc6  mov     ebx, eax
0x180139fc8  test    eax, eax
0x180139fca  jz      short loc_18013A009
0x180139fcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180139fd3  cmp     rcx, rsi
0x180139fd6  jz      loc_18013A184
0x180139fdc  test    [rcx+6Ch], dil
0x180139fe0  jz      loc_18013A184
0x180139fe6  cmp     byte ptr [rcx+69h], 1
0x180139fea  jb      loc_18013A184
0x180139ff0  mov     edx, 1Fh
0x180139ff5  mov     r9d, eax
0x180139ff8  mov     r8, r14
0x180139ffb  mov     rcx, [rcx+60h]
0x180139fff  call    WPP_SF_d
0x18013a004  jmp     loc_18013A184
0x18013a009  mov     [rsp+260h+ptablecreate.szTableName], r15
0x18013a00e  mov     eax, [rbp+160h+ptablecreate.cColumns]
0x18013a011  cmp     eax, 20h ; ' '
0x18013a014  jbe     short loc_18013A050
0x18013a016  mov     rcx, cs:WPP_GLOBAL_Control
0x18013a01d  cmp     rcx, rsi
0x18013a020  jz      short loc_18013A046
0x18013a022  test    [rcx+6Ch], dil
0x18013a026  jz      short loc_18013A046
0x18013a028  cmp     byte ptr [rcx+69h], 1
0x18013a02c  jb      short loc_18013A046
0x18013a02e  mov     edx, 20h ; ' '
0x18013a033  mov     [rsp+260h+var_240], eax
0x18013a037  mov     r9, r15
0x18013a03a  mov     r8, r14
0x18013a03d  mov     rcx, [rcx+60h]
0x18013a041  call    WPP_SF_Sd
0x18013a046  mov     ebx, 306h
0x18013a04b  jmp     loc_18013A184
0x18013a050  lea     r8, [rsp+260h+ptablecreate]; ptablecreate
0x18013a055  mov     edx, [r12]; dbid
0x18013a059  mov     rcx, [r13+0]; sesid
0x18013a05d  call    cs:__imp_JetCreateTableColumnIndex3W
0x18013a063  mov     r12d, eax
0x18013a066  test    eax, eax
0x18013a068  jz      short loc_18013A098
0x18013a06a  mov     rcx, cs:WPP_GLOBAL_Control
0x18013a071  cmp     rcx, rsi
0x18013a074  jz      loc_18013A17A
0x18013a07a  test    [rcx+6Ch], dil
0x18013a07e  jz      loc_18013A17A
0x18013a084  cmp     byte ptr [rcx+69h], 1
0x18013a088  jb      loc_18013A17A
0x18013a08e  mov     edx, 21h ; '!'
0x18013a093  jmp     loc_18013A16B
0x18013a098  mov     r9d, [rbp+160h+ptablecreate.cColumns]
0x18013a09c  mov     ecx, [rbp+160h+ptablecreate.cIndexes]
0x18013a09f  inc     ecx
0x18013a0a1  add     ecx, r9d
0x18013a0a4  mov     eax, [rbp+160h+ptablecreate.cCreated]
0x18013a0a7  cmp     eax, ecx
0x18013a0a9  jz      short loc_18013A0D6
0x18013a0ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18013a0b2  cmp     rcx, rsi
0x18013a0b5  jz      short loc_18013A046
0x18013a0b7  test    [rcx+6Ch], dil
0x18013a0bb  jz      short loc_18013A046
0x18013a0bd  cmp     byte ptr [rcx+69h], 1
0x18013a0c1  jb      short loc_18013A046
0x18013a0c3  mov     edx, 22h ; '"'
0x18013a0c8  mov     [rsp+260h+var_240], eax
0x18013a0cc  mov     r9, [rsp+260h+ptablecreate.szTableName]
0x18013a0d1  jmp     loc_18013A03A
0x18013a0d6  xor     r8d, r8d
0x18013a0d9  test    r9d, r9d
0x18013a0dc  jz      short loc_18013A139
0x18013a0de  mov     r10, [rsp+260h+var_208]
0x18013a0e3  cmp     r8d, 20h ; ' '
0x18013a0e7  jnb     short loc_18013A104
0x18013a0e9  mov     edx, r8d
0x18013a0ec  imul    rcx, rdx, 38h ; '8'
0x18013a0f0  mov     rax, [rbp+160h+ptablecreate.rgcolumncreate]
0x18013a0f4  mov     ecx, [rcx+rax+30h]
0x18013a0f8  mov     [r10+r8*4], ecx
0x18013a0fc  inc     r8d
0x18013a0ff  cmp     r8d, r9d
0x18013a102  jb      short loc_18013A0E3
0x18013a104  cmp     r8d, r9d
0x18013a107  jnb     short loc_18013A139
0x18013a109  mov     rcx, cs:WPP_GLOBAL_Control
0x18013a110  cmp     rcx, rsi
0x18013a113  jz      loc_18013A046
0x18013a119  test    [rcx+6Ch], dil
0x18013a11d  jz      loc_18013A046
0x18013a123  cmp     byte ptr [rcx+69h], 1
0x18013a127  jb      loc_18013A046
0x18013a12d  mov     edx, 23h ; '#'
0x18013a132  mov     [rsp+260h+var_240], r9d
0x18013a137  jmp     short loc_18013A0CC
0x18013a139  mov     rdx, [rbp+160h+ptablecreate.tableid]; tableid
0x18013a13d  mov     rcx, [r13+0]; sesid
0x18013a141  call    cs:__imp_JetCloseTable
0x18013a147  mov     r12d, eax
0x18013a14a  test    eax, eax
0x18013a14c  jz      short loc_18013A184
0x18013a14e  mov     rcx, cs:WPP_GLOBAL_Control
0x18013a155  cmp     rcx, rsi
0x18013a158  jz      short loc_18013A17A
0x18013a15a  test    [rcx+6Ch], dil
0x18013a15e  jz      short loc_18013A17A
0x18013a160  cmp     byte ptr [rcx+69h], 1
0x18013a164  jb      short loc_18013A17A
0x18013a166  mov     edx, 24h ; '$'
0x18013a16b  mov     r9d, r12d
0x18013a16e  mov     r8, r14
0x18013a171  mov     rcx, [rcx+60h]
  ... truncated ...
```
