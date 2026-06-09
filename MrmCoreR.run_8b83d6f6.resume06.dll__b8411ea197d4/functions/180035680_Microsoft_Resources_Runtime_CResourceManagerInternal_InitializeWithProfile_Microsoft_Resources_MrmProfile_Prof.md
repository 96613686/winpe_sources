# Microsoft::Resources::Runtime::CResourceManagerInternal::InitializeWithProfile(Microsoft::Resources::MrmProfile::ProfileType,ushort const *,ushort const *,ushort const *)

- ea: `0x180035680`
- end: `0x180035b65`
- name: `?InitializeWithProfile@CResourceManagerInternal@Runtime@Resources@Microsoft@@QEAAJW4ProfileType@MrmProfile@34@PEBG11@Z`
- size: `1253`
- prototype: `int __high(enum Microsoft::Resources::MrmProfile::ProfileType, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `8`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032b50`
- `0x180035fe0`
- `0x180036dc0`
- `0x180052d2c`
- `0x18007a0e0`
- `0x18007ae10`
- `0x1800a9318`
- `0x1800a9370`

## callees

- `0x180015944`
- `0x180017960`
- `0x18001916c`
- `0x180027270`
- `0x180028ad0`
- `0x18002c8d0`
- `0x18002cfd0`
- `0x18003274c`
- `0x180034650`
- `0x180035680`
- `0x180035d4c`
- `0x180035e8c`
- `0x180036180`
- `0x180036290`
- `0x1800739f4`
- `0x180083ad4`
- `0x1800862f0`
- `0x180086f7c`
- `0x18008fcec`
- `0x18009b300`
- `0x1800a4688`
- `0x1800c5010`

## import_xrefs

