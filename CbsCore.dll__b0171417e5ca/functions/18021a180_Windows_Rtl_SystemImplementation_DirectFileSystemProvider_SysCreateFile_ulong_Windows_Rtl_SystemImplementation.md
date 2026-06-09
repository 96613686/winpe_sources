# Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile(ulong,Windows::Rtl::SystemImplementation::CSilHandle *,ulong,_OBJECT_ATTRIBUTES &,_IO_STATUS_BLOCK *,_LARGE_INTEGER *,ulong,ulong,ulong,ulong,void *,ulong,Windows::Rtl::KtmTransactionInfoPointer,ulong *)

- ea: `0x18021a180`
- end: `0x18021b6f3`
- name: `?SysCreateFile@DirectFileSystemProvider@SystemImplementation@Rtl@Windows@@UEAAJKPEAVCSilHandle@234@KAEAU_OBJECT_ATTRIBUTES@@PEAU_IO_STATUS_BLOCK@@PEAT_LARGE_INTEGER@@KKKKPEAXKUKtmTransactionInfoPointer@34@PEAK@Z`
- size: `5491`
- prototype: ``
- caller_count: `0`
- callee_count: `37`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180019bdc`
- `0x18001a1a0`
- `0x180046198`
- `0x18005556c`
- `0x1800aa1a4`
- `0x1800aa1d4`
- `0x1800c16bc`
- `0x1800c21b0`
- `0x1800eb920`
- `0x1800f70dc`
- `0x1801f68f0`
- `0x180210730`
- `0x1802108c0`
- `0x180210c78`
- `0x180210c9c`
- `0x18021100c`
- `0x1802111e0`
- `0x1802125c0`
- `0x180213b78`
- `0x180215430`
- `0x1802159f8`
- `0x180216610`
- `0x18021905c`
- `0x180219364`
- `0x180219834`
- `0x1802198b4`
- `0x18021a180`
- `0x18022318c`
- `0x180225b38`
- `0x1802263dc`
- `0x180226488`
- `0x180227778`
- `0x180228fe4`
- `0x180228ffc`
- `0x18027d068`
- `0x18027ed9c`
- `0x1802d5010`

## import_xrefs

- `ntdll!RtlSetCurrentTransaction` at `0x18021ad56`
- `ntdll!RtlSetCurrentTransaction` at `0x18021b27a`
- `ntdll!RtlSetCurrentTransaction` at `0x18021b2c5`
- `ntdll!RtlSetCurrentTransaction` at `0x18021ad56`
- `ntdll!RtlSetCurrentTransaction` at `0x18021b27a`
- `ntdll!RtlSetCurrentTransaction` at `0x18021b2c5`
- `ntdll!RtlGetCurrentTransaction` at `0x18021ad45`
- `ntdll!RtlGetCurrentTransaction` at `0x18021b269`
- `ntdll!RtlGetCurrentTransaction` at `0x18021b2b4`
- `ntdll!RtlGetCurrentTransaction` at `0x18021ad45`
- `ntdll!RtlGetCurrentTransaction` at `0x18021b269`
- `ntdll!RtlGetCurrentTransaction` at `0x18021b2b4`
- `ntdll!RtlRaiseStatus` at `0x18021b2e7`
- `ntdll!RtlRaiseStatus` at `0x18021b2e7`
- `ntdll!NtCreateFile` at `0x18021ade1`
- `ntdll!NtCreateFile` at `0x18021aeda`
- `ntdll!NtCreateFile` at `0x18021ade1`
- `ntdll!NtCreateFile` at `0x18021aeda`

## string_xrefs

- `0x18021b08f`: `Sharing violation at NtCreateFile - giving up after {retries} retries!!\n   Flags = {flags}\n   DesiredAccess = {da}\n   ObjectAttributes = {oa}\n   AllocationSize = {as}\n   FileAttributes = {fa}\n   ShareAccess = {sa}\n   CreateDisposition = {cd}\n   CreateOptions = {co}`
- `0x18021af05`: `Transient sharing violation at NtCreateFile\n   Flags = {flags}\n   DesiredAccess = {da}\n   ObjectAttributes = {oa}\n   AllocationSize = {as}\n   FileAttributes = {fa}\n   ShareAccess = {sa}\n   CreateDisposition = {cd}\n   CreateOptions = {co}`
- `0x18021a5f6`: `DesiredAccessIn`
- `0x18021a636`: `DesiredAccessIn`
- `0x18021a792`: `DesiredAccessIn`
- `0x18021a7fc`: `DesiredAccessIn`
- `0x18021a238`: `Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile`
- `0x18021a48c`: `Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile`
- `0x18021a5e8`: `Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile`
- `0x18021a62b`: `Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile`
- `0x18021a787`: `Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile`
- `0x18021a7ee`: `Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile`
- `0x18021b68d`: `Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile`
- `0x18021a4dd`: `ValidateForEnsureSetSecurity(DesiredAccessIn, CreateOptions, ObjectAttributesIn)`
- `0x18021a526`: `ValidateForEnsureSetAttributes(DesiredAccessIn, FileAttributes)`

## pseudocode

```c
__int64 __fastcall Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile(
        __int64 *a1,
        unsigned int a2,
        _QWORD *a3,
        int a4,
        __int64 a5,
        PIO_STATUS_BLOCK IoStatusBlock,
        union _LARGE_INTEGER *a7,
        ULONG FileAttributes,
        ULONG ShareAccess,
        ULONG CreateDisposition,
        ULONG CreateOptions,
        void *a12,
        ULONG EaLength,
        _QWORD *a14,
        _DWORD *a15)
{
  _QWORD *v15; // r12
  _DWORD *v17; // rsi
  char ShouldArm; // al
  const char *v19; // r8
  const char *v20; // r9
  __m128i *v21; // rdx
  int v22; // eax
  unsigned int v23; // ebx
  _QWORD *v24; // rbx
  __int64 v25; // rdx
  struct Windows::Rtl::SystemImplementation::ParsedOptionsDisposition *v26; // r9
  __int64 v27; // rdx
  __int64 v28; // r8
  ACCESS_MASK v29; // eax
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  int v32; // eax
  unsigned int v33; // edi
  __int128 *v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rax
  int v37; // eax
  __int128 *v38; // rcx
  int v39; // eax
  __int128 *v40; // rcx
  __m128i v41; // xmm2
  __int64 v42; // xmm1_8
  __int16 v43; // ax
  __int16 v44; // r14
  _WORD *v45; // r12
  int v46; // eax
  int v47; // eax
  __m128i v48; // xmm2
  __int64 v49; // xmm1_8
  __int16 v50; // ax
  __m128i v51; // xmm2
  __int64 v52; // xmm1_8
  __int16 v53; // ax
  __int64 v54; // rdx
  NTSTATUS FileNT; // edi
  union _LARGE_INTEGER *v56; // rax
  __int64 v57; // r9
  int v58; // eax
  int v59; // r14d
  __int64 v60; // rdi
  __int64 v61; // rax
  int v62; // eax
  bool v63; // zf
  __int64 v64; // rbx
  NTSTATUS v65; // eax
  int v66; // r14d
  __int64 v67; // r9
  unsigned __int64 v68; // rcx
  int v69; // eax
  __int64 v70; // rdx
  __int64 v71; // rcx
  __int64 v72; // r8
  int v73; // eax
  __int64 v74; // rbx
  __int64 CurrentTransaction; // r14
  const struct _SECURITY_DESCRIPTOR *v76; // rax
  int v77; // eax
  __int64 v78; // r14
  __int64 (__fastcall *v79)(__int64 *, _QWORD, __int64, __int128 *, __int128 *, __int64, int, _QWORD *, _QWORD); // rax
  __int64 v80; // r9
  __int64 v81; // rcx
  PLARGE_INTEGER AllocationSize; // [rsp+20h] [rbp-1F0h]
  char v84; // [rsp+190h] [rbp-80h]
  __int16 v85; // [rsp+194h] [rbp-7Ch] BYREF
  char v86; // [rsp+196h] [rbp-7Ah]
  unsigned __int8 v87; // [rsp+198h] [rbp-78h]
  PLARGE_INTEGER v88; // [rsp+1A0h] [rbp-70h] BYREF
  __int128 v89; // [rsp+1A8h] [rbp-68h] BYREF
  __int64 v90; // [rsp+1B8h] [rbp-58h]
  const char *v91; // [rsp+1C0h] [rbp-50h]
  __m128i v92; // [rsp+1C8h] [rbp-48h] BYREF
  __int64 v93; // [rsp+1D8h] [rbp-38h]
  const char *v94; // [rsp+1E0h] [rbp-30h]
  __m128i v95; // [rsp+1E8h] [rbp-28h] BYREF
  __int64 v96; // [rsp+1F8h] [rbp-18h]
  const char *v97; // [rsp+200h] [rbp-10h]
  PVOID EaBuffer; // [rsp+208h] [rbp-8h]
  _QWORD v99[4]; // [rsp+210h] [rbp+0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+230h] [rbp+20h] BYREF
  _OWORD v101[3]; // [rsp+260h] [rbp+50h] BYREF
  __int64 v102; // [rsp+290h] [rbp+80h]
  unsigned int v103; // [rsp+298h] [rbp+88h] BYREF
  unsigned int v104; // [rsp+2A0h] [rbp+90h] BYREF
  ACCESS_MASK DesiredAccess; // [rsp+2A8h] [rbp+98h] BYREF
  Windows::Rtl::SystemImplementation *v106; // [rsp+2B0h] [rbp+A0h]
  __int128 v107; // [rsp+2C0h] [rbp+B0h] BYREF
  __int64 v108; // [rsp+2D0h] [rbp+C0h]
  const char *v109; // [rsp+2D8h] [rbp+C8h]
  void *FileHandle[2]; // [rsp+2E0h] [rbp+D0h] BYREF
  __int128 v111; // [rsp+2F0h] [rbp+E0h] BYREF
  __int128 v112; // [rsp+300h] [rbp+F0h] BYREF
  __int128 v113; // [rsp+310h] [rbp+100h]
  __int64 v114; // [rsp+320h] [rbp+110h]
  __int128 v115; // [rsp+330h] [rbp+120h] BYREF
  __int64 v116; // [rsp+340h] [rbp+130h]
  char v117; // [rsp+348h] [rbp+138h]
  __int16 v118; // [rsp+34Ah] [rbp+13Ah]
  __int128 v119; // [rsp+350h] [rbp+140h]
  __int128 v120; // [rsp+360h] [rbp+150h]
  __int128 v121; // [rsp+370h] [rbp+160h] BYREF
  __int64 v122; // [rsp+380h] [rbp+170h]
  char v123[8]; // [rsp+390h] [rbp+180h] BYREF
  int v124; // [rsp+398h] [rbp+188h]
  int v125; // [rsp+3B8h] [rbp+1A8h]
  char v126; // [rsp+3C8h] [rbp+1B8h]

  v15 = a3;
  v17 = a15;
  v88 = a7;
  EaBuffer = a12;
  v103 = 0;
  v125 = 0;
  v126 = 0;
  FileHandle[0] = a3;
  v104 = a2;
  LODWORD(v106) = a4;
  v124 = 1;
  ShouldArm = Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,13>::ShouldArm();
  v19 = "co";
  v20 = "Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile";
  if ( ShouldArm )
  {
    AllocationSize = (PLARGE_INTEGER)"Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile";
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,13>::Arm(
      v123,
      &v103,
      Windows::WCP::Rtl::RtlTraceFormat_PCNTSTATUS,
      a1);
    v20 = "Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile";
  }
  if ( v17 )
    *v17 = 0;
  v63 = (v104 & 0x20000) == 0;
  *(_OWORD *)&IoStatusBlock->Status = 0;
  if ( v63
    || (unsigned __int8)Windows::Rtl::SystemImplementation::ValidateForEnsureSetSecurity(
                          (unsigned int)v106,
                          CreateOptions,
                          *(_QWORD *)(a5 + 32),
                          "Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile") )
  {
    if ( (v104 & 0x40000) != 0
      && !Windows::Rtl::SystemImplementation::ValidateForEnsureSetAttributes(
            (Windows::Rtl::SystemImplementation *)(unsigned int)v106,
            FileAttributes,
            (unsigned int)v19) )
    {
      v92.m128i_i64[1] = (__int64)v20;
      v92.m128i_i64[0] = (__int64)"onecore\\base\\wcp\\sil\\ntsystem.cpp";
      v21 = &v92;
      v93 = 1784;
      v94 = "ValidateForEnsureSetAttributes(DesiredAccessIn, FileAttributes)";
      goto LABEL_11;
    }
    v24 = a14;
    if ( a14 )
      v25 = *a14;
    else
      v25 = 0;
    v22 = Windows::Rtl::SystemImplementation::DirectHandleObjectBase<Windows::Rtl::SystemImplementation::DirectFileSystemProvider::DirectFSHandleObject>::ValidateTransaction(
            a5,
            v25,
            v19,
            v20);
    if ( v22 < 0
      || (v85 = 0,
          v86 = 0,
          v22 = Windows::Rtl::SystemImplementation::ParseOptionsDisposition(
                  (Windows::Rtl::SystemImplementation *)CreateOptions,
                  CreateDisposition,
                  (unsigned int)&v85,
                  v26),
          v22 < 0) )
    {
      v103 = v22;
      goto LABEL_12;
    }
    v28 = 2;
    v29 = (unsigned int)v106;
    LOBYTE(v27) = v86;
    if ( (CreateOptions & 0x4000) != 0 && v86 )
    {
      if ( (_BYTE)v85 )
      {
        if ( ((unsigned __int8)v106 & 4) == 0 )
        {
          v108 = 1803;
          *(_QWORD *)&v107 = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
          v21 = (__m128i *)&v107;
          *((_QWORD *)&v107 + 1) = "Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile";
          v109 = "DesiredAccessIn";
          goto LABEL_11;
        }
      }
      else if ( HIBYTE(v85) && ((unsigned __int8)v106 & 2) == 0 )
      {
        v90 = 1807;
        *(_QWORD *)&v89 = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
        v21 = (__m128i *)&v89;
        *((_QWORD *)&v89 + 1) = "Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile";
        v91 = "DesiredAccessIn";
        goto LABEL_11;
      }
    }
    DesiredAccess = (unsigned int)v106;
    if ( ((unsigned int)v106 & 0x10000000) != 0 )
    {
      v29 = (unsigned int)v106 & 0xEFE0FE00 | 0x1F01FF;
      DesiredAccess = v29;
    }
    if ( v24 && (CreateOptions & 0x40) != 0 && (v29 & 0x20) != 0 )
    {
      v29 &= ~0x20u;
      DesiredAccess = v29;
    }
    if ( (CreateOptions & 0x4000) != 0 && (v29 & 0x40) != 0 )
      DesiredAccess = v29 & 0xFFFFFFBF;
    v116 = 0;
    v115 = 0;
    v119 = 0;
    v120 = 0;
    v117 = 0;
    v118 = 0;
    v87 = 0;
    v84 = 0;
    v30 = *(_OWORD *)(a5 + 16);
    *(_OWORD *)&ObjectAttributes.Length = *(_OWORD *)a5;
    v31 = *(_OWORD *)(a5 + 32);
    *(_OWORD *)&ObjectAttributes.ObjectName = v30;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = v31;
    if ( v86 || (v104 & 0x20000) != 0 )
    {
      v32 = Windows::Rtl::SystemImplementation::IRtlObjectProvider::CalculateSecurityForCreate(
              a1,
              (_BYTE)v85 != 0 ? 28 : 26,
              ObjectAttributes.RootDirectory,
              ObjectAttributes.ObjectName,
              ObjectAttributes.SecurityDescriptor,
              0,
              v24,
              &v115,
              0);
      v33 = v32;
      if ( v32 < 0 )
      {
        v103 = v32;
LABEL_40:
        Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v115);
        v23 = v33;
        goto LABEL_213;
      }
      if ( (v118 & 0x400) != 0 )
      {
        if ( ((unsigned int)v106 & 0x40000) == 0 )
        {
          v99[2] = 1861;
          v99[0] = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
          v34 = (__int128 *)v99;
          v99[1] = "Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile";
          v99[3] = "DesiredAccessIn";
LABEL_44:
          v23 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
                  &v103,
                  v34);
LABEL_212:
          Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v115);
          goto LABEL_213;
        }
        v87 = 1;
      }
      if ( (v118 & 0x800) != 0 )
      {
        if ( ((unsigned int)v106 & 0x1000000) == 0 )
        {
          *(_QWORD *)&v113 = 1870;
          *(_QWORD *)&v112 = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
          v34 = &v112;
          *((_QWORD *)&v112 + 1) = "Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile";
          *((_QWORD *)&v113 + 1) = "DesiredAccessIn";
          goto LABEL_44;
        }
        v84 = 1;
      }
      ObjectAttributes.SecurityDescriptor = (PVOID)Windows::Rtl::SecurityDescriptor::Get((Windows::Rtl::SecurityDescriptor *)&v115);
    }
    if ( ObjectAttributes.RootDirectory )
      ObjectAttributes.RootDirectory = *(HANDLE *)ObjectAttributes.RootDirectory;
    BUCL::Interlocked::IncrementWithPin<unsigned long>((char *)a1 + 44, v27, v28);
    v89 = 0;
    if ( v24 )
    {
      if ( *((_BYTE *)v24 + 8) )
      {
        v111 = 0;
        if ( ObjectAttributes.RootDirectory )
        {
          v35 = *(_QWORD *)(a5 + 8);
          v122 = 0;
          v36 = *a1;
          v121 = 0;
          v37 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int128 *))(v36 + 56))(a1, v35, &v121);
          v38 = &v121;
          v33 = v37;
          if ( v37 < 0 )
          {
            v103 = v37;
LABEL_58:
            Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(v38);
            Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(&v111);
LABEL_59:
            Windows::Rtl::SystemImplementation::CSilHandle::~CSilHandle((Windows::Rtl::SystemImplementation::CSilHandle *)&v89);
            goto LABEL_40;
          }
          v92 = 0;
          v93 = 0;
          v39 = Windows::StringUtil::Rtl::CombineNtPaths<Windows::Auto<_LUNICODE_STRING>,_UNICODE_STRING>(
                  &v121,
                  (__int64)ObjectAttributes.ObjectName,
                  (__int64)&v92);
          v33 = v39;
          if ( v39 < 0 )
          {
            v103 = v39;
            Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v92);
            v38 = &v121;
            goto LABEL_58;
          }
          if ( v92.m128i_i64[0] > 0xFFFEuLL )
          {
            v23 = -1073740757;
            v103 = -1073740757;
            Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v92);
            v40 = &v121;
