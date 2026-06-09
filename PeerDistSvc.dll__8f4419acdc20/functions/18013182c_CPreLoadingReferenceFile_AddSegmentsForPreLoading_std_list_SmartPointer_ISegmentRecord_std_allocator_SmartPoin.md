# CPreLoadingReferenceFile::AddSegmentsForPreLoading(std::list<SmartPointer<ISegmentRecord>,std::allocator<SmartPointer<ISegmentRecord>>> const &)

- ea: `0x18013182c`
- end: `0x180131d78`
- name: `?AddSegmentsForPreLoading@CPreLoadingReferenceFile@@QEAAKAEBV?$list@V?$SmartPointer@VISegmentRecord@@@@V?$allocator@V?$SmartPointer@VISegmentRecord@@@@@std@@@std@@@Z`
- size: `1356`
- prototype: `__int64 __fastcall(CPreLoadingReferenceFile *this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18012eed0`

## callees

- `0x180008290`
- `0x180009ec4`
- `0x1800521d8`
- `0x18013182c`
- `0x1801331d0`
- `0x18013377c`
- `0x18013937c`
- `0x180139428`
- `0x180139820`
- `0x18013ab7c`
- `0x180144882`
- `0x1801448c0`
- `0x180159010`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x180131ba1`
- `ESENT!JetPrepareUpdate` at `0x180131ba1`
- `ESENT!JetSetColumns` at `0x180131c17`
- `ESENT!JetSetColumns` at `0x180131c17`
- `ESENT!JetUpdate` at `0x180131c91`
- `ESENT!JetUpdate` at `0x180131c91`

## pseudocode

```c
__int64 __fastcall CPreLoadingReferenceFile::AddSegmentsForPreLoading(JET_COLUMNID *this, __int64 ***a2)
{
  unsigned int v5; // eax
  unsigned int v6; // edi
  __int64 **v7; // rbx
  unsigned int v8; // eax
  int v9; // eax
  unsigned int v10; // eax
  unsigned int First; // eax
  unsigned int v12; // eax
  int v13; // edi
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // [rsp+30h] [rbp-1F8h] BYREF
  JET_TABLEID tableid; // [rsp+38h] [rbp-1F0h] BYREF
  JET_SESID sesid; // [rsp+40h] [rbp-1E8h] BYREF
  void **v19; // [rsp+48h] [rbp-1E0h] BYREF
  unsigned int v20; // [rsp+50h] [rbp-1D8h]
  const void *v21; // [rsp+58h] [rbp-1D0h]
  char v22; // [rsp+60h] [rbp-1C8h]
  JET_SETCOLUMN psetcolumn; // [rsp+68h] [rbp-1C0h] BYREF
  const void *v24; // [rsp+90h] [rbp-198h] BYREF
  __int16 v25; // [rsp+98h] [rbp-190h]
  _QWORD v26[4]; // [rsp+A0h] [rbp-188h] BYREF
  _QWORD v27[2]; // [rsp+C0h] [rbp-168h] BYREF
  __int16 v28; // [rsp+D0h] [rbp-158h]
  __m128i si128; // [rsp+D4h] [rbp-154h]
  __m128i v30; // [rsp+E4h] [rbp-144h]
  int v31; // [rsp+F4h] [rbp-134h]
  _BYTE v32[256]; // [rsp+F8h] [rbp-130h] BYREF
  int v33; // [rsp+1F8h] [rbp-30h]

  if ( !a2[1] )
    return 87;
  if ( *((_BYTE *)this + 3784) )
  {
    tableid = -1;
    sesid = -1;
    v27[0] = &CTnoJetSession::`vftable';
    v27[1] = -1;
    v28 = 0;
    v31 = 0;
    v33 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v30 = si128;
    memset_0(v32, -1, sizeof(v32));
    v5 = CPreLoadingReferenceFile::OpenDatabaseObjects(
           (CPreLoadingReferenceFile *)this,
           (struct CTnoJetSession *)v27,
           &sesid,
           &v16,
           &tableid);
    v6 = v5;
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 82, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids, v5);
      }
    }
    else
    {
      v7 = (__int64 **)**a2;
      while ( v7 != *a2 )
      {
        v20 = 0;
        v21 = 0;
        v22 = 1;
        v19 = &TnoHoHoDk::`vftable';
        v9 = (*(__int64 (__fastcall **)(__int64 *, void ***))(*v7[2] + 64))(v7[2], &v19);
        if ( v9 < 0 )
        {
          v10 = TnoWin32ErrFromHR(v9);
          v6 = v10;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 83, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids, v10);
          }
LABEL_57:
          v19 = &TnoHash::`vftable';
          TnoBaseHash::ReleaseHash((TnoBaseHash *)&v19);
          goto LABEL_58;
        }
        v26[0] = &CReferenceCatalogSegHoHoDkIterator::`vftable';
        v26[2] = sesid;
        v26[3] = tableid;
        v26[1] = &v19;
        First = CReferenceCatalogSegHoHoDkIterator::FindFirst((CReferenceCatalogSegHoHoDkIterator *)v26);
        v6 = First;
        if ( First == 1168 )
        {
          memset(&psetcolumn, 0, sizeof(psetcolumn));
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
          {
            v24 = v21;
            v25 = v20;
            WPP_SF__HEX_(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              84,
              WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids,
              &v24);
          }
          *(&psetcolumn.columnid + 1) = 0;
          *(_QWORD *)&psetcolumn.grbit = 0;
          *(_QWORD *)&psetcolumn.err = 0;
          psetcolumn.columnid = this[912];
          psetcolumn.cbData = v20;
          psetcolumn.pvData = v21;
          psetcolumn.itagSequence = 1;
          v12 = JetPrepareUpdate(sesid, tableid, 0);
          v13 = v12;
          if ( v12 )
          {
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 85, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids, v12);
            }
LABEL_51:
            v6 = TranslateJetError(v13);
            v19 = &TnoHash::`vftable';
            TnoBaseHash::ReleaseHash((TnoBaseHash *)&v19);
            goto LABEL_58;
          }
          v14 = JetSetColumns(sesid, tableid, &psetcolumn, 1u);
          v13 = v14;
          if ( v14 )
          {
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 86, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids, v14);
            }
            goto LABEL_51;
          }
          v15 = JetUpdate(sesid, tableid, 0, 0, 0);
          v13 = v15;
          if ( v15 )
          {
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 87, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids, v15);
            }
            goto LABEL_51;
          }
        }
        else if ( First )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 88, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids, First);
          }
          goto LABEL_57;
        }
        v7 = (__int64 **)*v7;
        v19 = &TnoHash::`vftable';
        TnoBaseHash::ReleaseHash((TnoBaseHash *)&v19);
      }
      v8 = CTnoJetSession::CommitTransaction((CTnoJetSession *)v27);
      v6 = v8;
      if ( v8
        && WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 89, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids, v8);
      }
    }
