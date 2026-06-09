# _AttributesFromBOE(AslFileMapping &,tagFILEATTRIBUTE *,unsigned __int64,FAR_MODE_FLAGS)

- ea: `0x1800e2500`
- end: `0x1800e3777`
- name: `?_AttributesFromBOE@@YAJAEAVAslFileMapping@@PEAUtagFILEATTRIBUTE@@_KW4FAR_MODE_FLAGS@@@Z`
- size: `4727`
- prototype: `__int64 __fastcall(const wchar_t ***, _DWORD *, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x18000d62c`
- `0x18004b1a0`
- `0x18004bb8c`
- `0x18004c020`
- `0x1800535ec`
- `0x1800e217c`
- `0x1800e2500`
- `0x1800e591c`
- `0x1800e5ec0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800e3080`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800e3080`
- `ntdll!RtlAllocateHeap` at `0x1800e2fc4`
- `ntdll!RtlAllocateHeap` at `0x1800e30bd`
- `ntdll!RtlAllocateHeap` at `0x1800e2fc4`
- `ntdll!RtlAllocateHeap` at `0x1800e30bd`
- `ntdll!RtlFreeHeap` at `0x1800e2b04`
- `ntdll!RtlFreeHeap` at `0x1800e2c53`
- `ntdll!RtlFreeHeap` at `0x1800e2cb4`
- `ntdll!RtlFreeHeap` at `0x1800e2e69`
- `ntdll!RtlFreeHeap` at `0x1800e2ecc`
- `ntdll!RtlFreeHeap` at `0x1800e2f2b`
- `ntdll!RtlFreeHeap` at `0x1800e2f86`
- `ntdll!RtlFreeHeap` at `0x1800e36ec`
- `ntdll!RtlFreeHeap` at `0x1800e370e`
- `ntdll!RtlFreeHeap` at `0x1800e372b`
- `ntdll!RtlFreeHeap` at `0x1800e3748`
- `ntdll!RtlFreeHeap` at `0x1800e2b04`
- `ntdll!RtlFreeHeap` at `0x1800e2c53`
- `ntdll!RtlFreeHeap` at `0x1800e2cb4`
- `ntdll!RtlFreeHeap` at `0x1800e2e69`
- `ntdll!RtlFreeHeap` at `0x1800e2ecc`
- `ntdll!RtlFreeHeap` at `0x1800e2f2b`
- `ntdll!RtlFreeHeap` at `0x1800e2f86`
- `ntdll!RtlFreeHeap` at `0x1800e36ec`
- `ntdll!RtlFreeHeap` at `0x1800e370e`
- `ntdll!RtlFreeHeap` at `0x1800e372b`
- `ntdll!RtlFreeHeap` at `0x1800e3748`

## string_xrefs

- `0x1800e36ac`: `StringCbCopyW failed [%x]`
- `0x1800e31bb`: `AeComputeProgramIdentityHash failed [%x]`
- `0x1800e25a1`: `_SetFileAttributeValue`
- `0x1800e3270`: `_SetFileAttributeValue`
- `0x1800e33d6`: `_SetFileAttributeValue`
- `0x1800e34f8`: `_SetFileAttributeValue`
- `0x1800e3617`: `_SetFileAttributeValue`
- `0x1800e2597`: `StringCbCopy failed to copy string attribute (index %d) [%x]`
- `0x1800e316a`: `StringCbCopy failed to copy string attribute (index %d) [%x]`

## pseudocode

```c
__int64 __fastcall _AttributesFromBOE(const wchar_t ***a1, _DWORD *a2, __int64 a3)
{
  const WCHAR **v5; // rcx
  _WORD *v6; // r15
  const WCHAR *v7; // rcx
  int v8; // r10d
  __int64 v9; // r14
  __int64 v10; // rax
  __int64 v11; // rdx
  const wchar_t *v12; // rcx
  _WORD *v13; // r8
  _WORD *v14; // rcx
  int v15; // r10d
  __int64 v16; // rax
  const wchar_t *v17; // rcx
  __int64 v18; // rdx
  _WORD *v19; // r8
  _WORD *v20; // rcx
  int v21; // r10d
  __int64 v22; // r8
  const wchar_t *v23; // rax
  __int64 v24; // rdx
  _WORD *v25; // r9
  _WORD *v26; // rcx
  int v27; // r10d
  __int64 v28; // r13
  const wchar_t *v29; // rax
  __int64 v30; // rdx
  _WORD *v31; // r8
  _WORD *v32; // rcx
  int v33; // r11d
  __int64 v34; // rax
  const wchar_t *v35; // rcx
  _WORD *v36; // r10
  _WORD *v37; // r9
  unsigned int v38; // ebx
  int FileKindDetail; // eax
  int Attribute; // eax
  int v41; // ebx
  const wchar_t ***v42; // r14
  int v43; // eax
  int v44; // eax
  const char *v45; // r9
  __int64 v46; // r8
  unsigned __int16 *v47; // r14
  int v48; // eax
  int v49; // ebx
  int v50; // eax
  int v51; // eax
  int v52; // eax
  const char *v53; // r9
  __int64 v54; // r8
  int v55; // ebx
  unsigned __int16 *v56; // rax
  int v57; // eax
  _WORD *v58; // r8
  const wchar_t *v59; // rbx
  wchar_t *v60; // rax
  __int64 v61; // r14
  SIZE_T v62; // r14
  _WORD *Heap; // rax
  unsigned __int64 v64; // r14
  __int64 v65; // rax
  _WORD *v66; // rdx
  _WORD *v67; // rcx
  __int64 v68; // r14
  int v69; // eax
  int v70; // r10d
  __int64 v71; // rax
  __int64 v72; // rdx
  _WORD *v73; // rcx
  _WORD *v74; // r8
  _WORD *v75; // rcx
  __int64 v76; // rdx
  const wchar_t *v77; // rbx
  __int64 v78; // rdx
  int v79; // r10d
  __int64 v80; // rax
  _WORD *v81; // r8
  const wchar_t *v82; // rcx
  __int64 v83; // rdx
  _WORD *v84; // rcx
  __int64 v85; // rdx
  int v86; // r10d
  __int64 v87; // rax
  _WORD *v88; // r8
  const wchar_t *v89; // rcx
  __int64 v90; // rdx
  _WORD *v91; // rcx
  __int64 v92; // rax
  int v93; // r9d
  __int64 v94; // rax
  _WORD *v95; // r8
  _WORD *v96; // rcx
  __int64 v98; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v99; // [rsp+30h] [rbp-D0h]
  PVOID v100; // [rsp+38h] [rbp-C8h] BYREF
  PVOID v101; // [rsp+40h] [rbp-C0h]
  PVOID v102; // [rsp+48h] [rbp-B8h]
  PVOID v103; // [rsp+50h] [rbp-B0h] BYREF
  int v104; // [rsp+58h] [rbp-A8h] BYREF
  PVOID P; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v106; // [rsp+68h] [rbp-98h] BYREF
  __int64 v107; // [rsp+70h] [rbp-90h]
  _QWORD v108[5]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v109[12]; // [rsp+A0h] [rbp-60h] BYREF

  v107 = a3;
  v104 = 0;
  memset_0(v109, 0, 0x5Au);
  v102 = 0;
  v5 = *a1;
  v6 = 0;
  P = 0;
  v101 = 0;
  v103 = 0;
  v7 = *v5;
  v100 = 0;
  v106 = 0;
  if ( (unsigned int)_IsOsComponent(v7) )
  {
    if ( !a2 )
      return 0;
    v8 = dword_180119B04;
    v9 = 260;
    if ( (unsigned int)dword_180119B04 <= 2 )
    {
      a2[4896] = 3145776;
    }
    else if ( dword_180119B04 == 3 )
    {
      *((_QWORD *)a2 + 2448) = 0x30003000300030LL;
    }
    else
    {
      if ( dword_180119B04 != 4 )
        goto LABEL_17;
      v10 = 45;
      v11 = 260;
      v12 = L"0000f519feec486de87ed73cb92d3cac802400000000";
      v13 = a2 + 4896;
      do
      {
        if ( !v10 )
          break;
        if ( !*v12 )
          break;
        *v13++ = *v12++;
        --v10;
        --v11;
      }
      while ( v11 );
      v14 = v13 - 1;
      if ( v11 )
        v14 = v13;
      *v14 = 0;
      if ( !v11 )
      {
        AslLogCallPrintf(
          1,
          "_SetFileAttributeValue",
          3178,
          "StringCbCopy failed to copy string attribute (index %d) [%x]",
          36,
          -2147024774);
        goto LABEL_17;
      }
    }
    a2[5026] = 36;
    a2[5027] = v8;
    a2[5028] = 1;
LABEL_17:
    v15 = dword_180119B1C;
    if ( (unsigned int)dword_180119B1C <= 2 )
    {
      a2[5032] = 6881357;
    }
    else if ( dword_180119B1C == 3 )
    {
      *((_QWORD *)a2 + 2516) = 0x7200630069004DLL;
    }
    else
    {
      if ( dword_180119B1C != 4 )
        goto LABEL_31;
      v16 = 35;
      v17 = L"Microsoft Windows Operating System";
      v18 = 260;
      v19 = a2 + 5032;
      do
      {
        if ( !v16 )
          break;
        if ( !*v17 )
          break;
        *v19++ = *v17++;
        --v16;
        --v18;
      }
      while ( v18 );
      v20 = v19 - 1;
      if ( v18 )
        v20 = v19;
      *v20 = 0;
      if ( !v18 )
      {
        AslLogCallPrintf(
          1,
          "_SetFileAttributeValue",
          3178,
          "StringCbCopy failed to copy string attribute (index %d) [%x]",
          37,
          -2147024774);
        goto LABEL_31;
      }
    }
    a2[5162] = 37;
    a2[5163] = v15;
    a2[5164] = 1;
LABEL_31:
    v21 = dword_180119B34;
    if ( (unsigned int)dword_180119B34 <= 2 )
    {
      a2[5168] = 6881357;
    }
    else if ( dword_180119B34 == 3 )
    {
      *((_QWORD *)a2 + 2584) = 0x7200630069004DLL;
    }
    else
    {
      if ( dword_180119B34 != 4 )
        goto LABEL_45;
      v22 = 22;
      v23 = L"Microsoft Corporation";
      v24 = 260;
      v25 = a2 + 5168;
      do
      {
        if ( !v22 )
          break;
        if ( !*v23 )
          break;
        *v25++ = *v23++;
        --v22;
        --v24;
      }
      while ( v24 );
      v26 = v25 - 1;
      if ( v24 )
        v26 = v25;
      *v26 = 0;
      if ( !v24 )
      {
        AslLogCallPrintf(
          1,
          "_SetFileAttributeValue",
          3178,
          "StringCbCopy failed to copy string attribute (index %d) [%x]",
          38,
          -2147024774);
        goto LABEL_45;
      }
    }
    a2[5298] = 38;
    a2[5299] = v21;
    a2[5300] = 1;
LABEL_45:
    v27 = dword_180119B4C;
    if ( (unsigned int)dword_180119B4C <= 2 )
    {
      a2[5304] = 3014704;
    }
    else if ( dword_180119B4C == 3 )
    {
      *((_QWORD *)a2 + 2652) = 0x2E0030002E0030LL;
    }
    else
    {
      if ( dword_180119B4C != 4 )
      {
LABEL_59:
        v33 = dword_180119B64;
        if ( (unsigned int)dword_180119B64 <= 2 )
        {
          a2[5440] = *(_DWORD *)L"0";
          goto LABEL_72;
        }
        if ( dword_180119B64 == 3 )
        {
          *((_QWORD *)a2 + 2720) = *(_QWORD *)L"0";
          goto LABEL_72;
        }
        if ( dword_180119B64 == 4 )
        {
          v34 = 2;
          v35 = L"0";
          v36 = a2 + 5440;
          do
          {
            if ( !v34 )
              break;
            if ( !*v35 )
              break;
            *v36++ = *v35++;
            --v34;
            --v9;
          }
          while ( v9 );
          v37 = v36 - 1;
          if ( v9 )
            v37 = v36;
          *v37 = 0;
          if ( !v9 )
          {
            AslLogCallPrintf(
              1,
              "_SetFileAttributeValue",
              3178,
              "StringCbCopy failed to copy string attribute (index %d) [%x]",
              40,
              -2147024774);
            return 0;
          }
LABEL_72:
          a2[5570] = 40;
          a2[5571] = v33;
          a2[5572] = 1;
        }
        return 0;
      }
      v28 = 8;
      v29 = L"0.0.0.0";
      v30 = 260;
      v31 = a2 + 5304;
      do
      {
        if ( !v28 )
          break;
        if ( !*v29 )
          break;
        *v31++ = *v29++;
        --v28;
        --v30;
      }
      while ( v30 );
      v32 = v31 - 1;
      if ( v30 )
        v32 = v31;
      *v32 = 0;
      if ( !v30 )
      {
        AslLogCallPrintf(
          1,
          "_SetFileAttributeValue",
          3178,
          "StringCbCopy failed to copy string attribute (index %d) [%x]",
          39,
          -2147024774);
        goto LABEL_59;
      }
    }
    a2[5434] = 39;
    a2[5435] = v27;
    a2[5436] = 1;
    goto LABEL_59;
  }
  FileKindDetail = AslFileMappingGetFileKindDetail(&v104, *a1);
  if ( FileKindDetail < 0 )
  {
    v38 = FileKindDetail | 0x10000000;
    AslLogCallPrintf(
      1,
      "_AttributesFromBOE",
      2211,
      "AslFileMapping::GetFileKindDetails failed [%x]",
      FileKindDetail | 0x10000000);
    return v38;
  }
  v99 = 0;
  if ( v104 <= 4 )
  {
LABEL_147:
    v59 = **a1;
    v60 = wcsrchr(v59, 0x5Cu);
    if ( v60 )
      v59 = v60 + 1;
    v61 = -1;
    do
      ++v61;
    while ( v59[v61] );
    v62 = 2 * v61 + 2;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v62);
    v102 = Heap;
    v58 = Heap;
    if ( !Heap )
    {
      AslLogCallPrintf(1, "_AttributesFromBOE", 2341, "Failed to alloc name string");
      v38 = -2147024882;
LABEL_251:
      v47 = v99;
      goto LABEL_252;
    }
    v64 = v62 >> 1;
    if ( !v64 )
    {
      v38 = -2147024809;
      goto LABEL_249;
    }
    if ( v64 > 0x7FFFFFFF )
    {
      v38 = -2147024809;
      *Heap = 0;
LABEL_249:
      v53 = "StringCbCopyW failed [%x]";
      v54 = 2349;
      goto LABEL_250;
    }
    v65 = 2147483646;
    v66 = v58;
    do
    {
      if ( !v65 )
        break;
      if ( !*v59 )
        break;
      *v66++ = *v59++;
      --v65;
      --v64;
    }
    while ( v64 );
    v67 = v66 - 1;
    v38 = v64 == 0 ? 0x8007007A : 0;
    if ( v64 )
      v67 = v66;
    *v67 = 0;
    if ( !v64 )
      goto LABEL_249;
LABEL_163:
    v68 = 260;
    if ( (v107 & 0x1000000000LL) != 0 )
    {
      v108[1] = v101;
      v108[3] = v99;
      v108[0] = v58;
      v108[2] = v6;
      v69 = AeComputeProgramIdentityHash(v108, v109);
      v38 = v69;
      if ( v69 < 0 )
      {
        LODWORD(v98) = v69;
        AslLogCallPrintf(1, "_AttributesFromBOE", 2368, "AeComputeProgramIdentityHash failed [%x]", v98);
        goto LABEL_251;
      }
      HIWORD(v109[0]) = 54;
      if ( a2 )
      {
        v70 = dword_180119B04;
        if ( (unsigned int)dword_180119B04 <= 2 )
        {
          a2[4896] = v109[0];
          goto LABEL_180;
        }
        if ( dword_180119B04 == 3 )
        {
          *((_QWORD *)a2 + 2448) = v109[0];
          goto LABEL_180;
        }
        if ( dword_180119B04 == 4 )
        {
          v71 = 45;
          v72 = 260;
          v73 = v109;
          v74 = a2 + 4896;
          do
          {
            if ( !v71 )
              break;
            if ( !*v73 )
              break;
            *v74++ = *v73++;
            --v71;
            --v72;
          }
          while ( v72 );
          v75 = v74 - 1;
          if ( v72 )
            v75 = v74;
          *v75 = 0;
          if ( !v72 )
          {
            AslLogCallPrintf(
              1,
              "_SetFileAttributeValue",
              3178,
              "StringCbCopy failed to copy string attribute (index %d) [%x]",
              36,
              -2147024774);
            goto LABEL_181;
          }
LABEL_180:
          a2[5026] = 36;
          a2[5027] = v70;
          a2[5028] = 1;
        }
      }
    }
LABEL_181:
    if ( !v102 || !*(_WORD *)v102 )
    {
      AslLogCallPrintf(1, "_AttributesFromBOE", 2400, "Failed to get a value to use for BOE App name.");
      v38 = -2147467259;
      goto LABEL_251;
    }
    v76 = -1;
    do
      ++v76;
    while ( *((_WORD *)v102 + v76) );
    _SetFileAttributeValue(v102, (unsigned int)(2 * v76 + 2), 37, a2);
    v77 = &dword_1800F6C3C;
    if ( v101 && *(_WORD *)v101 )
    {
      v78 = -1;
      do
        ++v78;
      while ( *((_WORD *)v102 + v78) );
      _SetFileAttributeValue(v102, (unsigned int)(2 * v78 + 2), 38, a2);
    }
    else if ( a2 )
    {
      v79 = dword_180119B34;
      if ( (unsigned int)dword_180119B34 <= 2 )
      {
        a2[5168] = 0;
      }
      else if ( dword_180119B34 == 3 )
      {
        *((_QWORD *)a2 + 2584) = 0x3000000000LL;
      }
      else
      {
        if ( dword_180119B34 != 4 )
          goto LABEL_205;
        v80 = 1;
        v81 = a2 + 5168;
        v82 = &dword_1800F6C3C;
        v83 = 260;
        do
        {
          if ( !v80 )
            break;
          if ( !*v82 )
            break;
          *v81++ = *v82++;
          --v80;
          --v83;
        }
        while ( v83 );
        v84 = v81 - 1;
        if ( v83 )
          v84 = v81;
        *v84 = 0;
        if ( !v83 )
        {
          AslLogCallPrintf(
            1,
            "_SetFileAttributeValue",
            3178,
            "StringCbCopy failed to copy string attribute (index %d) [%x]",
            38,
            -2147024774);
          goto LABEL_205;
        }
      }
      a2[5298] = 38;
      a2[5299] = v79;
      a2[5300] = 1;
    }
LABEL_205:
    if ( v6 && *v6 )
    {
      v85 = -1;
      do
        ++v85;
      while ( v6[v85] );
      _SetFileAttributeValue(v6, (unsigned int)(2 * v85 + 2), 39, a2);
    }
    else if ( a2 )
    {
      v86 = dword_180119B4C;
      if ( (unsigned int)dword_180119B4C <= 2 )
      {
        a2[5304] = 0;
      }
      else if ( dword_180119B4C == 3 )
      {
        *((_QWORD *)a2 + 2652) = 0x3000000000LL;
      }
      else
      {
        if ( dword_180119B4C != 4 )
          goto LABEL_225;
        v87 = 1;
        v88 = a2 + 5304;
        v89 = &dword_1800F6C3C;
        v90 = 260;
        do
        {
          if ( !v87 )
            break;
          if ( !*v89 )
            break;
          *v88++ = *v89++;
          --v87;
          --v90;
        }
        while ( v90 );
        v91 = v88 - 1;
        if ( v90 )
          v91 = v88;
        *v91 = 0;
        if ( !v90 )
        {
          AslLogCallPrintf(
            1,
            "_SetFileAttributeValue",
            3178,
            "StringCbCopy failed to copy string attribute (index %d) [%x]",
            39,
            -2147024774);
          goto LABEL_225;
        }
      }
      a2[5434] = 39;
      a2[5435] = v86;
      a2[5436] = 1;
    }
LABEL_225:
    if ( v99 && *v99 )
    {
      v47 = v99;
      v92 = -1;
      do
        ++v92;
      while ( v99[v92] );
      _SetFileAttributeValue(v99, (unsigned int)(2 * v92 + 2), 40, a2);
      goto LABEL_246;
    }
    if ( a2 )
    {
      v93 = dword_180119B64;
      if ( (unsigned int)dword_180119B64 <= 2 )
      {
        a2[5440] = 0;
        goto LABEL_244;
      }
      if ( dword_180119B64 == 3 )
      {
        *((_QWORD *)a2 + 2720) = 0x3000000000LL;
        goto LABEL_244;
      }
      if ( dword_180119B64 == 4 )
      {
        v94 = 1;
        v95 = a2 + 5440;
        do
        {
          if ( !v94 )
            break;
          if ( !*v77 )
            break;
          *v95++ = *v77++;
          --v94;
          --v68;
        }
        while ( v68 );
        v96 = v95 - 1;
        if ( v68 )
          v96 = v95;
        *v96 = 0;
        if ( !v68 )
        {
          AslLogCallPrintf(
            1,
            "_SetFileAttributeValue",
            3178,
            "StringCbCopy failed to copy string attribute (index %d) [%x]",
            40,
            -2147024774);
          v47 = v99;
LABEL_246:
          v38 = 0;
          goto LABEL_252;
        }
LABEL_244:
        v47 = v99;
        a2[5570] = 40;
        a2[5571] = v93;
        a2[5572] = 1;
        goto LABEL_246;
      }
    }
    v47 = v99;
    goto LABEL_246;
  }
  Attribute = AslFileMapping::GetAttribute(a1, 0, 8);
  v41 = Attribute;
  if ( Attribute >= 0 )
  {
    v42 = a1 + 1;
    v41 = AslFileAttributeToString(&P, a1 + 1, 8);
    if ( v41 >= 0 )
    {
      v102 = P;
      if ( P && !*(_WORD *)P )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
        v102 = 0;
      }
      goto LABEL_85;
    }
    v102 = P;
  }
  else
  {
    if ( Attribute != -1073741275 )
      AslLogCallPrintf(
        1,
        "AslFileMapping::AttributeToString",
        2669,
        "Failed to get attribute index %u [%x]",
        8,
        Attribute);
    v42 = a1 + 1;
  }
  if ( v41 != -1073741275 )
  {
    v45 = "AslFileMapping::GetAttribute failed to get PRODUCT_NAME [%x]";
    v46 = 2246;
    goto LABEL_97;
  }
