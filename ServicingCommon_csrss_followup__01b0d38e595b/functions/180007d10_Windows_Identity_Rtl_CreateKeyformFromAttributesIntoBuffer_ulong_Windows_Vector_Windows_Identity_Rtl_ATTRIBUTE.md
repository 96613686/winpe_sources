# Windows::Identity::Rtl::CreateKeyformFromAttributesIntoBuffer(ulong,Windows::Vector<Windows::Identity::Rtl::_ATTRIBUTE const> const &,unsigned __int64,_LUNICODE_STRING *)

- ea: `0x180007d10`
- end: `0x180008a0c`
- name: `?CreateKeyformFromAttributesIntoBuffer@Rtl@Identity@Windows@@YAJKAEBU?$Vector@$$CBU_ATTRIBUTE@Rtl@Identity@Windows@@@3@_KPEAU_LUNICODE_STRING@@@Z`
- size: `3324`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180006c10`
- `0x180006fc4`
- `0x180007d10`
- `0x180008a20`
- `0x180009430`
- `0x180009820`
- `0x1800098bc`
- `0x1800098f0`
- `0x18000bcd0`
- `0x18001f1d8`
- `0x18001f840`
- `0x180026e00`
- `0x18002d2b0`
- `0x1800981e0`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x180007d77`
- `ntdll!RtlRaiseStatus` at `0x180008951`
- `ntdll!RtlRaiseStatus` at `0x180007d77`
- `ntdll!RtlRaiseStatus` at `0x180008951`

## string_xrefs

- `0x180008255`: `Windows::Identity::Rtl::CreateKeyformFromAttributesIntoBuffer`
- `0x1800082a8`: `Windows::Identity::Rtl::CreateKeyformFromAttributesIntoBuffer`
- `0x180008345`: `Windows::Identity::Rtl::CreateKeyformFromAttributesIntoBuffer`
- `0x1800088e3`: `Windows::Identity::Rtl::CreateKeyformFromAttributesIntoBuffer`
- `0x18000835c`: `TempAttributeList.Allocate(AttributeListIn.Length)`

## pseudocode

