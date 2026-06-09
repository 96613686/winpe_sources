# CRepubCacheBackingStore::AddNewDatabaseId(unsigned __int64 &,ulong)

- ea: `0x18003af94`
- end: `0x18003b548`
- name: `?AddNewDatabaseId@CRepubCacheBackingStore@@AEAAKAEA_KK@Z`
- size: `1460`
- prototype: `unsigned int __fastcall(CRepubCacheBackingStore *__hidden this, unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18003b550`

## callees

- `0x1800024f0`
- `0x180003498`
- `0x180004374`
- `0x180008290`
- `0x18000ceac`
- `0x18003af94`
- `0x1800519b0`
- `0x180139428`
- `0x180139630`
- `0x180139820`
- `0x18013a410`
- `0x18013a680`
- `0x18013ab7c`
- `0x180144882`
- `0x1801448c0`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x18003b25a`
- `ESENT!JetPrepareUpdate` at `0x18003b25a`
- `ESENT!JetSetColumns` at `0x18003b2ca`
- `ESENT!JetSetColumns` at `0x18003b2ca`
- `ESENT!JetUpdate` at `0x18003b325`
- `ESENT!JetUpdate` at `0x18003b325`

## pseudocode

```c
__int64 __fastcall CRepubCacheBackingStore::AddNewDatabaseId(
        CRepubCacheBackingStore *this,
        unsigned __int64 *a2,
        unsigned int a3)
{
  __int64 v3; // r15
  __int64 v6; // r13
  _DWORD *v7; // rbx
  unsigned int v9; // eax
  unsigned int v10; // edi
  CHostedCacheMsgEncoding *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned int v14; // eax
  int v15; // edi
  __int64 v16; // r12
  char *v17; // r15
  int v18; // eax
  int v19; // eax
  JET_ERR v20; // eax
  CHostedCacheMsgEncoding *v21; // rcx
  __int64 v22; // rdx
  JET_ERR v23; // eax
  JET_ERR v24; // eax
  __int128 v25; // xmm3
  __int16 v26; // ax
  unsigned int v27; // r9d
  __int16 v28; // r11
  int v29; // r15d
  int v30; // ecx
  __int64 v31; // xmm2_8
  __int64 v32; // rax
  __int64 v33; // r10
  __int16 v34; // r14
  __int64 v35; // xmm1_8
  __int64 v36; // r8
  int v37; // edx
  int v38; // eax
  __int128 v39; // xmm0
  __int64 v40; // rdx
  unsigned int v41; // [rsp+40h] [rbp-C0h] BYREF
  JET_TABLEID tableid; // [rsp+48h] [rbp-B8h] BYREF
  int v43; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v44[22]; // [rsp+5Ah] [rbp-A6h]
  int v45; // [rsp+7Ch] [rbp-84h]
  _OWORD v46[2]; // [rsp+82h] [rbp-7Eh]
  _QWORD v47[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v48; // [rsp+C0h] [rbp-40h]
  __m128i si128; // [rsp+C4h] [rbp-3Ch]
  __m128i v50; // [rsp+D4h] [rbp-2Ch]
  int v51; // [rsp+E4h] [rbp-1Ch]
  _BYTE v52[256]; // [rsp+E8h] [rbp-18h] BYREF
  int v53; // [rsp+1E8h] [rbp+E8h]

  v3 = a3;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_D_guid_S(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      104,
      768 * a3 + (_DWORD)this + 4036,
      *((__int16 *)this + 384 * a3 + 2016),
      (__int64)this + 768 * a3 + 4036,
      (__int64)this + 768 * a3 + 4052);
  }
  *(GUID *)&v44[2] = GUID_NULL;
  v6 = 0;
  v7 = operator new[](0x500u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v7 )
    return 14;
  v47[0] = &CTnoJetSession::`vftable';
  v47[1] = *a2;
  v41 = -1;
  tableid = -1;
  v48 = 0;
  v51 = 0;
  v53 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v50 = si128;
  memset_0(v52, -1, sizeof(v52));
  v9 = CTnoJetSession::BeginTransaction((CTnoJetSession *)v47);
  v10 = v9;
  if ( v9 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_58;
    }
    v12 = 105;
    goto LABEL_12;
  }
  v9 = CTnoJetSession::OpenDatabase((CTnoJetSession *)v47, (const unsigned __int16 *)this + 1396, 0, &v41);
  v10 = v9;
  if ( v9 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_58;
    }
    v12 = 106;
LABEL_12:
    v13 = v9;
LABEL_13:
    WPP_SF_d(*((_QWORD *)v11 + 12), v12, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v13);
    goto LABEL_58;
  }
  v14 = CTnoJetSession::OpenTable((CTnoJetSession *)v47, v41, L"RepubDatabaseTable", 0, 0, 8u, &tableid);
  v15 = v14;
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 107, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v14);
    }
    v10 = TranslateJetError(v15);
    goto LABEL_58;
  }
  memset_0(v7, 0, 0x500u);
  *v7 = *((_DWORD *)this + 869);
  v7[4] = 2;
  v7[7] = 1;
  v16 = 768 * v3;
  v17 = (char *)this + 768 * v3 + 4032;
  *((_QWORD *)v7 + 1) = v17;
  v18 = *((_DWORD *)this + 870);
  v7[11] = 0;
  *(_QWORD *)(v7 + 15) = 0;
  *((_QWORD *)v7 + 9) = 0;
  v7[10] = v18;
  *((_QWORD *)v7 + 6) = v17 + 4;
  v7[14] = 16;
  v7[17] = 1;
  v19 = *((_DWORD *)this + 874);
  v43 = 0;
  v7[21] = 0;
  *(_QWORD *)(v7 + 25) = 0;
  *((_QWORD *)v7 + 14) = 0;
  v7[20] = v19;
  *((_QWORD *)v7 + 11) = &v43;
  v7[24] = 4;
  v7[27] = 1;
  v20 = JetPrepareUpdate(*a2, tableid, 0);
  if ( v20 )
  {
    v10 = TranslateJetError(v20);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_58;
    }
    v22 = 108;
    goto LABEL_30;
  }
  v23 = JetSetColumns(*a2, tableid, (JET_SETCOLUMN *)v7, 3u);
  if ( v23 )
  {
    v10 = TranslateJetError(v23);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_58;
    }
    v22 = 109;
    goto LABEL_30;
  }
  v24 = JetUpdate(*a2, tableid, 0, 0, 0);
  if ( v24 )
  {
    v10 = TranslateJetError(v24);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_58;
    }
    v22 = 110;
LABEL_30:
    WPP_SF_Dd(*((_QWORD *)v21 + 12), v22, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
    goto LABEL_58;
  }
  v10 = CTnoJetSession::CommitTransaction((CTnoJetSession *)v47);
  if ( !v10 )
  {
    v25 = *(_OWORD *)(v17 + 2);
    v26 = *((_WORD *)v17 + 9);
    v27 = 0;
    v28 = *(_WORD *)v17;
    v29 = *(_DWORD *)((char *)this + v16 + 4620);
    v30 = v45;
    *((_BYTE *)this + v16 + 4625) = 1;
    *(_OWORD *)v44 = v25;
    *(_WORD *)&v44[16] = v26;
    v31 = *(_QWORD *)&v44[14];
    if ( *((_DWORD *)this + 12570) )
    {
      while ( v27 < 0x400 )
      {
        v32 = v27 + 233LL;
        v33 = 5 * v32;
        v34 = *((_WORD *)this + 20 * v32);
        if ( v28 < v34 )
        {
          v35 = *((_QWORD *)this + 5 * v32 + 2);
          v36 = *((_QWORD *)this + 5 * v32 + 3);
          v37 = *((_DWORD *)this + 10 * v32 + 8);
          v38 = *((_DWORD *)this + 10 * v32 + 9);
          v46[0] = *(_OWORD *)((char *)this + 8 * v33 + 2);
          *((_WORD *)this + 4 * v33) = v28;
          v28 = v34;
          *(_OWORD *)((char *)this + 8 * v33 + 2) = v25;
          *((_QWORD *)this + v33 + 3) = v6;
          v6 = v36;
          *(_QWORD *)((char *)v46 + 14) = v35;
          v39 = v46[0];
          *((_DWORD *)this + 2 * v33 + 8) = v29;
          v29 = v37;
          *((_QWORD *)this + v33 + 2) = v31;
          v31 = v35;
          *(_OWORD *)v44 = v39;
          *((_DWORD *)this + 2 * v33 + 9) = v30;
          v30 = v38;
          *(_QWORD *)&v44[14] = v35;
          v25 = *(_OWORD *)v44;
        }
        if ( ++v27 >= *((_DWORD *)this + 12570) )
        {
          if ( v27 < 0x400 )
            goto LABEL_57;
          break;
        }
      }
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 112, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
      }
      v10 = 774;
    }
    else
    {
LABEL_57:
      v40 = 5 * (v27 + 233LL);
      *(_OWORD *)((char *)this + 8 * v40 + 2) = v25;
      *((_WORD *)this + 4 * v40) = v28;
      *((_QWORD *)this + v40 + 2) = v31;
      *((_QWORD *)this + v40 + 3) = v6;
      *((_DWORD *)this + 2 * v40 + 8) = v29;
      *((_DWORD *)this + 2 * v40 + 9) = v30;
      ++*((_DWORD *)this + 12570);
    }
    goto LABEL_58;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v12 = 111;
    v13 = v10;
    goto LABEL_13;
  }
LABEL_58:
  CTnoJetSession::~CTnoJetSession((CTnoJetSession *)v47);
  operator delete(v7);
  return v10;
}

```

## disassembly

```asm
0x18003af94  mov     [rsp-8+arg_18], rbx
0x18003af99  push    rbp
0x18003af9a  push    rsi
0x18003af9b  push    rdi
0x18003af9c  push    r12
0x18003af9e  push    r13
0x18003afa0  push    r14
0x18003afa2  push    r15
0x18003afa4  lea     rbp, [rsp-100h]
0x18003afac  sub     rsp, 200h
0x18003afb3  mov     rax, cs:__security_cookie
0x18003afba  xor     rax, rsp
0x18003afbd  mov     [rbp+130h+var_40], rax
0x18003afc4  mov     r15d, r8d
0x18003afc7  mov     r14, rdx
0x18003afca  mov     rsi, rcx
0x18003afcd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003afd4  lea     r12, WPP_GLOBAL_Control
0x18003afdb  cmp     rcx, r12
0x18003afde  jz      short loc_18003B029
0x18003afe0  test    byte ptr [rcx+6Ch], 4
0x18003afe4  jz      short loc_18003B029
0x18003afe6  cmp     byte ptr [rcx+69h], 4
0x18003afea  jb      short loc_18003B029
0x18003afec  mov     rcx, [rcx+60h]
0x18003aff0  lea     rdx, [r15+r15*2]
0x18003aff4  shl     rdx, 8
0x18003aff8  lea     rax, [rsi+0FD4h]
0x18003afff  add     rax, rdx
0x18003b002  lea     r8, [rsi+0FC4h]
0x18003b009  add     r8, rdx
0x18003b00c  mov     qword ptr [rsp+230h+var_208], rax
0x18003b011  mov     [rsp+230h+pcbActual], r8
0x18003b016  movsx   r9d, word ptr [rdx+rsi+0FC0h]
0x18003b01f  mov     edx, 68h ; 'h'
0x18003b024  call    WPP_SF_D_guid_S
0x18003b029  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003b030  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003b037  mov     ecx, 500h; unsigned __int64
0x18003b03c  movdqu  [rsp+230h+var_1D4], xmm0
0x18003b042  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003b047  xor     r13d, r13d
0x18003b04a  mov     rbx, rax
0x18003b04d  test    rax, rax
0x18003b050  jnz     short loc_18003B05A
0x18003b052  lea     eax, [rbx+0Eh]
0x18003b055  jmp     loc_18003B51E
0x18003b05a  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18003b062  lea     rax, ??_7CTnoJetSession@@6B@; const CTnoJetSession::`vftable'
0x18003b069  mov     [rbp+130h+var_180], rax
0x18003b06d  lea     rcx, [rbp+130h+var_148]; void *
0x18003b071  mov     rax, [r14]
0x18003b074  or      rdx, 0FFFFFFFFFFFFFFFFh; Val
0x18003b078  mov     r8d, 100h; Size
0x18003b07e  mov     [rbp+130h+var_178], rax
0x18003b082  mov     [rsp+230h+var_1F0], 0FFFFFFFFh
0x18003b08a  mov     [rsp+230h+tableid], rdx
0x18003b08f  mov     [rbp+130h+var_170], r13w
0x18003b094  mov     [rbp+130h+var_14C], r13d
0x18003b098  mov     [rbp+130h+var_48], r13d
0x18003b09f  movups  [rbp+130h+var_16C], xmm0
0x18003b0a3  movups  [rbp+130h+var_15C], xmm0
0x18003b0a7  call    memset_0
0x18003b0ac  lea     rcx, [rbp+130h+var_180]; this
0x18003b0b0  call    ?BeginTransaction@CTnoJetSession@@UEAAKXZ; CTnoJetSession::BeginTransaction(void)
0x18003b0b5  mov     edi, eax
0x18003b0b7  test    eax, eax
0x18003b0b9  jz      short loc_18003B0FC
0x18003b0bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b0c2  cmp     rcx, r12
0x18003b0c5  jz      loc_18003B50B
0x18003b0cb  test    byte ptr [rcx+6Ch], 4
0x18003b0cf  jz      loc_18003B50B
0x18003b0d5  cmp     byte ptr [rcx+69h], 1
0x18003b0d9  jb      loc_18003B50B
0x18003b0df  mov     edx, 69h ; 'i'
0x18003b0e4  mov     r9d, eax
0x18003b0e7  mov     rcx, [rcx+60h]
0x18003b0eb  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003b0f2  call    WPP_SF_d
0x18003b0f7  jmp     loc_18003B50B
0x18003b0fc  lea     rdx, [rsi+0AE8h]; unsigned __int16 *
0x18003b103  xor     r8d, r8d; unsigned int
0x18003b106  lea     r9, [rsp+230h+var_1F0]; unsigned int *
0x18003b10b  lea     rcx, [rbp+130h+var_180]; this
0x18003b10f  call    ?OpenDatabase@CTnoJetSession@@UEAAKPEBGKPEAK@Z; CTnoJetSession::OpenDatabase(ushort const *,ulong,ulong *)
0x18003b114  mov     edi, eax
0x18003b116  test    eax, eax
0x18003b118  jz      short loc_18003B145
0x18003b11a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b121  cmp     rcx, r12
0x18003b124  jz      loc_18003B50B
0x18003b12a  test    byte ptr [rcx+6Ch], 4
0x18003b12e  jz      loc_18003B50B
0x18003b134  cmp     byte ptr [rcx+69h], 1
0x18003b138  jb      loc_18003B50B
0x18003b13e  mov     edx, 6Ah ; 'j'
0x18003b143  jmp     short loc_18003B0E4
0x18003b145  mov     edx, [rsp+230h+var_1F0]; unsigned int
0x18003b149  lea     rax, [rsp+230h+tableid]
0x18003b14e  mov     [rsp+230h+var_200], rax; JET_TABLEID *
0x18003b153  lea     r8, aRepubdatabaset; "RepubDatabaseTable"
0x18003b15a  mov     [rsp+230h+var_208], 8; JET_GRBIT
0x18003b162  lea     rcx, [rbp+130h+var_180]; this
0x18003b166  xor     r9d, r9d; void *
0x18003b169  mov     dword ptr [rsp+230h+pcbActual], r13d; unsigned int
0x18003b16e  call    ?OpenTable@CTnoJetSession@@UEAAKKPEBGPEBXKKPEA_K@Z; CTnoJetSession::OpenTable(ulong,ushort const *,void const *,ulong,ulong,unsigned __int64 *)
0x18003b173  mov     edi, eax
0x18003b175  test    eax, eax
0x18003b177  jz      short loc_18003B1B7
0x18003b179  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b180  cmp     rcx, r12
0x18003b183  jz      short loc_18003B1A9
0x18003b185  test    byte ptr [rcx+6Ch], 4
0x18003b189  jz      short loc_18003B1A9
0x18003b18b  cmp     byte ptr [rcx+69h], 1
0x18003b18f  jb      short loc_18003B1A9
0x18003b191  mov     rcx, [rcx+60h]
0x18003b195  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003b19c  mov     edx, 6Bh ; 'k'
0x18003b1a1  mov     r9d, eax
0x18003b1a4  call    WPP_SF_d
0x18003b1a9  mov     ecx, edi; int
0x18003b1ab  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18003b1b0  mov     edi, eax
0x18003b1b2  jmp     loc_18003B50B
0x18003b1b7  xor     edx, edx; Val
0x18003b1b9  mov     r8d, 500h; Size
0x18003b1bf  mov     rcx, rbx; void *
0x18003b1c2  call    memset_0
0x18003b1c7  mov     eax, [rsi+0D94h]
0x18003b1cd  lea     r12, [r15+r15*2]
0x18003b1d1  mov     [rbx], eax
0x18003b1d3  lea     r15, [rsi+0FC0h]
0x18003b1da  mov     dword ptr [rbx+10h], 2
0x18003b1e1  xor     r8d, r8d; prep
0x18003b1e4  mov     dword ptr [rbx+1Ch], 1
0x18003b1eb  shl     r12, 8
0x18003b1ef  add     r15, r12
0x18003b1f2  mov     [rbx+8], r15
0x18003b1f6  mov     eax, [rsi+0D98h]
0x18003b1fc  mov     [rbx+2Ch], r13d
0x18003b200  mov     [rbx+3Ch], r13
0x18003b204  mov     [rbx+48h], r13
0x18003b208  mov     [rbx+28h], eax
0x18003b20b  lea     rax, [r15+4]
0x18003b20f  mov     [rbx+30h], rax
0x18003b213  mov     dword ptr [rbx+38h], 10h
0x18003b21a  mov     dword ptr [rbx+44h], 1
0x18003b221  mov     eax, [rsi+0DA8h]
0x18003b227  mov     [rsp+230h+var_1E0], r13d
0x18003b22c  mov     [rbx+54h], r13d
0x18003b230  mov     [rbx+64h], r13
0x18003b234  mov     [rbx+70h], r13
0x18003b238  mov     [rbx+50h], eax
0x18003b23b  lea     rax, [rsp+230h+var_1E0]
0x18003b240  mov     [rbx+58h], rax
0x18003b244  mov     dword ptr [rbx+60h], 4
0x18003b24b  mov     dword ptr [rbx+6Ch], 1
0x18003b252  mov     rdx, [rsp+230h+tableid]; tableid
0x18003b257  mov     rcx, [r14]; sesid
0x18003b25a  call    cs:__imp_JetPrepareUpdate
0x18003b260  mov     r9d, eax
0x18003b263  test    eax, eax
0x18003b265  jz      short loc_18003B2B9
0x18003b267  mov     ecx, eax; int
0x18003b269  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18003b26e  mov     edi, eax
0x18003b270  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b277  lea     rax, WPP_GLOBAL_Control
0x18003b27e  cmp     rcx, rax
0x18003b281  jz      loc_18003B50B
0x18003b287  test    byte ptr [rcx+6Ch], 4
0x18003b28b  jz      loc_18003B50B
0x18003b291  cmp     byte ptr [rcx+69h], 1
0x18003b295  jb      loc_18003B50B
0x18003b29b  mov     edx, 6Ch ; 'l'
0x18003b2a0  mov     rcx, [rcx+60h]
0x18003b2a4  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003b2ab  mov     dword ptr [rsp+230h+pcbActual], edi
0x18003b2af  call    WPP_SF_Dd
0x18003b2b4  jmp     loc_18003B50B
0x18003b2b9  mov     rdx, [rsp+230h+tableid]; tableid
0x18003b2be  mov     r9d, 3; csetcolumn
0x18003b2c4  mov     rcx, [r14]; sesid
0x18003b2c7  mov     r8, rbx; psetcolumn
0x18003b2ca  call    cs:__imp_JetSetColumns
0x18003b2d0  mov     r9d, eax
0x18003b2d3  test    eax, eax
0x18003b2d5  jz      short loc_18003B312
0x18003b2d7  mov     ecx, eax; int
0x18003b2d9  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18003b2de  mov     edi, eax
0x18003b2e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b2e7  lea     rax, WPP_GLOBAL_Control
0x18003b2ee  cmp     rcx, rax
0x18003b2f1  jz      loc_18003B50B
0x18003b2f7  test    byte ptr [rcx+6Ch], 4
0x18003b2fb  jz      loc_18003B50B
0x18003b301  cmp     byte ptr [rcx+69h], 1
0x18003b305  jb      loc_18003B50B
0x18003b30b  mov     edx, 6Dh ; 'm'
0x18003b310  jmp     short loc_18003B2A0
0x18003b312  mov     rdx, [rsp+230h+tableid]; tableid
0x18003b317  xor     r9d, r9d; cbBookmark
0x18003b31a  mov     rcx, [r14]; sesid
0x18003b31d  xor     r8d, r8d; pvBookmark
0x18003b320  mov     [rsp+230h+pcbActual], r13; pcbActual
0x18003b325  call    cs:__imp_JetUpdate
0x18003b32b  mov     r9d, eax
0x18003b32e  test    eax, eax
0x18003b330  jz      short loc_18003B370
0x18003b332  mov     ecx, eax; int
0x18003b334  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18003b339  mov     edi, eax
0x18003b33b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b342  lea     rax, WPP_GLOBAL_Control
0x18003b349  cmp     rcx, rax
0x18003b34c  jz      loc_18003B50B
0x18003b352  test    byte ptr [rcx+6Ch], 4
0x18003b356  jz      loc_18003B50B
0x18003b35c  cmp     byte ptr [rcx+69h], 1
0x18003b360  jb      loc_18003B50B
0x18003b366  mov     edx, 6Eh ; 'n'
0x18003b36b  jmp     loc_18003B2A0
0x18003b370  lea     rcx, [rbp+130h+var_180]; this
0x18003b374  call    ?CommitTransaction@CTnoJetSession@@UEAAKXZ; CTnoJetSession::CommitTransaction(void)
0x18003b379  mov     edi, eax
0x18003b37b  test    eax, eax
0x18003b37d  jz      short loc_18003B3B7
0x18003b37f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b386  lea     rax, WPP_GLOBAL_Control
0x18003b38d  cmp     rcx, rax
0x18003b390  jz      loc_18003B50B
0x18003b396  test    byte ptr [rcx+6Ch], 4
0x18003b39a  jz      loc_18003B50B
0x18003b3a0  cmp     byte ptr [rcx+69h], 1
0x18003b3a4  jb      loc_18003B50B
0x18003b3aa  mov     edx, 6Fh ; 'o'
0x18003b3af  mov     r9d, edi
0x18003b3b2  jmp     loc_18003B0E7
0x18003b3b7  movups  xmm3, xmmword ptr [r15+2]
0x18003b3bc  movzx   eax, word ptr [r15+12h]
0x18003b3c1  xor     r9d, r9d
0x18003b3c4  movzx   r11d, word ptr [r15]
0x18003b3c8  mov     r15d, [r12+rsi+120Ch]
0x18003b3d0  mov     ecx, [rsp+230h+var_1B4]
0x18003b3d4  mov     byte ptr [r12+rsi+1211h], 1
0x18003b3dd  movups  xmmword ptr [rsp+5Ah], xmm3
0x18003b3e2  mov     word ptr [rsp+230h+var_1D4+0Eh], ax
0x18003b3e7  movsd   xmm2, qword ptr [rsp+230h+var_1D4+0Ch]
0x18003b3ed  cmp     [rsi+0C468h], r9d
0x18003b3f4  jbe     loc_18003B4DA
0x18003b3fa  mov     r12d, 400h
0x18003b400  cmp     r9d, r12d
0x18003b403  jnb     loc_18003B49F
0x18003b409  mov     eax, r9d
0x18003b40c  add     rax, 0E9h
0x18003b412  lea     r10, [rax+rax*4]
0x18003b416  movzx   r14d, word ptr [rsi+r10*8]
0x18003b41b  cmp     r11w, r14w
0x18003b41f  jge     short loc_18003B48A
0x18003b421  movsd   xmm1, qword ptr [rsi+r10*8+10h]
0x18003b428  movups  xmm0, xmmword ptr [rsi+r10*8+2]
0x18003b42e  mov     r8, [rsi+r10*8+18h]
0x18003b433  mov     edx, [rsi+r10*8+20h]
0x18003b438  mov     eax, [rsi+r10*8+24h]
0x18003b43d  movups  xmmword ptr [rbp+130h+var_1AE], xmm0
0x18003b441  mov     [rsi+r10*8], r11w
0x18003b446  movzx   r11d, r14w
0x18003b44a  movups  xmmword ptr [rsi+r10*8+2], xmm3
0x18003b450  mov     [rsi+r10*8+18h], r13
0x18003b455  mov     r13, r8
0x18003b458  movsd   qword ptr [rbp+130h+var_1AE+0Eh], xmm1
0x18003b45d  movups  xmm0, xmmword ptr [rbp+130h+var_1AE]
0x18003b461  mov     [rsi+r10*8+20h], r15d
0x18003b466  mov     r15d, edx
0x18003b469  movsd   qword ptr [rsi+r10*8+10h], xmm2
0x18003b470  movaps  xmm2, xmm1
0x18003b473  movups  xmmword ptr [rsp+5Ah], xmm0
0x18003b478  mov     [rsi+r10*8+24h], ecx
0x18003b47d  mov     ecx, eax
0x18003b47f  movsd   qword ptr [rsp+230h+var_1D4+0Ch], xmm1
0x18003b485  movups  xmm3, xmmword ptr [rsp+5Ah]
0x18003b48a  inc     r9d
0x18003b48d  cmp     r9d, [rsi+0C468h]
0x18003b494  jb      loc_18003B400
0x18003b49a  cmp     r9d, r12d
0x18003b49d  jb      short loc_18003B4DA
0x18003b49f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b4a6  lea     rax, WPP_GLOBAL_Control
0x18003b4ad  cmp     rcx, rax
0x18003b4b0  jz      short loc_18003B4D3
0x18003b4b2  test    byte ptr [rcx+6Ch], 4
0x18003b4b6  jz      short loc_18003B4D3
0x18003b4b8  cmp     byte ptr [rcx+69h], 1
0x18003b4bc  jb      short loc_18003B4D3
0x18003b4be  mov     rcx, [rcx+60h]
0x18003b4c2  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003b4c9  mov     edx, 70h ; 'p'
  ... truncated ...
```