LABEL_64:
            Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(v40);
            Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(&v111);
LABEL_211:
            Windows::Rtl::SystemImplementation::CSilHandle::~CSilHandle((Windows::Rtl::SystemImplementation::CSilHandle *)&v89);
            goto LABEL_212;
          }
          v41 = v92;
          v42 = v93;
          v93 = 0;
          v43 = _mm_cvtsi128_si32(v92);
          v92 = 0;
          DWORD1(v107) = 0;
          LOWORD(v107) = v43;
          *((_QWORD *)&v107 + 1) = v42;
          WORD1(v107) = _mm_extract_epi16(v41, 4);
          Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(&v111);
          v111 = v107;
          ObjectAttributes.ObjectName = (PUNICODE_STRING)&v111;
          ObjectAttributes.RootDirectory = 0;
          Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v92);
          Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v121);
        }
        v107 = 0;
        if ( (unsigned __int8)Windows::StringUtil::IsStringLowerCaseAsciiPrefixEqualCaseInvariant<_UNICODE_STRING,_UNICODE_STRING>(
                                &___LiteralObject__2U__BaseLiteralBuffer__0M_U_UNICODE_STRING___W_Details_RtlStringLiterals__3_W0FM__0HD__0HJ__0HD__0HE__0GF__0GN__0HC__0GP__0GP__0HE__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__Details_RtlStringLiterals__3U_UNICODE_STRING__B,
                                ObjectAttributes.ObjectName,
                                &v107) )
        {
          v44 = v107;
          v45 = (_WORD *)*((_QWORD *)&v107 + 1);
          if ( !(_WORD)v107 || **((_WORD **)&v107 + 1) == 92 )
          {
            v92 = 0;
            v93 = 0;
            v46 = Windows::StringUtil::Rtl::ConvertWin32FilePathToNtFilePath<wchar_t [260]>();
            v33 = v46;
            if ( v46 < 0 )
            {
              v103 = v46;
LABEL_71:
              v38 = (__int128 *)&v92;
              goto LABEL_58;
            }
            if ( !v44 )
              goto LABEL_82;
            if ( *v45 == 92 )
            {
              Windows::StringUtil::PopFrontAsciiCharacter<_UNICODE_STRING>(&v107);
              v44 = v107;
            }
            if ( v44 )
            {
              v96 = 0;
              v95 = 0;
              v47 = Windows::StringUtil::Rtl::CombineNtPaths<Windows::Auto<_LUNICODE_STRING>,_UNICODE_STRING>(
                      (__int128 *)v92.m128i_i8,
                      (__int64)&v107,
                      (__int64)&v95);
              v33 = v47;
              if ( v47 < 0 )
              {
                v103 = v47;
                Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v95);
                goto LABEL_71;
              }
              if ( v95.m128i_i64[0] > 0xFFFEuLL )
              {
                v23 = -1073740757;
                v103 = -1073740757;
                Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v95);
LABEL_80:
                v40 = (__int128 *)&v92;
                goto LABEL_64;
              }
              v48 = v95;
              v49 = v96;
              v96 = 0;
              v50 = _mm_cvtsi128_si32(v95);
              v95 = 0;
              DWORD1(v107) = 0;
              LOWORD(v107) = v50;
              *((_QWORD *)&v107 + 1) = v49;
              WORD1(v107) = _mm_extract_epi16(v48, 4);
              Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(&v111);
              v111 = v107;
              Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v95);
            }
            else
            {
LABEL_82:
              if ( v92.m128i_i64[0] > 0xFFFEuLL )
              {
                v23 = -1073740757;
                v103 = -1073740757;
                goto LABEL_80;
              }
              v51 = v92;
              v52 = v93;
              v93 = 0;
              v53 = _mm_cvtsi128_si32(v92);
              v92 = 0;
              DWORD1(v107) = 0;
              LOWORD(v107) = v53;
              *((_QWORD *)&v107 + 1) = v52;
              WORD1(v107) = _mm_extract_epi16(v51, 4);
              Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(&v111);
              v111 = v107;
            }
            ObjectAttributes.ObjectName = (PUNICODE_STRING)&v111;
            Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v92);
          }
          v15 = FileHandle[0];
        }
        v102 = 0;
        v54 = *v24;
        memset(v101, 0, sizeof(v101));
        FileNT = FsTxCreateFileNT(
                   CreateOptions,
                   v54,
                   ShareAccess,
                   FileAttributes,
                   (_DWORD)AllocationSize,
                   DesiredAccess,
                   (__int64)&ObjectAttributes,
                   (__int64)IoStatusBlock,
                   (__int64)v88,
                   FileAttributes,
                   ShareAccess,
                   CreateDisposition,
                   CreateOptions,
                   (__int64)EaBuffer,
                   EaLength,
                   (__int64)v101);
        if ( FileNT >= 0 )
        {
          v56 = (union _LARGE_INTEGER *)*((_QWORD *)&v101[0] + 1);
          if ( (unsigned __int64)(*((_QWORD *)&v101[0] + 1) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            if ( (_BYTE)v85 && !IoStatusBlock->Information )
              IoStatusBlock->Information = 1;
            v57 = *v24;
            v88 = v56;
            v58 = Windows::Rtl::SystemImplementation::DirectFileSystemProvider::DirectFSHandleObject::CreateFsTx(
                    a1,
                    &v88,
                    &v89,
                    v57);
            v59 = v58;
            if ( v58 < 0 )
            {
              v103 = v58;
              if ( (unsigned __int64)&v88[-1].QuadPart + 7 <= 0xFFFFFFFFFFFFFFFDuLL )
                anonymous_namespace_::CloseWithFsTxCloseHandleNT(v88);
              Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(&v111);
              goto LABEL_96;
            }
            if ( (unsigned __int64)&v88[-1].QuadPart + 7 <= 0xFFFFFFFFFFFFFFFDuLL )
              anonymous_namespace_::CloseWithFsTxCloseHandleNT(v88);
          }
        }
        Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(&v111);
LABEL_100:
        if ( FileNT >= 0 )
        {
          v60 = *((_QWORD *)&v89 + 1);
          if ( (_BYTE)v85 )
          {
            *(_DWORD *)(*((_QWORD *)&v89 + 1) + 20LL) = 2;
          }
          else
          {
            if ( !HIBYTE(v85) )
              goto LABEL_145;
            *(_DWORD *)(*((_QWORD *)&v89 + 1) + 20LL) = 1;
          }
          _mm_mfence();
LABEL_145:
          if ( IoStatusBlock->Information == 1 )
          {
            v76 = Windows::Rtl::SecurityDescriptor::Get((Windows::Rtl::SecurityDescriptor *)&v115);
            v59 = Windows::Rtl::SystemImplementation::IRtlFileSystemProvider::EnsureSetSecurityIfRequired(
                    a1,
                    v104,
                    v60,
                    v76,
                    v24);
            if ( v59 < 0 )
            {
LABEL_147:
              v103 = v59;
LABEL_96:
              Windows::Rtl::SystemImplementation::CSilHandle::~CSilHandle((Windows::Rtl::SystemImplementation::CSilHandle *)&v89);
              Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v115);
              v23 = v59;
              goto LABEL_213;
            }
            v77 = Windows::Rtl::SystemImplementation::IRtlFileSystemProvider::EnsureSetAttributesIfRequired(
                    a1,
                    v104,
                    v60,
                    FileAttributes,
                    v24);
            v23 = v77;
            if ( v77 < 0 )
            {
LABEL_149:
              v103 = v77;
              goto LABEL_211;
            }
          }
          else
          {
            if ( (FileAttributes & 0x2000) != 0 )
            {
              v114 = FileAttributes;
              v79 = *(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, __int128 *, __int128 *, __int64, int, _QWORD *, _QWORD))(*a1 + 152);
              v112 = 0;
              v113 = 0;
              v107 = 0;
              v59 = v79(a1, 0, v60, &v107, &v112, 40, 4, v24, 0);
              if ( v59 < 0 )
                goto LABEL_147;
            }
            if ( v87 || v84 )
            {
              v78 = v60;
              v80 = (4 * v87) | 8u;
              if ( !v84 )
                v80 = 4 * (unsigned int)v87;
              v77 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64, PVOID, _QWORD *))(*a1 + 32))(
                      a1,
                      2,
                      v60,
                      v80,
                      ObjectAttributes.SecurityDescriptor,
                      v24);
              v23 = v77;
              if ( v77 < 0 )
                goto LABEL_149;
              goto LABEL_158;
            }
          }
          v78 = v60;
