# Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName(Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::BufferedPathElement *,Windows::Auto<_UNICODE_STRING> *)

- ea: `0x180158d64`
- end: `0x180159698`
- name: `?GetTempDirectoryName@CBufferedFileSystemProvider@SystemImplementation@Rtl@Windows@@AEAAJPEAUBufferedPathElement@CBufferedFileHierarchy@234@PEAV?$Auto@U_UNICODE_STRING@@@4@@Z`
- size: `2356`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180157db4`

## callees

- `0x1800031d0`
- `0x18000aedc`
- `0x18000e098`
- `0x180048c68`
- `0x180048eac`
- `0x1800497c0`
- `0x180049c6c`
- `0x18004d970`
- `0x18004f310`
- `0x18011c474`
- `0x180127540`
- `0x1801569d4`
- `0x180158d64`
- `0x1801598bc`
- `0x180159ae0`
- `0x1801a59f0`
- `0x1801a5d74`
- `0x1801bd010`

## import_xrefs

- `ntdll!RtlDuplicateUnicodeString` at `0x180158e06`
- `ntdll!RtlDuplicateUnicodeString` at `0x180159534`
- `ntdll!RtlDuplicateUnicodeString` at `0x1801595ed`
- `ntdll!RtlDuplicateUnicodeString` at `0x180158e06`
- `ntdll!RtlDuplicateUnicodeString` at `0x180159534`
- `ntdll!RtlDuplicateUnicodeString` at `0x1801595ed`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180159015`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180159015`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18015909e`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18015909e`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x180159103`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x180159103`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1801590d1`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1801590d1`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180159070`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180159070`

## string_xrefs

- `0x180158e27`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName`
- `0x180159041`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName`
- `0x180159551`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName`
- `0x18015960a`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName`
- `0x180159564`: `RtlDuplicateUnicodeString( 0, ObjectAttributes.ObjectName, TempDirectoryOut.GetMutablePointer())`
- `0x180158e3a`: `RtlDuplicateUnicodeString( 0, m_TempDirectory.GetMutablePointer(), TempDirectory->GetMutablePointer())`
- `0x18015961d`: `RtlDuplicateUnicodeString( 0, m_TempDirectory.GetMutablePointer(), TempDirectory->GetMutablePointer())`
- `0x18015911d`: `RtlSetControlSecurityDescriptor(&SecurityDescriptor, (0x1000), (0x1000))`
- `0x18015902f`: `RtlCreateSecurityDescriptor(&SecurityDescriptor, (1))`
- `0x18015908a`: `RtlSetOwnerSecurityDescriptor(&SecurityDescriptor, TrustedInstaller, 0)`
- `0x1801590b8`: `RtlSetGroupSecurityDescriptor(&SecurityDescriptor, TrustedInstaller, 0)`
- `0x1801590eb`: `RtlSetDaclSecurityDescriptor(&SecurityDescriptor, 1, Acl.GetMutablePointer(), 0)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName(
        __int64 a1,
        __int64 a2,
        struct _UNICODE_STRING *a3)
{
  PWSTR Buffer; // rcx
  __int64 result; // rax
  struct _UNICODE_STRING *v8; // r14
  int v9; // r12d
  NTSTATUS v10; // ebx
  int VolumeSerialNumber; // edi
  void (***v12)(void); // rcx
  void (*v13)(void); // rax
  void (__fastcall ***v14)(_QWORD); // rcx
  int v15; // r15d
  const char *v16; // rax
  void (__fastcall ***v17)(_QWORD); // rcx
  void (__fastcall ***v18)(_QWORD); // rcx
  void (***v19)(void); // rcx
  void (__fastcall ***v20)(_QWORD); // rcx
  struct _UNICODE_STRING v21; // xmm1
  _BYTE v22[8]; // [rsp+88h] [rbp-80h] BYREF
  __int128 v23; // [rsp+90h] [rbp-78h] BYREF
  __int64 v24; // [rsp+A0h] [rbp-68h]
  const char *v25; // [rsp+A8h] [rbp-60h]
  int v26; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v27; // [rsp+B8h] [rbp-50h]
  __int128 v28; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v29; // [rsp+D0h] [rbp-38h]
  __int64 v30; // [rsp+D8h] [rbp-30h]
  __int64 v31; // [rsp+E0h] [rbp-28h]
  const wchar_t *v32; // [rsp+E8h] [rbp-20h]
  __int128 SecurityDescriptor; // [rsp+F0h] [rbp-18h] BYREF
  PCUNICODE_STRING SourceString[2]; // [rsp+100h] [rbp-8h]
  __int128 v35; // [rsp+110h] [rbp+8h]
  __int128 v36; // [rsp+120h] [rbp+18h] BYREF
  __int128 v37; // [rsp+130h] [rbp+28h]
  __int128 v38; // [rsp+140h] [rbp+38h]
  __int128 v39; // [rsp+150h] [rbp+48h] BYREF
  PSID Owner; // [rsp+160h] [rbp+58h] BYREF
  PACL Dacl[2]; // [rsp+168h] [rbp+60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+178h] [rbp+70h] BYREF
  __int128 v43; // [rsp+188h] [rbp+80h] BYREF
  __int64 v44; // [rsp+198h] [rbp+90h]
  __int128 v45; // [rsp+1A0h] [rbp+98h] BYREF
  __int128 v46; // [rsp+1B0h] [rbp+A8h] BYREF

