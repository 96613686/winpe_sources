# CRepubCacheBackingStore::ReadDatabaseIdsFromCatalog(unsigned __int64 &,ulong &)

- ea: `0x18004b790`
- end: `0x18004bca7`
- name: `?ReadDatabaseIdsFromCatalog@CRepubCacheBackingStore@@AEAAKAEA_KAEAK@Z`
- size: `1303`
- prototype: `unsigned int __fastcall(CRepubCacheBackingStore *__hidden this, unsigned __int64 *, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180040de0`

## callees

- `0x1800024f0`
- `0x180003498`
- `0x180004374`
- `0x180008290`
- `0x18000ceac`
- `0x180018340`
- `0x18004b790`
- `0x180051928`
- `0x180139428`
- `0x18013a680`
- `0x18013ab7c`
- `0x180144882`
- `0x1801448c0`

## import_xrefs

- `ESENT!JetRetrieveColumns` at `0x18004ba14`
- `ESENT!JetRetrieveColumns` at `0x18004ba14`
- `ESENT!JetMove` at `0x18004bae9`
- `ESENT!JetMove` at `0x18004bae9`

## pseudocode

```c
__int64 __fastcall CRepubCacheBackingStore::ReadDatabaseIdsFromCatalog(
        CRepubCacheBackingStore *this,
        unsigned __int64 *a2,
        unsigned int *a3)
{
  JET_RETRIEVECOLUMN *v6; // r14
  JET_SESID v8; // rax
  unsigned int v9; // eax
  unsigned int v10; // edi
  CHostedCacheMsgEncoding *v11; // rcx
  _DWORD *v12; // rbx
  JET_COLUMNID v13; // eax
  JET_COLUMNID v14; // eax
  JET_COLUMNID v15; // eax
  JET_ERR Columns; // eax
  int v17; // edx
  __int64 v18; // rcx
  JET_ERR v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rdx
  unsigned int v22; // [rsp+40h] [rbp-C0h] BYREF
  JET_TABLEID tableid; // [rsp+48h] [rbp-B8h] BYREF
  __m256i v24; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v26[2]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v27; // [rsp+90h] [rbp-70h]
  __m128i si128; // [rsp+94h] [rbp-6Ch]
  __m128i v29; // [rsp+A4h] [rbp-5Ch]
  int v30; // [rsp+B4h] [rbp-4Ch]
  char v31[256]; // [rsp+B8h] [rbp-48h] BYREF
  int v32; // [rsp+1B8h] [rbp+B8h]

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      113,
      WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
      L"RepubDatabaseTable");
  }
  tableid = -1;
  v22 = 0;
  v6 = (JET_RETRIEVECOLUMN *)operator new[](0x600u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v6 )
    return 14;
  v24.m256i_i16[0] = 0;
  v26[0] = &CTnoJetSession::`vftable';
  v8 = *a2;
  *(GUID *)((char *)v24.m256i_i64 + 4) = GUID_NULL;
  v24.m256i_i64[3] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  LODWORD(v25) = 0;
  v29 = si128;
  v26[1] = v8;
  v27 = 0;
  v30 = 0;
  v32 = 0;
  memset_0(v31, -1, sizeof(v31));
  v9 = CTnoJetSession::OpenTable((CTnoJetSession *)v26, *a3, L"RepubDatabaseTable", 0, 0, 4u, &tableid);
  v10 = v9;
  if ( v9 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 114, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v9);
        v11 = WPP_GLOBAL_Control;
      }
      goto LABEL_48;
    }
    goto LABEL_52;
  }
  memset_0(v6, 0, 0x600u);
  v12 = (_DWORD *)((char *)this + 50280);
  v6->columnid = *((_DWORD *)this + 869);
  v6->cbData = 2;
  v6->pvData = &v24;
  v6->itagSequence = 1;
  v13 = *((_DWORD *)this + 870);
  *(_OWORD *)&v6[1].columnid = 0;
  *(_OWORD *)&v6[1].cbData = 0;
  *(_OWORD *)&v6[1].itagSequence = 0;
  v6[1].columnid = v13;
  v6[1].pvData = (char *)v24.m256i_i64 + 4;
  v6[1].cbData = 16;
  v6[1].itagSequence = 1;
  v14 = *((_DWORD *)this + 871);
  *(_OWORD *)&v6[2].columnid = 0;
  *(_OWORD *)&v6[2].cbData = 0;
  *(_OWORD *)&v6[2].itagSequence = 0;
  v6[2].columnid = v14;
  v6[2].pvData = &v22;
  v6[2].cbData = 4;
  v6[2].itagSequence = 1;
  v15 = *((_DWORD *)this + 874);
  *(_OWORD *)&v6[3].columnid = 0;
  *(_OWORD *)&v6[3].cbData = 0;
  *(_OWORD *)&v6[3].itagSequence = 0;
  v6[3].columnid = v15;
  v6[3].pvData = &v25;
  v6[3].cbData = 4;
  v6[3].itagSequence = 1;
  *((_DWORD *)this + 12570) = 0;
  while ( 1 )
  {
    if ( *v12 >= 0x400u )
      goto LABEL_47;
    Columns = JetRetrieveColumns(*a2, tableid, v6, 4u);
    if ( Columns == -1603 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
        goto LABEL_52;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 105) < 4u )
        goto LABEL_48;
      v21 = 115;
