# CWebServiceProxy::InitializeFromUrl(ushort *,ISessionService *,__MIDL___MIDL_itf_wmssvc_0000_0000_0002)

- ea: `0x14007704c`
- end: `0x140077442`
- name: `?InitializeFromUrl@CWebServiceProxy@@QEAAJPEAGPEAUISessionService@@W4__MIDL___MIDL_itf_wmssvc_0000_0000_0002@@@Z`
- size: `1014`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140050f00`
- `0x140051260`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140076c98`
- `0x14007704c`
- `0x14007cb9e`
- `0x14007e010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400770f9`
- `KERNEL32!GetLastError` at `0x1400770f9`
- `KERNEL32!IsDebuggerPresent` at `0x140077154`
- `KERNEL32!IsDebuggerPresent` at `0x14007720f`
- `KERNEL32!IsDebuggerPresent` at `0x1400772cb`
- `KERNEL32!IsDebuggerPresent` at `0x140077329`
- `KERNEL32!IsDebuggerPresent` at `0x140077154`
- `KERNEL32!IsDebuggerPresent` at `0x14007720f`
- `KERNEL32!IsDebuggerPresent` at `0x1400772cb`
- `KERNEL32!IsDebuggerPresent` at `0x140077329`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1400771c3`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1400771c3`
- `OLEAUT32!__imp_SysFreeString` at `0x140077403`
- `OLEAUT32!__imp_SysFreeString` at `0x140077414`
- `OLEAUT32!__imp_SysFreeString` at `0x14007741e`
- `OLEAUT32!__imp_SysFreeString` at `0x140077403`
- `OLEAUT32!__imp_SysFreeString` at `0x140077414`
- `OLEAUT32!__imp_SysFreeString` at `0x14007741e`
- `OLEAUT32!__imp_SysStringLen` at `0x1400770d6`
- `OLEAUT32!__imp_SysStringLen` at `0x1400773e2`
- `OLEAUT32!__imp_SysStringLen` at `0x1400770d6`
- `OLEAUT32!__imp_SysStringLen` at `0x1400773e2`
- `OLEAUT32!__imp_VariantInit` at `0x1400770bb`
- `OLEAUT32!__imp_VariantInit` at `0x1400770bb`
- `OLEAUT32!__imp_VariantClear` at `0x1400773d3`
- `OLEAUT32!__imp_VariantClear` at `0x1400773d3`
- `PROPSYS!VariantToUInt32` at `0x140077286`
- `PROPSYS!VariantToUInt32` at `0x140077286`
- `WINHTTP!WinHttpCrackUrl` at `0x1400770e8`
- `WINHTTP!WinHttpCrackUrl` at `0x1400770e8`

## string_xrefs

- `0x140077129`: `termsrv\wms\src\common\srcutils\cwebserviceproxy.cpp`
- `0x1400771e7`: `termsrv\wms\src\common\srcutils\cwebserviceproxy.cpp`
- `0x1400772a3`: `termsrv\wms\src\common\srcutils\cwebserviceproxy.cpp`
- `0x140077311`: `termsrv\wms\src\common\srcutils\cwebserviceproxy.cpp`
- `0x14007711c`: `CWebServiceProxy::InitializeFromUrl`
- `0x1400771d6`: `CWebServiceProxy::InitializeFromUrl`
- `0x140077296`: `CWebServiceProxy::InitializeFromUrl`
- `0x1400772ff`: `CWebServiceProxy::InitializeFromUrl`
- `0x1400772e8`: `sslPort == urlComponents.nPort`
- `0x140077331`: `sslPort == urlComponents.nPort`

## pseudocode

