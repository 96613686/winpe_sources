# LocalGetAclForString

- ea: `0x18001b480`
- end: `0x18001c910`
- name: `LocalGetAclForString`
- size: `5264`
- prototype: `__int64 __usercall@<rax>(wchar_t *String1@<rcx>, __int64, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18001cbbc`

## callees

- `0x18001a808`
- `0x18001ada0`
- `0x18001b2c0`
- `0x18001b480`
- `0x18001c920`
- `0x18001d3d0`
- `0x18003073c`
- `0x180053090`
- `0x1800532b8`
- `0x180053460`
- `0x180053c4c`
- `0x180065042`
- `0x180065090`

## import_xrefs

- `msvcrt!wcschr` at `0x18001b576`
- `msvcrt!wcschr` at `0x18001b576`
- `msvcrt!wcsncpy_s` at `0x18001c22e`
- `msvcrt!wcsncpy_s` at `0x18001c22e`
- `msvcrt!_wcsnicmp` at `0x18001b53c`
- `msvcrt!_wcsnicmp` at `0x18001b817`
- `msvcrt!_wcsnicmp` at `0x18001bbb1`
- `msvcrt!_wcsnicmp` at `0x18001bcb3`
- `msvcrt!_wcsnicmp` at `0x18001b53c`
- `msvcrt!_wcsnicmp` at `0x18001b817`
- `msvcrt!_wcsnicmp` at `0x18001bbb1`
- `msvcrt!_wcsnicmp` at `0x18001bcb3`
- `msvcrt!wcstoul` at `0x18001b839`
- `msvcrt!wcstoul` at `0x18001b839`
- `ntdll!RtlLengthSid` at `0x18001b9cb`
- `ntdll!RtlLengthSid` at `0x18001c492`
- `ntdll!RtlLengthSid` at `0x18001c4b4`
- `ntdll!RtlLengthSid` at `0x18001c4c6`
- `ntdll!RtlLengthSid` at `0x18001c5a1`
- `ntdll!RtlLengthSid` at `0x18001c757`
- `ntdll!RtlLengthSid` at `0x18001c78b`
- `ntdll!RtlLengthSid` at `0x18001b9cb`
- `ntdll!RtlLengthSid` at `0x18001c492`
- `ntdll!RtlLengthSid` at `0x18001c4b4`
- `ntdll!RtlLengthSid` at `0x18001c4c6`
- `ntdll!RtlLengthSid` at `0x18001c5a1`
- `ntdll!RtlLengthSid` at `0x18001c757`
- `ntdll!RtlLengthSid` at `0x18001c78b`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18001ba67`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18001ba67`
- `ntdll!RtlCopySid` at `0x18001c4a1`
- `ntdll!RtlCopySid` at `0x18001c5b0`
- `ntdll!RtlCopySid` at `0x18001c4a1`
- `ntdll!RtlCopySid` at `0x18001c5b0`
- `ntdll!RtlAddAce` at `0x18001c4fb`
- `ntdll!RtlAddAce` at `0x18001c4fb`
- `ntdll!RtlAddAuditAccessObjectAce` at `0x18001c608`
- `ntdll!RtlAddAuditAccessObjectAce` at `0x18001c608`
- `ntdll!RtlGetAce` at `0x18001c70d`
- `ntdll!RtlGetAce` at `0x18001c70d`
- `ntdll!RtlAddAuditAccessAceEx` at `0x18001bf0c`
- `ntdll!RtlAddAuditAccessAceEx` at `0x18001bf0c`
- `ntdll!RtlAddAccessAllowedObjectAce` at `0x18001bfb2`
- `ntdll!RtlAddAccessAllowedObjectAce` at `0x18001c6f0`
- `ntdll!RtlAddAccessAllowedObjectAce` at `0x18001bfb2`
- `ntdll!RtlAddAccessAllowedObjectAce` at `0x18001c6f0`
- `ntdll!RtlAddAccessDeniedObjectAce` at `0x18001c6ad`
- `ntdll!RtlAddAccessDeniedObjectAce` at `0x18001c6ad`
- `ntdll!RtlAddAccessDeniedAceEx` at `0x18001bdf7`
- `ntdll!RtlAddAccessDeniedAceEx` at `0x18001bdf7`
- `ntdll!RtlNtStatusToDosError` at `0x18001bcfd`
- `ntdll!RtlNtStatusToDosError` at `0x18001bea6`
- `ntdll!RtlNtStatusToDosError` at `0x18001bcfd`
- `ntdll!RtlNtStatusToDosError` at `0x18001bea6`
- `KERNELBASE!LocalAlloc` at `0x18001bae8`
- `KERNELBASE!LocalAlloc` at `0x18001bfd2`
- `KERNELBASE!LocalAlloc` at `0x18001c07d`
- `KERNELBASE!LocalAlloc` at `0x18001c459`
- `KERNELBASE!LocalAlloc` at `0x18001c573`
- `KERNELBASE!LocalAlloc` at `0x18001bae8`
- `KERNELBASE!LocalAlloc` at `0x18001bfd2`
- `KERNELBASE!LocalAlloc` at `0x18001c07d`
- `KERNELBASE!LocalAlloc` at `0x18001c459`
- `KERNELBASE!LocalAlloc` at `0x18001c573`
- `KERNEL32!LocalFree` at `0x18001ba06`
- `KERNEL32!LocalFree` at `0x18001bd3a`
- `KERNEL32!LocalFree` at `0x18001bd78`
- `KERNEL32!LocalFree` at `0x18001c0b3`
- `KERNEL32!LocalFree` at `0x18001c304`
- `KERNEL32!LocalFree` at `0x18001c324`
- `KERNEL32!LocalFree` at `0x18001c506`
- `KERNEL32!LocalFree` at `0x18001c7af`
- `KERNEL32!LocalFree` at `0x18001c7c2`
- `KERNEL32!LocalFree` at `0x18001c7e8`
- `KERNEL32!LocalFree` at `0x18001c805`
- `KERNEL32!LocalFree` at `0x18001c841`
- `KERNEL32!LocalFree` at `0x18001c84c`
- `KERNEL32!LocalFree` at `0x18001ba06`
- `KERNEL32!LocalFree` at `0x18001bd3a`
- `KERNEL32!LocalFree` at `0x18001bd78`
- `KERNEL32!LocalFree` at `0x18001c0b3`
- `KERNEL32!LocalFree` at `0x18001c304`
- `KERNEL32!LocalFree` at `0x18001c324`
- `KERNEL32!LocalFree` at `0x18001c506`
- `KERNEL32!LocalFree` at `0x18001c7af`
- `KERNEL32!LocalFree` at `0x18001c7c2`
- `KERNEL32!LocalFree` at `0x18001c7e8`
- `KERNEL32!LocalFree` at `0x18001c805`
- `KERNEL32!LocalFree` at `0x18001c841`
- `KERNEL32!LocalFree` at `0x18001c84c`
- `KERNEL32!GetLastError` at `0x18001beb4`
- `KERNEL32!GetLastError` at `0x18001beb4`
- `KERNEL32!SetLastError` at `0x18001ba36`
- `KERNEL32!SetLastError` at `0x18001be2f`
- `KERNEL32!SetLastError` at `0x18001beae`
- `KERNEL32!SetLastError` at `0x18001ba36`
- `KERNEL32!SetLastError` at `0x18001be2f`
- `KERNEL32!SetLastError` at `0x18001beae`

