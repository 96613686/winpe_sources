# PCPStorageProviderKey::GetProperty(KspProp,uchar *,ulong,ulong *,ulong)

- ea: `0x180037f94`
- end: `0x180038897`
- name: `?GetProperty@PCPStorageProviderKey@@QEAAJW4KspProp@@PEAEKPEAKK@Z`
- size: `2307`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180037250`
- `0x180037b20`
- `0x180061f70`

## callees

- `0x18000f240`
- `0x1800113f0`
- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x180026b90`
- `0x180036698`
- `0x180037f94`
- `0x1800389c0`
- `0x18004ff64`
- `0x180059b4c`
- `0x18007fe70`
- `0x180080620`
- `0x180080640`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18003878f`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18003878f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800380d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038188`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800381cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038213`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800380d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038188`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800381cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038213`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18003857e`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18003857e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800383fb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800383fb`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800387f3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180038815`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800387f3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180038815`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180038284`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180038284`

## string_xrefs

- `0x180038549`: `CreateFile failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PCPStorageProviderKey::GetProperty(
        __int64 a1,
        unsigned int a2,
        void *a3,
        unsigned int a4,
        unsigned int *a5,
        char a6)
{
  rsize_t v6; // r13
  unsigned int v10; // ebx
  int v11; // r15d
  int v12; // r12d
  __int64 v13; // rdx
  int *p_LastWriteTime; // rsi
  const char *v15; // r9
  __int64 result; // rax
  int v17; // eax
  unsigned int v18; // ebx
  __int64 v19; // rbx
  DWORD NamedSecurityInfoW; // eax
  void *v21; // rdx
  unsigned int v22; // r8d
  int Property; // eax
  unsigned int v24; // ebx
  int v25; // eax
  unsigned int v26; // edi
  DWORD FileAttributesW; // eax
  int *v28; // rax
  __int64 v29; // rbx
  int v30; // eax
  unsigned int v31; // edi
  char *FileWForAccessFailures; // rbx
  void *v33; // rdx
  unsigned int v34; // r8d
  const char *v35; // r9
  int v36; // eax
  unsigned int v37; // edi
  __int64 v38; // rax
  __int64 v39; // rbx
  int *v40; // rcx
  void *v41; // rcx
  DWORD SecurityDescriptorLength; // eax
  int *ppsidGroup; // [rsp+20h] [rbp-98h]
  int ppsidGroupa; // [rsp+20h] [rbp-98h]
  int ppsidGroupb; // [rsp+20h] [rbp-98h]
  PACL *ppDacl; // [rsp+28h] [rbp-90h]
  HLOCAL hMem; // [rsp+40h] [rbp-78h] BYREF
  int v48; // [rsp+48h] [rbp-70h] BYREF
  int v49; // [rsp+4Ch] [rbp-6Ch] BYREF
  int v50; // [rsp+50h] [rbp-68h] BYREF
  char *v51; // [rsp+58h] [rbp-60h] BYREF
  _BYTE v52[24]; // [rsp+60h] [rbp-58h] BYREF
  int v53; // [rsp+78h] [rbp-40h] BYREF
  int v54; // [rsp+7Ch] [rbp-3Ch] BYREF
  struct _FILETIME LastWriteTime; // [rsp+80h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  int v57; // [rsp+C0h] [rbp+8h] BYREF
  void *Destination; // [rsp+D0h] [rbp+18h]

  Destination = a3;
  v6 = a4;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v52, L"PCPStorageProviderKey::GetProperty", 1);
  try
  {
    v10 = 0;
    v57 = 0;
    v54 = 256;
    v11 = 0;
    v48 = 0;
    v12 = 0;
    v50 = 0;
    v49 = 0;
    hMem = 0;
    LastWriteTime = 0;
    v53 = 32772;
    v13 = *(_QWORD *)(a1 + 48);
    if ( !*(_DWORD *)(v13 + 8) )
    {
      ppsidGroupb = (int)a5;
      Property = ProviderGetProperty(*(_QWORD *)(a1 + 768), a2, a3);
      v24 = Property;
      if ( Property >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hMem);
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v52);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x80C,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
          (const char *)(unsigned int)Property,
          ppsidGroupb);
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hMem);
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v52);
        return v24;
      }
    }
    p_LastWriteTime = 0;
    if ( a2 <= 0x36 )
    {
      if ( a2 == 54 )
      {
        v10 = *(_DWORD *)(a1 + 656);
        p_LastWriteTime = *(int **)(a1 + 664);
        goto LABEL_13;
      }
      if ( a2 <= 0x18 )
      {
        switch ( a2 )
        {
          case 0x18u:
            if ( *(_QWORD *)(a1 + 80)
              && (*(_WORD *)(a1 + 88)
               || (int)PCPStorageProviderKey::GenerateKeyContainerName((PCPStorageProviderKey *)a1) >= 0) )
            {
              FileAttributesW = GetFileAttributesW((LPCWSTR)(a1 + 88));
              v10 = 4;
              if ( FileAttributesW != -1 )
                v50 = 8 * (FileAttributesW & 4);
            }
            else
            {
              if ( *(_BYTE *)(a1 + 652) )
                v12 = 32;
              v50 = v12;
              v10 = 4;
            }
            p_LastWriteTime = &v50;
            goto LABEL_13;
          case 0xEu:
            v10 = 4;
            p_LastWriteTime = (int *)(a1 + 752);
            goto LABEL_13;
          case 0x10u:
            v10 = 4;
            p_LastWriteTime = &v53;
            goto LABEL_13;
          case 0x11u:
            p_LastWriteTime = *(int **)(a1 + 712);
            v19 = -1;
            do
              ++v19;
            while ( *((_WORD *)p_LastWriteTime + v19) );
            v10 = 2 * v19 + 2;
            goto LABEL_13;
        }
        if ( a2 != 19 )
        {
          if ( a2 == 20 )
          {
            v10 = *(_DWORD *)(a1 + 648);
            p_LastWriteTime = *(int **)(a1 + 640);
LABEL_13:
            v57 = v10;
            goto LABEL_14;
          }
          if ( a2 == 22 )
          {
            v10 = 4;
            p_LastWriteTime = (int *)(a1 + 720);
            goto LABEL_13;
          }
LABEL_30:
          ppsidGroupa = (int)a5;
          v17 = ProviderGetProperty(*(_QWORD *)(a1 + 768), a2, Destination);
          v18 = v17;
          if ( v17 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x909,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
              (const char *)(unsigned int)v17,
              ppsidGroupa);
            wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hMem);
            KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v52);
            return v18;
          }
          else
          {
            KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v52);
            return 0;
          }
        }
        ppsidGroup = &v57;
        v10 = 4;
        v25 = ProviderGetProperty(*(_QWORD *)(a1 + 768), 2, &v49);
        v26 = v25;
        if ( v25 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x898,
            (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
            (const char *)(unsigned int)v25,
            (int)&v57);
          wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hMem);
          KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v52);
          return v26;
        }