  v27 = -2;
  Buffer = a3->Buffer;
  if ( Buffer )
  {
    if ( a3 )
      anonymous_namespace_::OurRtlFreeStringRoutine(Buffer);
    *a3 = 0;
  }
  v26 = 0;
  result = Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetVolumeSerialNumber(
             a1,
             a2,
             (unsigned int)&v26,
             0,
             0);
  if ( (int)result >= 0 )
  {
    v8 = (struct _UNICODE_STRING *)(a1 + 496);
    v9 = v26;
    if ( *(_QWORD *)(a1 + 504) && *(_DWORD *)(a1 + 512) == v26 )
    {
      v10 = RtlDuplicateUnicodeString(0, (PCUNICODE_STRING)(a1 + 496), a3);
      if ( v10 < 0 )
      {
        *(_QWORD *)&v23 = "onecore\\base\\wcp\\sil\\fs_buffered.cpp";
        *((_QWORD *)&v23 + 1) = "Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName";
        v24 = 3141;
        v25 = "RtlDuplicateUnicodeString( 0, m_TempDirectory.GetMutablePointer(), TempDirectory->GetMutablePointer())";
        RtlReportErrorOrigination(&v23, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v10);
        return (unsigned int)v10;
      }
      return 0;
    }
    DestinationString = 0;
    v23 = 0;
    v24 = 0;
    if ( !*(_DWORD *)(a1 + 212) )
    {
      v36 = 0x30u;
      *((_QWORD *)&v37 + 1) = 64;
      v39 = 0;
      *(_QWORD *)&v37 = &g_UNICODE_STRING__bslash_SystemRoot_bslash_;
      v38 = 0;
      VolumeSerialNumber = Windows::Rtl::SystemImplementation::IRtlFileSystemProvider::SysOpenFile(
                             *(_QWORD *)(a1 + 200),
                             0,
                             &v39,
                             1179785,
                             &v36,
                             7,
                             16417,
                             0,
                             0);
      if ( VolumeSerialNumber < 0
        || (VolumeSerialNumber = Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetVolumeSerialNumber(
                                   a1,
                                   DWORD2(v39),
                                   (int)a1 + 212,
                                   0,
                                   0),
            VolumeSerialNumber < 0) )
      {
        Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v39);
        v12 = (void (***)(void))v39;
        if ( (_QWORD)v39 )
        {
          *(_QWORD *)&v39 = 0;
LABEL_16:
          v13 = **v12;
LABEL_17:
          v13();
        }
LABEL_18:
        if ( DestinationString.Buffer )
          anonymous_namespace_::OurRtlFreeStringRoutine(DestinationString.Buffer);
        return (unsigned int)VolumeSerialNumber;
      }
      Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v39);
      v14 = (void (__fastcall ***)(_QWORD))v39;
      if ( (_QWORD)v39 )
      {
        *(_QWORD *)&v39 = 0;
        (**v14)(v14);
      }
    }
    v15 = *(_DWORD *)(a1 + 212);
    VolumeSerialNumber = RtlInitLUnicodeStringFromUnicodeString(a2 + 96, &v23);
    if ( VolumeSerialNumber < 0 )
      goto LABEL_18;
    v22[0] = 0;
    VolumeSerialNumber = RtlEqualLUnicodeStringPrefix(
                           &v23,
                           g_LUNICODE_STRING__bslash_SystemRoot_bslash_,
                           RtlUpcaseUCSCharacter,
                           v22);
    if ( VolumeSerialNumber < 0 )
      goto LABEL_18;
    if ( v22[0] || v9 == v15 )
    {
      SecurityDescriptor = 0x30u;
      SourceString[1] = (PCUNICODE_STRING)64;
      v45 = 0;
      v39 = 0;
      SourceString[0] = (PCUNICODE_STRING)L"02";
      v35 = 0;
      VolumeSerialNumber = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int128 *, __int64, __int128 *, __int128 *, _QWORD, int, int, int, int, _QWORD, _DWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 200) + 112LL))(
                             *(_QWORD *)(a1 + 200),
                             0,
                             &v39,
                             1179926,
                             &SecurityDescriptor,
                             &v45,
                             0,
                             16,
                             7,
                             3,
                             16417,
                             0,
                             0,
                             0,
                             0);
      if ( VolumeSerialNumber < 0
        || (Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v39),
            SourceString[0] = (PCUNICODE_STRING)L"NP",
            VolumeSerialNumber = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int128 *, __int64, __int128 *, __int128 *, _QWORD, int, int, int, int, _QWORD, _DWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 200) + 112LL))(
                                   *(_QWORD *)(a1 + 200),
                                   0,
                                   &v39,
                                   1179926,
                                   &SecurityDescriptor,
                                   &v45,
                                   0,
                                   16,
                                   7,
                                   3,
                                   16417,
                                   0,
                                   0,
                                   0,
                                   0),
            VolumeSerialNumber < 0) )
      {
        Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v39);
        v19 = (void (***)(void))v39;
        if ( !(_QWORD)v39 )
          goto LABEL_18;
        *(_QWORD *)&v39 = 0;
        v13 = **v19;
        goto LABEL_17;
      }
      VolumeSerialNumber = RtlDuplicateUnicodeString(0, SourceString[0], &DestinationString);
      if ( VolumeSerialNumber < 0 )
      {
        *(_QWORD *)&v23 = "onecore\\base\\wcp\\sil\\fs_buffered.cpp";
        *((_QWORD *)&v23 + 1) = "Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName";
        v24 = 3225;
        v25 = "RtlDuplicateUnicodeString( 0, ObjectAttributes.ObjectName, TempDirectoryOut.GetMutablePointer())";
        RtlReportErrorOrigination(&v23, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)VolumeSerialNumber);
        Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v39);
        v12 = (void (***)(void))v39;
        if ( !(_QWORD)v39 )
          goto LABEL_18;
        *(_QWORD *)&v39 = 0;
        goto LABEL_16;
      }
      Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v39);
      v20 = (void (__fastcall ***)(_QWORD))v39;
      if ( (_QWORD)v39 )
      {
        *(_QWORD *)&v39 = 0;
        (**v20)(v20);
      }
    }
    else
    {
      Owner = 0;
      VolumeSerialNumber = Windows::WCP::Implementation::Rtl::GetTrustedInstallerSid(&Owner);
      if ( VolumeSerialNumber < 0 )
      {
LABEL_28:
        Windows::Auto<_ACL>::Close(&Owner);
        goto LABEL_18;
      }
      Dacl[0] = 0;
      VolumeSerialNumber = Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL(Dacl);
      if ( VolumeSerialNumber < 0 )
      {
LABEL_30:
        Windows::Auto<_ACL>::Close(Dacl);
        goto LABEL_28;
      }
      SecurityDescriptor = 0;
      *(_OWORD *)SourceString = 0;
      *(_QWORD *)&v35 = 0;
      VolumeSerialNumber = RtlCreateSecurityDescriptor(&SecurityDescriptor, 1u);
      if ( VolumeSerialNumber < 0 )
      {
        v24 = 3240;
        v16 = "RtlCreateSecurityDescriptor(&SecurityDescriptor, (1))";
LABEL_33:
        *(_QWORD *)&v23 = "onecore\\base\\wcp\\sil\\fs_buffered.cpp";
        *((_QWORD *)&v23 + 1) = "Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName";
        v25 = v16;
        RtlReportErrorOrigination(&v23, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)VolumeSerialNumber);
        goto LABEL_30;
      }
      VolumeSerialNumber = RtlSetOwnerSecurityDescriptor(&SecurityDescriptor, Owner, 0);
      if ( VolumeSerialNumber < 0 )
      {
        v24 = 3241;
        v16 = "RtlSetOwnerSecurityDescriptor(&SecurityDescriptor, TrustedInstaller, 0)";
        goto LABEL_33;
      }
      VolumeSerialNumber = RtlSetGroupSecurityDescriptor(&SecurityDescriptor, Owner, 0);
      if ( VolumeSerialNumber < 0 )
      {
        v24 = 3242;
        v16 = "RtlSetGroupSecurityDescriptor(&SecurityDescriptor, TrustedInstaller, 0)";
        goto LABEL_33;
      }
      VolumeSerialNumber = RtlSetDaclSecurityDescriptor(&SecurityDescriptor, 1u, Dacl[0], 0);
      if ( VolumeSerialNumber < 0 )
      {
        v24 = 3243;
        v16 = "RtlSetDaclSecurityDescriptor(&SecurityDescriptor, 1, Acl.GetMutablePointer(), 0)";
        goto LABEL_33;
      }
      VolumeSerialNumber = RtlSetControlSecurityDescriptor(&SecurityDescriptor, 0x1000u, 0x1000u);
      if ( VolumeSerialNumber < 0 )
      {
        v24 = 3244;
        v16 = "RtlSetControlSecurityDescriptor(&SecurityDescriptor, (0x1000), (0x1000))";
        goto LABEL_33;
      }
      v36 = 0;
      v37 = 0;
      v38 = 0;
      v39 = 0;
      v46 = 0;
      v43 = 0;
      v44 = 0;
      v23 = 0;
      v24 = 0;
      VolumeSerialNumber = Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetVolumeSerialNumber(
                             a1,
                             a2,
                             (unsigned int)&v26,
                             (unsigned int)&v43,
                             0);
      if ( VolumeSerialNumber < 0 )
        goto LABEL_43;
      v28 = v43;
      v29 = v44;
      v30 = 28;
      v31 = 30;
      v32 = L"$$PendingFiles";
      VolumeSerialNumber = RtlCombineNtPathSegments(2, &v28, &v23);
      if ( VolumeSerialNumber < 0 )
        goto LABEL_43;
      *(_QWORD *)&v45 = &DestinationString;
      VolumeSerialNumber = Windows::StringUtil::Rtl::DuplicateToBackslashTerminatedString<Windows::Auto<_LUNICODE_STRING>,Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>>(
                             &v23,
                             &v45);
      if ( VolumeSerialNumber < 0 )
        goto LABEL_43;
      LODWORD(v36) = 48;
      *((_QWORD *)&v36 + 1) = 0;
      DWORD2(v37) = 64;
      *(_QWORD *)&v37 = &DestinationString;
      *(_QWORD *)&v38 = &SecurityDescriptor;
      *((_QWORD *)&v38 + 1) = 0;
      VolumeSerialNumber = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int128 *, __int64, __int128 *, __int128 *, _QWORD, int, int, int, int, _QWORD, _DWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 200) + 112LL))(
                             *(_QWORD *)(a1 + 200),
                             0,
                             &v39,
                             18743702,
                             &v36,
                             &v46,
                             0,
                             22,
                             7,
                             3,
                             16417,
                             0,
                             0,
                             0,
                             0);
      if ( VolumeSerialNumber < 0
        || (VolumeSerialNumber = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, __int128 *, _QWORD))(**(_QWORD **)(a1 + 200) + 32LL))(
                                   *(_QWORD *)(a1 + 200),
                                   0,
                                   *((_QWORD *)&v39 + 1),
                                   7,
                                   &SecurityDescriptor,
                                   0),
            VolumeSerialNumber < 0) )
      {
LABEL_43:
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v23);
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v43);
        Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v39);
        v17 = (void (__fastcall ***)(_QWORD))v39;
        if ( (_QWORD)v39 )
        {
          *(_QWORD *)&v39 = 0;
          (**v17)(v17);
        }
        goto LABEL_30;
      }
      v15 = v26;
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v23);
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v43);
      Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v39);
      v18 = (void (__fastcall ***)(_QWORD))v39;
      if ( (_QWORD)v39 )
      {
        *(_QWORD *)&v39 = 0;
        (**v18)(v18);
      }
      Windows::Auto<_ACL>::Close(Dacl);
      Windows::Auto<_ACL>::Close(&Owner);
    }
    if ( !DestinationString.Buffer )
    {
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x180159697LL);
    }
    v21 = DestinationString;
    DestinationString = *v8;
    *v8 = v21;
    *(_DWORD *)(a1 + 512) = v15;
    v10 = RtlDuplicateUnicodeString(0, (PCUNICODE_STRING)(a1 + 496), a3);
    if ( v10 < 0 )
    {
      *(_QWORD *)&v23 = "onecore\\base\\wcp\\sil\\fs_buffered.cpp";
      *((_QWORD *)&v23 + 1) = "Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName";
      v24 = 3302;
      v25 = "RtlDuplicateUnicodeString( 0, m_TempDirectory.GetMutablePointer(), TempDirectory->GetMutablePointer())";
      RtlReportErrorOrigination(&v23, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v10);
      if ( DestinationString.Buffer )
        anonymous_namespace_::OurRtlFreeStringRoutine(DestinationString.Buffer);
      return (unsigned int)v10;
    }
    if ( DestinationString.Buffer )
      anonymous_namespace_::OurRtlFreeStringRoutine(DestinationString.Buffer);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180158d64  mov     rax, rsp
