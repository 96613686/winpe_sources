# Print::Driver::CPrinterExtensionServer::CreateRestrictedToken(Win32HandleRAII &)

- ea: `0x18007e580`
- end: `0x18007e976`
- name: `?CreateRestrictedToken@CPrinterExtensionServer@Driver@Print@@AEAAXAEAVWin32HandleRAII@@@Z`
- size: `1014`
- prototype: `void __fastcall(Print::Driver::CPrinterExtensionServer *this, HANDLE *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008045c`

## callees

- `0x180003400`
- `0x180004564`
- `0x18000f830`
- `0x180010a40`
- `0x180014474`
- `0x1800197b4`
- `0x18007df00`
- `0x18007e25c`
- `0x18007e580`
- `0x180081540`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18007e6b8`
- `KERNEL32!CloseHandle` at `0x18007e740`
- `KERNEL32!CloseHandle` at `0x18007e79a`
- `KERNEL32!CloseHandle` at `0x18007e6b8`
- `KERNEL32!CloseHandle` at `0x18007e740`
- `KERNEL32!CloseHandle` at `0x18007e79a`
- `KERNEL32!GetLastError` at `0x18007e7d8`
- `KERNEL32!GetLastError` at `0x18007e841`
- `KERNEL32!GetLastError` at `0x18007e8a9`
- `KERNEL32!GetLastError` at `0x18007e911`
- `KERNEL32!GetLastError` at `0x18007e7d8`
- `KERNEL32!GetLastError` at `0x18007e841`
- `KERNEL32!GetLastError` at `0x18007e8a9`
- `KERNEL32!GetLastError` at `0x18007e911`
- `KERNEL32!LocalAlloc` at `0x18007e607`
- `KERNEL32!LocalAlloc` at `0x18007e607`
- `ADVAPI32!CreateWellKnownSid` at `0x18007e695`
- `ADVAPI32!CreateWellKnownSid` at `0x18007e695`
- `ADVAPI32!CreateRestrictedToken` at `0x18007e70b`
- `ADVAPI32!CreateRestrictedToken` at `0x18007e70b`
- `ADVAPI32!DuplicateTokenEx` at `0x18007e771`
- `ADVAPI32!DuplicateTokenEx` at `0x18007e771`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Print::Driver::CPrinterExtensionServer::CreateRestrictedToken(
        Print::Driver::CPrinterExtensionServer *this,
        HANDLE *a2)
{
  Print::Driver::CPrinterExtensionServer *v3; // rcx
  HLOCAL v4; // rdi
  _QWORD *v5; // rdx
  __int64 v6; // rdx
  signed int v7; // eax
  unsigned int v8; // ebx
  signed int LastError; // eax
  unsigned int v10; // ebx
  signed int v11; // eax
  unsigned int v12; // ebx
  signed int v13; // eax
  unsigned int v14; // ebx
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbSid; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v17; // [rsp+60h] [rbp-A0h]
  void **v18; // [rsp+68h] [rbp-98h] BYREF
  HANDLE ExistingTokenHandle[2]; // [rsp+70h] [rbp-90h]
  __int64 v20; // [rsp+80h] [rbp-80h]
  _BYTE pExceptionObject[32]; // [rsp+88h] [rbp-78h] BYREF
  _SID_AND_ATTRIBUTES SidsToDisable; // [rsp+A8h] [rbp-58h] BYREF
  struct _SECURITY_ATTRIBUTES TokenAttributes; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v24[7]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD *v25; // [rsp+108h] [rbp+8h]
  __int64 v26; // [rsp+110h] [rbp+10h]
  _QWORD *v27; // [rsp+118h] [rbp+18h]
  _QWORD v28[7]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD *v29; // [rsp+158h] [rbp+58h]
  HLOCAL v30; // [rsp+160h] [rbp+60h]

  v26 = -2;
  v18 = &ATL::CAccessToken::`vftable';
  *(_OWORD *)ExistingTokenHandle = 0;
  v20 = 0;
  hObject = 0;
  if ( !ATL::CAccessToken::GetEffectiveToken((ATL::CAccessToken *)&v18, 0x8Bu) )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x18u,
        (const GUID *)WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids,
        v10);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v10);
    throw (hr_error *)pExceptionObject;
  }
  Print::Driver::CPrinterExtensionServer::AttemptDemoteToNormalUserIfElevated(v3, (struct ATL::CAccessToken *)&v18);
  SidsToDisable = 0;
  cbSid = 68;
  v4 = LocalAlloc(0, 0x44u);
  v24[0] = &std::_Func_impl_no_alloc<_lambda_70d068de8cf8c158899d8a373041798e_,void,void *>::`vftable';
  v25 = v24;
  v17 = v24;
  v27 = v28;
  v29 = 0;
  v29 = std::_Func_impl_no_alloc__lambda_70d068de8cf8c158899d8a373041798e__void_void___::_Move((__int64)v24, v28);
  v30 = v4;
  if ( v25 )
  {
    v5 = v24;
    LOBYTE(v5) = v25 != v24;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v25 + 32LL))(v25, v5);
    v25 = 0;
    v4 = v30;
  }
  SidsToDisable.Sid = v4;
  if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v4, &cbSid) )
  {
    v11 = GetLastError();
    v12 = v11;
    if ( v11 > 0 )
      v12 = (unsigned __int16)v11 | 0x80070000;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x19u,
        (const GUID *)WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids,
        v12);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v12);
    throw (hr_error *)pExceptionObject;
  }
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( !CreateRestrictedToken(ExistingTokenHandle[0], 5u, 1u, &SidsToDisable, 0, 0, 0, 0, &hObject) )
  {
    v13 = GetLastError();
    v14 = v13;
    if ( v13 > 0 )
      v14 = (unsigned __int16)v13 | 0x80070000;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x1Au,
        (const GUID *)WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids,
        v14);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v14);
    throw (hr_error *)pExceptionObject;
  }
  *(_OWORD *)&TokenAttributes.nLength = 0;
  *(&TokenAttributes.bInheritHandle + 1) = 0;
  TokenAttributes.bInheritHandle = 1;
  if ( (char *)*a2 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(*a2);
    *a2 = 0;
  }
  if ( !DuplicateTokenEx(hObject, 0, &TokenAttributes, SecurityImpersonation, TokenPrimary, a2) )
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0x1Bu,
        (const GUID *)WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids,
        v8);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v8);
    throw (hr_error *)pExceptionObject;
  }
  Print::Driver::GenericRAII<void *>::~GenericRAII<void *>((__int64)v28, v6);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  v18 = &ATL::CAccessToken::`vftable';
  ATL::CAccessToken::Clear((ATL::CAccessToken *)&v18);
}