LABEL_50:
        p_LastWriteTime = &v49;
        goto LABEL_13;
      }
      switch ( a2 )
      {
        case 0x19u:
          LODWORD(v51) = 0;
          v48 = 0;
          ppsidGroup = &v48;
          v10 = 4;
          v36 = ProviderGetProperty(*(_QWORD *)(a1 + 768), 53, &v51);
          v37 = v36;
          if ( v36 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x867,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
              (const char *)(unsigned int)v36,
              (int)&v48);
            wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hMem);
            KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v52);
            return v37;
          }
          if ( ((unsigned __int8)v51 & 1) != 0 )
            v11 = 2;
          v48 = v11;
          if ( ((unsigned __int8)v51 & 2) != 0 )
            v48 = v11 | 1;
          p_LastWriteTime = &v48;
          goto LABEL_13;
        case 0x1Au:
          FileWForAccessFailures = (char *)CreateFileWForAccessFailures((LPCWSTR)(a1 + 88), 0x80000000, 0, 0, 3u, 0x80u);
          v51 = FileWForAccessFailures;
          if ( !wil::details::in1diag3::Log_GetLastErrorIfMsg(
                  retaddr,
                  (void *)0x8C6,
                  (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                  (const char *)((unsigned __int64)(FileWForAccessFailures - 1) > 0xFFFFFFFFFFFFFFFDuLL),
                  (bool)"CreateFile failed",
                  (const char *)ppDacl) )
          {
            if ( GetFileTime(FileWForAccessFailures, 0, 0, &LastWriteTime) )
            {
              v57 = 8;
              p_LastWriteTime = (int *)&LastWriteTime;
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v51);
              v10 = v57;
              goto LABEL_14;
            }
            wil::details::in1diag3::_Log_GetLastError(retaddr, v33, v34, v35);
          }
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v51);
          wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hMem);
          KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v52);
          return 2148073489LL;
        case 0x1Bu:
          ppsidGroup = &v57;
          v10 = 4;
          v30 = ProviderGetProperty(*(_QWORD *)(a1 + 768), 5, &v49);
          v31 = v30;
          if ( v30 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x8A2,
              (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
              (const char *)(unsigned int)v30,
              (int)&v57);
            wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hMem);
            KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v52);
            return v31;
          }
          goto LABEL_50;
        case 0x1Du:
          v10 = 4;
          p_LastWriteTime = &v54;
          goto LABEL_13;
      }
      if ( a2 != 30 )
        goto LABEL_30;
      v28 = *(int **)(a1 + 80);
      if ( v28 )
      {
        v29 = -1;
        do
          ++v29;
        while ( *((_WORD *)v28 + v29) );
LABEL_70:
        v10 = 2 * v29 + 2;
        p_LastWriteTime = v28;
        goto LABEL_13;
      }
