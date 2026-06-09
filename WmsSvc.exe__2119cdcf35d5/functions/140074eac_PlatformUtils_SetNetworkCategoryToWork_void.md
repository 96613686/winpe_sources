# PlatformUtils::SetNetworkCategoryToWork(void)

- ea: `0x140074eac`
- end: `0x1400757a6`
- name: `?SetNetworkCategoryToWork@PlatformUtils@@YAJXZ`
- size: `2298`
- prototype: `__int64 __fastcall(PlatformUtils *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400757ac`

## callees

- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140074b88`
- `0x140074eac`
- `0x14007cb9e`
- `0x14007cbd0`
- `0x14007e010`

## import_xrefs

- `ADVAPI32!RegSetKeyValueW` at `0x140075337`
- `ADVAPI32!RegSetKeyValueW` at `0x140075337`
- `KERNEL32!GetLastError` at `0x140074f74`
- `KERNEL32!GetLastError` at `0x140074f74`
- `KERNEL32!IsDebuggerPresent` at `0x140074fba`
- `KERNEL32!IsDebuggerPresent` at `0x14007509c`
- `KERNEL32!IsDebuggerPresent` at `0x140075151`
- `KERNEL32!IsDebuggerPresent` at `0x1400753d2`
- `KERNEL32!IsDebuggerPresent` at `0x14007544f`
- `KERNEL32!IsDebuggerPresent` at `0x1400754a2`
- `KERNEL32!IsDebuggerPresent` at `0x14007551f`
- `KERNEL32!IsDebuggerPresent` at `0x140075574`
- `KERNEL32!IsDebuggerPresent` at `0x1400755fb`
- `KERNEL32!IsDebuggerPresent` at `0x14007564c`
- `KERNEL32!IsDebuggerPresent` at `0x14007569d`
- `KERNEL32!IsDebuggerPresent` at `0x1400756ee`
- `KERNEL32!IsDebuggerPresent` at `0x140074fba`
- `KERNEL32!IsDebuggerPresent` at `0x14007509c`
- `KERNEL32!IsDebuggerPresent` at `0x140075151`
- `KERNEL32!IsDebuggerPresent` at `0x1400753d2`
- `KERNEL32!IsDebuggerPresent` at `0x14007544f`
- `KERNEL32!IsDebuggerPresent` at `0x1400754a2`
- `KERNEL32!IsDebuggerPresent` at `0x14007551f`
- `KERNEL32!IsDebuggerPresent` at `0x140075574`
- `KERNEL32!IsDebuggerPresent` at `0x1400755fb`
- `KERNEL32!IsDebuggerPresent` at `0x14007564c`
- `KERNEL32!IsDebuggerPresent` at `0x14007569d`
- `KERNEL32!IsDebuggerPresent` at `0x1400756ee`
- `KERNEL32!GetVersionExW` at `0x140074f46`
- `KERNEL32!GetVersionExW` at `0x140074f46`
- `ole32!StringFromGUID2` at `0x14007523c`
- `ole32!StringFromGUID2` at `0x14007523c`
- `ole32!CoCreateInstance` at `0x14007505b`
- `ole32!CoCreateInstance` at `0x14007505b`
- `OLEAUT32!__imp_SysFreeString` at `0x140075379`
- `OLEAUT32!__imp_SysFreeString` at `0x140075389`
- `OLEAUT32!__imp_SysFreeString` at `0x140075770`
- `OLEAUT32!__imp_SysFreeString` at `0x14007577b`
- `OLEAUT32!__imp_SysFreeString` at `0x140075379`
- `OLEAUT32!__imp_SysFreeString` at `0x140075389`
- `OLEAUT32!__imp_SysFreeString` at `0x140075770`
- `OLEAUT32!__imp_SysFreeString` at `0x14007577b`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140075308`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140075308`

## string_xrefs

- `0x140074f53`: `termsrv\wms\src\common\srcutils\platformutils.cpp`
- `0x14007570e`: `PlatformUtils::SetNetworkCategoryToWork - completed\n`

## pseudocode

```c
__int64 __fastcall PlatformUtils::SetNetworkCategoryToWork(PlatformUtils *this)
{
  signed int LastError; // eax
  int v2; // ebx
  BOOL v3; // edi
  HRESULT v4; // eax
  __int64 v5; // r9
  __int64 v6; // r8
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  const wchar_t *v13; // rax
  int v14; // eax
  UINT v15; // eax
  LSTATUS v16; // eax
  __int64 v17; // r9
  const unsigned __int16 *v18; // rax
  const unsigned __int16 *v20; // [rsp+30h] [rbp-D0h]
  int v21; // [rsp+38h] [rbp-C8h]
  __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v23; // [rsp+48h] [rbp-B8h] BYREF
  BSTR bstr; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+58h] [rbp-A8h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v27; // [rsp+68h] [rbp-98h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-90h] BYREF
  GUID rguid; // [rsp+78h] [rbp-88h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+90h] [rbp-70h] BYREF
  OLECHAR sz[40]; // [rsp+1B0h] [rbp+B0h] BYREF

  v22 = 0;
  ppv = 0;
  v27 = 0;
  v25 = 0;
  v23 = 0;
  bstr = 0;
  bstrString = 0;
  rguid = GUID_NULL;
  memset_0(sz, 0, sizeof(sz));
  DEBUGMSG(L"PlatformUtils::SetNetworkCategoryToWork - started\n");
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( GetVersionExW(&VersionInformation) )
  {
    v3 = VersionInformation.dwMajorVersion > 6
      || VersionInformation.dwMajorVersion == 6 && VersionInformation.dwMinorVersion > 1;
    v4 = CoCreateInstance(&CLSID_NetworkListManager, 0, 0x17u, &GUID_dcb00000_570f_4a9b_8d69_199fdba5723b, &ppv);
    v2 = v4;
    if ( v4 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, 1, &v27);
      v2 = v7;
      if ( v7 >= 0 )
      {
        while ( 1 )
        {
          if ( (*(unsigned int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v27 + 64LL))(v27, 1, &v22) )
          {
            DEBUGMSG(L"PlatformUtils::SetNetworkCategoryToWork - completed\n");
            goto LABEL_73;
          }
          v8 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v22 + 56LL))(v22, &bstr);
          v2 = v8;
          if ( v8 < 0 )
            break;
          DEBUGMSG(L"PlatformUtils::SetNetworkCategoryToWork - checking network '%s'\n", bstr);
          v9 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v22 + 72LL))(v22, &bstrString);
          v2 = v9;
          if ( v9 < 0 )
          {
            LOGASSERTHR(
              L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
              0x2B5u,
              L"PlatformUtils::SetNetworkCategoryToWork",
              L"CHRA",
              L"hr",
              v9);
            if ( IsDebuggerPresent() )
            {
              v5 = 693;
              goto LABEL_17;
            }
            v6 = 693;
            goto LABEL_19;
          }
          v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 136LL))(v22, &v25);
          v2 = v10;
          if ( v10 < 0 )
          {
            LOGASSERTHR(
              L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
              0x2B8u,
              L"PlatformUtils::SetNetworkCategoryToWork",
              L"CHRA",
              L"hr",
              v10);
            if ( IsDebuggerPresent() )
            {
              v5 = 696;
              goto LABEL_17;
            }
            v6 = 696;
            goto LABEL_19;
          }
          v11 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v22 + 88LL))(v22, &rguid);
          v2 = v11;
          if ( v11 < 0 )
          {
            LOGASSERTHR(
              L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
              0x2BBu,
              L"PlatformUtils::SetNetworkCategoryToWork",
              L"CHRA",
              L"hr",
              v11);
            if ( IsDebuggerPresent() )
            {
              v5 = 699;
              goto LABEL_17;
            }
            v6 = 699;
            goto LABEL_19;
          }
          if ( StringFromGUID2(&rguid, sz, 40) <= 0 )
          {
            v2 = -2147467259;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
              0x2BEu,
              L"PlatformUtils::SetNetworkCategoryToWork",
              L"CBRA",
              L"len > 0",
              -2147467259);
            if ( IsDebuggerPresent() )
            {
              v21 = -2147467259;
              v17 = 702;
              v20 = L"len > 0";
              v18 = L"CBRA";
LABEL_58:
              DEBUGMSGLEVEL(
                2u,
                L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
                v17,
                L"PlatformUtils::SetNetworkCategoryToWork",
                v18,
                v20,
                v21);
              goto LABEL_73;
            }
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
              702,
              L"PlatformUtils::SetNetworkCategoryToWork",
              L"CBRA",
              L"len > 0",
              -2147467259);
            goto LABEL_73;
          }
          v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v22 + 144LL))(v22, &v23);
          v2 = v12;
          if ( v12 < 0 )
          {
            LOGASSERTHR(
              L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
              0x2C2u,
              L"PlatformUtils::SetNetworkCategoryToWork",
              L"CHRA",
              L"hr",
              v12);
            if ( IsDebuggerPresent() )
            {
              v5 = 706;
              goto LABEL_17;
            }
            v6 = 706;
            goto LABEL_19;
          }
          if ( v23 > 2 )
          {
            v2 = -2147418113;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
              0x2C5u,
              L"PlatformUtils::SetNetworkCategoryToWork",
              L"CBRAEx",
              L"(eNetworkCategory >= NLM_NETWORK_CATEGORY_PUBLIC) && (eNetworkCategory <= NLM_NETWORK_CATEGORY_DOMAIN_AUTHENTICATED)",
              -2147418113);
            if ( !IsDebuggerPresent() )
            {
              DEBUGMSGBOX(
                L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
                709,
                L"PlatformUtils::SetNetworkCategoryToWork",
                L"CBRAEx",
                L"(eNetworkCategory >= NLM_NETWORK_CATEGORY_PUBLIC) && (eNetworkCategory <= NLM_NETWORK_CATEGORY_DOMAIN_AUTHENTICATED)",
                -2147418113);
              goto LABEL_73;
            }
            v21 = -2147418113;
            v17 = 709;
            v20 = L"(eNetworkCategory >= NLM_NETWORK_CATEGORY_PUBLIC) && (eNetworkCategory <= NLM_NETWORK_CATEGORY_DOMAIN_AUTHENTICATED)";
            v18 = L"CBRAEx";
            goto LABEL_58;
          }
          v13 = L"not connected";
          if ( v25 )
            v13 = L"connected";
          DEBUGMSG(
            L"PlatformUtils::SetNetworkCategoryToWork - %s network %s (%s) (%s)\n",
            off_14009C6A0[v23],
            bstr,
            bstrString,
            v13);
          if ( !v23 )
          {
            DEBUGMSG(L"PlatformUtils::SetNetworkCategoryToWork - setting network category to 'Private'\n");
            v14 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 152LL))(v22, 1);
            v2 = v14;
            if ( v14 < 0 )
            {
              LOGASSERTHR(
                L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
                0x2CDu,
                L"PlatformUtils::SetNetworkCategoryToWork",
                L"CHRA",
                L"hr",
                v14);
              if ( IsDebuggerPresent() )
              {
                v5 = 717;
                goto LABEL_17;
              }
              v6 = 717;
              goto LABEL_19;
            }
            if ( !v3 )
            {
              DEBUGMSG(L"PlatformUtils::SetNetworkCategoryToWork - setting network type value to 'Work'\n");
              v15 = SysStringByteLen(bstr);
              v16 = RegSetKeyValueW(
                      HKEY_LOCAL_MACHINE,
                      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\HomeGroup\\NetworkLocations\\Work",
                      sz,
                      1u,
                      bstr,
                      v15 + 2);
              v2 = v16;
              if ( v16 )
              {
                if ( v16 > 0 )
                  v2 = (unsigned __int16)v16 | 0x80070000;
                LOGASSERTHR(
                  L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
                  0x2D6u,
                  L"PlatformUtils::SetNetworkCategoryToWork",
                  L"CBRAEx",
                  L"lr == 0L",
                  v2);
                if ( !IsDebuggerPresent() )
                {
                  DEBUGMSGBOX(
                    L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                    L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
                    726,
                    L"PlatformUtils::SetNetworkCategoryToWork",
                    L"CBRAEx",
                    L"lr == 0L",
                    v2);
                  goto LABEL_73;
                }
                v21 = v2;
                v17 = 726;
                v20 = L"lr == 0L";
                v18 = L"CBRAEx";
                goto LABEL_58;
              }
              v2 = PlatformUtils::SetNetworkCategoryHelper((__int64)sz);
              if ( v2 < 0 )
                goto LABEL_73;
            }
          }
          if ( v22 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
            v22 = 0;
          }
          SysFreeString(bstr);
          bstr = 0;
          SysFreeString(bstrString);
          bstrString = 0;
        }
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
          0x2B1u,
          L"PlatformUtils::SetNetworkCategoryToWork",
          L"CHRA",
          L"hr",
          v8);
        if ( IsDebuggerPresent() )
        {
          v5 = 689;
          goto LABEL_17;
        }
        v6 = 689;
      }
      else
      {
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
          0x2AAu,
          L"PlatformUtils::SetNetworkCategoryToWork",
          L"CHRA",
          L"hr",
          v7);
        if ( IsDebuggerPresent() )
        {
          v5 = 682;
          goto LABEL_17;
        }
        v6 = 682;
      }
    }
    else
    {
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
        0x2A5u,
        L"PlatformUtils::SetNetworkCategoryToWork",
        L"CHRA",
        L"hr",
        v4);
      if ( IsDebuggerPresent() )
      {
        v5 = 677;
LABEL_17:
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
          v5,
          L"PlatformUtils::SetNetworkCategoryToWork",
          L"CHRA",
          L"hr",
          v2);
        goto LABEL_73;
      }
      v6 = 677;
    }
