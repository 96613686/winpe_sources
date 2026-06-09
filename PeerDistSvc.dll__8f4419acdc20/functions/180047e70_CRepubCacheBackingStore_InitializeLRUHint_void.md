# CRepubCacheBackingStore::InitializeLRUHint(void)

- ea: `0x180047e70`
- end: `0x180048299`
- name: `?InitializeLRUHint@CRepubCacheBackingStore@@AEAAKXZ`
- size: `1065`
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
- `0x180047e70`
- `0x180062d1c`
- `0x180139428`
- `0x18013a410`
- `0x18013a680`
- `0x18013aaf0`
- `0x18013ab7c`
- `0x180144882`
- `0x1801448c0`

## import_xrefs

- `ESENT!JetRetrieveColumns` at `0x180048142`
- `ESENT!JetRetrieveColumns` at `0x180048142`
- `ESENT!JetMove` at `0x18004809e`
- `ESENT!JetMove` at `0x18004809e`
- `ESENT!JetSetCurrentIndexW` at `0x180048079`
- `ESENT!JetSetCurrentIndexW` at `0x180048079`

## pseudocode

```c
__int64 __fastcall CRepubCacheBackingStore::InitializeLRUHint(CRepubCacheBackingStore *this)
{
  unsigned int started; // eax
  unsigned int RepubFileTableName; // ebx
  CHostedCacheMsgEncoding *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  __int64 v7; // r14
  unsigned __int64 v8; // rax
  JET_ERR v9; // eax
  JET_ERR v10; // eax
  CHostedCacheMsgEncoding *v11; // rcx
  unsigned __int64 v12; // r8
  JET_COLUMNID v13; // eax
  unsigned int v15; // [rsp+40h] [rbp-C0h] BYREF
  JET_TABLEID tableid; // [rsp+48h] [rbp-B8h] BYREF
  JET_SESID sesid; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v18; // [rsp+58h] [rbp-A8h] BYREF
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v20[2]; // [rsp+90h] [rbp-70h] BYREF
  __int16 v21; // [rsp+A0h] [rbp-60h]
  __m128i si128; // [rsp+A4h] [rbp-5Ch]
  __m128i v23; // [rsp+B4h] [rbp-4Ch]
  int v24; // [rsp+C4h] [rbp-3Ch]
  _BYTE v25[256]; // [rsp+C8h] [rbp-38h] BYREF
  int v26; // [rsp+1C8h] [rbp+C8h]
  unsigned __int16 v27[264]; // [rsp+1D0h] [rbp+D0h] BYREF

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 225, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
  }
  v15 = -1;
  v21 = 0;
  memset(&pretrievecolumn, 0, sizeof(pretrievecolumn));
  sesid = -1;
  tableid = -1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v20[0] = &CTnoJetSession::`vftable';
  v23 = si128;
  v20[1] = -1;
  v24 = 0;
  v26 = 0;
  memset_0(v25, -1, sizeof(v25));
  started = CTnoJetSession::StartSession((CTnoJetSession *)v20, *((_QWORD *)this + 27), &sesid);
  RepubFileTableName = started;
  if ( started )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_53;
    }
    v5 = 226;
  }
  else
  {
    started = CTnoJetSession::OpenDatabase((CTnoJetSession *)v20, (const unsigned __int16 *)this + 1396, 0, &v15);
    RepubFileTableName = started;
    if ( !started )
    {
      v7 = 0;
      *((_QWORD *)this + 6289) = 0;
      v8 = 0;
      v18 = 0;
      while ( 1 )
      {
        if ( (unsigned int)v7 >= *((_DWORD *)this + 1968) )
        {
          *((_QWORD *)this + 6289) = v8 + 1;
          goto LABEL_53;
        }
        RepubFileTableName = GetRepubFileTableName(*((_WORD *)this + 384 * v7 + 2016), v27);
        if ( RepubFileTableName )
          break;
        RepubFileTableName = CTnoJetSession::OpenTable((CTnoJetSession *)v20, v15, v27, 0, 0, 4u, &tableid);
        if ( RepubFileTableName )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            goto LABEL_53;
          }
          v5 = 229;
          goto LABEL_51;
        }
        v9 = JetSetCurrentIndexW(sesid, tableid, L"LRUHintIndex");
        if ( v9 )
        {
          RepubFileTableName = TranslateJetError(v9);
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 230, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
          }
          goto LABEL_53;
        }
        v10 = JetMove(sesid, tableid, 0x7FFFFFFF, 1u);
        if ( v10 == -1603 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 231, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
            v11 = WPP_GLOBAL_Control;
          }
          v12 = 0;
          v18 = 0;
        }
        else
        {
          if ( v10 )
            goto LABEL_38;
          v13 = *((_DWORD *)this + 192 * v7 + 1167);
          *(&pretrievecolumn.columnid + 1) = 0;
          pretrievecolumn.columnid = v13;
          memset(&pretrievecolumn.cbData, 0, 32);
          pretrievecolumn.pvData = &v18;
          pretrievecolumn.cbData = 8;
          pretrievecolumn.itagSequence = 1;
          v10 = JetRetrieveColumns(sesid, tableid, &pretrievecolumn, 1u);
          if ( v10 )
          {
LABEL_38:
            RepubFileTableName = TranslateJetError(v10);
            goto LABEL_53;
          }
          v12 = v18;
          v11 = WPP_GLOBAL_Control;
        }
        if ( v11 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)v11 + 108) & 4) != 0
          && *((_BYTE *)v11 + 105) >= 4u )
        {
          WPP_SF_q(*((_QWORD *)v11 + 12), 232, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
          v12 = v18;
        }
        v8 = *((_QWORD *)this + 6289);
        if ( v12 > v8 )
          v8 = v12;
        v7 = (unsigned int)(v7 + 1);
        *((_QWORD *)this + 6289) = v8;
      }
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_53;
      }
      v5 = 228;
