# GenerateDumpFileName(ushort *,unsigned __int64)

- ea: `0x140066ac8`
- end: `0x140066fe0`
- name: `?GenerateDumpFileName@@YAJPEAG_K@Z`
- size: `1304`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140069c40`

## callees

- `0x1400016b8`
- `0x1400033e8`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`
- `0x14005c408`
- `0x140061a0c`
- `0x140066ac8`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140066b5a`
- `ADVAPI32!RegOpenKeyExW` at `0x140066b5a`
- `ADVAPI32!RegCloseKey` at `0x140066fab`
- `ADVAPI32!RegCloseKey` at `0x140066fab`
- `KERNEL32!GetTimeFormatEx` at `0x140066e8c`
- `KERNEL32!GetTimeFormatEx` at `0x140066e8c`
- `KERNEL32!GetDateFormatEx` at `0x140066e3d`
- `KERNEL32!GetDateFormatEx` at `0x140066e3d`
- `KERNEL32!GetModuleFileNameW` at `0x140066c3f`
- `KERNEL32!GetModuleFileNameW` at `0x140066c3f`
- `KERNEL32!ProcessIdToSessionId` at `0x140066d8e`
- `KERNEL32!ProcessIdToSessionId` at `0x140066d8e`
- `KERNEL32!GetCurrentProcessId` at `0x140066d81`
- `KERNEL32!GetCurrentProcessId` at `0x140066d81`
- `KERNEL32!GetLastError` at `0x140066d98`
- `KERNEL32!GetLastError` at `0x140066e47`
- `KERNEL32!GetLastError` at `0x140066e96`
- `KERNEL32!GetLastError` at `0x140066f03`
- `KERNEL32!GetLastError` at `0x140066d98`
- `KERNEL32!GetLastError` at `0x140066e47`
- `KERNEL32!GetLastError` at `0x140066e96`
- `KERNEL32!GetLastError` at `0x140066f03`
- `KERNEL32!IsDebuggerPresent` at `0x140066be1`
- `KERNEL32!IsDebuggerPresent` at `0x140066d15`
- `KERNEL32!IsDebuggerPresent` at `0x140066de5`
- `KERNEL32!IsDebuggerPresent` at `0x140066f5e`
- `KERNEL32!IsDebuggerPresent` at `0x140066be1`
- `KERNEL32!IsDebuggerPresent` at `0x140066d15`
- `KERNEL32!IsDebuggerPresent` at `0x140066de5`
- `KERNEL32!IsDebuggerPresent` at `0x140066f5e`
- `msvcrt!wcsrchr` at `0x140066cc7`
- `msvcrt!wcsrchr` at `0x140066cc7`

## string_xrefs

- `0x140066bb2`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140066cd7`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140066f46`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140066f1a`: `cchUsedWithoutNull != 0 && cchUsedWithoutNull != (sizeof(*RtlpNumberOf(szModulePathName)))`

## pseudocode

