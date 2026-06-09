# ParseArguments(_FileAttributesStrs &,ushort * *,unsigned __int64,unsigned __int64)

- ea: `0x180015a60`
- end: `0x180016654`
- name: `?ParseArguments@@YA_NAEAU_FileAttributesStrs@@PEAPEAG_K2@Z`
- size: `3060`
- prototype: `bool __fastcall(struct _FileAttributesStrs *, unsigned __int16 **, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180014580`

## callees

- `0x18000c190`
- `0x18000e0e4`
- `0x180015a60`
- `0x1800543c0`
- `0x180065120`
- `0x180065150`

## string_xrefs

- `0x180015a8a`: `Wrong number of arguments: %zu. Can't access index: %zu`
- `0x180015ac0`: `Wrong number of arguments: %zu. Can't access (index + 1): %zu`
- `0x180015e7f`: `-CompanyName`
- `0x180015ef3`: `CompanyName: %ws`
- `0x180016243`: `-DriverInstalled`
- `0x1800162bd`: `DriverInstalled: %ws`
- `0x180016320`: `DriverInstalled value is wrong, %ws`

## pseudocode

```c
char __fastcall ParseArguments(
        struct _FileAttributesStrs *a1,
        unsigned __int16 **a2,
        unsigned __int64 a3,
        unsigned __int64 a4)
{
  char v7; // r15
  const wchar_t *v8; // rbx
  unsigned __int16 *v9; // r9
  unsigned __int64 v10; // rdx
  char *v11; // rsi
  char *v12; // r14
  __int64 v13; // rbx
  const char *v14; // r9
  __int64 v15; // r8
  unsigned __int16 *v16; // r9
  unsigned __int64 v17; // rdx
  char *v18; // r14
  __int64 v19; // rbx
  unsigned __int16 *v20; // r9
  unsigned __int64 v21; // rdx
  char *v22; // r14
  __int64 v23; // rbx
  unsigned __int16 *v24; // r9
  unsigned __int64 v25; // rdx
  char *v26; // r14
  __int64 v27; // rbx
  unsigned __int16 *v28; // r9
  unsigned __int64 v29; // rdx
  char *v30; // r14
  __int64 v31; // rbx
  unsigned __int16 *v32; // r9
  unsigned __int64 v33; // rdx
  char *v34; // r14
  __int64 v35; // rbx
  unsigned __int16 *v36; // r9
  char *v37; // rdi
  unsigned __int64 v38; // rdx
  char *v39; // rsi
  __int64 v40; // rbx
  unsigned __int16 *v41; // r9
  unsigned __int64 v42; // rdx
  char *v43; // r14
  __int64 v44; // rbx
  unsigned __int16 *v45; // r9
  unsigned __int64 v46; // rdx
  char *v47; // r14
  __int64 v48; // rbx
  unsigned __int16 *v49; // r9
  unsigned __int64 v50; // rdx
  char *v51; // r14
  __int64 v52; // rbx
  unsigned __int16 *v53; // r9
  unsigned __int64 v54; // rdx
  char *v55; // r14
  __int64 v56; // rbx
  unsigned __int16 *v57; // r9
  unsigned __int64 v58; // rdx
  char *v59; // r14
  __int64 v60; // rbx
  unsigned __int16 *v61; // r9
  unsigned __int64 v62; // rdx
  char *v63; // r14
  __int64 v64; // rbx
  unsigned __int16 *v65; // r9
  unsigned __int64 v66; // rdx
  char *v67; // r14
  __int64 v68; // rbx
  unsigned __int16 *v69; // r9
  unsigned __int64 *v70; // rdi
  unsigned __int64 v71; // rdx
  char *v72; // rsi
  __int64 v73; // rbx
  unsigned __int64 *v74; // rax
  unsigned __int64 v75; // rbx
  const wchar_t *v76; // rcx
  size_t v77; // r8
  const char *v78; // r9
  __int64 v79; // r8
  unsigned __int16 *v80; // r9
  unsigned __int64 v81; // rdx
  char *v82; // rsi
  __int64 v83; // rbx
  unsigned __int64 *v84; // rax
  unsigned __int64 v85; // rbx
  const wchar_t *v86; // rcx
  size_t v87; // r8
  unsigned __int16 *v88; // r9
  unsigned __int64 v89; // rdx
  char *v90; // rsi
  __int64 v91; // rbx
  unsigned __int64 *v92; // rax
  unsigned __int64 v93; // rbx
  const wchar_t *v94; // rcx
  size_t v95; // r8
  unsigned __int16 *v96; // r9
  char **v97; // r15
  unsigned __int64 v98; // rdx
  char *v99; // r12
  __int64 v100; // rbx
  int v101; // eax
  int v102; // ecx

  v7 = 0;
  if ( a3 <= a4 )
  {
    AslLogCallPrintf(1, "ParseArguments", 1892, "Wrong number of arguments: %zu. Can't access index: %zu", a3, a4);
    return v7;
  }
  if ( a3 > a4 + 1 )
  {
    v8 = a2[a4];
    if ( !wcscmp_0(v8, L"-FromBinVersion") )
    {
      v9 = a2[a4 + 1];
      v10 = -1;
      v11 = (char *)a1 + 8;
      do
        ++v10;
      while ( v9[v10] );
      if ( v10 > *((_QWORD *)a1 + 4) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>((char *)a1 + 8);
      }
      else
      {
        if ( *((_QWORD *)a1 + 4) <= 7u )
          v12 = (char *)a1 + 8;
        else
          v12 = *(char **)v11;
        v13 = 2 * v10;
        *((_QWORD *)a1 + 3) = v10;
        memmove_0(v12, v9, 2 * v10);
        *(_WORD *)&v12[v13] = 0;
      }
      *(_BYTE *)a1 = 1;
      if ( *((_QWORD *)a1 + 4) > 7u )
        v11 = *(char **)v11;
      v14 = "From bin ver: %ws";
      v15 = 1905;
    }
    else if ( !wcscmp_0(v8, L"-UptoBinVersion") )
    {
      v16 = a2[a4 + 1];
      v17 = -1;
      v11 = (char *)a1 + 40;
      do
        ++v17;
      while ( v16[v17] );
      if ( v17 > *((_QWORD *)a1 + 8) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>((char *)a1 + 40);
      }
      else
      {
        if ( *((_QWORD *)a1 + 8) <= 7u )
          v18 = (char *)a1 + 40;
        else
          v18 = *(char **)v11;
        v19 = 2 * v17;
        *((_QWORD *)a1 + 7) = v17;
        memmove_0(v18, v16, 2 * v17);
        *(_WORD *)&v18[v19] = 0;
      }
      *(_BYTE *)a1 = 1;
      if ( *((_QWORD *)a1 + 8) > 7u )
        v11 = *(char **)v11;
      v14 = "Upto bin ver: %ws";
      v15 = 1911;
    }
    else if ( !wcscmp_0(v8, L"-FromProductVersion") )
    {
      v20 = a2[a4 + 1];
      v21 = -1;
      v11 = (char *)a1 + 72;
      do
        ++v21;
      while ( v20[v21] );
      if ( v21 > *((_QWORD *)a1 + 12) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>((char *)a1 + 72);
      }
      else
      {
        if ( *((_QWORD *)a1 + 12) <= 7u )
          v22 = (char *)a1 + 72;
        else
          v22 = *(char **)v11;
        v23 = 2 * v21;
        *((_QWORD *)a1 + 11) = v21;
        memmove_0(v22, v20, 2 * v21);
        *(_WORD *)&v22[v23] = 0;
      }
      *(_BYTE *)a1 = 1;
      if ( *((_QWORD *)a1 + 12) > 7u )
        v11 = *(char **)v11;
      v14 = "From product ver: %ws";
      v15 = 1917;
    }
    else if ( !wcscmp_0(v8, L"-UptoProductVersion") )
    {
      v24 = a2[a4 + 1];
      v25 = -1;
      v11 = (char *)a1 + 104;
      do
        ++v25;
      while ( v24[v25] );
      if ( v25 > *((_QWORD *)a1 + 16) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>((char *)a1 + 104);
      }
      else
      {
        if ( *((_QWORD *)a1 + 16) <= 7u )
          v26 = (char *)a1 + 104;
        else
          v26 = *(char **)v11;
        v27 = 2 * v25;
        *((_QWORD *)a1 + 15) = v25;
        memmove_0(v26, v24, 2 * v25);
        *(_WORD *)&v26[v27] = 0;
      }
      *(_BYTE *)a1 = 1;
      if ( *((_QWORD *)a1 + 16) > 7u )
        v11 = *(char **)v11;
      v14 = "Upto product ver: %ws";
      v15 = 1923;
    }
    else if ( !wcscmp_0(v8, L"-MatchingText") )
    {
      v28 = a2[a4 + 1];
      v29 = -1;
      v11 = (char *)a1 + 136;
      do
        ++v29;
      while ( v28[v29] );
      if ( v29 > *((_QWORD *)a1 + 20) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>((char *)a1 + 136);
      }
      else
      {
        if ( *((_QWORD *)a1 + 20) <= 7u )
          v30 = (char *)a1 + 136;
        else
          v30 = *(char **)v11;
        v31 = 2 * v29;
        *((_QWORD *)a1 + 19) = v29;
        memmove_0(v30, v28, 2 * v29);
        *(_WORD *)&v30[v31] = 0;
      }
      *((_BYTE *)a1 + 1) = 1;
      if ( *((_QWORD *)a1 + 20) > 7u )
        v11 = *(char **)v11;
      v14 = "Matching text: %ws";
      v15 = 1929;
    }
    else if ( !wcscmp_0(v8, L"-MatchingRegexText") )
    {
      v32 = a2[a4 + 1];
      v33 = -1;
      v11 = (char *)a1 + 168;
      do
        ++v33;
      while ( v32[v33] );
      if ( v33 > *((_QWORD *)a1 + 24) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>((char *)a1 + 168);
      }
      else
      {
        if ( *((_QWORD *)a1 + 24) <= 7u )
          v34 = (char *)a1 + 168;
        else
          v34 = *(char **)v11;
        v35 = 2 * v33;
        *((_QWORD *)a1 + 23) = v33;
        memmove_0(v34, v32, 2 * v33);
        *(_WORD *)&v34[v35] = 0;
      }
      *((_BYTE *)a1 + 2) = 1;
      if ( *((_QWORD *)a1 + 24) > 7u )
        v11 = *(char **)v11;
      v14 = "Matching regex text: %ws";
      v15 = 1935;
    }
    else
    {
      if ( !wcscmp_0(v8, L"-Encoding") )
      {
        v36 = a2[a4 + 1];
        v37 = (char *)a1 + 200;
        v38 = -1;
        do
          ++v38;
        while ( v36[v38] );
        if ( v38 > *((_QWORD *)v37 + 3) )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v37);
        }
        else
        {
          if ( *((_QWORD *)v37 + 3) <= 7u )
            v39 = v37;
          else
            v39 = *(char **)v37;
          v40 = 2 * v38;
          *((_QWORD *)v37 + 2) = v38;
          memmove_0(v39, v36, 2 * v38);
          *(_WORD *)&v39[v40] = 0;
        }
        if ( *((_QWORD *)v37 + 3) > 7u )
          v37 = *(char **)v37;
        AslLogCallPrintf(3, "ParseArguments", 1940, "Encoding is: %ws", v37);
        return 1;
      }
      if ( !wcscmp_0(v8, L"-CompanyName") )
      {
        v41 = a2[a4 + 1];
        v42 = -1;
        v11 = (char *)a1 + 360;
        do
          ++v42;
        while ( v41[v42] );
        if ( v42 > *((_QWORD *)a1 + 48) )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>((char *)a1 + 360);
        }
        else
        {
          if ( *((_QWORD *)a1 + 48) <= 7u )
            v43 = (char *)a1 + 360;
          else
            v43 = *(char **)v11;
          v44 = 2 * v42;
          *((_QWORD *)a1 + 47) = v42;
          memmove_0(v43, v41, 2 * v42);
          *(_WORD *)&v43[v44] = 0;
        }
        *(_BYTE *)a1 = 1;
        if ( *((_QWORD *)a1 + 48) > 7u )
          v11 = *(char **)v11;
        v14 = "CompanyName: %ws";
        v15 = 1946;
      }
      else if ( !wcscmp_0(v8, L"-ProductName") )
      {
        v45 = a2[a4 + 1];
        v46 = -1;
        v11 = (char *)a1 + 392;
        do
          ++v46;
        while ( v45[v46] );
        if ( v46 > *((_QWORD *)a1 + 52) )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>((char *)a1 + 392);
        }
        else
        {
          if ( *((_QWORD *)a1 + 52) <= 7u )
            v47 = (char *)a1 + 392;
          else
            v47 = *(char **)v11;
          v48 = 2 * v46;
          *((_QWORD *)a1 + 51) = v46;
          memmove_0(v47, v45, 2 * v46);
          *(_WORD *)&v47[v48] = 0;
        }
        *(_BYTE *)a1 = 1;
        if ( *((_QWORD *)a1 + 52) > 7u )
          v11 = *(char **)v11;
        v14 = "ProductName: %ws";
        v15 = 1952;
      }
      else if ( !wcscmp_0(v8, L"-Size") )
      {
        v49 = a2[a4 + 1];
        v50 = -1;
        v11 = (char *)a1 + 232;
        do
          ++v50;
        while ( v49[v50] );
        if ( v50 > *((_QWORD *)a1 + 32) )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>((char *)a1 + 232);
        }
        else
        {
          if ( *((_QWORD *)a1 + 32) <= 7u )
            v51 = (char *)a1 + 232;
          else
            v51 = *(char **)v11;
          v52 = 2 * v50;
          *((_QWORD *)a1 + 31) = v50;
          memmove_0(v51, v49, 2 * v50);
          *(_WORD *)&v51[v52] = 0;
        }
        *(_BYTE *)a1 = 1;
        if ( *((_QWORD *)a1 + 32) > 7u )
          v11 = *(char **)v11;
        v14 = "File Size: %ws";
        v15 = 1958;
      }
      else if ( !wcscmp_0(v8, L"-Checksum") )
      {
        v53 = a2[a4 + 1];
        v54 = -1;
        v11 = (char *)a1 + 264;
        do
          ++v54;
        while ( v53[v54] );
        if ( v54 > *((_QWORD *)a1 + 36) )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>((char *)a1 + 264);
        }
        else
        {
          if ( *((_QWORD *)a1 + 36) <= 7u )
            v55 = (char *)a1 + 264;
          else
            v55 = *(char **)v11;
          v56 = 2 * v54;
          *((_QWORD *)a1 + 35) = v54;
          memmove_0(v55, v53, 2 * v54);
          *(_WORD *)&v55[v56] = 0;
        }
        *(_BYTE *)a1 = 1;
        if ( *((_QWORD *)a1 + 36) > 7u )
          v11 = *(char **)v11;
        v14 = "Checksum: %ws";
        v15 = 1964;
      }
      else if ( !wcscmp_0(v8, L"-PeChecksum") )
      {
        v57 = a2[a4 + 1];
        v58 = -1;
        v11 = (char *)a1 + 296;
        do
          ++v58;
        while ( v57[v58] );
        if ( v58 > *((_QWORD *)a1 + 40) )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>((char *)a1 + 296);
        }
        else
        {
          if ( *((_QWORD *)a1 + 40) <= 7u )
            v59 = (char *)a1 + 296;
          else
            v59 = *(char **)v11;
          v60 = 2 * v58;
          *((_QWORD *)a1 + 39) = v58;
          memmove_0(v59, v57, 2 * v58);
          *(_WORD *)&v59[v60] = 0;
        }
        *(_BYTE *)a1 = 1;
        if ( *((_QWORD *)a1 + 40) > 7u )
          v11 = *(char **)v11;
        v14 = "PeChecksum: %ws";
        v15 = 1970;
      }
      else if ( !wcscmp_0(v8, L"-CrcChecksum") )
      {
        v61 = a2[a4 + 1];
        v62 = -1;
        v11 = (char *)a1 + 328;
        do
          ++v62;
        while ( v61[v62] );
        if ( v62 > *((_QWORD *)a1 + 44) )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>((char *)a1 + 328);
        }
        else
        {
          if ( *((_QWORD *)a1 + 44) <= 7u )
            v63 = (char *)a1 + 328;
          else
            v63 = *(char **)v11;
          v64 = 2 * v62;
          *((_QWORD *)a1 + 43) = v62;
          memmove_0(v63, v61, 2 * v62);
          *(_WORD *)&v63[v64] = 0;
        }
        *(_BYTE *)a1 = 1;
        if ( *((_QWORD *)a1 + 44) > 7u )
          v11 = *(char **)v11;
        v14 = "CrcChecksum: %ws";
        v15 = 1976;
      }
      else
      {
        if ( wcscmp_0(v8, L"-FileDescription") )
        {
          if ( !wcscmp_0(v8, L"-DriverInstalled") )
          {
            v69 = a2[a4 + 1];
            v70 = (unsigned __int64 *)((char *)a1 + 456);
            v71 = -1;
            do
              ++v71;
            while ( v69[v71] );
            if ( v71 > v70[3] )
            {
              std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v70);
            }
            else
            {
              if ( v70[3] <= 7 )
                v72 = (char *)v70;
              else
                v72 = (char *)*v70;
              v73 = 2 * v71;
              v70[2] = v71;
              memmove_0(v72, v69, 2 * v71);
              *(_WORD *)&v72[v73] = 0;
            }
            if ( v70[3] <= 7 )
              v74 = v70;
            else
              v74 = (unsigned __int64 *)*v70;
            AslLogCallPrintf(3, "ParseArguments", 1987, "DriverInstalled: %ws", v74);
            v75 = v70[2];
            if ( v70[3] <= 7 )
              v76 = (const wchar_t *)v70;
            else
              v76 = (const wchar_t *)*v70;
            v77 = v70[2];
            if ( v75 > 1 )
              v77 = 1;
            if ( !wmemcmp(v76, L"1", v77) && v75 == 1 )
              return 1;
            if ( v70[3] > 7 )
              v70 = (unsigned __int64 *)*v70;
            v78 = "DriverInstalled value is wrong, %ws";
            v79 = 1991;
          }
          else if ( !wcscmp_0(v8, L"-DriverState") )
          {
            v80 = a2[a4 + 1];
            v70 = (unsigned __int64 *)((char *)a1 + 488);
            v81 = -1;
            do
              ++v81;
            while ( v80[v81] );
            if ( v81 > v70[3] )
            {
              std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v70);
            }
            else
            {
              if ( v70[3] <= 7 )
                v82 = (char *)v70;
              else
                v82 = (char *)*v70;
              v83 = 2 * v81;
              v70[2] = v81;
              memmove_0(v82, v80, 2 * v81);
              *(_WORD *)&v82[v83] = 0;
            }
            if ( v70[3] <= 7 )
              v84 = v70;
            else
              v84 = (unsigned __int64 *)*v70;
            AslLogCallPrintf(3, "ParseArguments", 1998, "DriverState: %ws", v84);
            v85 = v70[2];
            if ( v70[3] <= 7 )
              v86 = (const wchar_t *)v70;
            else
              v86 = (const wchar_t *)*v70;
            v87 = v70[2];
            if ( v85 > 0xB )
              v87 = 11;
            if ( !wmemcmp(v86, L"not_stopped", v87) && v85 == 11 )
              return 1;
            if ( v70[3] > 7 )
              v70 = (unsigned __int64 *)*v70;
            v78 = "DriverState value is wrong, %ws";
            v79 = 2002;
          }
          else
          {
            if ( wcscmp_0(v8, L"-DriverStartMode") )
            {
              if ( wcscmp_0(v8, L"-Sha1") && wcscmp_0(v8, L"-Sha256") && wcscmp_0(v8, L"-Md5") )
              {
                AslLogCallPrintf(1, "ParseArguments", 2038, "Unrecognized switch: %ws", v8);
                return v7;
              }
              v96 = a2[a4 + 1];
              v97 = (char **)((char *)a1 + 552);
              v98 = -1;
              do
                ++v98;
              while ( v96[v98] );
              if ( v98 > *((_QWORD *)a1 + 72) )
              {
                std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>((char *)a1 + 552);
              }
              else
              {
                if ( *((_QWORD *)a1 + 72) <= 7u )
                  v99 = (char *)a1 + 552;
                else
                  v99 = *v97;
                v100 = 2 * v98;
                *((_QWORD *)a1 + 71) = v98;
                memmove_0(v99, v96, 2 * v98);
                *(_WORD *)&v99[v100] = 0;
              }
              if ( *((_QWORD *)a1 + 72) > 7u )
                v97 = (char **)*v97;
              AslLogCallPrintf(3, "ParseArguments", 2022, "HashValue: %ws", v97);
              if ( !wcscmp_0(a2[a4], L"-Sha1") )
              {
                *((_DWORD *)a1 + 146) = 1;
              }
              else
              {
                v101 = wcscmp_0(a2[a4], L"-Sha256");
                v102 = 0;
                if ( !v101 )
                  v102 = 2;
                *((_DWORD *)a1 + 146) = v102;
              }
              return 1;
            }
            v88 = a2[a4 + 1];
            v70 = (unsigned __int64 *)((char *)a1 + 520);
            v89 = -1;
            do
              ++v89;
            while ( v88[v89] );
            if ( v89 > v70[3] )
            {
              std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v70);
            }
            else
            {
              if ( v70[3] <= 7 )
                v90 = (char *)v70;
              else
                v90 = (char *)*v70;
              v91 = 2 * v89;
              v70[2] = v89;
              memmove_0(v90, v88, 2 * v89);
              *(_WORD *)&v90[v91] = 0;
            }
            if ( v70[3] <= 7 )
              v92 = v70;
            else
              v92 = (unsigned __int64 *)*v70;
            AslLogCallPrintf(3, "ParseArguments", 2009, "DriverStartMode: %ws", v92);
            v93 = v70[2];
            if ( v70[3] <= 7 )
              v94 = (const wchar_t *)v70;
            else
              v94 = (const wchar_t *)*v70;
            v95 = v70[2];
            if ( v93 > 0xC )
              v95 = 12;
            if ( !wmemcmp(v94, L"not_disabled", v95) && v93 == 12 )
              return 1;
            if ( v70[3] > 7 )
              v70 = (unsigned __int64 *)*v70;
            v78 = "DriverStartMode value is wrong, %ws";
            v79 = 2013;
          }
          AslLogCallPrintf(1, "ParseArguments", v79, v78, v70);
          return v7;
        }
        v65 = a2[a4 + 1];
        v66 = -1;
        v11 = (char *)a1 + 424;
        do
          ++v66;
        while ( v65[v66] );
        if ( v66 > *((_QWORD *)a1 + 56) )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>((char *)a1 + 424);
        }
        else
        {
          if ( *((_QWORD *)a1 + 56) <= 7u )
            v67 = (char *)a1 + 424;
          else
            v67 = *(char **)v11;
          v68 = 2 * v66;
          *((_QWORD *)a1 + 55) = v66;
          memmove_0(v67, v65, 2 * v66);
          *(_WORD *)&v67[v68] = 0;
        }
        *(_BYTE *)a1 = 1;
        if ( *((_QWORD *)a1 + 56) > 7u )
          v11 = *(char **)v11;
        v14 = "FileDescription: %ws";
        v15 = 1982;
      }
    }
    AslLogCallPrintf(3, "ParseArguments", v15, v14, v11);
    return 1;
  }
  AslLogCallPrintf(
    1,
    "ParseArguments",
    1897,
    "Wrong number of arguments: %zu. Can't access (index + 1): %zu",
    a3,
    a4 + 1);
  return v7;
}

```

