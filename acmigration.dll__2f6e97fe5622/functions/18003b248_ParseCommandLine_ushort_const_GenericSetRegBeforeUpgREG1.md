# ParseCommandLine(ushort const *,_GenericSetRegBeforeUpgREG1 *)

- ea: `0x18003b248`
- end: `0x18003bfd4`
- name: `?ParseCommandLine@@YAHPEBGPEAU_GenericSetRegBeforeUpgREG1@@@Z`
- size: `3468`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _GenericSetRegBeforeUpgREG1 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003ad60`

## callees

- `0x180001cf0`
- `0x18000b5fc`
- `0x18000b720`
- `0x18000e0e4`
- `0x18000e504`
- `0x180010718`
- `0x180010730`
- `0x180011d40`
- `0x18003b054`
- `0x18003b248`
- `0x1800543c0`
- `0x180065144`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18003bf97`
- `KERNEL32!LocalFree` at `0x18003bf97`
- `ntdll!RtlAllocateHeap` at `0x18003ba83`
- `ntdll!RtlAllocateHeap` at `0x18003bb5c`
- `ntdll!RtlAllocateHeap` at `0x18003bc46`
- `ntdll!RtlAllocateHeap` at `0x18003bd76`
- `ntdll!RtlAllocateHeap` at `0x18003ba83`
- `ntdll!RtlAllocateHeap` at `0x18003bb5c`
- `ntdll!RtlAllocateHeap` at `0x18003bc46`
- `ntdll!RtlAllocateHeap` at `0x18003bd76`
- `SHLWAPI!StrToInt64ExW` at `0x18003ba4c`
- `SHLWAPI!StrToInt64ExW` at `0x18003ba4c`
- `SHELL32!CommandLineToArgvW` at `0x18003b296`
- `SHELL32!CommandLineToArgvW` at `0x18003b296`

## string_xrefs

