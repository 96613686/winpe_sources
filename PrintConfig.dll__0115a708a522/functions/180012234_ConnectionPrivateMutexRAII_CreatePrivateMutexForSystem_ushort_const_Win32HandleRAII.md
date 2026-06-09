# ConnectionPrivateMutexRAII::CreatePrivateMutexForSystem(ushort const *,Win32HandleRAII &)

- ea: `0x180012234`
- end: `0x180012869`
- name: `?CreatePrivateMutexForSystem@ConnectionPrivateMutexRAII@@CAXPEBGAEAVWin32HandleRAII@@@Z`
- size: `1589`
- prototype: `void __fastcall(LPCWSTR lpName, struct Win32HandleRAII *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180013918`

## callees

- `0x180004564`
- `0x18000e82c`
- `0x18000e8ac`
- `0x18000f45c`
- `0x18000f830`
- `0x18000fb68`
- `0x180012234`
- `0x180012870`
- `0x1800194ec`
- `0x1800197b4`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x1800124dd`
- `KERNEL32!CreateMutexW` at `0x1800124dd`
- `KERNEL32!OpenMutexW` at `0x18001249b`
- `KERNEL32!OpenMutexW` at `0x18001249b`
- `KERNEL32!FreeLibrary` at `0x180012333`
- `KERNEL32!FreeLibrary` at `0x180012333`
- `KERNEL32!CloseHandle` at `0x1800124b7`
- `KERNEL32!CloseHandle` at `0x1800124f9`
- `KERNEL32!CloseHandle` at `0x1800124b7`
- `KERNEL32!CloseHandle` at `0x1800124f9`
- `KERNEL32!GetLastError` at `0x18001237a`
- `KERNEL32!GetLastError` at `0x180012519`
- `KERNEL32!GetLastError` at `0x180012583`
- `KERNEL32!GetLastError` at `0x1800125ed`
- `KERNEL32!GetLastError` at `0x180012657`
- `KERNEL32!GetLastError` at `0x1800126c1`
- `KERNEL32!GetLastError` at `0x18001272b`
- `KERNEL32!GetLastError` at `0x180012795`
- `KERNEL32!GetLastError` at `0x1800127ff`
- `KERNEL32!GetLastError` at `0x18001237a`
- `KERNEL32!GetLastError` at `0x180012519`
- `KERNEL32!GetLastError` at `0x180012583`
- `KERNEL32!GetLastError` at `0x1800125ed`
- `KERNEL32!GetLastError` at `0x180012657`
- `KERNEL32!GetLastError` at `0x1800126c1`
- `KERNEL32!GetLastError` at `0x18001272b`
- `KERNEL32!GetLastError` at `0x180012795`
- `KERNEL32!GetLastError` at `0x1800127ff`
- `ADVAPI32!GetLengthSid` at `0x180012392`
- `ADVAPI32!GetLengthSid` at `0x180012392`
- `ADVAPI32!InitializeAcl` at `0x1800123be`
- `ADVAPI32!InitializeAcl` at `0x1800123be`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180012434`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180012434`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180012413`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180012413`
- `ADVAPI32!CreateWellKnownSid` at `0x180012293`
- `ADVAPI32!CreateWellKnownSid` at `0x180012293`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x1800123e7`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x1800123e7`

## string_xrefs

- `0x18001235c`: `PrintConfigConnections`
- `0x180012463`: `PrintConfigConnections`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall ConnectionPrivateMutexRAII::CreatePrivateMutexForSystem(LPCWSTR lpName, HANDLE *a2)
{
  size_t v4; // rbx
  __int64 v5; // r8
  ACL *v6; // r14
  HANDLE v7; // rbx
  HANDLE MutexW; // rbx
  signed int v9; // eax
  unsigned int v10; // ebx
  signed int v11; // eax
  unsigned int v12; // ebx
  signed int LastError; // eax
  unsigned int v14; // ebx
  signed int v15; // eax
  unsigned int v16; // ebx
  signed int v17; // eax
  unsigned int v18; // ebx
  signed int v19; // eax
  unsigned int v20; // ebx
  signed int v21; // eax
  unsigned int v22; // ebx
  signed int v23; // eax
  unsigned int v24; // ebx
  __int64 v25; // [rsp+38h] [rbp-D0h] BYREF
  void *v26; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v28[3]; // [rsp+68h] [rbp-A0h] BYREF
  PACL pAcl[4]; // [rsp+80h] [rbp-88h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v31; // [rsp+C0h] [rbp-48h]
  __int64 v32; // [rsp+C8h] [rbp-40h]
  _QWORD v33[7]; // [rsp+D8h] [rbp-30h] BYREF
  HMODULE hLibModule; // [rsp+110h] [rbp+8h]
  DWORD cbSid; // [rsp+158h] [rbp+50h] BYREF

  v32 = -2;
  Kernel32RAII::Kernel32RAII((Kernel32RAII *)v33);
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
      v14 = LastError;
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x11u,
          (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
          v14);
      }
      hr_error::hr_error((hr_error *)pAcl, v14);
      throw (hr_error *)pAcl;
    }
    `ConnectionPrivateMutexRAII::CreatePrivateMutexForSystem'::`2'::fInitializedSID = 1;
  }
  BoundaryDescriptorRAII::BoundaryDescriptorRAII(
    (BoundaryDescriptorRAII *)&v25,
    L"LocalSystem",
    (struct Kernel32RAII *)v33);
  if ( !(*(unsigned int (__fastcall **)(void **, __int64 *))(v25 + 40))(
          &v26,
          `ConnectionPrivateMutexRAII::CreatePrivateMutexForSystem'::`2'::SystemSID) )
  {
    v15 = GetLastError();
    v16 = v15;
    if ( v15 > 0 )
      v16 = (unsigned __int16)v15 | 0x80070000;
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0xBu,
        (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
        v16);
    }
    hr_error::hr_error((hr_error *)pAcl, v16);
    throw (hr_error *)pAcl;
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    ConnectionPrivateMutexRAII::CreatePrivateMutexInternal(
      lpName,
      v26,
      `ConnectionPrivateMutexRAII::CreatePrivateMutexForSystem'::`2'::SystemSID,
      a2);
  }
  else
  {
    if ( !((__int64 (__fastcall *)(void *, const wchar_t *))v33[1])(v26, L"PrintConfigConnections")
      && GetLastError() != 52 )
    {
      v4 = GetLengthSid(`ConnectionPrivateMutexRAII::CreatePrivateMutexForSystem'::`2'::SystemSID) + 16;
      std::vector<unsigned char>::vector<unsigned char>((__int64 *)pAcl, v4, v5);
      v6 = pAcl[0];
      if ( !InitializeAcl(pAcl[0], v4, 2u) )
      {
        v17 = GetLastError();
        v18 = v17;
        if ( v17 > 0 )
          v18 = (unsigned __int16)v17 | 0x80070000;
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            0x12u,
            (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
            v18);
        }
        hr_error::hr_error((hr_error *)pExceptionObject, v18);
        throw (hr_error *)pExceptionObject;
      }
      if ( !AddAccessAllowedAceEx(
              v6,
              2u,
              0,
              0x10000000u,
              `ConnectionPrivateMutexRAII::CreatePrivateMutexForSystem'::`2'::SystemSID) )
      {
        v19 = GetLastError();
        v20 = v19;
        if ( v19 > 0 )
          v20 = (unsigned __int16)v19 | 0x80070000;
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            0x13u,
            (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
            v20);
        }
        hr_error::hr_error((hr_error *)pExceptionObject, v20);
        throw (hr_error *)pExceptionObject;
      }
      memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
      v31 = 0;
      if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
      {
        v21 = GetLastError();
        v22 = v21;
        if ( v21 > 0 )
          v22 = (unsigned __int16)v21 | 0x80070000;
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            0x14u,
            (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
            v22);
        }
        hr_error::hr_error((hr_error *)pExceptionObject, v22);
        throw (hr_error *)pExceptionObject;
      }
      if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v6, 0) )
      {
        v23 = GetLastError();
        v24 = v23;
        if ( v23 > 0 )
          v24 = (unsigned __int16)v23 | 0x80070000;
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            0x15u,
            (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
            v24);
        }
        hr_error::hr_error((hr_error *)pExceptionObject, v24);
        throw (hr_error *)pExceptionObject;
      }
      v28[0] = 24;
      v28[2] = 0;
      v28[1] = pSecurityDescriptor;
      if ( !((__int64 (__fastcall *)(_QWORD *, void *, const wchar_t *))v33[0])(v28, v26, L"PrintConfigConnections") )
      {
        v9 = GetLastError();
        v10 = v9;
        if ( v9 > 0 )
          v10 = (unsigned __int16)v9 | 0x80070000;
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            0x16u,
            (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
            v10);
        }
        hr_error::hr_error((hr_error *)pExceptionObject, v10);
        throw (hr_error *)pExceptionObject;
      }
      std::vector<char>::~vector<char>((char **)pAcl);
    }
    v7 = OpenMutexW(0x10000000u, 1, lpName);
    if ( (char *)*a2 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(*a2);
    *a2 = v7;
    if ( (((unsigned __int64)v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      MutexW = CreateMutexW(0, 0, lpName);
      if ( (char *)*a2 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(*a2);
      *a2 = MutexW;
      if ( (((unsigned __int64)MutexW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
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
            0x17u,
            (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
            v12);
        }
        hr_error::hr_error((hr_error *)pExceptionObject, v12);
        throw (hr_error *)pExceptionObject;
      }
    }
  }
  if ( v26 )
    (*(void (**)(void))(v25 + 32))();
  v33[6] = &ModuleRAII::`vftable';
  if ( hLibModule )
    FreeLibrary(hLibModule);
}

```

## disassembly

```asm
0x180012234  mov     rax, rsp
0x180012237  push    rbp
0x180012238  push    rdi
0x180012239  push    r12
0x18001223b  push    r13
0x18001223d  push    r14
0x18001223f  lea     rbp, [rax-38h]
0x180012243  sub     rsp, 110h
0x18001224a  mov     [rbp+30h+var_70], 0FFFFFFFFFFFFFFFEh
0x180012252  mov     [rax+8], rbx
0x180012256  mov     [rax+10h], rsi
0x18001225a  mov     rdi, rdx
0x18001225d  mov     rsi, rcx
0x180012260  lea     rcx, [rbp+30h+var_60]; this
0x180012264  call    ??0Kernel32RAII@@QEAA@XZ; Kernel32RAII::Kernel32RAII(void)
0x180012269  nop
0x18001226a  lea     r13, ?SystemSID@?1??CreatePrivateMutexForSystem@ConnectionPrivateMutexRAII@@CAXPEBGAEAVWin32HandleRAII@@@Z@4PAEA; uchar near * `ConnectionPrivateMutexRAII::CreatePrivateMutexForSystem(ushort const *,Win32HandleRAII &)'::`2'::SystemSID
0x180012271  mov     r12d, 1
0x180012277  cmp     cs:?fInitializedSID@?1??CreatePrivateMutexForSystem@ConnectionPrivateMutexRAII@@CAXPEBGAEAVWin32HandleRAII@@@Z@4_NA, 0; bool `ConnectionPrivateMutexRAII::CreatePrivateMutexForSystem(ushort const *,Win32HandleRAII &)'::`2'::fInitializedSID
0x18001227e  jnz     short loc_1800122AE
0x180012280  mov     [rbp+30h+cbSid], 44h ; 'D'
0x180012287  lea     r9, [rbp+30h+cbSid]; cbSid
0x18001228b  mov     r8, r13; pSid
0x18001228e  xor     edx, edx; DomainSid
0x180012290  lea     ecx, [rdx+16h]; WellKnownSidType
0x180012293  call    cs:__imp_CreateWellKnownSid
0x18001229a  nop     dword ptr [rax+rax+00h]
0x18001229f  test    eax, eax
0x1800122a1  jz      loc_1800125ED
0x1800122a7  mov     cs:?fInitializedSID@?1??CreatePrivateMutexForSystem@ConnectionPrivateMutexRAII@@CAXPEBGAEAVWin32HandleRAII@@@Z@4_NA, r12b; bool `ConnectionPrivateMutexRAII::CreatePrivateMutexForSystem(ushort const *,Win32HandleRAII &)'::`2'::fInitializedSID
0x1800122ae  lea     r8, [rbp+30h+var_60]; struct Kernel32RAII *
0x1800122b2  lea     rdx, aLocalsystem; "LocalSystem"
0x1800122b9  lea     rcx, [rsp+130h+var_100]; this
0x1800122be  call    ??0BoundaryDescriptorRAII@@QEAA@PEBGAEAVKernel32RAII@@@Z; BoundaryDescriptorRAII::BoundaryDescriptorRAII(ushort const *,Kernel32RAII &)
0x1800122c3  nop
0x1800122c4  mov     rax, [rsp+130h+var_100]
0x1800122c9  mov     rdx, r13
0x1800122cc  lea     rcx, [rsp+130h+var_F8]
0x1800122d1  mov     rax, [rax+28h]
0x1800122d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122da  test    eax, eax
0x1800122dc  jz      loc_180012657
0x1800122e2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x1800122e9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x1800122ee  test    al, al
0x1800122f0  jz      short loc_18001235C
0x1800122f2  mov     r9, rdi; struct Win32HandleRAII *
0x1800122f5  mov     r8, r13; void *
0x1800122f8  mov     rdx, [rsp+130h+var_F8]; void *
0x1800122fd  mov     rcx, rsi; lpName
0x180012300  call    ?CreatePrivateMutexInternal@ConnectionPrivateMutexRAII@@CAXPEBGPEAX1AEAVWin32HandleRAII@@@Z; ConnectionPrivateMutexRAII::CreatePrivateMutexInternal(ushort const *,void *,void *,Win32HandleRAII &)
0x180012305  nop
0x180012306  mov     rcx, [rsp+130h+var_F8]
0x18001230b  test    rcx, rcx
0x18001230e  jz      short loc_18001231F
0x180012310  mov     rax, [rsp+130h+var_100]
0x180012315  mov     rax, [rax+20h]
0x180012319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001231e  nop
0x18001231f  lea     rax, ??_7ModuleRAII@@6B@; const ModuleRAII::`vftable'
0x180012326  mov     [rbp+30h+var_30], rax
0x18001232a  mov     rcx, [rbp+30h+hLibModule]; hLibModule
0x18001232e  test    rcx, rcx
0x180012331  jz      short loc_18001233F
0x180012333  call    cs:__imp_FreeLibrary
0x18001233a  nop     dword ptr [rax+rax+00h]
0x18001233f  lea     r11, [rsp+130h+var_20]
0x180012347  mov     rbx, [r11+30h]
0x18001234b  mov     rsi, [r11+38h]
0x18001234f  mov     rsp, r11
0x180012352  pop     r14
0x180012354  pop     r13
0x180012356  pop     r12
0x180012358  pop     rdi
0x180012359  pop     rbp
0x18001235a  retn
0x18001235c  lea     rdx, aPrintconfigcon; "PrintConfigConnections"
0x180012363  mov     rcx, [rsp+130h+var_F8]
0x180012368  mov     rax, [rbp+30h+var_58]
0x18001236c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012371  test    rax, rax
0x180012374  jnz     loc_180012490
0x18001237a  call    cs:__imp_GetLastError
0x180012381  nop     dword ptr [rax+rax+00h]
0x180012386  cmp     eax, 34h ; '4'
0x180012389  jz      loc_180012490
0x18001238f  mov     rcx, r13; pSid
0x180012392  call    cs:__imp_GetLengthSid
0x180012399  nop     dword ptr [rax+rax+00h]
0x18001239e  lea     ebx, [rax+10h]
0x1800123a1  mov     edx, ebx
0x1800123a3  lea     rcx, [rsp+130h+pAcl]
0x1800123a8  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1800123ad  nop
0x1800123ae  mov     r14, [rsp+130h+pAcl]
0x1800123b3  mov     r8d, 2; dwAclRevision
0x1800123b9  mov     edx, ebx; nAclLength
0x1800123bb  mov     rcx, r14; pAcl
0x1800123be  call    cs:__imp_InitializeAcl
0x1800123c5  nop     dword ptr [rax+rax+00h]
0x1800123ca  test    eax, eax
0x1800123cc  jz      loc_1800126C1
0x1800123d2  mov     [rsp+130h+pSid], r13; pSid
0x1800123d7  mov     r9d, 10000000h; AccessMask
0x1800123dd  xor     r8d, r8d; AceFlags
0x1800123e0  lea     edx, [r8+2]; dwAceRevision
0x1800123e4  mov     rcx, r14; pAcl
0x1800123e7  call    cs:__imp_AddAccessAllowedAceEx
0x1800123ee  nop     dword ptr [rax+rax+00h]
0x1800123f3  test    eax, eax
0x1800123f5  jz      loc_18001272B
0x1800123fb  xorps   xmm0, xmm0
0x1800123fe  xor     eax, eax
0x180012400  movups  [rbp+30h+pSecurityDescriptor], xmm0
0x180012404  movups  [rbp+30h+var_88], xmm0
0x180012408  mov     [rbp+30h+var_78], rax
0x18001240c  mov     edx, r12d; dwRevision
0x18001240f  lea     rcx, [rbp+30h+pSecurityDescriptor]; pSecurityDescriptor
0x180012413  call    cs:__imp_InitializeSecurityDescriptor
0x18001241a  nop     dword ptr [rax+rax+00h]
0x18001241f  test    eax, eax
0x180012421  jz      loc_180012795
0x180012427  xor     r9d, r9d; bDaclDefaulted
0x18001242a  mov     r8, r14; pDacl
0x18001242d  mov     edx, r12d; bDaclPresent
0x180012430  lea     rcx, [rbp+30h+pSecurityDescriptor]; pSecurityDescriptor
0x180012434  call    cs:__imp_SetSecurityDescriptorDacl
0x18001243b  nop     dword ptr [rax+rax+00h]
0x180012440  test    eax, eax
0x180012442  jz      loc_1800127FF
0x180012448  mov     [rsp+130h+var_D0], 18h
0x180012451  mov     [rsp+130h+var_C0], 0
0x18001245a  lea     rax, [rbp+30h+pSecurityDescriptor]
0x18001245e  mov     [rsp+130h+var_C8], rax
0x180012463  lea     r8, aPrintconfigcon; "PrintConfigConnections"
0x18001246a  mov     rdx, [rsp+130h+var_F8]
0x18001246f  lea     rcx, [rsp+130h+var_D0]
0x180012474  mov     rax, [rbp+30h+var_60]
0x180012478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001247d  test    rax, rax
0x180012480  jz      loc_180012519
0x180012486  lea     rcx, [rsp+130h+pAcl]
0x18001248b  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180012490  mov     r8, rsi; lpName
0x180012493  mov     edx, r12d; bInheritHandle
0x180012496  mov     ecx, 10000000h; dwDesiredAccess
0x18001249b  call    cs:__imp_OpenMutexW
0x1800124a2  nop     dword ptr [rax+rax+00h]
0x1800124a7  mov     rbx, rax
0x1800124aa  mov     rcx, [rdi]; hObject
0x1800124ad  lea     rdx, [rcx-1]
0x1800124b1  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800124b5  ja      short loc_1800124C3
0x1800124b7  call    cs:__imp_CloseHandle
0x1800124be  nop     dword ptr [rax+rax+00h]
0x1800124c3  mov     [rdi], rbx
0x1800124c6  lea     rax, [rbx+1]
0x1800124ca  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800124d0  jnz     loc_180012306
0x1800124d6  mov     r8, rsi; lpName
0x1800124d9  xor     edx, edx; bInitialOwner
0x1800124db  xor     ecx, ecx; lpMutexAttributes
0x1800124dd  call    cs:__imp_CreateMutexW
0x1800124e4  nop     dword ptr [rax+rax+00h]
0x1800124e9  mov     rbx, rax
0x1800124ec  mov     rcx, [rdi]; hObject
0x1800124ef  lea     rdx, [rcx-1]
0x1800124f3  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800124f7  ja      short loc_180012505
0x1800124f9  call    cs:__imp_CloseHandle
0x180012500  nop     dword ptr [rax+rax+00h]
0x180012505  mov     [rdi], rbx
0x180012508  lea     rax, [rbx+1]
0x18001250c  test    rax, 0FFFFFFFFFFFFFFFEh
0x180012512  jz      short loc_180012583
0x180012514  jmp     loc_180012306
0x180012519  call    cs:__imp_GetLastError
0x180012520  nop     dword ptr [rax+rax+00h]
0x180012525  mov     ebx, eax
0x180012527  test    eax, eax
0x180012529  jle     short loc_180012534
0x18001252b  movzx   ebx, ax
0x18001252e  or      ebx, 80070000h
0x180012534  lea     rax, WPP_GLOBAL_Control
0x18001253b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012542  cmp     rcx, rax
0x180012545  jz      short loc_180012565
0x180012547  test    [rcx+44h], r12b
0x18001254b  jz      short loc_180012565
0x18001254d  mov     edx, 16h
0x180012552  mov     r9d, ebx
0x180012555  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x18001255c  mov     rcx, [rcx+38h]
0x180012560  call    WPP_SF_d
0x180012565  mov     edx, ebx; int
0x180012567  lea     rcx, [rsp+130h+pExceptionObject]; this
0x18001256c  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180012571  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180012578  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x18001257d  call    _CxxThrowException_0
0x180012583  call    cs:__imp_GetLastError
0x18001258a  nop     dword ptr [rax+rax+00h]
0x18001258f  mov     ebx, eax
0x180012591  test    eax, eax
0x180012593  jle     short loc_18001259E
0x180012595  movzx   ebx, ax
0x180012598  or      ebx, 80070000h
0x18001259e  lea     rax, WPP_GLOBAL_Control
0x1800125a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125ac  cmp     rcx, rax
0x1800125af  jz      short loc_1800125CF
0x1800125b1  test    [rcx+44h], r12b
0x1800125b5  jz      short loc_1800125CF
0x1800125b7  mov     edx, 17h
0x1800125bc  mov     r9d, ebx
0x1800125bf  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x1800125c6  mov     rcx, [rcx+38h]
0x1800125ca  call    WPP_SF_d
0x1800125cf  mov     edx, ebx; int
0x1800125d1  lea     rcx, [rsp+130h+pExceptionObject]; this
0x1800125d6  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800125db  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800125e2  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x1800125e7  call    _CxxThrowException_0
0x1800125ed  call    cs:__imp_GetLastError
0x1800125f4  nop     dword ptr [rax+rax+00h]
0x1800125f9  mov     ebx, eax
0x1800125fb  test    eax, eax
0x1800125fd  jle     short loc_180012608
0x1800125ff  movzx   ebx, ax
0x180012602  or      ebx, 80070000h
0x180012608  lea     rax, WPP_GLOBAL_Control
0x18001260f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012616  cmp     rcx, rax
0x180012619  jz      short loc_180012639
0x18001261b  test    [rcx+44h], r12b
0x18001261f  jz      short loc_180012639
0x180012621  mov     edx, 11h
0x180012626  mov     r9d, ebx
0x180012629  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x180012630  mov     rcx, [rcx+38h]
0x180012634  call    WPP_SF_d
0x180012639  mov     edx, ebx; int
0x18001263b  lea     rcx, [rsp+130h+pAcl]; this
0x180012640  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180012645  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18001264c  lea     rcx, [rsp+130h+pAcl]; pExceptionObject
0x180012651  call    _CxxThrowException_0
0x180012657  call    cs:__imp_GetLastError
0x18001265e  nop     dword ptr [rax+rax+00h]
0x180012663  mov     ebx, eax
0x180012665  test    eax, eax
0x180012667  jle     short loc_180012672
0x180012669  movzx   ebx, ax
0x18001266c  or      ebx, 80070000h
0x180012672  lea     rax, WPP_GLOBAL_Control
0x180012679  mov     rcx, cs:WPP_GLOBAL_Control
0x180012680  cmp     rcx, rax
0x180012683  jz      short loc_1800126A3
0x180012685  test    [rcx+44h], r12b
0x180012689  jz      short loc_1800126A3
0x18001268b  mov     edx, 0Bh
0x180012690  mov     r9d, ebx
0x180012693  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x18001269a  mov     rcx, [rcx+38h]
0x18001269e  call    WPP_SF_d
0x1800126a3  mov     edx, ebx; int
0x1800126a5  lea     rcx, [rsp+130h+pAcl]; this
0x1800126aa  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x1800126af  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x1800126b6  lea     rcx, [rsp+130h+pAcl]; pExceptionObject
0x1800126bb  call    _CxxThrowException_0
0x1800126c1  call    cs:__imp_GetLastError
0x1800126c8  nop     dword ptr [rax+rax+00h]
0x1800126cd  mov     ebx, eax
0x1800126cf  test    eax, eax
0x1800126d1  jle     short loc_1800126DC
0x1800126d3  movzx   ebx, ax
0x1800126d6  or      ebx, 80070000h
0x1800126dc  lea     rax, WPP_GLOBAL_Control
0x1800126e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800126ea  cmp     rcx, rax
0x1800126ed  jz      short loc_18001270D
0x1800126ef  test    [rcx+44h], r12b
0x1800126f3  jz      short loc_18001270D
0x1800126f5  mov     edx, 12h
0x1800126fa  mov     r9d, ebx
0x1800126fd  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x180012704  mov     rcx, [rcx+38h]
0x180012708  call    WPP_SF_d
0x18001270d  mov     edx, ebx; int
0x18001270f  lea     rcx, [rsp+130h+pExceptionObject]; this
0x180012714  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x180012719  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x180012720  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x180012725  call    _CxxThrowException_0
0x18001272b  call    cs:__imp_GetLastError
0x180012732  nop     dword ptr [rax+rax+00h]
0x180012737  mov     ebx, eax
0x180012739  test    eax, eax
  ... truncated ...
```
