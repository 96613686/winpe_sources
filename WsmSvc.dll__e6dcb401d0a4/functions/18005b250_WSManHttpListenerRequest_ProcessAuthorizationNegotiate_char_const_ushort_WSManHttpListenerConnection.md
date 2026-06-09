# WSManHttpListenerRequest::ProcessAuthorizationNegotiate(char const *,ushort,WSManHttpListenerConnection *)

- ea: `0x18005b250`
- end: `0x18005c096`
- name: `?ProcessAuthorizationNegotiate@WSManHttpListenerRequest@@AEAAXPEBDGPEAVWSManHttpListenerConnection@@@Z`
- size: `3654`
- prototype: `void __fastcall(WSManHttpListener **this, LPCSTR pszString, unsigned __int16, struct WSManHttpListenerConnection *)`
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
- `0x18005a8c8`
- `0x18005a954`
- `0x18005b250`
- `0x18005c09c`
- `0x18005c664`
- `0x18005c8b0`
- `0x18005d800`
- `0x180071400`
- `0x1800723d4`
- `0x18007e410`
- `0x18008d16c`
- `0x18008e040`
- `0x180112380`
- `0x1801123a8`
- `0x1801123e8`
- `0x180112460`
- `0x18011a6d4`
- `0x18016e590`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005b4df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005b6f3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005b4df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005b6f3`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18005b517`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18005b517`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18005b538`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18005b538`
- `CRYPT32!CryptStringToBinaryA` at `0x18005b484`
- `CRYPT32!CryptStringToBinaryA` at `0x18005b5fa`
- `CRYPT32!CryptStringToBinaryA` at `0x18005b484`
- `CRYPT32!CryptStringToBinaryA` at `0x18005b5fa`
- `SspiCli!AcceptSecurityContext` at `0x18005b96a`
- `SspiCli!AcceptSecurityContext` at `0x18005b96a`
- `SspiCli!QuerySecurityContextToken` at `0x18005bd92`
- `SspiCli!QuerySecurityContextToken` at `0x18005bd92`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x18005b7d9`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x18005b7d9`

## string_xrefs

- `0x18005b4c2`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x18005b6d3`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x18005b3ba`: `Failed to retrieve server configuration settings`
- `0x18005b394`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x18005b7a9`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x18005b886`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x18005b8b6`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x18005bc37`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x18005bcd4`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x18005bd6e`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x18005be6b`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x18005bf39`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WSManHttpListenerRequest::ProcessAuthorizationNegotiate(
        WSManHttpListener **this,
        LPCSTR pszString,
        unsigned __int16 a3,
        struct WSManHttpListenerConnection *a4)
{
  DWORD v5; // edi
  PVOID *v8; // rcx
  __int64 v9; // r14
  unsigned int ErrorCode; // eax
  DWORD v11; // r15d
  CHeap *v12; // rcx
  WSManHttpListener *v13; // rdi
  SIZE_T v14; // rdi
  CHeap *v15; // rcx
  const unsigned __int16 *v16; // r8
  unsigned int v17; // edx
  void *Handle; // rax
  WSManHttpListener *v19; // rax
  SIZE_T v20; // r14
  CHeap *v21; // rcx
  void *v22; // rax
  SIZE_T v23; // rax
  CHeap *v24; // rcx
  void *v25; // rax
  SECURITY_STATUS v26; // r14d
  WSManHttpListener *v27; // rax
  SIZE_T v28; // rdi
  CHeap *v29; // rcx
  void *v30; // rax
  unsigned int v31; // edi
  int v32; // r15d
  WSManHttpListener *v33; // rax
  _WORD *v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rdx
  int v37; // r14d
  char *v38; // rcx
  _QWORD *v39; // r15
  struct _SecHandle *v40; // r8
  unsigned int v41; // r12d
  int v42; // edi
  __int64 cBuffers; // rax
  PSecBuffer pBuffers; // rdx
  __int64 v45; // rcx
  unsigned int v46; // r8d
  void *v47; // r9
  struct _SecHandle *v48; // rdx
  PVOID *v49; // rcx
  const wchar_t *v50; // r9
  int v51; // r12d
  unsigned int v52; // r8d
  PVOID *v53; // rcx
  char v54; // r15
  SECURITY_STATUS v55; // eax
  unsigned int SecurityPackageInfo; // eax
  void *v57; // rdx
  unsigned int v58; // eax
  _DWORD *v59; // rbx
  int v60; // eax
  unsigned int pfContextAttr; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbBinary; // [rsp+54h] [rbp-ACh] BYREF
  void *Token; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pdwSkip; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD *v65; // [rsp+68h] [rbp-98h] BYREF
  struct _SecBuffer v66; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v67; // [rsp+80h] [rbp-80h]
  struct _SecBufferDesc pInput; // [rsp+88h] [rbp-78h] BYREF
  __int64 v69; // [rsp+98h] [rbp-68h]
  SECURITY_INTEGER ptsExpiry; // [rsp+A0h] [rbp-60h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+A8h] [rbp-58h] BYREF
  void **v72; // [rsp+C0h] [rbp-40h] BYREF
  signed __int32 v73[4]; // [rsp+C8h] [rbp-38h] BYREF
  char v74; // [rsp+D8h] [rbp-28h]
  const wchar_t *v75; // [rsp+E0h] [rbp-20h]
  const wchar_t *v76; // [rsp+E8h] [rbp-18h]
  const wchar_t *v77; // [rsp+F0h] [rbp-10h]
  const wchar_t *v78; // [rsp+F8h] [rbp-8h]
  _DWORD v79[2]; // [rsp+100h] [rbp+0h] BYREF
  WSManHttpListener *v80; // [rsp+108h] [rbp+8h]

  v5 = a3;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 279, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, this);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !(_WORD)v5 )
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x400) != 0 )
      WPP_SF_(v8[2], 280, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
    WSManHttpListenerRequest::Send401((WSManHttpListenerRequest *)this, 0, 0);
    return;
  }
  v9 = *((_QWORD *)this[19] + 105);
  v69 = v9;
  v67 = *((_DWORD *)this[10] + 66);
  v73[0] = 0;
  v72 = &CErrorContext::`vftable';
  v73[2] = 0;
  v73[3] = -1;
  v75 = &Class;
  v76 = &Class;
  v77 = &Class;
  v78 = &Class;
  v74 = 0;
  _InterlockedIncrement(v73);
  v65 = (_DWORD *)(*(__int64 (__fastcall **)(_QWORD, void ***, WSManHttpListener *))(**((_QWORD **)this[10] + 2) + 112LL))(
                    *((_QWORD *)this[10] + 2),
                    &v72,
                    this[55]);
  if ( !v65 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 0x1444u, L"5188", 0x54Fu, 0);
    ErrorCode = CErrorContext::GetErrorCode((CErrorContext *)&v72);
    WSManHttpListenerRequest::SendHttpError(
      (WSManHttpListenerRequest *)this,
      0x1F4u,
      1,
      0,
      0,
      ErrorCode,
      L"Failed to retrieve server configuration settings",
      &Class);
    AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v65);
    return;
  }
  if ( v9 && WSManHttpListenerRequest::QueryChannelBindingToken((WSManHttpListenerRequest *)this, a4) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 281, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, this);
    WSManHttpListenerRequest::Send401((WSManHttpListenerRequest *)this, 0, 0);
    AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v65);
    return;
  }
  pcbBinary = 0;
  pdwSkip = 0;
  v11 = v5;
  CryptStringToBinaryA(pszString, v5, 1u, 0, &pcbBinary, &pdwSkip, &pdwSkip);
  v13 = this[52];
  if ( !v13 )
  {
    v14 = pcbBinary;
    if ( !CHeap::GetHandle(v12) )
    {
      v16 = L"170";
      v17 = 170;
LABEL_20:
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", v17, v16, 0x54Fu, 0);
LABEL_21:
      v13 = 0;
      goto LABEL_29;
    }
    Handle = CHeap::GetHandle(v15);
    v19 = (WSManHttpListener *)HeapAlloc(Handle, 0, v14);
    goto LABEL_28;
  }
  v20 = pcbBinary;
  if ( !CHeap::GetHandle(v12) )
  {
    v16 = L"207";
    v17 = 207;
    goto LABEL_20;
  }
  v22 = CHeap::GetHandle(v21);
  v23 = HeapSize(v22, 0, v13);
  if ( v23 == -1 )
    goto LABEL_21;
  if ( v23 < v20 )
  {
    v25 = CHeap::GetHandle(v24);
    v19 = (WSManHttpListener *)HeapReAlloc(v25, 0, v13, v20);
LABEL_28:
    v13 = v19;
  }
