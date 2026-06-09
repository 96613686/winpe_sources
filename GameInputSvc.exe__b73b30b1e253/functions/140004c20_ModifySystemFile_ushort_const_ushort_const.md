# ModifySystemFile(ushort const *,ushort const *)

- ea: `0x140004c20`
- end: `0x140005636`
- name: `?ModifySystemFile@@YAJPEBG0@Z`
- size: `2582`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName, LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140001e5c`
- `0x1400021f4`

## callees

- `0x140001008`
- `0x140004abc`
- `0x140004b48`
- `0x140004c20`
- `0x14000563c`
- `0x14000578c`
- `0x140007750`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004ca7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004d66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005061`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400051b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000528a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400052fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000537a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400053e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000548f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005513`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400055d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004ca7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004d66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004de2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005061`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400051b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000528a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400052fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000537a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400053e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000548f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005513`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400055d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400054e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400054e8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400055cc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400055cc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140005483`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140005483`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140004d58`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140004dd4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140004d58`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140004dd4`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x140005280`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x140005280`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x140005370`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x140005370`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x140004c94`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x140004c94`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1400052f4`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1400052f4`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1400053dc`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1400055f7`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1400053dc`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1400055f7`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x140005509`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x140005509`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000518f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000518f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140005053`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400051ac`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140005053`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400051ac`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x140004fab`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x140004fab`

## pseudocode

