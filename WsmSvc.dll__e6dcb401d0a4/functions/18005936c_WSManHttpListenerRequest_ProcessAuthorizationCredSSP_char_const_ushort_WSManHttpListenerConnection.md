# WSManHttpListenerRequest::ProcessAuthorizationCredSSP(char const *,ushort,WSManHttpListenerConnection *)

- ea: `0x18005936c`
- end: `0x180059e62`
- name: `?ProcessAuthorizationCredSSP@WSManHttpListenerRequest@@AEAAXPEBDGPEAVWSManHttpListenerConnection@@@Z`
- size: `2806`
- prototype: `void __fastcall(WSManHttpListener **this, const char *, unsigned __int16, struct WSManHttpListenerConnection *)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180058e84`

## callees

- `0x180005d10`
- `0x180019950`
- `0x1800224f0`
- `0x180026e80`
- `0x18004a900`
- `0x18005936c`
- `0x180059e68`
- `0x18005a8c8`
- `0x18005a954`
- `0x18005ad14`
- `0x18005c09c`
- `0x18005c664`
- `0x18005c8b0`
- `0x1800621e0`
- `0x180071400`
- `0x1800723d4`
- `0x18007e410`
- `0x18008d16c`
- `0x18008e040`
- `0x180112380`
- `0x1801123a8`
- `0x1801123e8`
- `0x18011a6d4`
- `0x18016d55c`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180059572`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180059572`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180059593`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180059593`
- `CRYPT32!CryptStringToBinaryA` at `0x18005950b`
- `CRYPT32!CryptStringToBinaryA` at `0x18005964e`
- `CRYPT32!CryptStringToBinaryA` at `0x18005950b`
- `CRYPT32!CryptStringToBinaryA` at `0x18005964e`
- `SspiCli!FreeContextBuffer` at `0x180059d5c`
- `SspiCli!FreeContextBuffer` at `0x180059d5c`
- `SspiCli!AcceptSecurityContext` at `0x180059867`
- `SspiCli!AcceptSecurityContext` at `0x180059867`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x18005980c`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x18005980c`

## string_xrefs

- `0x180059554`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x180059483`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x1800597da`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x180059b14`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x180059baa`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x180059c84`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x180059d48`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x1800594a2`: `Failed to get the server configuration settings`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WSManHttpListenerRequest::ProcessAuthorizationCredSSP(
        WSManHttpListener **this,
        const char *a2,
        unsigned __int16 a3,
        struct WSManHttpListenerConnection *a4)
{
  DWORD v5; // esi
  PVOID *v8; // rcx
  unsigned int ErrorCode; // eax
  DWORD v10; // r12d
  CHeap *v11; // rcx
  WSManHttpListener *v12; // rsi
  SIZE_T v13; // r14
  CHeap *v14; // rcx
  void *Handle; // rax
  SIZE_T v16; // rax
  CHeap *v17; // rcx
  void *v18; // rax
  SECURITY_STATUS v19; // r14d
  unsigned int SecurityPackageInfo; // esi
  int v21; // r15d
  WSManHttpListener *v22; // rax
  _WORD *v23; // rcx
  __int64 v24; // rdx
  _QWORD *v25; // r12
  struct _SecHandle *v26; // rdx
  PVOID *v27; // rcx
  const wchar_t *v28; // r9
  int v29; // r15d
  __int64 v30; // r9
  PVOID *v31; // rcx
  char v32; // r15
  void *v33; // rdx
  PVOID v34; // rdx
  unsigned int v35; // eax
  unsigned int pfContextAttr; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pdwSkip; // [rsp+54h] [rbp-ACh] BYREF
  void *v38; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+60h] [rbp-A0h] BYREF
  PVOID pvContextBuffer[2]; // [rsp+68h] [rbp-98h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+78h] [rbp-88h] BYREF
  struct _SecBufferDesc pInput; // [rsp+88h] [rbp-78h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+98h] [rbp-68h] BYREF
  _DWORD v44[2]; // [rsp+A0h] [rbp-60h] BYREF
  WSManHttpListener *v45; // [rsp+A8h] [rbp-58h]
  __int64 v46; // [rsp+B0h] [rbp-50h]
  __int64 v47; // [rsp+B8h] [rbp-48h]
  void **v48; // [rsp+C0h] [rbp-40h] BYREF
  signed __int32 v49[4]; // [rsp+C8h] [rbp-38h] BYREF
  char v50; // [rsp+D8h] [rbp-28h]
  const wchar_t *v51; // [rsp+E0h] [rbp-20h]
  const wchar_t *v52; // [rsp+E8h] [rbp-18h]
  const wchar_t *v53; // [rsp+F0h] [rbp-10h]
  const wchar_t *v54; // [rsp+F8h] [rbp-8h]
  DWORD pcbBinary; // [rsp+160h] [rbp+60h] BYREF

  v5 = a3;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 302, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, this);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !(_WORD)v5 )
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x400) != 0 )
      WPP_SF_(v8[2], 303, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
    WSManHttpListenerRequest::Send401((WSManHttpListenerRequest *)this, 0, 0);
    return;
  }
  v49[0] = 0;
  v48 = &CErrorContext::`vftable';
  v49[2] = 0;
  v49[3] = -1;
  v51 = &Class;
  v52 = &Class;
  v53 = &Class;
  v54 = &Class;
  v50 = 0;
  _InterlockedIncrement(v49);
  v39 = (*(__int64 (__fastcall **)(_QWORD, void ***, WSManHttpListener *))(**((_QWORD **)this[10] + 2) + 112LL))(
          *((_QWORD *)this[10] + 2),
          &v48,
          this[55]);
  if ( !v39 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 0x164Fu, L"5711", 0x54Fu, 0);
    ErrorCode = CErrorContext::GetErrorCode((CErrorContext *)&v48);
    WSManHttpListenerRequest::SendHttpError(
      (WSManHttpListenerRequest *)this,
      0x1F4u,
      1,
      0,
      0,
      ErrorCode,
      L"Failed to get the server configuration settings",
      &Class);
    AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v39);
    return;
  }
  pcbBinary = 0;
  pdwSkip = 0;
  v10 = v5;
  CryptStringToBinaryA(a2, v5, 1u, 0, &pcbBinary, &pdwSkip, &pdwSkip);
  v12 = this[52];
  if ( !v12 )
  {
    v12 = (WSManHttpListener *)WSManMemory::Alloc(pcbBinary, 0, 0);
    goto LABEL_19;
  }
  v13 = pcbBinary;
  if ( !CHeap::GetHandle(v11) )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 0xCFu, L"207", 0x54Fu, 0);