- `0x18003bf71`: `GenericSetRegBeforeUpgMigrationShim:CommandLineToArgvW failed, %ws, numArgs=%d`
- `0x18003b2db`: `ParseCommandLine`
- `0x18003b41c`: `ParseCommandLine`
- `0x18003b487`: `ParseCommandLine`
- `0x18003b4ef`: `ParseCommandLine`
- `0x18003b55d`: `ParseCommandLine`
- `0x18003b627`: `ParseCommandLine`
- `0x18003b7b1`: `ParseCommandLine`
- `0x18003bab5`: `ParseCommandLine`
- `0x18003bb8e`: `ParseCommandLine`
- `0x18003bc78`: `ParseCommandLine`
- `0x18003bcfc`: `ParseCommandLine`
- `0x18003bda8`: `ParseCommandLine`
- `0x18003be8b`: `ParseCommandLine`
- `0x18003bf0b`: `ParseCommandLine`
- `0x18003bf7e`: `ParseCommandLine`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ParseCommandLine(const unsigned __int16 *a1, struct _GenericSetRegBeforeUpgREG1 *a2)
{
  LPWSTR *v4; // rax
  LPWSTR *v5; // r12
  unsigned int v6; // r13d
  LPWSTR v7; // rdx
  __int64 v8; // r14
  __int64 v9; // r8
  LPWSTR v10; // rdx
  __int64 v11; // r8
  LPWSTR v12; // rdx
  __int64 v13; // r8
  LPWSTR v14; // rdx
  __int64 v15; // r8
  LPWSTR v16; // rdx
  __int64 v17; // r8
  unsigned __int64 v18; // rsi
  const wchar_t *v19; // rcx
  size_t v20; // r8
  wchar_t **v21; // rcx
  unsigned __int64 v22; // rsi
  const wchar_t *v23; // rcx
  size_t v24; // r8
  unsigned __int64 v25; // rsi
  const wchar_t *v26; // rcx
  size_t v27; // r8
  unsigned __int64 v28; // r15
  const wchar_t *v29; // rcx
  size_t v30; // r8
  __int128 *v31; // rax
  unsigned __int64 v32; // rcx
  __int128 *v33; // rax
  unsigned __int64 v34; // r14
  const wchar_t *v35; // rcx
  size_t v36; // r8
  unsigned __int64 v37; // r14
  const wchar_t *v38; // rcx
  size_t v39; // r8
  unsigned __int64 v40; // r14
  const wchar_t *v41; // rcx
  size_t v42; // r8
  unsigned __int64 v43; // r14
  const wchar_t *v44; // rcx
  size_t v45; // r8
  unsigned __int64 v46; // r14
  const wchar_t *v47; // rcx
  size_t v48; // r8
  const WCHAR *v49; // rcx
  PVOID Heap; // rax
  wchar_t **v51; // rax
  PCWSTR p_pllRet; // rdx
  __int64 v53; // rcx
  unsigned int v54; // edx
  PCWSTR *v55; // rax
  PVOID v56; // rax
  wchar_t **v57; // rax
  PCWSTR *v58; // rdx
  _WORD *i; // rcx
  wchar_t **v60; // rax
  PCWSTR *v61; // rax
  unsigned int v62; // eax
  wchar_t **v63; // rax
  wchar_t **v64; // rax
  wchar_t **v65; // rax
  int pNumArgs; // [rsp+30h] [rbp-118h] BYREF
  int v68; // [rsp+34h] [rbp-114h]
  int v69; // [rsp+38h] [rbp-110h] BYREF
  LONGLONG pllRet; // [rsp+40h] [rbp-108h] BYREF
  LPWSTR *v71; // [rsp+48h] [rbp-100h]
  __int64 v72; // [rsp+50h] [rbp-F8h]
  wchar_t *v73[2]; // [rsp+58h] [rbp-F0h] BYREF
  unsigned __int64 v74; // [rsp+68h] [rbp-E0h]
  unsigned __int64 v75; // [rsp+70h] [rbp-D8h]
  PCWSTR pszString[2]; // [rsp+78h] [rbp-D0h] BYREF
  __int64 v77; // [rsp+88h] [rbp-C0h]
  unsigned __int64 v78; // [rsp+90h] [rbp-B8h]
  wchar_t *v79[2]; // [rsp+98h] [rbp-B0h] BYREF
  unsigned __int64 v80; // [rsp+A8h] [rbp-A0h]
  unsigned __int64 v81; // [rsp+B0h] [rbp-98h]
  __int128 v82; // [rsp+B8h] [rbp-90h] BYREF
  unsigned __int64 v83; // [rsp+C8h] [rbp-80h]
  unsigned __int64 v84; // [rsp+D0h] [rbp-78h]
  wchar_t *S1[2]; // [rsp+D8h] [rbp-70h] BYREF
  unsigned __int64 v86; // [rsp+E8h] [rbp-60h]
  unsigned __int64 v87; // [rsp+F0h] [rbp-58h]
  _OWORD v88[2]; // [rsp+F8h] [rbp-50h] BYREF

  v72 = -2;
  pNumArgs = 0;
  pllRet = 0;
  v4 = CommandLineToArgvW(a1, &pNumArgs);
  v5 = v4;
  v71 = v4;
  if ( v4 && pNumArgs >= 1 )
  {
    v6 = 0;
    v68 = 0;
    if ( pNumArgs != 5 )
    {
      AslLogCallPrintf(
        1,
        "ParseCommandLine",
        193,
        "GenericSetRegBeforeUpgMigrationShim:Wrong arguments number: %d",
        pNumArgs);
LABEL_152:
      LocalFree(v5);
      return v6;
    }
    v7 = *v4;
    *(_OWORD *)v79 = 0;
    v80 = 0;
    v81 = 0;
    v8 = -1;
    v9 = -1;
    do
      ++v9;
    while ( v7[v9] );
    try
    {
      std::wstring::_Construct<1,unsigned short const *>(v79, v7, v9);
      v10 = v5[1];
      v82 = 0;
      v83 = 0;
      v84 = 0;
      v11 = -1;
      do
        ++v11;
      while ( v10[v11] );
      std::wstring::_Construct<1,unsigned short const *>(&v82, v10, v11);
      v12 = v5[2];
      *(_OWORD *)v73 = 0;
      v74 = 0;
      v75 = 0;
      v13 = -1;
      do
        ++v13;
      while ( v12[v13] );
      std::wstring::_Construct<1,unsigned short const *>(v73, v12, v13);
      v14 = v5[3];
      *(_OWORD *)S1 = 0;
      v86 = 0;
      v87 = 0;
      v15 = -1;
      do
        ++v15;
      while ( v14[v15] );
      std::wstring::_Construct<1,unsigned short const *>(S1, v14, v15);
      v16 = v5[4];
      *(_OWORD *)pszString = 0;
      v77 = 0;
      v78 = 0;
      v17 = -1;
      do
        ++v17;
      while ( v16[v17] );
      std::wstring::_Construct<1,unsigned short const *>(pszString, v16, v17);
      if ( !v80 )
      {
        AslLogCallPrintf(1, "ParseCommandLine", 218, "GenericSetRegBeforeUpgMigrationShim:Operation is NULL");
        std::wstring::~wstring(pszString);
        std::wstring::~wstring(S1);
        std::wstring::~wstring(v73);
        std::wstring::~wstring(&v82);
        std::wstring::~wstring(v79);
        goto LABEL_157;
      }
      if ( !v83 )
      {
        AslLogCallPrintf(1, "ParseCommandLine", 224, "GenericSetRegBeforeUpgMigrationShim:RegKey is NULL");
        std::wstring::~wstring(pszString);
        std::wstring::~wstring(S1);
        std::wstring::~wstring(v73);
        std::wstring::~wstring(&v82);
        std::wstring::~wstring(v79);
        goto LABEL_157;
      }
      if ( !v74 )
      {
        AslLogCallPrintf(1, "ParseCommandLine", 230, "GenericSetRegBeforeUpgMigrationShim:ValueType is NULL");
        std::wstring::~wstring(pszString);
        std::wstring::~wstring(S1);
        std::wstring::~wstring(v73);
        std::wstring::~wstring(&v82);
        std::wstring::~wstring(v79);
        goto LABEL_157;
      }
      v18 = v86;
      if ( !v86 )
      {
        AslLogCallPrintf(1, "ParseCommandLine", 236, "GenericSetRegBeforeUpgMigrationShim:ValueName is NULL");
        std::wstring::~wstring(pszString);
        std::wstring::~wstring(S1);
        std::wstring::~wstring(v73);
        std::wstring::~wstring(&v82);
        std::wstring::~wstring(v79);
        goto LABEL_157;
      }
      v19 = (const wchar_t *)S1;
      if ( v87 > 7 )
        v19 = S1[0];
      v20 = v86;
      if ( v86 > 1 )
        v20 = 1;
      if ( !wmemcmp(v19, L"@", v20) && v18 == 1 )
      {
        v21 = S1;
        if ( v87 > 7 )
          v21 = (wchar_t **)S1[0];
        v86 = 0;
        *(_WORD *)v21 = 0;
      }
      if ( !v77 )
      {
        AslLogCallPrintf(1, "ParseCommandLine", 247, "GenericSetRegBeforeUpgMigrationShimg:Data is NULL");
        std::wstring::~wstring(pszString);
        std::wstring::~wstring(S1);
        std::wstring::~wstring(v73);
        std::wstring::~wstring(&v82);
        std::wstring::~wstring(v79);
        goto LABEL_157;
      }
      v22 = v80;
      v23 = (const wchar_t *)v79;
      if ( v81 > 7 )
        v23 = v79[0];
      v24 = v80;
      if ( v80 > 6 )
        v24 = 6;
      if ( !wmemcmp(v23, L"Before", v24) && v22 == 6 )
      {
        *(_BYTE *)a2 = 1;
      }
      else
      {
        v25 = v80;
        v26 = (const wchar_t *)v79;
        if ( v81 > 7 )
          v26 = v79[0];
        v27 = v80;
        if ( v80 > 5 )
          v27 = 5;
        if ( !wmemcmp(v26, L"After", v27) && v25 == 5 )
        {
          *(_BYTE *)a2 = 2;
        }
        else
        {
          v28 = v80;
          v29 = (const wchar_t *)v79;
          if ( v81 > 7 )
            v29 = v79[0];
          v30 = v80;
          if ( v80 > 4 )
            v30 = 4;
          if ( wmemcmp(v29, L"Both", v30) || v28 != 4 )
          {
            v65 = v79;
            if ( v81 > 7 )
              v65 = (wchar_t **)v79[0];
            AslLogCallPrintf(
              1,
              "ParseCommandLine",
              269,
              "GenericSetRegBeforeUpgMigrationShim: Incorrect Operation parameter %ws",
              v65);
            std::wstring::~wstring(pszString);
            std::wstring::~wstring(S1);
            std::wstring::~wstring(v73);
            std::wstring::~wstring(&v82);
            std::wstring::~wstring(v79);
            goto LABEL_157;
          }
          *(_BYTE *)a2 = 3;
        }
      }
      if ( !(unsigned int)GetRootKey(&v82, (char *)a2 + 8) )
      {
        v31 = &v82;
        if ( v84 > 7 )
          v31 = (__int128 *)v82;
        AslLogCallPrintf(
          1,
          "ParseCommandLine",
          278,
          "GenericSetRegBeforeUpgMigrationShim: Incorrect RegKey parameter  %ws",
          v31);
        std::wstring::~wstring(pszString);
        std::wstring::~wstring(S1);
        std::wstring::~wstring(v73);
        std::wstring::~wstring(&v82);
        std::wstring::~wstring(v79);
        goto LABEL_157;
      }
      v32 = std::wstring::find(&v82, L"\\") + 1;
      memset(v88, 0, sizeof(v88));
      if ( v83 < v32 )
        std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
      if ( v83 - v32 != -1 )
        v8 = v83 - v32;
      v33 = &v82;
      if ( v84 > 7 )
        v33 = (__int128 *)v82;
      std::wstring::_Construct<1,unsigned short const *>(v88, (char *)v33 + 2 * v32, v8);
      std::wstring::operator=((char *)a2 + 16, v88);
      std::wstring::~wstring(v88);
      v34 = v74;
      v35 = (const wchar_t *)v73;
      if ( v75 > 7 )
        v35 = v73[0];
      v36 = v74;
      if ( v74 > 9 )
        v36 = 9;
      if ( !wmemcmp(v35, L"REG_DWORD", v36) && v34 == 9 )
      {
        *((_DWORD *)a2 + 12) = 4;
      }
      else
      {
        v37 = v74;
        v38 = (const wchar_t *)v73;
        if ( v75 > 7 )
          v38 = v73[0];
        v39 = v74;
        if ( v74 > 9 )
          v39 = 9;
        if ( !wmemcmp(v38, L"REG_QWORD", v39) && v37 == 9 )
        {
          *((_DWORD *)a2 + 12) = 11;
        }
        else
        {
          v40 = v74;
          v41 = (const wchar_t *)v73;
          if ( v75 > 7 )
            v41 = v73[0];
          v42 = v74;
          if ( v74 > 6 )
            v42 = 6;
          if ( !wmemcmp(v41, L"REG_SZ", v42) && v40 == 6 )
          {
            *((_DWORD *)a2 + 12) = 1;
          }
          else
          {
            v43 = v74;
            v44 = (const wchar_t *)v73;
            if ( v75 > 7 )
              v44 = v73[0];
            v45 = v74;
            if ( v74 > 0xD )
              v45 = 13;
            if ( !wmemcmp(v44, L"REG_EXPAND_SZ", v45) && v43 == 13 )
            {
              *((_DWORD *)a2 + 12) = 2;
            }
            else
            {
              v46 = v74;
              v47 = (const wchar_t *)v73;
              if ( v75 > 7 )
                v47 = v73[0];
              v48 = v74;
              if ( v74 > 0xC )
                v48 = 12;
              if ( wmemcmp(v47, L"REG_MULTI_SZ", v48) || v46 != 12 )
              {
                v64 = v73;
                if ( v75 > 7 )
                  v64 = (wchar_t **)v73[0];
                AslLogCallPrintf(
                  1,
                  "ParseCommandLine",
                  310,
                  "GenericSetRegBeforeUpgMigrationShim: Incorrect ValueType parameter %ws",
                  v64);
                std::wstring::~wstring(pszString);
                std::wstring::~wstring(S1);
                std::wstring::~wstring(v73);
                std::wstring::~wstring(&v82);
                std::wstring::~wstring(v79);
                goto LABEL_157;
              }
              *((_DWORD *)a2 + 12) = 7;
            }
          }
        }
      }
      std::wstring::operator=((char *)a2 + 56, S1);
      if ( *((_DWORD *)a2 + 12) == 1 || *((_DWORD *)a2 + 12) == 2 )
      {
        v62 = 2 * v77 + 2;
        *((_DWORD *)a2 + 22) = v62;
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v62);
        *((_QWORD *)a2 + 12) = Heap;
        if ( !Heap )
        {
          v63 = v73;
          if ( v75 > 7 )
            v63 = (wchar_t **)v73[0];
          AslLogCallPrintf(
            1,
            "ParseCommandLine",
            365,
            "GenericSetRegBeforeUpgMigrationShim: Allocate Data memory failed for ValueName %ws",
            v63);
          std::wstring::~wstring(pszString);
          std::wstring::~wstring(S1);
          std::wstring::~wstring(v73);
          std::wstring::~wstring(&v82);
          std::wstring::~wstring(v79);
          goto LABEL_157;
        }
        p_pllRet = (PCWSTR)pszString;
        if ( v78 > 7 )
          p_pllRet = pszString[0];
      }
      else
      {
        if ( *((_DWORD *)a2 + 12) != 4 )
        {
          if ( *((_DWORD *)a2 + 12) == 7 )
          {
            v53 = v77;
            v54 = 2 * v77 + 2;
            *((_DWORD *)a2 + 22) = v54;
            v55 = pszString;
            if ( v78 > 7 )
              v55 = (PCWSTR *)pszString[0];
            if ( *((_WORD *)v55 + v53 - 1) != 59 )
            {
              v54 += 2;
              *((_DWORD *)a2 + 22) = v54;
            }
            v56 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v54);
            *((_QWORD *)a2 + 12) = v56;
            if ( !v56 )
            {
              v57 = v73;
              if ( v75 > 7 )
                v57 = (wchar_t **)v73[0];
              AslLogCallPrintf(
                1,
                "ParseCommandLine",
                385,
                "GenericSetRegBeforeUpgMigrationShim: Allocate Data memory failed for ValueName %ws",
                v57);
              std::wstring::~wstring(pszString);
              std::wstring::~wstring(S1);
              std::wstring::~wstring(v73);
              std::wstring::~wstring(&v82);
              std::wstring::~wstring(v79);
              goto LABEL_157;
            }
            v58 = pszString;
            if ( v78 > 7 )
              v58 = (PCWSTR *)pszString[0];
            memcpy_0(v56, v58, 2 * v77 + 2);
            for ( i = (_WORD *)*((_QWORD *)a2 + 12); *i; ++i )
            {
              if ( *i == 59 )
                *i = 0;
            }
            goto LABEL_144;
          }
          if ( *((_DWORD *)a2 + 12) != 11 )
          {
LABEL_144:
            v6 = 1;
            v68 = 1;
            std::wstring::~wstring(pszString);
            std::wstring::~wstring(S1);
            std::wstring::~wstring(v73);
            std::wstring::~wstring(&v82);
            std::wstring::~wstring(v79);
            goto LABEL_157;
          }
        }
        v49 = (const WCHAR *)pszString;
        if ( v78 > 7 )
          v49 = pszString[0];
        if ( !StrToInt64ExW(v49, 1, &pllRet) )
        {
          v61 = pszString;
          if ( v78 > 7 )
            v61 = (PCWSTR *)pszString[0];
          AslLogCallPrintf(
            1,
            "ParseCommandLine",
            354,
            "GenericSetRegBeforeUpgMigrationShim: Incorrect ValueData parameter %ws",
            v61);
          std::wstring::~wstring(pszString);
          std::wstring::~wstring(S1);
          std::wstring::~wstring(v73);
          std::wstring::~wstring(&v82);
          std::wstring::~wstring(v79);
          goto LABEL_157;
        }
        if ( *((_DWORD *)a2 + 12) == 4 )
        {
          v69 = pllRet;
          *((_DWORD *)a2 + 22) = 4;
          Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 4u);
          *((_QWORD *)a2 + 12) = Heap;
          if ( !Heap )
          {
            v51 = v73;
            if ( v75 > 7 )
              v51 = (wchar_t **)v73[0];
            AslLogCallPrintf(
              1,
              "ParseCommandLine",
              334,
              "GenericSetRegBeforeUpgMigrationShim: Allocate Data memory failed for ValueName %ws",
              v51);
            std::wstring::~wstring(pszString);
            std::wstring::~wstring(S1);
            std::wstring::~wstring(v73);
            std::wstring::~wstring(&v82);
            std::wstring::~wstring(v79);
            goto LABEL_157;
          }
          p_pllRet = (PCWSTR)&v69;
        }
        else
        {
          *((_DWORD *)a2 + 22) = 8;
          Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 8u);
          *((_QWORD *)a2 + 12) = Heap;
          if ( !Heap )
          {
            v60 = v73;
            if ( v75 > 7 )
              v60 = (wchar_t **)v73[0];
            AslLogCallPrintf(
              1,
              "ParseCommandLine",
              346,
              "GenericSetRegBeforeUpgMigrationShim: Allocate Data memory failed for ValueName %ws",
              v60);
            std::wstring::~wstring(pszString);
            std::wstring::~wstring(S1);
            std::wstring::~wstring(v73);
            std::wstring::~wstring(&v82);
            std::wstring::~wstring(v79);
            goto LABEL_157;
          }
          p_pllRet = (PCWSTR)&pllRet;
        }
      }
      memcpy_0(Heap, p_pllRet, *((unsigned int *)a2 + 22));
      goto LABEL_144;
    }
    catch ( ... )
    {
      AslLogCallPrintf(
        1,
        "ParseCommandLine",
        411,
        "GenericSetRegBeforeUpgMigrationShim:ParseCommandLine: exception occured");
      v6 = v68;
      v5 = v71;
      goto LABEL_152;
    }