LABEL_14:
      *a5 = v10;
      if ( v10 )
      {
        if ( !(_DWORD)v6 || !Destination )
        {
          if ( !hMem )
            goto LABEL_20;
          goto LABEL_19;
        }
        if ( (unsigned int)v6 >= v10 )
        {
          memcpy_s_1(Destination, v6, p_LastWriteTime, v10);
          if ( !hMem )
          {
LABEL_20:
            KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v52);
            return 0;
          }
LABEL_19:
          LocalFree(hMem);
          goto LABEL_20;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x918,
          (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
          (const char *)0x80090028LL,
          (int)ppsidGroup);
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hMem);
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v52);
        return 2148073512LL;
      }
      else
      {
        KspDebugProvider::TraceLoggingInfo("Recognized the property, but it was not set.");
        if ( hMem )
          LocalFree(hMem);
        KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v52);
        return 2148073489LL;
      }
    }
    switch ( a2 )
    {
      case 'B':
        p_LastWriteTime = (int *)(a1 + 768);
        goto LABEL_115;
      case 'M':
        p_LastWriteTime = (int *)(a1 + 760);
        goto LABEL_115;
      case 'Y':
        p_LastWriteTime = (int *)(a1 + 48);
        goto LABEL_115;
    }
    if ( a2 != 91 )
    {
      if ( a2 == 92 )
      {
        if ( *(_DWORD *)(a1 + 632) )
        {
          v40 = *(int **)(a1 + 624);
          if ( v40 )
          {
            v10 = *(_DWORD *)(a1 + 632);
            v57 = v10;
            p_LastWriteTime = v40;
          }
        }
        goto LABEL_14;
      }
      if ( a2 != 93 )
      {
        if ( a2 == 94 )
        {
          v28 = *(int **)(a1 + 744);
          if ( v28 )
          {
            v29 = -1;
            do
              ++v29;
            while ( *((_WORD *)v28 + v29) );
            goto LABEL_70;
          }
          v38 = *(_QWORD *)(v13 + 96);
          if ( v38 )
          {
            v39 = -1;
            do
              ++v39;
            while ( *(_WORD *)(v38 + 2 * v39) );
            v10 = 2 * v39 + 2;
            v57 = v10;
            p_LastWriteTime = *(int **)(v13 + 96);
          }
          goto LABEL_14;
        }
        if ( a2 != 97 )
        {
          if ( a2 == 101 )
          {
            v10 = *(_DWORD *)(a1 + 696);
            p_LastWriteTime = *(int **)(a1 + 688);
            goto LABEL_13;
          }
          goto LABEL_30;
        }
        p_LastWriteTime = (int *)(a1 + 728);
LABEL_115:
        v10 = 8;
        goto LABEL_13;
      }
      if ( !*(_QWORD *)(a1 + 80) )
        goto LABEL_14;
      p_LastWriteTime = (int *)(a1 + 88);
      if ( *(_WORD *)(a1 + 88) || (int)PCPStorageProviderKey::GenerateKeyContainerName((PCPStorageProviderKey *)a1) >= 0 )
      {
        v10 = 2 * wcsnlen((const wchar_t *)(a1 + 88), 0x104u) + 2;
        goto LABEL_13;
      }
LABEL_101:
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hMem);
      KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v52);
      return 2148073489LL;
    }
    if ( *(_BYTE *)(a1 + 708) )
    {
      hMem = 0;
      NamedSecurityInfoW = GetNamedSecurityInfoW((LPCWSTR)(a1 + 88), SE_FILE_OBJECT, a6 & 0xF, 0, 0, 0, 0, &hMem);
      if ( NamedSecurityInfoW )
      {
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          v21,
          v22,
          (const char *)NamedSecurityInfoW,
          (unsigned int)ppsidGroup);
        goto LABEL_101;
      }
      if ( !hMem )
        goto LABEL_101;
      SecurityDescriptorLength = GetSecurityDescriptorLength(hMem);
      p_LastWriteTime = (int *)hMem;
    }
    else
    {
      v41 = *(void **)(a1 + 672);
      if ( !v41 )
        goto LABEL_14;
      SecurityDescriptorLength = GetSecurityDescriptorLength(v41);
      p_LastWriteTime = *(int **)(a1 + 672);
    }
    v10 = SecurityDescriptorLength;
    goto LABEL_13;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x91D,
                           (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\pcpkspclass.cpp",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x180037f94  mov     rax, rsp
0x180037f97  mov     [rax+10h], rbx
0x180037f9b  mov     [rax+20h], rsi
0x180037f9f  mov     [rax+18h], r8
0x180037fa3  push    rdi
0x180037fa4  push    r12
0x180037fa6  push    r13
0x180037fa8  push    r14
0x180037faa  push    r15
0x180037fac  sub     rsp, 90h
0x180037fb3  mov     r13d, r9d
0x180037fb6  mov     rsi, r8
0x180037fb9  mov     r14d, edx
0x180037fbc  mov     rdi, rcx
0x180037fbf  mov     r8b, 1; bool
0x180037fc2  lea     rdx, aPcpstorageprov_13; "PCPStorageProviderKey::GetProperty"
0x180037fc9  lea     rcx, [rax-58h]; this
0x180037fcd  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x180037fd2  nop
0x180037fd3  xor     r9d, r9d
0x180037fd6  mov     ebx, r9d
0x180037fd9  mov     [rsp+0B8h+arg_0], ebx
0x180037fe0  mov     [rsp+0B8h+var_3C], 100h
0x180037fe8  mov     r15d, r9d
0x180037feb  mov     [rsp+0B8h+var_70], r9d
0x180037ff0  mov     r12d, r9d
0x180037ff3  mov     [rsp+0B8h+var_68], r9d
0x180037ff8  mov     [rsp+0B8h+var_6C], r9d
0x180037ffd  mov     [rsp+0B8h+hMem], r9
0x180038002  mov     qword ptr [rsp+0B8h+LastWriteTime.dwLowDateTime], r9
0x18003800a  mov     [rsp+0B8h+var_40], 8004h
0x180038012  mov     rdx, [rdi+30h]
0x180038016  cmp     [rdx+8], r9d
0x18003801a  jz      loc_1800382CD
0x180038020  mov     esi, r9d
0x180038023  cmp     r14d, 36h ; '6'
0x180038027  ja      loc_1800380F5
0x18003802d  jz      loc_18003868E
0x180038033  cmp     r14d, 18h
0x180038037  ja      loc_18003843E
0x18003803d  jz      loc_1800383DB
0x180038043  mov     eax, r14d
0x180038046  sub     eax, 0Eh
0x180038049  jz      loc_1800383CA
0x18003804f  lea     ecx, [r9+2]
0x180038053  sub     eax, ecx
0x180038055  jz      loc_1800383BB
0x18003805b  sub     eax, 1
0x18003805e  jz      loc_18003822E
0x180038064  sub     eax, ecx
0x180038066  jz      loc_18003834A
0x18003806c  sub     eax, 1
0x18003806f  jnz     loc_1800381A3
0x180038075  mov     ebx, [rdi+288h]
0x18003807b  mov     rsi, [rdi+280h]
0x180038082  mov     [rsp+0B8h+arg_0], ebx
0x180038089  mov     rax, [rsp+0B8h+arg_20]
0x180038091  mov     [rax], ebx
0x180038093  test    ebx, ebx
0x180038095  jz      loc_1800381B8
0x18003809b  test    r13d, r13d
0x18003809e  jz      loc_180038209
0x1800380a4  mov     rcx, [rsp+0B8h+Destination]; Destination
0x1800380ac  test    rcx, rcx
0x1800380af  jz      loc_180038209
0x1800380b5  cmp     r13d, ebx
0x1800380b8  jb      loc_18003884D
0x1800380be  mov     r9d, ebx; SourceSize
0x1800380c1  mov     rdx, r13; DestinationSize
0x1800380c4  mov     r8, rsi; Source
0x1800380c7  call    memcpy_s_1
0x1800380cc  nop
0x1800380cd  mov     rcx, [rsp+0B8h+hMem]; hMem
0x1800380d2  test    rcx, rcx
0x1800380d5  jz      short loc_1800380E4
0x1800380d7  call    cs:__imp_LocalFree
0x1800380de  nop     dword ptr [rax+rax+00h]
0x1800380e3  nop
0x1800380e4  lea     rcx, [rsp+0B8h+var_58]; this
0x1800380e9  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800380ee  xor     eax, eax
0x1800380f0  jmp     loc_1800381EB
0x1800380f5  mov     eax, r14d
0x1800380f8  sub     eax, 42h ; 'B'
0x1800380fb  jz      loc_18003883C
0x180038101  sub     eax, 0Bh
0x180038104  jz      loc_180038833
0x18003810a  sub     eax, 0Ch
0x18003810d  jz      loc_18003882D
0x180038113  sub     eax, 2
0x180038116  jz      loc_1800387D6
0x18003811c  sub     eax, 1
0x18003811f  jz      loc_1800387A7
0x180038125  sub     eax, 1
0x180038128  jz      loc_180038748
0x18003812e  sub     eax, 1
0x180038131  jz      loc_1800386F7
0x180038137  sub     eax, 3
0x18003813a  jz      loc_1800386EB
0x180038140  mov     ebx, 4
0x180038145  cmp     eax, ebx
0x180038147  jz      loc_1800386D9
0x18003814d  mov     rax, [rsp+0B8h+arg_20]
0x180038155  mov     [rsp+0B8h+ppsidGroup], rax; int
0x18003815a  mov     r9d, r13d
0x18003815d  mov     r8, [rsp+0B8h+Destination]
0x180038165  mov     edx, r14d
0x180038168  mov     rcx, [rdi+300h]
0x18003816f  call    ?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z; ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)
0x180038174  mov     ebx, eax
0x180038176  test    eax, eax
0x180038178  js      loc_1800386A0
0x18003817e  mov     rcx, [rsp+0B8h+hMem]; hMem
0x180038183  test    rcx, rcx
0x180038186  jz      short loc_180038195
0x180038188  call    cs:__imp_LocalFree
0x18003818f  nop     dword ptr [rax+rax+00h]
0x180038194  nop
0x180038195  lea     rcx, [rsp+0B8h+var_58]; this
0x18003819a  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18003819f  xor     eax, eax
0x1800381a1  jmp     short loc_1800381EB
0x1800381a3  cmp     eax, ecx
0x1800381a5  jnz     short loc_18003814D
0x1800381a7  mov     ebx, 4
0x1800381ac  lea     rsi, [rdi+2D0h]
0x1800381b3  jmp     loc_180038082
0x1800381b8  lea     rcx, aRecognizedTheP; "Recognized the property, but it was not"...
0x1800381bf  call    ?TraceLoggingInfo@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingInfo(char const *,...)
0x1800381c4  nop
0x1800381c5  mov     rcx, [rsp+0B8h+hMem]; hMem
0x1800381ca  test    rcx, rcx
0x1800381cd  jz      short loc_1800381DC
0x1800381cf  call    cs:__imp_LocalFree
0x1800381d6  nop     dword ptr [rax+rax+00h]
0x1800381db  nop
0x1800381dc  lea     rcx, [rsp+0B8h+var_58]; this
0x1800381e1  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800381e6  mov     eax, 80090011h
0x1800381eb  lea     r11, [rsp+0B8h+var_28]
0x1800381f3  mov     rbx, [r11+38h]
0x1800381f7  mov     rsi, [r11+48h]
0x1800381fb  mov     rsp, r11
0x1800381fe  pop     r15
0x180038200  pop     r14
0x180038202  pop     r13
0x180038204  pop     r12
0x180038206  pop     rdi
0x180038207  retn
0x180038209  mov     rcx, [rsp+0B8h+hMem]; hMem
0x18003820e  test    rcx, rcx
0x180038211  jz      short loc_180038220
0x180038213  call    cs:__imp_LocalFree
0x18003821a  nop     dword ptr [rax+rax+00h]
0x18003821f  nop
0x180038220  lea     rcx, [rsp+0B8h+var_58]; this
0x180038225  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18003822a  xor     eax, eax
0x18003822c  jmp     short loc_1800381EB
0x18003822e  mov     rsi, [rdi+2C8h]
0x180038235  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180038239  inc     rbx
0x18003823c  cmp     [rsi+rbx*2], r9w
0x180038241  jnz     short loc_180038239
0x180038243  lea     ebx, ds:2[rbx*2]
0x18003824a  jmp     loc_180038082
0x18003824f  mov     [rsp+0B8h+hMem], r9
0x180038254  mov     r8d, [rsp+0B8h+arg_28]
0x18003825c  and     r8d, 0Fh; SecurityInfo
0x180038260  lea     rcx, [rdi+58h]; pObjectName
0x180038264  lea     rax, [rsp+0B8h+hMem]
0x180038269  mov     [rsp+0B8h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18003826e  mov     [rsp+0B8h+ppSacl], r9; ppSacl
0x180038273  mov     [rsp+0B8h+ppDacl], r9; ppDacl
0x180038278  mov     [rsp+0B8h+ppsidGroup], r9; unsigned int
0x18003827d  xor     r9d, r9d; ppsidOwner
0x180038280  lea     edx, [r9+1]; ObjectType
0x180038284  call    cs:__imp_GetNamedSecurityInfoW
0x18003828b  nop     dword ptr [rax+rax+00h]
0x180038290  mov     rcx, [rsp+0B8h]; this
0x180038298  test    eax, eax
0x18003829a  jnz     loc_180038808
0x1800382a0  mov     rcx, [rsp+0B8h+hMem]; pSecurityDescriptor
0x1800382a5  test    rcx, rcx
0x1800382a8  jnz     loc_180038815
0x1800382ae  lea     rcx, [rsp+0B8h+hMem]
0x1800382b3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800382b8  nop
0x1800382b9  lea     rcx, [rsp+0B8h+var_58]; this
0x1800382be  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800382c3  mov     eax, 80090011h
0x1800382c8  jmp     loc_1800381EB
0x1800382cd  mov     rax, [rsp+0B8h+arg_20]
0x1800382d5  mov     [rsp+0B8h+ppsidGroup], rax; int
0x1800382da  mov     r9d, r13d
0x1800382dd  mov     r8, rsi
0x1800382e0  mov     edx, r14d
0x1800382e3  mov     rcx, [rdi+300h]
0x1800382ea  call    ?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z; ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)
0x1800382ef  mov     ebx, eax
0x1800382f1  test    eax, eax
0x1800382f3  jns     short loc_18003832E
0x1800382f5  mov     rcx, [rsp+0B8h]; this
0x1800382fd  mov     r9d, eax; char *
0x180038300  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180038307  mov     edx, 80Ch; void *
0x18003830c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038311  nop
0x180038312  lea     rcx, [rsp+0B8h+hMem]
0x180038317  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003831c  nop
0x18003831d  lea     rcx, [rsp+0B8h+var_58]; this
0x180038322  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180038327  mov     eax, ebx
0x180038329  jmp     loc_1800381EB
0x18003832e  lea     rcx, [rsp+0B8h+hMem]
0x180038333  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180038338  nop
0x180038339  lea     rcx, [rsp+0B8h+var_58]; this
0x18003833e  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180038343  xor     eax, eax
0x180038345  jmp     loc_1800381EB
0x18003834a  lea     rax, [rsp+0B8h+arg_0]
0x180038352  mov     [rsp+0B8h+ppsidGroup], rax; int
0x180038357  mov     ebx, 4
0x18003835c  mov     r9d, ebx
0x18003835f  lea     r8, [rsp+0B8h+var_6C]
0x180038364  mov     edx, ecx
0x180038366  mov     rcx, [rdi+300h]
0x18003836d  call    ?ProviderGetProperty@@YAJPEAXW4KspProp@@PEAEKPEAK@Z; ProviderGetProperty(void *,KspProp,uchar *,ulong,ulong *)
0x180038372  mov     edi, eax
0x180038374  test    eax, eax
0x180038376  jns     short loc_1800383B1
0x180038378  mov     rcx, [rsp+0B8h]; this
0x180038380  mov     r9d, eax; char *
0x180038383  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18003838a  mov     edx, 898h; void *
0x18003838f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038394  nop
0x180038395  lea     rcx, [rsp+0B8h+hMem]
0x18003839a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18003839f  nop
0x1800383a0  lea     rcx, [rsp+0B8h+var_58]; this
0x1800383a5  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x1800383aa  mov     eax, edi
0x1800383ac  jmp     loc_1800381EB
0x1800383b1  lea     rsi, [rsp+0B8h+var_6C]
0x1800383b6  jmp     loc_180038082
0x1800383bb  mov     ebx, 4
0x1800383c0  lea     rsi, [rsp+0B8h+var_40]
0x1800383c5  jmp     loc_180038082
0x1800383ca  mov     ebx, 4
0x1800383cf  lea     rsi, [rdi+2F0h]
0x1800383d6  jmp     loc_180038082
0x1800383db  cmp     [rdi+50h], r9
0x1800383df  jz      short loc_18003841C
0x1800383e1  cmp     [rdi+58h], r9w
0x1800383e6  jnz     short loc_1800383F7
0x1800383e8  mov     rcx, rdi; this
0x1800383eb  call    ?GenerateKeyContainerName@PCPStorageProviderKey@@IEAAJXZ; PCPStorageProviderKey::GenerateKeyContainerName(void)
0x1800383f0  xor     r9d, r9d
0x1800383f3  test    eax, eax
0x1800383f5  js      short loc_18003841C
0x1800383f7  lea     rcx, [rdi+58h]; lpFileName
0x1800383fb  call    cs:__imp_GetFileAttributesW
0x180038402  nop     dword ptr [rax+rax+00h]
0x180038407  mov     ebx, 4
0x18003840c  cmp     eax, 0FFFFFFFFh
0x18003840f  jz      short loc_180038434
0x180038411  and     eax, ebx
0x180038413  shl     eax, 3
0x180038416  mov     [rsp+0B8h+var_68], eax
0x18003841a  jmp     short loc_180038434
0x18003841c  mov     eax, 20h ; ' '
0x180038421  cmp     [rdi+28Ch], r9b
0x180038428  cmovnz  r12d, eax
0x18003842c  mov     [rsp+0B8h+var_68], r12d
0x180038431  lea     ebx, [rax-1Ch]
0x180038434  lea     rsi, [rsp+0B8h+var_68]
0x180038439  jmp     loc_180038082
0x18003843e  mov     eax, r14d
0x180038441  sub     eax, 19h
0x180038444  jz      loc_1800385C9
0x18003844a  sub     eax, 1
0x18003844d  jz      loc_18003850B
0x180038453  sub     eax, 1
0x180038456  jz      short loc_18003849F
0x180038458  sub     eax, 2
0x18003845b  jz      short loc_180038490
0x18003845d  cmp     eax, 1
0x180038460  jnz     loc_18003814D
0x180038466  mov     rax, [rdi+50h]
0x18003846a  test    rax, rax
0x18003846d  jz      loc_180038089
0x180038473  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180038477  inc     rbx
0x18003847a  cmp     [rax+rbx*2], r9w
0x18003847f  jnz     short loc_180038477
0x180038481  lea     ebx, ds:2[rbx*2]
0x180038488  mov     rsi, rax
  ... truncated ...
```
