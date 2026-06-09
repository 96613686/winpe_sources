# Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName(Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::BufferedPathElement *,Windows::Auto<_UNICODE_STRING> *)

- ea: `0x180249b08`
- end: `0x18024a3a9`
- name: `?GetTempDirectoryName@CBufferedFileSystemProvider@SystemImplementation@Rtl@Windows@@AEAAJPEAUBufferedPathElement@CBufferedFileHierarchy@234@PEAV?$Auto@U_UNICODE_STRING@@@4@@Z`
- size: `2209`
- prototype: `__int64 __fastcall(Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider *this)`
- caller_count: `1`
- callee_count: `18`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180248d70`

## callees

- `0x180019bdc`
- `0x18001a1a0`
- `0x180046198`
- `0x180094db4`
- `0x1800aa1a4`
- `0x1800eb920`
- `0x1800ef360`
- `0x180155c88`
- `0x1801f7c94`
- `0x1801f7e90`
- `0x1802153a0`
- `0x180247970`
- `0x180249550`
- `0x180249b08`
- `0x18024a60c`
- `0x1802c5fbc`
- `0x1802c6334`
- `0x1802d5010`

## import_xrefs

- `ntdll!RtlDuplicateUnicodeString` at `0x180249b98`
- `ntdll!RtlDuplicateUnicodeString` at `0x18024a26b`
- `ntdll!RtlDuplicateUnicodeString` at `0x18024a307`
- `ntdll!RtlDuplicateUnicodeString` at `0x180249b98`
- `ntdll!RtlDuplicateUnicodeString` at `0x18024a26b`
- `ntdll!RtlDuplicateUnicodeString` at `0x18024a307`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180249d0e`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180249d0e`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x180249dc2`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x180249dc2`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x180249e68`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x180249e68`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180249e17`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180249e17`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180249d72`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180249d72`

## string_xrefs

- `0x18024a2a0`: `RtlDuplicateUnicodeString( 0, ObjectAttributes.ObjectName, TempDirectoryOut.GetMutablePointer())`
- `0x180249bcc`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName`
- `0x180249d35`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName`
- `0x180249d99`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName`
- `0x180249de9`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName`
- `0x180249e3e`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName`
- `0x180249e8f`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName`
- `0x18024a292`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName`
- `0x18024a32e`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName`
- `0x180249bdd`: `RtlDuplicateUnicodeString( 0, m_TempDirectory.GetMutablePointer(), TempDirectory->GetMutablePointer())`
- `0x18024a33c`: `RtlDuplicateUnicodeString( 0, m_TempDirectory.GetMutablePointer(), TempDirectory->GetMutablePointer())`
- `0x180249df4`: `RtlSetGroupSecurityDescriptor(&SecurityDescriptor, TrustedInstaller, 0)`
- `0x180249e49`: `RtlSetDaclSecurityDescriptor(&SecurityDescriptor, 1, Acl.GetMutablePointer(), 0)`
- `0x180249e9a`: `RtlSetControlSecurityDescriptor(&SecurityDescriptor, (0x1000), (0x1000))`
- `0x180249d40`: `RtlCreateSecurityDescriptor(&SecurityDescriptor, (1))`
- `0x180249da4`: `RtlSetOwnerSecurityDescriptor(&SecurityDescriptor, TrustedInstaller, 0)`

## pseudocode

```c
__int64 __fastcall Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName(
        UNICODE_STRING *this,
        __int64 a2,
        struct _UNICODE_STRING *a3)
{
  __int64 result; // rax
  int v7; // r14d
  struct _UNICODE_STRING *v8; // rsi
  NTSTATUS v9; // eax
  int BootVolumeSerialNumber; // ebx
  int inited; // eax
  int v12; // ebx
  NTSTATUS v13; // eax
  _QWORD *v14; // rdx
  PWSTR v15; // r11
  PWSTR Buffer; // r11
  int v17; // r15d
  PWSTR v18; // r11
  int v19; // r14d
  NTSTATUS v20; // eax
  struct _UNICODE_STRING v21; // xmm0
  NTSTATUS v22; // eax
  _BYTE v23[4]; // [rsp+80h] [rbp-80h] BYREF
  int v24; // [rsp+84h] [rbp-7Ch] BYREF
  _QWORD v25[4]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v26[4]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v27[4]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v28[4]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v29[4]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v30[4]; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v31[4]; // [rsp+148h] [rbp+48h] BYREF
  _QWORD v32[2]; // [rsp+168h] [rbp+68h] BYREF
  PCUNICODE_STRING SourceString; // [rsp+178h] [rbp+78h]
  __int64 v34; // [rsp+180h] [rbp+80h]
  __int128 v35; // [rsp+188h] [rbp+88h]
  __int128 v36; // [rsp+198h] [rbp+98h] BYREF
  __int128 v37; // [rsp+1A8h] [rbp+A8h]
  __int128 v38; // [rsp+1B8h] [rbp+B8h]
  PSID Owner; // [rsp+1C8h] [rbp+C8h] BYREF
  int v40; // [rsp+1D0h] [rbp+D0h] BYREF
  PACL Dacl; // [rsp+1D8h] [rbp+D8h] BYREF
  __int128 v42; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v43; // [rsp+1F0h] [rbp+F0h]
  const char *v44; // [rsp+1F8h] [rbp+F8h]
  __int128 v45; // [rsp+200h] [rbp+100h] BYREF
  const wchar_t *v46; // [rsp+210h] [rbp+110h]
  __int128 v47; // [rsp+218h] [rbp+118h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+230h] [rbp+130h] BYREF
  __int128 v49; // [rsp+240h] [rbp+140h] BYREF
  __int64 v50; // [rsp+250h] [rbp+150h]
  _OWORD SecurityDescriptor[2]; // [rsp+258h] [rbp+158h] BYREF
  __int64 v52; // [rsp+278h] [rbp+178h]
  __int128 v53; // [rsp+280h] [rbp+180h] BYREF