LABEL_157:
    goto LABEL_152;
  }
  AslLogCallPrintf(
    1,
    "ParseCommandLine",
    188,
    "GenericSetRegBeforeUpgMigrationShim:CommandLineToArgvW failed, %ws, numArgs=%d",
    a1,
    pNumArgs);
  v6 = 0;
  if ( v5 )
    goto LABEL_152;
  return v6;
}

```

## disassembly

```asm
0x18003b248  mov     rax, rsp
0x18003b24b  push    rdi
0x18003b24c  push    r12
0x18003b24e  push    r13
0x18003b250  push    r14
0x18003b252  push    r15
0x18003b254  sub     rsp, 120h
0x18003b25b  mov     [rsp+148h+var_F8], 0FFFFFFFFFFFFFFFEh
0x18003b264  mov     [rax+18h], rbx
0x18003b268  mov     [rax+20h], rsi
0x18003b26c  mov     rax, cs:__security_cookie
0x18003b273  xor     rax, rsp
0x18003b276  mov     [rsp+148h+var_30], rax
0x18003b27e  mov     rbx, rdx
0x18003b281  mov     rsi, rcx
0x18003b284  xor     r15d, r15d
0x18003b287  mov     [rsp+148h+pNumArgs], r15d
0x18003b28c  mov     [rsp+148h+pllRet], r15
0x18003b291  lea     rdx, [rsp+148h+pNumArgs]; pNumArgs
0x18003b296  call    cs:__imp_CommandLineToArgvW
0x18003b29c  mov     r12, rax
0x18003b29f  mov     [rsp+148h+var_100], rax
0x18003b2a4  mov     ecx, [rsp+148h+pNumArgs]
0x18003b2a8  lea     edi, [r15+1]
0x18003b2ac  test    rax, rax
0x18003b2af  jz      loc_18003BF68
0x18003b2b5  cmp     ecx, edi
0x18003b2b7  jl      loc_18003BF68
0x18003b2bd  mov     r13d, r15d
0x18003b2c0  mov     [rsp+148h+var_114], r15d
0x18003b2c5  cmp     ecx, 5
0x18003b2c8  jz      short loc_18003B2EE
0x18003b2ca  mov     dword ptr [rsp+148h+var_128], ecx
0x18003b2ce  lea     r9, aGenericsetregb_8; "GenericSetRegBeforeUpgMigrationShim:Wro"...
0x18003b2d5  mov     r8d, 0C1h
0x18003b2db  lea     rdx, aParsecommandli; "ParseCommandLine"
0x18003b2e2  mov     ecx, edi
0x18003b2e4  call    AslLogCallPrintf
0x18003b2e9  jmp     loc_18003BF94
0x18003b2ee  mov     rdx, [rax]
0x18003b2f1  xorps   xmm0, xmm0
0x18003b2f4  movups  xmmword ptr [rsp+148h+var_B0], xmm0
0x18003b2fc  mov     [rsp+148h+var_A0], r15
0x18003b304  mov     [rsp+148h+var_98], r15
0x18003b30c  or      r14, 0FFFFFFFFFFFFFFFFh
0x18003b310  mov     r8, r14
0x18003b313  inc     r8
0x18003b316  cmp     [rdx+r8*2], r15w
0x18003b31b  jnz     short loc_18003B313
0x18003b31d  lea     rcx, [rsp+148h+var_B0]
0x18003b325  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003b32a  nop
0x18003b32b  mov     rdx, [r12+8]
0x18003b330  xorps   xmm0, xmm0
0x18003b333  movups  [rsp+148h+var_90], xmm0
0x18003b33b  mov     [rsp+148h+var_80], r15
0x18003b343  mov     [rsp+148h+var_78], r15
0x18003b34b  mov     r8, r14
0x18003b34e  inc     r8
0x18003b351  cmp     [rdx+r8*2], r15w
0x18003b356  jnz     short loc_18003B34E
0x18003b358  lea     rcx, [rsp+148h+var_90]
0x18003b360  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003b365  nop
0x18003b366  mov     rdx, [r12+10h]
0x18003b36b  xorps   xmm0, xmm0
0x18003b36e  movups  xmmword ptr [rsp+148h+var_F0], xmm0
0x18003b373  mov     [rsp+148h+var_E0], r15
0x18003b378  mov     [rsp+148h+var_D8], r15
0x18003b37d  mov     r8, r14
0x18003b380  inc     r8
0x18003b383  cmp     [rdx+r8*2], r15w
0x18003b388  jnz     short loc_18003B380
0x18003b38a  lea     rcx, [rsp+148h+var_F0]
0x18003b38f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003b394  nop
0x18003b395  mov     rdx, [r12+18h]
0x18003b39a  xorps   xmm0, xmm0
0x18003b39d  movups  xmmword ptr [rsp+148h+S1], xmm0
0x18003b3a5  mov     [rsp+148h+var_60], r15
0x18003b3ad  mov     [rsp+148h+var_58], r15
0x18003b3b5  mov     r8, r14
0x18003b3b8  inc     r8
0x18003b3bb  cmp     [rdx+r8*2], r15w
0x18003b3c0  jnz     short loc_18003B3B8
0x18003b3c2  lea     rcx, [rsp+148h+S1]
0x18003b3ca  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003b3cf  nop
0x18003b3d0  mov     rdx, [r12+20h]
0x18003b3d5  xorps   xmm0, xmm0
0x18003b3d8  movups  xmmword ptr [rsp+148h+pszString], xmm0
0x18003b3dd  mov     [rsp+148h+var_C0], r15
0x18003b3e5  mov     [rsp+148h+var_B8], r15
0x18003b3ed  mov     r8, r14
0x18003b3f0  inc     r8
0x18003b3f3  cmp     [rdx+r8*2], r15w
0x18003b3f8  jnz     short loc_18003B3F0
0x18003b3fa  lea     rcx, [rsp+148h+pszString]
0x18003b3ff  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003b404  nop
0x18003b405  cmp     [rsp+148h+var_A0], r15
0x18003b40d  jnz     short loc_18003B470
0x18003b40f  lea     r9, aGenericsetregb_17; "GenericSetRegBeforeUpgMigrationShim:Ope"...
0x18003b416  mov     r8d, 0DAh
0x18003b41c  lea     rdx, aParsecommandli; "ParseCommandLine"
0x18003b423  mov     ecx, edi
0x18003b425  call    AslLogCallPrintf
0x18003b42a  nop
0x18003b42b  lea     rcx, [rsp+148h+pszString]; void *
0x18003b430  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b435  nop
0x18003b436  lea     rcx, [rsp+148h+S1]; void *
0x18003b43e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b443  nop
0x18003b444  lea     rcx, [rsp+148h+var_F0]; void *
0x18003b449  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b44e  nop
0x18003b44f  lea     rcx, [rsp+148h+var_90]; void *
0x18003b457  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b45c  nop
0x18003b45d  lea     rcx, [rsp+148h+var_B0]; void *
0x18003b465  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b46a  nop
0x18003b46b  jmp     loc_18003BF94
0x18003b470  cmp     [rsp+148h+var_80], r15
0x18003b478  jnz     short loc_18003B4DB
0x18003b47a  lea     r9, aGenericsetregb_6; "GenericSetRegBeforeUpgMigrationShim:Reg"...
0x18003b481  mov     r8d, 0E0h
0x18003b487  lea     rdx, aParsecommandli; "ParseCommandLine"
0x18003b48e  mov     ecx, edi
0x18003b490  call    AslLogCallPrintf
0x18003b495  nop
0x18003b496  lea     rcx, [rsp+148h+pszString]; void *
0x18003b49b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b4a0  nop
0x18003b4a1  lea     rcx, [rsp+148h+S1]; void *
0x18003b4a9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b4ae  nop
0x18003b4af  lea     rcx, [rsp+148h+var_F0]; void *
0x18003b4b4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b4b9  nop
0x18003b4ba  lea     rcx, [rsp+148h+var_90]; void *
0x18003b4c2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b4c7  nop
0x18003b4c8  lea     rcx, [rsp+148h+var_B0]; void *
0x18003b4d0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b4d5  nop
0x18003b4d6  jmp     loc_18003BF94
0x18003b4db  cmp     [rsp+148h+var_E0], r15
0x18003b4e0  jnz     short loc_18003B543
0x18003b4e2  lea     r9, aGenericsetregb_1; "GenericSetRegBeforeUpgMigrationShim:Val"...
0x18003b4e9  mov     r8d, 0E6h
0x18003b4ef  lea     rdx, aParsecommandli; "ParseCommandLine"
0x18003b4f6  mov     ecx, edi
0x18003b4f8  call    AslLogCallPrintf
0x18003b4fd  nop
0x18003b4fe  lea     rcx, [rsp+148h+pszString]; void *
0x18003b503  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b508  nop
0x18003b509  lea     rcx, [rsp+148h+S1]; void *
0x18003b511  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b516  nop
0x18003b517  lea     rcx, [rsp+148h+var_F0]; void *
0x18003b51c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b521  nop
0x18003b522  lea     rcx, [rsp+148h+var_90]; void *
0x18003b52a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b52f  nop
0x18003b530  lea     rcx, [rsp+148h+var_B0]; void *
0x18003b538  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b53d  nop
0x18003b53e  jmp     loc_18003BF94
0x18003b543  mov     rsi, [rsp+148h+var_60]
0x18003b54b  test    rsi, rsi
0x18003b54e  jnz     short loc_18003B5B1
0x18003b550  lea     r9, aGenericsetregb_15; "GenericSetRegBeforeUpgMigrationShim:Val"...
0x18003b557  mov     r8d, 0ECh
0x18003b55d  lea     rdx, aParsecommandli; "ParseCommandLine"
0x18003b564  mov     ecx, edi
0x18003b566  call    AslLogCallPrintf
0x18003b56b  nop
0x18003b56c  lea     rcx, [rsp+148h+pszString]; void *
0x18003b571  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b576  nop
0x18003b577  lea     rcx, [rsp+148h+S1]; void *
0x18003b57f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b584  nop
0x18003b585  lea     rcx, [rsp+148h+var_F0]; void *
0x18003b58a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b58f  nop
0x18003b590  lea     rcx, [rsp+148h+var_90]; void *
0x18003b598  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b59d  nop
0x18003b59e  lea     rcx, [rsp+148h+var_B0]; void *
0x18003b5a6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b5ab  nop
0x18003b5ac  jmp     loc_18003BF94
0x18003b5b1  lea     rcx, [rsp+148h+S1]
0x18003b5b9  cmp     [rsp+148h+var_58], 7
0x18003b5c2  cmova   rcx, [rsp+148h+S1]; S1
0x18003b5cb  mov     r8, rsi
0x18003b5ce  cmp     rsi, rdi
0x18003b5d1  cmova   r8, rdi; N
0x18003b5d5  lea     rdx, asc_18007AB68; "@"
0x18003b5dc  call    wmemcmp
0x18003b5e1  test    eax, eax
0x18003b5e3  jnz     short loc_18003B610
0x18003b5e5  cmp     rsi, rdi
0x18003b5e8  jnz     short loc_18003B610
0x18003b5ea  lea     rcx, [rsp+148h+S1]
0x18003b5f2  cmp     [rsp+148h+var_58], 7
0x18003b5fb  cmova   rcx, [rsp+148h+S1]
0x18003b604  mov     [rsp+148h+var_60], r15
0x18003b60c  mov     [rcx], r15w
0x18003b610  cmp     [rsp+148h+var_C0], r15
0x18003b618  jnz     short loc_18003B67B
0x18003b61a  lea     r9, aGenericsetregb_0; "GenericSetRegBeforeUpgMigrationShimg:Da"...
0x18003b621  mov     r8d, 0F7h
0x18003b627  lea     rdx, aParsecommandli; "ParseCommandLine"
0x18003b62e  mov     ecx, edi
0x18003b630  call    AslLogCallPrintf
0x18003b635  nop
0x18003b636  lea     rcx, [rsp+148h+pszString]; void *
0x18003b63b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b640  nop
0x18003b641  lea     rcx, [rsp+148h+S1]; void *
0x18003b649  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b64e  nop
0x18003b64f  lea     rcx, [rsp+148h+var_F0]; void *
0x18003b654  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b659  nop
0x18003b65a  lea     rcx, [rsp+148h+var_90]; void *
0x18003b662  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b667  nop
0x18003b668  lea     rcx, [rsp+148h+var_B0]; void *
0x18003b670  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b675  nop
0x18003b676  jmp     loc_18003BF94
0x18003b67b  mov     rsi, [rsp+148h+var_A0]
0x18003b683  lea     rcx, [rsp+148h+var_B0]
0x18003b68b  cmp     [rsp+148h+var_98], 7
0x18003b694  cmova   rcx, [rsp+148h+var_B0]; S1
0x18003b69d  mov     r8, rsi
0x18003b6a0  mov     eax, 6
0x18003b6a5  cmp     rsi, rax
0x18003b6a8  cmova   r8, rax; N
0x18003b6ac  lea     rdx, aBefore; "Before"
0x18003b6b3  call    wmemcmp
0x18003b6b8  test    eax, eax
0x18003b6ba  jnz     short loc_18003B6C7
0x18003b6bc  cmp     rsi, 6
0x18003b6c0  jnz     short loc_18003B6C7
0x18003b6c2  mov     [rbx], dil
0x18003b6c5  jmp     short loc_18003B711
0x18003b6c7  mov     rsi, [rsp+148h+var_A0]
0x18003b6cf  lea     rcx, [rsp+148h+var_B0]
0x18003b6d7  cmp     [rsp+148h+var_98], 7
0x18003b6e0  cmova   rcx, [rsp+148h+var_B0]; S1
0x18003b6e9  mov     r8, rsi
0x18003b6ec  mov     eax, 5
0x18003b6f1  cmp     rsi, rax
0x18003b6f4  cmova   r8, rax; N
0x18003b6f8  lea     rdx, aAfter; "After"
0x18003b6ff  call    wmemcmp
0x18003b704  test    eax, eax
0x18003b706  jnz     short loc_18003B718
0x18003b708  cmp     rsi, 5
0x18003b70c  jnz     short loc_18003B718
0x18003b70e  mov     byte ptr [rbx], 2
0x18003b711  mov     esi, 4
0x18003b716  jmp     short loc_18003B76C
0x18003b718  mov     r15, [rsp+148h+var_A0]
0x18003b720  lea     rcx, [rsp+148h+var_B0]
0x18003b728  cmp     [rsp+148h+var_98], 7
0x18003b731  cmova   rcx, [rsp+148h+var_B0]; S1
0x18003b73a  mov     r8, r15
0x18003b73d  mov     esi, 4
0x18003b742  cmp     r15, rsi
0x18003b745  cmova   r8, rsi; N
0x18003b749  lea     rdx, aBoth; "Both"
0x18003b750  call    wmemcmp
0x18003b755  test    eax, eax
0x18003b757  jnz     loc_18003BEDF
0x18003b75d  cmp     r15, rsi
0x18003b760  jnz     loc_18003BEDF
0x18003b766  mov     byte ptr [rbx], 3
0x18003b769  xor     r15d, r15d
0x18003b76c  lea     rdx, [rbx+8]
0x18003b770  lea     rcx, [rsp+148h+var_90]
0x18003b778  call    ?GetRootKey@@YAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAPEAUHKEY__@@@Z; GetRootKey(std::wstring const &,HKEY__ * &)
0x18003b77d  test    eax, eax
0x18003b77f  jnz     loc_18003B805
0x18003b785  lea     rax, [rsp+148h+var_90]
0x18003b78d  cmp     [rsp+148h+var_78], 7
0x18003b796  cmova   rax, qword ptr [rsp+148h+var_90]
0x18003b79f  mov     [rsp+148h+var_128], rax
0x18003b7a4  lea     r9, aGenericsetregb_16; "GenericSetRegBeforeUpgMigrationShim: In"...
0x18003b7ab  mov     r8d, 116h
0x18003b7b1  lea     rdx, aParsecommandli; "ParseCommandLine"
0x18003b7b8  mov     ecx, edi
  ... truncated ...
```
