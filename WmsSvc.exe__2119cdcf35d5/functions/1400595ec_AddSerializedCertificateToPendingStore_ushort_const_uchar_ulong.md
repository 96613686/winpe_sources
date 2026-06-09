# AddSerializedCertificateToPendingStore(ushort * const,uchar *,ulong)

- ea: `0x1400595ec`
- end: `0x1400599dd`
- name: `?AddSerializedCertificateToPendingStore@@YAJQEAGPEAEK@Z`
- size: `1009`
- prototype: `__int64 __fastcall(BSTR pbstr, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, service_task`

## callers

- `0x140055970`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x1400033e8`
- `0x140012158`
- `0x1400595ec`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140076488`
- `0x14007cbd0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400599a6`
- `KERNEL32!CloseHandle` at `0x1400599a6`
- `KERNEL32!CreateFileW` at `0x140059818`
- `KERNEL32!CreateFileW` at `0x140059818`
- `KERNEL32!WriteFile` at `0x1400598d6`
- `KERNEL32!WriteFile` at `0x1400598d6`
- `KERNEL32!GetLastError` at `0x14005982b`
- `KERNEL32!GetLastError` at `0x1400598e4`
- `KERNEL32!GetLastError` at `0x14005982b`
- `KERNEL32!GetLastError` at `0x1400598e4`
- `KERNEL32!IsDebuggerPresent` at `0x140059725`
- `KERNEL32!IsDebuggerPresent` at `0x1400597e0`
- `KERNEL32!IsDebuggerPresent` at `0x140059886`
- `KERNEL32!IsDebuggerPresent` at `0x14005993f`
- `KERNEL32!IsDebuggerPresent` at `0x140059725`
- `KERNEL32!IsDebuggerPresent` at `0x1400597e0`
- `KERNEL32!IsDebuggerPresent` at `0x140059886`
- `KERNEL32!IsDebuggerPresent` at `0x14005993f`
- `OLEAUT32!__imp_SysStringLen` at `0x1400596b8`
- `OLEAUT32!__imp_SysStringLen` at `0x1400596b8`

## string_xrefs

- `0x1400596fd`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x1400597b8`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x14005985b`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x140059914`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x140059654`: `AddSerializedCertificateToPendingStore\n`
- `0x1400596ee`: `AddSerializedCertificateToPendingStore`
- `0x1400597ab`: `AddSerializedCertificateToPendingStore`
- `0x14005984e`: `AddSerializedCertificateToPendingStore`
- `0x140059907`: `AddSerializedCertificateToPendingStore`
- `0x140059707`: `pszPendingCertificatePathName`

## pseudocode