- `KERNELBASE!GetCurrentPackageFullName` at `0x1800358d9`
- `KERNELBASE!GetCurrentPackageFullName` at `0x1800358d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800356da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800356da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003588f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035930`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035986`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035a52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035a61`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003588f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035930`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035986`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035a52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035a61`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800359cd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800359cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Resources::Runtime::CResourceManagerInternal::InitializeWithProfile(
        __int64 a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  struct _RTL_CRITICAL_SECTION *v9; // rdi
  __int64 v10; // rdx
  int v11; // eax
  unsigned int v12; // esi
  int FilenameFromPackageNameForInit; // eax
  const unsigned __int16 *v14; // rcx
  int v15; // eax
  int Instance; // eax
  bool v17; // dl
  bool v18; // r8
  int v19; // eax
  int PriFile; // eax
  LONG CurrentPackageFullName; // eax
  int CurrentDependentPackages; // eax
  int v24; // eax
  Microsoft::Resources *v25; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  struct _RTL_CRITICAL_SECTION *v27; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 packageFullNameLength; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE *v29; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v30[24]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE *v31; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v32[24]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR packageFullName[128]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  *(_DWORD *)(a1 + 192) = a2;
  if ( (*(_BYTE *)(a1 + 40) & 1) == 0 )
    return 2147943647LL;
  v9 = (struct _RTL_CRITICAL_SECTION *)(a1 + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v27 = v9;
  if ( (*(_BYTE *)(a1 + 40) & 1) == 0 )
  {
    if ( v9 )
      LeaveCriticalSection(v9);
    return 2147943647LL;
  }
  v11 = Microsoft::Resources::MrmProfile::ChooseDefaultProfile(a2, v10, a4, a3);
  v12 = v11;
  if ( v11 == -2147023728 || v11 == -2147009760 || v11 == -2147024886 || v11 == -2147024809 )
  {
    MrtRuntimeTelemetry::LoadError(a4);
    if ( v9 )
      LeaveCriticalSection(v9);
    return v12;
  }
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x104,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerinternal.cpp",
      (const char *)(unsigned int)v11,
      a5);
    MrtRuntimeTelemetry::LoadError(a4);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v27);
    return v12;
  }
  DefStringResult_InitBuf(v30);
  v29 = v30;
  if ( a3 && a2 != 10 )
    goto LABEL_18;
  FilenameFromPackageNameForInit = Microsoft::Resources::Runtime::CResourceManagerInternal::_GetFilenameFromPackageNameForInit(
                                     (Microsoft::Resources::Runtime::CResourceManagerInternal *)v30,
                                     a4,
                                     *(struct Microsoft::Resources::MrmProfile **)(a1 + 176),
                                     (struct Microsoft::Resources::StringResult *)&v29);
  v12 = FilenameFromPackageNameForInit;
  if ( FilenameFromPackageNameForInit < 0 )
  {
    if ( FilenameFromPackageNameForInit == -2147009737 )
    {
      Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v29);
      MrtRuntimeTelemetry::LoadError(a4);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v27);
      return 2147957559LL;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10B,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerinternal.cpp",
      (const char *)(unsigned int)FilenameFromPackageNameForInit,
      a5);
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v29);
    MrtRuntimeTelemetry::LoadError(a4);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v27);
    return v12;
  }
  if ( v29 && (*(_QWORD *)v29 || !*((_DWORD *)v29 + 2)) && (*((_DWORD *)v29 + 2) || !*(_QWORD *)v29) )
  {
    v14 = (const unsigned __int16 *)*((_QWORD *)v29 + 2);
    v15 = 0;
  }
  else
  {
    v14 = 0;
    v15 = -2147024809;
  }
  a3 = 0;
  if ( v15 >= 0 )
    a3 = v14;
LABEL_18:
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD))(**(_QWORD **)(a1 + 176) + 248LL))(
          *(_QWORD *)(a1 + 176),
          a3,
          0) )
  {
    MrtRuntimeTelemetry::LoadError(a3);
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v29);
    MrtRuntimeTelemetry::LoadError(a4);
    if ( v9 )
      LeaveCriticalSection(v9);
    return 2147942405LL;
  }
  Instance = Microsoft::Resources::UnifiedResourceView::CreateInstance(
               *(struct Microsoft::Resources::CoreProfile **)(a1 + 176),
               (struct Microsoft::Resources::UnifiedResourceView **)(a1 + 184));
  v12 = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x116,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerinternal.cpp",
      (const char *)(unsigned int)Instance,
      a5);
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v29);
    MrtRuntimeTelemetry::LoadError(a4);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v27);
    return v12;
  }
  v19 = Microsoft::Resources::Runtime::CResourceManagerInternal::_Initialize(
          (Microsoft::Resources::Runtime::CResourceManagerInternal *)a1,
          v17,
          v18);
  v12 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerinternal.cpp",
      (const char *)(unsigned int)v19,
      a5);
    goto LABEL_23;
  }
  bIgnoreCase = (int)a4;
  PriFile = Microsoft::Resources::Runtime::CResourceManagerInternal::LoadPriFile(a1, 0);
  v12 = PriFile;
  if ( PriFile >= 0 )
  {
    if ( a2 != 9 && a2 != 3
      || !a4
      || (memset_0(packageFullName, 0, sizeof(packageFullName)),
          packageFullNameLength = 128,
          CurrentPackageFullName = GetCurrentPackageFullName(&packageFullNameLength, packageFullName),
          CurrentPackageFullName != 15700)
      && (CurrentPackageFullName
       || (v24 = CompareStringOrdinal(a4, -1, packageFullName, -1, 1),
           !(unsigned int)IntToComparison((unsigned int)(v24 - 2)))) )
    {
      CurrentDependentPackages = Microsoft::Resources::Runtime::CResourceManagerInternal::_LoadCurrentDependentPackages(
                                   a1,
                                   1,
                                   a1,
                                   a3);
      v12 = CurrentDependentPackages;
      if ( CurrentDependentPackages >= 0 )
        goto LABEL_39;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x136,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerinternal.cpp",
        (const char *)(unsigned int)CurrentDependentPackages,
        bIgnoreCase);
    }
    if ( (v12 & 0x80000000) != 0 )
      goto LABEL_23;
LABEL_39:
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v29);
    if ( v9 )
      LeaveCriticalSection(v9);
    return 0;
  }
  if ( PriFile == -2147024894 && a2 == 9 )
    goto LABEL_39;
LABEL_23:
  *(_DWORD *)(a1 + 40) |= 0x20u;
  if ( v12 == -2147024891 )
  {
    Microsoft::Resources::StringResult::StringResult((Microsoft::Resources::StringResult *)&v31);
    v31 = v32;
    if ( (int)DefStringResult_InitRef(v32) >= 0
      && (Microsoft::Resources::StringResult::Contains((Microsoft::Resources::StringResult *)&v31, L"WindowsApps")
       || Microsoft::Resources::StringResult::Contains((Microsoft::Resources::StringResult *)&v31, L"SystemApps"))
      && !Microsoft::Resources::InShutdownOrLogoff(v25) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v31);
  }
  if ( a2 == 1 && v12 + 2147024894 <= 1 )
  {
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v29);
    MrtRuntimeTelemetry::LoadError(a4);
    goto LABEL_27;
  }
  if ( (v12 & 0x80000000) == 0 )
    goto LABEL_39;
  if ( v12 != -2147024894 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15C,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerinternal.cpp",
      (const char *)v12,
      bIgnoreCase);
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v29);
    MrtRuntimeTelemetry::LoadError(a4);
LABEL_27:
    if ( v9 )
      LeaveCriticalSection(v9);
    return v12;
  }
  Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v29);
  MrtRuntimeTelemetry::LoadError(a4);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v27);
  return 2147942402LL;
}

```

