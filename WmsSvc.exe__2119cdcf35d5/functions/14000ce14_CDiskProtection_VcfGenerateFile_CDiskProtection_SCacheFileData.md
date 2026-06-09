# CDiskProtection::VcfGenerateFile(CDiskProtection::SCacheFileData *)

- ea: `0x14000ce14`
- end: `0x14000d223`
- name: `?VcfGenerateFile@CDiskProtection@@IEAAJPEAUSCacheFileData@1@@Z`
- size: `1039`
- prototype: `__int64 __fastcall(CDiskProtection *__hidden this, struct CDiskProtection::SCacheFileData *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400087b0`

## callees

- `0x140008b40`
- `0x1400090dc`
- `0x14000ce14`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x1400651a0`
- `0x140068cec`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000cf91`
- `KERNEL32!CloseHandle` at `0x14000d1d5`
- `KERNEL32!CloseHandle` at `0x14000cf91`
- `KERNEL32!CloseHandle` at `0x14000d1d5`
- `KERNEL32!CreateFileW` at `0x14000ce8e`
- `KERNEL32!CreateFileW` at `0x14000cfdf`
- `KERNEL32!CreateFileW` at `0x14000ce8e`
- `KERNEL32!CreateFileW` at `0x14000cfdf`
- `KERNEL32!SetFilePointerEx` at `0x14000cf03`
- `KERNEL32!SetFilePointerEx` at `0x14000d101`
- `KERNEL32!SetFilePointerEx` at `0x14000cf03`
- `KERNEL32!SetFilePointerEx` at `0x14000d101`
- `KERNEL32!SetEndOfFile` at `0x14000cf30`
- `KERNEL32!SetEndOfFile` at `0x14000cf30`
- `KERNEL32!SetFileValidData` at `0x14000cf64`
- `KERNEL32!SetFileValidData` at `0x14000cf64`
- `KERNEL32!DeleteFileW` at `0x14000d1e9`
- `KERNEL32!DeleteFileW` at `0x14000d1e9`
- `KERNEL32!GetLastError` at `0x14000ce9d`
- `KERNEL32!GetLastError` at `0x14000cf0d`
- `KERNEL32!GetLastError` at `0x14000cf3a`
- `KERNEL32!GetLastError` at `0x14000cf6e`
- `KERNEL32!GetLastError` at `0x14000cf9b`
- `KERNEL32!GetLastError` at `0x14000cfee`
- `KERNEL32!GetLastError` at `0x14000d10f`
- `KERNEL32!GetLastError` at `0x14000ce9d`
- `KERNEL32!GetLastError` at `0x14000cf0d`
- `KERNEL32!GetLastError` at `0x14000cf3a`
- `KERNEL32!GetLastError` at `0x14000cf6e`
- `KERNEL32!GetLastError` at `0x14000cf9b`
- `KERNEL32!GetLastError` at `0x14000cfee`
- `KERNEL32!GetLastError` at `0x14000d10f`
- `KERNEL32!IsDebuggerPresent` at `0x14000d083`
- `KERNEL32!IsDebuggerPresent` at `0x14000d16a`
- `KERNEL32!IsDebuggerPresent` at `0x14000d083`
- `KERNEL32!IsDebuggerPresent` at `0x14000d16a`

## string_xrefs