```c
__int64 __fastcall AddSerializedCertificateToPendingStore(BSTR pbstr, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)
{
  WCHAR *v4; // r12
  signed int ReserveVolume; // ebx
  unsigned __int16 v8; // di
  unsigned __int64 v9; // rbx
  unsigned __int16 *v10; // rax
  unsigned int v11; // r14d
  const unsigned __int16 *v12; // r13
  bool v13; // zf
  const unsigned __int16 *v14; // rax
  int v15; // eax
  HANDLE FileW; // rax
  void *v17; // r15
  signed int LastError; // eax
  signed int v19; // eax
  HANDLE hTemplateFile; // [rsp+30h] [rbp-59h]
  unsigned __int16 v22[2]; // [rsp+40h] [rbp-49h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-45h] BYREF
  WCHAR pObjectName[20]; // [rsp+48h] [rbp-41h] BYREF
  unsigned __int16 v25; // [rsp+70h] [rbp-19h] BYREF
  __int128 v26; // [rsp+72h] [rbp-17h]
  __int128 v27; // [rsp+82h] [rbp-7h]
  __int64 v28; // [rsp+92h] [rbp+9h]

  v22[0] = 0;
  v4 = 0;
  wcscpy(pObjectName, L"X:\\MultiPointData");
  v25 = 88;
  v26 = *(_OWORD *)L":\\MultiPointData\\%s";
  NumberOfBytesWritten = 0;
  v28 = *(_QWORD *)L"\\%s";
  v27 = *(_OWORD *)L"ointData\\%s";
  DEBUGMSG(L"AddSerializedCertificateToPendingStore\n");
  ReserveVolume = CDiskProtection::s_GetReserveVolume(v22);
  if ( ReserveVolume >= 0 )
  {
    v8 = v22[0];
    pObjectName[0] = v22[0];
    ReserveVolume = CreatePendingCertificateStoreFolder(pObjectName);
    if ( ReserveVolume >= 0 )
    {
      v9 = SysStringLen(pbstr) + 21;
      v10 = (unsigned __int16 *)operator new(saturated_mul(v9, 2u));
      v4 = v10;
      if ( !v10 )
      {
        ReserveVolume = -2147024882;
        v11 = 96;
        v12 = L"pszPendingCertificatePathName";
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
          0x60u,
          L"AddSerializedCertificateToPendingStore",
          L"CPR",
          L"pszPendingCertificatePathName",
          -2147024882);
        v13 = !IsDebuggerPresent();
        v14 = L"CPR";
        goto LABEL_5;
      }
      v25 = v8;
      v15 = StringCchPrintfW(v10, v9, &v25, pbstr);
      ReserveVolume = v15;
      if ( v15 < 0 )
      {
        v11 = 100;
        v12 = L"hr";
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
          0x64u,
          L"AddSerializedCertificateToPendingStore",
          L"CHRA",
          L"hr",
          v15);
        v13 = !IsDebuggerPresent();
        v14 = L"CHRA";
LABEL_5:
        if ( v13 )
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
            v11,
            L"AddSerializedCertificateToPendingStore",
            v14,
            v12,
            ReserveVolume);
        else
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
            v11,
            L"AddSerializedCertificateToPendingStore",
            v14,
            v12,
            ReserveVolume);
        goto LABEL_28;
      }
      FileW = CreateFileW(v4, 0x40000000u, 0, 0, 2u, 0x80u, 0);
      v17 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        ReserveVolume = LastError;
        if ( LastError > 0 )
          ReserveVolume = (unsigned __int16)LastError | 0x80070000;
        if ( ReserveVolume >= 0 )
          ReserveVolume = -2147467259;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
          0x67u,
          L"AddSerializedCertificateToPendingStore",
          L"CBRAEx",
          L"hFile != ((HANDLE)(LONG_PTR)-1)",
          ReserveVolume);
        if ( IsDebuggerPresent() )
        {
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
            103,
            L"AddSerializedCertificateToPendingStore",
            L"CBRAEx",
            L"hFile != ((HANDLE)(LONG_PTR)-1)",
            ReserveVolume);
        }
        else
        {
          LODWORD(hTemplateFile) = ReserveVolume;
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
            103,
            L"AddSerializedCertificateToPendingStore",
            L"CBRAEx",
            L"hFile != ((HANDLE)(LONG_PTR)-1)",
            hTemplateFile);
        }
      }
      else
      {
        if ( !WriteFile(FileW, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
        {
          v19 = GetLastError();
          ReserveVolume = v19;
          if ( v19 > 0 )
            ReserveVolume = (unsigned __int16)v19 | 0x80070000;
          if ( ReserveVolume >= 0 )
            ReserveVolume = -2147467259;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
            0x6Au,
            L"AddSerializedCertificateToPendingStore",
            L"CBRAEx",
            L"fSuccess",
            ReserveVolume);
          if ( IsDebuggerPresent() )
          {
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
              106,
              L"AddSerializedCertificateToPendingStore",
              L"CBRAEx",
              L"fSuccess",
              ReserveVolume);
          }
          else
          {
            LODWORD(hTemplateFile) = ReserveVolume;
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
              106,
              L"AddSerializedCertificateToPendingStore",
              L"CBRAEx",
              L"fSuccess",
              hTemplateFile);
          }
        }
        if ( v17 )
          CloseHandle(v17);
      }
    }
  }
LABEL_28:
  operator delete(v4);
  return (unsigned int)ReserveVolume;
}

```

## disassembly

