# UpdateDefaultGlobalizationSettings

- ea: `0x180020490`
- end: `0x180020a48`
- name: `UpdateDefaultGlobalizationSettings`
- size: `1464`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

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
- `0x180013ac4`
- `0x180014eb4`
- `0x180018bec`
- `0x180018c10`
- `0x18001afcc`
- `0x18001d3ac`
- `0x18001ebcc`
- `0x180020490`

## import_xrefs

- `ntdll!RtlIsMultiSessionSku` at `0x1800204c1`
- `ntdll!RtlIsMultiSessionSku` at `0x1800204c1`
- `ntdll!RtlPublishWnfStateData` at `0x18002092b`
- `ntdll!RtlPublishWnfStateData` at `0x180020962`
- `ntdll!RtlPublishWnfStateData` at `0x18002092b`
- `ntdll!RtlPublishWnfStateData` at `0x180020962`
- `KERNELBASE!QueryGlobalizationUserSettingsStatus` at `0x180020599`
- `KERNELBASE!QueryGlobalizationUserSettingsStatus` at `0x180020599`
- `KERNELBASE!OpenGlobalizationUserSettingsKey` at `0x1800205d7`
- `KERNELBASE!OpenGlobalizationUserSettingsKey` at `0x1800205d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002073e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002073e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002074f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002074f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800208a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800208a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020552`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002057d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800206a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800207b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800207d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020846`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020865`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800209a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800209c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800209f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020a16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020552`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002057d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800206a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800207b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800207d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020846`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020865`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800209a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800209c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800209f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020a16`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180020623`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180020623`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180020564`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180020564`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180020664`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180020664`

## string_xrefs

