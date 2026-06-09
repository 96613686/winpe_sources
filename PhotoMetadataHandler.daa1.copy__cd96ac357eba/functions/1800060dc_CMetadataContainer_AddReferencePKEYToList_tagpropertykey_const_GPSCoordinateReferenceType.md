# CMetadataContainer::_AddReferencePKEYToList(_tagpropertykey const &,GPSCoordinateReferenceType)

- ea: `0x1800060dc`
- end: `0x1800062c0`
- name: `?_AddReferencePKEYToList@CMetadataContainer@@AEAAXAEBU_tagpropertykey@@W4GPSCoordinateReferenceType@@@Z`
- size: `484`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180003970`
- `0x18001b1fc`

## callees

- `0x180004e00`
- `0x1800060dc`
- `0x18002648c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006192`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006192`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000617f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000617f`

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
0x1800060dc  mov     [rsp-8+arg_0], rbx
0x1800060e1  mov     [rsp-8+arg_8], rdi
0x1800060e6  push    rbp
0x1800060e7  mov     rbp, rsp
0x1800060ea  sub     rsp, 60h
0x1800060ee  xor     eax, eax
0x1800060f0  mov     [rbp+Buf1], 0
0x1800060f7  mov     rdi, rcx
0x1800060fa  mov     qword ptr [rbp+pvar+10h], rax
0x1800060fe  xorps   xmm0, xmm0
0x180006101  xorps   xmm1, xmm1
0x180006104  mov     ebx, r8d
0x180006107  lea     ecx, [rax+64h]
0x18000610a  movups  [rbp+var_2C], xmm0
0x18000610e  movups  xmmword ptr [rbp+pvar], xmm1
0x180006112  cmp     [rdx+10h], ecx
0x180006115  jz      short loc_180006133
0x180006117  mov     r8d, 10h; Size
0x18000611d  lea     rdx, PKEY_Null; Buf2
0x180006124  lea     rcx, [rbp+Buf1]; Buf1
0x180006128  call    memcmp_0
0x18000612d  test    eax, eax
0x18000612f  jnz     short loc_180006173
0x180006131  jmp     short loc_18000618E
0x180006133  mov     rax, [rdx]
0x180006136  sub     rax, qword ptr cs:PKEY_GPS_Latitude.fmtid.Data1
0x18000613d  jnz     short loc_18000614A
0x18000613f  mov     rax, [rdx+8]
0x180006143  sub     rax, qword ptr cs:PKEY_GPS_Latitude.fmtid.Data4
0x18000614a  test    rax, rax
0x18000614d  jnz     loc_1800061EB
0x180006153  movsd   xmm0, qword ptr cs:PKEY_GPS_LatitudeRef.fmtid.Data2
0x18000615b  mov     eax, dword ptr cs:PKEY_GPS_LatitudeRef.fmtid.Data4+4
0x180006161  mov     [rbp+Buf1], 29C0252h
0x180006168  movsd   qword ptr [rbp+var_2C], xmm0
0x18000616d  mov     dword ptr [rbp+var_2C+8], eax
0x180006170  mov     dword ptr [rbp+var_2C+0Ch], ecx
0x180006173  mov     eax, 1Fh
0x180006178  mov     word ptr [rbp+pvar], ax
0x18000617c  lea     ecx, [rax-1Bh]; cb
0x18000617f  call    cs:__imp_CoTaskMemAlloc
0x180006185  mov     qword ptr [rbp+pvar+8], rax
0x180006189  test    rax, rax
0x18000618c  jnz     short loc_1800061A8
0x18000618e  lea     rcx, [rbp+pvar]; pvar
0x180006192  call    cs:__imp_PropVariantClear
0x180006198  mov     rbx, [rsp+60h+arg_0]
0x18000619d  mov     rdi, [rsp+60h+arg_8]
0x1800061a2  add     rsp, 60h
0x1800061a6  pop     rbp
0x1800061a7  retn
0x1800061a8  xor     ecx, ecx
0x1800061aa  mov     [rax], ecx
0x1800061ac  sub     ebx, 1
0x1800061af  jz      loc_1800062B2
0x1800061b5  sub     ebx, 1
0x1800061b8  jz      loc_1800062A4
0x1800061be  sub     ebx, 1
0x1800061c1  jnz     loc_180006291
0x1800061c7  mov     rax, qword ptr [rbp+pvar+8]
0x1800061cb  mov     word ptr [rax], 45h ; 'E'
0x1800061d0  lea     rcx, [rdi+60h]; this
0x1800061d4  mov     [rsp+60h+var_40], 0; bool
0x1800061d9  xor     r9d, r9d; bool
0x1800061dc  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x1800061e0  lea     rdx, [rbp+Buf1]; struct _tagpropertykey *
0x1800061e4  call    ?_InternalUpdateOrAddItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@_N2@Z; CPhotoPropertyItemList::_InternalUpdateOrAddItem(_tagpropertykey const *,tagPROPVARIANT const *,bool,bool)
0x1800061e9  jmp     short loc_18000618E
0x1800061eb  mov     rax, [rdx]
0x1800061ee  sub     rax, qword ptr cs:PKEY_GPS_DestLatitude.fmtid.Data1
0x1800061f5  jnz     short loc_180006202
0x1800061f7  mov     rax, [rdx+8]
0x1800061fb  sub     rax, qword ptr cs:PKEY_GPS_DestLatitude.fmtid.Data4
0x180006202  test    rax, rax
0x180006205  jz      short loc_18000625D
0x180006207  mov     rax, [rdx]
0x18000620a  sub     rax, qword ptr cs:PKEY_GPS_Longitude.fmtid.Data1
0x180006211  jnz     short loc_18000621E
0x180006213  mov     rax, [rdx+8]
0x180006217  sub     rax, qword ptr cs:PKEY_GPS_Longitude.fmtid.Data4
0x18000621e  test    rax, rax
0x180006221  jz      short loc_180006277
0x180006223  mov     rax, [rdx]
0x180006226  sub     rax, qword ptr cs:PKEY_GPS_DestLongitude.fmtid.Data1
0x18000622d  jnz     short loc_18000623A
0x18000622f  mov     rax, [rdx+8]
0x180006233  sub     rax, qword ptr cs:PKEY_GPS_DestLongitude.fmtid.Data4
0x18000623a  test    rax, rax
0x18000623d  jnz     loc_180006117
0x180006243  movsd   xmm0, qword ptr cs:PKEY_GPS_DestLongitudeRef.fmtid.Data2
0x18000624b  mov     eax, dword ptr cs:PKEY_GPS_DestLongitudeRef.fmtid.Data4+4
0x180006251  mov     [rbp+Buf1], 182C1EA6h
0x180006258  jmp     loc_180006168
0x18000625d  movsd   xmm0, qword ptr cs:PKEY_GPS_DestLatitudeRef.fmtid.Data2
0x180006265  mov     eax, dword ptr cs:PKEY_GPS_DestLatitudeRef.fmtid.Data4+4
0x18000626b  mov     [rbp+Buf1], 0CEA820B9h
0x180006272  jmp     loc_180006168
0x180006277  movsd   xmm0, qword ptr cs:PKEY_GPS_LongitudeRef.fmtid.Data2
0x18000627f  mov     eax, dword ptr cs:PKEY_GPS_LongitudeRef.fmtid.Data4+4
0x180006285  mov     [rbp+Buf1], 33DCF22Bh
0x18000628c  jmp     loc_180006168
0x180006291  cmp     ebx, 1
0x180006294  jnz     short loc_1800062B2
0x180006296  mov     rax, qword ptr [rbp+pvar+8]
0x18000629a  mov     word ptr [rax], 57h ; 'W'
0x18000629f  jmp     loc_1800061D0
0x1800062a4  mov     rax, qword ptr [rbp+pvar+8]
0x1800062a8  mov     word ptr [rax], 53h ; 'S'
0x1800062ad  jmp     loc_1800061D0
0x1800062b2  mov     rax, qword ptr [rbp+pvar+8]
0x1800062b6  mov     word ptr [rax], 4Eh ; 'N'
0x1800062bb  jmp     loc_1800061D0
```
