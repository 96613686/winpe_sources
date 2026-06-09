# LocalGetAclForString

- ea: `0x180019ed0`
- end: `0x18001b480`
- name: `LocalGetAclForString`
- size: `5552`
- prototype: `__int64 __usercall@<rax>(wchar_t *String1@<rcx>, __int64, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18001b744`

## callees

- `0x1800190f4`
- `0x1800194f8`
- `0x180019cf0`
- `0x180019ed0`
- `0x18001b490`
- `0x18001c000`
- `0x180030854`
- `0x180030f9c`
- `0x18005eb44`
- `0x18005ed98`
- `0x18005ef7c`
- `0x18005f824`
- `0x180072042`
- `0x1800720b0`

## import_xrefs

- `msvcrt!wcschr` at `0x180019fc6`
- `msvcrt!wcschr` at `0x180019fc6`
- `msvcrt!wcsncpy_s` at `0x18001acdb`
- `msvcrt!wcsncpy_s` at `0x18001acdb`
- `msvcrt!_wcsnicmp` at `0x180019f8c`
- `msvcrt!_wcsnicmp` at `0x18001a267`
- `msvcrt!_wcsnicmp` at `0x18001a632`
- `msvcrt!_wcsnicmp` at `0x18001a73a`
- `msvcrt!_wcsnicmp` at `0x180019f8c`
- `msvcrt!_wcsnicmp` at `0x18001a267`
- `msvcrt!_wcsnicmp` at `0x18001a632`
- `msvcrt!_wcsnicmp` at `0x18001a73a`
- `msvcrt!wcstoul` at `0x18001a28f`
- `msvcrt!wcstoul` at `0x18001a28f`
- `ntdll!RtlLengthSid` at `0x18001a427`
- `ntdll!RtlLengthSid` at `0x18001af81`
- `ntdll!RtlLengthSid` at `0x18001afaf`
- `ntdll!RtlLengthSid` at `0x18001afc7`
- `ntdll!RtlLengthSid` at `0x18001b0ba`
- `ntdll!RtlLengthSid` at `0x18001b294`
- `ntdll!RtlLengthSid` at `0x18001b2ce`
- `ntdll!RtlLengthSid` at `0x18001a427`
- `ntdll!RtlLengthSid` at `0x18001af81`
- `ntdll!RtlLengthSid` at `0x18001afaf`
- `ntdll!RtlLengthSid` at `0x18001afc7`
- `ntdll!RtlLengthSid` at `0x18001b0ba`
- `ntdll!RtlLengthSid` at `0x18001b294`
- `ntdll!RtlLengthSid` at `0x18001b2ce`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18001a4d5`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18001a4d5`
- `ntdll!RtlCopySid` at `0x18001af96`
- `ntdll!RtlCopySid` at `0x18001b0cf`
- `ntdll!RtlCopySid` at `0x18001af96`
- `ntdll!RtlCopySid` at `0x18001b0cf`
- `ntdll!RtlAddAce` at `0x18001b002`
- `ntdll!RtlAddAce` at `0x18001b002`
- `ntdll!RtlAddAuditAccessObjectAce` at `0x18001b12d`
- `ntdll!RtlAddAuditAccessObjectAce` at `0x18001b12d`
- `ntdll!RtlGetAce` at `0x18001b244`
- `ntdll!RtlGetAce` at `0x18001b244`
- `ntdll!RtlAddAuditAccessAceEx` at `0x18001a9a3`
- `ntdll!RtlAddAuditAccessAceEx` at `0x18001a9a3`
- `ntdll!RtlAddAccessAllowedObjectAce` at `0x18001aa53`
- `ntdll!RtlAddAccessAllowedObjectAce` at `0x18001b221`
- `ntdll!RtlAddAccessAllowedObjectAce` at `0x18001aa53`
- `ntdll!RtlAddAccessAllowedObjectAce` at `0x18001b221`
- `ntdll!RtlAddAccessDeniedObjectAce` at `0x18001b1d8`
- `ntdll!RtlAddAccessDeniedObjectAce` at `0x18001b1d8`
- `ntdll!RtlAddAccessDeniedAceEx` at `0x18001a89a`
- `ntdll!RtlAddAccessDeniedAceEx` at `0x18001a89a`
- `ntdll!RtlNtStatusToDosError` at `0x18001a78a`
- `ntdll!RtlNtStatusToDosError` at `0x18001a78a`
- `KERNELBASE!LocalAlloc` at `0x18001a563`
- `KERNELBASE!LocalAlloc` at `0x18001aa79`
- `KERNELBASE!LocalAlloc` at `0x18001ab11`
- `KERNELBASE!LocalAlloc` at `0x18001af42`
- `KERNELBASE!LocalAlloc` at `0x18001b086`
- `KERNELBASE!LocalAlloc` at `0x18001a563`
- `KERNELBASE!LocalAlloc` at `0x18001aa79`
- `KERNELBASE!LocalAlloc` at `0x18001ab11`
- `KERNELBASE!LocalAlloc` at `0x18001af42`
- `KERNELBASE!LocalAlloc` at `0x18001b086`
- `KERNEL32!LocalFree` at `0x18001a468`
- `KERNEL32!LocalFree` at `0x18001a7cd`
- `KERNEL32!LocalFree` at `0x18001a811`
- `KERNEL32!LocalFree` at `0x18001ab4d`
- `KERNEL32!LocalFree` at `0x18001adb7`
- `KERNEL32!LocalFree` at `0x18001addd`
- `KERNEL32!LocalFree` at `0x18001b013`
- `KERNEL32!LocalFree` at `0x18001b2f8`
- `KERNEL32!LocalFree` at `0x18001b311`
- `KERNEL32!LocalFree` at `0x18001b33d`
- `KERNEL32!LocalFree` at `0x18001b360`
- `KERNEL32!LocalFree` at `0x18001b3a2`
- `KERNEL32!LocalFree` at `0x18001b3b3`
- `KERNEL32!LocalFree` at `0x18001a468`
- `KERNEL32!LocalFree` at `0x18001a7cd`
- `KERNEL32!LocalFree` at `0x18001a811`
- `KERNEL32!LocalFree` at `0x18001ab4d`
- `KERNEL32!LocalFree` at `0x18001adb7`
- `KERNEL32!LocalFree` at `0x18001addd`
- `KERNEL32!LocalFree` at `0x18001b013`
- `KERNEL32!LocalFree` at `0x18001b2f8`
- `KERNEL32!LocalFree` at `0x18001b311`
- `KERNEL32!LocalFree` at `0x18001b33d`
- `KERNEL32!LocalFree` at `0x18001b360`
- `KERNEL32!LocalFree` at `0x18001b3a2`
- `KERNEL32!LocalFree` at `0x18001b3b3`
- `KERNEL32!GetLastError` at `0x18001a945`
- `KERNEL32!GetLastError` at `0x18001a945`
- `KERNEL32!SetLastError` at `0x18001a49e`
- `KERNEL32!SetLastError` at `0x18001a49e`

