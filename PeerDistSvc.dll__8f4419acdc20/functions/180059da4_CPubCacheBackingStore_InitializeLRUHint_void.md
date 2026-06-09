# CPubCacheBackingStore::InitializeLRUHint(void)

- ea: `0x180059da4`
- end: `0x18005a16a`
- name: `?InitializeLRUHint@CPubCacheBackingStore@@AEAAKXZ`
- size: `966`
- prototype: `unsigned int __fastcall(CPubCacheBackingStore *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800596e8`

## callees

- `0x180004374`
- `0x180008290`
- `0x1800082d0`
- `0x18000ceac`
- `0x180018340`
- `0x180059da4`
- `0x180139428`
- `0x18013a410`
- `0x18013a680`
- `0x18013aaf0`
- `0x18013ab7c`
- `0x180144882`
- `0x1801448c0`

## import_xrefs

- `ESENT!JetRetrieveColumns` at `0x18005a122`
- `ESENT!JetRetrieveColumns` at `0x18005a122`
- `ESENT!JetMove` at `0x180059fff`
- `ESENT!JetMove` at `0x180059fff`
- `ESENT!JetSetCurrentIndexW` at `0x180059f95`
- `ESENT!JetSetCurrentIndexW` at `0x180059f95`

## pseudocode

```c
__int64 __fastcall CPubCacheBackingStore::InitializeLRUHint(CPubCacheBackingStore *this)
{
  unsigned int started; // eax
  unsigned int v3; // ebx
  CHostedCacheMsgEncoding *v4; // rcx
  __int64 v5; // rdx
  JET_ERR v6; // eax
  CHostedCacheMsgEncoding *v7; // rcx
  __int64 v8; // rdx
  JET_ERR v9; // eax
  _QWORD *v10; // rdi
  JET_COLUMNID v12; // eax
  JET_ERR v13; // eax
  unsigned int v14; // [rsp+40h] [rbp-C0h] BYREF
  JET_TABLEID tableid; // [rsp+48h] [rbp-B8h] BYREF
  JET_SESID sesid; // [rsp+50h] [rbp-B0h] BYREF
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v18[2]; // [rsp+90h] [rbp-70h] BYREF
  __int16 v19; // [rsp+A0h] [rbp-60h]
  __m128i si128; // [rsp+A4h] [rbp-5Ch]
  __m128i v21; // [rsp+B4h] [rbp-4Ch]
  int v22; // [rsp+C4h] [rbp-3Ch]
  _BYTE v23[256]; // [rsp+C8h] [rbp-38h] BYREF
  int v24; // [rsp+1C8h] [rbp+C8h]

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      106,
      WPP_817cd87503153d87380e6127cb13644a_Traceguids,
      L"PubCatalogTable");
  }
  v14 = -1;
  v19 = 0;
  memset(&pretrievecolumn, 0, sizeof(pretrievecolumn));
  sesid = -1;
  tableid = -1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v18[0] = &CTnoJetSession::`vftable';
  v21 = si128;
  v18[1] = -1;
  v22 = 0;
  v24 = 0;
  memset_0(v23, -1, sizeof(v23));
  started = CTnoJetSession::StartSession((CTnoJetSession *)v18, *((_QWORD *)this + 33), &sesid);
  v3 = started;
  if ( started )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v5 = 107;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v4 + 12), v5, WPP_817cd87503153d87380e6127cb13644a_Traceguids, started);
      goto LABEL_38;
    }
    goto LABEL_38;
  }
  started = CTnoJetSession::OpenDatabase((CTnoJetSession *)v18, (const unsigned __int16 *)this + 1944, 0, &v14);
  v3 = started;
  if ( !started )
  {
    started = CTnoJetSession::OpenTable((CTnoJetSession *)v18, v14, L"PubCatalogTable", 0, 0, 4u, &tableid);
    v3 = started;
    if ( started )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v5 = 109;
        goto LABEL_10;
      }
      goto LABEL_38;
    }
    v6 = JetSetCurrentIndexW(sesid, tableid, L"LRUHintIndex");
    if ( v6 )
    {
      v3 = TranslateJetError(v6);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_38;
      }
      v8 = 110;
      goto LABEL_26;
    }
    v9 = JetMove(sesid, tableid, 0x7FFFFFFF, 1u);
    if ( v9 == -1603 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 111, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
      }
      v10 = (_QWORD *)((char *)this + 248);
      *v10 = 0;
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
        goto LABEL_38;
      }
      v8 = 112;
    }
    else
    {
      v12 = *((_DWORD *)this + 1143);
      v10 = (_QWORD *)((char *)this + 248);
      *(&pretrievecolumn.columnid + 1) = 0;
      pretrievecolumn.columnid = v12;
      memset(&pretrievecolumn.cbData, 0, 32);
      pretrievecolumn.cbData = 8;
      pretrievecolumn.pvData = v10;
      pretrievecolumn.itagSequence = 1;
      v13 = JetRetrieveColumns(sesid, tableid, &pretrievecolumn, 1u);
      if ( !v13 )
      {
LABEL_33:
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 114, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
        }
        ++*v10;
        goto LABEL_38;
      }
      v3 = TranslateJetError(v13);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_38;
      }
      v8 = 113;
    }
