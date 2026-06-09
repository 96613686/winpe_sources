# CRepubCacheBackingStore::InitializeStagedContentId(void)

- ea: `0x1800482a0`
- end: `0x180048664`
- name: `?InitializeStagedContentId@CRepubCacheBackingStore@@AEAAKXZ`
- size: `964`
- prototype: `unsigned int __fastcall(CRepubCacheBackingStore *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180047224`

## callees

- `0x180004374`
- `0x180008290`
- `0x1800082d0`
- `0x18000ceac`
- `0x180018340`
- `0x1800482a0`
- `0x180139428`
- `0x18013a410`
- `0x18013a680`
- `0x18013aaf0`
- `0x18013ab7c`
- `0x180144882`
- `0x1801448c0`

## import_xrefs

- `ESENT!JetRetrieveColumns` at `0x18004861c`
- `ESENT!JetRetrieveColumns` at `0x18004861c`
- `ESENT!JetMove` at `0x1800484fc`
- `ESENT!JetMove` at `0x1800484fc`
- `ESENT!JetSetCurrentIndexW` at `0x180048492`
- `ESENT!JetSetCurrentIndexW` at `0x180048492`

## pseudocode

```c
__int64 __fastcall CRepubCacheBackingStore::InitializeStagedContentId(CRepubCacheBackingStore *this)
{
  unsigned int started; // eax
  unsigned int v3; // ebx
  CHostedCacheMsgEncoding *v4; // rcx
  __int64 v5; // rdx
  JET_ERR v6; // eax
  CHostedCacheMsgEncoding *v7; // rcx
  __int64 v8; // rdx
  JET_ERR v9; // eax
  JET_COLUMNID v11; // eax
  JET_ERR v12; // eax
  unsigned int v13; // [rsp+40h] [rbp-C0h] BYREF
  JET_TABLEID tableid; // [rsp+48h] [rbp-B8h] BYREF
  JET_SESID sesid; // [rsp+50h] [rbp-B0h] BYREF
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v17[2]; // [rsp+90h] [rbp-70h] BYREF
  __int16 v18; // [rsp+A0h] [rbp-60h]
  __m128i si128; // [rsp+A4h] [rbp-5Ch]
  __m128i v20; // [rsp+B4h] [rbp-4Ch]
  int v21; // [rsp+C4h] [rbp-3Ch]
  _BYTE v22[256]; // [rsp+C8h] [rbp-38h] BYREF
  int v23; // [rsp+1C8h] [rbp+C8h]

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      203,
      WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
      L"RepubStagedContentTable");
  }
  v13 = -1;
  v18 = 0;
  memset(&pretrievecolumn, 0, sizeof(pretrievecolumn));
  sesid = -1;
  tableid = -1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v17[0] = &CTnoJetSession::`vftable';
  v20 = si128;
  v17[1] = -1;
  v21 = 0;
  v23 = 0;
  memset_0(v22, -1, sizeof(v22));
  started = CTnoJetSession::StartSession((CTnoJetSession *)v17, *((_QWORD *)this + 27), &sesid);
  v3 = started;
  if ( started )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v5 = 204;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v4 + 12), v5, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, started);
      goto LABEL_37;
    }
    goto LABEL_37;
  }
  started = CTnoJetSession::OpenDatabase((CTnoJetSession *)v17, (const unsigned __int16 *)this + 1396, 0, &v13);
  v3 = started;
  if ( !started )
  {
    started = CTnoJetSession::OpenTable((CTnoJetSession *)v17, v13, L"RepubStagedContentTable", 0, 0, 4u, &tableid);
    v3 = started;
    if ( started )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v5 = 206;
        goto LABEL_10;
      }
      goto LABEL_37;
    }
    v6 = JetSetCurrentIndexW(sesid, tableid, L"ContentIdIndex");
    if ( v6 )
    {
      v3 = TranslateJetError(v6);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_37;
      }
      v8 = 207;
      goto LABEL_26;
    }
    v9 = JetMove(sesid, tableid, 0x7FFFFFFF, 1u);
    if ( v9 == -1603 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 208, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
      }
      *((_QWORD *)this + 6296) = 0;
      goto LABEL_33;
    }
    if ( v9 )
    {
      v3 = TranslateJetError(v9);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_37;
      }
      v8 = 209;
    }
    else
    {
      v11 = *((_DWORD *)this + 934);
      *(&pretrievecolumn.columnid + 1) = 0;
      pretrievecolumn.columnid = v11;
      memset(&pretrievecolumn.cbData, 0, 32);
      pretrievecolumn.cbData = 8;
      pretrievecolumn.pvData = (char *)this + 50368;
      pretrievecolumn.itagSequence = 1;
      v12 = JetRetrieveColumns(sesid, tableid, &pretrievecolumn, 1u);
      if ( !v12 )
      {
LABEL_33:
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 211, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
        }
        goto LABEL_37;
      }
      v3 = TranslateJetError(v12);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_37;
      }
      v8 = 210;
    }
