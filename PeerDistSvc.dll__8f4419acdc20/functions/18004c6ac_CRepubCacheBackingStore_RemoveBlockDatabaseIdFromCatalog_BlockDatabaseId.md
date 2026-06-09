# CRepubCacheBackingStore::RemoveBlockDatabaseIdFromCatalog(_BlockDatabaseId)

- ea: `0x18004c6ac`
- end: `0x18004cbf3`
- name: `?RemoveBlockDatabaseIdFromCatalog@CRepubCacheBackingStore@@AEAAKU_BlockDatabaseId@@@Z`
- size: `1351`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180043b38`

## callees

- `0x1800024f0`
- `0x180003498`
- `0x180004374`
- `0x180008290`
- `0x18000ceac`
- `0x18004c6ac`
- `0x180051868`
- `0x180139428`
- `0x180139630`
- `0x180139820`
- `0x18013a410`
- `0x18013a680`
- `0x18013aaf0`
- `0x18013ab7c`
- `0x180144882`
- `0x1801448c0`

## import_xrefs

- `RPCRT4!UuidEqual` at `0x18004ca4d`
- `RPCRT4!UuidEqual` at `0x18004ca4d`
- `ESENT!JetRetrieveColumns` at `0x18004c984`
- `ESENT!JetRetrieveColumns` at `0x18004c984`
- `ESENT!JetMove` at `0x18004c9e5`
- `ESENT!JetMove` at `0x18004c9e5`
- `ESENT!JetDelete` at `0x18004cb00`
- `ESENT!JetDelete` at `0x18004cb00`

## pseudocode

```c
__int64 __fastcall CRepubCacheBackingStore::RemoveBlockDatabaseIdFromCatalog(__int64 a1, __int16 *a2, int a3)
{
  _OWORD *v5; // rsi
  unsigned int started; // eax
  unsigned int v8; // ebx
  CHostedCacheMsgEncoding *v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  CHostedCacheMsgEncoding *v12; // rcx
  __int64 v13; // rdx
  JET_SESID v14; // r15
  int v15; // eax
  int v16; // eax
  JET_ERR Columns; // eax
  int v18; // r8d
  JET_ERR v19; // eax
  int v20; // eax
  int v21; // r8d
  CHostedCacheMsgEncoding *v22; // rcx
  __int64 v23; // rdx
  JET_ERR v24; // eax
  unsigned int v25; // [rsp+40h] [rbp-C0h] BYREF
  JET_SESID sesid; // [rsp+48h] [rbp-B8h] BYREF
  JET_TABLEID tableid; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v28; // [rsp+58h] [rbp-A8h] BYREF
  UUID Uuid1; // [rsp+5Ch] [rbp-A4h] BYREF
  _QWORD v30[2]; // [rsp+70h] [rbp-90h] BYREF
  __int16 v31; // [rsp+80h] [rbp-80h]
  __m128i si128; // [rsp+84h] [rbp-7Ch]
  __m128i v33; // [rsp+94h] [rbp-6Ch]
  int v34; // [rsp+A4h] [rbp-5Ch]
  _BYTE v35[256]; // [rsp+A8h] [rbp-58h] BYREF
  int v36; // [rsp+1A8h] [rbp+A8h]

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_D_guid_(*((_QWORD *)WPP_GLOBAL_Control + 12), 123, a3, *a2, (__int64)(a2 + 2));
  }
  v28 = 0;
  Uuid1 = GUID_NULL;
  v5 = operator new[](0x600u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v5 )
    return 14;
  v30[0] = &CTnoJetSession::`vftable';
  sesid = -1;
  tableid = -1;
  v30[1] = -1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v25 = -1;
  v33 = si128;
  v31 = 0;
  v34 = 0;
  v36 = 0;
  memset_0(v35, -1, sizeof(v35));
  started = CTnoJetSession::StartSession((CTnoJetSession *)v30, *(_QWORD *)(a1 + 216), &sesid);
  v8 = started;
  if ( started )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_71;
    }
    v10 = 124;
    goto LABEL_12;
  }
  started = CTnoJetSession::BeginTransaction((CTnoJetSession *)v30);
  v8 = started;
  if ( started )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_71;
    }
    v10 = 125;
    goto LABEL_12;
  }
  started = CTnoJetSession::OpenDatabase((CTnoJetSession *)v30, (const unsigned __int16 *)(a1 + 2792), 0, &v25);
  v8 = started;
  if ( started )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_71;
    }
    v10 = 126;
    goto LABEL_12;
  }
  v11 = CTnoJetSession::OpenTable((CTnoJetSession *)v30, v25, L"RepubDatabaseTable", 0, 0, 8u, &tableid);
  if ( v11 )
  {
    v8 = TranslateJetError(v11);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_71;
    }
    v13 = 127;
    goto LABEL_70;
  }
  v14 = sesid;
  do
  {
    v15 = *(_DWORD *)(a1 + 3476);
    *v5 = 0;
    v5[1] = 0;
    v5[2] = 0;
    *(_DWORD *)v5 = v15;
    *((_QWORD *)v5 + 1) = &v28;
    *((_DWORD *)v5 + 4) = 2;
    *((_DWORD *)v5 + 8) = 1;
    v16 = *(_DWORD *)(a1 + 3480);
    v5[3] = 0;
    v5[4] = 0;
    v5[5] = 0;
    *((_DWORD *)v5 + 12) = v16;
    *((_QWORD *)v5 + 7) = &Uuid1;
    *((_DWORD *)v5 + 16) = 16;
    *((_DWORD *)v5 + 20) = 1;
    Columns = JetRetrieveColumns(v14, tableid, (JET_RETRIEVECOLUMN *)v5, 2u);
    if ( Columns )
    {
      v8 = TranslateJetError(Columns);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_71;
      }
      v13 = 128;
      goto LABEL_70;
    }
    if ( v28 == *a2 )
    {
      LODWORD(sesid) = 0;
      v20 = UuidEqual(&Uuid1, (UUID *)(a2 + 2), (RPC_STATUS *)&sesid);
      if ( (_DWORD)sesid )
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          goto LABEL_46;
        }
        v23 = 129;
LABEL_45:
        WPP_SF_(*((_QWORD *)v22 + 12), v23, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
LABEL_46:
        v8 = 774;
        goto LABEL_71;
      }
      if ( !v20 )
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          goto LABEL_46;
        }
        v23 = 130;
        goto LABEL_45;
      }
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
      {
        WPP_SF_D_guid_(*((_QWORD *)WPP_GLOBAL_Control + 12), 131, v21, *a2, (__int64)(a2 + 2));
      }
      v24 = JetDelete(v14, tableid);
      if ( !v24 )
      {
        started = CTnoJetSession::CommitTransaction((CTnoJetSession *)v30);
        v8 = started;
        if ( !started )
          goto LABEL_71;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          goto LABEL_71;
        }
        v10 = 133;
LABEL_12:
        WPP_SF_d(*((_QWORD *)v9 + 12), v10, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, started);
        goto LABEL_71;
      }
      v8 = TranslateJetError(v24);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_71;
      }
      v13 = 132;
LABEL_70:
      WPP_SF_Dd(*((_QWORD *)v12 + 12), v13, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
      goto LABEL_71;
    }
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      WPP_SF_D_guid_(*((_QWORD *)WPP_GLOBAL_Control + 12), 134, v18, v28, (__int64)&Uuid1);
    }
    v19 = JetMove(v14, tableid, 1, 0);
  }
  while ( !v19 );
  v8 = TranslateJetError(v19);
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v13 = 135;
    goto LABEL_70;
  }
LABEL_71:
  CTnoJetSession::~CTnoJetSession((CTnoJetSession *)v30);
  operator delete(v5);
  return v8;
}

```

