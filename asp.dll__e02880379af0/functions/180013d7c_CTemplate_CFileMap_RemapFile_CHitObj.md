# CTemplate::CFileMap::RemapFile(CHitObj *)

- ea: `0x180013d7c`
- end: `0x180013efc`
- name: `?RemapFile@CFileMap@CTemplate@@QEAAXPEAVCHitObj@@@Z`
- size: `384`
- prototype: `void __fastcall(CTemplate::CFileMap *__hidden this, struct CHitObj *)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001650c`
- `0x18005cf30`
- `0x18005d508`

## callees

- `0x180013d7c`
- `0x180013f04`
- `0x180013fd0`
- `0x180014bf0`
- `0x180016b50`
- `0x180019e7c`
- `0x180023dd0`
- `0x18005f5d8`
- `0x18005f6d4`
- `0x18005f7d0`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x180013ec5`
- `KERNEL32!MapViewOfFile` at `0x180013ec5`
- `KERNEL32!CreateFileMappingW` at `0x180013e96`
- `KERNEL32!CreateFileMappingW` at `0x180013e96`
- `KERNEL32!GetFileAttributesExW` at `0x18002be33`
- `KERNEL32!GetFileAttributesExW` at `0x18002be33`
- `KERNEL32!RaiseException` at `0x18002bdeb`
- `KERNEL32!RaiseException` at `0x18002bff6`
- `KERNEL32!RaiseException` at `0x18002bdeb`
- `KERNEL32!RaiseException` at `0x18002bff6`
- `KERNEL32!CloseHandle` at `0x18002bfb2`
- `KERNEL32!CloseHandle` at `0x18002bfcc`
- `KERNEL32!CloseHandle` at `0x18002bfdf`
- `KERNEL32!CloseHandle` at `0x18002bfb2`
- `KERNEL32!CloseHandle` at `0x18002bfcc`
- `KERNEL32!CloseHandle` at `0x18002bfdf`
- `KERNEL32!GetLastError` at `0x18002be0a`
- `KERNEL32!GetLastError` at `0x18002be3d`
- `KERNEL32!GetLastError` at `0x18002be0a`
- `KERNEL32!GetLastError` at `0x18002be3d`
- `iisutil!PuDbgPrint` at `0x18002be9b`
- `iisutil!PuDbgPrint` at `0x18002beea`
- `iisutil!PuDbgPrint` at `0x18002bf97`
- `iisutil!PuDbgPrint` at `0x18002be9b`
- `iisutil!PuDbgPrint` at `0x18002beea`
- `iisutil!PuDbgPrint` at `0x18002bf97`

## string_xrefs

- `0x18002be94`: `inetsrv\iis\svcs\cmp\asp\template.cpp`
- `0x18002becc`: `inetsrv\iis\svcs\cmp\asp\template.cpp`
- `0x18002bf79`: `inetsrv\iis\svcs\cmp\asp\template.cpp`
- `0x18002bede`: `Failed to open file %S because it is a directory.\n`
- `0x18002be82`: `CTemplate::CFileMap::RemapFile`
- `0x18002bebe`: `CTemplate::CFileMap::RemapFile`
- `0x18002bf6b`: `CTemplate::CFileMap::RemapFile`
- `0x18002be7b`: `ASP could not retrieve file attributes even though it could open the file.\n`

## pseudocode

```c
void __fastcall CTemplate::CFileMap::RemapFile(CTemplate::CFileMap *this, struct CHitObj *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdi
  unsigned __int64 v6; // rax
  const struct _GUID *v7; // rdx
  unsigned int v8; // r8d
  struct _SECURITY_ATTRIBUTES *v9; // r9
  void *File; // rax
  HANDLE FileMappingW; // rax
  void *v12; // rcx
  LPVOID v13; // rax
  const WCHAR *v14; // rcx
  const struct _GUID *v15; // rdx
  DWORD v16; // ecx
  const struct _GUID *v17; // rdx
  void *v18; // rdx
  const unsigned __int16 *v19; // rcx
  char *v20; // rcx
  char *v21; // rcx
  void *v22; // rcx
  unsigned int dwMaximumSizeLow; // [rsp+20h] [rbp-60h]
  unsigned int lpName; // [rsp+28h] [rbp-58h]
  void *v25; // [rsp+30h] [rbp-50h]
  unsigned int v26; // [rsp+40h] [rbp-40h] BYREF
  _OWORD FileInformation[2]; // [rsp+48h] [rbp-38h] BYREF
  int v28; // [rsp+68h] [rbp-18h]

  v26 = 0;
  if ( !*((_QWORD *)this + 6) )
  {
    v4 = *((_QWORD *)this + 1);
    v5 = 0;
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(v4 + 2 * v6) );
    if ( v6 >= 0x104 )
      RaiseException(0x8000D001, 0, 0, 0);
    *((_DWORD *)this + 19) ^= ((unsigned __int8)IsFileUNC(*((const unsigned __int16 **)this + 1), (int *)&v26)
                             ^ (unsigned __int8)*((_DWORD *)this + 19))
                            & 1;
    if ( a2 )
    {
      v5 = *((_QWORD *)a2 + 8);
      if ( v5 )
      {
        if ( (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                             *(struct _EXTENSION_CONTROL_BLOCK **)(v5 + 8),
                             4u) )
          AspReqEvents::ASP_READ_FILE::RaiseEvent(
            *(struct _EXTENSION_CONTROL_BLOCK **)(v5 + 8),
            v7,
            *((const unsigned __int16 **)this + 1));
      }
    }
    File = AspCreateFile(
             *((const unsigned __int16 **)this + 1),
             (unsigned int)v7,
             v8,
             v9,
             dwMaximumSizeLow,
             lpName,
             v25);
    *((_QWORD *)this + 4) = File;
    if ( File != (void *)-1LL )
    {
      v26 = 0;
      if ( AspGetFileAttributes(
             *((const unsigned __int16 **)this + 1),
             File,
             (struct _FILETIME *)this + 10,
             (unsigned int *)this + 32,
             &v26) >= 0 )
      {
        *((_DWORD *)this + 19) &= ~2u;
        *((_DWORD *)this + 19) |= (v26 >> 13) & 2;
        if ( (*((_BYTE *)this + 76) & 1) != 0 || (unsigned int)CTemplate::CFileMap::GetSecurityDescriptor(this) )
        {
          FileMappingW = CreateFileMappingW(*((HANDLE *)this + 4), 0, 2u, 0, 0, 0);
          *((_QWORD *)this + 5) = FileMappingW;
          if ( FileMappingW )
          {
LABEL_15:
            v12 = (void *)*((_QWORD *)this + 5);
            if ( v12 )
            {
              v13 = MapViewOfFile(v12, 4u, 0, 0, 0);
              *((_QWORD *)this + 6) = v13;
              if ( v13 )
                return;
              v21 = (char *)*((_QWORD *)this + 4);
              if ( (unsigned __int64)(v21 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              {
                CloseHandle(v21);
                *((_QWORD *)this + 4) = 0;
              }
              v22 = (void *)*((_QWORD *)this + 5);
              if ( v22 )
              {
                CloseHandle(v22);
                *((_QWORD *)this + 5) = 0;
              }
            }
            goto LABEL_45;
          }
          v18 = (void *)*((_QWORD *)this + 4);
          v19 = (const unsigned __int16 *)*((_QWORD *)this + 1);
          v26 = 0;
          if ( AspGetFileAttributes(v19, v18, 0, &v26, 0) >= 0 )
          {
            if ( !v26 )
            {
              if ( (g_dwDebugFlags & 3) != 0 )
                PuDbgPrint(
                  g_pDebug,
                  "inetsrv\\iis\\svcs\\cmp\\asp\\template.cpp",
                  10279,
                  "CTemplate::CFileMap::RemapFile",
                  "Empty source file %S\n",
                  *((const wchar_t **)this + 1));
              v16 = -2147430398;
              goto LABEL_46;
            }
            goto LABEL_15;
          }
          v20 = (char *)*((_QWORD *)this + 4);
          if ( (unsigned __int64)(v20 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            CloseHandle(v20);
            *((_QWORD *)this + 4) = 0;
          }
        }
LABEL_45:
        v16 = -2147430399;
        goto LABEL_46;
      }
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\cmp\\asp\\template.cpp",
          10239,
          "CTemplate::CFileMap::RemapFile",
          "ASP could not retrieve file attributes even though it could open the file.\n");
      goto LABEL_25;
    }
    if ( GetLastError() == 5 )
    {
      v14 = (const WCHAR *)*((_QWORD *)this + 1);
      v28 = 0;
      memset(FileInformation, 0, sizeof(FileInformation));
      if ( !GetFileAttributesExW(v14, GetFileExInfoStandard, FileInformation) )
      {
        if ( GetLastError() != 5 )
        {
LABEL_25:
          v16 = -2147467259;
          goto LABEL_46;
        }
        if ( v5
          && (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                             *(struct _EXTENSION_CONTROL_BLOCK **)(v5 + 8),
                             2u) )
        {
          AspReqEvents::ASP_FILE_ACCESS_DENIED::RaiseEvent(
            *(struct _EXTENSION_CONTROL_BLOCK **)(v5 + 8),
            v15,
            *((const unsigned __int16 **)this + 1));
        }
LABEL_24:
        v16 = -2147430396;
LABEL_46:
        RaiseException(v16, 0, 0, 0);
        return;
      }
      if ( (FileInformation[0] & 0x10) == 0 )
        goto LABEL_24;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\cmp\\asp\\template.cpp",
          10161,
          "CTemplate::CFileMap::RemapFile",
          "Failed to open file %S because it is a directory.\n",
          *((const wchar_t **)this + 1));
    }
    if ( v5
      && (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                         *(struct _EXTENSION_CONTROL_BLOCK **)(v5 + 8),
                         2u) )
    {
      AspReqEvents::ASP_FILE_NOT_FOUND::RaiseEvent(
        *(struct _EXTENSION_CONTROL_BLOCK **)(v5 + 8),
        v17,
        *((const unsigned __int16 **)this + 1));
    }
    goto LABEL_45;
  }
}