LABEL_15:
    v12 = 0;
    goto LABEL_19;
  }
  Handle = CHeap::GetHandle(v14);
  v16 = HeapSize(Handle, 0, v12);
  if ( v16 == -1 )
    goto LABEL_15;
  if ( v16 < v13 )
  {
    v18 = CHeap::GetHandle(v17);
    v12 = (WSManHttpListener *)HeapReAlloc(v18, 0, v12, v13);
  }
LABEL_19:
  if ( !v12 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 304, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
    WSManHttpListenerRequest::SendHttpError(
      (WSManHttpListenerRequest *)this,
      0x1F7u,
      1,
      0,
      0,
      0xEu,
      L"Not enough memory to carry out the request",
      &Class);
    AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v39);
    return;
  }
  this[52] = v12;
  if ( !CryptStringToBinaryA(a2, v10, 1u, (BYTE *)v12, &pcbBinary, &pdwSkip, &pdwSkip) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 305, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
    WSManHttpListenerRequest::Send401((WSManHttpListenerRequest *)this, 0, 0);
    AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v39);
    return;
  }
  v19 = 0;
  pfContextAttr = 0;
  ptsExpiry.QuadPart = 0;
  pInput = 0;
  pOutput = 0;
  *(_OWORD *)pvContextBuffer = 0;
  if ( !(unsigned int)WSManHttpListener::NeedToInitCredSSP(this[10])
    || (SecurityPackageInfo = WSManHttpListener::InitializeCredSSP(this[10])) == 0 )
  {
    pInput.ulVersion = 0;
    pInput.cBuffers = 2;
    pInput.pBuffers = (PSecBuffer)v44;
    v44[1] = 2;
    v44[0] = pcbBinary;
    v45 = this[52];
    v47 = 0;
    v46 = 0;
    pOutput.ulVersion = 0;
    pOutput.cBuffers = 1;
    pOutput.pBuffers = (PSecBuffer)pvContextBuffer;
    pvContextBuffer[0] = (PVOID)0x200000000LL;
    pvContextBuffer[1] = 0;
    if ( *((_DWORD *)a4 + 24) && *((_QWORD *)a4 + 10) != -1 && *((_QWORD *)a4 + 11) != -1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 306, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
      v21 = *((_DWORD *)a4 + 45);
      SecurityPackageInfo = WSManHttpListenerRequest::ResetConnection((WSManHttpListenerRequest *)this, a4);
      if ( SecurityPackageInfo )
        goto LABEL_116;
      *((_DWORD *)a4 + 45) = v21;
    }
    v22 = this[10];
    if ( *((_QWORD *)v22 + 34) == -1 || *((_QWORD *)v22 + 35) == -1 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 0x16C2u, L"5826", 0x54Fu, 0);
    LODWORD(v38) = 0;
    v23 = (_WORD *)*((_QWORD *)this[19] + 13);
    v24 = 28;
    if ( *v23 != 23 )
      v24 = 16;
    SeciAllocateAndSetIPAddress(v23, v24, &v38);
    v25 = (_QWORD *)((char *)a4 + 80);
    while ( 1 )
    {
      if ( *v25 == -1 || *((_QWORD *)a4 + 11) == -1 )
        v26 = 0;
      else
        v26 = (struct _SecHandle *)((char *)a4 + 80);
      v19 = AcceptSecurityContext(
              (PCredHandle)this[10] + 17,
              v26,
              &pInput,
              0x1811Du,
              0x10u,
              (PCtxtHandle)a4 + 5,
              &pOutput,
              &pfContextAttr,
              &ptsExpiry);
      v27 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          if ( *v25 == -1 || (v28 = L"continuation", *((_QWORD *)a4 + 11) == -1) )
            v28 = L"new context";
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            307,
            (unsigned int)&WPP_82c131e86f913802a795d1de50c3f51e_Traceguids,
            (_DWORD)v28,
            v19);
          v27 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v27 != &WPP_GLOBAL_Control )
        {
          if ( (*((_DWORD *)v27 + 7) & 0x400) != 0 )
          {
            WPP_SF_d(v27[2], 308, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, 98589);
            v27 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v27 != &WPP_GLOBAL_Control && (*((_DWORD *)v27 + 7) & 0x400) != 0 )
          {
            WPP_SF_d(v27[2], 309, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, pfContextAttr);
            v27 = (PVOID *)WPP_GLOBAL_Control;
          }
        }
      }
      if ( v19 != -2146893048 )
        break;
      if ( *v25 == -1 || *((_QWORD *)a4 + 11) == -1 )
      {
        if ( v27 != &WPP_GLOBAL_Control && (*((_DWORD *)v27 + 7) & 0x200) != 0 )
          WPP_SF_d(v27[2], 311, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, 2148074248LL);
LABEL_72:
        SecurityPackageInfo = SecurityStatusToWin32(v19);
        if ( SecurityPackageInfo != 14 )
          SecurityPackageInfo = 5;
        goto LABEL_116;
      }
      if ( v27 != &WPP_GLOBAL_Control && (*((_DWORD *)v27 + 7) & 0x400) != 0 )
        WPP_SF_(v27[2], 310, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
      v29 = *((_DWORD *)a4 + 45);
      SecurityPackageInfo = WSManHttpListenerRequest::ResetConnection((WSManHttpListenerRequest *)this, a4);
      if ( SecurityPackageInfo )
        goto LABEL_116;
      *((_DWORD *)a4 + 45) = v29;
    }
    if ( v19 < 0 )
    {
      if ( v27 != &WPP_GLOBAL_Control && (*((_DWORD *)v27 + 7) & 0x200) != 0 )
        WPP_SF_d(v27[2], 312, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, (unsigned int)v19);
      goto LABEL_72;
    }
    v30 = pfContextAttr;
    *((_DWORD *)a4 + 25) = pfContextAttr;
    v31 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 313, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, v30);
      v31 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v19 == 590610 || (v32 = 0, v19 == 590612) )
    {
      if ( v31 != &WPP_GLOBAL_Control && (*((_DWORD *)v31 + 7) & 0x400) != 0 )
      {
        WPP_SF_d(v31[2], 314, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, (unsigned int)v19);
        v31 = (PVOID *)WPP_GLOBAL_Control;
      }
      v32 = 1;
    }
    if ( LODWORD(pvContextBuffer[0]) )
    {
      SecurityPackageInfo = WSManHttpListenerRequest::PrepareNegotiateOutputAuthHeader(
                              (WSManHttpListenerRequest *)this,
                              (struct _SecBuffer *)pvContextBuffer,
                              a4);
      if ( SecurityPackageInfo )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            315,
            &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids,
            SecurityPackageInfo);
        if ( SecurityPackageInfo != 14 )
          WSManError(
            (wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp",
            0x173Eu,
            L"5950",
            0x54Fu,
            0);
        goto LABEL_116;
      }
      this[33] = (WSManHttpListener *)*((_QWORD *)a4 + 14);
      *((_DWORD *)this + 68) = *((_DWORD *)a4 + 26);
    }
    else if ( v31 != &WPP_GLOBAL_Control && (*((_DWORD *)v31 + 7) & 0x400) != 0 )
    {
      WPP_SF_(v31[2], 316, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
    }
    if ( v32 )
    {
      WSManHttpListenerRequest::Send401(
        (WSManHttpListenerRequest *)this,
        *((const char **)a4 + 14),
        *((_DWORD *)a4 + 26));
      SecurityPackageInfo = 0;
    }
    else if ( (pfContextAttr & 0x100000) != 0 )
    {
      *((_DWORD *)a4 + 30) = 5;
      SecurityPackageInfo = 5;
    }
    else
    {
      *((_DWORD *)this + 70) = pfContextAttr;
      SecurityPackageInfo = WSManHttpListenerRequest::ExtractSecurityPackageInfo((WSManHttpListenerRequest *)this, a4);
      if ( SecurityPackageInfo )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            317,
            &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids,
            SecurityPackageInfo);
      }
      else
      {
        v38 = 0;
        SecurityPackageInfo = WSManHttpListenerRequest::GetClientTokenFromCredSSPCredentials(
                                (WSManHttpListenerRequest *)this,
                                a4,
                                (struct AutoHandle *)&v38);
        if ( SecurityPackageInfo )
        {
          *((_DWORD *)a4 + 30) = 5;
          SecurityPackageInfo = 5;
        }
        else
        {
          *((_DWORD *)a4 + 24) = 1;
          if ( !*((_DWORD *)this[14] + 18)
            && (int)WSManHttpListener::DecrementUnauthenticatedConnections(this[10]) > 256 )
          {
            WSManError(
              (wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp",
              0x177Eu,
              L"6014",
              0x54Fu,
              0);
          }
          *((_DWORD *)a4 + 18) = 6;
          *((_QWORD *)a4 + 29) = L"CredSSP";
          *((_QWORD *)a4 + 28) = *((_QWORD *)a4 + 23);
          *((_QWORD *)a4 + 32) = this + 56;
          *((_QWORD *)a4 + 31) = v38;
          if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_AN_AUTHENTICATION_DONE) )
            WSMan::LogEvent<unsigned short *,unsigned short *>((struct _EVENT_DESCRIPTOR *)&LOG_WSMAN_AN_AUTHENTICATION_DONE);
          v33 = v38;
          v38 = 0;
          WSManHttpListenerRequest::DoUserAuthzCheck((WSManHttpListenerRequest *)this, v33, 1);
        }
        AutoCleanup<AutoHandle,void *>::ReleasePtr(&v38);
      }
    }
  }
