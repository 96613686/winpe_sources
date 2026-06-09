# JoinStatusStorage::ReadDeviceKey(struct_join_status *,RegistryPath &,int)

- ea: `0x18001a130`
- end: `0x18001b470`
- name: `?ReadDeviceKey@JoinStatusStorage@@CAJPEAUstruct_join_status@@AEAVRegistryPath@@H@Z`
- size: `4928`
- prototype: `static int(struct struct_join_status *, struct RegistryPath *, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18001f17c`

## callees

- `0x18001a100`
- `0x18001a130`
- `0x1800215e4`
- `0x18002a0b0`
- `0x18002f2d0`
- `0x18003582c`
- `0x180036000`
- `0x18004a650`
- `0x18004aa08`
- `0x18004ccd8`
- `0x18004d79c`
- `0x180052938`
- `0x1800ab8ec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a221`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a447`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a669`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001aa3f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ac20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ae86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b136`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a221`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a447`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a669`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001aa3f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ac20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ae86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b136`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a213`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a439`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a65b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001aa31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ac12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ae78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b128`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a213`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a439`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a65b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001aa31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ac12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ae78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b128`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a1b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a1b5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a293`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a34e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a4b5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a570`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a6d7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a78e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001aaa8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ab5e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ac89`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ad88`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001aef0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001afa6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b19f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b255`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a293`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a34e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a4b5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a570`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a6d7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a78e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001aaa8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ab5e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ac89`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ad88`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001aef0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001afa6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b19f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b255`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a161`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a1f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a161`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a1f4`

## string_xrefs

