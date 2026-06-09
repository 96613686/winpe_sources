# DiscoveryService::s_InitializeClientService(void *)

- ea: `0x1400789e0`
- end: `0x140078cfc`
- name: `?s_InitializeClientService@DiscoveryService@@CAJPEAX@Z`
- size: `796`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1400080f0`

## callees

- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140065368`
- `0x1400789e0`
- `0x14007903c`
- `0x14007a7ac`
- `0x14007e010`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x140078b49`
- `KERNEL32!WaitForSingleObjectEx` at `0x140078b49`
- `KERNEL32!GetLastError` at `0x140078bed`
- `KERNEL32!GetLastError` at `0x140078bed`
- `KERNEL32!IsDebuggerPresent` at `0x140078a75`
- `KERNEL32!IsDebuggerPresent` at `0x140078bc9`
- `KERNEL32!IsDebuggerPresent` at `0x140078c48`
- `KERNEL32!IsDebuggerPresent` at `0x140078a75`
- `KERNEL32!IsDebuggerPresent` at `0x140078bc9`
- `KERNEL32!IsDebuggerPresent` at `0x140078c48`
- `wsdapi!WSDCreateDiscoveryProvider` at `0x140078acd`
- `wsdapi!WSDCreateDiscoveryProvider` at `0x140078acd`

## string_xrefs

- `0x140078a5d`: `termsrv\wms\src\middletier\discovery\service\discoveryservice.cpp`
- `0x140078ba8`: `termsrv\wms\src\middletier\discovery\service\discoveryservice.cpp`
- `0x140078c1d`: `termsrv\wms\src\middletier\discovery\service\discoveryservice.cpp`
- `0x1400789f9`: `DiscoveryService::s_InitializeClientService - Waiting for LanmanServer to start\n`
- `0x140078a46`: `DiscoveryService::s_InitializeClientService`
- `0x140078b9e`: `DiscoveryService::s_InitializeClientService`
- `0x140078c10`: `DiscoveryService::s_InitializeClientService`
- `0x140078a39`: `!fLanmanServerServiceDisabled`
- `0x140078b2f`: `DiscoveryService::s_InitializeClientService - Attach failed, retrying\n`

## pseudocode

```c
__int64 __fastcall DiscoveryService::s_InitializeClientService(void *a1)
{
  int started; // ebx
  const unsigned __int16 *v3; // r15
  unsigned int v4; // r14d
  struct CClientNotificationSink **v5; // rdx
  struct IWSDiscoveryProvider *v6; // rcx
  unsigned int v7; // r15d
  int v8; // edi
  DWORD v9; // eax
  int v10; // eax
  signed int LastError; // eax
  int v13; // [rsp+88h] [rbp+10h] BYREF

  v13 = 0;
  DEBUGMSG(L"DiscoveryService::s_InitializeClientService - Waiting for LanmanServer to start\n");
  started = ConditionalWaitForServiceStartUsingEventToStop(L"LanmanServer", a1, &v13);
  if ( started < 0 )
    goto LABEL_30;
  if ( v13 )
  {
    started = -2147418113;
    v3 = L"!fLanmanServerServiceDisabled";
    v4 = 271;
LABEL_4:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
      v4,
      L"DiscoveryService::s_InitializeClientService",
      L"CBRAEx",
      v3,
      started);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
        v4,
        L"DiscoveryService::s_InitializeClientService",
        L"CBRAEx",
        v3,
        started);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
        v4,
        L"DiscoveryService::s_InitializeClientService",
        L"CBRAEx",
        v3,
        started);
  }
  else
  {
    started = WSDCreateDiscoveryProvider(0, &DiscoveryService::s_pProvider);
    if ( started >= 0 )
    {
      started = CreateClientNotificationSink(v6, v5);
      if ( started < 0 )
        goto LABEL_30;
      v8 = 120;
      started = (**(__int64 (__fastcall ***)(struct CClientNotificationSink *, GUID *, struct IWSDiscoveryProviderNotify **))DiscoveryService::s_pSink)(
                  DiscoveryService::s_pSink,
                  &GUID_73ee3ced_b6e6_4329_a546_3e8ad46563d2,
                  &DiscoveryService::s_pCallbackObject);
      if ( started < 0 )
        goto LABEL_30;
      do
      {
        if ( started < 0 )
        {
          if ( !--v8 )
          {
            started = -2147023436;
            v3 = L"cRetries > 0";
            v4 = 294;
            goto LABEL_4;
          }
          DEBUGMSG(L"DiscoveryService::s_InitializeClientService - Attach failed, retrying\n");
          v9 = WaitForSingleObjectEx(a1, 0x3E8u, 1);
          if ( !v9 )
          {
            started = -2147467260;
            goto LABEL_30;
          }
          if ( v9 != 258 )
          {
            LastError = GetLastError();
            started = LastError;
            if ( LastError > 0 )
              started = (unsigned __int16)LastError | 0x80070000;
            if ( started >= 0 )
              started = -2147467259;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
              0x12Au,
              L"DiscoveryService::s_InitializeClientService",
              L"CBRAEx",
              L"dwRet == 258L",
              started);
            if ( IsDebuggerPresent() )
              DEBUGMSGLEVEL(
                2u,
                L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
                298,
                L"DiscoveryService::s_InitializeClientService",
                L"CBRAEx",
                L"dwRet == 258L",
                started);
            else
              DEBUGMSGBOX(
                L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
                298,
                L"DiscoveryService::s_InitializeClientService",
                L"CBRAEx",
                L"dwRet == 258L",
                started);
            goto LABEL_30;
          }
        }
        v10 = ((__int64 (__fastcall *)(IWSDiscoveryProvider *, struct IWSDiscoveryProviderNotify *))DiscoveryService::s_pProvider->lpVtbl->Attach)(
                DiscoveryService::s_pProvider,
                DiscoveryService::s_pCallbackObject);
        started = v10;
      }
      while ( v10 == -2147014847 );
      if ( v10 >= 0 )
        return (unsigned int)started;
      v7 = 303;
    }
    else
    {
      v7 = 275;
    }
    LOGASSERTHR(
      L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
      v7,
      L"DiscoveryService::s_InitializeClientService",
      L"CHRA",
      L"hr",
      started);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
        v7,
        L"DiscoveryService::s_InitializeClientService",
        L"CHRA",
        L"hr",
        started);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\middletier\\discovery\\service\\discoveryservice.cpp",
        v7,
        L"DiscoveryService::s_InitializeClientService",
        L"CHRA",
        L"hr",
        started);
  }
