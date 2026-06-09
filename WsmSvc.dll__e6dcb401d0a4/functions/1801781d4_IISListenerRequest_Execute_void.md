# IISListenerRequest::Execute(void)

- ea: `0x1801781d4`
- end: `0x180178aa6`
- name: `?Execute@IISListenerRequest@@AEAAXXZ`
- size: `2258`
- prototype: `void __fastcall(IISListenerRequest *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180179ff0`

## callees

- `0x180005d10`
- `0x18000fc50`
- `0x1800134a0`
- `0x180025d90`
- `0x180026e80`
- `0x180058b10`
- `0x1800621e0`
- `0x1800973c0`
- `0x1800a8e00`
- `0x1800d7920`
- `0x18010389c`
- `0x180112380`
- `0x1801123a8`
- `0x180120718`
- `0x180177bd0`
- `0x1801781d4`
- `0x1801796b8`
- `0x1801ba152`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801785d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801785fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180178747`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801785d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801785fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180178747`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1801785b3`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1801785b3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180178a2d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180178a2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180178586`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18017858f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180178586`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18017858f`
- `CRYPT32!CertFreeCertificateContext` at `0x1801787d4`
- `CRYPT32!CertFreeCertificateContext` at `0x18017880e`
- `CRYPT32!CertFreeCertificateContext` at `0x1801787d4`
- `CRYPT32!CertFreeCertificateContext` at `0x18017880e`
- `CRYPT32!CertCreateCertificateContext` at `0x180178739`
- `CRYPT32!CertCreateCertificateContext` at `0x180178739`

## string_xrefs