LABEL_19:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
      v6,
      L"PlatformUtils::SetNetworkCategoryToWork",
      L"CHRA",
      L"hr",
      v2);
    goto LABEL_73;
  }
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( v2 >= 0 )
    v2 = -2147467259;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
    0x242u,
    L"PlatformUtils::IsOsWindows8OrHigher",
    L"CBRAEx",
    L"fSuccess",
    v2);
  if ( IsDebuggerPresent() )
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
      578,
      L"PlatformUtils::IsOsWindows8OrHigher",
      L"CBRAEx",
      L"fSuccess",
      v2);
  else
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\platformutils.cpp",
      578,
      L"PlatformUtils::IsOsWindows8OrHigher",
      L"CBRAEx",
      L"fSuccess",
      v2);
LABEL_73:
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  SysFreeString(bstr);
  SysFreeString(bstrString);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140074eac  push    rbp
0x140074eae  push    rbx
0x140074eaf  push    rsi
0x140074eb0  push    rdi
0x140074eb1  push    r12
0x140074eb3  push    r13
0x140074eb5  push    r14
0x140074eb7  push    r15
0x140074eb9  lea     rbp, [rsp-118h]
0x140074ec1  sub     rsp, 218h
0x140074ec8  mov     rax, cs:__security_cookie
0x140074ecf  xor     rax, rsp
0x140074ed2  mov     [rbp+150h+var_50], rax
0x140074ed9  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140074ee0  xor     r15d, r15d
0x140074ee3  lea     rcx, [rbp+150h+sz]; void *
0x140074eea  xor     edx, edx; Val
0x140074eec  mov     [rsp+250h+var_210], r15
0x140074ef1  mov     [rsp+250h+var_1E0], r15
0x140074ef6  mov     [rsp+250h+var_1E8], r15
0x140074efb  lea     r8d, [r15+50h]; Size
0x140074eff  mov     [rsp+250h+var_1F8], r15d
0x140074f04  mov     [rsp+250h+var_208], r15d
0x140074f09  mov     [rsp+250h+bstr], r15
0x140074f0e  mov     [rsp+250h+bstrString], r15
0x140074f13  movdqu  xmmword ptr [rsp+250h+rguid.Data1], xmm0
0x140074f19  call    memset_0
0x140074f1e  lea     rcx, aPlatformutilsS_5; "PlatformUtils::SetNetworkCategoryToWork"...
0x140074f25  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140074f2a  xor     edx, edx; Val
0x140074f2c  lea     rcx, [rbp+150h+VersionInformation.dwMajorVersion]; void *
0x140074f30  mov     r8d, 118h; Size
0x140074f36  call    memset_0
0x140074f3b  lea     rcx, [rbp+150h+VersionInformation]; lpVersionInformation
0x140074f3f  mov     [rbp+150h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x140074f46  call    cs:__imp_GetVersionExW
0x140074f4c  lea     rdi, aCbraex; "CBRAEx"
0x140074f53  lea     r12, aTermsrvWmsSrcC_1; "termsrv\\wms\\src\\common\\srcutils\\pl"...
0x140074f5a  lea     r14, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140074f61  lea     esi, [r15+2]
0x140074f65  lea     r13, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140074f6c  test    eax, eax
0x140074f6e  jnz     loc_140075025
0x140074f74  call    cs:__imp_GetLastError
0x140074f7a  mov     ebx, eax
0x140074f7c  test    eax, eax
0x140074f7e  jle     short loc_140074F89
0x140074f80  movzx   ebx, ax
0x140074f83  or      ebx, 80070000h
0x140074f89  mov     eax, 80004005h
0x140074f8e  lea     r8, aPlatformutilsI; "PlatformUtils::IsOsWindows8OrHigher"
0x140074f95  test    ebx, ebx
0x140074f97  mov     r9, rdi; unsigned __int16 *
0x140074f9a  mov     edx, 242h; unsigned int
0x140074f9f  mov     rcx, r12; unsigned __int16 *
0x140074fa2  cmovns  ebx, eax
0x140074fa5  lea     rax, aFsuccess; "fSuccess"
0x140074fac  mov     [rsp+250h+cbData], ebx; int
0x140074fb0  mov     [rsp+250h+ppv], rax; unsigned __int16 *
0x140074fb5  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140074fba  call    cs:__imp_IsDebuggerPresent
0x140074fc0  test    eax, eax
0x140074fc2  lea     r9, aPlatformutilsI; "PlatformUtils::IsOsWindows8OrHigher"
0x140074fc9  lea     rax, aFsuccess; "fSuccess"
0x140074fd0  jz      short loc_140074FFA
0x140074fd2  mov     [rsp+250h+var_218], ebx
0x140074fd6  mov     r8, r12
0x140074fd9  mov     [rsp+250h+var_220], rax
0x140074fde  mov     rdx, r14; unsigned __int16 *
0x140074fe1  mov     qword ptr [rsp+250h+cbData], rdi
0x140074fe6  mov     ecx, esi; unsigned __int8
0x140074fe8  mov     [rsp+250h+ppv], r9
0x140074fed  mov     r9d, 242h
0x140074ff3  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140074ff8  jmp     short loc_140075019
0x140074ffa  mov     dword ptr [rsp+250h+var_220], ebx
0x140074ffe  mov     r8d, 242h
0x140075004  mov     qword ptr [rsp+250h+cbData], rax
0x140075009  mov     rdx, r12
0x14007500c  mov     rcx, r13; unsigned __int16 *
0x14007500f  mov     [rsp+250h+ppv], rdi
0x140075014  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140075019  mov     edi, r15d
0x14007501c  test    ebx, ebx
0x14007501e  jns     short loc_14007503D
0x140075020  jmp     loc_14007571A
0x140075025  cmp     [rbp+150h+VersionInformation.dwMajorVersion], 6
0x140075029  ja      short loc_140075038
0x14007502b  jnz     short loc_140075033
0x14007502d  cmp     [rbp+150h+VersionInformation.dwMinorVersion], 1
0x140075031  ja      short loc_140075038
0x140075033  mov     edi, r15d
0x140075036  jmp     short loc_14007503D
0x140075038  mov     edi, 1
0x14007503d  xor     edx, edx; pUnkOuter
0x14007503f  lea     rax, [rsp+250h+var_1E0]
0x140075044  lea     r9, _GUID_dcb00000_570f_4a9b_8d69_199fdba5723b; riid
0x14007504b  mov     [rsp+250h+ppv], rax; ppv
0x140075050  lea     rcx, CLSID_NetworkListManager; rclsid
0x140075057  lea     r8d, [rdx+17h]; dwClsContext
0x14007505b  call    cs:__imp_CoCreateInstance
0x140075061  mov     ebx, eax
0x140075063  test    eax, eax
0x140075065  jns     loc_1400750FF
0x14007506b  mov     [rsp+250h+cbData], eax; int
0x14007506f  lea     r14, aChra; "CHRA"
0x140075076  lea     rdi, aPlatformutilsS_0; "PlatformUtils::SetNetworkCategoryToWork"
0x14007507d  mov     r9, r14; unsigned __int16 *
0x140075080  lea     rsi, aHr; "hr"
0x140075087  mov     r8, rdi; unsigned __int16 *
0x14007508a  mov     edx, 2A5h; unsigned int
0x14007508f  mov     [rsp+250h+ppv], rsi; unsigned __int16 *
0x140075094  mov     rcx, r12; unsigned __int16 *
0x140075097  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007509c  call    cs:__imp_IsDebuggerPresent
0x1400750a2  test    eax, eax
0x1400750a4  jz      short loc_1400750D8
0x1400750a6  mov     r9d, 2A5h
0x1400750ac  mov     [rsp+250h+var_218], ebx
0x1400750b0  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400750b7  mov     [rsp+250h+var_220], rsi
0x1400750bc  mov     ecx, 2; unsigned __int8
0x1400750c1  mov     qword ptr [rsp+250h+cbData], r14
0x1400750c6  mov     r8, r12
0x1400750c9  mov     [rsp+250h+ppv], rdi
0x1400750ce  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400750d3  jmp     loc_14007571A
0x1400750d8  mov     r8d, 2A5h
0x1400750de  mov     dword ptr [rsp+250h+var_220], ebx
0x1400750e2  mov     qword ptr [rsp+250h+cbData], rsi
0x1400750e7  mov     [rsp+250h+ppv], r14
0x1400750ec  mov     r9, rdi
0x1400750ef  mov     rdx, r12
0x1400750f2  mov     rcx, r13; unsigned __int16 *
0x1400750f5  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400750fa  jmp     loc_14007571A
0x1400750ff  mov     rcx, [rsp+250h+var_1E0]
0x140075104  lea     r8, [rsp+250h+var_1E8]
0x140075109  mov     edx, 1
0x14007510e  mov     rax, [rcx]
0x140075111  mov     rax, [rax+38h]
0x140075115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007511a  mov     ebx, eax
0x14007511c  test    eax, eax
0x14007511e  jns     short loc_140075171
0x140075120  mov     [rsp+250h+cbData], eax; int
0x140075124  lea     r14, aChra; "CHRA"
0x14007512b  lea     rdi, aPlatformutilsS_0; "PlatformUtils::SetNetworkCategoryToWork"
0x140075132  mov     r9, r14; unsigned __int16 *
0x140075135  lea     rsi, aHr; "hr"
0x14007513c  mov     r8, rdi; unsigned __int16 *
0x14007513f  mov     edx, 2AAh; unsigned int
0x140075144  mov     [rsp+250h+ppv], rsi; unsigned __int16 *
0x140075149  mov     rcx, r12; unsigned __int16 *
0x14007514c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140075151  call    cs:__imp_IsDebuggerPresent
0x140075157  test    eax, eax
0x140075159  jz      short loc_140075166
0x14007515b  mov     r9d, 2AAh
0x140075161  jmp     loc_1400750AC
0x140075166  mov     r8d, 2AAh
0x14007516c  jmp     loc_1400750DE
0x140075171  mov     rcx, [rsp+250h+var_1E8]
0x140075176  lea     r8, [rsp+250h+var_210]
0x14007517b  xor     r9d, r9d
0x14007517e  mov     rax, [rcx]
0x140075181  lea     edx, [r9+1]
0x140075185  mov     rax, [rax+40h]
0x140075189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007518e  test    eax, eax
0x140075190  jnz     loc_14007570E
0x140075196  mov     rcx, [rsp+250h+var_210]
0x14007519b  lea     rdx, [rsp+250h+bstr]
0x1400751a0  mov     rax, [rcx]
0x1400751a3  mov     rax, [rax+38h]
0x1400751a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400751ac  mov     ebx, eax
0x1400751ae  test    eax, eax
0x1400751b0  js      loc_1400756BD
0x1400751b6  mov     rdx, [rsp+250h+bstr]
0x1400751bb  lea     rcx, aPlatformutilsS_1; "PlatformUtils::SetNetworkCategoryToWork"...
0x1400751c2  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400751c7  mov     rcx, [rsp+250h+var_210]
0x1400751cc  lea     rdx, [rsp+250h+bstrString]
0x1400751d1  mov     rax, [rcx]
0x1400751d4  mov     rax, [rax+48h]
0x1400751d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400751dd  mov     ebx, eax
0x1400751df  test    eax, eax
0x1400751e1  js      loc_14007566C
0x1400751e7  mov     rcx, [rsp+250h+var_210]
0x1400751ec  lea     rdx, [rsp+250h+var_1F8]
0x1400751f1  mov     rax, [rcx]
0x1400751f4  mov     rax, [rax+88h]
0x1400751fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140075200  mov     ebx, eax
0x140075202  test    eax, eax
0x140075204  js      loc_14007561B
0x14007520a  mov     rcx, [rsp+250h+var_210]
0x14007520f  lea     rdx, [rsp+250h+rguid]
0x140075214  mov     rax, [rcx]
0x140075217  mov     rax, [rax+58h]
0x14007521b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140075220  mov     ebx, eax
0x140075222  test    eax, eax
0x140075224  js      loc_1400755CA
0x14007522a  mov     r8d, 28h ; '('; cchMax
0x140075230  lea     rdx, [rbp+150h+sz]; lpsz
0x140075237  lea     rcx, [rsp+250h+rguid]; rguid
0x14007523c  call    cs:__imp_StringFromGUID2
0x140075242  test    eax, eax
0x140075244  jle     loc_14007553F
0x14007524a  mov     rcx, [rsp+250h+var_210]
0x14007524f  lea     rdx, [rsp+250h+var_208]
0x140075254  mov     rax, [rcx]
0x140075257  mov     rax, [rax+90h]
0x14007525e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140075263  mov     ebx, eax
0x140075265  test    eax, eax
0x140075267  js      loc_1400754EE
0x14007526d  cmp     [rsp+250h+var_208], esi
0x140075271  ja      loc_14007546F
0x140075277  cmp     [rsp+250h+var_1F8], r15d
0x14007527c  lea     rcx, aConnected; "connected"
0x140075283  movsxd  rdx, [rsp+250h+var_208]
0x140075288  lea     rax, aNotConnected; "not connected"
0x14007528f  mov     r9, [rsp+250h+bstrString]
0x140075294  cmovnz  rax, rcx
0x140075298  mov     r8, [rsp+250h+bstr]
0x14007529d  lea     rcx, off_14009C6A0; "Public"
0x1400752a4  mov     [rsp+250h+ppv], rax
0x1400752a9  mov     rdx, [rcx+rdx*8]
0x1400752ad  lea     rcx, aPlatformutilsS_4; "PlatformUtils::SetNetworkCategoryToWork"...
0x1400752b4  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400752b9  cmp     [rsp+250h+var_208], r15d
0x1400752be  jnz     loc_140075359
0x1400752c4  lea     rcx, aPlatformutilsS_7; "PlatformUtils::SetNetworkCategoryToWork"...
0x1400752cb  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400752d0  mov     rcx, [rsp+250h+var_210]
0x1400752d5  mov     edx, 1
0x1400752da  mov     rax, [rcx]
0x1400752dd  mov     rax, [rax+98h]
0x1400752e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400752e9  mov     ebx, eax
0x1400752eb  test    eax, eax
0x1400752ed  js      loc_14007541E
0x1400752f3  test    edi, edi
0x1400752f5  jnz     short loc_140075359
0x1400752f7  lea     rcx, aPlatformutilsS_8; "PlatformUtils::SetNetworkCategoryToWork"...
0x1400752fe  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140075303  mov     rcx, [rsp+250h+bstr]; bstr
0x140075308  call    cs:__imp_SysStringByteLen
0x14007530e  lea     r9d, [rdi+1]; dwType
0x140075312  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140075319  add     eax, esi
0x14007531b  lea     r8, [rbp+150h+sz]; lpValueName
0x140075322  mov     [rsp+250h+cbData], eax; cbData
0x140075326  lea     rdx, aSoftwareMicros_40; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14007532d  mov     rax, [rsp+250h+bstr]
0x140075332  mov     [rsp+250h+ppv], rax; lpData
0x140075337  call    cs:__imp_RegSetKeyValueW
0x14007533d  mov     ebx, eax
0x14007533f  test    eax, eax
0x140075341  jnz     short loc_140075399
0x140075343  lea     rcx, [rbp+150h+sz]
0x14007534a  call    ?SetNetworkCategoryHelper@PlatformUtils@@YAJPEBGW4ENetworkCategory@1@@Z; PlatformUtils::SetNetworkCategoryHelper(ushort const *,PlatformUtils::ENetworkCategory)
0x14007534f  mov     ebx, eax
0x140075351  test    eax, eax
0x140075353  js      loc_14007571A
0x140075359  mov     rcx, [rsp+250h+var_210]
0x14007535e  test    rcx, rcx
0x140075361  jz      short loc_140075374
0x140075363  mov     rax, [rcx]
0x140075366  mov     rax, [rax+10h]
0x14007536a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007536f  mov     [rsp+250h+var_210], r15
0x140075374  mov     rcx, [rsp+250h+bstr]; bstrString
0x140075379  call    cs:__imp_SysFreeString
0x14007537f  mov     rcx, [rsp+250h+bstrString]; bstrString
0x140075384  mov     [rsp+250h+bstr], r15
0x140075389  call    cs:__imp_SysFreeString
0x14007538f  mov     [rsp+250h+bstrString], r15
0x140075394  jmp     loc_140075171
0x140075399  jle     short loc_1400753A4
0x14007539b  movzx   ebx, ax
0x14007539e  or      ebx, 80070000h
0x1400753a4  lea     rax, aLr0l; "lr == 0L"
0x1400753ab  mov     [rsp+250h+cbData], ebx; int
0x1400753af  lea     rdi, aPlatformutilsS_0; "PlatformUtils::SetNetworkCategoryToWork"
0x1400753b6  mov     [rsp+250h+ppv], rax; unsigned __int16 *
0x1400753bb  mov     r8, rdi; unsigned __int16 *
0x1400753be  lea     r9, aCbraex; "CBRAEx"
0x1400753c5  mov     edx, 2D6h; unsigned int
0x1400753ca  mov     rcx, r12; unsigned __int16 *
0x1400753cd  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400753d2  call    cs:__imp_IsDebuggerPresent
0x1400753d8  test    eax, eax
0x1400753da  lea     rax, aLr0l; "lr == 0L"
0x1400753e1  jz      short loc_1400753FE
0x1400753e3  mov     [rsp+250h+var_218], ebx
  ... truncated ...
```
