# MvGetMccFromGeoId(ushort * *)

- ea: `0x180007050`
- end: `0x180007810`
- name: `?MvGetMccFromGeoId@@YAJPEAPEAG@Z`
- size: `1984`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180005644`
- `0x180006d94`
- `0x180007050`
- `0x18000f998`
- `0x180010f80`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x18000708b`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x18000709b`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x18000708b`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x18000709b`
- `XmlLite!CreateXmlReader` at `0x18000714e`
- `XmlLite!CreateXmlReader` at `0x18000714e`
- `DMCmnUtils!SafeStringToDword` at `0x180007383`
- `DMCmnUtils!SafeStringToDword` at `0x180007383`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x1800070f4`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x1800070f4`

## pseudocode

```c
__int64 __fastcall MvGetMccFromGeoId(unsigned __int16 **a1)
{
  GEOID UserGeoID; // edi
  int MccLookupTablePath; // eax
  unsigned int v4; // ebx
  HRESULT v6; // eax
  IStream *v7; // rcx
  HRESULT v8; // eax
  void *v9; // rcx
  IStream *v10; // rcx
  int v11; // eax
  void *v12; // rcx
  IStream *v13; // rcx
  int v14; // eax
  void *v15; // rcx
  IStream *v16; // rcx
  int v17; // eax
  unsigned __int16 *v18; // rax
  int v19; // r8d
  int v20; // edx
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  void *v28; // rcx
  IStream *v29; // rcx
  void *v30; // rcx
  IStream *v31; // rcx
  void *v32; // rcx
  IStream *v33; // rcx
  void *v34; // rcx
  IStream *v35; // rcx
  void (*Release)(void); // rax
  void *v37; // rcx
  IStream *v38; // rcx
  void *v39; // rcx
  IStream *v40; // rcx
  void *v41; // rcx
  IStream *v42; // rcx
  void *v43; // rcx
  IStream *v44; // rcx
  void *v45; // rcx
  IStream *v46; // rcx
  void *v47; // rcx
  IStream *v48; // rcx
  void *v49; // rcx
  IStream *v50; // rcx
  void *ppvObject; // [rsp+20h] [rbp-E0h] BYREF
  IStream *ppstm; // [rsp+28h] [rbp-D8h] BYREF
  int v53; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v54; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int16 *v55; // [rsp+38h] [rbp-C8h] BYREF
  char *v56; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszFile[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a1 = 0;
  UserGeoID = GetUserGeoID(0x10u);
  if ( UserGeoID != -1 || (UserGeoID = GetUserGeoID(0xEu), UserGeoID != -1) )
  {
    MccLookupTablePath = GetMccLookupTablePath(pszFile, 260);
    v4 = MccLookupTablePath;
    if ( MccLookupTablePath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AB,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\countryhelpers.cpp",
        (const char *)(unsigned int)MccLookupTablePath,
        (int)ppvObject);
      return v4;
    }
    ppstm = 0;
    v6 = SHCreateStreamOnFileW(pszFile, 0, &ppstm);
    v4 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AE,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\countryhelpers.cpp",
        (const char *)(unsigned int)v6,
        (int)ppvObject);
      v7 = ppstm;
      if ( ppstm )
      {
        ppstm = 0;
        ((void (__fastcall *)(IStream *))v7->lpVtbl->Release)(v7);
      }
      return v4;
    }
    ppvObject = 0;
    v8 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
    v4 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B1,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\countryhelpers.cpp",
        (const char *)(unsigned int)v8,
        (int)ppvObject);
      v9 = ppvObject;
      if ( ppvObject )
      {
        ppvObject = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
      }
      v10 = ppstm;
      if ( ppstm )
      {
        ppstm = 0;
        ((void (__fastcall *)(IStream *))v10->lpVtbl->Release)(v10);
      }
      return v4;
    }
    v11 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
    v4 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B2,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\countryhelpers.cpp",
        (const char *)(unsigned int)v11,
        (int)ppvObject);
      v12 = ppvObject;
      if ( ppvObject )
      {
        ppvObject = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
      }
      v13 = ppstm;
      if ( ppstm )
      {
        ppstm = 0;
        ((void (__fastcall *)(IStream *))v13->lpVtbl->Release)(v13);
      }
      return v4;
    }
    v14 = (*(__int64 (__fastcall **)(void *, IStream *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppstm);
    v4 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B3,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\countryhelpers.cpp",
        (const char *)(unsigned int)v14,
        (int)ppvObject);
      v15 = ppvObject;
      if ( ppvObject )
      {
        ppvObject = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
      }
      v16 = ppstm;
      if ( ppstm )
      {
        ppstm = 0;
        ((void (__fastcall *)(IStream *))v16->lpVtbl->Release)(v16);
      }
      return v4;
    }
    v56 = 0;
    v53 = 0;
    while ( 1 )
    {
      v27 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v53);
      v4 = v27;
      if ( v27 )
        break;
      if ( *a1 )
        goto LABEL_97;
      if ( v53 == 1 )
      {
        v17 = (*(__int64 (__fastcall **)(void *, char **, _QWORD))(*(_QWORD *)ppvObject + 112LL))(ppvObject, &v56, 0);
        v4 = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1BE,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\countryhelpers.cpp",
            (const char *)(unsigned int)v17,
            (int)ppvObject);
          v47 = ppvObject;
          if ( ppvObject )
          {
            ppvObject = 0;
            (*(void (__fastcall **)(void *))(*(_QWORD *)v47 + 16LL))(v47);
          }
          v48 = ppstm;
          if ( ppstm )
          {
            ppstm = 0;
            ((void (__fastcall *)(IStream *))v48->lpVtbl->Release)(v48);
          }
          return v4;
        }
        v18 = (unsigned __int16 *)v56;
        do
        {
          v19 = *(unsigned __int16 *)((char *)v18 + (char *)L"country" - v56);
          v20 = *v18 - v19;
          if ( v20 )
            break;
          ++v18;
        }
        while ( v19 );
        if ( !v20 )
        {
          v21 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, _QWORD))(*(_QWORD *)ppvObject + 80LL))(
                  ppvObject,
                  L"GeoID",
                  0);
          v4 = v21;
          if ( v21 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1C4,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\countryhelpers.cpp",
              (const char *)(unsigned int)v21,
              (int)ppvObject);
            v45 = ppvObject;
            if ( ppvObject )
            {
              ppvObject = 0;
              (*(void (__fastcall **)(void *))(*(_QWORD *)v45 + 16LL))(v45);
            }
            v46 = ppstm;
            if ( ppstm )
            {
              ppstm = 0;
              ((void (__fastcall *)(IStream *))v46->lpVtbl->Release)(v46);
            }
            return v4;
          }
          if ( v21 == 1 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1C5,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\countryhelpers.cpp",
              (const char *)0x80070057LL,
              (int)ppvObject);
            v43 = ppvObject;
            if ( ppvObject )
            {
              ppvObject = 0;
              (*(void (__fastcall **)(void *))(*(_QWORD *)v43 + 16LL))(v43);
            }
            v44 = ppstm;
            if ( ppstm )
            {
              ppstm = 0;
              Release = (void (*)(void))v44->lpVtbl->Release;
LABEL_85:
              Release();
            }
            return 2147942487LL;
          }
          v55 = 0;
          v22 = (*(__int64 (__fastcall **)(void *, unsigned __int16 **, _QWORD))(*(_QWORD *)ppvObject + 128LL))(
                  ppvObject,
                  &v55,
                  0);
          v4 = v22;
          if ( v22 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1C8,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\countryhelpers.cpp",
              (const char *)(unsigned int)v22,
              (int)ppvObject);
            v41 = ppvObject;
            if ( ppvObject )
            {
              ppvObject = 0;
              (*(void (__fastcall **)(void *))(*(_QWORD *)v41 + 16LL))(v41);
            }
            v42 = ppstm;
            if ( ppstm )
            {
              ppstm = 0;
              ((void (__fastcall *)(IStream *))v42->lpVtbl->Release)(v42);
            }
            return v4;
          }
          v54 = 0;
          v23 = SafeStringToDword(v55, 10, 1, &v54);
          v4 = v23;
          if ( v23 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1CC,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\countryhelpers.cpp",
              (const char *)(unsigned int)v23,
              (int)ppvObject);
            v39 = ppvObject;
            if ( ppvObject )
            {
              ppvObject = 0;
              (*(void (__fastcall **)(void *))(*(_QWORD *)v39 + 16LL))(v39);
            }
            v40 = ppstm;
            if ( ppstm )
            {
              ppstm = 0;
              ((void (__fastcall *)(IStream *))v40->lpVtbl->Release)(v40);
            }
            return v4;
          }
          if ( v54 == UserGeoID )
          {
            v24 = (*(__int64 (__fastcall **)(void *, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 80LL))(
                    ppvObject,
                    L"mcc",
                    0);
            v4 = v24;
            if ( v24 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1D2,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\countryhelpers.cpp",
                (const char *)(unsigned int)v24,
                (int)ppvObject);
              v37 = ppvObject;
              if ( ppvObject )
              {
                ppvObject = 0;
                (*(void (__fastcall **)(void *))(*(_QWORD *)v37 + 16LL))(v37);
              }
              v38 = ppstm;
              if ( ppstm )
              {
                ppstm = 0;
                ((void (__fastcall *)(IStream *))v38->lpVtbl->Release)(v38);
              }
              return v4;
            }
            if ( v24 == 1 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1D3,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\countryhelpers.cpp",
                (const char *)0x80070057LL,
                (int)ppvObject);
              v34 = ppvObject;
              if ( ppvObject )
              {
                ppvObject = 0;
                (*(void (__fastcall **)(void *))(*(_QWORD *)v34 + 16LL))(v34);
              }
              v35 = ppstm;
              if ( ppstm )
              {
                ppstm = 0;
                Release = (void (*)(void))v35->lpVtbl->Release;
                goto LABEL_85;
              }
              return 2147942487LL;
            }
            v25 = (*(__int64 (__fastcall **)(void *, unsigned __int16 **, _QWORD))(*(_QWORD *)ppvObject + 128LL))(
                    ppvObject,
                    &v55,
                    0);
            v4 = v25;
            if ( v25 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1D4,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\countryhelpers.cpp",
                (const char *)(unsigned int)v25,
                (int)ppvObject);
              v32 = ppvObject;
              if ( ppvObject )
              {
                ppvObject = 0;
                (*(void (__fastcall **)(void *))(*(_QWORD *)v32 + 16LL))(v32);
              }
              v33 = ppstm;
              if ( ppstm )
              {
                ppstm = 0;
                ((void (__fastcall *)(IStream *))v33->lpVtbl->Release)(v33);
              }
              return v4;
            }
            v26 = CoAllocString(v55, a1);
            v4 = v26;
            if ( v26 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1D5,
                (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\countryhelpers.cpp",
                (const char *)(unsigned int)v26,
                (int)ppvObject);
              v30 = ppvObject;
              if ( ppvObject )
              {
                ppvObject = 0;
                (*(void (__fastcall **)(void *))(*(_QWORD *)v30 + 16LL))(v30);
              }
              v31 = ppstm;
              if ( ppstm )
              {
                ppstm = 0;
                ((void (__fastcall *)(IStream *))v31->lpVtbl->Release)(v31);
              }
              return v4;
            }
          }
        }
      }
    }
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E1,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\countryhelpers.cpp",
        (const char *)(unsigned int)v27,
        (int)ppvObject);
      v28 = ppvObject;
      if ( ppvObject )
      {
        ppvObject = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v28 + 16LL))(v28);
      }
      v29 = ppstm;
      if ( ppstm )
      {
        ppstm = 0;
        ((void (__fastcall *)(IStream *))v29->lpVtbl->Release)(v29);
      }
      return v4;
    }
