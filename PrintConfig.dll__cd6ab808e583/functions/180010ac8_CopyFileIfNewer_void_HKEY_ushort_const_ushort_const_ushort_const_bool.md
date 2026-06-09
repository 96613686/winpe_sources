# CopyFileIfNewer(void *,HKEY__ *,ushort const *,ushort const *,ushort const *,bool *)

- ea: `0x180010ac8`
- end: `0x180010d38`
- name: `?CopyFileIfNewer@@YAJPEAXPEAUHKEY__@@PEBG22PEA_N@Z`
- size: `624`
- prototype: `__int64 __fastcall(void *, HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180012f3c`

## callees

- `0x1800032e0`
- `0x180004418`
- `0x1800060ec`
- `0x180010ac8`
- `0x180014224`
- `0x180018200`
- `0x1800183f8`
- `0x1800376f4`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x180010c0e`
- `KERNEL32!CopyFileW` at `0x180010cb5`
- `KERNEL32!CopyFileW` at `0x180010c0e`
- `KERNEL32!CopyFileW` at `0x180010cb5`
- `KERNEL32!GetTempFileNameW` at `0x180010bdc`
- `KERNEL32!GetTempFileNameW` at `0x180010bdc`
- `KERNEL32!GetTempPathW` at `0x180010b99`
- `KERNEL32!GetTempPathW` at `0x180010b99`
- `KERNEL32!DeleteFileW` at `0x180010ce2`
- `KERNEL32!DeleteFileW` at `0x180010ce2`
- `KERNEL32!FreeLibrary` at `0x180010d0c`
- `KERNEL32!FreeLibrary` at `0x180010d0c`
- `KERNEL32!GetLastError` at `0x180010ba8`
- `KERNEL32!GetLastError` at `0x180010be6`
- `KERNEL32!GetLastError` at `0x180010c18`
- `KERNEL32!GetLastError` at `0x180010cc5`
- `KERNEL32!GetLastError` at `0x180010ba8`
- `KERNEL32!GetLastError` at `0x180010be6`
- `KERNEL32!GetLastError` at `0x180010c18`
- `KERNEL32!GetLastError` at `0x180010cc5`

## string_xrefs

- `0x180010c3f`: `CatalogForWOWPrintConfig`
- `0x180010c5e`: `32-bit PrintConfig.dll failed catalog check.`
- `0x180010c65`: `CopyFileIfNewer`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
__int64 __fastcall CopyFileIfNewer(
        void *a1,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        bool *a6)
{
  char v10; // si
  int FileVersion; // ebx
  int v12; // eax
  signed int LastError; // eax
  char v14; // bl
  signed int v15; // eax
  signed int v16; // eax
  const WCHAR *v17; // rdi
  signed int v18; // eax
  unsigned __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  HMODULE hLibModule[2]; // [rsp+40h] [rbp-C0h] BYREF
  void (*v23)(void); // [rsp+50h] [rbp-B0h]
  __int64 v24; // [rsp+58h] [rbp-A8h]
  WCHAR TempFileName[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[264]; // [rsp+270h] [rbp+170h] BYREF

  v24 = -2;
  v10 = 0;
  *a6 = 0;
  v20 = 0;
  FileVersion = GetFileVersion(a3, &v20);
  v21 = 0;
  if ( FileVersion < 0 )
    return (unsigned int)FileVersion;
  v12 = GetFileVersion(a4, &v21);
  FileVersion = v12;
  if ( v12 != -2147024894 )
  {
    if ( v12 < 0 )
      return (unsigned int)FileVersion;
    v10 = 1;
    if ( v21 >= v20 )
      return (unsigned int)FileVersion;
  }
  memset_0(TempFileName, 0, 0x208u);
  memset_0(Buffer, 0, 0x208u);
  if ( GetTempPathW(0x104u, Buffer) )
    goto LABEL_42;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  LODWORD(v20) = LastError;
  if ( LastError >= 0 )
  {
LABEL_42:
    if ( GetTempFileNameW(Buffer, L"PC", 0, TempFileName) )
    {
      v14 = 0;
    }
    else
    {
      v15 = GetLastError();
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
      LODWORD(v20) = v15;
      v14 = 0;
      if ( v15 < 0 )
        goto LABEL_24;
    }
    if ( CopyFileW(a3, TempFileName, 0) )
    {
      v14 = 1;
    }
    else
    {
      v16 = GetLastError();
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      LODWORD(v20) = v16;
      if ( v16 < 0 )
        goto LABEL_24;
    }
    LODWORD(v20) = VerifyFileUsingPrinterDataCatalog(a1, a2, TempFileName, L"CatalogForWOWPrintConfig", 0);
    if ( (v20 & 0x80000000) != 0LL )
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "CopyFileIfNewer",
        L"32-bit PrintConfig.dll failed catalog check.");
  }
  else
  {
    v14 = 0;
  }
LABEL_24:
  RevertToPrinterRAII::RevertToPrinterRAII((RevertToPrinterRAII *)hLibModule, (int *)&v20);
  v17 = (const WCHAR *)((unsigned __int64)TempFileName & -(__int64)(v14 != 0));
  FileVersion = v20;
  if ( (v20 & 0x80000000) == 0LL )
  {
    if ( v10 )
      FileVersion = DeleteFileNowOrOnReboot(a4, 0);
    if ( FileVersion >= 0 )
    {
      if ( CopyFileW(TempFileName, a4, 0) )
      {
        *a6 = 1;
      }
      else
      {
        v18 = GetLastError();
        FileVersion = v18;
        if ( v18 > 0 )
          FileVersion = (unsigned __int16)v18 | 0x80070000;
      }
    }
  }
  if ( v17 )
    DeleteFileW(v17);
  if ( v23 && hLibModule[1] )
    v23();
  if ( hLibModule[0] )
    FreeLibrary(hLibModule[0]);
  return (unsigned int)FileVersion;
}

```

