# CopyFileIfNewer(void *,HKEY__ *,ushort const *,ushort const *,ushort const *,bool *)

- ea: `0x18001109c`
- end: `0x180011349`
- name: `?CopyFileIfNewer@@YAJPEAXPEAUHKEY__@@PEBG22PEA_N@Z`
- size: `685`
- prototype: `__int64 __fastcall(void *, HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1800136f0`

## callees

- `0x180003400`
- `0x180004558`
- `0x180006268`
- `0x18001109c`
- `0x180014ab4`
- `0x180018d54`
- `0x180018f58`
- `0x180038bc4`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x1800111fa`
- `KERNEL32!CopyFileW` at `0x1800112ad`
- `KERNEL32!CopyFileW` at `0x1800111fa`
- `KERNEL32!CopyFileW` at `0x1800112ad`
- `KERNEL32!GetTempFileNameW` at `0x1800111bc`
- `KERNEL32!GetTempFileNameW` at `0x1800111bc`
- `KERNEL32!GetTempPathW` at `0x18001116d`
- `KERNEL32!GetTempPathW` at `0x18001116d`
- `KERNEL32!DeleteFileW` at `0x1800112e6`
- `KERNEL32!DeleteFileW` at `0x1800112e6`
- `KERNEL32!FreeLibrary` at `0x180011316`
- `KERNEL32!FreeLibrary` at `0x180011316`
- `KERNEL32!GetLastError` at `0x180011182`
- `KERNEL32!GetLastError` at `0x1800111cc`
- `KERNEL32!GetLastError` at `0x18001120a`
- `KERNEL32!GetLastError` at `0x1800112c3`
- `KERNEL32!GetLastError` at `0x180011182`
- `KERNEL32!GetLastError` at `0x1800111cc`
- `KERNEL32!GetLastError` at `0x18001120a`
- `KERNEL32!GetLastError` at `0x1800112c3`

## string_xrefs

- `0x180011237`: `CatalogForWOWPrintConfig`
- `0x180011256`: `32-bit PrintConfig.dll failed catalog check.`
- `0x18001125d`: `CopyFileIfNewer`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18001109c  push    rbp
0x18001109e  push    rbx
0x18001109f  push    rsi
0x1800110a0  push    rdi
0x1800110a1  push    r12
0x1800110a3  push    r13
0x1800110a5  push    r14
0x1800110a7  push    r15
0x1800110a9  lea     rbp, [rsp-398h]
0x1800110b1  sub     rsp, 498h
0x1800110b8  mov     [rsp+4D0h+var_478], 0FFFFFFFFFFFFFFFEh
0x1800110c1  mov     rax, cs:__security_cookie
0x1800110c8  xor     rax, rsp
0x1800110cb  mov     [rbp+3D0h+var_50], rax
0x1800110d2  mov     r14, r9
0x1800110d5  mov     rdi, r8
0x1800110d8  mov     r13, rdx
0x1800110db  mov     r12, rcx
0x1800110de  mov     r15, [rbp+3D0h+arg_28]
0x1800110e5  xor     esi, esi
0x1800110e7  mov     [r15], sil
0x1800110ea  mov     [rsp+4D0h+var_4A0], rsi
0x1800110ef  lea     rdx, [rsp+4D0h+var_4A0]; unsigned __int64 *
0x1800110f4  mov     rcx, r8; lptstrFilename
0x1800110f7  call    ?GetFileVersion@@YAJPEBGPEA_K@Z; GetFileVersion(ushort const *,unsigned __int64 *)
0x1800110fc  mov     ebx, eax
0x1800110fe  mov     [rsp+4D0h+var_498], rsi
0x180011103  test    eax, eax
0x180011105  js      loc_180011323
0x18001110b  lea     rdx, [rsp+4D0h+var_498]; unsigned __int64 *
0x180011110  mov     rcx, r14; lptstrFilename
0x180011113  call    ?GetFileVersion@@YAJPEBGPEA_K@Z; GetFileVersion(ushort const *,unsigned __int64 *)
0x180011118  mov     ebx, eax
0x18001111a  cmp     eax, 80070002h
0x18001111f  jz      short loc_18001113C
0x180011121  test    eax, eax
0x180011123  js      loc_180011323
0x180011129  mov     sil, 1
0x18001112c  mov     rax, [rsp+4D0h+var_4A0]
0x180011131  cmp     [rsp+4D0h+var_498], rax
0x180011136  jnb     loc_180011323
0x18001113c  mov     ebx, 208h
0x180011141  mov     r8d, ebx; Size
0x180011144  xor     edx, edx; Val
0x180011146  lea     rcx, [rsp+4D0h+TempFileName]; void *
0x18001114b  call    memset_0
0x180011150  mov     r8d, ebx; Size
0x180011153  xor     edx, edx; Val
0x180011155  lea     rcx, [rbp+3D0h+Buffer]; void *
0x18001115c  call    memset_0
0x180011161  lea     rdx, [rbp+3D0h+Buffer]; lpBuffer
0x180011168  mov     ecx, 104h; nBufferLength
0x18001116d  call    cs:__imp_GetTempPathW
0x180011174  nop     dword ptr [rax+rax+00h]
0x180011179  mov     ebx, 80070000h
0x18001117e  test    eax, eax
0x180011180  jnz     short loc_1800111A6
0x180011182  call    cs:__imp_GetLastError
0x180011189  nop     dword ptr [rax+rax+00h]
0x18001118e  test    eax, eax
0x180011190  jle     short loc_180011197
0x180011192  movzx   eax, ax
0x180011195  or      eax, ebx
0x180011197  mov     dword ptr [rsp+4D0h+var_4A0], eax
0x18001119b  test    eax, eax
0x18001119d  jns     short loc_1800111A6
0x18001119f  xor     bl, bl
0x1800111a1  jmp     loc_180011269
0x1800111a6  lea     r9, [rsp+4D0h+TempFileName]; lpTempFileName
0x1800111ab  xor     r8d, r8d; uUnique
0x1800111ae  lea     rdx, PrefixString; "PC"
0x1800111b5  lea     rcx, [rbp+3D0h+Buffer]; lpPathName
0x1800111bc  call    cs:__imp_GetTempFileNameW
0x1800111c3  nop     dword ptr [rax+rax+00h]
0x1800111c8  test    eax, eax
0x1800111ca  jnz     short loc_1800111ED
0x1800111cc  call    cs:__imp_GetLastError
0x1800111d3  nop     dword ptr [rax+rax+00h]
0x1800111d8  test    eax, eax
0x1800111da  jle     short loc_1800111E1
0x1800111dc  movzx   eax, ax
0x1800111df  or      eax, ebx
0x1800111e1  mov     dword ptr [rsp+4D0h+var_4A0], eax
0x1800111e5  xor     bl, bl
0x1800111e7  test    eax, eax
0x1800111e9  js      short loc_180011269
0x1800111eb  jmp     short loc_1800111EF
0x1800111ed  xor     bl, bl
0x1800111ef  xor     r8d, r8d; bFailIfExists
0x1800111f2  lea     rdx, [rsp+4D0h+TempFileName]; lpNewFileName
0x1800111f7  mov     rcx, rdi; lpExistingFileName
0x1800111fa  call    cs:__imp_CopyFileW
0x180011201  nop     dword ptr [rax+rax+00h]
0x180011206  test    eax, eax
0x180011208  jnz     short loc_18001122C
0x18001120a  call    cs:__imp_GetLastError
0x180011211  nop     dword ptr [rax+rax+00h]
0x180011216  test    eax, eax
0x180011218  jle     short loc_180011222
0x18001121a  movzx   eax, ax
0x18001121d  or      eax, 80070000h
0x180011222  mov     dword ptr [rsp+4D0h+var_4A0], eax
0x180011226  test    eax, eax
0x180011228  js      short loc_180011269
0x18001122a  jmp     short loc_18001122E
0x18001122c  mov     bl, 1
0x18001122e  mov     [rsp+4D0h+var_4B0], 0; struct Win32HandleRAII *
0x180011237  lea     r9, aCatalogforwowp; "CatalogForWOWPrintConfig"
0x18001123e  lea     r8, [rsp+4D0h+TempFileName]; unsigned __int16 *
0x180011243  mov     rdx, r13; HKEY
0x180011246  mov     rcx, r12; hPrinter
0x180011249  call    ?VerifyFileUsingPrinterDataCatalog@@YAJPEAXPEAUHKEY__@@PEBG2PEAVWin32HandleRAII@@@Z; VerifyFileUsingPrinterDataCatalog(void *,HKEY__ *,ushort const *,ushort const *,Win32HandleRAII *)
0x18001124e  mov     dword ptr [rsp+4D0h+var_4A0], eax
0x180011252  test    eax, eax
0x180011254  jns     short loc_180011269
0x180011256  lea     rdx, a32BitPrintconf; "32-bit PrintConfig.dll failed catalog c"...
0x18001125d  lea     rcx, aCopyfileifnewe; "CopyFileIfNewer"
0x180011264  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180011269  lea     rdx, [rsp+4D0h+var_4A0]; int *
0x18001126e  lea     rcx, [rsp+4D0h+hLibModule]; this
0x180011273  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x180011278  neg     bl
0x18001127a  sbb     rdi, rdi
0x18001127d  lea     rax, [rsp+4D0h+TempFileName]
0x180011282  and     rdi, rax
0x180011285  mov     ebx, dword ptr [rsp+4D0h+var_4A0]
0x180011289  test    ebx, ebx
0x18001128b  js      short loc_1800112DE
0x18001128d  test    sil, sil
0x180011290  jz      short loc_18001129E
0x180011292  xor     edx, edx; bool
0x180011294  mov     rcx, r14; lpExistingFileName
0x180011297  call    ?DeleteFileNowOrOnReboot@@YAJPEBG_N@Z; DeleteFileNowOrOnReboot(ushort const *,bool)
0x18001129c  mov     ebx, eax
0x18001129e  test    ebx, ebx
0x1800112a0  js      short loc_1800112DE
0x1800112a2  xor     r8d, r8d; bFailIfExists
0x1800112a5  mov     rdx, r14; lpNewFileName
0x1800112a8  lea     rcx, [rsp+4D0h+TempFileName]; lpExistingFileName
0x1800112ad  call    cs:__imp_CopyFileW
0x1800112b4  nop     dword ptr [rax+rax+00h]
0x1800112b9  test    eax, eax
0x1800112bb  jz      short loc_1800112C3
0x1800112bd  mov     byte ptr [r15], 1
0x1800112c1  jmp     short loc_1800112DE
0x1800112c3  call    cs:__imp_GetLastError
0x1800112ca  nop     dword ptr [rax+rax+00h]
0x1800112cf  mov     ebx, eax
0x1800112d1  test    eax, eax
0x1800112d3  jle     short loc_1800112DE
0x1800112d5  movzx   ebx, ax
0x1800112d8  or      ebx, 80070000h
0x1800112de  test    rdi, rdi
0x1800112e1  jz      short loc_1800112F3
0x1800112e3  mov     rcx, rdi; lpFileName
0x1800112e6  call    cs:__imp_DeleteFileW
0x1800112ed  nop     dword ptr [rax+rax+00h]
0x1800112f2  nop
0x1800112f3  mov     rax, [rsp+4D0h+var_480]
0x1800112f8  test    rax, rax
0x1800112fb  jz      short loc_18001130C
0x1800112fd  mov     rcx, [rsp+4D0h+var_488]
0x180011302  test    rcx, rcx
0x180011305  jz      short loc_18001130C
0x180011307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001130c  mov     rcx, [rsp+4D0h+hLibModule]; hLibModule
0x180011311  test    rcx, rcx
0x180011314  jz      short loc_180011323
0x180011316  call    cs:__imp_FreeLibrary
0x18001131d  nop     dword ptr [rax+rax+00h]
0x180011322  nop
0x180011323  mov     eax, ebx
0x180011325  mov     rcx, [rbp+3D0h+var_50]
0x18001132c  xor     rcx, rsp; StackCookie
0x18001132f  call    __security_check_cookie
0x180011334  add     rsp, 498h
0x18001133b  pop     r15
0x18001133d  pop     r14
0x18001133f  pop     r13
0x180011341  pop     r12
0x180011343  pop     rdi
0x180011344  pop     rsi
0x180011345  pop     rbx
0x180011346  pop     rbp
0x180011347  retn
```