LABEL_97:
    v49 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v49 + 16LL))(v49);
    }
    v50 = ppstm;
    if ( ppstm )
    {
      ppstm = 0;
      ((void (__fastcall *)(IStream *))v50->lpVtbl->Release)(v50);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180007050  mov     [rsp-8+arg_8], rbx
0x180007055  mov     [rsp-8+arg_10], rsi
0x18000705a  push    rbp
0x18000705b  push    rdi
0x18000705c  push    r14
0x18000705e  lea     rbp, [rsp-170h]
0x180007066  sub     rsp, 270h
0x18000706d  mov     rax, cs:__security_cookie
0x180007074  xor     rax, rsp
0x180007077  mov     [rbp+180h+var_20], rax
0x18000707e  mov     rsi, rcx
0x180007081  xor     r14d, r14d
0x180007084  mov     [rcx], r14
0x180007087  lea     ecx, [r14+10h]; GeoClass
0x18000708b  call    cs:__imp_GetUserGeoID
0x180007091  mov     edi, eax
0x180007093  cmp     eax, 0FFFFFFFFh
0x180007096  jnz     short loc_1800070AC
0x180007098  lea     ecx, [rax+0Fh]; GeoClass
0x18000709b  call    cs:__imp_GetUserGeoID
0x1800070a1  mov     edi, eax
0x1800070a3  cmp     eax, 0FFFFFFFFh
0x1800070a6  jz      loc_1800077E7
0x1800070ac  mov     edx, 104h; unsigned int
0x1800070b1  lea     rcx, [rsp+280h+pszFile]; lpFileName
0x1800070b6  call    ?GetMccLookupTablePath@@YAJPEAGK@Z; GetMccLookupTablePath(ushort *,ulong)
0x1800070bb  mov     ebx, eax
0x1800070bd  test    eax, eax
0x1800070bf  jns     short loc_1800070E3
0x1800070c1  mov     rcx, [rbp+188h]; this
0x1800070c8  mov     r9d, eax; char *
0x1800070cb  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800070d2  mov     edx, 1ABh; void *
0x1800070d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800070dc  mov     eax, ebx
0x1800070de  jmp     loc_1800077E9
0x1800070e3  mov     [rsp+280h+ppstm], r14
0x1800070e8  lea     r8, [rsp+280h+ppstm]; ppstm
0x1800070ed  xor     edx, edx; grfMode
0x1800070ef  lea     rcx, [rsp+280h+pszFile]; pszFile
0x1800070f4  call    cs:__imp_SHCreateStreamOnFileW
0x1800070fa  mov     ebx, eax
0x1800070fc  test    eax, eax
0x1800070fe  jns     short loc_18000713A
0x180007100  mov     rcx, [rbp+188h]; this
0x180007107  mov     r9d, eax; char *
0x18000710a  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180007111  mov     edx, 1AEh; void *
0x180007116  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000711b  nop
0x18000711c  mov     rcx, [rsp+280h+ppstm]
0x180007121  test    rcx, rcx
0x180007124  jz      short loc_180007138
0x180007126  mov     [rsp+280h+ppstm], r14
0x18000712b  mov     rax, [rcx]
0x18000712e  mov     rax, [rax+10h]
0x180007132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007137  nop
0x180007138  jmp     short loc_1800070DC
0x18000713a  mov     [rsp+280h+ppvObject], r14; int
0x18000713f  xor     r8d, r8d; pMalloc
0x180007142  lea     rdx, [rsp+280h+ppvObject]; ppvObject
0x180007147  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18000714e  call    cs:__imp_CreateXmlReader
0x180007154  mov     ebx, eax
0x180007156  test    eax, eax
0x180007158  jns     short loc_1800071B3
0x18000715a  mov     rcx, [rbp+188h]; this
0x180007161  mov     r9d, eax; char *
0x180007164  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000716b  mov     edx, 1B1h; void *
0x180007170  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007175  nop
0x180007176  mov     rcx, [rsp+280h+ppvObject]
0x18000717b  test    rcx, rcx
0x18000717e  jz      short loc_180007192
0x180007180  mov     [rsp+280h+ppvObject], r14
0x180007185  mov     rax, [rcx]
0x180007188  mov     rax, [rax+10h]
0x18000718c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007191  nop
0x180007192  mov     rcx, [rsp+280h+ppstm]
0x180007197  test    rcx, rcx
0x18000719a  jz      short loc_1800071AE
0x18000719c  mov     [rsp+280h+ppstm], r14
0x1800071a1  mov     rax, [rcx]
0x1800071a4  mov     rax, [rax+10h]
0x1800071a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071ad  nop
0x1800071ae  jmp     loc_1800070DC
0x1800071b3  mov     rcx, [rsp+280h+ppvObject]
0x1800071b8  mov     rax, [rcx]
0x1800071bb  xor     r8d, r8d
0x1800071be  lea     edx, [r8+4]
0x1800071c2  mov     rax, [rax+28h]
0x1800071c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071cb  mov     ebx, eax
0x1800071cd  test    eax, eax
0x1800071cf  jns     short loc_18000722A
0x1800071d1  mov     rcx, [rbp+188h]; this
0x1800071d8  mov     r9d, eax; char *
0x1800071db  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800071e2  mov     edx, 1B2h; void *
0x1800071e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800071ec  nop
0x1800071ed  mov     rcx, [rsp+280h+ppvObject]
0x1800071f2  test    rcx, rcx
0x1800071f5  jz      short loc_180007209
0x1800071f7  mov     [rsp+280h+ppvObject], r14
0x1800071fc  mov     rax, [rcx]
0x1800071ff  mov     rax, [rax+10h]
0x180007203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007208  nop
0x180007209  mov     rcx, [rsp+280h+ppstm]
0x18000720e  test    rcx, rcx
0x180007211  jz      short loc_180007225
0x180007213  mov     [rsp+280h+ppstm], r14
0x180007218  mov     rax, [rcx]
0x18000721b  mov     rax, [rax+10h]
0x18000721f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007224  nop
0x180007225  jmp     loc_1800070DC
0x18000722a  mov     rcx, [rsp+280h+ppvObject]
0x18000722f  mov     rax, [rcx]
0x180007232  mov     rdx, [rsp+280h+ppstm]
0x180007237  mov     rax, [rax+18h]
0x18000723b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007240  mov     ebx, eax
0x180007242  test    eax, eax
0x180007244  jns     short loc_18000729F
0x180007246  mov     rcx, [rbp+188h]; this
0x18000724d  mov     r9d, eax; char *
0x180007250  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180007257  mov     edx, 1B3h; void *
0x18000725c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007261  nop
0x180007262  mov     rcx, [rsp+280h+ppvObject]
0x180007267  test    rcx, rcx
0x18000726a  jz      short loc_18000727E
0x18000726c  mov     [rsp+280h+ppvObject], r14
0x180007271  mov     rax, [rcx]
0x180007274  mov     rax, [rax+10h]
0x180007278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000727d  nop
0x18000727e  mov     rcx, [rsp+280h+ppstm]
0x180007283  test    rcx, rcx
0x180007286  jz      short loc_18000729A
0x180007288  mov     [rsp+280h+ppstm], r14
0x18000728d  mov     rax, [rcx]
0x180007290  mov     rax, [rax+10h]
0x180007294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007299  nop
0x18000729a  jmp     loc_1800070DC
0x18000729f  mov     [rsp+280h+var_240], r14
0x1800072a4  mov     [rsp+280h+var_250], r14d
0x1800072a9  jmp     loc_180007404
0x1800072ae  cmp     [rsi], r14
0x1800072b1  jnz     loc_1800077AF
0x1800072b7  cmp     [rsp+280h+var_250], 1
0x1800072bc  jnz     loc_180007404
0x1800072c2  mov     rcx, [rsp+280h+ppvObject]
0x1800072c7  mov     rax, [rcx]
0x1800072ca  xor     r8d, r8d
0x1800072cd  lea     rdx, [rsp+280h+var_240]
0x1800072d2  mov     rax, [rax+70h]
0x1800072d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072db  mov     ebx, eax
0x1800072dd  test    eax, eax
0x1800072df  js      loc_180007756
0x1800072e5  mov     rax, [rsp+280h+var_240]
0x1800072ea  lea     rcx, ?gc_wszCountry@@3QBGB; "country"
0x1800072f1  sub     rcx, rax
0x1800072f4  movzx   edx, word ptr [rax]
0x1800072f7  movzx   r8d, word ptr [rax+rcx]
0x1800072fc  sub     edx, r8d
0x1800072ff  jnz     short loc_18000730A
0x180007301  add     rax, 2
0x180007305  test    r8d, r8d
0x180007308  jnz     short loc_1800072F4
0x18000730a  test    edx, edx
0x18000730c  jnz     loc_180007404
0x180007312  mov     rcx, [rsp+280h+ppvObject]
0x180007317  mov     rax, [rcx]
0x18000731a  xor     r8d, r8d
0x18000731d  lea     rdx, ?gc_wszGeoID@@3QBGB; "GeoID"
0x180007324  mov     rax, [rax+50h]
0x180007328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000732d  mov     ebx, eax
0x18000732f  test    eax, eax
0x180007331  js      loc_1800076FD
0x180007337  cmp     eax, 1
0x18000733a  jz      loc_18000769C
0x180007340  mov     [rsp+280h+var_248], r14
0x180007345  mov     rcx, [rsp+280h+ppvObject]
0x18000734a  mov     rax, [rcx]
0x18000734d  xor     r8d, r8d
0x180007350  lea     rdx, [rsp+280h+var_248]
0x180007355  mov     rax, [rax+80h]
0x18000735c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007361  mov     ebx, eax
0x180007363  test    eax, eax
0x180007365  js      loc_180007643
0x18000736b  mov     [rsp+280h+var_24C], r14d
0x180007370  lea     r9, [rsp+280h+var_24C]
0x180007375  mov     edx, 0Ah
0x18000737a  lea     r8d, [rdx-9]
0x18000737e  mov     rcx, [rsp+280h+var_248]
0x180007383  call    cs:__imp_?SafeStringToDword@@YAJPEBGHHPEAK@Z; SafeStringToDword(ushort const *,int,int,ulong *)
0x180007389  mov     ebx, eax
0x18000738b  test    eax, eax
0x18000738d  js      loc_1800075EA
0x180007393  cmp     [rsp+280h+var_24C], edi
0x180007397  jnz     short loc_180007404
0x180007399  mov     rcx, [rsp+280h+ppvObject]
0x18000739e  mov     rax, [rcx]
0x1800073a1  xor     r8d, r8d
0x1800073a4  lea     rdx, ?gc_wszMCC@@3QBGB; "mcc"
0x1800073ab  mov     rax, [rax+50h]
0x1800073af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073b4  mov     ebx, eax
0x1800073b6  test    eax, eax
0x1800073b8  js      loc_180007591
0x1800073be  cmp     eax, 1
0x1800073c1  jz      loc_180007537
0x1800073c7  mov     rcx, [rsp+280h+ppvObject]
0x1800073cc  mov     rax, [rcx]
0x1800073cf  xor     r8d, r8d
0x1800073d2  lea     rdx, [rsp+280h+var_248]
0x1800073d7  mov     rax, [rax+80h]
0x1800073de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073e3  mov     ebx, eax
0x1800073e5  test    eax, eax
0x1800073e7  js      loc_1800074DE
0x1800073ed  mov     rdx, rsi; unsigned __int16 **
0x1800073f0  mov     rcx, [rsp+280h+var_248]; unsigned __int16 *
0x1800073f5  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x1800073fa  mov     ebx, eax
0x1800073fc  test    eax, eax
0x1800073fe  js      loc_180007485
0x180007404  mov     rcx, [rsp+280h+ppvObject]
0x180007409  mov     rax, [rcx]
0x18000740c  lea     rdx, [rsp+280h+var_250]
0x180007411  mov     rax, [rax+30h]
0x180007415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000741a  test    eax, eax
0x18000741c  mov     ebx, eax
0x18000741e  jz      loc_1800072AE
0x180007424  test    eax, eax
0x180007426  jns     loc_1800077AF
0x18000742c  mov     rcx, [rbp+188h]; this
0x180007433  mov     r9d, eax; char *
0x180007436  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000743d  mov     edx, 1E1h; void *
0x180007442  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007447  nop
0x180007448  mov     rcx, [rsp+280h+ppvObject]
0x18000744d  test    rcx, rcx
0x180007450  jz      short loc_180007464
0x180007452  mov     [rsp+280h+ppvObject], r14
0x180007457  mov     rax, [rcx]
0x18000745a  mov     rax, [rax+10h]
0x18000745e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007463  nop
0x180007464  mov     rcx, [rsp+280h+ppstm]
0x180007469  test    rcx, rcx
0x18000746c  jz      short loc_180007480
0x18000746e  mov     [rsp+280h+ppstm], r14
0x180007473  mov     rax, [rcx]
0x180007476  mov     rax, [rax+10h]
0x18000747a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000747f  nop
0x180007480  jmp     loc_1800070DC
0x180007485  mov     rcx, [rbp+188h]; this
0x18000748c  mov     r9d, ebx; char *
0x18000748f  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180007496  mov     edx, 1D5h; void *
0x18000749b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800074a0  nop
0x1800074a1  mov     rcx, [rsp+280h+ppvObject]
0x1800074a6  test    rcx, rcx
0x1800074a9  jz      short loc_1800074BD
0x1800074ab  mov     [rsp+280h+ppvObject], r14
0x1800074b0  mov     rax, [rcx]
0x1800074b3  mov     rax, [rax+10h]
0x1800074b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074bc  nop
0x1800074bd  mov     rcx, [rsp+280h+ppstm]
0x1800074c2  test    rcx, rcx
0x1800074c5  jz      short loc_1800074D9
0x1800074c7  mov     [rsp+280h+ppstm], r14
0x1800074cc  mov     rax, [rcx]
0x1800074cf  mov     rax, [rax+10h]
0x1800074d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074d8  nop
0x1800074d9  jmp     loc_1800070DC
0x1800074de  mov     rcx, [rbp+188h]; this
0x1800074e5  mov     r9d, ebx; char *
0x1800074e8  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800074ef  mov     edx, 1D4h; void *
0x1800074f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
