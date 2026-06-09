# CPubCacheBackingStore::InitializeCatalogTableBootstrap(unsigned __int64 &,ulong &)

- ea: `0x18005983c`
- end: `0x180059c04`
- name: `?InitializeCatalogTableBootstrap@CPubCacheBackingStore@@AEAAKAEA_KAEAK@Z`
- size: `968`
- prototype: `unsigned int __fastcall(CPubCacheBackingStore *__hidden this, unsigned __int64 *, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180056a0c`

## callees

- `0x1800024f0`
- `0x180003498`
- `0x180004374`
- `0x180008290`
- `0x18000ceac`
- `0x18005983c`
- `0x180139428`
- `0x180139630`
- `0x180139820`
- `0x18013a680`
- `0x18013ab7c`
- `0x180144882`
- `0x1801448c0`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x180059a67`
- `ESENT!JetPrepareUpdate` at `0x180059a67`
- `ESENT!JetSetColumns` at `0x180059ad7`
- `ESENT!JetSetColumns` at `0x180059ad7`
- `ESENT!JetUpdate` at `0x180059b40`
- `ESENT!JetUpdate` at `0x180059b40`

## pseudocode

```c
__int64 __fastcall CPubCacheBackingStore::InitializeCatalogTableBootstrap(
        CPubCacheBackingStore *this,
        unsigned __int64 *a2,
        unsigned int *a3)
{
  _DWORD *v6; // rdi
  unsigned int v8; // ebx
  CHostedCacheMsgEncoding *v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  int v12; // eax
  JET_ERR v13; // eax
  CHostedCacheMsgEncoding *v14; // rcx
  __int64 v15; // rdx
  JET_ERR v16; // ebx
  JET_ERR v17; // eax
  int v18; // [rsp+40h] [rbp-C0h] BYREF
  JET_TABLEID tableid; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v21[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v22; // [rsp+70h] [rbp-90h]
  __m128i si128; // [rsp+74h] [rbp-8Ch]
  __m128i v24; // [rsp+84h] [rbp-7Ch]
  int v25; // [rsp+94h] [rbp-6Ch]
  _BYTE v26[256]; // [rsp+98h] [rbp-68h] BYREF
  int v27; // [rsp+198h] [rbp+98h]

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 83, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
  }
  tableid = -1;
  v6 = operator new[](0x500u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v6 )
    return 14;
  v21[0] = &CTnoJetSession::`vftable';
  v21[1] = *a2;
  v18 = 0;
  v20 = 0;
  v22 = 0;
  v25 = 0;
  v27 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v24 = si128;
  memset_0(v26, -1, sizeof(v26));
  v8 = CTnoJetSession::BeginTransaction((CTnoJetSession *)v21);
  if ( v8 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_40;
    }
    v10 = 84;
    goto LABEL_39;
  }
  v8 = CTnoJetSession::OpenTable((CTnoJetSession *)v21, *a3, L"PubCatalogBootstrapTable", 0, 0, 8u, &tableid);
  if ( v8 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_40;
    }
    v10 = 85;
    goto LABEL_39;
  }
  memset_0(v6, 0, 0x500u);
  *v6 = *((_DWORD *)this + 1105);
  *((_QWORD *)v6 + 1) = &v18;
  v6[4] = 4;
  v6[7] = 1;
  v11 = *((_DWORD *)this + 1106);
  v6[11] = 0;
  *(_QWORD *)(v6 + 15) = 0;
  *((_QWORD *)v6 + 9) = 0;
  v6[10] = v11;
  *((_QWORD *)v6 + 6) = &v18;
  v6[14] = 4;
  v6[17] = 1;
  v12 = *((_DWORD *)this + 1107);
  v6[21] = 0;
  *(_QWORD *)(v6 + 25) = 0;
  *((_QWORD *)v6 + 14) = 0;
  v6[20] = v12;
  *((_QWORD *)v6 + 11) = &v20;
  v6[24] = 4;
  v6[27] = 1;
  v13 = JetPrepareUpdate(*a2, tableid, 0);
  if ( v13 )
  {
    v8 = TranslateJetError(v13);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_40;
    }
    v15 = 86;
  }
  else
  {
    v16 = JetSetColumns(*a2, tableid, (JET_SETCOLUMN *)v6, 3u);
    if ( v16 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 87, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
      }
      v8 = TranslateJetError(v16);
      goto LABEL_40;
    }
    v17 = JetUpdate(*a2, tableid, 0, 0, 0);
    if ( !v17 )
    {
      v8 = CTnoJetSession::CommitTransaction((CTnoJetSession *)v21);
      if ( !v8 )
        goto LABEL_40;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_40;
      }
      v10 = 89;
LABEL_39:
      WPP_SF_d(*((_QWORD *)v9 + 12), v10, WPP_817cd87503153d87380e6127cb13644a_Traceguids, v8);
      goto LABEL_40;
    }
    v8 = TranslateJetError(v17);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_40;
    }
    v15 = 88;
  }
  WPP_SF_Dd(*((_QWORD *)v14 + 12), v15, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
LABEL_40:
  CTnoJetSession::~CTnoJetSession((CTnoJetSession *)v21);
  operator delete(v6);
  return v8;
}

```

## disassembly

```asm
0x18005983c  mov     [rsp-8+arg_0], rbx
0x180059841  push    rbp
0x180059842  push    rsi
0x180059843  push    rdi
0x180059844  push    r12
0x180059846  push    r13
0x180059848  push    r14
0x18005984a  push    r15
0x18005984c  lea     rbp, [rsp-0B0h]
0x180059854  sub     rsp, 1B0h
0x18005985b  mov     rax, cs:__security_cookie
0x180059862  xor     rax, rsp
0x180059865  mov     [rbp+0E0h+var_40], rax
0x18005986c  mov     r14, r8
0x18005986f  mov     rsi, rdx
0x180059872  mov     r15, rcx
0x180059875  mov     rcx, cs:WPP_GLOBAL_Control
0x18005987c  lea     rax, WPP_GLOBAL_Control
0x180059883  mov     r13d, 4
0x180059889  cmp     rcx, rax
0x18005988c  jz      short loc_1800598AE
0x18005988e  test    [rcx+6Ch], r13b
0x180059892  jz      short loc_1800598AE
0x180059894  cmp     [rcx+69h], r13b
0x180059898  jb      short loc_1800598AE
0x18005989a  mov     rcx, [rcx+60h]
0x18005989e  lea     edx, [r13+4Fh]
0x1800598a2  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x1800598a9  call    WPP_SF_
0x1800598ae  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800598b2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800598b9  mov     ecx, 500h; unsigned __int64
0x1800598be  mov     [rsp+1E0h+tableid], rbx
0x1800598c3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800598c8  xor     r12d, r12d
0x1800598cb  mov     rdi, rax
0x1800598ce  test    rax, rax
0x1800598d1  jnz     short loc_1800598DB
0x1800598d3  lea     eax, [rbx+0Fh]
0x1800598d6  jmp     loc_180059BDA
0x1800598db  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800598e3  lea     rax, ??_7CTnoJetSession@@6B@; const CTnoJetSession::`vftable'
0x1800598ea  mov     [rsp+1E0h+var_180], rax
0x1800598ef  lea     rcx, [rbp+0E0h+var_148]; void *
0x1800598f3  mov     rax, [rsi]
0x1800598f6  mov     r8d, 100h; Size
0x1800598fc  mov     rdx, rbx; Val
0x1800598ff  mov     [rsp+1E0h+var_178], rax
0x180059904  mov     [rsp+1E0h+var_1A0], r12d
0x180059909  mov     [rsp+1E0h+var_190], r12d
0x18005990e  mov     [rsp+1E0h+var_170], r12w
0x180059914  mov     [rbp+0E0h+var_14C], r12d
0x180059918  mov     [rbp+0E0h+var_48], r12d
0x18005991f  movups  [rsp+1E0h+var_16C], xmm0
0x180059924  movups  [rbp+0E0h+var_15C], xmm0
0x180059928  call    memset_0
0x18005992d  lea     rcx, [rsp+1E0h+var_180]; this
0x180059932  call    ?BeginTransaction@CTnoJetSession@@UEAAKXZ; CTnoJetSession::BeginTransaction(void)
0x180059937  mov     ebx, eax
0x180059939  test    eax, eax
0x18005993b  jz      short loc_180059972
0x18005993d  mov     rcx, cs:WPP_GLOBAL_Control
0x180059944  lea     rax, WPP_GLOBAL_Control
0x18005994b  cmp     rcx, rax
0x18005994e  jz      loc_180059BC6
0x180059954  test    [rcx+6Ch], r13b
0x180059958  jz      loc_180059BC6
0x18005995e  cmp     byte ptr [rcx+69h], 1
0x180059962  jb      loc_180059BC6
0x180059968  mov     edx, 54h ; 'T'
0x18005996d  jmp     loc_180059BB3
0x180059972  mov     edx, [r14]; unsigned int
0x180059975  lea     rax, [rsp+1E0h+tableid]
0x18005997a  mov     [rsp+1E0h+var_1B0], rax; JET_TABLEID *
0x18005997f  lea     r8, aPubcatalogboot; "PubCatalogBootstrapTable"
0x180059986  mov     [rsp+1E0h+var_1B8], 8; JET_GRBIT
0x18005998e  lea     rcx, [rsp+1E0h+var_180]; this
0x180059993  xor     r9d, r9d; void *
0x180059996  mov     dword ptr [rsp+1E0h+pcbActual], r12d; unsigned int
0x18005999b  call    ?OpenTable@CTnoJetSession@@UEAAKKPEBGPEBXKKPEA_K@Z; CTnoJetSession::OpenTable(ulong,ushort const *,void const *,ulong,ulong,unsigned __int64 *)
0x1800599a0  mov     ebx, eax
0x1800599a2  test    eax, eax
0x1800599a4  jz      short loc_1800599DB
0x1800599a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800599ad  lea     rax, WPP_GLOBAL_Control
0x1800599b4  cmp     rcx, rax
0x1800599b7  jz      loc_180059BC6
0x1800599bd  test    [rcx+6Ch], r13b
0x1800599c1  jz      loc_180059BC6
0x1800599c7  cmp     byte ptr [rcx+69h], 1
0x1800599cb  jb      loc_180059BC6
0x1800599d1  mov     edx, 55h ; 'U'
0x1800599d6  jmp     loc_180059BB3
0x1800599db  xor     edx, edx; Val
0x1800599dd  mov     r8d, 500h; Size
0x1800599e3  mov     rcx, rdi; void *
0x1800599e6  call    memset_0
0x1800599eb  mov     eax, [r15+1144h]
0x1800599f2  xor     r8d, r8d; prep
0x1800599f5  mov     [rdi], eax
0x1800599f7  lea     rax, [rsp+1E0h+var_1A0]
0x1800599fc  mov     [rdi+8], rax
0x180059a00  mov     [rdi+10h], r13d
0x180059a04  mov     dword ptr [rdi+1Ch], 1
0x180059a0b  mov     eax, [r15+1148h]
0x180059a12  mov     [rdi+2Ch], r12d
0x180059a16  mov     [rdi+3Ch], r12
0x180059a1a  mov     [rdi+48h], r12
0x180059a1e  mov     [rdi+28h], eax
0x180059a21  lea     rax, [rsp+1E0h+var_1A0]
0x180059a26  mov     [rdi+30h], rax
0x180059a2a  mov     [rdi+38h], r13d
0x180059a2e  mov     dword ptr [rdi+44h], 1
0x180059a35  mov     eax, [r15+114Ch]
0x180059a3c  mov     [rdi+54h], r12d
0x180059a40  mov     [rdi+64h], r12
0x180059a44  mov     [rdi+70h], r12
0x180059a48  mov     [rdi+50h], eax
0x180059a4b  lea     rax, [rsp+1E0h+var_190]
0x180059a50  mov     [rdi+58h], rax
0x180059a54  mov     [rdi+60h], r13d
0x180059a58  mov     dword ptr [rdi+6Ch], 1
0x180059a5f  mov     rdx, [rsp+1E0h+tableid]; tableid
0x180059a64  mov     rcx, [rsi]; sesid
0x180059a67  call    cs:__imp_JetPrepareUpdate
0x180059a6d  mov     r9d, eax
0x180059a70  test    eax, eax
0x180059a72  jz      short loc_180059AC6
0x180059a74  mov     ecx, eax; int
0x180059a76  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180059a7b  mov     ebx, eax
0x180059a7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180059a84  lea     rax, WPP_GLOBAL_Control
0x180059a8b  cmp     rcx, rax
0x180059a8e  jz      loc_180059BC6
0x180059a94  test    [rcx+6Ch], r13b
0x180059a98  jz      loc_180059BC6
0x180059a9e  cmp     byte ptr [rcx+69h], 1
0x180059aa2  jb      loc_180059BC6
0x180059aa8  mov     edx, 56h ; 'V'
0x180059aad  mov     rcx, [rcx+60h]
0x180059ab1  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x180059ab8  mov     dword ptr [rsp+1E0h+pcbActual], ebx
0x180059abc  call    WPP_SF_Dd
0x180059ac1  jmp     loc_180059BC6
0x180059ac6  mov     rdx, [rsp+1E0h+tableid]; tableid
0x180059acb  mov     r9d, 3; csetcolumn
0x180059ad1  mov     rcx, [rsi]; sesid
0x180059ad4  mov     r8, rdi; psetcolumn
0x180059ad7  call    cs:__imp_JetSetColumns
0x180059add  mov     ebx, eax
0x180059adf  test    eax, eax
0x180059ae1  jz      short loc_180059B2D
0x180059ae3  mov     rcx, cs:WPP_GLOBAL_Control
0x180059aea  lea     rax, WPP_GLOBAL_Control
0x180059af1  cmp     rcx, rax
0x180059af4  jz      short loc_180059B1F
0x180059af6  test    [rcx+6Ch], r13b
0x180059afa  jz      short loc_180059B1F
0x180059afc  cmp     byte ptr [rcx+69h], 1
0x180059b00  jb      short loc_180059B1F
0x180059b02  mov     rcx, [rcx+60h]
0x180059b06  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x180059b0d  mov     edx, 57h ; 'W'
0x180059b12  mov     dword ptr [rsp+1E0h+pcbActual], r12d
0x180059b17  mov     r9d, ebx
0x180059b1a  call    WPP_SF_Dd
0x180059b1f  mov     ecx, ebx; int
0x180059b21  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180059b26  mov     ebx, eax
0x180059b28  jmp     loc_180059BC6
0x180059b2d  mov     rdx, [rsp+1E0h+tableid]; tableid
0x180059b32  xor     r9d, r9d; cbBookmark
0x180059b35  mov     rcx, [rsi]; sesid
0x180059b38  xor     r8d, r8d; pvBookmark
0x180059b3b  mov     [rsp+1E0h+pcbActual], r12; pcbActual
0x180059b40  call    cs:__imp_JetUpdate
0x180059b46  mov     r9d, eax
0x180059b49  test    eax, eax
0x180059b4b  jz      short loc_180059B7F
0x180059b4d  mov     ecx, eax; int
0x180059b4f  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180059b54  mov     ebx, eax
0x180059b56  mov     rcx, cs:WPP_GLOBAL_Control
0x180059b5d  lea     rax, WPP_GLOBAL_Control
0x180059b64  cmp     rcx, rax
0x180059b67  jz      short loc_180059BC6
0x180059b69  test    [rcx+6Ch], r13b
0x180059b6d  jz      short loc_180059BC6
0x180059b6f  cmp     byte ptr [rcx+69h], 1
0x180059b73  jb      short loc_180059BC6
0x180059b75  mov     edx, 58h ; 'X'
0x180059b7a  jmp     loc_180059AAD
0x180059b7f  lea     rcx, [rsp+1E0h+var_180]; this
0x180059b84  call    ?CommitTransaction@CTnoJetSession@@UEAAKXZ; CTnoJetSession::CommitTransaction(void)
0x180059b89  mov     ebx, eax
0x180059b8b  test    eax, eax
0x180059b8d  jz      short loc_180059BC6
0x180059b8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180059b96  lea     rax, WPP_GLOBAL_Control
0x180059b9d  cmp     rcx, rax
0x180059ba0  jz      short loc_180059BC6
0x180059ba2  test    [rcx+6Ch], r13b
0x180059ba6  jz      short loc_180059BC6
0x180059ba8  cmp     byte ptr [rcx+69h], 1
0x180059bac  jb      short loc_180059BC6
0x180059bae  mov     edx, 59h ; 'Y'
0x180059bb3  mov     rcx, [rcx+60h]
0x180059bb7  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x180059bbe  mov     r9d, ebx
0x180059bc1  call    WPP_SF_d
0x180059bc6  lea     rcx, [rsp+1E0h+var_180]; this
0x180059bcb  call    ??1CTnoJetSession@@UEAA@XZ; CTnoJetSession::~CTnoJetSession(void)
0x180059bd0  mov     rcx, rdi; Block
0x180059bd3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180059bd8  mov     eax, ebx
0x180059bda  mov     rcx, [rbp+0E0h+var_40]
0x180059be1  xor     rcx, rsp; StackCookie
0x180059be4  call    __security_check_cookie
0x180059be9  mov     rbx, [rsp+1E0h+arg_0]
0x180059bf1  add     rsp, 1B0h
0x180059bf8  pop     r15
0x180059bfa  pop     r14
0x180059bfc  pop     r13
0x180059bfe  pop     r12
0x180059c00  pop     rdi
0x180059c01  pop     rsi
0x180059c02  pop     rbp
0x180059c03  retn
```