LABEL_33:
      WPP_SF_(*((_QWORD *)v11 + 12), v21, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
LABEL_47:
      v11 = WPP_GLOBAL_Control;
      goto LABEL_48;
    }
    if ( Columns )
    {
      v10 = TranslateJetError(Columns);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
        goto LABEL_52;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0 || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        goto LABEL_48;
      v20 = 116;
      goto LABEL_28;
    }
    v17 = v22 * *((_DWORD *)this + 39);
    v24.m256i_i64[3] = v22 * (unsigned __int64)*((unsigned int *)this + 39);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_D_guid_IDD(*((_QWORD *)WPP_GLOBAL_Control + 12), v17, v22, v24.m256i_i16[0], (__int64)v24.m256i_i64 + 4);
      v11 = WPP_GLOBAL_Control;
    }
    if ( v24.m256i_i16[0] < 0 )
    {
      if ( v11 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)v11 + 108) & 4) != 0
        && *((_BYTE *)v11 + 105) )
      {
        WPP_SF_(*((_QWORD *)v11 + 12), 118, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
        v11 = WPP_GLOBAL_Control;
      }
      v10 = 774;
      goto LABEL_48;
    }
    v18 = 5 * ((unsigned int)*v12 + 233LL);
    *(__m256i *)((char *)this + 8 * v18) = v24;
    *((_QWORD *)this + v18 + 4) = v25;
    ++*v12;
    v19 = JetMove(*a2, tableid, 1, 0);
    if ( v19 == -1603 )
      break;
    if ( v19 )
    {
      v10 = TranslateJetError(v19);
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
        goto LABEL_52;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0 || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        goto LABEL_48;
      v20 = 120;
LABEL_28:
      WPP_SF_Dd(*((_QWORD *)v11 + 12), v20, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
      goto LABEL_47;
    }
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    goto LABEL_52;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    v21 = 119;
    goto LABEL_33;
  }
LABEL_48:
  if ( v11 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)v11 + 108) & 4) != 0
    && *((_BYTE *)v11 + 105) >= 4u )
  {
    WPP_SF_Dd(*((_QWORD *)v11 + 12), 121, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
  }
LABEL_52:
  CTnoJetSession::~CTnoJetSession((CTnoJetSession *)v26);
  operator delete(v6);
  return v10;
}

