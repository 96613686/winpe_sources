# CUninstallCbsClient::Initialize(wchar_t const * const,wchar_t const * const,wchar_t const * const,wchar_t const * const,wchar_t const * const,ICbsUIHandler *)

- ea: `0x18007c1b4`
- end: `0x18007c4fb`
- name: `?Initialize@CUninstallCbsClient@@QEAAJQEB_W0000PEAUICbsUIHandler@@@Z`
- size: `839`
- prototype: `int(CUninstallCbsClient *__hidden this, const wchar_t *const, const wchar_t *const, const wchar_t *const, const wchar_t *const, const wchar_t *const, struct ICbsUIHandler *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007ba20`

## callees

- `0x180024c80`
- `0x180026c90`
- `0x18002d2b0`
- `0x180041bc0`
- `0x180041c90`
- `0x180042bac`
- `0x1800504d0`
- `0x18007c1b4`
- `0x18009e020`

## import_xrefs

- `KERNEL32!Sleep` at `0x18007c295`
- `KERNEL32!Sleep` at `0x18007c295`
- `ntdll!RtlRaiseStatus` at `0x18007c309`
- `ntdll!RtlRaiseStatus` at `0x18007c309`
- `OLE32!CoSetProxyBlanket` at `0x18007c2e0`
- `OLE32!CoSetProxyBlanket` at `0x18007c2e0`
- `OLE32!CoCreateInstance` at `0x18007c262`
- `OLE32!CoCreateInstance` at `0x18007c262`
- `OLE32!CoGetMalloc` at `0x18007c204`
- `OLE32!CoGetMalloc` at `0x18007c204`

## string_xrefs

- `0x18007c452`: `UninstallClient`
- `0x18007c216`: `Failed getting COM allocator`
- `0x18007c33f`: `Failed to create offline session from external stack path %ws.`
- `0x18007c3d6`: `Fail to get offline servicing stack path.`
- `0x18007c384`: `Failed to create offline windir`
- `0x18007c284`: `Unable to create session classID - waiting for a second and trying again`
- `0x18007c2a6`: `Failed to create session classID`
- `0x18007c484`: `Failed initiating Uninstall session`

## pseudocode

