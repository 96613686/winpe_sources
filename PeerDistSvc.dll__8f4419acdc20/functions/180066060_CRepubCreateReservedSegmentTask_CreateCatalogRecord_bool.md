# CRepubCreateReservedSegmentTask::CreateCatalogRecord(bool)

- ea: `0x180066060`
- end: `0x180066502`
- name: `?CreateCatalogRecord@CRepubCreateReservedSegmentTask@@IEAAK_N@Z`
- size: `1186`
- prototype: `unsigned int __fastcall(CRepubCreateReservedSegmentTask *__hidden this, bool)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, installer_update`

## callers

- `0x18006c840`
- `0x18006d400`

## callees

- `0x180004374`
- `0x180008290`
- `0x18000ceac`
- `0x18001fc30`
- `0x180066060`
- `0x18006acdc`
- `0x18013902c`
- `0x180139088`
- `0x18013937c`
- `0x1801448c0`
- `0x180159010`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x1800660ee`
- `ESENT!JetPrepareUpdate` at `0x1800660ee`
- `ESENT!JetSetColumns` at `0x18006633d`
- `ESENT!JetSetColumns` at `0x18006633d`
- `ESENT!JetRetrieveColumns` at `0x18006619d`
- `ESENT!JetRetrieveColumns` at `0x18006619d`
- `ESENT!JetUpdate` at `0x180066429`
- `ESENT!JetUpdate` at `0x180066429`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRepubCreateReservedSegmentTask::CreateCatalogRecord(
        CRepubCreateReservedSegmentTask *this,
        unsigned __int8 a2)
{
  int v2; // r14d
  unsigned int v4; // esi
  CHostedCacheMsgEncoding *v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // esi
  JET_COLUMNID v8; // ecx
  __int64 v9; // r9
  CHostedCacheMsgEncoding *v10; // rcx
  unsigned int v11; // esi
  __int64 v12; // r14
  CHostedCacheMsgEncoding *v13; // rcx
  unsigned int v14; // esi
  unsigned int csetcolumn; // [rsp+70h] [rbp-90h] BYREF
  __int16 v17; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v18; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v19; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v20; // [rsp+80h] [rbp-80h] BYREF
  int v21; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v22; // [rsp+88h] [rbp-78h]
  __int64 v23; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v24[4]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v25[4]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 v26; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v27; // [rsp+E0h] [rbp-20h] BYREF
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+E8h] [rbp-18h] BYREF
  struct peerdist_content_tag_tag v29; // [rsp+118h] [rbp+18h] BYREF

  v2 = a2;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 489, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
  }
  memset(&pretrievecolumn, 0, sizeof(pretrievecolumn));
  v23 = 0;
  v4 = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 54), 2 * v2);
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_11;
    }
    v6 = 490;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v5 + 12), v6, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v4);
LABEL_11:
    v7 = (*(__int64 (__fastcall **)(CRepubCreateReservedSegmentTask *, _QWORD))(*(_QWORD *)this + 48LL))(this, v4);
LABEL_46:
    v10 = WPP_GLOBAL_Control;
    goto LABEL_47;
  }
  v8 = *(_DWORD *)(*((_QWORD *)this + 52) + 812LL);
  *(&pretrievecolumn.columnid + 1) = 0;
  memset(&pretrievecolumn.cbData, 0, 32);
  pretrievecolumn.columnid = v8;
  pretrievecolumn.cbData = 8;
  pretrievecolumn.pvData = &v23;
  pretrievecolumn.itagSequence = 1;
  pretrievecolumn.grbit = (_BYTE)v2 == 0;
  v4 = JetRetrieveColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 54), &pretrievecolumn, 1u);
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_11;
    }
    v6 = 491;
    goto LABEL_10;
  }
  v9 = *((_QWORD *)this + 51);
  if ( v9 == v23 )
  {
    TnoHoHoDk::TnoHoHoDk((TnoHoHoDk *)v25, 8u);
    *(_QWORD *)v25[2] = *((_QWORD *)this + 51);
    TnoHash::TnoHash((TnoHash *)v24, 8u);
    *(_QWORD *)v24[2] = *((_QWORD *)this + 51);
    v21 = 1;
    v20 = 0;
    v19 = 0;
    v27 = 0;
    v26 = 0;
    v18 = 0;
    v17 = 255;
    v29 = 0;
    csetcolumn = *((_DWORD *)this + 96);
    CRepubCreateReservedSegmentTask::InitializeCatalogTableSetColumns(
      this,
      (const struct TnoHoHoDk *)v25,
      (const struct TnoHash *)v24,
      &v21,
      &v29,
      &v20,
      &v19,
      &v27,
      &v26,
      &v17,
      &v18,
      *((struct JET_SETCOLUMN **)this + 50),
      &csetcolumn);
    v11 = JetSetColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 54), *((JET_SETCOLUMN **)this + 50), csetcolumn);
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 493, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v11);
      }
      v7 = (*(__int64 (__fastcall **)(CRepubCreateReservedSegmentTask *, _QWORD))(*(_QWORD *)this + 48LL))(this, v11);
      v22 = v7;
      v12 = 0;
      if ( csetcolumn )
      {
        v13 = WPP_GLOBAL_Control;
        do
        {
          if ( *(_DWORD *)(*((_QWORD *)this + 50) + 40 * v12 + 32)
            && v13 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)v13 + 108) & 4) != 0
            && *((_BYTE *)v13 + 105) )
          {
            WPP_SF_Dd(*((_QWORD *)v13 + 12), 494, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
            v13 = WPP_GLOBAL_Control;
          }
          v12 = (unsigned int)(v12 + 1);
        }
        while ( (unsigned int)v12 < csetcolumn );
        v7 = v22;
      }
    }
    else
    {
      v14 = JetUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 54), 0, 0, 0);
      if ( v14 )
      {
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 495, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v14);
        }
        v7 = (*(__int64 (__fastcall **)(CRepubCreateReservedSegmentTask *, _QWORD))(*(_QWORD *)this + 48LL))(this, v14);
      }
      else
      {
        v7 = 0;
      }
    }
    v24[0] = &TnoHash::`vftable';
    TnoBaseHash::ReleaseHash((TnoBaseHash *)v24);
    v25[0] = &TnoHash::`vftable';
    TnoBaseHash::ReleaseHash((TnoBaseHash *)v25);
    goto LABEL_46;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 12), 492, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v9, v23);
    v10 = WPP_GLOBAL_Control;
  }
  v7 = 774;
LABEL_47:
  if ( v10 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)v10 + 108) & 4) != 0
    && *((_BYTE *)v10 + 105) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)v10 + 12), 496, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v7);
  }
  return v7;
}

```