## string_xrefs

- `0x18001b535`: `NO_ACCESS_CONTROL`

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
  void *v57; // r13
  NTSTATUS v58; // eax
  int v59; // ebx
  HLOCAL *v60; // r8
  unsigned int v61; // eax
  unsigned int v62; // ebx
  _BYTE *v63; // rax
  _BYTE *v64; // rax
  wchar_t i; // ax
  const wchar_t *v66; // r14
  unsigned __int64 v67; // rdi
  int v68; // eax
  wchar_t **v69; // rcx
  const wchar_t *v70; // rdx
  unsigned __int8 v71; // si
  unsigned int v72; // ebx
  __int64 v73; // rdx
  unsigned int v74; // r8d
  wchar_t **v75; // rdi
  NTSTATUS v76; // eax
  __int64 n; // r9
  ULONG v78; // eax
  _BYTE *v79; // rax
  unsigned int v80; // eax
  unsigned int v81; // eax
  unsigned __int64 v82; // rcx
  unsigned int v83; // ebx
  _WORD *v84; // rax
  _WORD *v85; // r14
  wchar_t v86; // ax
  __int16 v87; // ax
  _WORD *k; // rbx
  DWORD ConditionForString; // eax
  int v90; // eax
  int v91; // eax
  int v92; // ecx
  char *v93; // r14
  ULONG v94; // eax
  size_t v95; // rbx
  ULONG v96; // eax
  HLOCAL v97; // rdx
  int v98; // ecx
  ULONG v99; // eax
  char v100; // cl
  size_t v101; // rbx
  int v102; // edi
  ULONG v103; // eax
  ULONG v104; // eax
  int pSid; // [rsp+20h] [rbp-E0h]
  __int64 Success; // [rsp+28h] [rbp-D8h]
  unsigned __int8 v107; // [rsp+50h] [rbp-B0h]
  unsigned __int8 v108; // [rsp+51h] [rbp-AFh]
  char v109; // [rsp+52h] [rbp-AEh]
  ACCESS_MASK AccessMask; // [rsp+60h] [rbp-A0h]
  char *Sid; // [rsp+68h] [rbp-98h]
  int v113; // [rsp+70h] [rbp-90h]
  size_t v114; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v115; // [rsp+7Ch] [rbp-84h]
  _WORD *v116; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-78h] BYREF
  int v118; // [rsp+90h] [rbp-70h]
  unsigned __int16 v119; // [rsp+94h] [rbp-6Ch]
  unsigned int Size; // [rsp+98h] [rbp-68h]
  unsigned int Size_4; // [rsp+9Ch] [rbp-64h]
  int v122; // [rsp+A0h] [rbp-60h]
  HLOCAL Src; // [rsp+A8h] [rbp-58h] BYREF
  PVOID Ace; // [rsp+B0h] [rbp-50h] BYREF
  char *v125; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v126; // [rsp+C0h] [rbp-40h]
  _BYTE *v127; // [rsp+C8h] [rbp-38h]
  _BYTE *v128; // [rsp+D0h] [rbp-30h]
  wchar_t *EndPtr; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v130; // [rsp+E0h] [rbp-20h] BYREF
  GUID *v131; // [rsp+E8h] [rbp-18h]
  wchar_t **v132; // [rsp+F0h] [rbp-10h]
  __int128 v133; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v134; // [rsp+108h] [rbp+8h] BYREF
  wchar_t Destination[40]; // [rsp+120h] [rbp+20h] BYREF

  v8 = 0;
  v128 = a5;
  v127 = a6;
  v12 = String1;
  v126 = a7;
  v132 = a4;
  EndPtr = 0;
  Sid = 0;
  v125 = 0;
  hMem = 0;
  v114 = 0;
  Src = 0;
  Ace = 0;
  v116 = 0;
  v118 = 0;
  v119 = 256;
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
  v113 = 2 - (a2 != 0);
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
LABEL_211:
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
              goto LABEL_211;
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
  v115 = 0;
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
      v115 = v17 / 5;
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
          goto LABEL_220;
        if ( v27 == 1 )
        {
          if ( v17 < 5 )
            goto LABEL_220;
          v17 = 0;
          v115 = ++v8;
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
LABEL_220:
    LastError = 1336;
    goto LABEL_22;
  }
