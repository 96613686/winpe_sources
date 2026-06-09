# CPubAddPersistedPublicationTask::CreateCatalogRecord(bool,bool)

- ea: `0x18008b7dc`
- end: `0x18008bce8`
- name: `?CreateCatalogRecord@CPubAddPersistedPublicationTask@@IEAAK_N0@Z`
- size: `1292`
- prototype: `unsigned int __fastcall(CPubAddPersistedPublicationTask *__hidden this, bool, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update`

## callers

- `0x18008e0e0`

## callees

- `0x180004374`
- `0x180008290`
- `0x180008310`
- `0x18000ceac`
- `0x18008b7dc`
- `0x18008d920`
- `0x18013937c`
- `0x180159010`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x18008b875`
- `ESENT!JetPrepareUpdate` at `0x18008bc3d`
- `ESENT!JetPrepareUpdate` at `0x18008b875`
- `ESENT!JetPrepareUpdate` at `0x18008bc3d`
- `ESENT!JetSetColumns` at `0x18008badf`
- `ESENT!JetSetColumns` at `0x18008badf`
- `ESENT!JetRetrieveColumns` at `0x18008b939`
- `ESENT!JetRetrieveColumns` at `0x18008b939`
- `ESENT!JetUpdate` at `0x18008bbc3`
- `ESENT!JetUpdate` at `0x18008bbc3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPubAddPersistedPublicationTask::CreateCatalogRecord(
        CPubAddPersistedPublicationTask *this,
        unsigned __int8 a2,
        unsigned __int8 a3)
{
  int v3; // r14d
  int v4; // edi
  unsigned int v6; // esi
  unsigned int v7; // edi
  CHostedCacheMsgEncoding *v8; // rcx
  __int64 v9; // rdx
  JET_COLUMNID v10; // ecx
  unsigned int v11; // esi
  __int64 v12; // rdx
  unsigned __int64 v13; // rcx
  unsigned int *v14; // rsi
  unsigned int v15; // eax
  unsigned int v17; // r14d
  unsigned int v18; // esi
  __int64 i; // rsi
  unsigned int v20; // eax
  unsigned int v21; // esi
  unsigned __int64 v22; // [rsp+50h] [rbp-39h] BYREF
  void **v23; // [rsp+58h] [rbp-31h] BYREF
  int v24; // [rsp+60h] [rbp-29h]
  __int64 v25; // [rsp+68h] [rbp-21h]
  char v26; // [rsp+70h] [rbp-19h]
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+78h] [rbp-11h] BYREF
  unsigned int csetcolumn; // [rsp+F0h] [rbp+67h] BYREF
  unsigned int v29; // [rsp+F8h] [rbp+6Fh] BYREF
  unsigned int v30; // [rsp+108h] [rbp+7Fh] BYREF

  v3 = a3;
  v4 = a2;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 72, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids);
  }
  v24 = 0;
  v25 = 0;
  v26 = 1;
  v23 = &TnoHash::`vftable';
  memset(&pretrievecolumn, 0, sizeof(pretrievecolumn));
  v6 = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 53), 2 * v4);
  if ( !v6 )
  {
    v10 = *(_DWORD *)(*((_QWORD *)this + 51) + 660LL);
    *(&pretrievecolumn.columnid + 1) = 0;
    memset(&pretrievecolumn.cbData, 0, 32);
    pretrievecolumn.columnid = v10;
    pretrievecolumn.cbData = 8;
    pretrievecolumn.pvData = (char *)this + 472;
    pretrievecolumn.itagSequence = 1;
    pretrievecolumn.grbit = (_BYTE)v4 == 0;
    v11 = JetRetrieveColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 53), &pretrievecolumn, 1u);
    if ( v11 )
    {
      v7 = (*(__int64 (__fastcall **)(CPubAddPersistedPublicationTask *, _QWORD))(*(_QWORD *)this + 24LL))(this, v11);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
        goto LABEL_25;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0 || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        goto LABEL_21;
      v9 = 74;
    }
    else
    {
      v29 = 8 * v3;
      v12 = *((_QWORD *)this + 1);
      v13 = *(_QWORD *)(v12 + 248);
      *(_QWORD *)(v12 + 248) = v13 + 1;
      v22 = v13;
      v30 = 0;
      v14 = 0;
      if ( *((_BYTE *)this + 1076) )
      {
        if ( (_BYTE)v4 )
        {
          v7 = 87;
          goto LABEL_20;
        }
        v15 = v29 | 2;
        v29 |= 2u;
        v14 = &v30;
      }
      else
      {
        v15 = v29;
      }
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
      {
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          75,
          WPP_44a976264dd93922b20292445dd7a2ed_Traceguids,
          *((_QWORD *)this + 59),
          v15);
      }
      csetcolumn = *((_DWORD *)this + 96);
      CPubAddPersistedPublicationTask::InitializeCatalogTableSetColumns(
        this,
        (CPubAddPersistedPublicationTask *)((char *)this + 488),
        (CPubAddPersistedPublicationTask *)((char *)this + 520),
        (unsigned __int16 *)this + 276,
        &v22,
        &v29,
        v14,
        *((struct JET_SETCOLUMN **)this + 50),
        &csetcolumn);
      v17 = csetcolumn;
      v18 = JetSetColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 53), *((JET_SETCOLUMN **)this + 50), csetcolumn);
      if ( v18 )
      {
        v7 = (*(__int64 (__fastcall **)(CPubAddPersistedPublicationTask *, _QWORD))(*(_QWORD *)this + 24LL))(this, v18);
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 76, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids);
          v8 = WPP_GLOBAL_Control;
        }
        for ( i = 0; (unsigned int)i < v17; i = (unsigned int)(i + 1) )
        {
          if ( *(_DWORD *)(*((_QWORD *)this + 50) + 40 * i + 32)
            && v8 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)v8 + 108) & 4) != 0
            && *((_BYTE *)v8 + 105) )
          {
            WPP_SF_Dd(*((_QWORD *)v8 + 12), 77, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids);
            v8 = WPP_GLOBAL_Control;
          }
        }
        goto LABEL_21;
      }
      v20 = JetUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 53), 0, 0, 0);
      if ( v20 == -1605 )
      {
        v7 = (*(__int64 (__fastcall **)(CPubAddPersistedPublicationTask *, __int64))(*(_QWORD *)this + 24LL))(
               this,
               4294965691LL);
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 78, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids);
        }
        v21 = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 53), 3u);
        if ( !v21 )
          goto LABEL_20;
        v7 = (*(__int64 (__fastcall **)(CPubAddPersistedPublicationTask *, _QWORD))(*(_QWORD *)this + 24LL))(this, v21);
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
          goto LABEL_25;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0 || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
          goto LABEL_21;
        v9 = 79;
      }
      else
      {
        v7 = 0;
        if ( !v20 )
          goto LABEL_20;
        v7 = (*(__int64 (__fastcall **)(CPubAddPersistedPublicationTask *, _QWORD))(*(_QWORD *)this + 24LL))(this, v20);
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
          goto LABEL_25;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0 || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
          goto LABEL_21;
        v9 = 80;
      }
    }
LABEL_10:
    WPP_SF_Dd(*((_QWORD *)v8 + 12), v9, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids);
LABEL_20:
    v8 = WPP_GLOBAL_Control;
    goto LABEL_21;
  }
  v7 = (*(__int64 (__fastcall **)(CPubAddPersistedPublicationTask *, _QWORD))(*(_QWORD *)this + 24LL))(this, v6);
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    goto LABEL_25;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v9 = 73;
    goto LABEL_10;
  }
LABEL_21:
  if ( v8 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)v8 + 108) & 4) != 0
    && *((_BYTE *)v8 + 105) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)v8 + 12), 81, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids, v7);
  }
LABEL_25:
  v23 = &TnoHash::`vftable';
  TnoBaseHash::ReleaseHash((TnoBaseHash *)&v23);
  return v7;
}