LABEL_29:
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 282, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
    WSManHttpListenerRequest::SendHttpError(
      (WSManHttpListenerRequest *)this,
      0x1F7u,
      1,
      0,
      0,
      0xEu,
      L"Not enough memory to carry out the request",
      &Class);
    AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v65);
    return;
  }
  this[52] = v13;
  if ( !CryptStringToBinaryA(pszString, v11, 1u, (BYTE *)v13, &pcbBinary, &pdwSkip, &pdwSkip) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 283, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
    WSManHttpListenerRequest::Send401((WSManHttpListenerRequest *)this, 0, 0);
    AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v65);
    return;
  }
  v26 = 0;
  pfContextAttr = 0;
  ptsExpiry.QuadPart = 0;
  v66 = 0;
  pInput.ulVersion = 0;
  pInput.cBuffers = 1;
  pInput.pBuffers = (PSecBuffer)v79;
  v79[1] = 2;
  v79[0] = pcbBinary;
  v80 = this[52];
  pOutput.ulVersion = 0;
  pOutput.cBuffers = 1;
  pOutput.pBuffers = &v66;
  v66.BufferType = 2;
  v27 = this[10];
  v28 = *((unsigned int *)v27 + 66);
  v66.cbBuffer = *((_DWORD *)v27 + 66);
  if ( !CHeap::GetHandle((CHeap *)2) )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 0xAAu, L"170", 0x54Fu, 0);
    v66.pvBuffer = 0;
