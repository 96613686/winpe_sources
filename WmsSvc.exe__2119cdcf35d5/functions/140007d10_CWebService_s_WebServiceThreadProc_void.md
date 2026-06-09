# CWebService::s_WebServiceThreadProc(void *)

- ea: `0x140007d10`
- end: `0x140007fc7`
- name: `?s_WebServiceThreadProc@CWebService@@CAKPEAX@Z`
- size: `695`
- prototype: `__int64 __fastcall(char *Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x140007d10`
- `0x14005b9d4`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `KERNEL32!SetEvent` at `0x140007f42`
- `KERNEL32!SetEvent` at `0x140007fae`
- `KERNEL32!SetEvent` at `0x140007f42`
- `KERNEL32!SetEvent` at `0x140007fae`
- `KERNEL32!WaitForSingleObject` at `0x140007f5e`
- `KERNEL32!WaitForSingleObject` at `0x140007f5e`
- `KERNEL32!IsDebuggerPresent` at `0x140007d7d`
- `KERNEL32!IsDebuggerPresent` at `0x140007e66`
- `KERNEL32!IsDebuggerPresent` at `0x140007f1b`
- `KERNEL32!IsDebuggerPresent` at `0x140007d7d`
- `KERNEL32!IsDebuggerPresent` at `0x140007e66`
- `KERNEL32!IsDebuggerPresent` at `0x140007f1b`
- `ole32!CoUninitialize` at `0x140007f9b`
- `ole32!CoUninitialize` at `0x140007f9b`
- `ole32!CoInitializeEx` at `0x140007d28`
- `ole32!CoInitializeEx` at `0x140007d28`
- `webservices!WsFreeServiceHost` at `0x140007f8a`
- `webservices!WsFreeServiceHost` at `0x140007f8a`
- `webservices!WsCloseServiceHost` at `0x140007f6c`
- `webservices!WsCloseServiceHost` at `0x140007f6c`
- `webservices!WsOpenServiceHost` at `0x140007ed7`
- `webservices!WsOpenServiceHost` at `0x140007ed7`
- `webservices!WsCreateServiceHost` at `0x140007e1e`
- `webservices!WsCreateServiceHost` at `0x140007e1e`

## string_xrefs

- `0x140007d5a`: `termsrv\wms\src\devices\wmssvc\cwebservice.cpp`
- `0x140007e43`: `termsrv\wms\src\devices\wmssvc\cwebservice.cpp`
- `0x140007ef8`: `termsrv\wms\src\devices\wmssvc\cwebservice.cpp`
- `0x140007d43`: `CWebService::s_WebServiceThreadProc`
- `0x140007e39`: `CWebService::s_WebServiceThreadProc`
- `0x140007eee`: `CWebService::s_WebServiceThreadProc`
- `0x140007f48`: `CWebService::s_WebServiceThreadProc - signalled web service ready event\n`

## pseudocode