## string_xrefs

- `0x180019f85`: `NO_ACCESS_CONTROL`

## pseudocode

```c
__int64 __fastcall LocalGetAclForString(
        wchar_t *String1,
        char a2,
        HLOCAL *a3,
        wchar_t **a4,
        _BYTE *a5,
        _BYTE *a6,
        __int64 a7,
        char a8)
{
  unsigned int v8; // r12d
  wchar_t *v12; // rsi
  wchar_t *v13; // rdi
  __int64 v14; // rax
  wchar_t *v16; // rdi
  unsigned int v17; // r14d
  DWORD LastError; // r15d
  wchar_t *v19; // rbx
  int v20; // eax
  BOOL v21; // r8d
  BOOL v23; // r10d
  unsigned int v24; // r9d
  unsigned int v25; // r8d
  wchar_t *v26; // rdx
  int v27; // edx
  int v28; // ecx
  wchar_t v29; // ax
  wchar_t *v30; // r13
  ACCESS_MASK v31; // r14d
  int v32; // edi
  __int64 v33; // rbx
  const wchar_t **v34; // rsi
  unsigned int v35; // eax
  _WORD *v36; // rax
  unsigned __int8 v37; // r10
  int v38; // r8d
  GUID *v39; // r14
  wchar_t *v40; // r13
  GUID *v41; // r12
  unsigned int j; // ebx
  wchar_t v43; // ax
  char v44; // di
  __int64 *v45; // rax
  __int64 v46; // r13
  _WORD *v47; // rsi
  _WORD *v48; // rbx
  int v49; // ecx
  unsigned int v50; // edx
  unsigned int v51; // r8d
  __int16 m; // ax
  unsigned int v53; // ebx
  ULONG v54; // edi
  __int64 v55; // rbx
  ULONG v56; // eax
  unsigned int v57; // ebx
  void *v58; // r13
  NTSTATUS v59; // eax
  int v60; // ebx
  HLOCAL *v61; // r8
  unsigned int v62; // eax
  unsigned int v63; // ebx
  _BYTE *v64; // rax
  _BYTE *v65; // rax
  wchar_t i; // ax
  const wchar_t *v67; // r14
  unsigned __int64 v68; // rdi
  int v69; // eax
  wchar_t **v70; // rcx
  const wchar_t *v71; // rdx
  unsigned __int8 v72; // si
  unsigned int v73; // ebx
  __int64 v74; // rdx
  unsigned int v75; // r8d
  wchar_t **v76; // rdi
  __int64 n; // r9
  _BYTE *v78; // rax
  unsigned int v79; // eax
  unsigned int v80; // eax
  unsigned int v81; // ebx
  _WORD *v82; // rax
  _WORD *v83; // r14
  wchar_t v84; // ax
  __int16 v85; // ax
  _WORD *k; // rbx
  DWORD ConditionForString; // eax
  int v88; // eax
  int v89; // eax
  int v90; // ecx
  char *v91; // r14
  ULONG v92; // eax
  size_t v93; // rbx
  ULONG v94; // eax
  HLOCAL v95; // rdx
  int v96; // ecx
  ULONG v97; // eax
  char v98; // cl
  size_t v99; // rbx
  int v100; // edi
  ULONG v101; // eax
  ULONG v102; // eax
  int pSid; // [rsp+20h] [rbp-E0h]
  __int64 Success; // [rsp+28h] [rbp-D8h]
  unsigned __int8 v105; // [rsp+50h] [rbp-B0h]
  unsigned __int8 v106; // [rsp+51h] [rbp-AFh]
  char v107; // [rsp+52h] [rbp-AEh]
  ACCESS_MASK AccessMask; // [rsp+60h] [rbp-A0h]
  char *Sid; // [rsp+68h] [rbp-98h]
  int v111; // [rsp+70h] [rbp-90h]
  size_t v112; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v113; // [rsp+7Ch] [rbp-84h]
  _WORD *v114; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-78h] BYREF
  int v116; // [rsp+90h] [rbp-70h]
  unsigned __int16 v117; // [rsp+94h] [rbp-6Ch]
  unsigned int Size; // [rsp+98h] [rbp-68h]
  unsigned int Size_4; // [rsp+9Ch] [rbp-64h]
  int v120; // [rsp+A0h] [rbp-60h]
  char *v121; // [rsp+A8h] [rbp-58h] BYREF
  HLOCAL Src; // [rsp+B0h] [rbp-50h] BYREF
  PVOID Ace; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v124; // [rsp+C0h] [rbp-40h]
  _BYTE *v125; // [rsp+C8h] [rbp-38h]
  _BYTE *v126; // [rsp+D0h] [rbp-30h]
  wchar_t *EndPtr; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v128; // [rsp+E0h] [rbp-20h] BYREF
  GUID *v129; // [rsp+E8h] [rbp-18h]
  wchar_t **v130; // [rsp+F0h] [rbp-10h]
  __int128 v131; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v132; // [rsp+108h] [rbp+8h] BYREF
  wchar_t Destination[40]; // [rsp+120h] [rbp+20h] BYREF

  v8 = 0;
  v126 = a5;
  v125 = a6;
  v12 = String1;
  v124 = a7;
  v130 = a4;
  EndPtr = 0;
  Sid = 0;
  v121 = 0;
  hMem = 0;
  v112 = 0;
  Src = 0;
  Ace = 0;
  v114 = 0;
  v116 = 0;
  v117 = 256;
  if ( !String1 || !a3 || !a4 )
    return 87;
  if ( !_wcsnicmp(String1, L"NO_ACCESS_CONTROL", 0x11u) )
  {
    *a3 = 0;
    *a4 = v12 + 17;
    LastError = 0;
    goto LABEL_22;
  }
  *a4 = 0;
  v111 = 2 - (a2 != 0);
  if ( !(unsigned int)FContainCallBackAce(v12) )
  {
    *a4 = wcschr(v12, 0x3Au);
    goto LABEL_7;
  }
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = v12;
  if ( *v12 )
  {
    while ( 1 )
    {
      if ( *a4 || v25 )
      {
LABEL_39:
        if ( v23 || v24 )
          return 1336;
        if ( v25 )
          return v25;
        break;
      }
      switch ( *v26 )
      {
        case '"':
          if ( v24 <= 1 )
          {
LABEL_209:
            v25 = 1336;
            break;
          }
          v23 = !v23;
          break;
        case '(':
          if ( !v23 )
            ++v24;
          break;
        case ')':
          if ( !v23 )
          {
            if ( !v24 )
              goto LABEL_209;
            --v24;
          }
          break;
        default:
          if ( *v26 == 58 && !v24 )
            *a4 = v26;
          break;
      }
      if ( !*++v26 )
        goto LABEL_39;
    }
  }
LABEL_7:
  v13 = *a4;
  if ( *a4 == v12 )
    return 87;
  if ( v13 )
  {
    v16 = v13 - 1;
  }
  else
  {
    v14 = -1;
    while ( v12[++v14] != 0 )
      ;
    v16 = &v12[v14];
  }
  *a4 = v16;
  v17 = 0;
  v113 = 0;
  LastError = 0;
  v19 = v12;
  v20 = FContainCallBackAce(v12);
  v21 = 0;
  if ( !v20 )
  {
    if ( v12 < v16 )
    {
      do
      {
        if ( *v19 == 59 )
        {
          ++v17;
        }
        else if ( *v19 != 40 )
        {
          v21 = 1;
        }
        ++v19;
      }
      while ( v19 < v16 );
    }
    if ( v17 == 5 * (v17 / 5) )
    {
      if ( !v17 && v21 )
      {
LABEL_30:
        LastError = 87;
        goto LABEL_22;
      }
      v8 = v17 / 5;
      v113 = v17 / 5;
    }
    else
    {
      LastError = 87;
    }
    goto LABEL_21;
  }
  v27 = 0;
  if ( v12 < v16 )
  {
    while ( *v19 == 32 )
    {
      if ( ++v19 >= v16 )
        goto LABEL_44;
    }
  }
  else
  {
LABEL_44:
    if ( v19 == v16 )
    {
LABEL_45:
      v28 = 1;
      goto LABEL_46;
    }
  }
  if ( *v19 != 40 )
    goto LABEL_45;
  v28 = 0;
LABEL_46:
  while ( v19 < v16 )
  {
    v29 = *v19;
    if ( *v19 == 32 )
      goto LABEL_52;
    if ( v28 )
      goto LABEL_30;
    switch ( v29 )
    {
      case '(':
        if ( v21 )
          goto LABEL_54;
        ++v27;
        ++v19;
        break;
      case ')':
        if ( v21 )
          goto LABEL_54;
        if ( !v27 )
          goto LABEL_218;
        if ( v27 == 1 )
        {
          if ( v17 < 5 )
            goto LABEL_218;
          v17 = 0;
          v113 = ++v8;
        }
        --v27;
        ++v19;
        break;
      case ';':
        ++v17;
        ++v19;
        break;
      default:
LABEL_52:
        if ( v29 == 34 )
          v21 = !v21;
LABEL_54:
        ++v19;
        break;
    }
  }
  if ( v27 )
  {
LABEL_218:
    LastError = 1336;
    goto LABEL_22;
  }
LABEL_21:
  if ( LastError )
    goto LABEL_22;
  if ( !v8 )
  {
    v78 = LocalAlloc(0x40u, 8u);
    *a3 = v78;
    if ( v78 )
    {
      *v78 = 2;
      *((_BYTE *)*a3 + 1) = 0;
      *((_WORD *)*a3 + 1) = 8;
      *((_WORD *)*a3 + 2) = 0;
      *((_WORD *)*a3 + 3) = 0;
    }
    else
    {
      return 8;
    }
    return LastError;
  }
  v63 = 84 * v8 + 8;
  Size = v63;
  if ( v63 > 0xFFFF )
  {
    v63 = 0xFFFF;
    Size = 0xFFFF;
  }
  v64 = LocalAlloc(0x40u, v63);
  v61 = a3;
  *a3 = v64;
  if ( !v64 )
  {
    LastError = 8;
    goto LABEL_22;
  }
  *v64 = 2;
  v65 = *a3;
  v120 = 8;
  v107 = 0;
  v65[1] = 0;
  *((_WORD *)*a3 + 1) = v63;
  v62 = 0;
  *((_WORD *)*a3 + 2) = 0;
  *((_WORD *)*a3 + 3) = 0;
  while ( 2 )
  {
    Size_4 = v62;
    if ( v62 >= v8 )
      goto LABEL_154;
    v131 = 0;
    v132 = 0;
    for ( i = *v12; i == 32; ++v12 )
      i = v12[1];
    v67 = v12 + 1;
    if ( i != 40 )
      v67 = v12;
    for ( ; *v67 == 32; ++v67 )
      ;
    v38 = v111;
    v55 = 0;
    while ( 2 )
    {
      v68 = 24 * v55;
      if ( (v38 & dword_1800AE490[6 * v55]) != v38 )
        goto LABEL_104;
      if ( v67 )
      {
        v69 = _wcsnicmp(v67, (&off_1800AE480)[v68 / 8], *(unsigned int *)&byte_1800AE488[v68]);
        v38 = v111;
        if ( !v69 )
          break;
        goto LABEL_104;
      }
      if ( dword_1800AE48C[v68 / 4] )
      {
LABEL_104:
        v55 = (unsigned int)(v55 + 1);
        if ( (unsigned int)v55 >= 0x11 )
          goto LABEL_105;
        continue;
      }
      break;
    }
    v70 = &(&off_1800AE480)[v68 / 8];
    if ( !&(&off_1800AE480)[v68 / 8] )
    {
LABEL_105:
      LastError = 1804;
      v36 = *a3;
      goto LABEL_106;
    }
    v71 = &v67[*((unsigned int *)v70 + 2)];
    if ( *v71 != 59 && *v71 != 32 )
      goto LABEL_75;
    v30 = (wchar_t *)(v71 + 1);
    v72 = 0;
    v106 = *((_BYTE *)v70 + 12);
    v37 = v106;
    v105 = 0;
    if ( (unsigned __int8)(v106 - 5) <= 3u || v106 == 11 )
      *(_BYTE *)*a3 = 4;
    for ( ; *v30 == 32; ++v30 )
      ;
LABEL_143:
    if ( v30 == *v130 )
    {
LABEL_65:
      v31 = 0;
      for ( AccessMask = 0; *v30 == 32; ++v30 )
        ;
      while ( *v30 != 59 )
      {
        for ( ; *v30 == 32; ++v30 )
          ;
        v32 = v38;
        if ( v37 == 17 )
          v32 = 4;
        v33 = 0;
        while ( 1 )
        {
          if ( (v32 & dword_1800AE1F0[6 * v33]) == v32 )
          {
            v34 = (const wchar_t **)&_ImageBase[12 * v33 + 356592];
            if ( !_wcsnicmp(v30, *v34, (unsigned int)dword_1800AE1E8[6 * v33]) )
              break;
          }
          v33 = (unsigned int)(v33 + 1);
          if ( (unsigned int)v33 >= 0x1C )
            goto LABEL_74;
        }
        v113 = v8;
        if ( v34 )
        {
          v31 |= *(_DWORD *)&word_18000000C[12 * v33 + 356592];
          v37 = v106;
          v38 = v111;
          v30 += *(unsigned int *)&word_180000008[12 * v33 + 356592];
          AccessMask = v31;
        }
        else
        {
LABEL_74:
          v35 = wcstoul(v30, &EndPtr, 0);
          if ( EndPtr == v30 )
            goto LABEL_75;
          v37 = v106;
          v38 = v111;
          v31 |= v35;
          AccessMask = v31;
          v30 = EndPtr;
        }
      }
      v39 = 0;
      v40 = v30 + 1;
      v41 = 0;
      v129 = 0;
      for ( j = 0; ; ++j )
      {
        v43 = *v40;
        if ( j >= 2 )
          break;
        for ( ; v43 == 32; ++v40 )
          v43 = v40[1];
        if ( v43 != 59 )
        {
          if ( (unsigned __int8)(v37 - 5) > 3u && v37 != 11 )
            goto LABEL_75;
          wcsncpy_s(Destination, 0x25u, v40, 0x24u);
          Destination[36] = 0;
          if ( j )
          {
            if ( !(unsigned int)SddlpUuidFromString(Destination, &v132) )
              goto LABEL_311;
            v39 = (GUID *)&v132;
            v129 = (GUID *)&v132;
          }
          else
          {
            if ( !(unsigned int)SddlpUuidFromString(Destination, &v131) )
              goto LABEL_311;
            v41 = (GUID *)&v131;
          }
          v84 = v40[36];
          v40 += 36;
          if ( v84 != 59 && v84 != 32 )
          {
LABEL_311:
            LastError = 1705;
            v36 = *a3;
            goto LABEL_106;
          }
          v37 = v106;
        }
        ++v40;
      }
      for ( ; v43 == 32; ++v40 )
        v43 = v40[1];
      v44 = 0;
      v128 = 0;
      v107 = 0;
      if ( !v43 || !v40[1] )
      {
        LastError = 1332;
        v36 = *a3;
        goto LABEL_106;
      }
      v114 = v40 + 2;
      LastError = 0;
      LOBYTE(Success) = a8;
      v45 = LookupSidInTable(v40, 0, v126, v125, v124, Success, (PSID *)&v128);
      if ( v45 )
      {
        v46 = v45[2];
LABEL_89:
        Sid = (char *)v46;
        goto LABEL_90;
      }
      Sid = (char *)v128;
      if ( v128 )
      {
        v46 = v128;
        v44 = 1;
        v107 = 1;
      }
      else
      {
        v114 -= 2;
        if ( !(unsigned int)LocalConvertStringSidToSid(v40, &v121, &v114) )
        {
          LastError = GetLastError();
          if ( LastError )
          {
            v46 = (__int64)v121;
            goto LABEL_89;
          }
        }
        v46 = (__int64)v121;
        Sid = v121;
        if ( v121 )
        {
          v44 = 1;
          v107 = 1;
        }
      }
LABEL_90:
      if ( LastError )
        goto LABEL_153;
      v47 = v114;
      if ( !v114 || !v46 )
        goto LABEL_75;
      v48 = v114;
      v107 = v44;
      if ( *v114 == 32 )
      {
        do
          ++v48;
        while ( *v48 == 32 );
      }
      else
      {
        v107 = v44;
      }
      if ( v106 <= 0x15u && (v49 = 2371072, _bittest(&v49, v106)) )
      {
        if ( *v48 == 59 )
        {
          v85 = v48[1];
          for ( k = v48 + 1; v85 == 32; ++k )
            v85 = k[1];
          if ( v85 == 40 )
          {
            if ( hMem )
            {
              LocalFree(hMem);
              hMem = 0;
            }
            LODWORD(v112) = 0;
            if ( Src )
            {
              LocalFree(Src);
              Src = 0;
            }
            HIDWORD(v112) = 0;
            if ( v106 == 18 )
            {
              LastError = LocalGetRelativeAttributeForString(
                            (_DWORD)k,
                            (unsigned int)&v114,
                            (unsigned int)&Src,
                            (unsigned int)&v112 + 4,
                            (__int64)v126,
                            (__int64)v125,
                            v124,
                            a8);
              if ( LastError )
                goto LABEL_76;
              v47 = v114;
            }
            else
            {
              ConditionForString = LocalGetConditionForString(
                                     (_DWORD)k,
                                     (unsigned int)&v114,
                                     (unsigned int)&hMem,
                                     (unsigned int)&v112,
                                     (__int64)v126,
                                     (__int64)v125,
                                     v124,
                                     a8,
                                     0);
              v47 = v114;
              LastError = ConditionForString;
            }
          }
          else
          {
            v47 = k;
            v114 = k;
          }
        }
        v50 = v112;
        v51 = HIDWORD(v112);
        if ( !v112 )
        {
LABEL_75:
          LastError = 1336;
LABEL_76:
          v36 = *a3;
          goto LABEL_106;
        }
        if ( LastError )
          goto LABEL_76;
      }
      else
      {
        v50 = v112;
        v51 = HIDWORD(v112);
      }
      for ( m = *v47; *v47 == 32; m = *v47 )
        v114 = ++v47;
      if ( m != 41 )
        goto LABEL_75;
      if ( v106 != 3 )
      {
        switch ( v106 )
        {
          case 0u:
          case 1u:
          case 2u:
          case 0x11u:
          case 0x13u:
          case 0x14u:
            break;
          case 5u:
          case 6u:
          case 7u:
          case 8u:
            v88 = 32;
            if ( !v41 )
              v88 = 16;
            v53 = v88 + 16;
            if ( !v39 )
              v53 = v88;
            goto LABEL_102;
          case 9u:
          case 0xAu:
          case 0xDu:
          case 0x15u:
            if ( v50 > 0xFFFFFFFC )
              goto LABEL_183;
            v79 = (v50 + 3) & 0xFFFFFFFC;
            v53 = v79 + 12;
            if ( v79 + 12 >= v79 )
              goto LABEL_102;
            goto LABEL_103;
          case 0xBu:
            v89 = 32;
            if ( !v41 )
              v89 = 16;
            v90 = v89 + 16;
            if ( !v39 )
              v90 = v89;
            if ( v50 > 0xFFFFFFFC )
            {
LABEL_183:
              LastError = 534;
              goto LABEL_22;
            }
            v80 = (v50 + 3) & 0xFFFFFFFC;
            v53 = v90 + v80;
            if ( v90 + v80 >= v80 )
              goto LABEL_102;
            goto LABEL_103;
          case 0x12u:
            v53 = v51 + 12;
            if ( v51 + 12 >= v51 )
              goto LABEL_102;
            goto LABEL_103;
          default:
            goto LABEL_75;
        }
      }
      v53 = 12;
LABEL_102:
      v12 = v47 + 1;
      v54 = v53 + RtlLengthSid(Sid) - 4;
      if ( v54 < v53 || (v56 = v54 + v120, v120 = v56, v56 < v54) )
      {
LABEL_103:
        LastError = 534;
        v36 = *a3;
        goto LABEL_106;
      }
      v57 = Size;
      if ( v56 > Size )
      {
        LODWORD(v121) = 0;
        if ( (int)RtlULongLongToULong(v54 * (unsigned __int64)(v113 - Size_4), &v121) < 0 )
          goto LABEL_103;
        v81 = (_DWORD)v121 + v57;
        if ( v81 < (unsigned int)v121 )
          goto LABEL_103;
        v82 = LocalAlloc(0x40u, v81);
        v83 = v82;
        if ( !v82 )
        {
          LocalFree(*a3);
          *a3 = 0;
          if ( v107 == 1 )
          {
            LocalFree(Sid);
            Sid = 0;
            v107 = 0;
          }
          v36 = *a3;
          LastError = 8;
          goto LABEL_106;
        }
        memcpy_0(v82, *a3, Size);
        v83[1] = v81;
        LocalFree(*a3);
        Size = v81;
        *a3 = v83;
        v39 = v129;
      }
      SetLastError(0);
      if ( v106 )
      {
        if ( v106 == 17 )
        {
          v58 = Sid;
          v59 = SddlAddMandatoryAce((PACL)*a3, pSid, AccessMask);
        }
        else
        {
          switch ( v106 )
          {
            case 1u:
              v58 = Sid;
              v59 = RtlAddAccessDeniedAceEx((PACL)*a3, 2u, v105, AccessMask, Sid);
              break;
            case 2u:
              v58 = Sid;
              v59 = RtlAddAuditAccessAceEx((PACL)*a3, 2u, v105 & 0x3F, AccessMask, Sid, v105 & 0x40, v105 & 0x80);
              break;
            case 5u:
              v58 = Sid;
              v59 = RtlAddAccessAllowedObjectAce((PACL)*a3, 4u, v105, AccessMask, v41, v39, Sid);
              break;
            case 6u:
              v58 = Sid;
              v59 = RtlAddAccessDeniedObjectAce((PACL)*a3, 4u, v105, AccessMask, v41, v39, Sid);
              break;
            case 7u:
              v58 = Sid;
              v59 = RtlAddAuditAccessObjectAce((PACL)*a3, 4u, v105, AccessMask, v41, v39, Sid, v105 & 0x40, v105 & 0x80);
              break;
            case 9u:
            case 0xAu:
            case 0xDu:
              if ( v54 >= 0xFFFF )
                goto LABEL_316;
              v91 = (char *)LocalAlloc(0x40u, v54);
              if ( !v91 )
                goto LABEL_315;
              v58 = Sid;
              *v91 = v106;
              v91[1] = v105;
              *((_WORD *)v91 + 1) = v54;
              *((_DWORD *)v91 + 1) = AccessMask;
              v92 = RtlLengthSid(Sid);
              RtlCopySid(v92, v91 + 8, Sid);
              if ( !(_DWORD)v112 )
                goto LABEL_285;
              v93 = (unsigned int)v112;
              v94 = RtlLengthSid(Sid);
              v95 = hMem;
              goto LABEL_284;
            case 0xBu:
              if ( v54 >= 0xFFFF )
                goto LABEL_316;
              v58 = Sid;
              v60 = RtlAddAccessAllowedObjectAce((PACL)*a3, 4u, v105, AccessMask, v41, v39, Sid);
              if ( v60 < 0 )
                goto LABEL_152;
              v60 = RtlGetAce((PACL)*a3, *((unsigned __int16 *)*a3 + 2) - 1, &Ace);
              if ( v60 < 0 )
                goto LABEL_152;
              v98 = 9;
              if ( *(_BYTE *)Ace == 5 )
                v98 = 11;
              *(_BYTE *)Ace = v98;
              *((_WORD *)Ace + 1) = v54;
              if ( (_DWORD)v112 )
              {
                v99 = (unsigned int)v112;
                if ( *(_BYTE *)Ace == 11 )
                {
                  v100 = *((_DWORD *)Ace + 2);
                  v101 = RtlLengthSid(Sid);
                  memcpy_0((char *)Ace + 16 * (v100 & 1) + 8 * (v100 & 2) + v101 + 12, hMem, (unsigned int)v99);
                }
                else
                {
                  v102 = RtlLengthSid(Sid);
                  memcpy_0((char *)Ace + v102 + 8, hMem, v99);
                }
              }
              goto LABEL_113;
            case 0x12u:
              if ( v54 >= 0xFFFF || (v105 & 0xE0) != 0 || AccessMask )
                goto LABEL_316;
              v58 = Sid;
              v96 = *(_DWORD *)(Sid + 2) - v116;
              if ( !v96 )
                v96 = *((unsigned __int16 *)Sid + 3) - v117;
              if ( v96 || Sid[1] != 1 || *((_DWORD *)Sid + 2) )
                goto LABEL_316;
              v91 = (char *)LocalAlloc(0x40u, v54);
              if ( v91 )
              {
                *v91 = v106;
                v91[1] = v105;
                *((_WORD *)v91 + 1) = v54;
                *((_DWORD *)v91 + 1) = 0;
                v97 = RtlLengthSid(Sid);
                RtlCopySid(v97, v91 + 8, Sid);
                if ( HIDWORD(v112) )
                {
                  v93 = HIDWORD(v112);
                  v94 = RtlLengthSid(Sid);
                  v95 = Src;
LABEL_284:
                  memcpy_0(&v91[v94 + 8], v95, v93);
                }
LABEL_285:
                v60 = RtlAddAce((PACL)*a3, 2u, 0xFFFFFFFF, v91, v54);
                LocalFree(v91);
                goto LABEL_112;
              }
LABEL_315:
              v60 = -1073741801;
              goto LABEL_152;
            case 0x13u:
              v58 = Sid;
              v59 = SddlAddScopedPolicyIDAce((PACL)*a3, Sid);
              break;
            case 0x14u:
              v58 = Sid;
              v59 = SddlAddProcessTrustLabelAce((PACL)*a3, pSid, AccessMask);
              break;
            case 0x15u:
              if ( (unsigned int)v112 >= 0xFFFF )
              {
LABEL_316:
                v60 = -1073741705;
LABEL_152:
                LastError = RtlNtStatusToDosError(v60);
LABEL_153:
                v61 = a3;
LABEL_154:
                v36 = *v61;
                if ( LastError )
                  goto LABEL_106;
                v36[1] = v120;
                goto LABEL_156;
              }
              v58 = Sid;
              v59 = SddlAddAccessFilterAce((PACL)*a3, pSid, AccessMask, hMem, v112);
              break;
            default:
              v60 = -1073741811;
              goto LABEL_152;
          }
        }
      }
      else
      {
        v58 = Sid;
        v59 = RtlAddAccessAllowedAceEx((PACL)*a3, 2u, v105, AccessMask, Sid);
      }
      v60 = v59;
LABEL_112:
      if ( v60 < 0 )
        goto LABEL_152;
LABEL_113:
      if ( v107 == 1 )
        LocalFree(v58);
      Sid = 0;
      v121 = 0;
      if ( hMem )
      {
        LocalFree(hMem);
        hMem = 0;
      }
      LODWORD(v112) = 0;
      if ( Src )
      {
        LocalFree(Src);
        Src = 0;
      }
      HIDWORD(v112) = 0;
      if ( *v12 == 40 )
        ++v12;
      v61 = a3;
      v62 = Size_4 + 1;
      v8 = v113;
      continue;
    }
    break;
  }
  if ( *v30 == 59 )
  {
    ++v30;
    goto LABEL_65;
  }
  for ( ; *v30 == 32; ++v30 )
    ;
  v73 = 0;
  while ( 1 )
  {
    v74 = 4LL * v73;
    if ( (v38 & qword_1800AE0C8[v74 + 1]) == v38 )
      break;
LABEL_161:
    if ( ++v73 >= 9 )
      goto LABEL_162;
  }
  v75 = HIDWORD(qword_1800AE0C8[v74 + 1]);
  if ( v75 )
  {
    for ( n = 0; (unsigned int)n < v75; n = (unsigned int)(n + 1) )
    {
      if ( *(_BYTE *)(n + qword_1800AE0C8[v74 + 2]) == v37 )
        goto LABEL_149;
    }
    goto LABEL_160;
  }
LABEL_149:
  v76 = &(&off_1800AE0C0)[v74];
  if ( _wcsnicmp(v30, (&off_1800AE0C0)[v74], LODWORD(qword_1800AE0C8[v74])) )
  {
    v37 = v106;
LABEL_160:
    v38 = v111;
    goto LABEL_161;
  }
  if ( v76 )
  {
    v72 |= *((_BYTE *)v76 + 12);
    v37 = v106;
    v38 = v111;
    v30 += *((unsigned int *)v76 + 2);
    v105 = v72;
    goto LABEL_143;
  }
LABEL_162:
  LastError = 1004;
  v36 = *a3;
LABEL_106:
  LocalFree(v36);
  *a3 = 0;
LABEL_156:
  if ( v107 && Sid )
    LocalFree(Sid);
LABEL_22:
  if ( hMem )
    LocalFree(hMem);
  if ( !Src )
    return LastError;
  LocalFree(Src);
  return LastError;
}

```