LABEL_21:
  if ( LastError )
    goto LABEL_22;
  if ( !v8 )
  {
    v79 = LocalAlloc(0x40u, 8u);
    *a3 = v79;
    if ( v79 )
    {
      *v79 = 2;
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
  v62 = 84 * v8 + 8;
  if ( v62 > 0xFFFF )
    v62 = 0xFFFF;
  Size = v62;
  v63 = LocalAlloc(0x40u, v62);
  v60 = a3;
  *a3 = v63;
  if ( !v63 )
  {
    LastError = 8;
    goto LABEL_22;
  }
  *v63 = 2;
  v64 = *a3;
  v122 = 8;
  v109 = 0;
  v64[1] = 0;
  *((_WORD *)*a3 + 1) = v62;
  v61 = 0;
  *((_WORD *)*a3 + 2) = 0;
  *((_WORD *)*a3 + 3) = 0;
  while ( 2 )
  {
    Size_4 = v61;
    if ( v61 >= v8 )
      goto LABEL_154;
    v133 = 0;
    v134 = 0;
    for ( i = *v12; i == 32; ++v12 )
      i = v12[1];
    v66 = v12 + 1;
    if ( i != 40 )
      v66 = v12;
    for ( ; *v66 == 32; ++v66 )
      ;
    v38 = v113;
    v55 = 0;
    while ( 2 )
    {
      v67 = 24 * v55;
      if ( (v38 & dword_18009F490[6 * v55]) != v38 )
        goto LABEL_104;
      if ( v66 )
      {
        v68 = _wcsnicmp(v66, (&off_18009F480)[v67 / 8], *(unsigned int *)&byte_18009F488[v67]);
        v38 = v113;
        if ( !v68 )
          break;
        goto LABEL_104;
      }
      if ( dword_18009F48C[v67 / 4] )
      {
LABEL_104:
        v55 = (unsigned int)(v55 + 1);
        if ( (unsigned int)v55 >= 0x11 )
          goto LABEL_105;
        continue;
      }
      break;
    }
    v69 = &(&off_18009F480)[v67 / 8];
    if ( !&(&off_18009F480)[v67 / 8] )
    {
LABEL_105:
      LastError = 1804;
      v36 = *a3;
      goto LABEL_106;
    }
    v70 = &v66[*((unsigned int *)v69 + 2)];
    if ( *v70 != 59 && *v70 != 32 )
      goto LABEL_75;
    v30 = (wchar_t *)(v70 + 1);
    v71 = 0;
    v108 = *((_BYTE *)v69 + 12);
    v37 = v108;
    v107 = 0;
    if ( (unsigned __int8)(v108 - 5) <= 3u || v108 == 11 )
      *(_BYTE *)*a3 = 4;
    for ( ; *v30 == 32; ++v30 )
      ;
LABEL_143:
    if ( v30 == *v132 )
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
          if ( (v32 & dword_18009F1F0[6 * v33]) == v32 )
          {
            v34 = (const wchar_t **)&_ImageBase[12 * v33 + 325872];
            if ( !_wcsnicmp(v30, *v34, (unsigned int)dword_18009F1E8[6 * v33]) )
              break;
          }
          v33 = (unsigned int)(v33 + 1);
          if ( (unsigned int)v33 >= 0x1C )
            goto LABEL_74;
        }
        v115 = v8;
        if ( v34 )
        {
          v31 |= *(_DWORD *)&word_18000000C[12 * v33 + 325872];
          v37 = v108;
          v38 = v113;
          v30 += *(unsigned int *)&word_180000008[12 * v33 + 325872];
          AccessMask = v31;
        }
        else
        {
LABEL_74:
          v35 = wcstoul(v30, &EndPtr, 0);
          if ( EndPtr == v30 )
            goto LABEL_75;
          v37 = v108;
          v38 = v113;
          v31 |= v35;
          AccessMask = v31;
          v30 = EndPtr;
        }
      }
      v39 = 0;
      v40 = v30 + 1;
      v41 = 0;
      v131 = 0;
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
            if ( !(unsigned int)SddlpUuidFromString(Destination, &v134) )
              goto LABEL_311;
            v39 = (GUID *)&v134;
            v131 = (GUID *)&v134;
          }
          else
          {
            if ( !(unsigned int)SddlpUuidFromString(Destination, &v133) )
              goto LABEL_311;
            v41 = (GUID *)&v133;
          }
          v86 = v40[36];
          v40 += 36;
          if ( v86 != 59 && v86 != 32 )
          {
LABEL_311:
            LastError = 1705;
            v36 = *a3;
            goto LABEL_106;
          }
          v37 = v108;
        }
        ++v40;
      }
      for ( ; v43 == 32; ++v40 )
        v43 = v40[1];
      v44 = 0;
      v130 = 0;
      v109 = 0;
      if ( !v43 || !v40[1] )
      {
        LastError = 1332;
        v36 = *a3;
        goto LABEL_106;
      }
      v116 = v40 + 2;
      LastError = 0;
      LOBYTE(Success) = a8;
      v45 = LookupSidInTable(v40, 0, v128, v127, v126, Success, (PSID *)&v130);
      if ( v45 )
      {
        v46 = v45[2];
LABEL_89:
        Sid = (char *)v46;
        goto LABEL_90;
      }
      Sid = (char *)v130;
      if ( v130 )
      {
        v46 = v130;
        v44 = 1;
        v109 = 1;
      }
      else
      {
        v116 -= 2;
        v76 = LocalpConvertStringSidToSid(v40, &v125, &v116);
        if ( v76 < 0 )
        {
          v78 = RtlNtStatusToDosError(v76);
          SetLastError(v78);
          LastError = GetLastError();
          if ( LastError )
          {
            v46 = (__int64)v125;
            goto LABEL_89;
          }
        }
        else
        {
          SetLastError(0);
        }
        v46 = (__int64)v125;
        Sid = v125;
        if ( v125 )
        {
          v44 = 1;
          v109 = 1;
        }
      }