```c
__int64 __fastcall Windows::Identity::Rtl::CreateKeyformFromAttributesIntoBuffer(
        int a1,
        __int128 *a2,
        char *a3,
        unsigned __int64 *a4)
{
  unsigned __int64 v4; // r10
  char v6; // r15
  char *v7; // r14
  unsigned __int64 v8; // rdi
  char *v9; // rcx
  int v10; // r15d
  __int64 *v11; // rax
  unsigned __int64 v12; // r12
  __int64 v13; // rdx
  char *v14; // r13
  unsigned __int64 j; // rbx
  __int64 *v16; // r8
  _QWORD *v17; // rcx
  unsigned __int64 v18; // r13
  unsigned __int64 v19; // rbx
  unsigned __int8 v20; // r8
  unsigned __int64 v21; // rdi
  unsigned int v22; // r11d
  __int64 v23; // rcx
  __int64 v24; // r10
  size_t *v25; // rax
  size_t v26; // rsi
  size_t v27; // rcx
  const void *v28; // rdx
  int v29; // ebx
  char *v30; // rcx
  __int64 v31; // r9
  unsigned __int64 v32; // r8
  __int16 v33; // dx
  unsigned __int64 v34; // rax
  __int64 v35; // rsi
  unsigned __int64 v36; // r11
  unsigned __int64 v37; // r9
  char *v38; // rbx
  __int16 v39; // dx
  unsigned int v40; // r8d
  _WORD *v41; // rbx
  __int16 v42; // r8
  unsigned int v43; // edx
  _WORD *v44; // rbx
  __int16 v45; // r8
  unsigned int v46; // edx
  _WORD *v47; // rbx
  unsigned int v48; // eax
  const struct std::nothrow_t *v49; // rdx
  int v51; // eax
  unsigned __int64 v52; // rsi
  __int64 Elements; // rax
  unsigned __int64 i; // rdx
  __int64 v55; // rax
  __int64 v56; // rcx
  __int64 v57; // xmm1_8
  const char *v58; // rax
  int v59; // esi
  const struct std::nothrow_t *v60; // rdx
  char *v61; // rcx
  __int64 v62; // r9
  unsigned __int64 v63; // r8
  unsigned __int64 v64; // rax
  char *v65; // r8
  __int64 v66; // r8
  int v67; // eax
  int v68; // eax
  int v69; // esi
  unsigned int v70; // r12d
  unsigned int v71; // edi
  const char *v72; // rax
  char v73; // [rsp+30h] [rbp-D0h]
  char v74; // [rsp+31h] [rbp-CFh]
  const char *v75; // [rsp+38h] [rbp-C8h] BYREF
  const char *v76; // [rsp+40h] [rbp-C0h]
  __int64 v77; // [rsp+48h] [rbp-B8h]
  const char *v78; // [rsp+50h] [rbp-B0h]
  __int128 v79; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v80; // [rsp+68h] [rbp-98h]
  const char *v81; // [rsp+70h] [rbp-90h]
  __int64 v82; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v83; // [rsp+80h] [rbp-80h]
  __int128 v84; // [rsp+88h] [rbp-78h] BYREF
  __int64 v85; // [rsp+98h] [rbp-68h]
  const char *v86; // [rsp+A0h] [rbp-60h]
  char *v87; // [rsp+A8h] [rbp-58h]
  unsigned __int64 *v88; // [rsp+B0h] [rbp-50h]
  int v89; // [rsp+B8h] [rbp-48h] BYREF
  char *v90; // [rsp+C0h] [rbp-40h] BYREF
  int v91; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v92[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 *v93; // [rsp+E0h] [rbp-20h]
  __int64 *v94; // [rsp+E8h] [rbp-18h]
  _QWORD v95[5]; // [rsp+F0h] [rbp-10h]
  __int64 *v96; // [rsp+118h] [rbp+18h]
  __int64 v97; // [rsp+120h] [rbp+20h]
  __int64 *v98; // [rsp+128h] [rbp+28h]
  __int64 *v99; // [rsp+130h] [rbp+30h]
  __int64 v100; // [rsp+138h] [rbp+38h]
  __int64 *v101; // [rsp+140h] [rbp+40h]
  __int64 *v102; // [rsp+148h] [rbp+48h]
  __int64 v103; // [rsp+150h] [rbp+50h]
  __int64 *v104; // [rsp+158h] [rbp+58h]
  __int64 *v105; // [rsp+160h] [rbp+60h]
  __int64 v106; // [rsp+168h] [rbp+68h]

  v4 = 0;
  v88 = a4;
  v87 = a3;
  v91 = 0;
  v6 = a1;
  v84 = 0u;
  v7 = 0;
  v8 = 0;
  v82 = 0;
  v83 = 0;
  if ( (a1 & 0xFFFFFFF0) != 0 )
LABEL_2:
    RtlRaiseStatus(-1073741595);
  *a4 = 0;
  v80 = a4[2];
  v79 = *(_OWORD *)a4;
  if ( (a1 & 2) != 0 )
  {
    v8 = *((_QWORD *)a2 + 1);
    v84 = *a2;
    v9 = (char *)v84;
  }
  else
  {
    v52 = *((_QWORD *)a2 + 1);
    if ( v52 )
    {
      Elements = Windows::VectorTraits<Windows::Identity::Rtl::_ATTRIBUTE>::AllocateElements(*((_QWORD *)a2 + 1));
      if ( !Elements )
      {
        v80 = 321;
        *(_QWORD *)&v79 = "onecore\\base\\wcp\\identity\\id_keyform_lib.cpp";
        *((_QWORD *)&v79 + 1) = "Windows::Identity::Rtl::CreateKeyformFromAttributesIntoBuffer";
        v81 = "TempAttributeList.Allocate(AttributeListIn.Length)";
        RtlReportErrorOrigination(&v79, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225495LL);
        return 3221225495LL;
      }
      v7 = (char *)Elements;
      v82 = Elements;
      v8 = v52;
      v83 = v52;
    }
    for ( i = 0; i < *((_QWORD *)a2 + 1); *(_QWORD *)&v7[v56 + 16] = v57 )
    {
      v55 = 3 * i++;
      v56 = 8 * v55;
      v57 = *(_QWORD *)(8 * v55 + *(_QWORD *)a2 + 16);
      *(_OWORD *)&v7[v56] = *(_OWORD *)(8 * v55 + *(_QWORD *)a2);
    }
    BUCL::Implementation::QuickSort<BUCL::Rtl::CCallDisposition,unsigned __int64,Windows::Identity::Rtl::_ATTRIBUTE,BUCL::Implementation::ComparisonResultKind<BUCL::Rtl::CCallDisposition> (*)(Windows::Identity::Rtl::_ATTRIBUTE const &,Windows::Identity::Rtl::_ATTRIBUTE const &)>(
      &v89,
      v7,
      0xAAAAAAAAAAAAAAABuLL * ((__int64)(24 * v8) >> 3));
    v29 = v89;
    if ( v89 < 0 )
      goto LABEL_86;
    v9 = v7;
    *((_QWORD *)&v84 + 1) = v8;
    *(_QWORD *)&v84 = v7;
    v4 = 0;
  }
  v90 = v9;
  v74 = v6 & 1;
  if ( (v6 & 4) == 0 )
  {
    *(_QWORD *)v92 = 0;
    v90 = 0;
    v29 = Windows::Identity::Rtl::GeneratePsuedokeyFromAttributes(v9, &v84, v92, &v90);
    if ( v29 < 0 )
    {
      if ( v7 )
        operator delete(v7, v60);
      return (unsigned int)v29;
    }
    v65 = v90;
    if ( v74 )
      v65 = *(char **)v92;
    v4 = 0;
    v8 = *((_QWORD *)&v84 + 1);
    v9 = (char *)v84;
    v87 = v65;
    v90 = (char *)v84;
  }
  v95[0] = 16;
  v10 = v6 & 8;
  v95[2] = 0;
  v11 = g_LUNICODE_STRING__star_;
  v95[3] = 16;
  if ( !v10 )
    v11 = g_LUNICODE_STRING_none;
  v97 = 40;
  v94 = v11;
  v93 = g_LUNICODE_STRING_processorArchitecture;
  v12 = 0;
  v96 = v11;
  v95[1] = g_LUNICODE_STRING_typeName;
  v95[4] = g_LUNICODE_STRING_name;
  v98 = g_LUNICODE_STRING_publicKeyToken;
  v101 = g_LUNICODE_STRING_version;
  v104 = g_LUNICODE_STRING_culture;
  v13 = (__int64)RtlDowncaseUCSCharacter;
  v99 = v11;
  v100 = 0;
  v102 = v11;
  v103 = 0;
  v105 = v11;
  v106 = 8;
  while ( v12 < v8 )
  {
    v89 = 0;
    v14 = &v9[24 * v12];
    if ( *(_QWORD *)v14 && **(_QWORD **)v14 )
      goto LABEL_18;
    for ( j = 0; ; ++j )
    {
      if ( j >= 6 )
        goto LABEL_17;
      if ( !BYTE4(v95[3 * j]) )
      {
        v16 = (&v93)[3 * j];
        v17 = (_QWORD *)*((_QWORD *)v14 + 1);
        if ( *v17 == *v16 )
        {
          v92[0] = RtlCompareEncodedLBlobs(
                     v17,
                     (__int64 (__fastcall *)(const char **, __int64, __int64))RtlDecodeUtf16LE,
                     v16,
                     (__int64 (__fastcall *)(const char **, __int64, __int64))RtlDecodeUtf16LE,
                     (__int64 (__fastcall *)(_QWORD))RtlDowncaseUCSCharacter,
                     &v89);
          if ( (v92[0] & 0x80000000) != 0 )
          {
            Windows::Auto<Windows::Vector<_LUNICODE_STRING const *>>::~Auto<Windows::Vector<_LUNICODE_STRING const *>>(&v82);
            return v92[0];
          }
          v13 = (__int64)RtlDowncaseUCSCharacter;
          if ( !v89 )
            break;
        }
      }
    }
    v95[3 * j - 1] = *((_QWORD *)v14 + 2);
    BYTE4(v95[3 * j]) = 1;
LABEL_17:
    v9 = v90;
    v4 = 0;
LABEL_18:
    ++v12;
  }
  if ( !v96 )
  {
    v80 = 419;
    *(_QWORD *)&v79 = "onecore\\base\\wcp\\identity\\id_keyform_lib.cpp";
    *((_QWORD *)&v79 + 1) = "Windows::Identity::Rtl::CreateKeyformFromAttributesIntoBuffer";
    v81 = "AttrsToFind[IdIdxName].FoundValue != 0";
    v51 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
            &v91,
            &v79);
    goto LABEL_85;
  }
  v18 = *((_QWORD *)&v79 + 1);
  v19 = v79;
  v20 = 1;
  LODWORD(v90) = 10240;
  v73 = 1;
  v21 = 0;
  v22 = -1073741471;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( v21 >= 6 )
      {
        v35 = v80;
        if ( !v19 )
          goto LABEL_60;
        LODWORD(v90) = 95;
        v89 = 0;
        if ( (v19 & 1) != 0 || (v18 & 1) != 0 || v19 > v18 || !v80 )
        {
          v75 = "onecore\\base\\lstring\\lunicode_string.cpp";
          v76 = "RtlAppendUcsCharactersToLUnicodeString";
          v77 = 1293;
          v78 = "::RtlIsLUnicodeStringValid(StringInOut)";
          v68 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
                  &v89,
                  &v75);
          goto LABEL_151;
        }
        v61 = (char *)(v80 + v19);
        v62 = 0;
        v63 = v80 + v18;
        while ( 1 )
        {
          if ( (unsigned __int64)v61 > v63 || v62 )
          {
            v19 = (unsigned __int64)&v61[-v35];
            *(_QWORD *)&v79 = &v61[-v35];
            goto LABEL_126;
          }
          v13 = (unsigned int)v90;
          v64 = v63 - (_QWORD)v61;
          if ( (unsigned int)v90 >= 0x10000 )
          {
            if ( (unsigned int)v90 >= 0x110000 )
              goto LABEL_138;
            if ( v64 < 4 )
            {
LABEL_137:
              v22 = -1073741789;
LABEL_138:
              v77 = 1300;
              v75 = "onecore\\base\\lstring\\lunicode_string.cpp";
              v78 = "__rv.NewCursorValue != 0";
              v76 = "RtlAppendUcsCharactersToLUnicodeString";
              v68 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                      &v89,
                      &v75,
                      v22);
LABEL_151:
              v71 = v68;
              if ( v68 < 0 )
              {
                Windows::Auto<Windows::Vector<_LUNICODE_STRING const *>>::~Auto<Windows::Vector<_LUNICODE_STRING const *>>(&v82);
                return v71;
              }
              v4 = 0;
LABEL_126:
              v20 = v73;
LABEL_60:
              if ( !v10 || v20 )
              {
                v36 = (unsigned __int64)v87;
                v37 = v35 + v18;
                v38 = (char *)(v35 + v19);
                while ( v4 < 4 )
                {
                  v39 = 87;
                  v40 = (unsigned int)HIWORD(v36) >> 12;
                  if ( v40 < 0xA )
                    v39 = 48;
                  if ( v37 - (unsigned __int64)v38 < 2 )
                  {
                    v77 = 482;
                    v75 = "onecore\\base\\wcp\\identity\\id_keyform_lib.cpp";
                    v78 = "__rv.NewCursorValue != 0";
                    v76 = "Windows::Identity::Rtl::CreateKeyformFromAttributesIntoBuffer";
                    RtlReportErrorOrigination(&v75, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225507LL);
                    if ( v7 )
                      operator delete(v7, v49);
                    return 3221225507LL;
                  }
                  *(_WORD *)v38 = v40 + v39;
                  v41 = v38 + 2;
                  if ( !v41 )
                    goto LABEL_2;
                  v42 = 87;
                  v43 = ((unsigned int)HIWORD(v36) >> 8) & 0xF;
                  if ( v43 < 0xA )
                    v42 = 48;
                  if ( v37 - (unsigned __int64)v41 < 2 )
                  {
                    v77 = 483;
LABEL_84:
                    v78 = "__rv.NewCursorValue != 0";
                    v75 = "onecore\\base\\wcp\\identity\\id_keyform_lib.cpp";
                    v76 = "Windows::Identity::Rtl::CreateKeyformFromAttributesIntoBuffer";
                    v51 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                            &v91,
                            &v75,
                            3221225507LL);
LABEL_85:
                    v29 = v51;
LABEL_86:
                    Windows::Auto<Windows::Vector<_LUNICODE_STRING const *>>::~Auto<Windows::Vector<_LUNICODE_STRING const *>>(&v82);
                    return (unsigned int)v29;
                  }
                  *v41 = v43 + v42;
                  v44 = v41 + 1;
                  if ( !v44 )
                    goto LABEL_2;
                  v45 = 87;
                  v46 = BYTE6(v36) >> 4;
                  if ( v46 < 0xA )
                    v45 = 48;
                  if ( v37 - (unsigned __int64)v44 < 2 )
                  {
                    v77 = 484;
                    goto LABEL_84;
                  }
                  *v44 = v46 + v45;
                  v47 = v44 + 1;
                  if ( !v47 )
                    goto LABEL_2;
                  v48 = BYTE6(v36) & 0xF;
                  v13 = 87;
                  if ( v48 < 0xA )
                    v13 = 48;
                  if ( v37 - (unsigned __int64)v47 < 2 )
                  {
                    v77 = 485;
                    goto LABEL_84;
                  }
                  LOWORD(v13) = v48 + v13;
                  *v47 = v13;
                  v38 = (char *)(v47 + 1);
                  if ( !v38 )
                    goto LABEL_2;
                  v36 <<= 16;
                  ++v4;
                }
                v19 = (unsigned __int64)&v38[-v35];
LABEL_140:
                *v88 = v19;
                if ( v7 )
                  operator delete(v7, (const struct std::nothrow_t *)v13);
                return 0;
              }
              LODWORD(v90) = 0;
              if ( (unsigned __int8)RtlIsLUnicodeStringValid(&v79) )
              {
                if ( (unsigned __int8)RtlIsLUnicodeStringValid(g_LUNICODE_STRING__star_) )
                {
                  if ( v18 - v19 >= 2 )
                  {
                    v13 = v19 >> 1;
                    v19 += 2LL;
                    *(_WORD *)(v35 + 2 * v13) = g_RGWCH__star_[0];
                    goto LABEL_140;
                  }
                  v77 = 686;
                  v75 = "onecore\\base\\lstring\\lunicode_string.cpp";
                  v78 = 0;
                  v76 = "RtlAppendLUnicodeStringToLUnicodeString";
                  v69 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                          &v90,
                          &v75,
                          2147483653LL);
                  if ( v69 >= 0 )
                    goto LABEL_140;
LABEL_172:
                  Windows::Auto<Windows::Vector<_LUNICODE_STRING const *>>::~Auto<Windows::Vector<_LUNICODE_STRING const *>>(&v82);
                  return (unsigned int)v69;
                }
                v77 = 678;
                v75 = "onecore\\base\\lstring\\lunicode_string.cpp";
                v76 = "RtlAppendLUnicodeStringToLUnicodeString";
                v72 = "::RtlIsLUnicodeStringValid(Source)";
              }
              else
              {
                v77 = 676;
                v75 = "onecore\\base\\lstring\\lunicode_string.cpp";
                v76 = "RtlAppendLUnicodeStringToLUnicodeString";
                v72 = "::RtlIsLUnicodeStringValid(Destination)";
              }
              v78 = v72;
              RtlReportErrorOrigination(&v75, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
              v69 = -1073741811;
              goto LABEL_172;
            }
            *(_WORD *)v61 = ((unsigned int)((_DWORD)v90 - 0x10000) >> 10) - 10240;
            v61 += 2;
            LOWORD(v13) = (v13 & 0x3FF) - 9216;
          }
          else
          {
            if ( v64 < 2 )
              goto LABEL_137;
            if ( (unsigned int)((_DWORD)v90 - 56320) <= 0x3FF )
              goto LABEL_138;
          }
          *(_WORD *)v61 = v13;
          v61 += 2;
          if ( !v61 )
LABEL_167:
            RtlRaiseStatus(-1073741595);
          v62 = 1;
        }
      }
      v23 = 0;
      v13 = BYTE4(v95[3 * v21]);
      if ( (_BYTE)v13 )
        v23 = v20;
      v73 = v23;
      v20 = v23;
      if ( v21 != 4 )
        break;
      if ( !v74 )
        goto LABEL_27;
      v21 = 5;
    }
    if ( v21 == 1 && !(_BYTE)v13 )
      goto LABEL_45;
LABEL_27:
    if ( !LODWORD(v95[3 * v21]) || !(_BYTE)v13 )
      break;
    v29 = anonymous_namespace_::FilterIdentityStringWhileAppending(v23, v95[3 * v21 - 1], &v79, LODWORD(v95[3 * v21]));
    if ( v29 < 0 )
      goto LABEL_86;
    v18 = *((_QWORD *)&v79 + 1);
    v19 = v79;
LABEL_44:
    v20 = v73;
    v22 = -1073741471;
    v4 = 0;
LABEL_45:
    ++v21;
  }
  if ( !v19 )
  {
    v24 = v80;
    goto LABEL_30;
  }
  v92[0] = 95;
  v89 = 0;
  if ( (v19 & 1) != 0 || (v18 & 1) != 0 || v19 > v18 || (v24 = v80) == 0 )
  {
    v75 = "onecore\\base\\lstring\\lunicode_string.cpp";
    v76 = "RtlAppendUcsCharactersToLUnicodeString";
    v77 = 1293;
    v78 = "::RtlIsLUnicodeStringValid(StringInOut)";
    v67 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
            &v89,
            &v75);
    goto LABEL_148;
  }
  v30 = (char *)(v80 + v19);
  v31 = 0;
  v32 = v80 + v18;
  while ( 2 )
  {
    if ( (unsigned __int64)v30 > v32 || v31 )
    {
      v19 = (unsigned __int64)&v30[-v24];
      *(_QWORD *)&v79 = &v30[-v24];
      goto LABEL_30;
    }
    v33 = v92[0];
    v34 = v32 - (_QWORD)v30;
    if ( v92[0] >= 0x10000 )
    {
      if ( v92[0] >= 0x110000 )
        break;
      if ( v34 < 4 )
      {
LABEL_130:
        v66 = 3221225507LL;
        goto LABEL_131;
      }
      *(_WORD *)v30 = ((v92[0] - 0x10000) >> 10) - (_WORD)v90;
      v30 += 2;
      v33 = (v33 & 0x3FF) - 9216;
      goto LABEL_56;
    }
    if ( v34 < 2 )
      goto LABEL_130;
    if ( v92[0] - 56320 > 0x3FF )
    {
LABEL_56:
      *(_WORD *)v30 = v33;
      v30 += 2;
      if ( !v30 )
        goto LABEL_167;
      v31 = 1;
      continue;
    }
    break;
  }
  v66 = 3221225825LL;
LABEL_131:
  v85 = 1300;
  *(_QWORD *)&v84 = "onecore\\base\\lstring\\lunicode_string.cpp";
  v86 = "__rv.NewCursorValue != 0";
  *((_QWORD *)&v84 + 1) = "RtlAppendUcsCharactersToLUnicodeString";
  v67 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
          &v89,
          &v84,
          v66);
LABEL_148:
  v70 = v67;
  if ( v67 < 0 )
  {
    Windows::Auto<Windows::Vector<_LUNICODE_STRING const *>>::~Auto<Windows::Vector<_LUNICODE_STRING const *>>(&v82);
    return v70;
  }
  v24 = v80;
LABEL_30:
  v92[0] = 0;
  if ( (v19 & 1) != 0 || (v18 & 1) != 0 || v19 > v18 || !v24 && v19 )
  {
    v77 = 676;
    v76 = "RtlAppendLUnicodeStringToLUnicodeString";
    v58 = "::RtlIsLUnicodeStringValid(Destination)";
    goto LABEL_100;
  }
  v25 = (size_t *)v95[3 * v21 - 1];
  if ( !v25 )
  {
    v77 = 677;
    v76 = "RtlAppendLUnicodeStringToLUnicodeString";
    v58 = "Not-null check failed: Source";
    goto LABEL_100;
  }
  v26 = *v25;
  if ( (*v25 & 1) == 0 )
  {
    v27 = v25[1];
    if ( (v27 & 1) == 0 && v26 <= v27 )
    {
      v28 = (const void *)v25[2];
      if ( v28 || !v26 )
      {
        if ( v18 - v19 < v26 )
        {
          *(_QWORD *)&v84 = "onecore\\base\\lstring\\lunicode_string.cpp";
          *((_QWORD *)&v84 + 1) = "RtlAppendLUnicodeStringToLUnicodeString";
          v85 = 686;
          v86 = 0;
          v59 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                  v92,
                  &v84,
                  2147483653LL);
          if ( v59 < 0 )
            goto LABEL_101;
        }
        else
        {
          memmove((void *)(v24 + 2 * (v19 >> 1)), v28, v26);
          v19 += v26;
          *(_QWORD *)&v79 = v19;
        }
        goto LABEL_44;
      }
    }
  }
  v77 = 678;
  v76 = "RtlAppendLUnicodeStringToLUnicodeString";
  v58 = "::RtlIsLUnicodeStringValid(Source)";
LABEL_100:
  v75 = "onecore\\base\\lstring\\lunicode_string.cpp";
  v78 = v58;
  RtlReportErrorOrigination(&v75, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
  v59 = -1073741811;
LABEL_101:
  if ( v7 )
    operator delete(v7, (const struct std::nothrow_t *)v13);
  return (unsigned int)v59;
}

```

