# Print::Driver::CPrinterExtensionServer::CreateRestrictedToken(Win32HandleRAII &)

- ea: `0x18007b8f4`
- end: `0x18007bca7`
- name: `?CreateRestrictedToken@CPrinterExtensionServer@Driver@Print@@AEAAXAEAVWin32HandleRAII@@@Z`
- size: `947`
- prototype: `void(Print::Driver::CPrinterExtensionServer *__hidden this, struct Win32HandleRAII *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007d6d0`

## callees

- `0x1800032e0`
- `0x180004424`
- `0x18000f380`
- `0x1800104d0`
- `0x180013c38`
- `0x180018bbc`
- `0x18007b2ec`
- `0x18007b608`
- `0x18007b8f4`
- `0x18007e6d0`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18007ba20`
- `KERNEL32!CloseHandle` at `0x18007ba9c`
- `KERNEL32!CloseHandle` at `0x18007baea`
- `KERNEL32!CloseHandle` at `0x18007ba20`
- `KERNEL32!CloseHandle` at `0x18007ba9c`
- `KERNEL32!CloseHandle` at `0x18007baea`
- `KERNEL32!GetLastError` at `0x18007bb21`
- `KERNEL32!GetLastError` at `0x18007bb84`
- `KERNEL32!GetLastError` at `0x18007bbe6`
- `KERNEL32!GetLastError` at `0x18007bc48`
- `KERNEL32!GetLastError` at `0x18007bb21`
- `KERNEL32!GetLastError` at `0x18007bb84`
- `KERNEL32!GetLastError` at `0x18007bbe6`
- `KERNEL32!GetLastError` at `0x18007bc48`
- `KERNEL32!LocalAlloc` at `0x18007b97b`
- `KERNEL32!LocalAlloc` at `0x18007b97b`
- `ADVAPI32!CreateWellKnownSid` at `0x18007ba03`
- `ADVAPI32!CreateWellKnownSid` at `0x18007ba03`
- `ADVAPI32!CreateRestrictedToken` at `0x18007ba6d`
- `ADVAPI32!CreateRestrictedToken` at `0x18007ba6d`
- `ADVAPI32!DuplicateTokenEx` at `0x18007bac7`
- `ADVAPI32!DuplicateTokenEx` at `0x18007bac7`

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
  signed int v6; // eax
  unsigned int v7; // ebx
  signed int LastError; // eax
  unsigned int v9; // ebx
  signed int v10; // eax
  unsigned int v11; // ebx
  signed int v12; // eax
  unsigned int v13; // ebx
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbSid; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v16; // [rsp+60h] [rbp-A0h]
  void **v17; // [rsp+68h] [rbp-98h] BYREF
  HANDLE ExistingTokenHandle[2]; // [rsp+70h] [rbp-90h]
  __int64 v19; // [rsp+80h] [rbp-80h]
  _BYTE pExceptionObject[32]; // [rsp+88h] [rbp-78h] BYREF
  _SID_AND_ATTRIBUTES SidsToDisable; // [rsp+A8h] [rbp-58h] BYREF
  struct _SECURITY_ATTRIBUTES TokenAttributes; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v23[7]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD *v24; // [rsp+108h] [rbp+8h]
  __int64 v25; // [rsp+110h] [rbp+10h]
  _BYTE *v26; // [rsp+118h] [rbp+18h]
  _BYTE v27[56]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v28; // [rsp+158h] [rbp+58h]
  HLOCAL v29; // [rsp+160h] [rbp+60h]

  v25 = -2;
  v17 = &ATL::CAccessToken::`vftable';
  *(_OWORD *)ExistingTokenHandle = 0;
  v19 = 0;
  hObject = 0;
  if ( !ATL::CAccessToken::GetEffectiveToken((ATL::CAccessToken *)&v17, 0x8Bu) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 24, WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids, v9);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v9);
    throw (hr_error *)pExceptionObject;
  }
  Print::Driver::CPrinterExtensionServer::AttemptDemoteToNormalUserIfElevated(v3, (struct ATL::CAccessToken *)&v17);
  SidsToDisable = 0;
  cbSid = 68;
  v4 = LocalAlloc(0, 0x44u);
  v23[0] = &std::_Func_impl_no_alloc<_lambda_70d068de8cf8c158899d8a373041798e_,void,void *>::`vftable';
  v24 = v23;
  v16 = v23;
  v26 = v27;
  v28 = 0;
  v28 = std::_Func_impl_no_alloc__lambda_70d068de8cf8c158899d8a373041798e__void_void___::_Move(v23, v27);
  v29 = v4;
  if ( v24 )
  {
    v5 = v23;
    LOBYTE(v5) = v24 != v23;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v24 + 32LL))(v24, v5);
    v24 = 0;
    v4 = v29;
  }
  SidsToDisable.Sid = v4;
  if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v4, &cbSid) )
  {
    v10 = GetLastError();
    v11 = v10;
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 25, WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids, v11);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v11);
    throw (hr_error *)pExceptionObject;
  }
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( !CreateRestrictedToken(ExistingTokenHandle[0], 5u, 1u, &SidsToDisable, 0, 0, 0, 0, &hObject) )
  {
    v12 = GetLastError();
    v13 = v12;
    if ( v12 > 0 )
      v13 = (unsigned __int16)v12 | 0x80070000;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 26, WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids, v13);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v13);
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
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 27, WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids, v7);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v7);
    throw (hr_error *)pExceptionObject;
  }
  Print::Driver::GenericRAII<void *>::~GenericRAII<void *>(v27);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  v17 = &ATL::CAccessToken::`vftable';
  ATL::CAccessToken::Clear((ATL::CAccessToken *)&v17);
}

