# MakeNamedLocaleHashNode

- ea: `0x18001c970`
- end: `0x18001d7b7`
- name: `MakeNamedLocaleHashNode`
- size: `3655`
- prototype: ``
- caller_count: `22`
- callee_count: `19`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000dd50`
- `0x180010080`
- `0x180010320`
- `0x1800108d0`
- `0x180012070`
- `0x1800123e0`
- `0x1800181e0`
- `0x180019090`
- `0x18001a230`
- `0x18001b1d0`
- `0x18001b3a0`
- `0x18001d7c0`
- `0x180037730`
- `0x18003e054`
- `0x180071550`
- `0x1800754b0`
- `0x180089570`
- `0x180089a10`
- `0x1800b1630`
- `0x1800b1bc0`
- `0x1800b1f48`
- `0x180104268`

## callees

- `0x180010080`
- `0x180012070`
- `0x1800134a0`
- `0x18001a1b8`
- `0x18001c970`
- `0x18001e794`
- `0x1800749d4`
- `0x1800880d8`
- `0x1800a562c`
- `0x1800b1bc0`
- `0x1800c1468`
- `0x1800c1668`
- `0x1800c1738`
- `0x1800c1bf0`
- `0x1800c2188`
- `0x1800e5f7c`
- `0x18012d119`
- `0x180138ebc`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001ccce`
- `ntdll!RtlInitUnicodeString` at `0x18001cf0b`
- `ntdll!RtlInitUnicodeString` at `0x18001d462`
- `ntdll!RtlInitUnicodeString` at `0x18001d5a4`
- `ntdll!RtlInitUnicodeString` at `0x18001ccce`
- `ntdll!RtlInitUnicodeString` at `0x18001cf0b`
- `ntdll!RtlInitUnicodeString` at `0x18001d462`
- `ntdll!RtlInitUnicodeString` at `0x18001d5a4`
- `ntdll!NtOpenKey` at `0x18001cd05`
- `ntdll!NtOpenKey` at `0x18001d499`
- `ntdll!NtOpenKey` at `0x18001cd05`
- `ntdll!NtOpenKey` at `0x18001d499`
- `ntdll!NtQueryValueKey` at `0x18001cf46`
- `ntdll!NtQueryValueKey` at `0x18001d5df`
- `ntdll!NtQueryValueKey` at `0x18001cf46`
- `ntdll!NtQueryValueKey` at `0x18001d5df`
- `ntdll!NtClose` at `0x18001cf9e`
- `ntdll!NtClose` at `0x18001d633`
- `ntdll!NtClose` at `0x18001cf9e`
- `ntdll!NtClose` at `0x18001d633`
- `ntdll!RtlFreeHeap` at `0x18001d36a`
- `ntdll!RtlFreeHeap` at `0x18001d571`
- `ntdll!RtlFreeHeap` at `0x18001d36a`
- `ntdll!RtlFreeHeap` at `0x18001d571`
- `ntdll!RtlFlushSecureMemoryCache` at `0x18001d118`
- `ntdll!RtlFlushSecureMemoryCache` at `0x18001d76e`
- `ntdll!RtlFlushSecureMemoryCache` at `0x18001d118`
- `ntdll!RtlFlushSecureMemoryCache` at `0x18001d76e`
- `ntdll!NtUnmapViewOfSectionEx` at `0x18001d0f8`
- `ntdll!NtUnmapViewOfSectionEx` at `0x18001d133`
- `ntdll!NtUnmapViewOfSectionEx` at `0x18001d53c`
- `ntdll!NtUnmapViewOfSectionEx` at `0x18001d789`
- `ntdll!NtUnmapViewOfSectionEx` at `0x18001d0f8`
- `ntdll!NtUnmapViewOfSectionEx` at `0x18001d133`
- `ntdll!NtUnmapViewOfSectionEx` at `0x18001d53c`
- `ntdll!NtUnmapViewOfSectionEx` at `0x18001d789`
- `ntdll!RtlAllocateHeap` at `0x18001d1b6`
- `ntdll!RtlAllocateHeap` at `0x18001d1b6`

## string_xrefs

- `0x18001cb78`: `\Registry\Machine\System\CurrentControlSet\Control`

## pseudocode