LABEL_90:
      if ( LastError )
        goto LABEL_153;
      v47 = v116;
      if ( !v116 || !v46 )
        goto LABEL_75;
      v48 = v116;
      v109 = v44;
      if ( *v116 == 32 )
      {
        do
          ++v48;
        while ( *v48 == 32 );
      }
      else
      {
        v109 = v44;
      }
      if ( v108 <= 0x15u && (v49 = 2371072, _bittest(&v49, v108)) )
      {
        if ( *v48 == 59 )
        {
          v87 = v48[1];
          for ( k = v48 + 1; v87 == 32; ++k )
            v87 = k[1];
          if ( v87 == 40 )
          {
            if ( hMem )
            {
              LocalFree(hMem);
              hMem = 0;
            }
            LODWORD(v114) = 0;
            if ( Src )
            {
              LocalFree(Src);
              Src = 0;
            }
            HIDWORD(v114) = 0;
            if ( v108 == 18 )
            {
              LastError = LocalGetRelativeAttributeForString(
                            (_DWORD)k,
                            (unsigned int)&v116,
                            (unsigned int)&Src,
                            (unsigned int)&v114 + 4,
                            (__int64)v128,
                            (__int64)v127,
                            v126,
                            a8);
              if ( LastError )
                goto LABEL_76;
              v47 = v116;
            }
            else
            {
              ConditionForString = LocalGetConditionForString(
                                     (_DWORD)k,
                                     (unsigned int)&v116,
                                     (unsigned int)&hMem,
                                     (unsigned int)&v114,
                                     (__int64)v128,
                                     (__int64)v127,
                                     v126,
                                     a8,
                                     0);
              v47 = v116;
              LastError = ConditionForString;
            }
          }
          else
          {
            v47 = k;
            v116 = k;
          }
        }
        v50 = v114;
        v51 = HIDWORD(v114);
        if ( !v114 )
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
        v50 = v114;
        v51 = HIDWORD(v114);
      }
      for ( m = *v47; *v47 == 32; m = *v47 )
        v116 = ++v47;
      if ( m != 41 )
        goto LABEL_75;
      if ( v108 != 3 )
      {
        switch ( v108 )
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
            v90 = 32;
            if ( !v41 )
              v90 = 16;
            v53 = v90 + 16;
            if ( !v39 )
              v53 = v90;
            goto LABEL_102;
          case 9u:
          case 0xAu:
          case 0xDu:
          case 0x15u:
            if ( v50 > 0xFFFFFFFC )
              goto LABEL_184;
            v80 = (v50 + 3) & 0xFFFFFFFC;
            v53 = v80 + 12;
            if ( v80 + 12 >= v80 )
              goto LABEL_102;
            goto LABEL_103;
          case 0xBu:
            v91 = 32;
            if ( !v41 )
              v91 = 16;
            v92 = v91 + 16;
            if ( !v39 )
              v92 = v91;
            if ( v50 > 0xFFFFFFFC )
            {
LABEL_184:
              LastError = 534;
              goto LABEL_22;
            }
            v81 = (v50 + 3) & 0xFFFFFFFC;
            v53 = v92 + v81;
            if ( v92 + v81 >= v81 )
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
      if ( v54 < v53 || (v56 = v54 + v122, v122 = v56, v56 < v54) )
      {
LABEL_103:
        LastError = 534;
        v36 = *a3;
        goto LABEL_106;
      }
      if ( v56 > Size )
      {
        v82 = v54 * (unsigned __int64)(v115 - Size_4);
        if ( v82 > 0xFFFFFFFF )
          goto LABEL_103;
        v83 = v82 + Size;
        if ( (unsigned int)v82 + Size < (unsigned int)v82 )
          goto LABEL_103;
        v84 = LocalAlloc(0x40u, v83);
        v85 = v84;
        if ( !v84 )
        {
          LocalFree(*a3);
          *a3 = 0;
          if ( v109 == 1 )
          {
            LocalFree(Sid);
            Sid = 0;
            v109 = 0;
          }
          v36 = *a3;
          LastError = 8;
          goto LABEL_106;
        }
        memcpy_0(v84, *a3, Size);
        v85[1] = v83;
        LocalFree(*a3);
        Size = v83;
        *a3 = v85;
        v39 = v131;
      }
      SetLastError(0);
      if ( v108 )
      {
        if ( v108 == 17 )
        {
          v57 = Sid;
          v58 = SddlAddMandatoryAce((PACL)*a3, pSid, AccessMask);
        }
        else
        {
          switch ( v108 )
          {
            case 1u:
              v57 = Sid;
              v58 = RtlAddAccessDeniedAceEx((PACL)*a3, 2u, v107, AccessMask, Sid);
              break;
            case 2u:
              v57 = Sid;
              v58 = RtlAddAuditAccessAceEx((PACL)*a3, 2u, v107 & 0x3F, AccessMask, Sid, v107 & 0x40, v107 & 0x80);
              break;
            case 5u:
              v57 = Sid;
              v58 = RtlAddAccessAllowedObjectAce((PACL)*a3, 4u, v107, AccessMask, v41, v39, Sid);
              break;
            case 6u:
              v57 = Sid;
              v58 = RtlAddAccessDeniedObjectAce((PACL)*a3, 4u, v107, AccessMask, v41, v39, Sid);
              break;
            case 7u:
              v57 = Sid;
              v58 = RtlAddAuditAccessObjectAce((PACL)*a3, 4u, v107, AccessMask, v41, v39, Sid, v107 & 0x40, v107 & 0x80);
              break;
            case 9u:
            case 0xAu:
            case 0xDu:
              if ( v54 >= 0xFFFF )
                goto LABEL_316;
              v93 = (char *)LocalAlloc(0x40u, v54);
              if ( !v93 )
                goto LABEL_315;
              v57 = Sid;
              *v93 = v108;
              v93[1] = v107;
              *((_WORD *)v93 + 1) = v54;
              *((_DWORD *)v93 + 1) = AccessMask;
              v94 = RtlLengthSid(Sid);
              RtlCopySid(v94, v93 + 8, Sid);
              if ( !(_DWORD)v114 )
                goto LABEL_285;
              v95 = (unsigned int)v114;
              v96 = RtlLengthSid(Sid);
              v97 = hMem;
              goto LABEL_284;
            case 0xBu:
              if ( v54 >= 0xFFFF )
                goto LABEL_316;
              v57 = Sid;
              v59 = RtlAddAccessAllowedObjectAce((PACL)*a3, 4u, v107, AccessMask, v41, v39, Sid);
              if ( v59 < 0 )
                goto LABEL_152;
              v59 = RtlGetAce((PACL)*a3, *((unsigned __int16 *)*a3 + 2) - 1, &Ace);
              if ( v59 < 0 )
                goto LABEL_152;
              v100 = 9;
              if ( *(_BYTE *)Ace == 5 )
                v100 = 11;
              *(_BYTE *)Ace = v100;
              *((_WORD *)Ace + 1) = v54;
              if ( (_DWORD)v114 )
              {
                v101 = (unsigned int)v114;
                if ( *(_BYTE *)Ace == 11 )
                {
                  v102 = *((_DWORD *)Ace + 2);
                  v103 = RtlLengthSid(Sid);
                  memcpy_0((char *)Ace + 16 * (v102 & 1) + 8 * (v102 & 2) + v103 + 12, hMem, (unsigned int)v101);
                }
                else
                {
                  v104 = RtlLengthSid(Sid);
                  memcpy_0((char *)Ace + v104 + 8, hMem, v101);
                }
              }
              goto LABEL_113;
            case 0x12u:
              if ( v54 >= 0xFFFF || (v107 & 0xE0) != 0 || AccessMask )
                goto LABEL_316;
              v57 = Sid;
              v98 = *(_DWORD *)(Sid + 2) - v118;
              if ( !v98 )
                v98 = *((unsigned __int16 *)Sid + 3) - v119;
              if ( v98 || Sid[1] != 1 || *((_DWORD *)Sid + 2) )
                goto LABEL_316;
              v93 = (char *)LocalAlloc(0x40u, v54);
              if ( v93 )
              {
                *v93 = v108;
                v93[1] = v107;
                *((_WORD *)v93 + 1) = v54;
                *((_DWORD *)v93 + 1) = 0;
                v99 = RtlLengthSid(Sid);
                RtlCopySid(v99, v93 + 8, Sid);
                if ( HIDWORD(v114) )
                {
                  v95 = HIDWORD(v114);
                  v96 = RtlLengthSid(Sid);
                  v97 = Src;
LABEL_284:
                  memcpy_0(&v93[v96 + 8], v97, v95);
                }
LABEL_285:
                v59 = RtlAddAce((PACL)*a3, 2u, 0xFFFFFFFF, v93, v54);
                LocalFree(v93);
                goto LABEL_112;
              }
LABEL_315:
              v59 = -1073741801;
              goto LABEL_152;
            case 0x13u:
              v57 = Sid;
              v58 = SddlAddScopedPolicyIDAce((PACL)*a3, Sid);
              break;
            case 0x14u:
              v57 = Sid;
              v58 = SddlAddProcessTrustLabelAce((PACL)*a3, pSid, AccessMask);
              break;
            case 0x15u:
              if ( (unsigned int)v114 >= 0xFFFF )
              {
LABEL_316:
                v59 = -1073741705;
LABEL_152:
                LastError = RtlNtStatusToDosError(v59);
LABEL_153:
                v60 = a3;
LABEL_154:
                v36 = *v60;
                if ( LastError )
                  goto LABEL_106;
                v36[1] = v122;
                goto LABEL_156;
              }
              v57 = Sid;
              v58 = SddlAddAccessFilterAce((PACL)*a3, pSid, AccessMask, hMem, v114);
              break;
            default:
              v59 = -1073741811;
              goto LABEL_152;
          }
        }
      }
      else
      {
        v57 = Sid;
        v58 = RtlAddAccessAllowedAceEx((PACL)*a3, 2u, v107, AccessMask, Sid);
      }
      v59 = v58;
LABEL_112:
      if ( v59 < 0 )
        goto LABEL_152;
LABEL_113:
      if ( v109 == 1 )
        LocalFree(v57);
      Sid = 0;
      v125 = 0;
      if ( hMem )
      {
        LocalFree(hMem);
        hMem = 0;
      }
      LODWORD(v114) = 0;
      if ( Src )
      {
        LocalFree(Src);
        Src = 0;
      }
      HIDWORD(v114) = 0;
      if ( *v12 == 40 )
        ++v12;
      v60 = a3;
      v61 = Size_4 + 1;
      v8 = v115;
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
  v72 = 0;
  while ( 1 )
  {
    v73 = 4LL * v72;
    if ( (v38 & qword_18009F0C8[v73 + 1]) == v38 )
      break;
LABEL_161:
    if ( ++v72 >= 9 )
      goto LABEL_162;
  }
  v74 = HIDWORD(qword_18009F0C8[v73 + 1]);
  if ( v74 )
  {
    for ( n = 0; (unsigned int)n < v74; n = (unsigned int)(n + 1) )
    {
      if ( *(_BYTE *)(n + qword_18009F0C8[v73 + 2]) == v37 )
        goto LABEL_149;
    }
    goto LABEL_160;
  }
LABEL_149:
  v75 = &(&off_18009F0C0)[v73];
  if ( _wcsnicmp(v30, (&off_18009F0C0)[v73], LODWORD(qword_18009F0C8[v73])) )
  {
    v37 = v108;
LABEL_160:
    v38 = v113;
    goto LABEL_161;
  }
  if ( v75 )
  {
    v71 |= *((_BYTE *)v75 + 12);
    v37 = v108;
    v38 = v113;
    v30 += *((unsigned int *)v75 + 2);
    v107 = v71;
    goto LABEL_143;
  }
LABEL_162:
  LastError = 1004;
  v36 = *a3;
LABEL_106:
  LocalFree(v36);
  *a3 = 0;
LABEL_156:
  if ( v109 && Sid )
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
0x18001b480  mov     [rsp-8+arg_8], rbx
0x18001b485  push    rbp
0x18001b486  push    rsi
0x18001b487  push    rdi
0x18001b488  push    r12
0x18001b48a  push    r13
0x18001b48c  push    r14
0x18001b48e  push    r15
0x18001b490  lea     rbp, [rsp-80h]
0x18001b495  sub     rsp, 180h
0x18001b49c  mov     rax, cs:__security_cookie
0x18001b4a3  xor     rax, rsp
0x18001b4a6  mov     [rbp+0B0h+var_40], rax
0x18001b4aa  mov     rax, [rbp+0B0h+arg_20]
0x18001b4b1  xor     r12d, r12d
0x18001b4b4  mov     [rbp+0B0h+var_E0], rax
0x18001b4b8  mov     r14, r9
0x18001b4bb  mov     rax, [rbp+0B0h+arg_28]
0x18001b4c2  mov     rdi, r8
0x18001b4c5  mov     [rbp+0B0h+var_E8], rax
0x18001b4c9  movzx   ebx, dl
0x18001b4cc  mov     rax, [rbp+0B0h+arg_30]
0x18001b4d3  mov     rsi, rcx
0x18001b4d6  mov     [rbp+0B0h+var_F0], rax
0x18001b4da  mov     [rbp+0B0h+var_C0], r9
0x18001b4de  mov     [rsp+1B0h+var_158], r8
0x18001b4e3  mov     [rbp+0B0h+EndPtr], r12
0x18001b4e7  mov     [rsp+1B0h+Sid], r12
0x18001b4ec  mov     [rbp+0B0h+var_F8], r12
0x18001b4f0  mov     [rbp+0B0h+hMem], r12
0x18001b4f4  mov     dword ptr [rsp+1B0h+var_13C], r12d
0x18001b4f9  mov     [rbp+0B0h+Src], r12
0x18001b4fd  mov     dword ptr [rsp+1B0h+var_13C+4], r12d
0x18001b502  mov     [rbp+0B0h+Ace], r12
0x18001b506  mov     [rbp+0B0h+var_130], r12
0x18001b50a  mov     [rbp+0B0h+var_120], r12d
0x18001b50e  mov     [rbp+0B0h+var_11C], 100h
0x18001b514  test    rcx, rcx
0x18001b517  jz      loc_18001C85A
0x18001b51d  test    r8, r8
0x18001b520  jz      loc_18001C85A
0x18001b526  test    r9, r9
0x18001b529  jz      loc_18001C85A
0x18001b52f  mov     r8d, 11h; MaxCount
0x18001b535  lea     rdx, aNoAccessContro; "NO_ACCESS_CONTROL"
0x18001b53c  call    cs:__imp__wcsnicmp
0x18001b542  test    eax, eax
0x18001b544  jz      loc_18001C0CD
0x18001b54a  neg     bl
0x18001b54c  mov     [r14], r12
0x18001b54f  mov     rcx, rsi; String1
0x18001b552  sbb     eax, eax
0x18001b554  add     eax, 2
0x18001b557  mov     [rsp+1B0h+var_140], eax
0x18001b55b  call    FContainCallBackAce
0x18001b560  mov     r13d, 0FFFFFFFFh
0x18001b566  test    eax, eax
0x18001b568  jnz     loc_18001B68A
0x18001b56e  mov     edx, 3Ah ; ':'; Ch
0x18001b573  mov     rcx, rsi; Str
0x18001b576  call    cs:__imp_wcschr
0x18001b57c  mov     [r14], rax
0x18001b57f  mov     rdi, [r14]
0x18001b582  cmp     rdi, rsi
0x18001b585  jz      loc_18001C85A
0x18001b58b  test    rdi, rdi
0x18001b58e  jnz     loc_18001B674
0x18001b594  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001b59b  nop     dword ptr [rax+rax+00h]
0x18001b5a0  cmp     [rsi+rax*2+2], r12w
0x18001b5a6  lea     rax, [rax+1]
0x18001b5aa  jnz     short loc_18001B5A0
0x18001b5ac  lea     rdi, [rsi+rax*2]
0x18001b5b0  mov     [r14], rdi
0x18001b5b3  mov     rcx, rsi; String1
0x18001b5b6  mov     r14d, r12d
0x18001b5b9  mov     [rsp+1B0h+var_134], r12d
0x18001b5be  mov     r15d, r12d
0x18001b5c1  mov     rbx, rsi
0x18001b5c4  call    FContainCallBackAce
0x18001b5c9  xor     r8d, r8d
0x18001b5cc  test    eax, eax
0x18001b5ce  jnz     loc_18001B6FB
0x18001b5d4  cmp     rsi, rdi
0x18001b5d7  jnb     short loc_18001B5FB
0x18001b5d9  mov     ecx, 1
0x18001b5de  xchg    ax, ax
0x18001b5e0  movzx   eax, word ptr [rbx]
0x18001b5e3  cmp     ax, 3Bh ; ';'
0x18001b5e7  jz      short loc_18001B667
0x18001b5e9  cmp     ax, 28h ; '('
0x18001b5ed  jz      short loc_18001B5F2
0x18001b5ef  mov     r8d, ecx
0x18001b5f2  add     rbx, 2
0x18001b5f6  cmp     rbx, rdi
0x18001b5f9  jb      short loc_18001B5E0
0x18001b5fb  mov     eax, 0CCCCCCCDh
0x18001b600  mul     r14d
0x18001b603  shr     edx, 2
0x18001b606  lea     ecx, [rdx+rdx*4]
0x18001b609  cmp     r14d, ecx
0x18001b60c  jnz     short loc_18001B66C
0x18001b60e  test    r14d, r14d
0x18001b611  jz      short loc_18001B67D
0x18001b613  mov     r12d, edx
0x18001b616  mov     [rsp+1B0h+var_134], edx
0x18001b61a  test    r15d, r15d
0x18001b61d  jz      loc_18001BFBD
0x18001b623  mov     rcx, [rbp+0B0h+hMem]; hMem
0x18001b627  test    rcx, rcx
0x18001b62a  jnz     loc_18001C841
0x18001b630  mov     rcx, [rbp+0B0h+Src]; hMem
0x18001b634  test    rcx, rcx
0x18001b637  jnz     loc_18001C84C
0x18001b63d  mov     eax, r15d
0x18001b640  mov     rcx, [rbp+0B0h+var_40]
0x18001b644  xor     rcx, rsp; StackCookie
0x18001b647  call    __security_check_cookie
0x18001b64c  mov     rbx, [rsp+1B0h+arg_8]
0x18001b654  add     rsp, 180h
0x18001b65b  pop     r15
0x18001b65d  pop     r14
0x18001b65f  pop     r13
0x18001b661  pop     r12
0x18001b663  pop     rdi
0x18001b664  pop     rsi
0x18001b665  pop     rbp
0x18001b666  retn
0x18001b667  inc     r14d
0x18001b66a  jmp     short loc_18001B5F2
0x18001b66c  mov     r15d, 57h ; 'W'
0x18001b672  jmp     short loc_18001B61A
0x18001b674  add     rdi, 0FFFFFFFFFFFFFFFEh
0x18001b678  jmp     loc_18001B5B0
0x18001b67d  test    r8d, r8d
0x18001b680  jz      short loc_18001B613
0x18001b682  mov     r15d, 57h ; 'W'
0x18001b688  jmp     short loc_18001B623
0x18001b68a  mov     r10d, r12d
0x18001b68d  mov     r9d, r12d
0x18001b690  mov     r8d, r12d
0x18001b693  mov     rdx, rsi
0x18001b696  cmp     [rsi], r12w
0x18001b69a  jz      loc_18001B57F
0x18001b6a0  cmp     [r14], r12
0x18001b6a3  jnz     short loc_18001B6DB
0x18001b6a5  test    r8d, r8d
0x18001b6a8  jnz     short loc_18001B6DB
0x18001b6aa  movzx   ecx, word ptr [rdx]
0x18001b6ad  sub     ecx, 22h ; '"'
0x18001b6b0  jz      loc_18001C117
0x18001b6b6  sub     ecx, 6
0x18001b6b9  jz      loc_18001C106
0x18001b6bf  sub     ecx, 1
0x18001b6c2  jz      loc_18001C0F0
0x18001b6c8  cmp     ecx, 11h
0x18001b6cb  jz      loc_18001C0DF
0x18001b6d1  add     rdx, 2
0x18001b6d5  cmp     [rdx], r12w
0x18001b6d9  jnz     short loc_18001B6A0
0x18001b6db  test    r10d, r10d
0x18001b6de  jnz     loc_18001C139
0x18001b6e4  test    r9d, r9d
0x18001b6e7  jnz     loc_18001C139
0x18001b6ed  test    r8d, r8d
0x18001b6f0  jz      loc_18001B57F
0x18001b6f6  jmp     loc_18001C13F
0x18001b6fb  xor     edx, edx
0x18001b6fd  cmp     rsi, rdi
0x18001b700  jb      loc_18001C147
0x18001b706  cmp     rbx, rdi
0x18001b709  jnz     loc_18001C15B
0x18001b70f  mov     ecx, 1
0x18001b714  cmp     rbx, rdi
0x18001b717  jnb     loc_18001C16C
0x18001b71d  movzx   eax, word ptr [rbx]
0x18001b720  cmp     ax, 20h ; ' '
0x18001b724  jz      short loc_18001B740
0x18001b726  test    ecx, ecx
0x18001b728  jnz     loc_18001B682
0x18001b72e  cmp     ax, 28h ; '('
0x18001b732  jz      short loc_18001B755
0x18001b734  cmp     ax, 29h ; ')'
0x18001b738  jz      short loc_18001B762
0x18001b73a  cmp     ax, 3Bh ; ';'
0x18001b73e  jz      short loc_18001B74C
0x18001b740  cmp     ax, 22h ; '"'
0x18001b744  jz      short loc_18001B792
0x18001b746  add     rbx, 2
0x18001b74a  jmp     short loc_18001B714
0x18001b74c  inc     r14d
0x18001b74f  add     rbx, 2
0x18001b753  jmp     short loc_18001B714
0x18001b755  test    r8d, r8d
0x18001b758  jnz     short loc_18001B746
0x18001b75a  inc     edx
0x18001b75c  add     rbx, 2
0x18001b760  jmp     short loc_18001B714
0x18001b762  test    r8d, r8d
0x18001b765  jnz     short loc_18001B746
0x18001b767  test    edx, edx
0x18001b769  jz      loc_18001C174
0x18001b76f  cmp     edx, 1
0x18001b772  jnz     short loc_18001B789
0x18001b774  cmp     r14d, 5
0x18001b778  jb      loc_18001C174
0x18001b77e  xor     r14d, r14d
0x18001b781  inc     r12d
0x18001b784  mov     [rsp+1B0h+var_134], r12d
0x18001b789  add     edx, r13d
0x18001b78c  add     rbx, 2
0x18001b790  jmp     short loc_18001B714
0x18001b792  xor     eax, eax
0x18001b794  test    r8d, r8d
0x18001b797  setz    al
0x18001b79a  mov     r8d, eax
0x18001b79d  jmp     short loc_18001B746
0x18001b79f  add     r13, 2
0x18001b7a3  xor     r14d, r14d
0x18001b7a6  cmp     word ptr [r13+0], 20h ; ' '
0x18001b7ac  mov     [rsp+1B0h+AccessMask], r14d
0x18001b7b1  jz      loc_18001C1D4
0x18001b7b7  nop     word ptr [rax+rax+00000000h]
0x18001b7c0  movzx   eax, word ptr [r13+0]
0x18001b7c5  cmp     ax, 3Bh ; ';'
0x18001b7c9  jz      loc_18001B891
0x18001b7cf  cmp     ax, 20h ; ' '
0x18001b7d3  jz      loc_18001C1E5
0x18001b7d9  cmp     r10b, 11h
0x18001b7dd  mov     edi, r8d
0x18001b7e0  mov     r9d, 4
0x18001b7e6  cmovz   edi, r9d
0x18001b7ea  xor     ebx, ebx
0x18001b7ec  lea     rcx, [rbx+rbx*2]
0x18001b7f0  mov     eax, rva dword_18009F1F0[r11+rcx*8]
0x18001b7f8  and     eax, edi
0x18001b7fa  cmp     eax, edi
0x18001b7fc  jnz     short loc_18001B828
0x18001b7fe  mov     r8d, rva dword_18009F1E8[r11+rcx*8]; MaxCount
0x18001b806  lea     rsi, ds:9F1E0h[rcx*8]
0x18001b80e  add     rsi, r11
0x18001b811  mov     rcx, r13; String1
0x18001b814  mov     rdx, [rsi]; String2
0x18001b817  call    cs:__imp__wcsnicmp
0x18001b81d  test    eax, eax
0x18001b81f  jz      short loc_18001B85F
0x18001b821  lea     r11, __ImageBase
0x18001b828  inc     ebx
0x18001b82a  cmp     ebx, 1Ch
0x18001b82d  jb      short loc_18001B7EC
0x18001b82f  xor     r8d, r8d; Radix
0x18001b832  lea     rdx, [rbp+0B0h+EndPtr]; EndPtr
0x18001b836  mov     rcx, r13; String
0x18001b839  call    cs:__imp_wcstoul
0x18001b83f  mov     rcx, [rbp+0B0h+EndPtr]
0x18001b843  cmp     rcx, r13
0x18001b846  jnz     loc_18001BE82
0x18001b84c  mov     r15d, 538h; jumptable 000000018001BF5D default case, cases 3,4,12,14-16
0x18001b852  mov     rax, [rsp+1B0h+var_158]
0x18001b857  mov     rax, [rax]
0x18001b85a  jmp     loc_18001BA03
0x18001b85f  mov     [rsp+1B0h+var_134], r12d
0x18001b864  test    rsi, rsi
0x18001b867  jz      short loc_18001B82F
0x18001b869  mov     eax, [rsi+8]
0x18001b86c  lea     r11, __ImageBase
0x18001b873  or      r14d, [rsi+0Ch]
0x18001b877  movzx   r10d, [rsp+1B0h+var_15F]
0x18001b87d  mov     r8d, [rsp+1B0h+var_140]
0x18001b882  lea     r13, [r13+rax*2+0]
0x18001b887  mov     [rsp+1B0h+AccessMask], r14d
0x18001b88c  jmp     loc_18001B7C0
0x18001b891  xor     r14d, r14d
0x18001b894  add     r13, 2
0x18001b898  xor     r12d, r12d
0x18001b89b  mov     [rbp+0B0h+var_C8], r14
0x18001b89f  xor     ebx, ebx
0x18001b8a1  movzx   eax, word ptr [r13+0]
0x18001b8a6  cmp     ebx, 2
0x18001b8a9  jnb     short loc_18001B8C7
0x18001b8ab  cmp     ax, 20h ; ' '
0x18001b8af  jz      loc_18001C1F6
0x18001b8b5  cmp     ax, 3Bh ; ';'
0x18001b8b9  jnz     loc_18001C20A
0x18001b8bf  add     r13, 2
0x18001b8c3  inc     ebx
0x18001b8c5  jmp     short loc_18001B8A1
0x18001b8c7  cmp     ax, 20h ; ' '
0x18001b8cb  jz      loc_18001C296
0x18001b8d1  xor     dil, dil
0x18001b8d4  mov     [rbp+0B0h+var_D0], 0
0x18001b8dc  mov     [rsp+1B0h+var_15E], dil
0x18001b8e1  test    ax, ax
0x18001b8e4  jz      loc_18001BF73
0x18001b8ea  cmp     word ptr [r13+2], 0
0x18001b8f0  jz      loc_18001BF73
0x18001b8f6  mov     r9, [rbp+0B0h+var_E8]
0x18001b8fa  lea     rax, [r13+4]
0x18001b8fe  mov     r8, [rbp+0B0h+var_E0]
0x18001b902  xor     edx, edx; Sid2
  ... truncated ...
```