LABEL_42:
    v31 = 14;
    v66.cbBuffer = 0;
    goto LABEL_157;
  }
  v30 = CHeap::GetHandle(v29);
  v66.pvBuffer = HeapAlloc(v30, 0, v28);
  if ( !v66.pvBuffer )
    goto LABEL_42;
  if ( *((_DWORD *)a4 + 24) && *((_QWORD *)a4 + 10) != -1 && *((_QWORD *)a4 + 11) != -1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 284, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
    v32 = *((_DWORD *)a4 + 45);
    v31 = WSManHttpListenerRequest::ResetConnection((WSManHttpListenerRequest *)this, a4);
    if ( v31 )
      goto LABEL_157;
    *((_DWORD *)a4 + 45) = v32;
  }
  v33 = this[10];
  if ( *((_QWORD *)v33 + 31) == -1 || *((_QWORD *)v33 + 32) == -1 )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 0x14BBu, L"5307", 0x54Fu, 0);
  LODWORD(Token) = 0;
  v34 = (_WORD *)*((_QWORD *)this[19] + 13);
  v35 = 28;
  if ( *v34 != 23 )
    v35 = 16;
  SeciAllocateAndSetIPAddress(v34, v35, &Token);
  v36 = v69;
  v37 = (v69 == 0 ? 0x14 : 0) | 0x8003;
  LODWORD(Token) = v37;
  v38 = (char *)a4 + 88;
  v39 = (_QWORD *)((char *)a4 + 88);
  while ( 1 )
  {
    v40 = (struct _SecHandle *)((char *)a4 + 80);
    v41 = v37;
    if ( v36 )
    {
      if ( *(_BYTE *)(*((_QWORD *)a4 + 7) + 932LL) )
      {
        v42 = v65[99];
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 278, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, this);
        if ( !this[19] )
          WSManError(
            (wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp",
            0x1403u,
            L"5123",
            0x54Fu,
            0);
        if ( !*((_QWORD *)this[19] + 105) )
          WSManError(
            (wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp",
            0x1404u,
            L"5124",
            0x54Fu,
            0);
        if ( v42 )
        {
          cBuffers = pInput.cBuffers;
          pBuffers = pInput.pBuffers;
          v45 = *((_QWORD *)a4 + 37);
          if ( v45 )
          {
            v46 = *(_DWORD *)(v45 + 16);
            v47 = *(void **)(v45 + 8);
          }
          else
          {
            v46 = 0;
            v47 = 0;
          }
          if ( v42 == 1 )
            v41 = v37 | 0x10000000;
          pInput.pBuffers[pInput.cBuffers].BufferType = 14;
          pBuffers[cBuffers].pvBuffer = v47;
          pBuffers[cBuffers].cbBuffer = v46;
          ++pInput.cBuffers;
        }
        v39 = (_QWORD *)((char *)a4 + 88);
        v40 = (struct _SecHandle *)((char *)a4 + 80);
      }
      else
      {
        v39 = v38;
      }
    }
    if ( v40->dwLower == -1 || *v39 == -1 )
      v48 = 0;
    else
      v48 = v40;
    v26 = AcceptSecurityContext(
            (PCredHandle)((char *)this[10] + 248),
            v48,
            &pInput,
            v41,
            0x10u,
            v40,
            &pOutput,
            &pfContextAttr,
            &ptsExpiry);
    v49 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        if ( *((_QWORD *)a4 + 10) == -1 || (v50 = L"continuation", *v39 == -1) )
          v50 = L"new context";
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          286,
          (unsigned int)&WPP_82c131e86f913802a795d1de50c3f51e_Traceguids,
          (_DWORD)v50,
          v26);
        v49 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v49 != &WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)v49 + 7) & 0x400) != 0 )
        {
          WPP_SF_d(v49[2], 287, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, v41);
          v49 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v49 != &WPP_GLOBAL_Control && (*((_DWORD *)v49 + 7) & 0x400) != 0 )
        {
          WPP_SF_d(v49[2], 288, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, pfContextAttr);
          v49 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
    }
    if ( v26 != -2146893048 )
      break;
    if ( *((_QWORD *)a4 + 10) == -1 || *v39 == -1 )
    {
      if ( v49 != &WPP_GLOBAL_Control && (*((_DWORD *)v49 + 7) & 0x200) != 0 )
        WPP_SF_d(v49[2], 290, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, 2148074248LL);
      goto LABEL_102;
    }
    if ( v49 != &WPP_GLOBAL_Control && (*((_DWORD *)v49 + 7) & 0x400) != 0 )
      WPP_SF_(v49[2], 289, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
    v51 = *((_DWORD *)a4 + 45);
    v31 = WSManHttpListenerRequest::ResetConnection((WSManHttpListenerRequest *)this, a4);
    if ( v31 )
      goto LABEL_157;
    *((_DWORD *)a4 + 45) = v51;
    v37 = (int)Token;
    v38 = (char *)a4 + 88;
    v36 = v69;
  }
  if ( v26 < 0 )
  {
    if ( v49 != &WPP_GLOBAL_Control && (*((_DWORD *)v49 + 7) & 0x200) != 0 )
      WPP_SF_d(v49[2], 291, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, (unsigned int)v26);
LABEL_102:
    v31 = SecurityStatusToWin32(v26);
    if ( v31 != 14 )
      v31 = 5;
    goto LABEL_157;
  }
  v52 = pfContextAttr;
  *((_DWORD *)a4 + 25) = pfContextAttr;
  v53 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 292, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, v52);
    v52 = pfContextAttr;
    v53 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v26 == 590610 || (v54 = 0, v26 == 590612) )
  {
    if ( v53 != &WPP_GLOBAL_Control && (*((_DWORD *)v53 + 7) & 0x400) != 0 )
    {
      WPP_SF_d(v53[2], 293, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, (unsigned int)v26);
      v52 = pfContextAttr;
      v53 = (PVOID *)WPP_GLOBAL_Control;
    }
    v54 = 1;
  }
  if ( v66.cbBuffer )
  {
    v31 = WSManHttpListenerRequest::PrepareNegotiateOutputAuthHeader((WSManHttpListenerRequest *)this, &v66, a4);
    if ( v31 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 294, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, v31);
      if ( v31 != 14 )
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 0x1549u, L"5449", 0x54Fu, 0);
      goto LABEL_157;
    }
    this[33] = (WSManHttpListener *)*((_QWORD *)a4 + 14);
    *((_DWORD *)this + 68) = *((_DWORD *)a4 + 26);
  }
  else
  {
    if ( v53 == &WPP_GLOBAL_Control || (*((_DWORD *)v53 + 7) & 0x400) == 0 )
      goto LABEL_130;
    WPP_SF_(v53[2], 295, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
  }
  v52 = pfContextAttr;
LABEL_130:
  if ( v54 )
  {
    WSManHttpListenerRequest::Send401((WSManHttpListenerRequest *)this, *((const char **)a4 + 14), *((_DWORD *)a4 + 26));
    v31 = 0;
    goto LABEL_157;
  }
  if ( (v52 & 0x100000) != 0 )
  {
    *((_DWORD *)a4 + 30) = 5;
    v31 = 5;
    goto LABEL_157;
  }
  *((_DWORD *)this + 70) = v52;
  if ( *((_QWORD *)this[19] + 105)
    || (v52 & 0x10) != 0
    || (*(unsigned int (__fastcall **)(_DWORD *))(*(_QWORD *)v65 + 96LL))(v65) )
  {
    Token = 0;
    v55 = QuerySecurityContextToken((PCtxtHandle)a4 + 5, &Token);
    v26 = v55;
    if ( v55 >= 0 )
    {
      SecurityPackageInfo = WSManHttpListenerRequest::ExtractSecurityPackageInfo((WSManHttpListenerRequest *)this, a4);
      v31 = SecurityPackageInfo;
      if ( !SecurityPackageInfo )
      {
        *((_DWORD *)a4 + 24) = 1;
        if ( !*((_DWORD *)this[14] + 18) && (int)WSManHttpListener::DecrementUnauthenticatedConnections(this[10]) > 256 )
          WSManError(
            (wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp",
            0x159Bu,
            L"5531",
            0x54Fu,
            0);
        *((_DWORD *)a4 + 18) = (*((_DWORD *)a4 + 45) != 1) + 3;
        *((_QWORD *)a4 + 29) = *(_QWORD *)(*((_QWORD *)a4 + 17) + 16LL);
        *((_QWORD *)a4 + 28) = *((_QWORD *)a4 + 16);
        *((_QWORD *)a4 + 32) = this + 56;
        *((_QWORD *)a4 + 31) = Token;
        if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_AN_AUTHENTICATION_DONE) )
          WSMan::LogEvent<unsigned short *,unsigned short *>((struct _EVENT_DESCRIPTOR *)&LOG_WSMAN_AN_AUTHENTICATION_DONE);
        v57 = Token;
        Token = 0;
        WSManHttpListenerRequest::DoUserAuthzCheck((WSManHttpListenerRequest *)this, v57, 1);
        AutoCleanup<AutoHandle,void *>::ReleasePtr(&Token);
        goto LABEL_157;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          298,
          &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids,
          SecurityPackageInfo);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          297,
          &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids,
          (unsigned int)v55);
      v31 = SecurityStatusToWin32(v26);
      *((_DWORD *)a4 + 30) = v31;
    }
    AutoCleanup<AutoHandle,void *>::ReleasePtr(&Token);
    goto LABEL_157;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 296, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids);
  *((_DWORD *)a4 + 30) = 5;
  v31 = 5;