```

## disassembly

```asm
0x18008b7dc  push    rbp
0x18008b7de  push    rbx
0x18008b7df  push    rsi
0x18008b7e0  push    rdi
0x18008b7e1  push    r13
0x18008b7e3  push    r14
0x18008b7e5  push    r15
0x18008b7e7  lea     rbp, [rsp-27h]
0x18008b7ec  sub     rsp, 0B0h
0x18008b7f3  movzx   r14d, r8b
0x18008b7f7  movzx   edi, dl
0x18008b7fa  mov     rbx, rcx
0x18008b7fd  lea     rax, WPP_GLOBAL_Control
0x18008b804  mov     r13b, 4
0x18008b807  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b80e  cmp     rcx, rax
0x18008b811  jz      short loc_18008B834
0x18008b813  test    [rcx+6Ch], r13b
0x18008b817  jz      short loc_18008B834
0x18008b819  cmp     [rcx+69h], r13b
0x18008b81d  jb      short loc_18008B834
0x18008b81f  mov     edx, 48h ; 'H'
0x18008b824  lea     r8, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids
0x18008b82b  mov     rcx, [rcx+60h]
0x18008b82f  call    WPP_SF_
0x18008b834  mov     [rbp+57h+var_80], 0
0x18008b83b  mov     [rbp+57h+var_78], 0
0x18008b843  mov     [rbp+57h+var_70], 1
0x18008b847  lea     rax, ??_7TnoHash@@6B@; const TnoHash::`vftable'
0x18008b84e  mov     [rbp+57h+var_88], rax
0x18008b852  xorps   xmm0, xmm0
0x18008b855  movups  xmmword ptr [rbp+57h+pretrievecolumn.columnid], xmm0
0x18008b859  movups  xmmword ptr [rbp+57h+pretrievecolumn.cbData], xmm0
0x18008b85d  movups  xmmword ptr [rbp+57h+pretrievecolumn.itagSequence], xmm0
0x18008b861  mov     r8d, edi
0x18008b864  add     r8d, r8d; prep
0x18008b867  mov     rdx, [rbx+1A8h]; tableid
0x18008b86e  mov     rcx, [rbx+178h]; sesid
0x18008b875  call    cs:__imp_JetPrepareUpdate
0x18008b87b  mov     esi, eax
0x18008b87d  test    eax, eax
0x18008b87f  jz      short loc_18008B8E0
0x18008b881  mov     rcx, [rbx]
0x18008b884  mov     rax, [rcx+18h]
0x18008b888  mov     edx, esi
0x18008b88a  mov     rcx, rbx
0x18008b88d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b892  mov     edi, eax
0x18008b894  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b89b  lea     r15, WPP_GLOBAL_Control
0x18008b8a2  cmp     rcx, r15
0x18008b8a5  jz      loc_18008BA0B
0x18008b8ab  test    [rcx+6Ch], r13b
0x18008b8af  jz      loc_18008B9E1
0x18008b8b5  cmp     byte ptr [rcx+69h], 1
0x18008b8b9  jb      loc_18008B9E1
0x18008b8bf  mov     edx, 49h ; 'I'
0x18008b8c4  mov     dword ptr [rsp+0E0h+pcbActual], eax
0x18008b8c8  mov     r9d, esi
0x18008b8cb  lea     r8, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids
0x18008b8d2  mov     rcx, [rcx+60h]
0x18008b8d6  call    WPP_SF_Dd
0x18008b8db  jmp     loc_18008B9DA
0x18008b8e0  mov     rax, [rbx+198h]
0x18008b8e7  mov     ecx, [rax+294h]
0x18008b8ed  xorps   xmm0, xmm0
0x18008b8f0  movups  xmmword ptr [rbp+57h+pretrievecolumn.columnid], xmm0
0x18008b8f4  movups  xmmword ptr [rbp+57h+pretrievecolumn.cbData], xmm0
0x18008b8f8  movups  xmmword ptr [rbp+57h+pretrievecolumn.itagSequence], xmm0
0x18008b8fc  mov     [rbp+57h+pretrievecolumn.columnid], ecx
0x18008b8ff  mov     [rbp+57h+pretrievecolumn.cbData], 8
0x18008b906  lea     r15, [rbx+1D8h]
0x18008b90d  mov     [rbp+57h+pretrievecolumn.pvData], r15
0x18008b911  mov     ecx, 1
0x18008b916  mov     [rbp+57h+pretrievecolumn.itagSequence], ecx
0x18008b919  xor     eax, eax
0x18008b91b  test    dil, dil
0x18008b91e  setz    al
0x18008b921  mov     [rbp+57h+pretrievecolumn.grbit], eax
0x18008b924  mov     r9d, ecx; cretrievecolumn
0x18008b927  lea     r8, [rbp+57h+pretrievecolumn]; pretrievecolumn
0x18008b92b  mov     rdx, [rbx+1A8h]; tableid
0x18008b932  mov     rcx, [rbx+178h]; sesid
0x18008b939  call    cs:__imp_JetRetrieveColumns
0x18008b93f  mov     esi, eax
0x18008b941  test    eax, eax
0x18008b943  jz      short loc_18008B985
0x18008b945  mov     rcx, [rbx]
0x18008b948  mov     rax, [rcx+18h]
0x18008b94c  mov     edx, esi
0x18008b94e  mov     rcx, rbx
0x18008b951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b956  mov     edi, eax
0x18008b958  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b95f  lea     r15, WPP_GLOBAL_Control
0x18008b966  cmp     rcx, r15
0x18008b969  jz      loc_18008BA0B
0x18008b96f  test    [rcx+6Ch], r13b
0x18008b973  jz      short loc_18008B9E1
0x18008b975  cmp     byte ptr [rcx+69h], 1
0x18008b979  jb      short loc_18008B9E1
0x18008b97b  mov     edx, 4Ah ; 'J'
0x18008b980  jmp     loc_18008B8C4
0x18008b985  mov     eax, r14d
0x18008b988  shl     eax, 3
0x18008b98b  mov     [rbp+57h+arg_8], eax
0x18008b98e  mov     rdx, [rbx+8]
0x18008b992  mov     rcx, [rdx+0F8h]
0x18008b999  lea     rax, [rcx+1]
0x18008b99d  mov     [rdx+0F8h], rax
0x18008b9a4  mov     [rbp+57h+var_90], rcx
0x18008b9a8  mov     [rbp+57h+arg_18], 0
0x18008b9af  xor     esi, esi
0x18008b9b1  cmp     [rbx+434h], sil
0x18008b9b8  jz      short loc_18008BA33
0x18008b9ba  test    dil, dil
0x18008b9bd  jnz     short loc_18008B9CE
0x18008b9bf  mov     eax, [rbp+57h+arg_8]
0x18008b9c2  or      eax, 2
0x18008b9c5  mov     [rbp+57h+arg_8], eax
0x18008b9c8  lea     rsi, [rbp+57h+arg_18]
0x18008b9cc  jmp     short loc_18008BA36
0x18008b9ce  mov     edi, 57h ; 'W'
0x18008b9d3  lea     r15, WPP_GLOBAL_Control
0x18008b9da  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b9e1  cmp     rcx, r15
0x18008b9e4  jz      short loc_18008BA0B
0x18008b9e6  test    [rcx+6Ch], r13b
0x18008b9ea  jz      short loc_18008BA0B
0x18008b9ec  cmp     [rcx+69h], r13b
0x18008b9f0  jb      short loc_18008BA0B
0x18008b9f2  mov     edx, 51h ; 'Q'
0x18008b9f7  mov     r9d, edi
0x18008b9fa  lea     r8, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids
0x18008ba01  mov     rcx, [rcx+60h]
0x18008ba05  call    WPP_SF_d
0x18008ba0a  nop
0x18008ba0b  lea     rax, ??_7TnoHash@@6B@; const TnoHash::`vftable'
0x18008ba12  mov     [rbp+57h+var_88], rax
0x18008ba16  lea     rcx, [rbp+57h+var_88]; this
0x18008ba1a  call    ?ReleaseHash@TnoBaseHash@@QEAAXXZ; TnoBaseHash::ReleaseHash(void)
0x18008ba1f  mov     eax, edi
0x18008ba21  add     rsp, 0B0h
0x18008ba28  pop     r15
0x18008ba2a  pop     r14
0x18008ba2c  pop     r13
0x18008ba2e  pop     rdi
0x18008ba2f  pop     rsi
0x18008ba30  pop     rbx
0x18008ba31  pop     rbp
0x18008ba32  retn
0x18008ba33  mov     eax, [rbp+57h+arg_8]
0x18008ba36  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ba3d  lea     rdx, WPP_GLOBAL_Control
0x18008ba44  cmp     rcx, rdx
0x18008ba47  jz      short loc_18008BA71
0x18008ba49  test    [rcx+6Ch], r13b
0x18008ba4d  jz      short loc_18008BA71
0x18008ba4f  cmp     byte ptr [rcx+69h], 3
0x18008ba53  jb      short loc_18008BA71
0x18008ba55  mov     edx, 4Bh ; 'K'
0x18008ba5a  mov     dword ptr [rsp+0E0h+pcbActual], eax
0x18008ba5e  mov     r9, [r15]
0x18008ba61  lea     r8, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids
0x18008ba68  mov     rcx, [rcx+60h]
0x18008ba6c  call    WPP_SF_qD
0x18008ba71  mov     eax, [rbx+180h]
0x18008ba77  mov     [rbp+57h+csetcolumn], eax
0x18008ba7a  lea     r9, [rbx+228h]; unsigned __int16 *
0x18008ba81  lea     r8, [rbx+208h]; struct TnoHash *
0x18008ba88  lea     rdx, [rbx+1E8h]; struct TnoHash *
0x18008ba8f  lea     rax, [rbp+57h+csetcolumn]
0x18008ba93  mov     [rsp+0E0h+var_A0], rax; unsigned int *
0x18008ba98  mov     rax, [rbx+190h]
0x18008ba9f  mov     [rsp+0E0h+var_A8], rax; struct JET_SETCOLUMN *
0x18008baa4  mov     [rsp+0E0h+var_B0], rsi; unsigned int *
0x18008baa9  lea     rax, [rbp+57h+arg_8]
0x18008baad  mov     [rsp+0E0h+var_B8], rax; unsigned int *
0x18008bab2  lea     rax, [rbp+57h+var_90]
0x18008bab6  mov     [rsp+0E0h+pcbActual], rax; unsigned __int64 *
0x18008babb  mov     rcx, rbx; this
0x18008babe  call    ?InitializeCatalogTableSetColumns@CPubAddPersistedPublicationTask@@IEAAXAEAVTnoHash@@0PEAGPEA_KPEAKPEBKPEAUJET_SETCOLUMN@@3@Z; CPubAddPersistedPublicationTask::InitializeCatalogTableSetColumns(TnoHash &,TnoHash &,ushort *,unsigned __int64 *,ulong *,ulong const *,JET_SETCOLUMN *,ulong *)
0x18008bac3  mov     r14d, [rbp+57h+csetcolumn]
0x18008bac7  mov     r9d, r14d; csetcolumn
0x18008baca  mov     r8, [rbx+190h]; psetcolumn
0x18008bad1  mov     rdx, [rbx+1A8h]; tableid
0x18008bad8  mov     rcx, [rbx+178h]; sesid
0x18008badf  call    cs:__imp_JetSetColumns
0x18008bae5  mov     esi, eax
0x18008bae7  test    eax, eax
0x18008bae9  jz      loc_18008BBA6
0x18008baef  mov     rcx, [rbx]
0x18008baf2  mov     rax, [rcx+18h]
0x18008baf6  mov     edx, esi
0x18008baf8  mov     rcx, rbx
0x18008bafb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bb00  mov     edi, eax
0x18008bb02  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bb09  lea     r15, WPP_GLOBAL_Control
0x18008bb10  cmp     rcx, r15
0x18008bb13  jz      short loc_18008BB44
0x18008bb15  test    [rcx+6Ch], r13b
0x18008bb19  jz      short loc_18008BB44
0x18008bb1b  cmp     byte ptr [rcx+69h], 1
0x18008bb1f  jb      short loc_18008BB44
0x18008bb21  mov     edx, 4Ch ; 'L'
0x18008bb26  mov     dword ptr [rsp+0E0h+pcbActual], eax
0x18008bb2a  mov     r9d, esi
0x18008bb2d  lea     r8, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids
0x18008bb34  mov     rcx, [rcx+60h]
0x18008bb38  call    WPP_SF_Dd
0x18008bb3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bb44  xor     esi, esi
0x18008bb46  test    r14d, r14d
0x18008bb49  jz      loc_18008B9E1
0x18008bb4f  lea     r9, [rsi+rsi*4]
0x18008bb53  mov     rax, [rbx+190h]
0x18008bb5a  mov     r8d, [rax+r9*8+20h]
0x18008bb5f  test    r8d, r8d
0x18008bb62  jz      short loc_18008BB9A
0x18008bb64  cmp     rcx, r15
0x18008bb67  jz      short loc_18008BB9A
0x18008bb69  test    [rcx+6Ch], r13b
0x18008bb6d  jz      short loc_18008BB9A
0x18008bb6f  cmp     byte ptr [rcx+69h], 1
0x18008bb73  jb      short loc_18008BB9A
0x18008bb75  mov     edx, 4Dh ; 'M'
0x18008bb7a  mov     dword ptr [rsp+0E0h+pcbActual], r8d
0x18008bb7f  mov     r9d, [rax+r9*8]
0x18008bb83  lea     r8, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids
0x18008bb8a  mov     rcx, [rcx+60h]
0x18008bb8e  call    WPP_SF_Dd
0x18008bb93  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bb9a  inc     esi
0x18008bb9c  cmp     esi, r14d
0x18008bb9f  jb      short loc_18008BB4F
0x18008bba1  jmp     loc_18008B9E1
0x18008bba6  mov     [rsp+0E0h+pcbActual], 0; pcbActual
0x18008bbaf  xor     r9d, r9d; cbBookmark
0x18008bbb2  xor     r8d, r8d; pvBookmark
0x18008bbb5  mov     rdx, [rbx+1A8h]; tableid
0x18008bbbc  mov     rcx, [rbx+178h]; sesid
0x18008bbc3  call    cs:__imp_JetUpdate
0x18008bbc9  mov     esi, eax
0x18008bbcb  mov     r14d, 0FFFFF9BBh
0x18008bbd1  cmp     eax, r14d
0x18008bbd4  jnz     loc_18008BC95
0x18008bbda  mov     rax, [rbx]
0x18008bbdd  mov     edx, r14d
0x18008bbe0  mov     rcx, rbx
0x18008bbe3  mov     rax, [rax+18h]
0x18008bbe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bbec  mov     edi, eax
0x18008bbee  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bbf5  lea     rax, WPP_GLOBAL_Control
0x18008bbfc  cmp     rcx, rax
0x18008bbff  jz      short loc_18008BC29
0x18008bc01  test    [rcx+6Ch], r13b
0x18008bc05  jz      short loc_18008BC29
0x18008bc07  cmp     [rcx+69h], r13b
0x18008bc0b  jb      short loc_18008BC29
0x18008bc0d  mov     edx, 4Eh ; 'N'
0x18008bc12  mov     dword ptr [rsp+0E0h+pcbActual], edi
0x18008bc16  mov     r9d, r14d
0x18008bc19  lea     r8, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids
0x18008bc20  mov     rcx, [rcx+60h]
0x18008bc24  call    WPP_SF_Dd
0x18008bc29  mov     r8d, 3; prep
0x18008bc2f  mov     rdx, [rbx+1A8h]; tableid
0x18008bc36  mov     rcx, [rbx+178h]; sesid
0x18008bc3d  call    cs:__imp_JetPrepareUpdate
0x18008bc43  mov     esi, eax
0x18008bc45  test    eax, eax
0x18008bc47  jz      loc_18008B9D3
0x18008bc4d  mov     rcx, [rbx]
0x18008bc50  mov     rax, [rcx+18h]
0x18008bc54  mov     edx, esi
0x18008bc56  mov     rcx, rbx
0x18008bc59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bc5e  mov     edi, eax
0x18008bc60  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bc67  lea     r15, WPP_GLOBAL_Control
0x18008bc6e  cmp     rcx, r15
0x18008bc71  jz      loc_18008BA0B
0x18008bc77  test    [rcx+6Ch], r13b
0x18008bc7b  jz      loc_18008B9E1
0x18008bc81  cmp     byte ptr [rcx+69h], 1
0x18008bc85  jb      loc_18008B9E1
0x18008bc8b  mov     edx, 4Fh ; 'O'
0x18008bc90  jmp     loc_18008B8C4
0x18008bc95  xor     edi, edi
0x18008bc97  test    esi, esi
0x18008bc99  jz      loc_18008B9D3
0x18008bc9f  mov     rax, [rbx]
0x18008bca2  mov     edx, esi
0x18008bca4  mov     rcx, rbx
0x18008bca7  mov     rax, [rax+18h]
0x18008bcab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bcb0  mov     edi, eax
0x18008bcb2  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