```asm
0x1400595ec  mov     [rsp-8+arg_18], rbx
0x1400595f1  push    rbp
0x1400595f2  push    rsi
0x1400595f3  push    rdi
0x1400595f4  push    r12
0x1400595f6  push    r13
0x1400595f8  push    r14
0x1400595fa  push    r15
0x1400595fc  lea     rbp, [rsp-27h]
0x140059601  sub     rsp, 0B0h
0x140059608  mov     rax, cs:__security_cookie
0x14005960f  xor     rax, rsp
0x140059612  mov     [rbp+57h+var_40], rax
0x140059616  movups  xmm0, xmmword ptr cs:aXMultipointdat_1+2; ":\\MultiPointData"
0x14005961d  xor     eax, eax
0x14005961f  mov     rsi, rcx
0x140059622  movups  xmm1, xmmword ptr cs:aXMultipointdat_1+12h; "ointData"
0x140059629  mov     [rbp+57h+var_A0], ax
0x14005962d  xor     r12d, r12d
0x140059630  movups  [rbp+57h+var_96], xmm0
0x140059634  lea     ecx, [rax+58h]
0x140059637  movzx   eax, word ptr cs:aXMultipointdat_1+22h; ""
0x14005963e  movups  xmm0, xmmword ptr cs:aXMultipointdat+2; ":\\MultiPointData\\%s"
0x140059645  mov     [rbp+57h+pObjectName], cx
0x140059649  mov     r13d, r8d
0x14005964c  movups  [rbp+57h+var_86], xmm1
0x140059650  mov     [rbp+57h+var_70], cx
0x140059654  lea     rcx, aAddserializedc_0; "AddSerializedCertificateToPendingStore"...
0x14005965b  movups  xmm1, xmmword ptr cs:aXMultipointdat+12h; "ointData\\%s"
0x140059662  mov     r14, rdx
0x140059665  mov     [rbp+57h+var_76], ax
0x140059669  movups  [rbp+57h+var_6E], xmm0
0x14005966d  mov     [rbp+57h+NumberOfBytesWritten], r12d
0x140059671  movsd   xmm0, qword ptr cs:aXMultipointdat+22h; "\\%s"
0x140059679  movsd   [rbp+57h+var_4E], xmm0
0x14005967e  movups  [rbp+57h+var_5E], xmm1
0x140059682  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140059687  lea     rcx, [rbp+57h+var_A0]; unsigned __int16 *
0x14005968b  call    ?s_GetReserveVolume@CDiskProtection@@SAJPEAG@Z; CDiskProtection::s_GetReserveVolume(ushort *)
0x140059690  mov     ebx, eax
0x140059692  test    eax, eax
0x140059694  js      loc_1400599AC
0x14005969a  movzx   edi, [rbp+57h+var_A0]
0x14005969e  lea     rcx, [rbp+57h+pObjectName]; pObjectName
0x1400596a2  mov     [rbp+57h+pObjectName], di
0x1400596a6  call    ?CreatePendingCertificateStoreFolder@@YAJPEAG@Z; CreatePendingCertificateStoreFolder(ushort *)
0x1400596ab  mov     ebx, eax
0x1400596ad  test    eax, eax
0x1400596af  js      loc_1400599AC
0x1400596b5  mov     rcx, rsi; pbstr
0x1400596b8  call    cs:__imp_SysStringLen
0x1400596be  lea     rcx, [r12-1]
0x1400596c3  lea     r15d, [r12+2]
0x1400596c8  lea     ebx, [rax+15h]
0x1400596cb  mov     eax, r15d
0x1400596ce  mul     rbx
0x1400596d1  cmovb   rax, rcx
0x1400596d5  mov     rcx, rax; Size
0x1400596d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400596dd  mov     r12, rax
0x1400596e0  test    rax, rax
0x1400596e3  jnz     loc_14005978B
0x1400596e9  mov     ebx, 8007000Eh
0x1400596ee  lea     rsi, aAddserializedc; "AddSerializedCertificateToPendingStore"
0x1400596f5  lea     r14d, [r15+5Eh]
0x1400596f9  mov     [rsp+0E0h+dwFlagsAndAttributes], ebx; int
0x1400596fd  lea     rdi, aTermsrvWmsSrcD_15; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140059704  mov     r8, rsi; unsigned __int16 *
0x140059707  lea     r13, aPszpendingcert; "pszPendingCertificatePathName"
0x14005970e  mov     edx, r14d; unsigned int
0x140059711  mov     rcx, rdi; unsigned __int16 *
0x140059714  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r13; unsigned __int16 *
0x140059719  lea     r9, aCpr; "CPR"
0x140059720  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140059725  call    cs:__imp_IsDebuggerPresent
0x14005972b  test    eax, eax
0x14005972d  lea     rax, aCpr; "CPR"
0x140059734  jz      short loc_140059763
0x140059736  mov     [rsp+0E0h+var_A8], ebx
0x14005973a  mov     r9d, r14d
0x14005973d  mov     [rsp+0E0h+hTemplateFile], r13
0x140059742  mov     ecx, r15d; unsigned __int8
0x140059745  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax
0x14005974a  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140059751  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rsi
0x140059756  mov     r8, rdi
0x140059759  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14005975e  jmp     loc_1400599AC
0x140059763  mov     dword ptr [rsp+0E0h+hTemplateFile], ebx
0x140059767  mov     r8d, r14d
0x14005976a  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], r13
0x14005976f  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax
0x140059774  mov     r9, rsi
0x140059777  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14005977e  mov     rdx, rdi
0x140059781  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140059786  jmp     loc_1400599AC
0x14005978b  mov     r9, rsi
0x14005978e  mov     [rbp+57h+var_70], di
0x140059792  lea     r8, [rbp+57h+var_70]; unsigned __int16 *
0x140059796  mov     rdx, rbx; unsigned __int64
0x140059799  mov     rcx, r12; unsigned __int16 *
0x14005979c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400597a1  mov     ebx, eax
0x1400597a3  test    eax, eax
0x1400597a5  jns     short loc_1400597F4
0x1400597a7  mov     [rsp+0E0h+dwFlagsAndAttributes], eax; int
0x1400597ab  lea     rsi, aAddserializedc; "AddSerializedCertificateToPendingStore"
0x1400597b2  mov     r14d, 64h ; 'd'
0x1400597b8  lea     rdi, aTermsrvWmsSrcD_15; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x1400597bf  lea     r13, aHr; "hr"
0x1400597c6  mov     r8, rsi; unsigned __int16 *
0x1400597c9  mov     edx, r14d; unsigned int
0x1400597cc  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r13; unsigned __int16 *
0x1400597d1  mov     rcx, rdi; unsigned __int16 *
0x1400597d4  lea     r9, aChra; "CHRA"
0x1400597db  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400597e0  call    cs:__imp_IsDebuggerPresent
0x1400597e6  test    eax, eax
0x1400597e8  lea     rax, aChra; "CHRA"
0x1400597ef  jmp     loc_140059734
0x1400597f4  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x1400597fd  xor     r9d, r9d; lpSecurityAttributes
0x140059800  mov     [rsp+0E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140059808  xor     r8d, r8d; dwShareMode
0x14005980b  mov     edx, 40000000h; dwDesiredAccess
0x140059810  mov     [rsp+0E0h+dwCreationDisposition], r15d; dwCreationDisposition
0x140059815  mov     rcx, r12; lpFileName
0x140059818  call    cs:__imp_CreateFileW
0x14005981e  mov     r15, rax
0x140059821  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140059825  jnz     loc_1400598C0
0x14005982b  call    cs:__imp_GetLastError
0x140059831  mov     ebx, eax
0x140059833  test    eax, eax
0x140059835  jle     short loc_140059840
0x140059837  movzx   ebx, ax
0x14005983a  or      ebx, 80070000h
0x140059840  mov     eax, 80004005h
0x140059845  lea     r14, aCbraex; "CBRAEx"
0x14005984c  test    ebx, ebx
0x14005984e  lea     rsi, aAddserializedc; "AddSerializedCertificateToPendingStore"
0x140059855  mov     r15d, 67h ; 'g'
0x14005985b  lea     rdi, aTermsrvWmsSrcD_15; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140059862  cmovns  ebx, eax
0x140059865  lea     r13, aHfileHandleLon; "hFile != ((HANDLE)(LONG_PTR)-1)"
0x14005986c  mov     [rsp+0E0h+dwFlagsAndAttributes], ebx; int
0x140059870  mov     r9, r14; unsigned __int16 *
0x140059873  mov     r8, rsi; unsigned __int16 *
0x140059876  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r13; unsigned __int16 *
0x14005987b  mov     edx, r15d; unsigned int
0x14005987e  mov     rcx, rdi; unsigned __int16 *
0x140059881  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140059886  call    cs:__imp_IsDebuggerPresent
0x14005988c  test    eax, eax
0x14005988e  jz      short loc_1400598AA
0x140059890  mov     [rsp+0E0h+var_A8], ebx
0x140059894  lea     ecx, [r15-65h]
0x140059898  mov     [rsp+0E0h+hTemplateFile], r13
0x14005989d  mov     r9d, r15d
0x1400598a0  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], r14
0x1400598a5  jmp     loc_14005974A
0x1400598aa  mov     dword ptr [rsp+0E0h+hTemplateFile], ebx
0x1400598ae  mov     r8d, r15d
0x1400598b1  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], r13
0x1400598b6  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r14
0x1400598bb  jmp     loc_140059774
0x1400598c0  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400598c4  mov     qword ptr [rsp+0E0h+dwCreationDisposition], 0; lpOverlapped
0x1400598cd  mov     r8d, r13d; nNumberOfBytesToWrite
0x1400598d0  mov     rdx, r14; lpBuffer
0x1400598d3  mov     rcx, r15; hFile
0x1400598d6  call    cs:__imp_WriteFile
0x1400598dc  test    eax, eax
0x1400598de  jnz     loc_14005999E
0x1400598e4  call    cs:__imp_GetLastError
0x1400598ea  mov     ebx, eax
0x1400598ec  test    eax, eax
0x1400598ee  jle     short loc_1400598F9
0x1400598f0  movzx   ebx, ax
0x1400598f3  or      ebx, 80070000h
0x1400598f9  mov     eax, 80004005h
0x1400598fe  lea     r14, aCbraex; "CBRAEx"
0x140059905  test    ebx, ebx
0x140059907  lea     rsi, aAddserializedc; "AddSerializedCertificateToPendingStore"
0x14005990e  mov     r13d, 6Ah ; 'j'
0x140059914  lea     rdi, aTermsrvWmsSrcD_15; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14005991b  cmovns  ebx, eax
0x14005991e  mov     r9, r14; unsigned __int16 *
0x140059921  lea     rax, aFsuccess; "fSuccess"
0x140059928  mov     [rsp+0E0h+dwFlagsAndAttributes], ebx; int
0x14005992c  mov     r8, rsi; unsigned __int16 *
0x14005992f  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax; unsigned __int16 *
0x140059934  mov     edx, r13d; unsigned int
0x140059937  mov     rcx, rdi; unsigned __int16 *
0x14005993a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005993f  call    cs:__imp_IsDebuggerPresent
0x140059945  test    eax, eax
0x140059947  lea     rax, aFsuccess; "fSuccess"
0x14005994e  jz      short loc_14005997B
0x140059950  mov     [rsp+0E0h+var_A8], ebx
0x140059954  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14005995b  mov     [rsp+0E0h+hTemplateFile], rax
0x140059960  lea     ecx, [r13-68h]; unsigned __int8
0x140059964  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], r14
0x140059969  mov     r9d, r13d
0x14005996c  mov     r8, rdi
0x14005996f  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rsi
0x140059974  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140059979  jmp     short loc_14005999E
0x14005997b  mov     dword ptr [rsp+0E0h+hTemplateFile], ebx
0x14005997f  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140059986  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax
0x14005998b  mov     r9, rsi
0x14005998e  mov     r8d, r13d
0x140059991  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r14
0x140059996  mov     rdx, rdi
0x140059999  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14005999e  test    r15, r15
0x1400599a1  jz      short loc_1400599AC
0x1400599a3  mov     rcx, r15; hObject
0x1400599a6  call    cs:__imp_CloseHandle
0x1400599ac  mov     rcx, r12; Block
0x1400599af  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400599b4  mov     eax, ebx
0x1400599b6  mov     rcx, [rbp+57h+var_40]
0x1400599ba  xor     rcx, rsp; StackCookie
0x1400599bd  call    __security_check_cookie
0x1400599c2  mov     rbx, [rsp+0E0h+arg_18]
0x1400599ca  add     rsp, 0B0h
0x1400599d1  pop     r15
0x1400599d3  pop     r14
0x1400599d5  pop     r13
0x1400599d7  pop     r12
0x1400599d9  pop     rdi
0x1400599da  pop     rsi
0x1400599db  pop     rbp
0x1400599dc  retn
```
