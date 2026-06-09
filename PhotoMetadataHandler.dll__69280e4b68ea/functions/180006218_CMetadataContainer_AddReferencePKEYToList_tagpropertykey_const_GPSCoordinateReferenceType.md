# CMetadataContainer::_AddReferencePKEYToList(_tagpropertykey const &,GPSCoordinateReferenceType)

- ea: `0x180006218`
- end: `0x180006409`
- name: `?_AddReferencePKEYToList@CMetadataContainer@@AEAAXAEBU_tagpropertykey@@W4GPSCoordinateReferenceType@@@Z`
- size: `497`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180003900`
- `0x18001beb8`

## callees

- `0x180004e20`
- `0x180006218`
- `0x18002773c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800062d4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800062d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800062bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800062bb`

## pseudocode

```c
HRESULT __fastcall CMetadataContainer::_AddReferencePKEYToList(__int64 a1, __int64 a2, int a3)
{
  __int64 v5; // rax
  __int64 v6; // xmm0_8
  int v7; // eax
  _DWORD *v8; // rax
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  struct _tagpropertykey Buf1; // [rsp+30h] [rbp-30h] BYREF
  PROPVARIANT pvar; // [rsp+48h] [rbp-18h] BYREF

  memset(&Buf1, 0, sizeof(Buf1));
  memset(&pvar, 0, sizeof(pvar));
  if ( *(_DWORD *)(a2 + 16) != 100 )
    goto LABEL_2;
  v5 = *(_QWORD *)a2 - *(_QWORD *)&PKEY_GPS_Latitude.fmtid.Data1;
  if ( *(_QWORD *)a2 == *(_QWORD *)&PKEY_GPS_Latitude.fmtid.Data1 )
    v5 = *(_QWORD *)(a2 + 8) - *(_QWORD *)PKEY_GPS_Latitude.fmtid.Data4;
  if ( !v5 )
  {
    v6 = *(_QWORD *)&PKEY_GPS_LatitudeRef.fmtid.Data2;
    v7 = *(_DWORD *)&PKEY_GPS_LatitudeRef.fmtid.Data4[4];
    Buf1.fmtid.Data1 = 43778642;
LABEL_8:
    *(_QWORD *)&Buf1.fmtid.Data2 = v6;
    *(_DWORD *)&Buf1.fmtid.Data4[4] = v7;
    Buf1.pid = 100;
    goto LABEL_9;
  }
  v13 = *(_QWORD *)a2 - *(_QWORD *)&PKEY_GPS_DestLatitude.fmtid.Data1;
  if ( *(_QWORD *)a2 == *(_QWORD *)&PKEY_GPS_DestLatitude.fmtid.Data1 )
    v13 = *(_QWORD *)(a2 + 8) - *(_QWORD *)PKEY_GPS_DestLatitude.fmtid.Data4;
  if ( !v13 )
  {
    v6 = *(_QWORD *)&PKEY_GPS_DestLatitudeRef.fmtid.Data2;
    v7 = *(_DWORD *)&PKEY_GPS_DestLatitudeRef.fmtid.Data4[4];
    Buf1.fmtid.Data1 = -827842375;
    goto LABEL_8;
  }
  v14 = *(_QWORD *)a2 - *(_QWORD *)&PKEY_GPS_Longitude.fmtid.Data1;
  if ( *(_QWORD *)a2 == *(_QWORD *)&PKEY_GPS_Longitude.fmtid.Data1 )
    v14 = *(_QWORD *)(a2 + 8) - *(_QWORD *)PKEY_GPS_Longitude.fmtid.Data4;
  if ( !v14 )
  {
    v6 = *(_QWORD *)&PKEY_GPS_LongitudeRef.fmtid.Data2;
    v7 = *(_DWORD *)&PKEY_GPS_LongitudeRef.fmtid.Data4[4];
    Buf1.fmtid.Data1 = 870117931;
    goto LABEL_8;
  }
  v15 = *(_QWORD *)a2 - *(_QWORD *)&PKEY_GPS_DestLongitude.fmtid.Data1;
  if ( *(_QWORD *)a2 == *(_QWORD *)&PKEY_GPS_DestLongitude.fmtid.Data1 )
    v15 = *(_QWORD *)(a2 + 8) - *(_QWORD *)PKEY_GPS_DestLongitude.fmtid.Data4;
  if ( !v15 )
  {
    v6 = *(_QWORD *)&PKEY_GPS_DestLongitudeRef.fmtid.Data2;
    v7 = *(_DWORD *)&PKEY_GPS_DestLongitudeRef.fmtid.Data4[4];
    Buf1.fmtid.Data1 = 405544614;
    goto LABEL_8;
  }
LABEL_2:
  if ( !memcmp_0(&Buf1, &PKEY_Null, 0x10u) )
    return PropVariantClear(&pvar);
LABEL_9:
  pvar.vt = 31;
  v8 = CoTaskMemAlloc(4u);
  pvar.hVal.QuadPart = (LONGLONG)v8;
  if ( v8 )
  {
    *v8 = 0;
    v10 = a3 - 1;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( !v11 )
      {
        *pvar.bstrVal = 83;
        goto LABEL_15;
      }
      v12 = v11 - 1;
      if ( !v12 )
      {
        *pvar.bstrVal = 69;
LABEL_15:
        CPhotoPropertyItemList::_InternalUpdateOrAddItem((CPhotoPropertyItemList *)(a1 + 96), &Buf1, &pvar, 0, 0);
        return PropVariantClear(&pvar);
      }
      if ( v12 == 1 )
      {
        *pvar.bstrVal = 87;
        goto LABEL_15;
      }
    }
    *pvar.bstrVal = 78;
    goto LABEL_15;
  }
  return PropVariantClear(&pvar);
}