- `0x18017820f`: `onecore\admin\wmi\wmx\service\iislistener.cpp`
- `0x180178a53`: `onecore\admin\wmi\wmx\service\iislistener.cpp`
- `0x180178542`: `Failed to create IIS User object`
- `0x180178466`: `Failed to create IIS Connection context`
- `0x180178a5f`: `Failed to get IIS configuration`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall IISListenerRequest::Execute(IISListenerRequest *this)
{
  struct IHttpUser *v2; // r15
  __int64 v3; // r13
  __int64 v4; // rax
  const unsigned __int16 *v5; // rax
  __int64 v6; // r14
  __int64 v7; // r12
  IISUser *v8; // rbx
  bool *v9; // r14
  unsigned int ErrorCode; // eax
  IISConnectionContext *v11; // rax
  IISConnectionContext *v12; // rsi
  signed int v13; // ebx
  unsigned int v14; // edx
  void *v15; // r12
  HANDLE CurrentProcess; // rbx
  HANDLE v17; // rax
  DWORD LastError; // eax
  DWORD v19; // eax
  const unsigned __int16 *v20; // rcx
  _QWORD *v21; // rbx
  __int64 v22; // rsi
  __int64 v23; // rdx
  PCCERT_CONTEXT CertificateContext; // r14
  unsigned int v25; // eax
  __int64 v26; // rax
  InboundRequestDetails *v27; // rax
  InboundRequestDetails *v28; // rcx
  CRequestContext *v29; // rax
  CRequestContext *v30; // rax
  __int64 v31; // rcx
  void (__fastcall ***v32)(_QWORD); // rcx
  __int64 v33; // rdx
  SOCKADDR *v34; // rcx
  socklen_t v35; // edx
  const unsigned __int16 *dwOptions; // [rsp+30h] [rbp-39h]
  void **v37; // [rsp+40h] [rbp-29h] BYREF
  signed __int32 v38; // [rsp+48h] [rbp-21h] BYREF
  int v39; // [rsp+50h] [rbp-19h]
  int v40; // [rsp+54h] [rbp-15h]
  char v41; // [rsp+58h] [rbp-11h]
  const wchar_t *v42; // [rsp+60h] [rbp-9h]
  const wchar_t *v43; // [rsp+68h] [rbp-1h]
  const wchar_t *v44; // [rsp+70h] [rbp+7h]
  const wchar_t *v45; // [rsp+78h] [rbp+Fh]
  IISUser *v46; // [rsp+D0h] [rbp+67h] BYREF
  int v47; // [rsp+D8h] [rbp+6Fh] BYREF
  IISUser **v48; // [rsp+E0h] [rbp+77h]
  InboundRequestDetails *v49; // [rsp+E8h] [rbp+7Fh]

  if ( !*((_QWORD *)this + 7) )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\iislistener.cpp", 525, L"525", 0x54Fu, 0);
  v2 = (struct IHttpUser *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 48LL))(*((_QWORD *)this + 9));
  v3 = *(_QWORD *)(*((_QWORD *)this + 6) + 176LL);
  v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 16LL))(*((_QWORD *)this + 9));
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_d6cffbb67e90322691f38b07bd2f6a1e_Traceguids);
    v5 = L"Failed to retrieve IIS connection object";
    goto LABEL_8;
  }
  v6 = **((_QWORD **)this + 7);
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( (**(__int64 (__fastcall ***)(__int64, __int64))v7)(v7, v3) )
  {
    v9 = (bool *)(v6 + 130);
  }
  else
  {
    v8 = (IISUser *)WSManMemory::Alloc(40, 0, 0);
    v46 = v8;
    if ( !v8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_d6cffbb67e90322691f38b07bd2f6a1e_Traceguids);
      v5 = L"Failed to create IIS User object";
      goto LABEL_8;
    }
    *(_QWORD *)v8 = &IISUser::`vftable';
    *((_DWORD *)v8 + 2) = 1;
    *((_QWORD *)v8 + 2) = 0;
    *((_QWORD *)v8 + 3) = 0;
    *((_QWORD *)v8 + 4) = 0;
    v38 = 0;
    v37 = &CErrorContext::`vftable';
    v39 = 0;
    v40 = -1;
    v42 = &Class;
    v43 = &Class;
    v44 = &Class;
    v45 = &Class;
    v41 = 0;
    _InterlockedIncrement(&v38);
    v9 = (bool *)(v6 + 130);
    if ( !IISUser::Initialize(v8, (struct IRequestContext *)&v37, v2, *v9) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_d6cffbb67e90322691f38b07bd2f6a1e_Traceguids);
      ErrorCode = CErrorContext::GetErrorCode((CErrorContext *)&v37);
      IISListenerRequest::SendHttpError(
        this,
        0x1F4u,
        0,
        0,
        ErrorCode,
        L"Failed to initialize IIS user object",
        dwOptions);
      (*(void (__fastcall **)(IISUser *))(*(_QWORD *)v8 + 56LL))(v8);
      return;
    }
    LODWORD(v46) = 0;
    v48 = &v46;
    v11 = (IISConnectionContext *)WSManMemory::Alloc(16, 0, 0);
    v12 = v11;
    v49 = v11;
    if ( v11 )
    {
      *(_QWORD *)v11 = &IISConnectionContext::`vftable';
      *((_QWORD *)v11 + 1) = v8;
      (*(void (__fastcall **)(IISUser *))(*(_QWORD *)v8 + 48LL))(v8);
    }
    else
    {
      v12 = 0;
    }
    (*(void (__fastcall **)(IISUser *))(*(_QWORD *)v8 + 56LL))(v8);
    if ( !v12 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_d6cffbb67e90322691f38b07bd2f6a1e_Traceguids);
      IISListenerRequest::SendHttpError(this, 0x1F4u, 0, 0, 0xEu, L"Failed to create IIS Connection context", dwOptions);
      return;
    }
    v13 = (*(__int64 (__fastcall **)(__int64, IISConnectionContext *, __int64))(*(_QWORD *)v7 + 8LL))(v7, v12, v3);
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          40,
          WPP_d6cffbb67e90322691f38b07bd2f6a1e_Traceguids,
          (unsigned int)v13);
      IISListenerRequest::SendHttpError(this, 0x1F4u, 0, 0, v13, L"Failed to set IIS module context", dwOptions);
      IISConnectionContext::`scalar deleting destructor'(v12, v14);
      return;
    }
  }
  *((_QWORD *)this + 26) = 0;
  v15 = (void *)(*(__int64 (__fastcall **)(struct IHttpUser *))(*(_QWORD *)v2 + 32LL))(v2);
  if ( v15 )
  {
    if ( !*v9 )
    {
      CurrentProcess = GetCurrentProcess();
      v17 = GetCurrentProcess();
      if ( !DuplicateHandle(v17, v15, CurrentProcess, (LPHANDLE)this + 26, 0, 0, 2u) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_d6cffbb67e90322691f38b07bd2f6a1e_Traceguids, LastError);
        }
        v19 = GetLastError();
        v20 = L"Failure identifying IIS user";
        goto LABEL_42;
      }
    }
  }
  if ( (int)StringCchCopyNW(
              (unsigned __int16 *)this + 108,
              0x800u,
              *(const unsigned __int16 **)(*((_QWORD *)this + 10) + 72LL),
              (unsigned __int64)*(unsigned __int16 *)(*((_QWORD *)this + 10) + 64LL) >> 1) >= 0 )
  {
    v21 = (_QWORD *)((char *)this + 128);
    *((_OWORD *)this + 8) = 0;
    *((_OWORD *)this + 9) = 0;
    *((_OWORD *)this + 10) = 0;
    *((_OWORD *)this + 11) = 0;
    *((_OWORD *)this + 12) = 0;
    *((_QWORD *)this + 16) = (**(__int64 (__fastcall ***)(struct IHttpUser *))v2)(v2);
    *((_QWORD *)this + 19) = *((_QWORD *)this + 26);
    *((_QWORD *)this + 17) = (*(__int64 (__fastcall **)(struct IHttpUser *))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 20) = (char *)this + 216;
    v47 = 0;
    v22 = -1;
    if ( (*(int (__fastcall **)(_QWORD, char *, int *))(**((_QWORD **)this + 8) + 160LL))(
           *((_QWORD *)this + 8),
           (char *)this + 88,
           &v47) >= 0 )
    {
      v23 = *((_QWORD *)this + 11);
      if ( v23 )
      {
        CertificateContext = CertCreateCertificateContext(0x10001u, *(const BYTE **)(v23 + 8), *(_DWORD *)(v23 + 4));
        if ( !CertificateContext )
        {
          v19 = GetLastError();
          v20 = L"Failed to process IIS client certificate";
LABEL_42:
          IISListenerRequest::SendHttpError(this, 0x1F4u, 0, 0, v19, v20, dwOptions);
          return;
        }
        v38 = 0;
        v37 = &CErrorContext::`vftable';
        v39 = 0;
        v40 = -1;
        v42 = &Class;
        v43 = &Class;
        v44 = &Class;
        v45 = &Class;
        v41 = 0;
        _InterlockedIncrement(&v38);
        if ( !GetCertDetails(
                (struct IRequestContext *)&v37,
                CertificateContext,
                (struct _WSMAN_CERTIFICATE_DETAILS *)((char *)this + 176)) )
        {
          v25 = CErrorContext::GetErrorCode((CErrorContext *)&v37);
          IISListenerRequest::SendHttpError(
            this,
            0x1F4u,
            0,
            0,
            v25,
            L"Failed to extract details from the IIS client certificate",
            dwOptions);
          CertFreeCertificateContext(CertificateContext);
          return;
        }
        if ( !*v21 )
          goto LABEL_58;
        v26 = -1;
        do
          ++v26;
        while ( *(_WORD *)(*v21 + 2 * v26) );
        if ( !v26 )
LABEL_58:
          *v21 = *((_QWORD *)this + 25);
        *((_QWORD *)this + 18) = (char *)this + 176;
        CertFreeCertificateContext(CertificateContext);
        v21 = (_QWORD *)((char *)this + 128);
      }
    }
    if ( !*v21 )
      goto LABEL_80;
    do
      ++v22;
    while ( *(_WORD *)(*v21 + 2 * v22) );
    if ( !v22 )
    {
LABEL_80:
      IISListenerRequest::SendHttpError(
        this,
        0x191u,
        0,
        0,
        5u,
        L"IIS Request had no username so sending 401, probably due to anonymous auth module being present",
        dwOptions);
      return;
    }
    LODWORD(v46) = 0;
    v48 = &v46;
    v27 = (InboundRequestDetails *)WSManMemory::Alloc(720, 0, 0);
    v49 = v27;
    if ( v27 )
      v28 = InboundRequestDetails::InboundRequestDetails(v27);
    else
      v28 = 0;
    *((_QWORD *)this + 539) = v28;
    if ( v28 )
    {
      (**(void (__fastcall ***)(InboundRequestDetails *))v28)(v28);
      LODWORD(v46) = 0;
      v48 = &v46;
      v29 = (CRequestContext *)WSManMemory::Alloc(672, 0, 0);
      v49 = v29;
      v30 = v29 ? CRequestContext::CRequestContext(v29) : 0LL;
      AutoRelease<CServiceConfigCache>::operator=(*((_QWORD *)this + 539) + 72LL, v30);
      v31 = *((_QWORD *)this + 539);
      if ( *(_QWORD *)(v31 + 72) )
      {
        AutoRelease<CCommonConfigSettings>::operator=(v31 + 80, *(_QWORD *)(*((_QWORD *)this + 7) + 8LL));
        v32 = *(void (__fastcall ****)(_QWORD))(*((_QWORD *)this + 539) + 80LL);
        if ( !v32 )
        {
          WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\iislistener.cpp", 680, L"680", 0x54Fu, 0);
          v5 = L"Failed to get IIS configuration";
          goto LABEL_8;
        }
        (**v32)(v32);
        *(_QWORD *)(*((_QWORD *)this + 539) + 64LL) = **((_QWORD **)this + 7);
        *(_QWORD *)(*((_QWORD *)this + 539) + 88LL) = ((unsigned __int64)this + 8)
                                                    & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64);
        *(_QWORD *)(*((_QWORD *)this + 539) + 104LL) = 0;
        AutoHandle::operator=(*((_QWORD *)this + 539) + 112LL, *((_QWORD *)this + 26));
        *((_QWORD *)this + 26) = 0;
        v33 = (*((_QWORD *)this + 539) + 16LL) & ((unsigned __int128)-(__int128)*((unsigned __int64 *)this + 539) >> 64);
        *(_OWORD *)v33 = *((_OWORD *)this + 8);
        *(_OWORD *)(v33 + 16) = *((_OWORD *)this + 9);
        *(_OWORD *)(v33 + 32) = *((_OWORD *)this + 10);
        *(_QWORD *)(v33 + 24) = *(_QWORD *)(*((_QWORD *)this + 539) + 112LL);
        memset_0((void *)(*((_QWORD *)this + 539) + 120LL), 0, 0x82u);
        v34 = *(SOCKADDR **)(*((_QWORD *)this + 10) + 104LL);
        v35 = 16;
        if ( v34->sa_family != 2 )
          v35 = 28;
        if ( !(unsigned int)ConvertSocketAddrToStringW(
                              v34,
                              v35,
                              (LPWSTR)(*((_QWORD *)this + 539) + 120LL),
                              *(struct IRequestContext **)(*((_QWORD *)this + 539) + 72LL)) )
        {
          v19 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 539) + 72LL) + 152LL))(*(_QWORD *)(*((_QWORD *)this + 539) + 72LL));
          v20 = L"Cannot retrieve remote IP";
          goto LABEL_42;
        }
        if ( QueueUserWorkItem(IISListenerRequest::AsyncGetUserProc, this, 0x10u) )
          return;
      }
    }
    v5 = L"Not enough memory to carry out the request";
LABEL_8:
    IISListenerRequest::SendHttpError(this, 0x1F4u, 0, 0, 0xEu, v5, dwOptions);
    return;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_d6cffbb67e90322691f38b07bd2f6a1e_Traceguids);
  IISListenerRequest::SendHttpError(this, 0x190u, 0, 0, 0xDu, L"IIS request HTTP url is too long", dwOptions);
}

```

## disassembly

```asm
0x1801781d4  push    rbp
0x1801781d6  push    rbx
0x1801781d7  push    rsi
0x1801781d8  push    rdi
0x1801781d9  push    r12
0x1801781db  push    r13
0x1801781dd  push    r14
0x1801781df  push    r15
0x1801781e1  lea     rbp, [rsp-1Fh]
0x1801781e6  sub     rsp, 88h
0x1801781ed  mov     rdi, rcx
0x1801781f0  xor     esi, esi
0x1801781f2  cmp     [rcx+38h], rsi
0x1801781f6  jnz     short loc_18017821B
0x1801781f8  mov     qword ptr [rsp+0C0h+dwDesiredAccess], rsi; struct IRequestContext *
0x1801781fd  mov     r9d, 54Fh; unsigned int
0x180178203  lea     r8, a525; "525"
0x18017820a  mov     edx, 20Dh; unsigned int
0x18017820f  lea     rcx, aOnecoreAdminWm_0; "onecore\\admin\\wmi\\wmx\\service\\iisl"...
0x180178216  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18017821b  mov     rcx, [rdi+48h]
0x18017821f  mov     rax, [rcx]
0x180178222  mov     rax, [rax+30h]
0x180178226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017822b  mov     r15, rax
0x18017822e  mov     rcx, [rdi+30h]
0x180178232  mov     r13, [rcx+0B0h]
0x180178239  mov     rcx, [rdi+48h]
0x18017823d  mov     rdx, [rcx]
0x180178240  mov     rax, [rdx+10h]
0x180178244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180178249  mov     rcx, rax
0x18017824c  test    rax, rax
0x18017824f  jnz     short loc_1801782A0
0x180178251  lea     rax, WPP_GLOBAL_Control
0x180178258  mov     rcx, cs:WPP_GLOBAL_Control
0x18017825f  cmp     rcx, rax
0x180178262  jz      short loc_180178282
0x180178264  test    dword ptr [rcx+1Ch], 400h
0x18017826b  jz      short loc_180178282
0x18017826d  mov     edx, 24h ; '$'
0x180178272  lea     r8, WPP_d6cffbb67e90322691f38b07bd2f6a1e_Traceguids
0x180178279  mov     rcx, [rcx+10h]
0x18017827d  call    WPP_SF_
0x180178282  lea     rax, aFailedToRetrie_0; "Failed to retrieve IIS connection objec"...
0x180178289  mov     edx, 1F4h
0x18017828e  mov     qword ptr [rsp+0C0h+bInheritHandle], rax
0x180178293  mov     [rsp+0C0h+dwDesiredAccess], 0Eh
0x18017829b  jmp     loc_180178A84
0x1801782a0  mov     rax, [rdi+38h]
0x1801782a4  mov     r14, [rax]
0x1801782a7  mov     rax, [rcx]
0x1801782aa  mov     rax, [rax+10h]
0x1801782ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801782b3  mov     r12, rax
0x1801782b6  mov     rcx, [rax]
0x1801782b9  mov     rax, [rcx]
0x1801782bc  mov     rdx, r13
0x1801782bf  mov     rcx, r12
0x1801782c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801782c7  test    rax, rax
0x1801782ca  jnz     loc_18017854E
0x1801782d0  xor     r8d, r8d
0x1801782d3  xor     edx, edx
0x1801782d5  lea     ecx, [rax+28h]
0x1801782d8  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x1801782dd  mov     rbx, rax
0x1801782e0  mov     [rbp+57h+arg_0], rax
0x1801782e4  test    rax, rax
0x1801782e7  jz      loc_180178511
0x1801782ed  lea     rax, ??_7IISUser@@6B@; const IISUser::`vftable'
0x1801782f4  mov     [rbx], rax
0x1801782f7  mov     dword ptr [rbx+8], 1
0x1801782fe  mov     [rbx+10h], rsi
0x180178302  mov     [rbx+18h], rsi
0x180178306  mov     [rbx+20h], rsi
0x18017830a  test    rbx, rbx
0x18017830d  jz      loc_180178511
0x180178313  mov     [rbp+57h+var_78], esi
0x180178316  lea     rax, ??_7CErrorContext@@6B@; const CErrorContext::`vftable'
0x18017831d  mov     [rbp+57h+var_80], rax
0x180178321  mov     [rbp+57h+var_70], esi
0x180178324  mov     [rbp+57h+var_6C], 0FFFFFFFFh
0x18017832b  lea     rax, Class
0x180178332  mov     [rbp+57h+var_60], rax
0x180178336  mov     [rbp+57h+var_58], rax
0x18017833a  mov     [rbp+57h+var_50], rax
0x18017833e  mov     [rbp+57h+var_48], rax
0x180178342  mov     [rbp+57h+var_68], sil
0x180178346  lock inc [rbp+57h+var_78]
0x18017834a  add     r14, 82h
0x180178351  mov     r9b, [r14]; bool
0x180178354  mov     r8, r15; struct IHttpUser *
0x180178357  lea     rdx, [rbp+57h+var_80]; struct IRequestContext *
0x18017835b  mov     rcx, rbx; this
0x18017835e  call    ?Initialize@IISUser@@QEAA_NAEAVIRequestContext@@PEAVIHttpUser@@_N@Z; IISUser::Initialize(IRequestContext &,IHttpUser *,bool)
0x180178363  test    al, al
0x180178365  jnz     short loc_1801783D9
0x180178367  lea     rax, WPP_GLOBAL_Control
0x18017836e  mov     rcx, cs:WPP_GLOBAL_Control
0x180178375  cmp     rcx, rax
0x180178378  jz      short loc_180178398
0x18017837a  test    dword ptr [rcx+1Ch], 200h
0x180178381  jz      short loc_180178398
0x180178383  mov     edx, 26h ; '&'
0x180178388  lea     r8, WPP_d6cffbb67e90322691f38b07bd2f6a1e_Traceguids
0x18017838f  mov     rcx, [rcx+10h]
0x180178393  call    WPP_SF_
0x180178398  lea     rcx, [rbp+57h+var_80]; this
0x18017839c  call    ?GetErrorCode@CErrorContext@@UEBAKXZ; CErrorContext::GetErrorCode(void)
0x1801783a1  mov     edx, 1F4h; unsigned __int16
0x1801783a6  lea     rcx, aFailedToInitia; "Failed to initialize IIS user object"
0x1801783ad  mov     qword ptr [rsp+0C0h+bInheritHandle], rcx; unsigned __int16 *
0x1801783b2  mov     [rsp+0C0h+dwDesiredAccess], eax; unsigned int
0x1801783b6  xor     r9d, r9d; char *
0x1801783b9  xor     r8d, r8d; unsigned int
0x1801783bc  mov     rcx, rdi; this
0x1801783bf  call    ?SendHttpError@IISListenerRequest@@AEAAKGKPEBDKPEBG1@Z; IISListenerRequest::SendHttpError(ushort,ulong,char const *,ulong,ushort const *,ushort const *)
0x1801783c4  mov     rax, [rbx]
0x1801783c7  mov     rcx, rbx
0x1801783ca  mov     rax, [rax+38h]
0x1801783ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801783d3  nop
0x1801783d4  jmp     loc_180178A92
0x1801783d9  mov     dword ptr [rbp+57h+arg_0], esi
0x1801783dc  lea     rax, [rbp+57h+arg_0]
0x1801783e0  mov     [rbp+57h+arg_10], rax
0x1801783e4  xor     r8d, r8d
0x1801783e7  xor     edx, edx
0x1801783e9  lea     ecx, [rdx+10h]
0x1801783ec  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x1801783f1  mov     rsi, rax
0x1801783f4  mov     [rbp+57h+arg_18], rax
0x1801783f8  test    rax, rax
0x1801783fb  jz      short loc_18017841C
0x1801783fd  lea     rax, ??_7IISConnectionContext@@6B@; const IISConnectionContext::`vftable'
0x180178404  mov     [rsi], rax
0x180178407  mov     [rsi+8], rbx
0x18017840b  mov     rax, [rbx]
0x18017840e  mov     rcx, rbx
0x180178411  mov     rax, [rax+30h]
0x180178415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017841a  jmp     short loc_18017841E
0x18017841c  xor     esi, esi
0x18017841e  mov     rax, [rbx]
0x180178421  mov     rcx, rbx
0x180178424  mov     rax, [rax+38h]
0x180178428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017842d  test    rsi, rsi
0x180178430  jnz     short loc_18017848D
0x180178432  lea     rax, WPP_GLOBAL_Control
0x180178439  mov     rcx, cs:WPP_GLOBAL_Control
0x180178440  cmp     rcx, rax
0x180178443  jz      short loc_180178461
0x180178445  test    dword ptr [rcx+1Ch], 200h
0x18017844c  jz      short loc_180178461
0x18017844e  lea     edx, [rsi+27h]
0x180178451  lea     r8, WPP_d6cffbb67e90322691f38b07bd2f6a1e_Traceguids
0x180178458  mov     rcx, [rcx+10h]
0x18017845c  call    WPP_SF_
0x180178461  mov     edx, 1F4h; unsigned __int16
0x180178466  lea     rax, aFailedToCreate_2; "Failed to create IIS Connection context"
0x18017846d  mov     qword ptr [rsp+0C0h+bInheritHandle], rax; unsigned __int16 *
0x180178472  mov     [rsp+0C0h+dwDesiredAccess], 0Eh; unsigned int
0x18017847a  xor     r9d, r9d; char *
0x18017847d  xor     r8d, r8d; unsigned int
0x180178480  mov     rcx, rdi; this
0x180178483  call    ?SendHttpError@IISListenerRequest@@AEAAKGKPEBDKPEBG1@Z; IISListenerRequest::SendHttpError(ushort,ulong,char const *,ulong,ushort const *,ushort const *)
0x180178488  jmp     loc_1801783D4
0x18017848d  mov     rax, [r12]
0x180178491  mov     r8, r13
0x180178494  mov     rdx, rsi
0x180178497  mov     rcx, r12
0x18017849a  mov     rax, [rax+8]
0x18017849e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801784a3  mov     ebx, eax
0x1801784a5  xor     r13d, r13d
0x1801784a8  test    eax, eax
0x1801784aa  jns     short loc_18017850F
0x1801784ac  lea     rax, WPP_GLOBAL_Control
0x1801784b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1801784ba  cmp     rcx, rax
0x1801784bd  jz      short loc_1801784DF
0x1801784bf  test    dword ptr [rcx+1Ch], 200h
0x1801784c6  jz      short loc_1801784DF
0x1801784c8  lea     edx, [r13+28h]
0x1801784cc  mov     r9d, ebx
0x1801784cf  lea     r8, WPP_d6cffbb67e90322691f38b07bd2f6a1e_Traceguids
0x1801784d6  mov     rcx, [rcx+10h]
0x1801784da  call    WPP_SF_d
0x1801784df  mov     edx, 1F4h; unsigned __int16
0x1801784e4  lea     rax, aFailedToSetIis; "Failed to set IIS module context"
0x1801784eb  mov     qword ptr [rsp+0C0h+bInheritHandle], rax; unsigned __int16 *
0x1801784f0  mov     [rsp+0C0h+dwDesiredAccess], ebx; unsigned int
0x1801784f4  xor     r9d, r9d; char *
0x1801784f7  xor     r8d, r8d; unsigned int
0x1801784fa  mov     rcx, rdi; this
0x1801784fd  call    ?SendHttpError@IISListenerRequest@@AEAAKGKPEBDKPEBG1@Z; IISListenerRequest::SendHttpError(ushort,ulong,char const *,ulong,ushort const *,ushort const *)
0x180178502  mov     rcx, rsi; this
0x180178505  call    ??_GIISConnectionContext@@QEAAPEAXI@Z; IISConnectionContext::`scalar deleting destructor'(uint)
0x18017850a  jmp     loc_1801783D4
0x18017850f  jmp     short loc_180178558
0x180178511  lea     rax, WPP_GLOBAL_Control
0x180178518  mov     rcx, cs:WPP_GLOBAL_Control
0x18017851f  cmp     rcx, rax
0x180178522  jz      short loc_180178542
0x180178524  test    dword ptr [rcx+1Ch], 200h
0x18017852b  jz      short loc_180178542
0x18017852d  mov     edx, 25h ; '%'
0x180178532  lea     r8, WPP_d6cffbb67e90322691f38b07bd2f6a1e_Traceguids
0x180178539  mov     rcx, [rcx+10h]
0x18017853d  call    WPP_SF_
0x180178542  lea     rax, aFailedToCreate_3; "Failed to create IIS User object"
0x180178549  jmp     loc_180178289
0x18017854e  add     r14, 82h
0x180178555  xor     r13d, r13d
0x180178558  lea     rsi, [rdi+0D0h]
0x18017855f  mov     [rsi], r13
0x180178562  mov     rax, [r15]
0x180178565  mov     rcx, r15
0x180178568  mov     rax, [rax+20h]
0x18017856c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180178571  mov     r12, rax
0x180178574  test    rax, rax
0x180178577  jz      loc_18017861E
0x18017857d  cmp     [r14], r13b
0x180178580  jnz     loc_18017861E
0x180178586  call    cs:__imp_GetCurrentProcess
0x18017858c  mov     rbx, rax
0x18017858f  call    cs:__imp_GetCurrentProcess
0x180178595  mov     [rsp+0C0h+dwOptions], 2; dwOptions
0x18017859d  mov     [rsp+0C0h+bInheritHandle], r13d; bInheritHandle
0x1801785a2  mov     [rsp+0C0h+dwDesiredAccess], r13d; dwDesiredAccess
0x1801785a7  mov     r9, rsi; lpTargetHandle
0x1801785aa  mov     r8, rbx; hTargetProcessHandle
0x1801785ad  mov     rdx, r12; hSourceHandle
0x1801785b0  mov     rcx, rax; hSourceProcessHandle
0x1801785b3  call    cs:__imp_DuplicateHandle
0x1801785b9  test    eax, eax
0x1801785bb  jnz     short loc_18017861E
0x1801785bd  lea     rax, WPP_GLOBAL_Control
0x1801785c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1801785cb  cmp     rcx, rax
0x1801785ce  jz      short loc_1801785FE
0x1801785d0  test    dword ptr [rcx+1Ch], 200h
0x1801785d7  jz      short loc_1801785FE
0x1801785d9  call    cs:__imp_GetLastError
0x1801785df  mov     edx, 29h ; ')'
0x1801785e4  mov     r9d, eax
0x1801785e7  lea     r8, WPP_d6cffbb67e90322691f38b07bd2f6a1e_Traceguids
0x1801785ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1801785f5  mov     rcx, [rcx+10h]
0x1801785f9  call    WPP_SF_d
0x1801785fe  call    cs:__imp_GetLastError
0x180178604  lea     rcx, aFailureIdentif; "Failure identifying IIS user"
0x18017860b  mov     edx, 1F4h
0x180178610  mov     qword ptr [rsp+0C0h+bInheritHandle], rcx
0x180178615  mov     [rsp+0C0h+dwDesiredAccess], eax
0x180178619  jmp     loc_180178A84
0x18017861e  mov     r8, [rdi+50h]
0x180178622  lea     r14, [rdi+0D8h]
0x180178629  movzx   r9d, word ptr [r8+40h]
0x18017862e  shr     r9, 1; unsigned __int64
0x180178631  mov     r8, [r8+48h]; unsigned __int16 *
0x180178635  mov     edx, 800h; unsigned __int64
0x18017863a  mov     rcx, r14; unsigned __int16 *
0x18017863d  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180178642  test    eax, eax
0x180178644  jns     short loc_180178695
0x180178646  lea     rax, WPP_GLOBAL_Control
0x18017864d  mov     rcx, cs:WPP_GLOBAL_Control
0x180178654  cmp     rcx, rax
0x180178657  jz      short loc_180178677
0x180178659  test    dword ptr [rcx+1Ch], 400h
0x180178660  jz      short loc_180178677
0x180178662  mov     edx, 2Ah ; '*'
0x180178667  lea     r8, WPP_d6cffbb67e90322691f38b07bd2f6a1e_Traceguids
0x18017866e  mov     rcx, [rcx+10h]
0x180178672  call    WPP_SF_
0x180178677  mov     edx, 190h
0x18017867c  lea     rax, aIisRequestHttp; "IIS request HTTP url is too long"
0x180178683  mov     qword ptr [rsp+0C0h+bInheritHandle], rax
0x180178688  mov     [rsp+0C0h+dwDesiredAccess], 0Dh
0x180178690  jmp     loc_180178A84
0x180178695  lea     rbx, [rdi+80h]
0x18017869c  xorps   xmm0, xmm0
0x18017869f  movups  xmmword ptr [rbx], xmm0
0x1801786a2  movups  xmmword ptr [rbx+10h], xmm0
0x1801786a6  movups  xmmword ptr [rbx+20h], xmm0
0x1801786aa  lea     r12, [rdi+0B0h]
0x1801786b1  movups  xmmword ptr [r12], xmm0
0x1801786b6  movups  xmmword ptr [r12+10h], xmm0
0x1801786bc  mov     rax, [r15]
0x1801786bf  mov     rcx, r15
0x1801786c2  mov     rax, [rax]
0x1801786c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801786ca  mov     [rbx], rax
0x1801786cd  mov     rax, [rsi]
0x1801786d0  mov     [rdi+98h], rax
0x1801786d7  mov     rax, [r15]
  ... truncated ...
```