LABEL_58:
    CTnoJetSession::~CTnoJetSession((CTnoJetSession *)v27);
    return v6;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 105) )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 81, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids, 4317);
    }
    return 4317;
  }
}

```

## disassembly

```asm
0x18013182c  mov     [rsp+arg_8], rbx
0x180131831  mov     [rsp+arg_10], rdi
0x180131836  push    r12
0x180131838  push    r13
0x18013183a  push    r14
0x18013183c  sub     rsp, 210h
0x180131843  mov     rax, cs:__security_cookie
0x18013184a  xor     rax, rsp
0x18013184d  mov     [rsp+228h+var_28], rax
0x180131855  mov     r12, rdx
0x180131858  mov     r13, rcx
0x18013185b  xor     ebx, ebx
0x18013185d  cmp     [rdx+8], rbx
0x180131861  jnz     short loc_180131890
0x180131863  lea     eax, [rbx+57h]
0x180131866  mov     rcx, [rsp+228h+var_28]
0x18013186e  xor     rcx, rsp; StackCookie
0x180131871  call    __security_check_cookie
0x180131876  lea     r11, [rsp+228h+var_18]
0x18013187e  mov     rbx, [r11+28h]
0x180131882  mov     rdi, [r11+30h]
0x180131886  mov     rsp, r11
0x180131889  pop     r14
0x18013188b  pop     r13
0x18013188d  pop     r12
0x18013188f  retn
0x180131890  cmp     [rcx+0EC8h], bl
0x180131896  jnz     short loc_1801318D9
0x180131898  lea     r14, WPP_GLOBAL_Control
0x18013189f  mov     rcx, cs:WPP_GLOBAL_Control
0x1801318a6  cmp     rcx, r14
0x1801318a9  jz      short loc_1801318D2
0x1801318ab  test    byte ptr [rcx+6Ch], 4
0x1801318af  jz      short loc_1801318D2
0x1801318b1  cmp     byte ptr [rcx+69h], 1
0x1801318b5  jb      short loc_1801318D2
0x1801318b7  mov     edx, 51h ; 'Q'
0x1801318bc  mov     r9d, 10DDh
0x1801318c2  lea     r8, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids
0x1801318c9  mov     rcx, [rcx+60h]
0x1801318cd  call    WPP_SF_d
0x1801318d2  mov     eax, 10DDh
0x1801318d7  jmp     short loc_180131866
0x1801318d9  or      rdx, 0FFFFFFFFFFFFFFFFh; Val
0x1801318dd  mov     [rsp+228h+tableid], rdx
0x1801318e2  mov     [rsp+228h+sesid], rdx
0x1801318e7  lea     rax, ??_7CTnoJetSession@@6B@; const CTnoJetSession::`vftable'
0x1801318ee  mov     [rsp+228h+var_168], rax
0x1801318f6  mov     [rsp+228h+var_160], rdx
0x1801318fe  mov     [rsp+228h+var_158], bx
0x180131906  mov     [rsp+228h+var_134], ebx
0x18013190d  mov     [rsp+228h+var_30], ebx
0x180131914  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18013191c  movups  [rsp+228h+var_154], xmm0
0x180131924  movups  [rsp+228h+var_144], xmm0
0x18013192c  mov     r8d, 100h; Size
0x180131932  lea     rcx, [rsp+228h+var_130]; void *
0x18013193a  call    memset_0
0x18013193f  lea     rax, [rsp+228h+tableid]
0x180131944  mov     [rsp+228h+pcbActual], rax; unsigned __int64 *
0x180131949  lea     r9, [rsp+228h+var_1F8]; unsigned int *
0x18013194e  lea     r8, [rsp+228h+sesid]; unsigned __int64 *
0x180131953  lea     rdx, [rsp+228h+var_168]; struct CTnoJetSession *
0x18013195b  mov     rcx, r13; this
0x18013195e  call    ?OpenDatabaseObjects@CPreLoadingReferenceFile@@AEAAKAEAVCTnoJetSession@@PEA_KPEAK1@Z; CPreLoadingReferenceFile::OpenDatabaseObjects(CTnoJetSession &,unsigned __int64 *,ulong *,unsigned __int64 *)
0x180131963  mov     edi, eax
0x180131965  test    eax, eax
0x180131967  jz      short loc_1801319B1
0x180131969  lea     r14, WPP_GLOBAL_Control
0x180131970  mov     rcx, cs:WPP_GLOBAL_Control
0x180131977  cmp     rcx, r14
0x18013197a  jz      loc_180131D44
0x180131980  test    byte ptr [rcx+6Ch], 4
0x180131984  jz      loc_180131D44
0x18013198a  cmp     byte ptr [rcx+69h], 1
0x18013198e  jb      loc_180131D44
0x180131994  mov     edx, 52h ; 'R'
0x180131999  mov     r9d, eax
0x18013199c  lea     r8, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids
0x1801319a3  mov     rcx, [rcx+60h]
0x1801319a7  call    WPP_SF_d
0x1801319ac  jmp     loc_180131D44
0x1801319b1  mov     rbx, [r12]
0x1801319b5  mov     rbx, [rbx]
0x1801319b8  lea     r14, WPP_GLOBAL_Control
0x1801319bf  cmp     rbx, [r12]
0x1801319c3  jnz     short loc_180131A13
0x1801319c5  lea     rcx, [rsp+228h+var_168]; this
0x1801319cd  call    ?CommitTransaction@CTnoJetSession@@UEAAKXZ; CTnoJetSession::CommitTransaction(void)
0x1801319d2  mov     edi, eax
0x1801319d4  test    eax, eax
0x1801319d6  jz      short loc_180131A0E
0x1801319d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1801319df  cmp     rcx, r14
0x1801319e2  jz      short loc_180131A09
0x1801319e4  test    byte ptr [rcx+6Ch], 4
0x1801319e8  jz      short loc_180131A09
0x1801319ea  cmp     byte ptr [rcx+69h], 1
0x1801319ee  jb      short loc_180131A09
0x1801319f0  mov     edx, 59h ; 'Y'
0x1801319f5  mov     r9d, eax
0x1801319f8  lea     r8, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids
0x1801319ff  mov     rcx, [rcx+60h]
0x180131a03  call    WPP_SF_d
0x180131a08  nop
0x180131a09  jmp     loc_180131D44
0x180131a0e  jmp     loc_180131D44
0x180131a13  mov     [rsp+228h+var_1D8], 0
0x180131a1b  mov     [rsp+228h+var_1D0], 0
0x180131a24  mov     [rsp+228h+var_1C8], 1
0x180131a29  lea     rax, ??_7TnoHoHoDk@@6B@; const TnoHoHoDk::`vftable'
0x180131a30  mov     [rsp+228h+var_1E0], rax
0x180131a35  mov     rcx, [rbx+10h]
0x180131a39  mov     rax, [rcx]
0x180131a3c  lea     rdx, [rsp+228h+var_1E0]
0x180131a41  mov     rax, [rax+40h]
0x180131a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131a4a  test    eax, eax
0x180131a4c  jns     short loc_180131AA3
0x180131a4e  mov     ecx, eax; int
0x180131a50  call    ?TnoWin32ErrFromHR@@YAKJ@Z; TnoWin32ErrFromHR(long)
0x180131a55  mov     edi, eax
0x180131a57  mov     rcx, cs:WPP_GLOBAL_Control
0x180131a5e  cmp     rcx, r14
0x180131a61  jz      short loc_180131A87
0x180131a63  test    byte ptr [rcx+6Ch], 4
0x180131a67  jz      short loc_180131A87
0x180131a69  cmp     byte ptr [rcx+69h], 1
0x180131a6d  jb      short loc_180131A87
0x180131a6f  mov     edx, 53h ; 'S'
0x180131a74  mov     r9d, eax
0x180131a77  lea     r8, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids
0x180131a7e  mov     rcx, [rcx+60h]
0x180131a82  call    WPP_SF_d
0x180131a87  lea     rax, ??_7TnoHash@@6B@; const TnoHash::`vftable'
0x180131a8e  mov     [rsp+228h+var_1E0], rax
0x180131a93  lea     rcx, [rsp+228h+var_1E0]; this
0x180131a98  call    ?ReleaseHash@TnoBaseHash@@QEAAXXZ; TnoBaseHash::ReleaseHash(void)
0x180131a9d  nop
0x180131a9e  jmp     loc_180131D44
0x180131aa3  lea     rax, ??_7CReferenceCatalogSegHoHoDkIterator@@6B@; const CReferenceCatalogSegHoHoDkIterator::`vftable'
0x180131aaa  mov     [rsp+228h+var_188], rax
0x180131ab2  mov     rax, [rsp+228h+sesid]
0x180131ab7  mov     [rsp+228h+var_178], rax
0x180131abf  mov     rax, [rsp+228h+tableid]
0x180131ac4  mov     [rsp+228h+var_170], rax
0x180131acc  lea     rax, [rsp+228h+var_1E0]
0x180131ad1  mov     [rsp+228h+var_180], rax
0x180131ad9  lea     rcx, [rsp+228h+var_188]; this
0x180131ae1  call    ?FindFirst@CReferenceCatalogSegHoHoDkIterator@@UEAAKXZ; CReferenceCatalogSegHoHoDkIterator::FindFirst(void)
0x180131ae6  mov     edi, eax
0x180131ae8  cmp     eax, 490h
0x180131aed  jnz     loc_180131CF3
0x180131af3  xorps   xmm0, xmm0
0x180131af6  xor     eax, eax
0x180131af8  movups  xmmword ptr [rsp+228h+psetcolumn.columnid], xmm0
0x180131afd  movups  xmmword ptr [rsp+228h+psetcolumn.cbData], xmm0
0x180131b02  mov     qword ptr [rsp+228h+psetcolumn.err], rax
0x180131b0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180131b11  cmp     rcx, r14
0x180131b14  jz      short loc_180131B59
0x180131b16  test    byte ptr [rcx+6Ch], 4
0x180131b1a  jz      short loc_180131B59
0x180131b1c  cmp     byte ptr [rcx+69h], 3
0x180131b20  jb      short loc_180131B59
0x180131b22  mov     rax, [rsp+228h+var_1D0]
0x180131b27  mov     [rsp+228h+var_198], rax
0x180131b2f  movzx   eax, word ptr [rsp+228h+var_1D8]
0x180131b34  mov     [rsp+228h+var_190], ax
0x180131b3c  mov     edx, 54h ; 'T'
0x180131b41  lea     r9, [rsp+228h+var_198]
0x180131b49  lea     r8, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids
0x180131b50  mov     rcx, [rcx+60h]
0x180131b54  call    WPP_SF__HEX_
0x180131b59  xor     eax, eax
0x180131b5b  mov     dword ptr [rsp+228h+psetcolumn+4], eax
0x180131b5f  mov     qword ptr [rsp+228h+psetcolumn.grbit], rax
0x180131b64  mov     qword ptr [rsp+228h+psetcolumn.err], rax
0x180131b6c  mov     eax, [r13+0E40h]
0x180131b73  mov     [rsp+228h+psetcolumn.columnid], eax
0x180131b77  mov     eax, [rsp+228h+var_1D8]
0x180131b7b  mov     [rsp+228h+psetcolumn.cbData], eax
0x180131b7f  mov     rax, [rsp+228h+var_1D0]
0x180131b84  mov     [rsp+228h+psetcolumn.pvData], rax
0x180131b89  mov     [rsp+228h+psetcolumn.itagSequence], 1
0x180131b94  xor     r8d, r8d; prep
0x180131b97  mov     rdx, [rsp+228h+tableid]; tableid
0x180131b9c  mov     rcx, [rsp+228h+sesid]; sesid
0x180131ba1  call    cs:__imp_JetPrepareUpdate
0x180131ba7  mov     edi, eax
0x180131ba9  test    eax, eax
0x180131bab  jz      short loc_180131C02
0x180131bad  mov     rcx, cs:WPP_GLOBAL_Control
0x180131bb4  cmp     rcx, r14
0x180131bb7  jz      short loc_180131BDD
0x180131bb9  test    byte ptr [rcx+6Ch], 4
0x180131bbd  jz      short loc_180131BDD
0x180131bbf  cmp     byte ptr [rcx+69h], 1
0x180131bc3  jb      short loc_180131BDD
0x180131bc5  mov     edx, 55h ; 'U'
0x180131bca  mov     r9d, eax
0x180131bcd  lea     r8, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids
0x180131bd4  mov     rcx, [rcx+60h]
0x180131bd8  call    WPP_SF_d
0x180131bdd  mov     ecx, edi; int
0x180131bdf  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180131be4  mov     edi, eax
0x180131be6  lea     rax, ??_7TnoHash@@6B@; const TnoHash::`vftable'
0x180131bed  mov     [rsp+228h+var_1E0], rax
0x180131bf2  lea     rcx, [rsp+228h+var_1E0]; this
0x180131bf7  call    ?ReleaseHash@TnoBaseHash@@QEAAXXZ; TnoBaseHash::ReleaseHash(void)
0x180131bfc  nop
0x180131bfd  jmp     loc_180131D44
0x180131c02  mov     r9d, 1; csetcolumn
0x180131c08  lea     r8, [rsp+228h+psetcolumn]; psetcolumn
0x180131c0d  mov     rdx, [rsp+228h+tableid]; tableid
0x180131c12  mov     rcx, [rsp+228h+sesid]; sesid
0x180131c17  call    cs:__imp_JetSetColumns
0x180131c1d  mov     edi, eax
0x180131c1f  test    eax, eax
0x180131c21  jz      short loc_180131C78
0x180131c23  mov     rcx, cs:WPP_GLOBAL_Control
0x180131c2a  cmp     rcx, r14
0x180131c2d  jz      short loc_180131C53
0x180131c2f  test    byte ptr [rcx+6Ch], 4
0x180131c33  jz      short loc_180131C53
0x180131c35  cmp     byte ptr [rcx+69h], 1
0x180131c39  jb      short loc_180131C53
0x180131c3b  mov     edx, 56h ; 'V'
0x180131c40  mov     r9d, eax
0x180131c43  lea     r8, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids
0x180131c4a  mov     rcx, [rcx+60h]
0x180131c4e  call    WPP_SF_d
0x180131c53  mov     ecx, edi; int
0x180131c55  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180131c5a  mov     edi, eax
0x180131c5c  lea     rax, ??_7TnoHash@@6B@; const TnoHash::`vftable'
0x180131c63  mov     [rsp+228h+var_1E0], rax
0x180131c68  lea     rcx, [rsp+228h+var_1E0]; this
0x180131c6d  call    ?ReleaseHash@TnoBaseHash@@QEAAXXZ; TnoBaseHash::ReleaseHash(void)
0x180131c72  nop
0x180131c73  jmp     loc_180131D44
0x180131c78  mov     [rsp+228h+pcbActual], 0; pcbActual
0x180131c81  xor     r9d, r9d; cbBookmark
0x180131c84  xor     r8d, r8d; pvBookmark
0x180131c87  mov     rdx, [rsp+228h+tableid]; tableid
0x180131c8c  mov     rcx, [rsp+228h+sesid]; sesid
0x180131c91  call    cs:__imp_JetUpdate
0x180131c97  mov     edi, eax
0x180131c99  test    eax, eax
0x180131c9b  jz      loc_180131D58
0x180131ca1  mov     rcx, cs:WPP_GLOBAL_Control
0x180131ca8  cmp     rcx, r14
0x180131cab  jz      short loc_180131CD1
0x180131cad  test    byte ptr [rcx+6Ch], 4
0x180131cb1  jz      short loc_180131CD1
0x180131cb3  cmp     byte ptr [rcx+69h], 1
0x180131cb7  jb      short loc_180131CD1
0x180131cb9  mov     edx, 57h ; 'W'
0x180131cbe  mov     r9d, eax
0x180131cc1  lea     r8, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids
0x180131cc8  mov     rcx, [rcx+60h]
0x180131ccc  call    WPP_SF_d
0x180131cd1  mov     ecx, edi; int
0x180131cd3  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180131cd8  mov     edi, eax
0x180131cda  lea     rax, ??_7TnoHash@@6B@; const TnoHash::`vftable'
0x180131ce1  mov     [rsp+228h+var_1E0], rax
0x180131ce6  lea     rcx, [rsp+228h+var_1E0]; this
0x180131ceb  call    ?ReleaseHash@TnoBaseHash@@QEAAXXZ; TnoBaseHash::ReleaseHash(void)
0x180131cf0  nop
0x180131cf1  jmp     short loc_180131D44
0x180131cf3  test    eax, eax
0x180131cf5  jz      short loc_180131D58
0x180131cf7  mov     rcx, cs:WPP_GLOBAL_Control
0x180131cfe  cmp     rcx, r14
0x180131d01  jz      short loc_180131D27
0x180131d03  test    byte ptr [rcx+6Ch], 4
0x180131d07  jz      short loc_180131D27
0x180131d09  cmp     byte ptr [rcx+69h], 1
0x180131d0d  jb      short loc_180131D27
0x180131d0f  mov     edx, 58h ; 'X'
0x180131d14  mov     r9d, eax
0x180131d17  lea     r8, WPP_dddfbaf8e29833ad8f504afc37c7cea8_Traceguids
0x180131d1e  mov     rcx, [rcx+60h]
0x180131d22  call    WPP_SF_d
0x180131d27  lea     rax, ??_7TnoHash@@6B@; const TnoHash::`vftable'
0x180131d2e  mov     [rsp+228h+var_1E0], rax
0x180131d33  lea     rcx, [rsp+228h+var_1E0]; this
0x180131d38  call    ?ReleaseHash@TnoBaseHash@@QEAAXXZ; TnoBaseHash::ReleaseHash(void)
0x180131d3d  nop
0x180131d3e  jmp     short loc_180131D44
0x180131d40  mov     edi, [rsp+228h+var_1F8]
0x180131d44  lea     rcx, [rsp+228h+var_168]; this
0x180131d4c  call    ??1CTnoJetSession@@UEAA@XZ; CTnoJetSession::~CTnoJetSession(void)
0x180131d51  mov     eax, edi
0x180131d53  jmp     loc_180131866
0x180131d58  mov     rbx, [rbx]
0x180131d5b  lea     rax, ??_7TnoHash@@6B@; const TnoHash::`vftable'
0x180131d62  mov     [rsp+228h+var_1E0], rax
  ... truncated ...
```
