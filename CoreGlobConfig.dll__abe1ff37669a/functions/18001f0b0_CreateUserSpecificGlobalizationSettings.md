# CreateUserSpecificGlobalizationSettings

- ea: `0x18001f0b0`
- end: `0x18001fa24`
- name: `CreateUserSpecificGlobalizationSettings`
- size: `2420`
- prototype: `int()`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002380`
- `0x180006cbc`
- `0x180008274`
- `0x180008294`
- `0x1800087e4`
- `0x180008870`
- `0x18001111c`
- `0x180011388`
- `0x180011428`
- `0x1800114e4`
- `0x180013ac4`
- `0x180014eb4`
- `0x180018bec`
- `0x180018c10`
- `0x18001d3ac`
- `0x18001ebcc`
- `0x18001f0b0`

## import_xrefs

- `ntdll!NtDeleteKey` at `0x18001f512`
- `ntdll!NtDeleteKey` at `0x18001f6d9`
- `ntdll!NtDeleteKey` at `0x18001f782`
- `ntdll!NtDeleteKey` at `0x18001f8cb`
- `ntdll!NtDeleteKey` at `0x18001f9e2`
- `ntdll!NtDeleteKey` at `0x18001f512`
- `ntdll!NtDeleteKey` at `0x18001f6d9`
- `ntdll!NtDeleteKey` at `0x18001f782`
- `ntdll!NtDeleteKey` at `0x18001f8cb`
- `ntdll!NtDeleteKey` at `0x18001f9e2`
- `ntdll!RtlPublishWnfStateData` at `0x18001f93a`
- `ntdll!RtlPublishWnfStateData` at `0x18001f971`
- `ntdll!RtlPublishWnfStateData` at `0x18001f93a`
- `ntdll!RtlPublishWnfStateData` at `0x18001f971`
- `KERNELBASE!QueryGlobalizationUserSettingsStatus` at `0x18001f438`
- `KERNELBASE!QueryGlobalizationUserSettingsStatus` at `0x18001f438`
- `KERNELBASE!OpenGlobalizationUserSettingsKey` at `0x18001f492`
- `KERNELBASE!OpenGlobalizationUserSettingsKey` at `0x18001f492`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f619`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f619`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f62a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f62a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f842`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f842`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001f507`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001f6ce`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001f777`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001f8c0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001f9d7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001f507`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001f6ce`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001f777`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001f8c0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001f9d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f575`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f5dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f6a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f6bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f750`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f765`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f899`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f8ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f9b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f9c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f575`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f5dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f6a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f6bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f750`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f765`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f899`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f8ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f9b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f9c5`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001f4d7`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18001f4d7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001f59f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001f59f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001f7b0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001f7b0`

## string_xrefs

