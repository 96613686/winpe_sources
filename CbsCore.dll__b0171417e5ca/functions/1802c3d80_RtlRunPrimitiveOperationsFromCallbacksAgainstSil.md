# RtlRunPrimitiveOperationsFromCallbacksAgainstSil

- ea: `0x1802c3d80`
- end: `0x1802c4bae`
- name: `RtlRunPrimitiveOperationsFromCallbacksAgainstSil`
- size: `3630`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, struct Windows::Rtl::IRtlSystemIsolationLayerPublic *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `39`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180010cc0`
- `0x180019bdc`
- `0x18002ec34`
- `0x180044e7c`
- `0x180045444`
- `0x180048c24`
- `0x180048c80`
- `0x180064c6c`
- `0x1800a26b0`
- `0x1800aa1a4`
- `0x1800aa1d4`
- `0x1800bea58`
- `0x1800c22ec`
- `0x1800eb920`
- `0x1800ec920`
- `0x1800ef360`
- `0x18011a3d8`
- `0x180210b50`
- `0x180212434`
- `0x180232608`
- `0x18027d474`
- `0x1802b95a0`
- `0x1802bce2c`
- `0x1802bcfb8`
- `0x1802bd248`
- `0x1802bd4a8`
- `0x1802bd4d8`
- `0x1802bd5dc`
- `0x1802bd644`
- `0x1802bd6a0`
- `0x1802be4b0`
- `0x1802bed98`
- `0x1802bf654`
- `0x1802c3d80`
- `0x1802c556c`
- `0x1802c56d4`
- `0x1802ccd1c`
- `0x1802cdb0c`
- `0x1802d5010`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x1802c427b`
- `ntdll!NtQuerySystemInformation` at `0x1802c427b`
- `ntdll!NtCreateEvent` at `0x1802c4478`
- `ntdll!NtCreateEvent` at `0x1802c44dc`
- `ntdll!NtCreateEvent` at `0x1802c4478`
- `ntdll!NtCreateEvent` at `0x1802c44dc`
- `ntdll!NtCreateIoCompletion` at `0x1802c43b8`
- `ntdll!NtCreateIoCompletion` at `0x1802c4414`
- `ntdll!NtCreateIoCompletion` at `0x1802c43b8`
- `ntdll!NtCreateIoCompletion` at `0x1802c4414`
- `ntdll!TpSimpleTryPost` at `0x1802c4532`
- `ntdll!TpSimpleTryPost` at `0x1802c4590`
- `ntdll!TpSimpleTryPost` at `0x1802c4532`
- `ntdll!TpSimpleTryPost` at `0x1802c4590`

## string_xrefs

- `0x1802c43ed`: `::NtCreateIoCompletion(CompletionContext.DispatcherPort.GetInitPointer(), ((0x000F0000L)|(0x00100000L)|0x3), nullptr, 0)`
- `0x1802c4449`: `::NtCreateIoCompletion(CompletionContext.WorkerPort.GetInitPointer(), ((0x000F0000L)|(0x00100000L)|0x3), nullptr, 0)`
- `0x1802c4365`: `!GlobalContext.fPendingDeletesBehavior || GlobalContext.fAgainstUnbufferedSil`
- `0x1802c4567`: `::TpSimpleTryPost(DispatcherCallback, &CompletionContext, nullptr)`
- `0x1802c4687`: `::TpSimpleTryPost(WorkerCallback, &CompletionContext, nullptr)`
- `0x1802c44ad`: `::NtCreateEvent(CompletionContext.DispatcherEvent.GetInitPointer(), ((0x000F0000L)|(0x00100000L)|0x3), nullptr, SynchronizationEvent, 0 )`
- `0x1802c4511`: `::NtCreateEvent(CompletionContext.WorkerEvent.GetInitPointer(), ((0x000F0000L)|(0x00100000L)|0x3), nullptr, SynchronizationEvent, 0 )`

## pseudocode

