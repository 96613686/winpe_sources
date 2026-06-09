# CHstsContainerProps::SetHstsEntry(unsigned __int64,_RPC_HSTS_ENTRY *,int)

- ea: `0x180093448`
- end: `0x1800939b0`
- name: `?SetHstsEntry@CHstsContainerProps@@QEAAJ_KPEAU_RPC_HSTS_ENTRY@@H@Z`
- size: `1384`
- prototype: `__int64 __fastcall(CHstsContainerProps *__hidden this, unsigned __int64, struct _RPC_HSTS_ENTRY *, int)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180134080`
- `0x1801af6f4`

## callees

- `0x180020fc4`
- `0x180021360`
- `0x18007ec9c`
- `0x180083540`
- `0x1800838d8`
- `0x180083dc4`
- `0x1800861f8`
- `0x180093448`
- `0x1800939b8`
- `0x180093cf0`
- `0x1800ace84`
- `0x1800ee168`
- `0x1800fa844`
- `0x18014a7a0`
- `0x1801dcfe4`
- `0x1801e1790`
- `0x1801e1b00`
- `0x1801e3c78`

## import_xrefs

- `ESENT!JetDelete` at `0x1800936ef`
- `ESENT!JetDelete` at `0x1800936ef`
- `ESENT!JetCommitTransaction` at `0x1800938f9`
- `ESENT!JetCommitTransaction` at `0x1800938f9`
- `ESENT!JetUpdate` at `0x1800938da`
- `ESENT!JetUpdate` at `0x1800938da`
- `ESENT!JetPrepareUpdate` at `0x18009377a`
- `ESENT!JetPrepareUpdate` at `0x180093994`
- `ESENT!JetPrepareUpdate` at `0x18009377a`
- `ESENT!JetPrepareUpdate` at `0x180093994`
- `ESENT!JetRollback` at `0x1800939a5`
- `ESENT!JetRollback` at `0x1800939a5`
- `ESENT!JetBeginTransaction` at `0x180093599`
- `ESENT!JetBeginTransaction` at `0x180093599`
- `ESENT!JetMove` at `0x180093653`
- `ESENT!JetMove` at `0x180093653`

## pseudocode

