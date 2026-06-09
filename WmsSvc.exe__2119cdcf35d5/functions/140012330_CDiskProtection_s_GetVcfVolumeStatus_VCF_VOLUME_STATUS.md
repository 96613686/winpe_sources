# CDiskProtection::s_GetVcfVolumeStatus(_VCF_VOLUME_STATUS *)

- ea: `0x140012330`
- end: `0x1400125bb`
- name: `?s_GetVcfVolumeStatus@CDiskProtection@@KAJPEAU_VCF_VOLUME_STATUS@@@Z`
- size: `651`
- prototype: `__int64 __fastcall(struct _VCF_VOLUME_STATUS *lpOutBuffer)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x140008da0`
- `0x140009778`
- `0x140009e80`
- `0x140013660`

## callees

- `0x1400033e8`
- `0x140012330`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140012593`
- `KERNEL32!CloseHandle` at `0x140012593`
- `KERNEL32!GetWindowsDirectoryW` at `0x14001237b`
- `KERNEL32!GetWindowsDirectoryW` at `0x14001237b`
- `KERNEL32!CreateFileW` at `0x1400124fe`
- `KERNEL32!CreateFileW` at `0x1400124fe`
- `KERNEL32!DeviceIoControl` at `0x140012562`
- `KERNEL32!DeviceIoControl` at `0x140012562`
- `KERNEL32!GetLastError` at `0x140012389`
- `KERNEL32!GetLastError` at `0x14001250d`
- `KERNEL32!GetLastError` at `0x14001256c`
- `KERNEL32!GetLastError` at `0x140012389`
- `KERNEL32!GetLastError` at `0x14001250d`
- `KERNEL32!GetLastError` at `0x14001256c`
- `KERNEL32!IsDebuggerPresent` at `0x1400123e4`
- `KERNEL32!IsDebuggerPresent` at `0x14001249f`
- `KERNEL32!IsDebuggerPresent` at `0x1400123e4`
- `KERNEL32!IsDebuggerPresent` at `0x14001249f`

## pseudocode

```c
__int64 __fastcall CDiskProtection::s_GetVcfVolumeStatus(struct _VCF_VOLUME_STATUS *lpOutBuffer)
{
  signed int LastError; // eax
  signed int v3; // ebx
  const unsigned __int16 *v4; // r12
  unsigned int v5; // r15d
  int v6; // eax
  HANDLE FileW; // rdi
  signed int v8; // eax
  signed int v9; // eax
  HANDLE hTemplateFile; // [rsp+30h] [rbp-278h]
  DWORD BytesReturned[4]; // [rsp+40h] [rbp-268h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-258h] BYREF

  BytesReturned[0] = 0;
  memset_0(Buffer, 0, 0x208u);
  if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v4 = L"fSuccess";
    v5 = 1999;
LABEL_5:
    if ( v3 >= 0 )
      v3 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      v5,
      L"CDiskProtection::s_GetVcfVolumeStatus",
      L"CBRAEx",
      v4,
      v3);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        v5,
        L"CDiskProtection::s_GetVcfVolumeStatus",
        L"CBRAEx",
        v4,
        v3,
        *(_QWORD *)BytesReturned);
    }
    else
    {
      LODWORD(hTemplateFile) = v3;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        v5,
        L"CDiskProtection::s_GetVcfVolumeStatus",
        L"CBRAEx",
        v4,
        hTemplateFile);
    }
    return (unsigned int)v3;
  }
  v6 = StringCchPrintfW(Buffer, 0x104u, L"\\\\.\\%c:", Buffer[0]);
  v3 = v6;
  if ( v6 < 0 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x7D2u,
      L"CDiskProtection::s_GetVcfVolumeStatus",
      L"CHRA",
      L"hr",
      v6);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        2002,
        L"CDiskProtection::s_GetVcfVolumeStatus",
        L"CHRA",
        L"hr",
        v3,
        *(_QWORD *)BytesReturned);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        2002,
        L"CDiskProtection::s_GetVcfVolumeStatus",
        L"CHRA",
        L"hr",
        v3);
    return (unsigned int)v3;
  }
  FileW = CreateFileW(Buffer, 0x80000000, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    v8 = GetLastError();
    v3 = v8;
    if ( v8 > 0 )
      v3 = (unsigned __int16)v8 | 0x80070000;
    v4 = L"hVolume != ((HANDLE)(LONG_PTR)-1)";
    v5 = 2006;
    goto LABEL_5;
  }
  if ( !DeviceIoControl(FileW, 0x32336004u, 0, 0, lpOutBuffer, 0x18u, BytesReturned, 0) )
  {
    v9 = GetLastError();
    v3 = v9;
    if ( v9 > 0 )
      v3 = (unsigned __int16)v9 | 0x80070000;
    if ( v3 >= 0 )
      v3 = -2147467259;
  }
  if ( FileW )
    CloseHandle(FileW);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140012330  push    rbx
