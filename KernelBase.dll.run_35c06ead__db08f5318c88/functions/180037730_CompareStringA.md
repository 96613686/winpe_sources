# CompareStringA

- ea: `0x180037730`
- end: `0x180038da4`
- name: `CompareStringA`
- size: `5748`
- prototype: `int __stdcall(LCID Locale, DWORD dwCmpFlags, PCNZCH lpString1, int cchCount1, PCNZCH lpString2, int cchCount2)`
- caller_count: `11`
- callee_count: `34`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800069c8`
- `0x180007550`
- `0x180007610`
- `0x18003abc0`
- `0x18003b620`
- `0x1800c7d00`
- `0x1800f8540`
- `0x1800ffa50`
- `0x1801042bc`
- `0x18010af00`
- `0x18013dfd0`

## callees

- `0x18000d4a0`
- `0x18000d7e0`
- `0x18000dd50`
- `0x180010080`
- `0x1800108d0`
- `0x180011b90`
- `0x1800123e0`
- `0x180012f10`
- `0x180018040`
- `0x18001a1b8`
- `0x18001b3a0`
- `0x18001c970`
- `0x18001e794`
- `0x18001e8c0`
- `0x18001ea10`
- `0x180037714`
- `0x180037730`
- `0x180038db0`
- `0x18003b5e8`
- `0x18003e054`
- `0x180040160`
- `0x180042480`
- `0x180071550`
- `0x18007217c`
- `0x180075a5c`
- `0x180075ad0`
- `0x180077680`
- `0x1800fa3bc`
- `0x180122e60`
- `0x18012d119`
- `0x180138ebc`
- `0x180188eb9`
- `0x180188f10`
- `0x180197010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18003897a`
- `ntdll!RtlInitUnicodeString` at `0x18003897a`
- `ntdll!NtOpenKey` at `0x1800389bd`
- `ntdll!NtOpenKey` at `0x1800389bd`
- `ntdll!NtCreateKey` at `0x1800389f5`
- `ntdll!NtCreateKey` at `0x1800389f5`
- `ntdll!RtlLcidToLocaleName` at `0x1800387b3`
- `ntdll!RtlLcidToLocaleName` at `0x1800387b3`
- `ntdll!RtlOpenCurrentUser` at `0x180038353`
- `ntdll!RtlOpenCurrentUser` at `0x180038353`
- `ntdll!CsrClientCallServer` at `0x18003815a`
- `ntdll!CsrClientCallServer` at `0x18003815a`
- `ntdll!CsrCaptureMessageBuffer` at `0x180038134`
- `ntdll!CsrCaptureMessageBuffer` at `0x180038134`
- `ntdll!CsrFreeCaptureBuffer` at `0x180038182`
- `ntdll!CsrFreeCaptureBuffer` at `0x180038182`
- `ntdll!CsrAllocateCaptureBuffer` at `0x180037e4c`
- `ntdll!CsrAllocateCaptureBuffer` at `0x180037e4c`
- `ntdll!NtClose` at `0x180037ebf`
- `ntdll!NtClose` at `0x180038404`
- `ntdll!NtClose` at `0x180038a07`
- `ntdll!NtClose` at `0x180038a42`
- `ntdll!NtClose` at `0x180037ebf`
- `ntdll!NtClose` at `0x180038404`
- `ntdll!NtClose` at `0x180038a07`
- `ntdll!NtClose` at `0x180038a42`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180037956`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180037a98`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180037e07`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180037f39`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800380c1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003825e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800387f2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180037956`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180037a98`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180037e07`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180037f39`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800380c1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003825e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800387f2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180037a3c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180037b7e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003801f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180038054`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800380eb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800382b8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180038817`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180038acb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180038c8c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180037a3c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180037b7e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003801f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180038054`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800380eb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800382b8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180038817`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180038acb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180038c8c`
- `ntdll!RtlFreeHeap` at `0x18003893e`
- `ntdll!RtlFreeHeap` at `0x180038964`
- `ntdll!RtlFreeHeap` at `0x180038d33`
- `ntdll!RtlFreeHeap` at `0x180038d7c`
- `ntdll!RtlFreeHeap` at `0x180038d99`
- `ntdll!RtlFreeHeap` at `0x18003893e`
- `ntdll!RtlFreeHeap` at `0x180038964`
- `ntdll!RtlFreeHeap` at `0x180038d33`
- `ntdll!RtlFreeHeap` at `0x180038d7c`
- `ntdll!RtlFreeHeap` at `0x180038d99`
- `ntdll!RtlAllocateHeap` at `0x180038871`
- `ntdll!RtlAllocateHeap` at `0x1800388d0`
- `ntdll!RtlAllocateHeap` at `0x180038cc0`
- `ntdll!RtlAllocateHeap` at `0x180038cf3`
- `ntdll!RtlAllocateHeap` at `0x180038871`
- `ntdll!RtlAllocateHeap` at `0x1800388d0`
- `ntdll!RtlAllocateHeap` at `0x180038cc0`
- `ntdll!RtlAllocateHeap` at `0x180038cf3`

## pseudocode

