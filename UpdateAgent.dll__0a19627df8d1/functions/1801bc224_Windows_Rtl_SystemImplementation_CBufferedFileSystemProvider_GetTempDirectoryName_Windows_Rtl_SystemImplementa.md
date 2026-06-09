# Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName(Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::BufferedPathElement *,Windows::Auto<_UNICODE_STRING> *)

- ea: `0x1801bc224`
- end: `0x1801bcb58`
- name: `?GetTempDirectoryName@CBufferedFileSystemProvider@SystemImplementation@Rtl@Windows@@AEAAJPEAUBufferedPathElement@CBufferedFileHierarchy@234@PEAV?$Auto@U_UNICODE_STRING@@@4@@Z`
- size: `2356`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801bb274`

## callees

- `0x1800059d0`
- `0x180022940`
- `0x1800692fc`
- `0x18017f6c4`
- `0x18018a830`
- `0x1801b9e90`
- `0x1801bc224`
- `0x1801bcd7c`
- `0x1801bcfa0`
- `0x1801ee020`
- `0x1801ee264`
- `0x1801efdc0`
- `0x1801f01e4`
- `0x1801f250c`
- `0x1801f3840`
- `0x1801f9370`
- `0x1801f978c`
- `0x1802b1010`

## import_xrefs

- `ntdll!RtlDuplicateUnicodeString` at `0x1801bc2c6`
- `ntdll!RtlDuplicateUnicodeString` at `0x1801bc9f4`
- `ntdll!RtlDuplicateUnicodeString` at `0x1801bcaad`
- `ntdll!RtlDuplicateUnicodeString` at `0x1801bc2c6`
- `ntdll!RtlDuplicateUnicodeString` at `0x1801bc9f4`
- `ntdll!RtlDuplicateUnicodeString` at `0x1801bcaad`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1801bc530`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1801bc530`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1801bc591`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1801bc591`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x1801bc5c3`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x1801bc5c3`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x1801bc55e`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x1801bc55e`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1801bc4d5`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1801bc4d5`

## string_xrefs

- `0x1801bc2fa`: `RtlDuplicateUnicodeString( 0, m_TempDirectory.GetMutablePointer(), TempDirectory->GetMutablePointer())`
- `0x1801bcadd`: `RtlDuplicateUnicodeString( 0, m_TempDirectory.GetMutablePointer(), TempDirectory->GetMutablePointer())`
- `0x1801bc2e7`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName`
- `0x1801bc501`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName`
- `0x1801bca11`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName`
- `0x1801bcaca`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName`
- `0x1801bc4ef`: `RtlCreateSecurityDescriptor(&SecurityDescriptor, (1))`
- `0x1801bca24`: `RtlDuplicateUnicodeString( 0, ObjectAttributes.ObjectName, TempDirectoryOut.GetMutablePointer())`
- `0x1801bc5dd`: `RtlSetControlSecurityDescriptor(&SecurityDescriptor, (0x1000), (0x1000))`
- `0x1801bc5ab`: `RtlSetDaclSecurityDescriptor(&SecurityDescriptor, 1, Acl.GetMutablePointer(), 0)`
- `0x1801bc578`: `RtlSetGroupSecurityDescriptor(&SecurityDescriptor, TrustedInstaller, 0)`
- `0x1801bc54a`: `RtlSetOwnerSecurityDescriptor(&SecurityDescriptor, TrustedInstaller, 0)`

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
      JUMPOUT(0x1801BCB57LL);
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
0x1801bc224  mov     rax, rsp
0x1801bc227  push    rbp
0x1801bc228  push    rsi
0x1801bc229  push    rdi
0x1801bc22a  push    r12
0x1801bc22c  push    r13
0x1801bc22e  push    r14
0x1801bc230  push    r15
0x1801bc232  lea     rbp, [rax-0F8h]
0x1801bc239  sub     rsp, 1C0h
0x1801bc240  mov     [rbp+0F0h+var_140], 0FFFFFFFFFFFFFFFEh
0x1801bc248  mov     [rax+20h], rbx
0x1801bc24c  mov     rax, cs:__security_cookie
0x1801bc253  xor     rax, rsp
0x1801bc256  mov     [rbp+0F0h+var_38], rax
0x1801bc25d  mov     rsi, r8
0x1801bc260  mov     r13, rdx
0x1801bc263  mov     rbx, rcx
0x1801bc266  mov     rcx, [r8+8]
0x1801bc26a  xor     edi, edi
0x1801bc26c  test    rcx, rcx
0x1801bc26f  jz      short loc_1801BC282
0x1801bc271  test    r8, r8
0x1801bc274  jz      short loc_1801BC27B
0x1801bc276  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1801bc27b  xorps   xmm0, xmm0
0x1801bc27e  movdqu  xmmword ptr [rsi], xmm0
0x1801bc282  mov     [rbp+0F0h+var_148], edi
0x1801bc285  mov     [rsp+1F0h+var_1D0], rdi
0x1801bc28a  xor     r9d, r9d
0x1801bc28d  lea     r8, [rbp+0F0h+var_148]
0x1801bc291  mov     rdx, r13
0x1801bc294  mov     rcx, rbx
0x1801bc297  call    ?GetVolumeSerialNumber@CBufferedFileSystemProvider@SystemImplementation@Rtl@Windows@@AEAAJPEAUBufferedPathElement@CBufferedFileHierarchy@234@PEAKPEAV?$Auto@U_LUNICODE_STRING@@@4@2@Z; Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetVolumeSerialNumber(Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::BufferedPathElement *,ulong *,Windows::Auto<_LUNICODE_STRING> *,Windows::Auto<_LUNICODE_STRING> *)
0x1801bc29c  test    eax, eax
0x1801bc29e  js      loc_1801BCB22
0x1801bc2a4  lea     r14, [rbx+1F0h]
0x1801bc2ab  mov     r12d, [rbp+0F0h+var_148]
0x1801bc2af  cmp     [r14+8], rdi
0x1801bc2b3  jz      short loc_1801BC31F
0x1801bc2b5  cmp     [rbx+200h], r12d
0x1801bc2bc  jnz     short loc_1801BC31F
0x1801bc2be  mov     r8, rsi; DestinationString
0x1801bc2c1  mov     rdx, r14; SourceString
0x1801bc2c4  xor     ecx, ecx; Flags
0x1801bc2c6  call    cs:__imp_RtlDuplicateUnicodeString
0x1801bc2cd  nop     dword ptr [rax+rax+00h]
0x1801bc2d2  mov     ebx, eax
0x1801bc2d4  test    eax, eax
0x1801bc2d6  jns     loc_1801BCB20
0x1801bc2dc  lea     rcx, aOnecoreBaseWcp_26; "onecore\\base\\wcp\\sil\\fs_buffered.cp"...
0x1801bc2e3  mov     qword ptr [rbp+0F0h+var_168], rcx
0x1801bc2e7  lea     rcx, aWindowsRtlSyst_177; "Windows::Rtl::SystemImplementation::CBu"...
0x1801bc2ee  mov     qword ptr [rbp+0F0h+var_168+8], rcx
0x1801bc2f2  mov     [rbp+0F0h+var_158], 0C45h
0x1801bc2fa  lea     rax, aRtlduplicateun_2; "RtlDuplicateUnicodeString( 0, m_TempDir"...
0x1801bc301  mov     [rbp+0F0h+var_150], rax
0x1801bc305  mov     r8d, ebx
0x1801bc308  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801bc30f  lea     rcx, [rbp+0F0h+var_168]
0x1801bc313  call    RtlReportErrorOrigination
0x1801bc318  mov     eax, ebx
0x1801bc31a  jmp     loc_1801BCB22
0x1801bc31f  xorps   xmm0, xmm0
0x1801bc322  movups  xmmword ptr [rbp+0F0h+DestinationString.Length], xmm0
0x1801bc326  xorps   xmm1, xmm1
0x1801bc329  xor     eax, eax
0x1801bc32b  movups  [rbp+0F0h+var_168], xmm1
0x1801bc32f  mov     [rbp+0F0h+var_158], rax
0x1801bc333  lea     r15, [rbx+0D4h]
0x1801bc33a  cmp     [r15], edi
0x1801bc33d  jnz     loc_1801BC42D
0x1801bc343  mov     qword ptr [rbp+0F0h+var_D8], 30h ; '0'
0x1801bc34b  mov     qword ptr [rbp+0F0h+var_C8+8], 40h ; '@'
0x1801bc353  movdqu  [rbp+0F0h+var_A8], xmm0
0x1801bc358  mov     qword ptr [rbp+0F0h+var_D8+8], rdi
0x1801bc35c  lea     rax, g_UNICODE_STRING__bslash_SystemRoot_bslash_
0x1801bc363  mov     qword ptr [rbp+0F0h+var_C8], rax
0x1801bc367  movdqu  [rbp+0F0h+var_B8], xmm0
0x1801bc36c  mov     qword ptr [rsp+1F0h+var_1B0], rdi
0x1801bc371  mov     [rsp+1F0h+var_1B8], rdi
0x1801bc376  mov     dword ptr [rsp+1F0h+var_1C0], 4021h
0x1801bc37e  mov     dword ptr [rsp+1F0h+var_1C8], 7
0x1801bc386  lea     rax, [rbp+0F0h+var_D8]
0x1801bc38a  mov     [rsp+1F0h+var_1D0], rax
0x1801bc38f  mov     r9d, 120089h
0x1801bc395  lea     r8, [rbp+0F0h+var_A8]
0x1801bc399  xor     edx, edx
0x1801bc39b  mov     rcx, [rbx+0C8h]
0x1801bc3a2  call    ?SysOpenFile@IRtlFileSystemProvider@SystemImplementation@Rtl@Windows@@QEAAJKPEAVCSilHandle@234@KAEAU_OBJECT_ATTRIBUTES@@KKUKtmTransactionInfoPointer@34@PEAK@Z; Windows::Rtl::SystemImplementation::IRtlFileSystemProvider::SysOpenFile(ulong,Windows::Rtl::SystemImplementation::CSilHandle *,ulong,_OBJECT_ATTRIBUTES &,ulong,ulong,Windows::Rtl::KtmTransactionInfoPointer,ulong *)
0x1801bc3a7  mov     edi, eax
0x1801bc3a9  test    eax, eax
0x1801bc3ab  js      short loc_1801BC3CE
0x1801bc3ad  mov     [rsp+1F0h+var_1D0], 0
0x1801bc3b6  xor     r9d, r9d
0x1801bc3b9  mov     r8, r15
0x1801bc3bc  mov     rdx, qword ptr [rbp+0F0h+var_A8+8]
0x1801bc3c0  mov     rcx, rbx
0x1801bc3c3  call    ?GetVolumeSerialNumber@CBufferedFileSystemProvider@SystemImplementation@Rtl@Windows@@AEAAJPEAXPEAKPEAV?$Auto@U_LUNICODE_STRING@@@4@2@Z; Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetVolumeSerialNumber(void *,ulong *,Windows::Auto<_LUNICODE_STRING> *,Windows::Auto<_LUNICODE_STRING> *)
0x1801bc3c8  mov     edi, eax
0x1801bc3ca  test    eax, eax
0x1801bc3cc  jns     short loc_1801BC408
0x1801bc3ce  lea     rcx, [rbp+0F0h+var_A8]; this
0x1801bc3d2  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x1801bc3d7  mov     rcx, qword ptr [rbp+0F0h+var_A8]
0x1801bc3db  test    rcx, rcx
0x1801bc3de  jz      short loc_1801BC3F3
0x1801bc3e0  mov     qword ptr [rbp+0F0h+var_A8], 0
0x1801bc3e8  mov     rax, [rcx]
0x1801bc3eb  mov     rax, [rax]
0x1801bc3ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc3f3  mov     rcx, [rbp+0F0h+DestinationString.Buffer]
0x1801bc3f7  test    rcx, rcx
0x1801bc3fa  jz      short loc_1801BC401
0x1801bc3fc  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1801bc401  mov     eax, edi
0x1801bc403  jmp     loc_1801BCB22
0x1801bc408  lea     rcx, [rbp+0F0h+var_A8]; this
0x1801bc40c  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x1801bc411  mov     rcx, qword ptr [rbp+0F0h+var_A8]
0x1801bc415  test    rcx, rcx
0x1801bc418  jz      short loc_1801BC42D
0x1801bc41a  mov     qword ptr [rbp+0F0h+var_A8], 0
0x1801bc422  mov     rax, [rcx]
0x1801bc425  mov     rax, [rax]
0x1801bc428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc42d  mov     r15d, [r15]
0x1801bc430  lea     rcx, [r13+60h]
0x1801bc434  lea     rdx, [rbp+0F0h+var_168]
0x1801bc438  call    RtlInitLUnicodeStringFromUnicodeString
0x1801bc43d  mov     edi, eax
0x1801bc43f  test    eax, eax
0x1801bc441  js      short loc_1801BC3F3
0x1801bc443  mov     [rbp+0F0h+var_170], 0
0x1801bc447  lea     r9, [rbp+0F0h+var_170]
0x1801bc44b  lea     r8, RtlUpcaseUCSCharacter
0x1801bc452  lea     rdx, g_LUNICODE_STRING__bslash_SystemRoot_bslash_
0x1801bc459  lea     rcx, [rbp+0F0h+var_168]
0x1801bc45d  call    RtlEqualLUnicodeStringPrefix
0x1801bc462  mov     edi, eax
0x1801bc464  test    eax, eax
0x1801bc466  js      short loc_1801BC3F3
0x1801bc468  cmp     [rbp+0F0h+var_170], 0
0x1801bc46c  jnz     loc_1801BC882
0x1801bc472  cmp     r12d, r15d
0x1801bc475  jz      loc_1801BC882
0x1801bc47b  xor     r12d, r12d
0x1801bc47e  mov     [rbp+0F0h+Owner], r12
0x1801bc482  lea     rcx, [rbp+0F0h+Owner]
0x1801bc486  call    ?GetTrustedInstallerSid@Rtl@Implementation@WCP@Windows@@YAJPEAV?$Auto@U_SID@@@4@@Z; Windows::WCP::Implementation::Rtl::GetTrustedInstallerSid(Windows::Auto<_SID> *)
0x1801bc48b  mov     edi, eax
0x1801bc48d  test    eax, eax
0x1801bc48f  jns     short loc_1801BC49F
0x1801bc491  lea     rcx, [rbp+0F0h+Owner]
0x1801bc495  call    ?Close@?$Auto@U_ACL@@@Windows@@QEAAXXZ; Windows::Auto<_ACL>::Close(void)
0x1801bc49a  jmp     loc_1801BC3F3
0x1801bc49f  mov     [rbp+0F0h+Dacl], r12
0x1801bc4a3  lea     rcx, [rbp+0F0h+Dacl]
0x1801bc4a7  call    ?GetDefaultWRPLeafDirDACL@Rtl@Implementation@WCP@Windows@@YAJPEAV?$Auto@U_ACL@@@4@@Z; Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL(Windows::Auto<_ACL> *)
0x1801bc4ac  mov     edi, eax
0x1801bc4ae  test    eax, eax
0x1801bc4b0  jns     short loc_1801BC4BD
0x1801bc4b2  lea     rcx, [rbp+0F0h+Dacl]
0x1801bc4b6  call    ?Close@?$Auto@U_ACL@@@Windows@@QEAAXXZ; Windows::Auto<_ACL>::Close(void)
0x1801bc4bb  jmp     short loc_1801BC491
0x1801bc4bd  xorps   xmm0, xmm0
0x1801bc4c0  xor     eax, eax
0x1801bc4c2  movups  [rbp+0F0h+SecurityDescriptor], xmm0
0x1801bc4c6  movups  xmmword ptr [rbp+0F0h+SourceString], xmm0
0x1801bc4ca  mov     qword ptr [rbp+0F0h+var_E8], rax
0x1801bc4ce  lea     edx, [rax+1]; Revision
0x1801bc4d1  lea     rcx, [rbp+0F0h+SecurityDescriptor]; SecurityDescriptor
0x1801bc4d5  call    cs:__imp_RtlCreateSecurityDescriptor
0x1801bc4dc  nop     dword ptr [rax+rax+00h]
0x1801bc4e1  mov     edi, eax
0x1801bc4e3  test    eax, eax
0x1801bc4e5  jns     short loc_1801BC525
0x1801bc4e7  mov     [rbp+0F0h+var_158], 0CA8h
0x1801bc4ef  lea     rax, aRtlcreatesecur_0; "RtlCreateSecurityDescriptor(&SecurityDe"...
0x1801bc4f6  lea     rcx, aOnecoreBaseWcp_26; "onecore\\base\\wcp\\sil\\fs_buffered.cp"...
0x1801bc4fd  mov     qword ptr [rbp+0F0h+var_168], rcx
0x1801bc501  lea     rcx, aWindowsRtlSyst_177; "Windows::Rtl::SystemImplementation::CBu"...
0x1801bc508  mov     qword ptr [rbp+0F0h+var_168+8], rcx
0x1801bc50c  mov     [rbp+0F0h+var_150], rax
0x1801bc510  mov     r8d, edi
0x1801bc513  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801bc51a  lea     rcx, [rbp+0F0h+var_168]
0x1801bc51e  call    RtlReportErrorOrigination
0x1801bc523  jmp     short loc_1801BC4B2
0x1801bc525  xor     r8d, r8d; OwnerDefaulted
0x1801bc528  mov     rdx, [rbp+0F0h+Owner]; Owner
0x1801bc52c  lea     rcx, [rbp+0F0h+SecurityDescriptor]; SecurityDescriptor
0x1801bc530  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x1801bc537  nop     dword ptr [rax+rax+00h]
0x1801bc53c  mov     edi, eax
0x1801bc53e  test    eax, eax
0x1801bc540  jns     short loc_1801BC553
0x1801bc542  mov     [rbp+0F0h+var_158], 0CA9h
0x1801bc54a  lea     rax, aRtlsetownersec; "RtlSetOwnerSecurityDescriptor(&Security"...
0x1801bc551  jmp     short loc_1801BC4F6
0x1801bc553  xor     r8d, r8d; GroupDefaulted
0x1801bc556  mov     rdx, [rbp+0F0h+Owner]; Group
0x1801bc55a  lea     rcx, [rbp+0F0h+SecurityDescriptor]; SecurityDescriptor
0x1801bc55e  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x1801bc565  nop     dword ptr [rax+rax+00h]
0x1801bc56a  mov     edi, eax
0x1801bc56c  test    eax, eax
0x1801bc56e  jns     short loc_1801BC584
0x1801bc570  mov     [rbp+0F0h+var_158], 0CAAh
0x1801bc578  lea     rax, aRtlsetgroupsec_0; "RtlSetGroupSecurityDescriptor(&Security"...
0x1801bc57f  jmp     loc_1801BC4F6
0x1801bc584  xor     r9d, r9d; DaclDefaulted
0x1801bc587  mov     r8, [rbp+0F0h+Dacl]; Dacl
0x1801bc58b  mov     dl, 1; DaclPresent
0x1801bc58d  lea     rcx, [rbp+0F0h+SecurityDescriptor]; SecurityDescriptor
0x1801bc591  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1801bc598  nop     dword ptr [rax+rax+00h]
0x1801bc59d  mov     edi, eax
0x1801bc59f  test    eax, eax
0x1801bc5a1  jns     short loc_1801BC5B7
0x1801bc5a3  mov     [rbp+0F0h+var_158], 0CABh
0x1801bc5ab  lea     rax, aRtlsetdaclsecu; "RtlSetDaclSecurityDescriptor(&SecurityD"...
0x1801bc5b2  jmp     loc_1801BC4F6
0x1801bc5b7  mov     edx, 1000h; ControlBitsOfInterest
0x1801bc5bc  mov     r8d, edx; ControlBitsToSet
0x1801bc5bf  lea     rcx, [rbp+0F0h+SecurityDescriptor]; SecurityDescriptor
0x1801bc5c3  call    cs:__imp_RtlSetControlSecurityDescriptor
0x1801bc5ca  nop     dword ptr [rax+rax+00h]
0x1801bc5cf  mov     edi, eax
0x1801bc5d1  test    eax, eax
0x1801bc5d3  jns     short loc_1801BC5E9
0x1801bc5d5  mov     [rbp+0F0h+var_158], 0CACh
0x1801bc5dd  lea     rax, aRtlsetcontrols_0; "RtlSetControlSecurityDescriptor(&Securi"...
0x1801bc5e4  jmp     loc_1801BC4F6
0x1801bc5e9  xorps   xmm0, xmm0
0x1801bc5ec  movups  [rbp+0F0h+var_D8], xmm0
0x1801bc5f0  movups  [rbp+0F0h+var_C8], xmm0
0x1801bc5f4  movups  [rbp+0F0h+var_B8], xmm0
0x1801bc5f8  movdqu  [rbp+0F0h+var_A8], xmm0
0x1801bc5fd  movups  [rbp+0F0h+var_48], xmm0
0x1801bc604  xorps   xmm1, xmm1
0x1801bc607  xor     eax, eax
0x1801bc609  movups  [rbp+0F0h+var_70], xmm1
0x1801bc610  mov     [rbp+0F0h+var_60], rax
0x1801bc617  movups  [rbp+0F0h+var_168], xmm0
0x1801bc61b  mov     [rbp+0F0h+var_158], rax
0x1801bc61f  mov     [rsp+1F0h+var_1D0], r12
0x1801bc624  lea     r9, [rbp+0F0h+var_70]
0x1801bc62b  lea     r8, [rbp+0F0h+var_148]
0x1801bc62f  mov     rdx, r13
0x1801bc632  mov     rcx, rbx
0x1801bc635  call    ?GetVolumeSerialNumber@CBufferedFileSystemProvider@SystemImplementation@Rtl@Windows@@AEAAJPEAUBufferedPathElement@CBufferedFileHierarchy@234@PEAKPEAV?$Auto@U_LUNICODE_STRING@@@4@2@Z; Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetVolumeSerialNumber(Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::BufferedPathElement *,ulong *,Windows::Auto<_LUNICODE_STRING> *,Windows::Auto<_LUNICODE_STRING> *)
0x1801bc63a  mov     edi, eax
0x1801bc63c  test    eax, eax
0x1801bc63e  jns     short loc_1801BC681
0x1801bc640  lea     rcx, [rbp+0F0h+var_168]
0x1801bc644  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801bc649  nop
0x1801bc64a  lea     rcx, [rbp+0F0h+var_70]
0x1801bc651  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801bc656  nop
0x1801bc657  lea     rcx, [rbp+0F0h+var_A8]; this
0x1801bc65b  call    ?Close@CSilHandle@SystemImplementation@Rtl@Windows@@QEAAXXZ; Windows::Rtl::SystemImplementation::CSilHandle::Close(void)
0x1801bc660  mov     rcx, qword ptr [rbp+0F0h+var_A8]
0x1801bc664  test    rcx, rcx
0x1801bc667  jz      loc_1801BC4B2
0x1801bc66d  mov     qword ptr [rbp+0F0h+var_A8], r12
0x1801bc671  mov     rax, [rcx]
0x1801bc674  mov     rax, [rax]
0x1801bc677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc67c  jmp     loc_1801BC4B2
0x1801bc681  movups  xmm0, [rbp+0F0h+var_70]
0x1801bc688  movups  [rbp+0F0h+var_138], xmm0
0x1801bc68c  movsd   xmm1, [rbp+0F0h+var_60]
0x1801bc694  movsd   [rbp+0F0h+var_128], xmm1
0x1801bc699  mov     [rbp+0F0h+var_120], 1Ch
0x1801bc6a1  mov     [rbp+0F0h+var_118], 1Eh
0x1801bc6a9  lea     rax, aPendingfiles; "$$PendingFiles"
0x1801bc6b0  mov     [rbp+0F0h+var_110], rax
0x1801bc6b4  lea     r8, [rbp+0F0h+var_168]
0x1801bc6b8  lea     rdx, [rbp+0F0h+var_138]
0x1801bc6bc  mov     ecx, 2
0x1801bc6c1  call    RtlCombineNtPathSegments
0x1801bc6c6  mov     edi, eax
0x1801bc6c8  test    eax, eax
0x1801bc6ca  jns     short loc_1801BC6E8
0x1801bc6cc  lea     rcx, [rbp+0F0h+var_168]
0x1801bc6d0  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801bc6d5  nop
0x1801bc6d6  lea     rcx, [rbp+0F0h+var_70]
0x1801bc6dd  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801bc6e2  nop
0x1801bc6e3  jmp     loc_1801BC657
0x1801bc6e8  lea     rax, [rbp+0F0h+DestinationString]
0x1801bc6ec  mov     qword ptr [rbp+0F0h+var_58], rax
0x1801bc6f3  lea     rdx, [rbp+0F0h+var_58]
0x1801bc6fa  lea     rcx, [rbp+0F0h+var_168]
0x1801bc6fe  call    ??$DuplicateToBackslashTerminatedString@V?$Auto@U_LUNICODE_STRING@@@Windows@@V?$AutoOperatorAmpersandHelper@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@2@@Rtl@StringUtil@Windows@@YAJAEBV?$Auto@U_LUNICODE_STRING@@@2@V?$AutoOperatorAmpersandHelper@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@2@@Z; Windows::StringUtil::Rtl::DuplicateToBackslashTerminatedString<Windows::Auto<_LUNICODE_STRING>,Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>>(Windows::Auto<_LUNICODE_STRING> const &,Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>)
0x1801bc703  mov     edi, eax
0x1801bc705  test    eax, eax
  ... truncated ...
```
