# Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::Initialize(SERVICE_STATUS_HANDLE__ *)

- ea: `0x18008d578`
- end: `0x18008d811`
- name: `?Initialize@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@QEAAJPEAUSERVICE_STATUS_HANDLE__@@@Z`
- size: `665`
- prototype: `__int64 __fastcall(Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation *__hidden this, struct SERVICE_STATUS_HANDLE__ *)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007f748`
- `0x18008d484`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18006c628`
- `0x18007755c`
- `0x18008019c`
- `0x18008084c`
- `0x1800814a8`
- `0x1800839bc`
- `0x1800873a4`
- `0x18008c244`
- `0x18008cef8`
- `0x18008d04c`
- `0x18008d270`
- `0x18008d310`
- `0x18008d578`
- `0x18008dbe4`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18008d59c`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18008d59c`
- `api-ms-win-service-core-l1-1-4!GetServiceDirectory` at `0x18008d5d3`
- `api-ms-win-service-core-l1-1-4!GetServiceDirectory` at `0x18008d646`
- `api-ms-win-service-core-l1-1-4!GetServiceDirectory` at `0x18008d5d3`
- `api-ms-win-service-core-l1-1-4!GetServiceDirectory` at `0x18008d646`

## string_xrefs

- `0x18008d5f9`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`
- `0x18008d658`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`
- `0x18008d702`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`
- `0x18008d7b4`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`
- `0x18008d6e8`: `%windir%\ServiceState\wmansvc`
- `0x18008d6b0`: `%windir%\ServiceState\autopilot`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::Initialize(
        Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation *this,
        struct SERVICE_STATUS_HANDLE__ *a2)
{
  char IsStateSeparationEnabled; // al
  int ServiceDirectory; // eax
  const char *v6; // r9
  unsigned int v7; // ebx
  __int64 result; // rax
  unsigned int v9; // eax
  unsigned int v10; // ebx
  char *v11; // rbx
  int NonStateSeparationAwareExpandedFilePath; // eax
  unsigned int v13; // edi
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  int FolderHierarchyWithAcls; // edi
  __int64 v19; // rax
  __int64 v20; // rcx
  unsigned int *v21; // [rsp+20h] [rbp-48h]
  unsigned int v22; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v23[4]; // [rsp+34h] [rbp-34h] BYREF
  _QWORD v24[4]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  try
  {
    if ( IsStateSeparationEnabled )
    {
      *(_BYTE *)this = 1;
      if ( a2 )
      {
        v22 = 0;
        ServiceDirectory = GetServiceDirectory(a2, 0, 0, 0);
        v7 = ServiceDirectory;
        if ( ServiceDirectory != 122 )
        {
          if ( ServiceDirectory > 0 )
            v7 = (unsigned __int16)ServiceDirectory | 0x80070000;
          if ( (v7 & 0x80000000) != 0 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x45,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
              (const char *)v7,
              (int)&v22);
          return v7;
        }
        std::vector<unsigned short>::vector<unsigned short>(v24, v22 + 1, v23);
        v21 = &v22;
        v9 = GetServiceDirectory(a2, 0, v24[0], (__int64)(v24[1] - v24[0]) >> 1);
        if ( v9 )
        {
          v10 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x4D,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
                  (const char *)v9,
                  (unsigned int)&v22);
          std::vector<unsigned short>::_Tidy(v24);
          return v10;
        }
        v11 = (char *)this + 8;
        std::wstring::assign((char *)this + 8, v24[0]);
        std::vector<unsigned short>::_Tidy(v24);
        goto LABEL_20;
      }
    }
    else
    {
      *(_BYTE *)this = 0;
    }
    std::wstring::wstring(v24);
    if ( (int)Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetNonStateSeparationAwareExpandedFilePath(L"%windir%\\ServiceState\\autopilot") >= 0
      && (unsigned __int8)Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::DirectoryExists(v24) )
    {
      v11 = (char *)this + 8;
      std::wstring::operator=((char *)this + 8, v24);
    }
    else
    {
      v11 = (char *)this + 8;
      NonStateSeparationAwareExpandedFilePath = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetNonStateSeparationAwareExpandedFilePath(L"%windir%\\ServiceState\\wmansvc");
      v13 = NonStateSeparationAwareExpandedFilePath;
      if ( NonStateSeparationAwareExpandedFilePath < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5C,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
          (const char *)(unsigned int)NonStateSeparationAwareExpandedFilePath,
          (int)v21);
        std::wstring::_Tidy_deallocate(v24);
        return v13;
      }
    }
    std::wstring::_Tidy_deallocate(v24);
LABEL_20:
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 0x80u) != 0 )
    {
      v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
      McTemplateU0z_EventWriteTransfer(v15, ManagementServiceStateSeparationFolderPath, v14);
    }
    if ( !(unsigned __int8)Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::DirectoryExists(v11) )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 0x80u) != 0 )
      {
        v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
        McTemplateU0z_EventWriteTransfer(v17, ManagementServiceStateSeparationFolderNotFound, v16);
      }
      std::wstring::wstring(v24, L"D:PAI(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)(A;OICI;FA;;;SU)(A;OICI;FR;;;WD)");
      FolderHierarchyWithAcls = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::CreateFolderHierarchyWithAcls(
                                  v11,
                                  v24);
      std::wstring::_Tidy_deallocate(v24);
      if ( FolderHierarchyWithAcls < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x66,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
          (const char *)(unsigned int)FolderHierarchyWithAcls,
          (int)v21);
        return (unsigned int)FolderHierarchyWithAcls;
      }
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 0x80u) != 0 )
      {
        v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
        McTemplateU0z_EventWriteTransfer(v20, ManagementServiceStateSeparationFolderCreated, v19);
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x6C,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x18008d578  mov     [rsp+arg_10], rbx
0x18008d57d  mov     [rsp+arg_18], rsi
0x18008d582  push    rdi
0x18008d583  sub     rsp, 60h
0x18008d587  mov     rax, cs:__security_cookie
0x18008d58e  xor     rax, rsp
0x18008d591  mov     [rsp+68h+var_10], rax
0x18008d596  mov     rsi, rdx
0x18008d599  mov     rdi, rcx
0x18008d59c  call    cs:__imp_RtlIsStateSeparationEnabled
0x18008d5a2  test    al, al
0x18008d5a4  jz      loc_18008D69D
0x18008d5aa  mov     byte ptr [rdi], 1
0x18008d5ad  test    rsi, rsi
0x18008d5b0  jz      loc_18008D6A0
0x18008d5b6  mov     [rsp+68h+var_38], 0
0x18008d5be  lea     rax, [rsp+68h+var_38]
0x18008d5c3  mov     qword ptr [rsp+68h+var_48], rax; int
0x18008d5c8  xor     r9d, r9d
0x18008d5cb  xor     r8d, r8d
0x18008d5ce  xor     edx, edx
0x18008d5d0  mov     rcx, rsi
0x18008d5d3  call    cs:__imp_GetServiceDirectory
0x18008d5d9  mov     ebx, eax
0x18008d5db  cmp     eax, 7Ah ; 'z'
0x18008d5de  jz      short loc_18008D611
0x18008d5e0  test    eax, eax
0x18008d5e2  jle     short loc_18008D5ED
0x18008d5e4  movzx   ebx, ax
0x18008d5e7  or      ebx, 80070000h
0x18008d5ed  test    ebx, ebx
0x18008d5ef  jns     short loc_18008D60A
0x18008d5f1  mov     rcx, [rsp+68h]; this
0x18008d5f6  mov     r9d, ebx; char *
0x18008d5f9  lea     r8, aOnecoreuapAdmi_67; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008d600  mov     edx, 45h ; 'E'; void *
0x18008d605  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d60a  mov     eax, ebx
0x18008d60c  jmp     loc_18008D7F1
0x18008d611  mov     edx, [rsp+68h+var_38]
0x18008d615  inc     edx
0x18008d617  lea     r8, [rsp+68h+var_34]
0x18008d61c  lea     rcx, [rsp+68h+var_30]
0x18008d621  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18008d626  nop
0x18008d627  mov     r8, [rsp+68h+var_30]
0x18008d62c  mov     r9, [rsp+68h+var_28]
0x18008d631  sub     r9, r8
0x18008d634  sar     r9, 1
0x18008d637  lea     rax, [rsp+68h+var_38]
0x18008d63c  mov     qword ptr [rsp+68h+var_48], rax; unsigned int
0x18008d641  xor     edx, edx
0x18008d643  mov     rcx, rsi
0x18008d646  call    cs:__imp_GetServiceDirectory
0x18008d64c  test    eax, eax
0x18008d64e  jz      short loc_18008D67C
0x18008d650  mov     rcx, [rsp+68h]; this
0x18008d655  mov     r9d, eax; char *
0x18008d658  lea     r8, aOnecoreuapAdmi_67; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008d65f  mov     edx, 4Dh ; 'M'; void *
0x18008d664  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008d669  mov     ebx, eax
0x18008d66b  lea     rcx, [rsp+68h+var_30]
0x18008d670  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18008d675  mov     eax, ebx
0x18008d677  jmp     loc_18008D7F1
0x18008d67c  lea     rbx, [rdi+8]
0x18008d680  mov     rdx, [rsp+68h+var_30]
0x18008d685  mov     rcx, rbx
0x18008d688  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18008d68d  nop
0x18008d68e  lea     rcx, [rsp+68h+var_30]
0x18008d693  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18008d698  jmp     loc_18008D72F
0x18008d69d  mov     byte ptr [rdi], 0
0x18008d6a0  lea     rcx, [rsp+68h+var_30]
0x18008d6a5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008d6aa  nop
0x18008d6ab  lea     rdx, [rsp+68h+var_30]
0x18008d6b0  lea     rcx, aWindirServices; "%windir%\\ServiceState\\autopilot"
0x18008d6b7  call    ?GetNonStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetNonStateSeparationAwareExpandedFilePath(ushort const *,std::wstring &)
0x18008d6bc  test    eax, eax
0x18008d6be  js      short loc_18008D6E1
0x18008d6c0  lea     rcx, [rsp+68h+var_30]
0x18008d6c5  call    ?DirectoryExists@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::DirectoryExists(std::wstring const &)
0x18008d6ca  test    al, al
0x18008d6cc  jz      short loc_18008D6E1
0x18008d6ce  lea     rbx, [rdi+8]
0x18008d6d2  lea     rdx, [rsp+68h+var_30]
0x18008d6d7  mov     rcx, rbx
0x18008d6da  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18008d6df  jmp     short loc_18008D725
0x18008d6e1  lea     rbx, [rdi+8]
0x18008d6e5  mov     rdx, rbx
0x18008d6e8  lea     rcx, aWindirServices_0; "%windir%\\ServiceState\\wmansvc"
0x18008d6ef  call    ?GetNonStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetNonStateSeparationAwareExpandedFilePath(ushort const *,std::wstring &)
0x18008d6f4  mov     edi, eax
0x18008d6f6  test    eax, eax
0x18008d6f8  jns     short loc_18008D725
0x18008d6fa  mov     rcx, [rsp+68h]; this
0x18008d6ff  mov     r9d, eax; char *
0x18008d702  lea     r8, aOnecoreuapAdmi_67; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008d709  mov     edx, 5Ch ; '\'; void *
0x18008d70e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d713  nop
0x18008d714  lea     rcx, [rsp+68h+var_30]
0x18008d719  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008d71e  mov     eax, edi
0x18008d720  jmp     loc_18008D7F1
0x18008d725  lea     rcx, [rsp+68h+var_30]
0x18008d72a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008d72f  cmp     byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 0
0x18008d736  jge     short loc_18008D74F
0x18008d738  mov     rcx, rbx
0x18008d73b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008d740  mov     r8, rax
0x18008d743  lea     rdx, ManagementServiceStateSeparationFolderPath
0x18008d74a  call    McTemplateU0z_EventWriteTransfer
0x18008d74f  mov     rcx, rbx
0x18008d752  call    ?DirectoryExists@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::DirectoryExists(std::wstring const &)
0x18008d757  test    al, al
0x18008d759  jnz     loc_18008D7E9
0x18008d75f  cmp     byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, al
0x18008d765  jge     short loc_18008D77E
0x18008d767  mov     rcx, rbx
0x18008d76a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008d76f  mov     r8, rax
0x18008d772  lea     rdx, ManagementServiceStateSeparationFolderNotFound
0x18008d779  call    McTemplateU0z_EventWriteTransfer
0x18008d77e  lea     rdx, aDPaiAOiciFaBaA; "D:PAI(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)(A"...
0x18008d785  lea     rcx, [rsp+68h+var_30]
0x18008d78a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008d78f  lea     rdx, [rsp+68h+var_30]
0x18008d794  mov     rcx, rbx
0x18008d797  call    ?CreateFolderHierarchyWithAcls@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::CreateFolderHierarchyWithAcls(std::wstring const &,std::wstring const &)
0x18008d79c  mov     edi, eax
0x18008d79e  lea     rcx, [rsp+68h+var_30]
0x18008d7a3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008d7a8  test    edi, edi
0x18008d7aa  jns     short loc_18008D7C9
0x18008d7ac  mov     rcx, [rsp+68h]; this
0x18008d7b1  mov     r9d, edi; char *
0x18008d7b4  lea     r8, aOnecoreuapAdmi_67; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008d7bb  mov     edx, 66h ; 'f'; void *
0x18008d7c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d7c5  mov     eax, edi
0x18008d7c7  jmp     short loc_18008D7F1
0x18008d7c9  cmp     byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 0
0x18008d7d0  jge     short loc_18008D7E9
0x18008d7d2  mov     rcx, rbx
0x18008d7d5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008d7da  mov     r8, rax
0x18008d7dd  lea     rdx, ManagementServiceStateSeparationFolderCreated
0x18008d7e4  call    McTemplateU0z_EventWriteTransfer
0x18008d7e9  xor     eax, eax
0x18008d7eb  jmp     short loc_18008D7F1
0x18008d7ed  mov     eax, [rsp+68h+var_38]
0x18008d7f1  mov     rcx, [rsp+68h+var_10]
0x18008d7f6  xor     rcx, rsp; StackCookie
0x18008d7f9  call    __security_check_cookie
0x18008d7fe  lea     r11, [rsp+68h+var_8]
0x18008d803  mov     rbx, [r11+20h]
0x18008d807  mov     rsi, [r11+28h]
0x18008d80b  mov     rsp, r11
0x18008d80e  pop     rdi
0x18008d80f  retn
```
