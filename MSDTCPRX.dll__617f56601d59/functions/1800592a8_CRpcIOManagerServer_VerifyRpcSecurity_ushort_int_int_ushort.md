# CRpcIOManagerServer::VerifyRpcSecurity(ushort * *,int *,int *,ushort *)

- ea: `0x1800592a8`
- end: `0x1800594da`
- name: `?VerifyRpcSecurity@CRpcIOManagerServer@@AEAAJPEAPEAGPEAH1PEAG@Z`
- size: `562`
- prototype: `__int64 __fastcall(CRpcIOManagerServer *__hidden this, unsigned __int16 **, int *, int *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18005743c`
- `0x180058304`

## callees

- `0x180003cf0`
- `0x180006764`
- `0x18000d000`
- `0x18000d5f4`
- `0x180054968`
- `0x1800592a8`
- `0x180070f24`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800594b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800594b4`
- `RPCRT4!RpcBindingInqAuthClientExW` at `0x180059348`
- `RPCRT4!RpcBindingInqAuthClientExW` at `0x180059348`

## string_xrefs

- `0x18005936a`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x1800593c9`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x18005941f`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180059314`: `CRpcIOManagerServer::VerifyRpcSecurity (com\complus\dtc\dtc\cm\src\iomgrsrv.cpp@740): pwszHostName != NULL`
- `0x180059375`: `CRpcIOManagerServer::VerifyRpcSecurity`
- `0x1800593d0`: `CRpcIOManagerServer::VerifyRpcSecurity`
- `0x180059426`: `CRpcIOManagerServer::VerifyRpcSecurity`

## pseudocode

```c
__int64 __fastcall CRpcIOManagerServer::VerifyRpcSecurity(
        CRpcIOManagerServer *this,
        unsigned __int16 **a2,
        int *a3,
        int *a4,
        unsigned __int16 *a5)
{
  RPC_STATUS v9; // ebx
  int v10; // ecx
  int ClientAuthInfo; // ebx
  void *v12; // r9
  unsigned int *AuthzSvc; // [rsp+28h] [rbp-49h]
  unsigned int *AuthzSvca; // [rsp+28h] [rbp-49h]
  unsigned int v16; // [rsp+50h] [rbp-21h] BYREF
  unsigned int AuthnSvc; // [rsp+54h] [rbp-1Dh] BYREF
  unsigned int AuthnLevel; // [rsp+58h] [rbp-19h] BYREF
  RPC_AUTHZ_HANDLE Privs; // [rsp+60h] [rbp-11h] BYREF
  LPVOID pv[2]; // [rsp+68h] [rbp-9h] BYREF
  unsigned __int16 *v21; // [rsp+78h] [rbp+7h]

  *a2 = 0;
  *a3 = 0;
  Privs = 0;
  AuthnLevel = 0;
  AuthnSvc = 0;
  v16 = 0;
  *a4 = 0;
  if ( !a5 )
    DtcInternalErrorW(
      L"CRpcIOManagerServer::VerifyRpcSecurity (com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp@740): pwszHostName != NULL");
  v9 = RpcBindingInqAuthClientExW(0, &Privs, 0, &AuthnLevel, &AuthnSvc, &v16, 0);
  if ( v9 == 1746 )
  {
    LODWORD(AuthzSvc) = 1746;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      752,
      L"CRpcIOManagerServer::VerifyRpcSecurity",
      AuthzSvc,
      L"Received Unauthenticated Rpc Call");
    if ( *(_DWORD *)(*((_QWORD *)this + 11) + 40LL) == 2 )
    {
      ClientAuthInfo = 0;
      *a4 = 1;
      return (unsigned int)ClientAuthInfo;
    }
    v10 = 1746;
  }
  else
  {
    if ( !v9 )
    {
      ClientAuthInfo = CRpcIOManagerServer::GetClientAuthInfo((PSID *)this, a2, a3, a4);
      if ( ClientAuthInfo >= 0 )
        return (unsigned int)ClientAuthInfo;
      LODWORD(AuthzSvc) = ClientAuthInfo;
      TraceStringInline(
        1,
        1,
        L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
        790,
        L"CRpcIOManagerServer::VerifyRpcSecurity",
        AuthzSvc,
        L"GetClientSPN call failed");
      goto LABEL_12;
    }
    LODWORD(AuthzSvc) = v9;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      777,
      L"CRpcIOManagerServer::VerifyRpcSecurity",
      AuthzSvc,
      L"RpcBindingInqAuthClient call failed");
    v10 = v9;
  }
  ClientAuthInfo = RpcStatusToHresult(v10);
LABEL_12:
  if ( ClientAuthInfo < 0 )
  {
    v21 = 0;
    *(_OWORD *)pv = 0;
    MakeStringW((unsigned __int16 **)pv, L"%X", (unsigned int)ClientAuthInfo);
    v21 = *a2;
    LODWORD(AuthzSvca) = 0;
    pv[1] = a5;
    DtcWriteToEventLoggerExW(2, 3, 2147488526LL, v12, 3u, (size_t)AuthzSvca, (unsigned __int16 **)pv, 0, 1);
    CoTaskMemFree(pv[0]);
  }
  return (unsigned int)ClientAuthInfo;
}

```

