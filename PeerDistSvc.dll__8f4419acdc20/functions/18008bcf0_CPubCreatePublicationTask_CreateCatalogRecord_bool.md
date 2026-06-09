# CPubCreatePublicationTask::CreateCatalogRecord(bool)

- ea: `0x18008bcf0`
- end: `0x18008c1bf`
- name: `?CreateCatalogRecord@CPubCreatePublicationTask@@IEAAK_N@Z`
- size: `1231`
- prototype: `unsigned int __fastcall(CPubCreatePublicationTask *__hidden this, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update`

## callers

- `0x18008e3f0`

## callees

- `0x180004374`
- `0x1800082d0`
- `0x18000ceac`
- `0x18008bcf0`
- `0x18008dab4`
- `0x1801390d8`
- `0x18013937c`
- `0x180159010`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x18008bd85`
- `ESENT!JetPrepareUpdate` at `0x18008c0f7`
- `ESENT!JetPrepareUpdate` at `0x18008bd85`
- `ESENT!JetPrepareUpdate` at `0x18008c0f7`
- `ESENT!JetSetColumns` at `0x18008bf85`
- `ESENT!JetSetColumns` at `0x18008bf85`
- `ESENT!JetRetrieveColumns` at `0x18008be31`
- `ESENT!JetRetrieveColumns` at `0x18008be31`
- `ESENT!JetUpdate` at `0x18008c076`
- `ESENT!JetUpdate` at `0x18008c076`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPubCreatePublicationTask::CreateCatalogRecord(CPubCreatePublicationTask *this, unsigned __int8 a2)
{
  int v2; // edi
  unsigned int v4; // esi
  unsigned int v5; // edi
  CHostedCacheMsgEncoding *v6; // rcx
  __int64 v7; // rdx
  JET_COLUMNID v8; // ecx
  unsigned int v9; // esi
  __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  unsigned int v12; // r14d
  unsigned int v13; // esi
  CHostedCacheMsgEncoding *v14; // rcx
  __int64 v15; // rsi
  unsigned int v16; // eax
  unsigned int v17; // esi
  void **v19; // [rsp+60h] [rbp-9h] BYREF
  int v20; // [rsp+68h] [rbp-1h]
  __int64 v21; // [rsp+70h] [rbp+7h]
  char v22; // [rsp+78h] [rbp+Fh]
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+80h] [rbp+17h] BYREF
  unsigned __int64 v24; // [rsp+D0h] [rbp+67h] BYREF
  unsigned int csetcolumn; // [rsp+D8h] [rbp+6Fh] BYREF

  v2 = a2;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 47, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids);
  }
  v20 = 0;
  v21 = 0;
  v22 = 1;
  v19 = &TnoHash::`vftable';
  memset(&pretrievecolumn, 0, sizeof(pretrievecolumn));
  v4 = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 53), 2 * v2);
  if ( v4 )
  {
    v5 = (*(__int64 (__fastcall **)(CPubCreatePublicationTask *, _QWORD))(*(_QWORD *)this + 24LL))(this, v4);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v7 = 48;
LABEL_47:
      WPP_SF_Dd(*((_QWORD *)v6 + 12), v7, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids);
    }
  }
  else
  {
    v8 = *(_DWORD *)(*((_QWORD *)this + 51) + 660LL);
    *(&pretrievecolumn.columnid + 1) = 0;
    memset(&pretrievecolumn.cbData, 0, 32);
    pretrievecolumn.columnid = v8;
    pretrievecolumn.cbData = 8;
    pretrievecolumn.pvData = (char *)this + 472;
    pretrievecolumn.itagSequence = 1;
    pretrievecolumn.grbit = (_BYTE)v2 == 0;
    v9 = JetRetrieveColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 53), &pretrievecolumn, 1u);
    if ( v9 )
    {
      v5 = (*(__int64 (__fastcall **)(CPubCreatePublicationTask *, _QWORD))(*(_QWORD *)this + 24LL))(this, v9);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v7 = 49;
        goto LABEL_47;
      }
    }
    else
    {
      TnoBaseHash::operator=(&v19, *((_QWORD *)this + 61) + 1720LL);
      v10 = *((_QWORD *)this + 1);
      v11 = *(_QWORD *)(v10 + 248);
      *(_QWORD *)(v10 + 248) = v11 + 1;
      v24 = v11;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 50, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids);
      }
      csetcolumn = *((_DWORD *)this + 96);
      CPubCreatePublicationTask::InitializeCatalogTableSetColumns(
        this,
        *((_DWORD *)this + 134),
        *((unsigned __int8 **)this + 68),
        (CPubCreatePublicationTask *)((char *)this + 504),
        (struct TnoHash *)&v19,
        (unsigned __int16 *)this + 276,
        *((unsigned __int16 **)this + 134),
        (char *)this + 1080,
        &v24,
        (unsigned int *)this + 271,
        *((struct JET_SETCOLUMN **)this + 50),
        &csetcolumn);
      v12 = csetcolumn;
      v13 = JetSetColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 53), *((JET_SETCOLUMN **)this + 50), csetcolumn);
      if ( v13 )
      {
        v5 = (*(__int64 (__fastcall **)(CPubCreatePublicationTask *, _QWORD))(*(_QWORD *)this + 24LL))(this, v13);
        csetcolumn = v5;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 51, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids);
          v14 = WPP_GLOBAL_Control;
        }
        v15 = 0;
        if ( v12 )
        {
          do
          {
            if ( *(_DWORD *)(*((_QWORD *)this + 50) + 40 * v15 + 32)
              && v14 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)v14 + 108) & 4) != 0
              && *((_BYTE *)v14 + 105) )
            {
              WPP_SF_Dd(*((_QWORD *)v14 + 12), 52, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids);
              v14 = WPP_GLOBAL_Control;
            }
            v15 = (unsigned int)(v15 + 1);
          }
          while ( (unsigned int)v15 < v12 );
          v5 = csetcolumn;
        }
      }
      else
      {
        v16 = JetUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 53), 0, 0, 0);
        if ( v16 == -1605 )
        {
          v5 = (*(__int64 (__fastcall **)(CPubCreatePublicationTask *, __int64))(*(_QWORD *)this + 24LL))(
                 this,
                 4294965691LL);
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
          {
            WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 53, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids);
          }
          *((_BYTE *)this + 1088) = 1;
          v17 = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 53), 3u);
          if ( v17 )
          {
            v5 = (*(__int64 (__fastcall **)(CPubCreatePublicationTask *, _QWORD))(*(_QWORD *)this + 24LL))(this, v17);
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              v7 = 54;
              goto LABEL_47;
            }
          }
        }
        else
        {
          v5 = 0;
          if ( v16 )
          {
            v5 = (*(__int64 (__fastcall **)(CPubCreatePublicationTask *, _QWORD))(*(_QWORD *)this + 24LL))(this, v16);
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              v7 = 55;
              goto LABEL_47;
            }
          }
        }
      }
    }
  }
  v19 = &TnoHash::`vftable';
  TnoBaseHash::ReleaseHash((TnoBaseHash *)&v19);
  return v5;
}

```

