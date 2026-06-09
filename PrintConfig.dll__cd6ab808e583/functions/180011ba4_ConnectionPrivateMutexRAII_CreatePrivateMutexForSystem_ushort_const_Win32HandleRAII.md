# ConnectionPrivateMutexRAII::CreatePrivateMutexForSystem(ushort const *,Win32HandleRAII &)

- ea: `0x180011ba4`
- end: `0x18001215c`
- name: `?CreatePrivateMutexForSystem@ConnectionPrivateMutexRAII@@CAXPEBGAEAVWin32HandleRAII@@@Z`
- size: `1464`
- prototype: `void __fastcall(LPCWSTR lpName, struct Win32HandleRAII *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180013150`

## callees

- `0x180004424`
- `0x18000e420`
- `0x18000e4a0`
- `0x18000efdc`
- `0x18000f380`
- `0x18000f6a0`
- `0x180011ba4`
- `0x180012164`
- `0x1800188fc`
- `0x180018bbc`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x180011e0c`
- `KERNEL32!CreateMutexW` at `0x180011e0c`
- `KERNEL32!OpenMutexW` at `0x180011dd6`
- `KERNEL32!OpenMutexW` at `0x180011dd6`
- `KERNEL32!FreeLibrary` at `0x180011c9d`
- `KERNEL32!FreeLibrary` at `0x180011c9d`
- `KERNEL32!CloseHandle` at `0x180011dec`
- `KERNEL32!CloseHandle` at `0x180011e22`
- `KERNEL32!CloseHandle` at `0x180011dec`
- `KERNEL32!CloseHandle` at `0x180011e22`
- `KERNEL32!GetLastError` at `0x180011cdd`
- `KERNEL32!GetLastError` at `0x180011e3c`
- `KERNEL32!GetLastError` at `0x180011ea0`
- `KERNEL32!GetLastError` at `0x180011f04`
- `KERNEL32!GetLastError` at `0x180011f68`
- `KERNEL32!GetLastError` at `0x180011fcc`
- `KERNEL32!GetLastError` at `0x180012030`
- `KERNEL32!GetLastError` at `0x180012094`
- `KERNEL32!GetLastError` at `0x1800120f8`
- `KERNEL32!GetLastError` at `0x180011cdd`
- `KERNEL32!GetLastError` at `0x180011e3c`
- `KERNEL32!GetLastError` at `0x180011ea0`
- `KERNEL32!GetLastError` at `0x180011f04`
- `KERNEL32!GetLastError` at `0x180011f68`
- `KERNEL32!GetLastError` at `0x180011fcc`
- `KERNEL32!GetLastError` at `0x180012030`
- `KERNEL32!GetLastError` at `0x180012094`
- `KERNEL32!GetLastError` at `0x1800120f8`
- `ADVAPI32!GetLengthSid` at `0x180011cef`
- `ADVAPI32!GetLengthSid` at `0x180011cef`
- `ADVAPI32!InitializeAcl` at `0x180011d15`
- `ADVAPI32!InitializeAcl` at `0x180011d15`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180011d79`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180011d79`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180011d5e`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180011d5e`
- `ADVAPI32!CreateWellKnownSid` at `0x180011c03`
- `ADVAPI32!CreateWellKnownSid` at `0x180011c03`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x180011d38`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x180011d38`

## string_xrefs

- `0x180011cbf`: `PrintConfigConnections`
- `0x180011da2`: `PrintConfigConnections`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall ConnectionPrivateMutexRAII::CreatePrivateMutexForSystem(LPCWSTR lpName, struct Win32HandleRAII *a2)
{
  __int64 v4; // rbx
  ACL *v5; // r14
  HANDLE v6; // rbx
  HANDLE MutexW; // rbx
  signed int v8; // eax
  unsigned int v9; // ebx
  signed int v10; // eax
  unsigned int v11; // ebx
  signed int LastError; // eax
  unsigned int v13; // ebx
  signed int v14; // eax
  unsigned int v15; // ebx
  signed int v16; // eax
  unsigned int v17; // ebx
  signed int v18; // eax
  unsigned int v19; // ebx
  signed int v20; // eax
  unsigned int v21; // ebx
  signed int v22; // eax
  unsigned int v23; // ebx
  __int64 v24; // [rsp+38h] [rbp-D0h] BYREF
  void *v25; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v27[3]; // [rsp+68h] [rbp-A0h] BYREF
  PACL pAcl[4]; // [rsp+80h] [rbp-88h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v30; // [rsp+C0h] [rbp-48h]
  __int64 v31; // [rsp+C8h] [rbp-40h]
  _QWORD v32[7]; // [rsp+D8h] [rbp-30h] BYREF
  HMODULE hLibModule; // [rsp+110h] [rbp+8h]
  DWORD cbSid; // [rsp+158h] [rbp+50h] BYREF

  v31 = -2;
  Kernel32RAII::Kernel32RAII((Kernel32RAII *)v32);
  if ( !`ConnectionPrivateMutexRAII::CreatePrivateMutexForSystem'::`2'::fInitializedSID )
  {
    cbSid = 68;
    if ( !CreateWellKnownSid(
            WinLocalSystemSid,
            0,
            `ConnectionPrivateMutexRAII::CreatePrivateMutexForSystem'::`2'::SystemSID,
            &cbSid) )
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, v13);
      }
      hr_error::hr_error((hr_error *)pAcl, v13);
      throw (hr_error *)pAcl;
    }
    `ConnectionPrivateMutexRAII::CreatePrivateMutexForSystem'::`2'::fInitializedSID = 1;
  }
  BoundaryDescriptorRAII::BoundaryDescriptorRAII(
    (BoundaryDescriptorRAII *)&v24,
    L"LocalSystem",
    (struct Kernel32RAII *)v32);
  if ( !(*(unsigned int (__fastcall **)(void **, __int64 *))(v24 + 40))(
          &v25,
          `ConnectionPrivateMutexRAII::CreatePrivateMutexForSystem'::`2'::SystemSID) )
  {
    v14 = GetLastError();
    v15 = v14;
    if ( v14 > 0 )
      v15 = (unsigned __int16)v14 | 0x80070000;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, v15);
    }
    hr_error::hr_error((hr_error *)pAcl, v15);
    throw (hr_error *)pAcl;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    ConnectionPrivateMutexRAII::CreatePrivateMutexInternal(
      lpName,
      v25,
      `ConnectionPrivateMutexRAII::CreatePrivateMutexForSystem'::`2'::SystemSID,
      a2);
  }
  else
  {
    if ( !((__int64 (__fastcall *)(void *, const wchar_t *))v32[1])(v25, L"PrintConfigConnections")
      && GetLastError() != 52 )
    {
      v4 = GetLengthSid(`ConnectionPrivateMutexRAII::CreatePrivateMutexForSystem'::`2'::SystemSID) + 16;
      std::vector<unsigned char>::vector<unsigned char>(pAcl, v4);
      v5 = pAcl[0];
      if ( !InitializeAcl(pAcl[0], v4, 2u) )
      {
        v16 = GetLastError();
        v17 = v16;
        if ( v16 > 0 )
          v17 = (unsigned __int16)v16 | 0x80070000;
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 18, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, v17);
        }
        hr_error::hr_error((hr_error *)pExceptionObject, v17);
        throw (hr_error *)pExceptionObject;
      }
      if ( !AddAccessAllowedAceEx(
              v5,
              2u,
              0,
              0x10000000u,
              `ConnectionPrivateMutexRAII::CreatePrivateMutexForSystem'::`2'::SystemSID) )
      {
        v18 = GetLastError();
        v19 = v18;
        if ( v18 > 0 )
          v19 = (unsigned __int16)v18 | 0x80070000;
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 19, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, v19);
        }
        hr_error::hr_error((hr_error *)pExceptionObject, v19);
        throw (hr_error *)pExceptionObject;
      }
      memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
      v30 = 0;
      if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
      {
        v20 = GetLastError();
        v21 = v20;
        if ( v20 > 0 )
          v21 = (unsigned __int16)v20 | 0x80070000;
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, v21);
        }
        hr_error::hr_error((hr_error *)pExceptionObject, v21);
        throw (hr_error *)pExceptionObject;
      }
      if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v5, 0) )
      {
        v22 = GetLastError();
        v23 = v22;
        if ( v22 > 0 )
          v23 = (unsigned __int16)v22 | 0x80070000;
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, v23);
        }
        hr_error::hr_error((hr_error *)pExceptionObject, v23);
        throw (hr_error *)pExceptionObject;
      }
      v27[0] = 24;
      v27[2] = 0;
      v27[1] = pSecurityDescriptor;
      if ( !((__int64 (__fastcall *)(_QWORD *, void *, const wchar_t *))v32[0])(v27, v25, L"PrintConfigConnections") )
      {
        v8 = GetLastError();
        v9 = v8;
        if ( v8 > 0 )
          v9 = (unsigned __int16)v8 | 0x80070000;
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 22, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, v9);
        }
        hr_error::hr_error((hr_error *)pExceptionObject, v9);
        throw (hr_error *)pExceptionObject;
      }
      std::vector<char>::~vector<char>(pAcl);
    }
    v6 = OpenMutexW(0x10000000u, 1, lpName);
    if ( (unsigned __int64)(*(_QWORD *)a2 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(*(HANDLE *)a2);
    *(_QWORD *)a2 = v6;
    if ( (((unsigned __int64)v6 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      MutexW = CreateMutexW(0, 0, lpName);
      if ( (unsigned __int64)(*(_QWORD *)a2 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(*(HANDLE *)a2);
      *(_QWORD *)a2 = MutexW;
      if ( (((unsigned __int64)MutexW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        v10 = GetLastError();
        v11 = v10;
        if ( v10 > 0 )
          v11 = (unsigned __int16)v10 | 0x80070000;
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 23, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, v11);
        }
        hr_error::hr_error((hr_error *)pExceptionObject, v11);
        throw (hr_error *)pExceptionObject;
      }
    }
  }
  if ( v25 )
    (*(void (**)(void))(v24 + 32))();
  v32[6] = &ModuleRAII::`vftable';
  if ( hLibModule )
    FreeLibrary(hLibModule);
}

```

## disassembly

```asm
0x180011ba4  mov     rax, rsp
0x180011ba7  push    rbp
0x180011ba8  push    rdi
0x180011ba9  push    r12
0x180011bab  push    r13
0x180011bad  push    r14
0x180011baf  lea     rbp, [rax-38h]
0x180011bb3  sub     rsp, 110h
0x180011bba  mov     [rbp+30h+var_70], 0FFFFFFFFFFFFFFFEh
0x180011bc2  mov     [rax+8], rbx
0x180011bc6  mov     [rax+10h], rsi
0x180011bca  mov     rdi, rdx
0x180011bcd  mov     rsi, rcx
0x180011bd0  lea     rcx, [rbp+30h+var_60]; this
0x180011bd4  call    ??0Kernel32RAII@@QEAA@XZ; Kernel32RAII::Kernel32RAII(void)
0x180011bd9  nop
0x180011bda  lea     r13, ?SystemSID@?1??CreatePrivateMutexForSystem@ConnectionPrivateMutexRAII@@CAXPEBGAEAVWin32HandleRAII@@@Z@4PAEA; uchar near * `ConnectionPrivateMutexRAII::CreatePrivateMutexForSystem(ushort const *,Win32HandleRAII &)'::`2'::SystemSID
0x180011be1  mov     r12d, 1
0x180011be7  cmp     cs:?fInitializedSID@?1??CreatePrivateMutexForSystem@ConnectionPrivateMutexRAII@@CAXPEBGAEAVWin32HandleRAII@@@Z@4_NA, 0; bool `ConnectionPrivateMutexRAII::CreatePrivateMutexForSystem(ushort const *,Win32HandleRAII &)'::`2'::fInitializedSID
0x180011bee  jnz     short loc_180011C18
0x180011bf0  mov     [rbp+30h+cbSid], 44h ; 'D'
0x180011bf7  lea     r9, [rbp+30h+cbSid]; cbSid
0x180011bfb  mov     r8, r13; pSid
0x180011bfe  xor     edx, edx; DomainSid
0x180011c00  lea     ecx, [rdx+16h]; WellKnownSidType
0x180011c03  call    cs:__imp_CreateWellKnownSid
0x180011c09  test    eax, eax
0x180011c0b  jz      loc_180011F04
0x180011c11  mov     cs:?fInitializedSID@?1??CreatePrivateMutexForSystem@ConnectionPrivateMutexRAII@@CAXPEBGAEAVWin32HandleRAII@@@Z@4_NA, r12b; bool `ConnectionPrivateMutexRAII::CreatePrivateMutexForSystem(ushort const *,Win32HandleRAII &)'::`2'::fInitializedSID
0x180011c18  lea     r8, [rbp+30h+var_60]; struct Kernel32RAII *
0x180011c1c  lea     rdx, aLocalsystem; "LocalSystem"
0x180011c23  lea     rcx, [rsp+130h+var_100]; this
0x180011c28  call    ??0BoundaryDescriptorRAII@@QEAA@PEBGAEAVKernel32RAII@@@Z; BoundaryDescriptorRAII::BoundaryDescriptorRAII(ushort const *,Kernel32RAII &)
0x180011c2d  nop
0x180011c2e  mov     rax, [rsp+130h+var_100]
0x180011c33  mov     rdx, r13
0x180011c36  lea     rcx, [rsp+130h+var_F8]
0x180011c3b  mov     rax, [rax+28h]
0x180011c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c44  test    eax, eax
0x180011c46  jz      loc_180011F68
0x180011c4c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x180011c53  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x180011c58  test    al, al
0x180011c5a  jz      short loc_180011CBF
0x180011c5c  mov     r9, rdi; struct Win32HandleRAII *
0x180011c5f  mov     r8, r13; void *
0x180011c62  mov     rdx, [rsp+130h+var_F8]; void *
0x180011c67  mov     rcx, rsi; lpName
0x180011c6a  call    ?CreatePrivateMutexInternal@ConnectionPrivateMutexRAII@@CAXPEBGPEAX1AEAVWin32HandleRAII@@@Z; ConnectionPrivateMutexRAII::CreatePrivateMutexInternal(ushort const *,void *,void *,Win32HandleRAII &)
0x180011c6f  nop
0x180011c70  mov     rcx, [rsp+130h+var_F8]
0x180011c75  test    rcx, rcx
0x180011c78  jz      short loc_180011C89
0x180011c7a  mov     rax, [rsp+130h+var_100]
0x180011c7f  mov     rax, [rax+20h]
0x180011c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c88  nop
0x180011c89  lea     rax, ??_7ModuleRAII@@6B@; const ModuleRAII::`vftable'
0x180011c90  mov     [rbp+30h+var_30], rax
0x180011c94  mov     rcx, [rbp+30h+hLibModule]; hLibModule
0x180011c98  test    rcx, rcx
0x180011c9b  jz      short loc_180011CA3
0x180011c9d  call    cs:__imp_FreeLibrary
0x180011ca3  lea     r11, [rsp+130h+var_20]
0x180011cab  mov     rbx, [r11+30h]
0x180011caf  mov     rsi, [r11+38h]
0x180011cb3  mov     rsp, r11
0x180011cb6  pop     r14
0x180011cb8  pop     r13
0x180011cba  pop     r12
0x180011cbc  pop     rdi
0x180011cbd  pop     rbp
0x180011cbe  retn
0x180011cbf  lea     rdx, aPrintconfigcon; "PrintConfigConnections"
0x180011cc6  mov     rcx, [rsp+130h+var_F8]
0x180011ccb  mov     rax, [rbp+30h+var_58]
0x180011ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cd4  test    rax, rax
0x180011cd7  jnz     loc_180011DCB
0x180011cdd  call    cs:__imp_GetLastError
0x180011ce3  cmp     eax, 34h ; '4'
0x180011ce6  jz      loc_180011DCB
0x180011cec  mov     rcx, r13; pSid
0x180011cef  call    cs:__imp_GetLengthSid
0x180011cf5  lea     ebx, [rax+10h]
0x180011cf8  mov     edx, ebx
0x180011cfa  lea     rcx, [rsp+130h+pAcl]
0x180011cff  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180011d04  nop
0x180011d05  mov     r14, [rsp+130h+pAcl]
0x180011d0a  mov     r8d, 2; dwAclRevision
0x180011d10  mov     edx, ebx; nAclLength
0x180011d12  mov     rcx, r14; pAcl
0x180011d15  call    cs:__imp_InitializeAcl
0x180011d1b  test    eax, eax
0x180011d1d  jz      loc_180011FCC
0x180011d23  mov     [rsp+130h+pSid], r13; pSid
0x180011d28  mov     r9d, 10000000h; AccessMask
0x180011d2e  xor     r8d, r8d; AceFlags
0x180011d31  lea     edx, [r8+2]; dwAceRevision
0x180011d35  mov     rcx, r14; pAcl
0x180011d38  call    cs:__imp_AddAccessAllowedAceEx
0x180011d3e  test    eax, eax
0x180011d40  jz      loc_180012030
0x180011d46  xorps   xmm0, xmm0
0x180011d49  xor     eax, eax
0x180011d4b  movups  [rbp+30h+pSecurityDescriptor], xmm0
0x180011d4f  movups  [rbp+30h+var_88], xmm0
0x180011d53  mov     [rbp+30h+var_78], rax
0x180011d57  mov     edx, r12d; dwRevision
0x180011d5a  lea     rcx, [rbp+30h+pSecurityDescriptor]; pSecurityDescriptor
0x180011d5e  call    cs:__imp_InitializeSecurityDescriptor
0x180011d64  test    eax, eax
0x180011d66  jz      loc_180012094
0x180011d6c  xor     r9d, r9d; bDaclDefaulted
0x180011d6f  mov     r8, r14; pDacl
0x180011d72  mov     edx, r12d; bDaclPresent
0x180011d75  lea     rcx, [rbp+30h+pSecurityDescriptor]; pSecurityDescriptor
0x180011d79  call    cs:__imp_SetSecurityDescriptorDacl
0x180011d7f  test    eax, eax
0x180011d81  jz      loc_1800120F8
0x180011d87  mov     [rsp+130h+var_D0], 18h
0x180011d90  mov     [rsp+130h+var_C0], 0
0x180011d99  lea     rax, [rbp+30h+pSecurityDescriptor]
0x180011d9d  mov     [rsp+130h+var_C8], rax
0x180011da2  lea     r8, aPrintconfigcon; "PrintConfigConnections"
0x180011da9  mov     rdx, [rsp+130h+var_F8]
0x180011dae  lea     rcx, [rsp+130h+var_D0]
0x180011db3  mov     rax, [rbp+30h+var_60]
0x180011db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dbc  test    rax, rax
0x180011dbf  jz      short loc_180011E3C
0x180011dc1  lea     rcx, [rsp+130h+pAcl]
0x180011dc6  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180011dcb  mov     r8, rsi; lpName
0x180011dce  mov     edx, r12d; bInheritHandle
0x180011dd1  mov     ecx, 10000000h; dwDesiredAccess
0x180011dd6  call    cs:__imp_OpenMutexW
0x180011ddc  mov     rbx, rax
0x180011ddf  mov     rcx, [rdi]; hObject
0x180011de2  lea     rdx, [rcx-1]
0x180011de6  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180011dea  ja      short loc_180011DF2
0x180011dec  call    cs:__imp_CloseHandle
0x180011df2  mov     [rdi], rbx
0x180011df5  lea     rax, [rbx+1]
0x180011df9  test    rax, 0FFFFFFFFFFFFFFFEh
0x180011dff  jnz     loc_180011C70
0x180011e05  mov     r8, rsi; lpName
0x180011e08  xor     edx, edx; bInitialOwner
0x180011e0a  xor     ecx, ecx; lpMutexAttributes
0x180011e0c  call    cs:__imp_CreateMutexW
0x180011e12  mov     rbx, rax
0x180011e15  mov     rcx, [rdi]; hObject
0x180011e18  lea     rdx, [rcx-1]
0x180011e1c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180011e20  ja      short loc_180011E28
0x180011e22  call    cs:__imp_CloseHandle
0x180011e28  mov     [rdi], rbx
0x180011e2b  lea     rax, [rbx+1]
0x180011e2f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180011e35  jz      short loc_180011EA0
0x180011e37  jmp     loc_180011C70
0x180011e3c  call    cs:__imp_GetLastError
0x180011e42  mov     ebx, eax
0x180011e44  test    eax, eax
0x180011e46  jle     short loc_180011E51
0x180011e48  movzx   ebx, ax
0x180011e4b  or      ebx, 80070000h
0x180011e51  lea     rax, WPP_GLOBAL_Control
0x180011e58  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e5f  cmp     rcx, rax
0x180011e62  jz      short loc_180011E82
0x180011e64  test    [rcx+44h], r12b
0x180011e68  jz      short loc_180011E82
0x180011e6a  mov     edx, 16h
0x180011e6f  mov     r9d, ebx
0x180011e72  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x180011e79  mov     rcx, [rcx+38h]
0x180011e7d  call    WPP_SF_d
0x180011e82  mov     edx, ebx; int
0x180011e84  lea     rcx, [rsp+130h+pExceptionObject]; this
0x180011e89  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180011e8e  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180011e95  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x180011e9a  call    _CxxThrowException_0
0x180011ea0  call    cs:__imp_GetLastError
0x180011ea6  mov     ebx, eax
0x180011ea8  test    eax, eax
0x180011eaa  jle     short loc_180011EB5
0x180011eac  movzx   ebx, ax
0x180011eaf  or      ebx, 80070000h
0x180011eb5  lea     rax, WPP_GLOBAL_Control
0x180011ebc  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ec3  cmp     rcx, rax
0x180011ec6  jz      short loc_180011EE6
0x180011ec8  test    [rcx+44h], r12b
0x180011ecc  jz      short loc_180011EE6
0x180011ece  mov     edx, 17h
0x180011ed3  mov     r9d, ebx
0x180011ed6  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x180011edd  mov     rcx, [rcx+38h]
0x180011ee1  call    WPP_SF_d
0x180011ee6  mov     edx, ebx; int
0x180011ee8  lea     rcx, [rsp+130h+pExceptionObject]; this
0x180011eed  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180011ef2  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180011ef9  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x180011efe  call    _CxxThrowException_0
0x180011f04  call    cs:__imp_GetLastError
0x180011f0a  mov     ebx, eax
0x180011f0c  test    eax, eax
0x180011f0e  jle     short loc_180011F19
0x180011f10  movzx   ebx, ax
0x180011f13  or      ebx, 80070000h
0x180011f19  lea     rax, WPP_GLOBAL_Control
0x180011f20  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f27  cmp     rcx, rax
0x180011f2a  jz      short loc_180011F4A
0x180011f2c  test    [rcx+44h], r12b
0x180011f30  jz      short loc_180011F4A
0x180011f32  mov     edx, 11h
0x180011f37  mov     r9d, ebx
0x180011f3a  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x180011f41  mov     rcx, [rcx+38h]
0x180011f45  call    WPP_SF_d
0x180011f4a  mov     edx, ebx; int
0x180011f4c  lea     rcx, [rsp+130h+pAcl]; this
0x180011f51  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180011f56  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180011f5d  lea     rcx, [rsp+130h+pAcl]; pExceptionObject
0x180011f62  call    _CxxThrowException_0
0x180011f68  call    cs:__imp_GetLastError
0x180011f6e  mov     ebx, eax
0x180011f70  test    eax, eax
0x180011f72  jle     short loc_180011F7D
0x180011f74  movzx   ebx, ax
0x180011f77  or      ebx, 80070000h
0x180011f7d  lea     rax, WPP_GLOBAL_Control
0x180011f84  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f8b  cmp     rcx, rax
0x180011f8e  jz      short loc_180011FAE
0x180011f90  test    [rcx+44h], r12b
0x180011f94  jz      short loc_180011FAE
0x180011f96  mov     edx, 0Bh
0x180011f9b  mov     r9d, ebx
0x180011f9e  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x180011fa5  mov     rcx, [rcx+38h]
0x180011fa9  call    WPP_SF_d
0x180011fae  mov     edx, ebx; int
0x180011fb0  lea     rcx, [rsp+130h+pAcl]; this
0x180011fb5  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180011fba  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180011fc1  lea     rcx, [rsp+130h+pAcl]; pExceptionObject
0x180011fc6  call    _CxxThrowException_0
0x180011fcc  call    cs:__imp_GetLastError
0x180011fd2  mov     ebx, eax
0x180011fd4  test    eax, eax
0x180011fd6  jle     short loc_180011FE1
0x180011fd8  movzx   ebx, ax
0x180011fdb  or      ebx, 80070000h
0x180011fe1  lea     rax, WPP_GLOBAL_Control
0x180011fe8  mov     rcx, cs:WPP_GLOBAL_Control
0x180011fef  cmp     rcx, rax
0x180011ff2  jz      short loc_180012012
0x180011ff4  test    [rcx+44h], r12b
0x180011ff8  jz      short loc_180012012
0x180011ffa  mov     edx, 12h
0x180011fff  mov     r9d, ebx
0x180012002  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x180012009  mov     rcx, [rcx+38h]
0x18001200d  call    WPP_SF_d
0x180012012  mov     edx, ebx; int
0x180012014  lea     rcx, [rsp+130h+pExceptionObject]; this
0x180012019  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18001201e  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180012025  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x18001202a  call    _CxxThrowException_0
0x180012030  call    cs:__imp_GetLastError
0x180012036  mov     ebx, eax
0x180012038  test    eax, eax
0x18001203a  jle     short loc_180012045
0x18001203c  movzx   ebx, ax
0x18001203f  or      ebx, 80070000h
0x180012045  lea     rax, WPP_GLOBAL_Control
0x18001204c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012053  cmp     rcx, rax
0x180012056  jz      short loc_180012076
0x180012058  test    [rcx+44h], r12b
0x18001205c  jz      short loc_180012076
0x18001205e  mov     edx, 13h
0x180012063  mov     r9d, ebx
0x180012066  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x18001206d  mov     rcx, [rcx+38h]
0x180012071  call    WPP_SF_d
0x180012076  mov     edx, ebx; int
0x180012078  lea     rcx, [rsp+130h+pExceptionObject]; this
0x18001207d  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180012082  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
  ... truncated ...
```