```c
__int64 __fastcall CHstsContainerProps::SetHstsEntry(
        CHstsContainerProps *this,
        unsigned __int64 a2,
        struct _RPC_HSTS_ENTRY *a3,
        int a4)
{
  CHstsContainerProps *v4; // r15
  JET_SESID *v5; // rdi
  int v6; // r13d
  int HstsEntryAtCursor; // ebx
  int v9; // esi
  int v11; // r12d
  int v12; // eax
  unsigned int v13; // r9d
  JET_ERR v14; // eax
  int v15; // eax
  JET_ERR v16; // esi
  unsigned int v17; // r15d
  unsigned __int16 *v18; // rax
  int v19; // ecx
  int v20; // edx
  JET_ERR v21; // eax
  JET_ERR v22; // eax
  JET_ERR v23; // eax
  JET_ERR v24; // eax
  int v26; // [rsp+60h] [rbp-39h]
  CJetContext *v27; // [rsp+68h] [rbp-31h] BYREF
  int v28; // [rsp+70h] [rbp-29h]
  struct CInFlightEntry *v29; // [rsp+78h] [rbp-21h] BYREF
  __int128 v30; // [rsp+80h] [rbp-19h] BYREF
  __int128 v31; // [rsp+90h] [rbp-9h]
  __int64 v32; // [rsp+A0h] [rbp+7h]
  unsigned __int64 v33; // [rsp+A8h] [rbp+Fh] BYREF

  v4 = this;
  v33 = a2;
  v5 = 0;
  v27 = 0;
  v6 = 0;
  v29 = 0;
  v32 = 0;
  v28 = a4;
  v30 = 0;
  v31 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
  {
    WPP_SF_qSliill(
      0,
      a2,
      (_DWORD)a3,
      (_DWORD)a3,
      *(_QWORD *)a3,
      *((_DWORD *)a3 + 3),
      *((_QWORD *)a3 + 2),
      *((_QWORD *)a3 + 3),
      *((_DWORD *)a3 + 8),
      a4);
    a2 = v33;
  }
  HstsEntryAtCursor = CInFlightLocks::AcquireLock(*((CInFlightLocks **)v4 + 10), a2, &v29);
  if ( HstsEntryAtCursor < 0 )
  {
    v9 = 0;
    goto LABEL_5;
  }
  v11 = *((_DWORD *)a3 + 8);
  v12 = CJetContextList::AcquireContext(*((CJetContextList **)v4 + 11), &v27, 0);
  v5 = (JET_SESID *)v27;
  HstsEntryAtCursor = v12;
  if ( v12 < 0
    || (v9 = 1,
        HstsEntryAtCursor = CJetContext::SetCurrentIndex(v27, 1u, L"MinimizedRDomainHash", v13),
        HstsEntryAtCursor < 0)
    || (v14 = JetBeginTransaction(v5[2]), HstsEntryAtCursor = HRESULTFromJET_ERR(v14, 1), HstsEntryAtCursor < 0) )
  {
    v9 = 0;
    goto LABEL_5;
  }
  v15 = SeekToHstsEntryByMinimizedRDomainHash((struct CJetContext *)v5, v33);
  HstsEntryAtCursor = v15;
  if ( v15 >= 0 )
  {
    v16 = 0;
    v17 = 0;
    v26 = 0;
    if ( v15 )
    {
      if ( v11 )
      {
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          WPP_SF_(1036, 17, &WPP_ae00b7117931323f1bc64bef90768346_Traceguids);
        HstsEntryAtCursor = 0;
        goto LABEL_44;
      }
      v26 = 1;
LABEL_39:
      v22 = JetPrepareUpdate(v5[2], v5[4], v17);
      HstsEntryAtCursor = HRESULTFromJET_ERR(v22, 1);
      if ( HstsEntryAtCursor < 0 )
        goto LABEL_44;
      v6 = 1;
      if ( !v17 )
      {
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          WPP_SF_(1036, 18, &WPP_ae00b7117931323f1bc64bef90768346_Traceguids);
        HstsEntryAtCursor = CJetContext::SetBasicColumn((CJetContext *)v5, 1u, &v33, 8u);
        if ( HstsEntryAtCursor < 0 )
          goto LABEL_44;
        HstsEntryAtCursor = CJetContext::SetStringColumn((CJetContext *)v5, 2u, *(const unsigned __int16 **)a3);
        if ( HstsEntryAtCursor < 0 )
          goto LABEL_44;
        HstsEntryAtCursor = CJetContext::SetBasicColumn((CJetContext *)v5, 3u, (char *)a3 + 8, 4u);
        if ( HstsEntryAtCursor < 0 )
          goto LABEL_44;
      }
      HstsEntryAtCursor = CJetContext::SetBasicColumn((CJetContext *)v5, 4u, (char *)a3 + 12, 4u);
      if ( HstsEntryAtCursor < 0 )
        goto LABEL_44;
      HstsEntryAtCursor = CJetContext::SetBasicColumn((CJetContext *)v5, 5u, (char *)a3 + 16, 8u);
      if ( HstsEntryAtCursor < 0 )
        goto LABEL_44;
      HstsEntryAtCursor = CJetContext::SetBasicColumn((CJetContext *)v5, 6u, (char *)a3 + 24, 8u);
      if ( HstsEntryAtCursor < 0 )
        goto LABEL_44;
      v23 = JetUpdate(v5[2], v5[4], 0, 0, 0);
      HstsEntryAtCursor = HRESULTFromJET_ERR(v23, 1);
      if ( HstsEntryAtCursor < 0 )
        goto LABEL_44;
LABEL_54:
      v24 = JetCommitTransaction(v5[2], 1u);
      HstsEntryAtCursor = HRESULTFromJET_ERR(v24, 1);
      if ( HstsEntryAtCursor >= 0 )
      {
        v4 = this;
        v9 = 0;
        v6 = 0;
        if ( v26 && !v28 )
          HstsEntryAtCursor = CHstsContainerProps::AddHstsEntryToBloomFilter(
                                this,
                                *(const unsigned __int16 **)a3,
                                *((_DWORD *)a3 + 2),
                                0,
                                0);
        goto LABEL_5;
      }
      v6 = 0;
LABEL_44:
      v4 = this;
      v9 = 1;
      goto LABEL_5;
    }
    while ( 1 )
    {
      WxHeapFree<_WX_AVL_TABLE>(&v30);
      if ( v16 == -1603 )
        goto LABEL_39;
      HstsEntryAtCursor = HRESULTFromJET_ERR(v16, 1);
      if ( HstsEntryAtCursor < 0 )
        goto LABEL_44;
      HstsEntryAtCursor = GetHstsEntryAtCursor((struct CJetContext *)v5, (struct _RPC_HSTS_ENTRY *)&v30, 0);
      if ( HstsEntryAtCursor < 0 )
        goto LABEL_44;
      v18 = (unsigned __int16 *)v30;
      do
      {
        v19 = *(unsigned __int16 *)((char *)v18 + *(_QWORD *)a3 - v30);
        v20 = *v18 - v19;
        if ( v20 )
          break;
        ++v18;
      }
      while ( v19 );
      if ( !v20 )
        break;
      v16 = JetMove(v5[2], v5[4], 1, 0);
    }
    if ( v11 )
    {
      if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
        WPP_SF_(1036, 14, &WPP_ae00b7117931323f1bc64bef90768346_Traceguids);
      v21 = JetDelete(v5[2], v5[4]);
      v9 = 1;
      HstsEntryAtCursor = HRESULTFromJET_ERR(v21, 1);
      if ( HstsEntryAtCursor < 0 )
      {
        v4 = this;
        goto LABEL_5;
      }
      goto LABEL_54;
    }
    if ( (_QWORD)v31 == 0x7FFFFFFFFFFFFFFFLL )
    {
      if ( (BYTE1(xmmword_180266B60) & 0x10) == 0 )
      {
LABEL_38:
        v17 = 2;
        goto LABEL_39;
      }
      WPP_SF_S(1036, 15, &WPP_ae00b7117931323f1bc64bef90768346_Traceguids, v30);
    }
    if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
      WPP_SF_(1036, 16, &WPP_ae00b7117931323f1bc64bef90768346_Traceguids);
    goto LABEL_38;
  }
LABEL_5:
  WxHeapFree<_WX_AVL_TABLE>(&v30);
  if ( v6 )
    JetPrepareUpdate(v5[2], v5[4], 3u);
  if ( v9 )
    JetRollback(v5[2], 0);
  CJetContextList::ReleaseContext(*((CJetContextList **)v4 + 11), &v27);
  CInFlightLocks::ReleaseLock(*((CInFlightLocks **)v4 + 10), &v29);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 19, &WPP_ae00b7117931323f1bc64bef90768346_Traceguids, (unsigned int)HstsEntryAtCursor);
  return (unsigned int)HstsEntryAtCursor;
}

```