  v40 = 0;
  Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(a3);
  v24 = 0;
  result = Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetVolumeSerialNumber(
             (_DWORD)this,
             a2,
             (unsigned int)&v24,
             0,
             0);
  if ( (int)result >= 0 )
  {
    v7 = v24;
    v8 = this + 31;
    if ( this[31].Buffer && *(_DWORD *)&this[32].Length == v24 )
    {
      v9 = RtlDuplicateUnicodeString(0, this + 31, a3);
      if ( v9 < 0 )
      {
        v43 = 3141;
        *(_QWORD *)&v42 = "onecore\\base\\wcp\\sil\\fs_buffered.cpp";
        *((_QWORD *)&v42 + 1) = "Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName";
        v44 = "RtlDuplicateUnicodeString( 0, m_TempDirectory.GetMutablePointer(), TempDirectory->GetMutablePointer())";
        return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                 &v40,
                 &v42,
                 (unsigned int)v9);
      }
      return 0;
    }
    LODWORD(Owner) = 0;
    DestinationString = 0;
    v43 = 0;
    v42 = 0;
    BootVolumeSerialNumber = Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetBootVolumeSerialNumber(
                               (Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider *)this,
                               (unsigned int *)&Owner);
    if ( BootVolumeSerialNumber < 0 )
    {
LABEL_44:
      Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(&DestinationString);
      return (unsigned int)BootVolumeSerialNumber;
    }
    inited = RtlInitLUnicodeStringFromUnicodeString(a2 + 96, &v42);
    if ( inited >= 0 )
    {
      v23[0] = 0;
      inited = RtlEqualLUnicodeStringPrefix(
                 &v42,
                 g_LUNICODE_STRING__bslash_SystemRoot_bslash_,
                 RtlUpcaseUCSCharacter,
                 v23);
      if ( inited >= 0 )
      {
        v12 = (int)Owner;
        if ( v23[0] || v7 == (_DWORD)Owner )
        {
          Buffer = this[12].Buffer;
          SourceString = (PCUNICODE_STRING)L"02";
          v32[0] = 48;
          v34 = 64;
          v49 = 0;
          v32[1] = 0;
          v45 = 0;
          v35 = 0;
          v17 = (*(__int64 (__fastcall **)(PWSTR, _QWORD, __int128 *, __int64, _QWORD *, __int128 *, _QWORD, int, int, int, int, _QWORD, _DWORD, _QWORD, _QWORD))(*(_QWORD *)Buffer + 112LL))(
                  Buffer,
                  0,
                  &v45,
                  1179926,
                  v32,
                  &v49,
                  0,
                  16,
                  7,
                  3,
                  16417,
                  0,
                  0,
                  0,
                  0);
          if ( v17 < 0 )
          {
            Windows::Rtl::SystemImplementation::CSilHandle::~CSilHandle((Windows::Rtl::SystemImplementation::CSilHandle *)&v45);
            BootVolumeSerialNumber = v17;
            goto LABEL_44;
          }
          Windows::Rtl::SystemImplementation::CSilHandle::Close((Windows::Rtl::SystemImplementation::CSilHandle *)&v45);
          v18 = this[12].Buffer;
          SourceString = (PCUNICODE_STRING)L"NP";
          v19 = (*(__int64 (__fastcall **)(PWSTR, _QWORD, __int128 *, __int64, _QWORD *, __int128 *, _QWORD, int, int, int, int, _QWORD, _DWORD, _QWORD, _QWORD))(*(_QWORD *)v18 + 112LL))(
                  v18,
                  0,
                  &v45,
                  1179926,
                  v32,
                  &v49,
                  0,
                  16,
                  7,
                  3,
                  16417,
                  0,
                  0,
                  0,
                  0);
          if ( v19 < 0 )
          {
            Windows::Rtl::SystemImplementation::CSilHandle::~CSilHandle((Windows::Rtl::SystemImplementation::CSilHandle *)&v45);
            BootVolumeSerialNumber = v19;
            goto LABEL_44;
          }
          v20 = RtlDuplicateUnicodeString(0, SourceString, &DestinationString);
          if ( v20 < 0 )
          {
            v30[2] = 3225;
            v30[0] = "onecore\\base\\wcp\\sil\\fs_buffered.cpp";
            v30[1] = "Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName";
            v30[3] = "RtlDuplicateUnicodeString( 0, ObjectAttributes.ObjectName, TempDirectoryOut.GetMutablePointer())";
            BootVolumeSerialNumber = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                                       &v40,
                                       v30,
                                       (unsigned int)v20);
            Windows::Rtl::SystemImplementation::CSilHandle::~CSilHandle((Windows::Rtl::SystemImplementation::CSilHandle *)&v45);
            goto LABEL_44;
          }
          Windows::Rtl::SystemImplementation::CSilHandle::~CSilHandle((Windows::Rtl::SystemImplementation::CSilHandle *)&v45);
        }
        else
        {
          Owner = 0;
          BootVolumeSerialNumber = Windows::WCP::Implementation::Rtl::GetTrustedInstallerSid(&Owner);
          if ( BootVolumeSerialNumber < 0 )
          {
LABEL_12:
            Windows::Auto<_ACL>::Close(&Owner);
            goto LABEL_44;
          }
          Dacl = 0;
          BootVolumeSerialNumber = Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL((__int64)&Dacl);
          if ( BootVolumeSerialNumber < 0 )
          {
LABEL_14:
            Windows::Auto<_ACL>::Close(&Dacl);
            goto LABEL_12;
          }
          v52 = 0;
          memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
          v13 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
          if ( v13 < 0 )
          {
            v25[2] = 3240;
            v25[0] = "onecore\\base\\wcp\\sil\\fs_buffered.cpp";
            v14 = v25;
            v25[1] = "Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName";
            v25[3] = "RtlCreateSecurityDescriptor(&SecurityDescriptor, (1))";
LABEL_17:
            BootVolumeSerialNumber = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                                       &v40,
                                       v14,
                                       (unsigned int)v13);
            goto LABEL_14;
          }
          v13 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, Owner, 0);
          if ( v13 < 0 )
          {
            v26[2] = 3241;
            v26[0] = "onecore\\base\\wcp\\sil\\fs_buffered.cpp";
            v14 = v26;
            v26[1] = "Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName";
            v26[3] = "RtlSetOwnerSecurityDescriptor(&SecurityDescriptor, TrustedInstaller, 0)";
            goto LABEL_17;
          }
          v13 = RtlSetGroupSecurityDescriptor(SecurityDescriptor, Owner, 0);
          if ( v13 < 0 )
          {
            v27[2] = 3242;
            v27[0] = "onecore\\base\\wcp\\sil\\fs_buffered.cpp";
            v14 = v27;
            v27[1] = "Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName";
            v27[3] = "RtlSetGroupSecurityDescriptor(&SecurityDescriptor, TrustedInstaller, 0)";
            goto LABEL_17;
          }
          v13 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, Dacl, 0);
          if ( v13 < 0 )
          {
            v28[2] = 3243;
            v28[0] = "onecore\\base\\wcp\\sil\\fs_buffered.cpp";
            v14 = v28;
            v28[1] = "Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName";
            v28[3] = "RtlSetDaclSecurityDescriptor(&SecurityDescriptor, 1, Acl.GetMutablePointer(), 0)";
            goto LABEL_17;
          }
          v13 = RtlSetControlSecurityDescriptor(SecurityDescriptor, 0x1000u, 0x1000u);
          if ( v13 < 0 )
          {
            v29[2] = 3244;
            v29[0] = "onecore\\base\\wcp\\sil\\fs_buffered.cpp";
            v14 = v29;
            v29[1] = "Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName";
            v29[3] = "RtlSetControlSecurityDescriptor(&SecurityDescriptor, (0x1000), (0x1000))";
            goto LABEL_17;
          }
          v43 = 0;
          v50 = 0;
          v36 = 0;
          v37 = 0;
          v38 = 0;
          v47 = 0;
          v53 = 0;
          v42 = 0;
          v49 = 0;
          BootVolumeSerialNumber = Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetVolumeSerialNumber(
                                     (_DWORD)this,
                                     a2,
                                     (unsigned int)&v24,
                                     (unsigned int)&v42,
                                     0);
          if ( BootVolumeSerialNumber < 0 )
            goto LABEL_27;
          *(_QWORD *)&v45 = 28;
          v46 = L"$$PendingFiles";
          *((_QWORD *)&v45 + 1) = 30;
          BootVolumeSerialNumber = Windows::StringUtil::Rtl::CombineNtPaths<_LUNICODE_STRING,_LUNICODE_STRING>(
                                     &v42,
                                     &v45,
                                     (__int64)&v49);
          if ( BootVolumeSerialNumber < 0 )
            goto LABEL_27;
          *(_QWORD *)&v45 = &DestinationString;
          BootVolumeSerialNumber = Windows::StringUtil::Rtl::DuplicateToBackslashTerminatedString<Windows::Auto<_LUNICODE_STRING>,Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>>(
                                     &v49,
                                     &v45);
          if ( BootVolumeSerialNumber < 0 )
            goto LABEL_27;
          v15 = this[12].Buffer;
          *(_QWORD *)&v37 = &DestinationString;
          *(_QWORD *)&v38 = SecurityDescriptor;
          LODWORD(v36) = 48;
          *((_QWORD *)&v36 + 1) = 0;
          DWORD2(v37) = 64;
          *((_QWORD *)&v38 + 1) = 0;
          BootVolumeSerialNumber = (*(__int64 (__fastcall **)(PWSTR, _QWORD, __int128 *, __int64, __int128 *, __int128 *, _QWORD, int, int, int, int, _QWORD, _DWORD, _QWORD, _QWORD))(*(_QWORD *)v15 + 112LL))(
                                     v15,
                                     0,
                                     &v47,
                                     18743702,
                                     &v36,
                                     &v53,
                                     0,
                                     22,
                                     7,
                                     3,
                                     16417,
                                     0,
                                     0,
                                     0,
                                     0);
          if ( BootVolumeSerialNumber < 0
            || (BootVolumeSerialNumber = (*(__int64 (__fastcall **)(PWSTR, _QWORD, _QWORD, __int64, _OWORD *, _QWORD))(*(_QWORD *)this[12].Buffer + 32LL))(
                                           this[12].Buffer,
                                           0,
                                           *((_QWORD *)&v47 + 1),
                                           7,
                                           SecurityDescriptor,
                                           0),
                BootVolumeSerialNumber < 0) )
          {
LABEL_27:
            Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v49);
            Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v42);
            Windows::Rtl::SystemImplementation::CSilHandle::~CSilHandle((Windows::Rtl::SystemImplementation::CSilHandle *)&v47);
            goto LABEL_14;
          }
          v12 = v24;
          Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v49);
          Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v42);
          Windows::Rtl::SystemImplementation::CSilHandle::~CSilHandle((Windows::Rtl::SystemImplementation::CSilHandle *)&v47);
          Windows::Auto<_ACL>::Close(&Dacl);
          Windows::Auto<_ACL>::Close(&Owner);
        }
        if ( !DestinationString.Buffer )
        {
          INTERNAL_ERROR_ACTION(-1073741595);
          JUMPOUT(0x18024A3A8LL);
        }
        v21 = *v8;
        *v8 = DestinationString;
        *(_DWORD *)&this[32].Length = v12;
        DestinationString = v21;
        v22 = RtlDuplicateUnicodeString(0, this + 31, a3);
        if ( v22 >= 0 )
        {
          Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(&DestinationString);
          return 0;
        }
        v31[2] = 3302;
        v31[0] = "onecore\\base\\wcp\\sil\\fs_buffered.cpp";
        v31[1] = "Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetTempDirectoryName";
        v31[3] = "RtlDuplicateUnicodeString( 0, m_TempDirectory.GetMutablePointer(), TempDirectory->GetMutablePointer())";
        inited = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                   &v40,
                   v31,
                   (unsigned int)v22);
      }
    }
    BootVolumeSerialNumber = inited;
    goto LABEL_44;
  }
  return result;
}