```c
__int64 __fastcall ModifySystemFile(LPCWSTR lpExistingFileName, LPCWSTR lpFileName)
{
  signed int LastError; // ebx
  int v4; // r8d
  int v5; // r9d
  const WCHAR *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  DWORD v9; // eax
  int v10; // r8d
  int v11; // r9d
  int v12; // r8d
  int v13; // r9d
  __int64 v15; // rdx
  __int64 v16; // r8
  int v17; // r9d
  int v18; // ecx
  char *v19; // rdx
  int v20; // r9d
  bool v21; // cc
  enum _SE_OBJECT_TYPE v22; // edx
  int v23; // r9d
  int v24; // ecx
  __int16 *v25; // rdx
  enum _SE_OBJECT_TYPE v26; // edx
  HANDLE v27; // rax
  DWORD v28; // eax
  int v29; // [rsp+40h] [rbp-C0h] BYREF
  int v30; // [rsp+44h] [rbp-BCh] BYREF
  const char *v31; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int FileAttributesW; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpFileNamea; // [rsp+58h] [rbp-A8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  int v35; // [rsp+68h] [rbp-98h] BYREF
  int v36; // [rsp+6Ch] [rbp-94h] BYREF
  int v37; // [rsp+70h] [rbp-90h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+78h] [rbp-88h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v40[8]; // [rsp+A0h] [rbp-60h] BYREF
  char v41; // [rsp+E0h] [rbp-20h]
  WCHAR TempFileName[264]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR Buffer[264]; // [rsp+300h] [rbp+200h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+510h] [rbp+410h] BYREF

  lpFileNamea = lpFileName;
  FileAttributesW = 0;
  ppSecurityDescriptor = 0;
  SecurityDescriptor = 0;
  v36 = 0;
  v35 = 0;
  v37 = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( GetFullPathNameW(lpFileName, 0x104u, Buffer, 0) - 1 > 0x103 )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_14000E000 > 2
      && (qword_14000E010 & 0x800) != 0
      && (qword_14000E018 & 0x800) == qword_14000E018 )
    {
      v29 = LastError;
      v31 = "onecore\\xbox\\gameinput\\published\\svc\\sfpmodify.cpp";
      v30 = 150;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_14000E018,
        (unsigned int)byte_14000B629,
        v4,
        v5,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29);
    }
LABEL_6:
    if ( LastError )
    {
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      return (unsigned int)-2147418113;
    }
    return (unsigned int)LastError;
  }
  v6 = Buffer;
  lpFileNamea = Buffer;
  if ( lpExistingFileName )
  {
    FileAttributesW = GetFileAttributesW(lpExistingFileName);
    if ( FileAttributesW == -1 )
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_14000E000 > 2
        && (qword_14000E010 & 0x800) != 0
        && (qword_14000E018 & 0x800) == qword_14000E018 )
      {
        v30 = LastError;
        v31 = "onecore\\xbox\\gameinput\\published\\svc\\sfpmodify.cpp";
        v29 = 157;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_14000E018,
          (unsigned int)byte_14000B5E9,
          v7,
          v8,
          (__int64)&v31,
          (__int64)&v29,
          (__int64)&v30);
      }
      goto LABEL_6;
    }
    v6 = lpFileNamea;
  }
  v9 = GetFileAttributesW(v6);
  FileAttributesW = v9;
  if ( v9 == -1 )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_14000E000 > 2
      && (qword_14000E010 & 0x800) != 0
      && (qword_14000E018 & 0x800) == qword_14000E018 )
    {
      v30 = LastError;
      v31 = "onecore\\xbox\\gameinput\\published\\svc\\sfpmodify.cpp";
      v29 = 161;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_14000E018,
        (unsigned int)byte_14000B5A9,
        v12,
        v13,
        (__int64)&v31,
        (__int64)&v29,
        (__int64)&v30);
    }
    goto LABEL_6;
  }
  if ( (v9 & 0x10) == 0 )
  {
    v40[0] = &v37;
    v40[1] = &v35;
    v40[2] = TempFileName;
    v40[3] = &lpFileNamea;
    v40[4] = &v36;
    v40[5] = &FileAttributesW;
    v40[6] = &ppSecurityDescriptor;
    v40[7] = &SecurityDescriptor;
    v41 = 1;
    LastError = EnableNecessaryPrivileges();
    if ( LastError < 0 )
    {
      if ( (unsigned int)dword_14000E000 <= 2 )
        goto LABEL_108;
      v16 = qword_14000E018;
      v15 = 2048;
      v18 = qword_14000E010;
      if ( (qword_14000E010 & 0x800) == 0 || (qword_14000E018 & 0x800) != qword_14000E018 )
        goto LABEL_108;
      v29 = 199;
      v19 = (char *)&dword_14000B52C;
      goto LABEL_54;
    }
    LastError = GetNamedSecurityInfoW(lpFileNamea, SE_FILE_OBJECT, 0xFu, 0, 0, 0, 0, &ppSecurityDescriptor);
    if ( LastError )
    {
      if ( (unsigned int)dword_14000E000 > 2 )
      {
        v16 = qword_14000E018;
        v15 = 2048;
        if ( (qword_14000E010 & 0x800) != 0 && (qword_14000E018 & 0x800) == qword_14000E018 )
        {
          v30 = LastError;
          v31 = "onecore\\xbox\\gameinput\\published\\svc\\sfpmodify.cpp";
          v29 = 214;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            qword_14000E010,
            (unsigned int)&dword_14000B4EC,
            qword_14000E018,
            v20,
            (__int64)&v31,
            (__int64)&v29,
            (__int64)&v30);
        }
      }
      v21 = LastError <= 0;
      goto LABEL_39;
    }
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"O:BA", 1u, &SecurityDescriptor, 0) )
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_14000E000 > 2 )
      {
        v24 = qword_14000E018;
        v15 = 2048;
        if ( (qword_14000E010 & 0x800) != 0 && (qword_14000E018 & 0x800) == qword_14000E018 )
        {
          v29 = 220;
          v25 = (__int16 *)&dword_14000B4AC;
LABEL_46:
          v31 = "onecore\\xbox\\gameinput\\published\\svc\\sfpmodify.cpp";
          v30 = LastError;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v24,
            (_DWORD)v25,
            v16,
            v23,
            (__int64)&v31,
            (__int64)&v29,
            (__int64)&v30);
          goto LABEL_47;
        }
      }
      goto LABEL_47;
    }
    LastError = SetObjectSD((LPWSTR)lpFileNamea, v22, SecurityDescriptor);
    if ( LastError >= 0 )
    {
      v36 = 1;
      LocalFree(SecurityDescriptor);
      SecurityDescriptor = 0;
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"O:BAG:BAD:(A;;GA;;;BA)", 1u, &SecurityDescriptor, 0) )
      {
        LastError = GetLastError();
        if ( (unsigned int)dword_14000E000 > 2 )
        {
          v24 = qword_14000E018;
          v15 = 2048;
          if ( (qword_14000E010 & 0x800) != 0 && (qword_14000E018 & 0x800) == qword_14000E018 )
          {
            v29 = 236;
            v25 = (__int16 *)&byte_14000B42F;
            goto LABEL_46;
          }
        }
LABEL_47:
        v21 = LastError <= 0;
        if ( !LastError )
        {
          LastError = -2147418113;
LABEL_108:
          utl::scope_exit__ModifySystemFile_::_2_::_lambda_1___::_scope_exit__ModifySystemFile_::_2_::_lambda_1___(
            v40,
            v15,
            v16);
          return (unsigned int)LastError;
        }
LABEL_39:
        if ( !v21 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_108;
      }
      LastError = SetObjectSD((LPWSTR)lpFileNamea, v26, SecurityDescriptor);
      if ( LastError >= 0 )
      {
        if ( (FileAttributesW & 3) != 0 && !SetFileAttributesW(lpFileNamea, 0x80u) )
        {
          LastError = GetLastError();
          if ( (unsigned int)dword_14000E000 > 2 )
          {
            v24 = qword_14000E018;
            v15 = 2048;
            if ( (qword_14000E010 & 0x800) != 0 && (qword_14000E018 & 0x800) == qword_14000E018 )
            {
              v29 = 245;
              v25 = word_14000B3B2;
              goto LABEL_46;
            }
          }
          goto LABEL_47;
        }
        if ( !GetVolumePathNameW(Buffer, szVolumePathName, 0x104u) )
        {
          LastError = GetLastError();
          if ( (unsigned int)dword_14000E000 > 2 )
          {
            v24 = qword_14000E018;
            v15 = 2048;
            if ( (qword_14000E010 & 0x800) != 0 && (qword_14000E018 & 0x800) == qword_14000E018 )
            {
              v29 = 256;
              v25 = word_14000B372;
              goto LABEL_46;
            }
          }
          goto LABEL_47;
        }
        szVolumePathName[259] = 0;
        if ( !GetTempFileNameW(szVolumePathName, L"WRP", 0, TempFileName) )
        {
          LastError = GetLastError();
          if ( (unsigned int)dword_14000E000 > 2 )
          {
            v24 = qword_14000E018;
            v15 = 2048;
            if ( (qword_14000E010 & 0x800) != 0 && (qword_14000E018 & 0x800) == qword_14000E018 )
            {
              v29 = 259;
              v25 = word_14000B332;
              goto LABEL_46;
            }
          }
          goto LABEL_47;
        }
        if ( !MoveFileExW(lpFileNamea, TempFileName, 1u) )
        {
          LastError = GetLastError();
          if ( (unsigned int)dword_14000E000 > 2 )
          {
            v24 = qword_14000E018;
            v15 = 2048;
            if ( (qword_14000E010 & 0x800) != 0 && (qword_14000E018 & 0x800) == qword_14000E018 )
            {
              v29 = 264;
              v25 = word_14000B2F2;
              goto LABEL_46;
            }
          }
          goto LABEL_47;
        }
        if ( !lpExistingFileName )
          goto LABEL_105;
        SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
        v35 = 1;
        SecurityAttributes.nLength = 24;
        SecurityAttributes.bInheritHandle = 0;
        v27 = CreateFileW(lpFileNamea, 0x40000000u, 3u, &SecurityAttributes, 1u, 0x2000000u, 0);
        if ( v27 == (HANDLE)-1LL )
        {
          LastError = GetLastError();
          if ( (unsigned int)dword_14000E000 > 2 )
          {
            v24 = qword_14000E018;
            v15 = 2048;
            if ( (qword_14000E010 & 0x800) != 0 && (qword_14000E018 & 0x800) == qword_14000E018 )
            {
              v29 = 288;
              v25 = word_14000B2B2;
              goto LABEL_46;
            }
          }
          goto LABEL_47;
        }
        CloseHandle(v27);
        if ( !CopyFileExW(lpExistingFileName, lpFileNamea, 0, 0, 0, 0x400000u) )
        {
          LastError = GetLastError();
          if ( (unsigned int)dword_14000E000 > 2 )
          {
            v24 = qword_14000E018;
            v15 = 2048;
            if ( (qword_14000E010 & 0x800) != 0 && (qword_14000E018 & 0x800) == qword_14000E018 )
            {
              v29 = 294;
              v25 = word_14000B272;
              goto LABEL_46;
            }
          }
          goto LABEL_47;
        }
        v35 = 0;
        LastError = SetFileAttributesAndAcl((LPWSTR)lpFileNamea, FileAttributesW, ppSecurityDescriptor);
        if ( LastError >= 0 )
        {
LABEL_105:
          if ( !DeleteFileW(TempFileName) )
          {
            v28 = GetLastError();
            if ( v28 == 5 || v28 == 32 || v28 == 1224 )
              MoveFileExW(TempFileName, 0, 4u);
          }
          v37 = 1;
          LastError = 0;
          goto LABEL_108;
        }
        if ( (unsigned int)dword_14000E000 <= 2 )
          goto LABEL_108;
        v16 = qword_14000E018;
        v15 = 2048;
        v18 = qword_14000E010;
        if ( (qword_14000E010 & 0x800) == 0 || (qword_14000E018 & 0x800) != qword_14000E018 )
          goto LABEL_108;
        v29 = 298;
        v19 = byte_14000B235;
      }
      else
      {
        if ( (unsigned int)dword_14000E000 <= 2 )
          goto LABEL_108;
        v16 = qword_14000E018;
        v15 = 2048;
        v18 = qword_14000E010;
        if ( (qword_14000E010 & 0x800) == 0 || (qword_14000E018 & 0x800) != qword_14000E018 )
          goto LABEL_108;
        v29 = 241;
        v19 = (char *)word_14000B3F2;
      }
    }
    else
    {
      if ( (unsigned int)dword_14000E000 <= 2 )
        goto LABEL_108;
      v16 = qword_14000E018;
      v15 = 2048;
      v18 = qword_14000E010;
      if ( (qword_14000E010 & 0x800) == 0 || (qword_14000E018 & 0x800) != qword_14000E018 )
        goto LABEL_108;
      v29 = 225;
      v19 = &byte_14000B46F;
    }
LABEL_54:
    v31 = "onecore\\xbox\\gameinput\\published\\svc\\sfpmodify.cpp";
    v30 = LastError;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v18,
      (_DWORD)v19,
      v16,
      v17,
      (__int64)&v31,
      (__int64)&v29,
      (__int64)&v30);
    goto LABEL_108;
  }
  if ( (unsigned int)dword_14000E000 > 2
    && (qword_14000E010 & 0x800) != 0
    && (qword_14000E018 & 0x800) == qword_14000E018 )
  {
    v30 = 2;
    v31 = "onecore\\xbox\\gameinput\\published\\svc\\sfpmodify.cpp";
    v29 = 165;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_14000E018,
      (unsigned int)byte_14000B569,
      v10,
      v11,
      (__int64)&v31,
      (__int64)&v29,
      (__int64)&v30);
  }
  return 2147942402LL;
}

```