- `0x18001f552`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x18001f5bb`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x18001f63f`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x18001f681`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x18001f725`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x18001f7c1`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x18001f901`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
int CreateUserSpecificGlobalizationSettings()
{
  int v0; // eax
  unsigned int v1; // r8d
  int v3; // eax
  unsigned int v4; // r8d
  int CurrentUserSid; // ebx
  unsigned int PersistedRegistryLocationW; // eax
  unsigned int v7; // r8d
  HLOCAL v8; // rcx
  BOOL v9; // ebx
  const char *v10; // r9
  HLOCAL v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rcx
  unsigned __int64 v14; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v16; // rax
  wil::details *v17; // rbx
  int v18; // esi
  __int64 v19; // rdx
  void *v20; // rdx
  HLOCAL v21; // rcx
  HLOCAL v22; // rcx
  int v23; // eax
  int v24; // edi
  void *v25; // rdx
  HLOCAL v26; // rcx
  HLOCAL v27; // rcx
  const char *v28; // r9
  int LastError; // eax
  unsigned int v30; // eax
  unsigned int v31; // r8d
  void *v32; // rdx
  HLOCAL v33; // rcx
  HLOCAL v34; // rcx
  int v35; // eax
  int v36; // eax
  unsigned int v37; // r8d
  int v38; // eax
  unsigned int v39; // r8d
  void *v40; // rdx
  HLOCAL v41; // rcx
  HLOCAL v42; // rcx
  int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL v47; // [rsp+60h] [rbp-A0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp-98h] BYREF
  int v49; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v51; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL *p_hMem; // [rsp+80h] [rbp-80h] BYREF
  LPWSTR StringSid; // [rsp+88h] [rbp-78h] BYREF
  char v54; // [rsp+90h] [rbp-70h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+98h] [rbp-68h] BYREF
  WCHAR StringSecurityDescriptor[200]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v57[264]; // [rsp+240h] [rbp+140h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+3A8h]

  wcscpy(
    StringSecurityDescriptor,
    L"D:(A;OICI;GA;;;SY)(A;OICI;GA;;;BA)(A;OICI;GA;;;OW)(A;OICI;GR;;;AC)(A;OICI;GR;;;S-1-15-3-1024-1065365936-1281604716-"
     "3511738428-1654721687-432734479-3232135806-4053264122-3456934681)S:(ML;OICI;NW;;;LW)");
  v49 = 0;
  v0 = QueryGlobalizationUserSettingsStatus(0, &v49);
  if ( v0 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x407,
             v1,
             (const char *)(unsigned int)v0,
             dwOptions);
  if ( v49 == 2 )
    return -2147024713;
  if ( !v49 )
    return -2147024846;
  hKey = 0;
  v51 = 0;
  v3 = OpenGlobalizationUserSettingsKey(131097, 0, &v51);
  if ( v3 >= 0 )
  {
    PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                   L"GlobalizationUserSettings",
                                   L"SYSTEM\\CurrentControlSet\\Control\\International",
                                   v57,
                                   520);
    if ( PersistedRegistryLocationW )
    {
      CurrentUserSid = wil::details::in1diag3::Return_Win32(
                         retaddr,
                         (void *)0x42E,
                         v7,
                         (const char *)PersistedRegistryLocationW,
                         0);
      goto LABEL_70;
    }
    hMem = 0;
    p_hMem = &hMem;
    StringSid = 0;
    v54 = 1;
    CurrentUserSid = GetCurrentUserSid((void **)&StringSid);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
    if ( CurrentUserSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x431,
        (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
        (const char *)(unsigned int)CurrentUserSid,
        0);
LABEL_14:
      v8 = hMem;
      hMem = 0;
      if ( v8 )
        LocalFree(v8);
      goto LABEL_70;
    }
    p_hMem = &v47;
    v47 = 0;
    StringSid = 0;
    v54 = 1;
    v9 = ConvertSidToStringSidW(hMem, &StringSid);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
    if ( !v9 )
    {
      CurrentUserSid = wil::details::in1diag3::Return_GetLastError(
                         retaddr,
                         (void *)0x434,
                         (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
                         v10);
      goto LABEL_18;
    }
    v12 = -1;
    v13 = -1;
    do
      ++v13;
    while ( v57[v13] );
    do
      ++v12;
    while ( *((_WORD *)v47 + v12) );
    v14 = (unsigned int)(v12 + v13 + 2);
    ProcessHeap = GetProcessHeap();
    v16 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2 * v14);
    v17 = (wil::details *)v16;
    if ( !v16 )
    {
      CurrentUserSid = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x438,
        (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
        (const char *)0x8007000ELL,
        0);
LABEL_18:
      v11 = v47;
      v47 = 0;
      if ( v11 )
        LocalFree(v11);
      goto LABEL_14;
    }
    v18 = StringCchCopyW(v16, v14, v57);
    if ( v18 < 0 )
    {
      v19 = 1082;
LABEL_27:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
        (const char *)(unsigned int)v18,
        0);
      wil::details::FreeProcessHeap(v17, v20);
      v21 = v47;
      v47 = 0;
      if ( v21 )
        LocalFree(v21);
      v22 = hMem;
      hMem = 0;
      if ( v22 )
        LocalFree(v22);
      CurrentUserSid = v18;
      goto LABEL_70;
    }
    v18 = StringCchCatW((unsigned __int16 *)v17, v14, L"\\");
    if ( v18 < 0 )
    {
      v19 = 1083;
      goto LABEL_27;
    }
    v23 = StringCchCatW((unsigned __int16 *)v17, v14, (const unsigned __int16 *)v47);
    v24 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x43C,
        (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
        (const char *)(unsigned int)v23,
        0);