LABEL_85:
  v43 = AslFileMapping::GetAttribute(a1, 0, 7);
  v41 = v43;
  if ( v43 >= 0 )
  {
    v41 = AslFileAttributeToString(&v103, v42, 7);
    v101 = v103;
    if ( v41 >= 0 )
    {
      if ( !v103 || *(_WORD *)v103 )
        goto LABEL_106;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v103);
      v101 = 0;
      v103 = 0;
LABEL_89:
      v44 = AslFileMapping::GetAttribute(a1, 0, 6);
      v41 = v44;
      if ( v44 >= 0 )
      {
        v41 = AslFileAttributeToString(&v103, v42, 6);
        v101 = v103;
        if ( v41 >= 0 )
        {
          if ( v103 && !*(_WORD *)v103 )
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v103);
            v101 = 0;
          }
          goto LABEL_106;
        }
      }
      else if ( v44 != -1073741275 )
      {
        AslLogCallPrintf(1, "AslFileMapping::AttributeToString", 2669, "Failed to get attribute index %u [%x]", 6, v44);
      }
      if ( v41 != -1073741275 )
        goto LABEL_93;
LABEL_106:
      v48 = AslFileMapping::GetAttribute(a1, 0, 5);
      v49 = v48;
      if ( v48 >= 0 )
      {
        v49 = AslFileAttributeToString(&v100, v42, 5);
        v6 = v100;
        if ( v49 >= 0 )
        {
          if ( !v100 || *(_WORD *)v100 )
            goto LABEL_139;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v100);
          v6 = 0;
          v100 = 0;
          goto LABEL_110;
        }
      }
      else
      {
        if ( v48 == -1073741275 )
          goto LABEL_110;
        AslLogCallPrintf(1, "AslFileMapping::AttributeToString", 2669, "Failed to get attribute index %u [%x]", 5, v48);
      }
      if ( v49 != -1073741275 )
        goto LABEL_122;