LABEL_26:
    WPP_SF_Dd(*((_QWORD *)v7 + 12), v8, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
    goto LABEL_38;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v5 = 108;
    goto LABEL_10;
  }
LABEL_38:
  CTnoJetSession::~CTnoJetSession((CTnoJetSession *)v18);
  return v3;
}

```

## disassembly

```asm
0x180059da4  push    rbp
0x180059da6  push    rbx
0x180059da7  push    rdi
0x180059da8  push    r12
0x180059daa  push    r14
0x180059dac  push    r15
0x180059dae  lea     rbp, [rsp-0E8h]
0x180059db6  sub     rsp, 1E8h
0x180059dbd  mov     rax, cs:__security_cookie
0x180059dc4  xor     rax, rsp
0x180059dc7  mov     [rbp+110h+var_40], rax
0x180059dce  mov     rdi, rcx
0x180059dd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180059dd8  lea     r15, WPP_GLOBAL_Control
0x180059ddf  lea     r12, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x180059de6  mov     r14d, 4
0x180059dec  cmp     rcx, r15
0x180059def  jz      short loc_180059E14
0x180059df1  test    [rcx+6Ch], r14b
0x180059df5  jz      short loc_180059E14
0x180059df7  cmp     [rcx+69h], r14b
0x180059dfb  jb      short loc_180059E14
0x180059dfd  mov     rcx, [rcx+60h]
0x180059e01  lea     edx, [r14+66h]
0x180059e05  lea     r9, aPubcatalogtabl; "PubCatalogTable"
0x180059e0c  mov     r8, r12
0x180059e0f  call    WPP_SF_S
0x180059e14  xorps   xmm0, xmm0
0x180059e17  mov     [rsp+210h+var_1D0], 0FFFFFFFFh
0x180059e1f  or      rdx, 0FFFFFFFFFFFFFFFFh; Val
0x180059e23  mov     [rbp+110h+var_170], 0
0x180059e29  movups  xmmword ptr [rsp+210h+pretrievecolumn.columnid], xmm0
0x180059e2e  lea     rax, ??_7CTnoJetSession@@6B@; const CTnoJetSession::`vftable'
0x180059e35  mov     r8d, 100h; Size
0x180059e3b  movups  xmmword ptr [rsp+210h+pretrievecolumn.cbData], xmm0
0x180059e40  lea     rcx, [rbp+110h+var_148]; void *
0x180059e44  mov     [rsp+210h+sesid], rdx
0x180059e49  movups  xmmword ptr [rsp+210h+pretrievecolumn.itagSequence], xmm0
0x180059e4e  mov     [rsp+210h+tableid], rdx
0x180059e53  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180059e5b  movups  [rbp+110h+var_16C], xmm0
0x180059e5f  mov     [rbp+110h+var_180], rax
0x180059e63  movups  [rbp+110h+var_15C], xmm0
0x180059e67  mov     [rbp+110h+var_178], rdx
0x180059e6b  mov     [rbp+110h+var_14C], 0
0x180059e72  mov     [rbp+110h+var_48], 0
0x180059e7c  call    memset_0
0x180059e81  mov     rdx, [rdi+108h]; unsigned __int64
0x180059e88  lea     r8, [rsp+210h+sesid]; unsigned __int64 *
0x180059e8d  lea     rcx, [rbp+110h+var_180]; this
0x180059e91  call    ?StartSession@CTnoJetSession@@UEAAK_KPEA_K@Z; CTnoJetSession::StartSession(unsigned __int64,unsigned __int64 *)
0x180059e96  mov     ebx, eax
0x180059e98  test    eax, eax
0x180059e9a  jz      short loc_180059ED9
0x180059e9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180059ea3  cmp     rcx, r15
0x180059ea6  jz      loc_18005A079
0x180059eac  test    [rcx+6Ch], r14b
0x180059eb0  jz      loc_18005A079
0x180059eb6  cmp     byte ptr [rcx+69h], 1
0x180059eba  jb      loc_18005A079
0x180059ec0  mov     edx, 6Bh ; 'k'
0x180059ec5  mov     rcx, [rcx+60h]
0x180059ec9  mov     r9d, eax
0x180059ecc  mov     r8, r12
0x180059ecf  call    WPP_SF_d
0x180059ed4  jmp     loc_18005A079
0x180059ed9  lea     rdx, [rdi+0F30h]; unsigned __int16 *
0x180059ee0  xor     r8d, r8d; unsigned int
0x180059ee3  lea     r9, [rsp+210h+var_1D0]; unsigned int *
0x180059ee8  lea     rcx, [rbp+110h+var_180]; this
0x180059eec  call    ?OpenDatabase@CTnoJetSession@@UEAAKPEBGKPEAK@Z; CTnoJetSession::OpenDatabase(ushort const *,ulong,ulong *)
0x180059ef1  mov     ebx, eax
0x180059ef3  test    eax, eax
0x180059ef5  jz      short loc_180059F22
0x180059ef7  mov     rcx, cs:WPP_GLOBAL_Control
0x180059efe  cmp     rcx, r15
0x180059f01  jz      loc_18005A079
0x180059f07  test    [rcx+6Ch], r14b
0x180059f0b  jz      loc_18005A079
0x180059f11  cmp     byte ptr [rcx+69h], 1
0x180059f15  jb      loc_18005A079
0x180059f1b  mov     edx, 6Ch ; 'l'
0x180059f20  jmp     short loc_180059EC5
0x180059f22  mov     edx, [rsp+210h+var_1D0]; unsigned int
0x180059f26  lea     rax, [rsp+210h+tableid]
0x180059f2b  mov     [rsp+210h+var_1E0], rax; JET_TABLEID *
0x180059f30  lea     r8, aPubcatalogtabl; "PubCatalogTable"
0x180059f37  mov     [rsp+210h+var_1E8], r14d; JET_GRBIT
0x180059f3c  lea     rcx, [rbp+110h+var_180]; this
0x180059f40  xor     r9d, r9d; void *
0x180059f43  mov     [rsp+210h+var_1F0], 0; unsigned int
0x180059f4b  call    ?OpenTable@CTnoJetSession@@UEAAKKPEBGPEBXKKPEA_K@Z; CTnoJetSession::OpenTable(ulong,ushort const *,void const *,ulong,ulong,unsigned __int64 *)
0x180059f50  mov     ebx, eax
0x180059f52  test    eax, eax
0x180059f54  jz      short loc_180059F84
0x180059f56  mov     rcx, cs:WPP_GLOBAL_Control
0x180059f5d  cmp     rcx, r15
0x180059f60  jz      loc_18005A079
0x180059f66  test    [rcx+6Ch], r14b
0x180059f6a  jz      loc_18005A079
0x180059f70  cmp     byte ptr [rcx+69h], 1
0x180059f74  jb      loc_18005A079
0x180059f7a  mov     edx, 6Dh ; 'm'
0x180059f7f  jmp     loc_180059EC5
0x180059f84  mov     r8, cs:off_1801617F8; szIndexName
0x180059f8b  mov     rdx, [rsp+210h+tableid]; tableid
0x180059f90  mov     rcx, [rsp+210h+sesid]; sesid
0x180059f95  call    cs:__imp_JetSetCurrentIndexW
0x180059f9b  mov     r9d, eax
0x180059f9e  test    eax, eax
0x180059fa0  jz      short loc_180059FE9
0x180059fa2  mov     ecx, eax; int
0x180059fa4  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180059fa9  mov     ebx, eax
0x180059fab  mov     rcx, cs:WPP_GLOBAL_Control
0x180059fb2  cmp     rcx, r15
0x180059fb5  jz      loc_18005A079
0x180059fbb  test    [rcx+6Ch], r14b
0x180059fbf  jz      loc_18005A079
0x180059fc5  cmp     byte ptr [rcx+69h], 1
0x180059fc9  jb      loc_18005A079
0x180059fcf  mov     edx, 6Eh ; 'n'
0x180059fd4  mov     rcx, [rcx+60h]
0x180059fd8  mov     r8, r12
0x180059fdb  mov     [rsp+210h+var_1F0], eax
0x180059fdf  call    WPP_SF_Dd
0x180059fe4  jmp     loc_18005A079
0x180059fe9  mov     rdx, [rsp+210h+tableid]; tableid
0x180059fee  mov     r9d, 1; grbit
0x180059ff4  mov     rcx, [rsp+210h+sesid]; sesid
0x180059ff9  mov     r8d, 7FFFFFFFh; cRow
0x180059fff  call    cs:__imp_JetMove
0x18005a005  mov     r9d, eax
0x18005a008  cmp     eax, 0FFFFF9BDh
0x18005a00d  jnz     loc_18005A0A4
0x18005a013  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a01a  cmp     rcx, r15
0x18005a01d  jz      short loc_18005A03C
0x18005a01f  test    [rcx+6Ch], r14b
0x18005a023  jz      short loc_18005A03C
0x18005a025  cmp     [rcx+69h], r14b
0x18005a029  jb      short loc_18005A03C
0x18005a02b  mov     rcx, [rcx+60h]
0x18005a02f  mov     edx, 6Fh ; 'o'
0x18005a034  mov     r8, r12
0x18005a037  call    WPP_SF_
0x18005a03c  add     rdi, 0F8h
0x18005a043  mov     qword ptr [rdi], 0
0x18005a04a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a051  cmp     rcx, r15
0x18005a054  jz      short loc_18005A076
0x18005a056  test    [rcx+6Ch], r14b
0x18005a05a  jz      short loc_18005A076
0x18005a05c  cmp     [rcx+69h], r14b
0x18005a060  jb      short loc_18005A076
0x18005a062  mov     r9, [rdi]
0x18005a065  mov     edx, 72h ; 'r'
0x18005a06a  mov     rcx, [rcx+60h]
0x18005a06e  mov     r8, r12
0x18005a071  call    WPP_SF_q
0x18005a076  inc     qword ptr [rdi]
0x18005a079  lea     rcx, [rbp+110h+var_180]; this
0x18005a07d  call    ??1CTnoJetSession@@UEAA@XZ; CTnoJetSession::~CTnoJetSession(void)
0x18005a082  mov     eax, ebx
0x18005a084  mov     rcx, [rbp+110h+var_40]
0x18005a08b  xor     rcx, rsp; StackCookie
0x18005a08e  call    __security_check_cookie
0x18005a093  add     rsp, 1E8h
0x18005a09a  pop     r15
0x18005a09c  pop     r14
0x18005a09e  pop     r12
0x18005a0a0  pop     rdi
0x18005a0a1  pop     rbx
0x18005a0a2  pop     rbp
0x18005a0a3  retn
0x18005a0a4  test    r9d, r9d
0x18005a0a7  jz      short loc_18005A0D5
0x18005a0a9  mov     ecx, r9d; int
0x18005a0ac  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18005a0b1  mov     ebx, eax
0x18005a0b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a0ba  cmp     rcx, r15
0x18005a0bd  jz      short loc_18005A079
0x18005a0bf  test    [rcx+6Ch], r14b
0x18005a0c3  jz      short loc_18005A079
0x18005a0c5  cmp     byte ptr [rcx+69h], 1
0x18005a0c9  jb      short loc_18005A079
0x18005a0cb  mov     edx, 70h ; 'p'
0x18005a0d0  jmp     loc_180059FD4
0x18005a0d5  mov     eax, [rdi+11DCh]
0x18005a0db  lea     r8, [rsp+210h+pretrievecolumn]; pretrievecolumn
0x18005a0e0  mov     rdx, [rsp+210h+tableid]; tableid
0x18005a0e5  xorps   xmm0, xmm0
0x18005a0e8  mov     rcx, [rsp+210h+sesid]; sesid
0x18005a0ed  add     rdi, 0F8h
0x18005a0f4  movups  xmmword ptr [rsp+210h+pretrievecolumn.columnid], xmm0
0x18005a0f9  mov     r9d, 1; cretrievecolumn
0x18005a0ff  mov     [rsp+210h+pretrievecolumn.columnid], eax
0x18005a103  movups  xmmword ptr [rsp+210h+pretrievecolumn.cbData], xmm0
0x18005a108  mov     [rsp+210h+pretrievecolumn.cbData], 8
0x18005a110  movups  xmmword ptr [rsp+210h+pretrievecolumn.itagSequence], xmm0
0x18005a115  mov     [rsp+210h+pretrievecolumn.pvData], rdi
0x18005a11a  mov     [rsp+210h+pretrievecolumn.itagSequence], 1
0x18005a122  call    cs:__imp_JetRetrieveColumns
0x18005a128  mov     r9d, eax
0x18005a12b  test    eax, eax
0x18005a12d  jz      loc_18005A04A
0x18005a133  mov     ecx, eax; int
0x18005a135  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18005a13a  mov     ebx, eax
0x18005a13c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a143  cmp     rcx, r15
0x18005a146  jz      loc_18005A079
0x18005a14c  test    [rcx+6Ch], r14b
0x18005a150  jz      loc_18005A079
0x18005a156  cmp     byte ptr [rcx+69h], 1
0x18005a15a  jb      loc_18005A079
0x18005a160  mov     edx, 71h ; 'q'
0x18005a165  jmp     loc_180059FD4
```