LABEL_158:
          HandleTracker::TrackHandle(a1 + 2, 0, v78, 0);
          v81 = v89;
          v89 = *(_OWORD *)v15;
          v15[1] = v60;
          *v15 = v81;
          if ( v17 )
            *v17 = 1;
          goto LABEL_207;
        }
        if ( v17 )
        {
          if ( (FileNT == -1073741772 || FileNT == -1073741766) && (v104 & 2) != 0 )
          {
            *v17 = 3;
LABEL_207:
            v126 = 1;
            Windows::Rtl::SystemImplementation::CSilHandle::~CSilHandle((Windows::Rtl::SystemImplementation::CSilHandle *)&v89);
            Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v115);
            Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,13>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,13>(v123);
            return v103;
          }
          switch ( FileNT )
          {
            case -1073741738:
              if ( (v104 & 0x400) != 0 )
              {
                *v17 = 12;
                goto LABEL_207;
              }
              break;
            case -1073741638:
              if ( (v104 & 0x80u) != 0 )
              {
                *v17 = 9;
                goto LABEL_207;
              }
              break;
            case -1073741565:
              if ( (v104 & 0x100) != 0 )
              {
                *v17 = 10;
                goto LABEL_207;
              }
              break;
            case -1073741771:
              if ( (v104 & 1) != 0 )
              {
                *v17 = 2;
                goto LABEL_207;
              }
              break;
            case -1073741757:
              if ( (v104 & 4) != 0 )
              {
                *v17 = 4;
                goto LABEL_207;
              }
              break;
            case -1073741790:
              if ( (v104 & 8) != 0 )
              {
                *v17 = 5;
                goto LABEL_207;
              }
              break;
            case -1073741788:
              if ( (v104 & 0x10) != 0 )
              {
                *v17 = 6;
                goto LABEL_207;
              }
              break;
            case -1073741773:
              if ( (v104 & 0x20) != 0 )
              {
                *v17 = 7;
                goto LABEL_207;
              }
              break;
            case -1073741767:
              if ( (v104 & 0x40) != 0 )
              {
                *v17 = 8;
                goto LABEL_207;
              }
              break;
            case -1072103423:
              if ( (v104 & 0x200) != 0 )
              {
                *v17 = 11;
                goto LABEL_207;
              }
              break;
            case -1073741535:
              if ( (v104 & 0x800) != 0 )
              {
                *v17 = 13;
                goto LABEL_207;
              }
              break;
            case -1073741489:
              if ( (v104 & 0x1000) != 0 )
              {
                *v17 = 14;
                goto LABEL_207;
              }
              break;
            case -1073741184:
              if ( (v104 & 0x100000) != 0 )
              {
                *v17 = 15;
                goto LABEL_207;
              }
              break;
            default:
              if ( FileNT == -1073741191 && (v104 & 0x200000) != 0 )
              {
                *v17 = 16;
                goto LABEL_207;
              }
              break;
          }
          *(_QWORD *)&v113 = 2233;
        }
        else
        {
          *(_QWORD *)&v113 = 2238;
        }
        *((_QWORD *)&v113 + 1) = 0;
        *(_QWORD *)&v112 = "onecore\\base\\wcp\\sil\\ntsystem.cpp";
        *((_QWORD *)&v112 + 1) = "Windows::Rtl::SystemImplementation::DirectFileSystemProvider::SysCreateFile";
        v23 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                &v103,
                &v112,
                (unsigned int)FileNT);
        goto LABEL_211;
      }
      v61 = *v24;
    }
    else
    {
      v61 = 0;
    }
    *(_QWORD *)&v107 = v61;
    BYTE8(v107) = 0;
    v62 = TxCaptureAndRelease::Set((TxCaptureAndRelease *)&v107);
    v33 = v62;
    if ( v62 >= 0 )
    {
      FileHandle[0] = 0;
      v65 = NtCreateFile(
              FileHandle,
              DesiredAccess,
              &ObjectAttributes,
              IoStatusBlock,
              v88,
              FileAttributes,
              ShareAccess,
              CreateDisposition,
              CreateOptions,
              EaBuffer,
              EaLength);
      FileNT = v65;
      if ( v65 == -1073741191 || v65 == -1073741184 )
        Windows::Rtl::SystemImplementation::LogReparseData(&ObjectAttributes);
      if ( (v104 & 4) != 0 )
        goto LABEL_117;
      v66 = 30;
LABEL_116:
      if ( FileNT != -1073741757 )
      {
LABEL_117:
        if ( FileNT < 0
          || (!v24 ? (v67 = 0) : (v67 = *v24),
              v73 = Windows::Rtl::SystemImplementation::DirectHandleObjectBase<Windows::Rtl::SystemImplementation::DirectFileSystemProvider::DirectFSHandleObject>::Create(
                      a1,
                      FileHandle,
                      &v89,
                      v67),
              v59 = v73,
              v73 >= 0) )
        {
LABEL_138:
          Windows::Rtl::AutoHandleBase<Windows::Rtl::AutoHandleDefaultTraits<void *>,Windows::Rtl::AutoTxnHandle>::Close(FileHandle);
          if ( !BYTE8(v107) )
            goto LABEL_100;
          CurrentTransaction = RtlGetCurrentTransaction();
          if ( (unsigned int)RtlSetCurrentTransaction(0) )
          {
            if ( CurrentTransaction == (_QWORD)v107 )
              goto LABEL_100;
          }
        }
        else
        {
          v103 = v73;
          Windows::Rtl::AutoHandleBase<Windows::Rtl::AutoHandleDefaultTraits<void *>,Windows::Rtl::AutoTxnHandle>::Close(FileHandle);
          if ( !BYTE8(v107) )
            goto LABEL_96;
          v74 = RtlGetCurrentTransaction();
          if ( (unsigned int)RtlSetCurrentTransaction(0) )
          {
            if ( v74 == (_QWORD)v107 )
              goto LABEL_96;
          }
        }
LABEL_141:
        RtlRaiseStatus(-1073740768);
      }
      while ( 1 )
      {
        if ( !v66 )
          goto LABEL_138;
        v68 = (30 - v66) / 0xAu;
        if ( v68 >= 3 )
          v68 = 2;
        v69 = DelayExecution((&s_rgSharingViolationWaitMilliseconds)[v68]);
        v33 = v69;
        if ( v69 < 0 )
          break;
        FileNT = NtCreateFile(
                   FileHandle,
                   DesiredAccess,
                   &ObjectAttributes,
                   IoStatusBlock,
                   v88,
                   FileAttributes,
                   ShareAccess,
                   CreateDisposition,
                   CreateOptions,
                   EaBuffer,
                   EaLength);
        if ( FileNT >= 0 )
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
            Windows::Rtl::SystemImplementation::IRtlFileSystemProvider::Format_PCULONG_AsSysCreateFileFlags,
            &v104,
            "da",
            Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSFileDesiredAccess,
            &DesiredAccess,
            "oa",
            Windows::WCP::Rtl::RtlTraceFormat_PCOBJECT_ATTRIBUTES,
            &ObjectAttributes,
            "as",
            `Windows::Tracing::RtlFormatIntoStream<unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,int,__int64>'::`2'::_lambda_4_::_lambda_invoker_cdecl_,
            v88,
            "fa",
            Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSFileAttributes,
            &FileAttributes,
            "sa",
            Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSShareAccess,
            &ShareAccess,
            "cd",
            Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSCreateDisposition,
            &CreateDisposition,
            "co",
            Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSCreateOptions,
            &CreateOptions);
        if ( --v66 )
          goto LABEL_116;
        if ( FileNT != -1073741757 )
          goto LABEL_117;
        if ( (int)Windows::Rtl::SystemImplementation::LogProcessesHoldingFile(&ObjectAttributes) < 0 )
          Windows::WCP::Rtl::RtlAutoTrace<_UNICODE_STRING *>(v71, v70, v72, &ObjectAttributes.ObjectName);
        *(_QWORD *)&v111 = 30;
        Windows::WCP::Rtl::RtlTrace(
          0,
          (unsigned int)&Windows::WCP::Rtl::Facility_SIL,
          (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)"Sharing violation at NtCreateFile - giving up after {retrie"
                                                             "s} retries!!\n"
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
          &v111,
          "flags",
          Windows::Rtl::SystemImplementation::IRtlFileSystemProvider::Format_PCULONG_AsSysCreateFileFlags,
          &v104,
          "da",
          Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSFileDesiredAccess,
          &DesiredAccess,
          "oa",
          Windows::WCP::Rtl::RtlTraceFormat_PCOBJECT_ATTRIBUTES,
          &ObjectAttributes,
          "as",
          `Windows::Tracing::RtlFormatIntoStream<unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,int,__int64>'::`2'::_lambda_4_::_lambda_invoker_cdecl_,
          v88,
          "fa",
          Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSFileAttributes,
          &FileAttributes,
          "sa",
          Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSShareAccess,
          &ShareAccess,
          "cd",
          Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSCreateDisposition,
          &CreateDisposition,
          "co",
          Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSCreateOptions,
          &CreateOptions);
      }
      v103 = v69;
      Windows::Rtl::AutoHandleBase<Windows::Rtl::AutoHandleDefaultTraits<void *>,Windows::Rtl::AutoTxnHandle>::Close(FileHandle);
      v63 = BYTE8(v107) == 0;
    }
    else
    {
      v63 = BYTE8(v107) == 0;
      v103 = v62;
    }
    if ( v63 )
      goto LABEL_59;
    v64 = RtlGetCurrentTransaction();
    if ( (unsigned int)RtlSetCurrentTransaction(0) )
    {
      if ( v64 == (_QWORD)v107 )
        goto LABEL_59;
    }
    goto LABEL_141;
  }
  v95.m128i_i64[1] = (__int64)v20;
  v95.m128i_i64[0] = (__int64)"onecore\\base\\wcp\\sil\\ntsystem.cpp";
  v21 = &v95;
  v96 = 1779;
  v97 = "ValidateForEnsureSetSecurity(DesiredAccessIn, CreateOptions, ObjectAttributesIn)";