```

## disassembly

```asm
0x18004b790  mov     [rsp-8+arg_18], rbx
0x18004b795  push    rbp
0x18004b796  push    rsi
0x18004b797  push    rdi
0x18004b798  push    r12
0x18004b79a  push    r13
0x18004b79c  push    r14
0x18004b79e  push    r15
0x18004b7a0  lea     rbp, [rsp-0D0h]
0x18004b7a8  sub     rsp, 1D0h
0x18004b7af  mov     rax, cs:__security_cookie
0x18004b7b6  xor     rax, rsp
0x18004b7b9  mov     [rbp+100h+var_40], rax
0x18004b7c0  mov     rbx, r8
0x18004b7c3  mov     r12, rdx
0x18004b7c6  mov     r15, rcx
0x18004b7c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b7d0  lea     rax, WPP_GLOBAL_Control
0x18004b7d7  mov     r13d, 4
0x18004b7dd  cmp     rcx, rax
0x18004b7e0  jz      short loc_18004B809
0x18004b7e2  test    [rcx+6Ch], r13b
0x18004b7e6  jz      short loc_18004B809
0x18004b7e8  cmp     [rcx+69h], r13b
0x18004b7ec  jb      short loc_18004B809
0x18004b7ee  mov     rcx, [rcx+60h]
0x18004b7f2  lea     edx, [r13+6Dh]
0x18004b7f6  lea     r9, aRepubdatabaset; "RepubDatabaseTable"
0x18004b7fd  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004b804  call    WPP_SF_S
0x18004b809  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004b80d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004b814  xor     esi, esi
0x18004b816  mov     [rsp+200h+tableid], rdi
0x18004b81b  mov     ecx, 600h; unsigned __int64
0x18004b820  mov     [rsp+200h+var_1C0], esi
0x18004b824  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18004b829  mov     r14, rax
0x18004b82c  test    rax, rax
0x18004b82f  jnz     short loc_18004B839
0x18004b831  lea     eax, [rdi+0Fh]
0x18004b834  jmp     loc_18004BC7D
0x18004b839  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004b840  lea     rax, ??_7CTnoJetSession@@6B@; const CTnoJetSession::`vftable'
0x18004b847  mov     word ptr [rsp+200h+var_1B0], si
0x18004b84c  mov     [rbp+100h+var_180], rax
0x18004b850  lea     rcx, [rbp+100h+var_148]; void *
0x18004b854  mov     rax, [r12]
0x18004b858  mov     r8d, 100h; Size
0x18004b85e  movdqu  [rsp+200h+var_1B0+4], xmm0
0x18004b864  mov     rdx, rdi; Val
0x18004b867  mov     [rsp+200h+var_198], rsi
0x18004b86c  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18004b874  movups  [rbp+100h+var_16C], xmm0
0x18004b878  mov     dword ptr [rsp+200h+var_190], esi
0x18004b87c  movups  [rbp+100h+var_15C], xmm0
0x18004b880  mov     [rbp+100h+var_178], rax
0x18004b884  mov     [rbp+100h+var_170], si
0x18004b888  mov     [rbp+100h+var_14C], esi
0x18004b88b  mov     [rbp+100h+var_48], esi
0x18004b891  call    memset_0
0x18004b896  mov     edx, [rbx]; unsigned int
0x18004b898  lea     rax, [rsp+200h+tableid]
0x18004b89d  mov     [rsp+200h+var_1D0], rax; JET_TABLEID *
0x18004b8a2  lea     r8, aRepubdatabaset; "RepubDatabaseTable"
0x18004b8a9  mov     [rsp+200h+var_1D8], r13d; JET_GRBIT
0x18004b8ae  lea     rcx, [rbp+100h+var_180]; this
0x18004b8b2  xor     r9d, r9d; void *
0x18004b8b5  mov     [rsp+200h+var_1E0], esi; unsigned int
0x18004b8b9  call    ?OpenTable@CTnoJetSession@@UEAAKKPEBGPEBXKKPEA_K@Z; CTnoJetSession::OpenTable(ulong,ushort const *,void const *,ulong,ulong,unsigned __int64 *)
0x18004b8be  mov     edi, eax
0x18004b8c0  test    eax, eax
0x18004b8c2  jz      short loc_18004B915
0x18004b8c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b8cb  lea     r12, WPP_GLOBAL_Control
0x18004b8d2  cmp     rcx, r12
0x18004b8d5  jz      loc_18004BC6A
0x18004b8db  test    [rcx+6Ch], r13b
0x18004b8df  jz      short loc_18004B909
0x18004b8e1  mov     esi, 1
0x18004b8e6  cmp     [rcx+69h], sil
0x18004b8ea  jb      short loc_18004B909
0x18004b8ec  mov     rcx, [rcx+60h]
0x18004b8f0  lea     edx, [rsi+71h]
0x18004b8f3  mov     r9d, eax
0x18004b8f6  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004b8fd  call    WPP_SF_d
0x18004b902  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b909  lea     rbx, [r15+0C468h]
0x18004b910  jmp     loc_18004BC3D
0x18004b915  xor     edx, edx; Val
0x18004b917  mov     r8d, 600h; Size
0x18004b91d  mov     rcx, r14; void *
0x18004b920  call    memset_0
0x18004b925  mov     eax, [r15+0D94h]
0x18004b92c  lea     rbx, [r15+0C468h]
0x18004b933  mov     [r14], eax
0x18004b936  xorps   xmm0, xmm0
0x18004b939  mov     dword ptr [r14+10h], 2
0x18004b941  lea     rax, [rsp+200h+var_1B0]
0x18004b946  mov     [r14+8], rax
0x18004b94a  mov     esi, 1
0x18004b94f  mov     [r14+20h], esi
0x18004b953  mov     eax, [r15+0D98h]
0x18004b95a  movups  xmmword ptr [r14+30h], xmm0
0x18004b95f  movups  xmmword ptr [r14+40h], xmm0
0x18004b964  movups  xmmword ptr [r14+50h], xmm0
0x18004b969  mov     [r14+30h], eax
0x18004b96d  lea     rax, [rsp+200h+var_1B0+4]
0x18004b972  mov     [r14+38h], rax
0x18004b976  mov     dword ptr [r14+40h], 10h
0x18004b97e  mov     [r14+50h], esi
0x18004b982  mov     eax, [r15+0D9Ch]
0x18004b989  movups  xmmword ptr [r14+60h], xmm0
0x18004b98e  movups  xmmword ptr [r14+70h], xmm0
0x18004b993  movups  xmmword ptr [r14+80h], xmm0
0x18004b99b  mov     [r14+60h], eax
0x18004b99f  lea     rax, [rsp+200h+var_1C0]
0x18004b9a4  mov     [r14+68h], rax
0x18004b9a8  mov     [r14+70h], r13d
0x18004b9ac  mov     [r14+80h], esi
0x18004b9b3  mov     eax, [r15+0DA8h]
0x18004b9ba  movups  xmmword ptr [r14+90h], xmm0
0x18004b9c2  movups  xmmword ptr [r14+0A0h], xmm0
0x18004b9ca  movups  xmmword ptr [r14+0B0h], xmm0
0x18004b9d2  mov     [r14+90h], eax
0x18004b9d9  lea     rax, [rsp+200h+var_190]
0x18004b9de  mov     [r14+98h], rax
0x18004b9e5  mov     [r14+0A0h], r13d
0x18004b9ec  mov     [r14+0B0h], esi
0x18004b9f3  mov     dword ptr [rbx], 0
0x18004b9f9  cmp     dword ptr [rbx], 400h
0x18004b9ff  jnb     loc_18004BC2F
0x18004ba05  mov     rdx, [rsp+200h+tableid]; tableid
0x18004ba0a  mov     r9d, r13d; cretrievecolumn
0x18004ba0d  mov     rcx, [r12]; sesid
0x18004ba11  mov     r8, r14; pretrievecolumn
0x18004ba14  call    cs:__imp_JetRetrieveColumns
0x18004ba1a  mov     r9d, eax
0x18004ba1d  cmp     eax, 0FFFFF9BDh
0x18004ba22  jz      loc_18004BC06
0x18004ba28  test    eax, eax
0x18004ba2a  jnz     loc_18004BBD3
0x18004ba30  mov     edx, [r15+9Ch]
0x18004ba37  mov     r8d, [rsp+200h+var_1C0]
0x18004ba3c  imul    rdx, r8
0x18004ba40  mov     [rsp+200h+var_198], rdx
0x18004ba45  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ba4c  lea     r9, WPP_GLOBAL_Control
0x18004ba53  cmp     rcx, r9
0x18004ba56  jz      short loc_18004BA9D
0x18004ba58  test    [rcx+6Ch], r13b
0x18004ba5c  jz      short loc_18004BA9D
0x18004ba5e  cmp     [rcx+69h], r13b
0x18004ba62  jb      short loc_18004BA9D
0x18004ba64  mov     eax, dword ptr [rsp+200h+var_190]
0x18004ba68  movsx   r9d, word ptr [rsp+200h+var_1B0]
0x18004ba6e  mov     rcx, [rcx+60h]
0x18004ba72  mov     [rsp+200h+var_1C8], r8d
0x18004ba77  mov     dword ptr [rsp+200h+var_1D0], eax
0x18004ba7b  lea     rax, [rsp+200h+var_1B0+4]
0x18004ba80  mov     qword ptr [rsp+200h+var_1D8], rdx
0x18004ba85  mov     qword ptr [rsp+200h+var_1E0], rax
0x18004ba8a  call    WPP_SF_D_guid_IDD
0x18004ba8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ba96  lea     r9, WPP_GLOBAL_Control
0x18004ba9d  xor     eax, eax
0x18004ba9f  cmp     word ptr [rsp+200h+var_1B0], ax
0x18004baa4  jl      loc_18004BB98
0x18004baaa  mov     eax, [rbx]
0x18004baac  xor     r9d, r9d; grbit
0x18004baaf  movups  xmm0, [rsp+200h+var_1B0]
0x18004bab4  add     rax, 0E9h
0x18004baba  mov     r8d, esi; cRow
0x18004babd  lea     rcx, [rax+rax*4]
0x18004bac1  movups  xmmword ptr [r15+rcx*8], xmm0
0x18004bac6  movups  xmm1, xmmword ptr [rsp+60h]
0x18004bacb  movups  xmmword ptr [r15+rcx*8+10h], xmm1
0x18004bad1  movsd   xmm0, [rsp+200h+var_190]
0x18004bad7  movsd   qword ptr [r15+rcx*8+20h], xmm0
0x18004bade  add     [rbx], esi
0x18004bae0  mov     rcx, [r12]; sesid
0x18004bae4  mov     rdx, [rsp+200h+tableid]; tableid
0x18004bae9  call    cs:__imp_JetMove
0x18004baef  mov     r9d, eax
0x18004baf2  cmp     eax, 0FFFFF9BDh
0x18004baf7  jz      short loc_18004BB53
0x18004baf9  test    eax, eax
0x18004bafb  jz      loc_18004B9F9
0x18004bb01  mov     ecx, eax; int
0x18004bb03  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18004bb08  mov     edi, eax
0x18004bb0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bb11  lea     r12, WPP_GLOBAL_Control
0x18004bb18  cmp     rcx, r12
0x18004bb1b  jz      loc_18004BC6A
0x18004bb21  test    [rcx+6Ch], r13b
0x18004bb25  jz      loc_18004BC3D
0x18004bb2b  cmp     [rcx+69h], sil
0x18004bb2f  jb      loc_18004BC3D
0x18004bb35  mov     edx, 78h ; 'x'
0x18004bb3a  mov     rcx, [rcx+60h]
0x18004bb3e  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004bb45  mov     [rsp+200h+var_1E0], eax
0x18004bb49  call    WPP_SF_Dd
0x18004bb4e  jmp     loc_18004BC36
0x18004bb53  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bb5a  lea     r12, WPP_GLOBAL_Control
0x18004bb61  cmp     rcx, r12
0x18004bb64  jz      loc_18004BC6A
0x18004bb6a  test    [rcx+6Ch], r13b
0x18004bb6e  jz      loc_18004BC3D
0x18004bb74  cmp     [rcx+69h], r13b
0x18004bb78  jb      loc_18004BC3D
0x18004bb7e  mov     edx, 77h ; 'w'
0x18004bb83  mov     rcx, [rcx+60h]
0x18004bb87  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004bb8e  call    WPP_SF_
0x18004bb93  jmp     loc_18004BC36
0x18004bb98  cmp     rcx, r9
0x18004bb9b  jz      short loc_18004BBC5
0x18004bb9d  test    [rcx+6Ch], r13b
0x18004bba1  jz      short loc_18004BBC5
0x18004bba3  cmp     [rcx+69h], sil
0x18004bba7  jb      short loc_18004BBC5
0x18004bba9  mov     rcx, [rcx+60h]
0x18004bbad  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004bbb4  mov     edx, 76h ; 'v'
0x18004bbb9  call    WPP_SF_
0x18004bbbe  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bbc5  mov     edi, 306h
0x18004bbca  lea     r12, WPP_GLOBAL_Control
0x18004bbd1  jmp     short loc_18004BC3D
0x18004bbd3  mov     ecx, r9d; int
0x18004bbd6  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18004bbdb  mov     edi, eax
0x18004bbdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bbe4  lea     r12, WPP_GLOBAL_Control
0x18004bbeb  cmp     rcx, r12
0x18004bbee  jz      short loc_18004BC6A
0x18004bbf0  test    [rcx+6Ch], r13b
0x18004bbf4  jz      short loc_18004BC3D
0x18004bbf6  cmp     [rcx+69h], sil
0x18004bbfa  jb      short loc_18004BC3D
0x18004bbfc  mov     edx, 74h ; 't'
0x18004bc01  jmp     loc_18004BB3A
0x18004bc06  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bc0d  lea     r12, WPP_GLOBAL_Control
0x18004bc14  cmp     rcx, r12
0x18004bc17  jz      short loc_18004BC6A
0x18004bc19  test    [rcx+6Ch], r13b
0x18004bc1d  jz      short loc_18004BC3D
0x18004bc1f  cmp     [rcx+69h], r13b
0x18004bc23  jb      short loc_18004BC3D
0x18004bc25  mov     edx, 73h ; 's'
0x18004bc2a  jmp     loc_18004BB83
0x18004bc2f  lea     r12, WPP_GLOBAL_Control
0x18004bc36  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bc3d  cmp     rcx, r12
0x18004bc40  jz      short loc_18004BC6A
0x18004bc42  test    [rcx+6Ch], r13b
0x18004bc46  jz      short loc_18004BC6A
0x18004bc48  cmp     [rcx+69h], r13b
0x18004bc4c  jb      short loc_18004BC6A
0x18004bc4e  mov     r9d, [rbx]
0x18004bc51  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004bc58  mov     rcx, [rcx+60h]
0x18004bc5c  mov     edx, 79h ; 'y'
0x18004bc61  mov     [rsp+200h+var_1E0], edi
0x18004bc65  call    WPP_SF_Dd
0x18004bc6a  lea     rcx, [rbp+100h+var_180]; this
0x18004bc6e  call    ??1CTnoJetSession@@UEAA@XZ; CTnoJetSession::~CTnoJetSession(void)
0x18004bc73  mov     rcx, r14; Block
0x18004bc76  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004bc7b  mov     eax, edi
0x18004bc7d  mov     rcx, [rbp+100h+var_40]
0x18004bc84  xor     rcx, rsp; StackCookie
0x18004bc87  call    __security_check_cookie
0x18004bc8c  mov     rbx, [rsp+200h+arg_18]
0x18004bc94  add     rsp, 1D0h
0x18004bc9b  pop     r15
0x18004bc9d  pop     r14
0x18004bc9f  pop     r13
0x18004bca1  pop     r12
0x18004bca3  pop     rdi
0x18004bca4  pop     rsi
0x18004bca5  pop     rbp
0x18004bca6  retn
```