## disassembly

```asm
0x180015a60  push    rbx
0x180015a62  push    rbp
0x180015a63  push    rsi
0x180015a64  push    rdi
0x180015a65  push    r12
0x180015a67  push    r13
0x180015a69  push    r14
0x180015a6b  push    r15
0x180015a6d  sub     rsp, 38h
0x180015a71  xor     r13d, r13d
0x180015a74  mov     rsi, r9
0x180015a77  mov     r14, rdx
0x180015a7a  mov     rdi, rcx
0x180015a7d  mov     r15b, r13b
0x180015a80  cmp     r8, r9
0x180015a83  ja      short loc_180015AB2
0x180015a85  mov     [rsp+78h+var_50], r9
0x180015a8a  lea     r9, aWrongNumberOfA; "Wrong number of arguments: %zu. Can't a"...
0x180015a91  mov     [rsp+78h+var_58], r8
0x180015a96  mov     r8d, 764h
0x180015a9c  lea     rdx, aParsearguments; "ParseArguments"
0x180015aa3  mov     ecx, 1
0x180015aa8  call    AslLogCallPrintf
0x180015aad  jmp     loc_180016640
0x180015ab2  lea     rax, [r9+1]
0x180015ab6  cmp     r8, rax
0x180015ab9  ja      short loc_180015AD4
0x180015abb  mov     [rsp+78h+var_50], rax
0x180015ac0  lea     r9, aWrongNumberOfA_0; "Wrong number of arguments: %zu. Can't a"...
0x180015ac7  mov     [rsp+78h+var_58], r8
0x180015acc  mov     r8d, 769h
0x180015ad2  jmp     short loc_180015A9C
0x180015ad4  mov     rbx, [rdx+r9*8]
0x180015ad8  lea     rdx, aFrombinversion; "-FromBinVersion"
0x180015adf  mov     rcx, rbx; String1
0x180015ae2  call    wcscmp_0
0x180015ae7  mov     ebp, 1
0x180015aec  test    eax, eax
0x180015aee  jnz     short loc_180015B60
0x180015af0  mov     r9, [r14+rsi*8+8]
0x180015af5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180015af9  lea     rsi, [rdi+8]
0x180015afd  inc     rdx
0x180015b00  cmp     [r9+rdx*2], r13w
0x180015b05  jnz     short loc_180015AFD
0x180015b07  cmp     rdx, [rsi+18h]
0x180015b0b  ja      short loc_180015B39
0x180015b0d  cmp     qword ptr [rsi+18h], 7
0x180015b12  jbe     short loc_180015B19
0x180015b14  mov     r14, [rsi]
0x180015b17  jmp     short loc_180015B1C
0x180015b19  mov     r14, rsi
0x180015b1c  lea     rbx, [rdx+rdx]
0x180015b20  mov     [rsi+10h], rdx
0x180015b24  mov     r8, rbx; Size
0x180015b27  mov     rdx, r9; Src
0x180015b2a  mov     rcx, r14; void *
0x180015b2d  call    memmove_0
0x180015b32  mov     [rbx+r14], r13w
0x180015b37  jmp     short loc_180015B41
0x180015b39  mov     rcx, rsi
0x180015b3c  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180015b41  mov     [rdi], bpl
0x180015b44  cmp     qword ptr [rsi+18h], 7
0x180015b49  jbe     short loc_180015B4E
0x180015b4b  mov     rsi, [rsi]
0x180015b4e  lea     r9, aFromBinVerWs; "From bin ver: %ws"
0x180015b55  mov     r8d, 771h
0x180015b5b  jmp     loc_180016228
0x180015b60  lea     rdx, aUptobinversion; "-UptoBinVersion"
0x180015b67  mov     rcx, rbx; String1
0x180015b6a  call    wcscmp_0
0x180015b6f  test    eax, eax
0x180015b71  jnz     short loc_180015BE3
0x180015b73  mov     r9, [r14+rsi*8+8]
0x180015b78  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180015b7c  lea     rsi, [rdi+28h]
0x180015b80  inc     rdx
0x180015b83  cmp     [r9+rdx*2], r13w
0x180015b88  jnz     short loc_180015B80
0x180015b8a  cmp     rdx, [rsi+18h]
0x180015b8e  ja      short loc_180015BBC
0x180015b90  cmp     qword ptr [rsi+18h], 7
0x180015b95  jbe     short loc_180015B9C
0x180015b97  mov     r14, [rsi]
0x180015b9a  jmp     short loc_180015B9F
0x180015b9c  mov     r14, rsi
0x180015b9f  lea     rbx, [rdx+rdx]
0x180015ba3  mov     [rsi+10h], rdx
0x180015ba7  mov     r8, rbx; Size
0x180015baa  mov     rdx, r9; Src
0x180015bad  mov     rcx, r14; void *
0x180015bb0  call    memmove_0
0x180015bb5  mov     [rbx+r14], r13w
0x180015bba  jmp     short loc_180015BC4
0x180015bbc  mov     rcx, rsi
0x180015bbf  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180015bc4  mov     [rdi], bpl
0x180015bc7  cmp     qword ptr [rsi+18h], 7
0x180015bcc  jbe     short loc_180015BD1
0x180015bce  mov     rsi, [rsi]
0x180015bd1  lea     r9, aUptoBinVerWs; "Upto bin ver: %ws"
0x180015bd8  mov     r8d, 777h
0x180015bde  jmp     loc_180016228
0x180015be3  lea     rdx, aFromproductver; "-FromProductVersion"
0x180015bea  mov     rcx, rbx; String1
0x180015bed  call    wcscmp_0
0x180015bf2  test    eax, eax
0x180015bf4  jnz     short loc_180015C66
0x180015bf6  mov     r9, [r14+rsi*8+8]
0x180015bfb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180015bff  lea     rsi, [rdi+48h]
0x180015c03  inc     rdx
0x180015c06  cmp     [r9+rdx*2], r13w
0x180015c0b  jnz     short loc_180015C03
0x180015c0d  cmp     rdx, [rsi+18h]
0x180015c11  ja      short loc_180015C3F
0x180015c13  cmp     qword ptr [rsi+18h], 7
0x180015c18  jbe     short loc_180015C1F
0x180015c1a  mov     r14, [rsi]
0x180015c1d  jmp     short loc_180015C22
0x180015c1f  mov     r14, rsi
0x180015c22  lea     rbx, [rdx+rdx]
0x180015c26  mov     [rsi+10h], rdx
0x180015c2a  mov     r8, rbx; Size
0x180015c2d  mov     rdx, r9; Src
0x180015c30  mov     rcx, r14; void *
0x180015c33  call    memmove_0
0x180015c38  mov     [rbx+r14], r13w
0x180015c3d  jmp     short loc_180015C47
0x180015c3f  mov     rcx, rsi
0x180015c42  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180015c47  mov     [rdi], bpl
0x180015c4a  cmp     qword ptr [rsi+18h], 7
0x180015c4f  jbe     short loc_180015C54
0x180015c51  mov     rsi, [rsi]
0x180015c54  lea     r9, aFromProductVer; "From product ver: %ws"
0x180015c5b  mov     r8d, 77Dh
0x180015c61  jmp     loc_180016228
0x180015c66  lea     rdx, aUptoproductver; "-UptoProductVersion"
0x180015c6d  mov     rcx, rbx; String1
0x180015c70  call    wcscmp_0
0x180015c75  test    eax, eax
0x180015c77  jnz     short loc_180015CE9
0x180015c79  mov     r9, [r14+rsi*8+8]
0x180015c7e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180015c82  lea     rsi, [rdi+68h]
0x180015c86  inc     rdx
0x180015c89  cmp     [r9+rdx*2], r13w
0x180015c8e  jnz     short loc_180015C86
0x180015c90  cmp     rdx, [rsi+18h]
0x180015c94  ja      short loc_180015CC2
0x180015c96  cmp     qword ptr [rsi+18h], 7
0x180015c9b  jbe     short loc_180015CA2
0x180015c9d  mov     r14, [rsi]
0x180015ca0  jmp     short loc_180015CA5
0x180015ca2  mov     r14, rsi
0x180015ca5  lea     rbx, [rdx+rdx]
0x180015ca9  mov     [rsi+10h], rdx
0x180015cad  mov     r8, rbx; Size
0x180015cb0  mov     rdx, r9; Src
0x180015cb3  mov     rcx, r14; void *
0x180015cb6  call    memmove_0
0x180015cbb  mov     [rbx+r14], r13w
0x180015cc0  jmp     short loc_180015CCA
0x180015cc2  mov     rcx, rsi
0x180015cc5  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180015cca  mov     [rdi], bpl
0x180015ccd  cmp     qword ptr [rsi+18h], 7
0x180015cd2  jbe     short loc_180015CD7
0x180015cd4  mov     rsi, [rsi]
0x180015cd7  lea     r9, aUptoProductVer; "Upto product ver: %ws"
0x180015cde  mov     r8d, 783h
0x180015ce4  jmp     loc_180016228
0x180015ce9  lea     rdx, aMatchingtext; "-MatchingText"
0x180015cf0  mov     rcx, rbx; String1
0x180015cf3  call    wcscmp_0
0x180015cf8  test    eax, eax
0x180015cfa  jnz     short loc_180015D70
0x180015cfc  mov     r9, [r14+rsi*8+8]
0x180015d01  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180015d05  lea     rsi, [rdi+88h]
0x180015d0c  inc     rdx
0x180015d0f  cmp     [r9+rdx*2], r13w
0x180015d14  jnz     short loc_180015D0C
0x180015d16  cmp     rdx, [rsi+18h]
0x180015d1a  ja      short loc_180015D48
0x180015d1c  cmp     qword ptr [rsi+18h], 7
0x180015d21  jbe     short loc_180015D28
0x180015d23  mov     r14, [rsi]
0x180015d26  jmp     short loc_180015D2B
0x180015d28  mov     r14, rsi
0x180015d2b  lea     rbx, [rdx+rdx]
0x180015d2f  mov     [rsi+10h], rdx
0x180015d33  mov     r8, rbx; Size
0x180015d36  mov     rdx, r9; Src
0x180015d39  mov     rcx, r14; void *
0x180015d3c  call    memmove_0
0x180015d41  mov     [rbx+r14], r13w
0x180015d46  jmp     short loc_180015D50
0x180015d48  mov     rcx, rsi
0x180015d4b  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180015d50  mov     [rdi+1], bpl
0x180015d54  cmp     qword ptr [rsi+18h], 7
0x180015d59  jbe     short loc_180015D5E
0x180015d5b  mov     rsi, [rsi]
0x180015d5e  lea     r9, aMatchingTextWs; "Matching text: %ws"
0x180015d65  mov     r8d, 789h
0x180015d6b  jmp     loc_180016228
0x180015d70  lea     rdx, aMatchingregext_0; "-MatchingRegexText"
0x180015d77  mov     rcx, rbx; String1
0x180015d7a  call    wcscmp_0
0x180015d7f  test    eax, eax
0x180015d81  jnz     short loc_180015DF7
0x180015d83  mov     r9, [r14+rsi*8+8]
0x180015d88  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180015d8c  lea     rsi, [rdi+0A8h]
0x180015d93  inc     rdx
0x180015d96  cmp     [r9+rdx*2], r13w
0x180015d9b  jnz     short loc_180015D93
0x180015d9d  cmp     rdx, [rsi+18h]
0x180015da1  ja      short loc_180015DCF
0x180015da3  cmp     qword ptr [rsi+18h], 7
0x180015da8  jbe     short loc_180015DAF
0x180015daa  mov     r14, [rsi]
0x180015dad  jmp     short loc_180015DB2
0x180015daf  mov     r14, rsi
0x180015db2  lea     rbx, [rdx+rdx]
0x180015db6  mov     [rsi+10h], rdx
0x180015dba  mov     r8, rbx; Size
0x180015dbd  mov     rdx, r9; Src
0x180015dc0  mov     rcx, r14; void *
0x180015dc3  call    memmove_0
0x180015dc8  mov     [rbx+r14], r13w
0x180015dcd  jmp     short loc_180015DD7
0x180015dcf  mov     rcx, rsi
0x180015dd2  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180015dd7  mov     [rdi+2], bpl
0x180015ddb  cmp     qword ptr [rsi+18h], 7
0x180015de0  jbe     short loc_180015DE5
0x180015de2  mov     rsi, [rsi]
0x180015de5  lea     r9, aMatchingRegexT; "Matching regex text: %ws"
0x180015dec  mov     r8d, 78Fh
0x180015df2  jmp     loc_180016228
0x180015df7  lea     rdx, aEncoding; "-Encoding"
0x180015dfe  mov     rcx, rbx; String1
0x180015e01  call    wcscmp_0
0x180015e06  test    eax, eax
0x180015e08  jnz     short loc_180015E7F
0x180015e0a  mov     r9, [r14+rsi*8+8]
0x180015e0f  add     rdi, 0C8h
0x180015e16  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180015e1a  inc     rdx
0x180015e1d  cmp     [r9+rdx*2], r13w
0x180015e22  jnz     short loc_180015E1A
0x180015e24  cmp     rdx, [rdi+18h]
0x180015e28  ja      short loc_180015E56
0x180015e2a  cmp     qword ptr [rdi+18h], 7
0x180015e2f  jbe     short loc_180015E36
0x180015e31  mov     rsi, [rdi]
0x180015e34  jmp     short loc_180015E39
0x180015e36  mov     rsi, rdi
0x180015e39  lea     rbx, [rdx+rdx]
0x180015e3d  mov     [rdi+10h], rdx
0x180015e41  mov     r8, rbx; Size
0x180015e44  mov     rdx, r9; Src
0x180015e47  mov     rcx, rsi; void *
0x180015e4a  call    memmove_0
0x180015e4f  mov     [rbx+rsi], r13w
0x180015e54  jmp     short loc_180015E5E
0x180015e56  mov     rcx, rdi
0x180015e59  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180015e5e  cmp     qword ptr [rdi+18h], 7
0x180015e63  jbe     short loc_180015E68
0x180015e65  mov     rdi, [rdi]
0x180015e68  mov     [rsp+78h+var_58], rdi
0x180015e6d  lea     r9, aEncodingIsWs; "Encoding is: %ws"
0x180015e74  mov     r8d, 794h
0x180015e7a  jmp     loc_18001622D
0x180015e7f  lea     rdx, aCompanyname_0; "-CompanyName"
0x180015e86  mov     rcx, rbx; String1
0x180015e89  call    wcscmp_0
0x180015e8e  test    eax, eax
0x180015e90  jnz     short loc_180015F05
0x180015e92  mov     r9, [r14+rsi*8+8]
0x180015e97  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180015e9b  lea     rsi, [rdi+168h]
0x180015ea2  inc     rdx
0x180015ea5  cmp     [r9+rdx*2], r13w
0x180015eaa  jnz     short loc_180015EA2
0x180015eac  cmp     rdx, [rsi+18h]
0x180015eb0  ja      short loc_180015EDE
0x180015eb2  cmp     qword ptr [rsi+18h], 7
0x180015eb7  jbe     short loc_180015EBE
0x180015eb9  mov     r14, [rsi]
0x180015ebc  jmp     short loc_180015EC1
0x180015ebe  mov     r14, rsi
0x180015ec1  lea     rbx, [rdx+rdx]
0x180015ec5  mov     [rsi+10h], rdx
0x180015ec9  mov     r8, rbx; Size
  ... truncated ...
```