## disassembly

```asm
0x180093448  mov     [rsp-8+arg_18], rbx
0x18009344d  push    rbp
0x18009344e  push    rsi
0x18009344f  push    rdi
0x180093450  push    r12
0x180093452  push    r13
0x180093454  push    r14
0x180093456  push    r15
0x180093458  lea     rbp, [rsp-27h]
0x18009345d  sub     rsp, 0C0h
0x180093464  mov     rax, cs:__security_cookie
0x18009346b  xor     rax, rsp
0x18009346e  mov     [rbp+57h+var_40], rax
0x180093472  xorps   xmm0, xmm0
0x180093475  mov     [rbp+57h+var_98], rcx
0x180093479  mov     r15, rcx
0x18009347c  mov     [rbp+57h+var_48], rdx
0x180093480  xor     ecx, ecx
0x180093482  mov     eax, r9d
0x180093485  mov     [rbp+57h+var_8C], ecx
0x180093488  mov     edi, ecx
0x18009348a  mov     [rbp+57h+var_88], rcx
0x18009348e  mov     r13d, ecx
0x180093491  mov     [rbp+57h+var_78], rcx
0x180093495  mov     r14, r8
0x180093498  mov     [rbp+57h+var_50], rcx
0x18009349c  mov     [rbp+57h+var_80], eax
0x18009349f  movups  [rbp+57h+var_70], xmm0
0x1800934a3  movups  [rbp+57h+var_60], xmm0
0x1800934a7  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800934ae  jnz     loc_180093660
0x1800934b4  mov     rcx, [r15+50h]; this
0x1800934b8  lea     r8, [rbp+57h+var_78]; struct CInFlightEntry **
0x1800934bc  call    ?AcquireLock@CInFlightLocks@@QEAAJ_KPEAPEAVCInFlightEntry@@@Z; CInFlightLocks::AcquireLock(unsigned __int64,CInFlightEntry * *)
0x1800934c1  mov     ebx, eax
0x1800934c3  test    eax, eax
0x1800934c5  jns     loc_180093553
0x1800934cb  mov     [rbp+57h+var_8C], 1BCh
0x1800934d2  mov     esi, edi
0x1800934d4  lea     rcx, [rbp+57h+var_70]
0x1800934d8  call    ??$WxHeapFree@U_WX_AVL_TABLE@@@@YAXPEAPEAU_WX_AVL_TABLE@@@Z; WxHeapFree<_WX_AVL_TABLE>(_WX_AVL_TABLE * *)
0x1800934dd  test    r13d, r13d
0x1800934e0  jnz     loc_180093986
0x1800934e6  test    esi, esi
0x1800934e8  jnz     loc_18009399F
0x1800934ee  mov     rcx, [r15+58h]; this
0x1800934f2  lea     rdx, [rbp+57h+var_88]; struct CJetContext **
0x1800934f6  call    ?ReleaseContext@CJetContextList@@QEAAXPEAPEAVCJetContext@@@Z; CJetContextList::ReleaseContext(CJetContext * *)
0x1800934fb  mov     rcx, [r15+50h]; this
0x1800934ff  lea     rdx, [rbp+57h+var_78]; struct CInFlightEntry **
0x180093503  call    ?ReleaseLock@CInFlightLocks@@QEAAXPEAPEAVCInFlightEntry@@@Z; CInFlightLocks::ReleaseLock(CInFlightEntry * *)
0x180093508  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18009350f  jz      short loc_18009352A
0x180093511  mov     edx, 13h
0x180093516  lea     r8, WPP_ae00b7117931323f1bc64bef90768346_Traceguids
0x18009351d  mov     ecx, 40Ch
0x180093522  mov     r9d, ebx
0x180093525  call    WPP_SF_d
0x18009352a  mov     eax, ebx
0x18009352c  mov     rcx, [rbp+57h+var_40]
0x180093530  xor     rcx, rsp; StackCookie
0x180093533  call    __security_check_cookie
0x180093538  mov     rbx, [rsp+0F0h+arg_18]
0x180093540  add     rsp, 0C0h
0x180093547  pop     r15
0x180093549  pop     r14
0x18009354b  pop     r13
0x18009354d  pop     r12
0x18009354f  pop     rdi
0x180093550  pop     rsi
0x180093551  pop     rbp
0x180093552  retn
0x180093553  mov     rcx, [r15+58h]; this
0x180093557  lea     rdx, [rbp+57h+var_88]; struct CJetContext **
0x18009355b  mov     r12d, [r14+20h]
0x18009355f  xor     r8d, r8d; int *
0x180093562  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x180093567  mov     rdi, [rbp+57h+var_88]
0x18009356b  mov     ebx, eax
0x18009356d  test    eax, eax
0x18009356f  js      loc_18009369F
0x180093575  mov     esi, 1
0x18009357a  lea     r8, aMinimizedrdoma_1; "MinimizedRDomainHash"
0x180093581  mov     edx, esi; unsigned int
0x180093583  mov     rcx, rdi; this
0x180093586  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x18009358b  mov     ebx, eax
0x18009358d  test    eax, eax
0x18009358f  js      loc_1800936AE
0x180093595  mov     rcx, [rdi+10h]; sesid
0x180093599  call    cs:__imp_JetBeginTransaction
0x18009359f  mov     ecx, eax; int
0x1800935a1  mov     edx, esi; int
0x1800935a3  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800935a8  mov     ebx, eax
0x1800935aa  test    eax, eax
0x1800935ac  js      loc_1800936A6
0x1800935b2  mov     rdx, [rbp+57h+var_48]; unsigned __int64
0x1800935b6  mov     rcx, rdi; struct CJetContext *
0x1800935b9  mov     [rbp+57h+var_A0], esi
0x1800935bc  call    ?SeekToHstsEntryByMinimizedRDomainHash@@YAJPEAVCJetContext@@_K@Z; SeekToHstsEntryByMinimizedRDomainHash(CJetContext *,unsigned __int64)
0x1800935c1  mov     ebx, eax
0x1800935c3  test    eax, eax
0x1800935c5  js      loc_1800936B7
0x1800935cb  xor     esi, esi
0x1800935cd  xor     r15d, r15d
0x1800935d0  mov     [rbp+57h+var_90], esi
0x1800935d3  test    eax, eax
0x1800935d5  jnz     loc_1800937F6
0x1800935db  lea     rcx, [rbp+57h+var_70]
0x1800935df  call    ??$WxHeapFree@U_WX_AVL_TABLE@@@@YAXPEAPEAU_WX_AVL_TABLE@@@Z; WxHeapFree<_WX_AVL_TABLE>(_WX_AVL_TABLE * *)
0x1800935e4  cmp     esi, 0FFFFF9BDh
0x1800935ea  jz      loc_18009376A
0x1800935f0  mov     edx, 1; int
0x1800935f5  mov     ecx, esi; int
0x1800935f7  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800935fc  mov     ebx, eax
0x1800935fe  test    eax, eax
0x180093600  js      loc_1800937E1
0x180093606  xor     r8d, r8d; unsigned __int64 *
0x180093609  lea     rdx, [rbp+57h+var_70]; struct _RPC_HSTS_ENTRY *
0x18009360d  mov     rcx, rdi; struct CJetContext *
0x180093610  call    ?GetHstsEntryAtCursor@@YAJPEAVCJetContext@@PEAU_RPC_HSTS_ENTRY@@PEA_K@Z; GetHstsEntryAtCursor(CJetContext *,_RPC_HSTS_ENTRY *,unsigned __int64 *)
0x180093615  mov     ebx, eax
0x180093617  test    eax, eax
0x180093619  js      loc_1800937ED
0x18009361f  mov     r9, qword ptr [rbp+57h+var_70]
0x180093623  mov     r8, [r14]
0x180093626  mov     rax, r9
0x180093629  sub     r8, r9
0x18009362c  movzx   edx, word ptr [rax]
0x18009362f  movzx   ecx, word ptr [rax+r8]
0x180093634  sub     edx, ecx
0x180093636  jnz     short loc_180093640
0x180093638  add     rax, 2
0x18009363c  test    ecx, ecx
0x18009363e  jnz     short loc_18009362C
0x180093640  test    edx, edx
0x180093642  jz      short loc_1800936C3
0x180093644  mov     rdx, [rdi+20h]; tableid
0x180093648  xor     r9d, r9d; grbit
0x18009364b  mov     rcx, [rdi+10h]; sesid
0x18009364f  lea     r8d, [r9+1]; cRow
0x180093653  call    cs:__imp_JetMove
0x180093659  mov     esi, eax
0x18009365b  jmp     loc_1800935DB
0x180093660  mov     [rsp+0F0h+var_A8], eax
0x180093664  mov     r9, r14
0x180093667  mov     eax, [r8+20h]
0x18009366b  mov     [rsp+0F0h+var_B0], eax
0x18009366f  mov     rax, [r8+18h]
0x180093673  mov     [rsp+0F0h+var_B8], rax
0x180093678  mov     rax, [r8+10h]
0x18009367c  mov     [rsp+0F0h+var_C0], rax
0x180093681  mov     eax, [r8+0Ch]
0x180093685  mov     [rsp+0F0h+var_C8], eax
0x180093689  mov     rax, [r8]
0x18009368c  mov     [rsp+0F0h+pcbActual], rax
0x180093691  call    WPP_SF_qSliill
0x180093696  mov     rdx, [rbp+57h+var_48]
0x18009369a  jmp     loc_1800934B4
0x18009369f  mov     [rbp+57h+var_8C], 1C5h
0x1800936a6  mov     esi, r13d
0x1800936a9  jmp     loc_1800934D4
0x1800936ae  mov     [rbp+57h+var_8C], 1C9h
0x1800936b5  jmp     short loc_1800936A6
0x1800936b7  mov     [rbp+57h+var_8C], 1CFh
0x1800936be  jmp     loc_1800934D4
0x1800936c3  test    r12d, r12d
0x1800936c6  jz      short loc_180093716
0x1800936c8  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800936cf  jz      short loc_1800936E7
0x1800936d1  mov     edx, 0Eh
0x1800936d6  lea     r8, WPP_ae00b7117931323f1bc64bef90768346_Traceguids
0x1800936dd  mov     ecx, 40Ch
0x1800936e2  call    WPP_SF_
0x1800936e7  mov     rdx, [rdi+20h]; tableid
0x1800936eb  mov     rcx, [rdi+10h]; sesid
0x1800936ef  call    cs:__imp_JetDelete
0x1800936f5  mov     esi, 1
0x1800936fa  mov     ecx, eax; int
0x1800936fc  mov     edx, esi; int
0x1800936fe  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180093703  mov     ebx, eax
0x180093705  test    eax, eax
0x180093707  jns     loc_1800938F3
0x18009370d  mov     r15, [rbp+57h+var_98]
0x180093711  jmp     loc_1800934D4
0x180093716  mov     rax, 7FFFFFFFFFFFFFFFh
0x180093720  cmp     qword ptr [rbp+57h+var_60], rax
0x180093724  jnz     short loc_180093745
0x180093726  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18009372d  jz      short loc_180093764
0x18009372f  mov     edx, 0Fh
0x180093734  lea     r8, WPP_ae00b7117931323f1bc64bef90768346_Traceguids
0x18009373b  mov     ecx, 40Ch
0x180093740  call    WPP_SF_S
0x180093745  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18009374c  jz      short loc_180093764
0x18009374e  mov     edx, 10h
0x180093753  lea     r8, WPP_ae00b7117931323f1bc64bef90768346_Traceguids
0x18009375a  mov     ecx, 40Ch
0x18009375f  call    WPP_SF_
0x180093764  mov     r15d, 2
0x18009376a  mov     esi, 1
0x18009376f  mov     rdx, [rdi+20h]; tableid
0x180093773  mov     r8d, r15d; prep
0x180093776  mov     rcx, [rdi+10h]; sesid
0x18009377a  call    cs:__imp_JetPrepareUpdate
0x180093780  mov     ecx, eax; int
0x180093782  mov     edx, esi; int
0x180093784  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180093789  mov     ebx, eax
0x18009378b  test    eax, eax
0x18009378d  js      short loc_1800937E1
0x18009378f  mov     r13d, esi
0x180093792  mov     r12d, 4
0x180093798  test    r15d, r15d
0x18009379b  jnz     loc_18009384E
0x1800937a1  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800937a8  jz      short loc_1800937C0
0x1800937aa  lea     edx, [r12+0Eh]
0x1800937af  mov     ecx, 40Ch
0x1800937b4  lea     r8, WPP_ae00b7117931323f1bc64bef90768346_Traceguids
0x1800937bb  call    WPP_SF_
0x1800937c0  mov     r9d, 8; unsigned int
0x1800937c6  lea     r8, [rbp+57h+var_48]; void *
0x1800937ca  mov     edx, esi; unsigned int
0x1800937cc  mov     rcx, rdi; this
0x1800937cf  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x1800937d4  mov     ebx, eax
0x1800937d6  test    eax, eax
0x1800937d8  jns     short loc_18009380C
0x1800937da  mov     [rbp+57h+var_8C], 22Dh
0x1800937e1  mov     r15, [rbp+57h+var_98]
0x1800937e5  mov     esi, [rbp+57h+var_A0]
0x1800937e8  jmp     loc_1800934D4
0x1800937ed  mov     [rbp+57h+var_8C], 1E1h
0x1800937f4  jmp     short loc_1800937E1
0x1800937f6  test    r12d, r12d
0x1800937f9  jnz     loc_180093960
0x1800937ff  lea     esi, [r12+1]
0x180093804  mov     [rbp+57h+var_90], esi
0x180093807  jmp     loc_18009376F
0x18009380c  mov     r8, [r14]; unsigned __int16 *
0x18009380f  mov     edx, 2; unsigned int
0x180093814  mov     rcx, rdi; this
0x180093817  call    ?SetStringColumn@CJetContext@@QEAAJKPEBG@Z; CJetContext::SetStringColumn(ulong,ushort const *)
0x18009381c  mov     ebx, eax
0x18009381e  test    eax, eax
0x180093820  jns     short loc_18009382B
0x180093822  mov     [rbp+57h+var_8C], 22Fh
0x180093829  jmp     short loc_1800937E1
0x18009382b  lea     r8, [r14+8]; void *
0x18009382f  mov     r9d, r12d; unsigned int
0x180093832  mov     edx, 3; unsigned int
0x180093837  mov     rcx, rdi; this
0x18009383a  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x18009383f  mov     ebx, eax
0x180093841  test    eax, eax
0x180093843  jns     short loc_18009384E
0x180093845  mov     [rbp+57h+var_8C], 233h
0x18009384c  jmp     short loc_1800937E1
0x18009384e  lea     r8, [r14+0Ch]; void *
0x180093852  mov     r9d, r12d; unsigned int
0x180093855  mov     edx, r12d; unsigned int
0x180093858  mov     rcx, rdi; this
0x18009385b  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x180093860  mov     ebx, eax
0x180093862  test    eax, eax
0x180093864  jns     short loc_180093872
0x180093866  mov     [rbp+57h+var_8C], 238h
0x18009386d  jmp     loc_1800937E1
0x180093872  mov     r15d, 8
0x180093878  lea     r8, [r14+10h]; void *
0x18009387c  mov     r9d, r15d; unsigned int
0x18009387f  mov     rcx, rdi; this
0x180093882  lea     edx, [r15-3]; unsigned int
0x180093886  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x18009388b  mov     ebx, eax
0x18009388d  test    eax, eax
0x18009388f  jns     short loc_18009389D
0x180093891  mov     [rbp+57h+var_8C], 23Ch
0x180093898  jmp     loc_1800937E1
0x18009389d  lea     r8, [r14+18h]; void *
0x1800938a1  mov     r9d, r15d; unsigned int
0x1800938a4  mov     edx, 6; unsigned int
0x1800938a9  mov     rcx, rdi; this
0x1800938ac  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x1800938b1  mov     ebx, eax
0x1800938b3  test    eax, eax
0x1800938b5  jns     short loc_1800938C3
0x1800938b7  mov     [rbp+57h+var_8C], 240h
0x1800938be  jmp     loc_1800937E1
0x1800938c3  mov     rdx, [rdi+20h]; tableid
0x1800938c7  xor     r9d, r9d; cbBookmark
0x1800938ca  mov     rcx, [rdi+10h]; sesid
0x1800938ce  xor     r8d, r8d; pvBookmark
0x1800938d1  mov     [rsp+0F0h+pcbActual], 0; pcbActual
0x1800938da  call    cs:__imp_JetUpdate
  ... truncated ...
```
