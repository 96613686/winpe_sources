# CPubPersistPublicationTask::UpdateCatalogRecord(void)

- ea: `0x1800912a8`
- end: `0x180091564`
- name: `?UpdateCatalogRecord@CPubPersistPublicationTask@@IEAAKXZ`
- size: `700`
- prototype: `unsigned int __fastcall(CPubPersistPublicationTask *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x18008f640`

## callees

- `0x180008290`
- `0x18000ceac`
- `0x180063414`
- `0x180076218`
- `0x1800912a8`
- `0x180159010`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x1800913e3`
- `ESENT!JetPrepareUpdate` at `0x1800913e3`
- `ESENT!JetSetColumns` at `0x18009145e`
- `ESENT!JetSetColumns` at `0x18009145e`
- `ESENT!JetUpdate` at `0x1800914c5`
- `ESENT!JetUpdate` at `0x1800914c5`

## pseudocode

```c
__int64 __fastcall CPubPersistPublicationTask::UpdateCatalogRecord(CPubPersistPublicationTask *this)
{
  unsigned __int64 v1; // r9
  unsigned __int64 v3; // rcx
  __int64 v5; // rax
  int v6; // ecx
  __int64 v7; // rax
  int v8; // ecx
  __int64 v9; // rax
  unsigned int v10; // eax
  unsigned int v11; // ebx
  CHostedCacheMsgEncoding *v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // r9d
  unsigned int updated; // eax
  unsigned __int64 v18; // [rsp+70h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 64);
  v18 = v1;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_IIID(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      222,
      WPP_44a976264dd93922b20292445dd7a2ed_Traceguids,
      *((_QWORD *)this + 60),
      v1 + *((_QWORD *)this + 61),
      v1,
      *((_DWORD *)this + 126));
    v1 = v18;
  }
  v3 = v1 + *((_QWORD *)this + 61);
  if ( v3 < v1 )
    return 774;
  v5 = *((_QWORD *)this + 51);
  *((_DWORD *)this + 126) |= 4u;
  v18 = v3;
  v6 = *(_DWORD *)(v5 + 692);
  v7 = *((_QWORD *)this + 50);
  *(_DWORD *)(v7 + 4) = 0;
  *(_QWORD *)(v7 + 20) = 0;
  *(_QWORD *)(v7 + 32) = 0;
  *(_DWORD *)v7 = v6;
  *(_QWORD *)(v7 + 8) = &v18;
  *(_DWORD *)(v7 + 16) = 8;
  *(_DWORD *)(v7 + 28) = 1;
  v8 = *(_DWORD *)(*((_QWORD *)this + 51) + 688LL);
  v9 = *((_QWORD *)this + 50);
  *(_DWORD *)(v9 + 44) = 0;
  *(_QWORD *)(v9 + 60) = 0;
  *(_QWORD *)(v9 + 72) = 0;
  *(_DWORD *)(v9 + 40) = v8;
  *(_DWORD *)(v9 + 56) = 4;
  *(_QWORD *)(v9 + 48) = (char *)this + 504;
  *(_DWORD *)(v9 + 68) = 1;
  v10 = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 53), 2u);
  if ( v10 )
  {
    v11 = (*(__int64 (__fastcall **)(CPubPersistPublicationTask *, _QWORD))(*(_QWORD *)this + 24LL))(this, v10);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      return v11;
    }
    v13 = 223;
    goto LABEL_12;
  }
  v14 = JetSetColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 53), *((JET_SETCOLUMN **)this + 50), 2u);
  if ( v14 )
  {
    v11 = (*(__int64 (__fastcall **)(CPubPersistPublicationTask *, _QWORD))(*(_QWORD *)this + 24LL))(this, v14);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      return v11;
    }
    v13 = 224;
    goto LABEL_12;
  }
  v15 = JetUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 53), 0, 0, 0);
  if ( !v15 )
  {
    updated = UpdatePublicationCount(
                *((_QWORD *)this + 47),
                *((_QWORD *)this + 54),
                *((const struct _PublicationDatabaseDescriptor **)this + 51),
                v16,
                1);
    v11 = updated;
    if ( updated
      && WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 226, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids, updated);
    }
    return v11;
  }
  v11 = (*(__int64 (__fastcall **)(CPubPersistPublicationTask *, _QWORD))(*(_QWORD *)this + 24LL))(this, v15);
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v13 = 225;
LABEL_12:
    WPP_SF_Dd(*((_QWORD *)v12 + 12), v13, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids);
  }
  return v11;
}