- `0x1800204d5`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x18002052f`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x180020681`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x1800206dd`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x18002078d`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x18002081b`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x180020901`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x1800209d6`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
__int64 __fastcall UpdateDefaultGlobalizationSettings(PSID Sid)
{
  int CurrentUserSid; // ebx
  HLOCAL v4; // rcx
  HLOCAL v5; // rcx
  int v6; // eax
  unsigned int v7; // r8d
  int v8; // eax
  unsigned int v9; // r8d
  int v10; // eax
  unsigned int PersistedRegistryLocationW; // eax
  unsigned int v12; // r8d
  BOOL v13; // ebx
  const char *v14; // r9
  HLOCAL v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  unsigned __int64 v18; // rdx
  __int64 v19; // rdx
  unsigned __int64 v20; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v22; // rax
  wil::details *v23; // rbx
  int v24; // esi
  __int64 v25; // rdx
  void *v26; // rdx
  HLOCAL v27; // rcx
  HLOCAL v28; // rcx
  int v29; // eax
  unsigned int v30; // edi
  void *v31; // rdx
  HLOCAL v32; // rcx
  HLOCAL v33; // rcx
  unsigned int v34; // eax
  unsigned int v35; // r8d
  int v36; // eax
  int v37; // eax
  unsigned int v38; // r8d
  int v39; // eax
  unsigned int v40; // r8d
  void *v41; // rdx
  HLOCAL v42; // rcx
  HLOCAL v43; // rcx
  HLOCAL v44; // rcx
  HLOCAL v45; // rcx
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL v49; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v50; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v51; // [rsp+48h] [rbp-B8h] BYREF
  int v52; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v53; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL *p_hMem; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp-98h] BYREF
  char v56; // [rsp+70h] [rbp-90h]
  unsigned __int16 v57[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  if ( (unsigned __int8)RtlIsMultiSessionSku() )
  {
    CurrentUserSid = -2147024846;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46A,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)0x80070032LL,
      phkResult);
    return (unsigned int)CurrentUserSid;
  }
  hMem = 0;
  p_hMem = &hMem;
  StringSid = 0;
  v56 = 1;
  CurrentUserSid = GetCurrentUserSid((void **)&StringSid);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( CurrentUserSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46E,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)(unsigned int)CurrentUserSid,
      phkResult);
    goto LABEL_6;
  }
  if ( !IsWellKnownSid(hMem, WinLocalSystemSid) )
  {
    v5 = hMem;
    hMem = 0;
    if ( v5 )
      LocalFree(v5);
    return 2147942405LL;
  }
  v52 = 0;
  v6 = QueryGlobalizationUserSettingsStatus(0, &v52);
  if ( v6 < 0 )
  {
    CurrentUserSid = wil::details::in1diag3::Return_NtStatus(
                       retaddr,
                       (void *)0x479,
                       v7,
                       (const char *)(unsigned int)v6,
                       phkResult);
    goto LABEL_6;
  }
  if ( !v52 )
  {
    v50 = 0;
    v8 = OpenGlobalizationUserSettingsKey(0x2000000, 0, &v50);
    if ( v8 < 0 )
    {
      v10 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x482,
              v9,
              (const char *)(unsigned int)v8,
              phkResult);
LABEL_17:
      CurrentUserSid = v10;
LABEL_18:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v50);
LABEL_6:
      v4 = hMem;
      hMem = 0;
      if ( v4 )
        LocalFree(v4);
      return (unsigned int)CurrentUserSid;
    }
    PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                   L"GlobalizationUserSettings",
                                   L"SYSTEM\\CurrentControlSet\\Control\\International",
                                   v57,
                                   520);
    if ( PersistedRegistryLocationW )
    {
      v10 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x48A,
              v12,
              (const char *)PersistedRegistryLocationW,
              0);
      goto LABEL_17;
    }
    v49 = 0;
    p_hMem = &v49;
    StringSid = 0;
    v56 = 1;
    v13 = ConvertSidToStringSidW(Sid, &StringSid);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
    if ( !v13 )
    {
      CurrentUserSid = wil::details::in1diag3::Return_GetLastError(
                         retaddr,
                         (void *)0x48D,
                         (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
                         v14);
      goto LABEL_23;
    }
    v53 = 0;
    CurrentUserSid = StringCchLengthW((const unsigned __int16 *)v49, 0x7FFFFFFFu, &v53);
    if ( CurrentUserSid < 0 )
    {
      v16 = 1168;
LABEL_27:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
        (const char *)(unsigned int)CurrentUserSid,
        0);
LABEL_23:
      v15 = v49;
      v49 = 0;
      if ( v15 )
        LocalFree(v15);
      goto LABEL_18;
    }
    v17 = -1;
    do
      ++v17;
    while ( v57[v17] );
    v18 = v53 + v17;
    if ( v53 + v17 < v53 )
    {
      v19 = 1169;
LABEL_70:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
        (const char *)0x80070216LL,
        0);
      v44 = v49;
      v49 = 0;
      if ( v44 )
        LocalFree(v44);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v50);
      v45 = hMem;
      hMem = 0;
      if ( v45 )
        LocalFree(v45);
      return 2147942934LL;
    }
    v20 = v18 + 2;
    if ( v18 + 2 < v18 )
    {
      v19 = 1170;
      goto LABEL_70;
    }
    if ( !is_mul_ok(v20, 2u) )
    {
      v19 = 1173;
      goto LABEL_70;
    }
    ProcessHeap = GetProcessHeap();
    v22 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, (unsigned int)(2 * v20));
    v23 = (wil::details *)v22;
    if ( !v22 )
    {
      CurrentUserSid = -2147024882;
      v16 = 1176;
      goto LABEL_27;
    }
    v24 = StringCchCopyW(v22, v20, v57);
    if ( v24 < 0 )
    {
      v25 = 1178;
LABEL_39:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
        (const char *)(unsigned int)v24,
        0);
      wil::details::FreeProcessHeap(v23, v26);
      v27 = v49;
      v49 = 0;
      if ( v27 )
        LocalFree(v27);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v50);
      v28 = hMem;
      hMem = 0;
      if ( v28 )
        LocalFree(v28);
      return (unsigned int)v24;
    }
    v24 = StringCchCatW((unsigned __int16 *)v23, v20, L"\\");
    if ( v24 < 0 )
    {
      v25 = 1179;
      goto LABEL_39;
    }
    v29 = StringCchCatW((unsigned __int16 *)v23, v20, (const unsigned __int16 *)v49);
    v30 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x49C,
        (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
        (const char *)(unsigned int)v29,
        0);
LABEL_48:
      wil::details::FreeProcessHeap(v23, v31);
      v32 = v49;
      v49 = 0;
      if ( v32 )
        LocalFree(v32);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v50);
      v33 = hMem;
      hMem = 0;
      if ( v33 )
        LocalFree(v33);
      return v30;
    }
    v51 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v51,
      0);
    v34 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v23, 0, 0x20019u, &v51);
    if ( v34 - 2 > 1 )
    {
      if ( v34 )
      {
        v30 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x4A9, v35, (const char *)v34, phkResulta);
LABEL_56:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v51);
        goto LABEL_48;
      }
      v36 = CopyRegistryTree(v51, &qword_180028DA0, v50, &qword_180028DA0);
      v30 = v36;
      if ( v36 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4AB,
          (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
          (const char *)(unsigned int)v36,
          phkResulta);
        goto LABEL_56;
      }
      v37 = RtlPublishWnfStateData(WNF_NLS_USER_UILANG_CHANGED, 0, 0, 0) | 0x10000000;
      if ( v37 < 0 )
        wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x4AD, v38, (const char *)(unsigned int)v37, 0);
      v39 = RtlPublishWnfStateData(WNF_GLOB_GLOBALIZATION_PREFERENCES_CHANGED, 0, 0, 0) | 0x10000000;
      if ( v39 < 0 )
        wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x4AF, v40, (const char *)(unsigned int)v39, 0);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v51);
    wil::details::FreeProcessHeap(v23, v41);
    v42 = v49;
    v49 = 0;
    if ( v42 )
      LocalFree(v42);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v50);
  }
  v43 = hMem;
  hMem = 0;
  if ( v43 )
    LocalFree(v43);
  return 0;
}

```