## disassembly

```asm
0x18008bcf0  mov     [rsp-8+arg_10], rbx
0x18008bcf5  mov     [rsp-8+arg_18], rsi
0x18008bcfa  push    rbp
0x18008bcfb  push    rdi
0x18008bcfc  push    r14
0x18008bcfe  lea     rbp, [rsp-47h]
0x18008bd03  sub     rsp, 0B0h
0x18008bd0a  movzx   edi, dl
0x18008bd0d  mov     rbx, rcx
0x18008bd10  lea     r14, WPP_GLOBAL_Control
0x18008bd17  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bd1e  cmp     rcx, r14
0x18008bd21  jz      short loc_18008BD44
0x18008bd23  test    byte ptr [rcx+6Ch], 4
0x18008bd27  jz      short loc_18008BD44
0x18008bd29  cmp     byte ptr [rcx+69h], 4
0x18008bd2d  jb      short loc_18008BD44
0x18008bd2f  mov     edx, 2Fh ; '/'
0x18008bd34  lea     r8, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids
0x18008bd3b  mov     rcx, [rcx+60h]
0x18008bd3f  call    WPP_SF_
0x18008bd44  mov     [rbp+57h+var_58], 0
0x18008bd4b  mov     [rbp+57h+var_50], 0
0x18008bd53  mov     [rbp+57h+var_48], 1
0x18008bd57  lea     rax, ??_7TnoHash@@6B@; const TnoHash::`vftable'
0x18008bd5e  mov     [rbp+57h+var_60], rax
0x18008bd62  xorps   xmm0, xmm0
0x18008bd65  movups  xmmword ptr [rbp+57h+pretrievecolumn.columnid], xmm0
0x18008bd69  movups  xmmword ptr [rbp+57h+pretrievecolumn.cbData], xmm0
0x18008bd6d  movups  xmmword ptr [rbp+57h+pretrievecolumn.itagSequence], xmm0
0x18008bd71  mov     r8d, edi
0x18008bd74  add     r8d, r8d; prep
0x18008bd77  mov     rdx, [rbx+1A8h]; tableid
0x18008bd7e  mov     rcx, [rbx+178h]; sesid
0x18008bd85  call    cs:__imp_JetPrepareUpdate
0x18008bd8b  mov     esi, eax
0x18008bd8d  test    eax, eax
0x18008bd8f  jz      short loc_18008BDD6
0x18008bd91  mov     rcx, [rbx]
0x18008bd94  mov     rax, [rcx+18h]
0x18008bd98  mov     edx, esi
0x18008bd9a  mov     rcx, rbx
0x18008bd9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bda2  mov     edi, eax
0x18008bda4  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bdab  cmp     rcx, r14
0x18008bdae  jz      loc_18008C191
0x18008bdb4  test    byte ptr [rcx+6Ch], 4
0x18008bdb8  jz      loc_18008C191
0x18008bdbe  cmp     byte ptr [rcx+69h], 1
0x18008bdc2  jb      loc_18008C191
0x18008bdc8  mov     edx, 30h ; '0'
0x18008bdcd  mov     dword ptr [rsp+0C0h+pcbActual], eax
0x18008bdd1  jmp     loc_18008C17D
0x18008bdd6  mov     rax, [rbx+198h]
0x18008bddd  mov     ecx, [rax+294h]
0x18008bde3  xorps   xmm0, xmm0
0x18008bde6  movups  xmmword ptr [rbp+57h+pretrievecolumn.columnid], xmm0
0x18008bdea  movups  xmmword ptr [rbp+57h+pretrievecolumn.cbData], xmm0
0x18008bdee  movups  xmmword ptr [rbp+57h+pretrievecolumn.itagSequence], xmm0
0x18008bdf2  mov     [rbp+57h+pretrievecolumn.columnid], ecx
0x18008bdf5  mov     [rbp+57h+pretrievecolumn.cbData], 8
0x18008bdfc  lea     r14, [rbx+1D8h]
0x18008be03  mov     [rbp+57h+pretrievecolumn.pvData], r14
0x18008be07  mov     [rbp+57h+pretrievecolumn.itagSequence], 1
0x18008be0e  xor     eax, eax
0x18008be10  test    dil, dil
0x18008be13  setz    al
0x18008be16  mov     [rbp+57h+pretrievecolumn.grbit], eax
0x18008be19  mov     r9d, 1; cretrievecolumn
0x18008be1f  lea     r8, [rbp+57h+pretrievecolumn]; pretrievecolumn
0x18008be23  mov     rdx, [rbx+1A8h]; tableid
0x18008be2a  mov     rcx, [rbx+178h]; sesid
0x18008be31  call    cs:__imp_JetRetrieveColumns
0x18008be37  mov     esi, eax
0x18008be39  test    eax, eax
0x18008be3b  jz      short loc_18008BE85
0x18008be3d  mov     rcx, [rbx]
0x18008be40  mov     rax, [rcx+18h]
0x18008be44  mov     edx, esi
0x18008be46  mov     rcx, rbx
0x18008be49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008be4e  mov     edi, eax
0x18008be50  mov     rcx, cs:WPP_GLOBAL_Control
0x18008be57  lea     rax, WPP_GLOBAL_Control
0x18008be5e  cmp     rcx, rax
0x18008be61  jz      loc_18008C191
0x18008be67  test    byte ptr [rcx+6Ch], 4
0x18008be6b  jz      loc_18008C191
0x18008be71  cmp     byte ptr [rcx+69h], 1
0x18008be75  jb      loc_18008C191
0x18008be7b  mov     edx, 31h ; '1'
0x18008be80  jmp     loc_18008C179
0x18008be85  mov     rdx, [rbx+1E8h]
0x18008be8c  add     rdx, 6B8h
0x18008be93  lea     rcx, [rbp+57h+var_60]
0x18008be97  call    ??4TnoBaseHash@@QEAAAEAV0@AEBV0@@Z; TnoBaseHash::operator=(TnoBaseHash const &)
0x18008be9c  mov     rdx, [rbx+8]
0x18008bea0  mov     rcx, [rdx+0F8h]
0x18008bea7  lea     rax, [rcx+1]
0x18008beab  mov     [rdx+0F8h], rax
0x18008beb2  mov     [rbp+57h+arg_0], rcx
0x18008beb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bebd  lea     rax, WPP_GLOBAL_Control
0x18008bec4  cmp     rcx, rax
0x18008bec7  jz      short loc_18008BEED
0x18008bec9  test    byte ptr [rcx+6Ch], 4
0x18008becd  jz      short loc_18008BEED
0x18008becf  cmp     byte ptr [rcx+69h], 3
0x18008bed3  jb      short loc_18008BEED
0x18008bed5  mov     edx, 32h ; '2'
0x18008beda  mov     r9, [r14]
0x18008bedd  lea     r8, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids
0x18008bee4  mov     rcx, [rcx+60h]
0x18008bee8  call    WPP_SF_q
0x18008beed  mov     eax, [rbx+180h]
0x18008bef3  mov     [rbp+57h+csetcolumn], eax
0x18008bef6  lea     rcx, [rbx+43Ch]
0x18008befd  lea     rdx, [rbx+438h]
0x18008bf04  lea     r8, [rbx+228h]
0x18008bf0b  lea     r9, [rbx+1F8h]; struct TnoHash *
0x18008bf12  lea     rax, [rbp+57h+csetcolumn]
0x18008bf16  mov     [rsp+0C0h+var_68], rax; unsigned int *
0x18008bf1b  mov     rax, [rbx+190h]
0x18008bf22  mov     [rsp+0C0h+var_70], rax; struct JET_SETCOLUMN *
0x18008bf27  mov     [rsp+0C0h+var_78], rcx; unsigned int *
0x18008bf2c  lea     rax, [rbp+57h+arg_0]
0x18008bf30  mov     [rsp+0C0h+var_80], rax; unsigned __int64 *
0x18008bf35  mov     [rsp+0C0h+var_88], rdx; void *
0x18008bf3a  mov     rax, [rbx+430h]
0x18008bf41  mov     [rsp+0C0h+var_90], rax; unsigned __int16 *
0x18008bf46  mov     [rsp+0C0h+var_98], r8; unsigned __int16 *
0x18008bf4b  lea     rax, [rbp+57h+var_60]
0x18008bf4f  mov     [rsp+0C0h+pcbActual], rax; struct TnoHash *
0x18008bf54  mov     r8, [rbx+220h]; unsigned __int8 *
0x18008bf5b  mov     edx, [rbx+218h]; unsigned int
0x18008bf61  mov     rcx, rbx; this
0x18008bf64  call    ?InitializeCatalogTableSetColumns@CPubCreatePublicationTask@@IEAAXKPEAEAEAVTnoHash@@1PEAG2PEAXPEA_KPEAKPEAUJET_SETCOLUMN@@5@Z; CPubCreatePublicationTask::InitializeCatalogTableSetColumns(ulong,uchar *,TnoHash &,TnoHash &,ushort *,ushort *,void *,unsigned __int64 *,ulong *,JET_SETCOLUMN *,ulong *)
0x18008bf69  mov     r14d, [rbp+57h+csetcolumn]
0x18008bf6d  mov     r9d, r14d; csetcolumn
0x18008bf70  mov     r8, [rbx+190h]; psetcolumn
0x18008bf77  mov     rdx, [rbx+1A8h]; tableid
0x18008bf7e  mov     rcx, [rbx+178h]; sesid
0x18008bf85  call    cs:__imp_JetSetColumns
0x18008bf8b  mov     esi, eax
0x18008bf8d  test    eax, eax
0x18008bf8f  jz      loc_18008C059
0x18008bf95  mov     rcx, [rbx]
0x18008bf98  mov     rax, [rcx+18h]
0x18008bf9c  mov     edx, esi
0x18008bf9e  mov     rcx, rbx
0x18008bfa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bfa6  mov     edi, eax
0x18008bfa8  mov     [rbp+57h+csetcolumn], eax
0x18008bfab  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bfb2  lea     rax, WPP_GLOBAL_Control
0x18008bfb9  cmp     rcx, rax
0x18008bfbc  jz      short loc_18008BFED
0x18008bfbe  test    byte ptr [rcx+6Ch], 4
0x18008bfc2  jz      short loc_18008BFED
0x18008bfc4  cmp     byte ptr [rcx+69h], 1
0x18008bfc8  jb      short loc_18008BFED
0x18008bfca  mov     edx, 33h ; '3'
0x18008bfcf  mov     dword ptr [rsp+0C0h+pcbActual], edi
0x18008bfd3  mov     r9d, esi
0x18008bfd6  lea     r8, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids
0x18008bfdd  mov     rcx, [rcx+60h]
0x18008bfe1  call    WPP_SF_Dd
0x18008bfe6  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bfed  xor     esi, esi
0x18008bfef  test    r14d, r14d
0x18008bff2  jz      loc_18008C191
0x18008bff8  lea     rdi, WPP_GLOBAL_Control
0x18008bfff  lea     r9, [rsi+rsi*4]
0x18008c003  mov     rax, [rbx+190h]
0x18008c00a  mov     r8d, [rax+r9*8+20h]
0x18008c00f  test    r8d, r8d
0x18008c012  jz      short loc_18008C04A
0x18008c014  cmp     rcx, rdi
0x18008c017  jz      short loc_18008C04A
0x18008c019  test    byte ptr [rcx+6Ch], 4
0x18008c01d  jz      short loc_18008C04A
0x18008c01f  cmp     byte ptr [rcx+69h], 1
0x18008c023  jb      short loc_18008C04A
0x18008c025  mov     edx, 34h ; '4'
0x18008c02a  mov     dword ptr [rsp+0C0h+pcbActual], r8d
0x18008c02f  mov     r9d, [rax+r9*8]
0x18008c033  lea     r8, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids
0x18008c03a  mov     rcx, [rcx+60h]
0x18008c03e  call    WPP_SF_Dd
0x18008c043  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c04a  inc     esi
0x18008c04c  cmp     esi, r14d
0x18008c04f  jb      short loc_18008BFFF
0x18008c051  mov     edi, [rbp+57h+csetcolumn]
0x18008c054  jmp     loc_18008C191
0x18008c059  mov     [rsp+0C0h+pcbActual], 0; pcbActual
0x18008c062  xor     r9d, r9d; cbBookmark
0x18008c065  xor     r8d, r8d; pvBookmark
0x18008c068  mov     rdx, [rbx+1A8h]; tableid
0x18008c06f  mov     rcx, [rbx+178h]; sesid
0x18008c076  call    cs:__imp_JetUpdate
0x18008c07c  mov     esi, eax
0x18008c07e  mov     ecx, 0FFFFF9BBh
0x18008c083  cmp     eax, ecx
0x18008c085  jnz     loc_18008C13C
0x18008c08b  mov     rax, [rbx]
0x18008c08e  mov     edx, ecx
0x18008c090  mov     rcx, rbx
0x18008c093  mov     rax, [rax+18h]
0x18008c097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c09c  mov     edi, eax
0x18008c09e  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c0a5  lea     r14, WPP_GLOBAL_Control
0x18008c0ac  cmp     rcx, r14
0x18008c0af  jz      short loc_18008C0DC
0x18008c0b1  test    byte ptr [rcx+6Ch], 4
0x18008c0b5  jz      short loc_18008C0DC
0x18008c0b7  cmp     byte ptr [rcx+69h], 4
0x18008c0bb  jb      short loc_18008C0DC
0x18008c0bd  mov     edx, 35h ; '5'
0x18008c0c2  mov     dword ptr [rsp+0C0h+pcbActual], eax
0x18008c0c6  mov     r9d, 0FFFFF9BBh
0x18008c0cc  lea     r8, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids
0x18008c0d3  mov     rcx, [rcx+60h]
0x18008c0d7  call    WPP_SF_Dd
0x18008c0dc  mov     byte ptr [rbx+440h], 1
0x18008c0e3  mov     r8d, 3; prep
0x18008c0e9  mov     rdx, [rbx+1A8h]; tableid
0x18008c0f0  mov     rcx, [rbx+178h]; sesid
0x18008c0f7  call    cs:__imp_JetPrepareUpdate
0x18008c0fd  mov     esi, eax
0x18008c0ff  test    eax, eax
0x18008c101  jz      loc_18008C191
0x18008c107  mov     rcx, [rbx]
0x18008c10a  mov     rax, [rcx+18h]
0x18008c10e  mov     edx, esi
0x18008c110  mov     rcx, rbx
0x18008c113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c118  mov     edi, eax
0x18008c11a  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c121  cmp     rcx, r14
0x18008c124  jz      short loc_18008C191
0x18008c126  test    byte ptr [rcx+6Ch], 4
0x18008c12a  jz      short loc_18008C191
0x18008c12c  cmp     byte ptr [rcx+69h], 1
0x18008c130  jb      short loc_18008C191
0x18008c132  mov     edx, 36h ; '6'
0x18008c137  jmp     loc_18008BDCD
0x18008c13c  xor     edi, edi
0x18008c13e  test    esi, esi
0x18008c140  jz      short loc_18008C191
0x18008c142  mov     rax, [rbx]
0x18008c145  mov     edx, esi
0x18008c147  mov     rcx, rbx
0x18008c14a  mov     rax, [rax+18h]
0x18008c14e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c153  mov     edi, eax
0x18008c155  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c15c  lea     rax, WPP_GLOBAL_Control
0x18008c163  cmp     rcx, rax
0x18008c166  jz      short loc_18008C191
0x18008c168  test    byte ptr [rcx+6Ch], 4
0x18008c16c  jz      short loc_18008C191
0x18008c16e  cmp     byte ptr [rcx+69h], 1
0x18008c172  jb      short loc_18008C191
0x18008c174  mov     edx, 37h ; '7'
0x18008c179  mov     dword ptr [rsp+0C0h+pcbActual], edi
0x18008c17d  mov     r9d, esi
0x18008c180  lea     r8, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids
0x18008c187  mov     rcx, [rcx+60h]
0x18008c18b  call    WPP_SF_Dd
0x18008c190  nop
0x18008c191  lea     rax, ??_7TnoHash@@6B@; const TnoHash::`vftable'
0x18008c198  mov     [rbp+57h+var_60], rax
0x18008c19c  lea     rcx, [rbp+57h+var_60]; this
0x18008c1a0  call    ?ReleaseHash@TnoBaseHash@@QEAAXXZ; TnoBaseHash::ReleaseHash(void)
0x18008c1a5  mov     eax, edi
0x18008c1a7  lea     r11, [rsp+0C0h+var_10]
0x18008c1af  mov     rbx, [r11+30h]
0x18008c1b3  mov     rsi, [r11+38h]
0x18008c1b7  mov     rsp, r11
0x18008c1ba  pop     r14
0x18008c1bc  pop     rdi
0x18008c1bd  pop     rbp
0x18008c1be  retn
```