```c
__int64 __fastcall MakeNamedLocaleHashNode(const WCHAR *a1, int a2)
{
  const WCHAR *v2; // r9
  const WCHAR *v3; // r8
  __int64 v4; // r10
  unsigned __int64 v5; // rcx
  int v6; // edx
  int v7; // edi
  __int64 v8; // r13
  int v9; // r11d
  int v10; // r8d
  int v11; // ebx
  unsigned __int16 *v12; // rsi
  unsigned __int16 *i; // r10
  WCHAR v14; // ax
  unsigned __int16 v15; // dx
  int v16; // edx
  int v17; // ebx
  unsigned int v18; // r12d
  unsigned int *v19; // r14
  int v20; // ecx
  const wchar_t *v21; // rsi
  WCHAR *v22; // rax
  __int64 v23; // rcx
  WCHAR *v24; // r8
  __int64 v25; // rdx
  WCHAR *v26; // rcx
  unsigned int *v27; // r15
  __int64 v28; // rcx
  unsigned __int64 v29; // rdx
  WCHAR *v30; // rax
  WCHAR *v31; // rcx
  __int64 v32; // rcx
  WCHAR *v33; // rax
  __int64 v34; // rdi
  __int64 v35; // rcx
  WCHAR *v36; // rcx
  NTSTATUS v37; // eax
  HANDLE v38; // rdi
  __int64 LocaleHashNode; // rax
  __int64 v40; // rdi
  _DWORD *v41; // rsi
  char *v42; // r8
  char *v43; // r9
  int v44; // r15d
  unsigned int *v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // r8
  __int64 v48; // rax
  bool v49; // zf
  __int64 LocaleNullStringFromArrayInPool; // rax
  int v51; // eax
  __int16 v52; // ax
  void *v53; // rcx
  __int64 result; // rax
  unsigned int *WindowsLocaleData; // rax
  PCWSTR v56; // rsi
  NTSTATUS v57; // edi
  __int64 v58; // r10
  WCHAR *v59; // rax
  __int64 v60; // rcx
  WCHAR *v61; // rcx
  WCHAR *v62; // rax
  __int64 v63; // rcx
  WCHAR *v64; // rax
  const wchar_t *v65; // rcx
  unsigned __int64 v66; // r9
  WCHAR *v67; // rcx
  int v68; // r9d
  __int64 v69; // rax
  unsigned int *v70; // rdi
  int v71; // eax
  int v72; // eax
  int v73; // esi
  const WCHAR *v74; // rbx
  __int64 v75; // rax
  _QWORD *Heap; // rax
  _QWORD *v77; // rbx
  __int64 v78; // r10
  __int64 v79; // rdx
  __int64 v80; // rax
  __int64 v81; // rax
  __int16 v82; // r8
  __int64 NamedLocaleHashNode; // rax
  __int64 v84; // r9
  const wchar_t *v85; // rdx
  __int64 v86; // rcx
  WCHAR *v87; // r9
  WCHAR *v88; // rcx
  WCHAR *v89; // rax
  __int64 v90; // rcx
  WCHAR *v91; // rcx
  int v92; // edx
  int v93; // r9d
  __int64 v94; // rax
  int v95; // eax
  int v96; // ebx
  HANDLE v97; // rbx
  NTSTATUS v98; // ebx
  PCWSTR v99; // rbx
  WCHAR *v100; // rax
  __int64 v101; // rcx
  __int64 v102; // rdx
  WCHAR *v103; // rcx
  __int64 v104; // rcx
  WCHAR *v105; // rax
  __int64 v106; // r9
  const wchar_t *v107; // rdx
  WCHAR *v108; // r9
  __int64 v109; // rcx
  HANDLE KeyHandle; // [rsp+38h] [rbp-D0h] BYREF
  ULONG DestinationString; // [rsp+40h] [rbp-C8h] BYREF
  int DestinationString_4; // [rsp+44h] [rbp-C4h]
  struct _UNICODE_STRING DestinationString_8; // [rsp+48h] [rbp-C0h] BYREF
  struct _UNICODE_STRING NtPathName_8; // [rsp+58h] [rbp-B0h] BYREF
  PCWSTR v115; // [rsp+68h] [rbp-A0h]
  union _LARGE_INTEGER FileSize; // [rsp+70h] [rbp-98h] BYREF
  const WCHAR *v117; // [rsp+78h] [rbp-90h]
  __int64 v118; // [rsp+80h] [rbp-88h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-80h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+B8h] [rbp-50h] BYREF
  int v121; // [rsp+BCh] [rbp-4Ch]
  unsigned int v122; // [rsp+C0h] [rbp-48h]
  unsigned int v123; // [rsp+C4h] [rbp-44h]
  wchar_t pszSrc[512]; // [rsp+2D8h] [rbp+1D0h] BYREF
  WCHAR SourceString[512]; // [rsp+6D8h] [rbp+5D0h] BYREF

  v2 = a1;
  v3 = a1;
  v4 = 0x43FFFFFF01FF9LL;
  v117 = a1;
  v5 = 0;
  DestinationString_4 = a2;
  NtPathName_8 = 0;
  FileSize.QuadPart = 0;
  while ( 1 )
  {
    if ( v5 >= 0x55 )
      return 0;
    v6 = *v3;
    if ( !(_WORD)v6 )
      break;
    if ( ((unsigned __int16)(v6 - 45) > 0x32u || !_bittest64(&v4, (unsigned int)(v6 - 45)))
      && (unsigned __int16)(v6 - 97) > 0x19u )
    {
      return 0;
    }
    ++v3;
    ++v5;
  }
  if ( BasepIsSecureProcess )
    return 0;
  v7 = 0;
  v8 = qword_18039EC90;
  v9 = (unsigned __int16)word_18039EC6A - 1;
  v115 = v2;
LABEL_9:
  while ( 2 )
  {
    if ( v7 > v9 )
    {
      v17 = 0;
      v18 = 4096;
      v118 = 0;
      v19 = 0;
    }
    else
    {
      v10 = 85;
      v11 = (v9 + v7) / 2;
      v12 = (unsigned __int16 *)(qword_18039EC88 + 8LL * v11);
      v118 = qword_18039EC90 + 2 + 2LL * *v12;
      for ( i = (unsigned __int16 *)v118; v10 > 0; ++i )
      {
        v14 = *v2;
        if ( !*v2 )
          break;
        v15 = *i;
        if ( !*i )
          goto LABEL_168;
        if ( (unsigned __int16)(v14 - 65) <= 0x19u )
          v14 |= 0x20u;
        if ( (unsigned __int16)(v15 - 65) <= 0x19u )
          v15 |= 0x20u;
        if ( v14 == 95 )
          v14 = 45;
        if ( v15 == 95 )
          v15 = 45;
        v16 = v14 - v15;
        if ( v16 )
        {
          if ( v16 < 0 )
            goto LABEL_14;
LABEL_168:
          v2 = v117;
          v7 = v11 + 1;
          goto LABEL_9;
        }
        --v10;
        ++v2;
      }
      if ( *v2 )
        goto LABEL_168;
      if ( *i )
      {
LABEL_14:
        v2 = v117;
        v9 = v11 - 1;
        continue;
      }
      v20 = *((_DWORD *)v12 + 1);
      v18 = v20 & 0x7FFFFFFF;
      if ( v20 < 0 || (v20 & 0xF0000) != 0 || v20 == 1034 )
      {
        v17 = 0;
      }
      else
      {
        v17 = 0;
        v118 = 0;
      }
      v19 = (unsigned int *)(qword_18039EC78 + (unsigned __int16)word_18039EC70 * v12[1]);
      if ( v19 )
      {
        if ( (v18 & 0xF0000) != 0 )
        {
          WindowsLocaleData = (unsigned int *)GetWindowsLocaleData((unsigned __int16)v20);
          if ( WindowsLocaleData )
            v115 = (PCWSTR)(v8 + 2LL * *WindowsLocaleData + 2);
        }
      }
    }
    break;
  }
  if ( (unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
    || v18 != 4096
    || DestinationString_4
    || !(unsigned int)Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline()
    && !(unsigned int)CreateTransientLocales()
    || (result = FindNamedLocaleHashNode(v117)) == 0 )
  {
    KeyHandle = 0;
    v21 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control";
    v22 = pszSrc;
    v23 = 2147483646;
    v24 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control";
    v25 = 512;
    memset(&ObjectAttributes, 0, 44);
    DestinationString_8 = 0;
    do
    {
      if ( !v23 )
        break;
      if ( !*v24 )
        break;
      *v22++ = *v24++;
      --v23;
      --v25;
    }
    while ( v25 );
    v26 = v22 - 1;
    if ( v25 )
      v26 = v22;
    *v26 = 0;
    if ( !v25 )
      goto LABEL_41;
    v90 = 512;
    v89 = pszSrc;
    do
    {
      if ( !*v89 )
        break;
      ++v89;
      --v90;
    }
    while ( v90 );
    v84 = 512 - v90;
    if ( !v90 )
      goto LABEL_41;
    v85 = L"\\Nls\\CustomLocale";
    v24 = (WCHAR *)v90;
    v49 = v84 == 512;
    v86 = 2147483646;
    v87 = &pszSrc[v84];
    if ( !v49 )
    {
      do
      {
        if ( !v86 )
          break;
        if ( !*v85 )
          break;
        *v87++ = *v85++;
        --v86;
        v24 = (WCHAR *)((char *)v24 - 1);
      }
      while ( v24 );
    }
    v88 = v87 - 1;
    if ( v24 )
      v88 = v87;
    *v88 = 0;
    if ( v24 )
    {
      RtlInitUnicodeString(&DestinationString_8, pszSrc);
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString_8;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v27 = 0;
      if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
      {
        v97 = KeyHandle;
        DestinationString_8 = 0;
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString_8, v115);
        memset_0(KeyValueInformation, 0, 0x214u);
        v98 = NtQueryValueKey(
                v97,
                &DestinationString_8,
                KeyValueFullInformation,
                KeyValueInformation,
                0x214u,
                &DestinationString);
        if ( v121 == 1 )
        {
          if ( v98 >= 0 )
          {
            if ( (v123 & 1) != 0
              || v123 < 2
              || *(_WORD *)&KeyValueInformation[2 * ((unsigned __int64)v123 >> 1) - 2 + v122] )
            {
              v98 = -1073741492;
            }
            else
            {
              v98 = 0;
            }
          }
        }
        else
        {
          v98 = -1073741492;
        }
        if ( KeyHandle )
          NtClose(KeyHandle);
        if ( v98 < 0 )
          goto LABEL_202;
        v99 = v115;
        v100 = pszSrc;
        v101 = 2147483646;
        v24 = (WCHAR *)v115;
        v102 = 260;
        do
        {
          if ( !v101 )
            break;
          if ( !*v24 )
            break;
          *v100++ = *v24++;
          --v101;
          --v102;
        }
        while ( v102 );
        v103 = v100 - 1;
        if ( v102 )
          v103 = v100;
        v27 = 0;
        *v103 = 0;
        if ( !v102 )
          goto LABEL_202;
        v104 = 260;
        v105 = pszSrc;
        do
        {
          if ( !*v105 )
            break;
          ++v105;
          --v104;
        }
        while ( v104 );
        v106 = 260 - v104;
        if ( !v104 )
          goto LABEL_202;
        v24 = (WCHAR *)v104;
        v49 = v106 == 260;
        v107 = L".nlp";
        v108 = &pszSrc[v106];
        v109 = 2147483646;
        v27 = 0;
        if ( !v49 )
        {
          do
          {
            v27 = 0;
            if ( !v109 )
              break;
            if ( !*v107 )
              break;
            *v108++ = *v107++;
            --v109;
            v24 = (WCHAR *)((char *)v24 - 1);
          }
          while ( v24 );
        }
        v91 = v108 - 1;
        if ( v24 )
          v91 = v108;
        *v91 = 0;
        if ( v24 )
        {
          if ( (unsigned int)GetNTFileName(pszSrc, &NtPathName_8)
            || (v94 = CreateAndMapFileSection((int)&NtPathName_8, v92, (int)v24, v93, &FileSize),
                (v27 = (unsigned int *)v94) == 0)
            || (unsigned int)ValidateLocaleFile(v94, v99, &FileSize) )
          {
            v17 = 0;
          }
          else
          {
            v95 = NtUnmapViewOfSectionEx(-1, v27, 0);
            v96 = v95;
            if ( v95 < 0 )
            {
              if ( v95 != -1073741755
                || !RtlFlushSecureMemoryCache(v27, 0)
                || (v96 = NtUnmapViewOfSectionEx(-1, v27, 0), v96 < 0) )
              {
                BaseSetLastNTError((unsigned int)v96);
              }
            }
            v17 = 0;
            v27 = 0;
          }
          if ( NtPathName_8.Buffer )
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName_8.Buffer);
            NtPathName_8.Buffer = 0;
          }
        }
        else
        {
LABEL_202:
          v17 = 0;
        }
      }
      else
      {
        KeyHandle = 0;
      }
    }
    else
    {
LABEL_41:
      v27 = 0;
    }
    KeyHandle = 0;
    v28 = 2147483646;
    v29 = 512;
    v30 = SourceString;
    memset(&ObjectAttributes, 0, 44);
    DestinationString_8 = 0;
    do
    {
      if ( !v28 )
        break;
      v24 = (WCHAR *)*v21;
      if ( !(_WORD)v24 )
        break;
      *v30 = (unsigned __int16)v24;
      ++v21;
      ++v30;
      --v28;
      --v29;
    }
    while ( v29 );
    v31 = v30 - 1;
    if ( v29 )
      v31 = v30;
    *v31 = 0;
    if ( !v29 )
      goto LABEL_64;
    v32 = 512;
    v33 = SourceString;
    do
    {
      if ( !*v33 )
        break;
      ++v33;
      --v32;
    }
    while ( v32 );
    if ( !v32 )
    {
      v24 = 0;
      goto LABEL_64;
    }
    v34 = v32;
    v29 = (unsigned __int64)L"\\Nls\\ExtendedLocale";
    v24 = &SourceString[512 - v32];
    v35 = 2147483646;
    do
    {
      if ( !v35 )
        break;
      if ( !*(_WORD *)v29 )
        break;
      *v24 = *(_WORD *)v29;
      v29 += 2LL;
      ++v24;
      --v35;
      --v34;
    }
    while ( v34 );
    v36 = v24 - 1;
    if ( v34 )
      v36 = v24;
    *v36 = 0;
    if ( !v34 )
      goto LABEL_64;
    RtlInitUnicodeString(&DestinationString_8, SourceString);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString_8;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v37 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( v37 >= 0 )
    {
      v38 = KeyHandle;
    }
    else
    {
      v38 = 0;
      KeyHandle = 0;
    }
    if ( v37 < 0 )
      goto LABEL_64;
    v56 = v115;
    DestinationString = 0;
    DestinationString_8 = 0;
    RtlInitUnicodeString(&DestinationString_8, v115);
    memset_0(KeyValueInformation, 0, 0x214u);
    v57 = NtQueryValueKey(
            v38,
            &DestinationString_8,
            KeyValueFullInformation,
            KeyValueInformation,
            0x214u,
            &DestinationString);
    if ( v121 == 1 )
    {
      if ( v57 >= 0 )
      {
        if ( (v123 & 1) != 0
          || v123 < 2
          || (v29 = (unsigned __int64)v123 >> 1, *(_WORD *)&KeyValueInformation[2 * v29 - 2 + v122]) )
        {
          v57 = -1073741492;
        }
        else
        {
          v57 = 0;
        }
      }
    }
    else
    {
      v57 = -1073741492;
    }
    if ( KeyHandle )
      NtClose(KeyHandle);
    if ( v57 < 0 )
      goto LABEL_64;
    v58 = 2147483646;
    v59 = pszSrc;
    v60 = 2147483646;
    v24 = (WCHAR *)v56;
    v29 = 260;
    do
    {
      if ( !v60 )
        break;
      if ( !*v24 )
        break;
      *v59++ = *v24++;
      --v60;
      --v29;
    }
    while ( v29 );
    v61 = v59 - 1;
    if ( v29 )
      v61 = v59;
    v17 = 0;
    *v61 = 0;
    if ( !v29 )
      goto LABEL_64;
    v62 = pszSrc;
    v63 = 260;
    do
    {
      if ( !*v62 )
        break;
      ++v62;
      --v63;
    }
    while ( v63 );
    v29 = 260 - v63;
    if ( !v63 )
    {
      v29 = 0;
      goto LABEL_64;
    }
    v64 = &pszSrc[v29];
    v65 = L".nlx";
    v66 = 260 - v29;
    if ( 260 != v29 )
    {
      do
      {
        v17 = 0;
        if ( !v58 )
          break;
        v29 = *v65;
        if ( !(_WORD)v29 )
          break;
        *v64 = v29;
        ++v65;
        ++v64;
        --v58;
        --v66;
      }
      while ( v66 );
    }
    v67 = v64 - 1;
    if ( v66 )
      v67 = v64;
    *v67 = 0;
    if ( !v66 )
    {
LABEL_64:
      if ( v27 )
      {
        LocaleHashNode = CreateLocaleHashNode(0, v29, v24);
        v40 = LocaleHashNode;
        if ( LocaleHashNode )
        {
          v41 = (unsigned int *)((char *)v27 + *v27);
          v42 = (char *)v27 + (unsigned int)v41[7];
          *(_QWORD *)(LocaleHashNode + 40) = v42;
          *(_QWORD *)(LocaleHashNode + 56) = v42;
          v43 = (char *)v27 + (unsigned int)v41[14];
          v44 = 1;
          *(_QWORD *)(LocaleHashNode + 48) = v43;
          *(_QWORD *)(LocaleHashNode + 64) = v43;
          *(_DWORD *)(LocaleHashNode + 72) = *v41;
          if ( (v42[24] & 1) != 0 )
          {
            *(_DWORD *)(LocaleHashNode + 76) = 32;
LABEL_68:
            *(_QWORD *)(v40 + 104) = v40;
            goto LABEL_69;
          }
          *(_DWORD *)(LocaleHashNode + 76) = 16;
          NamedLocaleHashNode = GetNamedLocaleHashNode(&v43[2 * *((unsigned int *)v42 + 73) + 2], 1);
          *(_QWORD *)(v40 + 104) = NamedLocaleHashNode;
          if ( !NamedLocaleHashNode )
          {
            if ( *v41 >= 3u )
              goto LABEL_68;
            *(_QWORD *)(v40 + 104) = GetNamedLocaleHashNode(&word_180290A38, 1);
          }
LABEL_69:
          v45 = *(unsigned int **)(v40 + 40);
          v46 = *(_QWORD *)(v40 + 48);
          v47 = v46 + 2 * (*v45 + 1LL);
          v48 = v118;
          v49 = v118 == 0;
          *(_QWORD *)(v40 + 16) = v47;
          if ( v49 )
            v48 = v47;
          *(_QWORD *)(v40 + 8) = v48;
          *(_QWORD *)(v40 + 24) = v46 + 2LL * v45[46] + 2;
          if ( !v19 || v18 == 4096 )
          {
            if ( *((_WORD *)v45 + 4) == 4096 )
              *(_DWORD *)v40 = GetTransientLCID(v47);
            if ( !v19 )
              goto LABEL_75;
          }
          else
          {
            *(_DWORD *)v40 = v18;
          }
          v82 = *(_WORD *)(v40 + 2);
          if ( (v82 & 0xF) != 0 )
          {
            LocaleNullStringFromArrayInPool = GetLocaleNullStringFromArrayInPool(
                                                qword_18039EC90,
                                                v19[54],
                                                (v82 & 0xFu) - 1);
LABEL_76:
            *(_QWORD *)(v40 + 32) = LocaleNullStringFromArrayInPool;
            v51 = *(_DWORD *)(v40 + 76);
            if ( v17 )
            {
              if ( !v19 )
                v44 = 32769;
              *(_DWORD *)(v40 + 76) = v51 | v44;
              if ( v19 )
                goto LABEL_80;
            }
            else
            {
              if ( v19 )
              {
                *(_DWORD *)(v40 + 76) = v51 | 9;
LABEL_80:
                *(_WORD *)(v40 + 80) = *((_WORD *)v19 + 5);
                *(_WORD *)(v40 + 82) = (unsigned __int8)*((_WORD *)v19 + 61);
                v52 = *((unsigned __int8 *)v19 + 123);
LABEL_81:
                *(_WORD *)(v40 + 84) = v52;
                v53 = (void *)v40;
                return InsertLocaleHashNode(v53);
              }
              *(_DWORD *)(v40 + 76) = v51 | 2;
            }
            *(_WORD *)(v40 + 80) = 4096;
            *(_WORD *)(v40 + 82) = 6;
            v52 = 22;
            goto LABEL_81;
          }
LABEL_75:
          LocaleNullStringFromArrayInPool = *(_QWORD *)(v40 + 16);
          goto LABEL_76;
        }
        return 0;
      }
      if ( !v19 )
      {
        if ( !DestinationString_4 )
        {
          v74 = v117;
          if ( !(unsigned int)IsBadLocaleName(v117) )
          {
            v75 = ResolveLocaleHashNode(v74, 1, 1);
            return MakeConstructedLocaleFromHashNode(v74, v75);
          }
        }
        return 0;
      }
      if ( BasepIsSecureProcess )
        return 0;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x70u);
      v77 = Heap;
      if ( !Heap )
        return 0;
      *(_DWORD *)Heap = v18;
      Heap[5] = v19;
      Heap[7] = v19;
      v78 = qword_18039EC90;
      Heap[6] = qword_18039EC90;
      Heap[8] = qword_18039EC90;
      *((_DWORD *)Heap + 18) = dword_18039EC74;
      v79 = v78 + 2 * (*v19 + 1LL);
      Heap[2] = v79;
      Heap[3] = v78 + 2 * (v19[46] + 1LL);
      *((_WORD *)Heap + 40) = *((_WORD *)v19 + 5);
      *((_WORD *)Heap + 41) = (unsigned __int8)*((_WORD *)v19 + 61);
      *((_WORD *)Heap + 42) = *((unsigned __int8 *)v19 + 123);
      if ( (v18 & 0xF0000) != 0 )
        v79 = GetLocaleNullStringFromArrayInPool(qword_18039EC90, v19[54], (HIWORD(v18) & 0xF) - 1);
      v80 = v118;
      v49 = v118 == 0;
      v77[4] = v79;
      if ( v49 )
        v80 = v79;
      v77[1] = v80;
      if ( (v19[6] & 1) != 0 )
      {
        *((_DWORD *)v77 + 19) = 33;
      }
      else
      {
        *((_DWORD *)v77 + 19) = 17;
        v81 = GetNamedLocaleHashNode(v78 + 2 + 2LL * v19[73], 2);
        v77[13] = v81;
        if ( v81 )
          goto LABEL_144;
      }
      v77[13] = v77;
LABEL_144:
      if ( v18 == 4096 )
        *(_DWORD *)v77 = GetTransientLCID(v77[2]);
      v53 = v77;
      return InsertLocaleHashNode(v53);
    }
    if ( !(unsigned int)GetNTFileName(pszSrc, &NtPathName_8) )
    {
      v69 = CreateAndMapFileSection((int)&NtPathName_8, v29, (int)v24, v68, &FileSize);
      v70 = (unsigned int *)v69;
      if ( v69 )
      {
        v71 = ValidateLocaleFile(v69, v56, &FileSize);
        v17 = v71;
        if ( v71 == 1 )
        {
          if ( v27 )
          {
            v17 = 0;
LABEL_124:
            v72 = NtUnmapViewOfSectionEx(-1, v70, 0);
            v73 = v72;
            if ( v72 < 0 )
            {
              if ( v72 != -1073741755
                || !RtlFlushSecureMemoryCache(v70, 0)
                || (v73 = NtUnmapViewOfSectionEx(-1, v70, 0), v73 < 0) )
              {
                BaseSetLastNTError((unsigned int)v73);
              }
            }
            goto LABEL_160;
          }
        }
        else if ( !v71 )
        {
          goto LABEL_124;
        }
        v27 = v70;
      }
    }
LABEL_160:
    if ( NtPathName_8.Buffer )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName_8.Buffer);
      NtPathName_8.Buffer = 0;
    }
    goto LABEL_64;
  }
  return result;
}

```