```

## disassembly

```asm
0x180006218  mov     [rsp-8+arg_0], rbx
0x18000621d  mov     [rsp-8+arg_8], rdi
0x180006222  push    rbp
0x180006223  mov     rbp, rsp
0x180006226  sub     rsp, 60h
0x18000622a  xor     eax, eax
0x18000622c  mov     [rbp+Buf1], 0
0x180006233  mov     rdi, rcx
0x180006236  mov     qword ptr [rbp+pvar+10h], rax
0x18000623a  xorps   xmm0, xmm0
0x18000623d  xorps   xmm1, xmm1
0x180006240  mov     ebx, r8d
0x180006243  lea     ecx, [rax+64h]
0x180006246  movups  [rbp+var_2C], xmm0
0x18000624a  movups  xmmword ptr [rbp+pvar], xmm1
0x18000624e  cmp     [rdx+10h], ecx
0x180006251  jz      short loc_18000626F
0x180006253  mov     r8d, 10h; Size
0x180006259  lea     rdx, PKEY_Null; Buf2
0x180006260  lea     rcx, [rbp+Buf1]; Buf1
0x180006264  call    memcmp_0
0x180006269  test    eax, eax
0x18000626b  jnz     short loc_1800062AF
0x18000626d  jmp     short loc_1800062D0
0x18000626f  mov     rax, [rdx]
0x180006272  sub     rax, qword ptr cs:PKEY_GPS_Latitude.fmtid.Data1
0x180006279  jnz     short loc_180006286
0x18000627b  mov     rax, [rdx+8]
0x18000627f  sub     rax, qword ptr cs:PKEY_GPS_Latitude.fmtid.Data4
0x180006286  test    rax, rax
0x180006289  jnz     loc_180006334
0x18000628f  movsd   xmm0, qword ptr cs:PKEY_GPS_LatitudeRef.fmtid.Data2
0x180006297  mov     eax, dword ptr cs:PKEY_GPS_LatitudeRef.fmtid.Data4+4
0x18000629d  mov     [rbp+Buf1], 29C0252h
0x1800062a4  movsd   qword ptr [rbp+var_2C], xmm0
0x1800062a9  mov     dword ptr [rbp+var_2C+8], eax
0x1800062ac  mov     dword ptr [rbp+var_2C+0Ch], ecx
0x1800062af  mov     eax, 1Fh
0x1800062b4  mov     word ptr [rbp+pvar], ax
0x1800062b8  lea     ecx, [rax-1Bh]; cb
0x1800062bb  call    cs:__imp_CoTaskMemAlloc
0x1800062c2  nop     dword ptr [rax+rax+00h]
0x1800062c7  mov     qword ptr [rbp+pvar+8], rax
0x1800062cb  test    rax, rax
0x1800062ce  jnz     short loc_1800062F1
0x1800062d0  lea     rcx, [rbp+pvar]; pvar
0x1800062d4  call    cs:__imp_PropVariantClear
0x1800062db  nop     dword ptr [rax+rax+00h]
0x1800062e0  mov     rbx, [rsp+60h+arg_0]
0x1800062e5  mov     rdi, [rsp+60h+arg_8]
0x1800062ea  add     rsp, 60h
0x1800062ee  pop     rbp
0x1800062ef  retn
0x1800062f1  xor     ecx, ecx
0x1800062f3  mov     [rax], ecx
0x1800062f5  sub     ebx, 1
0x1800062f8  jz      loc_1800063FB
0x1800062fe  sub     ebx, 1
0x180006301  jz      loc_1800063ED
0x180006307  sub     ebx, 1
0x18000630a  jnz     loc_1800063DA
0x180006310  mov     rax, qword ptr [rbp+pvar+8]
0x180006314  mov     word ptr [rax], 45h ; 'E'
0x180006319  lea     rcx, [rdi+60h]; this
0x18000631d  mov     [rsp+60h+var_40], 0; bool
0x180006322  xor     r9d, r9d; bool
0x180006325  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x180006329  lea     rdx, [rbp+Buf1]; struct _tagpropertykey *
0x18000632d  call    ?_InternalUpdateOrAddItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@_N2@Z; CPhotoPropertyItemList::_InternalUpdateOrAddItem(_tagpropertykey const *,tagPROPVARIANT const *,bool,bool)
0x180006332  jmp     short loc_1800062D0
0x180006334  mov     rax, [rdx]
0x180006337  sub     rax, qword ptr cs:PKEY_GPS_DestLatitude.fmtid.Data1
0x18000633e  jnz     short loc_18000634B
0x180006340  mov     rax, [rdx+8]
0x180006344  sub     rax, qword ptr cs:PKEY_GPS_DestLatitude.fmtid.Data4
0x18000634b  test    rax, rax
0x18000634e  jz      short loc_1800063A6
0x180006350  mov     rax, [rdx]
0x180006353  sub     rax, qword ptr cs:PKEY_GPS_Longitude.fmtid.Data1
0x18000635a  jnz     short loc_180006367
0x18000635c  mov     rax, [rdx+8]
0x180006360  sub     rax, qword ptr cs:PKEY_GPS_Longitude.fmtid.Data4
0x180006367  test    rax, rax
0x18000636a  jz      short loc_1800063C0
0x18000636c  mov     rax, [rdx]
0x18000636f  sub     rax, qword ptr cs:PKEY_GPS_DestLongitude.fmtid.Data1
0x180006376  jnz     short loc_180006383
0x180006378  mov     rax, [rdx+8]
0x18000637c  sub     rax, qword ptr cs:PKEY_GPS_DestLongitude.fmtid.Data4
0x180006383  test    rax, rax
0x180006386  jnz     loc_180006253
0x18000638c  movsd   xmm0, qword ptr cs:PKEY_GPS_DestLongitudeRef.fmtid.Data2
0x180006394  mov     eax, dword ptr cs:PKEY_GPS_DestLongitudeRef.fmtid.Data4+4
0x18000639a  mov     [rbp+Buf1], 182C1EA6h
0x1800063a1  jmp     loc_1800062A4
0x1800063a6  movsd   xmm0, qword ptr cs:PKEY_GPS_DestLatitudeRef.fmtid.Data2
0x1800063ae  mov     eax, dword ptr cs:PKEY_GPS_DestLatitudeRef.fmtid.Data4+4
0x1800063b4  mov     [rbp+Buf1], 0CEA820B9h
0x1800063bb  jmp     loc_1800062A4
0x1800063c0  movsd   xmm0, qword ptr cs:PKEY_GPS_LongitudeRef.fmtid.Data2
0x1800063c8  mov     eax, dword ptr cs:PKEY_GPS_LongitudeRef.fmtid.Data4+4
0x1800063ce  mov     [rbp+Buf1], 33DCF22Bh
0x1800063d5  jmp     loc_1800062A4
0x1800063da  cmp     ebx, 1
0x1800063dd  jnz     short loc_1800063FB
0x1800063df  mov     rax, qword ptr [rbp+pvar+8]
0x1800063e3  mov     word ptr [rax], 57h ; 'W'
0x1800063e8  jmp     loc_180006319
0x1800063ed  mov     rax, qword ptr [rbp+pvar+8]
0x1800063f1  mov     word ptr [rax], 53h ; 'S'
0x1800063f6  jmp     loc_180006319
0x1800063fb  mov     rax, qword ptr [rbp+pvar+8]
0x1800063ff  mov     word ptr [rax], 4Eh ; 'N'
0x180006404  jmp     loc_180006319
```