```c
__int64 __fastcall CWebService::s_WebServiceThreadProc(char *Parameter)
{
  HRESULT v2; // eax
  HRESULT v3; // ebx
  int v4; // ebp
  WS_ERROR **v5; // rdi
  WS_SERVICE_HOST **v6; // r14
  HRESULT ServiceHost; // eax
  __int64 v8; // r9
  __int64 v9; // r8
  HRESULT v10; // eax
  void *v11; // rcx
  HRESULT v13; // [rsp+30h] [rbp-58h]
  HRESULT v14; // [rsp+30h] [rbp-58h]
  HRESULT v15; // [rsp+38h] [rbp-50h]
  HRESULT v16; // [rsp+38h] [rbp-50h]

  v2 = CoInitializeEx(0, 0);
  v3 = v2;
  if ( v2 < 0 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\cwebservice.cpp",
      0x13Au,
      L"CWebService::s_WebServiceThreadProc",
      L"CHRA",
      L"hr",
      v2);
    if ( IsDebuggerPresent() )
    {
      v15 = v3;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\cwebservice.cpp",
        314,
        L"CWebService::s_WebServiceThreadProc",
        L"CHRA",
        L"hr",
        v15);
    }
    else
    {
      v13 = v3;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\cwebservice.cpp",
        314,
        L"CWebService::s_WebServiceThreadProc",
        L"CHRA",
        L"hr",
        v13);
    }
    v4 = 0;
    v5 = (WS_ERROR **)(Parameter + 24);
    v6 = (WS_SERVICE_HOST **)(Parameter + 168);
    goto LABEL_18;
  }
  v5 = (WS_ERROR **)(Parameter + 24);
  v6 = (WS_SERVICE_HOST **)(Parameter + 168);
  v4 = 1;
  ServiceHost = WsCreateServiceHost(
                  *((const WS_SERVICE_ENDPOINT ***)Parameter + 23),
                  *((_WORD *)Parameter + 96),
                  0,
                  0,
                  (WS_SERVICE_HOST **)Parameter + 21,
                  *((WS_ERROR **)Parameter + 3));
  v3 = ServiceHost;
  if ( ServiceHost >= 0 )
  {
    v10 = WsOpenServiceHost(*v6, 0, *v5);
    v3 = v10;
    if ( v10 >= 0 )
    {
      SetEvent(*((HANDLE *)Parameter + 27));
      DEBUGMSG(L"CWebService::s_WebServiceThreadProc - signalled web service ready event\n");
      WaitForSingleObject(*((HANDLE *)Parameter + 26), 0xFFFFFFFF);
      v3 = WsCloseServiceHost(*v6, 0, *v5);
      if ( v3 >= 0 )
        goto LABEL_19;
      goto LABEL_18;
    }
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\cwebservice.cpp",
      0x144u,
      L"CWebService::s_WebServiceThreadProc",
      L"CHRA",
      L"hr",
      v10);
    if ( IsDebuggerPresent() )
    {
      v8 = 324;
      goto LABEL_9;
    }
    v9 = 324;
LABEL_11:
    v14 = v3;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\cwebservice.cpp",
      v9,
      L"CWebService::s_WebServiceThreadProc",
      L"CHRA",
      L"hr",
      v14);
    goto LABEL_12;
  }
  LOGASSERTHR(
    L"termsrv\\wms\\src\\devices\\wmssvc\\cwebservice.cpp",
    0x140u,
    L"CWebService::s_WebServiceThreadProc",
    L"CHRA",
    L"hr",
    ServiceHost);
  if ( !IsDebuggerPresent() )
  {
    v9 = 320;
    goto LABEL_11;
  }
  v8 = 320;
LABEL_9:
  v16 = v3;
  DEBUGMSGLEVEL(
    2u,
    L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
    L"termsrv\\wms\\src\\devices\\wmssvc\\cwebservice.cpp",
    v8,
    L"CWebService::s_WebServiceThreadProc",
    L"CHRA",
    L"hr",
    v16);
LABEL_12:
  v4 = 1;
LABEL_18:
  WebServicePrintExtendedErrorInfo(v3, *v5);
LABEL_19:
  if ( *v6 )
  {
    WsFreeServiceHost(*v6);
    *v6 = 0;
  }
  if ( v4 )
    CoUninitialize();
  v11 = (void *)*((_QWORD *)Parameter + 27);
  *((_DWORD *)Parameter + 56) = v3;
  SetEvent(v11);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140007d10  push    rbx
0x140007d12  push    rbp
0x140007d13  push    rsi
0x140007d14  push    rdi
0x140007d15  push    r12
0x140007d17  push    r13
0x140007d19  push    r14
0x140007d1b  push    r15
0x140007d1d  sub     rsp, 48h
0x140007d21  mov     rsi, rcx
0x140007d24  xor     edx, edx; dwCoInit
0x140007d26  xor     ecx, ecx; pvReserved
0x140007d28  call    cs:__imp_CoInitializeEx
0x140007d2e  mov     ebx, eax
0x140007d30  test    eax, eax
0x140007d32  jns     loc_140007DED
0x140007d38  mov     dword ptr [rsp+88h+error], eax; int
0x140007d3c  lea     r13, aChra; "CHRA"
0x140007d43  lea     r15, aCwebserviceSWe; "CWebService::s_WebServiceThreadProc"
0x140007d4a  mov     [rsp+88h+arg_0], 0
0x140007d55  mov     edi, 13Ah
0x140007d5a  lea     rbp, aTermsrvWmsSrcD_31; "termsrv\\wms\\src\\devices\\wmssvc\\cwe"...
0x140007d61  lea     r12, aHr; "hr"
0x140007d68  mov     r9, r13; unsigned __int16 *
0x140007d6b  mov     r8, r15; unsigned __int16 *
0x140007d6e  mov     [rsp+88h+serviceHost], r12; unsigned __int16 *
0x140007d73  mov     edx, edi; unsigned int
0x140007d75  mov     rcx, rbp; unsigned __int16 *
0x140007d78  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140007d7d  call    cs:__imp_IsDebuggerPresent
0x140007d83  test    eax, eax
0x140007d85  jz      short loc_140007DB3
0x140007d87  mov     [rsp+88h+var_50], ebx
0x140007d8b  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140007d92  mov     [rsp+88h+var_58], r12
0x140007d97  mov     r9d, edi
0x140007d9a  mov     [rsp+88h+error], r13
0x140007d9f  mov     r8, rbp
0x140007da2  mov     ecx, 2; unsigned __int8
0x140007da7  mov     [rsp+88h+serviceHost], r15
0x140007dac  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140007db1  jmp     short loc_140007DD6
0x140007db3  mov     dword ptr [rsp+88h+var_58], ebx
0x140007db7  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140007dbe  mov     [rsp+88h+error], r12
0x140007dc3  mov     r9, r15
0x140007dc6  mov     r8d, edi
0x140007dc9  mov     [rsp+88h+serviceHost], r13
0x140007dce  mov     rdx, rbp
0x140007dd1  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140007dd6  mov     ebp, [rsp+88h+arg_0]
0x140007ddd  lea     rdi, [rsi+18h]
0x140007de1  lea     r14, [rsi+0A8h]
0x140007de8  jmp     loc_140007F78
0x140007ded  movzx   edx, word ptr [rsi+0C0h]; endpointCount
0x140007df4  lea     rdi, [rsi+18h]
0x140007df8  mov     rax, [rdi]
0x140007dfb  lea     r14, [rsi+0A8h]
0x140007e02  mov     rcx, [rsi+0B8h]; endpoints
0x140007e09  xor     r9d, r9d; servicePropertyCount
0x140007e0c  mov     [rsp+88h+error], rax; error
0x140007e11  xor     r8d, r8d; serviceProperties
0x140007e14  mov     [rsp+88h+serviceHost], r14; serviceHost
0x140007e19  mov     ebp, 1
0x140007e1e  call    cs:__imp_WsCreateServiceHost
0x140007e24  mov     ebx, eax
0x140007e26  test    eax, eax
0x140007e28  jns     loc_140007ECF
0x140007e2e  mov     dword ptr [rsp+88h+error], eax; int
0x140007e32  lea     r13, aChra; "CHRA"
0x140007e39  lea     r15, aCwebserviceSWe; "CWebService::s_WebServiceThreadProc"
0x140007e40  mov     r9, r13; unsigned __int16 *
0x140007e43  lea     rbp, aTermsrvWmsSrcD_31; "termsrv\\wms\\src\\devices\\wmssvc\\cwe"...
0x140007e4a  mov     r8, r15; unsigned __int16 *
0x140007e4d  lea     r12, aHr; "hr"
0x140007e54  mov     rcx, rbp; unsigned __int16 *
0x140007e57  mov     edx, 140h; unsigned int
0x140007e5c  mov     [rsp+88h+serviceHost], r12; unsigned __int16 *
0x140007e61  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140007e66  call    cs:__imp_IsDebuggerPresent
0x140007e6c  test    eax, eax
0x140007e6e  jz      short loc_140007E9F
0x140007e70  mov     r9d, 140h
0x140007e76  mov     [rsp+88h+var_50], ebx
0x140007e7a  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140007e81  mov     [rsp+88h+var_58], r12
0x140007e86  mov     r8, rbp
0x140007e89  mov     [rsp+88h+error], r13
0x140007e8e  mov     ecx, 2; unsigned __int8
0x140007e93  mov     [rsp+88h+serviceHost], r15
0x140007e98  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140007e9d  jmp     short loc_140007EC5
0x140007e9f  mov     r8d, 140h
0x140007ea5  mov     dword ptr [rsp+88h+var_58], ebx
0x140007ea9  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140007eb0  mov     [rsp+88h+error], r12
0x140007eb5  mov     r9, r15
0x140007eb8  mov     rdx, rbp
0x140007ebb  mov     [rsp+88h+serviceHost], r13
0x140007ec0  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140007ec5  mov     ebp, 1
0x140007eca  jmp     loc_140007F78
0x140007ecf  mov     r8, [rdi]; error
0x140007ed2  xor     edx, edx; asyncContext
0x140007ed4  mov     rcx, [r14]; serviceHost
0x140007ed7  call    cs:__imp_WsOpenServiceHost
0x140007edd  mov     ebx, eax
0x140007edf  test    eax, eax
0x140007ee1  jns     short loc_140007F3B
0x140007ee3  mov     dword ptr [rsp+88h+error], eax; int
0x140007ee7  lea     r13, aChra; "CHRA"
0x140007eee  lea     r15, aCwebserviceSWe; "CWebService::s_WebServiceThreadProc"
0x140007ef5  mov     r9, r13; unsigned __int16 *
0x140007ef8  lea     rbp, aTermsrvWmsSrcD_31; "termsrv\\wms\\src\\devices\\wmssvc\\cwe"...
0x140007eff  mov     r8, r15; unsigned __int16 *
0x140007f02  lea     r12, aHr; "hr"
0x140007f09  mov     rcx, rbp; unsigned __int16 *
0x140007f0c  mov     edx, 144h; unsigned int
0x140007f11  mov     [rsp+88h+serviceHost], r12; unsigned __int16 *
0x140007f16  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140007f1b  call    cs:__imp_IsDebuggerPresent
0x140007f21  test    eax, eax
0x140007f23  jz      short loc_140007F30
0x140007f25  mov     r9d, 144h
0x140007f2b  jmp     loc_140007E76
0x140007f30  mov     r8d, 144h
0x140007f36  jmp     loc_140007EA5
0x140007f3b  mov     rcx, [rsi+0D8h]; hEvent
0x140007f42  call    cs:__imp_SetEvent
0x140007f48  lea     rcx, aCwebserviceSWe_0; "CWebService::s_WebServiceThreadProc - s"...
0x140007f4f  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140007f54  mov     rcx, [rsi+0D0h]; hHandle
0x140007f5b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140007f5e  call    cs:__imp_WaitForSingleObject
0x140007f64  mov     r8, [rdi]; error
0x140007f67  xor     edx, edx; asyncContext
0x140007f69  mov     rcx, [r14]; serviceHost
0x140007f6c  call    cs:__imp_WsCloseServiceHost
0x140007f72  mov     ebx, eax
0x140007f74  test    eax, eax
0x140007f76  jns     short loc_140007F82
0x140007f78  mov     rdx, [rdi]; struct _WS_ERROR *
0x140007f7b  mov     ecx, ebx; int
0x140007f7d  call    ?WebServicePrintExtendedErrorInfo@@YAXJPEAU_WS_ERROR@@@Z; WebServicePrintExtendedErrorInfo(long,_WS_ERROR *)
0x140007f82  mov     rcx, [r14]; serviceHost
0x140007f85  test    rcx, rcx
0x140007f88  jz      short loc_140007F97
0x140007f8a  call    cs:__imp_WsFreeServiceHost
0x140007f90  mov     qword ptr [r14], 0
0x140007f97  test    ebp, ebp
0x140007f99  jz      short loc_140007FA1
0x140007f9b  call    cs:__imp_CoUninitialize
0x140007fa1  mov     rcx, [rsi+0D8h]; hEvent
0x140007fa8  mov     [rsi+0E0h], ebx
0x140007fae  call    cs:__imp_SetEvent
0x140007fb4  mov     eax, ebx
0x140007fb6  add     rsp, 48h
0x140007fba  pop     r15
0x140007fbc  pop     r14
0x140007fbe  pop     r13
0x140007fc0  pop     r12
0x140007fc2  pop     rdi
0x140007fc3  pop     rsi
0x140007fc4  pop     rbp
0x140007fc5  pop     rbx
0x140007fc6  retn
```