## disassembly

```asm
0x180019ed0  mov     [rsp-8+arg_8], rbx
0x180019ed5  push    rbp
0x180019ed6  push    rsi
0x180019ed7  push    rdi
0x180019ed8  push    r12
0x180019eda  push    r13
0x180019edc  push    r14
0x180019ede  push    r15
0x180019ee0  lea     rbp, [rsp-80h]
0x180019ee5  sub     rsp, 180h
0x180019eec  mov     rax, cs:__security_cookie
0x180019ef3  xor     rax, rsp
0x180019ef6  mov     [rbp+0B0h+var_40], rax
0x180019efa  mov     rax, [rbp+0B0h+arg_20]
0x180019f01  xor     r12d, r12d
0x180019f04  mov     [rbp+0B0h+var_E0], rax
0x180019f08  mov     r14, r9
0x180019f0b  mov     rax, [rbp+0B0h+arg_28]
0x180019f12  mov     rdi, r8
0x180019f15  mov     [rbp+0B0h+var_E8], rax
0x180019f19  movzx   ebx, dl
0x180019f1c  mov     rax, [rbp+0B0h+arg_30]
0x180019f23  mov     rsi, rcx
0x180019f26  mov     [rbp+0B0h+var_F0], rax
0x180019f2a  mov     [rbp+0B0h+var_C0], r9
0x180019f2e  mov     [rsp+1B0h+var_158], r8
0x180019f33  mov     [rbp+0B0h+EndPtr], r12
0x180019f37  mov     [rsp+1B0h+Sid], r12
0x180019f3c  mov     [rbp+0B0h+var_108], r12
0x180019f40  mov     [rbp+0B0h+hMem], r12
0x180019f44  mov     dword ptr [rsp+1B0h+var_13C], r12d
0x180019f49  mov     [rbp+0B0h+Src], r12
0x180019f4d  mov     dword ptr [rsp+1B0h+var_13C+4], r12d
0x180019f52  mov     [rbp+0B0h+Ace], r12
0x180019f56  mov     [rbp+0B0h+var_130], r12
0x180019f5a  mov     [rbp+0B0h+var_120], r12d
0x180019f5e  mov     [rbp+0B0h+var_11C], 100h
0x180019f64  test    rcx, rcx
0x180019f67  jz      loc_18001B3C7
0x180019f6d  test    r8, r8
0x180019f70  jz      loc_18001B3C7
0x180019f76  test    r9, r9
0x180019f79  jz      loc_18001B3C7
0x180019f7f  mov     r8d, 11h; MaxCount
0x180019f85  lea     rdx, aNoAccessContro; "NO_ACCESS_CONTROL"
0x180019f8c  call    cs:__imp__wcsnicmp
0x180019f93  nop     dword ptr [rax+rax+00h]
0x180019f98  test    eax, eax
0x180019f9a  jz      loc_18001AB6D
0x180019fa0  neg     bl
0x180019fa2  mov     [r14], r12
0x180019fa5  mov     rcx, rsi; String1
0x180019fa8  sbb     eax, eax
0x180019faa  add     eax, 2
0x180019fad  mov     [rsp+1B0h+var_140], eax
0x180019fb1  call    FContainCallBackAce
0x180019fb6  test    eax, eax
0x180019fb8  jnz     loc_18001A0DB
0x180019fbe  mov     edx, 3Ah ; ':'; Ch
0x180019fc3  mov     rcx, rsi; Str
0x180019fc6  call    cs:__imp_wcschr
0x180019fcd  nop     dword ptr [rax+rax+00h]
0x180019fd2  mov     [r14], rax
0x180019fd5  mov     rdi, [r14]
0x180019fd8  cmp     rdi, rsi
0x180019fdb  jz      loc_18001B3C7
0x180019fe1  test    rdi, rdi
0x180019fe4  jnz     loc_18001A0C5
0x180019fea  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180019ff1  cmp     [rsi+rax*2+2], r12w
0x180019ff7  lea     rax, [rax+1]
0x180019ffb  jnz     short loc_180019FF1
0x180019ffd  lea     rdi, [rsi+rax*2]
0x18001a001  mov     [r14], rdi
0x18001a004  mov     rcx, rsi; String1
0x18001a007  mov     r14d, r12d
0x18001a00a  mov     [rsp+1B0h+var_134], r12d
0x18001a00f  mov     r15d, r12d
0x18001a012  mov     rbx, rsi
0x18001a015  call    FContainCallBackAce
0x18001a01a  xor     r8d, r8d
0x18001a01d  test    eax, eax
0x18001a01f  jnz     loc_18001A14C
0x18001a025  cmp     rsi, rdi
0x18001a028  jnb     short loc_18001A04B
0x18001a02a  mov     ecx, 1
0x18001a02f  nop
0x18001a030  movzx   eax, word ptr [rbx]
0x18001a033  cmp     ax, 3Bh ; ';'
0x18001a037  jz      short loc_18001A0B8
0x18001a039  cmp     ax, 28h ; '('
0x18001a03d  jz      short loc_18001A042
0x18001a03f  mov     r8d, ecx
0x18001a042  add     rbx, 2
0x18001a046  cmp     rbx, rdi
0x18001a049  jb      short loc_18001A030
0x18001a04b  mov     eax, 0CCCCCCCDh
0x18001a050  mul     r14d
0x18001a053  shr     edx, 2
0x18001a056  lea     ecx, [rdx+rdx*4]
0x18001a059  cmp     r14d, ecx
0x18001a05c  jnz     short loc_18001A0BD
0x18001a05e  test    r14d, r14d
0x18001a061  jz      short loc_18001A0CE
0x18001a063  mov     r12d, edx
0x18001a066  mov     [rsp+1B0h+var_134], edx
0x18001a06a  test    r15d, r15d
0x18001a06d  jz      loc_18001AA64
0x18001a073  mov     rcx, [rbp+0B0h+hMem]; hMem
0x18001a077  test    rcx, rcx
0x18001a07a  jnz     loc_18001B3A2
0x18001a080  mov     rcx, [rbp+0B0h+Src]; hMem
0x18001a084  test    rcx, rcx
0x18001a087  jnz     loc_18001B3B3
0x18001a08d  mov     eax, r15d
0x18001a090  mov     rcx, [rbp+0B0h+var_40]
0x18001a094  xor     rcx, rsp; StackCookie
0x18001a097  call    __security_check_cookie
0x18001a09c  mov     rbx, [rsp+1B0h+arg_8]
0x18001a0a4  add     rsp, 180h
0x18001a0ab  pop     r15
0x18001a0ad  pop     r14
0x18001a0af  pop     r13
0x18001a0b1  pop     r12
0x18001a0b3  pop     rdi
0x18001a0b4  pop     rsi
0x18001a0b5  pop     rbp
0x18001a0b6  retn
0x18001a0b8  inc     r14d
0x18001a0bb  jmp     short loc_18001A042
0x18001a0bd  mov     r15d, 57h ; 'W'
0x18001a0c3  jmp     short loc_18001A06A
0x18001a0c5  add     rdi, 0FFFFFFFFFFFFFFFEh
0x18001a0c9  jmp     loc_18001A001
0x18001a0ce  test    r8d, r8d
0x18001a0d1  jz      short loc_18001A063
0x18001a0d3  mov     r15d, 57h ; 'W'
0x18001a0d9  jmp     short loc_18001A073
0x18001a0db  mov     r10d, r12d
0x18001a0de  mov     r9d, r12d
0x18001a0e1  mov     r8d, r12d
0x18001a0e4  mov     rdx, rsi
0x18001a0e7  cmp     [rsi], r12w
0x18001a0eb  jz      loc_180019FD5
0x18001a0f1  cmp     [r14], r12
0x18001a0f4  jnz     short loc_18001A12C
0x18001a0f6  test    r8d, r8d
0x18001a0f9  jnz     short loc_18001A12C
0x18001a0fb  movzx   ecx, word ptr [rdx]
0x18001a0fe  sub     ecx, 22h ; '"'
0x18001a101  jz      loc_18001ABB7
0x18001a107  sub     ecx, 6
0x18001a10a  jz      loc_18001ABA6
0x18001a110  sub     ecx, 1
0x18001a113  jz      loc_18001AB90
0x18001a119  cmp     ecx, 11h
0x18001a11c  jz      loc_18001AB7F
0x18001a122  add     rdx, 2
0x18001a126  cmp     [rdx], r12w
0x18001a12a  jnz     short loc_18001A0F1
0x18001a12c  test    r10d, r10d
0x18001a12f  jnz     loc_18001ABD9
0x18001a135  test    r9d, r9d
0x18001a138  jnz     loc_18001ABD9
0x18001a13e  test    r8d, r8d
0x18001a141  jz      loc_180019FD5
0x18001a147  jmp     loc_18001ABDF
0x18001a14c  xor     edx, edx
0x18001a14e  cmp     rsi, rdi
0x18001a151  jb      loc_18001ABE7
0x18001a157  cmp     rbx, rdi
0x18001a15a  jnz     loc_18001ABFB
0x18001a160  mov     ecx, 1
0x18001a165  cmp     rbx, rdi
0x18001a168  jnb     loc_18001AC0C
0x18001a16e  movzx   eax, word ptr [rbx]
0x18001a171  cmp     ax, 20h ; ' '
0x18001a175  jz      short loc_18001A191
0x18001a177  test    ecx, ecx
0x18001a179  jnz     loc_18001A0D3
0x18001a17f  cmp     ax, 28h ; '('
0x18001a183  jz      short loc_18001A1A6
0x18001a185  cmp     ax, 29h ; ')'
0x18001a189  jz      short loc_18001A1B3
0x18001a18b  cmp     ax, 3Bh ; ';'
0x18001a18f  jz      short loc_18001A19D
0x18001a191  cmp     ax, 22h ; '"'
0x18001a195  jz      short loc_18001A1E2
0x18001a197  add     rbx, 2
0x18001a19b  jmp     short loc_18001A165
0x18001a19d  inc     r14d
0x18001a1a0  add     rbx, 2
0x18001a1a4  jmp     short loc_18001A165
0x18001a1a6  test    r8d, r8d
0x18001a1a9  jnz     short loc_18001A197
0x18001a1ab  inc     edx
0x18001a1ad  add     rbx, 2
0x18001a1b1  jmp     short loc_18001A165
0x18001a1b3  test    r8d, r8d
0x18001a1b6  jnz     short loc_18001A197
0x18001a1b8  test    edx, edx
0x18001a1ba  jz      loc_18001AC14
0x18001a1c0  cmp     edx, 1
0x18001a1c3  jnz     short loc_18001A1DA
0x18001a1c5  cmp     r14d, 5
0x18001a1c9  jb      loc_18001AC14
0x18001a1cf  xor     r14d, r14d
0x18001a1d2  inc     r12d
0x18001a1d5  mov     [rsp+1B0h+var_134], r12d
0x18001a1da  dec     edx
0x18001a1dc  add     rbx, 2
0x18001a1e0  jmp     short loc_18001A165
0x18001a1e2  xor     eax, eax
0x18001a1e4  test    r8d, r8d
0x18001a1e7  setz    al
0x18001a1ea  mov     r8d, eax
0x18001a1ed  jmp     short loc_18001A197
0x18001a1ef  add     r13, 2
0x18001a1f3  xor     r14d, r14d
0x18001a1f6  cmp     word ptr [r13+0], 20h ; ' '
0x18001a1fc  mov     [rsp+1B0h+AccessMask], r14d
0x18001a201  jz      loc_18001AC81
0x18001a207  nop     word ptr [rax+rax+00000000h]
0x18001a210  movzx   eax, word ptr [r13+0]
0x18001a215  cmp     ax, 3Bh ; ';'
0x18001a219  jz      loc_18001A2ED
0x18001a21f  cmp     ax, 20h ; ' '
0x18001a223  jz      loc_18001AC92
0x18001a229  cmp     r10b, 11h
0x18001a22d  mov     edi, r8d
0x18001a230  mov     r9d, 4
0x18001a236  cmovz   edi, r9d
0x18001a23a  xor     ebx, ebx
0x18001a23c  lea     rcx, [rbx+rbx*2]
0x18001a240  mov     eax, rva dword_1800AE1F0[r11+rcx*8]
0x18001a248  and     eax, edi
0x18001a24a  cmp     eax, edi
0x18001a24c  jnz     short loc_18001A27E
0x18001a24e  mov     r8d, rva dword_1800AE1E8[r11+rcx*8]; MaxCount
0x18001a256  lea     rsi, ds:0AE1E0h[rcx*8]
0x18001a25e  add     rsi, r11
0x18001a261  mov     rcx, r13; String1
0x18001a264  mov     rdx, [rsi]; String2
0x18001a267  call    cs:__imp__wcsnicmp
0x18001a26e  nop     dword ptr [rax+rax+00h]
0x18001a273  test    eax, eax
0x18001a275  jz      short loc_18001A2BB
0x18001a277  lea     r11, __ImageBase
0x18001a27e  inc     ebx
0x18001a280  cmp     ebx, 1Ch
0x18001a283  jb      short loc_18001A23C
0x18001a285  xor     r8d, r8d; Radix
0x18001a288  lea     rdx, [rbp+0B0h+EndPtr]; EndPtr
0x18001a28c  mov     rcx, r13; String
0x18001a28f  call    cs:__imp_wcstoul
0x18001a296  nop     dword ptr [rax+rax+00h]
0x18001a29b  mov     rcx, [rbp+0B0h+EndPtr]
0x18001a29f  cmp     rcx, r13
0x18001a2a2  jnz     loc_18001A923
0x18001a2a8  mov     r15d, 538h; jumptable 000000018001A9FA default case, cases 3,4,12,14-16
0x18001a2ae  mov     rax, [rsp+1B0h+var_158]
0x18001a2b3  mov     rax, [rax]
0x18001a2b6  jmp     loc_18001A465
0x18001a2bb  mov     [rsp+1B0h+var_134], r12d
0x18001a2c0  test    rsi, rsi
0x18001a2c3  jz      short loc_18001A285
0x18001a2c5  mov     eax, [rsi+8]
0x18001a2c8  lea     r11, __ImageBase
0x18001a2cf  or      r14d, [rsi+0Ch]
0x18001a2d3  movzx   r10d, [rsp+1B0h+var_15F]
0x18001a2d9  mov     r8d, [rsp+1B0h+var_140]
0x18001a2de  lea     r13, [r13+rax*2+0]
0x18001a2e3  mov     [rsp+1B0h+AccessMask], r14d
0x18001a2e8  jmp     loc_18001A210
0x18001a2ed  xor     r14d, r14d
0x18001a2f0  add     r13, 2
0x18001a2f4  xor     r12d, r12d
0x18001a2f7  mov     [rbp+0B0h+var_C8], r14
0x18001a2fb  xor     ebx, ebx
0x18001a2fd  movzx   eax, word ptr [r13+0]
0x18001a302  cmp     ebx, 2
0x18001a305  jnb     short loc_18001A323
0x18001a307  cmp     ax, 20h ; ' '
0x18001a30b  jz      loc_18001ACA3
0x18001a311  cmp     ax, 3Bh ; ';'
0x18001a315  jnz     loc_18001ACB7
0x18001a31b  add     r13, 2
0x18001a31f  inc     ebx
0x18001a321  jmp     short loc_18001A2FD
0x18001a323  cmp     ax, 20h ; ' '
0x18001a327  jz      loc_18001AD49
0x18001a32d  xor     dil, dil
0x18001a330  mov     [rbp+0B0h+var_D0], 0
0x18001a338  mov     [rsp+1B0h+var_15E], dil
0x18001a33d  test    ax, ax
0x18001a340  jz      loc_18001AA14
0x18001a346  cmp     word ptr [r13+2], 0
0x18001a34c  jz      loc_18001AA14
0x18001a352  mov     r9, [rbp+0B0h+var_E8]
0x18001a356  lea     rax, [r13+4]
  ... truncated ...
```