LABEL_11:
  v22 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
          &v103,
          v21);
LABEL_12:
  v23 = v22;
LABEL_213:
  Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,13>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,13>(v123);
  return v23;
}

```

## disassembly

```asm
0x18021a180  push    rbp
0x18021a182  push    rbx
0x18021a183  push    rsi
0x18021a184  push    rdi
0x18021a185  push    r12
0x18021a187  push    r13
0x18021a189  push    r14
0x18021a18b  push    r15
0x18021a18d  lea     rbp, [rsp-3A8h]
0x18021a195  sub     rsp, 5B8h
0x18021a19c  mov     rax, cs:__security_cookie
0x18021a1a3  xor     rax, rsp
0x18021a1a6  mov     [rbp+3E0h+var_50], rax
0x18021a1ad  mov     rbx, [rbp+3E0h+arg_30]
0x18021a1b4  xor     eax, eax
0x18021a1b6  mov     rdi, [rbp+3E0h+arg_58]
0x18021a1bd  mov     r12, r8
0x18021a1c0  mov     r14, [rbp+3E0h+arg_20]
0x18021a1c7  mov     r15, rcx
0x18021a1ca  mov     r13, [rbp+3E0h+IoStatusBlock]
0x18021a1d1  mov     rsi, [rbp+3E0h+arg_70]
0x18021a1d8  mov     [rbp+3E0h+var_450], rbx
0x18021a1dc  mov     [rbp+3E0h+var_3E8], rdi
0x18021a1e0  mov     [rbp+3E0h+var_358], eax
0x18021a1e6  mov     [rbp+3E0h+var_238], eax
0x18021a1ec  mov     [rbp+3E0h+var_228], al
0x18021a1f2  mov     [rbp+3E0h+FileHandle], r8
0x18021a1f9  mov     [rbp+3E0h+var_350], edx
0x18021a1ff  mov     dword ptr [rbp+3E0h+var_340], r9d
0x18021a206  mov     [rbp+3E0h+var_258], 1
0x18021a210  call    ?ShouldArm@?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$0N@@Rtl@WCP@Windows@@SA_NPEAU_RTL_TRACING_FACILITY@234@@Z; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,13>::ShouldArm(Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)
0x18021a215  lea     rdx, ?RtlTraceFormat_PCULONG_AsFSCreateOptions@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSCreateOptions(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18021a21c  lea     r8, aCo; "co"
0x18021a223  lea     r10, ?RtlTraceFormat_PCULONG_AsFSCreateDisposition@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSCreateDisposition(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18021a22a  lea     r11, aCd; "cd"
0x18021a231  lea     rcx, ?Facility_SIL@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_SIL
0x18021a238  lea     r9, aWindowsRtlSyst_266; "Windows::Rtl::SystemImplementation::Dir"...
0x18021a23f  test    al, al
0x18021a241  jz      loc_18021A493
0x18021a247  mov     [rsp+5F0h+var_470], rsi
0x18021a24f  lea     rax, ?Format_PCULONG_AsSysCreateFileDisposition@IRtlFileSystemProvider@SystemImplementation@Rtl@Windows@@SAXPEAUIRtlFormattedOutputStream@34@PEBX@Z; Windows::Rtl::SystemImplementation::IRtlFileSystemProvider::Format_PCULONG_AsSysCreateFileDisposition(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18021a256  mov     [rsp+5F0h+var_478], rax
0x18021a25e  lea     rax, aDisp; "disp"
0x18021a265  mov     [rsp+5F0h+var_480], rax
0x18021a26d  lea     rax, [rbp+3E0h+arg_60]
0x18021a274  mov     [rsp+5F0h+var_488], rax
0x18021a27c  lea     rax, ?RtlTraceFormat_PCULONG@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18021a283  mov     [rsp+5F0h+var_490], rax
0x18021a28b  lea     rax, aEal; "eal"
0x18021a292  mov     [rsp+5F0h+var_498], rax
0x18021a29a  lea     rax, ?RtlTraceFormat_PCVOID@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCVOID(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18021a2a1  mov     [rsp+5F0h+var_4A0], rdi
0x18021a2a9  mov     [rsp+5F0h+var_4A8], rax
0x18021a2b1  lea     rax, aEab; "eab"
0x18021a2b8  mov     [rsp+5F0h+var_4B0], rax
0x18021a2c0  lea     rax, [rbp+3E0h+arg_50]
0x18021a2c7  mov     [rsp+5F0h+var_4B8], rax
0x18021a2cf  lea     rax, [rbp+3E0h+arg_48]
0x18021a2d6  mov     [rsp+5F0h+var_4C0], rdx
0x18021a2de  lea     rdx, [rbp+3E0h+var_358]
0x18021a2e5  mov     [rsp+5F0h+var_4C8], r8
0x18021a2ed  lea     r8, ?RtlTraceFormat_PCNTSTATUS@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCNTSTATUS(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18021a2f4  mov     [rsp+5F0h+var_4D0], rax
0x18021a2fc  lea     rax, [rbp+3E0h+arg_40]
0x18021a303  mov     [rsp+5F0h+var_4D8], r10
0x18021a30b  mov     [rsp+5F0h+var_4E0], r11
0x18021a313  mov     [rsp+5F0h+var_4E8], rax
0x18021a31b  lea     rax, ?RtlTraceFormat_PCULONG_AsFSShareAccess@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSShareAccess(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18021a322  mov     [rsp+5F0h+var_4F0], rax
0x18021a32a  lea     rax, aSa; "sa"
0x18021a331  mov     [rsp+5F0h+var_4F8], rax
0x18021a339  lea     rax, [rbp+3E0h+arg_38]
0x18021a340  mov     [rsp+5F0h+var_500], rax
0x18021a348  lea     rax, ?RtlTraceFormat_PCULONG_AsFSFileAttributes@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSFileAttributes(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18021a34f  mov     [rsp+5F0h+var_508], rax
0x18021a357  lea     rax, aFa; "fa"
0x18021a35e  mov     [rsp+5F0h+var_510], rax
0x18021a366  lea     rax, ?_lambda_invoker_cdecl_@_lambda_4_@?1???$RtlFormatIntoStream@_K_K_K_K_K_KH_J@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@3@QEBDAEB_K22222AEBHAEB_J@Z@SA@0PEBX@Z; `Windows::Tracing::RtlFormatIntoStream<unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,int,__int64>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,int const &,__int64 const &)'::`2'::_lambda_4_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18021a36d  mov     [rsp+5F0h+var_518], rbx
0x18021a375  mov     [rsp+5F0h+var_520], rax
0x18021a37d  lea     rax, aAs; "as"
0x18021a384  mov     [rsp+5F0h+var_528], rax
0x18021a38c  lea     rax, ?RtlTraceFormat_PCIO_STATUS_BLOCK@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCIO_STATUS_BLOCK(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18021a393  mov     [rsp+5F0h+var_530], r13
0x18021a39b  mov     [rsp+5F0h+var_538], rax
0x18021a3a3  lea     rax, aIosb; "iosb"
0x18021a3aa  mov     [rsp+5F0h+var_540], rax
0x18021a3b2  lea     rax, ?RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectFSHandleObject@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCOBJECT_ATTRIBUTES_WithDirectFSHandleObject(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18021a3b9  mov     [rsp+5F0h+var_548], r14
0x18021a3c1  mov     [rsp+5F0h+var_550], rax
0x18021a3c9  lea     rax, aOa; "oa"
0x18021a3d0  mov     [rsp+5F0h+var_558], rax
0x18021a3d8  lea     rax, [rbp+3E0h+var_340]
0x18021a3df  mov     [rsp+5F0h+var_560], rax
0x18021a3e7  lea     rax, ?RtlTraceFormat_PCULONG_AsFSFileDesiredAccess@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; Windows::WCP::Rtl::RtlTraceFormat_PCULONG_AsFSFileDesiredAccess(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18021a3ee  mov     [rsp+5F0h+var_568], rax
0x18021a3f6  lea     rax, aDa; "da"
0x18021a3fd  mov     [rsp+5F0h+var_570], rax
0x18021a405  lea     rax, ?Format_PCSilHandle@CSilHandle@SystemImplementation@Rtl@Windows@@SAXPEAUIRtlFormattedOutputStream@34@PEBX@Z; Windows::Rtl::SystemImplementation::CSilHandle::Format_PCSilHandle(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18021a40c  mov     [rsp+5F0h+var_578], r12
0x18021a411  mov     [rsp+5F0h+var_580], rax
0x18021a416  lea     rax, aHandle; "handle"
0x18021a41d  mov     [rsp+5F0h+var_588], rax
0x18021a422  lea     rax, [rbp+3E0h+var_350]
0x18021a429  mov     [rsp+5F0h+var_590], rax
0x18021a42e  lea     rax, ?Format_PCULONG_AsSysCreateFileFlags@IRtlFileSystemProvider@SystemImplementation@Rtl@Windows@@SAXPEAUIRtlFormattedOutputStream@34@PEBX@Z; Windows::Rtl::SystemImplementation::IRtlFileSystemProvider::Format_PCULONG_AsSysCreateFileFlags(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x18021a435  mov     [rsp+5F0h+var_598], rax
0x18021a43a  lea     rax, aFlags_0; "flags"
0x18021a441  mov     qword ptr [rsp+5F0h+EaLength], rax
0x18021a446  lea     rax, aHandleHandleIo; "(handle = {handle}, iosb = {iosb}, disp"...
0x18021a44d  mov     [rsp+5F0h+EaBuffer], 0Dh
0x18021a456  mov     qword ptr [rsp+5F0h+CreateOptions], rax
0x18021a45b  lea     rax, aFlagsFlagsHand; "(flags = {flags}, handle = {handle}, da"...
0x18021a462  mov     qword ptr [rsp+5F0h+CreateDisposition], rax
0x18021a467  lea     rax, aFlagsFlagsDaDa_2; "(flags = {flags}, da = {da}, oa = {oa},"...
0x18021a46e  mov     qword ptr [rsp+5F0h+ShareAccess], rax
0x18021a473  mov     qword ptr [rsp+5F0h+FileAttributes], rcx
0x18021a478  lea     rcx, [rbp+3E0h+var_260]
0x18021a47f  mov     [rsp+5F0h+AllocationSize], r9
0x18021a484  mov     r9, r15
0x18021a487  call    ?Arm@?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$0N@@Rtl@WCP@Windows@@QEAAXAEBUCSimpleNtStatusCarryingFrame@2ErrorHandling@4@P6AXPEAUIRtlFormattedOutputStream@24@PEBX@Z2QEBDPEAU_RTL_TRACING_FACILITY@234@444_KZZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,13>::Arm(Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame const &,void (*)(Windows::Rtl::IRtlFormattedOutputStream *,void const *),void const *,char const * const,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,char const * const,char const * const,unsigned __int64,...)
0x18021a48c  lea     r9, aWindowsRtlSyst_266; "Windows::Rtl::SystemImplementation::Dir"...
0x18021a493  xor     edi, edi
0x18021a495  test    rsi, rsi
0x18021a498  jz      short loc_18021A49C
0x18021a49a  mov     [rsi], edi
0x18021a49c  test    [rbp+3E0h+var_350], 20000h
0x18021a4a6  xorps   xmm0, xmm0
0x18021a4a9  movdqu  xmmword ptr [r13+0], xmm0
0x18021a4af  jz      short loc_18021A4F2
0x18021a4b1  mov     r8, [r14+20h]
0x18021a4b5  mov     edx, [rbp+3E0h+arg_50]
0x18021a4bb  mov     ecx, dword ptr [rbp+3E0h+var_340]
0x18021a4c1  call    Windows__Rtl__SystemImplementation__ValidateForEnsureSetSecurity
0x18021a4c6  test    al, al
0x18021a4c8  jnz     short loc_18021A4F2
0x18021a4ca  lea     rax, aOnecoreBaseWcp_36; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x18021a4d1  mov     qword ptr [rbp+3E0h+var_408+8], r9
0x18021a4d5  mov     qword ptr [rbp+3E0h+var_408], rax
0x18021a4d9  lea     rdx, [rbp+3E0h+var_408]
0x18021a4dd  lea     rax, aValidateforens_2; "ValidateForEnsureSetSecurity(DesiredAcc"...
0x18021a4e4  mov     [rbp+3E0h+var_3F8], 6F3h
0x18021a4ec  mov     [rbp+3E0h+var_3F0], rax
0x18021a4f0  jmp     short loc_18021A539
0x18021a4f2  test    [rbp+3E0h+var_350], 40000h
0x18021a4fc  jz      short loc_18021A54C
0x18021a4fe  mov     edx, [rbp+3E0h+arg_38]; unsigned int
0x18021a504  mov     ecx, dword ptr [rbp+3E0h+var_340]; this
0x18021a50a  call    ?ValidateForEnsureSetAttributes@SystemImplementation@Rtl@Windows@@YA_NKK@Z; Windows::Rtl::SystemImplementation::ValidateForEnsureSetAttributes(ulong,ulong)
0x18021a50f  test    al, al
0x18021a511  jnz     short loc_18021A54C
0x18021a513  lea     rax, aOnecoreBaseWcp_36; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x18021a51a  mov     qword ptr [rbp+3E0h+var_428+8], r9
0x18021a51e  mov     qword ptr [rbp+3E0h+var_428], rax
0x18021a522  lea     rdx, [rbp+3E0h+var_428]
0x18021a526  lea     rax, aValidateforens_0; "ValidateForEnsureSetAttributes(DesiredA"...
0x18021a52d  mov     [rbp+3E0h+var_418], 6F8h
0x18021a535  mov     [rbp+3E0h+var_410], rax
0x18021a539  lea     rcx, [rbp+3E0h+var_358]
0x18021a540  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18021a545  mov     ebx, eax
0x18021a547  jmp     loc_18021B6C1
0x18021a54c  mov     rbx, [rbp+3E0h+arg_68]
0x18021a553  test    rbx, rbx
0x18021a556  jz      short loc_18021A55D
0x18021a558  mov     rdx, [rbx]
0x18021a55b  jmp     short loc_18021A560
0x18021a55d  mov     rdx, rdi
0x18021a560  mov     rcx, r14
0x18021a563  call    ?ValidateTransaction@?$DirectHandleObjectBase@UDirectFSHandleObject@DirectFileSystemProvider@SystemImplementation@Rtl@Windows@@@SystemImplementation@Rtl@Windows@@SAJAEAU_OBJECT_ATTRIBUTES@@PEAX@Z; Windows::Rtl::SystemImplementation::DirectHandleObjectBase<Windows::Rtl::SystemImplementation::DirectFileSystemProvider::DirectFSHandleObject>::ValidateTransaction(_OBJECT_ATTRIBUTES &,void *)
0x18021a568  test    eax, eax
0x18021a56a  jns     short loc_18021A574
0x18021a56c  mov     [rbp+3E0h+var_358], eax
0x18021a572  jmp     short loc_18021A545
0x18021a574  mov     edx, [rbp+3E0h+arg_48]; unsigned int
0x18021a57a  lea     r8, [rbp+3E0h+var_45C]; unsigned int
0x18021a57e  mov     ecx, [rbp+3E0h+arg_50]; this
0x18021a584  mov     word ptr [rbp+3E0h+var_45C], di
0x18021a588  mov     byte ptr [rbp+3E0h+var_45C+2], dil
0x18021a58c  call    ?ParseOptionsDisposition@SystemImplementation@Rtl@Windows@@YAJKKAEAUParsedOptionsDisposition@123@@Z; Windows::Rtl::SystemImplementation::ParseOptionsDisposition(ulong,ulong,Windows::Rtl::SystemImplementation::ParsedOptionsDisposition &)
0x18021a591  test    eax, eax
0x18021a593  js      short loc_18021A56C
0x18021a595  mov     ecx, [rbp+3E0h+arg_50]
0x18021a59b  mov     r8d, 2
0x18021a5a1  mov     eax, dword ptr [rbp+3E0h+var_340]
0x18021a5a7  mov     dl, byte ptr [rbp+3E0h+var_45C+2]
0x18021a5aa  and     ecx, 4000h
0x18021a5b0  jz      loc_18021A646
0x18021a5b6  test    dl, dl
0x18021a5b8  jz      loc_18021A646
0x18021a5be  cmp     byte ptr [rbp+3E0h+var_45C], dil
0x18021a5c2  jz      short loc_18021A609
0x18021a5c4  test    al, 4
0x18021a5c6  jnz     short loc_18021A646
0x18021a5c8  lea     rax, aOnecoreBaseWcp_36; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x18021a5cf  mov     [rbp+3E0h+var_320], 70Bh
0x18021a5da  mov     qword ptr [rbp+3E0h+var_330], rax
0x18021a5e1  lea     rdx, [rbp+3E0h+var_330]
0x18021a5e8  lea     rax, aWindowsRtlSyst_266; "Windows::Rtl::SystemImplementation::Dir"...
0x18021a5ef  mov     qword ptr [rbp+3E0h+var_330+8], rax
0x18021a5f6  lea     rax, aDesiredaccessi; "DesiredAccessIn"
0x18021a5fd  mov     [rbp+3E0h+var_318], rax
0x18021a604  jmp     loc_18021A539
0x18021a609  cmp     byte ptr [rbp+3E0h+var_45C+1], dil
0x18021a60d  jz      short loc_18021A646
0x18021a60f  test    r8b, al
0x18021a612  jnz     short loc_18021A646
0x18021a614  lea     rax, aOnecoreBaseWcp_36; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x18021a61b  mov     [rbp+3E0h+var_438], 70Fh
0x18021a623  mov     qword ptr [rbp+3E0h+var_448], rax
0x18021a627  lea     rdx, [rbp+3E0h+var_448]
0x18021a62b  lea     rax, aWindowsRtlSyst_266; "Windows::Rtl::SystemImplementation::Dir"...
0x18021a632  mov     qword ptr [rbp+3E0h+var_448+8], rax
0x18021a636  lea     rax, aDesiredaccessi; "DesiredAccessIn"
0x18021a63d  mov     [rbp+3E0h+var_430], rax
0x18021a641  jmp     loc_18021A539
0x18021a646  mov     [rbp+3E0h+DesiredAccess], eax
0x18021a64c  bt      eax, 1Ch
0x18021a650  jnb     short loc_18021A661
0x18021a652  btr     eax, 1Ch
0x18021a656  or      eax, 1F01FFh
0x18021a65b  mov     [rbp+3E0h+DesiredAccess], eax
0x18021a661  test    rbx, rbx
0x18021a664  jz      short loc_18021A67C
0x18021a666  test    byte ptr [rbp+3E0h+arg_50], 40h
0x18021a66d  jz      short loc_18021A67C
0x18021a66f  test    al, 20h
0x18021a671  jz      short loc_18021A67C
0x18021a673  and     eax, 0FFFFFFDFh
0x18021a676  mov     [rbp+3E0h+DesiredAccess], eax
0x18021a67c  test    ecx, ecx
0x18021a67e  jz      short loc_18021A68D
0x18021a680  test    al, 40h
0x18021a682  jz      short loc_18021A68D
0x18021a684  and     eax, 0FFFFFFBFh
0x18021a687  mov     [rbp+3E0h+DesiredAccess], eax
0x18021a68d  mov     [rbp+3E0h+var_2B0], rdi
0x18021a694  xorps   xmm0, xmm0
0x18021a697  movdqa  [rbp+3E0h+var_2C0], xmm0
0x18021a69f  xorps   xmm1, xmm1
0x18021a6a2  movdqa  [rbp+3E0h+var_2A0], xmm0
0x18021a6aa  movdqa  [rbp+3E0h+var_290], xmm1
0x18021a6b2  mov     [rbp+3E0h+var_2A8], dil
0x18021a6b9  mov     [rbp+3E0h+var_2A6], di
0x18021a6c0  mov     [rbp+3E0h+var_458], dil
0x18021a6c4  mov     [rbp+3E0h+var_460], dil
0x18021a6c8  movups  xmm0, xmmword ptr [r14]
0x18021a6cc  movups  xmm1, xmmword ptr [r14+10h]
0x18021a6d1  movups  xmmword ptr [rbp+3E0h+ObjectAttributes.Length], xmm0
0x18021a6d5  movups  xmm0, xmmword ptr [r14+20h]
0x18021a6da  movups  xmmword ptr [rbp+3E0h+ObjectAttributes.ObjectName], xmm1
0x18021a6de  movups  xmmword ptr [rbp+3E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18021a6e2  test    dl, dl
0x18021a6e4  jnz     short loc_18021A6F6
0x18021a6e6  test    [rbp+3E0h+var_350], 20000h
0x18021a6f0  jz      loc_18021A822
0x18021a6f6  mov     al, byte ptr [rbp+3E0h+var_45C]
0x18021a6f9  mov     rcx, r15
0x18021a6fc  mov     r9, [rbp+3E0h+ObjectAttributes.ObjectName]
0x18021a700  neg     al
0x18021a702  mov     qword ptr [rsp+5F0h+CreateOptions], rdi
0x18021a707  lea     rax, [rbp+3E0h+var_2C0]
0x18021a70e  mov     qword ptr [rsp+5F0h+CreateDisposition], rax
0x18021a713  sbb     edx, edx
0x18021a715  mov     rax, [rbp+3E0h+ObjectAttributes.SecurityDescriptor]
0x18021a719  and     edx, r8d
0x18021a71c  mov     r8, [rbp+3E0h+ObjectAttributes.RootDirectory]
0x18021a720  add     edx, 1Ah
0x18021a723  mov     qword ptr [rsp+5F0h+ShareAccess], rbx
0x18021a728  mov     qword ptr [rsp+5F0h+FileAttributes], rdi
0x18021a72d  mov     [rsp+5F0h+AllocationSize], rax
0x18021a732  call    ?CalculateSecurityForCreate@IRtlObjectProvider@SystemImplementation@Rtl@Windows@@QEAAJW4CalculateInheritedSecurityFlags@1234@PEAXAEBU_UNICODE_STRING@@11UKtmTransactionInfoPointer@34@PEAVSecurityDescriptor@34@4@Z; Windows::Rtl::SystemImplementation::IRtlObjectProvider::CalculateSecurityForCreate(Windows::Rtl::SystemImplementation::IRtlObjectProvider::CalculateInheritedSecurityFlags,void *,_UNICODE_STRING const &,void *,void *,Windows::Rtl::KtmTransactionInfoPointer,Windows::Rtl::SecurityDescriptor *,Windows::Rtl::SecurityDescriptor *)
0x18021a737  mov     edi, eax
0x18021a739  test    eax, eax
0x18021a73b  jns     short loc_18021A756
0x18021a73d  mov     [rbp+3E0h+var_358], eax
0x18021a743  lea     rcx, [rbp+3E0h+var_2C0]
0x18021a74a  call    ?Close@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAXXZ; Windows::Auto<_SECURITY_DESCRIPTOR>::Close(void)
0x18021a74f  mov     ebx, edi
0x18021a751  jmp     loc_18021B6C1
0x18021a756  mov     eax, 400h
0x18021a75b  test    [rbp+3E0h+var_2A6], ax
0x18021a762  jz      short loc_18021A7B4
0x18021a764  test    dword ptr [rbp+3E0h+var_340], 40000h
0x18021a76e  jnz     short loc_18021A7B0
0x18021a770  lea     rax, aOnecoreBaseWcp_36; "onecore\\base\\wcp\\sil\\ntsystem.cpp"
0x18021a777  mov     [rbp+3E0h+var_3D0], 745h
0x18021a77f  mov     [rbp+3E0h+var_3E0], rax
0x18021a783  lea     rdx, [rbp+3E0h+var_3E0]
0x18021a787  lea     rax, aWindowsRtlSyst_266; "Windows::Rtl::SystemImplementation::Dir"...
0x18021a78e  mov     [rbp+3E0h+var_3D8], rax
0x18021a792  lea     rax, aDesiredaccessi; "DesiredAccessIn"
0x18021a799  mov     [rbp+3E0h+var_3C8], rax
0x18021a79d  lea     rcx, [rbp+3E0h+var_358]
0x18021a7a4  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18021a7a9  mov     ebx, eax
0x18021a7ab  jmp     loc_18021B6B5
0x18021a7b0  mov     [rbp+3E0h+var_458], 1
0x18021a7b4  mov     eax, 800h
0x18021a7b9  test    [rbp+3E0h+var_2A6], ax
  ... truncated ...
```