```c
__int64 __fastcall CUninstallCbsClient::Initialize(
        CUninstallCbsClient *this,
        const wchar_t *const a2,
        const wchar_t *a3,
        const wchar_t *const a4,
        const wchar_t *a5,
        const wchar_t *const a6,
        struct ICbsUIHandler *a7)
{
  LPMALLOC *InitPointer; // rax
  HRESULT Malloc; // eax
  unsigned int v11; // ebx
  unsigned int v12; // r14d
  LPVOID *ppv; // rdi
  HRESULT Instance; // eax
  HRESULT v15; // eax
  struct ICbsSession **v16; // rax
  int OfflineSessionFromExternalStack; // eax
  int v18; // eax
  struct ICbsSession **v19; // rax
  int OfflineSessionFromStackInImage; // eax
  __int64 (__fastcall ***v21)(LPVOID, GUID *, __int64); // rdi
  __int64 (__fastcall *v22)(LPVOID, GUID *, __int64); // rbx
  __int64 v23; // rax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  wchar_t *v29; // [rsp+40h] [rbp-20h] BYREF
  __int64 v30; // [rsp+48h] [rbp-18h] BYREF

  v30 = 0;
  InitPointer = (LPMALLOC *)Windows::AutoComPtr<ICbsIdentity>::GetInitPointer((char *)this + 16);
  Malloc = CoGetMalloc(1u, InitPointer);
  v11 = Malloc;
  if ( Malloc < 0 )
  {
    CBSWdsLog(0x4000000, (unsigned int)Malloc, 1, "Failed getting COM allocator");
    goto LABEL_32;
  }
  if ( !a5 )
  {
    v12 = 0;
    ppv = (LPVOID *)((char *)this + 8);
    while ( 1 )
    {
      if ( *ppv )
        RtlRaiseStatus(-1073741595);
      Instance = CoCreateInstance(
                   &GUID_752073a1_23f2_4396_85f0_8fdb879ed0ed,
                   0,
                   0x15u,
                   &GUID_75207391_23f2_4396_85f0_8fdb879ed0ed,
                   ppv);
      v11 = Instance;
      if ( Instance >= 0 )
        break;
      if ( v12 >= 0xA )
      {
        CBSWdsLog(0x4000000, (unsigned int)Instance, 1, "Failed to create session classID");
        goto LABEL_32;
      }
      CBSWdsLog(
        0x4000000,
        (unsigned int)Instance,
        1,
        "Unable to create session classID - waiting for a second and trying again");
      Sleep(0x3E8u);
      ++v12;
    }
    v15 = CoSetProxyBlanket((IUnknown *)*ppv, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 5u, 3u, 0, 0);
    v11 = v15;
    if ( v15 < 0 )
    {
      CBSWdsLog(0x4000000, (unsigned int)v15, 1, "Failed to set proxy blanket.");
      goto LABEL_32;
    }
    goto LABEL_23;
  }
  if ( a3 )
  {
    ppv = (LPVOID *)((char *)this + 8);
    v16 = (struct ICbsSession **)Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(ppv);
    OfflineSessionFromExternalStack = CbsOfflineUtil::CbsCreateOfflineSessionFromExternalStack(
                                        (CbsOfflineUtil *)&vCbsOfflineUtil,
                                        a3,
                                        v16);
    v11 = OfflineSessionFromExternalStack;
    if ( OfflineSessionFromExternalStack < 0 )
    {
      CBSWdsLog(
        0x4000000,
        (unsigned int)OfflineSessionFromExternalStack,
        1,
        "Failed to create offline session from external stack path %ws.",
        a3);
      goto LABEL_32;
    }
    goto LABEL_23;
  }
  v29 = 0;
  v18 = SczAllocFromSz(&v29, a5);
  v11 = v18;
  if ( v18 < 0 )
  {
    CBSWdsLog(0x4000000, (unsigned int)v18, 1, "Failed to create offline windir");
LABEL_19:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v29);
    goto LABEL_32;
  }
  ppv = (LPVOID *)((char *)this + 8);
  v19 = (struct ICbsSession **)Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(ppv);
  OfflineSessionFromStackInImage = CbsOfflineUtil::CbsCreateOfflineSessionFromStackInImage(
                                     (CbsOfflineUtil *)&vCbsOfflineUtil,
                                     1,
                                     v29,
                                     v19);
  v11 = OfflineSessionFromStackInImage;
  if ( OfflineSessionFromStackInImage < 0 )
  {
    CBSWdsLog(0x4000000, (unsigned int)OfflineSessionFromStackInImage, 1, "Fail to get offline servicing stack path.");
    goto LABEL_19;
  }
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v29);
LABEL_23:
  v21 = (__int64 (__fastcall ***)(LPVOID, GUID *, __int64))*ppv;
  v22 = **v21;
  v23 = Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&v30);
  v24 = v22(v21, &GUID_f112757a_565b_4260_bd05_9fa34417349a, v23);
  v11 = v24;
  if ( v24 >= 0 )
  {
    if ( a7
      && (v25 = (*(__int64 (__fastcall **)(__int64, struct ICbsUIHandler *))(*(_QWORD *)v30 + 128LL))(v30, a7),
          v11 = v25,
          v25 < 0) )
    {
      CBSWdsLog(0x4000000, (unsigned int)v25, 1, "Failed to register progress bar handler");
    }
    else
    {
      v26 = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)v30 + 152LL))(
              v30,
              0x1000000,
              L"UninstallClient",
              0,
              a5,
              0);
      v11 = v26;
      if ( v26 >= 0 )
      {
        v27 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v30 + 184LL))(v30, 4);
        v11 = v27;
        if ( v27 < 0 )
          CBSWdsLog(0x4000000, (unsigned int)v27, 1, "Failed to set enhanced options");
      }
      else
      {
        CBSWdsLog(0x4000000, (unsigned int)v26, 1, "Failed initiating Uninstall session");
      }
    }
  }
  else
  {
    CBSWdsLog(0x4000000, (unsigned int)v24, 1, "Failed querying ICbsSession10 interface.");
  }
LABEL_32:
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  return v11;
}

```