```c
__int64 __fastcall RtlRunPrimitiveOperationsFromCallbacksAgainstSil(
        unsigned int a1,
        struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *a2,
        void (__fastcall *a3)(__int64, _BYTE *, __int128 *, char *),
        __int64 a4,
        __int64 a5,
        __int64 a6,
        struct Windows::Rtl::IRtlSystemIsolationLayerPublic *a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  __int64 v12; // r12
  __int64 v13; // r9
  unsigned int v14; // eax
  _QWORD *v15; // rdx
  unsigned int v16; // ebx
  __int64 v17; // rax
  int v18; // eax
  Windows::Rtl::SystemImplementation::CSystemIsolationLayer *v19; // rax
  struct Windows::Rtl::IRtlDirectory *v20; // r8
  struct IUpdateReserveManager *v21; // r9
  __int64 v22; // rax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  unsigned __int64 v26; // rdi
  NTSTATUS v27; // eax
  __int64 v28; // r8
  _QWORD *v29; // rdx
  unsigned int v30; // eax
  char v31; // al
  char v32; // cl
  char v33; // cl
  void **InitPointer; // rax
  NTSTATUS IoCompletion; // eax
  void **v36; // rax
  NTSTATUS v37; // eax
  void **v38; // rax
  NTSTATUS Event; // eax
  void **v40; // rax
  NTSTATUS v41; // eax
  int v42; // eax
  __int64 v43; // rbx
  int v44; // eax
  __int64 v45; // rdx
  bool v46; // al
  int v47; // eax
  unsigned int v48; // edi
  void (__fastcall *v49)(__int64, _BYTE *, __int128 *, char *); // r13
  char v50; // al
  Windows::Rtl::StopWatch *v51; // rbx
  int v52; // esi
  __int64 v53; // rcx
  char v54; // al
  int v55; // eax
  _QWORD *v56; // rbx
  int v57; // eax
  unsigned int v58; // edx
  __int64 v59; // r8
  unsigned int v61; // r8d
  __int64 v62; // rdx
  unsigned __int64 v63; // [rsp+58h] [rbp-A8h]
  bool v64; // [rsp+60h] [rbp-A0h] BYREF
  void (__fastcall *v65)(__int64, _BYTE *, __int128 *, char *); // [rsp+68h] [rbp-98h]
  __int64 v66; // [rsp+70h] [rbp-90h]
  __int64 v67; // [rsp+78h] [rbp-88h]
  _QWORD v68[4]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v69[4]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v70[4]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v71[4]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v72[4]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v73[4]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v74[4]; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v75[4]; // [rsp+160h] [rbp+60h] BYREF
  _QWORD v76[4]; // [rsp+180h] [rbp+80h] BYREF
  _QWORD v77[4]; // [rsp+1A0h] [rbp+A0h] BYREF
  _QWORD v78[4]; // [rsp+1C0h] [rbp+C0h] BYREF
  _QWORD v79[4]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v80; // [rsp+200h] [rbp+100h] BYREF
  __int128 v81; // [rsp+210h] [rbp+110h] BYREF
  signed __int32 v82; // [rsp+220h] [rbp+120h] BYREF
  unsigned int v83; // [rsp+224h] [rbp+124h]
  unsigned int v84; // [rsp+228h] [rbp+128h]
  int v85; // [rsp+22Ch] [rbp+12Ch]
  char v86; // [rsp+230h] [rbp+130h]
  __int64 v87; // [rsp+238h] [rbp+138h] BYREF
  struct Windows::Rtl::IRtlSystemIsolationLayerPublic *v88; // [rsp+240h] [rbp+140h]
  _OWORD v89[2]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v90; // [rsp+270h] [rbp+170h]
  __int128 *v91; // [rsp+278h] [rbp+178h]
  __int128 v92; // [rsp+280h] [rbp+180h]
  __int128 v93; // [rsp+290h] [rbp+190h]
  int v94; // [rsp+2A0h] [rbp+1A0h]
  int v95; // [rsp+2A4h] [rbp+1A4h]
  __int16 v96; // [rsp+2A8h] [rbp+1A8h]
  _BYTE v97[48]; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int64 v98[8]; // [rsp+2E0h] [rbp+1E0h] BYREF
  int v99; // [rsp+320h] [rbp+220h]
  int v100; // [rsp+330h] [rbp+230h] BYREF
  char v101[4]; // [rsp+334h] [rbp+234h] BYREF
  __int64 v102; // [rsp+338h] [rbp+238h] BYREF
  __int64 v103; // [rsp+340h] [rbp+240h] BYREF
  __int64 v104; // [rsp+348h] [rbp+248h] BYREF
  __int64 v105; // [rsp+350h] [rbp+250h] BYREF
  __int64 v106; // [rsp+358h] [rbp+258h] BYREF
  char v107[8]; // [rsp+360h] [rbp+260h] BYREF
  __int64 v108; // [rsp+368h] [rbp+268h]
  __int64 v109; // [rsp+370h] [rbp+270h]
  __int64 v110; // [rsp+378h] [rbp+278h]
  __int64 v111; // [rsp+380h] [rbp+280h]
  char v112[8]; // [rsp+388h] [rbp+288h] BYREF
  __int64 v113; // [rsp+390h] [rbp+290h]
  __int64 v114; // [rsp+398h] [rbp+298h]
  __int64 v115; // [rsp+3A0h] [rbp+2A0h]
  __int64 v116; // [rsp+3A8h] [rbp+2A8h]
  char v117[8]; // [rsp+3B0h] [rbp+2B0h] BYREF
  __int64 v118; // [rsp+3B8h] [rbp+2B8h]
  __int64 v119; // [rsp+3C0h] [rbp+2C0h]
  __int64 v120; // [rsp+3C8h] [rbp+2C8h]
  __int64 v121; // [rsp+3D0h] [rbp+2D0h]
  __int128 v122; // [rsp+3D8h] [rbp+2D8h] BYREF
  __int64 v123; // [rsp+3E8h] [rbp+2E8h]
  __int128 v124; // [rsp+3F0h] [rbp+2F0h] BYREF
  int v125; // [rsp+400h] [rbp+300h]
  __int64 v126; // [rsp+408h] [rbp+308h]
  __int64 v127; // [rsp+410h] [rbp+310h]
  __int64 v128; // [rsp+418h] [rbp+318h]
  __int64 v129; // [rsp+420h] [rbp+320h]
  __int64 v130; // [rsp+428h] [rbp+328h]
  __int64 v131; // [rsp+430h] [rbp+330h]
  _BYTE v132[4]; // [rsp+440h] [rbp+340h] BYREF
  int v133; // [rsp+444h] [rbp+344h]
  __int64 v134; // [rsp+490h] [rbp+390h]
  __int64 v135; // [rsp+498h] [rbp+398h]
  __int128 v136; // [rsp+4A0h] [rbp+3A0h] BYREF
  _BYTE SystemInformation[56]; // [rsp+4B0h] [rbp+3B0h] BYREF
  char v138; // [rsp+4E8h] [rbp+3E8h]
  int v139[14]; // [rsp+4F0h] [rbp+3F0h] BYREF
  char v140; // [rsp+528h] [rbp+428h]

  v12 = 0;
  v105 = a10;
  v67 = a6;
  v66 = a4;
  v65 = a3;
  v106 = a8;
  v100 = 0;
  Windows::WCP::Rtl::RtlGetFacilityTracingFlags((Windows::WCP::Rtl *)&Windows::WCP::Rtl::Facility_POQ, a2);
  v139[10] = 0;
  v140 = 0;
  v139[2] = 1;
  if ( (unsigned __int8)Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,0>::ShouldArm(&Windows::WCP::Rtl::Facility_POQ) )
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,0>::Arm(
      (int)v139,
      0,
      (int)&v100,
      (int)Windows::WCP::Rtl::RtlTraceFormat_PCNTSTATUS,
      0,
      (__int64)"RtlRunPrimitiveOperationsFromCallbacksAgainstSil",
      (Windows::WCP::Rtl *)&Windows::WCP::Rtl::Facility_POQ,
      0,
      0,
      0,
      0,
      v63);
  v101[0] = 0;
  memset(v89, 0, sizeof(v89));
  v92 = 0;
  v93 = 0;
  v90 = 0;
  v91 = 0;
  v94 = 0;
  v95 = 0;
  v96 = 0;
  OperationContext::OperationContext((OperationContext *)v97);
  v86 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  v85 = 0;
  v87 = 0;
  v88 = 0;
  if ( a9 )
  {
    *(_OWORD *)a9 = 0;
    *(_OWORD *)(a9 + 16) = 0;
    *(_OWORD *)(a9 + 32) = 0;
  }
  if ( (a1 & 0xFFFFFCC6) != 0 )
  {
    v75[1] = v13;
    v75[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
    v75[2] = 3986;
    v75[3] = "Valid flags check failed: Flags";
    v14 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
            &v100,
            v75);
LABEL_10:
    v16 = v14;
LABEL_112:
    IoCompletionContext::~IoCompletionContext((IoCompletionContext *)&v80);
    OperationContext::~OperationContext((OperationContext *)v97);
    PoqContext::~PoqContext((PoqContext *)v89);
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,0>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,0>(v139);
    return v16;
  }
  if ( !a7 )
  {
    v76[1] = v13;
    v76[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
    v15 = v76;
    v76[2] = 3988;
    v76[3] = "Not-null check failed: IsoLayer";
LABEL_9:
    v14 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
            &v100,
            v15);
    goto LABEL_10;
  }
  if ( !a3 )
  {
    v77[1] = v13;
    v77[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
    v15 = v77;
    v77[2] = 3989;
    v77[3] = "Not-null check failed: GetOperationCallback";
    goto LABEL_9;
  }
  v17 = *(_QWORD *)a7;
  v102 = 0;
  v18 = (*(__int64 (__fastcall **)(struct Windows::Rtl::IRtlSystemIsolationLayerPublic *, GUID *, __int64 *))(v17 + 8))(
          a7,
          &GUID_bf537349_9167_47f4_a8a8_df3c233df232,
          &v102);
  v16 = v18;
  if ( v18 < 0 )
    goto LABEL_14;
  v98[7] = (__int64)v89;
  v90 = a5;
  v19 = (Windows::Rtl::SystemImplementation::CSystemIsolationLayer *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v102 + 16LL))(v102);
  LOBYTE(v95) = Windows::Rtl::SystemImplementation::CSystemIsolationLayer::IsUnbufferedSil(v19);
  *(_QWORD *)&v92 = a9;
  *((_QWORD *)&v92 + 1) = a8;
  BYTE1(v95) = a1 & 1;
  HIBYTE(v96) = (a1 & 0x200) != 0;
  v91 = &v80;
  v18 = Windows::Rtl::PendingDeletesHelper::Initialize((Windows::Rtl::PendingDeletesHelper *)v89, a7, v20, v21);
  v16 = v18;
  if ( v18 < 0 )
    goto LABEL_14;
  if ( v98[0] )
    __debugbreak();
  v18 = Windows::Rtl::IRtlObject::CreateRequiredInterface<Windows::Rtl::IRtlSystemIsolationLayer>((__int64 *)a7, v98);
  v16 = v18;
  if ( v18 < 0 )
    goto LABEL_14;
  if ( !HIBYTE(v96) )
  {
    v18 = SafeOpenCreateHelper::TryAddProtectedPath(
            (SafeOpenCreateHelper *)v97,
            (const struct _LUNICODE_STRING *)___LiteralObject__2U__BaseLiteralBuffer__0M_U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0FM__0FD__0HJ__0HD__0HE__0GF__0GN__0FC__0GP__0GP__0HE__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__Details_RtlStringLiterals__3U_LUNICODE_STRING__B);
    v16 = v18;
    if ( v18 < 0 )
    {
LABEL_14:
      v100 = v18;
LABEL_111:
      Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v102);
      goto LABEL_112;
    }
    v22 = *(_QWORD *)a7;
    v103 = 0;
    v23 = (*(__int64 (__fastcall **)(struct Windows::Rtl::IRtlSystemIsolationLayerPublic *, _QWORD, _QWORD, __int64 *, _QWORD))(v22 + 128))(
            a7,
            0,
            0,
            &v103,
            0);
    v16 = v23;
    if ( v23 < 0 )
    {
      v100 = v23;
LABEL_23:
      Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v103);
      goto LABEL_111;
    }
    v123 = 0;
    v122 = 0;
    v24 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int128 *, _QWORD))(*(_QWORD *)v103 + 32LL))(
            v103,
            0,
            0x100000,
            &v122,
            0);
    v16 = v24;
    if ( v24 < 0 )
    {
      v100 = v24;
LABEL_26:
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v122);
      goto LABEL_23;
    }
    if ( (*(unsigned __int8 (__fastcall **)(struct Windows::Rtl::IRtlSystemIsolationLayerPublic *, __int128 *, __int64))(*(_QWORD *)a7 + 176LL))(
           a7,
           &v122,
           0x80000000LL) )
    {
      v104 = 0;
      v25 = SafeOpenCreateHelper::SafeOpenDirectory((SafeOpenCreateHelper *)v97, 0);
      v16 = v25;
      if ( v25 < 0 )
      {
        v100 = v25;
        Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v104);
        goto LABEL_26;
      }
      Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v104);
    }
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v122);
    Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v103);
  }
  if ( (a1 & 0x100) != 0 )
  {
    HIWORD(v95) = 257;
    LOBYTE(v96) = 1;
  }
  v26 = 0;
  if ( (_BYTE)v95 )
  {
    memset_0(SystemInformation, 0, 0x40u);
    v27 = NtQuerySystemInformation(SystemBasicInformation, SystemInformation, 0x40u, 0);
    v28 = (unsigned int)v27;
    if ( v27 < 0 )
    {
      v78[2] = 4043;
      v78[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
      v29 = v78;
      v78[1] = "RtlRunPrimitiveOperationsFromCallbacksAgainstSil";
      v78[3] = "NtQuerySystemInformation(SystemBasicInformation, &SystemInformation, sizeof(SystemInformation), nullptr)";
LABEL_37:
      v30 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
              &v100,
              v29,
              v28);
LABEL_38:
      v16 = v30;
      goto LABEL_111;
    }
    v31 = v138;
    if ( v138 >= 2 )
    {
      v32 = 10;
      if ( v138 > 10 )
      {
LABEL_43:
        v26 = v32;
        goto LABEL_44;
      }
    }
    else
    {
      v31 = 2;
    }
    v32 = v31;
    goto LABEL_43;
  }
LABEL_44:
  v18 = (*(__int64 (__fastcall **)(struct Windows::Rtl::IRtlSystemIsolationLayerPublic *, __int64 *))(*(_QWORD *)a7 + 104LL))(
          a7,
          &v87);
  v16 = v18;
  if ( v18 < 0 )
    goto LABEL_14;
  v88 = a7;
  if ( BYTE1(v95) && !(_BYTE)v95 )
  {
    v79[2] = 4057;
    v79[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
    v79[1] = "RtlRunPrimitiveOperationsFromCallbacksAgainstSil";
    v79[3] = "!GlobalContext.fPendingDeletesBehavior || GlobalContext.fAgainstUnbufferedSil";
    v30 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
            &v100,
            v79);
    goto LABEL_38;
  }
  v33 = v86;
  if ( (a1 & 0x18) != 0 )
    v33 = 0;
  v86 = v33;
  if ( v33 )
  {
    InitPointer = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(&v80);
    IoCompletion = NtCreateIoCompletion(InitPointer, 0x1F0003u, 0, 0);
    v28 = (unsigned int)IoCompletion;
    if ( IoCompletion < 0 )
    {
      v68[2] = 4067;
      v68[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
      v29 = v68;
      v68[1] = "RtlRunPrimitiveOperationsFromCallbacksAgainstSil";
      v68[3] = "::NtCreateIoCompletion(CompletionContext.DispatcherPort.GetInitPointer(), ((0x000F0000L)|(0x00100000L)|0x3), nullptr, 0)";
      goto LABEL_37;
    }
    v36 = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer((char *)&v80 + 8);
    v37 = NtCreateIoCompletion(v36, 0x1F0003u, 0, 0);
    v28 = (unsigned int)v37;
    if ( v37 < 0 )
    {
      v74[2] = 4068;
      v74[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
      v29 = v74;
      v74[1] = "RtlRunPrimitiveOperationsFromCallbacksAgainstSil";
      v74[3] = "::NtCreateIoCompletion(CompletionContext.WorkerPort.GetInitPointer(), ((0x000F0000L)|(0x00100000L)|0x3), nullptr, 0)";
      goto LABEL_37;
    }
    v38 = (void **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v81);
    Event = NtCreateEvent(v38, 0x1F0003u, 0, SynchronizationEvent, 0);
    v28 = (unsigned int)Event;
    if ( Event < 0 )
    {
      v73[2] = 4070;
      v73[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
      v29 = v73;
      v73[1] = "RtlRunPrimitiveOperationsFromCallbacksAgainstSil";
      v73[3] = "::NtCreateEvent(CompletionContext.DispatcherEvent.GetInitPointer(), ((0x000F0000L)|(0x00100000L)|0x3), nu"
               "llptr, SynchronizationEvent, 0 )";
      goto LABEL_37;
    }
    v40 = (void **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer((char *)&v81 + 8);
    v41 = NtCreateEvent(v40, 0x1F0003u, 0, SynchronizationEvent, 0);
    v28 = (unsigned int)v41;
    if ( v41 < 0 )
    {
      v72[2] = 4071;
      v72[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
      v29 = v72;
      v72[1] = "RtlRunPrimitiveOperationsFromCallbacksAgainstSil";
      v72[3] = "::NtCreateEvent(CompletionContext.WorkerEvent.GetInitPointer(), ((0x000F0000L)|(0x00100000L)|0x3), nullpt"
               "r, SynchronizationEvent, 0 )";
      goto LABEL_37;
    }
    v42 = TpSimpleTryPost(DispatcherCallback_0, &v80, 0);
    v28 = (unsigned int)v42;
    if ( v42 < 0 )
    {
      v71[2] = 4073;
      v71[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
      v29 = v71;
      v71[1] = "RtlRunPrimitiveOperationsFromCallbacksAgainstSil";
      v71[3] = "::TpSimpleTryPost(DispatcherCallback, &CompletionContext, nullptr)";
      goto LABEL_37;
    }
    v43 = 0;
    if ( v26 )
    {
      while ( 1 )
      {
        v44 = TpSimpleTryPost(WorkerCallback_0, &v80, 0);
        v28 = (unsigned int)v44;
        if ( v44 < 0 )
          break;
        _InterlockedIncrement(&v82);
        if ( ++v43 >= v26 )
          goto LABEL_64;
      }
      v70[2] = 4078;
      v70[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
      v29 = v70;
      v70[1] = "RtlRunPrimitiveOperationsFromCallbacksAgainstSil";
      v70[3] = "::TpSimpleTryPost(WorkerCallback, &CompletionContext, nullptr)";
      goto LABEL_37;
    }
  }
LABEL_64:
  v110 = 0;
  v111 = 0;
  v107[0] = 0;
  v108 = 0;
  v109 = 0;
  Windows::Rtl::StopWatch::Start((Windows::Rtl::StopWatch *)v107);
  v125 = 0;
  v124 = 0;
  v46 = 0;
  v64 = 0;
  v126 = 0;
  v127 = 0;
  v128 = 0;
  v129 = 0;
  v130 = 0;
  v131 = 0;
  if ( (a1 & 0x18) != 0 )
  {
    v47 = RMContext::Initialize((RMContext *)&v124, v45, &v64);
    v16 = v47;
    if ( v47 < 0 )
    {
      v100 = v47;
LABEL_110:
      RMContext::~RMContext((RMContext *)&v124);
      Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v107);
      goto LABEL_111;
    }
    v46 = v64;
  }
  v48 = (a1 >> 5) & 1;
  if ( v46 )
  {
    v48 |= 4u;
    if ( (a1 & 8) != 0 )
      v48 |= 2u;
  }
  v120 = 0;
  v121 = 0;
  v117[0] = 0;
  v118 = 0;
  v119 = 0;
  v115 = 0;
  v116 = 0;
  v112[0] = 0;
  v113 = 0;
  v114 = 0;
  if ( !v101[0] )
  {
    v49 = v65;
    while ( 1 )
    {
      v133 = 0;
      memset_0(v132, 0, 0x50u);
      v134 = v66;
      v135 = v67;
      v136 = 0;
      v49(v67, v132, &v136, v101);
      if ( v101[0] )
        goto LABEL_95;
      if ( (_DWORD)v136 == 9
        || (_DWORD)v136 == 10
        || (_DWORD)v136 == 11
        || (_DWORD)v136 == 12
        || (_DWORD)v136 == 13
        || (v50 = 0, (_DWORD)v136 == 19) )
      {
        v50 = 1;
      }
      v51 = (Windows::Rtl::StopWatch *)v112;
      if ( v50 )
        v51 = (Windows::Rtl::StopWatch *)v117;
      Windows::Rtl::StopWatch::Start(v51);
      v52 = ExecuteSingleOperation(v48, a7, v132, v97, &v124);
      Windows::Rtl::StopWatch::Stop(v51);
      v54 = v86;
      if ( !v86 )
      {
        SendProgress(v53, v132, v106);
        v54 = v86;
      }
      if ( v52 < 0 )
        break;
      v52 = v99;
      if ( v99 < 0 )
        break;
      ++v12;
      FireDoneOperation::~FireDoneOperation((FireDoneOperation *)v132);
      if ( v101[0] )
        goto LABEL_96;
    }
    if ( v54 )
    {
      v85 = v52;
      v55 = IoCompletionContext::WaitForThreads((IoCompletionContext *)&v80);
      v16 = v55;
      if ( v55 < 0 )
        goto LABEL_92;
    }
    if ( !a9 )
    {
      if ( v52 >= 0 )
      {
        INTERNAL_ERROR_ACTION(-1073741595);
        JUMPOUT(0x1802C4BADLL);
      }
      v100 = v52;
      FireDoneOperation::~FireDoneOperation((FireDoneOperation *)v132);
      Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v112);
      Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v117);
      RMContext::~RMContext((RMContext *)&v124);
      Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v107);
      Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v102);
      v16 = v52;
      goto LABEL_112;
    }
    *(_DWORD *)(a9 + 4) = v136;
    *(_DWORD *)a9 = v52;
    *(_QWORD *)(a9 + 16) = v12;
    v55 = RtlpGenerateDiagnosabilityString(&v136, a9 + 24);
    v16 = v55;
    if ( v55 < 0 )
    {
LABEL_92:
      v100 = v55;
      FireDoneOperation::~FireDoneOperation((FireDoneOperation *)v132);
      goto LABEL_109;
    }
LABEL_95:
    FireDoneOperation::~FireDoneOperation((FireDoneOperation *)v132);
  }
LABEL_96:
  v56 = (_QWORD *)v105;
  if ( v105 )
  {
    *v56 += Windows::Rtl::StopWatch::ElapsedMilliseconds((Windows::Rtl::StopWatch *)v117);
    v56[1] += Windows::Rtl::StopWatch::ElapsedMilliseconds((Windows::Rtl::StopWatch *)v112);
  }
  if ( v86 )
  {
    v57 = IoCompletionContext::WaitForThreads((IoCompletionContext *)&v80);
    v16 = v57;
    if ( v57 < 0 )
    {
      v100 = v57;
LABEL_109:
      Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v112);
      Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v117);
      goto LABEL_110;
    }
    if ( v86 )
    {
      if ( v85 >= 0 )
      {
        if ( v83 != v84 )
        {
          v106 = v83;
          v105 = v84;
          Windows::WCP::Rtl::RtlAutoTrace<unsigned __int64,unsigned __int64>(
            v84,
            v58,
            v59,
            (__int64)&v106,
            (__int64)&v105);
          v69[2] = 4191;
          v69[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
          v69[3] = 0;
          v69[1] = "RtlRunPrimitiveOperationsFromCallbacksAgainstSil";
          v16 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                  &v100,
                  v69,
                  3221225701LL);
          goto LABEL_109;
        }
      }
      else if ( !a9 )
      {
        v16 = v85;
        v100 = v85;
        goto LABEL_109;
      }
    }
  }
  RMContext::Close((RMContext *)&v124);
  Windows::Rtl::StopWatch::Stop((Windows::Rtl::StopWatch *)v107);
  if ( Windows::WCP::Rtl::RtlIsTracingEnabled(
         (Windows::WCP::Rtl *)&Windows::WCP::Rtl::Facility_POQ,
         (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)0x20000,
         v61) )
  {
    Windows::WCP::Rtl::RtlAutoTrace<Windows::Rtl::StopWatch>(1, v62, "CSI Perf Trace\nCSIPERF:POQEXECUTE:{}\n", v107);
  }
  v140 = 1;
  Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v112);
  Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v117);
  RMContext::~RMContext((RMContext *)&v124);
  Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v107);
  Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v102);
  IoCompletionContext::~IoCompletionContext((IoCompletionContext *)&v80);
  OperationContext::~OperationContext((OperationContext *)v97);
  PoqContext::~PoqContext((PoqContext *)v89);
  Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,0>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,0>(v139);
  return (unsigned int)v100;
}

```

