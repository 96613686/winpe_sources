# CWmiEventListener::ThreadProc(void)

- ea: `0x1400398e0`
- end: `0x140039dda`
- name: `?ThreadProc@CWmiEventListener@@MEAAJXZ`
- size: `1274`
- prototype: `__int64 __fastcall(CWmiEventListener *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400398e0`
- `0x14003a768`
- `0x14003aa0c`
- `0x14003ab94`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`
- `0x14005c408`
- `0x14007e010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x140039bfb`
- `KERNEL32!WaitForSingleObject` at `0x140039bfb`
- `KERNEL32!GetLastError` at `0x140039c09`
- `KERNEL32!GetLastError` at `0x140039c09`
- `KERNEL32!IsDebuggerPresent` at `0x1400399bb`
- `KERNEL32!IsDebuggerPresent` at `0x140039b42`
- `KERNEL32!IsDebuggerPresent` at `0x140039c56`
- `KERNEL32!IsDebuggerPresent` at `0x140039cbd`
- `KERNEL32!IsDebuggerPresent` at `0x1400399bb`
- `KERNEL32!IsDebuggerPresent` at `0x140039b42`
- `KERNEL32!IsDebuggerPresent` at `0x140039c56`
- `KERNEL32!IsDebuggerPresent` at `0x140039cbd`
- `ole32!CoUninitialize` at `0x140039db0`
- `ole32!CoUninitialize` at `0x140039db0`
- `ole32!CoInitializeEx` at `0x14003996e`
- `ole32!CoInitializeEx` at `0x14003996e`
- `ole32!CoCreateInstance` at `0x140039a38`
- `ole32!CoCreateInstance` at `0x140039aec`
- `ole32!CoCreateInstance` at `0x140039a38`
- `ole32!CoCreateInstance` at `0x140039aec`
- `ole32!CoSetProxyBlanket` at `0x140039ab8`
- `ole32!CoSetProxyBlanket` at `0x140039ab8`

## string_xrefs

- `0x140039944`: `CWmiEventListener::ThreadProc - Entered.\n`
- `0x140039985`: `CWmiEventListener::ThreadProc`
- `0x140039af2`: `CWmiEventListener::ThreadProc`
- `0x140039db8`: `CWmiEventListener::ThreadProc - Exiting, returning 0x%08x.\n`

## pseudocode

```c
__int64 __fastcall CWmiEventListener::ThreadProc(CWmiEventListener *this)
{
  int v2; // r12d
  int Instance; // ebx
  unsigned int v4; // r13d
  const unsigned __int16 *v5; // r9
  unsigned __int64 i; // r14
  const unsigned __int16 *v7; // r9
  signed int LastError; // eax
  __int64 v9; // r14
  CWmiEventSink *v10; // r15
  RPC_AUTH_IDENTITY_HANDLE pAuthInfo; // [rsp+30h] [rbp-89h]
  DWORD dwCapabilities[2]; // [rsp+38h] [rbp-81h]
  IUnknown *pProxy; // [rsp+50h] [rbp-69h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-61h] BYREF
  LPVOID v16; // [rsp+60h] [rbp-59h] BYREF
  CWmiEventSink *v17; // [rsp+70h] [rbp-49h] BYREF
  int v18; // [rsp+78h] [rbp-41h]
  _QWORD v19[2]; // [rsp+80h] [rbp-39h]
  int v20; // [rsp+90h] [rbp-29h]
  const wchar_t *v21; // [rsp+98h] [rbp-21h]
  __int64 v22; // [rsp+A0h] [rbp-19h]
  int v23; // [rsp+A8h] [rbp-11h]
  const wchar_t *v24; // [rsp+B0h] [rbp-9h]
  __int64 v25; // [rsp+B8h] [rbp-1h]
  int v26; // [rsp+C0h] [rbp+7h]
  const wchar_t *v27; // [rsp+C8h] [rbp+Fh]

  v23 = 2;
  ppv = 0;
  v19[0] = L"SELECT * FROM __InstanceCreationEvent WITHIN 1 WHERE TargetInstance ISA 'Win32_UserAccount' and TargetInstanc"
            "e.LocalAccount = true";
  pProxy = 0;
  v21 = L"SELECT * FROM __InstanceModificationEvent WITHIN 1 WHERE TargetInstance ISA 'Win32_UserAccount' and TargetInstan"
         "ce.LocalAccount = true";
  v2 = 1;
  v16 = 0;
  v24 = L"SELECT * FROM __InstanceDeletionEvent WITHIN 1 WHERE TargetInstance ISA 'Win32_UserAccount' and TargetInstance.L"
         "ocalAccount = true";
  v17 = 0;
  v27 = L"SELECT * FROM __InstanceCreationEvent WITHIN 1 WHERE TargetInstance ISA 'Win32_NTLogEvent' AND (TargetInstance.E"
         "ventCode=4732 OR TargetInstance.EventCode=4733)";
  v18 = 0;
  v19[1] = 0;
  v20 = 1;
  v22 = 0;
  v25 = 0;
  v26 = 3;
  DEBUGMSG(L"CWmiEventListener::ThreadProc - Entered.\n");
  Instance = CoInitializeEx(0, 0);
  if ( Instance < 0 )
  {
    v2 = 0;
    v4 = 130;
    goto LABEL_3;
  }
  Instance = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &GUID_dc12a687_737f_11cf_884d_00aa004b2e24, &ppv);
  if ( Instance < 0 )
  {
    v4 = 139;
    goto LABEL_3;
  }
  Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **))(*(_QWORD *)ppv + 24LL))(
               ppv,
               *((_QWORD *)this + 41),
               0,
               0,
               0,
               0,
               0,
               0,
               &pProxy);
  if ( Instance < 0 )
  {
    v4 = 142;
    goto LABEL_3;
  }
  Instance = CoSetProxyBlanket(pProxy, 0xAu, 0, 0, 3u, 3u, 0, 0);
  if ( Instance < 0 )
  {
    v4 = 152;
    goto LABEL_3;
  }
  Instance = CoCreateInstance(&CLSID_UnsecuredApartment, 0, 4u, &GUID_1cfaba8c_1523_11d1_ad79_00c04fd8fdff, &v16);
  if ( Instance < 0 )
  {
    v4 = 155;
LABEL_3:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmieventlistener.cpp",
      v4,
      L"CWmiEventListener::ThreadProc",
      L"CHRA",
      L"hr",
      Instance);
    if ( IsDebuggerPresent() )
    {
      dwCapabilities[0] = Instance;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmieventlistener.cpp",
        v4,
        L"CWmiEventListener::ThreadProc",
        L"CHRA",
        L"hr",
        *(_QWORD *)dwCapabilities);
    }
    else
    {
      LODWORD(pAuthInfo) = Instance;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmieventlistener.cpp",
        v4,
        L"CWmiEventListener::ThreadProc",
        L"CHRA",
        L"hr",
        pAuthInfo);
    }
    goto LABEL_41;
  }
  for ( i = 0; i < 4; ++i )
  {
    if ( *(&v17 + 3 * i) )
    {
      LOGASSERT(
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmieventlistener.cpp",
        0xA3u,
        L"CWmiEventListener::ThreadProc",
        v5,
        L"rgWmiEventParams[i].pEventSink == NULL");
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmieventlistener.cpp",
          163,
          L"CWmiEventListener::ThreadProc",
          L"ASSERT",
          L"rgWmiEventParams[i].pEventSink == NULL");
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmieventlistener.cpp",
          163,
          L"CWmiEventListener::ThreadProc",
          L"ASSERT",
          L"rgWmiEventParams[i].pEventSink == NULL");
    }
    Instance = CWmiEventSink::s_CreateInstance(&v17 + 3 * i);
    if ( Instance < 0 )
      goto LABEL_40;
    Instance = CWmiEventSink::RegisterWmiEvent(*(&v17 + 3 * i), pProxy, v16, v19[3 * i], v19[3 * i]);
    v2 = 1;
    if ( Instance < 0 )
      goto LABEL_41;
  }
  if ( !WaitForSingleObject(*((HANDLE *)this + 3), 0xFFFFFFFF) )
  {
    v9 = 0;
    while ( 1 )
    {
      v10 = *(&v17 + 3 * v9);
      if ( !v10 )
      {
        LOGASSERT(
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmieventlistener.cpp",
          0xC5u,
          L"CWmiEventListener::ThreadProc",
          v7,
          L"rgWmiEventParams[i].pEventSink != NULL");
        if ( IsDebuggerPresent() )
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\wmieventlistener.cpp",
            197,
            L"CWmiEventListener::ThreadProc",
            L"ASSERT",
            L"rgWmiEventParams[i].pEventSink != NULL");
        else
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\wmieventlistener.cpp",
            197,
            L"CWmiEventListener::ThreadProc",
            L"ASSERT",
            L"rgWmiEventParams[i].pEventSink != NULL");
      }
      Instance = CWmiEventSink::UnregisterWmiEvent(v10, (struct IWbemServices *)pProxy);
      if ( Instance < 0 )
        break;
      if ( v10 )
      {
        (*(void (__fastcall **)(CWmiEventSink *))(*(_QWORD *)v10 + 16LL))(v10);
        *(&v17 + 3 * v9) = 0;
      }
      v2 = 1;
      if ( (unsigned __int64)++v9 >= 4 )
        goto LABEL_41;
    }
