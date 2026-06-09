# CWmsService::StartUp(void)

- ea: `0x140045b90`
- end: `0x140045f98`
- name: `?StartUp@CWmsService@@AEAAJXZ`
- size: `1032`
- prototype: `__int64 __fastcall(CWmsService *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1400460b0`

## callees

- `0x140001cd4`
- `0x140001d44`
- `0x140039de0`
- `0x140044688`
- `0x140044940`
- `0x140045b90`
- `0x140048704`
- `0x14004c234`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14005ec34`
- `0x140065fdc`
- `0x140068ebc`
- `0x14007e010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x140045e7a`
- `KERNEL32!SetEvent` at `0x140045e7a`
- `KERNEL32!WaitForSingleObject` at `0x140045dd8`
- `KERNEL32!WaitForSingleObject` at `0x140045dd8`
- `KERNEL32!GetLastError` at `0x140045e84`
- `KERNEL32!GetLastError` at `0x140045e84`
- `KERNEL32!IsDebuggerPresent` at `0x140045c45`
- `KERNEL32!IsDebuggerPresent` at `0x140045e2b`
- `KERNEL32!IsDebuggerPresent` at `0x140045c45`
- `KERNEL32!IsDebuggerPresent` at `0x140045e2b`
- `ole32!CoCreateInstance` at `0x140045bfb`
- `ole32!CoCreateInstance` at `0x140045bfb`

## string_xrefs

- `0x140045c22`: `termsrv\wms\src\devices\wmssvc\wmsservice.cpp`
- `0x140045e13`: `termsrv\wms\src\devices\wmssvc\wmsservice.cpp`
- `0x140045c16`: `CWmsService::StartUp`
- `0x140045e07`: `CWmsService::StartUp`
- `0x140045dc1`: `CWmsService::StartUp - waiting for web service ready event\n`
- `0x140045eb5`: `CWmsService::StartUp - signalled service ready event\n`
- `0x140045f4a`: `Global\WmsSelfHealingSvcReadyEvent`

## pseudocode

```c
__int64 __fastcall CWmsService::StartUp(CWmsService *this)
{
  HRESULT Instance; // eax
  signed int SvcEventSink; // ebx
  CWmsService *v4; // rcx
  unsigned __int64 i; // rsi
  signed int v6; // eax
  const unsigned __int16 *v7; // r15
  unsigned int v8; // r14d
  signed int LastError; // eax
  HANDLE hHandle; // [rsp+80h] [rbp+8h] BYREF

  if ( dword_1400EF628 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
  {
    Init_thread_header(&dword_1400EF628);
    if ( dword_1400EF628 == -1 )
    {
      qword_1400EE2D0 = (__int64)this + 856;
      dword_1400EE2E0 = 1048578;
      qword_1400EE2D8 = (__int64)L"Global\\WmsSelfHealingSvcReadyEvent";
      qword_1400EE2E8 = (__int64)this + 864;
      qword_1400EE2F0 = (__int64)L"Global\\WmsShellStartingEvent";
      qword_1400EE300 = (__int64)this + 872;
      dword_1400EE2F8 = 1048578;
      Init_thread_footer(&dword_1400EF628);
    }
  }
  hHandle = 0;
  SetSuppressDeviceInstallUI(1);
  COutOfProcFactory::s_StartFactories();
  Instance = CoCreateInstance(
               &CLSID_DiskProtection,
               0,
               4u,
               &GUID_ca426330_3409_48e1_b77c_87b19091cddf,
               (LPVOID *)this + 146);
  SvcEventSink = Instance;
  if ( Instance < 0 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmsservice.cpp",
      0x1AAu,
      L"CWmsService::StartUp",
      L"CHRA",
      L"hr",
      Instance);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmsservice.cpp",
        426,
        L"CWmsService::StartUp",
        L"CHRA",
        L"hr",
        SvcEventSink);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmsservice.cpp",
        426,
        L"CWmsService::StartUp",
        L"CHRA",
        L"hr",
        SvcEventSink);
    return (unsigned int)SvcEventSink;
  }
  SvcEventSink = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 149) + 8LL))((char *)this + 1192);
  if ( SvcEventSink >= 0 )
  {
    SvcEventSink = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 190) + 8LL))((char *)this + 1520);
    if ( SvcEventSink >= 0 )
    {
      SvcEventSink = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 393) + 8LL))((char *)this + 3144);
      if ( SvcEventSink >= 0 )
      {
        SvcEventSink = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 272) + 8LL))((char *)this + 2176);
        if ( SvcEventSink >= 0 )
        {
          SvcEventSink = CWmsService::CreateSvcEventSink(this);
          if ( SvcEventSink >= 0 )
          {
            SvcEventSink = CWmsService::CheckWmsVmReadyState(v4);
            if ( SvcEventSink >= 0 )
            {
              SvcEventSink = CWmsWebService::s_CreateInstance(&hHandle, (struct CWmsWebService **)this + 391);
              if ( SvcEventSink >= 0 )
              {
                SvcEventSink = CWmiEventListener::s_CreateInstance((struct CWmiEventListener **)this + 392);
                if ( SvcEventSink >= 0 )
                {
                  SvcEventSink = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 392) + 8LL))(*((_QWORD *)this + 392));
                  if ( SvcEventSink >= 0 )
                  {
                    for ( i = 0; i < 3; ++i )
                    {
                      SvcEventSink = CreateWmsNamedEvent(
                                       *((_DWORD *)&off_1400EE2C0 + 6 * i + 2),
                                       (&off_1400EE2C0)[3 * i],
                                       (void **)(&off_1400EE2C0)[3 * i + 1]);
                      if ( SvcEventSink < 0 )
                        return (unsigned int)SvcEventSink;
                    }
                    DEBUGMSG(L"CWmsService::StartUp - waiting for web service ready event\n");
                    v6 = WaitForSingleObject(hHandle, 0xFFFFFFFF);
                    SvcEventSink = v6;
                    if ( v6 )
                    {
                      if ( v6 > 0 )
                        SvcEventSink = (unsigned __int16)v6 | 0x80070000;
                      v7 = L"dwWait == ((((NTSTATUS)0x00000000L) ) + 0 )";
                      v8 = 474;
LABEL_24:
                      LOGASSERTHR(
                        L"termsrv\\wms\\src\\devices\\wmssvc\\wmsservice.cpp",
                        v8,
                        L"CWmsService::StartUp",
                        L"CBRAEx",
                        v7,
                        SvcEventSink);
                      if ( IsDebuggerPresent() )
                        DEBUGMSGLEVEL(
                          2u,
                          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                          L"termsrv\\wms\\src\\devices\\wmssvc\\wmsservice.cpp",
                          v8,
                          L"CWmsService::StartUp",
                          L"CBRAEx",
                          v7,
                          SvcEventSink);
                      else
                        DEBUGMSGBOX(
                          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                          L"termsrv\\wms\\src\\devices\\wmssvc\\wmsservice.cpp",
                          v8,
                          L"CWmsService::StartUp",
                          L"CBRAEx",
                          v7,
                          SvcEventSink);
                      return (unsigned int)SvcEventSink;
                    }
                    SvcEventSink = CWmsWebService::GetWebServiceThreadHresult(*((CWmsWebService **)this + 391));
                    if ( SvcEventSink < 0 )
                      return (unsigned int)SvcEventSink;
                    if ( !SetEvent(*((HANDLE *)this + 107)) )
                    {
                      LastError = GetLastError();
                      SvcEventSink = LastError;
                      if ( LastError > 0 )
                        SvcEventSink = (unsigned __int16)LastError | 0x80070000;
                      v7 = L"fResult";
                      v8 = 482;
                      if ( SvcEventSink >= 0 )
                        SvcEventSink = -2147467259;
                      goto LABEL_24;
                    }
                    DEBUGMSG(L"CWmsService::StartUp - signalled service ready event\n");
                    SvcEventSink = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 231) + 8LL))((char *)this + 1848);
                    if ( SvcEventSink >= 0 )
                    {
                      SvcEventSink = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 313) + 8LL))((char *)this + 2504);
                      if ( SvcEventSink >= 0 )
                        return (unsigned int)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 438) + 8LL))((char *)this + 3504);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)SvcEventSink;
}