LABEL_110:
      v50 = AslFileMapping::GetAttribute(a1, 0, 9);
      v49 = v50;
      if ( v50 >= 0 )
      {
        v49 = AslFileAttributeToString(&v100, v42, 9);
        v6 = v100;
        if ( v49 >= 0 )
        {
          if ( !v100 || *(_WORD *)v100 )
            goto LABEL_139;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v100);
          v6 = 0;
          v100 = 0;
LABEL_114:
          v51 = AslFileMapping::GetAttribute(a1, 0, 4);
          v49 = v51;
          if ( v51 >= 0 )
          {
            v49 = AslFileAttributeToString(&v100, v42, 4);
            v6 = v100;
            if ( v49 >= 0 )
            {
              if ( !v100 || *(_WORD *)v100 )
                goto LABEL_139;
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v100);
              v6 = 0;
              v100 = 0;
LABEL_118:
              v52 = AslFileMapping::GetAttribute(a1, 0, 3);
              v49 = v52;
              if ( v52 >= 0 )
              {
                v49 = AslFileAttributeToString(&v100, v42, 3);
                v6 = v100;
                if ( v49 >= 0 )
                {
                  if ( v100 && !*(_WORD *)v100 )
                  {
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v100);
                    v6 = 0;
                  }
                  goto LABEL_139;
                }
              }
              else if ( v52 != -1073741275 )
              {
                AslLogCallPrintf(
                  1,
                  "AslFileMapping::AttributeToString",
                  2669,
                  "Failed to get attribute index %u [%x]",
                  3,
                  v52);
              }
              if ( v49 != -1073741275 )
                goto LABEL_122;
LABEL_139:
              v55 = AslFileMapping::GetAttribute(a1, &v106, 24);
              if ( v55 < 0 )
              {
                if ( v55 != -1073741275 )
                {
                  v38 = v55 | 0x10000000;
                  v53 = "AslFileMapping::GetAttribute failed to get VER_LANGUAGE [%x]";
                  v54 = 2325;
                  goto LABEL_250;
                }
              }
              else
              {
                v56 = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x16u);
                v99 = v56;
                v47 = v56;
                if ( !v56 )
                {
                  AslLogCallPrintf(1, "_AttributesFromBOE", 2310, "Failed to alloc language string");
                  v38 = -2147024882;
                  goto LABEL_252;
                }
                v57 = StringCchPrintfW(v56, 0xBu, L"%d", *(unsigned int *)(v106 + 16));
                v38 = v57;
                if ( v57 < 0 )
                {
                  AslLogCallPrintf(1, "_AttributesFromBOE", 2318, "StringCchPrintfW failed [%x]", v57);
                  goto LABEL_252;
                }
              }
              v58 = v102;
              if ( v102 )
                goto LABEL_163;
              goto LABEL_147;
            }
          }
          else if ( v51 != -1073741275 )
          {
            AslLogCallPrintf(
              1,
              "AslFileMapping::AttributeToString",
              2669,
              "Failed to get attribute index %u [%x]",
              4,
              v51);
          }
          if ( v49 == -1073741275 )
            goto LABEL_118;