```c
int __stdcall CompareStringA(
        LCID Locale,
        DWORD dwCmpFlags,
        PCNZCH lpString1,
        int cchCount1,
        PCNZCH lpString2,
        int cchCount2)
{
  int v6; // edi
  DWORD v8; // eax
  unsigned __int64 v9; // r13
  UINT v10; // r14d
  DWORD v11; // r12d
  __int64 v12; // rdx
  int v13; // ecx
  WCHAR *lpWideCharStr; // r12
  int cchWideChar; // r14d
  int v16; // eax
  __int64 v17; // r8
  int v18; // ebx
  WCHAR *Heap; // rdi
  int v20; // eax
  int v21; // r14d
  HANDLE NamedLocaleHashNode; // rcx
  DWORD v23; // ebx
  __int64 j; // rdx
  unsigned int *v25; // rax
  __int64 v26; // r8
  DWORD v27; // ebx
  const WCHAR *v28; // rcx
  __int64 v29; // rax
  DWORD v30; // ebx
  __int64 i; // rdx
  unsigned int *WindowsLocaleData; // rax
  __int64 v33; // r8
  DWORD v34; // ebx
  const WCHAR *v35; // rcx
  __int64 LocHashNodeFromSystemLocale; // rax
  __int64 v37; // rcx
  __int64 v38; // rbx
  __int64 v39; // rsi
  __int16 *v40; // rbx
  int v41; // ebx
  __int64 v43; // rax
  bool v44; // zf
  __int64 v45; // rax
  DWORD v46; // ecx
  __int64 SortNode; // rax
  __int64 v48; // rdx
  __int64 IsImpersonating; // rcx
  int IsInteractiveUserProcess; // eax
  __int16 v51; // ax
  struct _CSR_CAPTURE_BUFFER *CaptureBuffer; // rax
  struct _CSR_CAPTURE_BUFFER *v53; // rbx
  NTSTATUS v54; // esi
  HANDLE v55; // rbx
  __int64 v56; // rbx
  __int64 v57; // rax
  DWORD v58; // ebx
  __int64 k; // rdx
  unsigned int *v60; // rax
  __int64 v61; // r8
  DWORD v62; // ebx
  const WCHAR *v63; // rcx
  __int64 v64; // rax
  HANDLE *NlsCache; // rbx
  __int64 v66; // rdx
  __int64 v67; // rdx
  int v68; // eax
  int GlobalizationUserModelType; // eax
  int v70; // eax
  __int64 v71; // rcx
  WCHAR *v72; // rax
  __int64 v73; // rdx
  __int64 v74; // r8
  const WCHAR *v75; // rcx
  WCHAR *v76; // rdx
  __int64 v77; // r9
  WCHAR *v78; // rcx
  __int64 v79; // rdx
  int v80; // ecx
  int v81; // r15d
  _DWORD *v82; // rax
  __int64 LocaleHashNode; // r14
  int v84; // eax
  HANDLE *v85; // rbx
  HANDLE *v86; // rax
  HANDLE *v87; // rax
  NTSTATUS v88; // ebx
  HANDLE v89; // rcx
  void *v90; // rbx
  unsigned int *v91; // rcx
  __int64 v92; // r8
  const WCHAR *v93; // rcx
  __int64 TransientLocale; // rax
  unsigned __int64 v95; // r12
  int v96; // r14d
  wchar_t *v97; // rax
  __int64 v98; // rdx
  __int64 v99; // rcx
  const WCHAR *v100; // r9
  __int64 v101; // r8
  wchar_t *v102; // rax
  wchar_t *v103; // rcx
  __int64 v104; // rax
  UINT CodePage[2]; // [rsp+50h] [rbp-B0h] BYREF
  ULONG Disposition; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v107; // [rsp+5Ch] [rbp-A4h]
  unsigned int v108; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE Handle[2]; // [rsp+68h] [rbp-98h] BYREF
  UINT v110; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  __int64 v112; // [rsp+90h] [rbp-70h]
  __int64 v113; // [rsp+98h] [rbp-68h]
  __int64 v114; // [rsp+A0h] [rbp-60h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR WideCharStr[128]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR P[128]; // [rsp+1E0h] [rbp+E0h] BYREF
  wchar_t ApiMessage[32]; // [rsp+2E0h] [rbp+1E0h] BYREF
  PVOID CapturedData; // [rsp+320h] [rbp+220h] BYREF
  int v120; // [rsp+328h] [rbp+228h]
  wchar_t pszDest[512]; // [rsp+6E0h] [rbp+5E0h] BYREF

  v6 = cchCount1;
  v107 = dwCmpFlags;
  v8 = dwCmpFlags;
  v9 = Locale;
  Disposition = cchCount1 < 0 && cchCount2 < 0;
  v110 = 0;
  if ( (dwCmpFlags & 0x60000000) != 0 )
    goto LABEL_257;
  if ( Locale == 1033 || Locale == 127 )
  {
    v10 = dword_18039EC10;
    CodePage[0] = dword_18039EC10;
    if ( !dword_18039EC10 )
    {
      v10 = 1252;
      CodePage[0] = 1252;
      if ( gAnsiCodePage != 1252 && gOemCodePage != 1252 && (unsigned int)IsCPHashNodeLoaded(1252) != 1 )
      {
        if ( !(unsigned int)GetCPFileNameFromRegistry(1252, ApiMessage, 64) )
          goto LABEL_330;
        v95 = (unsigned __int16)qword_1803A2DD8;
        v96 = (unsigned __int16)qword_1803A2DD8 >> 1;
        if ( (unsigned __int64)(unsigned __int16)qword_1803A2DD8 + 2 <= 0x400 )
        {
          memcpy_0(pszDest, Src, (unsigned __int16)qword_1803A2DD8);
          pszDest[v95 >> 1] = 0;
        }
        else
        {
          ++v96;
        }
        if ( !v96 )
          goto LABEL_330;
        v97 = pszDest;
        v98 = 512;
        do
        {
          if ( !*v97 )
            break;
          ++v97;
          --v98;
        }
        while ( v98 );
        v99 = 512 - v98;
        if ( !v98 )
          goto LABEL_330;
        v100 = L"\\";
        v101 = 2147483646;
        v102 = &pszDest[v99];
        if ( v99 != 512 )
        {
          do
          {
            if ( !v101 )
              break;
            if ( !*v100 )
              break;
            *v102++ = *v100++;
            --v101;
            --v98;
          }
          while ( v98 );
        }
        v103 = v102 - 1;
        if ( v98 )
          v103 = v102;
        *v103 = 0;
        if ( !v98 || StringCchCatW(pszDest, 0x200u, ApiMessage) < 0 || GetFileAttributesW(pszDest) == -1 )
        {
LABEL_330:
          v10 = 65001;
          CodePage[0] = 65001;
          dword_18039EC10 = 65001;
          goto LABEL_7;
        }
        v10 = CodePage[0];
      }
      dword_18039EC10 = v10;
    }
LABEL_7:
    v8 = v107;
    v11 = 87;
    goto LABEL_8;
  }
  if ( Locale == 2048 )
  {
LABEL_257:
    v11 = 87;
LABEL_238:
    v10 = gAnsiCodePage;
    CodePage[0] = gAnsiCodePage;
    goto LABEL_8;
  }
  v82 = CheckSpecialLocales(Locale);
  v11 = 87;
  if ( !v82 )
  {
    LocaleHashNode = *((_QWORD *)::P + (((unsigned __int8)v9 ^ (unsigned __int8)((v9 ^ (v9 >> 7)) >> 7)) & 0x7F));
    if ( LocaleHashNode )
    {
      while ( *(_DWORD *)LocaleHashNode != (_DWORD)v9 )
      {
        LocaleHashNode = *(_QWORD *)(LocaleHashNode + 88);
        if ( !LocaleHashNode )
          goto LABEL_277;
      }
    }
    else
    {
LABEL_277:
      RtlAcquireSRWLockExclusive(&gTblPtrsLock);
      LocaleHashNode = FindLocaleHashNode((unsigned int)v9);
      if ( !LocaleHashNode )
        LocaleHashNode = MakeLocHashNode();
      RtlReleaseSRWLockExclusive(&gTblPtrsLock);
    }
    if ( (!LocaleHashNode || (v82 = *(_DWORD **)(LocaleHashNode + 104)) == 0)
      && (!(unsigned int)IsUnspecifiedLcid((unsigned int)v9) || (v82 = GetCurrentNlsCache()[2]) == 0) )
    {
      SetLastError_0(0x57u);
      goto LABEL_263;
    }
  }
  if ( !(unsigned int)GetLocaleInfoHelper(v82, 2684358660LL, &v110, 2) )
  {
LABEL_263:
    SetLastError_0(0x57u);
    SetLastError_0(0x57u);
    return 0;
  }
  v10 = v110;
  v8 = v107;
  CodePage[0] = v110;
  if ( !v110 )
    goto LABEL_238;
LABEL_8:
  if ( !v10 || !lpString1 || !lpString2 )
    goto LABEL_89;
  if ( (v8 & 0xA7FCEFC8) != 0 )
  {
    SetLastError_0(0x3ECu);
    return 0;
  }
  v12 = -1;
  v114 = -1;
  if ( v6 < 0 )
  {
    v43 = -1;
    do
      v44 = lpString1[++v43] == 0;
    while ( !v44 );
    v6 = v43 + 1;
    if ( (unsigned __int64)(v43 + 1) > 0x7FFFFFFF )
      goto LABEL_89;
  }
  v13 = 127;
  LODWORD(Handle[0]) = 127;
  if ( v6 > 127 )
  {
    lpWideCharStr = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v6 + 1));
    if ( !lpWideCharStr )
    {
      v11 = 14;
      goto LABEL_89;
    }
    cchWideChar = v6;
LABEL_16:
    v16 = MultiByteToWideChar(CodePage[0], 0, lpString1, v6, lpWideCharStr, cchWideChar);
    v17 = v16;
    v108 = v16;
    if ( v16 && v16 <= cchWideChar )
    {
      v10 = CodePage[0];
      lpWideCharStr[v16] = 0;
      v12 = -1;
      v13 = 127;
      goto LABEL_19;
    }
    if ( lpWideCharStr != WideCharStr && lpWideCharStr )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, lpWideCharStr);
    v11 = 87;
LABEL_89:
    SetLastError_0(v11);
    return 0;
  }
  lpWideCharStr = WideCharStr;
  if ( v6 )
  {
    cchWideChar = 127;
    goto LABEL_16;
  }
  v17 = 0;
  WideCharStr[0] = 0;
  v108 = 0;
LABEL_19:
  if ( cchCount2 < 0 )
  {
    v45 = -1;
    do
      v44 = lpString2[++v45] == 0;
    while ( !v44 );
    v18 = v45 + 1;
    if ( (unsigned __int64)(v45 + 1) > 0x7FFFFFFF )
    {
      v46 = 87;
      goto LABEL_347;
    }
  }
  else
  {
    v18 = cchCount2;
  }
  if ( v18 > 127 )
  {
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v18 + 1));
    if ( Heap )
    {
      v13 = v18;
      LODWORD(Handle[0]) = v18;
LABEL_23:
      v20 = MultiByteToWideChar(v10, 0, lpString2, v18, Heap, v13);
      v21 = v20;
      if ( v20 && v20 <= SLODWORD(Handle[0]) )
      {
        v17 = v108;
        Heap[v20] = 0;
        v12 = v20;
        goto LABEL_26;
      }
      if ( Heap != P && Heap )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      v46 = 87;
      goto LABEL_347;
    }
    v46 = 14;
LABEL_347:
    SetLastError_0(v46);
    if ( lpWideCharStr != WideCharStr && lpWideCharStr )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, lpWideCharStr);
      return 0;
    }
    return 0;
  }
  Heap = P;
  if ( v18 )
    goto LABEL_23;
  P[0] = 0;
  v21 = 0;
LABEL_26:
  if ( Disposition )
    v21 = -1;
  else
    LODWORD(v114) = v17;
  if ( (_DWORD)v9 == 127 )
  {
    NamedLocaleHashNode = (HANDLE)gpInvLocHashN;
    goto LABEL_72;
  }
  if ( (unsigned int)v9 > 0xC00 )
  {
    if ( (_DWORD)v9 == 4096 )
    {
      NamedLocaleHashNode = (HANDLE)gpOneCustomHashNode;
      if ( gpOneCustomHashNode )
        goto LABEL_77;
    }
    else if ( (_DWORD)v9 != 5120 )
    {
      goto LABEL_54;
    }
    Handle[0] = (HANDLE)11141120;
    Handle[1] = ApiMessage;
    if ( (int)RtlLcidToLocaleName((unsigned int)v9, Handle, 0, 0) >= 0 )
    {
      NamedLocaleHashNode = (HANDLE)GetNamedLocaleHashNode(Handle[1], 0);
      if ( NamedLocaleHashNode )
        goto LABEL_77;
    }
LABEL_54:
    NamedLocaleHashNode = (HANDLE)gpSysLocHashN;
    if ( gpSysLocHashN || BasepIsSecureProcess )
    {
LABEL_71:
      if ( (_DWORD)v9 != *(_DWORD *)NamedLocaleHashNode )
        goto LABEL_73;
      goto LABEL_72;
    }
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    if ( gpSysLocHashN )
      goto LABEL_70;
    v30 = gSystemLocale;
    for ( i = *((_QWORD *)::P
              + (((unsigned __int8)gSystemLocale
                ^ (unsigned __int8)((gSystemLocale ^ ((unsigned __int64)gSystemLocale >> 7)) >> 7))
               & 0x7F)); i; i = *(_QWORD *)(i + 88) )
    {
      if ( *(_DWORD *)i == gSystemLocale )
        break;
    }
    gpSysLocHashN = i;
    if ( i )
      goto LABEL_70;
    if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
      goto LABEL_158;
    WindowsLocaleData = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
    if ( WindowsLocaleData )
    {
      if ( (_WORD)v30 != 127 )
      {
        v34 = HIWORD(v30);
        if ( (v34 & 0xF) == 0 )
        {
          v35 = (const WCHAR *)(qword_18039EC90 + 2 + 2LL * *WindowsLocaleData);
LABEL_66:
          LocHashNodeFromSystemLocale = MakeNamedLocaleHashNode(v35, 0);
          goto LABEL_67;
        }
        v66 = WindowsLocaleData[54];
        v35 = (const WCHAR *)qword_18039EC90;
        if ( (_DWORD)v66 )
          v35 = (const WCHAR *)(qword_18039EC90
                              + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v66 + 2LL * (v34 & 0xF)) - 2)
                              + 2);
        if ( v35 && *v35 )
          goto LABEL_66;
LABEL_158:
        gpSysLocHashN = 0;
LABEL_68:
        gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
        if ( !gpSysLocHashN )
          gpSysLocHashN = gpInvLocHashN;
        goto LABEL_70;
      }
      LocHashNodeFromSystemLocale = MakeLocHashNodeFromSystemLocale(WindowsLocaleData, v30, v33, 0);
    }
    else
    {
      if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
        goto LABEL_158;
      if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
        || (unsigned int)CreateTransientLocales() )
      {
        LocHashNodeFromSystemLocale = FindLocaleHashNode(v30);
      }
      else
      {
        LocHashNodeFromSystemLocale = 0;
      }
    }
LABEL_67:
    gpSysLocHashN = LocHashNodeFromSystemLocale;
    if ( !LocHashNodeFromSystemLocale )
      goto LABEL_68;
LABEL_70:
    RtlReleaseSRWLockExclusive(&gTblPtrsLock);
    NamedLocaleHashNode = (HANDLE)gpSysLocHashN;
    goto LABEL_71;
  }
  if ( (_DWORD)v9 != 3072 && (_DWORD)v9 && (_DWORD)v9 != 1024 )
  {
    if ( (_DWORD)v9 == 2048 )
    {
      NamedLocaleHashNode = (HANDLE)gpSysLocHashN;
      if ( gpSysLocHashN )
        goto LABEL_77;
      if ( BasepIsSecureProcess )
        goto LABEL_72;
      RtlAcquireSRWLockExclusive(&gTblPtrsLock);
      if ( gpSysLocHashN )
        goto LABEL_50;
      v23 = gSystemLocale;
      for ( j = *((_QWORD *)::P
                + (((unsigned __int8)gSystemLocale
                  ^ (unsigned __int8)((gSystemLocale ^ ((unsigned __int64)gSystemLocale >> 7)) >> 7))
                 & 0x7F)); j; j = *(_QWORD *)(j + 88) )
      {
        if ( *(_DWORD *)j == gSystemLocale )
          break;
      }
      gpSysLocHashN = j;
      if ( j )
        goto LABEL_50;
      if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
        goto LABEL_183;
      v25 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
      if ( v25 )
      {
        if ( (_WORD)v23 != 127 )
        {
          v27 = HIWORD(v23);
          if ( (v27 & 0xF) == 0 )
          {
            v28 = (const WCHAR *)(qword_18039EC90 + 2 + 2LL * *v25);
LABEL_46:
            v29 = MakeNamedLocaleHashNode(v28, 0);
            goto LABEL_47;
          }
          v67 = v25[54];
          v28 = (const WCHAR *)qword_18039EC90;
          if ( (_DWORD)v67 )
            v28 = (const WCHAR *)(qword_18039EC90
                                + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v67 + 2LL * (v27 & 0xF)) - 2)
                                + 2);
          if ( v28 && *v28 )
            goto LABEL_46;
LABEL_183:
          gpSysLocHashN = 0;
          goto LABEL_48;
        }
        v29 = MakeLocHashNodeFromSystemLocale(v25, v23, v26, 0);
      }
      else
      {
        if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
          goto LABEL_183;
        if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
          || (unsigned int)CreateTransientLocales() )
        {
          v29 = FindLocaleHashNode(v23);
        }
        else
        {
          v29 = 0;
        }
      }
LABEL_47:
      gpSysLocHashN = v29;
      if ( v29 )
      {
LABEL_50:
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        NamedLocaleHashNode = (HANDLE)gpSysLocHashN;
        goto LABEL_72;
      }
LABEL_48:
      gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
      if ( !gpSysLocHashN )
        gpSysLocHashN = gpInvLocHashN;
      goto LABEL_50;
    }
    goto LABEL_54;
  }
  IsImpersonating = NtCurrentTeb()->IsImpersonating;
  if ( !(_DWORD)IsImpersonating )
  {
    IsInteractiveUserProcess = gInteractiveLogonUserProcess;
    if ( gInteractiveLogonUserProcess == -1 )
      IsInteractiveUserProcess = NlsInitIsInteractiveUserProcess(IsImpersonating, v12, v17);
    if ( !IsInteractiveUserProcess )
    {
      NlsCheckStaleCache();
      goto LABEL_152;
    }
    if ( dword_1803A4270 != *(_DWORD *)(gpServerNlsUserInfo + 1656) )
      word_1803A4276 = 1;
    if ( !word_1803A4276 )
      goto LABEL_152;
    v51 = word_1803A4274;
    if ( word_1803A4274 != 3 )
    {
      RtlAcquireSRWLockExclusive(&gNlsProcessCacheLock);
      v51 = word_1803A4274;
      if ( word_1803A4274 != 3 )
      {
        if ( !word_1803A4276 )
          goto LABEL_151;
        v51 = word_1803A4274;
      }
    }
    word_1803A4276 = 2;
    if ( v51 == 1 )
    {
      memset_0(ApiMessage, 0, 0x3B8u);
      CaptureBuffer = CsrAllocateCaptureBuffer(1u, 0x67Cu);
      v53 = CaptureBuffer;
      if ( CaptureBuffer )
      {
        CsrCaptureMessageBuffer(CaptureBuffer, 0, 0x67Cu, &CapturedData);
        v120 = 1660;
        v54 = CsrClientCallServer(ApiMessage, v53, (CSR_API_NUMBER)0x1001B, 0x10u);
        if ( v54 >= 0 )
          memcpy_0(&word_1803A3BF8, CapturedData, 0x67Cu);
        CsrFreeCaptureBuffer(v53);
      }
      else
      {
        v54 = -1073741801;
      }
      if ( word_1803A4274 == 1 && v54 >= 0 )
      {
LABEL_127:
        if ( word_1803A3BF8 == -1 )
        {
          qword_1803A3BF0 = 0;
        }
        else
        {
          v56 = gpOneCustomHashNode;
          _InterlockedExchange64(&qword_1803A3BF0, GetNamedLocaleHashNode(word_1803A3BFA, 0));
          if ( !v56 && gpOneCustomHashNode )
            gpOneCustomHashNode = 0;
          if ( qword_1803A3BF0 )
          {
LABEL_150:
            _InterlockedCompareExchange16(&word_1803A4276, 0, 2);
            if ( word_1803A4274 != 3 )
LABEL_151:
              RtlReleaseSRWLockExclusive(&gNlsProcessCacheLock);
LABEL_152:
            NlsCache = &gNlsProcessLocalCache;
LABEL_153:
            NamedLocaleHashNode = NlsCache[2];
            goto LABEL_72;
          }
        }
        v57 = gpSysLocHashN;
        if ( gpSysLocHashN || BasepIsSecureProcess )
        {
LABEL_149:
          qword_1803A3BF0 = v57;
          goto LABEL_150;
        }
        RtlAcquireSRWLockExclusive(&gTblPtrsLock);
        if ( gpSysLocHashN )
          goto LABEL_148;
        v58 = gSystemLocale;
        for ( k = *((_QWORD *)::P
                  + (((unsigned __int8)gSystemLocale
                    ^ (unsigned __int8)((gSystemLocale ^ ((unsigned __int64)gSystemLocale >> 7)) >> 7))
                   & 0x7F)); k; k = *(_QWORD *)(k + 88) )
        {
          if ( *(_DWORD *)k == gSystemLocale )
            break;
        }
        gpSysLocHashN = k;
        if ( k )
          goto LABEL_148;
        if ( (gSystemLocale & 0xFFF00000) != 0 || BasepIsSecureProcess )
          goto LABEL_218;
        v60 = (unsigned int *)GetWindowsLocaleData(gSystemLocale);
        if ( v60 )
        {
          if ( (_WORD)v58 != 127 )
          {
            v62 = HIWORD(v58);
            if ( (v62 & 0xF) == 0 )
            {
              v63 = (const WCHAR *)(qword_18039EC90 + 2 + 2LL * *v60);
LABEL_144:
              v64 = MakeNamedLocaleHashNode(v63, 0);
              goto LABEL_145;
            }
            v79 = v60[54];
            v63 = (const WCHAR *)qword_18039EC90;
            if ( (_DWORD)v79 )
              v63 = (const WCHAR *)(qword_18039EC90
                                  + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v79 + 2LL * (v62 & 0xF)) - 2)
                                  + 2);
            if ( v63 && *v63 )
              goto LABEL_144;
LABEL_218:
            gpSysLocHashN = 0;
LABEL_146:
            gpSysLocHashN = MakeNamedLocaleHashNode(L"en-US", 0);
            if ( !gpSysLocHashN )
              gpSysLocHashN = gpInvLocHashN;
            goto LABEL_148;
          }
          v64 = MakeLocHashNodeFromSystemLocale(v60, v58, v61, 0);
        }
        else
        {
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
            goto LABEL_218;
          if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
            || (unsigned int)CreateTransientLocales() )
          {
            v64 = FindLocaleHashNode(v58);
          }
          else
          {
            v64 = 0;
          }
        }
LABEL_145:
        gpSysLocHashN = v64;
        if ( !v64 )
          goto LABEL_146;
LABEL_148:
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        v57 = gpSysLocHashN;
        goto LABEL_149;
      }
    }
    Handle[0] = 0;
    if ( gNlsProcessLocalCache )
    {
      Handle[0] = gNlsProcessLocalCache;
LABEL_124:
      v55 = Handle[0];
      NlsUpdateCacheInfo(&word_1803A3BF8, Handle[0], 1);
      if ( word_1803A4274 == 3 && v55 )
        NtClose(v55);
      goto LABEL_127;
    }
    *(_QWORD *)CodePage = 0;
    Disposition = 0;
    memset(&ObjectAttributes, 0, 44);
    DestinationString = 0;
    GlobalizationUserModelType = GetGlobalizationUserModelType(0, v12, v17);
    if ( GlobalizationUserModelType == 1 )
    {
      v70 = RtlOpenCurrentUser(0x2000000u, (PHANDLE)CodePage);
    }
    else
    {
      v84 = GlobalizationUserModelType - 2;
      if ( v84 )
      {
        if ( v84 != 1 )
        {
LABEL_213:
          SetLastError_0(0x3F1u);
          goto LABEL_124;
        }
        v108 = 0;
        v70 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, (PHANDLE)CodePage, &v108);
      }
      else
      {
        v70 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, (PHANDLE)CodePage);
      }
    }
    if ( v70 >= 0 )
    {
      ApiMessage[0] = 0;
      v71 = 512;
      v72 = ApiMessage;
      do
      {
        if ( !*v72 )
          break;
        ++v72;
        --v71;
      }
      while ( v71 );
      v73 = 512 - v71;
      if ( !v71 )
        goto LABEL_211;
      v74 = v71;
      v75 = L"Control Panel\\International";
      v76 = &ApiMessage[v73];
      v77 = 2147483646;
      do
      {
        if ( !v77 )
          break;
        if ( !*v75 )
          break;
        *v76++ = *v75++;
        --v77;
        --v74;
      }
      while ( v74 );
      v78 = v76 - 1;
      if ( v74 )
        v78 = v76;
      *v78 = 0;
      if ( v74 )
      {
        RtlInitUnicodeString(&DestinationString, ApiMessage);
        ObjectAttributes.RootDirectory = *(HANDLE *)CodePage;
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        Disposition = 0;
        v88 = NtOpenKey(Handle, 0x20019u, &ObjectAttributes);
        if ( v88 < 0 )
          v88 = NtCreateKey(Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition);
        if ( *(_QWORD *)CodePage )
          NtClose(*(HANDLE *)CodePage);
        if ( v88 >= 0 )
        {
          v89 = Handle[0];
        }
        else
        {
          v89 = 0;
          Handle[0] = 0;
        }
        if ( v88 >= 0 )
        {
          v90 = (void *)_InterlockedCompareExchange64(
                          (volatile signed __int64 *)&gNlsProcessLocalCache,
                          (signed __int64)v89,
                          0);
          if ( v90 )
          {
            if ( Handle[0] )
              NtClose(Handle[0]);
            Handle[0] = v90;
          }
          goto LABEL_124;
        }
      }
      else
      {
LABEL_211:
        if ( *(_QWORD *)CodePage )
          NtClose(*(HANDLE *)CodePage);
      }
    }
    goto LABEL_213;
  }
  NlsCache = 0;
  v80 = IsImpersonating - 1;
  if ( v80 )
  {
    if ( v80 != 1 )
      goto LABEL_153;
    if ( BasepIsSecureProcess )
      goto LABEL_152;
    v81 = 0;
    NlsCache = (HANDLE *)NtCurrentTeb()->NlsCache;
    if ( !NlsCache )
    {
      v86 = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x698u);
      NlsCache = v86;
      LOWORD(v80) = 1;
      if ( v86 )
      {
        *v86 = 0;
        v86[1] = 0;
        v86[2] = 0;
        v81 = 1;
        *((_WORD *)v86 + 842) = 3;
        *((_WORD *)v86 + 843) = 1;
      }
      else
      {
        NlsCache = &gNlsProcessLocalCache;
      }
      NtCurrentTeb()->NlsCache = NlsCache;
    }
    if ( NlsCache == &gNlsProcessLocalCache || !v81 && *((_WORD *)NlsCache + 843) != 1 )
      goto LABEL_153;
    *((_WORD *)NlsCache + 843) = v80;
    UpdateNlsInfoCache(NlsCache, 0);
    NamedLocaleHashNode = NlsCache[2];
  }
  else
  {
    if ( BasepIsSecureProcess )
    {
      v85 = &gNlsProcessLocalCache;
    }
    else
    {
      v85 = (HANDLE *)NtCurrentTeb()->NlsCache;
      if ( !v85 )
      {
        v87 = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x698u);
        v85 = v87;
        if ( v87 )
        {
          *v87 = 0;
          v87[1] = 0;
          v87[2] = 0;
          *((_WORD *)v87 + 842) = 3;
          *((_WORD *)v87 + 843) = 1;
        }
        else
        {
          v85 = &gNlsProcessLocalCache;
        }
        NtCurrentTeb()->NlsCache = v85;
      }
      if ( v85 != &gNlsProcessLocalCache )
      {
        *((_WORD *)v85 + 843) = 1;
        UpdateNlsInfoCache(v85, 0);
      }
    }
    NtCurrentTeb()->IsImpersonating = 2;
    NamedLocaleHashNode = v85[2];
  }
LABEL_72:
  if ( NamedLocaleHashNode )
    goto LABEL_77;
LABEL_73:
  v37 = ((unsigned __int8)v9 ^ (unsigned __int8)((v9 ^ (v9 >> 7)) >> 7)) & 0x7F;
  v38 = *((_QWORD *)::P + v37);
  v39 = 8 * v37;
  if ( v38 )
  {
    while ( *(_DWORD *)v38 != (_DWORD)v9 )
    {
      v38 = *(_QWORD *)(v38 + 88);
      if ( !v38 )
        goto LABEL_160;
    }
    goto LABEL_75;
  }
LABEL_160:
  RtlAcquireSRWLockExclusive(&gTblPtrsLock);
  v38 = *(_QWORD *)((char *)::P + v39);
  if ( v38 )
  {
    while ( *(_DWORD *)v38 != (_DWORD)v9 )
    {
      v38 = *(_QWORD *)(v38 + 88);
      if ( !v38 )
        goto LABEL_305;
    }
    goto LABEL_162;
  }
LABEL_305:
  if ( (v9 & 0xFFF00000) == 0 && !BasepIsSecureProcess )
  {
    v91 = (unsigned int *)GetWindowsLocaleData((unsigned int)v9);
    if ( v91 )
    {
      if ( (_WORD)v9 == 127 )
      {
        v38 = MakeLocHashNodeFromSystemLocale(v91, (unsigned int)v9, v92, 0);
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        goto LABEL_75;
      }
      if ( (v9 & 0xF0000) == 0 )
      {
        v93 = (const WCHAR *)(qword_18039EC90 + 2 + 2LL * *v91);
LABEL_311:
        TransientLocale = MakeNamedLocaleHashNode(v93, 0);
LABEL_312:
        v38 = TransientLocale;
        RtlReleaseSRWLockExclusive(&gTblPtrsLock);
        goto LABEL_75;
      }
      v104 = v91[54];
      v93 = (const WCHAR *)qword_18039EC90;
      if ( (_DWORD)v104 )
        v93 = (const WCHAR *)(qword_18039EC90
                            + 2LL * *(unsigned int *)(qword_18039EC90 + 2 * (v104 + 2LL * (BYTE2(v9) & 0xF)) - 2)
                            + 2);
      if ( v93 && *v93 )
        goto LABEL_311;
    }
    else if ( !(unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline() )
    {
      TransientLocale = GetTransientLocale((unsigned int)v9);
      goto LABEL_312;
    }
  }
  v38 = 0;
LABEL_162:
  RtlReleaseSRWLockExclusive(&gTblPtrsLock);
LABEL_75:
  if ( v38 )
  {
    NamedLocaleHashNode = *(HANDLE *)(v38 + 104);
    if ( NamedLocaleHashNode )
      goto LABEL_77;
  }
  else
  {
    NamedLocaleHashNode = 0;
  }
  if ( (_DWORD)v9 == 4096 || (v9 & 0x3FF) == 0 && (unsigned int)(v9 - 0x2000) <= 0x2C00 )
    NamedLocaleHashNode = GetCurrentNlsCache()[2];
  if ( !NamedLocaleHashNode )
    goto LABEL_78;
LABEL_77:
  v40 = (__int16 *)*((_QWORD *)NamedLocaleHashNode + 4);
  if ( !v40 )
    goto LABEL_78;
  if ( !g_definedDefaultSortVersion )
  {
    *(_QWORD *)&DestinationString.Length = 32;
    DestinationString.Buffer = 0;
    v112 = 0;
    v113 = 0;
    RtlAcquireSRWLockExclusive(&gTblPtrsLock);
    if ( !g_definedDefaultSortVersion )
    {
      if ( (unsigned int)QueryRegDefaultSortingVersion(&DestinationString)
        && (unsigned int)QueryRegSortVersionDll(&DestinationString, 0, 0) )
      {
        v68 = *(_DWORD *)(&DestinationString.MaximumLength + 1);
      }
      else
      {
        v68 = 256;
      }
      dword_18039D2B4 = v68 | 0xFF;
      dword_18039D2B8 = v68 | 0xFF;
      _InterlockedExchange(&g_definedDefaultSortVersion, 1);
    }
    RtlReleaseSRWLockExclusive(&gTblPtrsLock);
  }
  SortNode = GetSortNode(v40, (__int64)g_defaultSortVersion, 0);
  if ( !SortNode )
  {
LABEL_78:
    SetLastError_0(0x57u);
    v41 = 0;
    goto LABEL_79;
  }
  v48 = v107;
  LODWORD(v48) = v107 ^ 0x8000000;
  v41 = (*(__int64 (__fastcall **)(__int64, __int64, WCHAR *, _QWORD, WCHAR *, int, _QWORD, _QWORD))(SortNode + 240))(
          SortNode,
          v48,
          lpWideCharStr,
          (unsigned int)v114,
          Heap,
          v21,
          0,
          0);
LABEL_79:
  if ( lpWideCharStr != WideCharStr && lpWideCharStr )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, lpWideCharStr);
  if ( Heap != P )
  {
    if ( Heap )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  }
  return v41;
}

```