## disassembly

```asm
0x180020490  mov     [rsp-8+arg_8], rbx
0x180020495  mov     [rsp-8+arg_10], rsi
0x18002049a  push    rbp
0x18002049b  push    rdi
0x18002049c  push    r14
0x18002049e  lea     rbp, [rsp-1A0h]
0x1800204a6  sub     rsp, 2A0h
0x1800204ad  mov     rax, cs:__security_cookie
0x1800204b4  xor     rax, rsp
0x1800204b7  mov     [rbp+1B0h+var_20], rax
0x1800204be  mov     rdi, rcx
0x1800204c1  call    cs:__imp_RtlIsMultiSessionSku
0x1800204c7  xor     r14d, r14d
0x1800204ca  test    al, al
0x1800204cc  jz      short loc_1800204F5
0x1800204ce  mov     rcx, [rbp+1B8h]; this
0x1800204d5  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x1800204dc  mov     ebx, 80070032h
0x1800204e1  mov     edx, 46Ah; void *
0x1800204e6  mov     r9d, ebx; char *
0x1800204e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800204ee  mov     eax, ebx
0x1800204f0  jmp     loc_180020A21
0x1800204f5  lea     rax, [rsp+2B0h+hMem]
0x1800204fa  mov     [rsp+2B0h+hMem], r14
0x1800204ff  lea     rcx, [rsp+2B0h+StringSid]; void **
0x180020504  mov     [rsp+2B0h+var_250], rax
0x180020509  mov     [rsp+2B0h+StringSid], r14
0x18002050e  mov     [rsp+2B0h+var_240], 1
0x180020513  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x180020518  lea     rcx, [rsp+2B0h+var_250]
0x18002051d  mov     ebx, eax
0x18002051f  call    ??1?$out_param_t@V?$unique_ptr@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180020524  test    ebx, ebx
0x180020526  jns     short loc_18002055A
0x180020528  mov     rcx, [rbp+1B8h]; this
0x18002052f  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180020536  mov     r9d, ebx; char *
0x180020539  mov     edx, 46Eh; void *
0x18002053e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020543  mov     rcx, [rsp+2B0h+hMem]; hMem
0x180020548  mov     [rsp+2B0h+hMem], r14
0x18002054d  test    rcx, rcx
0x180020550  jz      short loc_1800204EE
0x180020552  call    cs:__imp_LocalFree
0x180020558  jmp     short loc_1800204EE
0x18002055a  mov     rcx, [rsp+2B0h+hMem]; pSid
0x18002055f  mov     edx, 16h; WellKnownSidType
0x180020564  call    cs:__imp_IsWellKnownSid
0x18002056a  test    eax, eax
0x18002056c  jnz     short loc_18002058D
0x18002056e  mov     rcx, [rsp+2B0h+hMem]; hMem
0x180020573  mov     [rsp+2B0h+hMem], r14
0x180020578  test    rcx, rcx
0x18002057b  jz      short loc_180020583
0x18002057d  call    cs:__imp_LocalFree
0x180020583  mov     eax, 80070005h
0x180020588  jmp     loc_180020A21
0x18002058d  lea     rdx, [rsp+2B0h+var_260]
0x180020592  mov     [rsp+2B0h+var_260], r14d
0x180020597  xor     ecx, ecx
0x180020599  call    cs:__imp_QueryGlobalizationUserSettingsStatus
0x18002059f  test    eax, eax
0x1800205a1  jns     short loc_1800205BB
0x1800205a3  mov     rcx, [rbp+1B8h]; this
0x1800205aa  mov     r9d, eax; char *
0x1800205ad  mov     edx, 479h; void *
0x1800205b2  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800205b7  mov     ebx, eax
0x1800205b9  jmp     short loc_180020543
0x1800205bb  cmp     [rsp+2B0h+var_260], r14d
0x1800205c0  jnz     loc_1800209B1
0x1800205c6  lea     r8, [rsp+2B0h+var_270]
0x1800205cb  mov     [rsp+2B0h+var_270], r14
0x1800205d0  xor     edx, edx
0x1800205d2  mov     ecx, 2000000h
0x1800205d7  call    cs:__imp_OpenGlobalizationUserSettingsKey
0x1800205dd  test    eax, eax
0x1800205df  jns     short loc_180020606
0x1800205e1  mov     rcx, [rbp+1B8h]; this
0x1800205e8  mov     r9d, eax; char *
0x1800205eb  mov     edx, 482h; void *
0x1800205f0  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800205f5  mov     ebx, eax
0x1800205f7  lea     rcx, [rsp+2B0h+var_270]
0x1800205fc  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180020601  jmp     loc_180020543
0x180020606  mov     r9d, 208h
0x18002060c  mov     qword ptr [rsp+2B0h+phkResult], r14; int
0x180020611  lea     r8, [rbp+1B0h+var_230]
0x180020615  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Int"...
0x18002061c  lea     rcx, aGlobalizationu; "GlobalizationUserSettings"
0x180020623  call    cs:__imp_GetPersistedRegistryLocationW
0x180020629  test    eax, eax
0x18002062b  jz      short loc_180020643
0x18002062d  mov     rcx, [rbp+1B8h]; this
0x180020634  mov     r9d, eax; char *
0x180020637  mov     edx, 48Ah; void *
0x18002063c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180020641  jmp     short loc_1800205F5
0x180020643  lea     rax, [rsp+2B0h+var_278]
0x180020648  mov     [rsp+2B0h+var_278], r14
0x18002064d  lea     rdx, [rsp+2B0h+StringSid]; StringSid
0x180020652  mov     [rsp+2B0h+var_250], rax
0x180020657  mov     rcx, rdi; Sid
0x18002065a  mov     [rsp+2B0h+StringSid], r14
0x18002065f  mov     [rsp+2B0h+var_240], 1
0x180020664  call    cs:__imp_ConvertSidToStringSidW
0x18002066a  lea     rcx, [rsp+2B0h+var_250]
0x18002066f  mov     ebx, eax
0x180020671  call    ??1?$out_param_t@V?$unique_ptr@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180020676  test    ebx, ebx
0x180020678  jnz     short loc_1800206B2
0x18002067a  mov     rcx, [rbp+1B8h]; this
0x180020681  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180020688  mov     edx, 48Dh; void *
0x18002068d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180020692  mov     ebx, eax
0x180020694  mov     rcx, [rsp+2B0h+var_278]; hMem
0x180020699  mov     [rsp+2B0h+var_278], r14
0x18002069e  test    rcx, rcx
0x1800206a1  jz      loc_1800205F7
0x1800206a7  call    cs:__imp_LocalFree
0x1800206ad  jmp     loc_1800205F7
0x1800206b2  mov     rcx, [rsp+2B0h+var_278]; unsigned __int16 *
0x1800206b7  lea     r8, [rsp+2B0h+var_258]; unsigned __int64 *
0x1800206bc  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800206c1  mov     [rsp+2B0h+var_258], r14
0x1800206c6  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800206cb  mov     ebx, eax
0x1800206cd  test    eax, eax
0x1800206cf  jns     short loc_1800206EE
0x1800206d1  mov     edx, 490h; void *
0x1800206d6  mov     rcx, [rbp+1B8h]; this
0x1800206dd  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x1800206e4  mov     r9d, ebx; char *
0x1800206e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800206ec  jmp     short loc_180020694
0x1800206ee  lea     rax, [rbp+1B0h+var_230]
0x1800206f2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800206f6  inc     rcx
0x1800206f9  cmp     [rax+rcx*2], r14w
0x1800206fe  jnz     short loc_1800206F6
0x180020700  mov     rax, [rsp+2B0h+var_258]
0x180020705  lea     rdx, [rax+rcx]
0x180020709  cmp     rdx, rax
0x18002070c  jnb     short loc_180020718
0x18002070e  mov     edx, 491h
0x180020713  jmp     loc_1800209CF
0x180020718  lea     rdi, [rdx+2]
0x18002071c  cmp     rdi, rdx
0x18002071f  jnb     short loc_18002072B
0x180020721  mov     edx, 492h
0x180020726  jmp     loc_1800209CF
0x18002072b  mov     eax, 2
0x180020730  mul     rdi
0x180020733  test    rdx, rdx
0x180020736  jnz     loc_1800209CA
0x18002073c  mov     ebx, eax
0x18002073e  call    cs:__imp_GetProcessHeap
0x180020744  mov     r8d, ebx; dwBytes
0x180020747  mov     edx, 8; dwFlags
0x18002074c  mov     rcx, rax; hHeap
0x18002074f  call    cs:__imp_HeapAlloc
0x180020755  mov     rbx, rax
0x180020758  test    rax, rax
0x18002075b  jnz     short loc_18002076C
0x18002075d  mov     ebx, 8007000Eh
0x180020762  mov     edx, 498h
0x180020767  jmp     loc_1800206D6
0x18002076c  lea     r8, [rbp+1B0h+var_230]; unsigned __int16 *
0x180020770  mov     rdx, rdi; unsigned __int64
0x180020773  mov     rcx, rbx; unsigned __int16 *
0x180020776  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002077b  mov     esi, eax
0x18002077d  test    eax, eax
0x18002077f  jns     short loc_1800207DF
0x180020781  mov     edx, 49Ah; void *
0x180020786  mov     rcx, [rbp+1B8h]; this
0x18002078d  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180020794  mov     r9d, esi; char *
0x180020797  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002079c  mov     rcx, rbx; this
0x18002079f  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800207a4  mov     rcx, [rsp+2B0h+var_278]; hMem
0x1800207a9  mov     [rsp+2B0h+var_278], r14
0x1800207ae  test    rcx, rcx
0x1800207b1  jz      short loc_1800207B9
0x1800207b3  call    cs:__imp_LocalFree
0x1800207b9  lea     rcx, [rsp+2B0h+var_270]
0x1800207be  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800207c3  mov     rcx, [rsp+2B0h+hMem]; hMem
0x1800207c8  mov     [rsp+2B0h+hMem], r14
0x1800207cd  test    rcx, rcx
0x1800207d0  jz      short loc_1800207D8
0x1800207d2  call    cs:__imp_LocalFree
0x1800207d8  mov     eax, esi
0x1800207da  jmp     loc_180020A21
0x1800207df  lea     r8, asc_180028050; "\\"
0x1800207e6  mov     rdx, rdi; unsigned __int64
0x1800207e9  mov     rcx, rbx; unsigned __int16 *
0x1800207ec  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800207f1  mov     esi, eax
0x1800207f3  test    eax, eax
0x1800207f5  jns     short loc_1800207FE
0x1800207f7  mov     edx, 49Bh
0x1800207fc  jmp     short loc_180020786
0x1800207fe  mov     r8, [rsp+2B0h+var_278]; unsigned __int16 *
0x180020803  mov     rdx, rdi; unsigned __int64
0x180020806  mov     rcx, rbx; unsigned __int16 *
0x180020809  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002080e  mov     edi, eax
0x180020810  test    eax, eax
0x180020812  jns     short loc_180020872
0x180020814  mov     rcx, [rbp+1B8h]; this
0x18002081b  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180020822  mov     r9d, eax; char *
0x180020825  mov     edx, 49Ch; void *
0x18002082a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002082f  mov     rcx, rbx; this
0x180020832  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180020837  mov     rcx, [rsp+2B0h+var_278]; hMem
0x18002083c  mov     [rsp+2B0h+var_278], r14
0x180020841  test    rcx, rcx
0x180020844  jz      short loc_18002084C
0x180020846  call    cs:__imp_LocalFree
0x18002084c  lea     rcx, [rsp+2B0h+var_270]
0x180020851  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180020856  mov     rcx, [rsp+2B0h+hMem]; hMem
0x18002085b  mov     [rsp+2B0h+hMem], r14
0x180020860  test    rcx, rcx
0x180020863  jz      short loc_18002086B
0x180020865  call    cs:__imp_LocalFree
0x18002086b  mov     eax, edi
0x18002086d  jmp     loc_180020A21
0x180020872  xor     edx, edx
0x180020874  mov     [rsp+2B0h+var_268], r14
0x180020879  lea     rcx, [rsp+2B0h+var_268]
0x18002087e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180020883  lea     rax, [rsp+2B0h+var_268]
0x180020888  mov     r9d, 20019h; samDesired
0x18002088e  xor     r8d, r8d; ulOptions
0x180020891  mov     qword ptr [rsp+2B0h+phkResult], rax; int
0x180020896  mov     rdx, rbx; lpSubKey
0x180020899  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800208a0  call    cs:__imp_RegOpenKeyExW
0x1800208a6  lea     ecx, [rax-2]
0x1800208a9  cmp     ecx, 1
0x1800208ac  jbe     loc_180020980
0x1800208b2  test    eax, eax
0x1800208b4  jz      short loc_1800208DB
0x1800208b6  mov     rcx, [rbp+1B8h]; this
0x1800208bd  mov     r9d, eax; char *
0x1800208c0  mov     edx, 4A9h; void *
0x1800208c5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800208ca  mov     edi, eax
0x1800208cc  lea     rcx, [rsp+2B0h+var_268]
0x1800208d1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800208d6  jmp     loc_18002082F
0x1800208db  mov     r8, [rsp+2B0h+var_270]
0x1800208e0  lea     rdx, qword_180028DA0
0x1800208e7  mov     rcx, [rsp+2B0h+var_268]
0x1800208ec  mov     r9, rdx
0x1800208ef  call    CopyRegistryTree
0x1800208f4  mov     edi, eax
0x1800208f6  test    eax, eax
0x1800208f8  jns     short loc_180020917
0x1800208fa  mov     rcx, [rbp+1B8h]; this
0x180020901  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180020908  mov     r9d, eax; char *
0x18002090b  mov     edx, 4ABh; void *
0x180020910  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020915  jmp     short loc_1800208CC
0x180020917  mov     rcx, cs:WNF_NLS_USER_UILANG_CHANGED
0x18002091e  xor     r9d, r9d
0x180020921  xor     r8d, r8d
0x180020924  mov     qword ptr [rsp+2B0h+phkResult], r14; int
0x180020929  xor     edx, edx
0x18002092b  call    cs:__imp_RtlPublishWnfStateData
0x180020931  mov     edi, 10000000h
0x180020936  or      eax, edi
0x180020938  jge     short loc_18002094E
0x18002093a  mov     rcx, [rbp+1B8h]; this
0x180020941  mov     r9d, eax; char *
0x180020944  mov     edx, 4ADh; void *
0x180020949  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002094e  mov     rcx, cs:WNF_GLOB_GLOBALIZATION_PREFERENCES_CHANGED
0x180020955  xor     r9d, r9d
0x180020958  xor     r8d, r8d
0x18002095b  mov     qword ptr [rsp+2B0h+phkResult], r14; int
0x180020960  xor     edx, edx
0x180020962  call    cs:__imp_RtlPublishWnfStateData
0x180020968  or      eax, edi
0x18002096a  jge     short loc_180020980
0x18002096c  mov     rcx, [rbp+1B8h]; this
0x180020973  mov     r9d, eax; char *
0x180020976  mov     edx, 4AFh; void *
0x18002097b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020980  lea     rcx, [rsp+2B0h+var_268]
0x180020985  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
  ... truncated ...
```
