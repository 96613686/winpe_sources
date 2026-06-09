# CWmsWebService::SetBlockAllMessage(_WS_OPERATION_CONTEXT const *,_WS_STRING,_WS_ASYNC_CONTEXT const *,_WS_ERROR *)

- ea: `0x140051640`
- end: `0x1400518be`
- name: `?SetBlockAllMessage@CWmsWebService@@SAJPEBU_WS_OPERATION_CONTEXT@@U_WS_STRING@@PEBU_WS_ASYNC_CONTEXT@@PEAU_WS_ERROR@@@Z`
- size: `638`
- prototype: `static int(const struct _WS_OPERATION_CONTEXT *, struct _WS_STRING *__struct_ptr, const struct _WS_ASYNC_CONTEXT *, struct _WS_ERROR *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x14004c43c`
- `0x140051640`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14006296c`
- `0x140065070`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1400517b4`
- `ADVAPI32!RegOpenKeyExW` at `0x1400517b4`
- `ADVAPI32!RegCloseKey` at `0x140051888`
- `ADVAPI32!RegCloseKey` at `0x140051888`
- `ADVAPI32!RegDeleteValueW` at `0x140051875`
- `ADVAPI32!RegDeleteValueW` at `0x140051875`
- `ADVAPI32!RegCreateKeyExW` at `0x1400516cd`
- `ADVAPI32!RegCreateKeyExW` at `0x1400516cd`
- `KERNEL32!IsDebuggerPresent` at `0x14005171d`
- `KERNEL32!IsDebuggerPresent` at `0x140051810`
- `KERNEL32!IsDebuggerPresent` at `0x14005171d`
- `KERNEL32!IsDebuggerPresent` at `0x140051810`
- `OLEAUT32!__imp_SysFreeString` at `0x14005189f`
- `OLEAUT32!__imp_SysFreeString` at `0x14005189f`

## string_xrefs

- `0x140051711`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x140051731`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x140051804`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x14005182f`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x1400516f3`: `CWmsWebService::SetBlockAllMessage`
- `0x1400517e6`: `CWmsWebService::SetBlockAllMessage`

## pseudocode