```c
__int64 __fastcall CWebServiceProxy::InitializeFromUrl(CWebServiceProxy *a1, OLECHAR *a2, __int64 a3, ULONG a4)
{
  UINT v7; // eax
  unsigned __int16 *v8; // r15
  signed int LastError; // eax
  int v10; // ebx
  unsigned int v11; // r13d
  bool v12; // zf
  const unsigned __int16 *v13; // rax
  unsigned int v14; // r14d
  const unsigned __int16 *v15; // r13
  bool v16; // zf
  const unsigned __int16 *v17; // rax
  HRESULT v18; // eax
  OLECHAR *v19; // rcx
  __int64 v20; // rax
  BSTR pbstr; // [rsp+48h] [rbp-69h] BYREF
  __int64 v23; // [rsp+50h] [rbp-61h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-59h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-51h] BYREF
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+78h] [rbp-39h] BYREF
  ULONG pulRet; // [rsp+130h] [rbp+7Fh] BYREF

  pulRet = a4;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  v23 = 0;
  bstrString = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  pbstr = 0;
  pulRet = 0;
  VariantInit(&pvarg);
  UrlComponents.dwStructSize = 104;
  UrlComponents.dwHostNameLength = 1;
  UrlComponents.dwUrlPathLength = 1;
  v7 = SysStringLen(a2);
  if ( !WinHttpCrackUrl(a2, v7, 0, &UrlComponents) )
  {
    v8 = 0;
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    v11 = 228;
    if ( v10 >= 0 )
      v10 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
      0xE4u,
      L"CWebServiceProxy::InitializeFromUrl",
      L"CBRAEx",
      L"fSuccess",
      v10);
    v12 = !IsDebuggerPresent();
    v13 = L"fSuccess";
    goto LABEL_7;
  }
  v8 = SysAllocStringLen((const OLECHAR *)UrlComponents.lpszHostName, UrlComponents.dwHostNameLength);
  if ( !v8 )
  {
    v10 = -2147024882;
    v14 = 231;
    v15 = L"bstrRemoteServerName";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
      0xE7u,
      L"CWebServiceProxy::InitializeFromUrl",
      L"CPR",
      L"bstrRemoteServerName",
      -2147024882);
    v16 = !IsDebuggerPresent();
    v17 = L"CPR";
    goto LABEL_14;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 *))(*(_QWORD *)a3 + 216LL))(a3, 1, v8);
  if ( v10 < 0 )
    goto LABEL_25;
  v18 = VariantToUInt32(&pvarg, &pulRet);
  v10 = v18;
  if ( v18 < 0 )
  {
    v14 = 238;
    v15 = L"hr";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
      0xEEu,
      L"CWebServiceProxy::InitializeFromUrl",
      L"CHRA",
      L"hr",
      v18);
    v16 = !IsDebuggerPresent();
    v17 = L"CHRA";
LABEL_14:
    if ( v16 )
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
        v14,
        L"CWebServiceProxy::InitializeFromUrl",
        v17,
        v15,
        v10);
    else
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
        v14,
        L"CWebServiceProxy::InitializeFromUrl",
        v17,
        v15,
        v10);
    goto LABEL_25;
  }
  if ( pulRet != UrlComponents.nPort )
  {
    v10 = -2147418113;
    v11 = 240;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
      0xF0u,
      L"CWebServiceProxy::InitializeFromUrl",
      L"CBRAEx",
      L"sslPort == urlComponents.nPort",
      -2147418113);
    v12 = !IsDebuggerPresent();
    v13 = L"sslPort == urlComponents.nPort";
LABEL_7:
    if ( v12 )
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
        v11,
        L"CWebServiceProxy::InitializeFromUrl",
        L"CBRAEx",
        v13,
        v10);
    else
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
        v11,
        L"CWebServiceProxy::InitializeFromUrl",
        L"CBRAEx",
        v13,
        v10);
    goto LABEL_25;
  }
  v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a3)(
          a3,
          &GUID_d5bbf19e_4292_4ad2_aff7_699fd76111e8,
          &v23);
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, __int64, BSTR *, BSTR *))(*(_QWORD *)v23 + 224LL))(
            v23,
            1,
            &bstrString,
            &pbstr);
    if ( v10 >= 0 )
      v10 = CWebServiceProxy::Initialize(
              a1,
              UrlComponents.nScheme,
              v8,
              UrlComponents.nPort,
              (unsigned __int16 *)UrlComponents.lpszUrlPath,
              bstrString,
              pbstr);
  }
LABEL_25:
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  VariantClear(&pvarg);
  if ( pbstr )
  {
    LODWORD(v20) = SysStringLen(pbstr);
    v19 = pbstr;
    v20 = (unsigned int)v20;
    if ( (_DWORD)v20 )
    {
      do
      {
        *(_BYTE *)v19 = 0;
        v19 = (OLECHAR *)((char *)v19 + 1);
        --v20;
      }
      while ( v20 );
      v19 = pbstr;
    }
    SysFreeString(v19);
    pbstr = 0;
  }
  SysFreeString(v8);
  SysFreeString(bstrString);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14007704c  mov     rax, rsp
0x14007704f  mov     [rax+8], rbx
0x140077053  mov     [rax+10h], rsi
0x140077057  mov     [rax+20h], r9d
0x14007705b  push    rbp
0x14007705c  push    rdi
0x14007705d  push    r13
0x14007705f  push    r14
0x140077061  push    r15
0x140077063  lea     rbp, [rax-5Fh]
0x140077067  sub     rsp, 0E0h
0x14007706e  mov     rdi, r8
0x140077071  mov     rbx, rdx
0x140077074  mov     rsi, rcx
0x140077077  mov     r14d, 68h ; 'h'
0x14007707d  mov     r8d, r14d; Size
0x140077080  lea     rcx, [rbp+57h+UrlComponents]; void *
0x140077084  xor     edx, edx; Val
0x140077086  call    memset_0
0x14007708b  xorps   xmm0, xmm0
0x14007708e  mov     [rbp+57h+var_B8], 0
0x140077096  xor     eax, eax
0x140077098  mov     [rbp+57h+bstrString], 0
0x1400770a0  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1400770a4  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1400770a8  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1400770ac  mov     [rbp+57h+pbstr], 0
0x1400770b4  mov     [rbp+57h+pulRet], 0
0x1400770bb  call    cs:__imp_VariantInit
0x1400770c1  mov     rcx, rbx; pbstr
0x1400770c4  mov     [rbp+57h+UrlComponents.dwStructSize], r14d
0x1400770c8  mov     [rbp+57h+UrlComponents.dwHostNameLength], 1
0x1400770cf  mov     [rbp+57h+UrlComponents.dwUrlPathLength], 1
0x1400770d6  call    cs:__imp_SysStringLen
0x1400770dc  lea     r9, [rbp+57h+UrlComponents]; lpUrlComponents
0x1400770e0  xor     r8d, r8d; dwFlags
0x1400770e3  mov     edx, eax; dwUrlLength
0x1400770e5  mov     rcx, rbx; pwszUrl
0x1400770e8  call    cs:__imp_WinHttpCrackUrl
0x1400770ee  test    eax, eax
0x1400770f0  jnz     loc_1400771BC
0x1400770f6  xor     r15d, r15d
0x1400770f9  call    cs:__imp_GetLastError
0x1400770ff  mov     ebx, eax
0x140077101  test    eax, eax
0x140077103  jle     short loc_14007710E
0x140077105  movzx   ebx, ax
0x140077108  or      ebx, 80070000h
0x14007710e  mov     eax, 80004005h
0x140077113  lea     r14, aCbraex; "CBRAEx"
0x14007711a  test    ebx, ebx
0x14007711c  lea     rsi, aCwebservicepro_5; "CWebServiceProxy::InitializeFromUrl"
0x140077123  mov     r13d, 0E4h
0x140077129  lea     rdi, aTermsrvWmsSrcC_9; "termsrv\\wms\\src\\common\\srcutils\\cw"...
0x140077130  cmovns  ebx, eax
0x140077133  mov     r9, r14; unsigned __int16 *
0x140077136  lea     rax, aFsuccess; "fSuccess"
0x14007713d  mov     dword ptr [rsp+100h+var_D8], ebx; int
0x140077141  mov     r8, rsi; unsigned __int16 *
0x140077144  mov     [rsp+100h+var_E0], rax; unsigned __int16 *
0x140077149  mov     edx, r13d; unsigned int
0x14007714c  mov     rcx, rdi; unsigned __int16 *
0x14007714f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140077154  call    cs:__imp_IsDebuggerPresent
0x14007715a  test    eax, eax
0x14007715c  lea     rax, aFsuccess; "fSuccess"
0x140077163  jz      short loc_140077194
0x140077165  mov     [rsp+100h+var_C8], ebx
0x140077169  mov     r9d, r13d
0x14007716c  mov     [rsp+100h+var_D0], rax
0x140077171  mov     [rsp+100h+var_D8], r14
0x140077176  mov     r8, rdi
0x140077179  mov     [rsp+100h+var_E0], rsi
0x14007717e  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140077185  mov     ecx, 2; unsigned __int8
0x14007718a  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14007718f  jmp     loc_1400773B2
0x140077194  mov     dword ptr [rsp+100h+var_D0], ebx
0x140077198  mov     r8d, r13d
0x14007719b  mov     [rsp+100h+var_D8], rax
0x1400771a0  mov     [rsp+100h+var_E0], r14
0x1400771a5  mov     r9, rsi
0x1400771a8  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400771af  mov     rdx, rdi
0x1400771b2  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400771b7  jmp     loc_1400773B2
0x1400771bc  mov     edx, [rbp+57h+UrlComponents.dwHostNameLength]; ui
0x1400771bf  mov     rcx, [rbp+57h+UrlComponents.lpszHostName]; strIn
0x1400771c3  call    cs:__imp_SysAllocStringLen
0x1400771c9  mov     r15, rax
0x1400771cc  test    rax, rax
0x1400771cf  jnz     short loc_14007724C
0x1400771d1  mov     ebx, 8007000Eh
0x1400771d6  lea     rsi, aCwebservicepro_5; "CWebServiceProxy::InitializeFromUrl"
0x1400771dd  mov     r14d, 0E7h
0x1400771e3  mov     dword ptr [rsp+100h+var_D8], ebx; int
0x1400771e7  lea     rdi, aTermsrvWmsSrcC_9; "termsrv\\wms\\src\\common\\srcutils\\cw"...
0x1400771ee  mov     r8, rsi; unsigned __int16 *
0x1400771f1  lea     r13, aBstrremoteserv; "bstrRemoteServerName"
0x1400771f8  mov     edx, r14d; unsigned int
0x1400771fb  mov     rcx, rdi; unsigned __int16 *
0x1400771fe  mov     [rsp+100h+var_E0], r13; unsigned __int16 *
0x140077203  lea     r9, aCpr; "CPR"
0x14007720a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007720f  call    cs:__imp_IsDebuggerPresent
0x140077215  test    eax, eax
0x140077217  lea     rax, aCpr; "CPR"
0x14007721e  jz      short loc_140077236
0x140077220  mov     [rsp+100h+var_C8], ebx
0x140077224  mov     r9d, r14d
0x140077227  mov     [rsp+100h+var_D0], r13
0x14007722c  mov     [rsp+100h+var_D8], rax
0x140077231  jmp     loc_140077176
0x140077236  mov     dword ptr [rsp+100h+var_D0], ebx
0x14007723a  mov     r8d, r14d
0x14007723d  mov     [rsp+100h+var_D8], r13
0x140077242  mov     [rsp+100h+var_E0], rax
0x140077247  jmp     loc_1400771A5
0x14007724c  mov     rax, [rdi]
0x14007724f  lea     rcx, [rbp+57h+pvarg]
0x140077253  mov     r9d, 6
0x140077259  mov     [rsp+100h+var_E0], rcx
0x14007725e  mov     r8, r15
0x140077261  mov     rcx, rdi
0x140077264  mov     rax, [rax+0D8h]
0x14007726b  lea     edx, [r9-5]
0x14007726f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140077274  mov     ebx, eax
0x140077276  test    eax, eax
0x140077278  js      loc_1400773B2
0x14007727e  lea     rdx, [rbp+57h+pulRet]; pulRet
0x140077282  lea     rcx, [rbp+57h+pvarg]; varIn
0x140077286  call    cs:__imp_VariantToUInt32
0x14007728c  mov     ebx, eax
0x14007728e  test    eax, eax
0x140077290  jns     short loc_1400772DF
0x140077292  mov     dword ptr [rsp+100h+var_D8], eax; int
0x140077296  lea     rsi, aCwebservicepro_5; "CWebServiceProxy::InitializeFromUrl"
0x14007729d  mov     r14d, 0EEh
0x1400772a3  lea     rdi, aTermsrvWmsSrcC_9; "termsrv\\wms\\src\\common\\srcutils\\cw"...
0x1400772aa  lea     r13, aHr; "hr"
0x1400772b1  mov     r8, rsi; unsigned __int16 *
0x1400772b4  mov     edx, r14d; unsigned int
0x1400772b7  mov     [rsp+100h+var_E0], r13; unsigned __int16 *
0x1400772bc  mov     rcx, rdi; unsigned __int16 *
0x1400772bf  lea     r9, aChra; "CHRA"
0x1400772c6  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400772cb  call    cs:__imp_IsDebuggerPresent
0x1400772d1  test    eax, eax
0x1400772d3  lea     rax, aChra; "CHRA"
0x1400772da  jmp     loc_14007721E
0x1400772df  movzx   eax, [rbp+57h+UrlComponents.nPort]
0x1400772e3  cmp     [rbp+57h+pulRet], eax
0x1400772e6  jz      short loc_14007733D
0x1400772e8  lea     rax, aSslportUrlcomp; "sslPort == urlComponents.nPort"
0x1400772ef  mov     ebx, 8000FFFFh
0x1400772f4  lea     r14, aCbraex; "CBRAEx"
0x1400772fb  mov     dword ptr [rsp+100h+var_D8], ebx; int
0x1400772ff  lea     rsi, aCwebservicepro_5; "CWebServiceProxy::InitializeFromUrl"
0x140077306  mov     [rsp+100h+var_E0], rax; unsigned __int16 *
0x14007730b  mov     r13d, 0F0h
0x140077311  lea     rdi, aTermsrvWmsSrcC_9; "termsrv\\wms\\src\\common\\srcutils\\cw"...
0x140077318  mov     r9, r14; unsigned __int16 *
0x14007731b  mov     r8, rsi; unsigned __int16 *
0x14007731e  mov     edx, r13d; unsigned int
0x140077321  mov     rcx, rdi; unsigned __int16 *
0x140077324  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140077329  call    cs:__imp_IsDebuggerPresent
0x14007732f  test    eax, eax
0x140077331  lea     rax, aSslportUrlcomp; "sslPort == urlComponents.nPort"
0x140077338  jmp     loc_140077163
0x14007733d  mov     rax, [rdi]
0x140077340  lea     r8, [rbp+57h+var_B8]
0x140077344  lea     rdx, _GUID_d5bbf19e_4292_4ad2_aff7_699fd76111e8
0x14007734b  mov     rcx, rdi
0x14007734e  mov     rax, [rax]
0x140077351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140077356  mov     ebx, eax
0x140077358  test    eax, eax
0x14007735a  js      short loc_1400773B2
0x14007735c  mov     rcx, [rbp+57h+var_B8]
0x140077360  lea     r9, [rbp+57h+pbstr]
0x140077364  lea     r8, [rbp+57h+bstrString]
0x140077368  mov     edx, 1
0x14007736d  mov     rax, [rcx]
0x140077370  mov     rax, [rax+0E0h]
0x140077377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007737c  mov     ebx, eax
0x14007737e  test    eax, eax
0x140077380  js      short loc_1400773B2
0x140077382  mov     rax, [rbp+57h+pbstr]
0x140077386  mov     r8, r15; unsigned __int16 *
0x140077389  movzx   r9d, [rbp+57h+UrlComponents.nPort]; unsigned int
0x14007738e  mov     rcx, rsi; this
0x140077391  mov     edx, [rbp+57h+UrlComponents.nScheme]; int
0x140077394  mov     [rsp+100h+var_D0], rax; unsigned __int16 *
0x140077399  mov     rax, [rbp+57h+bstrString]
0x14007739d  mov     [rsp+100h+var_D8], rax; unsigned __int16 *
0x1400773a2  mov     rax, [rbp+57h+UrlComponents.lpszUrlPath]
0x1400773a6  mov     [rsp+100h+var_E0], rax; unsigned __int16 *
0x1400773ab  call    ?Initialize@CWebServiceProxy@@QEAAJHPEAGK000@Z; CWebServiceProxy::Initialize(int,ushort *,ulong,ushort *,ushort *,ushort *)
0x1400773b0  mov     ebx, eax
0x1400773b2  mov     rcx, [rbp+57h+var_B8]
0x1400773b6  test    rcx, rcx
0x1400773b9  jz      short loc_1400773CF
0x1400773bb  mov     rax, [rcx]
0x1400773be  mov     rax, [rax+10h]
0x1400773c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400773c7  mov     [rbp+57h+var_B8], 0
0x1400773cf  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1400773d3  call    cs:__imp_VariantClear
0x1400773d9  mov     rcx, [rbp+57h+pbstr]; pbstr
0x1400773dd  test    rcx, rcx
0x1400773e0  jz      short loc_140077411
0x1400773e2  call    cs:__imp_SysStringLen
0x1400773e8  mov     rcx, [rbp+57h+pbstr]
0x1400773ec  mov     eax, eax
0x1400773ee  test    rax, rax
0x1400773f1  jz      short loc_140077403
0x1400773f3  mov     byte ptr [rcx], 0
0x1400773f6  inc     rcx
0x1400773f9  sub     rax, 1
0x1400773fd  jnz     short loc_1400773F3
0x1400773ff  mov     rcx, [rbp+57h+pbstr]; bstrString
0x140077403  call    cs:__imp_SysFreeString
0x140077409  mov     [rbp+57h+pbstr], 0
0x140077411  mov     rcx, r15; bstrString
0x140077414  call    cs:__imp_SysFreeString
0x14007741a  mov     rcx, [rbp+57h+bstrString]; bstrString
0x14007741e  call    cs:__imp_SysFreeString
0x140077424  lea     r11, [rsp+100h+var_20]
0x14007742c  mov     eax, ebx
0x14007742e  mov     rbx, [r11+30h]
0x140077432  mov     rsi, [r11+38h]
0x140077436  mov     rsp, r11
0x140077439  pop     r15
0x14007743b  pop     r14
0x14007743d  pop     r13
0x14007743f  pop     rdi
0x140077440  pop     rbp
0x140077441  retn
```