## disassembly

```asm
0x18007c1b4  mov     [rsp-28h+arg_8], rbx
0x18007c1b9  mov     [rsp-28h+arg_18], rsi
0x18007c1be  push    rbp
0x18007c1bf  push    rdi
0x18007c1c0  push    r12
0x18007c1c2  push    r14
0x18007c1c4  push    r15
0x18007c1c6  mov     rbp, rsp
0x18007c1c9  sub     rsp, 60h
0x18007c1cd  mov     rax, cs:__security_cookie
0x18007c1d4  xor     rax, rsp
0x18007c1d7  mov     [rbp+var_10], rax
0x18007c1db  mov     r15, [rbp+arg_20]
0x18007c1df  mov     rdi, rcx
0x18007c1e2  mov     r12, [rbp+arg_30]
0x18007c1e6  add     rcx, 10h
0x18007c1ea  mov     r14, r8
0x18007c1ed  mov     [rbp+var_18], 0
0x18007c1f5  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18007c1fa  mov     esi, 1
0x18007c1ff  mov     rdx, rax; ppMalloc
0x18007c202  mov     ecx, esi; dwMemContext
0x18007c204  call    cs:__imp_CoGetMalloc
0x18007c20b  nop     dword ptr [rax+rax+00h]
0x18007c210  mov     ebx, eax
0x18007c212  test    eax, eax
0x18007c214  jns     short loc_18007C22A
0x18007c216  lea     r9, aFailedGettingC; "Failed getting COM allocator"
0x18007c21d  mov     r8d, esi
0x18007c220  mov     ecx, 4000000h
0x18007c225  jmp     loc_18007C4B7
0x18007c22a  mov     esi, 4000000h
0x18007c22f  test    r15, r15
0x18007c232  jnz     loc_18007C316
0x18007c238  xor     r14d, r14d
0x18007c23b  add     rdi, 8
0x18007c23f  cmp     qword ptr [rdi], 0
0x18007c243  jnz     loc_18007C304
0x18007c249  xor     edx, edx; pUnkOuter
0x18007c24b  mov     [rsp+60h+ppv], rdi; ppv
0x18007c250  lea     r9, _GUID_75207391_23f2_4396_85f0_8fdb879ed0ed; riid
0x18007c257  lea     rcx, _GUID_752073a1_23f2_4396_85f0_8fdb879ed0ed; rclsid
0x18007c25e  lea     r8d, [rdx+15h]; dwClsContext
0x18007c262  call    cs:__imp_CoCreateInstance
0x18007c269  nop     dword ptr [rax+rax+00h]
0x18007c26e  mov     ebx, eax
0x18007c270  test    eax, eax
0x18007c272  jns     short loc_18007C2B2
0x18007c274  mov     r8d, 1
0x18007c27a  mov     edx, eax
0x18007c27c  mov     ecx, esi
0x18007c27e  cmp     r14d, 0Ah
0x18007c282  jnb     short loc_18007C2A6
0x18007c284  lea     r9, aUnableToCreate; "Unable to create session classID - wait"...
0x18007c28b  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x18007c290  mov     ecx, 3E8h; dwMilliseconds
0x18007c295  call    cs:__imp_Sleep
0x18007c29c  nop     dword ptr [rax+rax+00h]
0x18007c2a1  inc     r14d
0x18007c2a4  jmp     short loc_18007C23F
0x18007c2a6  lea     r9, aFailedToCreate_2; "Failed to create session classID"
0x18007c2ad  jmp     loc_18007C4B9
0x18007c2b2  mov     rcx, [rdi]; pProxy
0x18007c2b5  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18007c2b8  mov     [rsp+60h+dwCapabilities], 0; dwCapabilities
0x18007c2c0  mov     r8d, edx; dwAuthzSvc
0x18007c2c3  mov     [rsp+60h+pAuthInfo], 0; pAuthInfo
0x18007c2cc  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18007c2d0  mov     [rsp+60h+dwImpLevel], 3; dwImpLevel
0x18007c2d8  mov     dword ptr [rsp+60h+ppv], 5; dwAuthnLevel
0x18007c2e0  call    cs:__imp_CoSetProxyBlanket
0x18007c2e7  nop     dword ptr [rax+rax+00h]
0x18007c2ec  mov     ebx, eax
0x18007c2ee  test    eax, eax
0x18007c2f0  jns     short loc_18007C35F
0x18007c2f2  lea     r9, aFailedToSetPro; "Failed to set proxy blanket."
0x18007c2f9  mov     r8d, 1
0x18007c2ff  jmp     loc_18007C4B5
0x18007c304  mov     ecx, 0C00000E5h; Status
0x18007c309  call    cs:__imp_RtlRaiseStatus
0x18007c310  nop     dword ptr [rax+rax+00h]
0x18007c315  int     3; Trap to Debugger
0x18007c316  test    r14, r14
0x18007c319  jz      short loc_18007C36A
0x18007c31b  add     rdi, 8
0x18007c31f  mov     rcx, rdi
0x18007c322  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18007c327  mov     r8, rax; struct ICbsSession **
0x18007c32a  lea     rcx, ?vCbsOfflineUtil@@3VCbsOfflineUtil@@A; this
0x18007c331  mov     rdx, r14; wchar_t *
0x18007c334  call    ?CbsCreateOfflineSessionFromExternalStack@CbsOfflineUtil@@UEAAJPEB_WPEAPEAUICbsSession@@@Z; CbsOfflineUtil::CbsCreateOfflineSessionFromExternalStack(wchar_t const *,ICbsSession * *)
0x18007c339  mov     ebx, eax
0x18007c33b  test    eax, eax
0x18007c33d  jns     short loc_18007C35F
0x18007c33f  lea     r9, aFailedToCreate_4; "Failed to create offline session from e"...
0x18007c346  mov     [rsp+60h+ppv], r14
0x18007c34b  mov     r8d, 1
0x18007c351  mov     edx, eax
0x18007c353  mov     ecx, esi
0x18007c355  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x18007c35a  jmp     loc_18007C4BE
0x18007c35f  mov     r14d, 1
0x18007c365  jmp     loc_18007C3EB
0x18007c36a  mov     rdx, r15
0x18007c36d  mov     [rbp+var_20], 0
0x18007c375  lea     rcx, [rbp+var_20]
0x18007c379  call    SczAllocFromSz
0x18007c37e  mov     ebx, eax
0x18007c380  test    eax, eax
0x18007c382  jns     short loc_18007C3A8
0x18007c384  lea     r9, aFailedToCreate; "Failed to create offline windir"
0x18007c38b  mov     r8d, 1
0x18007c391  mov     edx, eax
0x18007c393  mov     ecx, esi
0x18007c395  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x18007c39a  lea     rcx, [rbp+var_20]
0x18007c39e  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18007c3a3  jmp     loc_18007C4BE
0x18007c3a8  add     rdi, 8
0x18007c3ac  mov     rcx, rdi
0x18007c3af  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18007c3b4  mov     r8, [rbp+var_20]; wchar_t *
0x18007c3b8  lea     rcx, ?vCbsOfflineUtil@@3VCbsOfflineUtil@@A; this
0x18007c3bf  mov     r14d, 1
0x18007c3c5  mov     r9, rax; struct ICbsSession **
0x18007c3c8  mov     edx, r14d; int
0x18007c3cb  call    ?CbsCreateOfflineSessionFromStackInImage@CbsOfflineUtil@@UEAAJHPEB_WPEAPEAUICbsSession@@@Z; CbsOfflineUtil::CbsCreateOfflineSessionFromStackInImage(int,wchar_t const *,ICbsSession * *)
0x18007c3d0  mov     ebx, eax
0x18007c3d2  test    eax, eax
0x18007c3d4  jns     short loc_18007C3E2
0x18007c3d6  lea     r9, aFailToGetOffli; "Fail to get offline servicing stack pat"...
0x18007c3dd  mov     r8d, r14d
0x18007c3e0  jmp     short loc_18007C391
0x18007c3e2  lea     rcx, [rbp+var_20]
0x18007c3e6  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18007c3eb  mov     rdi, [rdi]
0x18007c3ee  lea     rcx, [rbp+var_18]
0x18007c3f2  mov     rax, [rdi]
0x18007c3f5  mov     rbx, [rax]
0x18007c3f8  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18007c3fd  mov     r8, rax
0x18007c400  lea     rdx, _GUID_f112757a_565b_4260_bd05_9fa34417349a
0x18007c407  mov     rax, rbx
0x18007c40a  mov     rcx, rdi
0x18007c40d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c412  mov     ebx, eax
0x18007c414  test    eax, eax
0x18007c416  jns     short loc_18007C424
0x18007c418  lea     r9, aFailedQuerying; "Failed querying ICbsSession10 interface"...
0x18007c41f  jmp     loc_18007C4B2
0x18007c424  test    r12, r12
0x18007c427  jz      short loc_18007C44E
0x18007c429  mov     rcx, [rbp+var_18]
0x18007c42d  mov     rdx, r12
0x18007c430  mov     rax, [rcx]
0x18007c433  mov     rax, [rax+80h]
0x18007c43a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c43f  mov     ebx, eax
0x18007c441  test    eax, eax
0x18007c443  jns     short loc_18007C44E
0x18007c445  lea     r9, aFailedToRegist; "Failed to register progress bar handler"
0x18007c44c  jmp     short loc_18007C4B2
0x18007c44e  mov     rcx, [rbp+var_18]
0x18007c452  lea     r8, aUninstallclien; "UninstallClient"
0x18007c459  mov     qword ptr [rsp+60h+dwImpLevel], 0
0x18007c462  xor     r9d, r9d
0x18007c465  mov     edx, 1000000h
0x18007c46a  mov     [rsp+60h+ppv], r15
0x18007c46f  mov     rax, [rcx]
0x18007c472  mov     rax, [rax+98h]
0x18007c479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c47e  mov     ebx, eax
0x18007c480  test    eax, eax
0x18007c482  jns     short loc_18007C48D
0x18007c484  lea     r9, aFailedInitiati; "Failed initiating Uninstall session"
0x18007c48b  jmp     short loc_18007C4B2
0x18007c48d  mov     rcx, [rbp+var_18]
0x18007c491  mov     edx, 4
0x18007c496  mov     rax, [rcx]
0x18007c499  mov     rax, [rax+0B8h]
0x18007c4a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c4a5  mov     ebx, eax
0x18007c4a7  test    eax, eax
0x18007c4a9  jns     short loc_18007C4BE
0x18007c4ab  lea     r9, aFailedToSetEnh; "Failed to set enhanced options"
0x18007c4b2  mov     r8d, r14d
0x18007c4b5  mov     ecx, esi
0x18007c4b7  mov     edx, eax
0x18007c4b9  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x18007c4be  mov     rcx, [rbp+var_18]
0x18007c4c2  test    rcx, rcx
0x18007c4c5  jz      short loc_18007C4D3
0x18007c4c7  mov     rax, [rcx]
0x18007c4ca  mov     rax, [rax+10h]
0x18007c4ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c4d3  mov     eax, ebx
0x18007c4d5  mov     rcx, [rbp+var_10]
0x18007c4d9  xor     rcx, rsp; StackCookie
0x18007c4dc  call    __security_check_cookie
0x18007c4e1  lea     r11, [rsp+60h+var_s0]
0x18007c4e6  mov     rbx, [r11+38h]
0x18007c4ea  mov     rsi, [r11+48h]
0x18007c4ee  mov     rsp, r11
0x18007c4f1  pop     r15
0x18007c4f3  pop     r14
0x18007c4f5  pop     r12
0x18007c4f7  pop     rdi
0x18007c4f8  pop     rbp
0x18007c4f9  retn
```