## disassembly

```asm
0x180037730  push    rbp
0x180037732  push    rbx
0x180037733  push    rsi
0x180037734  push    rdi
0x180037735  push    r13
0x180037737  push    r15
0x180037739  lea     rbp, [rsp-0A08h]
0x180037741  sub     rsp, 0B08h
0x180037748  mov     rax, cs:__security_cookie
0x18003774f  xor     rax, rsp
0x180037752  mov     [rbp+0A30h+var_50], rax
0x180037759  mov     r15, [rbp+0A30h+lpString2]
0x180037760  mov     edi, r9d
0x180037763  mov     esi, [rbp+0A30h+cchCount2]
0x180037769  mov     rbx, r8
0x18003776c  mov     [rsp+0B30h+var_AD4], edx
0x180037770  mov     eax, edx
0x180037772  mov     r13d, ecx
0x180037775  test    r9d, r9d
0x180037778  jns     loc_180037A4E
0x18003777e  test    esi, esi
0x180037780  jns     loc_180037A4E
0x180037786  mov     [rsp+0B30h+var_AD8], 1
0x18003778e  mov     [rsp+0B30h+var_30], r12
0x180037796  mov     [rsp+0B30h+var_38], r14
0x18003779e  mov     [rsp+0B30h+var_AB8], 0
0x1800377a6  test    eax, 60000000h
0x1800377ab  jnz     loc_18003867B
0x1800377b1  cmp     r13d, 409h
0x1800377b8  jnz     loc_1800384EE
0x1800377be  mov     r14d, cs:dword_18039EC10
0x1800377c5  mov     [rsp+0B30h+CodePage], r14d
0x1800377ca  test    r14d, r14d
0x1800377cd  jz      loc_1800385E7
0x1800377d3  mov     eax, [rsp+0B30h+var_AD4]
0x1800377d7  mov     r12d, 57h ; 'W'
0x1800377dd  test    r14d, r14d
0x1800377e0  jz      loc_180037C7C
0x1800377e6  test    rbx, rbx
0x1800377e9  jz      loc_180037C7C
0x1800377ef  test    r15, r15
0x1800377f2  jz      loc_180037C7C
0x1800377f8  test    eax, 0A7FCEFC8h
0x1800377fd  jnz     loc_180037D16
0x180037803  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18003780a  mov     [rbp+0A30h+var_A90], rdx
0x18003780e  test    edi, edi
0x180037810  js      loc_180037C4B
0x180037816  mov     ecx, 7Fh
0x18003781b  mov     dword ptr [rsp+0B30h+Handle], ecx
0x18003781f  cmp     edi, ecx
0x180037821  jg      loc_180038CA7
0x180037827  lea     r12, [rbp+0A30h+WideCharStr]
0x18003782b  test    edi, edi
0x18003782d  jz      loc_180037CF2
0x180037833  mov     r14d, ecx
0x180037836  mov     ecx, [rsp+0B30h+CodePage]; CodePage
0x18003783a  mov     r9d, edi; cbMultiByte
0x18003783d  mov     [rsp+0B30h+cchWideChar], r14d; cchWideChar
0x180037842  mov     r8, rbx; lpMultiByteStr
0x180037845  xor     edx, edx; dwFlags
0x180037847  mov     [rsp+0B30h+lpWideCharStr], r12; lpWideCharStr
0x18003784c  call    MultiByteToWideChar
0x180037851  movsxd  r8, eax
0x180037854  mov     [rsp+0B30h+var_AD0], r8d
0x180037859  test    eax, eax
0x18003785b  jz      loc_180037CE4
0x180037861  cmp     r8d, r14d
0x180037864  jg      loc_180037CE4
0x18003786a  mov     r14d, [rsp+0B30h+CodePage]
0x18003786f  xor     ecx, ecx
0x180037871  mov     [r12+r8*2], cx
0x180037876  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18003787d  mov     ecx, 7Fh
0x180037882  test    esi, esi
0x180037884  js      loc_180037C88
0x18003788a  mov     ebx, esi
0x18003788c  cmp     ebx, 7Fh
0x18003788f  jg      loc_180038CDA
0x180037895  lea     rdi, [rbp+0A30h+P]
0x18003789c  test    ebx, ebx
0x18003789e  jz      loc_180037D05
0x1800378a4  mov     [rsp+0B30h+cchWideChar], ecx; cchWideChar
0x1800378a8  mov     r9d, ebx; cbMultiByte
0x1800378ab  mov     ecx, r14d; CodePage
0x1800378ae  mov     [rsp+0B30h+lpWideCharStr], rdi; lpWideCharStr
0x1800378b3  mov     r8, r15; lpMultiByteStr
0x1800378b6  xor     edx, edx; dwFlags
0x1800378b8  call    MultiByteToWideChar
0x1800378bd  movsxd  r14, eax
0x1800378c0  test    eax, eax
0x1800378c2  jz      loc_180037CD6
0x1800378c8  cmp     r14d, dword ptr [rsp+0B30h+Handle]
0x1800378cd  jg      loc_180037CD6
0x1800378d3  mov     r8d, [rsp+0B30h+var_AD0]
0x1800378d8  xor     ecx, ecx
0x1800378da  mov     [rdi+r14*2], cx
0x1800378df  mov     rdx, r14
0x1800378e2  cmp     [rsp+0B30h+var_AD8], 0
0x1800378e7  jz      loc_1800380F6
0x1800378ed  mov     r14d, 0FFFFFFFFh
0x1800378f3  cmp     r13d, 7Fh
0x1800378f7  jz      loc_180037CB7
0x1800378fd  cmp     r13d, 0C00h
0x180037904  ja      loc_180037A5B
0x18003790a  jz      loc_180037D90
0x180037910  test    r13d, r13d
0x180037913  jz      loc_180037D90
0x180037919  cmp     r13d, 400h
0x180037920  jz      loc_180037D90
0x180037926  cmp     r13d, 800h
0x18003792d  jnz     loc_180037A75
0x180037933  mov     rcx, cs:gpSysLocHashN
0x18003793a  test    rcx, rcx
0x18003793d  jnz     loc_180037BE4
0x180037943  cmp     cs:BasepIsSecureProcess, cl
0x180037949  jnz     loc_180037B90
0x18003794f  lea     rcx, gTblPtrsLock
0x180037956  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18003795c  cmp     cs:gpSysLocHashN, 0
0x180037964  jnz     loc_180037A35
0x18003796a  mov     ebx, cs:gSystemLocale
0x180037970  mov     rax, cs:P
0x180037977  mov     ecx, ebx
0x180037979  shr     rcx, 7
0x18003797d  xor     rcx, rbx
0x180037980  shr     rcx, 7
0x180037984  xor     rcx, rbx
0x180037987  and     ecx, 7Fh
0x18003798a  mov     rdx, [rax+rcx*8]
0x18003798e  test    rdx, rdx
0x180037991  jz      short loc_18003799B
0x180037993  cmp     [rdx], ebx
0x180037995  jnz     loc_1800385A7
0x18003799b  mov     cs:gpSysLocHashN, rdx
0x1800379a2  test    rdx, rdx
0x1800379a5  jnz     loc_180037A35
0x1800379ab  test    ebx, 0FFF00000h
0x1800379b1  jnz     loc_180038227
0x1800379b7  cmp     cs:BasepIsSecureProcess, dl
0x1800379bd  jnz     loc_180038227
0x1800379c3  mov     ecx, ebx
0x1800379c5  call    GetWindowsLocaleData
0x1800379ca  test    rax, rax
0x1800379cd  jz      loc_1800385B9
0x1800379d3  cmp     bx, 7Fh
0x1800379d7  jz      loc_18003863B
0x1800379dd  shr     ebx, 10h
0x1800379e0  test    bl, 0Fh
0x1800379e3  jnz     loc_1800381F4
0x1800379e9  mov     ecx, [rax]
0x1800379eb  mov     rax, cs:qword_18039EC90
0x1800379f2  add     rax, 2
0x1800379f6  lea     rcx, [rax+rcx*2]
0x1800379fa  xor     edx, edx
0x1800379fc  call    MakeNamedLocaleHashNode
0x180037a01  mov     cs:gpSysLocHashN, rax
0x180037a08  test    rax, rax
0x180037a0b  jnz     short loc_180037A35
0x180037a0d  xor     edx, edx
0x180037a0f  lea     rcx, aEnUs; "en-US"
0x180037a16  call    MakeNamedLocaleHashNode
0x180037a1b  mov     cs:gpSysLocHashN, rax
0x180037a22  test    rax, rax
0x180037a25  jnz     short loc_180037A35
0x180037a27  mov     rax, cs:gpInvLocHashN
0x180037a2e  mov     cs:gpSysLocHashN, rax
0x180037a35  lea     rcx, gTblPtrsLock
0x180037a3c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180037a42  mov     rcx, cs:gpSysLocHashN
0x180037a49  jmp     loc_180037B90
0x180037a4e  mov     [rsp+0B30h+var_AD8], 0
0x180037a56  jmp     loc_18003778E
0x180037a5b  cmp     r13d, 1000h
0x180037a62  jz      loc_180038777
0x180037a68  cmp     r13d, 1400h
0x180037a6f  jz      loc_180038787
0x180037a75  mov     rcx, cs:gpSysLocHashN
0x180037a7c  test    rcx, rcx
0x180037a7f  jnz     loc_180037B8B
0x180037a85  cmp     cs:BasepIsSecureProcess, cl
0x180037a8b  jnz     loc_180037B8B
0x180037a91  lea     rcx, gTblPtrsLock
0x180037a98  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180037a9e  cmp     cs:gpSysLocHashN, 0
0x180037aa6  jnz     loc_180037B77
0x180037aac  mov     ebx, cs:gSystemLocale
0x180037ab2  mov     rax, cs:P
0x180037ab9  mov     ecx, ebx
0x180037abb  shr     rcx, 7
0x180037abf  xor     rcx, rbx
0x180037ac2  shr     rcx, 7
0x180037ac6  xor     rcx, rbx
0x180037ac9  and     ecx, 7Fh
0x180037acc  mov     rdx, [rax+rcx*8]
0x180037ad0  test    rdx, rdx
0x180037ad3  jz      short loc_180037ADD
0x180037ad5  cmp     [rdx], ebx
0x180037ad7  jnz     loc_180038110
0x180037add  mov     cs:gpSysLocHashN, rdx
0x180037ae4  test    rdx, rdx
0x180037ae7  jnz     loc_180037B77
0x180037aed  test    ebx, 0FFF00000h
0x180037af3  jnz     loc_18003809D
0x180037af9  cmp     cs:BasepIsSecureProcess, dl
0x180037aff  jnz     loc_18003809D
0x180037b05  mov     ecx, ebx
0x180037b07  call    GetWindowsLocaleData
0x180037b0c  test    rax, rax
0x180037b0f  jz      loc_1800381C6
0x180037b15  cmp     bx, 7Fh
0x180037b19  jz      loc_1800382FD
0x180037b1f  shr     ebx, 10h
0x180037b22  test    bl, 0Fh
0x180037b25  jnz     loc_18003806A
0x180037b2b  mov     ecx, [rax]
0x180037b2d  mov     rax, cs:qword_18039EC90
0x180037b34  add     rax, 2
0x180037b38  lea     rcx, [rax+rcx*2]
0x180037b3c  xor     edx, edx
0x180037b3e  call    MakeNamedLocaleHashNode
0x180037b43  mov     cs:gpSysLocHashN, rax
0x180037b4a  test    rax, rax
0x180037b4d  jnz     short loc_180037B77
0x180037b4f  xor     edx, edx
0x180037b51  lea     rcx, aEnUs; "en-US"
0x180037b58  call    MakeNamedLocaleHashNode
0x180037b5d  mov     cs:gpSysLocHashN, rax
0x180037b64  test    rax, rax
0x180037b67  jnz     short loc_180037B77
0x180037b69  mov     rax, cs:gpInvLocHashN
0x180037b70  mov     cs:gpSysLocHashN, rax
0x180037b77  lea     rcx, gTblPtrsLock
0x180037b7e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180037b84  mov     rcx, cs:gpSysLocHashN
0x180037b8b  cmp     r13d, [rcx]
0x180037b8e  jnz     short loc_180037B95
0x180037b90  test    rcx, rcx
0x180037b93  jnz     short loc_180037BE4
0x180037b95  mov     rax, cs:P
0x180037b9c  mov     rcx, r13
0x180037b9f  shr     rcx, 7
0x180037ba3  xor     rcx, r13
0x180037ba6  shr     rcx, 7
0x180037baa  xor     rcx, r13
0x180037bad  and     ecx, 7Fh
0x180037bb0  mov     rbx, [rax+rcx*8]
0x180037bb4  lea     rsi, ds:0[rcx*8]
0x180037bbc  test    rbx, rbx
0x180037bbf  jz      loc_1800380BA
0x180037bc5  cmp     [rbx], r13d
0x180037bc8  jnz     loc_1800380AD
0x180037bce  test    rbx, rbx
0x180037bd1  jz      loc_1800382C3
0x180037bd7  mov     rcx, [rbx+68h]
0x180037bdb  test    rcx, rcx
0x180037bde  jz      loc_1800382C5
0x180037be4  mov     rbx, [rcx+20h]
0x180037be8  test    rbx, rbx
0x180037beb  jnz     loc_180037D27
0x180037bf1  mov     ecx, 57h ; 'W'; dwErrCode
0x180037bf6  call    SetLastError_0
0x180037bfb  xor     ebx, ebx
0x180037bfd  lea     rax, [rbp+0A30h+WideCharStr]
0x180037c01  cmp     r12, rax
0x180037c04  jnz     loc_180038949
0x180037c0a  lea     rax, [rbp+0A30h+P]
0x180037c11  cmp     rdi, rax
0x180037c14  jnz     loc_180038923
0x180037c1a  mov     eax, ebx
0x180037c1c  mov     r14, [rsp+0B30h+var_38]
0x180037c24  mov     r12, [rsp+0B30h+var_30]
0x180037c2c  mov     rcx, [rbp+0A30h+var_50]
0x180037c33  xor     rcx, rsp; StackCookie
0x180037c36  call    __security_check_cookie
0x180037c3b  add     rsp, 0B08h
0x180037c42  pop     r15
0x180037c44  pop     r13
0x180037c46  pop     rdi
0x180037c47  pop     rsi
0x180037c48  pop     rbx
0x180037c49  pop     rbp
0x180037c4a  retn
0x180037c4b  mov     rax, rdx
0x180037c4e  xchg    ax, ax
0x180037c50  cmp     byte ptr [rbx+rax+1], 0
0x180037c55  lea     rax, [rax+1]
0x180037c59  jnz     short loc_180037C50
0x180037c5b  lea     rdi, [rax+1]
0x180037c5f  cmp     rdi, 7FFFFFFFh
0x180037c66  ja      short loc_180037C7C
0x180037c68  jmp     loc_180037816
0x180037c6d  test    r12, r12
0x180037c70  jnz     loc_180038D87
0x180037c76  mov     r12d, 57h ; 'W'
0x180037c7c  mov     ecx, r12d; dwErrCode
0x180037c7f  call    SetLastError_0
0x180037c84  xor     eax, eax
0x180037c86  jmp     short loc_180037C1C
0x180037c88  mov     rax, rdx
  ... truncated ...
```
