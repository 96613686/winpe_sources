# GenerateDumpFileName(ushort *,unsigned __int64)

- ea: `0x1400076e0`
- end: `0x140007bef`
- name: `?GenerateDumpFileName@@YAJPEAG_K@Z`
- size: `1295`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140009cb0`

## callees

- `0x1400011d4`
- `0x140002c08`
- `0x1400036d8`
- `0x140003918`
- `0x140003ab4`
- `0x140003c2c`
- `0x1400076e0`
- `0x14000aaa4`
- `0x14000ae32`
- `0x14000ae60`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140007772`
- `ADVAPI32!RegOpenKeyExW` at `0x140007772`
- `ADVAPI32!RegCloseKey` at `0x140007bba`
- `ADVAPI32!RegCloseKey` at `0x140007bba`
- `KERNEL32!GetTimeFormatEx` at `0x140007a9b`
- `KERNEL32!GetTimeFormatEx` at `0x140007a9b`
- `KERNEL32!GetDateFormatEx` at `0x140007a4c`
- `KERNEL32!GetDateFormatEx` at `0x140007a4c`
- `KERNEL32!IsDebuggerPresent` at `0x1400077f0`
- `KERNEL32!IsDebuggerPresent` at `0x140007924`
- `KERNEL32!IsDebuggerPresent` at `0x1400079f4`
- `KERNEL32!IsDebuggerPresent` at `0x140007b6d`
- `KERNEL32!IsDebuggerPresent` at `0x1400077f0`
- `KERNEL32!IsDebuggerPresent` at `0x140007924`
- `KERNEL32!IsDebuggerPresent` at `0x1400079f4`
- `KERNEL32!IsDebuggerPresent` at `0x140007b6d`
- `KERNEL32!GetLastError` at `0x1400079a7`
- `KERNEL32!GetLastError` at `0x140007a56`
- `KERNEL32!GetLastError` at `0x140007aa5`
- `KERNEL32!GetLastError` at `0x140007b12`
- `KERNEL32!GetLastError` at `0x1400079a7`
- `KERNEL32!GetLastError` at `0x140007a56`
- `KERNEL32!GetLastError` at `0x140007aa5`
- `KERNEL32!GetLastError` at `0x140007b12`
- `KERNEL32!GetCurrentProcessId` at `0x140007990`
- `KERNEL32!GetCurrentProcessId` at `0x140007990`
- `KERNEL32!ProcessIdToSessionId` at `0x14000799d`
- `KERNEL32!ProcessIdToSessionId` at `0x14000799d`
- `KERNEL32!GetModuleFileNameW` at `0x14000784e`
- `KERNEL32!GetModuleFileNameW` at `0x14000784e`
- `msvcrt!wcsrchr` at `0x1400078d6`
- `msvcrt!wcsrchr` at `0x1400078d6`

## string_xrefs