## disassembly

```asm
0x180035680  mov     [rsp-8+arg_8], rbx
0x180035685  push    rbp
0x180035686  push    rsi
0x180035687  push    rdi
0x180035688  push    r12
0x18003568a  push    r13
0x18003568c  push    r14
0x18003568e  push    r15
0x180035690  lea     rbp, [rsp-90h]
0x180035698  sub     rsp, 190h
0x18003569f  mov     rax, cs:__security_cookie
0x1800356a6  xor     rax, rsp
0x1800356a9  mov     [rbp+0C0h+var_40], rax
0x1800356b0  mov     r14, r9
0x1800356b3  mov     r12, r8
0x1800356b6  mov     r13d, edx
0x1800356b9  mov     r15, rcx
0x1800356bc  mov     rbx, qword ptr [rbp+0C0h+arg_20]
0x1800356c3  mov     [rcx+0C0h], edx
0x1800356c9  test    byte ptr [rcx+28h], 1
0x1800356cd  jz      loc_180035A37
0x1800356d3  lea     rdi, [rcx+30h]
0x1800356d7  mov     rcx, rdi; lpCriticalSection
0x1800356da  call    cs:__imp_EnterCriticalSection
0x1800356e0  mov     [rsp+1C0h+var_190], rdi
0x1800356e5  test    byte ptr [r15+28h], 1
0x1800356ea  jz      loc_180035A32
0x1800356f0  lea     rax, [r15+0B0h]
0x1800356f7  mov     [rsp+1C0h+var_198], rax
0x1800356fc  mov     qword ptr [rsp+1C0h+bIgnoreCase], rbx; int
0x180035701  mov     r9, r12
0x180035704  mov     r8, r14
0x180035707  mov     ecx, r13d
0x18003570a  call    ?ChooseDefaultProfile@MrmProfile@Resources@Microsoft@@SAJW4ProfileType@123@W4_MrmPlatformVersionInternal@23@PEBG22PEAPEAV123@@Z; Microsoft::Resources::MrmProfile::ChooseDefaultProfile(Microsoft::Resources::MrmProfile::ProfileType,Microsoft::Resources::_MrmPlatformVersionInternal,ushort const *,ushort const *,ushort const *,Microsoft::Resources::MrmProfile * *)
0x18003570f  mov     esi, eax
0x180035711  cmp     eax, 80070490h
0x180035716  jz      loc_180035A41
0x18003571c  cmp     eax, 80073B20h
0x180035721  jz      loc_180035A41
0x180035727  cmp     eax, 8007000Ah
0x18003572c  jz      loc_180035A41
0x180035732  cmp     eax, 80070057h
0x180035737  jz      loc_180035A41
0x18003573d  xor     ebx, ebx
0x18003573f  test    eax, eax
0x180035741  js      loc_180035A69
0x180035747  lea     rcx, [rsp+1C0h+var_178]
0x18003574c  call    DefStringResult_InitBuf
0x180035751  lea     rcx, [rsp+1C0h+var_178]; this
0x180035756  mov     [rsp+1C0h+var_180], rcx
0x18003575b  test    r12, r12
0x18003575e  jnz     loc_18003589D
0x180035764  lea     r9, [rsp+1C0h+var_180]; struct Microsoft::Resources::StringResult *
0x180035769  mov     r8, [r15+0B0h]; struct Microsoft::Resources::MrmProfile *
0x180035770  mov     rdx, r14; unsigned __int16 *
0x180035773  call    ?_GetFilenameFromPackageNameForInit@CResourceManagerInternal@Runtime@Resources@Microsoft@@AEAAJPEBGPEAVMrmProfile@34@PEAVStringResult@34@@Z; Microsoft::Resources::Runtime::CResourceManagerInternal::_GetFilenameFromPackageNameForInit(ushort const *,Microsoft::Resources::MrmProfile *,Microsoft::Resources::StringResult *)
0x180035778  mov     esi, eax
0x18003577a  test    eax, eax
0x18003577c  js      loc_180035A9D
0x180035782  mov     rax, [rsp+1C0h+var_180]
0x180035787  test    rax, rax
0x18003578a  jz      loc_180035994
0x180035790  cmp     [rax], rbx
0x180035793  jnz     short loc_18003579E
0x180035795  cmp     [rax+8], ebx
0x180035798  ja      loc_180035994
0x18003579e  cmp     [rax+8], ebx
0x1800357a1  jnz     short loc_1800357AC
0x1800357a3  cmp     [rax], rbx
0x1800357a6  jnz     loc_180035994
0x1800357ac  mov     rcx, [rax+10h]
0x1800357b0  mov     eax, ebx
0x1800357b2  mov     r12, rbx
0x1800357b5  test    eax, eax
0x1800357b7  cmovns  r12, rcx
0x1800357bb  lea     rsi, [r15+0B0h]
0x1800357c2  mov     rcx, [rsi]
0x1800357c5  mov     rax, [rcx]
0x1800357c8  xor     r8d, r8d
0x1800357cb  mov     rdx, r12
0x1800357ce  mov     rax, [rax+0F8h]
0x1800357d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800357da  test    al, al
0x1800357dc  jz      loc_180035963
0x1800357e2  lea     rdx, [r15+0B8h]; struct Microsoft::Resources::UnifiedResourceView **
0x1800357e9  mov     rcx, [rsi]; struct Microsoft::Resources::CoreProfile *
0x1800357ec  call    ?CreateInstance@UnifiedResourceView@Resources@Microsoft@@SAJPEAVCoreProfile@23@PEAPEAV123@@Z; Microsoft::Resources::UnifiedResourceView::CreateInstance(Microsoft::Resources::CoreProfile *,Microsoft::Resources::UnifiedResourceView * *)
0x1800357f1  mov     esi, eax
0x1800357f3  test    eax, eax
0x1800357f5  js      loc_180035ACF
0x1800357fb  mov     rcx, r15; this
0x1800357fe  call    ?_Initialize@CResourceManagerInternal@Runtime@Resources@Microsoft@@AEAAJ_N0@Z; Microsoft::Resources::Runtime::CResourceManagerInternal::_Initialize(bool,bool)
0x180035803  mov     esi, eax
0x180035805  mov     rcx, [rbp+0C8h]; this
0x18003580c  test    eax, eax
0x18003580e  js      loc_180035B0D
0x180035814  mov     r8d, 2
0x18003581a  cmp     r13d, 1
0x18003581e  cmovnz  r8d, ebx
0x180035822  mov     [rsp+1C0h+var_198], rbx
0x180035827  mov     qword ptr [rsp+1C0h+bIgnoreCase], r14; int
0x18003582c  mov     r9, r12
0x18003582f  xor     edx, edx
0x180035831  mov     rcx, r15
0x180035834  call    ?LoadPriFile@CResourceManagerInternal@Runtime@Resources@Microsoft@@QEAAJW4_MRMPROFILE_PHASE@34@W4LoadPriFlags@34@PEBG22@Z; Microsoft::Resources::Runtime::CResourceManagerInternal::LoadPriFile(Microsoft::Resources::_MRMPROFILE_PHASE,Microsoft::Resources::LoadPriFlags,ushort const *,ushort const *,ushort const *)
0x180035839  mov     esi, eax
0x18003583b  test    eax, eax
0x18003583d  jns     short loc_1800358AC
0x18003583f  cmp     eax, 80070002h
0x180035844  jz      loc_1800359A1
0x18003584a  or      dword ptr [r15+28h], 20h
0x18003584f  cmp     esi, 80070005h
0x180035855  jz      loc_1800C20E6
0x18003585b  cmp     r13d, 1
0x18003585f  jnz     loc_1800359E8
0x180035865  lea     eax, [rsi+7FF8FFFEh]
0x18003586b  cmp     eax, r13d
0x18003586e  ja      loc_1800359E8
0x180035874  lea     rcx, [rsp+1C0h+var_180]; this
0x180035879  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x18003587e  mov     rcx, r14; unsigned __int16 *
0x180035881  call    ?LoadError@MrtRuntimeTelemetry@@SAXPEBG@Z; MrtRuntimeTelemetry::LoadError(ushort const *)
0x180035886  nop
0x180035887  test    rdi, rdi
0x18003588a  jz      short loc_180035896
0x18003588c  mov     rcx, rdi; lpCriticalSection
0x18003588f  call    cs:__imp_LeaveCriticalSection
0x180035895  nop
0x180035896  mov     eax, esi
0x180035898  jmp     loc_180035939
0x18003589d  cmp     r13d, 0Ah
0x1800358a1  jnz     loc_1800357BB
0x1800358a7  jmp     loc_180035764
0x1800358ac  cmp     r13d, 9
0x1800358b0  jnz     short loc_1800358F3
0x1800358b2  test    r14, r14
0x1800358b5  jz      short loc_1800358F9
0x1800358b7  xor     edx, edx; Val
0x1800358b9  mov     r8d, 100h; Size
0x1800358bf  lea     rcx, [rbp+0C0h+packageFullName]; void *
0x1800358c3  call    memset_0
0x1800358c8  mov     [rsp+1C0h+packageFullNameLength], 80h
0x1800358d0  lea     rdx, [rbp+0C0h+packageFullName]; packageFullName
0x1800358d4  lea     rcx, [rsp+1C0h+packageFullNameLength]; packageFullNameLength
0x1800358d9  call    cs:__imp_GetCurrentPackageFullName
0x1800358df  cmp     eax, 3D54h
0x1800358e4  jnz     loc_1800359B0
0x1800358ea  test    esi, esi
0x1800358ec  jns     short loc_18003591D
0x1800358ee  jmp     loc_18003584A
0x1800358f3  cmp     r13d, 3
0x1800358f7  jz      short loc_1800358B2
0x1800358f9  mov     r9, r12
0x1800358fc  mov     r8, r15
0x1800358ff  mov     edx, 1
0x180035904  mov     rcx, r15
0x180035907  call    ?_LoadCurrentDependentPackages@CResourceManagerInternal@Runtime@Resources@Microsoft@@AEAAJW4_MRMPROFILE_PHASE@34@PEBV1234@PEBG@Z; Microsoft::Resources::Runtime::CResourceManagerInternal::_LoadCurrentDependentPackages(Microsoft::Resources::_MRMPROFILE_PHASE,Microsoft::Resources::Runtime::CResourceManagerInternal const *,ushort const *)
0x18003590c  mov     esi, eax
0x18003590e  mov     rcx, [rbp+0C8h]; this
0x180035915  test    eax, eax
0x180035917  js      loc_180035B26
0x18003591d  lea     rcx, [rsp+1C0h+var_180]; this
0x180035922  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x180035927  nop
0x180035928  test    rdi, rdi
0x18003592b  jz      short loc_180035937
0x18003592d  mov     rcx, rdi; lpCriticalSection
0x180035930  call    cs:__imp_LeaveCriticalSection
0x180035936  nop
0x180035937  xor     eax, eax
0x180035939  mov     rcx, [rbp+0C0h+var_40]
0x180035940  xor     rcx, rsp; StackCookie
0x180035943  call    __security_check_cookie
0x180035948  mov     rbx, [rsp+1C0h+arg_8]
0x180035950  add     rsp, 190h
0x180035957  pop     r15
0x180035959  pop     r14
0x18003595b  pop     r13
0x18003595d  pop     r12
0x18003595f  pop     rdi
0x180035960  pop     rsi
0x180035961  pop     rbp
0x180035962  retn
0x180035963  mov     rcx, r12; unsigned __int16 *
0x180035966  call    ?LoadError@MrtRuntimeTelemetry@@SAXPEBG@Z; MrtRuntimeTelemetry::LoadError(ushort const *)
0x18003596b  lea     rcx, [rsp+1C0h+var_180]; this
0x180035970  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x180035975  mov     rcx, r14; unsigned __int16 *
0x180035978  call    ?LoadError@MrtRuntimeTelemetry@@SAXPEBG@Z; MrtRuntimeTelemetry::LoadError(ushort const *)
0x18003597d  nop
0x18003597e  test    rdi, rdi
0x180035981  jz      short loc_18003598D
0x180035983  mov     rcx, rdi; lpCriticalSection
0x180035986  call    cs:__imp_LeaveCriticalSection
0x18003598c  nop
0x18003598d  mov     eax, 80070005h
0x180035992  jmp     short loc_180035939
0x180035994  mov     rcx, rbx
0x180035997  mov     eax, 80070057h
0x18003599c  jmp     loc_1800357B2
0x1800359a1  cmp     r13d, 9
0x1800359a5  jz      loc_18003591D
0x1800359ab  jmp     loc_18003584A
0x1800359b0  test    eax, eax
0x1800359b2  jnz     loc_1800358F9
0x1800359b8  mov     [rsp+1C0h+bIgnoreCase], 1; bIgnoreCase
0x1800359c0  or      edx, 0FFFFFFFFh; cchCount1
0x1800359c3  mov     r9d, edx; cchCount2
0x1800359c6  lea     r8, [rbp+0C0h+packageFullName]; lpString2
0x1800359ca  mov     rcx, r14; lpString1
0x1800359cd  call    cs:__imp_CompareStringOrdinal
0x1800359d3  lea     ecx, [rax-2]
0x1800359d6  call    _IntToComparison
0x1800359db  test    eax, eax
0x1800359dd  jz      loc_1800358F9
0x1800359e3  jmp     loc_1800358EA
0x1800359e8  test    esi, esi
0x1800359ea  jns     loc_18003591D
0x1800359f0  mov     r15d, 80070002h
0x1800359f6  cmp     esi, r15d
0x1800359f9  jz      loc_180035B3F
0x1800359ff  mov     rcx, [rbp+0C8h]; this
0x180035a06  mov     r9d, esi; char *
0x180035a09  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x180035a10  mov     edx, 15Ch; void *
0x180035a15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035a1a  lea     rcx, [rsp+1C0h+var_180]; this
0x180035a1f  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x180035a24  mov     rcx, r14; unsigned __int16 *
0x180035a27  call    ?LoadError@MrtRuntimeTelemetry@@SAXPEBG@Z; MrtRuntimeTelemetry::LoadError(ushort const *)
0x180035a2c  nop
0x180035a2d  jmp     loc_180035887
0x180035a32  test    rdi, rdi
0x180035a35  jnz     short loc_180035A5E
0x180035a37  mov     eax, 800704DFh
0x180035a3c  jmp     loc_180035939
0x180035a41  mov     rcx, r14; unsigned __int16 *
0x180035a44  call    ?LoadError@MrtRuntimeTelemetry@@SAXPEBG@Z; MrtRuntimeTelemetry::LoadError(ushort const *)
0x180035a49  nop
0x180035a4a  test    rdi, rdi
0x180035a4d  jz      short loc_180035A59
0x180035a4f  mov     rcx, rdi; lpCriticalSection
0x180035a52  call    cs:__imp_LeaveCriticalSection
0x180035a58  nop
0x180035a59  jmp     loc_180035896
0x180035a5e  mov     rcx, rdi; lpCriticalSection
0x180035a61  call    cs:__imp_LeaveCriticalSection
0x180035a67  jmp     short loc_180035A37
0x180035a69  mov     rcx, [rbp+0C8h]; this
0x180035a70  mov     r9d, esi; char *
0x180035a73  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x180035a7a  mov     edx, 104h; void *
0x180035a7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035a84  mov     rcx, r14; unsigned __int16 *
0x180035a87  call    ?LoadError@MrtRuntimeTelemetry@@SAXPEBG@Z; MrtRuntimeTelemetry::LoadError(ushort const *)
0x180035a8c  nop
0x180035a8d  lea     rcx, [rsp+1C0h+var_190]
0x180035a92  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180035a97  nop
0x180035a98  jmp     loc_180035896
0x180035a9d  mov     ebx, 80073B37h
0x180035aa2  cmp     esi, ebx
0x180035aa4  jnz     loc_1800C20A8
0x180035aaa  lea     rcx, [rsp+1C0h+var_180]; this
0x180035aaf  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x180035ab4  mov     rcx, r14; unsigned __int16 *
0x180035ab7  call    ?LoadError@MrtRuntimeTelemetry@@SAXPEBG@Z; MrtRuntimeTelemetry::LoadError(ushort const *)
0x180035abc  nop
0x180035abd  lea     rcx, [rsp+1C0h+var_190]
0x180035ac2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180035ac7  nop
0x180035ac8  mov     eax, ebx
0x180035aca  jmp     loc_180035939
0x180035acf  mov     rcx, [rbp+0C8h]; this
0x180035ad6  mov     r9d, esi; char *
0x180035ad9  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x180035ae0  mov     edx, 116h; void *
0x180035ae5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035aea  lea     rcx, [rsp+1C0h+var_180]; this
0x180035aef  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x180035af4  mov     rcx, r14; unsigned __int16 *
0x180035af7  call    ?LoadError@MrtRuntimeTelemetry@@SAXPEBG@Z; MrtRuntimeTelemetry::LoadError(ushort const *)
0x180035afc  nop
0x180035afd  lea     rcx, [rsp+1C0h+var_190]
0x180035b02  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180035b07  nop
0x180035b08  jmp     loc_180035896
0x180035b0d  mov     r9d, eax; char *
0x180035b10  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x180035b17  mov     edx, 119h; void *
0x180035b1c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035b21  jmp     loc_18003584A
0x180035b26  mov     r9d, eax; char *
0x180035b29  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x180035b30  mov     edx, 136h; void *
0x180035b35  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035b3a  jmp     loc_1800358EA
0x180035b3f  lea     rcx, [rsp+1C0h+var_180]; this
0x180035b44  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x180035b49  mov     rcx, r14; unsigned __int16 *
  ... truncated ...
```