## disassembly

```asm
0x1802c3d80  push    rbp
0x1802c3d82  push    rbx
0x1802c3d83  push    rsi
0x1802c3d84  push    rdi
0x1802c3d85  push    r12
0x1802c3d87  push    r13
0x1802c3d89  push    r14
0x1802c3d8b  push    r15
0x1802c3d8d  lea     rbp, [rsp-4E8h]
0x1802c3d95  sub     rsp, 5E8h
0x1802c3d9c  mov     rax, cs:__security_cookie
0x1802c3da3  xor     rax, rsp
0x1802c3da6  mov     [rbp+520h+var_50], rax
0x1802c3dad  mov     rax, [rbp+520h+arg_48]
0x1802c3db4  mov     rbx, r8
0x1802c3db7  mov     rsi, [rbp+520h+arg_38]
0x1802c3dbe  mov     r13d, ecx
0x1802c3dc1  mov     r14, [rbp+520h+arg_40]
0x1802c3dc8  lea     rcx, ?Facility_POQ@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; this
0x1802c3dcf  mov     rdi, [rbp+520h+arg_20]
0x1802c3dd6  xor     r12d, r12d
0x1802c3dd9  mov     r15, [rbp+520h+arg_30]
0x1802c3de0  mov     [rbp+520h+var_2D0], rax
0x1802c3de7  mov     rax, [rbp+520h+arg_28]
0x1802c3dee  mov     [rsp+620h+var_5A8], rax
0x1802c3df3  mov     [rsp+620h+var_5B0], r9
0x1802c3df8  mov     [rsp+620h+var_5B8], rbx
0x1802c3dfd  mov     [rbp+520h+var_2C8], rsi
0x1802c3e04  mov     [rbp+520h+var_2F0], r12d
0x1802c3e0b  call    ?RtlGetFacilityTracingFlags@Rtl@WCP@Windows@@YAKPEAU_RTL_TRACING_FACILITY@123@@Z; Windows::WCP::Rtl::RtlGetFacilityTracingFlags(Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)
0x1802c3e10  lea     rcx, ?Facility_POQ@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_POQ
0x1802c3e17  mov     [rbp+520h+var_108], r12d
0x1802c3e1e  mov     [rbp+520h+var_F8], r12b
0x1802c3e25  mov     [rbp+520h+var_128], 1
0x1802c3e2f  call    ?ShouldArm@?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$0A@@Rtl@WCP@Windows@@SA_NPEAU_RTL_TRACING_FACILITY@234@@Z; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,0>::ShouldArm(Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)
0x1802c3e34  lea     r9, aRtlrunprimitiv; "RtlRunPrimitiveOperationsFromCallbacksA"...
0x1802c3e3b  test    al, al
0x1802c3e3d  jz      short loc_1802C3E8C
0x1802c3e3f  mov     qword ptr [rsp+620h+var_5D0], r12; unsigned int
0x1802c3e44  lea     rax, ?Facility_POQ@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_POQ
0x1802c3e4b  mov     [rsp+620h+var_5D8], r12; __int64
0x1802c3e50  lea     r8, [rbp+520h+var_2F0]; int
0x1802c3e57  mov     [rsp+620h+var_5E0], r12; __int64
0x1802c3e5c  lea     rcx, [rbp+520h+var_130]; int
0x1802c3e63  mov     [rsp+620h+var_5E8], r12; __int64
0x1802c3e68  xor     edx, edx; int
0x1802c3e6a  mov     [rsp+620h+var_5F0], rax; Windows::WCP::Rtl *
0x1802c3e6f  mov     [rsp+620h+var_5F8], r9; __int64
0x1802c3e74  lea     r9, ?RtlTraceFormat_PCNTSTATUS@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; int
0x1802c3e7b  mov     qword ptr [rsp+620h+InitialState], r12; __int64
0x1802c3e80  call    ?Arm@?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$0A@@Rtl@WCP@Windows@@QEAAXKAEBUCSimpleNtStatusCarryingFrame@2ErrorHandling@4@P6AXPEAUIRtlFormattedOutputStream@24@PEBX@Z2QEBDPEAU_RTL_TRACING_FACILITY@234@444_KZZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,0>::Arm(ulong,Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame const &,void (*)(Windows::Rtl::IRtlFormattedOutputStream *,void const *),void const *,char const * const,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,char const * const,char const * const,unsigned __int64,...)
0x1802c3e85  lea     r9, aRtlrunprimitiv; "RtlRunPrimitiveOperationsFromCallbacksA"...
0x1802c3e8c  xorps   xmm0, xmm0
0x1802c3e8f  mov     [rbp+520h+var_2EC], r12b
0x1802c3e96  xorps   xmm1, xmm1
0x1802c3e99  movdqa  [rbp+520h+var_3D0], xmm0
0x1802c3ea1  movdqa  [rbp+520h+var_3C0], xmm1
0x1802c3ea9  lea     rcx, [rbp+520h+var_370]; this
0x1802c3eb0  movdqa  [rbp+520h+var_3A0], xmm0
0x1802c3eb8  movdqa  [rbp+520h+var_390], xmm1
0x1802c3ec0  mov     [rbp+520h+var_3B0], r12
0x1802c3ec7  mov     [rbp+520h+var_3A8], r12
0x1802c3ece  mov     [rbp+520h+var_380], r12d
0x1802c3ed5  mov     [rbp+520h+var_37C], r12d
0x1802c3edc  mov     [rbp+520h+var_378], r12w
0x1802c3ee4  call    ??0OperationContext@@QEAA@XZ; OperationContext::OperationContext(void)
0x1802c3ee9  mov     [rbp+520h+var_3F0], r12b
0x1802c3ef0  xorps   xmm2, xmm2
0x1802c3ef3  movdqa  [rbp+520h+var_420], xmm2
0x1802c3efb  xorps   xmm3, xmm3
0x1802c3efe  movdqa  [rbp+520h+var_410], xmm3
0x1802c3f06  mov     [rbp+520h+var_400], r12d
0x1802c3f0d  mov     [rbp+520h+var_3FC], r12d
0x1802c3f14  mov     [rbp+520h+var_3F8], r12d
0x1802c3f1b  mov     [rbp+520h+var_3F4], r12d
0x1802c3f22  mov     [rbp+520h+var_3E8], r12
0x1802c3f29  mov     [rbp+520h+var_3E0], r12
0x1802c3f30  test    r14, r14
0x1802c3f33  jz      short loc_1802C3F46
0x1802c3f35  xorps   xmm0, xmm0
0x1802c3f38  movups  xmmword ptr [r14], xmm0
0x1802c3f3c  movups  xmmword ptr [r14+10h], xmm0
0x1802c3f41  movups  xmmword ptr [r14+20h], xmm0
0x1802c3f46  test    r13d, 0FFFFFCC6h
0x1802c3f4d  jz      short loc_1802C3F83
0x1802c3f4f  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c3f56  mov     [rbp+520h+var_4B8], r9
0x1802c3f5a  mov     [rbp+520h+var_4C0], rax
0x1802c3f5e  lea     rdx, [rbp+520h+var_4C0]
0x1802c3f62  lea     rax, aValidFlagsChec_0; "Valid flags check failed: Flags"
0x1802c3f69  mov     [rbp+520h+var_4B0], 0F92h
0x1802c3f71  lea     rcx, [rbp+520h+var_2F0]
0x1802c3f78  mov     [rbp+520h+var_4A8], rax
0x1802c3f7c  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1802c3f81  jmp     short loc_1802C3FC9
0x1802c3f83  test    r15, r15
0x1802c3f86  jnz     short loc_1802C3FD0
0x1802c3f88  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c3f8f  mov     [rbp+520h+var_498], r9
0x1802c3f96  mov     [rbp+520h+var_4A0], rax
0x1802c3f9d  lea     rdx, [rbp+520h+var_4A0]
0x1802c3fa4  lea     rax, aNotNullCheckFa_25; "Not-null check failed: IsoLayer"
0x1802c3fab  mov     [rbp+520h+var_490], 0F94h
0x1802c3fb6  mov     [rbp+520h+var_488], rax
0x1802c3fbd  lea     rcx, [rbp+520h+var_2F0]
0x1802c3fc4  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1802c3fc9  mov     ebx, eax
0x1802c3fcb  jmp     loc_1802C4A7F
0x1802c3fd0  test    rbx, rbx
0x1802c3fd3  jnz     short loc_1802C400C
0x1802c3fd5  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c3fdc  mov     [rbp+520h+var_478], r9
0x1802c3fe3  mov     [rbp+520h+var_480], rax
0x1802c3fea  lea     rdx, [rbp+520h+var_480]
0x1802c3ff1  lea     rax, aNotNullCheckFa_60; "Not-null check failed: GetOperationCall"...
0x1802c3ff8  mov     [rbp+520h+var_470], 0F95h
0x1802c4003  mov     [rbp+520h+var_468], rax
0x1802c400a  jmp     short loc_1802C3FBD
0x1802c400c  mov     rax, [r15]
0x1802c400f  lea     r8, [rbp+520h+var_2E8]
0x1802c4016  lea     rdx, _GUID_bf537349_9167_47f4_a8a8_df3c233df232
0x1802c401d  mov     [rbp+520h+var_2E8], r12
0x1802c4024  mov     rcx, r15
0x1802c4027  mov     rax, [rax+8]
0x1802c402b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4030  mov     ebx, eax
0x1802c4032  test    eax, eax
0x1802c4034  jns     short loc_1802C4041
0x1802c4036  mov     [rbp+520h+var_2F0], eax
0x1802c403c  jmp     loc_1802C4A73
0x1802c4041  mov     rcx, [rbp+520h+var_2E8]
0x1802c4048  lea     rax, [rbp+520h+var_3D0]
0x1802c404f  mov     [rbp+520h+var_308], rax
0x1802c4056  mov     [rbp+520h+var_3B0], rdi
0x1802c405d  mov     rax, [rcx]
0x1802c4060  mov     rax, [rax+10h]
0x1802c4064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4069  mov     rcx, rax; this
0x1802c406c  call    ?IsUnbufferedSil@CSystemIsolationLayer@SystemImplementation@Rtl@Windows@@QEBA_NXZ; Windows::Rtl::SystemImplementation::CSystemIsolationLayer::IsUnbufferedSil(void)
0x1802c4071  mov     byte ptr [rbp+520h+var_37C], al
0x1802c4077  lea     rcx, [rbp+520h+var_3D0]; this
0x1802c407e  mov     al, r13b
0x1802c4081  mov     qword ptr [rbp+520h+var_3A0], r14
0x1802c4088  and     al, 1
0x1802c408a  mov     qword ptr [rbp+520h+var_3A0+8], rsi
0x1802c4091  mov     byte ptr [rbp+520h+var_37C+1], al
0x1802c4097  mov     rdx, r15; struct Windows::Rtl::IRtlSystemIsolationLayerPublic *
0x1802c409a  mov     eax, r13d
0x1802c409d  shr     eax, 9
0x1802c40a0  and     al, 1
0x1802c40a2  mov     byte ptr [rbp+520h+var_378+1], al
0x1802c40a8  lea     rax, [rbp+520h+var_420]
0x1802c40af  mov     [rbp+520h+var_3A8], rax
0x1802c40b6  call    ?Initialize@PendingDeletesHelper@Rtl@Windows@@QEAAJPEAUIRtlSystemIsolationLayerPublic@23@PEAUIRtlDirectory@23@PEAVIUpdateReserveManager@@@Z; Windows::Rtl::PendingDeletesHelper::Initialize(Windows::Rtl::IRtlSystemIsolationLayerPublic *,Windows::Rtl::IRtlDirectory *,IUpdateReserveManager *)
0x1802c40bb  mov     ebx, eax
0x1802c40bd  test    eax, eax
0x1802c40bf  js      loc_1802C4036
0x1802c40c5  cmp     [rbp+520h+var_340], r12
0x1802c40cc  jz      short loc_1802C40CF
0x1802c40ce  int     3; Trap to Debugger
0x1802c40cf  lea     rdx, [rbp+520h+var_340]
0x1802c40d6  mov     rcx, r15
0x1802c40d9  call    ??$CreateRequiredInterface@UIRtlSystemIsolationLayer@Rtl@Windows@@@IRtlObject@Rtl@Windows@@QEAAJPEAV?$Auto@PEAUIRtlSystemIsolationLayer@Rtl@Windows@@@2@@Z; Windows::Rtl::IRtlObject::CreateRequiredInterface<Windows::Rtl::IRtlSystemIsolationLayer>(Windows::Auto<Windows::Rtl::IRtlSystemIsolationLayer *> *)
0x1802c40de  mov     ebx, eax
0x1802c40e0  test    eax, eax
0x1802c40e2  js      loc_1802C4036
0x1802c40e8  cmp     byte ptr [rbp+520h+var_378+1], r12b
0x1802c40ef  jnz     loc_1802C422F
0x1802c40f5  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0M@U_LUNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0FM@@0FD@@0HJ@@0HD@@0HE@@0GF@@0GN@@0FC@@0GP@@0GP@@0HE@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@@Details@RtlStringLiterals@@3U_LUNICODE_STRING@@B; struct _LUNICODE_STRING *
0x1802c40fc  lea     rcx, [rbp+520h+var_370]; this
0x1802c4103  call    ?TryAddProtectedPath@SafeOpenCreateHelper@@QEAAJAEBU_LUNICODE_STRING@@@Z; SafeOpenCreateHelper::TryAddProtectedPath(_LUNICODE_STRING const &)
0x1802c4108  mov     ebx, eax
0x1802c410a  test    eax, eax
0x1802c410c  js      loc_1802C4036
0x1802c4112  mov     rax, [r15]
0x1802c4115  lea     r9, [rbp+520h+var_2E0]
0x1802c411c  xor     r8d, r8d
0x1802c411f  mov     [rbp+520h+var_2E0], r12
0x1802c4126  xor     edx, edx
0x1802c4128  mov     qword ptr [rsp+620h+InitialState], r12
0x1802c412d  mov     rcx, r15
0x1802c4130  mov     rax, [rax+80h]
0x1802c4137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c413c  mov     ebx, eax
0x1802c413e  test    eax, eax
0x1802c4140  jns     short loc_1802C4159
0x1802c4142  mov     [rbp+520h+var_2F0], eax
0x1802c4148  lea     rcx, [rbp+520h+var_2E0]
0x1802c414f  call    ??1?$Auto@PEAUIRtlIniFile@Rtl@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(void)
0x1802c4154  jmp     loc_1802C4A73
0x1802c4159  mov     rcx, [rbp+520h+var_2E0]
0x1802c4160  lea     r9, [rbp+520h+var_248]
0x1802c4167  xor     eax, eax
0x1802c4169  mov     qword ptr [rsp+620h+InitialState], r12
0x1802c416e  mov     [rbp+520h+var_238], rax
0x1802c4175  xorps   xmm0, xmm0
0x1802c4178  movups  [rbp+520h+var_248], xmm0
0x1802c417f  mov     rax, [rcx]
0x1802c4182  xor     edx, edx
0x1802c4184  mov     r8d, 100000h
0x1802c418a  mov     rax, [rax+20h]
0x1802c418e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4193  mov     ebx, eax
0x1802c4195  test    eax, eax
0x1802c4197  jns     short loc_1802C41AD
0x1802c4199  mov     [rbp+520h+var_2F0], eax
0x1802c419f  lea     rcx, [rbp+520h+var_248]
0x1802c41a6  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1802c41ab  jmp     short loc_1802C4148
0x1802c41ad  mov     rax, [r15]
0x1802c41b0  lea     rdx, [rbp+520h+var_248]
0x1802c41b7  mov     r8d, 80000000h
0x1802c41bd  mov     rcx, r15
0x1802c41c0  mov     rax, [rax+0B0h]
0x1802c41c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c41cc  test    al, al
0x1802c41ce  jz      short loc_1802C4217
0x1802c41d0  lea     r9, [rbp+520h+var_2D8]
0x1802c41d7  mov     [rbp+520h+var_2D8], r12
0x1802c41de  lea     r8, [rbp+520h+var_248]
0x1802c41e5  mov     qword ptr [rsp+620h+InitialState], r12; __int64
0x1802c41ea  xor     edx, edx
0x1802c41ec  lea     rcx, [rbp+520h+var_370]; this
0x1802c41f3  call    ?SafeOpenDirectory@SafeOpenCreateHelper@@QEAAJW4SafeOpenDirectoryFlags@1@AEBU_LUNICODE_STRING@@PEAV?$Auto@PEAUIRtlDirectory@Rtl@Windows@@@Windows@@PEAW4SafeOpenDirectoryDisposition@1@@Z; SafeOpenCreateHelper::SafeOpenDirectory(SafeOpenCreateHelper::SafeOpenDirectoryFlags,_LUNICODE_STRING const &,Windows::Auto<Windows::Rtl::IRtlDirectory *> *,SafeOpenCreateHelper::SafeOpenDirectoryDisposition *)
0x1802c41f8  lea     rcx, [rbp+520h+var_2D8]
0x1802c41ff  mov     ebx, eax
0x1802c4201  test    eax, eax
0x1802c4203  jns     short loc_1802C4212
0x1802c4205  mov     [rbp+520h+var_2F0], eax
0x1802c420b  call    ??1?$Auto@PEAUIRtlIniFile@Rtl@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(void)
0x1802c4210  jmp     short loc_1802C419F
0x1802c4212  call    ??1?$Auto@PEAUIRtlIniFile@Rtl@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(void)
0x1802c4217  lea     rcx, [rbp+520h+var_248]
0x1802c421e  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1802c4223  lea     rcx, [rbp+520h+var_2E0]
0x1802c422a  call    ??1?$Auto@PEAUIRtlIniFile@Rtl@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(void)
0x1802c422f  bt      r13d, 8
0x1802c4234  jnb     short loc_1802C4246
0x1802c4236  mov     word ptr [rbp+520h+var_37C+2], 101h
0x1802c423f  mov     byte ptr [rbp+520h+var_378], 1
0x1802c4246  mov     rdi, r12
0x1802c4249  cmp     byte ptr [rbp+520h+var_37C], r12b
0x1802c4250  jz      loc_1802C42F7
0x1802c4256  mov     ebx, 40h ; '@'
0x1802c425b  lea     rcx, [rbp+520h+SystemInformation]; void *
0x1802c4262  mov     r8d, ebx; Size
0x1802c4265  xor     edx, edx; Val
0x1802c4267  call    memset_0
0x1802c426c  xor     r9d, r9d; ReturnLength
0x1802c426f  lea     rdx, [rbp+520h+SystemInformation]; SystemInformation
0x1802c4276  mov     r8d, ebx; SystemInformationLength
0x1802c4279  xor     ecx, ecx; SystemInformationClass
0x1802c427b  call    cs:__imp_NtQuerySystemInformation
0x1802c4282  nop     dword ptr [rax+rax+00h]
0x1802c4287  mov     r8d, eax
0x1802c428a  test    eax, eax
0x1802c428c  jns     short loc_1802C42DD
0x1802c428e  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c4295  mov     [rbp+520h+var_450], 0FCBh
0x1802c42a0  mov     [rbp+520h+var_460], rax
0x1802c42a7  lea     rdx, [rbp+520h+var_460]
0x1802c42ae  lea     rax, aRtlrunprimitiv; "RtlRunPrimitiveOperationsFromCallbacksA"...
0x1802c42b5  mov     [rbp+520h+var_458], rax
0x1802c42bc  lea     rax, aNtquerysystemi; "NtQuerySystemInformation(SystemBasicInf"...
0x1802c42c3  mov     [rbp+520h+var_448], rax
0x1802c42ca  lea     rcx, [rbp+520h+var_2F0]
0x1802c42d1  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1802c42d6  mov     ebx, eax
0x1802c42d8  jmp     loc_1802C4A73
0x1802c42dd  mov     al, [rbp+520h+var_138]
0x1802c42e3  cmp     al, 2
0x1802c42e5  jge     short loc_1802C42EB
0x1802c42e7  mov     al, 2
0x1802c42e9  jmp     short loc_1802C42F1
0x1802c42eb  mov     cl, 0Ah
0x1802c42ed  cmp     al, cl
0x1802c42ef  jg      short loc_1802C42F3
0x1802c42f1  mov     cl, al
0x1802c42f3  movsx   rdi, cl
0x1802c42f7  mov     rax, [r15]
0x1802c42fa  lea     rdx, [rbp+520h+var_3E8]
0x1802c4301  mov     rcx, r15
0x1802c4304  mov     rax, [rax+68h]
0x1802c4308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c430d  mov     ebx, eax
0x1802c430f  test    eax, eax
0x1802c4311  js      loc_1802C4036
0x1802c4317  mov     [rbp+520h+var_3E0], r15
0x1802c431e  cmp     byte ptr [rbp+520h+var_37C+1], r12b
0x1802c4325  jz      short loc_1802C437D
0x1802c4327  cmp     byte ptr [rbp+520h+var_37C], r12b
0x1802c432e  jnz     short loc_1802C437D
0x1802c4330  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c4337  mov     [rbp+520h+var_430], 0FD9h
0x1802c4342  mov     [rbp+520h+var_440], rax
0x1802c4349  lea     rdx, [rbp+520h+var_440]
0x1802c4350  lea     rax, aRtlrunprimitiv; "RtlRunPrimitiveOperationsFromCallbacksA"...
0x1802c4357  mov     [rbp+520h+var_438], rax
0x1802c435e  lea     rcx, [rbp+520h+var_2F0]
0x1802c4365  lea     rax, aGlobalcontextF; "!GlobalContext.fPendingDeletesBehavior "...
  ... truncated ...
```