LABEL_122:
          v38 = v49 | 0x10000000;
          v53 = "AslFileMapping::GetAttribute failed [%x]";
          v54 = 2296;
LABEL_250:
          LODWORD(v98) = v38;
          AslLogCallPrintf(1, "_AttributesFromBOE", v54, v53, v98);
          goto LABEL_251;
        }
      }
      else if ( v50 != -1073741275 )
      {
        AslLogCallPrintf(1, "AslFileMapping::AttributeToString", 2669, "Failed to get attribute index %u [%x]", 9, v50);
      }
      if ( v49 != -1073741275 )
        goto LABEL_122;
      goto LABEL_114;
    }
  }
  else if ( v43 != -1073741275 )
  {
    AslLogCallPrintf(1, "AslFileMapping::AttributeToString", 2669, "Failed to get attribute index %u [%x]", 7, v43);
  }
  if ( v41 == -1073741275 )
    goto LABEL_89;
LABEL_93:
  v45 = "AslFileMapping::GetAttribute failed (BOE Publisher) [%x]";
  v46 = 2265;
LABEL_97:
  v38 = v41 | 0x10000000;
  LODWORD(v98) = v38;
  AslLogCallPrintf(1, "_AttributesFromBOE", v46, v45, v98);
  v47 = 0;
