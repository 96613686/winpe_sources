# Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey(ulong,Windows::Rtl::SystemImplementation::CSilHandle *,ulong,_OBJECT_ATTRIBUTES &,ulong,_UNICODE_STRING *,ulong,Windows::Rtl::KtmTransactionInfoPointer,ulong *)

- ea: `0x180124100`
- end: `0x180124b76`
- name: `?SysCreateKey@DirectRegistryProvider@SystemImplementation@Rtl@Windows@@UEAAJKPEAVCSilHandle@234@KAEAU_OBJECT_ATTRIBUTES@@KPEAU_UNICODE_STRING@@KUKtmTransactionInfoPointer@34@PEAK@Z`
- size: `2678`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800031d0`
- `0x18000aedc`
- `0x180030b68`
- `0x1800497c0`
- `0x18004f088`
- `0x18004f350`
- `0x18004fcf0`
- `0x1801189d4`
- `0x18011ae2c`
- `0x18011c474`
- `0x18011ccac`
- `0x18011f29c`
- `0x180120970`
- `0x180121cd0`
- `0x180124100`
- `0x18012d3a0`
- `0x18012fa2c`
- `0x180130944`
- `0x1801a28c0`
- `0x1801bd010`

## import_xrefs

- `ntdll!NtCreateKeyTransacted` at `0x1801246db`
- `ntdll!NtCreateKeyTransacted` at `0x18012477f`
- `ntdll!NtCreateKeyTransacted` at `0x1801246db`
- `ntdll!NtCreateKeyTransacted` at `0x18012477f`
- `ntdll!NtCreateKey` at `0x1801246a5`
- `ntdll!NtCreateKey` at `0x180124749`
- `ntdll!NtCreateKey` at `0x1801246a5`
- `ntdll!NtCreateKey` at `0x180124749`
- `ntdll!NtClose` at `0x180124337`
- `ntdll!NtClose` at `0x1801243cb`
- `ntdll!NtClose` at `0x180124442`
- `ntdll!NtClose` at `0x180124982`
- `ntdll!NtClose` at `0x180124b15`
- `ntdll!NtClose` at `0x180124337`
- `ntdll!NtClose` at `0x1801243cb`
- `ntdll!NtClose` at `0x180124442`
- `ntdll!NtClose` at `0x180124982`
- `ntdll!NtClose` at `0x180124b15`

## string_xrefs

- `0x1801245e8`: `DesiredAccess`
- `0x1801241b4`: `Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey`
- `0x180124388`: `Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey`
- `0x1801245d3`: `Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey`
- `0x180124ac8`: `Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey`
- `0x1801249c8`: `Failed to create key {key}, desired access {da} object attributes {oa} titleindex {ti} class {class} createoptions {co}`
- `0x1801247b7`: `Transient insufficient resources at NtCreateKey for {oa}`

## pseudocode

```c
__int64 __fastcall Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey(
        __int64 a1,
        struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *a2,
        __int64 *a3,
        ACCESS_MASK a4,
        __int128 *a5,
        ULONG TitleIndex,
        struct _UNICODE_STRING *a7,
        ULONG a8,
        _QWORD *a9,
        _DWORD *a10)
{
  _DWORD *v10; // rdi
  struct _UNICODE_STRING *v11; // rbx
  char v13; // r12
  char FacilityTracingFlags; // al
  Windows::Rtl::SystemImplementation::DirectRegistryProvider *v16; // rcx
  const struct _UNICODE_STRING *v17; // rdx
  int IsUnacceptableKeyPrefix; // eax
  int v19; // ebx
  HANDLE v20; // rax
  HANDLE v21; // rcx
  void (*v22)(void); // rax
  HANDLE v23; // rcx
  _QWORD *v24; // rbx
  __int64 v25; // rdx
  int v26; // eax
  bool *v27; // rdx
  int CanSetSystemOwner; // esi
  HANDLE v29; // rcx
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  bool v34; // al
  struct _SECURITY_DESCRIPTOR *v35; // rax
  int v36; // eax
  NTSTATUS v37; // eax
  bool *v38; // r8
  unsigned int v39; // esi
  int v40; // eax
  NTSTATUS v41; // eax
  __int64 v42; // r9
  __int64 v43; // rsi
  const struct _SECURITY_DESCRIPTOR *v44; // rax
  __int64 v45; // rcx
  HANDLE v46; // rcx
  HANDLE v47; // rcx
  ULONG CreateOptions[2]; // [rsp+28h] [rbp-158h]
  ULONG CreateOptionsa[2]; // [rsp+28h] [rbp-158h]
  __int64 v50; // [rsp+40h] [rbp-140h]
  bool v51[4]; // [rsp+100h] [rbp-80h] BYREF
  __int128 v52; // [rsp+108h] [rbp-78h] BYREF
  PUNICODE_STRING Class; // [rsp+118h] [rbp-68h]
  const char *v54; // [rsp+120h] [rbp-60h] BYREF
  const char *v55; // [rsp+128h] [rbp-58h]
  __int64 v56; // [rsp+130h] [rbp-50h]
  const char *v57; // [rsp+138h] [rbp-48h]
  struct _SECURITY_DESCRIPTOR *v58; // [rsp+140h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+148h] [rbp-38h] BYREF
  unsigned int v60; // [rsp+178h] [rbp-8h] BYREF
  HANDLE Handle; // [rsp+180h] [rbp+0h] BYREF
  ACCESS_MASK DesiredAccess; // [rsp+188h] [rbp+8h] BYREF
  ULONG Disposition[4]; // [rsp+190h] [rbp+10h] BYREF
  __int128 v64; // [rsp+1A0h] [rbp+20h] BYREF
  __int64 v65; // [rsp+1B0h] [rbp+30h]
  char v66; // [rsp+1B8h] [rbp+38h]
  __int16 v67; // [rsp+1BAh] [rbp+3Ah]
  __int128 v68; // [rsp+1C0h] [rbp+40h]
  __int128 v69; // [rsp+1D0h] [rbp+50h]
  _BYTE v70[8]; // [rsp+1E0h] [rbp+60h] BYREF
  int v71; // [rsp+1E8h] [rbp+68h]
  int v72; // [rsp+208h] [rbp+88h]
  char v73; // [rsp+218h] [rbp+98h]

  v10 = a10;
  v11 = a7;
  DesiredAccess = a4;
  v13 = (char)a2;
  Class = a7;
  v60 = 0;
  Handle = 0;
  Disposition[0] = 0;
  v52 = 0;
  if ( a10 )
    *a10 = 0;
  v72 = 0;
  v73 = 0;
  v71 = 1;
  FacilityTracingFlags = Windows::WCP::Rtl::RtlGetFacilityTracingFlags(
                           (Windows::WCP::Rtl *)&Windows::WCP::Rtl::Facility_SIL,
                           a2);
  v16 = (Windows::Rtl::SystemImplementation::DirectRegistryProvider *)"Windows::Rtl::SystemImplementation::DirectRegistry"
                                                                      "Provider::SysCreateKey";
  if ( (FacilityTracingFlags & 0xE) != 0 )
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::Arm(
      v70,
      &v60,
      Windows::WCP::Rtl::RtlTraceFormat_PCNTSTATUS,
      a1,
      "Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey",
      &Windows::WCP::Rtl::Facility_SIL,
      "(key = {key}, da = {da}, oa = {oa}, ti = {ti}, class = {class}, co = {co})\n",
      "(key = {key}, da = {da}, oa = {oa}, ti = {ti}, class = {class}, co = {co}, disp = {disp})\n",
      "(key = {key}, disp = {disp})\n",
      7,
      "key",
      Windows::Rtl::SystemImplementation::CSilHandle::Format_PCSilHandle,
      a3,
      "da",
      Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsRegKeyDesiredAccess,
      &DesiredAccess,
      "oa",
      Windows::WCP::Rtl::RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectHandleObject,
      a5,
      "ti",
      Windows::WCP::Rtl::RtlTraceFormat_PCULONG,
      &TitleIndex,
      "class",
      Windows::WCP::Rtl::RtlTraceFormat_PCUNICODE_STRING,
      v11,
      "co",
      Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsRegKeyCreateOptions,
      &a8,
      "disp",
      Windows::Rtl::SystemImplementation::IRtlRegistryProvider::Format_PCULONG_AsSysCreateKeyDisposition,
      v10);
  v17 = (const struct _UNICODE_STRING *)*((_QWORD *)a5 + 2);
  v51[0] = 0;
  IsUnacceptableKeyPrefix = Windows::Rtl::SystemImplementation::DirectRegistryProvider::IsUnacceptableKeyPrefix(
                              v16,
                              v17,
                              v51);
  v19 = IsUnacceptableKeyPrefix;
  if ( IsUnacceptableKeyPrefix < 0 )
  {
    v60 = IsUnacceptableKeyPrefix;
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(v70);
    v20 = Handle;
    if ( (char *)Handle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      goto LABEL_9;
    Handle = 0;
    v21 = v20;
    goto LABEL_8;
  }
  if ( v51[0] )
  {
    v56 = 5253;
    v54 = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
    v57 = 0;
    v55 = "Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey";
    v60 = -1073741767;
    RtlReportErrorOrigination(&v54, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225529LL);
    v19 = v60;
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(v70);
    v23 = Handle;
    if ( (char *)Handle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      goto LABEL_15;
    Handle = 0;
    goto LABEL_14;
  }
  v24 = a9;
  if ( a9 )
    v25 = *a9;
  else
    v25 = 0;
  v26 = Windows::Rtl::SystemImplementation::DirectHandleObjectBase<Windows::Rtl::SystemImplementation::DirectHandleObject>::ValidateTransaction(
          a5,
          v25);
  CanSetSystemOwner = v26;
  if ( v26 < 0 )
  {
    v60 = v26;
LABEL_22:
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(v70);
    if ( (char *)Handle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
LABEL_25:
      Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v52);
      if ( (_QWORD)v52 )
        (**(void (__fastcall ***)(_QWORD))v52)(v52);
      return (unsigned int)CanSetSystemOwner;
    }
    v29 = Handle;
LABEL_24:
    Handle = 0;
    NtClose(v29);
    goto LABEL_25;
  }
  DesiredAccess |= 0x100u;
  v67 = 0;
  v64 = 0;
  v68 = 0;
  v31 = *a5;
  v51[1] = 0;
  v69 = 0;
  v32 = a5[1];
  v51[2] = 0;
  *(_OWORD *)&ObjectAttributes.Length = v31;
  v65 = 0;
  v33 = a5[2];
  v66 = 0;
  *(_OWORD *)&ObjectAttributes.ObjectName = v32;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = v33;
  if ( (_QWORD)v33 || (v13 & 4) != 0 )
  {
    v50 = 0;
    CreateOptions[1] = 0;
    v36 = Windows::Rtl::SystemImplementation::IRtlObjectProvider::CalculateSecurityForCreate(
            a1,
            25,
            ObjectAttributes.RootDirectory,
            ObjectAttributes.ObjectName);
    CanSetSystemOwner = v36;
    if ( v36 < 0 )
    {
      v60 = v36;
      Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v64);
      Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(v70);
      if ( (char *)Handle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
        goto LABEL_25;
      v29 = Handle;
      goto LABEL_24;
    }
    if ( (v67 & 0x400) != 0 )
    {
      if ( (DesiredAccess & 0x40000) == 0 )
      {
        v56 = 5283;
LABEL_44:
        v60 = -1073741811;
        v54 = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
        v55 = "Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey";
        v57 = "DesiredAccess";
        RtlReportErrorOrigination(&v54, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
        v19 = v60;
        Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v64);
        Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(v70);
        v23 = Handle;
        if ( (char *)Handle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
        {
LABEL_15:
          Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v52);
          if ( (_QWORD)v52 )
          {
            v22 = **(void (***)(void))v52;
            goto LABEL_106;
          }
          return (unsigned int)v19;
        }
        Handle = 0;
LABEL_14:
        NtClose(v23);
        goto LABEL_15;
      }
      v51[1] = 1;
    }
    if ( (v67 & 0x800) != 0 )
    {
      if ( (DesiredAccess & 0x1000000) == 0 )
      {
        v56 = 5292;
        goto LABEL_44;
      }
      v51[2] = 1;
    }
    v35 = (struct _SECURITY_DESCRIPTOR *)Windows::Rtl::SecurityDescriptor::Get((Windows::Rtl::SecurityDescriptor *)&v64);
    goto LABEL_52;
  }
  if ( (a8 & 4) != 0 )
  {
    v34 = 1;
  }
  else
  {
    v51[0] = 0;
    CanSetSystemOwner = Windows::WCP::Implementation::Rtl::CanSetSystemOwner(
                          (Windows::WCP::Implementation::Rtl *)v51,
                          v27);
    if ( CanSetSystemOwner < 0 )
      goto LABEL_33;
    v34 = v51[0];
  }
  if ( !v34 )
    goto LABEL_53;
  v58 = 0;
  CanSetSystemOwner = Windows::WCP::Implementation::Rtl::GetSystemSecurity(
                        (Windows::WCP::Implementation::Rtl *)&v58,
                        (struct _SECURITY_DESCRIPTOR **)v27);
  if ( CanSetSystemOwner < 0 )
    goto LABEL_33;
  v35 = v58;
LABEL_52:
  ObjectAttributes.SecurityDescriptor = v35;
LABEL_53:
  if ( ObjectAttributes.RootDirectory )
    ObjectAttributes.RootDirectory = *(HANDLE *)ObjectAttributes.RootDirectory;
  if ( v24 )
  {
    CreateOptions[0] = a8;
    v37 = NtCreateKeyTransacted(
            &Handle,
            DesiredAccess,
            &ObjectAttributes,
            TitleIndex,
            Class,
            *(_QWORD *)CreateOptions,
            *v24,
            Disposition,
            v50);
  }
  else
  {
    v37 = NtCreateKey(&Handle, DesiredAccess, &ObjectAttributes, TitleIndex, Class, a8, Disposition);
  }
  v39 = v37;
  if ( v37 == -1073741670 )
  {
    LODWORD(v58) = 0;
    v51[0] = 1;
    while ( 1 )
    {
      v40 = Windows::Rtl::SystemImplementation::DelayForInsufficientResources(
              (Windows::Rtl::SystemImplementation *)&v58,
              (unsigned int *)v51,
              v38);
      CanSetSystemOwner = v40;
      if ( v40 < 0 )
        break;
      if ( v24 )
      {
        CreateOptionsa[0] = a8;
        v41 = NtCreateKeyTransacted(
                &Handle,
                DesiredAccess,
                &ObjectAttributes,
                TitleIndex,
                Class,
                *(_QWORD *)CreateOptionsa,
                *v24,
                Disposition,
                v50);
      }
      else
      {
        v41 = NtCreateKey(&Handle, DesiredAccess, &ObjectAttributes, TitleIndex, Class, a8, Disposition);
      }
      v39 = v41;
      if ( !v51[0] || v41 != -1073741670 )
      {
        if ( v41 < 0 )
          goto LABEL_88;
        Windows::WCP::Rtl::RtlTrace(
          0,
          (unsigned int)&Windows::WCP::Rtl::Facility_SIL,
          (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)"Transient insufficient resources at NtCreateKey for {oa}",
          (const char *const)1,
          (unsigned __int64)"oa",
          Windows::WCP::Rtl::RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectHandleObject,
          a5);
        goto LABEL_71;
      }
    }
    v60 = v40;
    Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v64);
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(v70);
    v29 = Handle;
    if ( (char *)Handle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      goto LABEL_25;
    goto LABEL_24;
  }
  if ( v37 < 0 )
  {
LABEL_88:
    if ( (v39 == -1073741772 || v39 == -1073741766) && (v13 & 1) != 0 )
    {
      if ( v10 )
        *v10 = 3;
    }
    else
    {
      if ( v39 != -1073741790 || (v13 & 2) == 0 )
      {
        Windows::WCP::Rtl::RtlTrace(
          (Windows::WCP::Rtl *)2,
          (unsigned int)&Windows::WCP::Rtl::Facility_SIL,
          (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)"Failed to create key {key}, desired access {da} object attr"
                                                             "ibutes {oa} titleindex {ti} class {class} createoptions {co}",
          (const char *const)6,
          (unsigned __int64)"key",
          Windows::Rtl::SystemImplementation::CSilHandle::Format_PCSilHandle,
          a3,
          "da",
          Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsRegKeyDesiredAccess,
          &DesiredAccess,
          "oa",
          Windows::WCP::Rtl::RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectHandleObject,
          a5,
          "ti",
          Windows::WCP::Rtl::RtlTraceFormat_PCULONG,
          &TitleIndex,
          "class",
          Windows::WCP::Rtl::RtlTraceFormat_PCUNICODE_STRING,
          Class,
          "co",
          Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsRegKeyCreateOptions,
          &a8);
        v56 = 5455;
        v54 = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
        v57 = 0;
        v55 = "Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey";
        v60 = v39;
        RtlReportErrorOrigination(&v54, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, v39);
        v19 = v60;
        Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v64);
        Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(v70);
        v47 = Handle;
        if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          Handle = 0;
          NtClose(v47);
        }
        Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v52);
        if ( !(_QWORD)v52 )
          return (unsigned int)v19;
        v22 = **(void (***)(void))v52;
        goto LABEL_106;
      }
      if ( v10 )
        *v10 = 4;
    }
    goto LABEL_97;
  }