- `0x18001a2ae`: `RegReadStringValue`
- `0x18001a2e3`: `RegReadStringValue`
- `0x18001a385`: `RegReadStringValue`
- `0x18001a3a7`: `RegReadStringValue`
- `0x18001a4d0`: `RegReadStringValue`
- `0x18001a505`: `RegReadStringValue`
- `0x18001a5a7`: `RegReadStringValue`
- `0x18001a5c9`: `RegReadStringValue`
- `0x18001a6f2`: `RegReadStringValue`
- `0x18001a725`: `RegReadStringValue`
- `0x18001a7c5`: `RegReadStringValue`
- `0x18001a7e9`: `RegReadStringValue`
- `0x18001aac3`: `RegReadStringValue`
- `0x18001aaf6`: `RegReadStringValue`
- `0x18001ab95`: `RegReadStringValue`
- `0x18001abb9`: `RegReadStringValue`
- `0x18001aca4`: `RegReadStringValue`
- `0x18001ad1e`: `RegReadStringValue`
- `0x18001adbf`: `RegReadStringValue`
- `0x18001ade1`: `RegReadStringValue`
- `0x18001af0b`: `RegReadStringValue`
- `0x18001af3e`: `RegReadStringValue`
- `0x18001afdd`: `RegReadStringValue`
- `0x18001b001`: `RegReadStringValue`
- `0x18001b1ba`: `RegReadStringValue`
- `0x18001b1ed`: `RegReadStringValue`
- `0x18001b28c`: `RegReadStringValue`
- `0x18001b2b0`: `RegReadStringValue`
- `0x18001a2ea`: `%s: The registry key value "%s@%s" is not of one of the specified types (flags = 0x%08x). Using default value NULL.`
- `0x18001a50c`: `%s: The registry key value "%s@%s" is not of one of the specified types (flags = 0x%08x). Using default value NULL.`
- `0x18001a72c`: `%s: The registry key value "%s@%s" is not of one of the specified types (flags = 0x%08x). Using default value NULL.`
- `0x18001aafd`: `%s: The registry key value "%s@%s" is not of one of the specified types (flags = 0x%08x). Using default value NULL.`
- `0x18001ad25`: `%s: The registry key value "%s@%s" is not of one of the specified types (flags = 0x%08x). Using default value NULL.`
- `0x18001af45`: `%s: The registry key value "%s@%s" is not of one of the specified types (flags = 0x%08x). Using default value NULL.`
- `0x18001b1f4`: `%s: The registry key value "%s@%s" is not of one of the specified types (flags = 0x%08x). Using default value NULL.`
- `0x18001a3f4`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x18001a616`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x18001a869`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x18001a8d1`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x18001a95f`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x18001a9ed`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x18001acc7`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x18001ae32`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x18001b050`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x18001b0e4`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x18001b2ff`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x18001b395`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x18001b3d1`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x18001a8ca`: `RegistryPath::ReadDwordValue`
- `0x18001a8e3`: `RegistryPath::ReadDwordValue`
- `0x18001a958`: `RegistryPath::ReadDwordValue`
- `0x18001a971`: `RegistryPath::ReadDwordValue`
- `0x18001a9e6`: `RegistryPath::ReadDwordValue`
- `0x18001a9ff`: `RegistryPath::ReadDwordValue`
- `0x18001b0dd`: `RegistryPath::ReadDwordValue`
- `0x18001b0f6`: `RegistryPath::ReadDwordValue`
- `0x18001a3ed`: `RegistryPath::ReadStringValue`
- `0x18001a406`: `RegistryPath::ReadStringValue`
- `0x18001a60f`: `RegistryPath::ReadStringValue`
- `0x18001a628`: `RegistryPath::ReadStringValue`
- `0x18001a862`: `RegistryPath::ReadStringValue`
- `0x18001a87b`: `RegistryPath::ReadStringValue`
- `0x18001acc0`: `RegistryPath::ReadStringValue`
- `0x18001acd9`: `RegistryPath::ReadStringValue`
- `0x18001ae2b`: `RegistryPath::ReadStringValue`
- `0x18001ae44`: `RegistryPath::ReadStringValue`
- `0x18001b049`: `RegistryPath::ReadStringValue`
- `0x18001b062`: `RegistryPath::ReadStringValue`
- `0x18001b2f8`: `RegistryPath::ReadStringValue`
- `0x18001b311`: `RegistryPath::ReadStringValue`
- `0x18001a40d`: `JoinStatusStorage::ReadDeviceKey`
- `0x18001a62f`: `JoinStatusStorage::ReadDeviceKey`
- `0x18001a882`: `JoinStatusStorage::ReadDeviceKey`
- `0x18001a8ea`: `JoinStatusStorage::ReadDeviceKey`
- `0x18001a978`: `JoinStatusStorage::ReadDeviceKey`
- `0x18001aa06`: `JoinStatusStorage::ReadDeviceKey`
- `0x18001ace0`: `JoinStatusStorage::ReadDeviceKey`
- `0x18001ae4b`: `JoinStatusStorage::ReadDeviceKey`
- `0x18001b069`: `JoinStatusStorage::ReadDeviceKey`
- `0x18001b0fd`: `JoinStatusStorage::ReadDeviceKey`
- `0x18001b318`: `JoinStatusStorage::ReadDeviceKey`
- `0x18001b3ae`: `JoinStatusStorage::ReadDeviceKey`
- `0x18001b3ed`: `JoinStatusStorage::ReadDeviceKey`
- `0x18001b44b`: `JoinStatusStorage::ReadDeviceKey`
- `0x18001b452`: `%s: Failed to read one or more join status entries from the registry.`
- `0x18001b38e`: `RegistryPath::ReadQwordValue`
- `0x18001b3a7`: `RegistryPath::ReadQwordValue`
- `0x18001a2b5`: `%s: The registry key value "%s@%s" does not exist. Using default value NULL. Error code: 0x%08x.`
- `0x18001a4d7`: `%s: The registry key value "%s@%s" does not exist. Using default value NULL. Error code: 0x%08x.`
- `0x18001a6f9`: `%s: The registry key value "%s@%s" does not exist. Using default value NULL. Error code: 0x%08x.`
- `0x18001aaca`: `%s: The registry key value "%s@%s" does not exist. Using default value NULL. Error code: 0x%08x.`
- `0x18001acab`: `%s: The registry key value "%s@%s" does not exist. Using default value NULL. Error code: 0x%08x.`
- `0x18001af12`: `%s: The registry key value "%s@%s" does not exist. Using default value NULL. Error code: 0x%08x.`
- `0x18001b1c1`: `%s: The registry key value "%s@%s" does not exist. Using default value NULL. Error code: 0x%08x.`
- `0x18001a1d6`: `RegistryPath::OpenSubKey`
- `0x18001b3ca`: `RegistryPath::OpenSubKey`
- `0x18001b3e6`: `RegistryPath::OpenSubKey`
- `0x18001a38c`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x18001a5ae`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x18001a7cc`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x18001ab9c`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x18001adc6`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x18001afe4`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x18001b293`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x18001a1c5`: `RegOpenKeyExW`
- `0x18001a1e0`: `%s: Failed to open registry key "%s". Error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall JoinStatusStorage::ReadDeviceKey(struct struct_join_status *a1, struct RegistryPath *a2, int a3)
{
  HKEY v4; // rcx
  HKEY *v5; // rsi
  HKEY v7; // rcx
  _WORD *v8; // rdx
  LSTATUS v9; // eax
  unsigned int v10; // r12d
  void *v11; // rbx
  void **v12; // r14
  HANDLE ProcessHeap; // rax
  unsigned int QwordValue; // r12d
  const unsigned __int16 *v15; // r15
  HKEY v16; // rax
  LSTATUS ValueW; // eax
  const unsigned __int16 *v18; // rdx
  unsigned int StringValue; // ebx
  void *v20; // rax
  unsigned __int16 *RegValueName; // rax
  const WCHAR *v22; // rax
  HKEY v23; // r10
  void *v24; // rbx
  void **v25; // r15
  HANDLE v26; // rax
  const unsigned __int16 *v27; // r14
  HKEY v28; // rax
  LSTATUS v29; // eax
  const unsigned __int16 *v30; // rdx
  void *v31; // rax
  unsigned __int16 *v32; // rax
  const WCHAR *v33; // rax
  HKEY v34; // r10
  void *v35; // rbx
  void **v36; // r15
  HANDLE v37; // rax
  const unsigned __int16 *v38; // r14
  HKEY v39; // rax
  LSTATUS v40; // eax
  const unsigned __int16 *v41; // rdx
  void *v42; // rax
  unsigned __int16 *v43; // rax
  const WCHAR *v44; // rax
  HKEY v45; // r10
  int v46; // r14d
  const unsigned __int16 *v47; // r9
  HKEY v48; // rcx
  unsigned int *v49; // r8
  const unsigned __int16 *v50; // rdx
  HKEY v51; // r10
  const unsigned __int16 *v52; // r9
  HKEY v53; // rcx
  unsigned int *v54; // r8
  const unsigned __int16 *v55; // rdx
  HKEY v56; // r10
  const unsigned __int16 *v57; // r9
  HKEY v58; // rcx
  unsigned int *v59; // r8
  const unsigned __int16 *v60; // rdx
  HKEY v61; // r10
  void **v62; // r15
  void *v63; // rbx
  HANDLE v64; // rax
  const unsigned __int16 *v65; // rsi
  HKEY v66; // r14
  LSTATUS v67; // eax
  const unsigned __int16 *v68; // rdx
  void *v69; // rax
  unsigned __int16 *v70; // rax
  const WCHAR *v71; // rax
  HKEY v72; // r10
  int v73; // r15d
  void **v74; // r14
  void *v75; // rbx
  HANDLE v76; // rax
  const unsigned __int16 *v77; // rsi
  HKEY v78; // r15
  LSTATUS v79; // eax
  const unsigned __int16 *v80; // rdx
  void *v81; // rax
  unsigned __int16 *v82; // rax
  const WCHAR *v83; // rax
  HKEY v84; // r10
  void **v85; // r14
  void *v86; // rbx
  HANDLE v87; // rax
  const unsigned __int16 *v88; // rsi
  HKEY v89; // r15
  LSTATUS v90; // eax
  const unsigned __int16 *v91; // rdx
  void *v92; // rax
  unsigned __int16 *v93; // rax
  const WCHAR *v94; // rax
  HKEY v95; // r10
  const unsigned __int16 *v96; // r9
  HKEY v97; // rcx
  unsigned int *v98; // r8
  const unsigned __int16 *v99; // rdx
  HKEY v100; // r10
  void **v101; // r14
  void *v102; // rbx
  HANDLE v103; // rax
  const unsigned __int16 *v104; // rsi
  HKEY v105; // r15
  LSTATUS v106; // eax
  const unsigned __int16 *v107; // rdx
  void *v108; // rax
  unsigned __int16 *v109; // rax
  const WCHAR *v110; // rax
  HKEY v111; // r10
  const unsigned __int16 *v112; // r8
  const unsigned __int16 *v113; // r9
  HKEY v114; // rcx
  __int64 *v115; // r10
  const unsigned __int16 *v116; // rdx
  PHKEY phkResult; // [rsp+20h] [rbp-58h]
  PHKEY phkResulta; // [rsp+20h] [rbp-58h]
  PVOID pvData; // [rsp+28h] [rbp-50h]
  DWORD pcbData; // [rsp+90h] [rbp+18h] BYREF
  DWORD pdwType; // [rsp+98h] [rbp+20h] BYREF
  int v123; // [rsp+A0h] [rbp+28h]
  HKEY hkey; // [rsp+A8h] [rbp+30h]

  v123 = a3;
  v4 = (HKEY)*((_QWORD *)a2 + 5);
  v5 = (HKEY *)((char *)a2 + 40);
  if ( v4 )
    RegCloseKey(v4);
  *v5 = 0;
  v7 = (HKEY)*((_QWORD *)a2 + 4);
  if ( !v7 || (v8 = *(_WORD **)a2) == 0 || !*v8 )
  {
    Logger::TraceError(
      L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
      L"RegistryPath::OpenSubKey");
    v10 = 87;
LABEL_230:
    StringValue = v10;
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadDeviceKey",
      L"RegistryPath::OpenSubKey",
      v10);
    goto LABEL_231;
  }
  v9 = RegOpenKeyExW(v7, &v8[*((_QWORD *)a2 + 3)], 0, 1u, v5);
  v10 = v9;
  if ( v9 )
  {
    Logger::WriteRegistryFailureEvent(v9, L"RegOpenKeyExW", *(const unsigned __int16 **)a2);
    Logger::TraceError(
      L"%s: Failed to open registry key \"%s\". Error code: 0x%08x.",
      L"RegistryPath::OpenSubKey",
      *(_QWORD *)a2,
      v10);
    if ( *v5 )
    {
      RegCloseKey(*v5);
      *v5 = 0;
    }
  }
  if ( v10 )
    goto LABEL_230;
  v11 = (void *)*((_QWORD *)a1 + 1);
  v12 = (void **)((char *)a1 + 8);
  if ( v11 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v11);
  }
  *v12 = 0;
  QwordValue = 87;
  if ( *((_QWORD *)a2 + 4) )
  {
    v15 = *(const unsigned __int16 **)a2;
    if ( *(_QWORD *)a2 )
    {
      if ( *v15 )
      {
        v16 = *v5;
        hkey = v16;
        if ( !v16 )
        {
          v22 = RegistryPath::SubPath(a2);
          StringValue = RegReadStringValue(v23, v22, L"IdpDomain", v15, (SIZE_T)phkResult, (unsigned __int16 **)a1 + 1);
LABEL_29:
          if ( !StringValue )
            goto LABEL_33;
          goto LABEL_32;
        }
        pdwType = 0;
        pcbData = 0;
        ValueW = RegGetValueW(v16, 0, L"IdpDomain", 2u, &pdwType, 0, &pcbData);
        StringValue = ValueW;
        switch ( ValueW )
        {
          case 2:
            LODWORD(phkResult) = 2;
            Logger::TraceWarning(
              L"%s: The registry key value \"%s@%s\" does not exist. Using default value NULL. Error code: 0x%08x.",
              L"RegReadStringValue",
              v15,
              L"IdpDomain");
            StringValue = 0;
            goto LABEL_29;
          case 1630:
            LODWORD(phkResult) = 2;
            Logger::TraceWarning(
              L"%s: The registry key value \"%s@%s\" is not of one of the specified types (flags = 0x%08x). Using default value NULL.",
              L"RegReadStringValue",
              v15,
              L"IdpDomain");
            StringValue = 0;
            goto LABEL_29;
          case 0:
          case 234:
            if ( !pcbData )
              goto LABEL_25;
            v20 = MIDL_user_allocate(pcbData);
            *v12 = v20;
            if ( v20 )
            {
              StringValue = RegGetValueW(hkey, 0, L"IdpDomain", 2u, &pdwType, v20, &pcbData);
LABEL_25:
              if ( !StringValue )
                goto LABEL_29;
              break;
            }
            StringValue = 14;
            Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegReadStringValue");
            break;
        }
        Logger::WriteRegistryFailureEvent(StringValue, v18, v15, L"IdpDomain");
        RegValueName = GetRegValueName(L"IdpDomain");
        LODWORD(phkResult) = StringValue;
        Logger::TraceWarning(
          L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
          L"RegReadStringValue",
          v15,
          RegValueName);
        SafeFree(*v12);
        *v12 = 0;
        goto LABEL_29;
      }
    }
  }
  Logger::TraceError(
    L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
    L"RegistryPath::ReadStringValue");
  StringValue = 87;
LABEL_32:
  Logger::TraceError(
    L"%s: %s failed with win32 error code: 0x%08x.",
    L"JoinStatusStorage::ReadDeviceKey",
    L"RegistryPath::ReadStringValue",
    StringValue);
  if ( !v123 )
    goto LABEL_231;
LABEL_33:
  v24 = (void *)*((_QWORD *)a1 + 2);
  v25 = (void **)((char *)a1 + 16);
  if ( v24 )
  {
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v24);
  }
  *v25 = 0;
  if ( *((_QWORD *)a2 + 4) )
  {
    v27 = *(const unsigned __int16 **)a2;
    if ( *(_QWORD *)a2 )
    {
      if ( *v27 )
      {
        v28 = *v5;
        hkey = v28;
        if ( !v28 )
        {
          v33 = RegistryPath::SubPath(a2);
          StringValue = RegReadStringValue(v34, v33, L"TenantId", v27, (SIZE_T)phkResult, (unsigned __int16 **)a1 + 2);
LABEL_52:
          if ( !StringValue )
            goto LABEL_56;
          goto LABEL_55;
        }
        pdwType = 0;
        pcbData = 0;
        v29 = RegGetValueW(v28, 0, L"TenantId", 2u, &pdwType, 0, &pcbData);
        StringValue = v29;
        switch ( v29 )
        {
          case 2:
            LODWORD(phkResult) = 2;
            Logger::TraceWarning(
              L"%s: The registry key value \"%s@%s\" does not exist. Using default value NULL. Error code: 0x%08x.",
              L"RegReadStringValue",
              v27,
              L"TenantId");
            StringValue = 0;
            goto LABEL_52;
          case 1630:
            LODWORD(phkResult) = 2;
            Logger::TraceWarning(
              L"%s: The registry key value \"%s@%s\" is not of one of the specified types (flags = 0x%08x). Using default value NULL.",
              L"RegReadStringValue",
              v27,
              L"TenantId");
            StringValue = 0;
            goto LABEL_52;
          case 0:
          case 234:
            if ( !pcbData )
              goto LABEL_48;
            v31 = MIDL_user_allocate(pcbData);
            *v25 = v31;
            if ( v31 )
            {
              StringValue = RegGetValueW(hkey, 0, L"TenantId", 2u, &pdwType, v31, &pcbData);
LABEL_48:
              if ( !StringValue )
                goto LABEL_52;
              break;
            }
            StringValue = 14;
            Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegReadStringValue");
            break;
        }
        Logger::WriteRegistryFailureEvent(StringValue, v30, v27, L"TenantId");
        v32 = GetRegValueName(L"TenantId");
        LODWORD(phkResult) = StringValue;
        Logger::TraceWarning(
          L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
          L"RegReadStringValue",
          v27,
          v32);
        SafeFree(*v25);
        *v25 = 0;
        goto LABEL_52;
      }
    }
  }
  Logger::TraceError(
    L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
    L"RegistryPath::ReadStringValue");
  StringValue = 87;
LABEL_55:
  Logger::TraceError(
    L"%s: %s failed with win32 error code: 0x%08x.",
    L"JoinStatusStorage::ReadDeviceKey",
    L"RegistryPath::ReadStringValue",
    StringValue);
  if ( !v123 )
    goto LABEL_231;
LABEL_56:
  v35 = (void *)*((_QWORD *)a1 + 3);
  v36 = (void **)((char *)a1 + 24);
  if ( v35 )
  {
    v37 = GetProcessHeap();
    HeapFree(v37, 0, v35);
  }
  *v36 = 0;
  if ( !*((_QWORD *)a2 + 4) || (v38 = *(const unsigned __int16 **)a2) == 0 || !*v38 )
  {
    Logger::TraceError(
      L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
      L"RegistryPath::ReadStringValue");
    StringValue = 87;
    goto LABEL_83;
  }
  v39 = *v5;
  hkey = v39;
  if ( v39 )
  {
    pdwType = 0;
    pcbData = 0;
    v40 = RegGetValueW(v39, 0, L"UserEmail", 2u, &pdwType, 0, &pcbData);
    StringValue = v40;
    if ( v40 == 2 )
    {
      LODWORD(phkResult) = 2;
      Logger::TraceWarning(
        L"%s: The registry key value \"%s@%s\" does not exist. Using default value NULL. Error code: 0x%08x.",
        L"RegReadStringValue",
        v38,
        L"UserEmail");
      StringValue = 0;
      goto LABEL_75;
    }
    if ( v40 == 1630 )
    {
      LODWORD(phkResult) = 2;
      Logger::TraceWarning(
        L"%s: The registry key value \"%s@%s\" is not of one of the specified types (flags = 0x%08x). Using default value NULL.",
        L"RegReadStringValue",
        v38,
        L"UserEmail");
      StringValue = 0;
      goto LABEL_75;
    }
    if ( v40 && v40 != 234 )
      goto LABEL_72;
    if ( pcbData )
    {
      v42 = MIDL_user_allocate(pcbData);
      *v36 = v42;
      if ( !v42 )
      {
        StringValue = 14;
        Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegReadStringValue");
LABEL_72:
        Logger::WriteRegistryFailureEvent(StringValue, v41, v38, L"UserEmail");
        v43 = GetRegValueName(L"UserEmail");
        LODWORD(phkResult) = StringValue;
        Logger::TraceWarning(
          L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
          L"RegReadStringValue",
          v38,
          v43);
        SafeFree(*v36);
        *v36 = 0;
        goto LABEL_75;
      }
      StringValue = RegGetValueW(hkey, 0, L"UserEmail", 2u, &pdwType, v42, &pcbData);
    }
    if ( !StringValue )
    {
LABEL_76:
      v46 = v123;
      goto LABEL_77;
    }
    goto LABEL_72;
  }
  v44 = RegistryPath::SubPath(a2);
  StringValue = RegReadStringValue(v45, v44, L"UserEmail", v38, (SIZE_T)phkResult, (unsigned __int16 **)a1 + 3);
LABEL_75:
  if ( !StringValue )
    goto LABEL_76;
LABEL_83:
  Logger::TraceError(
    L"%s: %s failed with win32 error code: 0x%08x.",
    L"JoinStatusStorage::ReadDeviceKey",
    L"RegistryPath::ReadStringValue",
    StringValue);
  v46 = v123;
  if ( !v123 )
    goto LABEL_231;
LABEL_77:
  if ( *((_QWORD *)a2 + 4) && (v47 = *(const unsigned __int16 **)a2) != 0 && *v47 )
  {
    v48 = *v5;
    v49 = (unsigned int *)((char *)a1 + 216);
    if ( *v5 )
    {
      v50 = 0;
    }
    else
    {
      v50 = RegistryPath::SubPath(a2);
      v48 = v51;
    }
    StringValue = RegReadDwordValue(v48, v50, L"TransportKeyStatus", v47, v49, (unsigned int)pvData);
    if ( !StringValue )
      goto LABEL_90;
  }
  else
  {
    Logger::TraceError(
      L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
      L"RegistryPath::ReadDwordValue");
    StringValue = 87;
  }
  Logger::TraceError(
    L"%s: %s failed with win32 error code: 0x%08x.",
    L"JoinStatusStorage::ReadDeviceKey",
    L"RegistryPath::ReadDwordValue",
    StringValue);
  if ( !v46 )
    goto LABEL_231;
LABEL_90:
  if ( *((_QWORD *)a2 + 4) && (v52 = *(const unsigned __int16 **)a2) != 0 && *v52 )
  {
    v53 = *v5;
    v54 = (unsigned int *)((char *)a1 + 208);
    if ( *v5 )
    {
      v55 = 0;
    }
    else
    {
      v55 = RegistryPath::SubPath(a2);
      v53 = v56;
    }
    StringValue = RegReadDwordValue(v53, v55, L"AttestationLevel", v52, v54, (unsigned int)pvData);
    if ( !StringValue )
      goto LABEL_100;
  }
  else
  {
    Logger::TraceError(
      L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
      L"RegistryPath::ReadDwordValue");
    StringValue = 87;
  }
  Logger::TraceError(
    L"%s: %s failed with win32 error code: 0x%08x.",
    L"JoinStatusStorage::ReadDeviceKey",
    L"RegistryPath::ReadDwordValue",
    StringValue);
  if ( !v46 )
    goto LABEL_231;
LABEL_100:
  if ( *((_QWORD *)a2 + 4) && (v57 = *(const unsigned __int16 **)a2) != 0 && *v57 )
  {
    v58 = *v5;
    v59 = (unsigned int *)((char *)a1 + 212);
    if ( *v5 )
    {
      v60 = 0;
    }
    else
    {
      v60 = RegistryPath::SubPath(a2);
      v58 = v61;
    }
    StringValue = RegReadDwordValue(v58, v60, L"AikCertStatus", v57, v59, (unsigned int)pvData);
    if ( !StringValue )
      goto LABEL_110;
  }
  else
  {
    Logger::TraceError(
      L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
      L"RegistryPath::ReadDwordValue");
    StringValue = 87;
  }
  Logger::TraceError(
    L"%s: %s failed with win32 error code: 0x%08x.",
    L"JoinStatusStorage::ReadDeviceKey",
    L"RegistryPath::ReadDwordValue",
    StringValue);
  if ( !v46 )
    goto LABEL_231;
LABEL_110:
  v62 = (void **)((char *)a1 + 232);
  v63 = (void *)*((_QWORD *)a1 + 29);
  if ( v63 )
  {
    v64 = GetProcessHeap();
    HeapFree(v64, 0, v63);
  }
  *v62 = 0;
  if ( !*((_QWORD *)a2 + 4) || (v65 = *(const unsigned __int16 **)a2) == 0 || !*v65 )
  {
    Logger::TraceError(
      L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
      L"RegistryPath::ReadStringValue");
    StringValue = 87;
    goto LABEL_140;
  }
  v66 = (HKEY)*((_QWORD *)a2 + 5);
  if ( v66 )
  {
    pdwType = 0;
    pcbData = 0;
    v67 = RegGetValueW(v66, 0, L"RbacResourceId", 2u, &pdwType, 0, &pcbData);
    StringValue = v67;
    if ( v67 == 2 )
    {
      LODWORD(phkResult) = 2;
      Logger::TraceWarning(
        L"%s: The registry key value \"%s@%s\" does not exist. Using default value NULL. Error code: 0x%08x.",
        L"RegReadStringValue",
        v65,
        L"RbacResourceId");
      StringValue = 0;
      goto LABEL_129;
    }
    if ( v67 == 1630 )
    {
      LODWORD(phkResult) = 2;
      Logger::TraceWarning(
        L"%s: The registry key value \"%s@%s\" is not of one of the specified types (flags = 0x%08x). Using default value NULL.",
        L"RegReadStringValue",
        v65,
        L"RbacResourceId");
      StringValue = 0;
      goto LABEL_129;
    }
    if ( v67 && v67 != 234 )
      goto LABEL_126;
    if ( pcbData )
    {
      v69 = MIDL_user_allocate(pcbData);
      *v62 = v69;
      if ( !v69 )
      {
        StringValue = 14;
        Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegReadStringValue");
LABEL_126:
        Logger::WriteRegistryFailureEvent(StringValue, v68, v65, L"RbacResourceId");
        v70 = GetRegValueName(L"RbacResourceId");
        LODWORD(phkResult) = StringValue;
        Logger::TraceWarning(
          L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
          L"RegReadStringValue",
          v65,
          v70);
        SafeFree(*v62);
        *v62 = 0;
        goto LABEL_129;
      }
      StringValue = RegGetValueW(v66, 0, L"RbacResourceId", 2u, &pdwType, v69, &pcbData);
    }
    if ( !StringValue )
    {
LABEL_130:
      v73 = v123;
      goto LABEL_131;
    }
    goto LABEL_126;
  }
  v71 = RegistryPath::SubPath(a2);
  StringValue = RegReadStringValue(v72, v71, L"RbacResourceId", v65, (SIZE_T)phkResult, (unsigned __int16 **)a1 + 29);
LABEL_129:
  if ( !StringValue )
    goto LABEL_130;
LABEL_140:
  Logger::TraceError(
    L"%s: %s failed with win32 error code: 0x%08x.",
    L"JoinStatusStorage::ReadDeviceKey",
    L"RegistryPath::ReadStringValue",
    StringValue);
  v73 = v123;
  if ( !v123 )
    goto LABEL_231;
LABEL_131:
  v74 = (void **)((char *)a1 + 240);
  v75 = (void *)*((_QWORD *)a1 + 30);
  if ( v75 )
  {
    v76 = GetProcessHeap();
    HeapFree(v76, 0, v75);
  }
  *v74 = 0;
  if ( *((_QWORD *)a2 + 4) )
  {
    v77 = *(const unsigned __int16 **)a2;
    if ( *(_QWORD *)a2 )
    {
      if ( *v77 )
      {
        v78 = (HKEY)*((_QWORD *)a2 + 5);
        if ( !v78 )
        {
          v83 = RegistryPath::SubPath(a2);
          StringValue = RegReadStringValue(
                          v84,
                          v83,
                          L"DeviceDisplayName",
                          v77,
                          (SIZE_T)phkResult,
                          (unsigned __int16 **)a1 + 30);
LABEL_153:
          v73 = v123;
          if ( !StringValue )
            goto LABEL_157;
          goto LABEL_156;
        }
        pdwType = 0;
        pcbData = 0;
        v79 = RegGetValueW(v78, 0, L"DeviceDisplayName", 2u, &pdwType, 0, &pcbData);
        StringValue = v79;
        switch ( v79 )
        {
          case 2:
            LODWORD(phkResult) = 2;
            Logger::TraceWarning(
              L"%s: The registry key value \"%s@%s\" does not exist. Using default value NULL. Error code: 0x%08x.",
              L"RegReadStringValue",
              v77,
              L"DeviceDisplayName");
            StringValue = 0;
            goto LABEL_153;
          case 1630:
            LODWORD(phkResult) = 2;
            Logger::TraceWarning(
              L"%s: The registry key value \"%s@%s\" is not of one of the specified types (flags = 0x%08x). Using default value NULL.",
              L"RegReadStringValue",
              v77,
              L"DeviceDisplayName");
            StringValue = 0;
            goto LABEL_153;
          case 0:
          case 234:
            if ( !pcbData )
              goto LABEL_149;
            v81 = MIDL_user_allocate(pcbData);
            *v74 = v81;
            if ( v81 )
            {
              StringValue = RegGetValueW(v78, 0, L"DeviceDisplayName", 2u, &pdwType, v81, &pcbData);
LABEL_149:
              if ( !StringValue )
                goto LABEL_153;
              break;
            }
            StringValue = 14;
            Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegReadStringValue");
            break;
        }
        Logger::WriteRegistryFailureEvent(StringValue, v80, v77, L"DeviceDisplayName");
        v82 = GetRegValueName(L"DeviceDisplayName");
        LODWORD(phkResult) = StringValue;
        Logger::TraceWarning(
          L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
          L"RegReadStringValue",
          v77,
          v82);
        SafeFree(*v74);
        *v74 = 0;
        goto LABEL_153;
      }
    }
  }
  Logger::TraceError(
    L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
    L"RegistryPath::ReadStringValue");
  StringValue = 87;
LABEL_156:
  Logger::TraceError(
    L"%s: %s failed with win32 error code: 0x%08x.",
    L"JoinStatusStorage::ReadDeviceKey",
    L"RegistryPath::ReadStringValue",
    StringValue);
  if ( !v73 )
    goto LABEL_231;
LABEL_157:
  v85 = (void **)((char *)a1 + 248);
  v86 = (void *)*((_QWORD *)a1 + 31);
  if ( v86 )
  {
    v87 = GetProcessHeap();
    HeapFree(v87, 0, v86);
  }
  *v85 = 0;
  if ( *((_QWORD *)a2 + 4) )
  {
    v88 = *(const unsigned __int16 **)a2;
    if ( *(_QWORD *)a2 )
    {
      if ( *v88 )
      {
        v89 = (HKEY)*((_QWORD *)a2 + 5);
        if ( !v89 )
        {
          v94 = RegistryPath::SubPath(a2);
          StringValue = RegReadStringValue(v95, v94, L"OsVersion", v88, (SIZE_T)phkResult, (unsigned __int16 **)a1 + 31);
LABEL_176:
          if ( StringValue )
          {
            v73 = v123;
            goto LABEL_179;
          }
LABEL_181:
          v73 = v123;
          goto LABEL_182;
        }
        pdwType = 0;
        pcbData = 0;
        v90 = RegGetValueW(v89, 0, L"OsVersion", 2u, &pdwType, 0, &pcbData);
        StringValue = v90;
        switch ( v90 )
        {
          case 2:
            LODWORD(phkResult) = 2;
            Logger::TraceWarning(
              L"%s: The registry key value \"%s@%s\" does not exist. Using default value NULL. Error code: 0x%08x.",
              L"RegReadStringValue",
              v88,
              L"OsVersion");
            StringValue = 0;
            goto LABEL_176;
          case 1630:
            LODWORD(phkResult) = 2;
            Logger::TraceWarning(
              L"%s: The registry key value \"%s@%s\" is not of one of the specified types (flags = 0x%08x). Using default value NULL.",
              L"RegReadStringValue",
              v88,
              L"OsVersion");
            StringValue = 0;
            goto LABEL_176;
          case 0:
          case 234:
            if ( !pcbData )
              goto LABEL_172;
            v92 = MIDL_user_allocate(pcbData);
            *v85 = v92;
            if ( v92 )
            {
              StringValue = RegGetValueW(v89, 0, L"OsVersion", 2u, &pdwType, v92, &pcbData);
LABEL_172:
              if ( !StringValue )
                goto LABEL_181;
              break;
            }
            StringValue = 14;
            Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegReadStringValue");
            break;
        }
        Logger::WriteRegistryFailureEvent(StringValue, v91, v88, L"OsVersion");
        v93 = GetRegValueName(L"OsVersion");
        LODWORD(phkResult) = StringValue;
        Logger::TraceWarning(
          L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
          L"RegReadStringValue",
          v88,
          v93);
        SafeFree(*v85);
        *v85 = 0;
        goto LABEL_176;
      }
    }
  }
  Logger::TraceError(
    L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
    L"RegistryPath::ReadStringValue");
  StringValue = 87;
LABEL_179:
  Logger::TraceError(
    L"%s: %s failed with win32 error code: 0x%08x.",
    L"JoinStatusStorage::ReadDeviceKey",
    L"RegistryPath::ReadStringValue",
    StringValue);
  if ( !v73 )
    goto LABEL_231;
LABEL_182:
  if ( *((_QWORD *)a2 + 4) && (v96 = *(const unsigned __int16 **)a2) != 0 && *v96 )
  {
    v97 = (HKEY)*((_QWORD *)a2 + 5);
    v98 = (unsigned int *)((char *)a1 + 256);
    if ( v97 )
    {
      v99 = 0;
    }
    else
    {
      v99 = RegistryPath::SubPath(a2);
      v97 = v100;
    }
    StringValue = RegReadDwordValue(v97, v99, L"DdidUpToDate", v96, v98, (unsigned int)pvData);
    if ( !StringValue )
      goto LABEL_192;
  }
  else
  {
    Logger::TraceError(
      L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
      L"RegistryPath::ReadDwordValue");
    StringValue = 87;
  }
  Logger::TraceError(
    L"%s: %s failed with win32 error code: 0x%08x.",
    L"JoinStatusStorage::ReadDeviceKey",
    L"RegistryPath::ReadDwordValue",
    StringValue);
  if ( !v73 )
    goto LABEL_231;
LABEL_192:
  v101 = (void **)((char *)a1 + 272);
  v102 = (void *)*((_QWORD *)a1 + 34);
  if ( v102 )
  {
    v103 = GetProcessHeap();
    HeapFree(v103, 0, v102);
  }
  *v101 = 0;
  if ( !*((_QWORD *)a2 + 4) || (v104 = *(const unsigned __int16 **)a2) == 0 || !*v104 )
  {
    Logger::TraceError(
      L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
      L"RegistryPath::ReadStringValue");
    StringValue = 87;
LABEL_214:
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadDeviceKey",
      L"RegistryPath::ReadStringValue",
      StringValue);
    if ( !v73 )
      goto LABEL_231;
    goto LABEL_217;
  }
  v105 = (HKEY)*((_QWORD *)a2 + 5);
  if ( v105 )
  {
    pdwType = 0;
    pcbData = 0;
    v106 = RegGetValueW(v105, 0, L"DnsFullyQualifiedName", 2u, &pdwType, 0, &pcbData);
    StringValue = v106;
    if ( v106 == 2 )
    {
      LODWORD(phkResulta) = 2;
      Logger::TraceWarning(
        L"%s: The registry key value \"%s@%s\" does not exist. Using default value NULL. Error code: 0x%08x.",
        L"RegReadStringValue",
        v104,
        L"DnsFullyQualifiedName",
        phkResulta);
      StringValue = 0;
      goto LABEL_211;
    }
    if ( v106 == 1630 )
    {
      LODWORD(phkResulta) = 2;
      Logger::TraceWarning(
        L"%s: The registry key value \"%s@%s\" is not of one of the specified types (flags = 0x%08x). Using default value NULL.",
        L"RegReadStringValue",
        v104,
        L"DnsFullyQualifiedName",
        phkResulta);
      StringValue = 0;
      goto LABEL_211;
    }
    if ( v106 && v106 != 234 )
      goto LABEL_208;
    if ( pcbData )
    {
      v108 = MIDL_user_allocate(pcbData);
      *v101 = v108;
      if ( !v108 )
      {
        StringValue = 14;
        Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegReadStringValue");
LABEL_208:
        Logger::WriteRegistryFailureEvent(StringValue, v107, v104, L"DnsFullyQualifiedName");
        v109 = GetRegValueName(L"DnsFullyQualifiedName");
        LODWORD(phkResulta) = StringValue;
        Logger::TraceWarning(
          L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
          L"RegReadStringValue",
          v104,
          v109,
          phkResulta);
        SafeFree(*v101);
        *v101 = 0;
        goto LABEL_211;
      }
      StringValue = RegGetValueW(v105, 0, L"DnsFullyQualifiedName", 2u, &pdwType, v108, &pcbData);
    }
    if ( !StringValue )
      goto LABEL_216;
    goto LABEL_208;
  }
  v110 = RegistryPath::SubPath(a2);
  StringValue = RegReadStringValue(
                  v111,
                  v110,
                  L"DnsFullyQualifiedName",
                  v104,
                  (SIZE_T)phkResult,
                  (unsigned __int16 **)a1 + 34);
LABEL_211:
  if ( StringValue )
  {
    v73 = v123;
    goto LABEL_214;
  }
LABEL_216:
  v73 = v123;
LABEL_217:
  v112 = (const unsigned __int16 *)*((_QWORD *)a2 + 4);
  if ( v112 && (v113 = *(const unsigned __int16 **)a2) != 0 && *v113 )
  {
    v114 = (HKEY)*((_QWORD *)a2 + 5);
    v115 = (__int64 *)((char *)a1 + 264);
    if ( v114 )
    {
      v116 = 0;
    }
    else
    {
      v116 = RegistryPath::SubPath(a2);
      v114 = (HKEY)v112;
    }
    QwordValue = RegReadQwordValue(v114, v116, v112, v113, v115, (__int64)pvData);
    StringValue = QwordValue;
    if ( !QwordValue )
    {
      if ( !v73 )
        goto LABEL_231;
      goto LABEL_228;
    }
  }
  else
  {
    Logger::TraceError(
      L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
      L"RegistryPath::ReadQwordValue");
    StringValue = 87;
  }
  Logger::TraceError(
    L"%s: %s failed with win32 error code: 0x%08x.",
    L"JoinStatusStorage::ReadDeviceKey",
    L"RegistryPath::ReadQwordValue",
    QwordValue);
  if ( v73 )
LABEL_228:
    StringValue = 0;
LABEL_231:
  if ( *((_QWORD *)a1 + 1) && *((_QWORD *)a1 + 2) && StringValue != 2 )
  {
    if ( (int)StringValue > 0 )
      return (unsigned __int16)StringValue | 0x80070000;
    return StringValue;
  }
  else
  {
    Logger::TraceError(
      L"%s: Failed to read one or more join status entries from the registry.",
      L"JoinStatusStorage::ReadDeviceKey");
    return 2149318678LL;
  }
}

```