- `0x14000ce4a`: `SeManageVolumePrivilege`
- `0x14000d1aa`: `SeManageVolumePrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDiskProtection::VcfGenerateFile(CDiskProtection *this, struct CDiskProtection::SCacheFileData *a2)
{
  signed int NtfsVolumeData; // ebx
  HANDLE FileW; // rax
  unsigned __int16 v5; // r8
  signed int LastError; // eax
  const unsigned __int16 *v7; // r15
  unsigned int v8; // r13d
  CDiskProtection *v9; // rcx
  signed int v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  signed int v13; // eax
  HANDLE v14; // rax
  CDiskProtection *v15; // rcx
  signed int v16; // eax
  char *v17; // rsi
  signed int v18; // eax
  HANDLE hTemplateFile; // [rsp+30h] [rbp-38h]
  int v21; // [rsp+38h] [rbp-30h]
  signed int v22; // [rsp+38h] [rbp-30h]
  unsigned int v23; // [rsp+70h] [rbp+8h] BYREF
  int v24; // [rsp+74h] [rbp+Ch]

  v24 = HIDWORD(this);
  v23 = 0;
  DEBUGMSG(L"CDiskProtection::VcfGenerateFile\n");
  NtfsVolumeData = AdjustPrivilege(L"SeManageVolumePrivilege", 1);
  if ( NtfsVolumeData < 0 )
    goto LABEL_46;
  FileW = CreateFileW(*((LPCWSTR *)a2 + 21), 0xC0000000, 0, 0, 2u, 0x80u, 0);
  *(_QWORD *)a2 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    NtfsVolumeData = LastError;
    if ( LastError > 0 )
      NtfsVolumeData = (unsigned __int16)LastError | 0x80070000;
    v7 = L"pcfd->hFile != ((HANDLE)(LONG_PTR)-1)";
    v8 = 2838;
    goto LABEL_41;
  }
  NtfsVolumeData = SetFileCompression(*((const unsigned __int16 **)a2 + 21), FileW, v5);
  if ( NtfsVolumeData < 0 )
    goto LABEL_46;
  NtfsVolumeData = CDiskProtection::GetNtfsVolumeData(
                     v9,
                     *(void **)a2,
                     (struct NTFS_VOLUME_DATA_BUFFER *)((char *)a2 + 8));
  if ( NtfsVolumeData < 0 )
    goto LABEL_46;
  if ( !SetFilePointerEx(*(HANDLE *)a2, *(LARGE_INTEGER *)((char *)a2 + 184), 0, 0) )
  {
    v10 = GetLastError();
    NtfsVolumeData = v10;
    if ( v10 > 0 )
      NtfsVolumeData = (unsigned __int16)v10 | 0x80070000;
    v8 = 2866;
LABEL_40:
    v7 = L"fSuccess";
LABEL_41:
    if ( NtfsVolumeData >= 0 )
      NtfsVolumeData = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      v8,
      L"CDiskProtection::VcfGenerateFile",
      L"CBRAEx",
      v7,
      NtfsVolumeData);
    if ( IsDebuggerPresent() )
    {
      v22 = NtfsVolumeData;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        v8,
        L"CDiskProtection::VcfGenerateFile",
        L"CBRAEx",
        v7,
        v22);
    }
    else
    {
      LODWORD(hTemplateFile) = NtfsVolumeData;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        v8,
        L"CDiskProtection::VcfGenerateFile",
        L"CBRAEx",
        v7,
        hTemplateFile);
    }
    goto LABEL_46;
  }
  if ( !SetEndOfFile(*(HANDLE *)a2) )
  {
    v11 = GetLastError();
    NtfsVolumeData = v11;
    if ( v11 > 0 )
      NtfsVolumeData = (unsigned __int16)v11 | 0x80070000;
    v8 = 2873;
    goto LABEL_40;
  }
  if ( !SetFileValidData(*(HANDLE *)a2, *((_QWORD *)a2 + 23)) )
  {
    v12 = GetLastError();
    NtfsVolumeData = v12;
    if ( v12 > 0 )
      NtfsVolumeData = (unsigned __int16)v12 | 0x80070000;
    v8 = 2882;
    goto LABEL_40;
  }
  if ( !CloseHandle(*(HANDLE *)a2) )
  {
    v13 = GetLastError();
    NtfsVolumeData = v13;
    if ( v13 > 0 )
      NtfsVolumeData = (unsigned __int16)v13 | 0x80070000;
    v8 = 2889;
    goto LABEL_40;
  }
  v14 = CreateFileW(*((LPCWSTR *)a2 + 21), 0xC0000000, 0, 0, 3u, 0x80u, 0);
  *(_QWORD *)a2 = v14;
  if ( v14 == (HANDLE)-1LL )
  {
    v16 = GetLastError();
    NtfsVolumeData = v16;
    if ( v16 > 0 )
      NtfsVolumeData = (unsigned __int16)v16 | 0x80070000;
    v7 = L"pcfd->hFile != ((HANDLE)(LONG_PTR)-1)";
    v8 = 2892;
    goto LABEL_41;
  }
  v17 = (char *)a2 + 144;
  NtfsVolumeData = CDiskProtection::GetFileRetrievalPointers(
                     v15,
                     v14,
                     (struct RETRIEVAL_POINTERS_BUFFER **)a2 + 18,
                     &v23);
  if ( NtfsVolumeData < 0 )
    goto LABEL_46;
  if ( !**(_DWORD **)v17 )
  {
    NtfsVolumeData = -2147418113;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0xB5Bu,
      L"CDiskProtection::VcfGenerateFile",
      L"CBRAEx",
      L"pcfd->pRetrievalPointers->ExtentCount > 0",
      -2147418113);
    if ( IsDebuggerPresent() )
    {
      v21 = -2147418113;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        2907,
        L"CDiskProtection::VcfGenerateFile",
        L"CBRAEx",
        L"pcfd->pRetrievalPointers->ExtentCount > 0",
        v21);
    }
    else
    {
      LODWORD(hTemplateFile) = -2147418113;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        2907,
        L"CDiskProtection::VcfGenerateFile",
        L"CBRAEx",
        L"pcfd->pRetrievalPointers->ExtentCount > 0",
        hTemplateFile);
    }
    goto LABEL_46;
  }
  if ( (unsigned __int64)*((unsigned int *)a2 + 13)
     * (*(_QWORD *)(*(_QWORD *)v17 + 16LL) - *(_QWORD *)(*(_QWORD *)v17 + 8LL))
     / *((unsigned int *)a2 + 12) < 0x90 )
  {
    NtfsVolumeData = -2147024594;
    goto LABEL_46;
  }
  if ( !SetFilePointerEx(*(HANDLE *)a2, 0, 0, 0) )
  {
    v18 = GetLastError();
    NtfsVolumeData = v18;
    if ( v18 > 0 )
      NtfsVolumeData = (unsigned __int16)v18 | 0x80070000;
    v8 = 2921;
    goto LABEL_40;
  }
LABEL_46:
  AdjustPrivilege(L"SeManageVolumePrivilege", 0);
  if ( NtfsVolumeData >= 0 )
  {
    DEBUGMSG(L"CDiskProtection::VcfGenerateFile - Succeeded.\n");
  }
  else
  {
    DEBUGMSG(
      L"CDiskProtection::VcfGenerateFile - Failed with hr = 0x%08X, deleting file.\n",
      (unsigned int)NtfsVolumeData);
    if ( (unsigned __int64)(*(_QWORD *)a2 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(*(HANDLE *)a2);
      *(_QWORD *)a2 = 0;
    }
    DeleteFileW(*((LPCWSTR *)a2 + 21));
    *((_QWORD *)a2 + 18) = 0;
  }
  return (unsigned int)NtfsVolumeData;
}

```