LABEL_71:
  if ( v24 )
    v42 = *v24;
  else
    v42 = 0;
  CanSetSystemOwner = Windows::Rtl::SystemImplementation::DirectHandleObjectBase<Windows::Rtl::SystemImplementation::DirectHandleObject>::Create(
                        a1,
                        &Handle,
                        &v52,
                        v42);
  if ( CanSetSystemOwner < 0 )
  {
LABEL_33:
    v60 = CanSetSystemOwner;
    Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v64);
    goto LABEL_22;
  }
  if ( Disposition[0] == 1 )
  {
    v43 = *((_QWORD *)&v52 + 1);
    if ( v51[1] || v51[2] )
    {
      v19 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 32LL))(a1, 2, *((_QWORD *)&v52 + 1));
      if ( v19 < 0 )
        goto LABEL_79;
    }
    if ( v10 )
      *v10 = 1;
  }
  else
  {
    v44 = Windows::Rtl::SecurityDescriptor::Get((Windows::Rtl::SecurityDescriptor *)&v64);
    v43 = *((_QWORD *)&v52 + 1);
    if ( (v13 & 4) != 0 )
    {
      v19 = Windows::Rtl::SystemImplementation::IRtlObjectProvider::EnsureSetSecurityIfRequired(
              a1,
              *((_QWORD *)&v52 + 1),
              v44,
              v24);
      if ( v19 < 0 )
      {
LABEL_79:
        v60 = v19;
        Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v64);
        Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(v70);
        v21 = Handle;
        if ( (char *)Handle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
        {
LABEL_9:
          Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v52);
          if ( (_QWORD)v52 )
          {
            v22 = **(void (***)(void))v52;
LABEL_106:
            v22();
            return (unsigned int)v19;
          }
          return (unsigned int)v19;
        }
        Handle = 0;
LABEL_8:
        NtClose(v21);
        goto LABEL_9;
      }
    }
    if ( v10 )
      *v10 = 2;
  }
  v45 = *a3;
  *((_QWORD *)&v52 + 1) = a3[1];
  *a3 = v52;
  a3[1] = v43;
  *(_QWORD *)&v52 = v45;