```

## disassembly

```asm
0x18007e580  push    rbp
0x18007e582  push    rbx
0x18007e583  push    rdi
0x18007e584  push    r14
0x18007e586  lea     rbp, [rsp-88h]
0x18007e58e  sub     rsp, 188h
0x18007e595  mov     [rbp+0A0h+var_90], 0FFFFFFFFFFFFFFFEh
0x18007e59d  mov     rax, cs:__security_cookie
0x18007e5a4  xor     rax, rsp
0x18007e5a7  mov     [rbp+0A0h+var_30], rax
0x18007e5ab  mov     rbx, rdx
0x18007e5ae  lea     r14, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x18007e5b5  mov     [rsp+1A0h+var_138], r14
0x18007e5ba  xorps   xmm0, xmm0
0x18007e5bd  movdqu  xmmword ptr [rsp+1A0h+ExistingTokenHandle], xmm0
0x18007e5c3  mov     [rbp+0A0h+var_120], 0
0x18007e5cb  mov     [rsp+1A0h+hObject], 0
0x18007e5d4  mov     edx, 8Bh; unsigned int
0x18007e5d9  lea     rcx, [rsp+1A0h+var_138]; this
0x18007e5de  call    ?GetEffectiveToken@CAccessToken@ATL@@QEAA_NK@Z; ATL::CAccessToken::GetEffectiveToken(ulong)
0x18007e5e3  test    al, al
0x18007e5e5  jz      loc_18007E841
0x18007e5eb  lea     rdx, [rsp+1A0h+var_138]; struct ATL::CAccessToken *
0x18007e5f0  call    ?AttemptDemoteToNormalUserIfElevated@CPrinterExtensionServer@Driver@Print@@AEAAXAEAVCAccessToken@ATL@@@Z; Print::Driver::CPrinterExtensionServer::AttemptDemoteToNormalUserIfElevated(ATL::CAccessToken &)
0x18007e5f5  xorps   xmm0, xmm0
0x18007e5f8  movups  xmmword ptr [rbp+0A0h+SidsToDisable.Sid], xmm0
0x18007e5fc  mov     edx, 44h ; 'D'; uBytes
0x18007e601  mov     [rsp+1A0h+cbSid], edx
0x18007e605  xor     ecx, ecx; uFlags
0x18007e607  call    cs:__imp_LocalAlloc
0x18007e60e  nop     dword ptr [rax+rax+00h]
0x18007e613  mov     rdi, rax
0x18007e616  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_70d068de8cf8c158899d8a373041798e_@@XPEAX@std@@6B@; const std::_Func_impl_no_alloc<_lambda_70d068de8cf8c158899d8a373041798e_,void,void *>::`vftable'
0x18007e61d  mov     [rbp+0A0h+var_D0], rax
0x18007e621  lea     rax, [rbp+0A0h+var_D0]
0x18007e625  mov     [rbp+0A0h+var_98], rax
0x18007e629  lea     rax, [rbp+0A0h+var_D0]
0x18007e62d  mov     [rsp+1A0h+var_140], rax
0x18007e632  lea     rax, [rbp+0A0h+var_80]
0x18007e636  mov     [rbp+0A0h+var_88], rax
0x18007e63a  mov     [rbp+0A0h+var_48], 0
0x18007e642  lea     rdx, [rbp+0A0h+var_80]
0x18007e646  lea     rcx, [rbp+0A0h+var_D0]
0x18007e64a  call    std___Func_impl_no_alloc__lambda_70d068de8cf8c158899d8a373041798e__void_void______Move
0x18007e64f  mov     [rbp+0A0h+var_48], rax
0x18007e653  mov     [rbp+0A0h+var_40], rdi
0x18007e657  mov     rcx, [rbp+0A0h+var_98]
0x18007e65b  test    rcx, rcx
0x18007e65e  jz      short loc_18007E682
0x18007e660  mov     rax, [rcx]
0x18007e663  lea     rdx, [rbp+0A0h+var_D0]
0x18007e667  cmp     rcx, rdx
0x18007e66a  setnz   dl
0x18007e66d  mov     rax, [rax+20h]
0x18007e671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e676  mov     [rbp+0A0h+var_98], 0
0x18007e67e  mov     rdi, [rbp+0A0h+var_40]
0x18007e682  mov     [rbp+0A0h+SidsToDisable.Sid], rdi
0x18007e686  lea     r9, [rsp+1A0h+cbSid]; cbSid
0x18007e68b  mov     r8, rdi; pSid
0x18007e68e  xor     edx, edx; DomainSid
0x18007e690  lea     edi, [rdx+1Ah]
0x18007e693  mov     ecx, edi; WellKnownSidType
0x18007e695  call    cs:__imp_CreateWellKnownSid
0x18007e69c  nop     dword ptr [rax+rax+00h]
0x18007e6a1  test    eax, eax
0x18007e6a3  jz      loc_18007E8A9
0x18007e6a9  mov     rcx, [rsp+1A0h+hObject]; hObject
0x18007e6ae  lea     rax, [rcx-1]
0x18007e6b2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007e6b6  ja      short loc_18007E6CD
0x18007e6b8  call    cs:__imp_CloseHandle
0x18007e6bf  nop     dword ptr [rax+rax+00h]
0x18007e6c4  mov     [rsp+1A0h+hObject], 0
0x18007e6cd  lea     rax, [rsp+1A0h+hObject]
0x18007e6d2  mov     [rsp+1A0h+NewTokenHandle], rax; NewTokenHandle
0x18007e6d7  mov     [rsp+1A0h+SidsToRestrict], 0; SidsToRestrict
0x18007e6e0  mov     [rsp+1A0h+RestrictedSidCount], 0; RestrictedSidCount
0x18007e6e8  mov     [rsp+1A0h+PrivilegesToDelete], 0; PrivilegesToDelete
0x18007e6f1  mov     [rsp+1A0h+DeletePrivilegeCount], 0; DeletePrivilegeCount
0x18007e6f9  lea     r9, [rbp+0A0h+SidsToDisable]; SidsToDisable
0x18007e6fd  mov     edx, 5; Flags
0x18007e702  lea     r8d, [rdx-4]; DisableSidCount
0x18007e706  mov     rcx, [rsp+1A0h+ExistingTokenHandle]; ExistingTokenHandle
0x18007e70b  call    cs:__imp_CreateRestrictedToken
0x18007e712  nop     dword ptr [rax+rax+00h]
0x18007e717  test    eax, eax
0x18007e719  jz      loc_18007E911
0x18007e71f  xorps   xmm0, xmm0
0x18007e722  xor     eax, eax
0x18007e724  movups  xmmword ptr [rbp+0A0h+TokenAttributes.nLength], xmm0
0x18007e728  mov     qword ptr [rbp+0A0h+TokenAttributes.bInheritHandle], rax
0x18007e72c  mov     [rbp+0A0h+TokenAttributes.bInheritHandle], 1
0x18007e733  mov     rcx, [rbx]; hObject
0x18007e736  lea     rax, [rcx-1]
0x18007e73a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007e73e  ja      short loc_18007E753
0x18007e740  call    cs:__imp_CloseHandle
0x18007e747  nop     dword ptr [rax+rax+00h]
0x18007e74c  mov     qword ptr [rbx], 0
0x18007e753  mov     [rsp+1A0h+PrivilegesToDelete], rbx; phNewToken
0x18007e758  mov     [rsp+1A0h+DeletePrivilegeCount], 1; TokenType
0x18007e760  mov     r9d, 2; ImpersonationLevel
0x18007e766  lea     r8, [rbp+0A0h+TokenAttributes]; lpTokenAttributes
0x18007e76a  xor     edx, edx; dwDesiredAccess
0x18007e76c  mov     rcx, [rsp+1A0h+hObject]; hExistingToken
0x18007e771  call    cs:__imp_DuplicateTokenEx
0x18007e778  nop     dword ptr [rax+rax+00h]
0x18007e77d  test    eax, eax
0x18007e77f  jz      short loc_18007E7D8
0x18007e781  lea     rcx, [rbp+0A0h+var_80]
0x18007e785  call    ??1?$GenericRAII@PEAX@Driver@Print@@QEAA@XZ; Print::Driver::GenericRAII<void *>::~GenericRAII<void *>(void)
0x18007e78a  nop
0x18007e78b  mov     rcx, [rsp+1A0h+hObject]; hObject
0x18007e790  lea     rax, [rcx-1]
0x18007e794  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007e798  ja      short loc_18007E7AF
0x18007e79a  call    cs:__imp_CloseHandle
0x18007e7a1  nop     dword ptr [rax+rax+00h]
0x18007e7a6  mov     [rsp+1A0h+hObject], 0
0x18007e7af  mov     [rsp+1A0h+var_138], r14
0x18007e7b4  lea     rcx, [rsp+1A0h+var_138]; this
0x18007e7b9  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x18007e7be  mov     rcx, [rbp+0A0h+var_30]
0x18007e7c2  xor     rcx, rsp; StackCookie
0x18007e7c5  call    __security_check_cookie
0x18007e7ca  add     rsp, 188h
0x18007e7d1  pop     r14
0x18007e7d3  pop     rdi
0x18007e7d4  pop     rbx
0x18007e7d5  pop     rbp
0x18007e7d6  retn
0x18007e7d8  call    cs:__imp_GetLastError
0x18007e7df  nop     dword ptr [rax+rax+00h]
0x18007e7e4  nop
0x18007e7e5  mov     ebx, eax
0x18007e7e7  test    eax, eax
0x18007e7e9  jle     short loc_18007E7F4
0x18007e7eb  movzx   ebx, ax
0x18007e7ee  or      ebx, 80070000h
0x18007e7f4  lea     rax, WPP_GLOBAL_Control
0x18007e7fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e802  cmp     rcx, rax
0x18007e805  jz      short loc_18007E825
0x18007e807  test    byte ptr [rcx+44h], 1
0x18007e80b  jz      short loc_18007E825
0x18007e80d  mov     edx, 1Bh
0x18007e812  mov     r9d, ebx
0x18007e815  lea     r8, WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids
0x18007e81c  mov     rcx, [rcx+38h]
0x18007e820  call    WPP_SF_d
0x18007e825  mov     edx, ebx; int
0x18007e827  lea     rcx, [rbp+0A0h+pExceptionObject]; this
0x18007e82b  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18007e830  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18007e837  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x18007e83b  call    _CxxThrowException_0
0x18007e841  call    cs:__imp_GetLastError
0x18007e848  nop     dword ptr [rax+rax+00h]
0x18007e84d  mov     ebx, eax
0x18007e84f  test    eax, eax
0x18007e851  jle     short loc_18007E85C
0x18007e853  movzx   ebx, ax
0x18007e856  or      ebx, 80070000h
0x18007e85c  lea     rax, WPP_GLOBAL_Control
0x18007e863  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e86a  cmp     rcx, rax
0x18007e86d  jz      short loc_18007E88D
0x18007e86f  test    byte ptr [rcx+44h], 1
0x18007e873  jz      short loc_18007E88D
0x18007e875  mov     edx, 18h
0x18007e87a  mov     r9d, ebx
0x18007e87d  lea     r8, WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids
0x18007e884  mov     rcx, [rcx+38h]
0x18007e888  call    WPP_SF_d
0x18007e88d  mov     edx, ebx; int
0x18007e88f  lea     rcx, [rbp+0A0h+pExceptionObject]; this
0x18007e893  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18007e898  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18007e89f  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x18007e8a3  call    _CxxThrowException_0
0x18007e8a9  call    cs:__imp_GetLastError
0x18007e8b0  nop     dword ptr [rax+rax+00h]
0x18007e8b5  mov     ebx, eax
0x18007e8b7  test    eax, eax
0x18007e8b9  jle     short loc_18007E8C4
0x18007e8bb  movzx   ebx, ax
0x18007e8be  or      ebx, 80070000h
0x18007e8c4  lea     rax, WPP_GLOBAL_Control
0x18007e8cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e8d2  cmp     rcx, rax
0x18007e8d5  jz      short loc_18007E8F5
0x18007e8d7  test    byte ptr [rcx+44h], 1
0x18007e8db  jz      short loc_18007E8F5
0x18007e8dd  mov     edx, 19h
0x18007e8e2  mov     r9d, ebx
0x18007e8e5  lea     r8, WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids
0x18007e8ec  mov     rcx, [rcx+38h]
0x18007e8f0  call    WPP_SF_d
0x18007e8f5  mov     edx, ebx; int
0x18007e8f7  lea     rcx, [rbp+0A0h+pExceptionObject]; this
0x18007e8fb  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18007e900  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18007e907  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x18007e90b  call    _CxxThrowException_0
0x18007e911  call    cs:__imp_GetLastError
0x18007e918  nop     dword ptr [rax+rax+00h]
0x18007e91d  mov     ebx, eax
0x18007e91f  test    eax, eax
0x18007e921  jle     short loc_18007E92C
0x18007e923  movzx   ebx, ax
0x18007e926  or      ebx, 80070000h
0x18007e92c  lea     rax, WPP_GLOBAL_Control
0x18007e933  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e93a  cmp     rcx, rax
0x18007e93d  jz      short loc_18007E95A
0x18007e93f  test    byte ptr [rcx+44h], 1
0x18007e943  jz      short loc_18007E95A
0x18007e945  mov     edx, edi
0x18007e947  mov     r9d, ebx
0x18007e94a  lea     r8, WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids
0x18007e951  mov     rcx, [rcx+38h]
0x18007e955  call    WPP_SF_d
0x18007e95a  mov     edx, ebx; int
0x18007e95c  lea     rcx, [rbp+0A0h+pExceptionObject]; this
0x18007e960  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18007e965  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18007e96c  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x18007e970  call    _CxxThrowException_0
```