## disassembly

```asm
0x14000ce14  mov     rax, rsp
0x14000ce17  mov     [rax+10h], rbx
0x14000ce1b  mov     [rax+18h], rbp
0x14000ce1f  mov     [rax+8], rcx
0x14000ce23  push    rsi
0x14000ce24  push    rdi
0x14000ce25  push    r13
0x14000ce27  push    r14
0x14000ce29  push    r15
0x14000ce2b  sub     rsp, 40h
0x14000ce2f  lea     rcx, aCdiskprotectio_70; "CDiskProtection::VcfGenerateFile\n"
0x14000ce36  mov     dword ptr [rax+8], 0
0x14000ce3d  mov     rdi, rdx
0x14000ce40  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000ce45  mov     edx, 1
0x14000ce4a  lea     rcx, aSemanagevolume; "SeManageVolumePrivilege"
0x14000ce51  call    ?AdjustPrivilege@@YAJPEBGW4EPrivilegeStatus@@@Z; AdjustPrivilege(ushort const *,EPrivilegeStatus)
0x14000ce56  mov     ebx, eax
0x14000ce58  test    eax, eax
0x14000ce5a  js      loc_14000D1A8
0x14000ce60  mov     rcx, [rdi+0A8h]; lpFileName
0x14000ce67  mov     esi, 80h
0x14000ce6c  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x14000ce75  mov     ebp, 0C0000000h
0x14000ce7a  mov     [rsp+68h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x14000ce7e  mov     edx, ebp; dwDesiredAccess
0x14000ce80  xor     r9d, r9d; lpSecurityAttributes
0x14000ce83  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x14000ce8b  xor     r8d, r8d; dwShareMode
0x14000ce8e  call    cs:__imp_CreateFileW
0x14000ce94  mov     [rdi], rax
0x14000ce97  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000ce9b  jnz     short loc_14000CEC4
0x14000ce9d  call    cs:__imp_GetLastError
0x14000cea3  mov     ebx, eax
0x14000cea5  test    eax, eax
0x14000cea7  jle     short loc_14000CEB2
0x14000cea9  movzx   ebx, ax
0x14000ceac  or      ebx, 80070000h
0x14000ceb2  lea     r15, aPcfdHfileHandl; "pcfd->hFile != ((HANDLE)(LONG_PTR)-1)"
0x14000ceb9  mov     r13d, 0B16h
0x14000cebf  jmp     loc_14000D131
0x14000cec4  mov     rcx, [rdi+0A8h]; unsigned __int16 *
0x14000cecb  mov     rdx, rax; void *
0x14000cece  call    ?SetFileCompression@@YAJPEBGPEAXG@Z; SetFileCompression(ushort const *,void *,ushort)
0x14000ced3  mov     ebx, eax
0x14000ced5  test    eax, eax
0x14000ced7  js      loc_14000D1A8
0x14000cedd  mov     rdx, [rdi]; void *
0x14000cee0  lea     r8, [rdi+8]; struct NTFS_VOLUME_DATA_BUFFER *
0x14000cee4  call    ?GetNtfsVolumeData@CDiskProtection@@IEAAJPEAXPEAUNTFS_VOLUME_DATA_BUFFER@@@Z; CDiskProtection::GetNtfsVolumeData(void *,NTFS_VOLUME_DATA_BUFFER *)
0x14000cee9  mov     ebx, eax
0x14000ceeb  test    eax, eax
0x14000ceed  js      loc_14000D1A8
0x14000cef3  mov     rdx, [rdi+0B8h]; liDistanceToMove
0x14000cefa  xor     r9d, r9d; dwMoveMethod
0x14000cefd  mov     rcx, [rdi]; hFile
0x14000cf00  xor     r8d, r8d; lpNewFilePointer
0x14000cf03  call    cs:__imp_SetFilePointerEx
0x14000cf09  test    eax, eax
0x14000cf0b  jnz     short loc_14000CF2D
0x14000cf0d  call    cs:__imp_GetLastError
0x14000cf13  mov     ebx, eax
0x14000cf15  test    eax, eax
0x14000cf17  jle     short loc_14000CF22
0x14000cf19  movzx   ebx, ax
0x14000cf1c  or      ebx, 80070000h
0x14000cf22  mov     r13d, 0B32h
0x14000cf28  jmp     loc_14000D12A
0x14000cf2d  mov     rcx, [rdi]; hFile
0x14000cf30  call    cs:__imp_SetEndOfFile
0x14000cf36  test    eax, eax
0x14000cf38  jnz     short loc_14000CF5A
0x14000cf3a  call    cs:__imp_GetLastError
0x14000cf40  mov     ebx, eax
0x14000cf42  test    eax, eax
0x14000cf44  jle     short loc_14000CF4F
0x14000cf46  movzx   ebx, ax
0x14000cf49  or      ebx, 80070000h
0x14000cf4f  mov     r13d, 0B39h
0x14000cf55  jmp     loc_14000D12A
0x14000cf5a  mov     rdx, [rdi+0B8h]; ValidDataLength
0x14000cf61  mov     rcx, [rdi]; hFile
0x14000cf64  call    cs:__imp_SetFileValidData
0x14000cf6a  test    eax, eax
0x14000cf6c  jnz     short loc_14000CF8E
0x14000cf6e  call    cs:__imp_GetLastError
0x14000cf74  mov     ebx, eax
0x14000cf76  test    eax, eax
0x14000cf78  jle     short loc_14000CF83
0x14000cf7a  movzx   ebx, ax
0x14000cf7d  or      ebx, 80070000h
0x14000cf83  mov     r13d, 0B42h
0x14000cf89  jmp     loc_14000D12A
0x14000cf8e  mov     rcx, [rdi]; hObject
0x14000cf91  call    cs:__imp_CloseHandle
0x14000cf97  test    eax, eax
0x14000cf99  jnz     short loc_14000CFBB
0x14000cf9b  call    cs:__imp_GetLastError
0x14000cfa1  mov     ebx, eax
0x14000cfa3  test    eax, eax
0x14000cfa5  jle     short loc_14000CFB0
0x14000cfa7  movzx   ebx, ax
0x14000cfaa  or      ebx, 80070000h
0x14000cfb0  mov     r13d, 0B49h
0x14000cfb6  jmp     loc_14000D12A
0x14000cfbb  mov     rcx, [rdi+0A8h]; lpFileName
0x14000cfc2  xor     r9d, r9d; lpSecurityAttributes
0x14000cfc5  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x14000cfce  xor     r8d, r8d; dwShareMode
0x14000cfd1  mov     [rsp+68h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x14000cfd5  mov     edx, ebp; dwDesiredAccess
0x14000cfd7  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x14000cfdf  call    cs:__imp_CreateFileW
0x14000cfe5  mov     [rdi], rax
0x14000cfe8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000cfec  jnz     short loc_14000D015
0x14000cfee  call    cs:__imp_GetLastError
0x14000cff4  mov     ebx, eax
0x14000cff6  test    eax, eax
0x14000cff8  jle     short loc_14000D003
0x14000cffa  movzx   ebx, ax
0x14000cffd  or      ebx, 80070000h
0x14000d003  lea     r15, aPcfdHfileHandl; "pcfd->hFile != ((HANDLE)(LONG_PTR)-1)"
0x14000d00a  mov     r13d, 0B4Ch
0x14000d010  jmp     loc_14000D131
0x14000d015  lea     rsi, [rdi+90h]
0x14000d01c  mov     rdx, rax; void *
0x14000d01f  mov     r8, rsi; struct RETRIEVAL_POINTERS_BUFFER **
0x14000d022  lea     r9, [rsp+68h+arg_0]; unsigned int *
0x14000d027  call    ?GetFileRetrievalPointers@CDiskProtection@@IEAAJPEAXPEAPEAURETRIEVAL_POINTERS_BUFFER@@PEAK@Z; CDiskProtection::GetFileRetrievalPointers(void *,RETRIEVAL_POINTERS_BUFFER * *,ulong *)
0x14000d02c  mov     ebx, eax
0x14000d02e  test    eax, eax
0x14000d030  js      loc_14000D1A8
0x14000d036  mov     rcx, [rsi]
0x14000d039  cmp     dword ptr [rcx], 0
0x14000d03c  ja      loc_14000D0CD
0x14000d042  mov     ebx, 8000FFFFh
0x14000d047  lea     r14, aCbraex; "CBRAEx"
0x14000d04e  lea     rbp, aCdiskprotectio_78; "CDiskProtection::VcfGenerateFile"
0x14000d055  mov     [rsp+68h+dwFlagsAndAttributes], ebx; int
0x14000d059  mov     r15d, 0B5Bh
0x14000d05f  lea     rsi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000d066  lea     r13, aPcfdPretrieval; "pcfd->pRetrievalPointers->ExtentCount >"...
0x14000d06d  mov     r9, r14; unsigned __int16 *
0x14000d070  mov     r8, rbp; unsigned __int16 *
0x14000d073  mov     qword ptr [rsp+68h+dwCreationDisposition], r13; unsigned __int16 *
0x14000d078  mov     edx, r15d; unsigned int
0x14000d07b  mov     rcx, rsi; unsigned __int16 *
0x14000d07e  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000d083  call    cs:__imp_IsDebuggerPresent
0x14000d089  test    eax, eax
0x14000d08b  jz      short loc_14000D0BC
0x14000d08d  mov     [rsp+68h+var_30], ebx
0x14000d091  mov     r9d, r15d
0x14000d094  mov     [rsp+68h+hTemplateFile], r13
0x14000d099  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], r14
0x14000d09e  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000d0a5  mov     r8, rsi
0x14000d0a8  mov     qword ptr [rsp+68h+dwCreationDisposition], rbp
0x14000d0ad  mov     ecx, 2; unsigned __int8
0x14000d0b2  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000d0b7  jmp     loc_14000D1A8
0x14000d0bc  mov     dword ptr [rsp+68h+hTemplateFile], ebx
0x14000d0c0  mov     r8d, r15d
0x14000d0c3  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], r13
0x14000d0c8  jmp     loc_14000D191
0x14000d0cd  mov     rax, [rcx+10h]
0x14000d0d1  xor     edx, edx
0x14000d0d3  sub     rax, [rcx+8]
0x14000d0d7  mov     ecx, [rdi+34h]
0x14000d0da  imul    rax, rcx
0x14000d0de  mov     ecx, [rdi+30h]
0x14000d0e1  div     rcx
0x14000d0e4  cmp     rax, 90h
0x14000d0ea  jnb     short loc_14000D0F6
0x14000d0ec  mov     ebx, 8007012Eh
0x14000d0f1  jmp     loc_14000D1A8
0x14000d0f6  mov     rcx, [rdi]; hFile
0x14000d0f9  xor     edx, edx; liDistanceToMove
0x14000d0fb  xor     r9d, r9d; dwMoveMethod
0x14000d0fe  xor     r8d, r8d; lpNewFilePointer
0x14000d101  call    cs:__imp_SetFilePointerEx
0x14000d107  test    eax, eax
0x14000d109  jnz     loc_14000D1A8
0x14000d10f  call    cs:__imp_GetLastError
0x14000d115  mov     ebx, eax
0x14000d117  test    eax, eax
0x14000d119  jle     short loc_14000D124
0x14000d11b  movzx   ebx, ax
0x14000d11e  or      ebx, 80070000h
0x14000d124  mov     r13d, 0B69h
0x14000d12a  lea     r15, aFsuccess; "fSuccess"
0x14000d131  mov     eax, 80004005h
0x14000d136  lea     r14, aCbraex; "CBRAEx"
0x14000d13d  test    ebx, ebx
0x14000d13f  lea     rbp, aCdiskprotectio_78; "CDiskProtection::VcfGenerateFile"
0x14000d146  lea     rsi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x14000d14d  mov     r9, r14; unsigned __int16 *
0x14000d150  cmovns  ebx, eax
0x14000d153  mov     r8, rbp; unsigned __int16 *
0x14000d156  mov     [rsp+68h+dwFlagsAndAttributes], ebx; int
0x14000d15a  mov     edx, r13d; unsigned int
0x14000d15d  mov     rcx, rsi; unsigned __int16 *
0x14000d160  mov     qword ptr [rsp+68h+dwCreationDisposition], r15; unsigned __int16 *
0x14000d165  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000d16a  call    cs:__imp_IsDebuggerPresent
0x14000d170  test    eax, eax
0x14000d172  jz      short loc_14000D185
0x14000d174  mov     [rsp+68h+var_30], ebx
0x14000d178  mov     r9d, r13d
0x14000d17b  mov     [rsp+68h+hTemplateFile], r15
0x14000d180  jmp     loc_14000D099
0x14000d185  mov     dword ptr [rsp+68h+hTemplateFile], ebx
0x14000d189  mov     r8d, r13d
0x14000d18c  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], r15
0x14000d191  mov     r9, rbp
0x14000d194  mov     qword ptr [rsp+68h+dwCreationDisposition], r14
0x14000d199  mov     rdx, rsi
0x14000d19c  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000d1a3  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000d1a8  xor     edx, edx
0x14000d1aa  lea     rcx, aSemanagevolume; "SeManageVolumePrivilege"
0x14000d1b1  call    ?AdjustPrivilege@@YAJPEBGW4EPrivilegeStatus@@@Z; AdjustPrivilege(ushort const *,EPrivilegeStatus)
0x14000d1b6  test    ebx, ebx
0x14000d1b8  jns     short loc_14000D1FC
0x14000d1ba  mov     edx, ebx
0x14000d1bc  lea     rcx, aCdiskprotectio_142; "CDiskProtection::VcfGenerateFile - Fail"...
0x14000d1c3  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000d1c8  mov     rcx, [rdi]; hObject
0x14000d1cb  lea     rax, [rcx-1]
0x14000d1cf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000d1d3  ja      short loc_14000D1E2
0x14000d1d5  call    cs:__imp_CloseHandle
0x14000d1db  mov     qword ptr [rdi], 0
0x14000d1e2  mov     rcx, [rdi+0A8h]; lpFileName
0x14000d1e9  call    cs:__imp_DeleteFileW
0x14000d1ef  mov     qword ptr [rdi+90h], 0
0x14000d1fa  jmp     short loc_14000D208
0x14000d1fc  lea     rcx, aCdiskprotectio_101; "CDiskProtection::VcfGenerateFile - Succ"...
0x14000d203  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14000d208  lea     r11, [rsp+68h+var_28]
0x14000d20d  mov     eax, ebx
0x14000d20f  mov     rbx, [r11+38h]
0x14000d213  mov     rbp, [r11+40h]
0x14000d217  mov     rsp, r11
0x14000d21a  pop     r15
0x14000d21c  pop     r14
0x14000d21e  pop     r13
0x14000d220  pop     rdi
0x14000d221  pop     rsi
0x14000d222  retn
```