## disassembly

```asm
0x180066060  mov     [rsp-8+arg_8], rbx
0x180066065  mov     [rsp-8+arg_10], rsi
0x18006606a  push    rbp
0x18006606b  push    rdi
0x18006606c  push    r14
0x18006606e  lea     rbp, [rsp-30h]
0x180066073  sub     rsp, 130h
0x18006607a  mov     rax, cs:__security_cookie
0x180066081  xor     rax, rsp
0x180066084  mov     [rbp+40h+var_18], rax
0x180066088  movzx   r14d, dl
0x18006608c  mov     rbx, rcx
0x18006608f  lea     rdi, WPP_GLOBAL_Control
0x180066096  mov     rcx, cs:WPP_GLOBAL_Control
0x18006609d  cmp     rcx, rdi
0x1800660a0  jz      short loc_1800660C3
0x1800660a2  test    byte ptr [rcx+6Ch], 4
0x1800660a6  jz      short loc_1800660C3
0x1800660a8  cmp     byte ptr [rcx+69h], 4
0x1800660ac  jb      short loc_1800660C3
0x1800660ae  mov     edx, 1E9h
0x1800660b3  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x1800660ba  mov     rcx, [rcx+60h]
0x1800660be  call    WPP_SF_
0x1800660c3  xorps   xmm0, xmm0
0x1800660c6  movups  xmmword ptr [rbp+40h+pretrievecolumn.columnid], xmm0
0x1800660ca  movups  xmmword ptr [rbp+40h+pretrievecolumn.cbData], xmm0
0x1800660ce  movups  xmmword ptr [rbp+40h+pretrievecolumn.itagSequence], xmm0
0x1800660d2  mov     [rbp+40h+var_B0], 0
0x1800660da  mov     r8d, r14d
0x1800660dd  add     r8d, r8d; prep
0x1800660e0  mov     rdx, [rbx+1B0h]; tableid
0x1800660e7  mov     rcx, [rbx+178h]; sesid
0x1800660ee  call    cs:__imp_JetPrepareUpdate
0x1800660f4  mov     esi, eax
0x1800660f6  test    eax, eax
0x1800660f8  jz      short loc_180066147
0x1800660fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180066101  cmp     rcx, rdi
0x180066104  jz      short loc_18006612F
0x180066106  test    byte ptr [rcx+6Ch], 4
0x18006610a  jz      short loc_18006612F
0x18006610c  mov     edi, 1
0x180066111  cmp     [rcx+69h], dil
0x180066115  jb      short loc_18006612F
0x180066117  mov     edx, 1EAh
0x18006611c  mov     r9d, esi
0x18006611f  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x180066126  mov     rcx, [rcx+60h]
0x18006612a  call    WPP_SF_d
0x18006612f  mov     rax, [rbx]
0x180066132  mov     edx, esi
0x180066134  mov     rcx, rbx
0x180066137  mov     rax, [rax+30h]
0x18006613b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066140  mov     esi, eax
0x180066142  jmp     loc_1800664A5
0x180066147  mov     rax, [rbx+1A0h]
0x18006614e  mov     ecx, [rax+32Ch]
0x180066154  xorps   xmm0, xmm0
0x180066157  movups  xmmword ptr [rbp+40h+pretrievecolumn.columnid], xmm0
0x18006615b  movups  xmmword ptr [rbp+40h+pretrievecolumn.cbData], xmm0
0x18006615f  movups  xmmword ptr [rbp+40h+pretrievecolumn.itagSequence], xmm0
0x180066163  mov     [rbp+40h+pretrievecolumn.columnid], ecx
0x180066166  mov     [rbp+40h+pretrievecolumn.cbData], 8
0x18006616d  lea     rax, [rbp+40h+var_B0]
0x180066171  mov     [rbp+40h+pretrievecolumn.pvData], rax
0x180066175  mov     edi, 1
0x18006617a  mov     [rbp+40h+pretrievecolumn.itagSequence], edi
0x18006617d  xor     eax, eax
0x18006617f  test    r14b, r14b
0x180066182  setz    al
0x180066185  mov     [rbp+40h+pretrievecolumn.grbit], eax
0x180066188  mov     r9d, edi; cretrievecolumn
0x18006618b  lea     r8, [rbp+40h+pretrievecolumn]; pretrievecolumn
0x18006618f  mov     rdx, [rbx+1B0h]; tableid
0x180066196  mov     rcx, [rbx+178h]; sesid
0x18006619d  call    cs:__imp_JetRetrieveColumns
0x1800661a3  mov     esi, eax
0x1800661a5  test    eax, eax
0x1800661a7  jz      short loc_1800661DE
0x1800661a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800661b0  lea     rax, WPP_GLOBAL_Control
0x1800661b7  cmp     rcx, rax
0x1800661ba  jz      loc_18006612F
0x1800661c0  test    byte ptr [rcx+6Ch], 4
0x1800661c4  jz      loc_18006612F
0x1800661ca  cmp     [rcx+69h], dil
0x1800661ce  jb      loc_18006612F
0x1800661d4  mov     edx, 1EBh
0x1800661d9  jmp     loc_18006611C
0x1800661de  mov     r9, [rbx+198h]
0x1800661e5  mov     rax, [rbp+40h+var_B0]
0x1800661e9  cmp     r9, rax
0x1800661ec  jz      short loc_180066238
0x1800661ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800661f5  lea     rdx, WPP_GLOBAL_Control
0x1800661fc  cmp     rcx, rdx
0x1800661ff  jz      short loc_18006622E
0x180066201  test    byte ptr [rcx+6Ch], 4
0x180066205  jz      short loc_18006622E
0x180066207  cmp     [rcx+69h], dil
0x18006620b  jb      short loc_18006622E
0x18006620d  mov     edx, 1ECh
0x180066212  mov     [rsp+140h+pcbActual], rax
0x180066217  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x18006621e  mov     rcx, [rcx+60h]
0x180066222  call    WPP_SF_qq
0x180066227  mov     rcx, cs:WPP_GLOBAL_Control
0x18006622e  mov     esi, 306h
0x180066233  jmp     loc_1800664AC
0x180066238  mov     edx, 8; unsigned int
0x18006623d  lea     rcx, [rbp+40h+var_88]; this
0x180066241  call    ??0TnoHoHoDk@@QEAA@K@Z; TnoHoHoDk::TnoHoHoDk(ulong)
0x180066246  nop
0x180066247  mov     rcx, [rbx+198h]
0x18006624e  mov     rax, [rbp+40h+var_78]
0x180066252  mov     [rax], rcx
0x180066255  mov     edx, 8; unsigned int
0x18006625a  lea     rcx, [rbp+40h+var_A8]; this
0x18006625e  call    ??0TnoHash@@QEAA@K@Z; TnoHash::TnoHash(ulong)
0x180066263  nop
0x180066264  mov     rcx, [rbx+198h]
0x18006626b  mov     rax, [rbp+40h+var_98]
0x18006626f  mov     [rax], rcx
0x180066272  mov     [rbp+40h+var_BC], edi
0x180066275  mov     [rbp+40h+var_C0], 0
0x18006627c  mov     [rsp+140h+var_C4], 0
0x180066284  mov     [rbp+40h+var_60], 0
0x18006628c  mov     [rbp+40h+var_68], 0
0x180066294  mov     [rsp+140h+var_C8], 0
0x18006629c  mov     eax, 0FFh
0x1800662a1  mov     [rsp+140h+var_CC], ax
0x1800662a6  xorps   xmm0, xmm0
0x1800662a9  movups  xmmword ptr [rbp+40h+var_28.Data], xmm0
0x1800662ad  mov     eax, [rbx+180h]
0x1800662b3  mov     [rsp+140h+csetcolumn], eax
0x1800662b7  lea     rax, [rsp+140h+csetcolumn]
0x1800662bc  mov     [rsp+140h+var_E0], rax; unsigned int *
0x1800662c1  mov     rax, [rbx+190h]
0x1800662c8  mov     [rsp+140h+var_E8], rax; struct JET_SETCOLUMN *
0x1800662cd  lea     rax, [rsp+140h+var_C8]
0x1800662d2  mov     [rsp+140h+var_F0], rax; unsigned int *
0x1800662d7  lea     rax, [rsp+140h+var_CC]
0x1800662dc  mov     [rsp+140h+var_F8], rax; __int16 *
0x1800662e1  lea     rax, [rbp+40h+var_68]
0x1800662e5  mov     [rsp+140h+var_100], rax; unsigned __int64 *
0x1800662ea  lea     rax, [rbp+40h+var_60]
0x1800662ee  mov     [rsp+140h+var_108], rax; unsigned __int64 *
0x1800662f3  lea     rax, [rsp+140h+var_C4]
0x1800662f8  mov     [rsp+140h+var_110], rax; unsigned int *
0x1800662fd  lea     rax, [rbp+40h+var_C0]
0x180066301  mov     [rsp+140h+var_118], rax; unsigned int *
0x180066306  lea     rax, [rbp+40h+var_28]
0x18006630a  mov     [rsp+140h+pcbActual], rax; struct peerdist_content_tag_tag *
0x18006630f  lea     r9, [rbp+40h+var_BC]; void *
0x180066313  lea     r8, [rbp+40h+var_A8]; struct TnoHash *
0x180066317  lea     rdx, [rbp+40h+var_88]; struct TnoHoHoDk *
0x18006631b  mov     rcx, rbx; this
0x18006631e  call    ?InitializeCatalogTableSetColumns@CRepubCreateReservedSegmentTask@@IEAAXPEBVTnoHoHoDk@@PEBVTnoHash@@PEAXPEBUpeerdist_content_tag_tag@@PEAK4PEA_K5PEAF4PEAUJET_SETCOLUMN@@4@Z; CRepubCreateReservedSegmentTask::InitializeCatalogTableSetColumns(TnoHoHoDk const *,TnoHash const *,void *,peerdist_content_tag_tag const *,ulong *,ulong *,unsigned __int64 *,unsigned __int64 *,short *,ulong *,JET_SETCOLUMN *,ulong *)
0x180066323  mov     r9d, [rsp+140h+csetcolumn]; csetcolumn
0x180066328  mov     r8, [rbx+190h]; psetcolumn
0x18006632f  mov     rdx, [rbx+1B0h]; tableid
0x180066336  mov     rcx, [rbx+178h]; sesid
0x18006633d  call    cs:__imp_JetSetColumns
0x180066343  mov     esi, eax
0x180066345  test    eax, eax
0x180066347  jz      loc_18006640C
0x18006634d  mov     rcx, cs:WPP_GLOBAL_Control
0x180066354  lea     rax, WPP_GLOBAL_Control
0x18006635b  cmp     rcx, rax
0x18006635e  jz      short loc_180066384
0x180066360  test    byte ptr [rcx+6Ch], 4
0x180066364  jz      short loc_180066384
0x180066366  cmp     [rcx+69h], dil
0x18006636a  jb      short loc_180066384
0x18006636c  mov     edx, 1EDh
0x180066371  mov     r9d, esi
0x180066374  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x18006637b  mov     rcx, [rcx+60h]
0x18006637f  call    WPP_SF_d
0x180066384  mov     rax, [rbx]
0x180066387  mov     edx, esi
0x180066389  mov     rcx, rbx
0x18006638c  mov     rax, [rax+30h]
0x180066390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066395  mov     esi, eax
0x180066397  mov     [rbp+40h+var_B8], eax
0x18006639a  xor     r14d, r14d
0x18006639d  cmp     [rsp+140h+csetcolumn], r14d
0x1800663a2  jbe     short loc_18006640A
0x1800663a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800663ab  lea     rsi, WPP_GLOBAL_Control
0x1800663b2  lea     r9, [r14+r14*4]
0x1800663b6  mov     rax, [rbx+190h]
0x1800663bd  mov     r8d, [rax+r9*8+20h]
0x1800663c2  test    r8d, r8d
0x1800663c5  jz      short loc_1800663FD
0x1800663c7  cmp     rcx, rsi
0x1800663ca  jz      short loc_1800663FD
0x1800663cc  test    byte ptr [rcx+6Ch], 4
0x1800663d0  jz      short loc_1800663FD
0x1800663d2  cmp     [rcx+69h], dil
0x1800663d6  jb      short loc_1800663FD
0x1800663d8  mov     edx, 1EEh
0x1800663dd  mov     dword ptr [rsp+140h+pcbActual], r8d
0x1800663e2  mov     r9d, [rax+r9*8]
0x1800663e6  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x1800663ed  mov     rcx, [rcx+60h]
0x1800663f1  call    WPP_SF_Dd
0x1800663f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800663fd  add     r14d, edi
0x180066400  cmp     r14d, [rsp+140h+csetcolumn]
0x180066405  jb      short loc_1800663B2
0x180066407  mov     esi, [rbp+40h+var_B8]
0x18006640a  jmp     short loc_180066483
0x18006640c  mov     [rsp+140h+pcbActual], 0; pcbActual
0x180066415  xor     r9d, r9d; cbBookmark
0x180066418  xor     r8d, r8d; pvBookmark
0x18006641b  mov     rdx, [rbx+1B0h]; tableid
0x180066422  mov     rcx, [rbx+178h]; sesid
0x180066429  call    cs:__imp_JetUpdate
0x18006642f  mov     esi, eax
0x180066431  test    eax, eax
0x180066433  jz      short loc_180066481
0x180066435  mov     rcx, cs:WPP_GLOBAL_Control
0x18006643c  lea     rax, WPP_GLOBAL_Control
0x180066443  cmp     rcx, rax
0x180066446  jz      short loc_18006646C
0x180066448  test    byte ptr [rcx+6Ch], 4
0x18006644c  jz      short loc_18006646C
0x18006644e  cmp     [rcx+69h], dil
0x180066452  jb      short loc_18006646C
0x180066454  mov     edx, 1EFh
0x180066459  mov     r9d, esi
0x18006645c  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x180066463  mov     rcx, [rcx+60h]
0x180066467  call    WPP_SF_d
0x18006646c  mov     rax, [rbx]
0x18006646f  mov     edx, esi
0x180066471  mov     rcx, rbx
0x180066474  mov     rax, [rax+30h]
0x180066478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006647d  mov     esi, eax
0x18006647f  jmp     short loc_18006640A
0x180066481  xor     esi, esi
0x180066483  lea     rbx, ??_7TnoHash@@6B@; const TnoHash::`vftable'
0x18006648a  mov     [rbp+40h+var_A8], rbx
0x18006648e  lea     rcx, [rbp+40h+var_A8]; this
0x180066492  call    ?ReleaseHash@TnoBaseHash@@QEAAXXZ; TnoBaseHash::ReleaseHash(void)
0x180066497  nop
0x180066498  mov     [rbp+40h+var_88], rbx
0x18006649c  lea     rcx, [rbp+40h+var_88]; this
0x1800664a0  call    ?ReleaseHash@TnoBaseHash@@QEAAXXZ; TnoBaseHash::ReleaseHash(void)
0x1800664a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800664ac  lea     rax, WPP_GLOBAL_Control
0x1800664b3  cmp     rcx, rax
0x1800664b6  jz      short loc_1800664DC
0x1800664b8  test    byte ptr [rcx+6Ch], 4
0x1800664bc  jz      short loc_1800664DC
0x1800664be  cmp     byte ptr [rcx+69h], 4
0x1800664c2  jb      short loc_1800664DC
0x1800664c4  mov     edx, 1F0h
0x1800664c9  mov     r9d, esi
0x1800664cc  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x1800664d3  mov     rcx, [rcx+60h]
0x1800664d7  call    WPP_SF_d
0x1800664dc  mov     eax, esi
0x1800664de  mov     rcx, [rbp+40h+var_18]
0x1800664e2  xor     rcx, rsp; StackCookie
0x1800664e5  call    __security_check_cookie
0x1800664ea  lea     r11, [rsp+140h+var_10]
0x1800664f2  mov     rbx, [r11+28h]
0x1800664f6  mov     rsi, [r11+30h]
0x1800664fa  mov     rsp, r11
0x1800664fd  pop     r14
0x1800664ff  pop     rdi
0x180066500  pop     rbp
0x180066501  retn
```