```

## disassembly

```asm
0x180249b08  mov     [rsp-8+arg_18], rbx
0x180249b0d  push    rbp
0x180249b0e  push    rsi
0x180249b0f  push    rdi
0x180249b10  push    r12
0x180249b12  push    r13
0x180249b14  push    r14
0x180249b16  push    r15
0x180249b18  lea     rbp, [rsp-1A0h]
0x180249b20  sub     rsp, 2A0h
0x180249b27  mov     rax, cs:__security_cookie
0x180249b2e  xor     rax, rsp
0x180249b31  mov     [rbp+1D0h+var_40], rax
0x180249b38  mov     rdi, rcx
0x180249b3b  xor     r13d, r13d
0x180249b3e  mov     rcx, r8
0x180249b41  mov     [rbp+1D0h+var_100], r13d
0x180249b48  mov     r12, r8
0x180249b4b  mov     r15, rdx
0x180249b4e  call    ?Close@?$AutoString@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(void)
0x180249b53  xor     r9d, r9d
0x180249b56  mov     [rbp+1D0h+var_24C], r13d
0x180249b5a  lea     r8, [rbp+1D0h+var_24C]
0x180249b5e  mov     [rsp+2D0h+var_2B0], r13
0x180249b63  mov     rdx, r15
0x180249b66  mov     rcx, rdi
0x180249b69  call    ?GetVolumeSerialNumber@CBufferedFileSystemProvider@SystemImplementation@Rtl@Windows@@AEAAJPEAUBufferedPathElement@CBufferedFileHierarchy@234@PEAKPEAV?$Auto@U_LUNICODE_STRING@@@4@2@Z; Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetVolumeSerialNumber(Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::BufferedPathElement *,ulong *,Windows::Auto<_LUNICODE_STRING> *,Windows::Auto<_LUNICODE_STRING> *)
0x180249b6e  test    eax, eax
0x180249b70  js      loc_18024A373
0x180249b76  mov     r14d, [rbp+1D0h+var_24C]
0x180249b7a  lea     rsi, [rdi+1F0h]
0x180249b81  cmp     [rsi+8], r13
0x180249b85  jz      short loc_180249BFC
0x180249b87  cmp     [rdi+200h], r14d
0x180249b8e  jnz     short loc_180249BFC
0x180249b90  mov     r8, r12; DestinationString
0x180249b93  mov     rdx, rsi; SourceString
0x180249b96  xor     ecx, ecx; Flags
0x180249b98  call    cs:__imp_RtlDuplicateUnicodeString
0x180249b9f  nop     dword ptr [rax+rax+00h]
0x180249ba4  test    eax, eax
0x180249ba6  jns     loc_18024A371
0x180249bac  lea     rcx, aOnecoreBaseWcp_29; "onecore\\base\\wcp\\sil\\fs_buffered.cp"...
0x180249bb3  mov     [rbp+1D0h+var_E0], 0C45h
0x180249bbe  mov     qword ptr [rbp+1D0h+var_F0], rcx
0x180249bc5  lea     rdx, [rbp+1D0h+var_F0]
0x180249bcc  lea     rcx, aWindowsRtlSyst_182; "Windows::Rtl::SystemImplementation::CBu"...
0x180249bd3  mov     r8d, eax
0x180249bd6  mov     qword ptr [rbp+1D0h+var_F0+8], rcx
0x180249bdd  lea     rcx, aRtlduplicateun_2; "RtlDuplicateUnicodeString( 0, m_TempDir"...
0x180249be4  mov     [rbp+1D0h+var_D8], rcx
0x180249beb  lea     rcx, [rbp+1D0h+var_100]
0x180249bf2  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180249bf7  jmp     loc_18024A373
0x180249bfc  xorps   xmm0, xmm0
0x180249bff  mov     dword ptr [rbp+1D0h+Owner], r13d
0x180249c06  xorps   xmm1, xmm1
0x180249c09  lea     rdx, [rbp+1D0h+Owner]; unsigned int *
0x180249c10  xor     eax, eax
0x180249c12  mov     rcx, rdi; this
0x180249c15  movups  xmmword ptr [rbp+1D0h+DestinationString.Length], xmm0
0x180249c1c  mov     [rbp+1D0h+var_E0], rax
0x180249c23  movups  [rbp+1D0h+var_F0], xmm1
0x180249c2a  call    ?GetBootVolumeSerialNumber@CBufferedFileSystemProvider@SystemImplementation@Rtl@Windows@@AEAAJPEAK@Z; Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetBootVolumeSerialNumber(ulong *)
0x180249c2f  mov     ebx, eax
0x180249c31  test    eax, eax
0x180249c33  js      loc_18024A355
0x180249c39  lea     rcx, [r15+60h]
0x180249c3d  lea     rdx, [rbp+1D0h+var_F0]
0x180249c44  call    RtlInitLUnicodeStringFromUnicodeString
0x180249c49  test    eax, eax
0x180249c4b  js      loc_18024A353
0x180249c51  lea     r9, [rbp+1D0h+var_250]
0x180249c55  mov     [rbp+1D0h+var_250], r13b
0x180249c59  lea     r8, RtlUpcaseUCSCharacter
0x180249c60  lea     rdx, g_LUNICODE_STRING__bslash_SystemRoot_bslash_
0x180249c67  lea     rcx, [rbp+1D0h+var_F0]
0x180249c6e  call    RtlEqualLUnicodeStringPrefix
0x180249c73  test    eax, eax
0x180249c75  js      loc_18024A353
0x180249c7b  mov     ebx, dword ptr [rbp+1D0h+Owner]
0x180249c81  cmp     [rbp+1D0h+var_250], r13b
0x180249c85  jnz     loc_18024A0ED
0x180249c8b  cmp     r14d, ebx
0x180249c8e  setz    al
0x180249c91  test    al, al
0x180249c93  jnz     loc_18024A0ED
0x180249c99  lea     rcx, [rbp+1D0h+Owner]
0x180249ca0  mov     [rbp+1D0h+Owner], r13
0x180249ca7  call    ?GetTrustedInstallerSid@Rtl@Implementation@WCP@Windows@@YAJPEAV?$Auto@U_SID@@@4@@Z; Windows::WCP::Implementation::Rtl::GetTrustedInstallerSid(Windows::Auto<_SID> *)
0x180249cac  mov     ebx, eax
0x180249cae  test    eax, eax
0x180249cb0  jns     short loc_180249CC3
0x180249cb2  lea     rcx, [rbp+1D0h+Owner]
0x180249cb9  call    ?Close@?$Auto@U_ACL@@@Windows@@QEAAXXZ; Windows::Auto<_ACL>::Close(void)
0x180249cbe  jmp     loc_18024A355
0x180249cc3  lea     rcx, [rbp+1D0h+Dacl]
0x180249cca  mov     [rbp+1D0h+Dacl], r13
0x180249cd1  call    ?GetDefaultWRPLeafDirDACL@Rtl@Implementation@WCP@Windows@@YAJPEAV?$Auto@U_ACL@@@4@@Z; Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL(Windows::Auto<_ACL> *)
0x180249cd6  mov     ebx, eax
0x180249cd8  test    eax, eax
0x180249cda  jns     short loc_180249CEA
0x180249cdc  lea     rcx, [rbp+1D0h+Dacl]
0x180249ce3  call    ?Close@?$Auto@U_ACL@@@Windows@@QEAAXXZ; Windows::Auto<_ACL>::Close(void)
0x180249ce8  jmp     short loc_180249CB2
0x180249cea  xor     eax, eax
0x180249cec  lea     rcx, [rbp+1D0h+SecurityDescriptor]; SecurityDescriptor
0x180249cf3  xorps   xmm0, xmm0
0x180249cf6  mov     [rbp+1D0h+var_58], rax
0x180249cfd  movups  [rbp+1D0h+SecurityDescriptor], xmm0
0x180249d04  lea     edx, [rax+1]; Revision
0x180249d07  movups  [rbp+1D0h+var_68], xmm0
0x180249d0e  call    cs:__imp_RtlCreateSecurityDescriptor
0x180249d15  nop     dword ptr [rax+rax+00h]
0x180249d1a  test    eax, eax
0x180249d1c  jns     short loc_180249D61
0x180249d1e  lea     rcx, aOnecoreBaseWcp_29; "onecore\\base\\wcp\\sil\\fs_buffered.cp"...
0x180249d25  mov     [rbp+1D0h+var_238], 0CA8h
0x180249d2d  mov     [rbp+1D0h+var_248], rcx
0x180249d31  lea     rdx, [rbp+1D0h+var_248]
0x180249d35  lea     rcx, aWindowsRtlSyst_182; "Windows::Rtl::SystemImplementation::CBu"...
0x180249d3c  mov     [rbp+1D0h+var_240], rcx
0x180249d40  lea     rcx, aRtlcreatesecur_0; "RtlCreateSecurityDescriptor(&SecurityDe"...
0x180249d47  mov     [rbp+1D0h+var_230], rcx
0x180249d4b  mov     r8d, eax
0x180249d4e  lea     rcx, [rbp+1D0h+var_100]
0x180249d55  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180249d5a  mov     ebx, eax
0x180249d5c  jmp     loc_180249CDC
0x180249d61  mov     rdx, [rbp+1D0h+Owner]; Owner
0x180249d68  lea     rcx, [rbp+1D0h+SecurityDescriptor]; SecurityDescriptor
0x180249d6f  xor     r8d, r8d; OwnerDefaulted
0x180249d72  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x180249d79  nop     dword ptr [rax+rax+00h]
0x180249d7e  test    eax, eax
0x180249d80  jns     short loc_180249DB1
0x180249d82  lea     rcx, aOnecoreBaseWcp_29; "onecore\\base\\wcp\\sil\\fs_buffered.cp"...
0x180249d89  mov     [rbp+1D0h+var_218], 0CA9h
0x180249d91  mov     [rbp+1D0h+var_228], rcx
0x180249d95  lea     rdx, [rbp+1D0h+var_228]
0x180249d99  lea     rcx, aWindowsRtlSyst_182; "Windows::Rtl::SystemImplementation::CBu"...
0x180249da0  mov     [rbp+1D0h+var_220], rcx
0x180249da4  lea     rcx, aRtlsetownersec; "RtlSetOwnerSecurityDescriptor(&Security"...
0x180249dab  mov     [rbp+1D0h+var_210], rcx
0x180249daf  jmp     short loc_180249D4B
0x180249db1  mov     rdx, [rbp+1D0h+Owner]; Group
0x180249db8  lea     rcx, [rbp+1D0h+SecurityDescriptor]; SecurityDescriptor
0x180249dbf  xor     r8d, r8d; GroupDefaulted
0x180249dc2  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x180249dc9  nop     dword ptr [rax+rax+00h]
0x180249dce  test    eax, eax
0x180249dd0  jns     short loc_180249E04
0x180249dd2  lea     rcx, aOnecoreBaseWcp_29; "onecore\\base\\wcp\\sil\\fs_buffered.cp"...
0x180249dd9  mov     [rbp+1D0h+var_1F8], 0CAAh
0x180249de1  mov     [rbp+1D0h+var_208], rcx
0x180249de5  lea     rdx, [rbp+1D0h+var_208]
0x180249de9  lea     rcx, aWindowsRtlSyst_182; "Windows::Rtl::SystemImplementation::CBu"...
0x180249df0  mov     [rbp+1D0h+var_200], rcx
0x180249df4  lea     rcx, aRtlsetgroupsec_0; "RtlSetGroupSecurityDescriptor(&Security"...
0x180249dfb  mov     [rbp+1D0h+var_1F0], rcx
0x180249dff  jmp     loc_180249D4B
0x180249e04  mov     r8, [rbp+1D0h+Dacl]; Dacl
0x180249e0b  lea     rcx, [rbp+1D0h+SecurityDescriptor]; SecurityDescriptor
0x180249e12  xor     r9d, r9d; DaclDefaulted
0x180249e15  mov     dl, 1; DaclPresent
0x180249e17  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180249e1e  nop     dword ptr [rax+rax+00h]
0x180249e23  test    eax, eax
0x180249e25  jns     short loc_180249E59
0x180249e27  lea     rcx, aOnecoreBaseWcp_29; "onecore\\base\\wcp\\sil\\fs_buffered.cp"...
0x180249e2e  mov     [rbp+1D0h+var_1D8], 0CABh
0x180249e36  mov     [rbp+1D0h+var_1E8], rcx
0x180249e3a  lea     rdx, [rbp+1D0h+var_1E8]
0x180249e3e  lea     rcx, aWindowsRtlSyst_182; "Windows::Rtl::SystemImplementation::CBu"...
0x180249e45  mov     [rbp+1D0h+var_1E0], rcx
0x180249e49  lea     rcx, aRtlsetdaclsecu; "RtlSetDaclSecurityDescriptor(&SecurityD"...
0x180249e50  mov     [rbp+1D0h+var_1D0], rcx
0x180249e54  jmp     loc_180249D4B
0x180249e59  mov     edx, 1000h; ControlBitsOfInterest
0x180249e5e  lea     rcx, [rbp+1D0h+SecurityDescriptor]; SecurityDescriptor
0x180249e65  mov     r8d, edx; ControlBitsToSet
0x180249e68  call    cs:__imp_RtlSetControlSecurityDescriptor
0x180249e6f  nop     dword ptr [rax+rax+00h]
0x180249e74  test    eax, eax
0x180249e76  jns     short loc_180249EAA
0x180249e78  lea     rcx, aOnecoreBaseWcp_29; "onecore\\base\\wcp\\sil\\fs_buffered.cp"...
0x180249e7f  mov     [rbp+1D0h+var_1B8], 0CACh
0x180249e87  mov     [rbp+1D0h+var_1C8], rcx
0x180249e8b  lea     rdx, [rbp+1D0h+var_1C8]
0x180249e8f  lea     rcx, aWindowsRtlSyst_182; "Windows::Rtl::SystemImplementation::CBu"...
0x180249e96  mov     [rbp+1D0h+var_1C0], rcx
0x180249e9a  lea     rcx, aRtlsetcontrols_0; "RtlSetControlSecurityDescriptor(&Securi"...
0x180249ea1  mov     [rbp+1D0h+var_1B0], rcx
0x180249ea5  jmp     loc_180249D4B
0x180249eaa  xorps   xmm0, xmm0
0x180249ead  mov     [rsp+2D0h+var_2B0], r13
0x180249eb2  xor     eax, eax
0x180249eb4  lea     r9, [rbp+1D0h+var_F0]
0x180249ebb  xorps   xmm1, xmm1
0x180249ebe  mov     [rbp+1D0h+var_E0], rax
0x180249ec5  lea     r8, [rbp+1D0h+var_24C]
0x180249ec9  mov     [rbp+1D0h+var_80], rax
0x180249ed0  mov     rdx, r15
0x180249ed3  mov     rcx, rdi
0x180249ed6  movups  [rbp+1D0h+var_138], xmm0
0x180249edd  movups  [rbp+1D0h+var_128], xmm0
0x180249ee4  movups  [rbp+1D0h+var_118], xmm0
0x180249eeb  movdqu  [rbp+1D0h+var_B8], xmm0
0x180249ef3  movups  [rbp+1D0h+var_50], xmm0
0x180249efa  movups  [rbp+1D0h+var_F0], xmm1
0x180249f01  movups  [rbp+1D0h+var_90], xmm0
0x180249f08  call    ?GetVolumeSerialNumber@CBufferedFileSystemProvider@SystemImplementation@Rtl@Windows@@AEAAJPEAUBufferedPathElement@CBufferedFileHierarchy@234@PEAKPEAV?$Auto@U_LUNICODE_STRING@@@4@2@Z; Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetVolumeSerialNumber(Windows::Rtl::SystemImplementation::CBufferedFileHierarchy::BufferedPathElement *,ulong *,Windows::Auto<_LUNICODE_STRING> *,Windows::Auto<_LUNICODE_STRING> *)
0x180249f0d  mov     ebx, eax
0x180249f0f  test    eax, eax
0x180249f11  jns     short loc_180249F3C
0x180249f13  lea     rcx, [rbp+1D0h+var_90]
0x180249f1a  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180249f1f  lea     rcx, [rbp+1D0h+var_F0]
0x180249f26  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180249f2b  lea     rcx, [rbp+1D0h+var_B8]; this
0x180249f32  call    ??1CSilHandle@SystemImplementation@Rtl@Windows@@QEAA@XZ; Windows::Rtl::SystemImplementation::CSilHandle::~CSilHandle(void)
0x180249f37  jmp     loc_180249CDC
0x180249f3c  lea     rax, aPendingfiles; "$$PendingFiles"
0x180249f43  mov     qword ptr [rbp+1D0h+var_D0], 1Ch
0x180249f4e  lea     r8, [rbp+1D0h+var_90]
0x180249f55  mov     [rbp+1D0h+var_C0], rax
0x180249f5c  lea     rdx, [rbp+1D0h+var_D0]
0x180249f63  mov     qword ptr [rbp+1D0h+var_D0+8], 1Eh
0x180249f6e  lea     rcx, [rbp+1D0h+var_F0]
0x180249f75  call    ??$CombineNtPaths@U_LUNICODE_STRING@@U1@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@0PEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::StringUtil::Rtl::CombineNtPaths<_LUNICODE_STRING,_LUNICODE_STRING>(_LUNICODE_STRING const &,_LUNICODE_STRING const &,Windows::Auto<_LUNICODE_STRING> *)
0x180249f7a  lea     rcx, [rbp+1D0h+var_90]
0x180249f81  mov     ebx, eax
0x180249f83  test    eax, eax
0x180249f85  js      short loc_180249F1A
0x180249f87  lea     rax, [rbp+1D0h+DestinationString]
0x180249f8e  lea     rdx, [rbp+1D0h+var_D0]
0x180249f95  mov     qword ptr [rbp+1D0h+var_D0], rax
0x180249f9c  call    ??$DuplicateToBackslashTerminatedString@V?$Auto@U_LUNICODE_STRING@@@Windows@@V?$AutoOperatorAmpersandHelper@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@2@@Rtl@StringUtil@Windows@@YAJAEBV?$Auto@U_LUNICODE_STRING@@@2@V?$AutoOperatorAmpersandHelper@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@2@@Z; Windows::StringUtil::Rtl::DuplicateToBackslashTerminatedString<Windows::Auto<_LUNICODE_STRING>,Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>>(Windows::Auto<_LUNICODE_STRING> const &,Windows::AutoOperatorAmpersandHelper<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>)
0x180249fa1  mov     ebx, eax
0x180249fa3  test    eax, eax
0x180249fa5  js      loc_180249F13
0x180249fab  mov     r11, [rdi+0C8h]
0x180249fb2  lea     rax, [rbp+1D0h+DestinationString]
0x180249fb9  mov     [rsp+2D0h+var_260], r13
0x180249fbe  lea     r8, [rbp+1D0h+var_B8]
0x180249fc5  mov     [rsp+2D0h+var_268], r13
0x180249fca  mov     r14d, 7
0x180249fd0  mov     [rsp+2D0h+var_270], r13d
0x180249fd5  mov     r9d, 11E0196h
0x180249fdb  mov     [rsp+2D0h+var_278], r13
0x180249fe0  xor     edx, edx
0x180249fe2  mov     qword ptr [rbp+1D0h+var_128], rax
0x180249fe9  lea     rax, [rbp+1D0h+SecurityDescriptor]
0x180249ff0  mov     [rsp+2D0h+var_280], 4021h
0x180249ff8  mov     qword ptr [rbp+1D0h+var_118], rax
0x180249fff  lea     rax, [rbp+1D0h+var_50]
0x18024a006  mov     [rsp+2D0h+var_288], 3
0x18024a00e  mov     [rsp+2D0h+var_290], r14d
0x18024a013  mov     [rsp+2D0h+var_298], 16h
0x18024a01b  mov     dword ptr [rbp+1D0h+var_138], 30h ; '0'
0x18024a025  mov     qword ptr [rbp+1D0h+var_138+8], r13
0x18024a02c  mov     dword ptr [rbp+1D0h+var_128+8], 40h ; '@'
0x18024a036  mov     qword ptr [rbp+1D0h+var_118+8], r13
0x18024a03d  mov     rcx, [r11]
0x18024a040  mov     [rsp+2D0h+var_2A0], r13
0x18024a045  mov     [rsp+2D0h+var_2A8], rax
0x18024a04a  lea     rax, [rbp+1D0h+var_138]
0x18024a051  mov     [rsp+2D0h+var_2B0], rax
0x18024a056  mov     r10, [rcx+70h]
0x18024a05a  mov     rcx, r11
0x18024a05d  mov     rax, r10
0x18024a060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024a065  mov     ebx, eax
0x18024a067  test    eax, eax
0x18024a069  js      loc_180249F13
0x18024a06f  mov     rcx, [rdi+0C8h]
0x18024a076  lea     rdx, [rbp+1D0h+SecurityDescriptor]
0x18024a07d  mov     r8, qword ptr [rbp+1D0h+var_B8+8]
0x18024a084  mov     r9d, r14d
0x18024a087  mov     [rsp+2D0h+var_2A8], r13
0x18024a08c  mov     [rsp+2D0h+var_2B0], rdx
0x18024a091  xor     edx, edx
0x18024a093  mov     rax, [rcx]
0x18024a096  mov     rax, [rax+20h]
0x18024a09a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024a09f  lea     rcx, [rbp+1D0h+var_90]
0x18024a0a6  mov     ebx, eax
0x18024a0a8  test    eax, eax
0x18024a0aa  js      loc_180249F1A
0x18024a0b0  mov     ebx, [rbp+1D0h+var_24C]
0x18024a0b3  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18024a0b8  lea     rcx, [rbp+1D0h+var_F0]
0x18024a0bf  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18024a0c4  lea     rcx, [rbp+1D0h+var_B8]; this
0x18024a0cb  call    ??1CSilHandle@SystemImplementation@Rtl@Windows@@QEAA@XZ; Windows::Rtl::SystemImplementation::CSilHandle::~CSilHandle(void)
0x18024a0d0  lea     rcx, [rbp+1D0h+Dacl]
0x18024a0d7  call    ?Close@?$Auto@U_ACL@@@Windows@@QEAAXXZ; Windows::Auto<_ACL>::Close(void)
0x18024a0dc  lea     rcx, [rbp+1D0h+Owner]
0x18024a0e3  call    ?Close@?$Auto@U_ACL@@@Windows@@QEAAXXZ; Windows::Auto<_ACL>::Close(void)
0x18024a0e8  jmp     loc_18024A2D6
  ... truncated ...
```
