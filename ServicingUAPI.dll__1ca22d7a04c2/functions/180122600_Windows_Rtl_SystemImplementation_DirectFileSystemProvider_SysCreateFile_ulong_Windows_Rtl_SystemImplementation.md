# Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile(ulong,Windows::Rtl::SystemImplementation::CSilHandle *,ulong,_OBJECT_ATTRIBUTES &,_IO_STATUS_BLOCK *,_LARGE_INTEGER *,ulong,ulong,ulong,ulong,void *,ulong,Windows::Rtl::KtmTransactionInfoPointer,ulong *)

- ea: `0x180122600`
- end: `0x180123eff`
- name: `?SysCreateFile@DirectFileSystemProvider@SystemImplementation@Rtl@Windows@@UEAAJKPEAVCSilHandle@234@KAEAU_OBJECT_ATTRIBUTES@@PEAU_IO_STATUS_BLOCK@@PEAT_LARGE_INTEGER@@KKKKPEAXKUKtmTransactionInfoPointer@34@PEAK@Z`
- size: `6399`
- prototype: ``
- caller_count: `0`
- callee_count: `30`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800031d0`
- `0x18000aedc`
- `0x18000e098`
- `0x180030b68`
- `0x18003104c`
- `0x1800497c0`
- `0x180049c6c`
- `0x18004a468`
- `0x18004d970`
- `0x18004f350`
- `0x180117ae4`
- `0x180119004`
- `0x18011b504`
- `0x18011c474`
- `0x18011cba4`
- `0x18011d7d8`
- `0x180120b1c`
- `0x1801210b4`
- `0x180121cd0`
- `0x180122600`
- `0x18012cc94`
- `0x18012e2e0`
- `0x18012e334`
- `0x18012fa2c`
- `0x180130898`
- `0x180130944`
- `0x180131fd8`
- `0x1801a18f4`
- `0x1801a28c0`
- `0x1801bd010`

## import_xrefs

- `ntdll!RtlSetCurrentTransaction` at `0x180123413`
- `ntdll!RtlSetCurrentTransaction` at `0x180123958`
- `ntdll!RtlSetCurrentTransaction` at `0x180123a00`
- `ntdll!RtlSetCurrentTransaction` at `0x180123413`
- `ntdll!RtlSetCurrentTransaction` at `0x180123958`
- `ntdll!RtlSetCurrentTransaction` at `0x180123a00`
- `ntdll!RtlGetCurrentTransaction` at `0x1801233f5`
- `ntdll!RtlGetCurrentTransaction` at `0x180123947`
- `ntdll!RtlGetCurrentTransaction` at `0x1801239ef`
- `ntdll!RtlGetCurrentTransaction` at `0x1801233f5`
- `ntdll!RtlGetCurrentTransaction` at `0x180123947`
- `ntdll!RtlGetCurrentTransaction` at `0x1801239ef`
- `ntdll!NtCreateFile` at `0x180123495`
- `ntdll!NtCreateFile` at `0x18012357d`
- `ntdll!NtCreateFile` at `0x180123495`
- `ntdll!NtCreateFile` at `0x18012357d`
- `ntdll!NtClose` at `0x180123932`
- `ntdll!NtClose` at `0x1801239d4`
- `ntdll!NtClose` at `0x180123932`
- `ntdll!NtClose` at `0x1801239d4`
- `ntdll!RtlRaiseStatus` at `0x180123976`
- `ntdll!RtlRaiseStatus` at `0x180123976`

## string_xrefs

- `0x180122b02`: `onecore\base\wcp\sil\inc\systemprovider.h`
- `0x1801226cb`: `Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile`
- `0x18012291f`: `Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile`
- `0x180122bcf`: `Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile`
- `0x180122c0f`: `Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile`
- `0x180122d68`: `Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile`
- `0x180122ddd`: `Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile`
- `0x180123dc0`: `Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile`
- `0x180123e4c`: `Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile`
- `0x180122991`: `ValidateForEnsureSetSecurity(DesiredAccessIn, CreateOptions, ObjectAttributesIn)`
- `0x1801229da`: `ValidateForEnsureSetAttributes(DesiredAccessIn, FileAttributes)`
- `0x180122be2`: `DesiredAccessIn`
- `0x180122c28`: `DesiredAccessIn`
- `0x180122d7b`: `DesiredAccessIn`
- `0x180122df6`: `DesiredAccessIn`
- `0x1801236d3`: `Transient sharing violation at NtCreateFile\n   Flags = {flags}\n   DesiredAccess = {da}\n   ObjectAttributes = {oa}\n   AllocationSize = {as}\n   FileAttributes = {fa}\n   ShareAccess = {sa}\n   CreateDisposition = {cd}\n   CreateOptions = {co}`
- `0x1801238d7`: `Sharing violation at NtCreateFile - giving up after {retries} retries!!\n   Flags = {flags}\n   DesiredAccess = {da}\n   ObjectAttributes = {oa}\n   AllocationSize = {as}\n   FileAttributes = {fa}\n   ShareAccess = {sa}\n   CreateDisposition = {cd}\n   CreateOptions = {co}`
- `0x180122b10`: `Windows::Rtl::SystemImplementation::DirectHandleObjectBase<struct Windows::Rtl::SystemImplementation::DirectFileSystemProvider::DirectFSHandleObject>::ValidateTransaction`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile(
        volatile signed __int32 *a1,
        struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *a2,
        _QWORD *a3,
        ACCESS_MASK a4,
        __int64 a5,
        struct _IO_STATUS_BLOCK *a6,
        union _LARGE_INTEGER *a7,
        ULONG FileAttributes,
        ULONG a9,
        ULONG CreateDisposition,
        ULONG CreateOptions,
        void *a12,
        ULONG EaLength,
        void **a14,
        _DWORD *a15)
{
  PIO_STATUS_BLOCK v16; // r15
  void *v17; // r13
  _DWORD *v18; // r14
  char FacilityTracingFlags; // al
  struct Windows::Rtl::SystemImplementation::ParsedOptionsDisposition *v20; // r9
  PLARGE_INTEGER *v21; // rcx
  unsigned int v22; // edi
  void **v23; // rbx
  void *v24; // rcx
  union _LARGE_INTEGER *v25; // rax
  union _LARGE_INTEGER *v26; // rdx
  int v27; // eax
  __int64 v28; // r8
  ACCESS_MASK v29; // eax
  __int64 v30; // rcx
  int v31; // eax
  _BYTE *v32; // rcx
  signed __int32 v33; // eax
  int v34; // eax
  int v35; // eax
  __m128i v36; // xmm2
  void *v37; // xmm1_8
  WCHAR *v38; // r15
  unsigned __int16 v39; // si
  __int64 v40; // rax
  int v41; // eax
  unsigned __int16 v42; // cx
  int v43; // eax
  __m128i v44; // xmm2
  void *v45; // xmm1_8
  __m128i v46; // xmm2
  void *v47; // xmm1_8
  NTSTATUS FileNT; // esi
  void *v49; // rax
  int v50; // eax
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rsi
  void *v54; // r15
  char v55; // r13
  NTSTATUS v56; // eax
  __int64 v57; // r8
  int v58; // eax
  unsigned __int64 v59; // rcx
  int v60; // eax
  __int64 v61; // rdx
  PLARGE_INTEGER v62; // rdi
  bool v63; // zf
  unsigned int v64; // edx
  void *v65; // r9
  void *v66; // rcx
  __int64 CurrentTransaction; // rbx
  int v68; // eax
  void *v69; // rdx
  __int64 v70; // rdi
  const struct _SECURITY_DESCRIPTOR *v71; // rax
  __int64 v72; // rdx
  int v73; // eax
  __int64 v74; // r15
  __int64 v75; // r9
  _QWORD *v76; // rdx
  __int64 v77; // rax
  __int64 v78; // rcx
  unsigned int v80; // ebx
  int AllocationSize; // [rsp+20h] [rbp-1F0h]
  struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *ShareAccess; // [rsp+30h] [rbp-1E0h]
  struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *ShareAccessa; // [rsp+30h] [rbp-1E0h]
  const char *v84; // [rsp+F8h] [rbp-118h]
  void (__fastcall *v85)(Windows::WCP::Rtl *__hidden, struct Windows::Rtl::IRtlFormattedOutputStream *, const void *); // [rsp+100h] [rbp-110h]
  ULONG *v86; // [rsp+108h] [rbp-108h]
  const char *v87; // [rsp+110h] [rbp-100h]
  void (__fastcall *v88)(Windows::WCP::Rtl *__hidden, struct Windows::Rtl::IRtlFormattedOutputStream *, const void *); // [rsp+118h] [rbp-F8h]
  ULONG *p_CreateDisposition; // [rsp+120h] [rbp-F0h]
  const char *v90; // [rsp+128h] [rbp-E8h]
  void (__fastcall *v91)(Windows::WCP::Rtl *__hidden, struct Windows::Rtl::IRtlFormattedOutputStream *, const void *); // [rsp+130h] [rbp-E0h]
  ULONG *p_CreateOptions; // [rsp+138h] [rbp-D8h]
  const char *v93; // [rsp+140h] [rbp-D0h]
  void (__fastcall *v94)(Windows::WCP::Rtl *__hidden, struct Windows::Rtl::IRtlFormattedOutputStream *, const void *); // [rsp+148h] [rbp-C8h]
  void *v95; // [rsp+150h] [rbp-C0h]
  const char *v96; // [rsp+158h] [rbp-B8h]
  void (__fastcall *v97)(Windows::WCP::Rtl *__hidden, struct Windows::Rtl::IRtlFormattedOutputStream *, const void *); // [rsp+160h] [rbp-B0h]
  ULONG *p_EaLength; // [rsp+168h] [rbp-A8h]
  const char *v99; // [rsp+170h] [rbp-A0h]
  void (__fastcall *v100)(struct Windows::Rtl::IRtlFormattedOutputStream *, const void *); // [rsp+178h] [rbp-98h]
  _DWORD *v101; // [rsp+180h] [rbp-90h]
  char v102; // [rsp+190h] [rbp-80h]
  __int16 v103; // [rsp+194h] [rbp-7Ch] BYREF
  char v104; // [rsp+196h] [rbp-7Ah]
  unsigned __int8 v105; // [rsp+198h] [rbp-78h]
  __int128 v106; // [rsp+1A0h] [rbp-70h] BYREF
  __int64 v107; // [rsp+1B0h] [rbp-60h]
  const char *v108; // [rsp+1B8h] [rbp-58h]
  int v109; // [rsp+1C0h] [rbp-50h]
  _BYTE v110[24]; // [rsp+1C8h] [rbp-48h] BYREF
  const char *v111; // [rsp+1E0h] [rbp-30h]
  PIO_STATUS_BLOCK IoStatusBlock; // [rsp+1E8h] [rbp-28h]
  PVOID EaBuffer; // [rsp+1F0h] [rbp-20h] BYREF
  __m128i v114; // [rsp+1F8h] [rbp-18h] BYREF
  __int64 v115; // [rsp+208h] [rbp-8h]
  const char *v116; // [rsp+210h] [rbp+0h]
  _QWORD *v117; // [rsp+218h] [rbp+8h]
  _QWORD v118[6]; // [rsp+220h] [rbp+10h] BYREF
  void *FileHandle[2]; // [rsp+250h] [rbp+40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+260h] [rbp+50h] BYREF
  int v121; // [rsp+290h] [rbp+80h] BYREF
  unsigned int v122; // [rsp+298h] [rbp+88h] BYREF
  ACCESS_MASK DesiredAccess[4]; // [rsp+2A0h] [rbp+90h] BYREF
  __int128 v124; // [rsp+2B0h] [rbp+A0h] BYREF
  ACCESS_MASK v125; // [rsp+2C0h] [rbp+B0h]
  _BYTE v126[40]; // [rsp+2C8h] [rbp+B8h] BYREF
  PWSTR Buffer; // [rsp+2F0h] [rbp+E0h]
  __int128 v128; // [rsp+300h] [rbp+F0h] BYREF
  __int64 v129; // [rsp+310h] [rbp+100h]
  char v130; // [rsp+318h] [rbp+108h]
  __int16 v131; // [rsp+31Ah] [rbp+10Ah]
  __int128 v132; // [rsp+320h] [rbp+110h]
  __int128 v133; // [rsp+330h] [rbp+120h]
  PLARGE_INTEGER v134[2]; // [rsp+340h] [rbp+130h] BYREF
  __int64 v135; // [rsp+350h] [rbp+140h]
  const char *v136; // [rsp+358h] [rbp+148h]
  int v137[14]; // [rsp+360h] [rbp+150h] BYREF
  char v138; // [rsp+398h] [rbp+188h]
  unsigned __int64 v139[2]; // [rsp+570h] [rbp+360h] BYREF
  __int64 p_ObjectName; // [rsp+580h] [rbp+370h]
  __int64 v141; // [rsp+588h] [rbp+378h]
  unsigned __int64 v142[2]; // [rsp+590h] [rbp+380h] BYREF
  __int128 v143; // [rsp+5A0h] [rbp+390h]
  __int128 v144; // [rsp+5B0h] [rbp+3A0h]
  __int64 v145; // [rsp+5C0h] [rbp+3B0h]
  __int64 (__fastcall *v146)(); // [rsp+5C8h] [rbp+3B8h]
  PLARGE_INTEGER *v147; // [rsp+5D0h] [rbp+3C0h]
  __int64 v148; // [rsp+5D8h] [rbp+3C8h]
  __int64 (__fastcall *v149)(); // [rsp+5E0h] [rbp+3D0h]
  PVOID *p_EaBuffer; // [rsp+5E8h] [rbp+3D8h]

  v118[4] = -2;
  v117 = a3;
  v122 = (unsigned int)a2;
  v125 = a4;
  v16 = a6;
  IoStatusBlock = a6;
  v134[0] = a7;
  v17 = a12;
  EaBuffer = a12;
  v18 = a15;
  v121 = 0;
  v137[10] = 0;
  v138 = 0;
  v137[2] = 1;
  FacilityTracingFlags = Windows::WCP::Rtl::RtlGetFacilityTracingFlags(
                           (Windows::WCP::Rtl *)&Windows::WCP::Rtl::Facility_SIL,
                           a2);
  v20 = (struct Windows::Rtl::SystemImplementation::ParsedOptionsDisposition *)Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSCreateDisposition;
  if ( (FacilityTracingFlags & 0xE) != 0 )
  {
    v101 = v18;
    v100 = Windows::Rtl::SystemImplementation::IRtlFileSystemProvider::Format_PCULONG_AsSysCreateFileDisposition;
    v99 = "disp";
    p_EaLength = &EaLength;
    v97 = Windows::WCP::Rtl::RtlTraceFormat_PCULONG;
    v96 = "eal";
    v95 = v17;
    v94 = Windows::WCP::Rtl::RtlTraceFormat_PCIO_STATUS_BLOCK;
    v93 = "eab";
    p_CreateOptions = &CreateOptions;
    v91 = Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSCreateOptions;
    v90 = "co";
    p_CreateDisposition = &CreateDisposition;
    v88 = Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSCreateDisposition;
    v87 = "cd";
    v86 = &a9;
    v85 = Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSShareAccess;
    v84 = "sa";
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,13>::Arm(
      (int)v137,
      (int)&v121,
      (int)Windows::WCP::Rtl::RtlTraceFormat_PCNTSTATUS,
      (int)a1,
      (__int64)"Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile",
      (Windows::WCP::Rtl *)&Windows::WCP::Rtl::Facility_SIL,
      (unsigned int)"(flags = {flags}, da = {da}, oa = {oa}, as = {as}, fa = {fa}, sa = {sa}, cd = {cd}, co = {co}, eab ="
                    " {eab}, eal = {eal})\n",
      (__int64)"(flags = {flags}, handle = {handle}, da = {da}, oa = {oa}, iosb = {iosb}, as = {as}, fa = {fa}, sa = {sa}"
               ", cd = {cd}, co = {co}, eab = {eab}, eal = {eal}, disp = {disp})\n",
      (__int64)"(handle = {handle}, iosb = {iosb}, disp = {disp})\n");
  }
  if ( v18 )
    *v18 = 0;
  *(_OWORD *)&a6->Status = 0;
  if ( (v122 & 0x20000) != 0
    && ((v125 & 0x10E0000) != 0x10E0000
     || !*(_QWORD *)(a5 + 32)
     || (CreateOptions & 0x41) == 0
     || (((CreateOptions & 0x41) - 1LL) & CreateOptions & 0x41) != 0) )
  {
    v114.m128i_i64[0] = (__int64)"onecore\\base\\wcp\\sil\\ntsystem.cpp";
    v114.m128i_i64[1] = (__int64)"Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile";
    v115 = 1779;
    v116 = "ValidateForEnsureSetSecurity(DesiredAccessIn, CreateOptions, ObjectAttributesIn)";
    v21 = (PLARGE_INTEGER *)&v114;
LABEL_15:
    v121 = -1073741811;
    RtlReportErrorOrigination(v21, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    v22 = v121;
LABEL_236:
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,13>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,13>(v137);
    return v22;
  }
  if ( (v122 & 0x40000) != 0 && ((v125 & 0x100) == 0 || !FileAttributes) )
  {
    *(_QWORD *)v110 = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
    *(_QWORD *)&v110[8] = "Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile";
    *(_QWORD *)&v110[16] = 1784;
    v111 = "ValidateForEnsureSetAttributes(DesiredAccessIn, FileAttributes)";
    v21 = (PLARGE_INTEGER *)v110;
    goto LABEL_15;
  }
  v23 = a14;
  if ( a14 )
    v24 = *a14;
  else
    v24 = 0;
  FileHandle[0] = v24;
  v25 = *(union _LARGE_INTEGER **)(a5 + 8);
  if ( v25 )
  {
    v26 = v25 + 1;
    if ( v25[1].QuadPart )
    {
      if ( (void *)v26->QuadPart != v24 )
      {
        EaBuffer = FileHandle;
        v134[0] = v25 + 1;
        v142[0] = 0;
        v142[1] = (unsigned __int64)`Windows::WCP::Rtl::RtlAutoTrace<Windows::Rtl::SystemImplementation::DirectFileSystemProvider::DirectFSHandleObject,_UNICODE_STRING *,Windows::WCP::Rtl::FormatPointerWrapper<void *>,Windows::WCP::Rtl::FormatPointerWrapper<void *>>'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
        v143 = (unsigned __int64)v25;
        *(_QWORD *)&v144 = `Windows::WCP::Rtl::RtlAutoTrace<_UNICODE_STRING *>'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
        *((_QWORD *)&v144 + 1) = a5 + 16;
        v145 = 0;
        v146 = `Windows::WCP::Rtl::RtlAutoTrace<Windows::Rtl::SystemImplementation::DirectFileSystemProvider::DirectFSHandleObject,_UNICODE_STRING *,Windows::WCP::Rtl::FormatPointerWrapper<void *>,Windows::WCP::Rtl::FormatPointerWrapper<void *>>'::`2'::_lambda_4_::_lambda_invoker_cdecl_;
        v147 = v134;
        v148 = 0;
        v149 = `Windows::WCP::Rtl::RtlAutoTrace<Windows::Rtl::SystemImplementation::DirectFileSystemProvider::DirectFSHandleObject,_UNICODE_STRING *,Windows::WCP::Rtl::FormatPointerWrapper<void *>,Windows::WCP::Rtl::FormatPointerWrapper<void *>>'::`2'::_lambda_4_::_lambda_invoker_cdecl_;
        p_EaBuffer = &EaBuffer;
        Windows::WCP::Rtl::RtlTraceFromParameterList(
          (Windows::WCP::Rtl *)2,
          (unsigned int)v26,
          (unsigned int)&Windows::WCP::Rtl::Facility_SIL,
          (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)"Transaction mismatch for [rd: {}, name: {}]. {} != {}",
          (const char *const)4,
          (unsigned __int64)v142,
          ShareAccess);
        v139[0] = (unsigned __int64)"onecore\\base\\wcp\\sil\\inc\\systemprovider.h";
        v139[1] = (unsigned __int64)"Windows::Rtl::SystemImplementation::DirectHandleObjectBase<struct Windows::Rtl::Syst"
                                    "emImplementation::DirectFileSystemProvider::DirectFSHandleObject>::ValidateTransaction";
        p_ObjectName = 1723;
        v141 = 0;
        RtlReportErrorOrigination(v139, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221226002LL);
        v22 = -1073741294;
        v121 = -1073741294;
        goto LABEL_236;
      }
    }
  }
  v103 = 0;
  v104 = 0;
  v27 = Windows::Rtl::SystemImplementation::ParseOptionsDisposition(
          (Windows::Rtl::SystemImplementation *)CreateOptions,
          CreateDisposition,
          (unsigned int)&v103,
          v20);
  v22 = v27;
  if ( v27 < 0 )
  {
    v121 = v27;
    goto LABEL_236;
  }
  v29 = v125;
  LOBYTE(v28) = v103;
  v30 = CreateOptions & 0x4000;
  if ( (CreateOptions & 0x4000) != 0 && v104 )
  {
    if ( (_BYTE)v103 )
    {
      if ( (v125 & 4) == 0 )
      {
        *(_QWORD *)&v106 = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
        *((_QWORD *)&v106 + 1) = "Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile";
        v107 = 1803;
        v108 = "DesiredAccessIn";
        v21 = (PLARGE_INTEGER *)&v106;
        goto LABEL_15;
      }
    }
    else if ( HIBYTE(v103) && (v125 & 2) == 0 )
    {
      v134[0] = (PLARGE_INTEGER)"onecore\\base\\wcp\\sil\\ntsystem.cpp";
      v134[1] = (PLARGE_INTEGER)"Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile";
      v135 = 1807;
      v136 = "DesiredAccessIn";
      v21 = v134;
      goto LABEL_15;
    }
  }
  DesiredAccess[0] = v125;
  if ( (v125 & 0x10000000) != 0 )
  {
    v29 = v125 & 0xEFE0FE00 | 0x1F01FF;
    DesiredAccess[0] = v29;
  }
  if ( v23 && (CreateOptions & 0x40) != 0 && (v29 & 0x20) != 0 )
  {
    v29 &= ~0x20u;
    DesiredAccess[0] = v29;
  }
  if ( (CreateOptions & 0x4000) != 0 && (v29 & 0x40) != 0 )
    DesiredAccess[0] = v29 & 0xFFFFFFBF;
  v128 = 0;
  v129 = 0;
  v130 = 0;
  v131 = 0;
  v132 = 0;
  v133 = 0;
  *(_OWORD *)&ObjectAttributes.Length = *(_OWORD *)a5;
  *(_OWORD *)&ObjectAttributes.ObjectName = *(_OWORD *)(a5 + 16);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = *(_OWORD *)(a5 + 32);
  v105 = 0;
  v102 = 0;
  if ( v104 || (v122 & 0x20000) != 0 )
  {
    AllocationSize = (int)ObjectAttributes.SecurityDescriptor;
    v31 = Windows::Rtl::SystemImplementation::IRtlObjectProvider::CalculateSecurityForCreate(
            a1,
            (_BYTE)v103 != 0 ? 28 : 26,
            ObjectAttributes.RootDirectory,
            ObjectAttributes.ObjectName);
    v22 = v31;
    if ( v31 < 0 )
    {
      v121 = v31;
LABEL_235:
      Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v128);
      goto LABEL_236;
    }
    if ( (v131 & 0x400) != 0 )
    {
      if ( (v125 & 0x40000) == 0 )
      {
        v118[0] = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
        v118[1] = "Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile";
        v118[2] = 1861;
        v118[3] = "DesiredAccessIn";
        v32 = v118;
LABEL_49:
        v121 = -1073741811;
        RtlReportErrorOrigination(v32, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
        v22 = v121;
        goto LABEL_235;
      }
      v105 = 1;
    }
    if ( (v131 & 0x800) != 0 )
    {
      if ( (v125 & 0x1000000) == 0 )
      {
        *(_QWORD *)v126 = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
        *(_QWORD *)&v126[8] = "Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile";
        *(_QWORD *)&v126[16] = 1870;
        *(_QWORD *)&v126[24] = "DesiredAccessIn";
        v32 = v126;
        goto LABEL_49;
      }
      v102 = 1;
    }
    ObjectAttributes.SecurityDescriptor = (PVOID)Windows::Rtl::SecurityDescriptor::Get((Windows::Rtl::SecurityDescriptor *)&v128);
  }
  if ( ObjectAttributes.RootDirectory )
    ObjectAttributes.RootDirectory = *(HANDLE *)ObjectAttributes.RootDirectory;
  do
  {
    v33 = *((_DWORD *)a1 + 11);
    if ( v33 == -1 )
      break;
    v30 = (unsigned int)(v33 + 1);
  }
  while ( v33 != _InterlockedCompareExchange(a1 + 11, v30, v33) );
  v106 = 0;
  if ( !v23 )
  {
    v54 = 0;
LABEL_124:
    v55 = 0;
    goto LABEL_125;
  }
  if ( *((_BYTE *)v23 + 8) )
  {
    v124 = 0;
    if ( ObjectAttributes.RootDirectory )
    {
      *(_OWORD *)v139 = 0;
      p_ObjectName = 0;
      v34 = (*(__int64 (__fastcall **)(volatile signed __int32 *, _QWORD, unsigned __int64 *))(*(_QWORD *)a1 + 56LL))(
              a1,
              *(_QWORD *)(a5 + 8),
              v139);
      v22 = v34;
      if ( v34 < 0 )
      {
        v121 = v34;
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(v139);
        goto LABEL_66;
      }
      memset(v110, 0, sizeof(v110));
      *(_OWORD *)v126 = *(_OWORD *)v139;
      *(_QWORD *)&v126[16] = p_ObjectName;
      *(__m128i *)&v126[24] = _mm_unpacklo_epi32(
                                _mm_unpacklo_epi16(
                                  _mm_cvtsi32_si128(*(_DWORD *)ObjectAttributes.ObjectName),
                                  (__m128i)0LL),
                                (__m128i)0LL);
      Buffer = ObjectAttributes.ObjectName->Buffer;
      v35 = RtlCombineNtPathSegments(2, v126, v110);
      v22 = v35;
      if ( v35 < 0 )
      {
        v121 = v35;
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(v110);
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(v139);
        goto LABEL_66;
      }
      if ( *(_QWORD *)v110 > 0xFFFEu )
      {
        v22 = -1073740757;
        v121 = -1073740757;
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(v110);
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(v139);
        goto LABEL_66;
      }
      v36 = *(__m128i *)v110;
      v37 = *(void **)&v110[16];
      memset(v110, 0, sizeof(v110));
      HIWORD(FileHandle[0]) = 0;
      FileHandle[1] = v37;
      LOWORD(FileHandle[0]) = _mm_cvtsi128_si32(v36);
      *(_DWORD *)((char *)FileHandle + 2) = (unsigned __int16)_mm_extract_epi16(v36, 4);
      if ( *((_QWORD *)&v124 + 1) )
        anonymous_namespace_::OurRtlFreeStringRoutine(*((_QWORD *)&v124 + 1));
      v124 = *(_OWORD *)FileHandle;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v124;
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(v110);
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(v139);
    }
    *(_OWORD *)FileHandle = 0;
    if ( (unsigned __int8)Windows::StringUtil::IsStringLowerCaseAsciiPrefixEqualCaseInvariant<_UNICODE_STRING,_UNICODE_STRING>(
                            &___LiteralObject__2U__BaseLiteralBuffer__0M_U_UNICODE_STRING___W_Details_RtlStringLiterals__3_W0FM__0HD__0HJ__0HD__0HE__0GF__0GN__0HC__0GP__0GP__0HE__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__Details_RtlStringLiterals__3U_UNICODE_STRING__B,
                            ObjectAttributes.ObjectName,
                            FileHandle) )
    {
      v38 = (WCHAR *)FileHandle[1];
      v39 = (unsigned __int16)FileHandle[0];
      if ( !LOWORD(FileHandle[0]) || *(_WORD *)FileHandle[1] == 92 )
      {
        memset(v110, 0, sizeof(v110));
        v40 = -1;
        do
          ++v40;
        while ( *(_WORD *)(2 * v40 + 0x7FFE0030) );
        v114.m128i_i64[0] = 2 * v40;
        v114.m128i_i64[1] = 2 * v40 + 2;
        v115 = 2147352624;
        v41 = RtlConvertWin32FilePathToNtFilePath(&v114, v110);
        v22 = v41;
        if ( v41 < 0 )
        {
          v121 = v41;
          Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(v110);
          goto LABEL_66;
        }
        if ( v39 && (*v38 != 92 ? (v42 = WORD1(FileHandle[0])) : (++v38, v39 -= 2, v42 = WORD1(FileHandle[0]) - 2), v39) )
        {
          v114 = 0;
          v115 = 0;
          *(_QWORD *)v126 = *(_QWORD *)v110;
          *(_OWORD *)&v126[8] = *(_OWORD *)&v110[8];
          *(_QWORD *)&v126[24] = v39;
          *(_QWORD *)&v126[32] = v42;
          Buffer = v38;
          v43 = RtlCombineNtPathSegments(2, v126, &v114);
          v22 = v43;
          if ( v43 < 0 )
          {
            v121 = v43;
            Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v114);
            Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(v110);
            goto LABEL_66;
          }
          if ( v114.m128i_i64[0] > 0xFFFEuLL )
          {
            v22 = -1073740757;
            v121 = -1073740757;
            Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v114);
            Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(v110);
            goto LABEL_66;
          }
          v44 = v114;
          v45 = (void *)v115;
          v114 = 0;
          v115 = 0;
          HIWORD(FileHandle[0]) = 0;
          FileHandle[1] = v45;
          LOWORD(FileHandle[0]) = _mm_cvtsi128_si32(v44);
          *(_DWORD *)((char *)FileHandle + 2) = (unsigned __int16)_mm_extract_epi16(v44, 4);
          if ( *((_QWORD *)&v124 + 1) )
            anonymous_namespace_::OurRtlFreeStringRoutine(*((_QWORD *)&v124 + 1));
          v124 = *(_OWORD *)FileHandle;
          Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v114);
        }
        else
        {
          if ( *(_QWORD *)v110 > 0xFFFEu )
          {
            v22 = -1073740757;
            v121 = -1073740757;
            Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(v110);
LABEL_66:
            if ( *((_QWORD *)&v124 + 1) )
            {
              anonymous_namespace_::OurRtlFreeStringRoutine(*((_QWORD *)&v124 + 1));
              v124 = 0;
            }
            goto LABEL_233;
          }
          v46 = *(__m128i *)v110;
          v47 = *(void **)&v110[16];
          memset(v110, 0, sizeof(v110));
          HIWORD(FileHandle[0]) = 0;
          FileHandle[1] = v47;
          LOWORD(FileHandle[0]) = _mm_cvtsi128_si32(v46);
          *(_DWORD *)((char *)FileHandle + 2) = (unsigned __int16)_mm_extract_epi16(v46, 4);
          if ( *((_QWORD *)&v124 + 1) )
            anonymous_namespace_::OurRtlFreeStringRoutine(*((_QWORD *)&v124 + 1));
          v124 = *(_OWORD *)FileHandle;
        }
        ObjectAttributes.ObjectName = (PUNICODE_STRING)&v124;
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(v110);
      }
      v16 = IoStatusBlock;
    }
    *(_OWORD *)v142 = 0;
    v143 = 0;
    v144 = 0;
    v145 = 0;
    FileNT = FsTxCreateFileNT(
               CreateOptions,
               (unsigned int)*v23,
               a9,
               FileAttributes,
               AllocationSize,
               DesiredAccess[0],
               (__int64)&ObjectAttributes,
               (__int64)v16,
               (__int64)v134[0],
               FileAttributes,
               a9,
               CreateDisposition,
               CreateOptions,
               (__int64)EaBuffer,
               EaLength,
               (__int64)v142);
    if ( FileNT >= 0 )
    {
      v49 = (void *)v142[1];
      if ( v142[1] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        if ( (_BYTE)v103 && !v16->Information )
          v16->Information = 1;
        FileHandle[0] = v49;
        v50 = Windows::Rtl::SystemImplementation::DirectFileSystemProvider::DirectFSHandleObject::CreateFsTx(
                a1,
                FileHandle,
                &v106,
                *v23);
        v22 = v50;
        if ( v50 < 0 )
        {
          v121 = v50;
          if ( (unsigned __int64)FileHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL
            && (int)FsTxCloseHandleNT(v51, FileHandle[0]) < 0 )
          {
            __fastfail(7u);
          }
          goto LABEL_66;
        }
        if ( (unsigned __int64)FileHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL
          && (int)FsTxCloseHandleNT(v51, FileHandle[0]) < 0 )
        {
          __fastfail(7u);
        }
      }
    }
    if ( *((_QWORD *)&v124 + 1) )
    {
      anonymous_namespace_::OurRtlFreeStringRoutine(*((_QWORD *)&v124 + 1));
      v124 = 0;
    }
    goto LABEL_115;
  }
  v54 = *v23;
  if ( !*v23 )
    goto LABEL_124;
  if ( ((RtlGetCurrentTransaction(v30, 0xFFFFFFFFLL, v28) + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0
    || !(unsigned int)RtlSetCurrentTransaction(v54) )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    __debugbreak();
  }
  v55 = 1;
LABEL_125:
  FileHandle[0] = 0;
  v56 = NtCreateFile(
          FileHandle,
          DesiredAccess[0],
          &ObjectAttributes,
          IoStatusBlock,
          v134[0],
          FileAttributes,
          a9,
          CreateDisposition,
          CreateOptions,
          EaBuffer,
          EaLength);
  FileNT = v56;
  if ( v56 == -1073741191 || v56 == -1073741184 )
    Windows::Rtl::SystemImplementation::LogReparseData(&ObjectAttributes);
  v52 = v122;
  if ( (v122 & 4) == 0 )
  {
    v58 = 30;
    v109 = 30;
    if ( FileNT == -1073741757 )
    {
      while ( 1 )
      {
        if ( !v58 )
          goto LABEL_156;
        v59 = (30 - v58) / 0xAu;
        if ( v59 >= 3 )
          v59 = 2;
        v60 = DelayExecution((&s_rgSharingViolationWaitMilliseconds)[v59]);
        v22 = v60;
        if ( v60 < 0 )
          break;
        v62 = v134[0];
        FileNT = NtCreateFile(
                   FileHandle,
                   DesiredAccess[0],
                   &ObjectAttributes,
                   IoStatusBlock,
                   v134[0],
                   FileAttributes,
                   a9,
                   CreateDisposition,
                   CreateOptions,
                   EaBuffer,
                   EaLength);
        if ( FileNT >= 0 )
        {
          ShareAccessa = (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *)&v122;
          Windows::WCP::Rtl::RtlTrace(
            0,
            (unsigned int)&Windows::WCP::Rtl::Facility_SIL,
            (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)"Transient sharing violation at NtCreateFile\n"
                                                               "   Flags = {flags}\n"
                                                               "   DesiredAccess = {da}\n"
                                                               "   ObjectAttributes = {oa}\n"
                                                               "   AllocationSize = {as}\n"
                                                               "   FileAttributes = {fa}\n"
                                                               "   ShareAccess = {sa}\n"
                                                               "   CreateDisposition = {cd}\n"
                                                               "   CreateOptions = {co}",
            (const char *const)8,
            (unsigned __int64)"flags",
            Windows::Rtl::SystemImplementation::IRtlFileSystemProvider::Format_PCULONG_AsSysCreateFileFlags);
        }
        v63 = v109 == 1;
        v58 = --v109;
        if ( v63 )
        {
          if ( FileNT != -1073741757 )
            goto LABEL_142;
          if ( (int)Windows::Rtl::SystemImplementation::LogProcessesHoldingFile(&ObjectAttributes) < 0 )
          {
            v139[0] = 0;
            v139[1] = (unsigned __int64)`Windows::WCP::Rtl::RtlAutoTrace<_UNICODE_STRING *>'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
            p_ObjectName = (__int64)&ObjectAttributes.ObjectName;
            Windows::WCP::Rtl::RtlTraceFromParameterList(
              (Windows::WCP::Rtl *)2,
              v64,
              (unsigned int)&Windows::WCP::Rtl::Facility_SIL,
              (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)"Failed to log processes holding {0}.",
              (const char *const)1,
              (unsigned __int64)v139,
              ShareAccessa);
          }
          *(_QWORD *)&v124 = 30;
          Windows::WCP::Rtl::RtlTrace(
            0,
            (unsigned int)&Windows::WCP::Rtl::Facility_SIL,
            (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)"Sharing violation at NtCreateFile - giving up after {retr"
                                                               "ies} retries!!\n"
                                                               "   Flags = {flags}\n"
                                                               "   DesiredAccess = {da}\n"
                                                               "   ObjectAttributes = {oa}\n"
                                                               "   AllocationSize = {as}\n"
                                                               "   FileAttributes = {fa}\n"
                                                               "   ShareAccess = {sa}\n"
                                                               "   CreateDisposition = {cd}\n"
                                                               "   CreateOptions = {co}",
            (const char *const)9,
            (unsigned __int64)"retries",
            Windows::WCP::Rtl::RtlTraceFormat_PCULONGLONG,
            &v124,
            "flags",
            Windows::Rtl::SystemImplementation::IRtlFileSystemProvider::Format_PCULONG_AsSysCreateFileFlags,
            &v122,
            "da",
            Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSFileDesiredAccess,
            DesiredAccess,
            "oa",
            Windows::WCP::Rtl::RtlTraceFormat_PCOBJECT_ATTRIBUTES,
            &ObjectAttributes,
            "as",
            Windows::WCP::Rtl::RtlTraceFormat_PCULONGLONG,
            v62,
            "fa",
            Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSFileAttributes,
            &FileAttributes,
            "sa",
            Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSShareAccess,
            &a9,
            "cd",
            Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSCreateDisposition,
            &CreateDisposition,
            "co",
            Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSCreateOptions,
            &CreateOptions,
            v84,
            v85,
            v86,
            v87,
            v88,
            p_CreateDisposition,
            v90,
            v91,
            p_CreateOptions,
            v93,
            v94,
            v95,
            v96,
            v97,
            p_EaLength,
            v99,
            v100,
            v101);
          v58 = v109;
        }
        else if ( FileNT != -1073741757 )
        {
LABEL_142:
          v52 = v122;
          goto LABEL_143;
        }
      }
      v121 = v60;
      v66 = FileHandle[0];
      if ( (unsigned __int64)FileHandle[0] - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      {
LABEL_148:
        if ( !v55 )
          goto LABEL_233;
        CurrentTransaction = RtlGetCurrentTransaction(v66, v61, v57);
        if ( (unsigned int)RtlSetCurrentTransaction(0) )
        {
          if ( (void *)CurrentTransaction == v54 )
            goto LABEL_233;
        }
        goto LABEL_151;
      }
LABEL_147:
      FileHandle[0] = 0;
      NtClose(v66);
      goto LABEL_148;
    }
  }
LABEL_143:
  if ( FileNT >= 0 )
  {
    if ( v23 )
      v65 = *v23;
    else
      v65 = 0;
    v68 = Windows::Rtl::SystemImplementation::DirectHandleObjectBase<Windows::Rtl::SystemImplementation::DirectFileSystemProvider::DirectFSHandleObject>::Create(
            a1,
            FileHandle,
            &v106,
            v65);
    v22 = v68;
    if ( v68 < 0 )
    {
      v121 = v68;
      v66 = FileHandle[0];
      if ( (unsigned __int64)FileHandle[0] - 1 > 0xFFFFFFFFFFFFFFFDuLL )
        goto LABEL_148;
      goto LABEL_147;
    }
LABEL_156:
    v52 = v122;
  }
  v69 = FileHandle[0];
  if ( (unsigned __int64)FileHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    FileHandle[0] = 0;
    NtClose(v69);
    v52 = v122;
  }
  if ( v55 )
  {
    v70 = RtlGetCurrentTransaction(v52, v69, v57);
    if ( (unsigned int)RtlSetCurrentTransaction(0) && (void *)v70 == v54 )
    {
LABEL_115:
      LODWORD(v52) = v122;
      goto LABEL_116;
    }
LABEL_151:
    RtlRaiseStatus(-1073740768);
  }
LABEL_116:
  if ( FileNT >= 0 )
  {
    v53 = *((_QWORD *)&v106 + 1);
    if ( (_BYTE)v103 )
    {
      *(_DWORD *)(*((_QWORD *)&v106 + 1) + 20LL) = 2;
    }
    else
    {
      if ( !HIBYTE(v103) )
        goto LABEL_166;
      *(_DWORD *)(*((_QWORD *)&v106 + 1) + 20LL) = 1;
    }
    _mm_mfence();
LABEL_166:
    if ( IoStatusBlock->Information == 1 )
    {
      v71 = Windows::Rtl::SecurityDescriptor::Get((Windows::Rtl::SecurityDescriptor *)&v128);
      v72 = v122;
      if ( (v122 & 0x20000) != 0 )
      {
        v73 = Windows::Rtl::SystemImplementation::IRtlObjectProvider::EnsureSetSecurityIfRequired(a1, v53, v71, v23);
        v22 = v73;
        if ( v73 < 0 )
        {
LABEL_169:
          v121 = v73;
          goto LABEL_233;
        }
        v72 = v122;
      }
      v73 = Windows::Rtl::SystemImplementation::IRtlFileSystemProvider::EnsureSetAttributesIfRequired(
              a1,
              v72,
              v53,
              FileAttributes,
              v23);
      v22 = v73;
      if ( v73 < 0 )
        goto LABEL_169;
    }
    else
    {
      if ( (FileAttributes & 0x2000) != 0 )
      {
        memset(v126, 0, 32);
        *(_QWORD *)&v126[32] = FileAttributes;
        *(_OWORD *)v134 = 0;
        LODWORD(ShareAccessa) = 4;
        v73 = (*(__int64 (__fastcall **)(volatile signed __int32 *, _QWORD, __int64, PLARGE_INTEGER *, _BYTE *, __int64, struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *, void **, _QWORD))(*(_QWORD *)a1 + 152LL))(
                a1,
                0,
                v53,
                v134,
                v126,
                40,
                ShareAccessa,
                v23,
                0);
        v22 = v73;
        if ( v73 < 0 )
          goto LABEL_169;
      }
      if ( v105 || v102 )
      {
        v74 = v53;
        v75 = (4 * v105) | 8u;
        if ( !v102 )
          v75 = 4 * (unsigned int)v105;
        v73 = (*(__int64 (__fastcall **)(volatile signed __int32 *, __int64, __int64, __int64, PVOID, void **))(*(_QWORD *)a1 + 32LL))(
                a1,
                2,
                v53,
                v75,
                ObjectAttributes.SecurityDescriptor,
                v23);
        v22 = v73;
        if ( v73 < 0 )
          goto LABEL_169;
        goto LABEL_180;
      }
    }
    v74 = v53;
LABEL_180:
    HandleTracker::TrackHandle(a1 + 4, 0, v74, 0);
    v76 = v117;
    v77 = v117[1];
    v117[1] = v53;
    *((_QWORD *)&v106 + 1) = v77;
    v78 = v106;
    *(_QWORD *)&v106 = *v76;
    *v76 = v78;
    if ( v18 )
      *v18 = 1;
    goto LABEL_229;
  }
  if ( v18 )
  {
    if ( (FileNT == -1073741772 || FileNT == -1073741766) && (v52 & 2) != 0 )
    {
      *v18 = 3;
LABEL_229:
      v138 = 1;
      Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v106);
      if ( (_QWORD)v106 )
        (**(void (__fastcall ***)(_QWORD))v106)(v106);
      Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v128);
      Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,13>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,13>(v137);
      return (unsigned int)v121;
    }
    switch ( FileNT )
    {
      case -1073741738:
        if ( (v52 & 0x400) != 0 )
        {
          *v18 = 12;
          goto LABEL_229;
        }
        break;
      case -1073741638:
        if ( (v52 & 0x80u) != 0LL )
        {
          *v18 = 9;
          goto LABEL_229;
        }
        break;
      case -1073741565:
        if ( (v52 & 0x100) != 0 )
        {
          *v18 = 10;
          goto LABEL_229;
        }
        break;
      case -1073741771:
        if ( (v52 & 1) != 0 )
        {
          *v18 = 2;
          goto LABEL_229;
        }
        break;
      case -1073741757:
        if ( (v52 & 4) != 0 )
        {
          *v18 = 4;
          goto LABEL_229;
        }
        break;
      case -1073741790:
        if ( (v52 & 8) != 0 )
        {
          *v18 = 5;
          goto LABEL_229;
        }
        break;
      case -1073741788:
        if ( (v52 & 0x10) != 0 )
        {
          *v18 = 6;
          goto LABEL_229;
        }
        break;
      case -1073741773:
        if ( (v52 & 0x20) != 0 )
        {
          *v18 = 7;
          goto LABEL_229;
        }
        break;
      case -1073741767:
        if ( (v52 & 0x40) != 0 )
        {
          *v18 = 8;
          goto LABEL_229;
        }
        break;
      case -1072103423:
        if ( (v52 & 0x200) != 0 )
        {
          *v18 = 11;
          goto LABEL_229;
        }
        break;
      case -1073741535:
        if ( (v52 & 0x800) != 0 )
        {
          *v18 = 13;
          goto LABEL_229;
        }
        break;
      case -1073741489:
        if ( (v52 & 0x1000) != 0 )
        {
          *v18 = 14;
          goto LABEL_229;
        }
        break;
      case -1073741184:
        if ( (v52 & 0x100000) != 0 )
        {
          *v18 = 15;
          goto LABEL_229;
        }
        break;
      default:
        if ( FileNT == -1073741191 && (v52 & 0x200000) != 0 )
        {
          *v18 = 16;
          goto LABEL_229;
        }
        break;
    }
    *(_QWORD *)v126 = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
    *(_QWORD *)&v126[8] = "Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile";
    *(_OWORD *)&v126[16] = 0x8B9u;
    v121 = FileNT;
    RtlReportErrorOrigination(v126, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)FileNT);
    v22 = v121;
LABEL_233:
    Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v106);
    if ( (_QWORD)v106 )
      (**(void (__fastcall ***)(_QWORD))v106)(v106);
    goto LABEL_235;
  }
  *(_QWORD *)v126 = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
  *(_QWORD *)&v126[8] = "Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile";
  *(_OWORD *)&v126[16] = 0x8BEu;
  v121 = FileNT;
  RtlReportErrorOrigination(v126, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)FileNT);
  v80 = v121;
  Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v106);
  if ( (_QWORD)v106 )
    (**(void (__fastcall ***)(_QWORD))v106)(v106);
  Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v128);
  Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,13>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,13>(v137);
  return v80;
}

```

## disassembly

```asm
0x180122600  push    rbp
0x180122602  push    rbx
0x180122603  push    rsi
0x180122604  push    rdi
0x180122605  push    r12
0x180122607  push    r13
0x180122609  push    r14
0x18012260b  push    r15
0x18012260d  lea     rbp, [rsp-3F8h]
0x180122615  sub     rsp, 608h
0x18012261c  mov     [rbp+430h+var_400], 0FFFFFFFFFFFFFFFEh
0x180122624  mov     rax, cs:__security_cookie
0x18012262b  xor     rax, rsp
0x18012262e  mov     [rbp+430h+var_50], rax
0x180122635  mov     rdi, r8
0x180122638  mov     [rbp+430h+var_428], r8
0x18012263c  mov     r12, rcx
0x18012263f  mov     [rbp+430h+var_3A8], edx
0x180122645  mov     [rbp+430h+var_380], r9d
0x18012264c  mov     rsi, [rbp+430h+arg_20]
0x180122653  mov     r15, [rbp+430h+arg_28]
0x18012265a  mov     [rbp+430h+IoStatusBlock], r15
0x18012265e  mov     rbx, [rbp+430h+arg_30]
0x180122665  mov     [rbp+430h+var_300], rbx
0x18012266c  mov     r13, [rbp+430h+arg_58]
0x180122673  mov     [rbp+430h+var_450], r13
0x180122677  mov     r14, [rbp+430h+arg_70]
0x18012267e  xor     eax, eax
0x180122680  mov     [rbp+430h+var_3B0], eax
0x180122686  mov     [rbp+430h+var_2B8], eax
0x18012268c  mov     [rbp+430h+var_2A8], al
0x180122692  mov     [rbp+430h+var_2D8], 1
0x18012269c  lea     rcx, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; this
0x1801226a3  call    ?RtlGetFacilityTracingFlags@Rtl@WCP@Windows@@YAKPEAU_RTL_TRACING_FACILITY@123@@Z; Windows::WCP::Rtl::RtlGetFacilityTracingFlags(Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)
0x1801226a8  lea     rcx, ?RtlTraceFormat_PCULONG_AsFSCreateOptions@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSCreateOptions(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x1801226af  lea     r8, aCo; "co"
0x1801226b6  lea     r9, ?RtlTraceFormat_PCULONG_AsFSCreateDisposition@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; struct Windows::Rtl::SystemImplementation::ParsedOptionsDisposition *
0x1801226bd  lea     r10, aCd; "cd"
0x1801226c4  lea     r11, ?RtlTraceFormat_PCULONG_AsFSShareAccess@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSShareAccess(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x1801226cb  lea     rdx, aWindowsRtlSyst_259; "Windows::Rtl::SystemImplementation::Dir"...
0x1801226d2  test    al, 0Eh
0x1801226d4  jz      loc_180122928
0x1801226da  mov     [rsp+640h+var_4C0], r14
0x1801226e2  lea     rax, ?Format_PCULONG_AsSysCreateFileDisposition@IRtlFileSystemProvider@SystemImplementation@Rtl@Windows@@SAXPEAUIRtlFormattedOutputStream@34@PEBX@Z; Windows::Rtl::SystemImplementation::IRtlFileSystemProvider::Format_PCULONG_AsSysCreateFileDisposition(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x1801226e9  mov     [rsp+640h+var_4C8], rax
0x1801226f1  lea     rax, aDisp; "disp"
0x1801226f8  mov     [rsp+640h+var_4D0], rax
0x180122700  lea     rax, [rbp+430h+arg_60]
0x180122707  mov     [rsp+640h+var_4D8], rax
0x18012270f  lea     rax, ?RtlTraceFormat_PCULONG@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180122716  mov     [rsp+640h+var_4E0], rax
0x18012271e  lea     rax, aEal; "eal"
0x180122725  mov     [rsp+640h+var_4E8], rax
0x18012272d  mov     [rsp+640h+var_4F0], r13
0x180122735  lea     rax, ?RtlTraceFormat_PCIO_STATUS_BLOCK@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCIO_STATUS_BLOCK(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18012273c  mov     [rsp+640h+var_4F8], rax
0x180122744  lea     rax, aEab; "eab"
0x18012274b  mov     [rsp+640h+var_500], rax
0x180122753  lea     rax, [rbp+430h+arg_50]
0x18012275a  mov     [rsp+640h+var_508], rax
0x180122762  mov     [rsp+640h+var_510], rcx
0x18012276a  mov     [rsp+640h+var_518], r8
0x180122772  lea     rax, [rbp+430h+arg_48]
0x180122779  mov     [rsp+640h+var_520], rax
0x180122781  mov     [rsp+640h+var_528], r9
0x180122789  mov     [rsp+640h+var_530], r10
0x180122791  lea     rax, [rbp+430h+arg_40]
0x180122798  mov     [rsp+640h+var_538], rax
0x1801227a0  mov     [rsp+640h+var_540], r11
0x1801227a8  lea     rax, aSa; "sa"
0x1801227af  mov     [rsp+640h+var_548], rax
0x1801227b7  lea     rax, [rbp+430h+arg_38]
0x1801227be  mov     [rsp+640h+var_550], rax
0x1801227c6  lea     rax, ?RtlTraceFormat_PCULONG_AsFSFileAttributes@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSFileAttributes(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x1801227cd  mov     [rsp+640h+var_558], rax
0x1801227d5  lea     rax, aFa; "fa"
0x1801227dc  mov     [rsp+640h+var_560], rax
0x1801227e4  mov     [rsp+640h+var_568], rbx
0x1801227ec  lea     rax, ?RtlTraceFormat_PCULONGLONG@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONGLONG(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x1801227f3  mov     [rsp+640h+var_570], rax
0x1801227fb  lea     rax, aAs; "as"
0x180122802  mov     [rsp+640h+var_578], rax
0x18012280a  mov     [rsp+640h+var_580], r15
0x180122812  lea     rax, ?RtlTraceFormat_PCIO_STATUS_BLOCK@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCIO_STATUS_BLOCK(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180122819  mov     [rsp+640h+var_588], rax
0x180122821  lea     rax, aIosb; "iosb"
0x180122828  mov     [rsp+640h+var_590], rax
0x180122830  mov     [rsp+640h+var_598], rsi
0x180122838  lea     rax, ?RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectFSHandleObject@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectFSHandleObject(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18012283f  mov     [rsp+640h+var_5A0], rax
0x180122847  lea     rax, aOa; "oa"
0x18012284e  mov     [rsp+640h+var_5A8], rax
0x180122856  lea     rax, [rbp+430h+var_380]
0x18012285d  mov     [rsp+640h+var_5B0], rax
0x180122865  lea     rax, ?RtlTraceFormat_PCULONG_AsFSFileDesiredAccess@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSFileDesiredAccess(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18012286c  mov     [rsp+640h+var_5B8], rax
0x180122874  lea     rax, aDa; "da"
0x18012287b  mov     [rsp+640h+var_5C0], rax
0x180122883  mov     [rsp+640h+var_5C8], rdi
0x180122888  lea     rax, ?Format_PCSilHandle@CSilHandle@SystemImplementation@Rtl@Windows@@SAXPEAUIRtlFormattedOutputStream@34@PEBX@Z; Windows::Rtl::SystemImplementation::CSilHandle::Format_PCSilHandle(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18012288f  mov     [rsp+640h+var_5D0], rax
0x180122894  lea     rax, aHandle; "handle"
0x18012289b  mov     [rsp+640h+var_5D8], rax
0x1801228a0  lea     rax, [rbp+430h+var_3A8]
0x1801228a7  mov     [rsp+640h+var_5E0], rax
0x1801228ac  lea     rax, ?Format_PCULONG_AsSysCreateFileFlags@IRtlFileSystemProvider@SystemImplementation@Rtl@Windows@@SAXPEAUIRtlFormattedOutputStream@34@PEBX@Z; Windows::Rtl::SystemImplementation::IRtlFileSystemProvider::Format_PCULONG_AsSysCreateFileFlags(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x1801228b3  mov     [rsp+640h+var_5E8], rax
0x1801228b8  lea     rax, aFlags; "flags"
0x1801228bf  mov     qword ptr [rsp+640h+EaLength], rax
0x1801228c4  mov     [rsp+640h+EaBuffer], 0Dh
0x1801228cd  lea     rax, aHandleHandleIo; "(handle = {handle}, iosb = {iosb}, disp"...
0x1801228d4  mov     qword ptr [rsp+640h+CreateOptions], rax; __int64
0x1801228d9  lea     rax, aFlagsFlagsHand; "(flags = {flags}, handle = {handle}, da"...
0x1801228e0  mov     qword ptr [rsp+640h+CreateDisposition], rax; __int64
0x1801228e5  lea     rax, aFlagsFlagsDaDa_2; "(flags = {flags}, da = {da}, oa = {oa},"...
0x1801228ec  mov     qword ptr [rsp+640h+ShareAccess], rax; unsigned int
0x1801228f1  lea     rdi, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_SIL
0x1801228f8  mov     qword ptr [rsp+640h+FileAttributes], rdi; Windows::WCP::Rtl *
0x1801228fd  mov     [rsp+640h+AllocationSize], rdx; __int64
0x180122902  mov     r9, r12; int
0x180122905  lea     r8, ?RtlTraceFormat_PCNTSTATUS@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; int
0x18012290c  lea     rdx, [rbp+430h+var_3B0]; int
0x180122913  lea     rcx, [rbp+430h+var_2E0]; int
0x18012291a  call    ?Arm@?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$0N@@Rtl@WCP@Windows@@QEAAXAEBUCSimpleNtStatusCarryingFrame@2ErrorHandling@4@P6AXPEAUIRtlFormattedOutputStream@24@PEBX@Z2QEBDPEAU_RTL_TRACING_FACILITY@234@444_KZZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,13>::Arm(Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame const &,void (*)(Windows::Rtl::IRtlFormattedOutputStream *,void const *),void const *,char const * const,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,char const * const,char const * const,unsigned __int64,...)
0x18012291f  lea     rdx, aWindowsRtlSyst_259; "Windows::Rtl::SystemImplementation::Dir"...
0x180122926  jmp     short loc_18012292F
0x180122928  lea     rdi, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_SIL
0x18012292f  xor     r13d, r13d
0x180122932  test    r14, r14
0x180122935  jz      short loc_18012293A
0x180122937  mov     [r14], r13d
0x18012293a  xorps   xmm0, xmm0
0x18012293d  movdqu  xmmword ptr [r15], xmm0
0x180122942  test    [rbp+430h+var_3A8], 20000h
0x18012294c  jz      short loc_1801229A2
0x18012294e  mov     eax, [rbp+430h+var_380]
0x180122954  mov     ecx, 10E0000h
0x180122959  and     eax, ecx
0x18012295b  cmp     eax, ecx
0x18012295d  jnz     short loc_18012297A
0x18012295f  cmp     [rsi+20h], r13
0x180122963  jz      short loc_18012297A
0x180122965  mov     eax, [rbp+430h+arg_50]
0x18012296b  and     eax, 41h
0x18012296e  mov     ecx, eax
0x180122970  jz      short loc_18012297A
0x180122972  dec     rax
0x180122975  test    rcx, rax
0x180122978  jz      short loc_1801229A2
0x18012297a  lea     rax, aOnecoreBaseWcp_30; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x180122981  mov     qword ptr [rbp+430h+var_448], rax
0x180122985  mov     qword ptr [rbp+430h+var_448+8], rdx
0x180122989  mov     [rbp+430h+var_438], 6F3h
0x180122991  lea     rax, aValidateforens_2; "ValidateForEnsureSetSecurity(DesiredAcc"...
0x180122998  mov     [rbp+430h+var_430], rax
0x18012299c  lea     rcx, [rbp+430h+var_448]
0x1801229a0  jmp     short loc_1801229E9
0x1801229a2  test    [rbp+430h+var_3A8], 40000h
0x1801229ac  jz      short loc_180122A10
0x1801229ae  test    [rbp+430h+var_380], 100h
0x1801229b8  jz      short loc_1801229C3
0x1801229ba  cmp     [rbp+430h+arg_38], r13d
0x1801229c1  jnz     short loc_180122A10
0x1801229c3  lea     rax, aOnecoreBaseWcp_30; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x1801229ca  mov     qword ptr [rbp+430h+var_478], rax
0x1801229ce  mov     qword ptr [rbp+430h+var_478+8], rdx
0x1801229d2  mov     [rbp+430h+var_468], 6F8h
0x1801229da  lea     rax, aValidateforens_0; "ValidateForEnsureSetAttributes(DesiredA"...
0x1801229e1  mov     [rbp+430h+var_460], rax
0x1801229e5  lea     rcx, [rbp+430h+var_478]
0x1801229e9  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801229f0  mov     r8d, 0C000000Dh
0x1801229f6  mov     [rbp+430h+var_3B0], 0C000000Dh
0x180122a00  call    RtlReportErrorOrigination
0x180122a05  mov     edi, [rbp+430h+var_3B0]
0x180122a0b  jmp     loc_180123E2B
0x180122a10  mov     rbx, [rbp+430h+arg_68]
0x180122a17  test    rbx, rbx
0x180122a1a  jz      short loc_180122A21
0x180122a1c  mov     rcx, [rbx]
0x180122a1f  jmp     short loc_180122A24
0x180122a21  mov     rcx, r13
0x180122a24  mov     [rbp+430h+FileHandle], rcx
0x180122a28  mov     rax, [rsi+8]
0x180122a2c  test    rax, rax
0x180122a2f  jz      loc_180122B59
0x180122a35  lea     rdx, [rax+8]; unsigned int
0x180122a39  cmp     [rdx], r13
0x180122a3c  jz      loc_180122B59
0x180122a42  cmp     [rdx], rcx
0x180122a45  jz      loc_180122B59
0x180122a4b  lea     rcx, [rbp+430h+FileHandle]
0x180122a4f  mov     [rbp+430h+var_450], rcx
0x180122a53  mov     [rbp+430h+var_300], rdx
0x180122a5a  mov     [rbp+430h+var_B0], r13
0x180122a61  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$RtlAutoTrace@UDirectFSHandleObject@DirectFileSystemProvider@SystemImplementation@Rtl@Windows@@PEAU_UNICODE_STRING@@U?$FormatPointerWrapper@PEAX@4WCP@5@U7485@@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@234@QEBDAEBUDirectFSHandleObject@DirectFileSystemProvider@SystemImplementation@24@AEBQEAU_UNICODE_STRING@@AEBU?$FormatPointerWrapper@PEAX@234@4@Z@SA@PEAUIRtlFormattedOutputStream@24@PEBX@Z; `Windows::WCP::Rtl::RtlAutoTrace<Windows::Rtl::SystemImplementation::DirectFileSystemProvider::DirectFSHandleObject,_UNICODE_STRING *,Windows::WCP::Rtl::FormatPointerWrapper<void *>,Windows::WCP::Rtl::FormatPointerWrapper<void *>>(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,Windows::Rtl::SystemImplementation::DirectFileSystemProvider::DirectFSHandleObject const &,_UNICODE_STRING * const &,Windows::WCP::Rtl::FormatPointerWrapper<void *> const &,Windows::WCP::Rtl::FormatPointerWrapper<void *> const &)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180122a68  mov     [rbp+430h+var_B0+8], rcx
0x180122a6f  mov     qword ptr [rbp+430h+var_A0], rax
0x180122a76  mov     qword ptr [rbp+430h+var_A0+8], r13
0x180122a7d  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$RtlAutoTrace@PEAU_UNICODE_STRING@@@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@234@QEBDAEBQEAU_UNICODE_STRING@@@Z@SA@PEAUIRtlFormattedOutputStream@24@PEBX@Z; `Windows::WCP::Rtl::RtlAutoTrace<_UNICODE_STRING *>(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,_UNICODE_STRING * const &)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180122a84  mov     qword ptr [rbp+430h+var_90], rax
0x180122a8b  lea     rax, [rsi+10h]
0x180122a8f  mov     qword ptr [rbp+430h+var_90+8], rax
0x180122a96  mov     [rbp+430h+var_80], r13
0x180122a9d  lea     rax, ?_lambda_invoker_cdecl_@_lambda_4_@?1???$RtlAutoTrace@UDirectFSHandleObject@DirectFileSystemProvider@SystemImplementation@Rtl@Windows@@PEAU_UNICODE_STRING@@U?$FormatPointerWrapper@PEAX@4WCP@5@U7485@@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@234@QEBDAEBUDirectFSHandleObject@DirectFileSystemProvider@SystemImplementation@24@AEBQEAU_UNICODE_STRING@@AEBU?$FormatPointerWrapper@PEAX@234@4@Z@SA@PEAUIRtlFormattedOutputStream@24@PEBX@Z; `Windows::WCP::Rtl::RtlAutoTrace<Windows::Rtl::SystemImplementation::DirectFileSystemProvider::DirectFSHandleObject,_UNICODE_STRING *,Windows::WCP::Rtl::FormatPointerWrapper<void *>,Windows::WCP::Rtl::FormatPointerWrapper<void *>>(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,Windows::Rtl::SystemImplementation::DirectFileSystemProvider::DirectFSHandleObject const &,_UNICODE_STRING * const &,Windows::WCP::Rtl::FormatPointerWrapper<void *> const &,Windows::WCP::Rtl::FormatPointerWrapper<void *> const &)'::`2'::_lambda_4_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180122aa4  mov     [rbp+430h+var_78], rax
0x180122aab  lea     rax, [rbp+430h+var_300]
0x180122ab2  mov     [rbp+430h+var_70], rax
0x180122ab9  mov     [rbp+430h+var_68], r13
0x180122ac0  lea     rax, ?_lambda_invoker_cdecl_@_lambda_4_@?1???$RtlAutoTrace@UDirectFSHandleObject@DirectFileSystemProvider@SystemImplementation@Rtl@Windows@@PEAU_UNICODE_STRING@@U?$FormatPointerWrapper@PEAX@4WCP@5@U7485@@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@234@QEBDAEBUDirectFSHandleObject@DirectFileSystemProvider@SystemImplementation@24@AEBQEAU_UNICODE_STRING@@AEBU?$FormatPointerWrapper@PEAX@234@4@Z@SA@PEAUIRtlFormattedOutputStream@24@PEBX@Z; `Windows::WCP::Rtl::RtlAutoTrace<Windows::Rtl::SystemImplementation::DirectFileSystemProvider::DirectFSHandleObject,_UNICODE_STRING *,Windows::WCP::Rtl::FormatPointerWrapper<void *>,Windows::WCP::Rtl::FormatPointerWrapper<void *>>(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,Windows::Rtl::SystemImplementation::DirectFileSystemProvider::DirectFSHandleObject const &,_UNICODE_STRING * const &,Windows::WCP::Rtl::FormatPointerWrapper<void *> const &,Windows::WCP::Rtl::FormatPointerWrapper<void *> const &)'::`2'::_lambda_4_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180122ac7  mov     [rbp+430h+var_60], rax
0x180122ace  lea     rax, [rbp+430h+var_450]
0x180122ad2  mov     [rbp+430h+var_58], rax
0x180122ad9  lea     rax, [rbp+430h+var_B0]
0x180122ae0  mov     qword ptr [rsp+640h+FileAttributes], rax; unsigned __int64
0x180122ae5  mov     [rsp+640h+AllocationSize], 4; char *
0x180122aee  lea     r9, aTransactionMis; "Transaction mismatch for [rd: {}, name:"...
0x180122af5  mov     r8, rdi; unsigned int
0x180122af8  mov     ecx, 2; this
0x180122afd  call    ?RtlTraceFromParameterList@Rtl@WCP@Windows@@YAXKKPEAU_RTL_TRACING_FACILITY@123@QEBD_KQEAU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlTraceFromParameterList(ulong,ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER * const)
0x180122b02  lea     rax, aOnecoreBaseWcp_28; "onecore\\base\\wcp\\sil\\inc\\systempro"...
0x180122b09  mov     [rbp+430h+var_D0], rax
0x180122b10  lea     rax, aWindowsRtlSyst_109; "Windows::Rtl::SystemImplementation::Dir"...
0x180122b17  mov     [rbp+430h+var_D0+8], rax
0x180122b1e  mov     [rbp+430h+var_C0], 6BBh
0x180122b29  mov     [rbp+430h+var_B8], r13
0x180122b30  mov     r8d, 0C0000212h
0x180122b36  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180122b3d  lea     rcx, [rbp+430h+var_D0]
0x180122b44  call    RtlReportErrorOrigination
0x180122b49  mov     edi, 0C0000212h
0x180122b4e  mov     [rbp+430h+var_3B0], edi
0x180122b54  jmp     loc_180123E2B
0x180122b59  mov     word ptr [rbp+430h+var_4AC], r13w
0x180122b5e  mov     byte ptr [rbp+430h+var_4AC+2], r13b
0x180122b62  lea     r8, [rbp+430h+var_4AC]; unsigned int
0x180122b66  mov     edx, [rbp+430h+arg_48]; unsigned int
0x180122b6c  mov     ecx, [rbp+430h+arg_50]; this
0x180122b72  call    ?ParseOptionsDisposition@SystemImplementation@Rtl@Windows@@YAJKKAEAUParsedOptionsDisposition@123@@Z; Windows::Rtl::SystemImplementation::ParseOptionsDisposition(ulong,ulong,Windows::Rtl::SystemImplementation::ParsedOptionsDisposition &)
0x180122b77  mov     edi, eax
0x180122b79  test    eax, eax
0x180122b7b  jns     short loc_180122B88
0x180122b7d  mov     [rbp+430h+var_3B0], eax
0x180122b83  jmp     loc_180123E2B
0x180122b88  mov     ecx, [rbp+430h+arg_50]
0x180122b8e  mov     r13d, 2
0x180122b94  mov     eax, [rbp+430h+var_380]
0x180122b9a  mov     r8b, byte ptr [rbp+430h+var_4AC]
0x180122b9e  mov     dl, byte ptr [rbp+430h+var_4AC+2]
0x180122ba1  and     ecx, 4000h
0x180122ba7  jz      loc_180122C42
0x180122bad  xor     edi, edi
0x180122baf  test    dl, dl
0x180122bb1  jz      loc_180122C44
0x180122bb7  test    r8b, r8b
0x180122bba  jz      short loc_180122BF6
0x180122bbc  test    al, 4
0x180122bbe  jnz     loc_180122C44
0x180122bc4  lea     rax, aOnecoreBaseWcp_30; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x180122bcb  mov     qword ptr [rbp+430h+var_4A0], rax
0x180122bcf  lea     rax, aWindowsRtlSyst_259; "Windows::Rtl::SystemImplementation::Dir"...
0x180122bd6  mov     qword ptr [rbp+430h+var_4A0+8], rax
0x180122bda  mov     [rbp+430h+var_490], 70Bh
0x180122be2  lea     rax, aDesiredaccessi; "DesiredAccessIn"
0x180122be9  mov     [rbp+430h+var_488], rax
0x180122bed  lea     rcx, [rbp+430h+var_4A0]
0x180122bf1  jmp     loc_1801229E9
0x180122bf6  cmp     byte ptr [rbp+430h+var_4AC+1], dil
0x180122bfa  jz      short loc_180122C44
0x180122bfc  test    r13b, al
0x180122bff  jnz     short loc_180122C44
0x180122c01  lea     rax, aOnecoreBaseWcp_30; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x180122c08  mov     [rbp+430h+var_300], rax
0x180122c0f  lea     rax, aWindowsRtlSyst_259; "Windows::Rtl::SystemImplementation::Dir"...
0x180122c16  mov     [rbp+430h+var_300+8], rax
0x180122c1d  mov     [rbp+430h+var_2F0], 70Fh
0x180122c28  lea     rax, aDesiredaccessi; "DesiredAccessIn"
0x180122c2f  mov     [rbp+430h+var_2E8], rax
0x180122c36  lea     rcx, [rbp+430h+var_300]
0x180122c3d  jmp     loc_1801229E9
0x180122c42  xor     edi, edi
0x180122c44  mov     [rbp+430h+DesiredAccess], eax
0x180122c4a  bt      eax, 1Ch
0x180122c4e  jnb     short loc_180122C5F
0x180122c50  btr     eax, 1Ch
0x180122c54  or      eax, 1F01FFh
0x180122c59  mov     [rbp+430h+DesiredAccess], eax
0x180122c5f  test    rbx, rbx
0x180122c62  jz      short loc_180122C7A
0x180122c64  test    byte ptr [rbp+430h+arg_50], 40h
0x180122c6b  jz      short loc_180122C7A
0x180122c6d  test    al, 20h
0x180122c6f  jz      short loc_180122C7A
0x180122c71  and     eax, 0FFFFFFDFh
0x180122c74  mov     [rbp+430h+DesiredAccess], eax
0x180122c7a  test    ecx, ecx
0x180122c7c  jz      short loc_180122C8B
0x180122c7e  test    al, 40h
0x180122c80  jz      short loc_180122C8B
0x180122c82  and     eax, 0FFFFFFBFh
  ... truncated ...
```