LABEL_97:
  v73 = 1;
  Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v64);
  Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(v70);
  v46 = Handle;
  if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    Handle = 0;
    NtClose(v46);
  }
  Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v52);
  if ( (_QWORD)v52 )
    (**(void (__fastcall ***)(_QWORD))v52)(v52);
  return v60;
}

```

## disassembly

```asm
0x180124100  mov     [rsp-8+arg_8], rbx
0x180124105  push    rbp
0x180124106  push    rsi
0x180124107  push    rdi
0x180124108  push    r12
0x18012410a  push    r13
0x18012410c  push    r14
0x18012410e  push    r15
0x180124110  lea     rbp, [rsp-1F0h]
0x180124118  sub     rsp, 370h
0x18012411f  mov     rax, cs:__security_cookie
0x180124126  xor     rax, rsp
0x180124129  mov     [rbp+220h+var_40], rax
0x180124130  mov     rdi, [rbp+220h+arg_48]
0x180124137  xor     esi, esi
0x180124139  mov     rbx, [rbp+220h+arg_30]
0x180124140  xorps   xmm0, xmm0
0x180124143  mov     r13, [rbp+220h+arg_20]
0x18012414a  mov     r15, r8
0x18012414d  mov     [rbp+220h+DesiredAccess], r9d
0x180124151  mov     r12d, edx
0x180124154  mov     [rbp+220h+var_288], rbx
0x180124158  mov     r14, rcx
0x18012415b  mov     [rbp+220h+var_228], esi
0x18012415e  mov     [rbp+220h+Handle], rsi
0x180124162  mov     [rbp+220h+var_210], esi
0x180124165  movdqu  [rbp+220h+var_298], xmm0
0x18012416a  test    rdi, rdi
0x18012416d  jz      short loc_180124171
0x18012416f  mov     [rdi], esi
0x180124171  lea     rcx, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; this
0x180124178  mov     [rbp+220h+var_198], esi
0x18012417e  mov     [rbp+220h+var_188], sil
0x180124185  mov     [rbp+220h+var_1B8], 1
0x18012418c  call    ?RtlGetFacilityTracingFlags@Rtl@WCP@Windows@@YAKPEAU_RTL_TRACING_FACILITY@123@@Z; Windows::WCP::Rtl::RtlGetFacilityTracingFlags(Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)
0x180124191  lea     r9, ?RtlTraceFormat_PCULONG_AsRegKeyCreateOptions@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsRegKeyCreateOptions(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180124198  lea     r10, aCo; "co"
0x18012419f  lea     r11, ?RtlTraceFormat_PCUNICODE_STRING@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCUNICODE_STRING(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x1801241a6  lea     rdx, ?RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectHandleObject@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectHandleObject(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x1801241ad  lea     r8, aOa; "oa"
0x1801241b4  lea     rcx, aWindowsRtlSyst_60; "Windows::Rtl::SystemImplementation::Dir"...
0x1801241bb  test    al, 0Eh
0x1801241bd  jz      loc_1801242FF
0x1801241c3  mov     [rsp+3A0h+var_2B0], rdi
0x1801241cb  lea     rax, ?Format_PCULONG_AsSysCreateKeyDisposition@IRtlRegistryProvider@SystemImplementation@Rtl@Windows@@SAXPEAUIRtlFormattedOutputStream@34@PEBX@Z; Windows::Rtl::SystemImplementation::IRtlRegistryProvider::Format_PCULONG_AsSysCreateKeyDisposition(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x1801241d2  mov     [rsp+3A0h+var_2B8], rax
0x1801241da  lea     rax, aDisp; "disp"
0x1801241e1  mov     [rsp+3A0h+var_2C0], rax
0x1801241e9  lea     rax, [rbp+220h+arg_38]
0x1801241f0  mov     [rsp+3A0h+var_2C8], rax
0x1801241f8  lea     rax, aClass; "class"
0x1801241ff  mov     [rsp+3A0h+var_2D0], r9
0x180124207  mov     r9, r14
0x18012420a  mov     [rsp+3A0h+var_2D8], r10
0x180124212  mov     [rsp+3A0h+var_2E0], rbx
0x18012421a  mov     [rsp+3A0h+var_2E8], r11
0x180124222  mov     [rsp+3A0h+var_2F0], rax
0x18012422a  lea     rax, [rbp+220h+TitleIndex]
0x180124231  mov     [rsp+3A0h+var_2F8], rax
0x180124239  lea     rax, ?RtlTraceFormat_PCULONG@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180124240  mov     [rsp+3A0h+var_300], rax
0x180124248  lea     rax, aTi; "ti"
0x18012424f  mov     [rsp+3A0h+var_308], rax
0x180124257  lea     rax, [rbp+220h+DesiredAccess]
0x18012425b  mov     [rsp+3A0h+var_310], r13
0x180124263  mov     [rsp+3A0h+var_318], rdx
0x18012426b  lea     rdx, [rbp+220h+var_228]
0x18012426f  mov     [rsp+3A0h+var_320], r8
0x180124277  lea     r8, ?RtlTraceFormat_PCNTSTATUS@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCNTSTATUS(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18012427e  mov     [rsp+3A0h+var_328], rax
0x180124283  lea     rax, ?RtlTraceFormat_PCULONG_AsRegKeyDesiredAccess@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsRegKeyDesiredAccess(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18012428a  mov     [rsp+3A0h+var_330], rax
0x18012428f  lea     rax, aDa; "da"
0x180124296  mov     [rsp+3A0h+var_338], rax
0x18012429b  lea     rax, ?Format_PCSilHandle@CSilHandle@SystemImplementation@Rtl@Windows@@SAXPEAUIRtlFormattedOutputStream@34@PEBX@Z; Windows::Rtl::SystemImplementation::CSilHandle::Format_PCSilHandle(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x1801242a2  mov     [rsp+3A0h+var_340], r15
0x1801242a7  mov     [rsp+3A0h+var_348], rax
0x1801242ac  lea     rax, aKey; "key"
0x1801242b3  mov     [rsp+3A0h+var_350], rax
0x1801242b8  lea     rax, aKeyKeyDispDisp_0; "(key = {key}, disp = {disp})\n"
0x1801242bf  mov     [rsp+3A0h+var_358], 7
0x1801242c8  mov     [rsp+3A0h+var_360], rax
0x1801242cd  lea     rax, aKeyKeyDaDaOaOa; "(key = {key}, da = {da}, oa = {oa}, ti "...
0x1801242d4  mov     [rsp+3A0h+var_368], rax
0x1801242d9  lea     rax, aKeyKeyDaDaOaOa_0; "(key = {key}, da = {da}, oa = {oa}, ti "...
0x1801242e0  mov     [rsp+3A0h+Disposition], rax
0x1801242e5  lea     rax, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_SIL
0x1801242ec  mov     qword ptr [rsp+3A0h+CreateOptions], rax
0x1801242f1  mov     [rsp+3A0h+Class], rcx
0x1801242f6  lea     rcx, [rbp+220h+var_1C0]
0x1801242fa  call    ?Arm@?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$06@Rtl@WCP@Windows@@QEAAXAEBUCSimpleNtStatusCarryingFrame@2ErrorHandling@4@P6AXPEAUIRtlFormattedOutputStream@24@PEBX@Z2QEBDPEAU_RTL_TRACING_FACILITY@234@444_KZZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::Arm(Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame const &,void (*)(Windows::Rtl::IRtlFormattedOutputStream *,void const *),void const *,char const * const,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,char const * const,char const * const,unsigned __int64,...)
0x1801242ff  mov     rdx, [r13+10h]; struct _UNICODE_STRING *
0x180124303  lea     r8, [rbp+220h+var_2A0]; bool *
0x180124307  mov     [rbp+220h+var_2A0], sil
0x18012430b  call    ?IsUnacceptableKeyPrefix@DirectRegistryProvider@SystemImplementation@Rtl@Windows@@AEAAJAEBU_UNICODE_STRING@@PEA_N@Z; Windows::Rtl::SystemImplementation::DirectRegistryProvider::IsUnacceptableKeyPrefix(_UNICODE_STRING const &,bool *)
0x180124310  mov     ebx, eax
0x180124312  test    eax, eax
0x180124314  jns     short loc_180124364
0x180124316  lea     rcx, [rbp+220h+var_1C0]
0x18012431a  mov     [rbp+220h+var_228], eax
0x18012431d  call    ??1?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$06@Rtl@WCP@Windows@@QEAA@XZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(void)
0x180124322  mov     rax, [rbp+220h+Handle]
0x180124326  lea     rcx, [rax-1]
0x18012432a  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18012432e  ja      short loc_180124343
0x180124330  mov     [rbp+220h+Handle], rsi
0x180124334  mov     rcx, rax; Handle
0x180124337  call    cs:__imp_NtClose
0x18012433e  nop     dword ptr [rax+rax+00h]
0x180124343  lea     rcx, [rbp+220h+var_298]; this
0x180124347  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x18012434c  mov     rcx, qword ptr [rbp+220h+var_298]
0x180124350  test    rcx, rcx
0x180124353  jz      loc_180124B3E
0x180124359  mov     rax, [rcx]
0x18012435c  mov     rax, [rax]
0x18012435f  jmp     loc_180124B39
0x180124364  cmp     [rbp+220h+var_2A0], sil
0x180124368  jz      loc_1801243FB
0x18012436e  lea     rax, aOnecoreBaseWcp_30; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x180124375  mov     [rbp+220h+var_270], 1485h
0x18012437d  mov     [rbp+220h+var_280], rax
0x180124381  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180124388  lea     rax, aWindowsRtlSyst_60; "Windows::Rtl::SystemImplementation::Dir"...
0x18012438f  mov     [rbp+220h+var_268], rsi
0x180124393  mov     r8d, 0C0000039h
0x180124399  mov     [rbp+220h+var_278], rax
0x18012439d  lea     rcx, [rbp+220h+var_280]
0x1801243a1  mov     [rbp+220h+var_228], 0C0000039h
0x1801243a8  call    RtlReportErrorOrigination
0x1801243ad  mov     ebx, [rbp+220h+var_228]
0x1801243b0  lea     rcx, [rbp+220h+var_1C0]
0x1801243b4  call    ??1?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$06@Rtl@WCP@Windows@@QEAA@XZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(void)
0x1801243b9  mov     rcx, [rbp+220h+Handle]; Handle
0x1801243bd  lea     rax, [rcx-1]
0x1801243c1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801243c5  ja      short loc_1801243D7
0x1801243c7  mov     [rbp+220h+Handle], rsi
0x1801243cb  call    cs:__imp_NtClose
0x1801243d2  nop     dword ptr [rax+rax+00h]
0x1801243d7  lea     rcx, [rbp+220h+var_298]; this
0x1801243db  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x1801243e0  mov     rdx, qword ptr [rbp+220h+var_298]
0x1801243e4  test    rdx, rdx
0x1801243e7  jz      loc_180124B3E
0x1801243ed  mov     rcx, [rdx]
0x1801243f0  mov     rax, [rcx]
0x1801243f3  mov     rcx, rdx
0x1801243f6  jmp     loc_180124B39
0x1801243fb  mov     rbx, [rbp+220h+arg_40]
0x180124402  test    rbx, rbx
0x180124405  jz      short loc_18012440C
0x180124407  mov     rdx, [rbx]
0x18012440a  jmp     short loc_18012440F
0x18012440c  mov     rdx, rsi
0x18012440f  mov     rcx, r13
0x180124412  call    ?ValidateTransaction@?$DirectHandleObjectBase@UDirectHandleObject@SystemImplementation@Rtl@Windows@@@SystemImplementation@Rtl@Windows@@SAJAEAU_OBJECT_ATTRIBUTES@@PEAX@Z; Windows::Rtl::SystemImplementation::DirectHandleObjectBase<Windows::Rtl::SystemImplementation::DirectHandleObject>::ValidateTransaction(_OBJECT_ATTRIBUTES &,void *)
0x180124417  mov     esi, eax
0x180124419  test    eax, eax
0x18012441b  jns     short loc_180124472
0x18012441d  mov     [rbp+220h+var_228], eax
0x180124420  lea     rcx, [rbp+220h+var_1C0]
0x180124424  call    ??1?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$06@Rtl@WCP@Windows@@QEAA@XZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(void)
0x180124429  mov     rax, [rbp+220h+Handle]
0x18012442d  lea     rcx, [rax-1]
0x180124431  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180124435  ja      short loc_18012444E
0x180124437  mov     rcx, rax; Handle
0x18012443a  mov     [rbp+220h+Handle], 0
0x180124442  call    cs:__imp_NtClose
0x180124449  nop     dword ptr [rax+rax+00h]
0x18012444e  lea     rcx, [rbp+220h+var_298]; this
0x180124452  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x180124457  mov     rcx, qword ptr [rbp+220h+var_298]
0x18012445b  test    rcx, rcx
0x18012445e  jz      short loc_18012446B
0x180124460  mov     rax, [rcx]
0x180124463  mov     rax, [rax]
0x180124466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012446b  mov     eax, esi
0x18012446d  jmp     loc_180124B40
0x180124472  bts     [rbp+220h+DesiredAccess], 8
0x180124477  xor     eax, eax
0x180124479  xorps   xmm0, xmm0
0x18012447c  mov     [rbp+220h+var_1E6], ax
0x180124480  movdqa  [rbp+220h+var_200], xmm0
0x180124485  xorps   xmm1, xmm1
0x180124488  movdqa  [rbp+220h+var_1E0], xmm0
0x18012448d  movups  xmm0, xmmword ptr [r13+0]
0x180124492  mov     [rbp+220h+var_2A0+1], al
0x180124495  movdqa  [rbp+220h+var_1D0], xmm1
0x18012449a  movups  xmm1, xmmword ptr [r13+10h]
0x18012449f  mov     [rbp+220h+var_2A0+2], al
0x1801244a2  movups  xmmword ptr [rbp+220h+ObjectAttributes.Length], xmm0
0x1801244a6  mov     [rbp+220h+var_1F0], 0
0x1801244ae  movups  xmm0, xmmword ptr [r13+20h]
0x1801244b3  mov     [rbp+220h+var_1E8], 0
0x1801244b7  movups  xmmword ptr [rbp+220h+ObjectAttributes.ObjectName], xmm1
0x1801244bb  movq    rax, xmm0
0x1801244c0  movups  xmmword ptr [rbp+220h+ObjectAttributes.SecurityDescriptor], xmm0
0x1801244c4  test    rax, rax
0x1801244c7  jnz     short loc_18012452B
0x1801244c9  test    r12b, 4
0x1801244cd  jnz     short loc_18012452B
0x1801244cf  test    byte ptr [rbp+220h+arg_38], 4
0x1801244d6  jz      short loc_1801244DC
0x1801244d8  mov     al, 1
0x1801244da  jmp     short loc_180124503
0x1801244dc  lea     rcx, [rbp+220h+var_2A0]; this
0x1801244e0  mov     [rbp+220h+var_2A0], 0
0x1801244e4  call    ?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z; Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)
0x1801244e9  mov     esi, eax
0x1801244eb  test    eax, eax
0x1801244ed  jns     short loc_180124500
0x1801244ef  lea     rcx, [rbp+220h+var_200]
0x1801244f3  mov     [rbp+220h+var_228], esi
0x1801244f6  call    ?Close@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAXXZ; Windows::Auto<_SECURITY_DESCRIPTOR>::Close(void)
0x1801244fb  jmp     loc_180124420
0x180124500  mov     al, [rbp+220h+var_2A0]
0x180124503  test    al, al
0x180124505  jz      loc_180124662
0x18012450b  lea     rcx, [rbp+220h+var_260]; this
0x18012450f  mov     [rbp+220h+var_260], 0
0x180124517  call    ?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)
0x18012451c  mov     esi, eax
0x18012451e  test    eax, eax
0x180124520  js      short loc_1801244EF
0x180124522  mov     rax, [rbp+220h+var_260]
0x180124526  jmp     loc_18012465E
0x18012452b  mov     r9, [rbp+220h+ObjectAttributes.ObjectName]
0x18012452f  lea     rcx, [rbp+220h+var_200]
0x180124533  mov     r8, [rbp+220h+ObjectAttributes.RootDirectory]
0x180124537  mov     edx, 19h
0x18012453c  mov     [rsp+3A0h+var_360], 0
0x180124545  mov     [rsp+3A0h+var_368], rcx
0x18012454a  mov     rcx, r14
0x18012454d  mov     [rsp+3A0h+Disposition], rbx
0x180124552  mov     qword ptr [rsp+3A0h+CreateOptions], 0
0x18012455b  mov     [rsp+3A0h+Class], rax
0x180124560  call    ?CalculateSecurityForCreate@IRtlObjectProvider@SystemImplementation@Rtl@Windows@@QEAAJW4CalculateInheritedSecurityFlags@1234@PEAXAEBU_UNICODE_STRING@@11UKtmTransactionInfoPointer@34@PEAVSecurityDescriptor@34@4@Z; Windows::Rtl::SystemImplementation::IRtlObjectProvider::CalculateSecurityForCreate(Windows::Rtl::SystemImplementation::IRtlObjectProvider::CalculateInheritedSecurityFlags,void *,_UNICODE_STRING const &,void *,void *,Windows::Rtl::KtmTransactionInfoPointer,Windows::Rtl::SecurityDescriptor *,Windows::Rtl::SecurityDescriptor *)
0x180124565  mov     esi, eax
0x180124567  test    eax, eax
0x180124569  jns     short loc_18012459A
0x18012456b  lea     rcx, [rbp+220h+var_200]
0x18012456f  mov     [rbp+220h+var_228], eax
0x180124572  call    ?Close@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAXXZ; Windows::Auto<_SECURITY_DESCRIPTOR>::Close(void)
0x180124577  lea     rcx, [rbp+220h+var_1C0]
0x18012457b  call    ??1?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$06@Rtl@WCP@Windows@@QEAA@XZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(void)
0x180124580  mov     rdx, [rbp+220h+Handle]
0x180124584  lea     rcx, [rdx-1]
0x180124588  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18012458c  ja      loc_18012444E
0x180124592  mov     rcx, rdx
0x180124595  jmp     loc_18012443A
0x18012459a  mov     eax, 400h
0x18012459f  test    [rbp+220h+var_1E6], ax
0x1801245a3  jz      loc_180124630
0x1801245a9  test    [rbp+220h+DesiredAccess], 40000h
0x1801245b0  jnz     short loc_18012462C
0x1801245b2  mov     [rbp+220h+var_270], 14A3h
0x1801245ba  lea     rax, aOnecoreBaseWcp_30; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x1801245c1  mov     [rbp+220h+var_228], 0C000000Dh
0x1801245c8  mov     [rbp+220h+var_280], rax
0x1801245cc  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801245d3  lea     rax, aWindowsRtlSyst_60; "Windows::Rtl::SystemImplementation::Dir"...
0x1801245da  mov     r8d, 0C000000Dh
0x1801245e0  mov     [rbp+220h+var_278], rax
0x1801245e4  lea     rcx, [rbp+220h+var_280]
0x1801245e8  lea     rax, aDesiredaccess; "DesiredAccess"
0x1801245ef  mov     [rbp+220h+var_268], rax
0x1801245f3  call    RtlReportErrorOrigination
0x1801245f8  mov     ebx, [rbp+220h+var_228]
0x1801245fb  lea     rcx, [rbp+220h+var_200]
0x1801245ff  call    ?Close@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAXXZ; Windows::Auto<_SECURITY_DESCRIPTOR>::Close(void)
0x180124604  lea     rcx, [rbp+220h+var_1C0]
0x180124608  call    ??1?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$06@Rtl@WCP@Windows@@QEAA@XZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(void)
0x18012460d  mov     rcx, [rbp+220h+Handle]
0x180124611  lea     rax, [rcx-1]
0x180124615  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180124619  ja      loc_1801243D7
0x18012461f  mov     [rbp+220h+Handle], 0
0x180124627  jmp     loc_1801243CB
0x18012462c  mov     [rbp+220h+var_2A0+1], 1
0x180124630  mov     eax, 800h
0x180124635  test    [rbp+220h+var_1E6], ax
0x180124639  jz      short loc_180124655
0x18012463b  test    [rbp+220h+DesiredAccess], 1000000h
0x180124642  jnz     short loc_180124651
0x180124644  mov     [rbp+220h+var_270], 14ACh
0x18012464c  jmp     loc_1801245BA
0x180124651  mov     [rbp+220h+var_2A0+2], 1
0x180124655  lea     rcx, [rbp+220h+var_200]; this
0x180124659  call    ?Get@SecurityDescriptor@Rtl@Windows@@QEBAPEBU_SECURITY_DESCRIPTOR@@XZ; Windows::Rtl::SecurityDescriptor::Get(void)
0x18012465e  mov     [rbp+220h+ObjectAttributes.SecurityDescriptor], rax
0x180124662  mov     rax, [rbp+220h+ObjectAttributes.RootDirectory]
0x180124666  test    rax, rax
0x180124669  jz      short loc_180124672
0x18012466b  mov     rax, [rax]
0x18012466e  mov     [rbp+220h+ObjectAttributes.RootDirectory], rax
0x180124672  mov     r9d, [rbp+220h+TitleIndex]; TitleIndex
  ... truncated ...
```