```

## disassembly

```asm
0x180013d7c  mov     [rsp-18h+arg_10], rbx
0x180013d81  mov     [rsp-18h+arg_18], rsi
0x180013d86  push    rbp
0x180013d87  push    rdi
0x180013d88  push    r14
0x180013d8a  mov     rbp, rsp
0x180013d8d  sub     rsp, 80h
0x180013d94  mov     rax, cs:__security_cookie
0x180013d9b  xor     rax, rsp
0x180013d9e  mov     [rbp+var_10], rax
0x180013da2  xor     r14d, r14d
0x180013da5  mov     rsi, rdx
0x180013da8  mov     rbx, rcx
0x180013dab  mov     [rbp+var_40], r14d
0x180013daf  cmp     [rcx+30h], r14
0x180013db3  jnz     loc_180013ED8
0x180013db9  mov     rcx, [rcx+8]
0x180013dbd  mov     edi, r14d
0x180013dc0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013dc4  inc     rax
0x180013dc7  cmp     [rcx+rax*2], r14w
0x180013dcc  jnz     short loc_180013DC4
0x180013dce  cmp     rax, 104h
0x180013dd4  jnb     loc_18002BDDE
0x180013dda  mov     rcx, [rbx+8]; unsigned __int16 *
0x180013dde  lea     rdx, [rbp+var_40]; int *
0x180013de2  call    ?IsFileUNC@@YAHPEBGAEAJ@Z; IsFileUNC(ushort const *,long &)
0x180013de7  mov     ecx, [rbx+4Ch]
0x180013dea  xor     ecx, eax
0x180013dec  and     ecx, 1
0x180013def  xor     [rbx+4Ch], ecx
0x180013df2  test    rsi, rsi
0x180013df5  jz      short loc_180013E16
0x180013df7  mov     rdi, [rsi+40h]
0x180013dfb  test    rdi, rdi
0x180013dfe  jz      short loc_180013E16
0x180013e00  mov     rcx, [rdi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x180013e04  mov     edx, 4; unsigned int
0x180013e09  call    ?CheckTracingEnabled@ActiveServerPagesASPTraceProvider@@SAHPEAU_EXTENSION_CONTROL_BLOCK@@K@Z; ActiveServerPagesASPTraceProvider::CheckTracingEnabled(_EXTENSION_CONTROL_BLOCK *,ulong)
0x180013e0e  test    eax, eax
0x180013e10  jnz     loc_18002BDF7
0x180013e16  mov     rcx, [rbx+8]; unsigned __int16 *
0x180013e1a  call    ?AspCreateFile@@YAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; AspCreateFile(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x180013e1f  mov     [rbx+20h], rax
0x180013e23  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013e27  jz      loc_18002BE0A
0x180013e2d  lea     rcx, [rbp+var_40]
0x180013e31  mov     [rbp+var_40], r14d
0x180013e35  mov     qword ptr [rsp+80h+dwMaximumSizeLow], rcx; unsigned int *
0x180013e3a  lea     r9, [rbx+80h]; unsigned int *
0x180013e41  mov     rcx, [rbx+8]; unsigned __int16 *
0x180013e45  lea     r8, [rbx+50h]; struct _FILETIME *
0x180013e49  mov     rdx, rax; void *
0x180013e4c  call    ?AspGetFileAttributes@@YAJPEBGPEAXPEAU_FILETIME@@PEAK3@Z; AspGetFileAttributes(ushort const *,void *,_FILETIME *,ulong *,ulong *)
0x180013e51  test    eax, eax
0x180013e53  js      loc_18002BF21
0x180013e59  and     dword ptr [rbx+4Ch], 0FFFFFFFDh
0x180013e5d  mov     eax, [rbp+var_40]
0x180013e60  shr     eax, 0Dh
0x180013e63  and     eax, 2
0x180013e66  or      [rbx+4Ch], eax
0x180013e69  test    byte ptr [rbx+4Ch], 1
0x180013e6d  jnz     short loc_180013E7F
0x180013e6f  mov     rcx, rbx; this
0x180013e72  call    ?GetSecurityDescriptor@CFileMap@CTemplate@@QEAAHXZ; CTemplate::CFileMap::GetSecurityDescriptor(void)
0x180013e77  test    eax, eax
0x180013e79  jz      loc_18002BFE9
0x180013e7f  mov     rcx, [rbx+20h]; hFile
0x180013e83  xor     r9d, r9d; dwMaximumSizeHigh
0x180013e86  mov     [rsp+80h+lpName], r14; lpName
0x180013e8b  xor     edx, edx; lpFileMappingAttributes
0x180013e8d  mov     [rsp+80h+dwMaximumSizeLow], r14d; dwMaximumSizeLow
0x180013e92  lea     r8d, [r9+2]; flProtect
0x180013e96  call    cs:__imp_CreateFileMappingW
0x180013e9c  mov     [rbx+28h], rax
0x180013ea0  test    rax, rax
0x180013ea3  jz      loc_18002BF33
0x180013ea9  mov     rcx, [rbx+28h]; hFileMappingObject
0x180013ead  test    rcx, rcx
0x180013eb0  jz      loc_18002BFE9
0x180013eb6  xor     r9d, r9d; dwFileOffsetLow
0x180013eb9  mov     qword ptr [rsp+80h+dwMaximumSizeLow], r14; dwNumberOfBytesToMap
0x180013ebe  xor     r8d, r8d; dwFileOffsetHigh
0x180013ec1  lea     edx, [r9+4]; dwDesiredAccess
0x180013ec5  call    cs:__imp_MapViewOfFile
0x180013ecb  mov     [rbx+30h], rax
0x180013ecf  test    rax, rax
0x180013ed2  jz      loc_18002BFBE
0x180013ed8  mov     rcx, [rbp+var_10]
0x180013edc  xor     rcx, rsp; StackCookie
0x180013edf  call    __security_check_cookie
0x180013ee4  lea     r11, [rsp+80h+var_s0]
0x180013eec  mov     rbx, [r11+30h]
0x180013ef0  mov     rsi, [r11+38h]
0x180013ef4  mov     rsp, r11
0x180013ef7  pop     r14
0x180013ef9  pop     rdi
0x180013efa  pop     rbp
0x180013efb  retn
0x18002bdde  xor     r9d, r9d; lpArguments
0x18002bde1  xor     r8d, r8d; nNumberOfArguments
0x18002bde4  xor     edx, edx; dwExceptionFlags
0x18002bde6  mov     ecx, 8000D001h; dwExceptionCode
0x18002bdeb  call    cs:__imp_RaiseException
0x18002bdf1  nop
0x18002bdf2  jmp     loc_180013DDA
0x18002bdf7  mov     r8, [rbx+8]; unsigned __int16 *
0x18002bdfb  mov     rcx, [rdi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x18002bdff  call    ?RaiseEvent@ASP_READ_FILE@AspReqEvents@@SAJPEAU_EXTENSION_CONTROL_BLOCK@@PEBU_GUID@@PEBG@Z; AspReqEvents::ASP_READ_FILE::RaiseEvent(_EXTENSION_CONTROL_BLOCK *,_GUID const *,ushort const *)
0x18002be04  nop
0x18002be05  jmp     loc_180013E16
0x18002be0a  call    cs:__imp_GetLastError
0x18002be10  cmp     eax, 5
0x18002be13  jnz     loc_18002BEF0
0x18002be19  mov     rcx, [rbx+8]; lpFileName
0x18002be1d  lea     r8, [rbp+FileInformation]; lpFileInformation
0x18002be21  xorps   xmm0, xmm0
0x18002be24  xor     eax, eax
0x18002be26  xor     edx, edx; fInfoLevelId
0x18002be28  mov     [rbp+var_18], eax
0x18002be2b  movups  [rbp+FileInformation], xmm0
0x18002be2f  movups  [rbp+var_28], xmm0
0x18002be33  call    cs:__imp_GetFileAttributesExW
0x18002be39  test    eax, eax
0x18002be3b  jnz     short loc_18002BEAB
0x18002be3d  call    cs:__imp_GetLastError
0x18002be43  cmp     eax, 5
0x18002be46  jnz     short loc_18002BEA1
0x18002be48  test    rdi, rdi
0x18002be4b  jz      short loc_18002BE6A
0x18002be4d  mov     rcx, [rdi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x18002be51  lea     edx, [rax-3]; unsigned int
0x18002be54  call    ?CheckTracingEnabled@ActiveServerPagesASPTraceProvider@@SAHPEAU_EXTENSION_CONTROL_BLOCK@@K@Z; ActiveServerPagesASPTraceProvider::CheckTracingEnabled(_EXTENSION_CONTROL_BLOCK *,ulong)
0x18002be59  test    eax, eax
0x18002be5b  jz      short loc_18002BE6A
0x18002be5d  mov     r8, [rbx+8]; unsigned __int16 *
0x18002be61  mov     rcx, [rdi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x18002be65  call    ?RaiseEvent@ASP_FILE_ACCESS_DENIED@AspReqEvents@@SAJPEAU_EXTENSION_CONTROL_BLOCK@@PEBU_GUID@@PEBG@Z; AspReqEvents::ASP_FILE_ACCESS_DENIED::RaiseEvent(_EXTENSION_CONTROL_BLOCK *,_GUID const *,ushort const *)
0x18002be6a  mov     ecx, 8000D004h
0x18002be6f  jmp     loc_18002BFEE
0x18002be74  mov     rcx, cs:g_pDebug
0x18002be7b  lea     rax, aAspCouldNotRet; "ASP could not retrieve file attributes "...
0x18002be82  lea     r9, aCtemplateCfile; "CTemplate::CFileMap::RemapFile"
0x18002be89  mov     qword ptr [rsp+80h+dwMaximumSizeLow], rax
0x18002be8e  mov     r8d, 27FFh
0x18002be94  lea     rdx, aInetsrvIisSvcs_4; "inetsrv\\iis\\svcs\\cmp\\asp\\template."...
0x18002be9b  call    cs:__imp_PuDbgPrint
0x18002bea1  mov     ecx, 80004005h
0x18002bea6  jmp     loc_18002BFEE
0x18002beab  test    byte ptr [rbp+FileInformation], 10h
0x18002beaf  jz      short loc_18002BE6A
0x18002beb1  test    byte ptr cs:g_dwDebugFlags, 3
0x18002beb8  jz      short loc_18002BEF0
0x18002beba  mov     rax, [rbx+8]
0x18002bebe  lea     r9, aCtemplateCfile; "CTemplate::CFileMap::RemapFile"
0x18002bec5  mov     rcx, cs:g_pDebug
0x18002becc  lea     rdx, aInetsrvIisSvcs_4; "inetsrv\\iis\\svcs\\cmp\\asp\\template."...
0x18002bed3  mov     [rsp+80h+lpName], rax
0x18002bed8  mov     r8d, 27B1h
0x18002bede  lea     rax, aFailedToOpenFi; "Failed to open file %S because it is a "...
0x18002bee5  mov     qword ptr [rsp+80h+dwMaximumSizeLow], rax
0x18002beea  call    cs:__imp_PuDbgPrint
0x18002bef0  test    rdi, rdi
0x18002bef3  jz      loc_18002BFE9
0x18002bef9  mov     rcx, [rdi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x18002befd  mov     edx, 2; unsigned int
0x18002bf02  call    ?CheckTracingEnabled@ActiveServerPagesASPTraceProvider@@SAHPEAU_EXTENSION_CONTROL_BLOCK@@K@Z; ActiveServerPagesASPTraceProvider::CheckTracingEnabled(_EXTENSION_CONTROL_BLOCK *,ulong)
0x18002bf07  test    eax, eax
0x18002bf09  jz      loc_18002BFE9
0x18002bf0f  mov     r8, [rbx+8]; unsigned __int16 *
0x18002bf13  mov     rcx, [rdi+8]; struct _EXTENSION_CONTROL_BLOCK *
0x18002bf17  call    ?RaiseEvent@ASP_FILE_NOT_FOUND@AspReqEvents@@SAJPEAU_EXTENSION_CONTROL_BLOCK@@PEBU_GUID@@PEBG@Z; AspReqEvents::ASP_FILE_NOT_FOUND::RaiseEvent(_EXTENSION_CONTROL_BLOCK *,_GUID const *,ushort const *)
0x18002bf1c  jmp     loc_18002BFE9
0x18002bf21  test    byte ptr cs:g_dwDebugFlags, 3
0x18002bf28  jz      loc_18002BEA1
0x18002bf2e  jmp     loc_18002BE74
0x18002bf33  mov     rdx, [rbx+20h]; void *
0x18002bf37  lea     r9, [rbp+var_40]; unsigned int *
0x18002bf3b  mov     rcx, [rbx+8]; unsigned __int16 *
0x18002bf3f  xor     r8d, r8d; struct _FILETIME *
0x18002bf42  mov     [rbp+var_40], r14d
0x18002bf46  mov     qword ptr [rsp+80h+dwMaximumSizeLow], r14; unsigned int *
0x18002bf4b  call    ?AspGetFileAttributes@@YAJPEBGPEAXPEAU_FILETIME@@PEAK3@Z; AspGetFileAttributes(ushort const *,void *,_FILETIME *,ulong *,ulong *)
0x18002bf50  test    eax, eax
0x18002bf52  js      short loc_18002BFA4
0x18002bf54  cmp     [rbp+var_40], r14d
0x18002bf58  jnz     loc_180013EA9
0x18002bf5e  test    byte ptr cs:g_dwDebugFlags, 3
0x18002bf65  jz      short loc_18002BF9D
0x18002bf67  mov     rax, [rbx+8]
0x18002bf6b  lea     r9, aCtemplateCfile; "CTemplate::CFileMap::RemapFile"
0x18002bf72  mov     rcx, cs:g_pDebug
0x18002bf79  lea     rdx, aInetsrvIisSvcs_4; "inetsrv\\iis\\svcs\\cmp\\asp\\template."...
0x18002bf80  mov     [rsp+80h+lpName], rax
0x18002bf85  mov     r8d, 2827h
0x18002bf8b  lea     rax, aEmptySourceFil; "Empty source file %S\n"
0x18002bf92  mov     qword ptr [rsp+80h+dwMaximumSizeLow], rax
0x18002bf97  call    cs:__imp_PuDbgPrint
0x18002bf9d  mov     ecx, 8000D002h
0x18002bfa2  jmp     short loc_18002BFEE
0x18002bfa4  mov     rcx, [rbx+20h]; hObject
0x18002bfa8  lea     rax, [rcx-1]
0x18002bfac  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002bfb0  ja      short loc_18002BFE9
0x18002bfb2  call    cs:__imp_CloseHandle
0x18002bfb8  mov     [rbx+20h], r14
0x18002bfbc  jmp     short loc_18002BFE9
0x18002bfbe  mov     rcx, [rbx+20h]; hObject
0x18002bfc2  lea     rax, [rcx-1]
0x18002bfc6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002bfca  ja      short loc_18002BFD6
0x18002bfcc  call    cs:__imp_CloseHandle
0x18002bfd2  mov     [rbx+20h], r14
0x18002bfd6  mov     rcx, [rbx+28h]; hObject
0x18002bfda  test    rcx, rcx
0x18002bfdd  jz      short loc_18002BFE9
0x18002bfdf  call    cs:__imp_CloseHandle
0x18002bfe5  mov     [rbx+28h], r14
0x18002bfe9  mov     ecx, 8000D001h; dwExceptionCode
0x18002bfee  xor     r9d, r9d; lpArguments
0x18002bff1  xor     r8d, r8d; nNumberOfArguments
0x18002bff4  xor     edx, edx; dwExceptionFlags
0x18002bff6  call    cs:__imp_RaiseException
0x18002bffc  nop
0x18002bffd  jmp     loc_180013ED8
```
