# Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey(ulong,Windows::Rtl::SystemImplementation::CSilHandle *,ulong,_OBJECT_ATTRIBUTES &,ulong,_UNICODE_STRING *,ulong,Windows::Rtl::KtmTransactionInfoPointer,ulong *)

- ea: `0x1801873f0`
- end: `0x180187e66`
- name: `?SysCreateKey@DirectRegistryProvider@SystemImplementation@Rtl@Windows@@UEAAJKPEAVCSilHandle@234@KAEAU_OBJECT_ATTRIBUTES@@KPEAU_UNICODE_STRING@@KUKtmTransactionInfoPointer@34@PEAK@Z`
- size: `2678`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800059d0`
- `0x1800692fc`
- `0x18017bc04`
- `0x18017dfdc`
- `0x18017f6c4`
- `0x18017ffa4`
- `0x18018258c`
- `0x180183c60`
- `0x180184fc0`
- `0x1801873f0`
- `0x180190700`
- `0x180192cec`
- `0x180193c04`
- `0x1801e4d48`
- `0x1801efdc0`
- `0x1801f35b8`
- `0x1801f3880`
- `0x1801f4220`
- `0x1801f5b50`
- `0x1802b1010`

## import_xrefs

- `ntdll!NtCreateKey` at `0x180187995`
- `ntdll!NtCreateKey` at `0x180187a39`
- `ntdll!NtCreateKey` at `0x180187995`
- `ntdll!NtCreateKey` at `0x180187a39`
- `ntdll!NtCreateKeyTransacted` at `0x1801879cb`
- `ntdll!NtCreateKeyTransacted` at `0x180187a6f`
- `ntdll!NtCreateKeyTransacted` at `0x1801879cb`
- `ntdll!NtCreateKeyTransacted` at `0x180187a6f`
- `ntdll!NtClose` at `0x180187627`
- `ntdll!NtClose` at `0x1801876bb`
- `ntdll!NtClose` at `0x180187732`
- `ntdll!NtClose` at `0x180187c72`
- `ntdll!NtClose` at `0x180187e05`
- `ntdll!NtClose` at `0x180187627`
- `ntdll!NtClose` at `0x1801876bb`
- `ntdll!NtClose` at `0x180187732`
- `ntdll!NtClose` at `0x180187c72`
- `ntdll!NtClose` at `0x180187e05`

## string_xrefs

- `0x1801874a4`: `Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey`
- `0x180187678`: `Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey`
- `0x1801878c3`: `Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey`
- `0x180187db8`: `Windows::Rtl::SystemImplementation::DirectRegistryProvider::SysCreateKey`
- `0x1801878d8`: `DesiredAccess`
- `0x180187aa7`: `Transient insufficient resources at NtCreateKey for {oa}`
- `0x180187cb8`: `Failed to create key {key}, desired access {da} object attributes {oa} titleindex {ti} class {class} createoptions {co}`

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
0x1801873f0  mov     [rsp-8+arg_8], rbx
0x1801873f5  push    rbp
0x1801873f6  push    rsi
0x1801873f7  push    rdi
0x1801873f8  push    r12
0x1801873fa  push    r13
0x1801873fc  push    r14
0x1801873fe  push    r15
0x180187400  lea     rbp, [rsp-1F0h]
0x180187408  sub     rsp, 370h
0x18018740f  mov     rax, cs:__security_cookie
0x180187416  xor     rax, rsp
0x180187419  mov     [rbp+220h+var_40], rax
0x180187420  mov     rdi, [rbp+220h+arg_48]
0x180187427  xor     esi, esi
0x180187429  mov     rbx, [rbp+220h+arg_30]
0x180187430  xorps   xmm0, xmm0
0x180187433  mov     r13, [rbp+220h+arg_20]
0x18018743a  mov     r15, r8
0x18018743d  mov     [rbp+220h+DesiredAccess], r9d
0x180187441  mov     r12d, edx
0x180187444  mov     [rbp+220h+var_288], rbx
0x180187448  mov     r14, rcx
0x18018744b  mov     [rbp+220h+var_228], esi
0x18018744e  mov     [rbp+220h+Handle], rsi
0x180187452  mov     [rbp+220h+var_210], esi
0x180187455  movdqu  [rbp+220h+var_298], xmm0
0x18018745a  test    rdi, rdi
0x18018745d  jz      short loc_180187461
0x18018745f  mov     [rdi], esi
0x180187461  lea     rcx, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; this
0x180187468  mov     [rbp+220h+var_198], esi
0x18018746e  mov     [rbp+220h+var_188], sil
0x180187475  mov     [rbp+220h+var_1B8], 1
0x18018747c  call    ?RtlGetFacilityTracingFlags@Rtl@WCP@Windows@@YAKPEAU_RTL_TRACING_FACILITY@123@@Z; Windows::WCP::Rtl::RtlGetFacilityTracingFlags(Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)
0x180187481  lea     r9, ?RtlTraceFormat_PCULONG_AsRegKeyCreateOptions@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsRegKeyCreateOptions(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180187488  lea     r10, aCo; "co"
0x18018748f  lea     r11, ?RtlTraceFormat_PCUNICODE_STRING@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCUNICODE_STRING(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180187496  lea     rdx, ?RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectHandleObject@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectHandleObject(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18018749d  lea     r8, aOa; "oa"
0x1801874a4  lea     rcx, aWindowsRtlSyst_60; "Windows::Rtl::SystemImplementation::Dir"...
0x1801874ab  test    al, 0Eh
0x1801874ad  jz      loc_1801875EF
0x1801874b3  mov     [rsp+3A0h+var_2B0], rdi
0x1801874bb  lea     rax, ?Format_PCULONG_AsSysCreateKeyDisposition@IRtlRegistryProvider@SystemImplementation@Rtl@Windows@@SAXPEAUIRtlFormattedOutputStream@34@PEBX@Z; Windows::Rtl::SystemImplementation::IRtlRegistryProvider::Format_PCULONG_AsSysCreateKeyDisposition(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x1801874c2  mov     [rsp+3A0h+var_2B8], rax
0x1801874ca  lea     rax, aDisp; "disp"
0x1801874d1  mov     [rsp+3A0h+var_2C0], rax
0x1801874d9  lea     rax, [rbp+220h+arg_38]
0x1801874e0  mov     [rsp+3A0h+var_2C8], rax
0x1801874e8  lea     rax, aClass; "class"
0x1801874ef  mov     [rsp+3A0h+var_2D0], r9
0x1801874f7  mov     r9, r14
0x1801874fa  mov     [rsp+3A0h+var_2D8], r10
0x180187502  mov     [rsp+3A0h+var_2E0], rbx
0x18018750a  mov     [rsp+3A0h+var_2E8], r11
0x180187512  mov     [rsp+3A0h+var_2F0], rax
0x18018751a  lea     rax, [rbp+220h+TitleIndex]
0x180187521  mov     [rsp+3A0h+var_2F8], rax
0x180187529  lea     rax, ?RtlTraceFormat_PCULONG@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180187530  mov     [rsp+3A0h+var_300], rax
0x180187538  lea     rax, aTi; "ti"
0x18018753f  mov     [rsp+3A0h+var_308], rax
0x180187547  lea     rax, [rbp+220h+DesiredAccess]
0x18018754b  mov     [rsp+3A0h+var_310], r13
0x180187553  mov     [rsp+3A0h+var_318], rdx
0x18018755b  lea     rdx, [rbp+220h+var_228]
0x18018755f  mov     [rsp+3A0h+var_320], r8
0x180187567  lea     r8, ?RtlTraceFormat_PCNTSTATUS@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCNTSTATUS(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18018756e  mov     [rsp+3A0h+var_328], rax
0x180187573  lea     rax, ?RtlTraceFormat_PCULONG_AsRegKeyDesiredAccess@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsRegKeyDesiredAccess(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18018757a  mov     [rsp+3A0h+var_330], rax
0x18018757f  lea     rax, aDa; "da"
0x180187586  mov     [rsp+3A0h+var_338], rax
0x18018758b  lea     rax, ?Format_PCSilHandle@CSilHandle@SystemImplementation@Rtl@Windows@@SAXPEAUIRtlFormattedOutputStream@34@PEBX@Z; Windows::Rtl::SystemImplementation::CSilHandle::Format_PCSilHandle(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180187592  mov     [rsp+3A0h+var_340], r15
0x180187597  mov     [rsp+3A0h+var_348], rax
0x18018759c  lea     rax, aKey; "key"
0x1801875a3  mov     [rsp+3A0h+var_350], rax
0x1801875a8  lea     rax, aKeyKeyDispDisp_0; "(key = {key}, disp = {disp})\n"
0x1801875af  mov     [rsp+3A0h+var_358], 7
0x1801875b8  mov     [rsp+3A0h+var_360], rax
0x1801875bd  lea     rax, aKeyKeyDaDaOaOa; "(key = {key}, da = {da}, oa = {oa}, ti "...
0x1801875c4  mov     [rsp+3A0h+var_368], rax
0x1801875c9  lea     rax, aKeyKeyDaDaOaOa_0; "(key = {key}, da = {da}, oa = {oa}, ti "...
0x1801875d0  mov     [rsp+3A0h+Disposition], rax
0x1801875d5  lea     rax, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_SIL
0x1801875dc  mov     qword ptr [rsp+3A0h+CreateOptions], rax
0x1801875e1  mov     [rsp+3A0h+Class], rcx
0x1801875e6  lea     rcx, [rbp+220h+var_1C0]
0x1801875ea  call    ?Arm@?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$06@Rtl@WCP@Windows@@QEAAXAEBUCSimpleNtStatusCarryingFrame@2ErrorHandling@4@P6AXPEAUIRtlFormattedOutputStream@24@PEBX@Z2QEBDPEAU_RTL_TRACING_FACILITY@234@444_KZZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::Arm(Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame const &,void (*)(Windows::Rtl::IRtlFormattedOutputStream *,void const *),void const *,char const * const,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,char const * const,char const * const,unsigned __int64,...)
0x1801875ef  mov     rdx, [r13+10h]; struct _UNICODE_STRING *
0x1801875f3  lea     r8, [rbp+220h+var_2A0]; bool *
0x1801875f7  mov     [rbp+220h+var_2A0], sil
0x1801875fb  call    ?IsUnacceptableKeyPrefix@DirectRegistryProvider@SystemImplementation@Rtl@Windows@@AEAAJAEBU_UNICODE_STRING@@PEA_N@Z; Windows::Rtl::SystemImplementation::DirectRegistryProvider::IsUnacceptableKeyPrefix(_UNICODE_STRING const &,bool *)
0x180187600  mov     ebx, eax
0x180187602  test    eax, eax
0x180187604  jns     short loc_180187654
0x180187606  lea     rcx, [rbp+220h+var_1C0]
0x18018760a  mov     [rbp+220h+var_228], eax
0x18018760d  call    ??1?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$06@Rtl@WCP@Windows@@QEAA@XZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(void)
0x180187612  mov     rax, [rbp+220h+Handle]
0x180187616  lea     rcx, [rax-1]
0x18018761a  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18018761e  ja      short loc_180187633
0x180187620  mov     [rbp+220h+Handle], rsi
0x180187624  mov     rcx, rax; Handle
0x180187627  call    cs:__imp_NtClose
0x18018762e  nop     dword ptr [rax+rax+00h]
0x180187633  lea     rcx, [rbp+220h+var_298]; this
0x180187637  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x18018763c  mov     rcx, qword ptr [rbp+220h+var_298]
0x180187640  test    rcx, rcx
0x180187643  jz      loc_180187E2E
0x180187649  mov     rax, [rcx]
0x18018764c  mov     rax, [rax]
0x18018764f  jmp     loc_180187E29
0x180187654  cmp     [rbp+220h+var_2A0], sil
0x180187658  jz      loc_1801876EB
0x18018765e  lea     rax, aOnecoreBaseWcp_30; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x180187665  mov     [rbp+220h+var_270], 1485h
0x18018766d  mov     [rbp+220h+var_280], rax
0x180187671  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180187678  lea     rax, aWindowsRtlSyst_60; "Windows::Rtl::SystemImplementation::Dir"...
0x18018767f  mov     [rbp+220h+var_268], rsi
0x180187683  mov     r8d, 0C0000039h
0x180187689  mov     [rbp+220h+var_278], rax
0x18018768d  lea     rcx, [rbp+220h+var_280]
0x180187691  mov     [rbp+220h+var_228], 0C0000039h
0x180187698  call    RtlReportErrorOrigination
0x18018769d  mov     ebx, [rbp+220h+var_228]
0x1801876a0  lea     rcx, [rbp+220h+var_1C0]
0x1801876a4  call    ??1?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$06@Rtl@WCP@Windows@@QEAA@XZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(void)
0x1801876a9  mov     rcx, [rbp+220h+Handle]; Handle
0x1801876ad  lea     rax, [rcx-1]
0x1801876b1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801876b5  ja      short loc_1801876C7
0x1801876b7  mov     [rbp+220h+Handle], rsi
0x1801876bb  call    cs:__imp_NtClose
0x1801876c2  nop     dword ptr [rax+rax+00h]
0x1801876c7  lea     rcx, [rbp+220h+var_298]; this
0x1801876cb  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x1801876d0  mov     rdx, qword ptr [rbp+220h+var_298]
0x1801876d4  test    rdx, rdx
0x1801876d7  jz      loc_180187E2E
0x1801876dd  mov     rcx, [rdx]
0x1801876e0  mov     rax, [rcx]
0x1801876e3  mov     rcx, rdx
0x1801876e6  jmp     loc_180187E29
0x1801876eb  mov     rbx, [rbp+220h+arg_40]
0x1801876f2  test    rbx, rbx
0x1801876f5  jz      short loc_1801876FC
0x1801876f7  mov     rdx, [rbx]
0x1801876fa  jmp     short loc_1801876FF
0x1801876fc  mov     rdx, rsi
0x1801876ff  mov     rcx, r13
0x180187702  call    ?ValidateTransaction@?$DirectHandleObjectBase@UDirectHandleObject@SystemImplementation@Rtl@Windows@@@SystemImplementation@Rtl@Windows@@SAJAEAU_OBJECT_ATTRIBUTES@@PEAX@Z; Windows::Rtl::SystemImplementation::DirectHandleObjectBase<Windows::Rtl::SystemImplementation::DirectHandleObject>::ValidateTransaction(_OBJECT_ATTRIBUTES &,void *)
0x180187707  mov     esi, eax
0x180187709  test    eax, eax
0x18018770b  jns     short loc_180187762
0x18018770d  mov     [rbp+220h+var_228], eax
0x180187710  lea     rcx, [rbp+220h+var_1C0]
0x180187714  call    ??1?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$06@Rtl@WCP@Windows@@QEAA@XZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(void)
0x180187719  mov     rax, [rbp+220h+Handle]
0x18018771d  lea     rcx, [rax-1]
0x180187721  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180187725  ja      short loc_18018773E
0x180187727  mov     rcx, rax; Handle
0x18018772a  mov     [rbp+220h+Handle], 0
0x180187732  call    cs:__imp_NtClose
0x180187739  nop     dword ptr [rax+rax+00h]
0x18018773e  lea     rcx, [rbp+220h+var_298]; this
0x180187742  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x180187747  mov     rcx, qword ptr [rbp+220h+var_298]
0x18018774b  test    rcx, rcx
0x18018774e  jz      short loc_18018775B
0x180187750  mov     rax, [rcx]
0x180187753  mov     rax, [rax]
0x180187756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018775b  mov     eax, esi
0x18018775d  jmp     loc_180187E30
0x180187762  bts     [rbp+220h+DesiredAccess], 8
0x180187767  xor     eax, eax
0x180187769  xorps   xmm0, xmm0
0x18018776c  mov     [rbp+220h+var_1E6], ax
0x180187770  movdqa  [rbp+220h+var_200], xmm0
0x180187775  xorps   xmm1, xmm1
0x180187778  movdqa  [rbp+220h+var_1E0], xmm0
0x18018777d  movups  xmm0, xmmword ptr [r13+0]
0x180187782  mov     [rbp+220h+var_2A0+1], al
0x180187785  movdqa  [rbp+220h+var_1D0], xmm1
0x18018778a  movups  xmm1, xmmword ptr [r13+10h]
0x18018778f  mov     [rbp+220h+var_2A0+2], al
0x180187792  movups  xmmword ptr [rbp+220h+ObjectAttributes.Length], xmm0
0x180187796  mov     [rbp+220h+var_1F0], 0
0x18018779e  movups  xmm0, xmmword ptr [r13+20h]
0x1801877a3  mov     [rbp+220h+var_1E8], 0
0x1801877a7  movups  xmmword ptr [rbp+220h+ObjectAttributes.ObjectName], xmm1
0x1801877ab  movq    rax, xmm0
0x1801877b0  movups  xmmword ptr [rbp+220h+ObjectAttributes.SecurityDescriptor], xmm0
0x1801877b4  test    rax, rax
0x1801877b7  jnz     short loc_18018781B
0x1801877b9  test    r12b, 4
0x1801877bd  jnz     short loc_18018781B
0x1801877bf  test    byte ptr [rbp+220h+arg_38], 4
0x1801877c6  jz      short loc_1801877CC
0x1801877c8  mov     al, 1
0x1801877ca  jmp     short loc_1801877F3
0x1801877cc  lea     rcx, [rbp+220h+var_2A0]; this
0x1801877d0  mov     [rbp+220h+var_2A0], 0
0x1801877d4  call    ?CanSetSystemOwner@Rtl@Implementation@WCP@Windows@@YAJPEA_N@Z; Windows::WCP::Implementation::Rtl::CanSetSystemOwner(bool *)
0x1801877d9  mov     esi, eax
0x1801877db  test    eax, eax
0x1801877dd  jns     short loc_1801877F0
0x1801877df  lea     rcx, [rbp+220h+var_200]
0x1801877e3  mov     [rbp+220h+var_228], esi
0x1801877e6  call    ?Close@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAXXZ; Windows::Auto<_SECURITY_DESCRIPTOR>::Close(void)
0x1801877eb  jmp     loc_180187710
0x1801877f0  mov     al, [rbp+220h+var_2A0]
0x1801877f3  test    al, al
0x1801877f5  jz      loc_180187952
0x1801877fb  lea     rcx, [rbp+220h+var_260]; this
0x1801877ff  mov     [rbp+220h+var_260], 0
0x180187807  call    ?GetSystemSecurity@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSecurity(_SECURITY_DESCRIPTOR * *)
0x18018780c  mov     esi, eax
0x18018780e  test    eax, eax
0x180187810  js      short loc_1801877DF
0x180187812  mov     rax, [rbp+220h+var_260]
0x180187816  jmp     loc_18018794E
0x18018781b  mov     r9, [rbp+220h+ObjectAttributes.ObjectName]
0x18018781f  lea     rcx, [rbp+220h+var_200]
0x180187823  mov     r8, [rbp+220h+ObjectAttributes.RootDirectory]
0x180187827  mov     edx, 19h
0x18018782c  mov     [rsp+3A0h+var_360], 0
0x180187835  mov     [rsp+3A0h+var_368], rcx
0x18018783a  mov     rcx, r14
0x18018783d  mov     [rsp+3A0h+Disposition], rbx
0x180187842  mov     qword ptr [rsp+3A0h+CreateOptions], 0
0x18018784b  mov     [rsp+3A0h+Class], rax
0x180187850  call    ?CalculateSecurityForCreate@IRtlObjectProvider@SystemImplementation@Rtl@Windows@@QEAAJW4CalculateInheritedSecurityFlags@1234@PEAXAEBU_UNICODE_STRING@@11UKtmTransactionInfoPointer@34@PEAVSecurityDescriptor@34@4@Z; Windows::Rtl::SystemImplementation::IRtlObjectProvider::CalculateSecurityForCreate(Windows::Rtl::SystemImplementation::IRtlObjectProvider::CalculateInheritedSecurityFlags,void *,_UNICODE_STRING const &,void *,void *,Windows::Rtl::KtmTransactionInfoPointer,Windows::Rtl::SecurityDescriptor *,Windows::Rtl::SecurityDescriptor *)
0x180187855  mov     esi, eax
0x180187857  test    eax, eax
0x180187859  jns     short loc_18018788A
0x18018785b  lea     rcx, [rbp+220h+var_200]
0x18018785f  mov     [rbp+220h+var_228], eax
0x180187862  call    ?Close@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAXXZ; Windows::Auto<_SECURITY_DESCRIPTOR>::Close(void)
0x180187867  lea     rcx, [rbp+220h+var_1C0]
0x18018786b  call    ??1?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$06@Rtl@WCP@Windows@@QEAA@XZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(void)
0x180187870  mov     rdx, [rbp+220h+Handle]
0x180187874  lea     rcx, [rdx-1]
0x180187878  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18018787c  ja      loc_18018773E
0x180187882  mov     rcx, rdx
0x180187885  jmp     loc_18018772A
0x18018788a  mov     eax, 400h
0x18018788f  test    [rbp+220h+var_1E6], ax
0x180187893  jz      loc_180187920
0x180187899  test    [rbp+220h+DesiredAccess], 40000h
0x1801878a0  jnz     short loc_18018791C
0x1801878a2  mov     [rbp+220h+var_270], 14A3h
0x1801878aa  lea     rax, aOnecoreBaseWcp_30; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x1801878b1  mov     [rbp+220h+var_228], 0C000000Dh
0x1801878b8  mov     [rbp+220h+var_280], rax
0x1801878bc  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801878c3  lea     rax, aWindowsRtlSyst_60; "Windows::Rtl::SystemImplementation::Dir"...
0x1801878ca  mov     r8d, 0C000000Dh
0x1801878d0  mov     [rbp+220h+var_278], rax
0x1801878d4  lea     rcx, [rbp+220h+var_280]
0x1801878d8  lea     rax, aDesiredaccess; "DesiredAccess"
0x1801878df  mov     [rbp+220h+var_268], rax
0x1801878e3  call    RtlReportErrorOrigination
0x1801878e8  mov     ebx, [rbp+220h+var_228]
0x1801878eb  lea     rcx, [rbp+220h+var_200]
0x1801878ef  call    ?Close@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAXXZ; Windows::Auto<_SECURITY_DESCRIPTOR>::Close(void)
0x1801878f4  lea     rcx, [rbp+220h+var_1C0]
0x1801878f8  call    ??1?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$06@Rtl@WCP@Windows@@QEAA@XZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,7>(void)
0x1801878fd  mov     rcx, [rbp+220h+Handle]
0x180187901  lea     rax, [rcx-1]
0x180187905  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180187909  ja      loc_1801876C7
0x18018790f  mov     [rbp+220h+Handle], 0
0x180187917  jmp     loc_1801876BB
0x18018791c  mov     [rbp+220h+var_2A0+1], 1
0x180187920  mov     eax, 800h
0x180187925  test    [rbp+220h+var_1E6], ax
0x180187929  jz      short loc_180187945
0x18018792b  test    [rbp+220h+DesiredAccess], 1000000h
0x180187932  jnz     short loc_180187941
0x180187934  mov     [rbp+220h+var_270], 14ACh
0x18018793c  jmp     loc_1801878AA
0x180187941  mov     [rbp+220h+var_2A0+2], 1
0x180187945  lea     rcx, [rbp+220h+var_200]; this
0x180187949  call    ?Get@SecurityDescriptor@Rtl@Windows@@QEBAPEBU_SECURITY_DESCRIPTOR@@XZ; Windows::Rtl::SecurityDescriptor::Get(void)
0x18018794e  mov     [rbp+220h+ObjectAttributes.SecurityDescriptor], rax
0x180187952  mov     rax, [rbp+220h+ObjectAttributes.RootDirectory]
0x180187956  test    rax, rax
0x180187959  jz      short loc_180187962
0x18018795b  mov     rax, [rax]
0x18018795e  mov     [rbp+220h+ObjectAttributes.RootDirectory], rax
0x180187962  mov     r9d, [rbp+220h+TitleIndex]; TitleIndex
  ... truncated ...
```
