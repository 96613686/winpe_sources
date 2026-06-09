# CRepubCacheBackingStore::UpdateCatalogTableBootstrap(unsigned __int64 &,ulong &,bool)

- ea: `0x18004ee4c`
- end: `0x18004f21e`
- name: `?UpdateCatalogTableBootstrap@CRepubCacheBackingStore@@AEAAKAEA_KAEAK_N@Z`
- size: `978`
- prototype: `unsigned int __fastcall(CRepubCacheBackingStore *__hidden this, unsigned __int64 *, unsigned int *, bool)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180040de0`
- `0x18004f224`

## callees

- `0x1800024f0`
- `0x180003498`
- `0x180004374`
- `0x180008290`
- `0x18000ceac`
- `0x18001fc30`
- `0x18004ee4c`
- `0x180139428`
- `0x180139630`
- `0x180139820`
- `0x18013a680`
- `0x18013ab7c`
- `0x180144882`
- `0x1801448c0`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x18004f05b`
- `ESENT!JetPrepareUpdate` at `0x18004f05b`
- `ESENT!JetSetColumns` at `0x18004f0cb`
- `ESENT!JetSetColumns` at `0x18004f0cb`
- `ESENT!JetUpdate` at `0x18004f126`
- `ESENT!JetUpdate` at `0x18004f126`

## pseudocode

```c
__int64 __fastcall CRepubCacheBackingStore::UpdateCatalogTableBootstrap(
        CRepubCacheBackingStore *this,
        unsigned __int64 *a2,
        unsigned int *a3,
        unsigned __int8 a4)
{
  int v4; // r12d
  _DWORD *v8; // rdi
  JET_SESID v10; // rax
  unsigned int v11; // ebx
  CHostedCacheMsgEncoding *v12; // rcx
  __int64 v13; // rdx
  _QWORD *v14; // r15
  int v15; // eax
  _QWORD *v16; // r14
  JET_ERR v17; // eax
  CHostedCacheMsgEncoding *v18; // rcx
  __int64 v19; // rdx
  JET_ERR v20; // eax
  JET_ERR v21; // eax
  JET_TABLEID tableid[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v23[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v24; // [rsp+60h] [rbp-A0h]
  __m128i si128; // [rsp+64h] [rbp-9Ch]
  __m128i v26; // [rsp+74h] [rbp-8Ch]
  int v27; // [rsp+84h] [rbp-7Ch]
  _BYTE v28[256]; // [rsp+88h] [rbp-78h] BYREF
  int v29; // [rsp+188h] [rbp+88h]

  v4 = a4;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 169, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
  }
  tableid[0] = -1;
  v8 = operator new[](0x500u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v8 )
    return 14;
  v23[0] = &CTnoJetSession::`vftable';
  v10 = *a2;
  v24 = 0;
  v27 = 0;
  v29 = 0;
  v23[1] = v10;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v26 = si128;
  memset_0(v28, -1, sizeof(v28));
  v11 = CTnoJetSession::BeginTransaction((CTnoJetSession *)v23);
  if ( v11 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_43;
    }
    v13 = 170;
    goto LABEL_12;
  }
  v11 = CTnoJetSession::OpenTable((CTnoJetSession *)v23, *a3, L"RepubCatalogBootstrapTable", 0, 0, 8u, tableid);
  if ( v11 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_43;
    }
    v13 = 171;
    goto LABEL_12;
  }
  memset_0(v8, 0, 0x500u);
  v14 = (_QWORD *)((char *)this + 50328);
  *v8 = *((_DWORD *)this + 839);
  v8[4] = 8;
  *((_QWORD *)v8 + 1) = (char *)this + 50328;
  v8[7] = 1;
  v15 = *((_DWORD *)this + 840);
  v16 = (_QWORD *)((char *)this + 50336);
  v8[11] = 0;
  *(_QWORD *)(v8 + 15) = 0;
  *((_QWORD *)v8 + 9) = 0;
  v8[10] = v15;
  v8[14] = 8;
  *((_QWORD *)v8 + 6) = v16;
  v8[17] = 1;
  v17 = JetPrepareUpdate(*a2, tableid[0], 2 * v4);
  if ( v17 )
  {
    v11 = TranslateJetError(v17);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_43;
    }
    v19 = 172;
    goto LABEL_23;
  }
  v20 = JetSetColumns(*a2, tableid[0], (JET_SETCOLUMN *)v8, 2u);
  if ( v20 )
  {
    v11 = TranslateJetError(v20);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_43;
    }
    v19 = 173;
    goto LABEL_23;
  }
  v21 = JetUpdate(*a2, tableid[0], 0, 0, 0);
  if ( v21 )
  {
    v11 = TranslateJetError(v21);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_43;
    }
    v19 = 174;
LABEL_23:
    WPP_SF_Dd(*((_QWORD *)v18 + 12), v19, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
    goto LABEL_43;
  }
  v11 = CTnoJetSession::CommitTransaction((CTnoJetSession *)v23);
  if ( !v11 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 12), 176, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, *v14, *v16);
    }
    goto LABEL_43;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v13 = 175;
LABEL_12:
    WPP_SF_d(*((_QWORD *)v12 + 12), v13, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v11);
  }
LABEL_43:
  CTnoJetSession::~CTnoJetSession((CTnoJetSession *)v23);
  operator delete(v8);
  return v11;
}

```

## disassembly

```asm
0x18004ee4c  push    rbp
0x18004ee4e  push    rbx
0x18004ee4f  push    rsi
0x18004ee50  push    rdi
0x18004ee51  push    r12
0x18004ee53  push    r14
0x18004ee55  push    r15
0x18004ee57  lea     rbp, [rsp-0A0h]
0x18004ee5f  sub     rsp, 1A0h
0x18004ee66  mov     rax, cs:__security_cookie
0x18004ee6d  xor     rax, rsp
0x18004ee70  mov     [rbp+0D0h+var_40], rax
0x18004ee77  movzx   r12d, r9b
0x18004ee7b  mov     r15, r8
0x18004ee7e  mov     rsi, rdx
0x18004ee81  mov     r14, rcx
0x18004ee84  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ee8b  lea     rax, WPP_GLOBAL_Control
0x18004ee92  cmp     rcx, rax
0x18004ee95  jz      short loc_18004EEB8
0x18004ee97  test    byte ptr [rcx+6Ch], 4
0x18004ee9b  jz      short loc_18004EEB8
0x18004ee9d  cmp     byte ptr [rcx+69h], 4
0x18004eea1  jb      short loc_18004EEB8
0x18004eea3  mov     rcx, [rcx+60h]
0x18004eea7  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004eeae  mov     edx, 0A9h
0x18004eeb3  call    WPP_SF_
0x18004eeb8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004eebc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004eec3  mov     ecx, 500h; unsigned __int64
0x18004eec8  mov     [rsp+1D0h+tableid], rbx
0x18004eecd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18004eed2  xor     ecx, ecx
0x18004eed4  mov     rdi, rax
0x18004eed7  test    rax, rax
0x18004eeda  jnz     short loc_18004EEE4
0x18004eedc  lea     eax, [rbx+0Fh]
0x18004eedf  jmp     loc_18004F1FD
0x18004eee4  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18004eeec  lea     rax, ??_7CTnoJetSession@@6B@; const CTnoJetSession::`vftable'
0x18004eef3  mov     [rsp+1D0h+var_180], rax
0x18004eef8  mov     r8d, 100h; Size
0x18004eefe  mov     rax, [rsi]
0x18004ef01  mov     rdx, rbx; Val
0x18004ef04  mov     [rsp+1D0h+var_170], cx
0x18004ef09  mov     [rbp+0D0h+var_14C], ecx
0x18004ef0c  mov     [rbp+0D0h+var_48], ecx
0x18004ef12  lea     rcx, [rbp+0D0h+var_148]; void *
0x18004ef16  mov     [rsp+1D0h+var_178], rax
0x18004ef1b  movups  [rsp+1D0h+var_16C], xmm0
0x18004ef20  movups  [rsp+1D0h+var_15C], xmm0
0x18004ef25  call    memset_0
0x18004ef2a  lea     rcx, [rsp+1D0h+var_180]; this
0x18004ef2f  call    ?BeginTransaction@CTnoJetSession@@UEAAKXZ; CTnoJetSession::BeginTransaction(void)
0x18004ef34  mov     ebx, eax
0x18004ef36  test    eax, eax
0x18004ef38  jz      short loc_18004EF82
0x18004ef3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ef41  lea     rax, WPP_GLOBAL_Control
0x18004ef48  cmp     rcx, rax
0x18004ef4b  jz      loc_18004F1E9
0x18004ef51  test    byte ptr [rcx+6Ch], 4
0x18004ef55  jz      loc_18004F1E9
0x18004ef5b  cmp     byte ptr [rcx+69h], 1
0x18004ef5f  jb      loc_18004F1E9
0x18004ef65  mov     edx, 0AAh
0x18004ef6a  mov     rcx, [rcx+60h]
0x18004ef6e  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004ef75  mov     r9d, ebx
0x18004ef78  call    WPP_SF_d
0x18004ef7d  jmp     loc_18004F1E9
0x18004ef82  mov     edx, [r15]; unsigned int
0x18004ef85  lea     rax, [rsp+1D0h+tableid]
0x18004ef8a  mov     [rsp+1D0h+var_1A0], rax; JET_TABLEID *
0x18004ef8f  lea     r8, aRepubcatalogbo; "RepubCatalogBootstrapTable"
0x18004ef96  mov     [rsp+1D0h+var_1A8], 8; JET_GRBIT
0x18004ef9e  lea     rcx, [rsp+1D0h+var_180]; this
0x18004efa3  xor     r9d, r9d; void *
0x18004efa6  mov     dword ptr [rsp+1D0h+pcbActual], 0; unsigned int
0x18004efae  call    ?OpenTable@CTnoJetSession@@UEAAKKPEBGPEBXKKPEA_K@Z; CTnoJetSession::OpenTable(ulong,ushort const *,void const *,ulong,ulong,unsigned __int64 *)
0x18004efb3  mov     ebx, eax
0x18004efb5  test    eax, eax
0x18004efb7  jz      short loc_18004EFEE
0x18004efb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004efc0  lea     rax, WPP_GLOBAL_Control
0x18004efc7  cmp     rcx, rax
0x18004efca  jz      loc_18004F1E9
0x18004efd0  test    byte ptr [rcx+6Ch], 4
0x18004efd4  jz      loc_18004F1E9
0x18004efda  cmp     byte ptr [rcx+69h], 1
0x18004efde  jb      loc_18004F1E9
0x18004efe4  mov     edx, 0ABh
0x18004efe9  jmp     loc_18004EF6A
0x18004efee  xor     edx, edx; Val
0x18004eff0  mov     r8d, 500h; Size
0x18004eff6  mov     rcx, rdi; void *
0x18004eff9  call    memset_0
0x18004effe  mov     eax, [r14+0D1Ch]
0x18004f005  lea     r15, [r14+0C498h]
0x18004f00c  mov     [rdi], eax
0x18004f00e  mov     ecx, 8
0x18004f013  mov     [rdi+10h], ecx
0x18004f016  xor     ebx, ebx
0x18004f018  mov     [rdi+8], r15
0x18004f01c  mov     r8d, r12d
0x18004f01f  mov     dword ptr [rdi+1Ch], 1
0x18004f026  add     r8d, r8d; prep
0x18004f029  mov     eax, [r14+0D20h]
0x18004f030  add     r14, 0C4A0h
0x18004f037  mov     [rdi+2Ch], ebx
0x18004f03a  mov     [rdi+3Ch], rbx
0x18004f03e  mov     [rdi+48h], rbx
0x18004f042  mov     [rdi+28h], eax
0x18004f045  mov     [rdi+38h], ecx
0x18004f048  mov     [rdi+30h], r14
0x18004f04c  mov     dword ptr [rdi+44h], 1
0x18004f053  mov     rdx, [rsp+1D0h+tableid]; tableid
0x18004f058  mov     rcx, [rsi]; sesid
0x18004f05b  call    cs:__imp_JetPrepareUpdate
0x18004f061  mov     r9d, eax
0x18004f064  test    eax, eax
0x18004f066  jz      short loc_18004F0BA
0x18004f068  mov     ecx, eax; int
0x18004f06a  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18004f06f  mov     ebx, eax
0x18004f071  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f078  lea     rax, WPP_GLOBAL_Control
0x18004f07f  cmp     rcx, rax
0x18004f082  jz      loc_18004F1E9
0x18004f088  test    byte ptr [rcx+6Ch], 4
0x18004f08c  jz      loc_18004F1E9
0x18004f092  cmp     byte ptr [rcx+69h], 1
0x18004f096  jb      loc_18004F1E9
0x18004f09c  mov     edx, 0ACh
0x18004f0a1  mov     rcx, [rcx+60h]
0x18004f0a5  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004f0ac  mov     dword ptr [rsp+1D0h+pcbActual], ebx
0x18004f0b0  call    WPP_SF_Dd
0x18004f0b5  jmp     loc_18004F1E9
0x18004f0ba  mov     rdx, [rsp+1D0h+tableid]; tableid
0x18004f0bf  mov     r9d, 2; csetcolumn
0x18004f0c5  mov     rcx, [rsi]; sesid
0x18004f0c8  mov     r8, rdi; psetcolumn
0x18004f0cb  call    cs:__imp_JetSetColumns
0x18004f0d1  mov     r9d, eax
0x18004f0d4  test    eax, eax
0x18004f0d6  jz      short loc_18004F113
0x18004f0d8  mov     ecx, eax; int
0x18004f0da  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18004f0df  mov     ebx, eax
0x18004f0e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f0e8  lea     rax, WPP_GLOBAL_Control
0x18004f0ef  cmp     rcx, rax
0x18004f0f2  jz      loc_18004F1E9
0x18004f0f8  test    byte ptr [rcx+6Ch], 4
0x18004f0fc  jz      loc_18004F1E9
0x18004f102  cmp     byte ptr [rcx+69h], 1
0x18004f106  jb      loc_18004F1E9
0x18004f10c  mov     edx, 0ADh
0x18004f111  jmp     short loc_18004F0A1
0x18004f113  mov     rdx, [rsp+1D0h+tableid]; tableid
0x18004f118  xor     r9d, r9d; cbBookmark
0x18004f11b  mov     rcx, [rsi]; sesid
0x18004f11e  xor     r8d, r8d; pvBookmark
0x18004f121  mov     [rsp+1D0h+pcbActual], rbx; pcbActual
0x18004f126  call    cs:__imp_JetUpdate
0x18004f12c  mov     r9d, eax
0x18004f12f  test    eax, eax
0x18004f131  jz      short loc_18004F171
0x18004f133  mov     ecx, eax; int
0x18004f135  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18004f13a  mov     ebx, eax
0x18004f13c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f143  lea     rax, WPP_GLOBAL_Control
0x18004f14a  cmp     rcx, rax
0x18004f14d  jz      loc_18004F1E9
0x18004f153  test    byte ptr [rcx+6Ch], 4
0x18004f157  jz      loc_18004F1E9
0x18004f15d  cmp     byte ptr [rcx+69h], 1
0x18004f161  jb      loc_18004F1E9
0x18004f167  mov     edx, 0AEh
0x18004f16c  jmp     loc_18004F0A1
0x18004f171  lea     rcx, [rsp+1D0h+var_180]; this
0x18004f176  call    ?CommitTransaction@CTnoJetSession@@UEAAKXZ; CTnoJetSession::CommitTransaction(void)
0x18004f17b  mov     ebx, eax
0x18004f17d  test    eax, eax
0x18004f17f  jz      short loc_18004F1AA
0x18004f181  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f188  lea     rax, WPP_GLOBAL_Control
0x18004f18f  cmp     rcx, rax
0x18004f192  jz      short loc_18004F1E9
0x18004f194  test    byte ptr [rcx+6Ch], 4
0x18004f198  jz      short loc_18004F1E9
0x18004f19a  cmp     byte ptr [rcx+69h], 1
0x18004f19e  jb      short loc_18004F1E9
0x18004f1a0  mov     edx, 0AFh
0x18004f1a5  jmp     loc_18004EF6A
0x18004f1aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f1b1  lea     rax, WPP_GLOBAL_Control
0x18004f1b8  cmp     rcx, rax
0x18004f1bb  jz      short loc_18004F1E9
0x18004f1bd  test    byte ptr [rcx+6Ch], 4
0x18004f1c1  jz      short loc_18004F1E9
0x18004f1c3  cmp     byte ptr [rcx+69h], 4
0x18004f1c7  jb      short loc_18004F1E9
0x18004f1c9  mov     rax, [r14]
0x18004f1cc  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004f1d3  mov     r9, [r15]
0x18004f1d6  mov     edx, 0B0h
0x18004f1db  mov     rcx, [rcx+60h]
0x18004f1df  mov     [rsp+1D0h+pcbActual], rax
0x18004f1e4  call    WPP_SF_qq
0x18004f1e9  lea     rcx, [rsp+1D0h+var_180]; this
0x18004f1ee  call    ??1CTnoJetSession@@UEAA@XZ; CTnoJetSession::~CTnoJetSession(void)
0x18004f1f3  mov     rcx, rdi; Block
0x18004f1f6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004f1fb  mov     eax, ebx
0x18004f1fd  mov     rcx, [rbp+0D0h+var_40]
0x18004f204  xor     rcx, rsp; StackCookie
0x18004f207  call    __security_check_cookie
0x18004f20c  add     rsp, 1A0h
0x18004f213  pop     r15
0x18004f215  pop     r14
0x18004f217  pop     r12
0x18004f219  pop     rdi
0x18004f21a  pop     rsi
0x18004f21b  pop     rbx
0x18004f21c  pop     rbp
0x18004f21d  retn
```