```

## disassembly

```asm
0x1800912a8  push    rbx
0x1800912aa  push    rdi
0x1800912ab  push    r14
0x1800912ad  push    r15
0x1800912af  sub     rsp, 48h
0x1800912b3  mov     r9, [rcx+200h]
0x1800912ba  mov     rbx, rcx
0x1800912bd  mov     [rsp+68h+arg_0], r9
0x1800912c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800912c9  lea     r15, WPP_GLOBAL_Control
0x1800912d0  lea     r14, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids
0x1800912d7  cmp     rcx, r15
0x1800912da  jz      short loc_180091323
0x1800912dc  test    byte ptr [rcx+6Ch], 4
0x1800912e0  jz      short loc_180091323
0x1800912e2  cmp     byte ptr [rcx+69h], 4
0x1800912e6  jb      short loc_180091323
0x1800912e8  mov     r8, [rbx+1E8h]
0x1800912ef  mov     edx, 0DEh
0x1800912f4  mov     eax, [rbx+1F8h]
0x1800912fa  add     r8, r9
0x1800912fd  mov     rcx, [rcx+60h]
0x180091301  mov     [rsp+68h+var_38], eax
0x180091305  mov     [rsp+68h+var_40], r9
0x18009130a  mov     r9, [rbx+1E0h]
0x180091311  mov     [rsp+68h+pcbActual], r8
0x180091316  mov     r8, r14
0x180091319  call    WPP_SF_IIID
0x18009131e  mov     r9, [rsp+68h+arg_0]
0x180091323  mov     rcx, [rbx+1E8h]
0x18009132a  add     rcx, r9
0x18009132d  cmp     rcx, r9
0x180091330  jnb     short loc_18009133C
0x180091332  mov     eax, 306h
0x180091337  jmp     loc_180091559
0x18009133c  mov     rax, [rbx+198h]
0x180091343  lea     rdx, [rbx+1F8h]
0x18009134a  or      dword ptr [rdx], 4
0x18009134d  mov     r8d, 2; prep
0x180091353  mov     [rsp+68h+arg_0], rcx
0x180091358  mov     ecx, [rax+2B4h]
0x18009135e  mov     rax, [rbx+190h]
0x180091365  mov     dword ptr [rax+4], 0
0x18009136c  mov     qword ptr [rax+14h], 0
0x180091374  mov     qword ptr [rax+20h], 0
0x18009137c  mov     [rax], ecx
0x18009137e  lea     rcx, [rsp+68h+arg_0]
0x180091383  mov     [rax+8], rcx
0x180091387  mov     dword ptr [rax+10h], 8
0x18009138e  mov     dword ptr [rax+1Ch], 1
0x180091395  mov     rax, [rbx+198h]
0x18009139c  mov     ecx, [rax+2B0h]
0x1800913a2  mov     rax, [rbx+190h]
0x1800913a9  mov     dword ptr [rax+2Ch], 0
0x1800913b0  mov     qword ptr [rax+3Ch], 0
0x1800913b8  mov     qword ptr [rax+48h], 0
0x1800913c0  mov     [rax+28h], ecx
0x1800913c3  mov     dword ptr [rax+38h], 4
0x1800913ca  mov     [rax+30h], rdx
0x1800913ce  mov     dword ptr [rax+44h], 1
0x1800913d5  mov     rdx, [rbx+1A8h]; tableid
0x1800913dc  mov     rcx, [rbx+178h]; sesid
0x1800913e3  call    cs:__imp_JetPrepareUpdate
0x1800913e9  mov     edi, eax
0x1800913eb  test    eax, eax
0x1800913ed  jz      short loc_180091443
0x1800913ef  mov     rcx, [rbx]
0x1800913f2  mov     edx, edi
0x1800913f4  mov     rax, [rcx+18h]
0x1800913f8  mov     rcx, rbx
0x1800913fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091400  mov     ebx, eax
0x180091402  mov     rcx, cs:WPP_GLOBAL_Control
0x180091409  cmp     rcx, r15
0x18009140c  jz      loc_180091557
0x180091412  test    byte ptr [rcx+6Ch], 4
0x180091416  jz      loc_180091557
0x18009141c  cmp     byte ptr [rcx+69h], 1
0x180091420  jb      loc_180091557
0x180091426  mov     edx, 0DFh
0x18009142b  mov     rcx, [rcx+60h]
0x18009142f  mov     r9d, edi
0x180091432  mov     r8, r14
0x180091435  mov     dword ptr [rsp+68h+pcbActual], eax
0x180091439  call    WPP_SF_Dd
0x18009143e  jmp     loc_180091557
0x180091443  mov     r8, [rbx+190h]; psetcolumn
0x18009144a  mov     r9d, 2; csetcolumn
0x180091450  mov     rdx, [rbx+1A8h]; tableid
0x180091457  mov     rcx, [rbx+178h]; sesid
0x18009145e  call    cs:__imp_JetSetColumns
0x180091464  mov     edi, eax
0x180091466  test    eax, eax
0x180091468  jz      short loc_1800914A8
0x18009146a  mov     rcx, [rbx]
0x18009146d  mov     edx, edi
0x18009146f  mov     rax, [rcx+18h]
0x180091473  mov     rcx, rbx
0x180091476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009147b  mov     ebx, eax
0x18009147d  mov     rcx, cs:WPP_GLOBAL_Control
0x180091484  cmp     rcx, r15
0x180091487  jz      loc_180091557
0x18009148d  test    byte ptr [rcx+6Ch], 4
0x180091491  jz      loc_180091557
0x180091497  cmp     byte ptr [rcx+69h], 1
0x18009149b  jb      loc_180091557
0x1800914a1  mov     edx, 0E0h
0x1800914a6  jmp     short loc_18009142B
0x1800914a8  mov     rdx, [rbx+1A8h]; tableid
0x1800914af  xor     r9d, r9d; cbBookmark
0x1800914b2  mov     rcx, [rbx+178h]; sesid
0x1800914b9  xor     r8d, r8d; pvBookmark
0x1800914bc  mov     [rsp+68h+pcbActual], 0; pcbActual
0x1800914c5  call    cs:__imp_JetUpdate
0x1800914cb  mov     edi, eax
0x1800914cd  test    eax, eax
0x1800914cf  jz      short loc_180091506
0x1800914d1  mov     rcx, [rbx]
0x1800914d4  mov     edx, edi
0x1800914d6  mov     rax, [rcx+18h]
0x1800914da  mov     rcx, rbx
0x1800914dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800914e2  mov     ebx, eax
0x1800914e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800914eb  cmp     rcx, r15
0x1800914ee  jz      short loc_180091557
0x1800914f0  test    byte ptr [rcx+6Ch], 4
0x1800914f4  jz      short loc_180091557
0x1800914f6  cmp     byte ptr [rcx+69h], 1
0x1800914fa  jb      short loc_180091557
0x1800914fc  mov     edx, 0E1h
0x180091501  jmp     loc_18009142B
0x180091506  mov     r8, [rbx+198h]; struct _PublicationDatabaseDescriptor *
0x18009150d  mov     rdx, [rbx+1B0h]; tableid
0x180091514  mov     rcx, [rbx+178h]; sesid
0x18009151b  mov     byte ptr [rsp+68h+pcbActual], 1; bool
0x180091520  call    ?UpdatePublicationCount@@YAK_K0PEBU_PublicationDatabaseDescriptor@@K_N@Z; UpdatePublicationCount(unsigned __int64,unsigned __int64,_PublicationDatabaseDescriptor const *,ulong,bool)
0x180091525  mov     ebx, eax
0x180091527  test    eax, eax
0x180091529  jz      short loc_180091557
0x18009152b  mov     rcx, cs:WPP_GLOBAL_Control
0x180091532  cmp     rcx, r15
0x180091535  jz      short loc_180091557
0x180091537  test    byte ptr [rcx+6Ch], 4
0x18009153b  jz      short loc_180091557
0x18009153d  cmp     byte ptr [rcx+69h], 1
0x180091541  jb      short loc_180091557
0x180091543  mov     rcx, [rcx+60h]
0x180091547  mov     edx, 0E2h
0x18009154c  mov     r9d, eax
0x18009154f  mov     r8, r14
0x180091552  call    WPP_SF_d
0x180091557  mov     eax, ebx
0x180091559  add     rsp, 48h
0x18009155d  pop     r15
0x18009155f  pop     r14
0x180091561  pop     rdi
0x180091562  pop     rbx
0x180091563  retn
```