```

## disassembly

```asm
0x140045b90  push    rbx
0x140045b92  push    rbp
0x140045b93  push    rsi
0x140045b94  push    rdi
0x140045b95  push    r14
0x140045b97  push    r15
0x140045b99  sub     rsp, 48h
0x140045b9d  mov     rax, gs:58h
0x140045ba6  mov     rdi, rcx
0x140045ba9  mov     ecx, 4
0x140045bae  mov     rax, [rax]
0x140045bb1  mov     eax, [rcx+rax]
0x140045bb4  cmp     cs:dword_1400EF628, eax
0x140045bba  jg      loc_140045F17
0x140045bc0  mov     ecx, 1
0x140045bc5  mov     [rsp+78h+hHandle], 0
0x140045bd1  call    ?SetSuppressDeviceInstallUI@@YAJW4ESuppressDeviceInstall@@@Z; SetSuppressDeviceInstallUI(ESuppressDeviceInstall)
0x140045bd6  call    ?s_StartFactories@COutOfProcFactory@@SAHXZ; COutOfProcFactory::s_StartFactories(void)
0x140045bdb  xor     edx, edx; pUnkOuter
0x140045bdd  lea     rax, [rdi+490h]
0x140045be4  lea     r9, _GUID_ca426330_3409_48e1_b77c_87b19091cddf; riid
0x140045beb  mov     [rsp+78h+ppv], rax; ppv
0x140045bf0  lea     rcx, CLSID_DiskProtection; rclsid
0x140045bf7  lea     r8d, [rdx+4]; dwClsContext
0x140045bfb  call    cs:__imp_CoCreateInstance
0x140045c01  mov     ebx, eax
0x140045c03  test    eax, eax
0x140045c05  jns     loc_140045CA6
0x140045c0b  mov     [rsp+78h+var_50], eax; int
0x140045c0f  lea     r15, aChra; "CHRA"
0x140045c16  lea     rsi, aCwmsserviceSta_0; "CWmsService::StartUp"
0x140045c1d  mov     ebp, 1AAh
0x140045c22  lea     rdi, aTermsrvWmsSrcD_6; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140045c29  mov     r9, r15; unsigned __int16 *
0x140045c2c  lea     r14, aHr; "hr"
0x140045c33  mov     r8, rsi; unsigned __int16 *
0x140045c36  mov     edx, ebp; unsigned int
0x140045c38  mov     [rsp+78h+ppv], r14; unsigned __int16 *
0x140045c3d  mov     rcx, rdi; unsigned __int16 *
0x140045c40  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140045c45  call    cs:__imp_IsDebuggerPresent
0x140045c4b  test    eax, eax
0x140045c4d  jz      short loc_140045C7E
0x140045c4f  mov     [rsp+78h+var_40], ebx
0x140045c53  mov     r9d, ebp
0x140045c56  mov     [rsp+78h+var_48], r14
0x140045c5b  mov     qword ptr [rsp+78h+var_50], r15
0x140045c60  mov     r8, rdi
0x140045c63  mov     [rsp+78h+ppv], rsi
0x140045c68  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140045c6f  mov     ecx, 2; unsigned __int8
0x140045c74  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140045c79  jmp     loc_140045F08
0x140045c7e  mov     dword ptr [rsp+78h+var_48], ebx
0x140045c82  mov     r8d, ebp
0x140045c85  mov     qword ptr [rsp+78h+var_50], r14
0x140045c8a  mov     [rsp+78h+ppv], r15
0x140045c8f  mov     r9, rsi
0x140045c92  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140045c99  mov     rdx, rdi
0x140045c9c  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140045ca1  jmp     loc_140045F08
0x140045ca6  lea     rcx, [rdi+4A8h]
0x140045cad  mov     rax, [rcx]
0x140045cb0  mov     rax, [rax+8]
0x140045cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045cb9  mov     ebx, eax
0x140045cbb  test    eax, eax
0x140045cbd  js      loc_140045F08
0x140045cc3  lea     rcx, [rdi+5F0h]
0x140045cca  mov     rax, [rcx]
0x140045ccd  mov     rax, [rax+8]
0x140045cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045cd6  mov     ebx, eax
0x140045cd8  test    eax, eax
0x140045cda  js      loc_140045F08
0x140045ce0  lea     rcx, [rdi+0C48h]
0x140045ce7  mov     rax, [rcx]
0x140045cea  mov     rax, [rax+8]
0x140045cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045cf3  mov     ebx, eax
0x140045cf5  test    eax, eax
0x140045cf7  js      loc_140045F08
0x140045cfd  lea     rcx, [rdi+880h]
0x140045d04  mov     rax, [rcx]
0x140045d07  mov     rax, [rax+8]
0x140045d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045d10  mov     ebx, eax
0x140045d12  test    eax, eax
0x140045d14  js      loc_140045F08
0x140045d1a  mov     rcx, rdi; this
0x140045d1d  call    ?CreateSvcEventSink@CWmsService@@AEAAJXZ; CWmsService::CreateSvcEventSink(void)
0x140045d22  mov     ebx, eax
0x140045d24  test    eax, eax
0x140045d26  js      loc_140045F08
0x140045d2c  call    ?CheckWmsVmReadyState@CWmsService@@AEAAJXZ; CWmsService::CheckWmsVmReadyState(void)
0x140045d31  mov     ebx, eax
0x140045d33  test    eax, eax
0x140045d35  js      loc_140045F08
0x140045d3b  lea     r14, [rdi+0C38h]
0x140045d42  mov     rdx, r14; struct CWmsWebService **
0x140045d45  lea     rcx, [rsp+78h+hHandle]; void **
0x140045d4d  call    ?s_CreateInstance@CWmsWebService@@SAJPEAPEAXPEAPEAV1@@Z; CWmsWebService::s_CreateInstance(void * *,CWmsWebService * *)
0x140045d52  mov     ebx, eax
0x140045d54  test    eax, eax
0x140045d56  js      loc_140045F08
0x140045d5c  lea     rsi, [rdi+0C40h]
0x140045d63  mov     rcx, rsi; struct CWmiEventListener **
0x140045d66  call    ?s_CreateInstance@CWmiEventListener@@SAJPEAPEAV1@@Z; CWmiEventListener::s_CreateInstance(CWmiEventListener * *)
0x140045d6b  mov     ebx, eax
0x140045d6d  test    eax, eax
0x140045d6f  js      loc_140045F08
0x140045d75  mov     rcx, [rsi]
0x140045d78  mov     rax, [rcx]
0x140045d7b  mov     rax, [rax+8]
0x140045d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045d84  mov     ebx, eax
0x140045d86  test    eax, eax
0x140045d88  js      loc_140045F08
0x140045d8e  xor     esi, esi
0x140045d90  lea     r15, off_1400EE2C0; "Global\\WmsSvcReadyEvent"
0x140045d97  lea     rcx, [rsi+rsi*2]
0x140045d9b  mov     r8, [r15+rcx*8+10h]; void **
0x140045da0  mov     rdx, [r15+rcx*8]; lpName
0x140045da4  mov     ecx, [r15+rcx*8+8]; dwDesiredAccess
0x140045da9  call    ?CreateWmsNamedEvent@@YAJKPEBGPEAPEAX@Z; CreateWmsNamedEvent(ulong,ushort const *,void * *)
0x140045dae  mov     ebx, eax
0x140045db0  test    eax, eax
0x140045db2  js      loc_140045F08
0x140045db8  inc     rsi
0x140045dbb  cmp     rsi, 3
0x140045dbf  jb      short loc_140045D97
0x140045dc1  lea     rcx, aCwmsserviceSta_1; "CWmsService::StartUp - waiting for web "...
0x140045dc8  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140045dcd  mov     rcx, [rsp+78h+hHandle]; hHandle
0x140045dd5  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140045dd8  call    cs:__imp_WaitForSingleObject
0x140045dde  mov     ebx, eax
0x140045de0  test    eax, eax
0x140045de2  jz      short loc_140045E61
0x140045de4  jle     short loc_140045DEF
0x140045de6  movzx   ebx, ax
0x140045de9  or      ebx, 80070000h
0x140045def  lea     r15, aDwwaitNtstatus; "dwWait == ((((NTSTATUS)0x00000000L) ) +"...
0x140045df6  mov     r14d, 1DAh
0x140045dfc  lea     rbp, aCbraex; "CBRAEx"
0x140045e03  mov     [rsp+78h+var_50], ebx; int
0x140045e07  lea     rsi, aCwmsserviceSta_0; "CWmsService::StartUp"
0x140045e0e  mov     [rsp+78h+ppv], r15; unsigned __int16 *
0x140045e13  lea     rdi, aTermsrvWmsSrcD_6; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140045e1a  mov     r9, rbp; unsigned __int16 *
0x140045e1d  mov     r8, rsi; unsigned __int16 *
0x140045e20  mov     rcx, rdi; unsigned __int16 *
0x140045e23  mov     edx, r14d; unsigned int
0x140045e26  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140045e2b  call    cs:__imp_IsDebuggerPresent
0x140045e31  test    eax, eax
0x140045e33  jz      short loc_140045E4B
0x140045e35  mov     [rsp+78h+var_40], ebx
0x140045e39  mov     r9d, r14d
0x140045e3c  mov     [rsp+78h+var_48], r15
0x140045e41  mov     qword ptr [rsp+78h+var_50], rbp
0x140045e46  jmp     loc_140045C60
0x140045e4b  mov     dword ptr [rsp+78h+var_48], ebx
0x140045e4f  mov     r8d, r14d
0x140045e52  mov     qword ptr [rsp+78h+var_50], r15
0x140045e57  mov     [rsp+78h+ppv], rbp
0x140045e5c  jmp     loc_140045C8F
0x140045e61  mov     rcx, [r14]; this
0x140045e64  call    ?GetWebServiceThreadHresult@CWmsWebService@@QEAAJXZ; CWmsWebService::GetWebServiceThreadHresult(void)
0x140045e69  mov     ebx, eax
0x140045e6b  test    eax, eax
0x140045e6d  js      loc_140045F08
0x140045e73  mov     rcx, [rdi+358h]; hEvent
0x140045e7a  call    cs:__imp_SetEvent
0x140045e80  test    eax, eax
0x140045e82  jnz     short loc_140045EB5
0x140045e84  call    cs:__imp_GetLastError
0x140045e8a  mov     ebx, eax
0x140045e8c  test    eax, eax
0x140045e8e  jle     short loc_140045E99
0x140045e90  movzx   ebx, ax
0x140045e93  or      ebx, 80070000h
0x140045e99  test    ebx, ebx
0x140045e9b  lea     r15, aFresult; "fResult"
0x140045ea2  mov     eax, 80004005h
0x140045ea7  mov     r14d, 1E2h
0x140045ead  cmovns  ebx, eax
0x140045eb0  jmp     loc_140045DFC
0x140045eb5  lea     rcx, aCwmsserviceSta; "CWmsService::StartUp - signalled servic"...
0x140045ebc  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140045ec1  lea     rcx, [rdi+738h]
0x140045ec8  mov     rax, [rcx]
0x140045ecb  mov     rax, [rax+8]
0x140045ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045ed4  mov     ebx, eax
0x140045ed6  test    eax, eax
0x140045ed8  js      short loc_140045F08
0x140045eda  lea     rcx, [rdi+9C8h]
0x140045ee1  mov     rax, [rcx]
0x140045ee4  mov     rax, [rax+8]
0x140045ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045eed  mov     ebx, eax
0x140045eef  test    eax, eax
0x140045ef1  js      short loc_140045F08
0x140045ef3  lea     rcx, [rdi+0DB0h]
0x140045efa  mov     rax, [rcx]
0x140045efd  mov     rax, [rax+8]
0x140045f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045f06  mov     ebx, eax
0x140045f08  mov     eax, ebx
0x140045f0a  add     rsp, 48h
0x140045f0e  pop     r15
0x140045f10  pop     r14
0x140045f12  pop     rdi
0x140045f13  pop     rsi
0x140045f14  pop     rbp
0x140045f15  pop     rbx
0x140045f16  retn
0x140045f17  lea     rcx, dword_1400EF628
0x140045f1e  call    _Init_thread_header
0x140045f23  cmp     cs:dword_1400EF628, 0FFFFFFFFh
0x140045f2a  jnz     loc_140045BC0
0x140045f30  mov     edx, 100002h
0x140045f35  lea     rax, [rdi+358h]
0x140045f3c  mov     cs:qword_1400EE2D0, rax
0x140045f43  lea     rcx, dword_1400EF628
0x140045f4a  lea     rax, aGlobalWmsselfh; "Global\\WmsSelfHealingSvcReadyEvent"
0x140045f51  mov     cs:dword_1400EE2E0, edx
0x140045f57  mov     cs:qword_1400EE2D8, rax
0x140045f5e  lea     rax, [rdi+360h]
0x140045f65  mov     cs:qword_1400EE2E8, rax
0x140045f6c  lea     rax, aGlobalWmsshell; "Global\\WmsShellStartingEvent"
0x140045f73  mov     cs:qword_1400EE2F0, rax
0x140045f7a  lea     rax, [rdi+368h]
0x140045f81  mov     cs:qword_1400EE300, rax
0x140045f88  mov     cs:dword_1400EE2F8, edx
0x140045f8e  call    _Init_thread_footer
0x140045f93  jmp     loc_140045BC0
```