LABEL_116:
  v34 = pvContextBuffer[1];
  if ( pvContextBuffer[1] )
  {
    if ( LODWORD(pvContextBuffer[0]) > *((_DWORD *)this[10] + 66) )
    {
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 0x1796u, L"6038", 0x54Fu, 0);
      v34 = pvContextBuffer[1];
    }
    FreeContextBuffer(v34);
  }
  if ( SecurityPackageInfo )
  {
    if ( v19 < 0 )
    {
      *((_DWORD *)a4 + 30) = SecurityStatusToWin32(v19);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          318,
          &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids,
          (unsigned int)v19);
    }
    v35 = WSManHttpListenerRequest::ResetConnection((WSManHttpListenerRequest *)this, a4);
    if ( v35 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 319, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, v35);
    if ( SecurityPackageInfo == 5 )
      WSManHttpListenerRequest::Send401((WSManHttpListenerRequest *)this, 0, 0);
    else
      WSManHttpListenerRequest::SendHttpError(
        (WSManHttpListenerRequest *)this,
        0x1F4u,
        1,
        0,
        0,
        SecurityPackageInfo,
        L"Failed to authenticate the user using credssp",
        &Class);
  }
  AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v39);
}

```

## disassembly

```asm
0x18005936c  push    rbp
0x18005936e  push    rbx
0x18005936f  push    rsi
0x180059370  push    rdi
0x180059371  push    r12
0x180059373  push    r13
0x180059375  push    r14
0x180059377  push    r15
0x180059379  lea     rbp, [rsp-8]
0x18005937e  sub     rsp, 108h
0x180059385  mov     rdi, r9
0x180059388  movzx   esi, r8w
0x18005938c  mov     r15, rdx
0x18005938f  mov     rbx, rcx
0x180059392  lea     r14, WPP_GLOBAL_Control
0x180059399  mov     rcx, cs:WPP_GLOBAL_Control
0x1800593a0  cmp     rcx, r14
0x1800593a3  jz      short loc_1800593CD
0x1800593a5  test    dword ptr [rcx+1Ch], 400h
0x1800593ac  jz      short loc_1800593CD
0x1800593ae  mov     edx, 12Eh
0x1800593b3  mov     r9, rbx
0x1800593b6  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x1800593bd  mov     rcx, [rcx+10h]
0x1800593c1  call    WPP_SF_q
0x1800593c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800593cd  xor     r13d, r13d
0x1800593d0  test    si, si
0x1800593d3  jnz     short loc_18005940A
0x1800593d5  cmp     rcx, r14
0x1800593d8  jz      short loc_1800593F8
0x1800593da  test    dword ptr [rcx+1Ch], 400h
0x1800593e1  jz      short loc_1800593F8
0x1800593e3  mov     edx, 12Fh
0x1800593e8  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x1800593ef  mov     rcx, [rcx+10h]
0x1800593f3  call    WPP_SF_
0x1800593f8  xor     r8d, r8d; unsigned int
0x1800593fb  xor     edx, edx; char *
0x1800593fd  mov     rcx, rbx; this
0x180059400  call    ?Send401@WSManHttpListenerRequest@@IEAAKPEBDK@Z; WSManHttpListenerRequest::Send401(char const *,ulong)
0x180059405  jmp     loc_180059E4E
0x18005940a  mov     [rbp+40h+var_78], r13d
0x18005940e  lea     rax, ??_7CErrorContext@@6B@; const CErrorContext::`vftable'
0x180059415  mov     [rbp+40h+var_80], rax
0x180059419  mov     [rbp+40h+var_70], r13d
0x18005941d  mov     [rbp+40h+var_6C], 0FFFFFFFFh
0x180059424  lea     r12, Class
0x18005942b  mov     [rbp+40h+var_60], r12
0x18005942f  mov     [rbp+40h+var_58], r12
0x180059433  mov     [rbp+40h+var_50], r12
0x180059437  mov     [rbp+40h+var_48], r12
0x18005943b  mov     [rbp+40h+var_68], r13b
0x18005943f  lock inc [rbp+40h+var_78]
0x180059443  mov     rax, [rbx+50h]
0x180059447  mov     rcx, [rax+10h]
0x18005944b  mov     rax, [rcx]
0x18005944e  mov     r8, [rbx+1B8h]
0x180059455  lea     rdx, [rbp+40h+var_80]
0x180059459  mov     rax, [rax+70h]
0x18005945d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059462  mov     [rsp+140h+var_E0], rax
0x180059467  test    rax, rax
0x18005946a  jnz     short loc_1800594D6
0x18005946c  mov     [rsp+140h+pcbBinary], r13; struct IRequestContext *
0x180059471  mov     r9d, 54Fh; unsigned int
0x180059477  lea     r8, a5711; "5711"
0x18005947e  mov     edx, 164Fh; unsigned int
0x180059483  lea     rcx, aOnecoreAdminWm_103; "onecore\\admin\\wmi\\wmx\\service\\wsma"...
0x18005948a  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18005948f  lea     rcx, [rbp+40h+var_80]; this
0x180059493  call    ?GetErrorCode@CErrorContext@@UEBAKXZ; CErrorContext::GetErrorCode(void)
0x180059498  mov     edx, 1F4h; unsigned __int16
0x18005949d  mov     [rsp+140h+pfContextAttr], r12; unsigned __int16 *
0x1800594a2  lea     rcx, aFailedToGetThe; "Failed to get the server configuration "...
0x1800594a9  mov     [rsp+140h+pdwFlags], rcx; unsigned __int16 *
0x1800594ae  mov     dword ptr [rsp+140h+pdwSkip], eax; unsigned int
0x1800594b2  mov     [rsp+140h+pcbBinary], r13; char *
0x1800594b7  xor     r9d, r9d; unsigned int
0x1800594ba  mov     r8b, 1; bool
0x1800594bd  mov     rcx, rbx; this
0x1800594c0  call    ?SendHttpError@WSManHttpListenerRequest@@IEAAKG_NKPEBDKPEBG2@Z; WSManHttpListenerRequest::SendHttpError(ushort,bool,ulong,char const *,ulong,ushort const *,ushort const *)
0x1800594c5  nop
0x1800594c6  lea     rcx, [rsp+140h+var_E0]
0x1800594cb  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VCServiceCommonConfigSettings@@@@PEAVCServiceCommonConfigSettings@@@@AEAAXXZ; AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(void)
0x1800594d0  nop
0x1800594d1  jmp     loc_180059E4E
0x1800594d6  mov     [rbp+40h+arg_10], r13d
0x1800594da  mov     [rsp+140h+var_EC], r13d
0x1800594df  mov     r12d, esi
0x1800594e2  lea     rax, [rsp+140h+var_EC]
0x1800594e7  mov     [rsp+140h+pdwFlags], rax; pdwFlags
0x1800594ec  lea     rax, [rsp+140h+var_EC]
0x1800594f1  mov     [rsp+140h+pdwSkip], rax; pdwSkip
0x1800594f6  lea     rax, [rbp+40h+arg_10]
0x1800594fa  mov     [rsp+140h+pcbBinary], rax; pcbBinary
0x1800594ff  xor     r9d, r9d; pbBinary
0x180059502  lea     r8d, [r9+1]; dwFlags
0x180059506  mov     edx, esi; cchString
0x180059508  mov     rcx, r15; pszString
0x18005950b  call    cs:__imp_CryptStringToBinaryA
0x180059511  mov     rsi, [rbx+1A0h]
0x180059518  test    rsi, rsi
0x18005951b  jnz     short loc_18005952F
0x18005951d  mov     ecx, [rbp+40h+arg_10]
0x180059520  xor     r8d, r8d
0x180059523  xor     edx, edx
0x180059525  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18005952a  mov     rsi, rax
0x18005952d  jmp     short loc_1800595A3
0x18005952f  mov     r14d, [rbp+40h+arg_10]
0x180059533  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x180059538  test    rax, rax
0x18005953b  jnz     short loc_180059565
0x18005953d  mov     [rsp+140h+pcbBinary], r13; struct IRequestContext *
0x180059542  mov     r9d, 54Fh; unsigned int
0x180059548  lea     r8, a207; "207"
0x18005954f  mov     edx, 0CFh; unsigned int
0x180059554  lea     rcx, aOnecoreAdminWm_20; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x18005955b  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180059560  mov     rsi, r13
0x180059563  jmp     short loc_18005959C
0x180059565  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18005956a  mov     r8, rsi; lpMem
0x18005956d  xor     edx, edx; dwFlags
0x18005956f  mov     rcx, rax; hHeap
0x180059572  call    cs:__imp_HeapSize
0x180059578  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005957c  jz      short loc_180059560
0x18005957e  cmp     rax, r14
0x180059581  jnb     short loc_18005959C
0x180059583  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x180059588  mov     r9, r14; dwBytes
0x18005958b  mov     r8, rsi; lpMem
0x18005958e  xor     edx, edx; dwFlags
0x180059590  mov     rcx, rax; hHeap
0x180059593  call    cs:__imp_HeapReAlloc
0x180059599  mov     rsi, rax
0x18005959c  lea     r14, WPP_GLOBAL_Control
0x1800595a3  test    rsi, rsi
0x1800595a6  jnz     short loc_18005961B
0x1800595a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800595af  cmp     rcx, r14
0x1800595b2  jz      short loc_1800595D2
0x1800595b4  test    dword ptr [rcx+1Ch], 400h
0x1800595bb  jz      short loc_1800595D2
0x1800595bd  mov     edx, 130h
0x1800595c2  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x1800595c9  mov     rcx, [rcx+10h]
0x1800595cd  call    WPP_SF_
0x1800595d2  mov     edx, 1F7h; unsigned __int16
0x1800595d7  lea     rax, Class
0x1800595de  mov     [rsp+140h+pfContextAttr], rax; unsigned __int16 *
0x1800595e3  lea     rax, aNotEnoughMemor; "Not enough memory to carry out the requ"...
0x1800595ea  mov     [rsp+140h+pdwFlags], rax; unsigned __int16 *
0x1800595ef  mov     dword ptr [rsp+140h+pdwSkip], 0Eh; unsigned int
0x1800595f7  mov     [rsp+140h+pcbBinary], r13; char *
0x1800595fc  xor     r9d, r9d; unsigned int
0x1800595ff  mov     r8b, 1; bool
0x180059602  mov     rcx, rbx; this
0x180059605  call    ?SendHttpError@WSManHttpListenerRequest@@IEAAKG_NKPEBDKPEBG2@Z; WSManHttpListenerRequest::SendHttpError(ushort,bool,ulong,char const *,ulong,ushort const *,ushort const *)
0x18005960a  nop
0x18005960b  lea     rcx, [rsp+140h+var_E0]
0x180059610  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VCServiceCommonConfigSettings@@@@PEAVCServiceCommonConfigSettings@@@@AEAAXXZ; AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(void)
0x180059615  nop
0x180059616  jmp     loc_180059E4E
0x18005961b  mov     [rbx+1A0h], rsi
0x180059622  lea     rax, [rsp+140h+var_EC]
0x180059627  mov     [rsp+140h+pdwFlags], rax; pdwFlags
0x18005962c  lea     rax, [rsp+140h+var_EC]
0x180059631  mov     [rsp+140h+pdwSkip], rax; pdwSkip
0x180059636  lea     rax, [rbp+40h+arg_10]
0x18005963a  mov     [rsp+140h+pcbBinary], rax; pcbBinary
0x18005963f  mov     r9, rsi; pbBinary
0x180059642  mov     r8d, 1; dwFlags
0x180059648  mov     edx, r12d; cchString
0x18005964b  mov     rcx, r15; pszString
0x18005964e  call    cs:__imp_CryptStringToBinaryA
0x180059654  xor     r12d, r12d
0x180059657  test    eax, eax
0x180059659  jnz     short loc_1800596A6
0x18005965b  mov     rcx, cs:WPP_GLOBAL_Control
0x180059662  cmp     rcx, r14
0x180059665  jz      short loc_180059688
0x180059667  mov     r13d, 200h
0x18005966d  test    [rcx+1Ch], r13d
0x180059671  jz      short loc_180059688
0x180059673  mov     edx, 131h
0x180059678  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18005967f  mov     rcx, [rcx+10h]
0x180059683  call    WPP_SF_
0x180059688  xor     r8d, r8d; unsigned int
0x18005968b  xor     edx, edx; char *
0x18005968d  mov     rcx, rbx; this
0x180059690  call    ?Send401@WSManHttpListenerRequest@@IEAAKPEBDK@Z; WSManHttpListenerRequest::Send401(char const *,ulong)
0x180059695  nop
0x180059696  lea     rcx, [rsp+140h+var_E0]
0x18005969b  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VCServiceCommonConfigSettings@@@@PEAVCServiceCommonConfigSettings@@@@AEAAXXZ; AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(void)
0x1800596a0  nop
0x1800596a1  jmp     loc_180059E4E
0x1800596a6  mov     esi, r12d
0x1800596a9  mov     r14d, r12d
0x1800596ac  mov     [rsp+140h+var_F0], r12d
0x1800596b1  mov     qword ptr [rbp+40h+var_A8], r12
0x1800596b5  xorps   xmm0, xmm0
0x1800596b8  movups  xmmword ptr [rbp+40h+pInput.ulVersion], xmm0
0x1800596bc  xorps   xmm1, xmm1
0x1800596bf  movups  xmmword ptr [rsp+140h+pOutput.ulVersion], xmm1
0x1800596c4  movups  xmmword ptr [rsp+140h+pvContextBuffer], xmm0
0x1800596c9  mov     rcx, [rbx+50h]; this
0x1800596cd  call    ?NeedToInitCredSSP@WSManHttpListener@@QEAAHXZ; WSManHttpListener::NeedToInitCredSSP(void)
0x1800596d2  mov     r13d, 200h
0x1800596d8  test    eax, eax
0x1800596da  jz      short loc_1800596EF
0x1800596dc  mov     rcx, [rbx+50h]; this
0x1800596e0  call    ?InitializeCredSSP@WSManHttpListener@@QEAAKXZ; WSManHttpListener::InitializeCredSSP(void)
0x1800596e5  mov     esi, eax
0x1800596e7  test    eax, eax
0x1800596e9  jnz     loc_180059D17
0x1800596ef  mov     [rbp+40h+pInput.ulVersion], r12d
0x1800596f3  mov     edx, 2
0x1800596f8  mov     [rbp+40h+pInput.cBuffers], edx
0x1800596fb  lea     rax, [rbp+40h+var_A0]
0x1800596ff  mov     [rbp+40h+pInput.pBuffers], rax
0x180059703  mov     [rbp+40h+var_9C], edx
0x180059706  mov     ecx, [rbp+40h+arg_10]
0x180059709  mov     [rbp+40h+var_A0], ecx
0x18005970c  mov     rcx, [rbx+1A0h]
0x180059713  mov     [rbp+40h+var_98], rcx
0x180059717  mov     [rbp+40h+var_88], r12
0x18005971b  mov     [rbp+40h+var_90], r12
0x18005971f  mov     [rsp+140h+pOutput.ulVersion], r12d
0x180059724  mov     [rsp+140h+pOutput.cBuffers], 1
0x18005972c  lea     rax, [rsp+140h+pvContextBuffer]
0x180059731  mov     [rbp+40h+pOutput.pBuffers], rax
0x180059735  mov     dword ptr [rsp+140h+pvContextBuffer+4], edx
0x180059739  mov     dword ptr [rsp+140h+pvContextBuffer], r12d
0x18005973e  mov     [rsp+140h+pvContextBuffer+8], r12
0x180059743  cmp     [rdi+60h], r12d
0x180059747  jz      short loc_1800597AB
0x180059749  cmp     qword ptr [rdi+50h], 0FFFFFFFFFFFFFFFFh
0x18005974e  jz      short loc_1800597AB
0x180059750  cmp     qword ptr [rdi+58h], 0FFFFFFFFFFFFFFFFh
0x180059755  jz      short loc_1800597AB
0x180059757  mov     rcx, cs:WPP_GLOBAL_Control
0x18005975e  lea     rax, WPP_GLOBAL_Control
0x180059765  cmp     rcx, rax
0x180059768  jz      short loc_180059788
0x18005976a  test    dword ptr [rcx+1Ch], 400h
0x180059771  jz      short loc_180059788
0x180059773  mov     edx, 132h
0x180059778  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18005977f  mov     rcx, [rcx+10h]
0x180059783  call    WPP_SF_
0x180059788  mov     r15d, [rdi+0B4h]
0x18005978f  mov     rdx, rdi; struct WSManHttpListenerConnection *
0x180059792  mov     rcx, rbx; this
0x180059795  call    ?ResetConnection@WSManHttpListenerRequest@@AEAAKPEAVWSManHttpListenerConnection@@@Z; WSManHttpListenerRequest::ResetConnection(WSManHttpListenerConnection *)
0x18005979a  mov     esi, eax
0x18005979c  test    eax, eax
0x18005979e  jnz     loc_180059D17
0x1800597a4  mov     [rdi+0B4h], r15d
0x1800597ab  mov     rax, [rbx+50h]
0x1800597af  cmp     qword ptr [rax+110h], 0FFFFFFFFFFFFFFFFh
0x1800597b7  jz      short loc_1800597C3
0x1800597b9  cmp     qword ptr [rax+118h], 0FFFFFFFFFFFFFFFFh
0x1800597c1  jnz     short loc_1800597E6
0x1800597c3  mov     [rsp+140h+pcbBinary], r12; struct IRequestContext *
0x1800597c8  mov     r9d, 54Fh; unsigned int
0x1800597ce  lea     r8, a5826; "5826"
0x1800597d5  mov     edx, 16C2h; unsigned int
0x1800597da  lea     rcx, aOnecoreAdminWm_103; "onecore\\admin\\wmi\\wmx\\service\\wsma"...
0x1800597e1  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800597e6  mov     dword ptr [rsp+140h+var_E8], r12d
0x1800597eb  mov     rax, [rbx+98h]
0x1800597f2  mov     rcx, [rax+68h]
0x1800597f6  mov     edx, 1Ch
0x1800597fb  lea     r14d, [rdx-0Ch]
0x1800597ff  cmp     word ptr [rcx], 17h
0x180059803  cmovnz  edx, r14d
0x180059807  lea     r8, [rsp+140h+var_E8]
0x18005980c  call    cs:__imp_SeciAllocateAndSetIPAddress
0x180059812  lea     r12, [rdi+50h]
0x180059816  cmp     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x18005981b  jz      short loc_180059829
0x18005981d  cmp     qword ptr [rdi+58h], 0FFFFFFFFFFFFFFFFh
0x180059822  jz      short loc_180059829
0x180059824  mov     rdx, r12
0x180059827  jmp     short loc_18005982B
0x180059829  xor     edx, edx; phContext
0x18005982b  mov     rcx, [rbx+50h]
0x18005982f  add     rcx, 110h; phCredential
0x180059836  lea     rax, [rbp+40h+var_A8]
0x18005983a  mov     [rsp+140h+ptsExpiry], rax; ptsExpiry
0x18005983f  lea     rax, [rsp+140h+var_F0]
0x180059844  mov     [rsp+140h+pfContextAttr], rax; pfContextAttr
0x180059849  lea     rax, [rsp+140h+pOutput]
0x18005984e  mov     [rsp+140h+pdwFlags], rax; pOutput
0x180059853  mov     [rsp+140h+pdwSkip], r12; phNewContext
0x180059858  mov     dword ptr [rsp+140h+pcbBinary], r14d; TargetDataRep
  ... truncated ...
```