## disassembly

```asm
0x18001a130  mov     [rsp-10h+arg_10], r8d
0x18001a135  push    rbp
0x18001a136  push    r13
0x18001a138  mov     rbp, rsp
0x18001a13b  sub     rsp, 78h
0x18001a13f  mov     [rsp+78h+var_10], rsi
0x18001a144  mov     r13, rcx
0x18001a147  mov     rcx, [rdx+28h]; hKey
0x18001a14b  lea     rsi, [rdx+28h]
0x18001a14f  mov     [rsp+78h+var_18], rdi
0x18001a154  mov     rdi, rdx
0x18001a157  mov     [rsp+78h+var_30], r15
0x18001a15c  test    rcx, rcx
0x18001a15f  jz      short loc_18001A167
0x18001a161  call    cs:__imp_RegCloseKey
0x18001a167  xor     r15d, r15d
0x18001a16a  mov     [rsp+78h+var_8], rbx
0x18001a16f  mov     [rsi], r15
0x18001a172  mov     rcx, [rdi+20h]; hKey
0x18001a176  mov     [rsp+78h+var_20], r12
0x18001a17b  mov     [rsp+78h+var_28], r14
0x18001a180  test    rcx, rcx
0x18001a183  jz      loc_18001B3CA
0x18001a189  mov     rdx, [rdi]
0x18001a18c  test    rdx, rdx
0x18001a18f  jz      loc_18001B3CA
0x18001a195  cmp     [rdx], r15w
0x18001a199  jz      loc_18001B3CA
0x18001a19f  mov     rax, [rdi+18h]
0x18001a1a3  mov     r9d, 1; samDesired
0x18001a1a9  xor     r8d, r8d; ulOptions
0x18001a1ac  mov     [rsp+78h+phkResult], rsi; dwBytes
0x18001a1b1  lea     rdx, [rdx+rax*2]; lpSubKey
0x18001a1b5  call    cs:__imp_RegOpenKeyExW
0x18001a1bb  mov     r12d, eax
0x18001a1be  test    eax, eax
0x18001a1c0  jz      short loc_18001A1FD
0x18001a1c2  mov     r8, [rdi]; unsigned __int16 *
0x18001a1c5  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x18001a1cc  mov     ecx, eax; unsigned int
0x18001a1ce  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x18001a1d3  mov     r8, [rdi]
0x18001a1d6  lea     rdx, aRegistrypathOp; "RegistryPath::OpenSubKey"
0x18001a1dd  mov     r9d, r12d
0x18001a1e0  lea     rcx, aSFailedToOpenR; "%s: Failed to open registry key \"%s\"."...
0x18001a1e7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001a1ec  mov     rcx, [rsi]; hKey
0x18001a1ef  test    rcx, rcx
0x18001a1f2  jz      short loc_18001A1FD
0x18001a1f4  call    cs:__imp_RegCloseKey
0x18001a1fa  mov     [rsi], r15
0x18001a1fd  test    r12d, r12d
0x18001a200  jnz     loc_18001B3E3
0x18001a206  mov     rbx, [r13+8]
0x18001a20a  lea     r14, [r13+8]
0x18001a20e  test    rbx, rbx
0x18001a211  jz      short loc_18001A227
0x18001a213  call    cs:__imp_GetProcessHeap
0x18001a219  mov     r8, rbx; lpMem
0x18001a21c  xor     edx, edx; dwFlags
0x18001a21e  mov     rcx, rax; hHeap
0x18001a221  call    cs:__imp_HeapFree
0x18001a227  mov     [r14], r15
0x18001a22a  mov     r12d, 57h ; 'W'
0x18001a230  mov     r10, [rdi+20h]
0x18001a234  test    r10, r10
0x18001a237  jz      loc_18001A3ED
0x18001a23d  mov     r15, [rdi]
0x18001a240  test    r15, r15
0x18001a243  jz      loc_18001A3ED
0x18001a249  cmp     word ptr [r15], 0
0x18001a24e  jz      loc_18001A3ED
0x18001a254  mov     rax, [rsi]
0x18001a257  mov     [rbp+hkey], rax
0x18001a25b  test    rax, rax
0x18001a25e  jz      loc_18001A3C1
0x18001a264  xor     edx, edx; lpSubKey
0x18001a266  lea     rcx, [rbp+arg_0]
0x18001a26a  mov     [rsp+78h+pcbData], rcx; pcbData
0x18001a26f  lea     r8, aIdpdomain; "IdpDomain"
0x18001a276  lea     rcx, [rbp+pdwType]
0x18001a27a  mov     [rsp+78h+pvData], rdx; pvData
0x18001a27f  mov     [rsp+78h+phkResult], rcx; pdwType
0x18001a284  mov     r9d, 2; dwFlags
0x18001a28a  mov     rcx, rax; hkey
0x18001a28d  mov     [rbp+pdwType], edx
0x18001a290  mov     [rbp+arg_0], edx
0x18001a293  call    cs:__imp_RegGetValueW
0x18001a299  mov     ebx, eax
0x18001a29b  cmp     eax, 2
0x18001a29e  jnz     short loc_18001A2CA
0x18001a2a0  lea     r9, aIdpdomain; "IdpDomain"
0x18001a2a7  mov     dword ptr [rsp+78h+phkResult], eax
0x18001a2ab  mov     r8, r15
0x18001a2ae  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18001a2b5  lea     rcx, aSTheRegistryKe; "%s: The registry key value \"%s@%s\" do"...
0x18001a2bc  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18001a2c1  xor     edx, edx
0x18001a2c3  mov     ebx, edx
0x18001a2c5  jmp     loc_18001A3E7
0x18001a2ca  cmp     eax, 65Eh
0x18001a2cf  jnz     short loc_18001A2FF
0x18001a2d1  lea     r9, aIdpdomain; "IdpDomain"
0x18001a2d8  mov     dword ptr [rsp+78h+phkResult], 2
0x18001a2e0  mov     r8, r15
0x18001a2e3  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18001a2ea  lea     rcx, aSTheRegistryKe_4; "%s: The registry key value \"%s@%s\" is"...
0x18001a2f1  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18001a2f6  xor     edx, edx
0x18001a2f8  mov     ebx, edx
0x18001a2fa  jmp     loc_18001A3E7
0x18001a2ff  test    eax, eax
0x18001a301  jz      short loc_18001A30A
0x18001a303  cmp     eax, 0EAh
0x18001a308  jnz     short loc_18001A35E
0x18001a30a  mov     eax, [rbp+arg_0]
0x18001a30d  test    eax, eax
0x18001a30f  jz      short loc_18001A356
0x18001a311  mov     ecx, eax; size
0x18001a313  call    MIDL_user_allocate
0x18001a318  mov     [r14], rax
0x18001a31b  test    rax, rax
0x18001a31e  jz      loc_18001A3A7
0x18001a324  lea     rcx, [rbp+arg_0]
0x18001a328  mov     r9d, 2; dwFlags
0x18001a32e  mov     [rsp+78h+pcbData], rcx; pcbData
0x18001a333  lea     r8, aIdpdomain; "IdpDomain"
0x18001a33a  mov     rcx, [rbp+hkey]; hkey
0x18001a33e  xor     edx, edx; lpSubKey
0x18001a340  mov     [rsp+78h+pvData], rax; pvData
0x18001a345  lea     rax, [rbp+pdwType]
0x18001a349  mov     [rsp+78h+phkResult], rax; pdwType
0x18001a34e  call    cs:__imp_RegGetValueW
0x18001a354  mov     ebx, eax
0x18001a356  test    ebx, ebx
0x18001a358  jz      loc_18001A3E5
0x18001a35e  lea     r9, aIdpdomain; "IdpDomain"
0x18001a365  mov     r8, r15; unsigned __int16 *
0x18001a368  mov     ecx, ebx; unsigned int
0x18001a36a  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)
0x18001a36f  lea     rcx, aIdpdomain; "IdpDomain"
0x18001a376  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x18001a37b  mov     r9, rax
0x18001a37e  mov     dword ptr [rsp+78h+phkResult], ebx
0x18001a382  mov     r8, r15
0x18001a385  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18001a38c  lea     rcx, aSCannotReadReg; "%s: Cannot read registry key value \"%s"...
0x18001a393  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18001a398  mov     rcx, [r14]; void *
0x18001a39b  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18001a3a0  xor     edx, edx
0x18001a3a2  mov     [r14], rdx
0x18001a3a5  jmp     short loc_18001A3E7
0x18001a3a7  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18001a3ae  mov     ebx, 0Eh
0x18001a3b3  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18001a3ba  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18001a3bf  jmp     short loc_18001A35E
0x18001a3c1  mov     rcx, rdi; this
0x18001a3c4  call    ?SubPath@RegistryPath@@QEBAPEBGXZ; RegistryPath::SubPath(void)
0x18001a3c9  mov     rdx, rax; lpSubKey
0x18001a3cc  mov     [rsp+78h+pvData], r14; unsigned __int16 **
0x18001a3d1  mov     r9, r15; unsigned __int16 *
0x18001a3d4  lea     r8, aIdpdomain; "IdpDomain"
0x18001a3db  mov     rcx, r10; hkey
0x18001a3de  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18001a3e3  mov     ebx, eax
0x18001a3e5  xor     edx, edx
0x18001a3e7  test    ebx, ebx
0x18001a3e9  jnz     short loc_18001A403
0x18001a3eb  jmp     short loc_18001A42C
0x18001a3ed  lea     rdx, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18001a3f4  lea     rcx, aSThisPathObjec; "%s: This path object has not been prope"...
0x18001a3fb  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001a400  mov     ebx, r12d
0x18001a403  mov     r9d, ebx
0x18001a406  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18001a40d  lea     rdx, aJoinstatusstor; "JoinStatusStorage::ReadDeviceKey"
0x18001a414  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18001a41b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001a420  cmp     [rbp+arg_10], 0
0x18001a424  jz      loc_18001B403
0x18001a42a  xor     edx, edx
0x18001a42c  mov     rbx, [r13+10h]
0x18001a430  lea     r15, [r13+10h]
0x18001a434  test    rbx, rbx
0x18001a437  jz      short loc_18001A44F
0x18001a439  call    cs:__imp_GetProcessHeap
0x18001a43f  mov     r8, rbx; lpMem
0x18001a442  xor     edx, edx; dwFlags
0x18001a444  mov     rcx, rax; hHeap
0x18001a447  call    cs:__imp_HeapFree
0x18001a44d  xor     edx, edx
0x18001a44f  mov     [r15], rdx
0x18001a452  mov     r10, [rdi+20h]
0x18001a456  test    r10, r10
0x18001a459  jz      loc_18001A60F
0x18001a45f  mov     r14, [rdi]
0x18001a462  test    r14, r14
0x18001a465  jz      loc_18001A60F
0x18001a46b  cmp     word ptr [r14], 0
0x18001a470  jz      loc_18001A60F
0x18001a476  mov     rax, [rsi]
0x18001a479  mov     [rbp+hkey], rax
0x18001a47d  test    rax, rax
0x18001a480  jz      loc_18001A5E3
0x18001a486  lea     rcx, [rbp+arg_0]
0x18001a48a  mov     [rbp+pdwType], edx
0x18001a48d  mov     [rsp+78h+pcbData], rcx; pcbData
0x18001a492  lea     r8, aTenantid; "TenantId"
0x18001a499  mov     [rsp+78h+pvData], rdx; pvData
0x18001a49e  lea     rcx, [rbp+pdwType]
0x18001a4a2  mov     [rsp+78h+phkResult], rcx; pdwType
0x18001a4a7  mov     r9d, 2; dwFlags
0x18001a4ad  mov     [rbp+arg_0], edx
0x18001a4b0  mov     rcx, rax; hkey
0x18001a4b3  xor     edx, edx; lpSubKey
0x18001a4b5  call    cs:__imp_RegGetValueW
0x18001a4bb  mov     ebx, eax
0x18001a4bd  cmp     eax, 2
0x18001a4c0  jnz     short loc_18001A4EC
0x18001a4c2  lea     r9, aTenantid; "TenantId"
0x18001a4c9  mov     dword ptr [rsp+78h+phkResult], eax
0x18001a4cd  mov     r8, r14
0x18001a4d0  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18001a4d7  lea     rcx, aSTheRegistryKe; "%s: The registry key value \"%s@%s\" do"...
0x18001a4de  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18001a4e3  xor     edx, edx
0x18001a4e5  mov     ebx, edx
0x18001a4e7  jmp     loc_18001A609
0x18001a4ec  cmp     eax, 65Eh
0x18001a4f1  jnz     short loc_18001A521
0x18001a4f3  lea     r9, aTenantid; "TenantId"
0x18001a4fa  mov     dword ptr [rsp+78h+phkResult], 2
0x18001a502  mov     r8, r14
0x18001a505  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18001a50c  lea     rcx, aSTheRegistryKe_4; "%s: The registry key value \"%s@%s\" is"...
0x18001a513  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18001a518  xor     edx, edx
0x18001a51a  mov     ebx, edx
0x18001a51c  jmp     loc_18001A609
0x18001a521  test    eax, eax
0x18001a523  jz      short loc_18001A52C
0x18001a525  cmp     eax, 0EAh
0x18001a52a  jnz     short loc_18001A580
0x18001a52c  mov     eax, [rbp+arg_0]
0x18001a52f  test    eax, eax
0x18001a531  jz      short loc_18001A578
0x18001a533  mov     ecx, eax; size
0x18001a535  call    MIDL_user_allocate
0x18001a53a  mov     [r15], rax
0x18001a53d  test    rax, rax
0x18001a540  jz      loc_18001A5C9
0x18001a546  lea     rcx, [rbp+arg_0]
0x18001a54a  mov     r9d, 2; dwFlags
0x18001a550  mov     [rsp+78h+pcbData], rcx; pcbData
0x18001a555  lea     r8, aTenantid; "TenantId"
0x18001a55c  mov     rcx, [rbp+hkey]; hkey
0x18001a560  xor     edx, edx; lpSubKey
0x18001a562  mov     [rsp+78h+pvData], rax; pvData
0x18001a567  lea     rax, [rbp+pdwType]
0x18001a56b  mov     [rsp+78h+phkResult], rax; pdwType
0x18001a570  call    cs:__imp_RegGetValueW
0x18001a576  mov     ebx, eax
0x18001a578  test    ebx, ebx
0x18001a57a  jz      loc_18001A607
0x18001a580  lea     r9, aTenantid; "TenantId"
0x18001a587  mov     r8, r14; unsigned __int16 *
0x18001a58a  mov     ecx, ebx; unsigned int
0x18001a58c  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)
0x18001a591  lea     rcx, aTenantid; "TenantId"
0x18001a598  call    ?GetRegValueName@@YAPEAGPEBG@Z; GetRegValueName(ushort const *)
0x18001a59d  mov     r9, rax
0x18001a5a0  mov     dword ptr [rsp+78h+phkResult], ebx
0x18001a5a4  mov     r8, r14
0x18001a5a7  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18001a5ae  lea     rcx, aSCannotReadReg; "%s: Cannot read registry key value \"%s"...
0x18001a5b5  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18001a5ba  mov     rcx, [r15]; void *
0x18001a5bd  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18001a5c2  xor     edx, edx
0x18001a5c4  mov     [r15], rdx
0x18001a5c7  jmp     short loc_18001A609
0x18001a5c9  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18001a5d0  mov     ebx, 0Eh
0x18001a5d5  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18001a5dc  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18001a5e1  jmp     short loc_18001A580
0x18001a5e3  mov     rcx, rdi; this
0x18001a5e6  call    ?SubPath@RegistryPath@@QEBAPEBGXZ; RegistryPath::SubPath(void)
0x18001a5eb  mov     rdx, rax; lpSubKey
0x18001a5ee  mov     [rsp+78h+pvData], r15; unsigned __int16 **
0x18001a5f3  mov     r9, r14; unsigned __int16 *
0x18001a5f6  lea     r8, aTenantid; "TenantId"
0x18001a5fd  mov     rcx, r10; hkey
0x18001a600  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18001a605  mov     ebx, eax
0x18001a607  xor     edx, edx
0x18001a609  test    ebx, ebx
0x18001a60b  jnz     short loc_18001A625
  ... truncated ...
```