LABEL_26:
    WPP_SF_Dd(*((_QWORD *)v7 + 12), v8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
    goto LABEL_37;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v5 = 205;
    goto LABEL_10;
  }
LABEL_37:
  CTnoJetSession::~CTnoJetSession((CTnoJetSession *)v17);
  return v3;
}

```

## disassembly

```asm
0x1800482a0  push    rbp
0x1800482a2  push    rbx
0x1800482a3  push    rdi
0x1800482a4  push    r12
0x1800482a6  push    r14
0x1800482a8  push    r15
0x1800482aa  lea     rbp, [rsp-0E8h]
0x1800482b2  sub     rsp, 1E8h
0x1800482b9  mov     rax, cs:__security_cookie
0x1800482c0  xor     rax, rsp
0x1800482c3  mov     [rbp+110h+var_40], rax
0x1800482ca  mov     rdi, rcx
0x1800482cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800482d4  lea     r15, WPP_GLOBAL_Control
0x1800482db  lea     r12, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x1800482e2  mov     r14d, 4
0x1800482e8  cmp     rcx, r15
0x1800482eb  jz      short loc_180048311
0x1800482ed  test    [rcx+6Ch], r14b
0x1800482f1  jz      short loc_180048311
0x1800482f3  cmp     [rcx+69h], r14b
0x1800482f7  jb      short loc_180048311
0x1800482f9  mov     rcx, [rcx+60h]
0x1800482fd  lea     r9, aRepubstagedcon; "RepubStagedContentTable"
0x180048304  mov     edx, 0CBh
0x180048309  mov     r8, r12
0x18004830c  call    WPP_SF_S
0x180048311  xorps   xmm0, xmm0
0x180048314  mov     [rsp+210h+var_1D0], 0FFFFFFFFh
0x18004831c  or      rdx, 0FFFFFFFFFFFFFFFFh; Val
0x180048320  mov     [rbp+110h+var_170], 0
0x180048326  movups  xmmword ptr [rsp+210h+pretrievecolumn.columnid], xmm0
0x18004832b  lea     rax, ??_7CTnoJetSession@@6B@; const CTnoJetSession::`vftable'
0x180048332  mov     r8d, 100h; Size
0x180048338  movups  xmmword ptr [rsp+210h+pretrievecolumn.cbData], xmm0
0x18004833d  lea     rcx, [rbp+110h+var_148]; void *
0x180048341  mov     [rsp+210h+sesid], rdx
0x180048346  movups  xmmword ptr [rsp+210h+pretrievecolumn.itagSequence], xmm0
0x18004834b  mov     [rsp+210h+tableid], rdx
0x180048350  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180048358  movups  [rbp+110h+var_16C], xmm0
0x18004835c  mov     [rbp+110h+var_180], rax
0x180048360  movups  [rbp+110h+var_15C], xmm0
0x180048364  mov     [rbp+110h+var_178], rdx
0x180048368  mov     [rbp+110h+var_14C], 0
0x18004836f  mov     [rbp+110h+var_48], 0
0x180048379  call    memset_0
0x18004837e  mov     rdx, [rdi+0D8h]; unsigned __int64
0x180048385  lea     r8, [rsp+210h+sesid]; unsigned __int64 *
0x18004838a  lea     rcx, [rbp+110h+var_180]; this
0x18004838e  call    ?StartSession@CTnoJetSession@@UEAAK_KPEA_K@Z; CTnoJetSession::StartSession(unsigned __int64,unsigned __int64 *)
0x180048393  mov     ebx, eax
0x180048395  test    eax, eax
0x180048397  jz      short loc_1800483D6
0x180048399  mov     rcx, cs:WPP_GLOBAL_Control
0x1800483a0  cmp     rcx, r15
0x1800483a3  jz      loc_180048573
0x1800483a9  test    [rcx+6Ch], r14b
0x1800483ad  jz      loc_180048573
0x1800483b3  cmp     byte ptr [rcx+69h], 1
0x1800483b7  jb      loc_180048573
0x1800483bd  mov     edx, 0CCh
0x1800483c2  mov     rcx, [rcx+60h]
0x1800483c6  mov     r9d, eax
0x1800483c9  mov     r8, r12
0x1800483cc  call    WPP_SF_d
0x1800483d1  jmp     loc_180048573
0x1800483d6  lea     rdx, [rdi+0AE8h]; unsigned __int16 *
0x1800483dd  xor     r8d, r8d; unsigned int
0x1800483e0  lea     r9, [rsp+210h+var_1D0]; unsigned int *
0x1800483e5  lea     rcx, [rbp+110h+var_180]; this
0x1800483e9  call    ?OpenDatabase@CTnoJetSession@@UEAAKPEBGKPEAK@Z; CTnoJetSession::OpenDatabase(ushort const *,ulong,ulong *)
0x1800483ee  mov     ebx, eax
0x1800483f0  test    eax, eax
0x1800483f2  jz      short loc_18004841F
0x1800483f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800483fb  cmp     rcx, r15
0x1800483fe  jz      loc_180048573
0x180048404  test    [rcx+6Ch], r14b
0x180048408  jz      loc_180048573
0x18004840e  cmp     byte ptr [rcx+69h], 1
0x180048412  jb      loc_180048573
0x180048418  mov     edx, 0CDh
0x18004841d  jmp     short loc_1800483C2
0x18004841f  mov     edx, [rsp+210h+var_1D0]; unsigned int
0x180048423  lea     rax, [rsp+210h+tableid]
0x180048428  mov     [rsp+210h+var_1E0], rax; JET_TABLEID *
0x18004842d  lea     r8, aRepubstagedcon; "RepubStagedContentTable"
0x180048434  mov     [rsp+210h+var_1E8], r14d; JET_GRBIT
0x180048439  lea     rcx, [rbp+110h+var_180]; this
0x18004843d  xor     r9d, r9d; void *
0x180048440  mov     [rsp+210h+var_1F0], 0; unsigned int
0x180048448  call    ?OpenTable@CTnoJetSession@@UEAAKKPEBGPEBXKKPEA_K@Z; CTnoJetSession::OpenTable(ulong,ushort const *,void const *,ulong,ulong,unsigned __int64 *)
0x18004844d  mov     ebx, eax
0x18004844f  test    eax, eax
0x180048451  jz      short loc_180048481
0x180048453  mov     rcx, cs:WPP_GLOBAL_Control
0x18004845a  cmp     rcx, r15
0x18004845d  jz      loc_180048573
0x180048463  test    [rcx+6Ch], r14b
0x180048467  jz      loc_180048573
0x18004846d  cmp     byte ptr [rcx+69h], 1
0x180048471  jb      loc_180048573
0x180048477  mov     edx, 0CEh
0x18004847c  jmp     loc_1800483C2
0x180048481  mov     r8, cs:off_180161480; szIndexName
0x180048488  mov     rdx, [rsp+210h+tableid]; tableid
0x18004848d  mov     rcx, [rsp+210h+sesid]; sesid
0x180048492  call    cs:__imp_JetSetCurrentIndexW
0x180048498  mov     r9d, eax
0x18004849b  test    eax, eax
0x18004849d  jz      short loc_1800484E6
0x18004849f  mov     ecx, eax; int
0x1800484a1  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x1800484a6  mov     ebx, eax
0x1800484a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800484af  cmp     rcx, r15
0x1800484b2  jz      loc_180048573
0x1800484b8  test    [rcx+6Ch], r14b
0x1800484bc  jz      loc_180048573
0x1800484c2  cmp     byte ptr [rcx+69h], 1
0x1800484c6  jb      loc_180048573
0x1800484cc  mov     edx, 0CFh
0x1800484d1  mov     rcx, [rcx+60h]
0x1800484d5  mov     r8, r12
0x1800484d8  mov     [rsp+210h+var_1F0], eax
0x1800484dc  call    WPP_SF_Dd
0x1800484e1  jmp     loc_180048573
0x1800484e6  mov     rdx, [rsp+210h+tableid]; tableid
0x1800484eb  mov     r9d, 1; grbit
0x1800484f1  mov     rcx, [rsp+210h+sesid]; sesid
0x1800484f6  mov     r8d, 7FFFFFFFh; cRow
0x1800484fc  call    cs:__imp_JetMove
0x180048502  mov     r9d, eax
0x180048505  cmp     eax, 0FFFFF9BDh
0x18004850a  jnz     loc_18004859E
0x180048510  mov     rcx, cs:WPP_GLOBAL_Control
0x180048517  cmp     rcx, r15
0x18004851a  jz      short loc_180048539
0x18004851c  test    [rcx+6Ch], r14b
0x180048520  jz      short loc_180048539
0x180048522  cmp     [rcx+69h], r14b
0x180048526  jb      short loc_180048539
0x180048528  mov     rcx, [rcx+60h]
0x18004852c  mov     edx, 0D0h
0x180048531  mov     r8, r12
0x180048534  call    WPP_SF_
0x180048539  add     rdi, 0C4C0h
0x180048540  mov     qword ptr [rdi], 0
0x180048547  mov     rcx, cs:WPP_GLOBAL_Control
0x18004854e  cmp     rcx, r15
0x180048551  jz      short loc_180048573
0x180048553  test    [rcx+6Ch], r14b
0x180048557  jz      short loc_180048573
0x180048559  cmp     [rcx+69h], r14b
0x18004855d  jb      short loc_180048573
0x18004855f  mov     r9, [rdi]
0x180048562  mov     edx, 0D3h
0x180048567  mov     rcx, [rcx+60h]
0x18004856b  mov     r8, r12
0x18004856e  call    WPP_SF_q
0x180048573  lea     rcx, [rbp+110h+var_180]; this
0x180048577  call    ??1CTnoJetSession@@UEAA@XZ; CTnoJetSession::~CTnoJetSession(void)
0x18004857c  mov     eax, ebx
0x18004857e  mov     rcx, [rbp+110h+var_40]
0x180048585  xor     rcx, rsp; StackCookie
0x180048588  call    __security_check_cookie
0x18004858d  add     rsp, 1E8h
0x180048594  pop     r15
0x180048596  pop     r14
0x180048598  pop     r12
0x18004859a  pop     rdi
0x18004859b  pop     rbx
0x18004859c  pop     rbp
0x18004859d  retn
0x18004859e  test    r9d, r9d
0x1800485a1  jz      short loc_1800485CF
0x1800485a3  mov     ecx, r9d; int
0x1800485a6  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x1800485ab  mov     ebx, eax
0x1800485ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800485b4  cmp     rcx, r15
0x1800485b7  jz      short loc_180048573
0x1800485b9  test    [rcx+6Ch], r14b
0x1800485bd  jz      short loc_180048573
0x1800485bf  cmp     byte ptr [rcx+69h], 1
0x1800485c3  jb      short loc_180048573
0x1800485c5  mov     edx, 0D1h
0x1800485ca  jmp     loc_1800484D1
0x1800485cf  mov     eax, [rdi+0E98h]
0x1800485d5  lea     r8, [rsp+210h+pretrievecolumn]; pretrievecolumn
0x1800485da  mov     rdx, [rsp+210h+tableid]; tableid
0x1800485df  xorps   xmm0, xmm0
0x1800485e2  mov     rcx, [rsp+210h+sesid]; sesid
0x1800485e7  add     rdi, 0C4C0h
0x1800485ee  movups  xmmword ptr [rsp+210h+pretrievecolumn.columnid], xmm0
0x1800485f3  mov     r9d, 1; cretrievecolumn
0x1800485f9  mov     [rsp+210h+pretrievecolumn.columnid], eax
0x1800485fd  movups  xmmword ptr [rsp+210h+pretrievecolumn.cbData], xmm0
0x180048602  mov     [rsp+210h+pretrievecolumn.cbData], 8
0x18004860a  movups  xmmword ptr [rsp+210h+pretrievecolumn.itagSequence], xmm0
0x18004860f  mov     [rsp+210h+pretrievecolumn.pvData], rdi
0x180048614  mov     [rsp+210h+pretrievecolumn.itagSequence], 1
0x18004861c  call    cs:__imp_JetRetrieveColumns
0x180048622  mov     r9d, eax
0x180048625  test    eax, eax
0x180048627  jz      loc_180048547
0x18004862d  mov     ecx, eax; int
0x18004862f  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180048634  mov     ebx, eax
0x180048636  mov     rcx, cs:WPP_GLOBAL_Control
0x18004863d  cmp     rcx, r15
0x180048640  jz      loc_180048573
0x180048646  test    [rcx+6Ch], r14b
0x18004864a  jz      loc_180048573
0x180048650  cmp     byte ptr [rcx+69h], 1
0x180048654  jb      loc_180048573
0x18004865a  mov     edx, 0D2h
0x18004865f  jmp     loc_1800484D1
```