```c
__int64 __fastcall CWmsWebService::SetBlockAllMessage(
        const struct _WS_OPERATION_CONTEXT *a1,
        struct _WS_STRING *a2,
        const struct _WS_ASYNC_CONTEXT *a3,
        struct _WS_ERROR *a4)
{
  bool v4; // zf
  signed int v6; // ebx
  LSTATUS v7; // eax
  const unsigned __int16 *v8; // r9
  __int64 v9; // r9
  __int64 v10; // r8
  LSTATUS v11; // eax
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-48h]
  PHKEY phkResult; // [rsp+38h] [rbp-40h]
  BSTR bstrString; // [rsp+50h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+10h] BYREF

  v4 = a2->length == 0;
  bstrString = 0;
  hKey = 0;
  if ( v4 )
  {
    v11 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows MultiPoint Server\\Orchestration",
            0,
            2u,
            &hKey);
    v6 = v11;
    if ( v11 == 2 )
    {
      v6 = 0;
      goto LABEL_25;
    }
    if ( !v11 )
    {
      v6 = 0;
      RegDeleteValueW(hKey, L"Block Message");
      goto LABEL_25;
    }
    if ( v11 > 0 )
      v6 = (unsigned __int16)v11 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
      0x6D5u,
      L"CWmsWebService::SetBlockAllMessage",
      L"CBRAEx",
      L"lr == 0L",
      v6);
    if ( IsDebuggerPresent() )
    {
      v9 = 1749;
      goto LABEL_8;
    }
    v10 = 1749;
LABEL_20:
    LODWORD(lpSecurityAttributes) = v6;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
      v10,
      L"CWmsWebService::SetBlockAllMessage",
      L"CBRAEx",
      L"lr == 0L",
      lpSecurityAttributes);
LABEL_21:
    if ( v6 >= 0 )
      goto LABEL_25;
    goto LABEL_22;
  }
  v6 = WsStringToBstr(a2, &bstrString);
  if ( v6 >= 0 )
  {
    v7 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows MultiPoint Server\\Orchestration",
           0,
           0,
           0,
           2u,
           0,
           &hKey,
           0);
    v6 = v7;
    if ( !v7 )
    {
      v6 = RegUtil::SetStringValue((RegUtil *)hKey, (HKEY)L"Block Message", bstrString, v8);
      if ( v6 >= 0 )
        goto LABEL_25;
      goto LABEL_22;
    }
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
      0x6CCu,
      L"CWmsWebService::SetBlockAllMessage",
      L"CBRAEx",
      L"lr == 0L",
      v6);
    if ( IsDebuggerPresent() )
    {
      v9 = 1740;
LABEL_8:
      LODWORD(phkResult) = v6;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
        v9,
        L"CWmsWebService::SetBlockAllMessage",
        L"CBRAEx",
        L"lr == 0L",
        phkResult);
      goto LABEL_21;
    }
    v10 = 1740;
    goto LABEL_20;
  }
LABEL_22:
  if ( a4 )
    CWmsWebService::s_CreateWmsFault(v6, a4);
LABEL_25:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  SysFreeString(bstrString);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140051640  mov     r11, rsp
0x140051643  mov     [r11+8], rbx
0x140051647  mov     [r11+18h], rbp
0x14005164b  push    r12
0x14005164d  push    r14
0x14005164f  push    r15
0x140051651  sub     rsp, 60h
0x140051655  cmp     dword ptr [rdx], 0
0x140051658  mov     r12, r9
0x14005165b  mov     rax, rdx
0x14005165e  mov     qword ptr [r11-28h], 0
0x140051666  mov     qword ptr [r11+10h], 0
0x14005166e  jbe     loc_140051790
0x140051674  lea     rdx, [r11-28h]; unsigned __int16 **
0x140051678  mov     rcx, rax; struct _WS_STRING *
0x14005167b  call    ?WsStringToBstr@@YAJPEBU_WS_STRING@@PEAPEAG@Z; WsStringToBstr(_WS_STRING const *,ushort * *)
0x140051680  mov     ebx, eax
0x140051682  test    eax, eax
0x140051684  js      loc_140051853
0x14005168a  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x140051693  lea     rax, [rsp+78h+hKey]
0x14005169b  mov     [rsp+78h+phkResult], rax; phkResult
0x1400516a0  lea     rdx, aSoftwareMicros_29; "SOFTWARE\\Microsoft\\Windows MultiPoint"...
0x1400516a7  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1400516b0  xor     r9d, r9d; lpClass
0x1400516b3  mov     [rsp+78h+samDesired], 2; samDesired
0x1400516bb  xor     r8d, r8d; Reserved
0x1400516be  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400516c5  mov     [rsp+78h+dwOptions], 0; dwOptions
0x1400516cd  call    cs:__imp_RegCreateKeyExW
0x1400516d3  mov     ebx, eax
0x1400516d5  test    eax, eax
0x1400516d7  jz      loc_140051768
0x1400516dd  jle     short loc_1400516E8
0x1400516df  movzx   ebx, ax
0x1400516e2  or      ebx, 80070000h
0x1400516e8  lea     r15, aCbraex; "CBRAEx"
0x1400516ef  mov     [rsp+78h+samDesired], ebx; int
0x1400516f3  lea     rbp, aCwmswebservice_62; "CWmsWebService::SetBlockAllMessage"
0x1400516fa  mov     r9, r15; unsigned __int16 *
0x1400516fd  lea     r14, aLr0l; "lr == 0L"
0x140051704  mov     r8, rbp; unsigned __int16 *
0x140051707  mov     edx, 6CCh; unsigned int
0x14005170c  mov     qword ptr [rsp+78h+dwOptions], r14; unsigned __int16 *
0x140051711  lea     rcx, aTermsrvWmsSrcD_5; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140051718  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005171d  call    cs:__imp_IsDebuggerPresent
0x140051723  test    eax, eax
0x140051725  jz      short loc_14005175D
0x140051727  mov     r9d, 6CCh
0x14005172d  mov     dword ptr [rsp+78h+phkResult], ebx
0x140051731  lea     r8, aTermsrvWmsSrcD_5; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140051738  mov     [rsp+78h+lpSecurityAttributes], r14
0x14005173d  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140051744  mov     qword ptr [rsp+78h+samDesired], r15
0x140051749  mov     ecx, 2; unsigned __int8
0x14005174e  mov     qword ptr [rsp+78h+dwOptions], rbp
0x140051753  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140051758  jmp     loc_14005184F
0x14005175d  mov     r8d, 6CCh
0x140051763  jmp     loc_14005182B
0x140051768  mov     r8, [rsp+78h+bstrString]; unsigned __int16 *
0x14005176d  lea     rdx, ?g_kszBlockMessage@@3QBGB; "Block Message"
0x140051774  mov     rcx, [rsp+78h+hKey]; this
0x14005177c  call    ?SetStringValue@RegUtil@@YAJPEAUHKEY__@@PEBG1@Z; RegUtil::SetStringValue(HKEY__ *,ushort const *,ushort const *)
0x140051781  mov     ebx, eax
0x140051783  test    eax, eax
0x140051785  js      loc_140051853
0x14005178b  jmp     loc_14005187B
0x140051790  lea     rax, [rsp+78h+hKey]
0x140051798  mov     r9d, 2; samDesired
0x14005179e  xor     r8d, r8d; ulOptions
0x1400517a1  mov     qword ptr [rsp+78h+dwOptions], rax; phkResult
0x1400517a6  lea     rdx, aSoftwareMicros_29; "SOFTWARE\\Microsoft\\Windows MultiPoint"...
0x1400517ad  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400517b4  call    cs:__imp_RegOpenKeyExW
0x1400517ba  mov     ebx, eax
0x1400517bc  cmp     eax, 2
0x1400517bf  jnz     short loc_1400517C8
0x1400517c1  xor     ebx, ebx
0x1400517c3  jmp     loc_14005187B
0x1400517c8  test    eax, eax
0x1400517ca  jz      loc_140051864
0x1400517d0  jle     short loc_1400517DB
0x1400517d2  movzx   ebx, ax
0x1400517d5  or      ebx, 80070000h
0x1400517db  lea     r15, aCbraex; "CBRAEx"
0x1400517e2  mov     [rsp+78h+samDesired], ebx; int
0x1400517e6  lea     rbp, aCwmswebservice_62; "CWmsWebService::SetBlockAllMessage"
0x1400517ed  mov     r9, r15; unsigned __int16 *
0x1400517f0  lea     r14, aLr0l; "lr == 0L"
0x1400517f7  mov     r8, rbp; unsigned __int16 *
0x1400517fa  mov     edx, 6D5h; unsigned int
0x1400517ff  mov     qword ptr [rsp+78h+dwOptions], r14; unsigned __int16 *
0x140051804  lea     rcx, aTermsrvWmsSrcD_5; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14005180b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140051810  call    cs:__imp_IsDebuggerPresent
0x140051816  test    eax, eax
0x140051818  jz      short loc_140051825
0x14005181a  mov     r9d, 6D5h
0x140051820  jmp     loc_14005172D
0x140051825  mov     r8d, 6D5h
0x14005182b  mov     dword ptr [rsp+78h+lpSecurityAttributes], ebx
0x14005182f  lea     rdx, aTermsrvWmsSrcD_5; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140051836  mov     qword ptr [rsp+78h+samDesired], r14
0x14005183b  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140051842  mov     r9, rbp
0x140051845  mov     qword ptr [rsp+78h+dwOptions], r15
0x14005184a  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14005184f  test    ebx, ebx
0x140051851  jns     short loc_14005187B
0x140051853  test    r12, r12
0x140051856  jz      short loc_14005187B
0x140051858  mov     rdx, r12; struct _WS_ERROR *
0x14005185b  mov     ecx, ebx; int
0x14005185d  call    ?s_CreateWmsFault@CWmsWebService@@CAJJPEAU_WS_ERROR@@@Z; CWmsWebService::s_CreateWmsFault(long,_WS_ERROR *)
0x140051862  jmp     short loc_14005187B
0x140051864  mov     rcx, [rsp+78h+hKey]; hKey
0x14005186c  lea     rdx, ?g_kszBlockMessage@@3QBGB; "Block Message"
0x140051873  xor     ebx, ebx
0x140051875  call    cs:__imp_RegDeleteValueW
0x14005187b  mov     rcx, [rsp+78h+hKey]; hKey
0x140051883  test    rcx, rcx
0x140051886  jz      short loc_14005189A
0x140051888  call    cs:__imp_RegCloseKey
0x14005188e  mov     [rsp+78h+hKey], 0
0x14005189a  mov     rcx, [rsp+78h+bstrString]; bstrString
0x14005189f  call    cs:__imp_SysFreeString
0x1400518a5  lea     r11, [rsp+78h+var_18]
0x1400518aa  mov     eax, ebx
0x1400518ac  mov     rbx, [r11+20h]
0x1400518b0  mov     rbp, [r11+30h]
0x1400518b4  mov     rsp, r11
0x1400518b7  pop     r15
0x1400518b9  pop     r14
0x1400518bb  pop     r12
0x1400518bd  retn
```