```

## disassembly

```asm
0x18007b8f4  push    rbp
0x18007b8f6  push    rbx
0x18007b8f7  push    rdi
0x18007b8f8  push    r14
0x18007b8fa  lea     rbp, [rsp-88h]
0x18007b902  sub     rsp, 188h
0x18007b909  mov     [rbp+0A0h+var_90], 0FFFFFFFFFFFFFFFEh
0x18007b911  mov     rax, cs:__security_cookie
0x18007b918  xor     rax, rsp
0x18007b91b  mov     [rbp+0A0h+var_30], rax
0x18007b91f  mov     rbx, rdx
0x18007b922  lea     r14, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x18007b929  mov     [rsp+1A0h+var_138], r14
0x18007b92e  xorps   xmm0, xmm0
0x18007b931  movdqu  xmmword ptr [rsp+1A0h+ExistingTokenHandle], xmm0
0x18007b937  mov     [rbp+0A0h+var_120], 0
0x18007b93f  mov     [rsp+1A0h+hObject], 0
0x18007b948  mov     edx, 8Bh; unsigned int
0x18007b94d  lea     rcx, [rsp+1A0h+var_138]; this
0x18007b952  call    ?GetEffectiveToken@CAccessToken@ATL@@QEAA_NK@Z; ATL::CAccessToken::GetEffectiveToken(ulong)
0x18007b957  test    al, al
0x18007b959  jz      loc_18007BB84
0x18007b95f  lea     rdx, [rsp+1A0h+var_138]; struct ATL::CAccessToken *
0x18007b964  call    ?AttemptDemoteToNormalUserIfElevated@CPrinterExtensionServer@Driver@Print@@AEAAXAEAVCAccessToken@ATL@@@Z; Print::Driver::CPrinterExtensionServer::AttemptDemoteToNormalUserIfElevated(ATL::CAccessToken &)
0x18007b969  xorps   xmm0, xmm0
0x18007b96c  movups  xmmword ptr [rbp+0A0h+SidsToDisable.Sid], xmm0
0x18007b970  mov     edx, 44h ; 'D'; uBytes
0x18007b975  mov     [rsp+1A0h+cbSid], edx
0x18007b979  xor     ecx, ecx; uFlags
0x18007b97b  call    cs:__imp_LocalAlloc
0x18007b981  mov     rdi, rax
0x18007b984  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_70d068de8cf8c158899d8a373041798e_@@XPEAX@std@@6B@; const std::_Func_impl_no_alloc<_lambda_70d068de8cf8c158899d8a373041798e_,void,void *>::`vftable'
0x18007b98b  mov     [rbp+0A0h+var_D0], rax
0x18007b98f  lea     rax, [rbp+0A0h+var_D0]
0x18007b993  mov     [rbp+0A0h+var_98], rax
0x18007b997  lea     rax, [rbp+0A0h+var_D0]
0x18007b99b  mov     [rsp+1A0h+var_140], rax
0x18007b9a0  lea     rax, [rbp+0A0h+var_80]
0x18007b9a4  mov     [rbp+0A0h+var_88], rax
0x18007b9a8  mov     [rbp+0A0h+var_48], 0
0x18007b9b0  lea     rdx, [rbp+0A0h+var_80]
0x18007b9b4  lea     rcx, [rbp+0A0h+var_D0]
0x18007b9b8  call    std___Func_impl_no_alloc__lambda_70d068de8cf8c158899d8a373041798e__void_void______Move
0x18007b9bd  mov     [rbp+0A0h+var_48], rax
0x18007b9c1  mov     [rbp+0A0h+var_40], rdi
0x18007b9c5  mov     rcx, [rbp+0A0h+var_98]
0x18007b9c9  test    rcx, rcx
0x18007b9cc  jz      short loc_18007B9F0
0x18007b9ce  mov     rax, [rcx]
0x18007b9d1  lea     rdx, [rbp+0A0h+var_D0]
0x18007b9d5  cmp     rcx, rdx
0x18007b9d8  setnz   dl
0x18007b9db  mov     rax, [rax+20h]
0x18007b9df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b9e4  mov     [rbp+0A0h+var_98], 0
0x18007b9ec  mov     rdi, [rbp+0A0h+var_40]
0x18007b9f0  mov     [rbp+0A0h+SidsToDisable.Sid], rdi
0x18007b9f4  lea     r9, [rsp+1A0h+cbSid]; cbSid
0x18007b9f9  mov     r8, rdi; pSid
0x18007b9fc  xor     edx, edx; DomainSid
0x18007b9fe  lea     edi, [rdx+1Ah]
0x18007ba01  mov     ecx, edi; WellKnownSidType
0x18007ba03  call    cs:__imp_CreateWellKnownSid
0x18007ba09  test    eax, eax
0x18007ba0b  jz      loc_18007BBE6
0x18007ba11  mov     rcx, [rsp+1A0h+hObject]; hObject
0x18007ba16  lea     rax, [rcx-1]
0x18007ba1a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007ba1e  ja      short loc_18007BA2F
0x18007ba20  call    cs:__imp_CloseHandle
0x18007ba26  mov     [rsp+1A0h+hObject], 0
0x18007ba2f  lea     rax, [rsp+1A0h+hObject]
0x18007ba34  mov     [rsp+1A0h+NewTokenHandle], rax; NewTokenHandle
0x18007ba39  mov     [rsp+1A0h+SidsToRestrict], 0; SidsToRestrict
0x18007ba42  mov     [rsp+1A0h+RestrictedSidCount], 0; RestrictedSidCount
0x18007ba4a  mov     [rsp+1A0h+PrivilegesToDelete], 0; PrivilegesToDelete
0x18007ba53  mov     [rsp+1A0h+DeletePrivilegeCount], 0; DeletePrivilegeCount
0x18007ba5b  lea     r9, [rbp+0A0h+SidsToDisable]; SidsToDisable
0x18007ba5f  mov     edx, 5; Flags
0x18007ba64  lea     r8d, [rdx-4]; DisableSidCount
0x18007ba68  mov     rcx, [rsp+1A0h+ExistingTokenHandle]; ExistingTokenHandle
0x18007ba6d  call    cs:__imp_CreateRestrictedToken
0x18007ba73  test    eax, eax
0x18007ba75  jz      loc_18007BC48
0x18007ba7b  xorps   xmm0, xmm0
0x18007ba7e  xor     eax, eax
0x18007ba80  movups  xmmword ptr [rbp+0A0h+TokenAttributes.nLength], xmm0
0x18007ba84  mov     qword ptr [rbp+0A0h+TokenAttributes.bInheritHandle], rax
0x18007ba88  mov     [rbp+0A0h+TokenAttributes.bInheritHandle], 1
0x18007ba8f  mov     rcx, [rbx]; hObject
0x18007ba92  lea     rax, [rcx-1]
0x18007ba96  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007ba9a  ja      short loc_18007BAA9
0x18007ba9c  call    cs:__imp_CloseHandle
0x18007baa2  mov     qword ptr [rbx], 0
0x18007baa9  mov     [rsp+1A0h+PrivilegesToDelete], rbx; phNewToken
0x18007baae  mov     [rsp+1A0h+DeletePrivilegeCount], 1; TokenType
0x18007bab6  mov     r9d, 2; ImpersonationLevel
0x18007babc  lea     r8, [rbp+0A0h+TokenAttributes]; lpTokenAttributes
0x18007bac0  xor     edx, edx; dwDesiredAccess
0x18007bac2  mov     rcx, [rsp+1A0h+hObject]; hExistingToken
0x18007bac7  call    cs:__imp_DuplicateTokenEx
0x18007bacd  test    eax, eax
0x18007bacf  jz      short loc_18007BB21
0x18007bad1  lea     rcx, [rbp+0A0h+var_80]
0x18007bad5  call    ??1?$GenericRAII@PEAX@Driver@Print@@QEAA@XZ; Print::Driver::GenericRAII<void *>::~GenericRAII<void *>(void)
0x18007bada  nop
0x18007badb  mov     rcx, [rsp+1A0h+hObject]; hObject
0x18007bae0  lea     rax, [rcx-1]
0x18007bae4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007bae8  ja      short loc_18007BAF9
0x18007baea  call    cs:__imp_CloseHandle
0x18007baf0  mov     [rsp+1A0h+hObject], 0
0x18007baf9  mov     [rsp+1A0h+var_138], r14
0x18007bafe  lea     rcx, [rsp+1A0h+var_138]; this
0x18007bb03  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x18007bb08  mov     rcx, [rbp+0A0h+var_30]
0x18007bb0c  xor     rcx, rsp; StackCookie
0x18007bb0f  call    __security_check_cookie
0x18007bb14  add     rsp, 188h
0x18007bb1b  pop     r14
0x18007bb1d  pop     rdi
0x18007bb1e  pop     rbx
0x18007bb1f  pop     rbp
0x18007bb20  retn
0x18007bb21  call    cs:__imp_GetLastError
0x18007bb27  nop
0x18007bb28  mov     ebx, eax
0x18007bb2a  test    eax, eax
0x18007bb2c  jle     short loc_18007BB37
0x18007bb2e  movzx   ebx, ax
0x18007bb31  or      ebx, 80070000h
0x18007bb37  lea     rax, WPP_GLOBAL_Control
0x18007bb3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bb45  cmp     rcx, rax
0x18007bb48  jz      short loc_18007BB68
0x18007bb4a  test    byte ptr [rcx+44h], 1
0x18007bb4e  jz      short loc_18007BB68
0x18007bb50  mov     edx, 1Bh
0x18007bb55  mov     r9d, ebx
0x18007bb58  lea     r8, WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids
0x18007bb5f  mov     rcx, [rcx+38h]
0x18007bb63  call    WPP_SF_d
0x18007bb68  mov     edx, ebx; int
0x18007bb6a  lea     rcx, [rbp+0A0h+pExceptionObject]; this
0x18007bb6e  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18007bb73  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18007bb7a  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x18007bb7e  call    _CxxThrowException_0
0x18007bb84  call    cs:__imp_GetLastError
0x18007bb8a  mov     ebx, eax
0x18007bb8c  test    eax, eax
0x18007bb8e  jle     short loc_18007BB99
0x18007bb90  movzx   ebx, ax
0x18007bb93  or      ebx, 80070000h
0x18007bb99  lea     rax, WPP_GLOBAL_Control
0x18007bba0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bba7  cmp     rcx, rax
0x18007bbaa  jz      short loc_18007BBCA
0x18007bbac  test    byte ptr [rcx+44h], 1
0x18007bbb0  jz      short loc_18007BBCA
0x18007bbb2  mov     edx, 18h
0x18007bbb7  mov     r9d, ebx
0x18007bbba  lea     r8, WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids
0x18007bbc1  mov     rcx, [rcx+38h]
0x18007bbc5  call    WPP_SF_d
0x18007bbca  mov     edx, ebx; int
0x18007bbcc  lea     rcx, [rbp+0A0h+pExceptionObject]; this
0x18007bbd0  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18007bbd5  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18007bbdc  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x18007bbe0  call    _CxxThrowException_0
0x18007bbe6  call    cs:__imp_GetLastError
0x18007bbec  mov     ebx, eax
0x18007bbee  test    eax, eax
0x18007bbf0  jle     short loc_18007BBFB
0x18007bbf2  movzx   ebx, ax
0x18007bbf5  or      ebx, 80070000h
0x18007bbfb  lea     rax, WPP_GLOBAL_Control
0x18007bc02  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bc09  cmp     rcx, rax
0x18007bc0c  jz      short loc_18007BC2C
0x18007bc0e  test    byte ptr [rcx+44h], 1
0x18007bc12  jz      short loc_18007BC2C
0x18007bc14  mov     edx, 19h
0x18007bc19  mov     r9d, ebx
0x18007bc1c  lea     r8, WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids
0x18007bc23  mov     rcx, [rcx+38h]
0x18007bc27  call    WPP_SF_d
0x18007bc2c  mov     edx, ebx; int
0x18007bc2e  lea     rcx, [rbp+0A0h+pExceptionObject]; this
0x18007bc32  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18007bc37  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18007bc3e  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x18007bc42  call    _CxxThrowException_0
0x18007bc48  call    cs:__imp_GetLastError
0x18007bc4e  mov     ebx, eax
0x18007bc50  test    eax, eax
0x18007bc52  jle     short loc_18007BC5D
0x18007bc54  movzx   ebx, ax
0x18007bc57  or      ebx, 80070000h
0x18007bc5d  lea     rax, WPP_GLOBAL_Control
0x18007bc64  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bc6b  cmp     rcx, rax
0x18007bc6e  jz      short loc_18007BC8B
0x18007bc70  test    byte ptr [rcx+44h], 1
0x18007bc74  jz      short loc_18007BC8B
0x18007bc76  mov     edx, edi
0x18007bc78  mov     r9d, ebx
0x18007bc7b  lea     r8, WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids
0x18007bc82  mov     rcx, [rcx+38h]
0x18007bc86  call    WPP_SF_d
0x18007bc8b  mov     edx, ebx; int
0x18007bc8d  lea     rcx, [rbp+0A0h+pExceptionObject]; this
0x18007bc91  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18007bc96  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18007bc9d  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x18007bca1  call    _CxxThrowException_0
```