```c
__int64 __fastcall GenerateDumpFileName(unsigned __int16 *a1)
{
  LSTATUS v2; // eax
  signed int StringValue; // ebx
  const unsigned __int16 *v4; // r13
  unsigned int v5; // r15d
  unsigned int v6; // r13d
  DWORD ModuleFileNameW; // eax
  WCHAR *v8; // rax
  WCHAR *v9; // rcx
  wchar_t *v10; // rax
  const unsigned __int16 *v11; // r9
  WCHAR *v12; // rbx
  DWORD CurrentProcessId; // eax
  signed int v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  signed int LastError; // eax
  const unsigned __int16 *cchDate; // [rsp+28h] [rbp-D8h]
  int cchDatea[2]; // [rsp+28h] [rbp-D8h]
  LPCWSTR lpCalendar; // [rsp+30h] [rbp-D0h]
  LPCWSTR lpCalendara; // [rsp+30h] [rbp-D0h]
  __int64 v23; // [rsp+38h] [rbp-C8h]
  DWORD pSessionId; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  void *Block; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR TimeStr[8]; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v28; // [rsp+68h] [rbp-98h]
  WCHAR DateStr[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v30; // [rsp+80h] [rbp-80h]
  WCHAR Filename[260]; // [rsp+90h] [rbp-70h] BYREF
  char v32; // [rsp+298h] [rbp+198h] BYREF

  hKey = 0;
  memset_0(Filename, 0, sizeof(Filename));
  Block = 0;
  v30 = 0;
  v28 = 0;
  pSessionId = 0;
  *a1 = 0;
  *(_OWORD *)DateStr = 0;
  *(_OWORD *)TimeStr = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows MultiPoint Server", 0, 1u, &hKey);
  StringValue = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      StringValue = (unsigned __int16)v2 | 0x80070000;
    v4 = L"lr == 0L";
    v5 = 1959;
LABEL_56:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      v5,
      L"GenerateDumpFileName",
      L"CBRAEx",
      v4,
      StringValue);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v5,
        L"GenerateDumpFileName",
        L"CBRAEx",
        v4,
        StringValue);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v5,
        L"GenerateDumpFileName",
        L"CBRAEx",
        v4,
        StringValue);
    goto LABEL_59;
  }
  StringValue = RegUtil::GetStringValue(0, hKey, L"ProductDumpsDir", &Block);
  if ( StringValue < 0 )
  {
    v6 = 1962;
    goto LABEL_7;
  }
  ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x104u);
  if ( !ModuleFileNameW || ModuleFileNameW == 260 )
  {
    LastError = GetLastError();
    StringValue = LastError;
    if ( LastError > 0 )
      StringValue = (unsigned __int16)LastError | 0x80070000;
    v4 = L"cchUsedWithoutNull != 0 && cchUsedWithoutNull != (sizeof(*RtlpNumberOf(szModulePathName)))";
    v5 = 1969;
    if ( StringValue >= 0 )
      StringValue = -2147467259;
    goto LABEL_56;
  }
  v8 = Filename;
  v9 = 0;
  while ( *v8 )
  {
    switch ( *v8 )
    {
      case ' ':
        goto LABEL_18;
      case '.':
        v9 = v8;
        break;
      case '\\':
LABEL_18:
        v9 = 0;
        break;
    }
    if ( ++v8 >= (WCHAR *)&v32 )
      break;
  }
  if ( v8 >= (WCHAR *)&v32 )
  {
    StringValue = -2147024809;
    v6 = 1972;
    goto LABEL_7;
  }
  if ( !v9 )
    v9 = v8;
  if ( *v9 )
    *v9 = 0;
  v10 = wcsrchr(Filename, 0x5Cu);
  if ( v10 )
  {
    v12 = v10 + 1;
    if ( !v10[1] )
    {
      LOGASSERT(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        0x7BAu,
        L"GenerateDumpFileName",
        v11,
        L"*pszModuleFileName != L'\\0'");
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          1978,
          L"GenerateDumpFileName",
          L"ASSERT",
          L"*pszModuleFileName != L'\\0'");
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
          L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
          1978,
          L"GenerateDumpFileName",
          L"ASSERT",
          L"*pszModuleFileName != L'\\0'");
    }
  }
  else
  {
    v12 = Filename;
  }
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
  {
    v14 = GetLastError();
    StringValue = v14;
    if ( v14 > 0 )
      StringValue = (unsigned __int16)v14 | 0x80070000;
    v6 = 1990;
    goto LABEL_37;
  }
  if ( !GetDateFormatEx(&psz, 0, 0, aYyyyyMmDd, DateStr, 12, 0) )
  {
    v15 = GetLastError();
    StringValue = v15;
    if ( v15 > 0 )
      StringValue = (unsigned __int16)v15 | 0x80070000;
    v6 = 1994;
    goto LABEL_37;
  }
  if ( GetTimeFormatEx(&psz, 0, 0, aHhMmSs, TimeStr, 9) )
  {
    cchDatea[0] = pSessionId;
    StringValue = StringCchPrintfW(
                    a1,
                    0x104u,
                    L"%s\\%s_%d_%s_%s.dmp",
                    Block,
                    v12,
                    *(_QWORD *)cchDatea,
                    DateStr,
                    TimeStr);
    if ( StringValue < 0 )
    {
      v6 = 2000;
LABEL_7:
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v6,
        L"GenerateDumpFileName",
        L"CHRA",
        L"hr",
        StringValue);
      if ( IsDebuggerPresent() )
      {
        LODWORD(v23) = StringValue;
        lpCalendara = L"hr";
        cchDate = L"CHRA";
        goto LABEL_9;
      }
      LODWORD(lpCalendar) = StringValue;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v6,
        L"GenerateDumpFileName",
        L"CHRA",
        L"hr",
        lpCalendar);
    }
  }
  else
  {
    v16 = GetLastError();
    StringValue = v16;
    if ( v16 > 0 )
      StringValue = (unsigned __int16)v16 | 0x80070000;
    v6 = 1997;
LABEL_37:
    if ( StringValue >= 0 )
      StringValue = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      v6,
      L"GenerateDumpFileName",
      L"CBRAEx",
      L"fSuccess",
      StringValue);
    if ( IsDebuggerPresent() )
    {
      LODWORD(v23) = StringValue;
      lpCalendara = L"fSuccess";
      cchDate = L"CBRAEx";
LABEL_9:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v6,
        L"GenerateDumpFileName",
        cchDate,
        lpCalendara,
        v23);
    }
    else
    {
      LODWORD(lpCalendar) = StringValue;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v6,
        L"GenerateDumpFileName",
        L"CBRAEx",
        L"fSuccess",
        lpCalendar);
    }
  }
LABEL_59:
  if ( hKey )
    RegCloseKey(hKey);
  operator delete(Block);
  return (unsigned int)StringValue;
}

```