LABEL_252:
  if ( v102 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v102);
  if ( v101 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v101);
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( v47 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v47);
  return v38;
}

```

## disassembly

```asm
0x1800e2500  mov     [rsp-8+arg_10], rbx
0x1800e2505  push    rbp
0x1800e2506  push    rsi
0x1800e2507  push    rdi
0x1800e2508  push    r12
0x1800e250a  push    r13
0x1800e250c  push    r14
0x1800e250e  push    r15
0x1800e2510  lea     rbp, [rsp-10h]
0x1800e2515  sub     rsp, 110h
0x1800e251c  mov     rax, cs:__security_cookie
0x1800e2523  xor     rax, rsp
0x1800e2526  mov     [rbp+40h+var_40], rax
0x1800e252a  xor     ebx, ebx
0x1800e252c  mov     [rsp+140h+var_D0], r8
0x1800e2531  mov     rdi, rdx
0x1800e2534  mov     [rsp+140h+var_E8], ebx
0x1800e2538  mov     r12, rcx
0x1800e253b  xor     edx, edx; Val
0x1800e253d  lea     rcx, [rbp+40h+var_A0]; void *
0x1800e2541  lea     r8d, [rbx+5Ah]; Size
0x1800e2545  call    memset_0
0x1800e254a  mov     ecx, ebx
0x1800e254c  mov     [rsp+140h+var_F8], rbx
0x1800e2551  mov     rcx, [r12]
0x1800e2555  mov     r15d, ebx
0x1800e2558  mov     [rsp+140h+P], rbx
0x1800e255d  mov     [rsp+140h+var_100], rbx
0x1800e2562  mov     [rsp+140h+var_F0], rbx
0x1800e2567  mov     rcx, [rcx]; lpFileName
0x1800e256a  mov     [rsp+140h+var_108], rbx
0x1800e256f  mov     [rsp+140h+var_D8], rbx
0x1800e2574  call    ?_IsOsComponent@@YAHPEBG@Z; _IsOsComponent(ushort const *)
0x1800e2579  xor     r11d, r11d
0x1800e257c  test    eax, eax
0x1800e257e  jz      loc_1800E2A16
0x1800e2584  test    rdi, rdi
0x1800e2587  jz      loc_1800E2A0E
0x1800e258d  mov     r10d, cs:dword_180119B04
0x1800e2594  lea     esi, [rbx+1]
0x1800e2597  lea     r12, aStringcbcopyFa; "StringCbCopy failed to copy string attr"...
0x1800e259e  mov     ecx, r10d
0x1800e25a1  lea     r15, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e25a8  mov     r14d, 104h
0x1800e25ae  mov     r13d, 8007007Ah
0x1800e25b4  mov     ebx, 0C6Ah
0x1800e25b9  test    r10d, r10d
0x1800e25bc  jz      loc_1800E266E
0x1800e25c2  sub     ecx, esi
0x1800e25c4  jz      loc_1800E266E
0x1800e25ca  sub     ecx, esi
0x1800e25cc  jz      loc_1800E266E
0x1800e25d2  sub     ecx, esi
0x1800e25d4  jz      loc_1800E265B
0x1800e25da  cmp     ecx, esi
0x1800e25dc  jnz     loc_1800E268F
0x1800e25e2  lea     eax, [rsi+2Ch]
0x1800e25e5  mov     edx, r14d
0x1800e25e8  lea     rcx, a0000f519feec48; "0000f519feec486de87ed73cb92d3cac8024000"...
0x1800e25ef  lea     r8, [rdi+4C80h]
0x1800e25f6  test    rax, rax
0x1800e25f9  jz      short loc_1800E2619
0x1800e25fb  movzx   r9d, word ptr [rcx]
0x1800e25ff  test    r9w, r9w
0x1800e2603  jz      short loc_1800E2619
0x1800e2605  mov     [r8], r9w
0x1800e2609  add     rcx, 2
0x1800e260d  add     r8, 2
0x1800e2611  sub     rax, rsi
0x1800e2614  sub     rdx, rsi
0x1800e2617  jnz     short loc_1800E25F6
0x1800e2619  mov     rax, rdx
0x1800e261c  lea     rcx, [r8-2]
0x1800e2620  neg     rax
0x1800e2623  sbb     r9d, r9d
0x1800e2626  not     r9d
0x1800e2629  and     r9d, r13d
0x1800e262c  test    rdx, rdx
0x1800e262f  cmovnz  rcx, r8
0x1800e2633  mov     [rcx], r11w
0x1800e2637  jnz     short loc_1800E2678
0x1800e2639  mov     [rsp+140h+var_118], r9d
0x1800e263e  mov     r8, rbx
0x1800e2641  mov     r9, r12
0x1800e2644  mov     dword ptr [rsp+140h+var_120], 24h ; '$'
0x1800e264c  mov     rdx, r15
0x1800e264f  mov     ecx, esi
0x1800e2651  call    AslLogCallPrintf
0x1800e2656  xor     r11d, r11d
0x1800e2659  jmp     short loc_1800E268F
0x1800e265b  mov     rax, 30003000300030h
0x1800e2665  mov     [rdi+4C80h], rax
0x1800e266c  jmp     short loc_1800E2678
0x1800e266e  mov     dword ptr [rdi+4C80h], 300030h
0x1800e2678  mov     dword ptr [rdi+4E88h], 24h ; '$'
0x1800e2682  mov     [rdi+4E8Ch], r10d
0x1800e2689  mov     [rdi+4E90h], esi
0x1800e268f  mov     r10d, cs:dword_180119B1C
0x1800e2696  mov     rax, 7200630069004Dh
0x1800e26a0  mov     ecx, r10d
0x1800e26a3  test    r10d, r10d
0x1800e26a6  jz      loc_1800E2750
0x1800e26ac  sub     ecx, esi
0x1800e26ae  jz      loc_1800E2750
0x1800e26b4  sub     ecx, esi
0x1800e26b6  jz      loc_1800E2750
0x1800e26bc  sub     ecx, esi
0x1800e26be  jz      loc_1800E2747
0x1800e26c4  cmp     ecx, esi
0x1800e26c6  jnz     loc_1800E2771
0x1800e26cc  mov     eax, 23h ; '#'
0x1800e26d1  lea     rcx, aMicrosoftWindo; "Microsoft Windows Operating System"
0x1800e26d8  mov     rdx, r14
0x1800e26db  lea     r8, [rdi+4EA0h]
0x1800e26e2  test    rax, rax
0x1800e26e5  jz      short loc_1800E2705
0x1800e26e7  movzx   r9d, word ptr [rcx]
0x1800e26eb  test    r9w, r9w
0x1800e26ef  jz      short loc_1800E2705
0x1800e26f1  mov     [r8], r9w
0x1800e26f5  add     rcx, 2
0x1800e26f9  add     r8, 2
0x1800e26fd  sub     rax, rsi
0x1800e2700  sub     rdx, rsi
0x1800e2703  jnz     short loc_1800E26E2
0x1800e2705  mov     rax, rdx
0x1800e2708  lea     rcx, [r8-2]
0x1800e270c  neg     rax
0x1800e270f  sbb     r9d, r9d
0x1800e2712  not     r9d
0x1800e2715  and     r9d, r13d
0x1800e2718  test    rdx, rdx
0x1800e271b  cmovnz  rcx, r8
0x1800e271f  mov     [rcx], r11w
0x1800e2723  jnz     short loc_1800E275A
0x1800e2725  mov     [rsp+140h+var_118], r9d
0x1800e272a  mov     r8, rbx
0x1800e272d  mov     r9, r12
0x1800e2730  mov     dword ptr [rsp+140h+var_120], 25h ; '%'
0x1800e2738  mov     rdx, r15
0x1800e273b  mov     ecx, esi
0x1800e273d  call    AslLogCallPrintf
0x1800e2742  xor     r11d, r11d
0x1800e2745  jmp     short loc_1800E2771
0x1800e2747  mov     [rdi+4EA0h], rax
0x1800e274e  jmp     short loc_1800E275A
0x1800e2750  mov     dword ptr [rdi+4EA0h], 69004Dh
0x1800e275a  mov     dword ptr [rdi+50A8h], 25h ; '%'
0x1800e2764  mov     [rdi+50ACh], r10d
0x1800e276b  mov     [rdi+50B0h], esi
0x1800e2771  mov     r10d, cs:dword_180119B34
0x1800e2778  mov     ecx, r10d
0x1800e277b  test    r10d, r10d
0x1800e277e  jz      loc_1800E2831
0x1800e2784  sub     ecx, esi
0x1800e2786  jz      loc_1800E2831
0x1800e278c  sub     ecx, esi
0x1800e278e  jz      loc_1800E2831
0x1800e2794  sub     ecx, esi
0x1800e2796  jz      loc_1800E281E
0x1800e279c  cmp     ecx, esi
0x1800e279e  jnz     loc_1800E2852
0x1800e27a4  mov     r8d, 16h
0x1800e27aa  lea     rax, aMicrosoftCorpo; "Microsoft Corporation"
0x1800e27b1  mov     rdx, r14
0x1800e27b4  lea     r9, [rdi+50C0h]
0x1800e27bb  test    r8, r8
0x1800e27be  jz      short loc_1800E27DC
0x1800e27c0  movzx   ecx, word ptr [rax]
0x1800e27c3  test    cx, cx
0x1800e27c6  jz      short loc_1800E27DC
0x1800e27c8  mov     [r9], cx
0x1800e27cc  add     rax, 2
0x1800e27d0  add     r9, 2
0x1800e27d4  sub     r8, rsi
0x1800e27d7  sub     rdx, rsi
0x1800e27da  jnz     short loc_1800E27BB
0x1800e27dc  mov     rax, rdx
0x1800e27df  lea     rcx, [r9-2]
0x1800e27e3  neg     rax
0x1800e27e6  sbb     r8d, r8d
0x1800e27e9  not     r8d
0x1800e27ec  and     r8d, r13d
0x1800e27ef  test    rdx, rdx
0x1800e27f2  cmovnz  rcx, r9
0x1800e27f6  mov     [rcx], r11w
0x1800e27fa  jnz     short loc_1800E283B
0x1800e27fc  mov     [rsp+140h+var_118], r8d
0x1800e2801  mov     r9, r12
0x1800e2804  mov     r8, rbx
0x1800e2807  mov     dword ptr [rsp+140h+var_120], 26h ; '&'
0x1800e280f  mov     rdx, r15
0x1800e2812  mov     ecx, esi
0x1800e2814  call    AslLogCallPrintf
0x1800e2819  xor     r11d, r11d
0x1800e281c  jmp     short loc_1800E2852
0x1800e281e  mov     rax, 7200630069004Dh
0x1800e2828  mov     [rdi+50C0h], rax
0x1800e282f  jmp     short loc_1800E283B
0x1800e2831  mov     dword ptr [rdi+50C0h], 69004Dh
0x1800e283b  mov     dword ptr [rdi+52C8h], 26h ; '&'
0x1800e2845  mov     [rdi+52CCh], r10d
0x1800e284c  mov     [rdi+52D0h], esi
0x1800e2852  mov     r10d, cs:dword_180119B4C
0x1800e2859  mov     ecx, r10d
0x1800e285c  test    r10d, r10d
0x1800e285f  jz      loc_1800E2915
0x1800e2865  sub     ecx, esi
0x1800e2867  jz      loc_1800E2915
0x1800e286d  sub     ecx, esi
0x1800e286f  jz      loc_1800E2915
0x1800e2875  sub     ecx, esi
0x1800e2877  jz      loc_1800E2902
0x1800e287d  cmp     ecx, esi
0x1800e287f  jnz     loc_1800E2936
0x1800e2885  mov     r13d, 8
0x1800e288b  lea     rax, a0000; "0.0.0.0"
0x1800e2892  mov     rdx, r14
0x1800e2895  lea     r8, [rdi+52E0h]
0x1800e289c  test    r13, r13
0x1800e289f  jz      short loc_1800E28BD
0x1800e28a1  movzx   ecx, word ptr [rax]
0x1800e28a4  test    cx, cx
0x1800e28a7  jz      short loc_1800E28BD
0x1800e28a9  mov     [r8], cx
0x1800e28ad  add     rax, 2
0x1800e28b1  add     r8, 2
0x1800e28b5  sub     r13, rsi
0x1800e28b8  sub     rdx, rsi
0x1800e28bb  jnz     short loc_1800E289C
0x1800e28bd  mov     rax, rdx
0x1800e28c0  lea     rcx, [r8-2]
0x1800e28c4  neg     rax
0x1800e28c7  mov     r13d, 8007007Ah
0x1800e28cd  sbb     r9d, r9d
0x1800e28d0  not     r9d
0x1800e28d3  and     r9d, r13d
0x1800e28d6  test    rdx, rdx
0x1800e28d9  cmovnz  rcx, r8
0x1800e28dd  mov     [rcx], r11w
0x1800e28e1  jnz     short loc_1800E291F
0x1800e28e3  mov     [rsp+140h+var_118], r9d
0x1800e28e8  mov     r8, rbx
0x1800e28eb  mov     r9, r12
0x1800e28ee  mov     dword ptr [rsp+140h+var_120], 27h ; '''
0x1800e28f6  mov     rdx, r15
0x1800e28f9  mov     ecx, esi
0x1800e28fb  call    AslLogCallPrintf
0x1800e2900  jmp     short loc_1800E2936
0x1800e2902  mov     rax, 2E0030002E0030h
0x1800e290c  mov     [rdi+52E0h], rax
0x1800e2913  jmp     short loc_1800E291F
0x1800e2915  mov     dword ptr [rdi+52E0h], 2E0030h
0x1800e291f  mov     dword ptr [rdi+54E8h], 27h ; '''
0x1800e2929  mov     [rdi+54ECh], r10d
0x1800e2930  mov     [rdi+54F0h], esi
0x1800e2936  mov     r11d, cs:dword_180119B64
0x1800e293d  xor     r8d, r8d
0x1800e2940  mov     ecx, r11d
0x1800e2943  test    r11d, r11d
0x1800e2946  jz      loc_1800E29E7
0x1800e294c  sub     ecx, esi
0x1800e294e  jz      loc_1800E29E7
0x1800e2954  sub     ecx, esi
0x1800e2956  jz      loc_1800E29E7
0x1800e295c  sub     ecx, esi
0x1800e295e  jz      short loc_1800E29D7
0x1800e2960  cmp     ecx, esi
0x1800e2962  jnz     loc_1800E2A0B
0x1800e2968  lea     eax, [r8+2]
0x1800e296c  lea     rcx, a0_0; "0"
0x1800e2973  lea     r10, [rdi+5500h]
0x1800e297a  test    rax, rax
0x1800e297d  jz      short loc_1800E299B
0x1800e297f  movzx   edx, word ptr [rcx]
0x1800e2982  test    dx, dx
0x1800e2985  jz      short loc_1800E299B
0x1800e2987  mov     [r10], dx
0x1800e298b  add     rcx, 2
0x1800e298f  add     r10, 2
0x1800e2993  sub     rax, rsi
0x1800e2996  sub     r14, rsi
0x1800e2999  jnz     short loc_1800E297A
0x1800e299b  mov     rax, r14
0x1800e299e  lea     r9, [r10-2]
0x1800e29a2  neg     rax
0x1800e29a5  sbb     ecx, ecx
0x1800e29a7  not     ecx
0x1800e29a9  and     ecx, r13d
0x1800e29ac  test    r14, r14
0x1800e29af  cmovnz  r9, r10
0x1800e29b3  mov     [r9], r8w
0x1800e29b7  jnz     short loc_1800E29F4
0x1800e29b9  mov     [rsp+140h+var_118], ecx
0x1800e29bd  mov     r9, r12
0x1800e29c0  mov     ecx, esi
0x1800e29c2  mov     dword ptr [rsp+140h+var_120], 28h ; '('
0x1800e29ca  mov     r8, rbx
0x1800e29cd  mov     rdx, r15
0x1800e29d0  call    AslLogCallPrintf
  ... truncated ...
```