- `0x1400077c1`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x1400078e6`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140007b55`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140007b29`: `cchUsedWithoutNull != 0 && cchUsedWithoutNull != (sizeof(*RtlpNumberOf(szModulePathName)))`

## pseudocode

```c
__int64 __fastcall GenerateDumpFileName(unsigned __int16 *a1)
{
  LSTATUS v2; // eax
  __int64 v3; // rcx
  __int64 v4; // r8
  signed int StringValue; // ebx
  const unsigned __int16 *v6; // r13
  unsigned int v7; // r15d
  unsigned int v8; // r13d
  DWORD ModuleFileNameW; // eax
  WCHAR *v10; // rax
  WCHAR *v11; // rcx
  wchar_t *v12; // rax
  const unsigned __int16 *v13; // r9
  WCHAR *v14; // rbx
  DWORD CurrentProcessId; // eax
  signed int v16; // eax
  signed int v17; // eax
  signed int v18; // eax
  signed int LastError; // eax
  const unsigned __int16 *cchDate; // [rsp+28h] [rbp-D8h]
  int cchDatea[2]; // [rsp+28h] [rbp-D8h]
  LPCWSTR lpCalendar; // [rsp+30h] [rbp-D0h]
  LPCWSTR lpCalendara; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD pSessionId; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  void *Block; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR TimeStr[8]; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v30; // [rsp+68h] [rbp-98h]
  WCHAR DateStr[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v32; // [rsp+80h] [rbp-80h]
  WCHAR Filename[260]; // [rsp+90h] [rbp-70h] BYREF
  char v34; // [rsp+298h] [rbp+198h] BYREF

  hKey = 0;
  memset_0(Filename, 0, sizeof(Filename));
  Block = 0;
  v32 = 0;
  v30 = 0;
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
    v6 = L"lr == 0L";
    v7 = 1959;
LABEL_56:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      v7,
      L"GenerateDumpFileName",
      L"CBRAEx",
      v6,
      StringValue);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v7,
        L"GenerateDumpFileName",
        L"CBRAEx",
        v6,
        StringValue);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v7,
        L"GenerateDumpFileName",
        L"CBRAEx",
        v6,
        StringValue);
    goto LABEL_59;
  }
  StringValue = RegUtil::GetStringValue(v3, hKey, v4, &Block);
  if ( StringValue < 0 )
  {
    v8 = 1962;
    goto LABEL_7;
  }
  ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x104u);
  if ( !ModuleFileNameW || ModuleFileNameW == 260 )
  {
    LastError = GetLastError();
    StringValue = LastError;
    if ( LastError > 0 )
      StringValue = (unsigned __int16)LastError | 0x80070000;
    v6 = L"cchUsedWithoutNull != 0 && cchUsedWithoutNull != (sizeof(*RtlpNumberOf(szModulePathName)))";
    v7 = 1969;
    if ( StringValue >= 0 )
      StringValue = -2147467259;
    goto LABEL_56;
  }
  v10 = Filename;
  v11 = 0;
  while ( *v10 )
  {
    switch ( *v10 )
    {
      case ' ':
        goto LABEL_18;
      case '.':
        v11 = v10;
        break;
      case '\\':
LABEL_18:
        v11 = 0;
        break;
    }
    if ( ++v10 >= (WCHAR *)&v34 )
      break;
  }
  if ( v10 >= (WCHAR *)&v34 )
  {
    StringValue = -2147024809;
    v8 = 1972;
    goto LABEL_7;
  }
  if ( !v11 )
    v11 = v10;
  if ( *v11 )
    *v11 = 0;
  v12 = wcsrchr(Filename, 0x5Cu);
  if ( v12 )
  {
    v14 = v12 + 1;
    if ( !v12[1] )
    {
      LOGASSERT(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        0x7BAu,
        L"GenerateDumpFileName",
        v13,
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
    v14 = Filename;
  }
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
  {
    v16 = GetLastError();
    StringValue = v16;
    if ( v16 > 0 )
      StringValue = (unsigned __int16)v16 | 0x80070000;
    v8 = 1990;
    goto LABEL_37;
  }
  if ( !GetDateFormatEx(&LocaleName, 0, 0, aYyyyyMmDd_0, DateStr, 12, 0) )
  {
    v17 = GetLastError();
    StringValue = v17;
    if ( v17 > 0 )
      StringValue = (unsigned __int16)v17 | 0x80070000;
    v8 = 1994;
    goto LABEL_37;
  }
  if ( GetTimeFormatEx(&LocaleName, 0, 0, aHhMmSs_0, TimeStr, 9) )
  {
    cchDatea[0] = pSessionId;
    StringValue = StringCchPrintfW(
                    a1,
                    0x104u,
                    L"%s\\%s_%d_%s_%s.dmp",
                    Block,
                    v14,
                    *(_QWORD *)cchDatea,
                    DateStr,
                    TimeStr);
    if ( StringValue < 0 )
    {
      v8 = 2000;
LABEL_7:
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v8,
        L"GenerateDumpFileName",
        L"CHRA",
        L"hr",
        StringValue);
      if ( IsDebuggerPresent() )
      {
        LODWORD(v25) = StringValue;
        lpCalendara = L"hr";
        cchDate = L"CHRA";
        goto LABEL_9;
      }
      LODWORD(lpCalendar) = StringValue;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v8,
        L"GenerateDumpFileName",
        L"CHRA",
        L"hr",
        lpCalendar);
    }
  }
  else
  {
    v18 = GetLastError();
    StringValue = v18;
    if ( v18 > 0 )
      StringValue = (unsigned __int16)v18 | 0x80070000;
    v8 = 1997;
LABEL_37:
    if ( StringValue >= 0 )
      StringValue = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      v8,
      L"GenerateDumpFileName",
      L"CBRAEx",
      L"fSuccess",
      StringValue);
    if ( IsDebuggerPresent() )
    {
      LODWORD(v25) = StringValue;
      lpCalendara = L"fSuccess";
      cchDate = L"CBRAEx";
LABEL_9:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v8,
        L"GenerateDumpFileName",
        cchDate,
        lpCalendara,
        v25);
    }
    else
    {
      LODWORD(lpCalendar) = StringValue;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v8,
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
0x1400076e0  push    rbp
0x1400076e2  push    rbx
0x1400076e3  push    rsi
0x1400076e4  push    rdi
0x1400076e5  push    r12
0x1400076e7  push    r13
0x1400076e9  push    r14
0x1400076eb  push    r15
0x1400076ed  lea     rbp, [rsp-1B8h]
0x1400076f5  sub     rsp, 2B8h
0x1400076fc  mov     rax, cs:__security_cookie
0x140007703  xor     rax, rsp
0x140007706  mov     [rbp+1F0h+var_50], rax
0x14000770d  mov     r14, rcx
0x140007710  xor     r12d, r12d
0x140007713  lea     rcx, [rbp+1F0h+Filename]; void *
0x140007717  mov     [rsp+2F0h+hKey], r12
0x14000771c  xor     edx, edx; Val
0x14000771e  mov     r8d, 208h; Size
0x140007724  call    memset_0
0x140007729  xor     eax, eax
0x14000772b  mov     [rsp+2F0h+Block], r12
0x140007730  mov     [rbp+1F0h+var_270], rax
0x140007734  lea     r9d, [r12+1]; samDesired
0x140007739  mov     [rsp+2F0h+var_288], ax
0x14000773e  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows MultiPoint"...
0x140007745  lea     rax, [rsp+2F0h+hKey]
0x14000774a  mov     [rsp+2F0h+pSessionId], r12d
0x14000774f  xorps   xmm0, xmm0
0x140007752  mov     [rsp+2F0h+phkResult], rax; phkResult
0x140007757  xorps   xmm1, xmm1
0x14000775a  mov     [r14], r12w
0x14000775e  xor     r8d, r8d; ulOptions
0x140007761  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140007768  movups  xmmword ptr [rsp+2F0h+DateStr], xmm0
0x14000776d  movups  xmmword ptr [rsp+2F0h+TimeStr], xmm1
0x140007772  call    cs:__imp_RegOpenKeyExW
0x140007778  mov     ebx, eax
0x14000777a  test    eax, eax
0x14000777c  jz      short loc_14000779B
0x14000777e  jle     short loc_140007789
0x140007780  movzx   ebx, ax
0x140007783  or      ebx, 80070000h
0x140007789  lea     r13, aLr0l; "lr == 0L"
0x140007790  mov     r15d, 7A7h
0x140007796  jmp     loc_140007B3E
0x14000779b  mov     rdx, [rsp+2F0h+hKey]
0x1400077a0  lea     r9, [rsp+2F0h+Block]
0x1400077a5  call    ?GetStringValue@RegUtil@@YAJW4EValueRequired@1@PEAUHKEY__@@PEBGPEAPEAG@Z; RegUtil::GetStringValue(RegUtil::EValueRequired,HKEY__ *,ushort const *,ushort * *)
0x1400077aa  mov     ebx, eax
0x1400077ac  test    eax, eax
0x1400077ae  jns     loc_14000783F
0x1400077b4  mov     r13d, 7AAh
0x1400077ba  lea     rsi, aGeneratedumpfi; "GenerateDumpFileName"
0x1400077c1  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x1400077c8  lea     r15, aChra; "CHRA"
0x1400077cf  mov     [rsp+2F0h+cchDate], ebx; int
0x1400077d3  lea     r14, aHr; "hr"
0x1400077da  mov     r9, r15; unsigned __int16 *
0x1400077dd  mov     r8, rsi; unsigned __int16 *
0x1400077e0  mov     [rsp+2F0h+phkResult], r14; unsigned __int16 *
0x1400077e5  mov     edx, r13d; unsigned int
0x1400077e8  mov     rcx, rdi; unsigned __int16 *
0x1400077eb  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400077f0  call    cs:__imp_IsDebuggerPresent
0x1400077f6  test    eax, eax
0x1400077f8  jz      short loc_140007829
0x1400077fa  mov     dword ptr [rsp+2F0h+var_2B8], ebx
0x1400077fe  mov     [rsp+2F0h+lpCalendar], r14
0x140007803  mov     qword ptr [rsp+2F0h+cchDate], r15
0x140007808  mov     r9d, r13d
0x14000780b  mov     r8, rdi
0x14000780e  mov     [rsp+2F0h+phkResult], rsi
0x140007813  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000781a  mov     ecx, 2; unsigned __int8
0x14000781f  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140007824  jmp     loc_140007BB0
0x140007829  mov     dword ptr [rsp+2F0h+lpCalendar], ebx
0x14000782d  mov     r8d, r13d
0x140007830  mov     qword ptr [rsp+2F0h+cchDate], r14
0x140007835  mov     [rsp+2F0h+phkResult], r15
0x14000783a  jmp     loc_140007B9E
0x14000783f  mov     r15d, 104h
0x140007845  lea     rdx, [rbp+1F0h+Filename]; lpFilename
0x140007849  mov     r8d, r15d; nSize
0x14000784c  xor     ecx, ecx; hModule
0x14000784e  call    cs:__imp_GetModuleFileNameW
0x140007854  test    eax, eax
0x140007856  jz      loc_140007B12
0x14000785c  cmp     eax, r15d
0x14000785f  jz      loc_140007B12
0x140007865  lea     rax, [rbp+1F0h+Filename]
0x140007869  mov     rcx, r12
0x14000786c  mov     r8d, 5Ch ; '\'
0x140007872  cmp     [rax], r12w
0x140007876  jz      short loc_14000789D
0x140007878  cmp     word ptr [rax], 20h ; ' '
0x14000787c  jz      short loc_14000788A
0x14000787e  cmp     word ptr [rax], 2Eh ; '.'
0x140007882  jz      short loc_1400078B9
0x140007884  cmp     [rax], r8w
0x140007888  jnz     short loc_14000788D
0x14000788a  mov     rcx, r12
0x14000788d  add     rax, 2
0x140007891  lea     rdx, [rbp+1F0h+var_58]
0x140007898  cmp     rax, rdx
0x14000789b  jb      short loc_140007872
0x14000789d  lea     rdx, [rbp+1F0h+var_58]
0x1400078a4  cmp     rax, rdx
0x1400078a7  jb      short loc_1400078BE
0x1400078a9  mov     ebx, 80070057h
0x1400078ae  mov     r13d, 7B4h
0x1400078b4  jmp     loc_1400077BA
0x1400078b9  mov     rcx, rax
0x1400078bc  jmp     short loc_14000788D
0x1400078be  test    rcx, rcx
0x1400078c1  cmovz   rcx, rax
0x1400078c5  cmp     [rcx], r12w
0x1400078c9  jz      short loc_1400078CF
0x1400078cb  mov     [rcx], r12w
0x1400078cf  mov     edx, r8d; Ch
0x1400078d2  lea     rcx, [rbp+1F0h+Filename]; Str
0x1400078d6  call    cs:__imp_wcsrchr
0x1400078dc  lea     rsi, aGeneratedumpfi; "GenerateDumpFileName"
0x1400078e3  mov     rbx, rax
0x1400078e6  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x1400078ed  test    rax, rax
0x1400078f0  jz      loc_14000798C
0x1400078f6  add     rbx, 2
0x1400078fa  cmp     [rbx], r12w
0x1400078fe  jnz     loc_140007990
0x140007904  lea     rax, aPszmodulefilen; "*pszModuleFileName != L'\\0'"
0x14000790b  mov     r13d, 7BAh
0x140007911  mov     edx, r13d; unsigned int
0x140007914  mov     [rsp+2F0h+phkResult], rax; unsigned __int16 *
0x140007919  mov     r8, rsi; unsigned __int16 *
0x14000791c  mov     rcx, rdi; unsigned __int16 *
0x14000791f  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140007924  call    cs:__imp_IsDebuggerPresent
0x14000792a  test    eax, eax
0x14000792c  lea     rax, aPszmodulefilen; "*pszModuleFileName != L'\\0'"
0x140007933  jz      short loc_140007964
0x140007935  mov     [rsp+2F0h+lpCalendar], rax
0x14000793a  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140007941  lea     rax, aAssert; "ASSERT"
0x140007948  mov     r9d, r13d
0x14000794b  mov     qword ptr [rsp+2F0h+cchDate], rax
0x140007950  mov     r8, rdi
0x140007953  mov     ecx, 2; unsigned __int8
0x140007958  mov     [rsp+2F0h+phkResult], rsi
0x14000795d  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140007962  jmp     short loc_140007990
0x140007964  mov     qword ptr [rsp+2F0h+cchDate], rax
0x140007969  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140007970  lea     rax, aAssert; "ASSERT"
0x140007977  mov     r9, rsi
0x14000797a  mov     r8d, r13d
0x14000797d  mov     [rsp+2F0h+phkResult], rax
0x140007982  mov     rdx, rdi
0x140007985  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000798a  jmp     short loc_140007990
0x14000798c  lea     rbx, [rbp+1F0h+Filename]
0x140007990  call    cs:__imp_GetCurrentProcessId
0x140007996  mov     ecx, eax; dwProcessId
0x140007998  lea     rdx, [rsp+2F0h+pSessionId]; pSessionId
0x14000799d  call    cs:__imp_ProcessIdToSessionId
0x1400079a3  test    eax, eax
0x1400079a5  jnz     short loc_140007A22
0x1400079a7  call    cs:__imp_GetLastError
0x1400079ad  mov     ebx, eax
0x1400079af  test    eax, eax
0x1400079b1  jle     short loc_1400079BC
0x1400079b3  movzx   ebx, ax
0x1400079b6  or      ebx, 80070000h
0x1400079bc  mov     r13d, 7C6h
0x1400079c2  mov     eax, 80004005h
0x1400079c7  lea     r14, aCbraex; "CBRAEx"
0x1400079ce  test    ebx, ebx
0x1400079d0  lea     r15, aFsuccess; "fSuccess"
0x1400079d7  mov     r9, r14; unsigned __int16 *
0x1400079da  mov     r8, rsi; unsigned __int16 *
0x1400079dd  cmovns  ebx, eax
0x1400079e0  mov     edx, r13d; unsigned int
0x1400079e3  mov     [rsp+2F0h+cchDate], ebx; int
0x1400079e7  mov     rcx, rdi; unsigned __int16 *
0x1400079ea  mov     [rsp+2F0h+phkResult], r15; unsigned __int16 *
0x1400079ef  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400079f4  call    cs:__imp_IsDebuggerPresent
0x1400079fa  test    eax, eax
0x1400079fc  jz      short loc_140007A11
0x1400079fe  mov     dword ptr [rsp+2F0h+var_2B8], ebx
0x140007a02  mov     [rsp+2F0h+lpCalendar], r15
0x140007a07  mov     qword ptr [rsp+2F0h+cchDate], r14
0x140007a0c  jmp     loc_140007808
0x140007a11  mov     dword ptr [rsp+2F0h+lpCalendar], ebx
0x140007a15  mov     r8d, r13d
0x140007a18  mov     qword ptr [rsp+2F0h+cchDate], r15
0x140007a1d  jmp     loc_140007B99
0x140007a22  mov     [rsp+2F0h+lpCalendar], r12; lpCalendar
0x140007a27  lea     rax, [rsp+2F0h+DateStr]
0x140007a2c  mov     [rsp+2F0h+cchDate], 0Ch; cchDate
0x140007a34  lea     r9, aYyyyyMmDd_0; "yyyyy-MM-dd"
0x140007a3b  xor     r8d, r8d; lpDate
0x140007a3e  mov     [rsp+2F0h+phkResult], rax; lpDateStr
0x140007a43  xor     edx, edx; dwFlags
0x140007a45  lea     rcx, LocaleName; lpLocaleName
0x140007a4c  call    cs:__imp_GetDateFormatEx
0x140007a52  test    eax, eax
0x140007a54  jnz     short loc_140007A76
0x140007a56  call    cs:__imp_GetLastError
0x140007a5c  mov     ebx, eax
0x140007a5e  test    eax, eax
0x140007a60  jle     short loc_140007A6B
0x140007a62  movzx   ebx, ax
0x140007a65  or      ebx, 80070000h
0x140007a6b  mov     r13d, 7CAh
0x140007a71  jmp     loc_1400079C2
0x140007a76  lea     rax, [rsp+2F0h+TimeStr]
0x140007a7b  mov     [rsp+2F0h+cchDate], 9; cchTime
0x140007a83  lea     r9, aHhMmSs_0; "HH-mm-ss"
0x140007a8a  mov     [rsp+2F0h+phkResult], rax; lpTimeStr
0x140007a8f  xor     r8d, r8d; lpTime
0x140007a92  lea     rcx, LocaleName; lpLocaleName
0x140007a99  xor     edx, edx; dwFlags
0x140007a9b  call    cs:__imp_GetTimeFormatEx
0x140007aa1  test    eax, eax
0x140007aa3  jnz     short loc_140007AC5
0x140007aa5  call    cs:__imp_GetLastError
0x140007aab  mov     ebx, eax
0x140007aad  test    eax, eax
0x140007aaf  jle     short loc_140007ABA
0x140007ab1  movzx   ebx, ax
0x140007ab4  or      ebx, 80070000h
0x140007aba  mov     r13d, 7CDh
0x140007ac0  jmp     loc_1400079C2
0x140007ac5  mov     r9, [rsp+2F0h+Block]
0x140007aca  lea     rax, [rsp+2F0h+TimeStr]
0x140007acf  mov     [rsp+2F0h+var_2B8], rax
0x140007ad4  lea     r8, aSSDSSDmp; "%s\\%s_%d_%s_%s.dmp"
0x140007adb  lea     rax, [rsp+2F0h+DateStr]
0x140007ae0  mov     rdx, r15; unsigned __int64
0x140007ae3  mov     [rsp+2F0h+lpCalendar], rax
0x140007ae8  mov     rcx, r14; unsigned __int16 *
0x140007aeb  mov     eax, [rsp+2F0h+pSessionId]
0x140007aef  mov     [rsp+2F0h+cchDate], eax
0x140007af3  mov     [rsp+2F0h+phkResult], rbx
0x140007af8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140007afd  mov     ebx, eax
0x140007aff  test    eax, eax
0x140007b01  jns     loc_140007BB0
0x140007b07  mov     r13d, 7D0h
0x140007b0d  jmp     loc_1400077C8
0x140007b12  call    cs:__imp_GetLastError
0x140007b18  mov     ebx, eax
0x140007b1a  test    eax, eax
0x140007b1c  jle     short loc_140007B27
0x140007b1e  movzx   ebx, ax
0x140007b21  or      ebx, 80070000h
0x140007b27  test    ebx, ebx
0x140007b29  lea     r13, aCchusedwithout; "cchUsedWithoutNull != 0 && cchUsedWitho"...
0x140007b30  mov     eax, 80004005h
0x140007b35  mov     r15d, 7B1h
0x140007b3b  cmovns  ebx, eax
0x140007b3e  lea     r14, aCbraex; "CBRAEx"
0x140007b45  mov     [rsp+2F0h+cchDate], ebx; int
0x140007b49  lea     rsi, aGeneratedumpfi; "GenerateDumpFileName"
0x140007b50  mov     [rsp+2F0h+phkResult], r13; unsigned __int16 *
0x140007b55  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140007b5c  mov     r9, r14; unsigned __int16 *
0x140007b5f  mov     r8, rsi; unsigned __int16 *
0x140007b62  mov     rcx, rdi; unsigned __int16 *
0x140007b65  mov     edx, r15d; unsigned int
0x140007b68  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140007b6d  call    cs:__imp_IsDebuggerPresent
0x140007b73  test    eax, eax
0x140007b75  jz      short loc_140007B8D
0x140007b77  mov     dword ptr [rsp+2F0h+var_2B8], ebx
0x140007b7b  mov     r9d, r15d
0x140007b7e  mov     [rsp+2F0h+lpCalendar], r13
0x140007b83  mov     qword ptr [rsp+2F0h+cchDate], r14
0x140007b88  jmp     loc_14000780B
0x140007b8d  mov     dword ptr [rsp+2F0h+lpCalendar], ebx
0x140007b91  mov     r8d, r15d
0x140007b94  mov     qword ptr [rsp+2F0h+cchDate], r13
0x140007b99  mov     [rsp+2F0h+phkResult], r14
0x140007b9e  mov     r9, rsi
0x140007ba1  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140007ba8  mov     rdx, rdi
0x140007bab  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140007bb0  mov     rcx, [rsp+2F0h+hKey]; hKey
0x140007bb5  test    rcx, rcx
0x140007bb8  jz      short loc_140007BC0
0x140007bba  call    cs:__imp_RegCloseKey
0x140007bc0  mov     rcx, [rsp+2F0h+Block]; Block
0x140007bc5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140007bca  mov     eax, ebx
0x140007bcc  mov     rcx, [rbp+1F0h+var_50]
0x140007bd3  xor     rcx, rsp; StackCookie
0x140007bd6  call    __security_check_cookie
0x140007bdb  add     rsp, 2B8h
  ... truncated ...
```