LABEL_30:
  DiscoveryService::s_UnInitializeClientService();
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1400789e0  mov     rax, rsp
0x1400789e3  push    rbx
0x1400789e4  push    rbp
0x1400789e5  push    rsi
0x1400789e6  push    rdi
0x1400789e7  push    r14
0x1400789e9  push    r15
0x1400789eb  sub     rsp, 48h
0x1400789ef  mov     rsi, rcx
0x1400789f2  mov     dword ptr [rax+10h], 0
0x1400789f9  lea     rcx, aDiscoveryservi; "DiscoveryService::s_InitializeClientSer"...
0x140078a00  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140078a05  lea     r8, [rsp+78h+arg_8]; int *
0x140078a0d  mov     rdx, rsi; void *
0x140078a10  lea     rcx, aLanmanserver; "LanmanServer"
0x140078a17  call    ?ConditionalWaitForServiceStartUsingEventToStop@@YAJPEBGPEAXPEAH@Z; ConditionalWaitForServiceStartUsingEventToStop(ushort const *,void *,int *)
0x140078a1c  mov     ebx, eax
0x140078a1e  test    eax, eax
0x140078a20  js      loc_140078CE8
0x140078a26  cmp     [rsp+78h+arg_8], 0
0x140078a2e  jz      loc_140078AC4
0x140078a34  mov     ebx, 8000FFFFh
0x140078a39  lea     r15, aFlanmanservers; "!fLanmanServerServiceDisabled"
0x140078a40  mov     r14d, 10Fh
0x140078a46  lea     rsi, aDiscoveryservi_5; "DiscoveryService::s_InitializeClientSer"...
0x140078a4d  mov     [rsp+78h+var_50], ebx; int
0x140078a51  lea     rbp, aCbraex; "CBRAEx"
0x140078a58  mov     [rsp+78h+var_58], r15; unsigned __int16 *
0x140078a5d  lea     rdi, aTermsrvWmsSrcM_1; "termsrv\\wms\\src\\middletier\\discover"...
0x140078a64  mov     r8, rsi; unsigned __int16 *
0x140078a67  mov     r9, rbp; unsigned __int16 *
0x140078a6a  mov     rcx, rdi; unsigned __int16 *
0x140078a6d  mov     edx, r14d; unsigned int
0x140078a70  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140078a75  call    cs:__imp_IsDebuggerPresent
0x140078a7b  test    eax, eax
0x140078a7d  jz      short loc_140078AAE
0x140078a7f  mov     [rsp+78h+var_40], ebx
0x140078a83  mov     r9d, r14d
0x140078a86  mov     [rsp+78h+var_48], r15
0x140078a8b  mov     qword ptr [rsp+78h+var_50], rbp
0x140078a90  mov     r8, rdi
0x140078a93  mov     [rsp+78h+var_58], rsi
0x140078a98  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140078a9f  mov     ecx, 2; unsigned __int8
0x140078aa4  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140078aa9  jmp     loc_140078CE8
0x140078aae  mov     dword ptr [rsp+78h+var_48], ebx
0x140078ab2  mov     r8d, r14d
0x140078ab5  mov     qword ptr [rsp+78h+var_50], r15
0x140078aba  mov     [rsp+78h+var_58], rbp
0x140078abf  jmp     loc_140078CD6
0x140078ac4  lea     rdx, ?s_pProvider@DiscoveryService@@0PEAUIWSDiscoveryProvider@@EA; ppProvider
0x140078acb  xor     ecx, ecx; pContext
0x140078acd  call    cs:__imp_WSDCreateDiscoveryProvider
0x140078ad3  mov     ebx, eax
0x140078ad5  test    eax, eax
0x140078ad7  jns     short loc_140078AE4
0x140078ad9  mov     r15d, 113h
0x140078adf  jmp     loc_140078B93
0x140078ae4  call    ?CreateClientNotificationSink@@YAJPEAUIWSDiscoveryProvider@@PEAPEAVCClientNotificationSink@@@Z; CreateClientNotificationSink(IWSDiscoveryProvider *,CClientNotificationSink * *)
0x140078ae9  mov     ebx, eax
0x140078aeb  test    eax, eax
0x140078aed  js      loc_140078CE8
0x140078af3  mov     rcx, cs:?s_pSink@DiscoveryService@@0PEAVCClientNotificationSink@@EA; CClientNotificationSink * DiscoveryService::s_pSink
0x140078afa  lea     r8, ?s_pCallbackObject@DiscoveryService@@0PEAUIWSDiscoveryProviderNotify@@EA; IWSDiscoveryProviderNotify * DiscoveryService::s_pCallbackObject
0x140078b01  lea     rdx, _GUID_73ee3ced_b6e6_4329_a546_3e8ad46563d2
0x140078b08  mov     edi, 78h ; 'x'
0x140078b0d  mov     rax, [rcx]
0x140078b10  mov     rax, [rax]
0x140078b13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140078b18  mov     ebx, eax
0x140078b1a  test    eax, eax
0x140078b1c  js      loc_140078CE8
0x140078b22  test    ebx, ebx
0x140078b24  jns     short loc_140078B62
0x140078b26  sub     edi, 1
0x140078b29  jz      loc_140078CAE
0x140078b2f  lea     rcx, aDiscoveryservi_3; "DiscoveryService::s_InitializeClientSer"...
0x140078b36  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140078b3b  mov     edx, 3E8h; dwMilliseconds
0x140078b40  mov     r8d, 1; bAlertable
0x140078b46  mov     rcx, rsi; hHandle
0x140078b49  call    cs:__imp_WaitForSingleObjectEx
0x140078b4f  test    eax, eax
0x140078b51  jz      loc_140078CA7
0x140078b57  cmp     eax, 102h
0x140078b5c  jnz     loc_140078BED
0x140078b62  mov     rcx, cs:?s_pProvider@DiscoveryService@@0PEAUIWSDiscoveryProvider@@EA; IWSDiscoveryProvider * DiscoveryService::s_pProvider
0x140078b69  mov     rdx, cs:?s_pCallbackObject@DiscoveryService@@0PEAUIWSDiscoveryProviderNotify@@EA; IWSDiscoveryProviderNotify * DiscoveryService::s_pCallbackObject
0x140078b70  mov     rax, [rcx]
0x140078b73  mov     rax, [rax+20h]
0x140078b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140078b7c  mov     ebx, eax
0x140078b7e  cmp     eax, 80072741h
0x140078b83  jz      short loc_140078B22
0x140078b85  test    eax, eax
0x140078b87  jns     loc_140078CED
0x140078b8d  mov     r15d, 12Fh
0x140078b93  lea     r14, aChra; "CHRA"
0x140078b9a  mov     [rsp+78h+var_50], ebx; int
0x140078b9e  lea     rsi, aDiscoveryservi_5; "DiscoveryService::s_InitializeClientSer"...
0x140078ba5  mov     r9, r14; unsigned __int16 *
0x140078ba8  lea     rdi, aTermsrvWmsSrcM_1; "termsrv\\wms\\src\\middletier\\discover"...
0x140078baf  mov     r8, rsi; unsigned __int16 *
0x140078bb2  lea     rbp, aHr; "hr"
0x140078bb9  mov     rcx, rdi; unsigned __int16 *
0x140078bbc  mov     edx, r15d; unsigned int
0x140078bbf  mov     [rsp+78h+var_58], rbp; unsigned __int16 *
0x140078bc4  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140078bc9  call    cs:__imp_IsDebuggerPresent
0x140078bcf  test    eax, eax
0x140078bd1  jz      loc_140078CC5
0x140078bd7  mov     [rsp+78h+var_40], ebx
0x140078bdb  mov     r9d, r15d
0x140078bde  mov     [rsp+78h+var_48], rbp
0x140078be3  mov     qword ptr [rsp+78h+var_50], r14
0x140078be8  jmp     loc_140078A90
0x140078bed  call    cs:__imp_GetLastError
0x140078bf3  mov     ebx, eax
0x140078bf5  test    eax, eax
0x140078bf7  jle     short loc_140078C02
0x140078bf9  movzx   ebx, ax
0x140078bfc  or      ebx, 80070000h
0x140078c02  mov     eax, 80004005h
0x140078c07  lea     rbp, aCbraex; "CBRAEx"
0x140078c0e  test    ebx, ebx
0x140078c10  lea     rsi, aDiscoveryservi_5; "DiscoveryService::s_InitializeClientSer"...
0x140078c17  mov     r14d, 12Ah
0x140078c1d  lea     rdi, aTermsrvWmsSrcM_1; "termsrv\\wms\\src\\middletier\\discover"...
0x140078c24  cmovns  ebx, eax
0x140078c27  lea     r15, aDwret258l; "dwRet == 258L"
0x140078c2e  mov     [rsp+78h+var_50], ebx; int
0x140078c32  mov     r9, rbp; unsigned __int16 *
0x140078c35  mov     r8, rsi; unsigned __int16 *
0x140078c38  mov     [rsp+78h+var_58], r15; unsigned __int16 *
0x140078c3d  mov     edx, r14d; unsigned int
0x140078c40  mov     rcx, rdi; unsigned __int16 *
0x140078c43  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140078c48  call    cs:__imp_IsDebuggerPresent
0x140078c4e  test    eax, eax
0x140078c50  jz      short loc_140078C7E
0x140078c52  mov     [rsp+78h+var_40], ebx
0x140078c56  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140078c5d  mov     [rsp+78h+var_48], r15
0x140078c62  mov     r9d, r14d
0x140078c65  mov     qword ptr [rsp+78h+var_50], rbp
0x140078c6a  mov     r8, rdi
0x140078c6d  mov     ecx, 2; unsigned __int8
0x140078c72  mov     [rsp+78h+var_58], rsi
0x140078c77  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140078c7c  jmp     short loc_140078CA1
0x140078c7e  mov     dword ptr [rsp+78h+var_48], ebx
0x140078c82  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140078c89  mov     qword ptr [rsp+78h+var_50], r15
0x140078c8e  mov     r9, rsi
0x140078c91  mov     r8d, r14d
0x140078c94  mov     [rsp+78h+var_58], rbp
0x140078c99  mov     rdx, rdi
0x140078c9c  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140078ca1  test    ebx, ebx
0x140078ca3  jns     short loc_140078CED
0x140078ca5  jmp     short loc_140078CE8
0x140078ca7  mov     ebx, 80004004h
0x140078cac  jmp     short loc_140078CE8
0x140078cae  mov     ebx, 800705B4h
0x140078cb3  lea     r15, aCretries0; "cRetries > 0"
0x140078cba  mov     r14d, 126h
0x140078cc0  jmp     loc_140078A46
0x140078cc5  mov     dword ptr [rsp+78h+var_48], ebx
0x140078cc9  mov     r8d, r15d
0x140078ccc  mov     qword ptr [rsp+78h+var_50], rbp
0x140078cd1  mov     [rsp+78h+var_58], r14
0x140078cd6  mov     r9, rsi
0x140078cd9  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140078ce0  mov     rdx, rdi
0x140078ce3  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140078ce8  call    ?s_UnInitializeClientService@DiscoveryService@@CAXXZ; DiscoveryService::s_UnInitializeClientService(void)
0x140078ced  mov     eax, ebx
0x140078cef  add     rsp, 48h
0x140078cf3  pop     r15
0x140078cf5  pop     r14
0x140078cf7  pop     rdi
0x140078cf8  pop     rsi
0x140078cf9  pop     rbp
0x140078cfa  pop     rbx
0x140078cfb  retn
```