LABEL_157:
  if ( v66.pvBuffer )
  {
    if ( v66.cbBuffer > v67 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\wsmanhttplistener.cpp", 0x15B3u, L"5555", 0x54Fu, 0);
    WSManMemory::Free(v66.pvBuffer, 0);
  }
  if ( v31 )
  {
    if ( v26 < 0 )
    {
      *((_DWORD *)a4 + 30) = SecurityStatusToWin32(v26);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          299,
          &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids,
          (unsigned int)v26);
    }
    v58 = WSManHttpListenerRequest::ResetConnection((WSManHttpListenerRequest *)this, a4);
    if ( v58 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 300, &WPP_82c131e86f913802a795d1de50c3f51e_Traceguids, v58);
    if ( v31 == 5 )
      WSManHttpListenerRequest::Send401((WSManHttpListenerRequest *)this, 0, 0);
    else
      WSManHttpListenerRequest::SendHttpError(
        (WSManHttpListenerRequest *)this,
        0x1F4u,
        1,
        0,
        0,
        v31,
        L"Failed to authenticate the user using negotiate",
        &Class);
    AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(&v65);
  }
  else
  {
    v59 = v65;
    if ( v65 )
    {
      v60 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v65 + 144LL))(v65);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_4bcfcb6bc4c53d70488bc6bf4d078fb8_Traceguids, v59, v60);
    }
  }
}