## disassembly

```asm
0x140004c20  mov     [rsp-8+arg_10], rbx
0x140004c25  mov     [rsp-8+arg_18], rsi
0x140004c2a  push    rbp
0x140004c2b  push    rdi
0x140004c2c  push    r14
0x140004c2e  lea     rbp, [rsp-630h]
0x140004c36  sub     rsp, 730h
0x140004c3d  mov     rax, cs:__security_cookie
0x140004c44  xor     rax, rsp
0x140004c47  mov     [rbp+640h+var_20], rax
0x140004c4e  xor     esi, esi
0x140004c50  mov     [rsp+740h+lpFileName], rdx
0x140004c55  mov     rdi, rcx
0x140004c58  mov     [rsp+740h+var_6F0], esi
0x140004c5c  xor     ecx, ecx
0x140004c5e  mov     [rsp+740h+var_6C8], rsi
0x140004c63  mov     rax, rdx
0x140004c66  mov     qword ptr [rbp+640h+SecurityAttributes.bInheritHandle], rcx
0x140004c6a  xorps   xmm0, xmm0
0x140004c6d  mov     [rsp+740h+SecurityDescriptor], rsi
0x140004c72  mov     rcx, rax; lpFileName
0x140004c75  mov     [rsp+740h+var_6D4], esi
0x140004c79  xor     r9d, r9d; lpFilePart
0x140004c7c  mov     [rsp+740h+var_6D8], esi
0x140004c80  lea     r8, [rbp+640h+Buffer]; lpBuffer
0x140004c87  mov     [rsp+740h+var_6D0], esi
0x140004c8b  mov     edx, 104h; nBufferLength
0x140004c90  movups  xmmword ptr [rbp+640h+SecurityAttributes.nLength], xmm0
0x140004c94  call    cs:__imp_GetFullPathNameW
0x140004c9a  dec     eax
0x140004c9c  cmp     eax, 103h
0x140004ca1  jbe     loc_140004D41
0x140004ca7  call    cs:__imp_GetLastError
0x140004cad  mov     ebx, eax
0x140004caf  mov     eax, cs:dword_14000E000
0x140004cb5  cmp     eax, 2
0x140004cb8  jbe     short loc_140004D1F
0x140004cba  mov     rcx, cs:qword_14000E018
0x140004cc1  mov     edx, 800h
0x140004cc6  mov     rax, cs:qword_14000E010
0x140004ccd  test    rdx, rax
0x140004cd0  jz      short loc_140004D1F
0x140004cd2  mov     rax, rcx
0x140004cd5  and     rax, rdx
0x140004cd8  cmp     rax, rcx
0x140004cdb  jnz     short loc_140004D1F
0x140004cdd  lea     rax, aOnecoreXboxGam_5; "onecore\\xbox\\gameinput\\published\\sv"...
0x140004ce4  mov     [rsp+740h+var_700], ebx
0x140004ce8  mov     [rsp+740h+var_6F8], rax
0x140004ced  lea     rdx, byte_14000B629
0x140004cf4  lea     rax, [rsp+740h+var_700]
0x140004cf9  mov     [rsp+740h+var_6FC], 96h
0x140004d01  mov     [rsp+740h+ppSacl], rax
0x140004d06  lea     rax, [rsp+740h+var_6FC]
0x140004d0b  mov     [rsp+740h+ppDacl], rax
0x140004d10  lea     rax, [rsp+740h+var_6F8]
0x140004d15  mov     [rsp+740h+ppsidGroup], rax
0x140004d1a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140004d1f  test    ebx, ebx
0x140004d21  jnz     short loc_140004D2D
0x140004d23  mov     ebx, 8000FFFFh
0x140004d28  jmp     loc_14000560D
0x140004d2d  jle     loc_14000560D
0x140004d33  movzx   ebx, bx
0x140004d36  or      ebx, 80070000h
0x140004d3c  jmp     loc_14000560D
0x140004d41  or      ebx, 0FFFFFFFFh
0x140004d44  lea     rcx, [rbp+640h+Buffer]
0x140004d4b  mov     [rsp+740h+lpFileName], rcx
0x140004d50  test    rdi, rdi
0x140004d53  jz      short loc_140004DD4
0x140004d55  mov     rcx, rdi; lpFileName
0x140004d58  call    cs:__imp_GetFileAttributesW
0x140004d5e  mov     [rsp+740h+var_6F0], eax
0x140004d62  cmp     eax, ebx
0x140004d64  jnz     short loc_140004DCF
0x140004d66  call    cs:__imp_GetLastError
0x140004d6c  mov     ebx, eax
0x140004d6e  mov     eax, cs:dword_14000E000
0x140004d74  cmp     eax, 2
0x140004d77  jbe     short loc_140004D1F
0x140004d79  mov     rcx, cs:qword_14000E018
0x140004d80  mov     edx, 800h
0x140004d85  mov     rax, cs:qword_14000E010
0x140004d8c  test    rdx, rax
0x140004d8f  jz      short loc_140004D1F
0x140004d91  mov     rax, rcx
0x140004d94  and     rax, rdx
0x140004d97  cmp     rax, rcx
0x140004d9a  jnz     short loc_140004D1F
0x140004d9c  lea     rax, aOnecoreXboxGam_5; "onecore\\xbox\\gameinput\\published\\sv"...
0x140004da3  mov     [rsp+740h+var_6FC], ebx
0x140004da7  mov     [rsp+740h+var_6F8], rax
0x140004dac  lea     rdx, byte_14000B5E9
0x140004db3  lea     rax, [rsp+740h+var_6FC]
0x140004db8  mov     [rsp+740h+var_700], 9Dh
0x140004dc0  mov     [rsp+740h+ppSacl], rax
0x140004dc5  lea     rax, [rsp+740h+var_700]
0x140004dca  jmp     loc_140004D0B
0x140004dcf  mov     rcx, [rsp+740h+lpFileName]; lpFileName
0x140004dd4  call    cs:__imp_GetFileAttributesW
0x140004dda  mov     [rsp+740h+var_6F0], eax
0x140004dde  cmp     eax, ebx
0x140004de0  jnz     short loc_140004E57
0x140004de2  call    cs:__imp_GetLastError
0x140004de8  mov     ebx, eax
0x140004dea  mov     eax, cs:dword_14000E000
0x140004df0  cmp     eax, 2
0x140004df3  jbe     loc_140004D1F
0x140004df9  mov     rcx, cs:qword_14000E018
0x140004e00  mov     edx, 800h
0x140004e05  mov     rax, cs:qword_14000E010
0x140004e0c  test    rdx, rax
0x140004e0f  jz      loc_140004D1F
0x140004e15  mov     rax, rcx
0x140004e18  and     rax, rdx
0x140004e1b  cmp     rax, rcx
0x140004e1e  jnz     loc_140004D1F
0x140004e24  lea     rax, aOnecoreXboxGam_5; "onecore\\xbox\\gameinput\\published\\sv"...
0x140004e2b  mov     [rsp+740h+var_6FC], ebx
0x140004e2f  mov     [rsp+740h+var_6F8], rax
0x140004e34  lea     rdx, byte_14000B5A9
0x140004e3b  lea     rax, [rsp+740h+var_6FC]
0x140004e40  mov     [rsp+740h+var_700], 0A1h
0x140004e48  mov     [rsp+740h+ppSacl], rax
0x140004e4d  lea     rax, [rsp+740h+var_700]
0x140004e52  jmp     loc_140004D0B
0x140004e57  test    al, 10h
0x140004e59  jz      short loc_140004ED9
0x140004e5b  mov     eax, cs:dword_14000E000
0x140004e61  cmp     eax, 2
0x140004e64  jbe     short loc_140004ECF
0x140004e66  mov     rcx, cs:qword_14000E018
0x140004e6d  mov     edx, 800h
0x140004e72  mov     rax, cs:qword_14000E010
0x140004e79  test    rdx, rax
0x140004e7c  jz      short loc_140004ECF
0x140004e7e  mov     rax, rcx
0x140004e81  and     rax, rdx
0x140004e84  cmp     rax, rcx
0x140004e87  jnz     short loc_140004ECF
0x140004e89  lea     rax, aOnecoreXboxGam_5; "onecore\\xbox\\gameinput\\published\\sv"...
0x140004e90  mov     [rsp+740h+var_6FC], 2
0x140004e98  mov     [rsp+740h+var_6F8], rax
0x140004e9d  lea     rdx, byte_14000B569
0x140004ea4  lea     rax, [rsp+740h+var_6FC]
0x140004ea9  mov     [rsp+740h+var_700], 0A5h
0x140004eb1  mov     [rsp+740h+ppSacl], rax
0x140004eb6  lea     rax, [rsp+740h+var_700]
0x140004ebb  mov     [rsp+740h+ppDacl], rax
0x140004ec0  lea     rax, [rsp+740h+var_6F8]
0x140004ec5  mov     [rsp+740h+ppsidGroup], rax
0x140004eca  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140004ecf  mov     eax, 80070002h
0x140004ed4  jmp     loc_14000560F
0x140004ed9  lea     rax, [rsp+740h+var_6D0]
0x140004ede  mov     r14d, 1
0x140004ee4  mov     [rbp+640h+var_6A0], rax
0x140004ee8  lea     rax, [rsp+740h+var_6D8]
0x140004eed  mov     [rbp+640h+var_698], rax
0x140004ef1  lea     rax, [rbp+640h+TempFileName]
0x140004ef5  mov     [rbp+640h+var_690], rax
0x140004ef9  lea     rax, [rsp+740h+lpFileName]
0x140004efe  mov     [rbp+640h+var_688], rax
0x140004f02  lea     rax, [rsp+740h+var_6D4]
0x140004f07  mov     [rbp+640h+var_680], rax
0x140004f0b  lea     rax, [rsp+740h+var_6F0]
0x140004f10  mov     [rbp+640h+var_678], rax
0x140004f14  lea     rax, [rsp+740h+var_6C8]
0x140004f19  mov     [rbp+640h+var_670], rax
0x140004f1d  lea     rax, [rsp+740h+SecurityDescriptor]
0x140004f22  mov     [rbp+640h+var_668], rax
0x140004f26  mov     [rbp+640h+var_660], r14b
0x140004f2a  call    ?EnableNecessaryPrivileges@@YAJXZ; EnableNecessaryPrivileges(void)
0x140004f2f  mov     ebx, eax
0x140004f31  test    eax, eax
0x140004f33  jns     short loc_140004F83
0x140004f35  mov     ecx, cs:dword_14000E000
0x140004f3b  cmp     ecx, 2
0x140004f3e  jbe     loc_140005604
0x140004f44  mov     r8, cs:qword_14000E018
0x140004f4b  mov     edx, 800h
0x140004f50  mov     rcx, cs:qword_14000E010
0x140004f57  test    rdx, rcx
0x140004f5a  jz      loc_140005604
0x140004f60  mov     rax, r8
0x140004f63  and     rax, rdx
0x140004f66  cmp     rax, r8
0x140004f69  jnz     loc_140005604
0x140004f6f  mov     [rsp+740h+var_700], 0C7h
0x140004f77  lea     rdx, dword_14000B52C
0x140004f7e  jmp     loc_14000514D
0x140004f83  mov     rcx, [rsp+740h+lpFileName]; pObjectName
0x140004f88  lea     rax, [rsp+740h+var_6C8]
0x140004f8d  mov     [rsp+740h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x140004f92  xor     r9d, r9d; ppsidOwner
0x140004f95  mov     [rsp+740h+ppSacl], rsi; ppSacl
0x140004f9a  mov     edx, r14d; ObjectType
0x140004f9d  mov     [rsp+740h+ppDacl], rsi; ppDacl
0x140004fa2  mov     [rsp+740h+ppsidGroup], rsi; ppsidGroup
0x140004fa7  lea     r8d, [r9+0Fh]; SecurityInfo
0x140004fab  call    cs:__imp_GetNamedSecurityInfoW
0x140004fb1  mov     ebx, eax
0x140004fb3  test    eax, eax
0x140004fb5  jz      loc_140005041
0x140004fbb  mov     ecx, cs:dword_14000E000
0x140004fc1  cmp     ecx, 2
0x140004fc4  jbe     short loc_14000502B
0x140004fc6  mov     r8, cs:qword_14000E018
0x140004fcd  mov     edx, 800h
0x140004fd2  mov     rcx, cs:qword_14000E010
0x140004fd9  test    rdx, rcx
0x140004fdc  jz      short loc_14000502B
0x140004fde  mov     rax, r8
0x140004fe1  and     rax, rdx
0x140004fe4  cmp     rax, r8
0x140004fe7  jnz     short loc_14000502B
0x140004fe9  lea     rax, aOnecoreXboxGam_5; "onecore\\xbox\\gameinput\\published\\sv"...
0x140004ff0  mov     [rsp+740h+var_6FC], ebx
0x140004ff4  mov     [rsp+740h+var_6F8], rax
0x140004ff9  lea     rdx, dword_14000B4EC
0x140005000  lea     rax, [rsp+740h+var_6FC]
0x140005005  mov     [rsp+740h+var_700], 0D6h
0x14000500d  mov     [rsp+740h+ppSacl], rax
0x140005012  lea     rax, [rsp+740h+var_700]
0x140005017  mov     [rsp+740h+ppDacl], rax
0x14000501c  lea     rax, [rsp+740h+var_6F8]
0x140005021  mov     [rsp+740h+ppsidGroup], rax
0x140005026  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000502b  test    ebx, ebx
0x14000502d  jle     loc_140005604
0x140005033  movzx   ebx, bx
0x140005036  or      ebx, 80070000h
0x14000503c  jmp     loc_140005604
0x140005041  xor     r9d, r9d; SecurityDescriptorSize
0x140005044  lea     r8, [rsp+740h+SecurityDescriptor]; SecurityDescriptor
0x140005049  mov     edx, r14d; StringSDRevision
0x14000504c  lea     rcx, StringSecurityDescriptor; "O:BA"
0x140005053  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140005059  test    eax, eax
0x14000505b  jnz     loc_1400050EB
0x140005061  call    cs:__imp_GetLastError
0x140005067  mov     ebx, eax
0x140005069  mov     eax, cs:dword_14000E000
0x14000506f  cmp     eax, 2
0x140005072  jbe     short loc_1400050D9
0x140005074  mov     rcx, cs:qword_14000E018
0x14000507b  mov     edx, 800h
0x140005080  mov     rax, cs:qword_14000E010
0x140005087  test    rdx, rax
0x14000508a  jz      short loc_1400050D9
0x14000508c  mov     rax, rcx
0x14000508f  and     rax, rdx
0x140005092  cmp     rax, rcx
0x140005095  jnz     short loc_1400050D9
0x140005097  mov     [rsp+740h+var_700], 0DCh
0x14000509f  lea     rdx, dword_14000B4AC
0x1400050a6  lea     rax, aOnecoreXboxGam_5; "onecore\\xbox\\gameinput\\published\\sv"...
0x1400050ad  mov     [rsp+740h+var_6F8], rax
0x1400050b2  lea     rax, [rsp+740h+var_6FC]
0x1400050b7  mov     [rsp+740h+ppSacl], rax
0x1400050bc  lea     rax, [rsp+740h+var_700]
0x1400050c1  mov     [rsp+740h+ppDacl], rax
0x1400050c6  lea     rax, [rsp+740h+var_6F8]
0x1400050cb  mov     [rsp+740h+ppsidGroup], rax
0x1400050d0  mov     [rsp+740h+var_6FC], ebx
0x1400050d4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400050d9  test    ebx, ebx
0x1400050db  jnz     loc_14000502D
0x1400050e1  mov     ebx, 8000FFFFh
0x1400050e6  jmp     loc_140005604
0x1400050eb  mov     r8, [rsp+740h+SecurityDescriptor]; void *
0x1400050f0  mov     rcx, [rsp+740h+lpFileName]; pObjectName
0x1400050f5  call    ?SetObjectSD@@YAJPEBGW4_SE_OBJECT_TYPE@@PEAX@Z; SetObjectSD(ushort const *,_SE_OBJECT_TYPE,void *)
0x1400050fa  mov     ebx, eax
0x1400050fc  test    eax, eax
0x1400050fe  jns     loc_140005185
0x140005104  mov     ecx, cs:dword_14000E000
0x14000510a  cmp     ecx, 2
0x14000510d  jbe     loc_140005604
0x140005113  mov     r8, cs:qword_14000E018
0x14000511a  mov     edx, 800h
0x14000511f  mov     rcx, cs:qword_14000E010
0x140005126  test    rdx, rcx
0x140005129  jz      loc_140005604
0x14000512f  mov     rax, r8
0x140005132  and     rax, rdx
0x140005135  cmp     rax, r8
0x140005138  jnz     loc_140005604
0x14000513e  mov     [rsp+740h+var_700], 0E1h
0x140005146  lea     rdx, byte_14000B46F
0x14000514d  lea     rax, aOnecoreXboxGam_5; "onecore\\xbox\\gameinput\\published\\sv"...
0x140005154  mov     [rsp+740h+var_6F8], rax
0x140005159  lea     rax, [rsp+740h+var_6FC]
0x14000515e  mov     [rsp+740h+ppSacl], rax
0x140005163  lea     rax, [rsp+740h+var_700]
0x140005168  mov     [rsp+740h+ppDacl], rax
0x14000516d  lea     rax, [rsp+740h+var_6F8]
0x140005172  mov     [rsp+740h+ppsidGroup], rax
0x140005177  mov     [rsp+740h+var_6FC], ebx
  ... truncated ...
```