## disassembly

```asm
0x18001c970  mov     r11, rsp
0x18001c973  push    rbp
0x18001c974  push    rbx
0x18001c975  lea     rbp, [r11-0A08h]
0x18001c97c  sub     rsp, 0AF8h
0x18001c983  mov     rax, cs:__security_cookie
0x18001c98a  xor     rax, rsp
0x18001c98d  mov     [rbp+0A00h+var_30], rax
0x18001c994  mov     [r11+10h], rsi
0x18001c998  xor     ebx, ebx
0x18001c99a  mov     [r11+18h], rdi
0x18001c99e  xorps   xmm0, xmm0
0x18001c9a1  mov     [r11+20h], r12
0x18001c9a5  mov     r9, rcx
0x18001c9a8  mov     [r11-18h], r13
0x18001c9ac  mov     r8, rcx
0x18001c9af  mov     [r11-20h], r14
0x18001c9b3  mov     r10, 43FFFFFF01FF9h
0x18001c9bd  mov     [rsp+0B00h+var_A90], rcx
0x18001c9c2  mov     ecx, ebx
0x18001c9c4  mov     [r11-28h], r15
0x18001c9c8  mov     dword ptr [rsp+0B00h+DestinationString+4], edx
0x18001c9cc  movups  xmmword ptr [rsp+0B00h+NtPathName.Buffer], xmm0
0x18001c9d1  mov     qword ptr [rsp+0B00h+FileSize], rbx
0x18001c9d6  cmp     rcx, 55h ; 'U'
0x18001c9da  jnb     loc_18001D14F
0x18001c9e0  movzx   edx, word ptr [r8]
0x18001c9e4  test    dx, dx
0x18001c9e7  jz      short loc_18001CA09
0x18001c9e9  lea     eax, [rdx-2Dh]
0x18001c9ec  cmp     ax, 32h ; '2'
0x18001c9f0  ja      loc_18001D73C
0x18001c9f6  bt      r10, rax
0x18001c9fa  jnb     loc_18001D73C
0x18001ca00  add     r8, 2
0x18001ca04  inc     rcx
0x18001ca07  jmp     short loc_18001C9D6
0x18001ca09  cmp     cs:BasepIsSecureProcess, bl
0x18001ca0f  jnz     loc_18001D14F
0x18001ca15  movzx   r11d, cs:word_18039EC6A
0x18001ca1d  mov     edi, ebx
0x18001ca1f  mov     r13, cs:qword_18039EC90
0x18001ca26  dec     r11d
0x18001ca29  mov     r14, cs:qword_18039EC88
0x18001ca30  mov     [rsp+0B00h+var_AA0], r9
0x18001ca35  cmp     edi, r11d
0x18001ca38  jg      loc_18001CAF5
0x18001ca3e  lea     eax, [r11+rdi]
0x18001ca42  mov     r8d, 55h ; 'U'
0x18001ca48  cdq
0x18001ca49  lea     r15, [r13+2]
0x18001ca4d  sub     eax, edx
0x18001ca4f  sar     eax, 1
0x18001ca51  movsxd  rbx, eax
0x18001ca54  movzx   ecx, word ptr [r14+rbx*8]
0x18001ca59  lea     rsi, [r14+rbx*8]
0x18001ca5d  lea     r15, [r15+rcx*2]
0x18001ca61  mov     [rsp+0B00h+var_A88], r15
0x18001ca66  mov     r10, r15
0x18001ca69  test    r8d, r8d
0x18001ca6c  jg      short loc_18001CA8F
0x18001ca6e  cmp     word ptr [r9], 0
0x18001ca73  jnz     loc_18001D3E6
0x18001ca79  cmp     word ptr [r10], 0
0x18001ca7e  jz      loc_18001CB0A
0x18001ca84  mov     r9, [rsp+0B00h+var_A90]
0x18001ca89  lea     r11d, [rbx-1]
0x18001ca8d  jmp     short loc_18001CA35
0x18001ca8f  movzx   eax, word ptr [r9]
0x18001ca93  test    ax, ax
0x18001ca96  jz      short loc_18001CA6E
0x18001ca98  movzx   edx, word ptr [r10]
0x18001ca9c  test    dx, dx
0x18001ca9f  jz      loc_18001D3E6
0x18001caa5  lea     ecx, [rax-41h]
0x18001caa8  cmp     cx, 19h
0x18001caac  ja      short loc_18001CAB2
0x18001caae  or      ax, 20h
0x18001cab2  lea     ecx, [rdx-41h]
0x18001cab5  cmp     cx, 19h
0x18001cab9  jbe     short loc_18001CAEF
0x18001cabb  cmp     ax, 5Fh ; '_'
0x18001cabf  jnz     short loc_18001CAC6
0x18001cac1  mov     eax, 2Dh ; '-'
0x18001cac6  cmp     dx, 5Fh ; '_'
0x18001caca  jnz     short loc_18001CAD1
0x18001cacc  mov     edx, 2Dh ; '-'
0x18001cad1  movzx   ecx, dx
0x18001cad4  movzx   edx, ax
0x18001cad7  sub     edx, ecx
0x18001cad9  jnz     loc_18001D3DE
0x18001cadf  dec     r8d
0x18001cae2  add     r9, 2
0x18001cae6  add     r10, 2
0x18001caea  jmp     loc_18001CA69
0x18001caef  or      dx, 20h
0x18001caf3  jmp     short loc_18001CABB
0x18001caf5  xor     ebx, ebx
0x18001caf7  mov     r13d, 1000h
0x18001cafd  mov     r12d, r13d
0x18001cb00  mov     [rsp+0B00h+var_A88], rbx
0x18001cb05  mov     r14d, ebx
0x18001cb08  jmp     short loc_18001CB61
0x18001cb0a  mov     ecx, [rsi+4]
0x18001cb0d  mov     r12d, ecx
0x18001cb10  btr     r12d, 1Fh
0x18001cb15  test    ecx, ecx
0x18001cb17  js      loc_18001D189
0x18001cb1d  mov     eax, ecx
0x18001cb1f  shr     eax, 10h
0x18001cb22  test    al, 0Fh
0x18001cb24  jnz     loc_18001D189
0x18001cb2a  cmp     ecx, 40Ah
0x18001cb30  jz      loc_18001D189
0x18001cb36  xor     ebx, ebx
0x18001cb38  mov     [rsp+0B00h+var_A88], rbx
0x18001cb3d  movzx   ecx, word ptr [rsi+2]
0x18001cb41  movzx   eax, cs:word_18039EC70
0x18001cb48  imul    ecx, eax
0x18001cb4b  movsxd  r14, ecx
0x18001cb4e  add     r14, cs:qword_18039EC78
0x18001cb55  jnz     loc_18001CEB7
0x18001cb5b  mov     r13d, 1000h
0x18001cb61  call    Feature_NoTransientLocales__private_IsEnabledDeviceUsageNoInline
0x18001cb66  test    eax, eax
0x18001cb68  jz      loc_18001CE31
0x18001cb6e  xorps   xmm0, xmm0
0x18001cb71  mov     [rsp+0B00h+KeyHandle], rbx
0x18001cb76  xor     eax, eax
0x18001cb78  lea     rsi, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x18001cb7f  mov     r15d, 7FFFFFFEh
0x18001cb85  lea     rax, [rbp+0A00h+pszSrc]
0x18001cb8c  mov     edi, 200h
0x18001cb91  mov     ecx, r15d
0x18001cb94  movups  xmmword ptr [rbp+0A00h+ObjectAttributes.ObjectName], xmm0
0x18001cb98  mov     r8, rsi
0x18001cb9b  mov     edx, edi
0x18001cb9d  movups  xmmword ptr [rbp+0A00h+ObjectAttributes+1Ch], xmm0
0x18001cba1  movups  xmmword ptr [rbp+0A00h+ObjectAttributes.Length], xmm0
0x18001cba5  movups  xmmword ptr [rsp+0B00h+DestinationString.Buffer], xmm0
0x18001cbaa  test    rcx, rcx
0x18001cbad  jz      short loc_18001CBCE
0x18001cbaf  movzx   r9d, word ptr [r8]
0x18001cbb3  test    r9w, r9w
0x18001cbb7  jz      short loc_18001CBCE
0x18001cbb9  mov     [rax], r9w
0x18001cbbd  add     r8, 2
0x18001cbc1  add     rax, 2
0x18001cbc5  dec     rcx
0x18001cbc8  sub     rdx, 1
0x18001cbcc  jnz     short loc_18001CBAA
0x18001cbce  test    rdx, rdx
0x18001cbd1  lea     rcx, [rax-2]
0x18001cbd5  cmovnz  rcx, rax
0x18001cbd9  mov     [rcx], bx
0x18001cbdc  jnz     loc_18001D74F
0x18001cbe2  mov     r15, rbx
0x18001cbe5  xorps   xmm0, xmm0
0x18001cbe8  mov     [rsp+0B00h+KeyHandle], rbx
0x18001cbed  xor     eax, eax
0x18001cbef  mov     r9d, 7FFFFFFEh
0x18001cbf5  movups  xmmword ptr [rbp+0A00h+ObjectAttributes.ObjectName], xmm0
0x18001cbf9  mov     ecx, r9d
0x18001cbfc  mov     rdx, rdi
0x18001cbff  movups  xmmword ptr [rbp+0A00h+ObjectAttributes+1Ch], xmm0
0x18001cc03  lea     rax, [rbp+0A00h+SourceString]
0x18001cc0a  movups  xmmword ptr [rbp+0A00h+ObjectAttributes.Length], xmm0
0x18001cc0e  movups  xmmword ptr [rsp+0B00h+DestinationString.Buffer], xmm0
0x18001cc13  test    rcx, rcx
0x18001cc16  jz      short loc_18001CC37
0x18001cc18  movzx   r8d, word ptr [rsi]
0x18001cc1c  test    r8w, r8w
0x18001cc20  jz      short loc_18001CC37
0x18001cc22  mov     [rax], r8w
0x18001cc26  add     rsi, 2
0x18001cc2a  add     rax, 2
0x18001cc2e  dec     rcx
0x18001cc31  sub     rdx, 1
0x18001cc35  jnz     short loc_18001CC13
0x18001cc37  test    rdx, rdx
0x18001cc3a  lea     rcx, [rax-2]
0x18001cc3e  cmovnz  rcx, rax
0x18001cc42  mov     [rcx], bx
0x18001cc45  jz      loc_18001CD23
0x18001cc4b  mov     rcx, rdi
0x18001cc4e  lea     rax, [rbp+0A00h+SourceString]
0x18001cc55  cmp     word ptr [rax], 0
0x18001cc59  jz      short loc_18001CC65
0x18001cc5b  add     rax, 2
0x18001cc5f  sub     rcx, 1
0x18001cc63  jnz     short loc_18001CC55
0x18001cc65  mov     r8, rdi
0x18001cc68  sub     r8, rcx
0x18001cc6b  test    rcx, rcx
0x18001cc6e  cmovz   r8, rbx
0x18001cc72  jz      loc_18001CD23
0x18001cc78  sub     rdi, r8
0x18001cc7b  lea     rdx, aNlsExtendedloc; "\\Nls\\ExtendedLocale"
0x18001cc82  lea     r8, [rbp+r8*2+0A00h+SourceString]
0x18001cc8a  mov     rcx, r9
0x18001cc8d  jz      short loc_18001CCB2
0x18001cc8f  nop
0x18001cc90  test    rcx, rcx
0x18001cc93  jz      short loc_18001CCB2
0x18001cc95  movzx   eax, word ptr [rdx]
0x18001cc98  test    ax, ax
0x18001cc9b  jz      short loc_18001CCB2
0x18001cc9d  mov     [r8], ax
0x18001cca1  add     rdx, 2
0x18001cca5  add     r8, 2
0x18001cca9  dec     rcx
0x18001ccac  sub     rdi, 1
0x18001ccb0  jnz     short loc_18001CC90
0x18001ccb2  test    rdi, rdi
0x18001ccb5  lea     rcx, [r8-2]
0x18001ccb9  cmovnz  rcx, r8
0x18001ccbd  mov     [rcx], bx
0x18001ccc0  jz      short loc_18001CD23
0x18001ccc2  lea     rdx, [rbp+0A00h+SourceString]; SourceString
0x18001ccc9  lea     rcx, [rsp+0B00h+DestinationString.Buffer]; DestinationString
0x18001ccce  call    cs:__imp_RtlInitUnicodeString
0x18001ccd4  lea     rax, [rsp+0B00h+DestinationString.Buffer]
0x18001ccd9  mov     [rbp+0A00h+ObjectAttributes.Length], 30h ; '0'
0x18001cce0  xorps   xmm0, xmm0
0x18001cce3  mov     [rbp+0A00h+ObjectAttributes.ObjectName], rax
0x18001cce7  lea     r8, [rbp+0A00h+ObjectAttributes]; ObjectAttributes
0x18001cceb  mov     [rbp+0A00h+ObjectAttributes.RootDirectory], rbx
0x18001ccef  mov     edx, 20019h; DesiredAccess
0x18001ccf4  mov     [rbp+0A00h+ObjectAttributes.Attributes], 40h ; '@'
0x18001ccfb  lea     rcx, [rsp+0B00h+KeyHandle]; KeyHandle
0x18001cd00  movdqu  xmmword ptr [rbp+0A00h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001cd05  call    cs:__imp_NtOpenKey
0x18001cd0b  test    eax, eax
0x18001cd0d  jns     loc_18001D79E
0x18001cd13  mov     rdi, rbx
0x18001cd16  mov     [rsp+0B00h+KeyHandle], rbx
0x18001cd1b  test    eax, eax
0x18001cd1d  jns     loc_18001CEEE
0x18001cd23  test    r15, r15
0x18001cd26  jz      loc_18001D190
0x18001cd2c  xor     ecx, ecx
0x18001cd2e  call    CreateLocaleHashNode
0x18001cd33  mov     rdi, rax
0x18001cd36  test    rax, rax
0x18001cd39  jz      loc_18001D14F
0x18001cd3f  mov     esi, [r15]
0x18001cd42  add     rsi, r15
0x18001cd45  mov     r8d, [rsi+1Ch]
0x18001cd49  add     r8, r15
0x18001cd4c  mov     [rax+28h], r8
0x18001cd50  mov     [rax+38h], r8
0x18001cd54  mov     r9d, [rsi+38h]
0x18001cd58  add     r9, r15
0x18001cd5b  mov     r15d, 1
0x18001cd61  mov     [rax+30h], r9
0x18001cd65  mov     [rax+40h], r9
0x18001cd69  mov     eax, [rsi]
0x18001cd6b  mov     [rdi+48h], eax
0x18001cd6e  test    [r8+18h], r15b
0x18001cd72  jz      loc_18001D389
0x18001cd78  mov     dword ptr [rdi+4Ch], 20h ; ' '
0x18001cd7f  mov     [rdi+68h], rdi
0x18001cd83  mov     rdx, [rdi+28h]
0x18001cd87  mov     rcx, [rdi+30h]
0x18001cd8b  mov     eax, [rdx]
0x18001cd8d  inc     rax
0x18001cd90  lea     r8, [rcx+rax*2]
0x18001cd94  mov     rax, [rsp+0B00h+var_A88]
0x18001cd99  test    rax, rax
0x18001cd9c  mov     [rdi+10h], r8
0x18001cda0  cmovz   rax, r8
0x18001cda4  mov     [rdi+8], rax
0x18001cda8  mov     eax, [rdx+0B8h]
0x18001cdae  lea     rcx, [rcx+rax*2]
0x18001cdb2  add     rcx, 2
0x18001cdb6  mov     [rdi+18h], rcx
0x18001cdba  test    r14, r14
0x18001cdbd  jnz     loc_18001D2B6
0x18001cdc3  cmp     [rdx+8], r13w
0x18001cdc8  jz      loc_18001D7A8
0x18001cdce  test    r14, r14
0x18001cdd1  jnz     loc_18001D2C2
0x18001cdd7  mov     rax, [rdi+10h]
0x18001cddb  mov     [rdi+20h], rax
0x18001cddf  mov     eax, [rdi+4Ch]
0x18001cde2  test    ebx, ebx
0x18001cde4  jz      loc_18001D2F0
0x18001cdea  test    r14, r14
0x18001cded  mov     ecx, 8001h
0x18001cdf2  cmovz   r15d, ecx
0x18001cdf6  or      r15d, eax
0x18001cdf9  mov     [rdi+4Ch], r15d
0x18001cdfd  test    r14, r14
0x18001ce00  jz      loc_18001D2FF
0x18001ce06  movzx   eax, word ptr [r14+0Ah]
0x18001ce0b  mov     [rdi+50h], ax
0x18001ce0f  movzx   eax, word ptr [r14+7Ah]
0x18001ce14  mov     ecx, 0FFh
0x18001ce19  and     ax, cx
0x18001ce1c  mov     [rdi+52h], ax
  ... truncated ...
```