0x140012332  push    rbp
0x140012333  push    rsi
0x140012334  push    rdi
0x140012335  push    r12
0x140012337  push    r15
0x140012339  sub     rsp, 278h
0x140012340  mov     rax, cs:__security_cookie
0x140012347  xor     rax, rsp
0x14001234a  mov     [rsp+2A8h+var_48], rax
0x140012352  mov     rsi, rcx
0x140012355  mov     [rsp+2A8h+BytesReturned], 0
0x14001235d  lea     rcx, [rsp+2A8h+Buffer]; void *
0x140012362  xor     edx, edx; Val
0x140012364  mov     r8d, 208h; Size
0x14001236a  call    memset_0
0x14001236f  mov     ebx, 104h
0x140012374  lea     rcx, [rsp+2A8h+Buffer]; lpBuffer
0x140012379  mov     edx, ebx; uSize
0x14001237b  call    cs:__imp_GetWindowsDirectoryW
0x140012381  test    eax, eax
0x140012383  jnz     loc_140012445
0x140012389  call    cs:__imp_GetLastError
0x14001238f  mov     ebx, eax
0x140012391  test    eax, eax
0x140012393  jle     short loc_14001239E
0x140012395  movzx   ebx, ax
0x140012398  or      ebx, 80070000h
0x14001239e  lea     r12, aFsuccess; "fSuccess"
0x1400123a5  mov     r15d, 7CFh
0x1400123ab  mov     eax, 80004005h
0x1400123b0  lea     rbp, aCbraex; "CBRAEx"
0x1400123b7  test    ebx, ebx
0x1400123b9  lea     rsi, aCdiskprotectio_128; "CDiskProtection::s_GetVcfVolumeStatus"
0x1400123c0  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x1400123c7  mov     r9, rbp; unsigned __int16 *
0x1400123ca  cmovns  ebx, eax
0x1400123cd  mov     r8, rsi; unsigned __int16 *
0x1400123d0  mov     [rsp+2A8h+dwFlagsAndAttributes], ebx; int
0x1400123d4  mov     edx, r15d; unsigned int
0x1400123d7  mov     rcx, rdi; unsigned __int16 *
0x1400123da  mov     qword ptr [rsp+2A8h+dwCreationDisposition], r12; unsigned __int16 *
0x1400123df  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400123e4  call    cs:__imp_IsDebuggerPresent
0x1400123ea  test    eax, eax
0x1400123ec  jz      short loc_14001241D
0x1400123ee  mov     dword ptr [rsp+2A8h+lpOverlapped], ebx
0x1400123f2  mov     r9d, r15d
0x1400123f5  mov     [rsp+2A8h+hTemplateFile], r12
0x1400123fa  mov     qword ptr [rsp+2A8h+dwFlagsAndAttributes], rbp
0x1400123ff  mov     r8, rdi
0x140012402  mov     qword ptr [rsp+2A8h+dwCreationDisposition], rsi
0x140012407  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14001240e  mov     ecx, 2; unsigned __int8
0x140012413  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140012418  jmp     loc_140012599
0x14001241d  mov     dword ptr [rsp+2A8h+hTemplateFile], ebx
0x140012421  mov     r8d, r15d
0x140012424  mov     qword ptr [rsp+2A8h+dwFlagsAndAttributes], r12
0x140012429  mov     qword ptr [rsp+2A8h+dwCreationDisposition], rbp
0x14001242e  mov     r9, rsi
0x140012431  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140012438  mov     rdx, rdi
0x14001243b  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140012440  jmp     loc_140012599
0x140012445  movzx   r9d, [rsp+2A8h+Buffer]
0x14001244b  lea     r8, aC; "\\\\.\\%c:"
0x140012452  mov     rdx, rbx; unsigned __int64
0x140012455  lea     rcx, [rsp+2A8h+Buffer]; unsigned __int16 *
0x14001245a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001245f  mov     ebx, eax
0x140012461  test    eax, eax
0x140012463  jns     short loc_1400124D5
0x140012465  mov     [rsp+2A8h+dwFlagsAndAttributes], eax; int
0x140012469  lea     r12, aChra; "CHRA"
0x140012470  lea     rsi, aCdiskprotectio_128; "CDiskProtection::s_GetVcfVolumeStatus"
0x140012477  mov     ebp, 7D2h
0x14001247c  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140012483  mov     r9, r12; unsigned __int16 *
0x140012486  lea     r15, aHr; "hr"
0x14001248d  mov     r8, rsi; unsigned __int16 *
0x140012490  mov     edx, ebp; unsigned int
0x140012492  mov     qword ptr [rsp+2A8h+dwCreationDisposition], r15; unsigned __int16 *
0x140012497  mov     rcx, rdi; unsigned __int16 *
0x14001249a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14001249f  call    cs:__imp_IsDebuggerPresent
0x1400124a5  test    eax, eax
0x1400124a7  jz      short loc_1400124BF
0x1400124a9  mov     dword ptr [rsp+2A8h+lpOverlapped], ebx
0x1400124ad  mov     r9d, ebp
0x1400124b0  mov     [rsp+2A8h+hTemplateFile], r15
0x1400124b5  mov     qword ptr [rsp+2A8h+dwFlagsAndAttributes], r12
0x1400124ba  jmp     loc_1400123FF
0x1400124bf  mov     dword ptr [rsp+2A8h+hTemplateFile], ebx
0x1400124c3  mov     r8d, ebp
0x1400124c6  mov     qword ptr [rsp+2A8h+dwFlagsAndAttributes], r15
0x1400124cb  mov     qword ptr [rsp+2A8h+dwCreationDisposition], r12
0x1400124d0  jmp     loc_14001242E
0x1400124d5  mov     [rsp+2A8h+hTemplateFile], 0; hTemplateFile
0x1400124de  lea     rcx, [rsp+2A8h+Buffer]; lpFileName
0x1400124e3  mov     r8d, 3; dwShareMode
0x1400124e9  mov     [rsp+2A8h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1400124f1  xor     r9d, r9d; lpSecurityAttributes
0x1400124f4  mov     [rsp+2A8h+dwCreationDisposition], r8d; dwCreationDisposition
0x1400124f9  mov     edx, 80000000h; dwDesiredAccess
0x1400124fe  call    cs:__imp_CreateFileW
0x140012504  mov     rdi, rax
0x140012507  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001250b  jnz     short loc_140012534
0x14001250d  call    cs:__imp_GetLastError
0x140012513  mov     ebx, eax
0x140012515  test    eax, eax
0x140012517  jle     short loc_140012522
0x140012519  movzx   ebx, ax
0x14001251c  or      ebx, 80070000h
0x140012522  lea     r12, aHvolumeHandleL; "hVolume != ((HANDLE)(LONG_PTR)-1)"
0x140012529  mov     r15d, 7D6h
0x14001252f  jmp     loc_1400123AB
0x140012534  mov     [rsp+2A8h+lpOverlapped], 0; lpOverlapped
0x14001253d  lea     rax, [rsp+2A8h+BytesReturned]
0x140012542  mov     [rsp+2A8h+hTemplateFile], rax; lpBytesReturned
0x140012547  xor     r9d, r9d; nInBufferSize
0x14001254a  mov     [rsp+2A8h+dwFlagsAndAttributes], 18h; nOutBufferSize
0x140012552  xor     r8d, r8d; lpInBuffer
0x140012555  mov     edx, 32336004h; dwIoControlCode
0x14001255a  mov     qword ptr [rsp+2A8h+dwCreationDisposition], rsi; lpOutBuffer
0x14001255f  mov     rcx, rdi; hDevice
0x140012562  call    cs:__imp_DeviceIoControl
0x140012568  test    eax, eax
0x14001256a  jnz     short loc_14001258B
0x14001256c  call    cs:__imp_GetLastError
0x140012572  mov     ebx, eax
0x140012574  test    eax, eax
0x140012576  jle     short loc_140012581
0x140012578  movzx   ebx, ax
0x14001257b  or      ebx, 80070000h
0x140012581  test    ebx, ebx
0x140012583  mov     eax, 80004005h
0x140012588  cmovns  ebx, eax
0x14001258b  test    rdi, rdi
0x14001258e  jz      short loc_140012599
0x140012590  mov     rcx, rdi; hObject
0x140012593  call    cs:__imp_CloseHandle
0x140012599  mov     eax, ebx
0x14001259b  mov     rcx, [rsp+2A8h+var_48]
0x1400125a3  xor     rcx, rsp; StackCookie
0x1400125a6  call    __security_check_cookie
0x1400125ab  add     rsp, 278h
0x1400125b2  pop     r15
0x1400125b4  pop     r12
0x1400125b6  pop     rdi
0x1400125b7  pop     rsi
0x1400125b8  pop     rbp
0x1400125b9  pop     rbx
0x1400125ba  retn
```