## disassembly

```asm
0x1800592a8  push    rbp
0x1800592aa  push    rbx
0x1800592ab  push    rsi
0x1800592ac  push    rdi
0x1800592ad  push    r12
0x1800592af  push    r14
0x1800592b1  push    r15
0x1800592b3  lea     rbp, [rsp-1Fh]
0x1800592b8  sub     rsp, 90h
0x1800592bf  mov     rax, cs:__security_cookie
0x1800592c6  xor     rax, rsp
0x1800592c9  mov     [rbp+4Fh+var_40], rax
0x1800592cd  mov     r12, [rbp+4Fh+arg_20]
0x1800592d1  mov     rsi, r9
0x1800592d4  mov     qword ptr [rdx], 0
0x1800592db  mov     rdi, r8
0x1800592de  mov     dword ptr [r8], 0
0x1800592e5  mov     r15, rdx
0x1800592e8  mov     [rbp+4Fh+Privs], 0
0x1800592f0  mov     r14, rcx
0x1800592f3  mov     [rbp+4Fh+AuthnLevel], 0
0x1800592fa  mov     [rbp+4Fh+var_6C], 0
0x180059301  mov     [rbp+4Fh+var_70], 0
0x180059308  mov     dword ptr [r9], 0
0x18005930f  test    r12, r12
0x180059312  jnz     short loc_180059321
0x180059314  lea     rcx, aCrpciomanagers_7; "CRpcIOManagerServer::VerifyRpcSecurity "...
0x18005931b  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180059321  lea     rax, [rbp+4Fh+var_70]
0x180059325  mov     [rsp+0C0h+Flags], 0; Flags
0x18005932d  mov     [rsp+0C0h+AuthzSvc], rax; AuthzSvc
0x180059332  lea     r9, [rbp+4Fh+AuthnLevel]; AuthnLevel
0x180059336  lea     rax, [rbp+4Fh+var_6C]
0x18005933a  xor     r8d, r8d; ServerPrincName
0x18005933d  lea     rdx, [rbp+4Fh+Privs]; Privs
0x180059341  mov     [rsp+0C0h+AuthnSvc], rax; AuthnSvc
0x180059346  xor     ecx, ecx; ClientBinding
0x180059348  call    cs:__imp_RpcBindingInqAuthClientExW
0x18005934e  mov     ecx, 6D2h
0x180059353  mov     ebx, eax
0x180059355  cmp     eax, ecx
0x180059357  jnz     short loc_1800593B4
0x180059359  lea     rax, aReceivedUnauth; "Received Unauthenticated Rpc Call"
0x180059360  mov     edi, 1
0x180059365  mov     qword ptr [rsp+0C0h+Flags], rax
0x18005936a  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180059371  mov     dword ptr [rsp+0C0h+AuthzSvc], ecx
0x180059375  lea     rax, aCrpciomanagers_22; "CRpcIOManagerServer::VerifyRpcSecurity"
0x18005937c  mov     ecx, edi
0x18005937e  mov     [rsp+0C0h+AuthnSvc], rax
0x180059383  mov     r9d, 2F0h
0x180059389  mov     edx, edi
0x18005938b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180059390  mov     rax, [r14+58h]
0x180059394  cmp     dword ptr [rax+28h], 2
0x180059398  jz      short loc_1800593AB
0x18005939a  mov     ecx, 6D2h; int
0x18005939f  call    ?RpcStatusToHresult@@YAJJ@Z; RpcStatusToHresult(long)
0x1800593a4  mov     ebx, eax
0x1800593a6  jmp     loc_180059445
0x1800593ab  xor     ebx, ebx
0x1800593ad  mov     [rsi], edi
0x1800593af  jmp     loc_1800594BA
0x1800593b4  test    ebx, ebx
0x1800593b6  jz      short loc_1800593F3
0x1800593b8  lea     rax, aRpcbindinginqa; "RpcBindingInqAuthClient call failed"
0x1800593bf  mov     edi, 1
0x1800593c4  mov     qword ptr [rsp+0C0h+Flags], rax
0x1800593c9  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x1800593d0  lea     rax, aCrpciomanagers_22; "CRpcIOManagerServer::VerifyRpcSecurity"
0x1800593d7  mov     dword ptr [rsp+0C0h+AuthzSvc], ebx
0x1800593db  mov     r9d, 309h
0x1800593e1  mov     [rsp+0C0h+AuthnSvc], rax
0x1800593e6  mov     edx, edi
0x1800593e8  mov     ecx, edi
0x1800593ea  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800593ef  mov     ecx, ebx
0x1800593f1  jmp     short loc_18005939F
0x1800593f3  mov     r9, rsi; int *
0x1800593f6  mov     r8, rdi; int *
0x1800593f9  mov     rdx, r15; unsigned __int16 **
0x1800593fc  mov     rcx, r14; this
0x1800593ff  call    ?GetClientAuthInfo@CRpcIOManagerServer@@AEAAJPEAPEAGPEAH1@Z; CRpcIOManagerServer::GetClientAuthInfo(ushort * *,int *,int *)
0x180059404  mov     ebx, eax
0x180059406  test    eax, eax
0x180059408  jns     loc_1800594BA
0x18005940e  lea     rax, aGetclientspnCa; "GetClientSPN call failed"
0x180059415  mov     edi, 1
0x18005941a  mov     qword ptr [rsp+0C0h+Flags], rax
0x18005941f  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180059426  lea     rax, aCrpciomanagers_22; "CRpcIOManagerServer::VerifyRpcSecurity"
0x18005942d  mov     dword ptr [rsp+0C0h+AuthzSvc], ebx
0x180059431  mov     r9d, 316h
0x180059437  mov     [rsp+0C0h+AuthnSvc], rax
0x18005943c  mov     edx, edi
0x18005943e  mov     ecx, edi
0x180059440  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180059445  test    ebx, ebx
0x180059447  jns     short loc_1800594BA
0x180059449  xorps   xmm0, xmm0
0x18005944c  lea     rdx, asc_1800B060C; "%X"
0x180059453  xor     eax, eax
0x180059455  lea     rcx, [rbp+4Fh+pv]; unsigned __int16 **
0x180059459  mov     r8d, ebx
0x18005945c  mov     [rbp+4Fh+var_48], rax
0x180059460  movups  xmmword ptr [rbp+4Fh+pv], xmm0
0x180059464  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x180059469  mov     rax, [r15]
0x18005946c  mov     r8d, 3
0x180059472  mov     [rsp+0C0h+var_80], edi; int
0x180059476  mov     edx, r8d; unsigned __int16
0x180059479  mov     [rsp+0C0h+Src], 0; Src
0x180059482  mov     [rbp+4Fh+var_48], rax
0x180059486  lea     rax, [rbp+4Fh+pv]
0x18005948a  mov     qword ptr [rsp+0C0h+Flags], rax; unsigned __int16 **
0x18005948f  lea     ecx, [r8-1]; unsigned __int16
0x180059493  mov     dword ptr [rsp+0C0h+AuthzSvc], 0; Size
0x18005949b  mov     word ptr [rsp+0C0h+AuthnSvc], r8w; unsigned __int16
0x1800594a1  mov     r8d, 8000130Eh; unsigned int
0x1800594a7  mov     [rbp+4Fh+pv+8], r12
0x1800594ab  call    ?DtcWriteToEventLoggerExW@@YAJGGKPEAXGKPEAPEBG0H@Z; DtcWriteToEventLoggerExW(ushort,ushort,ulong,void *,ushort,ulong,ushort const * *,void *,int)
0x1800594b0  mov     rcx, [rbp+4Fh+pv]; pv
0x1800594b4  call    cs:__imp_CoTaskMemFree
0x1800594ba  mov     eax, ebx
0x1800594bc  mov     rcx, [rbp+4Fh+var_40]
0x1800594c0  xor     rcx, rsp; StackCookie
0x1800594c3  call    __security_check_cookie
0x1800594c8  add     rsp, 90h
0x1800594cf  pop     r15
0x1800594d1  pop     r14
0x1800594d3  pop     r12
0x1800594d5  pop     rdi
0x1800594d6  pop     rsi
0x1800594d7  pop     rbx
0x1800594d8  pop     rbp
0x1800594d9  retn
```