LABEL_40:
    v2 = 1;
    goto LABEL_41;
  }
  LastError = GetLastError();
  Instance = LastError;
  if ( LastError > 0 )
    Instance = (unsigned __int16)LastError | 0x80070000;
  if ( Instance >= 0 )
    Instance = -2147467259;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\devices\\wmssvc\\wmieventlistener.cpp",
    0xBBu,
    L"CWmiEventListener::ThreadProc",
    L"CBRAEx",
    L"0",
    Instance);
  if ( IsDebuggerPresent() )
  {
    dwCapabilities[0] = Instance;
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmieventlistener.cpp",
      187,
      L"CWmiEventListener::ThreadProc",
      L"CBRAEx",
      L"0",
      *(_QWORD *)dwCapabilities);
  }
  else
  {
    LODWORD(pAuthInfo) = Instance;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmieventlistener.cpp",
      187,
      L"CWmiEventListener::ThreadProc",
      L"CBRAEx",
      L"0",
      pAuthInfo);
  }
LABEL_41:
  if ( pProxy )
  {
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    pProxy = 0;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v2 )
    CoUninitialize();
  DEBUGMSG(L"CWmiEventListener::ThreadProc - Exiting, returning 0x%08x.\n", (unsigned int)Instance);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1400398e0  push    rbp
