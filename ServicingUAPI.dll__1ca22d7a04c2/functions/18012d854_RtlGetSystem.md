# RtlGetSystem

- ea: `0x18012d854`
- end: `0x18012e1c4`
- name: `RtlGetSystem`
- size: `2416`
- prototype: ``
- caller_count: `4`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180112e48`
- `0x18011352c`
- `0x180113828`
- `0x18013dad0`

## callees

- `0x1800031d0`
- `0x180006198`
- `0x180030b68`
- `0x1800497c0`
- `0x180117064`
- `0x18011760c`
- `0x18011782c`
- `0x1801189d4`
- `0x180119dcc`
- `0x18011a15c`
- `0x18011aed0`
- `0x18011cda8`
- `0x18011e04c`
- `0x18011eb94`
- `0x18011f304`
- `0x1801206dc`
- `0x18012d854`
- `0x18013d978`
- `0x1801526d4`
- `0x1801bd010`

## import_xrefs

- `ntdll!LdrUnloadDll` at `0x18012da63`
- `ntdll!LdrUnloadDll` at `0x18012dbd9`
- `ntdll!LdrUnloadDll` at `0x18012dee2`
- `ntdll!LdrUnloadDll` at `0x18012e044`
- `ntdll!LdrUnloadDll` at `0x18012e0f5`
- `ntdll!LdrUnloadDll` at `0x18012da63`
- `ntdll!LdrUnloadDll` at `0x18012dbd9`
- `ntdll!LdrUnloadDll` at `0x18012dee2`
- `ntdll!LdrUnloadDll` at `0x18012e044`
- `ntdll!LdrUnloadDll` at `0x18012e0f5`

## string_xrefs

- `0x18012dc91`: `ConstructorData->RegistryLayers.Length > 0`

## pseudocode

```c
__int64 __fastcall RtlGetSystem(unsigned int a1, struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *a2, __int64 a3)
{
  struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *v6; // rdx
  _QWORD *v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // rcx
  int v10; // eax
  int TransactionCoordinator; // edi
  void (**v12)(void); // rax
  unsigned int v13; // r15d
  __int64 v14; // rcx
  void (__fastcall ***v15)(_QWORD); // rdx
  __int64 v16; // rsi
  void (__fastcall ***v17)(_QWORD); // rcx
  _QWORD *v18; // rcx
  void (__fastcall ***v19)(_QWORD); // rcx
  void (__fastcall ***v20)(_QWORD); // rcx
  void (__fastcall ***v21)(_QWORD); // rcx
  int v22; // eax
  struct Windows::Rtl::SystemImplementation::IRtlRegistryProvider *v23; // rsi
  _DWORD *v24; // rdi
  struct Windows::Rtl::SystemImplementation::IRtlFileSystemProvider *v25; // rbx
  struct Windows::Rtl::SystemImplementation::IRtlFileSystemProvider *v26; // rdx
  int v27; // eax
  unsigned int v28; // r14d
  void (__fastcall ***v29)(_QWORD); // rcx
  void (__fastcall ***v30)(_QWORD); // rcx
  void (__fastcall ***v31)(_QWORD); // rcx
  void (***v32)(void); // rbx
  int v33; // eax
  void (__fastcall ***v34)(_QWORD); // rcx
  void (__fastcall ***v35)(_QWORD); // rcx
  void (__fastcall ***v36)(_QWORD); // rcx
  void (__fastcall ***v38)(_QWORD); // rcx
  void (__fastcall ***v39)(_QWORD); // rcx
  void (__fastcall ***v40)(_QWORD); // rcx
  unsigned __int64 v41; // [rsp+58h] [rbp-A8h]
  void (***v42)(void); // [rsp+60h] [rbp-A0h] BYREF
  struct Windows::Rtl::SystemImplementation::IRtlFileSystemProvider *v43; // [rsp+68h] [rbp-98h] BYREF
  __int128 v44; // [rsp+70h] [rbp-90h] BYREF
  __int128 v45; // [rsp+80h] [rbp-80h]
  char v46; // [rsp+90h] [rbp-70h]
  int v47; // [rsp+94h] [rbp-6Ch]
  __int64 v48; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v49[4]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v50[4]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v51[4]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v52[4]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v53[4]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v54[4]; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v55[4]; // [rsp+160h] [rbp+60h] BYREF
  int v56; // [rsp+180h] [rbp+80h] BYREF
  __int64 v57; // [rsp+188h] [rbp+88h] BYREF
  int v58[2]; // [rsp+190h] [rbp+90h] BYREF
  void (__fastcall ***v59)(_QWORD); // [rsp+198h] [rbp+98h] BYREF
  PVOID BaseAddress; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v61; // [rsp+1A8h] [rbp+A8h] BYREF
  void (__fastcall ***v62)(_QWORD); // [rsp+1B0h] [rbp+B0h] BYREF
  int v63[14]; // [rsp+1C0h] [rbp+C0h] BYREF
  char v64; // [rsp+1F8h] [rbp+F8h]

  v56 = 0;
  Windows::WCP::Rtl::RtlGetFacilityTracingFlags((Windows::WCP::Rtl *)&Windows::WCP::Rtl::Facility_SIL, a2);
  v63[10] = 0;
  v64 = 0;
  v63[2] = 1;
  if ( (Windows::WCP::Rtl::RtlGetFacilityTracingFlags((Windows::WCP::Rtl *)&Windows::WCP::Rtl::Facility_SIL, v6) & 0xE) != 0 )
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::Arm(
      (int)v63,
      0,
      (int)&v56,
      (int)Windows::WCP::Rtl::RtlTraceFormat_PCNTSTATUS,
      0,
      (__int64)"Windows::Rtl::RtlGetSystem",
      (Windows::WCP::Rtl *)&Windows::WCP::Rtl::Facility_SIL,
      0,
      0,
      0,
      0,
      v41);
  if ( !a3 )
  {
    v49[1] = "Windows::Rtl::RtlGetSystem";
    v49[0] = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
    v7 = v49;
    v49[2] = 7858;
    v49[3] = "Not-null check failed: System";
LABEL_7:
    v56 = -1073741811;
    RtlReportErrorOrigination(v7, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    v8 = v56;
LABEL_101:
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(v63);
    return v8;
  }
  if ( (a1 & 0xFFFFFFF0) != 0 )
  {
    v50[1] = "Windows::Rtl::RtlGetSystem";
    v50[0] = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
    v7 = v50;
    v50[2] = 7859;
    v50[3] = "Valid flags check failed: Flags";
    goto LABEL_7;
  }
  v9 = a1 & 0xF;
  if ( (a1 & 0xF) != 0 && (((_DWORD)v9 - 1) & (unsigned int)v9) != 0 )
  {
    v51[1] = "Windows::Rtl::RtlGetSystem";
    v51[0] = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
    v7 = v51;
    v51[2] = 7860;
    v51[3] = "No more than one flag set check failed: __e";
    goto LABEL_7;
  }
  if ( !Windows::Rtl::SystemImplementation::g_pSystemIsolationLayerFromTest || a2 )
  {
    *(_QWORD *)v58 = 0;
    v57 = 0;
    v59 = 0;
    v44 = 0;
    v42 = 0;
    v45 = 0;
    BaseAddress = 0;
    LOWORD(v61) = 0;
    v46 = 0;
    v47 = 0;
    v48 = 0;
    TransactionCoordinator = Windows::Rtl::SystemImplementation::RtlGetTransactionCoordinator(&v42);
    if ( TransactionCoordinator < 0 )
    {
LABEL_16:
      v56 = TransactionCoordinator;
LABEL_17:
      if ( BaseAddress )
      {
        if ( LdrUnloadDll(BaseAddress) < 0 )
          __fastfail(7u);
        BaseAddress = 0;
      }
      if ( !v42 )
        goto LABEL_94;
      v12 = *v42;
      goto LABEL_93;
    }
    v13 = 0;
    if ( a2 )
    {
      v14 = *(_QWORD *)a2;
      if ( *(_QWORD *)a2 )
      {
        v62 = 0;
        TransactionCoordinator = (*(__int64 (__fastcall **)(__int64, GUID *, void (__fastcall ****)(_QWORD)))(*(_QWORD *)v14 + 8LL))(
                                   v14,
                                   &GUID_bf537349_9167_47f4_a8a8_df3c233df232,
                                   &v62);
        if ( TransactionCoordinator < 0
          || (v16 = ((__int64 (__fastcall *)(_QWORD))(*v62)[2])(v62),
              TransactionCoordinator = Windows::Rtl::SystemImplementation::CSystemIsolationLayer::GetProviders(
                                         v16,
                                         &v57,
                                         v58,
                                         &v59),
              TransactionCoordinator < 0) )
        {
          v15 = v62;
          v56 = TransactionCoordinator;
          if ( v62 )
          {
            v62 = 0;
            (**v15)(v15);
          }
          goto LABEL_17;
        }
        v17 = v62;
        v13 = *(_DWORD *)(v16 + 128);
        if ( v62 )
        {
          v62 = 0;
          (**v17)(v17);
        }
      }
      if ( !*(_QWORD *)v58 && !*((_QWORD *)a2 + 2) )
      {
        v52[1] = "Windows::Rtl::RtlGetSystem";
        v52[0] = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
        v18 = v52;
        v52[2] = 7916;
        v52[3] = "ConstructorData->FilesystemLayers.Length > 0";
LABEL_34:
        v56 = -1073741811;
        RtlReportErrorOrigination(v18, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
        v8 = v56;
LABEL_35:
        if ( BaseAddress )
        {
          if ( LdrUnloadDll(BaseAddress) < 0 )
            __fastfail(7u);
          BaseAddress = 0;
        }
        if ( v42 )
          ((void (__fastcall *)(void (***)(void)))**v42)(v42);
        v19 = v59;
        if ( v59 )
        {
          v59 = 0;
          (**v19)(v19);
        }
        v20 = (void (__fastcall ***)(_QWORD))v57;
        if ( v57 )
        {
          v57 = 0;
          (**v20)(v20);
        }
        v21 = *(void (__fastcall ****)(_QWORD))v58;
        if ( *(_QWORD *)v58 )
        {
          *(_QWORD *)v58 = 0;
          (**v21)(v21);
        }
        goto LABEL_101;
      }
      if ( !v57 && !*((_QWORD *)a2 + 4) )
      {
        v53[1] = "Windows::Rtl::RtlGetSystem";
        v53[0] = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
        v18 = v53;
        v53[2] = 7919;
        v53[3] = "ConstructorData->RegistryLayers.Length > 0";
        goto LABEL_34;
      }
      if ( !v59 && !*((_QWORD *)a2 + 6) )
      {
        v54[1] = "Windows::Rtl::RtlGetSystem";
        v54[0] = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
        v18 = v54;
        v54[2] = 7922;
        v54[3] = "ConstructorData->UserLayers.Length > 0";
        goto LABEL_34;
      }
      TransactionCoordinator = Windows::Rtl::SystemImplementation::CreateFilesystemProviderStack(
                                 0,
                                 v58[0],
                                 (int)a2 + 8,
                                 (int)v58,
                                 &BaseAddress,
                                 (__int64)&v61 + 1);
      if ( TransactionCoordinator < 0 )
        goto LABEL_16;
      TransactionCoordinator = Windows::Rtl::SystemImplementation::CreateRegistryProviderStack(
                                 0,
                                 v57,
                                 v58[0],
                                 (int)a2 + 24,
                                 (__int64)&v57,
                                 &BaseAddress,
                                 (__int64)&v61);
      if ( TransactionCoordinator < 0 )
        goto LABEL_16;
      v22 = Windows::Rtl::SystemImplementation::CreateUserProviderStack(v59, *(_QWORD *)v58, v57, (char *)a2 + 40, &v59);
      v8 = v22;
      if ( v22 < 0 )
      {
        v56 = v22;
        goto LABEL_35;
      }
    }
    else
    {
      v43 = 0;
      if ( !Windows::AutoNewPtr<Windows::Rtl::SystemImplementation::DirectFileSystemProvider>::Allocate<>(&v43) )
      {
        v55[1] = "Windows::Rtl::RtlGetSystem";
        v55[0] = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
        v55[2] = 7971;
        v55[3] = "Fs.Allocate()";
        v56 = -1073741801;
        RtlReportErrorOrigination(v55, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225495LL);
        v8 = v56;
        if ( v43 )
          (*(void (__fastcall **)(struct Windows::Rtl::SystemImplementation::IRtlFileSystemProvider *, __int64))(*(_QWORD *)v43 + 16LL))(
            v43,
            1);
        goto LABEL_35;
      }
      v23 = (struct Windows::Rtl::SystemImplementation::IRtlRegistryProvider *)operator new(0x10u);
      *((_DWORD *)v23 + 3) = 0;
      *(_QWORD *)v23 = &Windows::Rtl::SystemImplementation::DirectRegistryProvider::`vftable';
      *((_DWORD *)v23 + 2) = 1;
      v24 = operator new(0x30u);
      v24[3] = 0;
      *((_QWORD *)v24 + 3) = 0;
      v24[2] = 1;
      v25 = v43;
      v26 = v43;
      *(_QWORD *)v24 = &Windows::Rtl::SystemImplementation::DirectUserProvider::`vftable';
      *((_QWORD *)v24 + 2) = 0;
      *((_QWORD *)v24 + 4) = 0;
      *((_QWORD *)v24 + 5) = 0;
      v27 = Windows::Rtl::SystemImplementation::DirectUserProvider::Initialize(
              (Windows::Rtl::SystemImplementation::DirectUserProvider *)v24,
              v26,
              v23,
              0);
      v28 = v27;
      if ( v27 < 0 )
      {
        v56 = v27;
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v24 + 16LL))(v24, 1);
        (*(void (__fastcall **)(struct Windows::Rtl::SystemImplementation::IRtlRegistryProvider *, __int64))(*(_QWORD *)v23 + 16LL))(
          v23,
          1);
        if ( v25 )
          (*(void (__fastcall **)(struct Windows::Rtl::SystemImplementation::IRtlFileSystemProvider *, __int64))(*(_QWORD *)v25 + 16LL))(
            v25,
            1);
        if ( BaseAddress )
        {
          if ( LdrUnloadDll(BaseAddress) < 0 )
            __fastfail(7u);
          BaseAddress = 0;
        }
        if ( v42 )
          ((void (__fastcall *)(void (***)(void)))**v42)(v42);
        v29 = v59;
        if ( v59 )
        {
          v59 = 0;
          (**v29)(v29);
        }
        v30 = (void (__fastcall ***)(_QWORD))v57;
        if ( v57 )
        {
          v57 = 0;
          (**v30)(v30);
        }
        v31 = *(void (__fastcall ****)(_QWORD))v58;
        if ( *(_QWORD *)v58 )
        {
          *(_QWORD *)v58 = 0;
          (**v31)(v31);
        }
        v8 = v28;
        goto LABEL_101;
      }
      if ( *(_QWORD *)v58 )
        __debugbreak();
      *(_QWORD *)v58 = v25;
      if ( v57 )
        __debugbreak();
      v57 = (__int64)v23;
      if ( v59 )
        __debugbreak();
      v59 = (void (__fastcall ***)(_QWORD))v24;
    }
    *(_QWORD *)&v44 = *(_QWORD *)v58;
    *((_QWORD *)&v44 + 1) = v57;
    *(_QWORD *)&v45 = v59;
    if ( (_BYTE)v61 || (v46 = 0, BYTE1(v61)) )
      v46 = 1;
    v32 = v42;
    *((_QWORD *)&v45 + 1) = v42;
    v47 = Windows::Rtl::DetermineBitness(a1, v13);
    Windows::AutoGenericHandle<void *,0,&void Windows::Detail::CloseWithLdrUnloadDll(void *)>::operator=(
      &v48,
      &BaseAddress);
    v33 = Windows::Rtl::CRtlRefCountedObjectBase<Windows::Rtl::SystemImplementation::CSystemIsolationLayer,Windows::Rtl::IRtlSystemIsolationLayerWithPOQ,Windows::Rtl::IRtlSystemIsolationLayer,Windows::Rtl::IRtlSystemIsolationLayerPublic,Windows::Rtl::SystemImplementation::IRtlSystemIsolationLayerInternal,Windows::Rtl::IRtlSystemCreator,Windows::Rtl::Detail::CRtlRefCountedObjectBaseNoInterface>::CreateInstance<Windows::Rtl::SystemImplementation::CreateSILSource,Windows::Rtl::IRtlSystemIsolationLayer>(
            &v44,
            a3);
    TransactionCoordinator = v33;
    if ( v33 >= 0 )
    {
      Windows::Rtl::SystemImplementation::CreateSILSource::~CreateSILSource((Windows::Rtl::SystemImplementation::CreateSILSource *)&v44);
      if ( BaseAddress )
      {
        if ( LdrUnloadDll(BaseAddress) < 0 )
          __fastfail(7u);
        BaseAddress = 0;
      }
      if ( v32 )
        ((void (__fastcall *)(void (***)(void)))**v32)(v32);
      v38 = v59;
      if ( v59 )
      {
        v59 = 0;
        (**v38)(v38);
      }
      v39 = (void (__fastcall ***)(_QWORD))v57;
      if ( v57 )
      {
        v57 = 0;
        (**v39)(v39);
      }
      v40 = *(void (__fastcall ****)(_QWORD))v58;
      if ( *(_QWORD *)v58 )
      {
        *(_QWORD *)v58 = 0;
        (**v40)(v40);
      }
      goto LABEL_114;
    }
    v56 = v33;
    Windows::Rtl::SystemImplementation::CreateSILSource::~CreateSILSource((Windows::Rtl::SystemImplementation::CreateSILSource *)&v44);
    if ( BaseAddress )
    {
      if ( LdrUnloadDll(BaseAddress) < 0 )
        __fastfail(7u);
      BaseAddress = 0;
    }
    if ( !v32 )
    {
LABEL_94:
      v34 = v59;
      if ( v59 )
      {
        v59 = 0;
        (**v34)(v34);
      }
      v35 = (void (__fastcall ***)(_QWORD))v57;
      if ( v57 )
      {
        v57 = 0;
        (**v35)(v35);
      }
      v36 = *(void (__fastcall ****)(_QWORD))v58;
      if ( *(_QWORD *)v58 )
      {
        *(_QWORD *)v58 = 0;
        (**v36)(v36);
      }
      v8 = TransactionCoordinator;
      goto LABEL_101;
    }
    v12 = *v32;
LABEL_93:
    (*v12)();
    goto LABEL_94;
  }
  v10 = Windows::Rtl::IRtlObject::CreateRequiredInterface<Windows::Rtl::IRtlSystemIsolationLayer>(v9, a3);
  if ( v10 < 0 )
  {
    v56 = v10;
    v8 = v10;
    goto LABEL_101;
  }
LABEL_114:
  v64 = 1;
  Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(v63);
  return (unsigned int)v56;
}