LABEL_36:
      wil::details::FreeProcessHeap(v17, v25);
      v26 = v47;
      v47 = 0;
      if ( v26 )
        LocalFree(v26);
      v27 = hMem;
      hMem = 0;
      if ( v27 )
        LocalFree(v27);
      if ( hKey )
      {
        RegDeleteTreeW(hKey, 0);
        NtDeleteKey(hKey);
      }
      CurrentUserSid = v24;
      goto LABEL_70;
    }
    SecurityDescriptor = 0;
    memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
    {
      SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
      SecurityAttributes.nLength = 24;
      SecurityAttributes.bInheritHandle = 0;
      dwDisposition = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKey,
        0);
      v30 = RegCreateKeyExW(
              HKEY_LOCAL_MACHINE,
              (LPCWSTR)v17,
              0,
              0,
              0,
              0xF003Fu,
              &SecurityAttributes,
              &hKey,
              &dwDisposition);
      if ( !v30 )
      {
        if ( dwDisposition == 2 )
        {
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
            &hKey,
            0);
          wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&SecurityDescriptor);
          wil::details::FreeProcessHeap(v17, v32);
          v33 = v47;
          v47 = 0;
          if ( v33 )
            LocalFree(v33);
          v34 = hMem;
          hMem = 0;
          if ( v34 )
            LocalFree(v34);
          if ( hKey )
          {
            RegDeleteTreeW(hKey, 0);
            NtDeleteKey(hKey);
          }
          CurrentUserSid = -2147024713;
          goto LABEL_70;
        }
        v35 = CopyRegistryTree(v51, &qword_180028DA0, hKey, &qword_180028DA0);
        v24 = v35;
        if ( v35 >= 0 )
        {
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
            &hKey,
            0);
          v36 = RtlPublishWnfStateData(WNF_NLS_USER_UILANG_CHANGED, 0, 0, 0) | 0x10000000;
          if ( v36 < 0 )
            wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x45D, v37, (const char *)(unsigned int)v36, 0);
          v38 = RtlPublishWnfStateData(WNF_GLOB_GLOBALIZATION_PREFERENCES_CHANGED, 0, 0, 0) | 0x10000000;
          if ( v38 < 0 )
            wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x45F, v39, (const char *)(unsigned int)v38, 0);
          wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&SecurityDescriptor);
          wil::details::FreeProcessHeap(v17, v40);
          v41 = v47;
          v47 = 0;
          if ( v41 )
            LocalFree(v41);
          v42 = hMem;
          hMem = 0;
          if ( v42 )
            LocalFree(v42);
          if ( hKey )
          {
            RegDeleteTreeW(hKey, 0);
            NtDeleteKey(hKey);
          }
          CurrentUserSid = 0;
          goto LABEL_70;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x45A,
          (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
          (const char *)(unsigned int)v35,
          dwOptionsa);
        goto LABEL_46;
      }
      LastError = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x451, v31, (const char *)v30, dwOptionsa);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x441,
                    (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
                    v28);
    }
    v24 = LastError;
LABEL_46:
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&SecurityDescriptor);
    goto LABEL_36;
  }
  CurrentUserSid = wil::details::in1diag3::Return_NtStatus(
                     retaddr,
                     (void *)0x41A,
                     v4,
                     (const char *)(unsigned int)v3,
                     dwOptions);