0x1400398e2  push    rbx
0x1400398e3  push    rsi
0x1400398e4  push    rdi
0x1400398e5  push    r12
0x1400398e7  push    r13
0x1400398e9  push    r14
0x1400398eb  push    r15
0x1400398ed  lea     rbp, [rsp-1Fh]
0x1400398f2  sub     rsp, 0D8h
0x1400398f9  xor     edi, edi
0x1400398fb  mov     [rbp+57h+var_68], 2
0x140039902  lea     rax, aSelectFromInst_0; "SELECT * FROM __InstanceCreationEvent W"...
0x140039909  mov     [rbp+57h+var_B8], rdi
0x14003990d  mov     [rbp+57h+var_90], rax
0x140039911  mov     r13, rcx
0x140039914  lea     rax, aSelectFromInst_2; "SELECT * FROM __InstanceModificationEve"...
0x14003991b  mov     [rbp+57h+pProxy], rdi
0x14003991f  mov     [rbp+57h+var_78], rax
0x140039923  lea     r12d, [rdi+1]
0x140039927  lea     rax, aSelectFromInst_1; "SELECT * FROM __InstanceDeletionEvent W"...
0x14003992e  mov     [rbp+57h+var_B0], rdi
0x140039932  mov     [rbp+57h+var_60], rax
0x140039936  lea     esi, [rdi+3]
0x140039939  lea     rax, aSelectFromInst; "SELECT * FROM __InstanceCreationEvent W"...
0x140039940  mov     [rbp+57h+var_A0], rdi
0x140039944  lea     rcx, aCwmieventliste_5; "CWmiEventListener::ThreadProc - Entered"...
0x14003994b  mov     [rbp+57h+var_48], rax
0x14003994f  mov     [rbp+57h+var_98], edi
0x140039952  mov     [rbp+57h+var_88], rdi
0x140039956  mov     [rbp+57h+var_80], r12d
0x14003995a  mov     [rbp+57h+var_70], rdi
0x14003995e  mov     [rbp+57h+var_58], rdi
0x140039962  mov     [rbp+57h+var_50], esi
0x140039965  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14003996a  xor     edx, edx; dwCoInit
0x14003996c  xor     ecx, ecx; pvReserved
0x14003996e  call    cs:__imp_CoInitializeEx
0x140039974  mov     ebx, eax
0x140039976  test    eax, eax
0x140039978  jns     loc_140039A1C
0x14003997e  mov     r12d, edi
0x140039981  lea     r13d, [rsi+7Fh]
0x140039985  lea     rsi, aCwmieventliste_3; "CWmiEventListener::ThreadProc"
0x14003998c  lea     r15, aChra; "CHRA"
0x140039993  mov     [rsp+110h+dwImpLevel], ebx; int
0x140039997  lea     rdi, aTermsrvWmsSrcD_13; "termsrv\\wms\\src\\devices\\wmssvc\\wmi"...
0x14003999e  mov     r9, r15; unsigned __int16 *
0x1400399a1  lea     r14, aHr; "hr"
0x1400399a8  mov     rcx, rdi; unsigned __int16 *
0x1400399ab  mov     r8, rsi; unsigned __int16 *
0x1400399ae  mov     [rsp+110h+ppv], r14; unsigned __int16 *
0x1400399b3  mov     edx, r13d; unsigned int
0x1400399b6  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400399bb  call    cs:__imp_IsDebuggerPresent
0x1400399c1  test    eax, eax
0x1400399c3  jz      short loc_1400399F4
0x1400399c5  mov     [rsp+110h+dwCapabilities], ebx
0x1400399c9  mov     r9d, r13d
0x1400399cc  mov     [rsp+110h+pAuthInfo], r14
0x1400399d1  mov     qword ptr [rsp+110h+dwImpLevel], r15
0x1400399d6  mov     r8, rdi
0x1400399d9  mov     [rsp+110h+ppv], rsi
0x1400399de  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400399e5  mov     ecx, 2; unsigned __int8
0x1400399ea  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400399ef  jmp     loc_140039D5E
0x1400399f4  mov     dword ptr [rsp+110h+pAuthInfo], ebx
0x1400399f8  mov     r8d, r13d
0x1400399fb  mov     qword ptr [rsp+110h+dwImpLevel], r14
0x140039a00  mov     [rsp+110h+ppv], r15
0x140039a05  mov     r9, rsi
0x140039a08  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140039a0f  mov     rdx, rdi
0x140039a12  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140039a17  jmp     loc_140039D5E
0x140039a1c  lea     rax, [rbp+57h+var_B8]
0x140039a20  mov     r8d, r12d; dwClsContext
0x140039a23  lea     r9, _GUID_dc12a687_737f_11cf_884d_00aa004b2e24; riid
0x140039a2a  mov     [rsp+110h+ppv], rax; ppv
0x140039a2f  xor     edx, edx; pUnkOuter
0x140039a31  lea     rcx, CLSID_WbemLocator; rclsid
0x140039a38  call    cs:__imp_CoCreateInstance
0x140039a3e  mov     ebx, eax
0x140039a40  test    eax, eax
0x140039a42  jns     short loc_140039A4F
0x140039a44  mov     r13d, 8Bh
0x140039a4a  jmp     loc_140039985
0x140039a4f  mov     rcx, [rbp+57h+var_B8]
0x140039a53  lea     rdx, [rbp+57h+pProxy]
0x140039a57  mov     [rsp+110h+var_D0], rdx
0x140039a5c  xor     r9d, r9d
0x140039a5f  mov     rdx, [r13+148h]
0x140039a66  xor     r8d, r8d
0x140039a69  mov     qword ptr [rsp+110h+dwCapabilities], rdi
0x140039a6e  mov     rax, [rcx]
0x140039a71  mov     [rsp+110h+pAuthInfo], rdi
0x140039a76  mov     [rsp+110h+dwImpLevel], edi
0x140039a7a  mov     [rsp+110h+ppv], rdi
0x140039a7f  mov     rax, [rax+18h]
0x140039a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039a88  mov     ebx, eax
0x140039a8a  test    eax, eax
0x140039a8c  jns     short loc_140039A99
0x140039a8e  mov     r13d, 8Eh
0x140039a94  jmp     loc_140039985
0x140039a99  mov     rcx, [rbp+57h+pProxy]; pProxy
0x140039a9d  xor     r9d, r9d; pServerPrincName
0x140039aa0  mov     [rsp+110h+dwCapabilities], edi; dwCapabilities
0x140039aa4  xor     r8d, r8d; dwAuthzSvc
0x140039aa7  mov     [rsp+110h+pAuthInfo], rdi; pAuthInfo
0x140039aac  mov     [rsp+110h+dwImpLevel], esi; dwImpLevel
0x140039ab0  lea     edx, [r9+0Ah]; dwAuthnSvc
0x140039ab4  mov     dword ptr [rsp+110h+ppv], esi; dwAuthnLevel
0x140039ab8  call    cs:__imp_CoSetProxyBlanket
0x140039abe  mov     ebx, eax
0x140039ac0  test    eax, eax
0x140039ac2  jns     short loc_140039ACF
0x140039ac4  mov     r13d, 98h
0x140039aca  jmp     loc_140039985
0x140039acf  xor     edx, edx; pUnkOuter
0x140039ad1  lea     rax, [rbp+57h+var_B0]
0x140039ad5  lea     r9, _GUID_1cfaba8c_1523_11d1_ad79_00c04fd8fdff; riid
0x140039adc  mov     [rsp+110h+ppv], rax; ppv
0x140039ae1  lea     rcx, CLSID_UnsecuredApartment; rclsid
0x140039ae8  lea     r8d, [rdx+4]; dwClsContext
0x140039aec  call    cs:__imp_CoCreateInstance
0x140039af2  lea     rsi, aCwmieventliste_3; "CWmiEventListener::ThreadProc"
0x140039af9  mov     ebx, eax
0x140039afb  test    eax, eax
0x140039afd  jns     short loc_140039B0A
0x140039aff  mov     r13d, 9Bh
0x140039b05  jmp     loc_14003998C
0x140039b0a  mov     r14, rdi
0x140039b0d  lea     rbx, aRgwmieventpara_0; "rgWmiEventParams[i].pEventSink == NULL"
0x140039b14  lea     rdi, aTermsrvWmsSrcD_13; "termsrv\\wms\\src\\devices\\wmssvc\\wmi"...
0x140039b1b  lea     r12, [r14+r14*2]
0x140039b1f  lea     r15, [rbp+57h+var_A0]
0x140039b23  lea     r15, [r15+r12*8]
0x140039b27  cmp     qword ptr [r15], 0
0x140039b2b  jz      short loc_140039BA0
0x140039b2d  mov     r8, rsi; unsigned __int16 *
0x140039b30  mov     [rsp+110h+ppv], rbx; unsigned __int16 *
0x140039b35  mov     edx, 0A3h; unsigned int
0x140039b3a  mov     rcx, rdi; unsigned __int16 *
0x140039b3d  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140039b42  call    cs:__imp_IsDebuggerPresent
0x140039b48  test    eax, eax
0x140039b4a  lea     rax, aAssert; "ASSERT"
0x140039b51  jz      short loc_140039B7E
0x140039b53  mov     [rsp+110h+pAuthInfo], rbx
0x140039b58  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140039b5f  mov     qword ptr [rsp+110h+dwImpLevel], rax
0x140039b64  mov     r9d, 0A3h
0x140039b6a  mov     r8, rdi
0x140039b6d  mov     [rsp+110h+ppv], rsi
0x140039b72  mov     ecx, 2; unsigned __int8
0x140039b77  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140039b7c  jmp     short loc_140039BA0
0x140039b7e  mov     qword ptr [rsp+110h+dwImpLevel], rbx
0x140039b83  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140039b8a  mov     r9, rsi
0x140039b8d  mov     [rsp+110h+ppv], rax
0x140039b92  mov     r8d, 0A3h
0x140039b98  mov     rdx, rdi
0x140039b9b  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140039ba0  mov     rcx, r15; struct CWmiEventSink **
0x140039ba3  call    ?s_CreateInstance@CWmiEventSink@@SAJPEAPEAV1@@Z; CWmiEventSink::s_CreateInstance(CWmiEventSink * *)
0x140039ba8  mov     ebx, eax
0x140039baa  test    eax, eax
0x140039bac  js      loc_140039D58
0x140039bb2  mov     eax, [rbp+r12*8+57h+var_98]
0x140039bb7  mov     r9, [rbp+r12*8+57h+var_90]
0x140039bbc  mov     r8, [rbp+57h+var_B0]
0x140039bc0  mov     rdx, [rbp+57h+pProxy]
0x140039bc4  mov     rcx, [r15]
0x140039bc7  mov     dword ptr [rsp+110h+ppv], eax
0x140039bcb  call    ?RegisterWmiEvent@CWmiEventSink@@QEAAJPEAUIWbemServices@@PEAUIUnsecuredApartment@@PEBGW4EWmsWmiEvent@@@Z; CWmiEventSink::RegisterWmiEvent(IWbemServices *,IUnsecuredApartment *,ushort const *,EWmsWmiEvent)
0x140039bd0  mov     ebx, eax
0x140039bd2  mov     r12d, 1
0x140039bd8  test    eax, eax
0x140039bda  js      loc_140039D5E
0x140039be0  add     r14, r12
0x140039be3  lea     rbx, aRgwmieventpara_0; "rgWmiEventParams[i].pEventSink == NULL"
0x140039bea  cmp     r14, 4
0x140039bee  jb      loc_140039B1B
0x140039bf4  mov     rcx, [r13+18h]; hHandle
0x140039bf8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140039bfb  call    cs:__imp_WaitForSingleObject
0x140039c01  test    eax, eax
0x140039c03  jz      loc_140039C8C
0x140039c09  call    cs:__imp_GetLastError
0x140039c0f  mov     ebx, eax
0x140039c11  test    eax, eax
0x140039c13  jle     short loc_140039C1E
0x140039c15  movzx   ebx, ax
0x140039c18  or      ebx, 80070000h
0x140039c1e  mov     eax, 80004005h
0x140039c23  lea     r13, aCbraex; "CBRAEx"
0x140039c2a  test    ebx, ebx
0x140039c2c  lea     r15, a0; "0"
0x140039c33  mov     r14d, 0BBh
0x140039c39  mov     r9, r13; unsigned __int16 *
0x140039c3c  cmovns  ebx, eax
0x140039c3f  mov     r8, rsi; unsigned __int16 *
0x140039c42  mov     [rsp+110h+dwImpLevel], ebx; int
0x140039c46  mov     edx, r14d; unsigned int
0x140039c49  mov     rcx, rdi; unsigned __int16 *
0x140039c4c  mov     [rsp+110h+ppv], r15; unsigned __int16 *
0x140039c51  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140039c56  call    cs:__imp_IsDebuggerPresent
0x140039c5c  test    eax, eax
0x140039c5e  jz      short loc_140039C76
0x140039c60  mov     [rsp+110h+dwCapabilities], ebx
0x140039c64  mov     r9d, r14d
0x140039c67  mov     [rsp+110h+pAuthInfo], r15
0x140039c6c  mov     qword ptr [rsp+110h+dwImpLevel], r13
0x140039c71  jmp     loc_1400399D6
0x140039c76  mov     dword ptr [rsp+110h+pAuthInfo], ebx
0x140039c7a  mov     r8d, r14d
0x140039c7d  mov     qword ptr [rsp+110h+dwImpLevel], r15
0x140039c82  mov     [rsp+110h+ppv], r13
0x140039c87  jmp     loc_140039A05
0x140039c8c  xor     r14d, r14d
0x140039c8f  mov     r13d, 0C5h
0x140039c95  lea     r12, [r14+r14*2]
0x140039c99  mov     r15, [rbp+r12*8+57h+var_A0]
0x140039c9e  lea     rbx, aRgwmieventpara; "rgWmiEventParams[i].pEventSink != NULL"
0x140039ca5  test    r15, r15
0x140039ca8  jnz     short loc_140039D14
0x140039caa  mov     r8, rsi; unsigned __int16 *
0x140039cad  mov     [rsp+110h+ppv], rbx; unsigned __int16 *
0x140039cb2  mov     edx, r13d; unsigned int
0x140039cb5  mov     rcx, rdi; unsigned __int16 *
0x140039cb8  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140039cbd  call    cs:__imp_IsDebuggerPresent
0x140039cc3  test    eax, eax
0x140039cc5  lea     rax, aAssert; "ASSERT"
0x140039ccc  jz      short loc_140039CF5
0x140039cce  mov     [rsp+110h+pAuthInfo], rbx
0x140039cd3  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140039cda  mov     qword ptr [rsp+110h+dwImpLevel], rax
0x140039cdf  lea     ecx, [r15+2]; unsigned __int8
0x140039ce3  mov     r9d, r13d
0x140039ce6  mov     [rsp+110h+ppv], rsi
0x140039ceb  mov     r8, rdi
0x140039cee  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140039cf3  jmp     short loc_140039D14
0x140039cf5  mov     qword ptr [rsp+110h+dwImpLevel], rbx
0x140039cfa  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140039d01  mov     r9, rsi
0x140039d04  mov     [rsp+110h+ppv], rax
0x140039d09  mov     r8d, r13d
0x140039d0c  mov     rdx, rdi
0x140039d0f  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140039d14  mov     rdx, [rbp+57h+pProxy]; struct IWbemServices *
0x140039d18  mov     rcx, r15; this
0x140039d1b  call    ?UnregisterWmiEvent@CWmiEventSink@@QEAAJPEAUIWbemServices@@@Z; CWmiEventSink::UnregisterWmiEvent(IWbemServices *)
0x140039d20  mov     ebx, eax
0x140039d22  test    eax, eax
0x140039d24  js      short loc_140039D58
0x140039d26  test    r15, r15
0x140039d29  jz      short loc_140039D43
0x140039d2b  mov     rax, [r15]
0x140039d2e  mov     rcx, r15
0x140039d31  mov     rax, [rax+10h]
0x140039d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039d3a  mov     [rbp+r12*8+57h+var_A0], 0
0x140039d43  mov     r12d, 1
0x140039d49  add     r14, r12
0x140039d4c  cmp     r14, 4
0x140039d50  jb      loc_140039C95
0x140039d56  jmp     short loc_140039D5E
0x140039d58  mov     r12d, 1
0x140039d5e  mov     rcx, [rbp+57h+pProxy]
0x140039d62  xor     edi, edi
0x140039d64  test    rcx, rcx
0x140039d67  jz      short loc_140039D79
0x140039d69  mov     rax, [rcx]
0x140039d6c  mov     rax, [rax+10h]
0x140039d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039d75  mov     [rbp+57h+pProxy], rdi
0x140039d79  mov     rcx, [rbp+57h+var_B8]
0x140039d7d  test    rcx, rcx
0x140039d80  jz      short loc_140039D92
0x140039d82  mov     rax, [rcx]
0x140039d85  mov     rax, [rax+10h]
0x140039d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039d8e  mov     [rbp+57h+var_B8], rdi
0x140039d92  mov     rcx, [rbp+57h+var_B0]
0x140039d96  test    rcx, rcx
0x140039d99  jz      short loc_140039DAB
0x140039d9b  mov     rax, [rcx]
0x140039d9e  mov     rax, [rax+10h]
0x140039da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039da7  mov     [rbp+57h+var_B0], rdi
0x140039dab  test    r12d, r12d
0x140039dae  jz      short loc_140039DB6
0x140039db0  call    cs:__imp_CoUninitialize
0x140039db6  mov     edx, ebx
  ... truncated ...
```