```

## disassembly

```asm
0x18005b250  push    rbp
0x18005b252  push    rbx
0x18005b253  push    rsi
0x18005b254  push    rdi
0x18005b255  push    r12
0x18005b257  push    r13
0x18005b259  push    r14
0x18005b25b  push    r15
0x18005b25d  lea     rbp, [rsp-48h]
0x18005b262  sub     rsp, 148h
0x18005b269  mov     rax, cs:__security_cookie
0x18005b270  xor     rax, rsp
0x18005b273  mov     [rbp+80h+var_50], rax
0x18005b277  mov     rsi, r9
0x18005b27a  movzx   edi, r8w
0x18005b27e  mov     r12, rdx
0x18005b281  mov     rbx, rcx
0x18005b284  lea     r13, WPP_GLOBAL_Control
0x18005b28b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b292  cmp     rcx, r13
0x18005b295  jz      short loc_18005B2BF
0x18005b297  test    dword ptr [rcx+1Ch], 400h
0x18005b29e  jz      short loc_18005B2BF
0x18005b2a0  mov     edx, 117h
0x18005b2a5  mov     r9, rbx
0x18005b2a8  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18005b2af  mov     rcx, [rcx+10h]
0x18005b2b3  call    WPP_SF_q
0x18005b2b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b2bf  xor     r15d, r15d
0x18005b2c2  test    di, di
0x18005b2c5  jnz     short loc_18005B2FC
0x18005b2c7  cmp     rcx, r13
0x18005b2ca  jz      short loc_18005B2EA
0x18005b2cc  test    dword ptr [rcx+1Ch], 400h
0x18005b2d3  jz      short loc_18005B2EA
0x18005b2d5  mov     edx, 118h
0x18005b2da  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18005b2e1  mov     rcx, [rcx+10h]
0x18005b2e5  call    WPP_SF_
0x18005b2ea  xor     r8d, r8d; unsigned int
0x18005b2ed  xor     edx, edx; char *
0x18005b2ef  mov     rcx, rbx; this
0x18005b2f2  call    ?Send401@WSManHttpListenerRequest@@IEAAKPEBDK@Z; WSManHttpListenerRequest::Send401(char const *,ulong)
0x18005b2f7  jmp     loc_18005C076
0x18005b2fc  mov     rax, [rbx+98h]
0x18005b303  mov     r14, [rax+348h]
0x18005b30a  mov     [rbp+80h+var_E8], r14
0x18005b30e  mov     rax, [rbx+50h]
0x18005b312  mov     eax, [rax+108h]
0x18005b318  mov     [rbp+80h+var_100], eax
0x18005b31b  mov     [rbp+80h+var_B8], r15d
0x18005b31f  lea     rax, ??_7CErrorContext@@6B@; const CErrorContext::`vftable'
0x18005b326  mov     [rbp+80h+var_C0], rax
0x18005b32a  mov     [rbp+80h+var_B0], r15d
0x18005b32e  mov     [rbp+80h+var_AC], 0FFFFFFFFh
0x18005b335  lea     rax, Class
0x18005b33c  mov     [rbp+80h+var_A0], rax
0x18005b340  mov     [rbp+80h+var_98], rax
0x18005b344  mov     [rbp+80h+var_90], rax
0x18005b348  mov     [rbp+80h+var_88], rax
0x18005b34c  mov     [rbp+80h+var_A8], r15b
0x18005b350  lock inc [rbp+80h+var_B8]
0x18005b354  mov     rax, [rbx+50h]
0x18005b358  mov     rcx, [rax+10h]
0x18005b35c  mov     rax, [rcx]
0x18005b35f  mov     r8, [rbx+1B8h]
0x18005b366  lea     rdx, [rbp+80h+var_C0]
0x18005b36a  mov     rax, [rax+70h]
0x18005b36e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b373  mov     [rsp+180h+var_118], rax
0x18005b378  test    rax, rax
0x18005b37b  jnz     short loc_18005B3EE
0x18005b37d  mov     [rsp+180h+pcbBinary], r15; struct IRequestContext *
0x18005b382  mov     r9d, 54Fh; unsigned int
0x18005b388  lea     r8, a5188; "5188"
0x18005b38f  mov     edx, 1444h; unsigned int
0x18005b394  lea     rcx, aOnecoreAdminWm_103; "onecore\\admin\\wmi\\wmx\\service\\wsma"...
0x18005b39b  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18005b3a0  lea     rcx, [rbp+80h+var_C0]; this
0x18005b3a4  call    ?GetErrorCode@CErrorContext@@UEBAKXZ; CErrorContext::GetErrorCode(void)
0x18005b3a9  mov     edx, 1F4h; unsigned __int16
0x18005b3ae  lea     rcx, Class
0x18005b3b5  mov     [rsp+180h+pfContextAttr], rcx; unsigned __int16 *
0x18005b3ba  lea     rcx, aFailedToRetrie_2; "Failed to retrieve server configuration"...
0x18005b3c1  mov     [rsp+180h+pdwFlags], rcx; unsigned __int16 *
0x18005b3c6  mov     dword ptr [rsp+180h+pdwSkip], eax; unsigned int
0x18005b3ca  mov     [rsp+180h+pcbBinary], r15; char *
0x18005b3cf  xor     r9d, r9d; unsigned int
0x18005b3d2  mov     r8b, 1; bool
0x18005b3d5  mov     rcx, rbx; this
0x18005b3d8  call    ?SendHttpError@WSManHttpListenerRequest@@IEAAKG_NKPEBDKPEBG2@Z; WSManHttpListenerRequest::SendHttpError(ushort,bool,ulong,char const *,ulong,ushort const *,ushort const *)
0x18005b3dd  nop
0x18005b3de  lea     rcx, [rsp+180h+var_118]
0x18005b3e3  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VCServiceCommonConfigSettings@@@@PEAVCServiceCommonConfigSettings@@@@AEAAXXZ; AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(void)
0x18005b3e8  nop
0x18005b3e9  jmp     loc_18005C076
0x18005b3ee  test    r14, r14
0x18005b3f1  jz      short loc_18005B44D
0x18005b3f3  mov     rdx, rsi; struct WSManHttpListenerConnection *
0x18005b3f6  mov     rcx, rbx; this
0x18005b3f9  call    ?QueryChannelBindingToken@WSManHttpListenerRequest@@AEAAKPEAVWSManHttpListenerConnection@@@Z; WSManHttpListenerRequest::QueryChannelBindingToken(WSManHttpListenerConnection *)
0x18005b3fe  test    eax, eax
0x18005b400  jz      short loc_18005B44D
0x18005b402  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b409  cmp     rcx, r13
0x18005b40c  jz      short loc_18005B42F
0x18005b40e  test    dword ptr [rcx+1Ch], 400h
0x18005b415  jz      short loc_18005B42F
0x18005b417  mov     edx, 119h
0x18005b41c  mov     r9, rbx
0x18005b41f  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18005b426  mov     rcx, [rcx+10h]
0x18005b42a  call    WPP_SF_q
0x18005b42f  xor     r8d, r8d; unsigned int
0x18005b432  xor     edx, edx; char *
0x18005b434  mov     rcx, rbx; this
0x18005b437  call    ?Send401@WSManHttpListenerRequest@@IEAAKPEBDK@Z; WSManHttpListenerRequest::Send401(char const *,ulong)
0x18005b43c  nop
0x18005b43d  lea     rcx, [rsp+180h+var_118]
0x18005b442  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VCServiceCommonConfigSettings@@@@PEAVCServiceCommonConfigSettings@@@@AEAAXXZ; AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(void)
0x18005b447  nop
0x18005b448  jmp     loc_18005C076
0x18005b44d  mov     [rsp+180h+var_12C], r15d
0x18005b452  mov     [rsp+180h+var_120], r15d
0x18005b457  mov     r15d, edi
0x18005b45a  lea     rax, [rsp+180h+var_120]
0x18005b45f  mov     [rsp+180h+pdwFlags], rax; pdwFlags
0x18005b464  lea     rax, [rsp+180h+var_120]
0x18005b469  mov     [rsp+180h+pdwSkip], rax; pdwSkip
0x18005b46e  lea     rax, [rsp+180h+var_12C]
0x18005b473  mov     [rsp+180h+pcbBinary], rax; pcbBinary
0x18005b478  xor     r9d, r9d; pbBinary
0x18005b47b  lea     r8d, [r9+1]; dwFlags
0x18005b47f  mov     edx, edi; cchString
0x18005b481  mov     rcx, r12; pszString
0x18005b484  call    cs:__imp_CryptStringToBinaryA
0x18005b48a  mov     rdi, [rbx+1A0h]
0x18005b491  test    rdi, rdi
0x18005b494  jnz     short loc_18005B4E7
0x18005b496  mov     edi, [rsp+180h+var_12C]
0x18005b49a  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18005b49f  mov     r13d, 54Fh
0x18005b4a5  test    rax, rax
0x18005b4a8  jnz     short loc_18005B4D2
0x18005b4aa  lea     r8, a170; "170"
0x18005b4b1  mov     edx, 0AAh; unsigned int
0x18005b4b6  mov     r9d, r13d; unsigned int
0x18005b4b9  mov     [rsp+180h+pcbBinary], 0; struct IRequestContext *
0x18005b4c2  lea     rcx, aOnecoreAdminWm_20; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x18005b4c9  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18005b4ce  xor     edi, edi
0x18005b4d0  jmp     short loc_18005B541
0x18005b4d2  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18005b4d7  mov     r8, rdi; dwBytes
0x18005b4da  xor     edx, edx; dwFlags
0x18005b4dc  mov     rcx, rax; hHeap
0x18005b4df  call    cs:__imp_HeapAlloc
0x18005b4e5  jmp     short loc_18005B53E
0x18005b4e7  mov     r14d, [rsp+180h+var_12C]
0x18005b4ec  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18005b4f1  mov     r13d, 54Fh
0x18005b4f7  test    rax, rax
0x18005b4fa  jnz     short loc_18005B50A
0x18005b4fc  lea     r8, a207; "207"
0x18005b503  mov     edx, 0CFh
0x18005b508  jmp     short loc_18005B4B6
0x18005b50a  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18005b50f  mov     r8, rdi; lpMem
0x18005b512  xor     edx, edx; dwFlags
0x18005b514  mov     rcx, rax; hHeap
0x18005b517  call    cs:__imp_HeapSize
0x18005b51d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005b521  jz      short loc_18005B4CE
0x18005b523  cmp     rax, r14
0x18005b526  jnb     short loc_18005B541
0x18005b528  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18005b52d  mov     r9, r14; dwBytes
0x18005b530  mov     r8, rdi; lpMem
0x18005b533  xor     edx, edx; dwFlags
0x18005b535  mov     rcx, rax; hHeap
0x18005b538  call    cs:__imp_HeapReAlloc
0x18005b53e  mov     rdi, rax
0x18005b541  test    rdi, rdi
0x18005b544  jnz     short loc_18005B5C4
0x18005b546  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b54d  lea     rax, WPP_GLOBAL_Control
0x18005b554  cmp     rcx, rax
0x18005b557  jz      short loc_18005B577
0x18005b559  test    dword ptr [rcx+1Ch], 400h
0x18005b560  jz      short loc_18005B577
0x18005b562  mov     edx, 11Ah
0x18005b567  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18005b56e  mov     rcx, [rcx+10h]
0x18005b572  call    WPP_SF_
0x18005b577  mov     edx, 1F7h; unsigned __int16
0x18005b57c  lea     rcx, Class
0x18005b583  mov     [rsp+180h+pfContextAttr], rcx; unsigned __int16 *
0x18005b588  lea     rax, aNotEnoughMemor; "Not enough memory to carry out the requ"...
0x18005b58f  mov     [rsp+180h+pdwFlags], rax; unsigned __int16 *
0x18005b594  mov     dword ptr [rsp+180h+pdwSkip], 0Eh; unsigned int
0x18005b59c  mov     [rsp+180h+pcbBinary], 0; char *
0x18005b5a5  xor     r9d, r9d; unsigned int
0x18005b5a8  mov     r8b, 1; bool
0x18005b5ab  mov     rcx, rbx; this
0x18005b5ae  call    ?SendHttpError@WSManHttpListenerRequest@@IEAAKG_NKPEBDKPEBG2@Z; WSManHttpListenerRequest::SendHttpError(ushort,bool,ulong,char const *,ulong,ushort const *,ushort const *)
0x18005b5b3  nop
0x18005b5b4  lea     rcx, [rsp+180h+var_118]
0x18005b5b9  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VCServiceCommonConfigSettings@@@@PEAVCServiceCommonConfigSettings@@@@AEAAXXZ; AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(void)
0x18005b5be  nop
0x18005b5bf  jmp     loc_18005C076
0x18005b5c4  mov     [rbx+1A0h], rdi
0x18005b5cb  lea     rax, [rsp+180h+var_120]
0x18005b5d0  mov     [rsp+180h+pdwFlags], rax; pdwFlags
0x18005b5d5  lea     rax, [rsp+180h+var_120]
0x18005b5da  mov     [rsp+180h+pdwSkip], rax; pdwSkip
0x18005b5df  lea     rax, [rsp+180h+var_12C]
0x18005b5e4  mov     [rsp+180h+pcbBinary], rax; pcbBinary
0x18005b5e9  mov     r9, rdi; pbBinary
0x18005b5ec  mov     edi, 1
0x18005b5f1  mov     r8d, edi; dwFlags
0x18005b5f4  mov     edx, r15d; cchString
0x18005b5f7  mov     rcx, r12; pszString
0x18005b5fa  call    cs:__imp_CryptStringToBinaryA
0x18005b600  xor     r12d, r12d
0x18005b603  test    eax, eax
0x18005b605  jnz     short loc_18005B656
0x18005b607  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b60e  lea     rax, WPP_GLOBAL_Control
0x18005b615  cmp     rcx, rax
0x18005b618  jz      short loc_18005B638
0x18005b61a  test    dword ptr [rcx+1Ch], 200h
0x18005b621  jz      short loc_18005B638
0x18005b623  mov     edx, 11Bh
0x18005b628  lea     r8, WPP_82c131e86f913802a795d1de50c3f51e_Traceguids
0x18005b62f  mov     rcx, [rcx+10h]
0x18005b633  call    WPP_SF_
0x18005b638  xor     r8d, r8d; unsigned int
0x18005b63b  xor     edx, edx; char *
0x18005b63d  mov     rcx, rbx; this
0x18005b640  call    ?Send401@WSManHttpListenerRequest@@IEAAKPEBDK@Z; WSManHttpListenerRequest::Send401(char const *,ulong)
0x18005b645  nop
0x18005b646  lea     rcx, [rsp+180h+var_118]
0x18005b64b  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VCServiceCommonConfigSettings@@@@PEAVCServiceCommonConfigSettings@@@@AEAAXXZ; AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(void)
0x18005b650  nop
0x18005b651  jmp     loc_18005C076
0x18005b656  mov     r14d, r12d
0x18005b659  mov     [rsp+180h+var_130], r12d
0x18005b65e  mov     qword ptr [rbp+80h+var_E0], r12
0x18005b662  xorps   xmm0, xmm0
0x18005b665  movups  xmmword ptr [rsp+180h+var_110.cbBuffer], xmm0
0x18005b66a  mov     [rbp+80h+pInput.ulVersion], r12d
0x18005b66e  mov     [rbp+80h+pInput.cBuffers], edi
0x18005b671  lea     rax, [rbp+80h+var_80]
0x18005b675  mov     [rbp+80h+pInput.pBuffers], rax
0x18005b679  mov     ecx, 2; this
0x18005b67e  mov     [rbp+80h+var_7C], ecx
0x18005b681  mov     eax, [rsp+180h+var_12C]
0x18005b685  mov     [rbp+80h+var_80], eax
0x18005b688  mov     rax, [rbx+1A0h]
0x18005b68f  mov     [rbp+80h+var_78], rax
0x18005b693  mov     [rbp+80h+pOutput.ulVersion], r12d
0x18005b697  mov     [rbp+80h+pOutput.cBuffers], edi
0x18005b69a  lea     rax, [rsp+180h+var_110]
0x18005b69f  mov     [rbp+80h+pOutput.pBuffers], rax
0x18005b6a3  mov     [rsp+180h+var_110.BufferType], ecx
0x18005b6a7  mov     rax, [rbx+50h]
0x18005b6ab  mov     edi, [rax+108h]
0x18005b6b1  mov     [rsp+180h+var_110.cbBuffer], edi
0x18005b6b5  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18005b6ba  test    rax, rax
0x18005b6bd  jnz     short loc_18005B6E6
0x18005b6bf  mov     [rsp+180h+pcbBinary], r12; struct IRequestContext *
0x18005b6c4  mov     r9d, r13d; unsigned int
0x18005b6c7  lea     r8, a170; "170"
0x18005b6ce  mov     edx, 0AAh; unsigned int
0x18005b6d3  lea     rcx, aOnecoreAdminWm_20; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x18005b6da  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18005b6df  mov     [rsp+180h+var_110.pvBuffer], r12
0x18005b6e4  jmp     short loc_18005B703
0x18005b6e6  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x18005b6eb  mov     r8, rdi; dwBytes
0x18005b6ee  xor     edx, edx; dwFlags
0x18005b6f0  mov     rcx, rax; hHeap
0x18005b6f3  call    cs:__imp_HeapAlloc
0x18005b6f9  mov     [rsp+180h+var_110.pvBuffer], rax
0x18005b6fe  test    rax, rax
0x18005b701  jnz     short loc_18005B712
0x18005b703  mov     edi, 0Eh
0x18005b708  mov     [rsp+180h+var_110.cbBuffer], r12d
0x18005b70d  jmp     loc_18005BF0E
0x18005b712  mov     edi, r12d
0x18005b715  cmp     [rsi+60h], r12d
0x18005b719  jz      short loc_18005B77D
0x18005b71b  cmp     qword ptr [rsi+50h], 0FFFFFFFFFFFFFFFFh
0x18005b720  jz      short loc_18005B77D
0x18005b722  cmp     qword ptr [rsi+58h], 0FFFFFFFFFFFFFFFFh
0x18005b727  jz      short loc_18005B77D
0x18005b729  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b730  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