## disassembly

```asm
0x18004c6ac  mov     [rsp-8+arg_10], rbx
0x18004c6b1  mov     [rsp-8+arg_18], rsi
0x18004c6b6  push    rbp
0x18004c6b7  push    rdi
0x18004c6b8  push    r12
0x18004c6ba  push    r14
0x18004c6bc  push    r15
0x18004c6be  lea     rbp, [rsp-0C0h]
0x18004c6c6  sub     rsp, 1C0h
0x18004c6cd  mov     rax, cs:__security_cookie
0x18004c6d4  xor     rax, rsp
0x18004c6d7  mov     [rbp+0E0h+var_30], rax
0x18004c6de  mov     rdi, rdx
0x18004c6e1  mov     r14, rcx
0x18004c6e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c6eb  lea     r15, WPP_GLOBAL_Control
0x18004c6f2  mov     r12b, 4
0x18004c6f5  cmp     rcx, r15
0x18004c6f8  jz      short loc_18004C721
0x18004c6fa  test    [rcx+6Ch], r12b
0x18004c6fe  jz      short loc_18004C721
0x18004c700  cmp     [rcx+69h], r12b
0x18004c704  jb      short loc_18004C721
0x18004c706  movsx   r9d, word ptr [rdx]
0x18004c70a  lea     rax, [rdx+4]
0x18004c70e  mov     rcx, [rcx+60h]
0x18004c712  mov     edx, 7Bh ; '{'
0x18004c717  mov     qword ptr [rsp+1E0h+var_1C0], rax
0x18004c71c  call    WPP_SF_D_guid_
0x18004c721  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004c728  xor     eax, eax
0x18004c72a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004c731  mov     ecx, 600h; unsigned __int64
0x18004c736  mov     [rsp+1E0h+var_188], ax
0x18004c73b  movdqu  xmmword ptr [rsp+1E0h+Uuid1.Data1], xmm0
0x18004c741  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18004c746  mov     rsi, rax
0x18004c749  test    rax, rax
0x18004c74c  jnz     short loc_18004C756
0x18004c74e  lea     eax, [rsi+0Eh]
0x18004c751  jmp     loc_18004CBC8
0x18004c756  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18004c75e  lea     rax, ??_7CTnoJetSession@@6B@; const CTnoJetSession::`vftable'
0x18004c765  or      rdx, 0FFFFFFFFFFFFFFFFh; Val
0x18004c769  mov     [rsp+1E0h+var_170], rax
0x18004c76e  mov     r8d, 100h; Size
0x18004c774  mov     [rsp+1E0h+sesid], rdx
0x18004c779  lea     rcx, [rbp+0E0h+var_138]; void *
0x18004c77d  mov     [rsp+1E0h+tableid], rdx
0x18004c782  mov     [rsp+1E0h+var_168], rdx
0x18004c787  movups  [rbp+0E0h+var_15C], xmm0
0x18004c78b  mov     [rsp+1E0h+var_1A0], 0FFFFFFFFh
0x18004c793  movups  [rbp+0E0h+var_14C], xmm0
0x18004c797  mov     [rbp+0E0h+var_160], 0
0x18004c79d  mov     [rbp+0E0h+var_13C], 0
0x18004c7a4  mov     [rbp+0E0h+var_38], 0
0x18004c7ae  call    memset_0
0x18004c7b3  mov     rdx, [r14+0D8h]; unsigned __int64
0x18004c7ba  lea     r8, [rsp+1E0h+sesid]; unsigned __int64 *
0x18004c7bf  lea     rcx, [rsp+1E0h+var_170]; this
0x18004c7c4  call    ?StartSession@CTnoJetSession@@UEAAK_KPEA_K@Z; CTnoJetSession::StartSession(unsigned __int64,unsigned __int64 *)
0x18004c7c9  mov     ebx, eax
0x18004c7cb  test    eax, eax
0x18004c7cd  jz      short loc_18004C810
0x18004c7cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c7d6  cmp     rcx, r15
0x18004c7d9  jz      loc_18004CBB4
0x18004c7df  test    [rcx+6Ch], r12b
0x18004c7e3  jz      loc_18004CBB4
0x18004c7e9  cmp     byte ptr [rcx+69h], 1
0x18004c7ed  jb      loc_18004CBB4
0x18004c7f3  mov     edx, 7Ch ; '|'
0x18004c7f8  mov     rcx, [rcx+60h]
0x18004c7fc  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004c803  mov     r9d, eax
0x18004c806  call    WPP_SF_d
0x18004c80b  jmp     loc_18004CBB4
0x18004c810  lea     rcx, [rsp+1E0h+var_170]; this
0x18004c815  call    ?BeginTransaction@CTnoJetSession@@UEAAKXZ; CTnoJetSession::BeginTransaction(void)
0x18004c81a  mov     ebx, eax
0x18004c81c  test    eax, eax
0x18004c81e  jz      short loc_18004C84B
0x18004c820  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c827  cmp     rcx, r15
0x18004c82a  jz      loc_18004CBB4
0x18004c830  test    [rcx+6Ch], r12b
0x18004c834  jz      loc_18004CBB4
0x18004c83a  cmp     byte ptr [rcx+69h], 1
0x18004c83e  jb      loc_18004CBB4
0x18004c844  mov     edx, 7Dh ; '}'
0x18004c849  jmp     short loc_18004C7F8
0x18004c84b  lea     rdx, [r14+0AE8h]; unsigned __int16 *
0x18004c852  xor     r8d, r8d; unsigned int
0x18004c855  lea     r9, [rsp+1E0h+var_1A0]; unsigned int *
0x18004c85a  lea     rcx, [rsp+1E0h+var_170]; this
0x18004c85f  call    ?OpenDatabase@CTnoJetSession@@UEAAKPEBGKPEAK@Z; CTnoJetSession::OpenDatabase(ushort const *,ulong,ulong *)
0x18004c864  mov     ebx, eax
0x18004c866  test    eax, eax
0x18004c868  jz      short loc_18004C898
0x18004c86a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c871  cmp     rcx, r15
0x18004c874  jz      loc_18004CBB4
0x18004c87a  test    [rcx+6Ch], r12b
0x18004c87e  jz      loc_18004CBB4
0x18004c884  cmp     byte ptr [rcx+69h], 1
0x18004c888  jb      loc_18004CBB4
0x18004c88e  mov     edx, 7Eh ; '~'
0x18004c893  jmp     loc_18004C7F8
0x18004c898  mov     edx, [rsp+1E0h+var_1A0]; unsigned int
0x18004c89c  lea     rax, [rsp+1E0h+tableid]
0x18004c8a1  mov     [rsp+1E0h+var_1B0], rax; JET_TABLEID *
0x18004c8a6  lea     r8, aRepubdatabaset; "RepubDatabaseTable"
0x18004c8ad  mov     [rsp+1E0h+var_1B8], 8; JET_GRBIT
0x18004c8b5  lea     rcx, [rsp+1E0h+var_170]; this
0x18004c8ba  xor     r9d, r9d; void *
0x18004c8bd  mov     [rsp+1E0h+var_1C0], 0; unsigned int
0x18004c8c5  call    ?OpenTable@CTnoJetSession@@UEAAKKPEBGPEBXKKPEA_K@Z; CTnoJetSession::OpenTable(ulong,ushort const *,void const *,ulong,ulong,unsigned __int64 *)
0x18004c8ca  mov     r9d, eax
0x18004c8cd  test    eax, eax
0x18004c8cf  jz      short loc_18004C90C
0x18004c8d1  mov     ecx, eax; int
0x18004c8d3  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18004c8d8  mov     ebx, eax
0x18004c8da  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c8e1  cmp     rcx, r15
0x18004c8e4  jz      loc_18004CBB4
0x18004c8ea  test    [rcx+6Ch], r12b
0x18004c8ee  jz      loc_18004CBB4
0x18004c8f4  cmp     byte ptr [rcx+69h], 1
0x18004c8f8  jb      loc_18004CBB4
0x18004c8fe  mov     edx, 7Fh
0x18004c903  mov     [rsp+1E0h+var_1C0], eax
0x18004c907  jmp     loc_18004CBA4
0x18004c90c  mov     r15, [rsp+1E0h+sesid]
0x18004c911  lea     rbx, WPP_GLOBAL_Control
0x18004c918  mov     eax, [r14+0D94h]
0x18004c91f  xorps   xmm0, xmm0
0x18004c922  movups  xmmword ptr [rsi], xmm0
0x18004c925  mov     r9d, 2; cretrievecolumn
0x18004c92b  mov     r8, rsi; pretrievecolumn
0x18004c92e  movups  xmmword ptr [rsi+10h], xmm0
0x18004c932  mov     rcx, r15; sesid
0x18004c935  movups  xmmword ptr [rsi+20h], xmm0
0x18004c939  mov     [rsi], eax
0x18004c93b  lea     rax, [rsp+1E0h+var_188]
0x18004c940  mov     [rsi+8], rax
0x18004c944  mov     dword ptr [rsi+10h], 2
0x18004c94b  mov     dword ptr [rsi+20h], 1
0x18004c952  mov     eax, [r14+0D98h]
0x18004c959  movups  xmmword ptr [rsi+30h], xmm0
0x18004c95d  movups  xmmword ptr [rsi+40h], xmm0
0x18004c961  movups  xmmword ptr [rsi+50h], xmm0
0x18004c965  mov     [rsi+30h], eax
0x18004c968  lea     rax, [rsp+1E0h+Uuid1]
0x18004c96d  mov     [rsi+38h], rax
0x18004c971  mov     dword ptr [rsi+40h], 10h
0x18004c978  mov     dword ptr [rsi+50h], 1
0x18004c97f  mov     rdx, [rsp+1E0h+tableid]; tableid
0x18004c984  call    cs:__imp_JetRetrieveColumns
0x18004c98a  mov     r9d, eax
0x18004c98d  test    eax, eax
0x18004c98f  jnz     loc_18004CB72
0x18004c995  movsx   eax, [rsp+1E0h+var_188]
0x18004c99a  cmp     ax, [rdi]
0x18004c99d  jz      loc_18004CA34
0x18004c9a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c9aa  cmp     rcx, rbx
0x18004c9ad  jz      short loc_18004C9D6
0x18004c9af  test    [rcx+6Ch], r12b
0x18004c9b3  jz      short loc_18004C9D6
0x18004c9b5  cmp     byte ptr [rcx+69h], 3
0x18004c9b9  jb      short loc_18004C9D6
0x18004c9bb  mov     rcx, [rcx+60h]
0x18004c9bf  mov     r9d, eax
0x18004c9c2  lea     rax, [rsp+1E0h+Uuid1]
0x18004c9c7  mov     edx, 86h
0x18004c9cc  mov     qword ptr [rsp+1E0h+var_1C0], rax
0x18004c9d1  call    WPP_SF_D_guid_
0x18004c9d6  mov     rdx, [rsp+1E0h+tableid]; tableid
0x18004c9db  xor     r9d, r9d; grbit
0x18004c9de  mov     rcx, r15; sesid
0x18004c9e1  lea     r8d, [r9+1]; cRow
0x18004c9e5  call    cs:__imp_JetMove
0x18004c9eb  mov     r9d, eax
0x18004c9ee  test    eax, eax
0x18004c9f0  jz      loc_18004C918
0x18004c9f6  mov     ecx, eax; int
0x18004c9f8  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18004c9fd  mov     ebx, eax
0x18004c9ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ca06  lea     rax, WPP_GLOBAL_Control
0x18004ca0d  cmp     rcx, rax
0x18004ca10  jz      loc_18004CBB4
0x18004ca16  test    [rcx+6Ch], r12b
0x18004ca1a  jz      loc_18004CBB4
0x18004ca20  cmp     byte ptr [rcx+69h], 1
0x18004ca24  jb      loc_18004CBB4
0x18004ca2a  mov     edx, 87h
0x18004ca2f  jmp     loc_18004CBA0
0x18004ca34  lea     rbx, [rdi+4]
0x18004ca38  mov     dword ptr [rsp+1E0h+sesid], 0
0x18004ca40  mov     rdx, rbx; Uuid2
0x18004ca43  lea     r8, [rsp+1E0h+sesid]; Status
0x18004ca48  lea     rcx, [rsp+1E0h+Uuid1]; Uuid1
0x18004ca4d  call    cs:__imp_UuidEqual
0x18004ca53  cmp     dword ptr [rsp+1E0h+sesid], 0
0x18004ca58  jz      short loc_18004CA98
0x18004ca5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ca61  lea     rax, WPP_GLOBAL_Control
0x18004ca68  cmp     rcx, rax
0x18004ca6b  jz      short loc_18004CA8E
0x18004ca6d  test    [rcx+6Ch], r12b
0x18004ca71  jz      short loc_18004CA8E
0x18004ca73  cmp     byte ptr [rcx+69h], 1
0x18004ca77  jb      short loc_18004CA8E
0x18004ca79  mov     edx, 81h
0x18004ca7e  mov     rcx, [rcx+60h]
0x18004ca82  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004ca89  call    WPP_SF_
0x18004ca8e  mov     ebx, 306h
0x18004ca93  jmp     loc_18004CBB4
0x18004ca98  test    eax, eax
0x18004ca9a  jnz     short loc_18004CAC2
0x18004ca9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004caa3  lea     rax, WPP_GLOBAL_Control
0x18004caaa  cmp     rcx, rax
0x18004caad  jz      short loc_18004CA8E
0x18004caaf  test    [rcx+6Ch], r12b
0x18004cab3  jz      short loc_18004CA8E
0x18004cab5  cmp     byte ptr [rcx+69h], 1
0x18004cab9  jb      short loc_18004CA8E
0x18004cabb  mov     edx, 82h
0x18004cac0  jmp     short loc_18004CA7E
0x18004cac2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cac9  lea     r14, WPP_GLOBAL_Control
0x18004cad0  cmp     rcx, r14
0x18004cad3  jz      short loc_18004CAF8
0x18004cad5  test    [rcx+6Ch], r12b
0x18004cad9  jz      short loc_18004CAF8
0x18004cadb  cmp     byte ptr [rcx+69h], 3
0x18004cadf  jb      short loc_18004CAF8
0x18004cae1  movsx   r9d, word ptr [rdi]
0x18004cae5  mov     edx, 83h
0x18004caea  mov     rcx, [rcx+60h]
0x18004caee  mov     qword ptr [rsp+1E0h+var_1C0], rbx
0x18004caf3  call    WPP_SF_D_guid_
0x18004caf8  mov     rdx, [rsp+1E0h+tableid]; tableid
0x18004cafd  mov     rcx, r15; sesid
0x18004cb00  call    cs:__imp_JetDelete
0x18004cb06  mov     r9d, eax
0x18004cb09  test    eax, eax
0x18004cb0b  jz      short loc_18004CB40
0x18004cb0d  mov     ecx, eax; int
0x18004cb0f  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18004cb14  mov     ebx, eax
0x18004cb16  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cb1d  cmp     rcx, r14
0x18004cb20  jz      loc_18004CBB4
0x18004cb26  test    [rcx+6Ch], r12b
0x18004cb2a  jz      loc_18004CBB4
0x18004cb30  cmp     byte ptr [rcx+69h], 1
0x18004cb34  jb      short loc_18004CBB4
0x18004cb36  mov     edx, 84h
0x18004cb3b  jmp     loc_18004C903
0x18004cb40  lea     rcx, [rsp+1E0h+var_170]; this
0x18004cb45  call    ?CommitTransaction@CTnoJetSession@@UEAAKXZ; CTnoJetSession::CommitTransaction(void)
0x18004cb4a  mov     ebx, eax
0x18004cb4c  test    eax, eax
0x18004cb4e  jz      short loc_18004CBB4
0x18004cb50  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cb57  cmp     rcx, r14
0x18004cb5a  jz      short loc_18004CBB4
0x18004cb5c  test    [rcx+6Ch], r12b
0x18004cb60  jz      short loc_18004CBB4
0x18004cb62  cmp     byte ptr [rcx+69h], 1
0x18004cb66  jb      short loc_18004CBB4
0x18004cb68  mov     edx, 85h
0x18004cb6d  jmp     loc_18004C7F8
0x18004cb72  mov     ecx, r9d; int
0x18004cb75  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18004cb7a  mov     ebx, eax
0x18004cb7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cb83  lea     rax, WPP_GLOBAL_Control
0x18004cb8a  cmp     rcx, rax
0x18004cb8d  jz      short loc_18004CBB4
0x18004cb8f  test    [rcx+6Ch], r12b
0x18004cb93  jz      short loc_18004CBB4
0x18004cb95  cmp     byte ptr [rcx+69h], 1
0x18004cb99  jb      short loc_18004CBB4
0x18004cb9b  mov     edx, 80h
0x18004cba0  mov     [rsp+1E0h+var_1C0], ebx
0x18004cba4  mov     rcx, [rcx+60h]
0x18004cba8  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004cbaf  call    WPP_SF_Dd
0x18004cbb4  lea     rcx, [rsp+1E0h+var_170]; this
0x18004cbb9  call    ??1CTnoJetSession@@UEAA@XZ; CTnoJetSession::~CTnoJetSession(void)
0x18004cbbe  mov     rcx, rsi; Block
0x18004cbc1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004cbc6  mov     eax, ebx
0x18004cbc8  mov     rcx, [rbp+0E0h+var_30]
  ... truncated ...
```