## disassembly

```asm
0x180010ac8  push    rbp
0x180010aca  push    rbx
0x180010acb  push    rsi
0x180010acc  push    rdi
0x180010acd  push    r12
0x180010acf  push    r13
0x180010ad1  push    r14
0x180010ad3  push    r15
0x180010ad5  lea     rbp, [rsp-398h]
0x180010add  sub     rsp, 498h
0x180010ae4  mov     [rsp+4D0h+var_478], 0FFFFFFFFFFFFFFFEh
0x180010aed  mov     rax, cs:__security_cookie
0x180010af4  xor     rax, rsp
0x180010af7  mov     [rbp+3D0h+var_50], rax
0x180010afe  mov     r14, r9
0x180010b01  mov     rdi, r8
0x180010b04  mov     r13, rdx
0x180010b07  mov     r12, rcx
0x180010b0a  mov     r15, [rbp+3D0h+arg_28]
0x180010b11  xor     esi, esi
0x180010b13  mov     [r15], sil
0x180010b16  mov     [rsp+4D0h+var_4A0], rsi
0x180010b1b  lea     rdx, [rsp+4D0h+var_4A0]; unsigned __int64 *
0x180010b20  mov     rcx, r8; lptstrFilename
0x180010b23  call    ?GetFileVersion@@YAJPEBGPEA_K@Z; GetFileVersion(ushort const *,unsigned __int64 *)
0x180010b28  mov     ebx, eax
0x180010b2a  mov     [rsp+4D0h+var_498], rsi
0x180010b2f  test    eax, eax
0x180010b31  js      loc_180010D13
0x180010b37  lea     rdx, [rsp+4D0h+var_498]; unsigned __int64 *
0x180010b3c  mov     rcx, r14; lptstrFilename
0x180010b3f  call    ?GetFileVersion@@YAJPEBGPEA_K@Z; GetFileVersion(ushort const *,unsigned __int64 *)
0x180010b44  mov     ebx, eax
0x180010b46  cmp     eax, 80070002h
0x180010b4b  jz      short loc_180010B68
0x180010b4d  test    eax, eax
0x180010b4f  js      loc_180010D13
0x180010b55  mov     sil, 1
0x180010b58  mov     rax, [rsp+4D0h+var_4A0]
0x180010b5d  cmp     [rsp+4D0h+var_498], rax
0x180010b62  jnb     loc_180010D13
0x180010b68  mov     ebx, 208h
0x180010b6d  mov     r8d, ebx; Size
0x180010b70  xor     edx, edx; Val
0x180010b72  lea     rcx, [rsp+4D0h+TempFileName]; void *
0x180010b77  call    memset_0
0x180010b7c  mov     r8d, ebx; Size
0x180010b7f  xor     edx, edx; Val
0x180010b81  lea     rcx, [rbp+3D0h+Buffer]; void *
0x180010b88  call    memset_0
0x180010b8d  lea     rdx, [rbp+3D0h+Buffer]; lpBuffer
0x180010b94  mov     ecx, 104h; nBufferLength
0x180010b99  call    cs:__imp_GetTempPathW
0x180010b9f  mov     ebx, 80070000h
0x180010ba4  test    eax, eax
0x180010ba6  jnz     short loc_180010BC6
0x180010ba8  call    cs:__imp_GetLastError
0x180010bae  test    eax, eax
0x180010bb0  jle     short loc_180010BB7
0x180010bb2  movzx   eax, ax
0x180010bb5  or      eax, ebx
0x180010bb7  mov     dword ptr [rsp+4D0h+var_4A0], eax
0x180010bbb  test    eax, eax
0x180010bbd  jns     short loc_180010BC6
0x180010bbf  xor     bl, bl
0x180010bc1  jmp     loc_180010C71
0x180010bc6  lea     r9, [rsp+4D0h+TempFileName]; lpTempFileName
0x180010bcb  xor     r8d, r8d; uUnique
0x180010bce  lea     rdx, PrefixString; "PC"
0x180010bd5  lea     rcx, [rbp+3D0h+Buffer]; lpPathName
0x180010bdc  call    cs:__imp_GetTempFileNameW
0x180010be2  test    eax, eax
0x180010be4  jnz     short loc_180010C01
0x180010be6  call    cs:__imp_GetLastError
0x180010bec  test    eax, eax
0x180010bee  jle     short loc_180010BF5
0x180010bf0  movzx   eax, ax
0x180010bf3  or      eax, ebx
0x180010bf5  mov     dword ptr [rsp+4D0h+var_4A0], eax
0x180010bf9  xor     bl, bl
0x180010bfb  test    eax, eax
0x180010bfd  js      short loc_180010C71
0x180010bff  jmp     short loc_180010C03
0x180010c01  xor     bl, bl
0x180010c03  xor     r8d, r8d; bFailIfExists
0x180010c06  lea     rdx, [rsp+4D0h+TempFileName]; lpNewFileName
0x180010c0b  mov     rcx, rdi; lpExistingFileName
0x180010c0e  call    cs:__imp_CopyFileW
0x180010c14  test    eax, eax
0x180010c16  jnz     short loc_180010C34
0x180010c18  call    cs:__imp_GetLastError
0x180010c1e  test    eax, eax
0x180010c20  jle     short loc_180010C2A
0x180010c22  movzx   eax, ax
0x180010c25  or      eax, 80070000h
0x180010c2a  mov     dword ptr [rsp+4D0h+var_4A0], eax
0x180010c2e  test    eax, eax
0x180010c30  js      short loc_180010C71
0x180010c32  jmp     short loc_180010C36
0x180010c34  mov     bl, 1
0x180010c36  mov     [rsp+4D0h+var_4B0], 0; struct Win32HandleRAII *
0x180010c3f  lea     r9, aCatalogforwowp; "CatalogForWOWPrintConfig"
0x180010c46  lea     r8, [rsp+4D0h+TempFileName]; unsigned __int16 *
0x180010c4b  mov     rdx, r13; HKEY
0x180010c4e  mov     rcx, r12; hPrinter
0x180010c51  call    ?VerifyFileUsingPrinterDataCatalog@@YAJPEAXPEAUHKEY__@@PEBG2PEAVWin32HandleRAII@@@Z; VerifyFileUsingPrinterDataCatalog(void *,HKEY__ *,ushort const *,ushort const *,Win32HandleRAII *)
0x180010c56  mov     dword ptr [rsp+4D0h+var_4A0], eax
0x180010c5a  test    eax, eax
0x180010c5c  jns     short loc_180010C71
0x180010c5e  lea     rdx, a32BitPrintconf; "32-bit PrintConfig.dll failed catalog c"...
0x180010c65  lea     rcx, aCopyfileifnewe; "CopyFileIfNewer"
0x180010c6c  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180010c71  lea     rdx, [rsp+4D0h+var_4A0]; int *
0x180010c76  lea     rcx, [rsp+4D0h+hLibModule]; this
0x180010c7b  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x180010c80  neg     bl
0x180010c82  sbb     rdi, rdi
0x180010c85  lea     rax, [rsp+4D0h+TempFileName]
0x180010c8a  and     rdi, rax
0x180010c8d  mov     ebx, dword ptr [rsp+4D0h+var_4A0]
0x180010c91  test    ebx, ebx
0x180010c93  js      short loc_180010CDA
0x180010c95  test    sil, sil
0x180010c98  jz      short loc_180010CA6
0x180010c9a  xor     edx, edx; bool
0x180010c9c  mov     rcx, r14; lpExistingFileName
0x180010c9f  call    ?DeleteFileNowOrOnReboot@@YAJPEBG_N@Z; DeleteFileNowOrOnReboot(ushort const *,bool)
0x180010ca4  mov     ebx, eax
0x180010ca6  test    ebx, ebx
0x180010ca8  js      short loc_180010CDA
0x180010caa  xor     r8d, r8d; bFailIfExists
0x180010cad  mov     rdx, r14; lpNewFileName
0x180010cb0  lea     rcx, [rsp+4D0h+TempFileName]; lpExistingFileName
0x180010cb5  call    cs:__imp_CopyFileW
0x180010cbb  test    eax, eax
0x180010cbd  jz      short loc_180010CC5
0x180010cbf  mov     byte ptr [r15], 1
0x180010cc3  jmp     short loc_180010CDA
0x180010cc5  call    cs:__imp_GetLastError
0x180010ccb  mov     ebx, eax
0x180010ccd  test    eax, eax
0x180010ccf  jle     short loc_180010CDA
0x180010cd1  movzx   ebx, ax
0x180010cd4  or      ebx, 80070000h
0x180010cda  test    rdi, rdi
0x180010cdd  jz      short loc_180010CE9
0x180010cdf  mov     rcx, rdi; lpFileName
0x180010ce2  call    cs:__imp_DeleteFileW
0x180010ce8  nop
0x180010ce9  mov     rax, [rsp+4D0h+var_480]
0x180010cee  test    rax, rax
0x180010cf1  jz      short loc_180010D02
0x180010cf3  mov     rcx, [rsp+4D0h+var_488]
0x180010cf8  test    rcx, rcx
0x180010cfb  jz      short loc_180010D02
0x180010cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d02  mov     rcx, [rsp+4D0h+hLibModule]; hLibModule
0x180010d07  test    rcx, rcx
0x180010d0a  jz      short loc_180010D13
0x180010d0c  call    cs:__imp_FreeLibrary
0x180010d12  nop
0x180010d13  mov     eax, ebx
0x180010d15  mov     rcx, [rbp+3D0h+var_50]
0x180010d1c  xor     rcx, rsp; StackCookie
0x180010d1f  call    __security_check_cookie
0x180010d24  add     rsp, 498h
0x180010d2b  pop     r15
0x180010d2d  pop     r14
0x180010d2f  pop     r13
0x180010d31  pop     r12
0x180010d33  pop     rdi
0x180010d34  pop     rsi
0x180010d35  pop     rbx
0x180010d36  pop     rbp
0x180010d37  retn
```