## disassembly

```asm
0x180007d10  mov     [rsp-8+arg_0], rbx
0x180007d15  push    rbp
0x180007d16  push    rsi
0x180007d17  push    rdi
0x180007d18  push    r12
0x180007d1a  push    r13
0x180007d1c  push    r14
0x180007d1e  push    r15
0x180007d20  lea     rbp, [rsp-80h]
0x180007d25  sub     rsp, 180h
0x180007d2c  mov     rax, cs:__security_cookie
0x180007d33  xor     rax, rsp
0x180007d36  mov     [rbp+0B0h+var_40], rax
0x180007d3a  xor     r10d, r10d
0x180007d3d  mov     [rbp+0B0h+var_100], r9
0x180007d41  mov     [rbp+0B0h+var_108], r8
0x180007d45  mov     rbx, rdx
0x180007d48  mov     [rbp+0B0h+var_E8], r10d
0x180007d4c  mov     r15d, ecx
0x180007d4f  mov     qword ptr [rbp+0B0h+var_128], r10
0x180007d53  mov     r14d, r10d
0x180007d56  mov     qword ptr [rbp+0B0h+var_128+8], r10
0x180007d5a  mov     edi, r10d
0x180007d5d  mov     [rsp+1B0h+var_138], r10
0x180007d62  mov     [rbp+0B0h+var_130], r10
0x180007d66  test    ecx, 0FFFFFFF0h
0x180007d6c  jz      loc_1800082D6
0x180007d72  mov     ecx, 0C00000E5h; Status
0x180007d77  call    cs:__imp_RtlRaiseStatus
0x180007d7e  nop     dword ptr [rax+rax+00h]
0x180007d83  int     3; Trap to Debugger
0x180007d84  movups  xmm1, xmmword ptr [rdx]
0x180007d87  mov     rdi, [rdx+8]
0x180007d8b  movups  [rbp+0B0h+var_128], xmm1
0x180007d8f  movq    rcx, xmm1
0x180007d94  movzx   r9d, r15b
0x180007d98  mov     [rbp+0B0h+var_F0], rcx
0x180007d9c  and     r9b, 1
0x180007da0  mov     [rsp+1B0h+var_17F], r9b
0x180007da5  test    r15b, 4
0x180007da9  jz      loc_1800084AF
0x180007daf  lea     rdx, g_LUNICODE_STRING_none
0x180007db6  mov     [rbp+0B0h+var_C0], 10h
0x180007dbe  and     r15d, 8
0x180007dc2  mov     [rbp+0B0h+var_B0], r10
0x180007dc6  lea     rax, g_LUNICODE_STRING__star_
0x180007dcd  mov     [rbp+0B0h+var_A8], 10h
0x180007dd5  cmovz   rax, rdx
0x180007dd9  mov     [rbp+0B0h+var_90], 28h ; '('
0x180007de1  lea     rdx, g_LUNICODE_STRING_processorArchitecture
0x180007de8  mov     [rbp+0B0h+var_C8], rax
0x180007dec  mov     [rbp+0B0h+var_D0], rdx
0x180007df0  mov     r12, r10
0x180007df3  lea     rdx, g_LUNICODE_STRING_typeName
0x180007dfa  mov     [rbp+0B0h+var_98], rax
0x180007dfe  mov     [rbp+0B0h+var_B8], rdx
0x180007e02  lea     rdx, g_LUNICODE_STRING_name
0x180007e09  mov     [rbp+0B0h+var_A0], rdx
0x180007e0d  lea     rdx, g_LUNICODE_STRING_publicKeyToken
0x180007e14  mov     [rbp+0B0h+var_88], rdx
0x180007e18  lea     rdx, g_LUNICODE_STRING_version
0x180007e1f  mov     [rbp+0B0h+var_70], rdx
0x180007e23  lea     rdx, g_LUNICODE_STRING_culture
0x180007e2a  mov     [rbp+0B0h+var_58], rdx
0x180007e2e  lea     rdx, RtlDowncaseUCSCharacter
0x180007e35  mov     [rbp+0B0h+var_80], rax
0x180007e39  mov     [rbp+0B0h+var_78], 0
0x180007e41  mov     [rbp+0B0h+var_68], rax
0x180007e45  mov     [rbp+0B0h+var_60], 0
0x180007e4d  mov     [rbp+0B0h+var_50], rax
0x180007e51  mov     [rbp+0B0h+var_48], 8
0x180007e59  cmp     r12, rdi
0x180007e5c  jnb     loc_180007F08
0x180007e62  lea     rax, [r12+r12*2]
0x180007e66  mov     [rbp+0B0h+var_F8], r10d
0x180007e6a  lea     r13, [rcx+rax*8]
0x180007e6e  mov     rax, [rcx+rax*8]
0x180007e72  test    rax, rax
0x180007e75  jnz     loc_18000848D
0x180007e7b  mov     rbx, r10
0x180007e7e  xchg    ax, ax
0x180007e80  cmp     rbx, 6
0x180007e84  jnb     short loc_180007EF1
0x180007e86  lea     rax, [rbx+rbx*2]
0x180007e8a  lea     rsi, ds:0[rax*8]
0x180007e92  cmp     byte ptr [rbp+rsi+0B0h+var_C0+4], 0
0x180007e97  jnz     short loc_180007F00
0x180007e99  mov     r8, [rbp+rsi+0B0h+var_D0]
0x180007e9e  mov     rcx, [r13+8]
0x180007ea2  mov     rax, [r8]
0x180007ea5  cmp     [rcx], rax
0x180007ea8  jnz     short loc_180007F00
0x180007eaa  lea     rax, [rbp+0B0h+var_F8]
0x180007eae  mov     [rsp+1B0h+var_188], rax
0x180007eb3  lea     r9, RtlDecodeUtf16LE
0x180007eba  mov     [rsp+1B0h+var_190], rdx
0x180007ebf  lea     rdx, RtlDecodeUtf16LE
0x180007ec6  call    RtlCompareEncodedLBlobs
0x180007ecb  mov     [rbp+0B0h+var_E0], eax
0x180007ece  test    eax, eax
0x180007ed0  js      loc_1800088B7
0x180007ed6  cmp     [rbp+0B0h+var_F8], 0
0x180007eda  lea     rdx, RtlDowncaseUCSCharacter
0x180007ee1  jnz     short loc_180007F00
0x180007ee3  mov     rax, [r13+10h]
0x180007ee7  mov     [rbp+rsi+0B0h+var_C8], rax
0x180007eec  mov     byte ptr [rbp+rsi+0B0h+var_C0+4], 1
0x180007ef1  mov     rcx, [rbp+0B0h+var_F0]
0x180007ef5  xor     r10d, r10d
0x180007ef8  inc     r12
0x180007efb  jmp     loc_180007E59
0x180007f00  inc     rbx
0x180007f03  jmp     loc_180007E80
0x180007f08  cmp     [rbp+0B0h+var_98], 0
0x180007f0d  jz      loc_1800088C9
0x180007f13  mov     r13, qword ptr [rsp+1B0h+var_158+8]
0x180007f18  lea     r9, aOnecoreBaseLst_3; "onecore\\base\\lstring\\lunicode_string"...
0x180007f1f  mov     rbx, qword ptr [rsp+1B0h+var_158]
0x180007f24  lea     r12, aRvNewcursorval; "__rv.NewCursorValue != 0"
0x180007f2b  mov     r8b, 1
0x180007f2e  mov     dword ptr [rbp+0B0h+var_F0], 2800h
0x180007f35  mov     [rsp+1B0h+var_180], r8b
0x180007f3a  mov     rdi, r10
0x180007f3d  mov     r11d, 0C0000161h
0x180007f43  cmp     rdi, 6
0x180007f47  jnb     loc_180008127
0x180007f4d  lea     rax, [rdi+rdi*2]
0x180007f51  mov     ecx, r10d
0x180007f54  lea     rsi, ds:0[rax*8]
0x180007f5c  movzx   eax, r8b
0x180007f60  movzx   edx, byte ptr [rbp+rsi+0B0h+var_C0+4]
0x180007f65  test    dl, dl
0x180007f67  cmovnz  ecx, eax
0x180007f6a  mov     [rsp+1B0h+var_180], cl
0x180007f6e  movzx   r8d, cl
0x180007f72  cmp     rdi, 4
0x180007f76  jz      loc_18000849C
0x180007f7c  cmp     rdi, 1
0x180007f80  jz      loc_1800084E8
0x180007f86  mov     eax, dword ptr [rbp+rsi+0B0h+var_C0]
0x180007f8a  test    eax, eax
0x180007f8c  jnz     loc_180008035
0x180007f92  test    rbx, rbx
0x180007f95  jnz     loc_180008081
0x180007f9b  mov     r10, [rsp+1B0h+var_148]
0x180007fa0  mov     [rbp+0B0h+var_E0], 0
0x180007fa7  test    bl, 1
0x180007faa  jnz     loc_1800086F8
0x180007fb0  test    r13b, 1
0x180007fb4  jnz     loc_1800086F8
0x180007fba  cmp     rbx, r13
0x180007fbd  ja      loc_1800086F8
0x180007fc3  test    r10, r10
0x180007fc6  jz      loc_1800086EF
0x180007fcc  mov     rax, [rbp+rsi+0B0h+var_C8]
0x180007fd1  test    rax, rax
0x180007fd4  jz      loc_18000843B
0x180007fda  mov     rsi, [rax]
0x180007fdd  test    sil, 1
0x180007fe1  jnz     loc_180008722
0x180007fe7  mov     rcx, [rax+8]
0x180007feb  test    cl, 1
0x180007fee  jnz     loc_180008722
0x180007ff4  cmp     rsi, rcx
0x180007ff7  ja      loc_180008722
0x180007ffd  mov     rdx, [rax+10h]; Src
0x180008001  test    rdx, rdx
0x180008004  jz      loc_180008719
0x18000800a  mov     rax, r13
0x18000800d  sub     rax, rbx
0x180008010  cmp     rax, rsi
0x180008013  jb      loc_1800087F5
0x180008019  mov     rax, rbx
0x18000801c  mov     r8, rsi; Size
0x18000801f  shr     rax, 1
0x180008022  lea     rcx, [r10+rax*2]; void *
0x180008026  call    memmove
0x18000802b  add     rbx, rsi
0x18000802e  mov     qword ptr [rsp+1B0h+var_158], rbx
0x180008033  jmp     short loc_180008063
0x180008035  test    dl, dl
0x180008037  jz      loc_180007F92
0x18000803d  mov     rdx, [rbp+rsi+0B0h+var_C8]
0x180008042  lea     r8, [rsp+1B0h+var_158]
0x180008047  mov     r9, rax
0x18000804a  call    _anonymous_namespace___FilterIdentityStringWhileAppending
0x18000804f  mov     ebx, eax
0x180008051  test    eax, eax
0x180008053  js      loc_1800082C5
0x180008059  mov     r13, qword ptr [rsp+1B0h+var_158+8]
0x18000805e  mov     rbx, qword ptr [rsp+1B0h+var_158]
0x180008063  movzx   r8d, [rsp+1B0h+var_180]
0x180008069  lea     r9, aOnecoreBaseLst_3; "onecore\\base\\lstring\\lunicode_string"...
0x180008070  mov     r11d, 0C0000161h
0x180008076  xor     r10d, r10d
0x180008079  inc     rdi
0x18000807c  jmp     loc_180007F43
0x180008081  mov     [rbp+0B0h+var_E0], 5Fh ; '_'
0x180008088  mov     [rbp+0B0h+var_F8], r10d
0x18000808c  test    bl, 1
0x18000808f  jnz     loc_18000874C
0x180008095  test    r13b, 1
0x180008099  jnz     loc_18000874C
0x18000809f  cmp     rbx, r13
0x1800080a2  ja      loc_18000874C
0x1800080a8  mov     r10, [rsp+1B0h+var_148]
0x1800080ad  test    r10, r10
0x1800080b0  jz      loc_180008743
0x1800080b6  lea     rcx, [r10+rbx]
0x1800080ba  xor     r9d, r9d
0x1800080bd  lea     r8, [r10+r13]
0x1800080c1  cmp     rcx, r8
0x1800080c4  ja      short loc_180008110
0x1800080c6  cmp     r9, 1
0x1800080ca  jnb     short loc_180008110
0x1800080cc  mov     edx, [rbp+r9*4+0B0h+var_E0]
0x1800080d1  mov     rax, r8
0x1800080d4  sub     rax, rcx
0x1800080d7  cmp     edx, 10000h
0x1800080dd  jnb     loc_180008909
0x1800080e3  cmp     rax, 2
0x1800080e7  jb      loc_1800085BB
0x1800080ed  lea     eax, [rdx-0DC00h]
0x1800080f3  cmp     eax, 3FFh
0x1800080f8  jbe     loc_180008915
0x1800080fe  mov     [rcx], dx
0x180008101  add     rcx, 2
0x180008105  jz      loc_18000894C
0x18000810b  inc     r9
0x18000810e  jmp     short loc_1800080C1
0x180008110  mov     rbx, rcx
0x180008113  sub     rbx, r10
0x180008116  mov     qword ptr [rsp+1B0h+var_158], rbx
0x18000811b  lea     r9, aOnecoreBaseLst_3; "onecore\\base\\lstring\\lunicode_string"...
0x180008122  jmp     loc_180007FA0
0x180008127  mov     rsi, [rsp+1B0h+var_148]
0x18000812c  test    rbx, rbx
0x18000812f  jnz     loc_1800084F5
0x180008135  test    r15d, r15d
0x180008138  jnz     loc_1800085F5
0x18000813e  mov     r11, [rbp+0B0h+var_108]
0x180008142  lea     r9, [rsi+r13]
0x180008146  add     rbx, rsi
0x180008149  mov     edi, 30h ; '0'
0x18000814e  xchg    ax, ax
0x180008150  cmp     r10, 4
0x180008154  jnb     loc_1800089F7
0x18000815a  mov     rax, r11
0x18000815d  mov     edx, 57h ; 'W'
0x180008162  shr     rax, 30h
0x180008166  mov     rcx, r9
0x180008169  mov     r8d, eax
0x18000816c  shr     r8d, 0Ch
0x180008170  cmp     r8d, 0Ah
0x180008174  cmovb   edx, edi
0x180008177  sub     rcx, rbx
0x18000817a  cmp     rcx, 2
0x18000817e  jb      loc_180008239
0x180008184  add     dx, r8w
0x180008188  mov     [rbx], dx
0x18000818b  add     rbx, 2
0x18000818f  jz      loc_180007D72
0x180008195  mov     edx, eax
0x180008197  mov     r8d, 57h ; 'W'
0x18000819d  shr     edx, 8
0x1800081a0  mov     rcx, r9
0x1800081a3  and     edx, 0Fh
0x1800081a6  cmp     edx, 0Ah
0x1800081a9  cmovb   r8d, edi
0x1800081ad  sub     rcx, rbx
0x1800081b0  cmp     rcx, 2
0x1800081b4  jb      loc_18000842D
0x1800081ba  add     r8w, dx
0x1800081be  mov     [rbx], r8w
0x1800081c2  add     rbx, 2
0x1800081c6  jz      loc_180007D72
0x1800081cc  mov     edx, eax
0x1800081ce  mov     r8d, 57h ; 'W'
0x1800081d4  shr     edx, 4
0x1800081d7  mov     rcx, r9
0x1800081da  and     edx, 0Fh
0x1800081dd  cmp     edx, 0Ah
0x1800081e0  cmovb   r8d, edi
0x1800081e4  sub     rcx, rbx
0x1800081e7  cmp     rcx, 2
0x1800081eb  jb      loc_18000841F
0x1800081f1  add     r8w, dx
0x1800081f5  mov     [rbx], r8w
0x1800081f9  add     rbx, 2
0x1800081fd  jz      loc_180007D72
0x180008203  and     eax, 0Fh
0x180008206  mov     edx, 57h ; 'W'
0x18000820b  cmp     eax, 0Ah
0x18000820e  mov     rcx, r9
0x180008211  cmovb   edx, edi
0x180008214  sub     rcx, rbx
0x180008217  cmp     rcx, 2
0x18000821b  jb      short loc_180008289
0x18000821d  add     dx, ax
0x180008220  mov     [rbx], dx
  ... truncated ...
```