LABEL_51:
      v6 = RepubFileTableName;
      goto LABEL_11;
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_53;
    }
    v5 = 227;
  }
  v6 = started;
LABEL_11:
  WPP_SF_d(*((_QWORD *)v4 + 12), v5, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v6);
LABEL_53:
  CTnoJetSession::~CTnoJetSession((CTnoJetSession *)v20);
  return RepubFileTableName;
}

```

## disassembly

```asm
0x180047e70  mov     [rsp-8+arg_8], rbx
0x180047e75  mov     [rsp-8+arg_10], rsi
0x180047e7a  push    rbp
0x180047e7b  push    rdi
0x180047e7c  push    r14
0x180047e7e  lea     rbp, [rsp-2F0h]
0x180047e86  sub     rsp, 3F0h
0x180047e8d  mov     rax, cs:__security_cookie
0x180047e94  xor     rax, rsp
0x180047e97  mov     [rbp+300h+var_20], rax
0x180047e9e  mov     rdi, rcx
0x180047ea1  mov     rcx, cs:WPP_GLOBAL_Control
0x180047ea8  lea     rsi, WPP_GLOBAL_Control
0x180047eaf  lea     r14, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x180047eb6  cmp     rcx, rsi
0x180047eb9  jz      short loc_180047ED8
0x180047ebb  test    byte ptr [rcx+6Ch], 4
0x180047ebf  jz      short loc_180047ED8
0x180047ec1  cmp     byte ptr [rcx+69h], 4
0x180047ec5  jb      short loc_180047ED8
0x180047ec7  mov     rcx, [rcx+60h]
0x180047ecb  mov     edx, 0E1h
0x180047ed0  mov     r8, r14
0x180047ed3  call    WPP_SF_
0x180047ed8  xorps   xmm0, xmm0
0x180047edb  mov     [rsp+400h+var_3C0], 0FFFFFFFFh
0x180047ee3  or      rdx, 0FFFFFFFFFFFFFFFFh; Val
0x180047ee7  mov     [rbp+300h+var_360], 0
0x180047eed  movups  xmmword ptr [rsp+400h+pretrievecolumn.columnid], xmm0
0x180047ef2  lea     rax, ??_7CTnoJetSession@@6B@; const CTnoJetSession::`vftable'
0x180047ef9  mov     r8d, 100h; Size
0x180047eff  movups  xmmword ptr [rsp+400h+pretrievecolumn.cbData], xmm0
0x180047f04  lea     rcx, [rbp+300h+var_338]; void *
0x180047f08  mov     [rsp+400h+sesid], rdx
0x180047f0d  movups  xmmword ptr [rbp+300h+pretrievecolumn.itagSequence], xmm0
0x180047f11  mov     [rsp+400h+tableid], rdx
0x180047f16  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180047f1e  movups  [rbp+300h+var_35C], xmm0
0x180047f22  mov     [rbp+300h+var_370], rax
0x180047f26  movups  [rbp+300h+var_34C], xmm0
0x180047f2a  mov     [rbp+300h+var_368], rdx
0x180047f2e  mov     [rbp+300h+var_33C], 0
0x180047f35  mov     [rbp+300h+var_238], 0
0x180047f3f  call    memset_0
0x180047f44  mov     rdx, [rdi+0D8h]; unsigned __int64
0x180047f4b  lea     r8, [rsp+400h+sesid]; unsigned __int64 *
0x180047f50  lea     rcx, [rbp+300h+var_370]; this
0x180047f54  call    ?StartSession@CTnoJetSession@@UEAAK_KPEA_K@Z; CTnoJetSession::StartSession(unsigned __int64,unsigned __int64 *)
0x180047f59  mov     ebx, eax
0x180047f5b  test    eax, eax
0x180047f5d  jz      short loc_180047F9C
0x180047f5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180047f66  cmp     rcx, rsi
0x180047f69  jz      loc_180048267
0x180047f6f  test    byte ptr [rcx+6Ch], 4
0x180047f73  jz      loc_180048267
0x180047f79  cmp     byte ptr [rcx+69h], 1
0x180047f7d  jb      loc_180048267
0x180047f83  mov     edx, 0E2h
0x180047f88  mov     r9d, eax
0x180047f8b  mov     r8, r14
0x180047f8e  mov     rcx, [rcx+60h]
0x180047f92  call    WPP_SF_d
0x180047f97  jmp     loc_180048267
0x180047f9c  lea     rdx, [rdi+0AE8h]; unsigned __int16 *
0x180047fa3  xor     r8d, r8d; unsigned int
0x180047fa6  lea     r9, [rsp+400h+var_3C0]; unsigned int *
0x180047fab  lea     rcx, [rbp+300h+var_370]; this
0x180047faf  call    ?OpenDatabase@CTnoJetSession@@UEAAKPEBGKPEAK@Z; CTnoJetSession::OpenDatabase(ushort const *,ulong,ulong *)
0x180047fb4  mov     ebx, eax
0x180047fb6  test    eax, eax
0x180047fb8  jz      short loc_180047FE5
0x180047fba  mov     rcx, cs:WPP_GLOBAL_Control
0x180047fc1  cmp     rcx, rsi
0x180047fc4  jz      loc_180048267
0x180047fca  test    byte ptr [rcx+6Ch], 4
0x180047fce  jz      loc_180048267
0x180047fd4  cmp     byte ptr [rcx+69h], 1
0x180047fd8  jb      loc_180048267
0x180047fde  mov     edx, 0E3h
0x180047fe3  jmp     short loc_180047F88
0x180047fe5  xor     r14d, r14d
0x180047fe8  mov     qword ptr [rdi+0C488h], 0
0x180047ff3  xor     eax, eax
0x180047ff5  mov     [rsp+400h+var_3A8], 0
0x180047ffe  cmp     r14d, [rdi+1EC0h]
0x180048005  jnb     loc_18004825D
0x18004800b  lea     rsi, [r14+r14*2]
0x18004800f  shl     rsi, 8
0x180048013  lea     rdx, [rbp+300h+var_230]; unsigned __int16 *
0x18004801a  movzx   ecx, word ptr [rsi+rdi+0FC0h]; __int16
0x180048022  call    ?GetRepubFileTableName@@YAKFQEAG@Z; GetRepubFileTableName(short,ushort * const)
0x180048027  mov     ebx, eax
0x180048029  test    eax, eax
0x18004802b  jnz     loc_18004822A
0x180048031  mov     edx, [rsp+400h+var_3C0]; unsigned int
0x180048035  lea     rax, [rsp+400h+tableid]
0x18004803a  mov     [rsp+400h+var_3D0], rax; JET_TABLEID *
0x18004803f  lea     r8, [rbp+300h+var_230]; unsigned __int16 *
0x180048046  mov     [rsp+400h+var_3D8], 4; JET_GRBIT
0x18004804e  lea     rcx, [rbp+300h+var_370]; this
0x180048052  xor     r9d, r9d; void *
0x180048055  mov     [rsp+400h+var_3E0], ebx; unsigned int
0x180048059  call    ?OpenTable@CTnoJetSession@@UEAAKKPEBGPEBXKKPEA_K@Z; CTnoJetSession::OpenTable(ulong,ushort const *,void const *,ulong,ulong,unsigned __int64 *)
0x18004805e  mov     ebx, eax
0x180048060  test    eax, eax
0x180048062  jnz     loc_180048204
0x180048068  mov     r8, cs:szIndexName; szIndexName
0x18004806f  mov     rdx, [rsp+400h+tableid]; tableid
0x180048074  mov     rcx, [rsp+400h+sesid]; sesid
0x180048079  call    cs:__imp_JetSetCurrentIndexW
0x18004807f  mov     r9d, eax
0x180048082  test    eax, eax
0x180048084  jnz     loc_1800481B8
0x18004808a  mov     rdx, [rsp+400h+tableid]; tableid
0x18004808f  lea     r9d, [rbx+1]; grbit
0x180048093  mov     rcx, [rsp+400h+sesid]; sesid
0x180048098  mov     r8d, 7FFFFFFFh; cRow
0x18004809e  call    cs:__imp_JetMove
0x1800480a4  cmp     eax, 0FFFFF9BDh
0x1800480a9  jnz     short loc_1800480F0
0x1800480ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800480b2  lea     rsi, WPP_GLOBAL_Control
0x1800480b9  cmp     rcx, rsi
0x1800480bc  jz      short loc_1800480E6
0x1800480be  test    byte ptr [rcx+6Ch], 4
0x1800480c2  jz      short loc_1800480E6
0x1800480c4  cmp     byte ptr [rcx+69h], 4
0x1800480c8  jb      short loc_1800480E6
0x1800480ca  mov     rcx, [rcx+60h]
0x1800480ce  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x1800480d5  mov     edx, 0E7h
0x1800480da  call    WPP_SF_
0x1800480df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800480e6  xor     r8d, r8d
0x1800480e9  mov     [rsp+400h+var_3A8], r8
0x1800480ee  jmp     short loc_18004815F
0x1800480f0  test    eax, eax
0x1800480f2  jnz     loc_1800481AA
0x1800480f8  mov     eax, [rsi+rdi+123Ch]
0x1800480ff  lea     r8, [rsp+400h+pretrievecolumn]; pretrievecolumn
0x180048104  mov     rdx, [rsp+400h+tableid]; tableid
0x180048109  xorps   xmm0, xmm0
0x18004810c  mov     rcx, [rsp+400h+sesid]; sesid
0x180048111  mov     r9d, 1; cretrievecolumn
0x180048117  movups  xmmword ptr [rsp+400h+pretrievecolumn.columnid], xmm0
0x18004811c  mov     [rsp+400h+pretrievecolumn.columnid], eax
0x180048120  lea     rax, [rsp+400h+var_3A8]
0x180048125  movups  xmmword ptr [rsp+400h+pretrievecolumn.cbData], xmm0
0x18004812a  mov     [rsp+400h+pretrievecolumn.pvData], rax
0x18004812f  movups  xmmword ptr [rbp+300h+pretrievecolumn.itagSequence], xmm0
0x180048133  mov     [rsp+400h+pretrievecolumn.cbData], 8
0x18004813b  mov     [rbp+300h+pretrievecolumn.itagSequence], 1
0x180048142  call    cs:__imp_JetRetrieveColumns
0x180048148  test    eax, eax
0x18004814a  jnz     short loc_1800481AA
0x18004814c  mov     r8, [rsp+400h+var_3A8]
0x180048151  lea     rsi, WPP_GLOBAL_Control
0x180048158  mov     rcx, cs:WPP_GLOBAL_Control
0x18004815f  cmp     rcx, rsi
0x180048162  jz      short loc_18004818D
0x180048164  test    byte ptr [rcx+6Ch], 4
0x180048168  jz      short loc_18004818D
0x18004816a  cmp     byte ptr [rcx+69h], 4
0x18004816e  jb      short loc_18004818D
0x180048170  mov     rcx, [rcx+60h]
0x180048174  mov     r9, r8
0x180048177  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004817e  mov     edx, 0E8h
0x180048183  call    WPP_SF_q
0x180048188  mov     r8, [rsp+400h+var_3A8]
0x18004818d  mov     rax, [rdi+0C488h]
0x180048194  cmp     r8, rax
0x180048197  cmova   rax, r8
0x18004819b  inc     r14d
0x18004819e  mov     [rdi+0C488h], rax
0x1800481a5  jmp     loc_180047FFE
0x1800481aa  mov     ecx, eax; int
0x1800481ac  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x1800481b1  mov     ebx, eax
0x1800481b3  jmp     loc_180048267
0x1800481b8  mov     ecx, r9d; int
0x1800481bb  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x1800481c0  mov     ebx, eax
0x1800481c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800481c9  lea     rax, WPP_GLOBAL_Control
0x1800481d0  cmp     rcx, rax
0x1800481d3  jz      loc_180048267
0x1800481d9  test    byte ptr [rcx+6Ch], 4
0x1800481dd  jz      loc_180048267
0x1800481e3  cmp     byte ptr [rcx+69h], 1
0x1800481e7  jb      short loc_180048267
0x1800481e9  mov     rcx, [rcx+60h]
0x1800481ed  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x1800481f4  mov     edx, 0E6h
0x1800481f9  mov     [rsp+400h+var_3E0], ebx
0x1800481fd  call    WPP_SF_Dd
0x180048202  jmp     short loc_180048267
0x180048204  mov     rcx, cs:WPP_GLOBAL_Control
0x18004820b  lea     rax, WPP_GLOBAL_Control
0x180048212  cmp     rcx, rax
0x180048215  jz      short loc_180048267
0x180048217  test    byte ptr [rcx+6Ch], 4
0x18004821b  jz      short loc_180048267
0x18004821d  cmp     byte ptr [rcx+69h], 1
0x180048221  jb      short loc_180048267
0x180048223  mov     edx, 0E5h
0x180048228  jmp     short loc_18004824E
0x18004822a  mov     rcx, cs:WPP_GLOBAL_Control
0x180048231  lea     rax, WPP_GLOBAL_Control
0x180048238  cmp     rcx, rax
0x18004823b  jz      short loc_180048267
0x18004823d  test    byte ptr [rcx+6Ch], 4
0x180048241  jz      short loc_180048267
0x180048243  cmp     byte ptr [rcx+69h], 1
0x180048247  jb      short loc_180048267
0x180048249  mov     edx, 0E4h
0x18004824e  mov     r9d, ebx
0x180048251  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x180048258  jmp     loc_180047F8E
0x18004825d  inc     rax
0x180048260  mov     [rdi+0C488h], rax
0x180048267  lea     rcx, [rbp+300h+var_370]; this
0x18004826b  call    ??1CTnoJetSession@@UEAA@XZ; CTnoJetSession::~CTnoJetSession(void)
0x180048270  mov     eax, ebx
0x180048272  mov     rcx, [rbp+300h+var_20]
0x180048279  xor     rcx, rsp; StackCookie
0x18004827c  call    __security_check_cookie
0x180048281  lea     r11, [rsp+400h+var_10]
0x180048289  mov     rbx, [r11+28h]
0x18004828d  mov     rsi, [r11+30h]
0x180048291  mov     rsp, r11
0x180048294  pop     r14
0x180048296  pop     rdi
0x180048297  pop     rbp
0x180048298  retn
```