## disassembly

```asm
0x140066ac8  push    rbp
0x140066aca  push    rbx
0x140066acb  push    rsi
0x140066acc  push    rdi
0x140066acd  push    r12
0x140066acf  push    r13
0x140066ad1  push    r14
0x140066ad3  push    r15
0x140066ad5  lea     rbp, [rsp-1B8h]
0x140066add  sub     rsp, 2B8h
0x140066ae4  mov     rax, cs:__security_cookie
0x140066aeb  xor     rax, rsp
0x140066aee  mov     [rbp+1F0h+var_50], rax
0x140066af5  mov     r14, rcx
0x140066af8  xor     r12d, r12d
0x140066afb  lea     rcx, [rbp+1F0h+Filename]; void *
0x140066aff  mov     [rsp+2F0h+hKey], r12
0x140066b04  xor     edx, edx; Val
0x140066b06  mov     r8d, 208h; Size
0x140066b0c  call    memset_0
0x140066b11  xor     eax, eax
0x140066b13  mov     [rsp+2F0h+Block], r12
0x140066b18  mov     [rbp+1F0h+var_270], rax
0x140066b1c  lea     r9d, [r12+1]; samDesired
0x140066b21  mov     [rsp+2F0h+var_288], ax
0x140066b26  lea     rdx, aSoftwareMicros_33; "SOFTWARE\\Microsoft\\Windows MultiPoint"...
0x140066b2d  lea     rax, [rsp+2F0h+hKey]
0x140066b32  mov     [rsp+2F0h+pSessionId], r12d
0x140066b37  xorps   xmm0, xmm0
0x140066b3a  mov     [rsp+2F0h+phkResult], rax; phkResult
0x140066b3f  xorps   xmm1, xmm1
0x140066b42  mov     [r14], r12w
0x140066b46  xor     r8d, r8d; ulOptions
0x140066b49  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140066b50  movups  xmmword ptr [rsp+2F0h+DateStr], xmm0
0x140066b55  movups  xmmword ptr [rsp+2F0h+TimeStr], xmm1
0x140066b5a  call    cs:__imp_RegOpenKeyExW
0x140066b60  mov     ebx, eax
0x140066b62  test    eax, eax
0x140066b64  jz      short loc_140066B83
0x140066b66  jle     short loc_140066B71
0x140066b68  movzx   ebx, ax
0x140066b6b  or      ebx, 80070000h
0x140066b71  lea     r13, aLr0l; "lr == 0L"
0x140066b78  mov     r15d, 7A7h
0x140066b7e  jmp     loc_140066F2F
0x140066b83  mov     rdx, [rsp+2F0h+hKey]
0x140066b88  lea     r9, [rsp+2F0h+Block]
0x140066b8d  lea     r8, aProductdumpsdi; "ProductDumpsDir"
0x140066b94  xor     ecx, ecx
0x140066b96  call    ?GetStringValue@RegUtil@@YAJW4EValueRequired@1@PEAUHKEY__@@PEBGPEAPEAG@Z; RegUtil::GetStringValue(RegUtil::EValueRequired,HKEY__ *,ushort const *,ushort * *)
0x140066b9b  mov     ebx, eax
0x140066b9d  test    eax, eax
0x140066b9f  jns     loc_140066C30
0x140066ba5  mov     r13d, 7AAh
0x140066bab  lea     rsi, aGeneratedumpfi; "GenerateDumpFileName"
0x140066bb2  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140066bb9  lea     r15, aChra; "CHRA"
0x140066bc0  mov     [rsp+2F0h+cchDate], ebx; int
0x140066bc4  lea     r14, aHr; "hr"
0x140066bcb  mov     r9, r15; unsigned __int16 *
0x140066bce  mov     r8, rsi; unsigned __int16 *
0x140066bd1  mov     [rsp+2F0h+phkResult], r14; unsigned __int16 *
0x140066bd6  mov     edx, r13d; unsigned int
0x140066bd9  mov     rcx, rdi; unsigned __int16 *
0x140066bdc  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140066be1  call    cs:__imp_IsDebuggerPresent
0x140066be7  test    eax, eax
0x140066be9  jz      short loc_140066C1A
0x140066beb  mov     dword ptr [rsp+2F0h+var_2B8], ebx
0x140066bef  mov     [rsp+2F0h+lpCalendar], r14
0x140066bf4  mov     qword ptr [rsp+2F0h+cchDate], r15
0x140066bf9  mov     r9d, r13d
0x140066bfc  mov     r8, rdi
0x140066bff  mov     [rsp+2F0h+phkResult], rsi
0x140066c04  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140066c0b  mov     ecx, 2; unsigned __int8
0x140066c10  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140066c15  jmp     loc_140066FA1
0x140066c1a  mov     dword ptr [rsp+2F0h+lpCalendar], ebx
0x140066c1e  mov     r8d, r13d
0x140066c21  mov     qword ptr [rsp+2F0h+cchDate], r14
0x140066c26  mov     [rsp+2F0h+phkResult], r15
0x140066c2b  jmp     loc_140066F8F
0x140066c30  mov     r15d, 104h
0x140066c36  lea     rdx, [rbp+1F0h+Filename]; lpFilename
0x140066c3a  mov     r8d, r15d; nSize
0x140066c3d  xor     ecx, ecx; hModule
0x140066c3f  call    cs:__imp_GetModuleFileNameW
0x140066c45  test    eax, eax
0x140066c47  jz      loc_140066F03
0x140066c4d  cmp     eax, r15d
0x140066c50  jz      loc_140066F03
0x140066c56  lea     rax, [rbp+1F0h+Filename]
0x140066c5a  mov     rcx, r12
0x140066c5d  mov     r8d, 5Ch ; '\'
0x140066c63  cmp     [rax], r12w
0x140066c67  jz      short loc_140066C8E
0x140066c69  cmp     word ptr [rax], 20h ; ' '
0x140066c6d  jz      short loc_140066C7B
0x140066c6f  cmp     word ptr [rax], 2Eh ; '.'
0x140066c73  jz      short loc_140066CAA
0x140066c75  cmp     [rax], r8w
0x140066c79  jnz     short loc_140066C7E
0x140066c7b  mov     rcx, r12
0x140066c7e  add     rax, 2
0x140066c82  lea     rdx, [rbp+1F0h+var_58]
0x140066c89  cmp     rax, rdx
0x140066c8c  jb      short loc_140066C63
0x140066c8e  lea     rdx, [rbp+1F0h+var_58]
0x140066c95  cmp     rax, rdx
0x140066c98  jb      short loc_140066CAF
0x140066c9a  mov     ebx, 80070057h
0x140066c9f  mov     r13d, 7B4h
0x140066ca5  jmp     loc_140066BAB
0x140066caa  mov     rcx, rax
0x140066cad  jmp     short loc_140066C7E
0x140066caf  test    rcx, rcx
0x140066cb2  cmovz   rcx, rax
0x140066cb6  cmp     [rcx], r12w
0x140066cba  jz      short loc_140066CC0
0x140066cbc  mov     [rcx], r12w
0x140066cc0  mov     edx, r8d; Ch
0x140066cc3  lea     rcx, [rbp+1F0h+Filename]; Str
0x140066cc7  call    cs:__imp_wcsrchr
0x140066ccd  lea     rsi, aGeneratedumpfi; "GenerateDumpFileName"
0x140066cd4  mov     rbx, rax
0x140066cd7  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140066cde  test    rax, rax
0x140066ce1  jz      loc_140066D7D
0x140066ce7  add     rbx, 2
0x140066ceb  cmp     [rbx], r12w
0x140066cef  jnz     loc_140066D81
0x140066cf5  lea     rax, aPszmodulefilen; "*pszModuleFileName != L'\\0'"
0x140066cfc  mov     r13d, 7BAh
0x140066d02  mov     edx, r13d; unsigned int
0x140066d05  mov     [rsp+2F0h+phkResult], rax; unsigned __int16 *
0x140066d0a  mov     r8, rsi; unsigned __int16 *
0x140066d0d  mov     rcx, rdi; unsigned __int16 *
0x140066d10  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140066d15  call    cs:__imp_IsDebuggerPresent
0x140066d1b  test    eax, eax
0x140066d1d  lea     rax, aPszmodulefilen; "*pszModuleFileName != L'\\0'"
0x140066d24  jz      short loc_140066D55
0x140066d26  mov     [rsp+2F0h+lpCalendar], rax
0x140066d2b  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140066d32  lea     rax, aAssert; "ASSERT"
0x140066d39  mov     r9d, r13d
0x140066d3c  mov     qword ptr [rsp+2F0h+cchDate], rax
0x140066d41  mov     r8, rdi
0x140066d44  mov     ecx, 2; unsigned __int8
0x140066d49  mov     [rsp+2F0h+phkResult], rsi
0x140066d4e  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140066d53  jmp     short loc_140066D81
0x140066d55  mov     qword ptr [rsp+2F0h+cchDate], rax
0x140066d5a  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140066d61  lea     rax, aAssert; "ASSERT"
0x140066d68  mov     r9, rsi
0x140066d6b  mov     r8d, r13d
0x140066d6e  mov     [rsp+2F0h+phkResult], rax
0x140066d73  mov     rdx, rdi
0x140066d76  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140066d7b  jmp     short loc_140066D81
0x140066d7d  lea     rbx, [rbp+1F0h+Filename]
0x140066d81  call    cs:__imp_GetCurrentProcessId
0x140066d87  mov     ecx, eax; dwProcessId
0x140066d89  lea     rdx, [rsp+2F0h+pSessionId]; pSessionId
0x140066d8e  call    cs:__imp_ProcessIdToSessionId
0x140066d94  test    eax, eax
0x140066d96  jnz     short loc_140066E13
0x140066d98  call    cs:__imp_GetLastError
0x140066d9e  mov     ebx, eax
0x140066da0  test    eax, eax
0x140066da2  jle     short loc_140066DAD
0x140066da4  movzx   ebx, ax
0x140066da7  or      ebx, 80070000h
0x140066dad  mov     r13d, 7C6h
0x140066db3  mov     eax, 80004005h
0x140066db8  lea     r14, aCbraex; "CBRAEx"
0x140066dbf  test    ebx, ebx
0x140066dc1  lea     r15, aFsuccess; "fSuccess"
0x140066dc8  mov     r9, r14; unsigned __int16 *
0x140066dcb  mov     r8, rsi; unsigned __int16 *
0x140066dce  cmovns  ebx, eax
0x140066dd1  mov     edx, r13d; unsigned int
0x140066dd4  mov     [rsp+2F0h+cchDate], ebx; int
0x140066dd8  mov     rcx, rdi; unsigned __int16 *
0x140066ddb  mov     [rsp+2F0h+phkResult], r15; unsigned __int16 *
0x140066de0  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140066de5  call    cs:__imp_IsDebuggerPresent
0x140066deb  test    eax, eax
0x140066ded  jz      short loc_140066E02
0x140066def  mov     dword ptr [rsp+2F0h+var_2B8], ebx
0x140066df3  mov     [rsp+2F0h+lpCalendar], r15
0x140066df8  mov     qword ptr [rsp+2F0h+cchDate], r14
0x140066dfd  jmp     loc_140066BF9
0x140066e02  mov     dword ptr [rsp+2F0h+lpCalendar], ebx
0x140066e06  mov     r8d, r13d
0x140066e09  mov     qword ptr [rsp+2F0h+cchDate], r15
0x140066e0e  jmp     loc_140066F8A
0x140066e13  mov     [rsp+2F0h+lpCalendar], r12; lpCalendar
0x140066e18  lea     rax, [rsp+2F0h+DateStr]
0x140066e1d  mov     [rsp+2F0h+cchDate], 0Ch; cchDate
0x140066e25  lea     r9, aYyyyyMmDd; "yyyyy-MM-dd"
0x140066e2c  xor     r8d, r8d; lpDate
0x140066e2f  mov     [rsp+2F0h+phkResult], rax; lpDateStr
0x140066e34  xor     edx, edx; dwFlags
0x140066e36  lea     rcx, psz; lpLocaleName
0x140066e3d  call    cs:__imp_GetDateFormatEx
0x140066e43  test    eax, eax
0x140066e45  jnz     short loc_140066E67
0x140066e47  call    cs:__imp_GetLastError
0x140066e4d  mov     ebx, eax
0x140066e4f  test    eax, eax
0x140066e51  jle     short loc_140066E5C
0x140066e53  movzx   ebx, ax
0x140066e56  or      ebx, 80070000h
0x140066e5c  mov     r13d, 7CAh
0x140066e62  jmp     loc_140066DB3
0x140066e67  lea     rax, [rsp+2F0h+TimeStr]
0x140066e6c  mov     [rsp+2F0h+cchDate], 9; cchTime
0x140066e74  lea     r9, aHhMmSs; "HH-mm-ss"
0x140066e7b  mov     [rsp+2F0h+phkResult], rax; lpTimeStr
0x140066e80  xor     r8d, r8d; lpTime
0x140066e83  lea     rcx, psz; lpLocaleName
0x140066e8a  xor     edx, edx; dwFlags
0x140066e8c  call    cs:__imp_GetTimeFormatEx
0x140066e92  test    eax, eax
0x140066e94  jnz     short loc_140066EB6
0x140066e96  call    cs:__imp_GetLastError
0x140066e9c  mov     ebx, eax
0x140066e9e  test    eax, eax
0x140066ea0  jle     short loc_140066EAB
0x140066ea2  movzx   ebx, ax
0x140066ea5  or      ebx, 80070000h
0x140066eab  mov     r13d, 7CDh
0x140066eb1  jmp     loc_140066DB3
0x140066eb6  mov     r9, [rsp+2F0h+Block]
0x140066ebb  lea     rax, [rsp+2F0h+TimeStr]
0x140066ec0  mov     [rsp+2F0h+var_2B8], rax
0x140066ec5  lea     r8, aSSDSSDmp; "%s\\%s_%d_%s_%s.dmp"
0x140066ecc  lea     rax, [rsp+2F0h+DateStr]
0x140066ed1  mov     rdx, r15; unsigned __int64
0x140066ed4  mov     [rsp+2F0h+lpCalendar], rax
0x140066ed9  mov     rcx, r14; unsigned __int16 *
0x140066edc  mov     eax, [rsp+2F0h+pSessionId]
0x140066ee0  mov     [rsp+2F0h+cchDate], eax
0x140066ee4  mov     [rsp+2F0h+phkResult], rbx
0x140066ee9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140066eee  mov     ebx, eax
0x140066ef0  test    eax, eax
0x140066ef2  jns     loc_140066FA1
0x140066ef8  mov     r13d, 7D0h
0x140066efe  jmp     loc_140066BB9
0x140066f03  call    cs:__imp_GetLastError
0x140066f09  mov     ebx, eax
0x140066f0b  test    eax, eax
0x140066f0d  jle     short loc_140066F18
0x140066f0f  movzx   ebx, ax
0x140066f12  or      ebx, 80070000h
0x140066f18  test    ebx, ebx
0x140066f1a  lea     r13, aCchusedwithout; "cchUsedWithoutNull != 0 && cchUsedWitho"...
0x140066f21  mov     eax, 80004005h
0x140066f26  mov     r15d, 7B1h
0x140066f2c  cmovns  ebx, eax
0x140066f2f  lea     r14, aCbraex; "CBRAEx"
0x140066f36  mov     [rsp+2F0h+cchDate], ebx; int
0x140066f3a  lea     rsi, aGeneratedumpfi; "GenerateDumpFileName"
0x140066f41  mov     [rsp+2F0h+phkResult], r13; unsigned __int16 *
0x140066f46  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140066f4d  mov     r9, r14; unsigned __int16 *
0x140066f50  mov     r8, rsi; unsigned __int16 *
0x140066f53  mov     rcx, rdi; unsigned __int16 *
0x140066f56  mov     edx, r15d; unsigned int
0x140066f59  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140066f5e  call    cs:__imp_IsDebuggerPresent
0x140066f64  test    eax, eax
0x140066f66  jz      short loc_140066F7E
0x140066f68  mov     dword ptr [rsp+2F0h+var_2B8], ebx
0x140066f6c  mov     r9d, r15d
0x140066f6f  mov     [rsp+2F0h+lpCalendar], r13
0x140066f74  mov     qword ptr [rsp+2F0h+cchDate], r14
0x140066f79  jmp     loc_140066BFC
0x140066f7e  mov     dword ptr [rsp+2F0h+lpCalendar], ebx
0x140066f82  mov     r8d, r15d
0x140066f85  mov     qword ptr [rsp+2F0h+cchDate], r13
0x140066f8a  mov     [rsp+2F0h+phkResult], r14
0x140066f8f  mov     r9, rsi
0x140066f92  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140066f99  mov     rdx, rdi
0x140066f9c  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140066fa1  mov     rcx, [rsp+2F0h+hKey]; hKey
0x140066fa6  test    rcx, rcx
0x140066fa9  jz      short loc_140066FB1
0x140066fab  call    cs:__imp_RegCloseKey
0x140066fb1  mov     rcx, [rsp+2F0h+Block]; Block
0x140066fb6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140066fbb  mov     eax, ebx
0x140066fbd  mov     rcx, [rbp+1F0h+var_50]
0x140066fc4  xor     rcx, rsp; StackCookie
  ... truncated ...
```