LABEL_70:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v51);
  return CurrentUserSid;
}

```

## disassembly

```asm
0x18001f0b0  push    rbp
0x18001f0b2  push    rbx
0x18001f0b3  push    rsi
0x18001f0b4  push    rdi
0x18001f0b5  push    r12
0x18001f0b7  push    r13
0x18001f0b9  push    r14
0x18001f0bb  push    r15
0x18001f0bd  lea     rbp, [rsp-368h]
0x18001f0c5  sub     rsp, 468h
0x18001f0cc  mov     rax, cs:__security_cookie
0x18001f0d3  xor     rax, rsp
0x18001f0d6  mov     [rbp+3A0h+var_50], rax
0x18001f0dd  mov     dword ptr [rbp+3A0h+StringSecurityDescriptor], 3A0044h
0x18001f0e4  mov     [rbp+3A0h+var_3EC], 410028h
0x18001f0eb  mov     [rbp+3A0h+var_3E8], 4F003Bh
0x18001f0f2  mov     [rbp+3A0h+var_3E4], 430049h
0x18001f0f9  mov     [rbp+3A0h+var_3E0], 3B0049h
0x18001f100  mov     [rbp+3A0h+var_3DC], 410047h
0x18001f107  mov     [rbp+3A0h+var_3D8], 3B003Bh
0x18001f10e  mov     [rbp+3A0h+var_3D4], 53003Bh
0x18001f115  mov     [rbp+3A0h+var_3D0], 290059h
0x18001f11c  mov     [rbp+3A0h+var_3CC], 410028h
0x18001f123  mov     [rbp+3A0h+var_3C8], 4F003Bh
0x18001f12a  mov     [rbp+3A0h+var_3C4], 430049h
0x18001f131  mov     [rbp+3A0h+var_3C0], 3B0049h
0x18001f138  mov     [rbp+3A0h+var_3BC], 410047h
0x18001f13f  mov     [rbp+3A0h+var_3B8], 3B003Bh
0x18001f146  mov     [rbp+3A0h+var_3B4], 42003Bh
0x18001f14d  mov     [rbp+3A0h+var_3B0], 290041h
0x18001f154  mov     [rbp+3A0h+var_3AC], 410028h
0x18001f15b  mov     [rbp+3A0h+var_3A8], 4F003Bh
0x18001f162  mov     [rbp+3A0h+var_3A4], 430049h
0x18001f169  mov     [rbp+3A0h+var_3A0], 3B0049h
0x18001f170  mov     [rbp+3A0h+var_39C], 410047h
0x18001f177  mov     [rbp+3A0h+var_398], 3B003Bh
0x18001f17e  mov     [rbp+3A0h+var_394], 4F003Bh
0x18001f185  mov     [rbp+3A0h+var_390], 290057h
0x18001f18c  mov     [rbp+3A0h+var_38C], 410028h
0x18001f193  mov     [rbp+3A0h+var_388], 4F003Bh
0x18001f19a  mov     [rbp+3A0h+var_384], 430049h
0x18001f1a1  mov     [rbp+3A0h+var_380], 3B0049h
0x18001f1a8  mov     [rbp+3A0h+var_37C], 520047h
0x18001f1af  mov     [rbp+3A0h+var_378], 3B003Bh
0x18001f1b6  mov     [rbp+3A0h+var_374], 41003Bh
0x18001f1bd  mov     [rbp+3A0h+var_370], 290043h
0x18001f1c4  mov     [rbp+3A0h+var_36C], 410028h
0x18001f1cb  mov     [rbp+3A0h+var_368], 4F003Bh
0x18001f1d2  mov     [rbp+3A0h+var_364], 430049h
0x18001f1d9  mov     [rbp+3A0h+var_360], 3B0049h
0x18001f1e0  mov     [rbp+3A0h+var_35C], 520047h
0x18001f1e7  mov     [rbp+3A0h+var_358], 3B003Bh
0x18001f1ee  mov     [rbp+3A0h+var_354], 53003Bh
0x18001f1f5  mov     [rbp+3A0h+var_350], 31002Dh
0x18001f1fc  mov     [rbp+3A0h+var_34C], 31002Dh
0x18001f203  mov     [rbp+3A0h+var_348], 2D0035h
0x18001f20a  mov     [rbp+3A0h+var_344], 2D0033h
0x18001f211  mov     [rbp+3A0h+var_340], 300031h
0x18001f218  mov     [rbp+3A0h+var_33C], 340032h
0x18001f21f  mov     [rbp+3A0h+var_338], 31002Dh
0x18001f226  mov     [rbp+3A0h+var_334], 360030h
0x18001f22d  mov     [rbp+3A0h+var_330], 330035h
0x18001f234  mov     [rbp+3A0h+var_32C], 350036h
0x18001f23b  mov     [rbp+3A0h+var_328], 330039h
0x18001f242  mov     [rbp+3A0h+var_324], 2D0036h
0x18001f249  mov     [rbp+3A0h+var_320], 320031h
0x18001f253  mov     [rbp+3A0h+var_31C], 310038h
0x18001f25d  mov     [rbp+3A0h+var_318], 300036h
0x18001f267  mov     [rbp+3A0h+var_314], 370034h
0x18001f271  mov     [rbp+3A0h+var_310], 360031h
0x18001f27b  mov     [rbp+3A0h+var_30C], 33002Dh
0x18001f285  mov     [rbp+3A0h+var_308], 310035h
0x18001f28f  mov     [rbp+3A0h+var_304], 370031h
0x18001f299  mov     [rbp+3A0h+var_300], 380033h
0x18001f2a3  mov     [rbp+3A0h+var_2FC], 320034h
0x18001f2ad  mov     [rbp+3A0h+var_2F8], 2D0038h
0x18001f2b7  mov     [rbp+3A0h+var_2F4], 360031h
0x18001f2c1  mov     [rbp+3A0h+var_2F0], 340035h
0x18001f2cb  mov     [rbp+3A0h+var_2EC], 320037h
0x18001f2d5  mov     [rbp+3A0h+var_2E8], 360031h
0x18001f2df  mov     [rbp+3A0h+var_2E4], 370038h
0x18001f2e9  mov     [rbp+3A0h+var_2E0], 34002Dh
0x18001f2f3  mov     [rbp+3A0h+var_2DC], 320033h
0x18001f2fd  mov     [rbp+3A0h+var_2D8], 330037h
0x18001f307  mov     [rbp+3A0h+var_2D4], 340034h
0x18001f311  mov     [rbp+3A0h+var_2D0], 390037h
0x18001f31b  mov     [rbp+3A0h+var_2CC], 33002Dh
0x18001f325  mov     [rbp+3A0h+var_2C8], 330032h
0x18001f32f  mov     [rbp+3A0h+var_2C4], 310032h
0x18001f339  mov     [rbp+3A0h+var_2C0], 350033h
0x18001f343  mov     [rbp+3A0h+var_2BC], 300038h
0x18001f34d  mov     [rbp+3A0h+var_2B8], 2D0036h
0x18001f357  mov     [rbp+3A0h+var_2B4], 300034h
0x18001f361  mov     [rbp+3A0h+var_2B0], 330035h
0x18001f36b  xor     r14d, r14d
0x18001f36e  mov     [rbp+3A0h+var_2AC], 360032h
0x18001f378  lea     rdx, [rsp+4A0h+var_430]
0x18001f37d  mov     [rsp+4A0h+var_430], r14d
0x18001f382  xor     ecx, ecx
0x18001f384  mov     [rbp+3A0h+var_2A8], 310034h
0x18001f38e  mov     [rbp+3A0h+var_2A4], 320032h
0x18001f398  mov     [rbp+3A0h+var_2A0], 33002Dh
0x18001f3a2  mov     [rbp+3A0h+var_29C], 350034h
0x18001f3ac  mov     [rbp+3A0h+var_298], 390036h
0x18001f3b6  mov     [rbp+3A0h+var_294], 340033h
0x18001f3c0  mov     [rbp+3A0h+var_290], 380036h
0x18001f3ca  mov     [rbp+3A0h+var_28C], 290031h
0x18001f3d4  mov     [rbp+3A0h+var_288], 3A0053h
0x18001f3de  mov     [rbp+3A0h+var_284], 4D0028h
0x18001f3e8  mov     [rbp+3A0h+var_280], 3B004Ch
0x18001f3f2  mov     [rbp+3A0h+var_27C], 49004Fh
0x18001f3fc  mov     [rbp+3A0h+var_278], 490043h
0x18001f406  mov     [rbp+3A0h+var_274], 4E003Bh
0x18001f410  mov     [rbp+3A0h+var_270], 3B0057h
0x18001f41a  mov     [rbp+3A0h+var_26C], 3B003Bh
0x18001f424  mov     [rbp+3A0h+var_268], 57004Ch
0x18001f42e  mov     [rbp+3A0h+var_264], 29h ; ')'
0x18001f438  call    cs:__imp_QueryGlobalizationUserSettingsStatus
0x18001f43e  test    eax, eax
0x18001f440  jns     short loc_18001F45B
0x18001f442  mov     rcx, [rbp+3A8h]; this
0x18001f449  mov     r9d, eax; char *
0x18001f44c  mov     edx, 407h; void *
0x18001f451  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001f456  jmp     loc_18001FA01
0x18001f45b  mov     eax, [rsp+4A0h+var_430]
0x18001f45f  cmp     eax, 2
0x18001f462  jnz     short loc_18001F46E
0x18001f464  mov     eax, 800700B7h
0x18001f469  jmp     loc_18001FA01
0x18001f46e  test    eax, eax
0x18001f470  jnz     short loc_18001F47C
0x18001f472  mov     eax, 80070032h
0x18001f477  jmp     loc_18001FA01
0x18001f47c  lea     r8, [rsp+4A0h+var_428]
0x18001f481  mov     [rsp+4A0h+hKey], r14
0x18001f486  xor     edx, edx
0x18001f488  mov     [rsp+4A0h+var_428], r14
0x18001f48d  mov     ecx, 20019h
0x18001f492  call    cs:__imp_OpenGlobalizationUserSettingsKey
0x18001f498  test    eax, eax
0x18001f49a  jns     short loc_18001F4B7
0x18001f49c  mov     rcx, [rbp+3A8h]; this
0x18001f4a3  mov     r9d, eax; char *
0x18001f4a6  mov     edx, 41Ah; void *
0x18001f4ab  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001f4b0  mov     ebx, eax
0x18001f4b2  jmp     loc_18001F9EB
0x18001f4b7  mov     r9d, 208h
0x18001f4bd  mov     qword ptr [rsp+4A0h+dwOptions], r14; int
0x18001f4c2  lea     r8, [rbp+3A0h+var_260]
0x18001f4c9  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Int"...
0x18001f4d0  lea     rcx, aGlobalizationu; "GlobalizationUserSettings"
0x18001f4d7  call    cs:__imp_GetPersistedRegistryLocationW
0x18001f4dd  test    eax, eax
0x18001f4df  jz      short loc_18001F51D
0x18001f4e1  mov     rcx, [rbp+3A8h]; this
0x18001f4e8  mov     r9d, eax; char *
0x18001f4eb  mov     edx, 42Eh; void *
0x18001f4f0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001f4f5  mov     ebx, eax
0x18001f4f7  mov     rcx, [rsp+4A0h+hKey]; hKey
0x18001f4fc  test    rcx, rcx
0x18001f4ff  jz      loc_18001F9EB
0x18001f505  xor     edx, edx; lpSubKey
0x18001f507  call    cs:__imp_RegDeleteTreeW
0x18001f50d  mov     rcx, [rsp+4A0h+hKey]; KeyHandle
0x18001f512  call    cs:__imp_NtDeleteKey
0x18001f518  jmp     loc_18001F9EB
0x18001f51d  lea     rax, [rsp+4A0h+hMem]
0x18001f522  mov     [rsp+4A0h+hMem], r14
0x18001f527  lea     rcx, [rbp+3A0h+StringSid]; void **
0x18001f52b  mov     [rbp+3A0h+var_420], rax
0x18001f52f  mov     [rbp+3A0h+StringSid], r14
0x18001f533  mov     [rbp+3A0h+var_410], 1
0x18001f537  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x18001f53c  lea     rcx, [rbp+3A0h+var_420]
0x18001f540  mov     ebx, eax
0x18001f542  call    ??1?$out_param_t@V?$unique_ptr@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001f547  test    ebx, ebx
0x18001f549  jns     short loc_18001F580
0x18001f54b  mov     rcx, [rbp+3A8h]; this
0x18001f552  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18001f559  mov     r9d, ebx; char *
0x18001f55c  mov     edx, 431h; void *
0x18001f561  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f566  mov     rcx, [rsp+4A0h+hMem]; hMem
0x18001f56b  mov     [rsp+4A0h+hMem], r14
0x18001f570  test    rcx, rcx
0x18001f573  jz      short loc_18001F4F7
0x18001f575  call    cs:__imp_LocalFree
0x18001f57b  jmp     loc_18001F4F7
0x18001f580  mov     rcx, [rsp+4A0h+hMem]; Sid
0x18001f585  lea     rax, [rsp+4A0h+var_440]
0x18001f58a  lea     rdx, [rbp+3A0h+StringSid]; StringSid
0x18001f58e  mov     [rbp+3A0h+var_420], rax
0x18001f592  mov     [rsp+4A0h+var_440], r14
0x18001f597  mov     [rbp+3A0h+StringSid], r14
0x18001f59b  mov     [rbp+3A0h+var_410], 1
0x18001f59f  call    cs:__imp_ConvertSidToStringSidW
0x18001f5a5  lea     rcx, [rbp+3A0h+var_420]
0x18001f5a9  mov     ebx, eax
0x18001f5ab  call    ??1?$out_param_t@V?$unique_ptr@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001f5b0  test    ebx, ebx
0x18001f5b2  jnz     short loc_18001F5E5
0x18001f5b4  mov     rcx, [rbp+3A8h]; this
0x18001f5bb  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18001f5c2  mov     edx, 434h; void *
0x18001f5c7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001f5cc  mov     ebx, eax
0x18001f5ce  mov     rcx, [rsp+4A0h+var_440]; hMem
0x18001f5d3  mov     [rsp+4A0h+var_440], r14
0x18001f5d8  test    rcx, rcx
0x18001f5db  jz      short loc_18001F566
0x18001f5dd  call    cs:__imp_LocalFree
0x18001f5e3  jmp     short loc_18001F566
0x18001f5e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f5e9  lea     rdx, [rbp+3A0h+var_260]
0x18001f5f0  mov     rcx, rax
0x18001f5f3  inc     rcx
0x18001f5f6  cmp     [rdx+rcx*2], r14w
0x18001f5fb  jnz     short loc_18001F5F3
0x18001f5fd  mov     rdx, [rsp+4A0h+var_440]
0x18001f602  inc     rax
0x18001f605  cmp     [rdx+rax*2], r14w
0x18001f60a  jnz     short loc_18001F602
0x18001f60c  lea     rdi, [rcx+2]
0x18001f610  add     rdi, rax
0x18001f613  mov     edi, edi
0x18001f615  lea     rbx, [rdi+rdi]
0x18001f619  call    cs:__imp_GetProcessHeap
0x18001f61f  mov     r8, rbx; dwBytes
0x18001f622  mov     edx, 8; dwFlags
0x18001f627  mov     rcx, rax; hHeap
0x18001f62a  call    cs:__imp_HeapAlloc
0x18001f630  mov     rbx, rax
0x18001f633  test    rax, rax
0x18001f636  jnz     short loc_18001F65D
0x18001f638  mov     rcx, [rbp+3A8h]; this
0x18001f63f  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18001f646  mov     ebx, 8007000Eh
0x18001f64b  mov     edx, 438h; void *
0x18001f650  mov     r9d, ebx; char *
0x18001f653  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f658  jmp     loc_18001F5CE
0x18001f65d  lea     r8, [rbp+3A0h+var_260]; unsigned __int16 *
0x18001f664  mov     rdx, rdi; unsigned __int64
0x18001f667  mov     rcx, rbx; unsigned __int16 *
0x18001f66a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001f66f  mov     esi, eax
0x18001f671  test    eax, eax
0x18001f673  jns     short loc_18001F6E6
0x18001f675  mov     edx, 43Ah; void *
0x18001f67a  mov     rcx, [rbp+3A8h]; this
0x18001f681  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18001f688  mov     r9d, esi; char *
0x18001f68b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f690  mov     rcx, rbx; this
0x18001f693  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18001f698  mov     rcx, [rsp+4A0h+var_440]; hMem
0x18001f69d  mov     [rsp+4A0h+var_440], r14
0x18001f6a2  test    rcx, rcx
0x18001f6a5  jz      short loc_18001F6AD
0x18001f6a7  call    cs:__imp_LocalFree
0x18001f6ad  mov     rcx, [rsp+4A0h+hMem]; hMem
0x18001f6b2  mov     [rsp+4A0h+hMem], r14
0x18001f6b7  test    rcx, rcx
0x18001f6ba  jz      short loc_18001F6C2
0x18001f6bc  call    cs:__imp_LocalFree
0x18001f6c2  mov     rcx, [rsp+4A0h+hKey]; hKey
0x18001f6c7  test    rcx, rcx
0x18001f6ca  jz      short loc_18001F6DF
0x18001f6cc  xor     edx, edx; lpSubKey
0x18001f6ce  call    cs:__imp_RegDeleteTreeW
0x18001f6d4  mov     rcx, [rsp+4A0h+hKey]; KeyHandle
0x18001f6d9  call    cs:__imp_NtDeleteKey
0x18001f6df  mov     ebx, esi
0x18001f6e1  jmp     loc_18001F9EB
0x18001f6e6  lea     r8, asc_180028050; "\\"
0x18001f6ed  mov     rdx, rdi; unsigned __int64
0x18001f6f0  mov     rcx, rbx; unsigned __int16 *
0x18001f6f3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001f6f8  mov     esi, eax
0x18001f6fa  test    eax, eax
0x18001f6fc  jns     short loc_18001F708
0x18001f6fe  mov     edx, 43Bh
0x18001f703  jmp     loc_18001F67A
0x18001f708  mov     r8, [rsp+4A0h+var_440]; unsigned __int16 *
0x18001f70d  mov     rdx, rdi; unsigned __int64
0x18001f710  mov     rcx, rbx; unsigned __int16 *
0x18001f713  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001f718  mov     edi, eax
0x18001f71a  test    eax, eax
0x18001f71c  jns     short loc_18001F78F
0x18001f71e  mov     rcx, [rbp+3A8h]; this
0x18001f725  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18001f72c  mov     r9d, eax; char *
0x18001f72f  mov     edx, 43Ch; void *
0x18001f734  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f739  mov     rcx, rbx; this
  ... truncated ...
```