```

## disassembly

```asm
0x18012d854  mov     [rsp-8+arg_18], rbx
0x18012d859  push    rbp
0x18012d85a  push    rsi
0x18012d85b  push    rdi
0x18012d85c  push    r12
0x18012d85e  push    r13
0x18012d860  push    r14
0x18012d862  push    r15
0x18012d864  lea     rbp, [rsp-250h]
0x18012d86c  sub     rsp, 350h
0x18012d873  mov     rax, cs:__security_cookie
0x18012d87a  xor     rax, rsp
0x18012d87d  mov     [rbp+280h+var_40], rax
0x18012d884  mov     r13d, ecx
0x18012d887  lea     rdi, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_SIL
0x18012d88e  xor     r14d, r14d
0x18012d891  mov     rcx, rdi; this
0x18012d894  mov     r12, r8
0x18012d897  mov     [rbp+280h+var_200], r14d
0x18012d89e  mov     rbx, rdx
0x18012d8a1  call    ?RtlGetFacilityTracingFlags@Rtl@WCP@Windows@@YAKPEAU_RTL_TRACING_FACILITY@123@@Z; Windows::WCP::Rtl::RtlGetFacilityTracingFlags(Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)
0x18012d8a6  mov     rcx, rdi; this
0x18012d8a9  mov     [rbp+280h+var_198], r14d
0x18012d8b0  mov     [rbp+280h+var_188], r14b
0x18012d8b7  mov     [rbp+280h+var_1B8], 1
0x18012d8c1  call    ?RtlGetFacilityTracingFlags@Rtl@WCP@Windows@@YAKPEAU_RTL_TRACING_FACILITY@123@@Z; Windows::WCP::Rtl::RtlGetFacilityTracingFlags(Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)
0x18012d8c6  lea     rsi, aWindowsRtlRtlg_0; "Windows::Rtl::RtlGetSystem"
0x18012d8cd  test    al, 0Eh
0x18012d8cf  jz      short loc_18012D910
0x18012d8d1  mov     qword ptr [rsp+380h+var_330], r14; unsigned int
0x18012d8d6  lea     r9, ?RtlTraceFormat_PCNTSTATUS@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; int
0x18012d8dd  mov     [rsp+380h+var_338], r14; __int64
0x18012d8e2  lea     r8, [rbp+280h+var_200]; int
0x18012d8e9  mov     [rsp+380h+var_340], r14; __int64
0x18012d8ee  lea     rcx, [rbp+280h+var_1C0]; int
0x18012d8f5  mov     [rsp+380h+var_348], r14; __int64
0x18012d8fa  xor     edx, edx; int
0x18012d8fc  mov     [rsp+380h+var_350], rdi; Windows::WCP::Rtl *
0x18012d901  mov     [rsp+380h+var_358], rsi; __int64
0x18012d906  mov     [rsp+380h+var_360], r14; __int64
0x18012d90b  call    ?Arm@?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$06@Rtl@WCP@Windows@@QEAAXKAEBUCSimpleNtStatusCarryingFrame@2ErrorHandling@4@P6AXPEAUIRtlFormattedOutputStream@24@PEBX@Z2QEBDPEAU_RTL_TRACING_FACILITY@234@444_KZZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::Arm(ulong,Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame const &,void (*)(Windows::Rtl::IRtlFormattedOutputStream *,void const *),void const *,char const * const,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,char const * const,char const * const,unsigned __int64,...)
0x18012d910  test    r12, r12
0x18012d913  jnz     short loc_18012D93D
0x18012d915  lea     rax, aOnecoreBaseWcp_30; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x18012d91c  mov     [rbp+280h+var_2D8], rsi
0x18012d920  mov     [rbp+280h+var_2E0], rax
0x18012d924  lea     rcx, [rbp+280h+var_2E0]
0x18012d928  lea     rax, aNotNullCheckFa_40; "Not-null check failed: System"
0x18012d92f  mov     [rbp+280h+var_2D0], 1EB2h
0x18012d937  mov     [rbp+280h+var_2C8], rax
0x18012d93b  jmp     short loc_18012D96C
0x18012d93d  test    r13d, 0FFFFFFF0h
0x18012d944  jz      short loc_18012D993
0x18012d946  lea     rax, aOnecoreBaseWcp_30; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x18012d94d  mov     [rbp+280h+var_2B8], rsi
0x18012d951  mov     [rbp+280h+var_2C0], rax
0x18012d955  lea     rcx, [rbp+280h+var_2C0]
0x18012d959  lea     rax, aValidFlagsChec_0; "Valid flags check failed: Flags"
0x18012d960  mov     [rbp+280h+var_2B0], 1EB3h
0x18012d968  mov     [rbp+280h+var_2A8], rax
0x18012d96c  mov     r8d, 0C000000Dh
0x18012d972  mov     [rbp+280h+var_200], 0C000000Dh
0x18012d97c  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18012d983  call    RtlReportErrorOrigination
0x18012d988  mov     ebx, [rbp+280h+var_200]
0x18012d98e  jmp     loc_18012E0D1
0x18012d993  mov     ecx, r13d
0x18012d996  and     ecx, 0Fh
0x18012d999  jz      short loc_18012D9CA
0x18012d99b  lea     eax, [rcx-1]
0x18012d99e  test    ecx, eax
0x18012d9a0  jz      short loc_18012D9CA
0x18012d9a2  lea     rax, aOnecoreBaseWcp_30; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x18012d9a9  mov     [rbp+280h+var_298], rsi
0x18012d9ad  mov     [rbp+280h+var_2A0], rax
0x18012d9b1  lea     rcx, [rbp+280h+var_2A0]
0x18012d9b5  lea     rax, aNoMoreThanOneF; "No more than one flag set check failed:"...
0x18012d9bc  mov     [rbp+280h+var_290], 1EB4h
0x18012d9c4  mov     [rbp+280h+var_288], rax
0x18012d9c8  jmp     short loc_18012D96C
0x18012d9ca  cmp     cs:?g_pSystemIsolationLayerFromTest@SystemImplementation@Rtl@Windows@@3PEAUIRtlSystemIsolationLayer@23@EA, r14; Windows::Rtl::IRtlSystemIsolationLayer * Windows::Rtl::SystemImplementation::g_pSystemIsolationLayerFromTest
0x18012d9d1  jz      short loc_18012D9F5
0x18012d9d3  test    rbx, rbx
0x18012d9d6  jnz     short loc_18012D9F5
0x18012d9d8  mov     rdx, r12
0x18012d9db  call    ??$CreateRequiredInterface@UIRtlSystemIsolationLayer@Rtl@Windows@@@IRtlObject@Rtl@Windows@@QEAAJPEAV?$Auto@PEAUIRtlSystemIsolationLayer@Rtl@Windows@@@2@@Z; Windows::Rtl::IRtlObject::CreateRequiredInterface<Windows::Rtl::IRtlSystemIsolationLayer>(Windows::Auto<Windows::Rtl::IRtlSystemIsolationLayer *> *)
0x18012d9e0  test    eax, eax
0x18012d9e2  jns     loc_18012E180
0x18012d9e8  mov     [rbp+280h+var_200], eax
0x18012d9ee  mov     ebx, eax
0x18012d9f0  jmp     loc_18012E0D1
0x18012d9f5  xorps   xmm0, xmm0
0x18012d9f8  mov     qword ptr [rbp+280h+var_1F0], r14
0x18012d9ff  xorps   xmm1, xmm1
0x18012da02  mov     [rbp+280h+var_1F8], r14
0x18012da09  lea     rcx, [rsp+380h+var_320]
0x18012da0e  mov     [rbp+280h+var_1E8], r14
0x18012da15  movdqu  [rsp+380h+var_310], xmm0
0x18012da1b  mov     [rsp+380h+var_320], r14
0x18012da20  movdqu  [rbp+280h+var_300], xmm1
0x18012da25  mov     [rbp+280h+BaseAddress], r14
0x18012da2c  mov     byte ptr [rbp+280h+var_1D8], r14b
0x18012da33  mov     byte ptr [rbp+280h+var_1D8+1], r14b
0x18012da3a  mov     [rbp+280h+var_2F0], r14b
0x18012da3e  mov     [rbp+280h+var_2EC], r14d
0x18012da42  mov     [rbp+280h+var_2E8], r14
0x18012da46  call    ?RtlGetTransactionCoordinator@SystemImplementation@Rtl@Windows@@YAJPEAV?$Auto@PEAUIRtlTransactionCoordinator@SystemImplementation@Rtl@Windows@@@3@@Z; Windows::Rtl::SystemImplementation::RtlGetTransactionCoordinator(Windows::Auto<Windows::Rtl::SystemImplementation::IRtlTransactionCoordinator *> *)
0x18012da4b  mov     edi, eax
0x18012da4d  test    eax, eax
0x18012da4f  jns     short loc_18012DA97
0x18012da51  mov     [rbp+280h+var_200], edi
0x18012da57  mov     rcx, [rbp+280h+BaseAddress]; BaseAddress
0x18012da5e  test    rcx, rcx
0x18012da61  jz      short loc_18012DA81
0x18012da63  call    cs:__imp_LdrUnloadDll
0x18012da6a  nop     dword ptr [rax+rax+00h]
0x18012da6f  test    eax, eax
0x18012da71  jns     short loc_18012DA7A
0x18012da73  mov     ecx, 7
0x18012da78  int     29h; Win8: RtlFailFast(ecx)
0x18012da7a  mov     [rbp+280h+BaseAddress], r14
0x18012da81  mov     rcx, [rsp+380h+var_320]
0x18012da86  test    rcx, rcx
0x18012da89  jz      loc_18012E075
0x18012da8f  mov     rax, [rcx]
0x18012da92  jmp     loc_18012E06D
0x18012da97  mov     r15d, r14d
0x18012da9a  test    rbx, rbx
0x18012da9d  jz      loc_18012DD9D
0x18012daa3  mov     rcx, [rbx]
0x18012daa6  test    rcx, rcx
0x18012daa9  jz      loc_18012DB6B
0x18012daaf  mov     [rbp+280h+var_1D0], r14
0x18012dab6  lea     r8, [rbp+280h+var_1D0]
0x18012dabd  mov     rax, [rcx]
0x18012dac0  lea     rdx, _GUID_bf537349_9167_47f4_a8a8_df3c233df232
0x18012dac7  mov     rax, [rax+8]
0x18012dacb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012dad0  mov     edi, eax
0x18012dad2  test    eax, eax
0x18012dad4  jns     short loc_18012DB06
0x18012dad6  mov     rdx, [rbp+280h+var_1D0]
0x18012dadd  mov     [rbp+280h+var_200], edi
0x18012dae3  test    rdx, rdx
0x18012dae6  jz      loc_18012DA57
0x18012daec  mov     [rbp+280h+var_1D0], r14
0x18012daf3  mov     rcx, [rdx]
0x18012daf6  mov     rax, [rcx]
0x18012daf9  mov     rcx, rdx
0x18012dafc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012db01  jmp     loc_18012DA57
0x18012db06  mov     rcx, [rbp+280h+var_1D0]
0x18012db0d  mov     rax, [rcx]
0x18012db10  mov     rax, [rax+10h]
0x18012db14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012db19  lea     r9, [rbp+280h+var_1E8]
0x18012db20  mov     rcx, rax
0x18012db23  lea     r8, [rbp+280h+var_1F0]
0x18012db2a  mov     rsi, rax
0x18012db2d  lea     rdx, [rbp+280h+var_1F8]
0x18012db34  call    ?GetProviders@CSystemIsolationLayer@SystemImplementation@Rtl@Windows@@QEAAJPEAV?$Auto@PEAVIRtlRegistryProvider@SystemImplementation@Rtl@Windows@@@4@PEAV?$Auto@PEAVIRtlFileSystemProvider@SystemImplementation@Rtl@Windows@@@4@PEAV?$Auto@PEAVIRtlUserProvider@SystemImplementation@Rtl@Windows@@@4@@Z; Windows::Rtl::SystemImplementation::CSystemIsolationLayer::GetProviders(Windows::Auto<Windows::Rtl::SystemImplementation::IRtlRegistryProvider *> *,Windows::Auto<Windows::Rtl::SystemImplementation::IRtlFileSystemProvider *> *,Windows::Auto<Windows::Rtl::SystemImplementation::IRtlUserProvider *> *)
0x18012db39  mov     edi, eax
0x18012db3b  test    eax, eax
0x18012db3d  js      short loc_18012DAD6
0x18012db3f  mov     rcx, [rbp+280h+var_1D0]
0x18012db46  mov     r15d, [rsi+80h]
0x18012db4d  test    rcx, rcx
0x18012db50  jz      short loc_18012DB64
0x18012db52  mov     [rbp+280h+var_1D0], r14
0x18012db59  mov     rax, [rcx]
0x18012db5c  mov     rax, [rax]
0x18012db5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012db64  lea     rsi, aWindowsRtlRtlg_0; "Windows::Rtl::RtlGetSystem"
0x18012db6b  mov     rdx, qword ptr [rbp+280h+var_1F0]; int
0x18012db72  test    rdx, rdx
0x18012db75  jnz     loc_18012DC6F
0x18012db7b  cmp     [rbx+10h], r14
0x18012db7f  ja      loc_18012DC6F
0x18012db85  lea     rax, aOnecoreBaseWcp_30; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x18012db8c  mov     [rbp+280h+var_278], rsi
0x18012db90  mov     [rbp+280h+var_280], rax
0x18012db94  lea     rcx, [rbp+280h+var_280]
0x18012db98  lea     rax, aConstructordat_1; "ConstructorData->FilesystemLayers.Lengt"...
0x18012db9f  mov     [rbp+280h+var_270], 1EECh
0x18012dba7  mov     [rbp+280h+var_268], rax
0x18012dbab  mov     r8d, 0C000000Dh
0x18012dbb1  mov     [rbp+280h+var_200], 0C000000Dh
0x18012dbbb  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18012dbc2  call    RtlReportErrorOrigination
0x18012dbc7  mov     ebx, [rbp+280h+var_200]
0x18012dbcd  mov     rcx, [rbp+280h+BaseAddress]; BaseAddress
0x18012dbd4  test    rcx, rcx
0x18012dbd7  jz      short loc_18012DBF7
0x18012dbd9  call    cs:__imp_LdrUnloadDll
0x18012dbe0  nop     dword ptr [rax+rax+00h]
0x18012dbe5  test    eax, eax
0x18012dbe7  jns     short loc_18012DBF0
0x18012dbe9  mov     ecx, 7
0x18012dbee  int     29h; Win8: RtlFailFast(ecx)
0x18012dbf0  mov     [rbp+280h+BaseAddress], r14
0x18012dbf7  mov     rcx, [rsp+380h+var_320]
0x18012dbfc  test    rcx, rcx
0x18012dbff  jz      short loc_18012DC0C
0x18012dc01  mov     rax, [rcx]
0x18012dc04  mov     rax, [rax]
0x18012dc07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012dc0c  mov     rcx, [rbp+280h+var_1E8]
0x18012dc13  test    rcx, rcx
0x18012dc16  jz      short loc_18012DC2A
0x18012dc18  mov     [rbp+280h+var_1E8], r14
0x18012dc1f  mov     rax, [rcx]
0x18012dc22  mov     rax, [rax]
0x18012dc25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012dc2a  mov     rcx, [rbp+280h+var_1F8]
0x18012dc31  test    rcx, rcx
0x18012dc34  jz      short loc_18012DC48
0x18012dc36  mov     [rbp+280h+var_1F8], r14
0x18012dc3d  mov     rax, [rcx]
0x18012dc40  mov     rax, [rax]
0x18012dc43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012dc48  mov     rcx, qword ptr [rbp+280h+var_1F0]
0x18012dc4f  test    rcx, rcx
0x18012dc52  jz      loc_18012E0D1
0x18012dc58  mov     qword ptr [rbp+280h+var_1F0], r14
0x18012dc5f  mov     rax, [rcx]
0x18012dc62  mov     rax, [rax]
0x18012dc65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012dc6a  jmp     loc_18012E0D1
0x18012dc6f  cmp     [rbp+280h+var_1F8], r14
0x18012dc76  jnz     short loc_18012DCA9
0x18012dc78  cmp     [rbx+20h], r14
0x18012dc7c  ja      short loc_18012DCA9
0x18012dc7e  lea     rax, aOnecoreBaseWcp_30; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x18012dc85  mov     [rbp+280h+var_258], rsi
0x18012dc89  mov     [rbp+280h+var_260], rax
0x18012dc8d  lea     rcx, [rbp+280h+var_260]
0x18012dc91  lea     rax, aConstructordat_0; "ConstructorData->RegistryLayers.Length "...
0x18012dc98  mov     [rbp+280h+var_250], 1EEFh
0x18012dca0  mov     [rbp+280h+var_248], rax
0x18012dca4  jmp     loc_18012DBAB
0x18012dca9  cmp     [rbp+280h+var_1E8], r14
0x18012dcb0  jnz     short loc_18012DCE3
0x18012dcb2  cmp     [rbx+30h], r14
0x18012dcb6  ja      short loc_18012DCE3
0x18012dcb8  lea     rax, aOnecoreBaseWcp_30; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x18012dcbf  mov     [rbp+280h+var_238], rsi
0x18012dcc3  mov     [rbp+280h+var_240], rax
0x18012dcc7  lea     rcx, [rbp+280h+var_240]
0x18012dccb  lea     rax, aConstructordat; "ConstructorData->UserLayers.Length > 0"
0x18012dcd2  mov     [rbp+280h+var_230], 1EF2h
0x18012dcda  mov     [rbp+280h+var_228], rax
0x18012dcde  jmp     loc_18012DBAB
0x18012dce3  lea     rax, [rbp+280h+var_1D8+1]
0x18012dcea  xor     ecx, ecx; int
0x18012dcec  mov     [rsp+380h+var_358], rax; __int64
0x18012dcf1  lea     r8, [rbx+8]; int
0x18012dcf5  lea     rax, [rbp+280h+BaseAddress]
0x18012dcfc  lea     r9, [rbp+280h+var_1F0]; int
0x18012dd03  mov     [rsp+380h+var_360], rax; BaseAddress
0x18012dd08  call    ?CreateFilesystemProviderStack@SystemImplementation@Rtl@Windows@@YAJKPEAVIRtlFileSystemProvider@123@AEBU?$Vector@USYSTEM_LAYER@Rtl@Windows@@@3@PEAV?$Auto@PEAVIRtlFileSystemProvider@SystemImplementation@Rtl@Windows@@@3@PEAV?$AutoGenericHandle@PEAX$0A@$1?CloseWithLdrUnloadDll@Detail@Windows@@YAXPEAX@Z@3@PEA_N@Z; Windows::Rtl::SystemImplementation::CreateFilesystemProviderStack(ulong,Windows::Rtl::SystemImplementation::IRtlFileSystemProvider *,Windows::Vector<Windows::Rtl::SYSTEM_LAYER> const &,Windows::Auto<Windows::Rtl::SystemImplementation::IRtlFileSystemProvider *> *,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithLdrUnloadDll(void *)> *,bool *)
0x18012dd0d  mov     edi, eax
0x18012dd0f  test    eax, eax
0x18012dd11  js      loc_18012DA51
0x18012dd17  mov     r8, qword ptr [rbp+280h+var_1F0]; int
0x18012dd1e  lea     rax, [rbp+280h+var_1D8]
0x18012dd25  mov     rdx, [rbp+280h+var_1F8]; int
0x18012dd2c  lea     r9, [rbx+18h]; int
0x18012dd30  mov     [rsp+380h+var_350], rax; __int64
0x18012dd35  xor     ecx, ecx; int
0x18012dd37  lea     rax, [rbp+280h+BaseAddress]
0x18012dd3e  mov     [rsp+380h+var_358], rax; BaseAddress
0x18012dd43  lea     rax, [rbp+280h+var_1F8]
0x18012dd4a  mov     [rsp+380h+var_360], rax; __int64
0x18012dd4f  call    ?CreateRegistryProviderStack@SystemImplementation@Rtl@Windows@@YAJKPEAVIRtlRegistryProvider@123@PEAVIRtlFileSystemProvider@123@AEBU?$Vector@USYSTEM_LAYER@Rtl@Windows@@@3@PEAV?$Auto@PEAVIRtlRegistryProvider@SystemImplementation@Rtl@Windows@@@3@PEAV?$AutoGenericHandle@PEAX$0A@$1?CloseWithLdrUnloadDll@Detail@Windows@@YAXPEAX@Z@3@PEA_N@Z; Windows::Rtl::SystemImplementation::CreateRegistryProviderStack(ulong,Windows::Rtl::SystemImplementation::IRtlRegistryProvider *,Windows::Rtl::SystemImplementation::IRtlFileSystemProvider *,Windows::Vector<Windows::Rtl::SYSTEM_LAYER> const &,Windows::Auto<Windows::Rtl::SystemImplementation::IRtlRegistryProvider *> *,Windows::AutoGenericHandle<void *,0,&Windows::Detail::CloseWithLdrUnloadDll(void *)> *,bool *)
0x18012dd54  mov     edi, eax
0x18012dd56  test    eax, eax
0x18012dd58  js      loc_18012DA51
0x18012dd5e  mov     r8, [rbp+280h+var_1F8]
0x18012dd65  lea     rax, [rbp+280h+var_1E8]
0x18012dd6c  mov     rdx, qword ptr [rbp+280h+var_1F0]
0x18012dd73  lea     r9, [rbx+28h]
0x18012dd77  mov     rcx, [rbp+280h+var_1E8]
0x18012dd7e  mov     [rsp+380h+var_360], rax
0x18012dd83  call    ?CreateUserProviderStack@SystemImplementation@Rtl@Windows@@YAJPEAVIRtlUserProvider@123@PEAVIRtlFileSystemProvider@123@PEAVIRtlRegistryProvider@123@AEBU?$Vector@USYSTEM_LAYER@Rtl@Windows@@@3@PEAV?$Auto@PEAVIRtlUserProvider@SystemImplementation@Rtl@Windows@@@3@@Z; Windows::Rtl::SystemImplementation::CreateUserProviderStack(Windows::Rtl::SystemImplementation::IRtlUserProvider *,Windows::Rtl::SystemImplementation::IRtlFileSystemProvider *,Windows::Rtl::SystemImplementation::IRtlRegistryProvider *,Windows::Vector<Windows::Rtl::SYSTEM_LAYER> const &,Windows::Auto<Windows::Rtl::SystemImplementation::IRtlUserProvider *> *)
0x18012dd88  mov     ebx, eax
0x18012dd8a  test    eax, eax
0x18012dd8c  jns     loc_18012DFAD
0x18012dd92  mov     [rbp+280h+var_200], eax
0x18012dd98  jmp     loc_18012DBCD
0x18012dd9d  lea     rcx, [rsp+380h+var_318]
0x18012dda2  mov     [rsp+380h+var_318], r14
0x18012dda7  call    ??$Allocate@$$V@?$AutoNewPtr@VDirectFileSystemProvider@SystemImplementation@Rtl@Windows@@@Windows@@QEAAPEAVDirectFileSystemProvider@SystemImplementation@Rtl@1@XZ; Windows::AutoNewPtr<Windows::Rtl::SystemImplementation::DirectFileSystemProvider>::Allocate<>(void)
0x18012ddac  test    rax, rax
0x18012ddaf  jnz     short loc_18012DE1D
0x18012ddb1  lea     rax, aOnecoreBaseWcp_30; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x18012ddb8  mov     [rbp+280h+var_218], rsi
0x18012ddbc  mov     [rbp+280h+var_220], rax
0x18012ddc0  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18012ddc7  lea     rax, aFsAllocate; "Fs.Allocate()"
0x18012ddce  mov     [rbp+280h+var_210], 1F23h
  ... truncated ...
```