0x180158d67  push    rbp
0x180158d68  push    rsi
0x180158d69  push    rdi
0x180158d6a  push    r12
0x180158d6c  push    r13
0x180158d6e  push    r14
0x180158d70  push    r15
0x180158d72  lea     rbp, [rax-0F8h]
0x180158d79  sub     rsp, 1C0h
0x180158d80  mov     [rbp+0F0h+var_140], 0FFFFFFFFFFFFFFFEh
0x180158d88  mov     [rax+20h], rbx
0x180158d8c  mov     rax, cs:__security_cookie
0x180158d93  xor     rax, rsp
0x180158d96  mov     [rbp+0F0h+var_38], rax
0x180158d9d  mov     rsi, r8
0x180158da0  mov     r13, rdx
0x180158da3  mov     rbx, rcx
0x180158da6  mov     rcx, [r8+8]
0x180158daa  xor     edi, edi
0x180158dac  test    rcx, rcx
0x180158daf  jz      short loc_180158DC2
0x180158db1  test    r8, r8
0x180158db4  jz      short loc_180158DBB
0x180158db6  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180158dbb  xorps   xmm0, xmm0
0x180158dbe  movdqu  xmmword ptr [rsi], xmm0
0x180158dc2  mov     [rbp+0F0h+var_148], edi
0x180158dc5  mov     [rsp+1F0h+var_1D0], rdi
0x180158dca  xor     r9d, r9d
0x180158dcd  lea     r8, [rbp+0F0h+var_148]
0x180158dd1  mov     rdx, r13
0x180158dd4  mov     rcx, rbx
0x180158dd7  call    ?GetVolumeSerialNumber@CBufferedFileSystemProvider@SystemImplementation@Rtl@Windows@@AEAAJPEAUBufferedPathElement@CBufferedFileHierarchy@234@PEAKPEAV?$Auto@U_LUNICODE_STRING@@@4@2@Z; Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetVolumeSerialNumber(Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::BufferedPathElement *,ulong *,Windows::Auto<_LUNICODE_STRING> *,Windows::Auto<_LUNICODE_STRING> *)
0x180158ddc  test    eax, eax
0x180158dde  js      loc_180159662
0x180158de4  lea     r14, [rbx+1F0h]
0x180158deb  mov     r12d, [rbp+0F0h+var_148]
0x180158def  cmp     [r14+8], rdi
0x180158df3  jz      short loc_180158E5F
0x180158df5  cmp     [rbx+200h], r12d
0x180158dfc  jnz     short loc_180158E5F
0x180158dfe  mov     r8, rsi; DestinationString
0x180158e01  mov     rdx, r14; SourceString
0x180158e04  xor     ecx, ecx; Flags
0x180158e06  call    cs:__imp_RtlDuplicateUnicodeString
0x180158e0d  nop     dword ptr [rax+rax+00h]
0x180158e12  mov     ebx, eax
0x180158e14  test    eax, eax
0x180158e16  jns     loc_180159660
0x180158e1c  lea     rcx, aOnecoreBaseWcp_26; "onecore\\base\\wcp\\sil\\fs_buffered.cp"...
0x180158e23  mov     qword ptr [rbp+0F0h+var_168], rcx
0x180158e27  lea     rcx, aWindowsRtlSyst_177; "Windows::Rtl::SystemImplementation::CBu"...
0x180158e2e  mov     qword ptr [rbp+0F0h+var_168+8], rcx
0x180158e32  mov     [rbp+0F0h+var_158], 0C45h
0x180158e3a  lea     rax, aRtlduplicateun_2; "RtlDuplicateUnicodeString( 0, m_TempDir"...
0x180158e41  mov     [rbp+0F0h+var_150], rax
0x180158e45  mov     r8d, ebx
0x180158e48  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180158e4f  lea     rcx, [rbp+0F0h+var_168]
0x180158e53  call    RtlReportErrorOrigination
0x180158e58  mov     eax, ebx
0x180158e5a  jmp     loc_180159662
0x180158e5f  xorps   xmm0, xmm0
0x180158e62  movups  xmmword ptr [rbp+0F0h+DestinationString.Length], xmm0
0x180158e66  xorps   xmm1, xmm1
0x180158e69  xor     eax, eax
0x180158e6b  movups  [rbp+0F0h+var_168], xmm1
0x180158e6f  mov     [rbp+0F0h+var_158], rax
0x180158e73  lea     r15, [rbx+0D4h]
0x180158e7a  cmp     [r15], edi
0x180158e7d  jnz     loc_180158F6D
0x180158e83  mov     qword ptr [rbp+0F0h+var_D8], 30h ; '0'
0x180158e8b  mov     qword ptr [rbp+0F0h+var_C8+8], 40h ; '@'
0x180158e93  movdqu  [rbp+0F0h+var_A8], xmm0
0x180158e98  mov     qword ptr [rbp+0F0h+var_D8+8], rdi
0x180158e9c  lea     rax, g_UNICODE_STRING__bslash_SystemRoot_bslash_
0x180158ea3  mov     qword ptr [rbp+0F0h+var_C8], rax
0x180158ea7  movdqu  [rbp+0F0h+var_B8], xmm0
0x180158eac  mov     qword ptr [rsp+1F0h+var_1B0], rdi
0x180158eb1  mov     [rsp+1F0h+var_1B8], rdi
0x180158eb6  mov     dword ptr [rsp+1F0h+var_1C0], 4021h
0x180158ebe  mov     dword ptr [rsp+1F0h+var_1C8], 7
0x180158ec6  lea     rax, [rbp+0F0h+var_D8]
0x180158eca  mov     [rsp+1F0h+var_1D0], rax
0x180158ecf  mov     r9d, 120089h
0x180158ed5  lea     r8, [rbp+0F0h+var_A8]
0x180158ed9  xor     edx, edx
0x180158edb  mov     rcx, [rbx+0C8h]
0x180158ee2  call    ?SysOpenFile@IRtlFileSystemProvider@SystemImplementation@Rtl@Windows@@QEAAJKPEAVCSilHandle@234@KAEAU_OBJECT_ATTRIBUTES@@KKUKtmTransactionInfoPointer@34@PEAK@Z; Windows::Rtl::SystemImplementation::IRtlFileSystemProvider::SysOpenFile(ulong,Windows::Rtl::SystemImplementation::CSilHandle *,ulong,_OBJECT_ATTRIBUTES &,ulong,ulong,Windows::Rtl::KtmTransactionInfoPointer,ulong *)
0x180158ee7  mov     edi, eax
0x180158ee9  test    eax, eax
0x180158eeb  js      short loc_180158F0E
0x180158eed  mov     [rsp+1F0h+var_1D0], 0
0x180158ef6  xor     r9d, r9d
0x180158ef9  mov     r8, r15
0x180158efc  mov     rdx, qword ptr [rbp+0F0h+var_A8+8]
0x180158f00  mov     rcx, rbx
0x180158f03  call    ?GetVolumeSerialNumber@CBufferedFileSystemProvider@SystemImplementation@Rtl@Windows@@AEAAJPEAXPEAKPEAV?$Auto@U_LUNICODE_STRING@@@4@2@Z; Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetVolumeSerialNumber(void *,ulong *,Windows::Auto<_LUNICODE_STRING> *,Windows::Auto<_LUNICODE_STRING> *)
0x180158f08  mov     edi, eax
0x180158f0a  test    eax, eax
0x180158f0c  jns     short loc_180158F48
0x180158f0e  lea     rcx, [rbp+0F0h+var_A8]; this
0x180158f12  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x180158f17  mov     rcx, qword ptr [rbp+0F0h+var_A8]
0x180158f1b  test    rcx, rcx
0x180158f1e  jz      short loc_180158F33
0x180158f20  mov     qword ptr [rbp+0F0h+var_A8], 0
0x180158f28  mov     rax, [rcx]
0x180158f2b  mov     rax, [rax]
0x180158f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180158f33  mov     rcx, [rbp+0F0h+DestinationString.Buffer]
0x180158f37  test    rcx, rcx
0x180158f3a  jz      short loc_180158F41
0x180158f3c  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180158f41  mov     eax, edi
0x180158f43  jmp     loc_180159662
0x180158f48  lea     rcx, [rbp+0F0h+var_A8]; this
0x180158f4c  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x180158f51  mov     rcx, qword ptr [rbp+0F0h+var_A8]
0x180158f55  test    rcx, rcx
0x180158f58  jz      short loc_180158F6D
0x180158f5a  mov     qword ptr [rbp+0F0h+var_A8], 0
0x180158f62  mov     rax, [rcx]
0x180158f65  mov     rax, [rax]
0x180158f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180158f6d  mov     r15d, [r15]
0x180158f70  lea     rcx, [r13+60h]
0x180158f74  lea     rdx, [rbp+0F0h+var_168]
0x180158f78  call    RtlInitLUnicodeStringFromUnicodeString
0x180158f7d  mov     edi, eax
0x180158f7f  test    eax, eax
0x180158f81  js      short loc_180158F33
0x180158f83  mov     [rbp+0F0h+var_170], 0
0x180158f87  lea     r9, [rbp+0F0h+var_170]
0x180158f8b  lea     r8, RtlUpcaseUCSCharacter
0x180158f92  lea     rdx, g_LUNICODE_STRING__bslash_SystemRoot_bslash_
0x180158f99  lea     rcx, [rbp+0F0h+var_168]
0x180158f9d  call    RtlEqualLUnicodeStringPrefix
0x180158fa2  mov     edi, eax
0x180158fa4  test    eax, eax
0x180158fa6  js      short loc_180158F33
0x180158fa8  cmp     [rbp+0F0h+var_170], 0
0x180158fac  jnz     loc_1801593C2
0x180158fb2  cmp     r12d, r15d
0x180158fb5  jz      loc_1801593C2
0x180158fbb  xor     r12d, r12d
0x180158fbe  mov     [rbp+0F0h+Owner], r12
0x180158fc2  lea     rcx, [rbp+0F0h+Owner]
0x180158fc6  call    ?GetTrustedInstallerSid@Rtl@Implementation@WCP@Windows@@YAJPEAV?$Auto@U_SID@@@4@@Z; Windows::WCP::Implementation::Rtl::GetTrustedInstallerSid(Windows::Auto<_SID> *)
0x180158fcb  mov     edi, eax
0x180158fcd  test    eax, eax
0x180158fcf  jns     short loc_180158FDF
0x180158fd1  lea     rcx, [rbp+0F0h+Owner]
0x180158fd5  call    ?Close@?$Auto@U_ACL@@@Windows@@QEAAXXZ; Windows::Auto<_ACL>::Close(void)
0x180158fda  jmp     loc_180158F33
0x180158fdf  mov     [rbp+0F0h+Dacl], r12
0x180158fe3  lea     rcx, [rbp+0F0h+Dacl]
0x180158fe7  call    ?GetDefaultWRPLeafDirDACL@Rtl@Implementation@WCP@Windows@@YAJPEAV?$Auto@U_ACL@@@4@@Z; Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL(Windows::Auto<_ACL> *)
0x180158fec  mov     edi, eax
0x180158fee  test    eax, eax
0x180158ff0  jns     short loc_180158FFD
0x180158ff2  lea     rcx, [rbp+0F0h+Dacl]
0x180158ff6  call    ?Close@?$Auto@U_ACL@@@Windows@@QEAAXXZ; Windows::Auto<_ACL>::Close(void)
0x180158ffb  jmp     short loc_180158FD1
0x180158ffd  xorps   xmm0, xmm0
0x180159000  xor     eax, eax
0x180159002  movups  [rbp+0F0h+SecurityDescriptor], xmm0
0x180159006  movups  xmmword ptr [rbp+0F0h+SourceString], xmm0
0x18015900a  mov     qword ptr [rbp+0F0h+var_E8], rax
0x18015900e  lea     edx, [rax+1]; Revision
0x180159011  lea     rcx, [rbp+0F0h+SecurityDescriptor]; SecurityDescriptor
0x180159015  call    cs:__imp_RtlCreateSecurityDescriptor
0x18015901c  nop     dword ptr [rax+rax+00h]
0x180159021  mov     edi, eax
0x180159023  test    eax, eax
0x180159025  jns     short loc_180159065
0x180159027  mov     [rbp+0F0h+var_158], 0CA8h
0x18015902f  lea     rax, aRtlcreatesecur_0; "RtlCreateSecurityDescriptor(&SecurityDe"...
0x180159036  lea     rcx, aOnecoreBaseWcp_26; "onecore\\base\\wcp\\sil\\fs_buffered.cp"...
0x18015903d  mov     qword ptr [rbp+0F0h+var_168], rcx
0x180159041  lea     rcx, aWindowsRtlSyst_177; "Windows::Rtl::SystemImplementation::CBu"...
0x180159048  mov     qword ptr [rbp+0F0h+var_168+8], rcx
0x18015904c  mov     [rbp+0F0h+var_150], rax
0x180159050  mov     r8d, edi
0x180159053  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18015905a  lea     rcx, [rbp+0F0h+var_168]
0x18015905e  call    RtlReportErrorOrigination
0x180159063  jmp     short loc_180158FF2
0x180159065  xor     r8d, r8d; OwnerDefaulted
0x180159068  mov     rdx, [rbp+0F0h+Owner]; Owner
0x18015906c  lea     rcx, [rbp+0F0h+SecurityDescriptor]; SecurityDescriptor
0x180159070  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x180159077  nop     dword ptr [rax+rax+00h]
0x18015907c  mov     edi, eax
0x18015907e  test    eax, eax
0x180159080  jns     short loc_180159093
0x180159082  mov     [rbp+0F0h+var_158], 0CA9h
0x18015908a  lea     rax, aRtlsetownersec; "RtlSetOwnerSecurityDescriptor(&Security"...
0x180159091  jmp     short loc_180159036
0x180159093  xor     r8d, r8d; GroupDefaulted
0x180159096  mov     rdx, [rbp+0F0h+Owner]; Group
0x18015909a  lea     rcx, [rbp+0F0h+SecurityDescriptor]; SecurityDescriptor
0x18015909e  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x1801590a5  nop     dword ptr [rax+rax+00h]
0x1801590aa  mov     edi, eax
0x1801590ac  test    eax, eax
0x1801590ae  jns     short loc_1801590C4
0x1801590b0  mov     [rbp+0F0h+var_158], 0CAAh
0x1801590b8  lea     rax, aRtlsetgroupsec_0; "RtlSetGroupSecurityDescriptor(&Security"...
0x1801590bf  jmp     loc_180159036
0x1801590c4  xor     r9d, r9d; DaclDefaulted
0x1801590c7  mov     r8, [rbp+0F0h+Dacl]; Dacl
0x1801590cb  mov     dl, 1; DaclPresent
0x1801590cd  lea     rcx, [rbp+0F0h+SecurityDescriptor]; SecurityDescriptor
0x1801590d1  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1801590d8  nop     dword ptr [rax+rax+00h]
0x1801590dd  mov     edi, eax
0x1801590df  test    eax, eax
0x1801590e1  jns     short loc_1801590F7
0x1801590e3  mov     [rbp+0F0h+var_158], 0CABh
0x1801590eb  lea     rax, aRtlsetdaclsecu; "RtlSetDaclSecurityDescriptor(&SecurityD"...
0x1801590f2  jmp     loc_180159036
0x1801590f7  mov     edx, 1000h; ControlBitsOfInterest
0x1801590fc  mov     r8d, edx; ControlBitsToSet
0x1801590ff  lea     rcx, [rbp+0F0h+SecurityDescriptor]; SecurityDescriptor
0x180159103  call    cs:__imp_RtlSetControlSecurityDescriptor
0x18015910a  nop     dword ptr [rax+rax+00h]
0x18015910f  mov     edi, eax
0x180159111  test    eax, eax
0x180159113  jns     short loc_180159129
0x180159115  mov     [rbp+0F0h+var_158], 0CACh
0x18015911d  lea     rax, aRtlsetcontrols_0; "RtlSetControlSecurityDescriptor(&Securi"...
0x180159124  jmp     loc_180159036
0x180159129  xorps   xmm0, xmm0
0x18015912c  movups  [rbp+0F0h+var_D8], xmm0
0x180159130  movups  [rbp+0F0h+var_C8], xmm0
0x180159134  movups  [rbp+0F0h+var_B8], xmm0
0x180159138  movdqu  [rbp+0F0h+var_A8], xmm0
0x18015913d  movups  [rbp+0F0h+var_48], xmm0
0x180159144  xorps   xmm1, xmm1
0x180159147  xor     eax, eax
0x180159149  movups  [rbp+0F0h+var_70], xmm1
0x180159150  mov     [rbp+0F0h+var_60], rax
0x180159157  movups  [rbp+0F0h+var_168], xmm0
0x18015915b  mov     [rbp+0F0h+var_158], rax
0x18015915f  mov     [rsp+1F0h+var_1D0], r12
0x180159164  lea     r9, [rbp+0F0h+var_70]
0x18015916b  lea     r8, [rbp+0F0h+var_148]
0x18015916f  mov     rdx, r13
0x180159172  mov     rcx, rbx
0x180159175  call    ?GetVolumeSerialNumber@CBufferedFileSystemProvider@SystemImplementation@Rtl@Windows@@AEAAJPEAUBufferedPathElement@CBufferedFileHierarchy@234@PEAKPEAV?$Auto@U_LUNICODE_STRING@@@4@2@Z; Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetVolumeSerialNumber(Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::BufferedPathElement *,ulong *,Windows::Auto<_LUNICODE_STRING> *,Windows::Auto<_LUNICODE_STRING> *)
0x18015917a  mov     edi, eax
0x18015917c  test    eax, eax
0x18015917e  jns     short loc_1801591C1
0x180159180  lea     rcx, [rbp+0F0h+var_168]
0x180159184  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180159189  nop
0x18015918a  lea     rcx, [rbp+0F0h+var_70]
0x180159191  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180159196  nop
0x180159197  lea     rcx, [rbp+0F0h+var_A8]; this
0x18015919b  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x1801591a0  mov     rcx, qword ptr [rbp+0F0h+var_A8]
0x1801591a4  test    rcx, rcx
0x1801591a7  jz      loc_180158FF2
0x1801591ad  mov     qword ptr [rbp+0F0h+var_A8], r12
0x1801591b1  mov     rax, [rcx]
0x1801591b4  mov     rax, [rax]
0x1801591b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801591bc  jmp     loc_180158FF2
0x1801591c1  movups  xmm0, [rbp+0F0h+var_70]
0x1801591c8  movups  [rbp+0F0h+var_138], xmm0
0x1801591cc  movsd   xmm1, [rbp+0F0h+var_60]
0x1801591d4  movsd   [rbp+0F0h+var_128], xmm1
0x1801591d9  mov     [rbp+0F0h+var_120], 1Ch
0x1801591e1  mov     [rbp+0F0h+var_118], 1Eh
0x1801591e9  lea     rax, aPendingfiles; "$$PendingFiles"
0x1801591f0  mov     [rbp+0F0h+var_110], rax
0x1801591f4  lea     r8, [rbp+0F0h+var_168]
0x1801591f8  lea     rdx, [rbp+0F0h+var_138]
0x1801591fc  mov     ecx, 2
0x180159201  call    RtlCombineNtPathSegments
0x180159206  mov     edi, eax
0x180159208  test    eax, eax
0x18015920a  jns     short loc_180159228
0x18015920c  lea     rcx, [rbp+0F0h+var_168]
0x180159210  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180159215  nop
0x180159216  lea     rcx, [rbp+0F0h+var_70]
0x18015921d  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180159222  nop
0x180159223  jmp     loc_180159197
0x180159228  lea     rax, [rbp+0F0h+DestinationString]
0x18015922c  mov     qword ptr [rbp+0F0h+var_58], rax
0x180159233  lea     rdx, [rbp+0F0h+var_58]
0x18015923a  lea     rcx, [rbp+0F0h+var_168]
0x18015923e  call    ??$DuplicateToBackslashTerminatedString@V?$Auto@U_LUNICODE_STRING@@@Windows@@V?$AutoOperatorAmpersandHelper@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@2@@Rtl@StringUtil@Windows@@YAJAEBV?$Auto@U_LUNICODE_STRING@@@2@V?$AutoOperatorAmpersandHelper@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@2@@Z; Windows::StringUtil::Rtl::DuplicateToBackslashTerminatedString<Windows::Auto<_LUNICODE_STRING>,Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>>(Windows::Auto<_LUNICODE_STRING> const &,Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>)
0x180159243  mov     edi, eax
0x180159245  test    eax, eax
  ... truncated ...
```
