# Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::Initialize(SERVICE_STATUS_HANDLE__ *)

- ea: `0x18008e664`
- end: `0x18008e90f`
- name: `?Initialize@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@QEAAJPEAUSERVICE_STATUS_HANDLE__@@@Z`
- size: `683`
- prototype: `__int64 __fastcall(Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation *__hidden this, struct SERVICE_STATUS_HANDLE__ *)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180080120`
- `0x18008e570`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x18006cb28`
- `0x180077de0`
- `0x180080bac`
- `0x180081294`
- `0x180081f38`
- `0x180084574`
- `0x180088144`
- `0x18008d290`
- `0x18008dffc`
- `0x18008e138`
- `0x18008e344`
- `0x18008e3ec`
- `0x18008e664`
- `0x18008ecb8`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18008e688`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18008e688`
- `api-ms-win-service-core-l1-1-4!GetServiceDirectory` at `0x18008e6c5`
- `api-ms-win-service-core-l1-1-4!GetServiceDirectory` at `0x18008e73e`
- `api-ms-win-service-core-l1-1-4!GetServiceDirectory` at `0x18008e6c5`
- `api-ms-win-service-core-l1-1-4!GetServiceDirectory` at `0x18008e73e`

## string_xrefs

- `0x18008e6f1`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`
- `0x18008e756`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`
- `0x18008e800`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`
- `0x18008e8b2`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`
- `0x18008e7e6`: `%windir%\ServiceState\wmansvc`
- `0x18008e7ae`: `%windir%\ServiceState\autopilot`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18008e664  mov     [rsp+arg_10], rbx
0x18008e669  mov     [rsp+arg_18], rsi
0x18008e66e  push    rdi
0x18008e66f  sub     rsp, 60h
0x18008e673  mov     rax, cs:__security_cookie
0x18008e67a  xor     rax, rsp
0x18008e67d  mov     [rsp+68h+var_10], rax
0x18008e682  mov     rsi, rdx
0x18008e685  mov     rdi, rcx
0x18008e688  call    cs:__imp_RtlIsStateSeparationEnabled
0x18008e68f  nop     dword ptr [rax+rax+00h]
0x18008e694  test    al, al
0x18008e696  jz      loc_18008E79B
0x18008e69c  mov     byte ptr [rdi], 1
0x18008e69f  test    rsi, rsi
0x18008e6a2  jz      loc_18008E79E
0x18008e6a8  mov     [rsp+68h+var_38], 0
0x18008e6b0  lea     rax, [rsp+68h+var_38]
0x18008e6b5  mov     qword ptr [rsp+68h+var_48], rax; int
0x18008e6ba  xor     r9d, r9d
0x18008e6bd  xor     r8d, r8d
0x18008e6c0  xor     edx, edx
0x18008e6c2  mov     rcx, rsi
0x18008e6c5  call    cs:__imp_GetServiceDirectory
0x18008e6cc  nop     dword ptr [rax+rax+00h]
0x18008e6d1  mov     ebx, eax
0x18008e6d3  cmp     eax, 7Ah ; 'z'
0x18008e6d6  jz      short loc_18008E709
0x18008e6d8  test    eax, eax
0x18008e6da  jle     short loc_18008E6E5
0x18008e6dc  movzx   ebx, ax
0x18008e6df  or      ebx, 80070000h
0x18008e6e5  test    ebx, ebx
0x18008e6e7  jns     short loc_18008E702
0x18008e6e9  mov     rcx, [rsp+68h]; this
0x18008e6ee  mov     r9d, ebx; char *
0x18008e6f1  lea     r8, aOnecoreuapAdmi_67; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008e6f8  mov     edx, 45h ; 'E'; void *
0x18008e6fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e702  mov     eax, ebx
0x18008e704  jmp     loc_18008E8EF
0x18008e709  mov     edx, [rsp+68h+var_38]
0x18008e70d  inc     edx
0x18008e70f  lea     r8, [rsp+68h+var_34]
0x18008e714  lea     rcx, [rsp+68h+var_30]
0x18008e719  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18008e71e  nop
0x18008e71f  mov     r8, [rsp+68h+var_30]
0x18008e724  mov     r9, [rsp+68h+var_28]
0x18008e729  sub     r9, r8
0x18008e72c  sar     r9, 1
0x18008e72f  lea     rax, [rsp+68h+var_38]
0x18008e734  mov     qword ptr [rsp+68h+var_48], rax; unsigned int
0x18008e739  xor     edx, edx
0x18008e73b  mov     rcx, rsi
0x18008e73e  call    cs:__imp_GetServiceDirectory
0x18008e745  nop     dword ptr [rax+rax+00h]
0x18008e74a  test    eax, eax
0x18008e74c  jz      short loc_18008E77A
0x18008e74e  mov     rcx, [rsp+68h]; this
0x18008e753  mov     r9d, eax; char *
0x18008e756  lea     r8, aOnecoreuapAdmi_67; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008e75d  mov     edx, 4Dh ; 'M'; void *
0x18008e762  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008e767  mov     ebx, eax
0x18008e769  lea     rcx, [rsp+68h+var_30]
0x18008e76e  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18008e773  mov     eax, ebx
0x18008e775  jmp     loc_18008E8EF
0x18008e77a  lea     rbx, [rdi+8]
0x18008e77e  mov     rdx, [rsp+68h+var_30]
0x18008e783  mov     rcx, rbx
0x18008e786  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18008e78b  nop
0x18008e78c  lea     rcx, [rsp+68h+var_30]
0x18008e791  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18008e796  jmp     loc_18008E82D
0x18008e79b  mov     byte ptr [rdi], 0
0x18008e79e  lea     rcx, [rsp+68h+var_30]
0x18008e7a3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008e7a8  nop
0x18008e7a9  lea     rdx, [rsp+68h+var_30]
0x18008e7ae  lea     rcx, aWindirServices; "%windir%\\ServiceState\\autopilot"
0x18008e7b5  call    ?GetNonStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetNonStateSeparationAwareExpandedFilePath(ushort const *,std::wstring &)
0x18008e7ba  test    eax, eax
0x18008e7bc  js      short loc_18008E7DF
0x18008e7be  lea     rcx, [rsp+68h+var_30]
0x18008e7c3  call    ?DirectoryExists@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::DirectoryExists(std::wstring const &)
0x18008e7c8  test    al, al
0x18008e7ca  jz      short loc_18008E7DF
0x18008e7cc  lea     rbx, [rdi+8]
0x18008e7d0  lea     rdx, [rsp+68h+var_30]
0x18008e7d5  mov     rcx, rbx
0x18008e7d8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18008e7dd  jmp     short loc_18008E823
0x18008e7df  lea     rbx, [rdi+8]
0x18008e7e3  mov     rdx, rbx
0x18008e7e6  lea     rcx, aWindirServices_0; "%windir%\\ServiceState\\wmansvc"
0x18008e7ed  call    ?GetNonStateSeparationAwareExpandedFilePath@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetNonStateSeparationAwareExpandedFilePath(ushort const *,std::wstring &)
0x18008e7f2  mov     edi, eax
0x18008e7f4  test    eax, eax
0x18008e7f6  jns     short loc_18008E823
0x18008e7f8  mov     rcx, [rsp+68h]; this
0x18008e7fd  mov     r9d, eax; char *
0x18008e800  lea     r8, aOnecoreuapAdmi_67; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008e807  mov     edx, 5Ch ; '\'; void *
0x18008e80c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e811  nop
0x18008e812  lea     rcx, [rsp+68h+var_30]
0x18008e817  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008e81c  mov     eax, edi
0x18008e81e  jmp     loc_18008E8EF
0x18008e823  lea     rcx, [rsp+68h+var_30]
0x18008e828  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008e82d  cmp     byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 0
0x18008e834  jge     short loc_18008E84D
0x18008e836  mov     rcx, rbx
0x18008e839  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008e83e  mov     r8, rax
0x18008e841  lea     rdx, ManagementServiceStateSeparationFolderPath
0x18008e848  call    McTemplateU0z_EventWriteTransfer
0x18008e84d  mov     rcx, rbx
0x18008e850  call    ?DirectoryExists@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::DirectoryExists(std::wstring const &)
0x18008e855  test    al, al
0x18008e857  jnz     loc_18008E8E7
0x18008e85d  cmp     byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, al
0x18008e863  jge     short loc_18008E87C
0x18008e865  mov     rcx, rbx
0x18008e868  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008e86d  mov     r8, rax
0x18008e870  lea     rdx, ManagementServiceStateSeparationFolderNotFound
0x18008e877  call    McTemplateU0z_EventWriteTransfer
0x18008e87c  lea     rdx, aDPaiAOiciFaBaA; "D:PAI(A;OICI;FA;;;BA)(A;OICI;FA;;;SY)(A"...
0x18008e883  lea     rcx, [rsp+68h+var_30]
0x18008e888  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008e88d  lea     rdx, [rsp+68h+var_30]
0x18008e892  mov     rcx, rbx
0x18008e895  call    ?CreateFolderHierarchyWithAcls@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::CreateFolderHierarchyWithAcls(std::wstring const &,std::wstring const &)
0x18008e89a  mov     edi, eax
0x18008e89c  lea     rcx, [rsp+68h+var_30]
0x18008e8a1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008e8a6  test    edi, edi
0x18008e8a8  jns     short loc_18008E8C7
0x18008e8aa  mov     rcx, [rsp+68h]; this
0x18008e8af  mov     r9d, edi; char *
0x18008e8b2  lea     r8, aOnecoreuapAdmi_67; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008e8b9  mov     edx, 66h ; 'f'; void *
0x18008e8be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e8c3  mov     eax, edi
0x18008e8c5  jmp     short loc_18008E8EF
0x18008e8c7  cmp     byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 0
0x18008e8ce  jge     short loc_18008E8E7
0x18008e8d0  mov     rcx, rbx
0x18008e8d3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008e8d8  mov     r8, rax
0x18008e8db  lea     rdx, ManagementServiceStateSeparationFolderCreated
0x18008e8e2  call    McTemplateU0z_EventWriteTransfer
0x18008e8e7  xor     eax, eax
0x18008e8e9  jmp     short loc_18008E8EF
0x18008e8eb  mov     eax, [rsp+68h+var_38]
0x18008e8ef  mov     rcx, [rsp+68h+var_10]
0x18008e8f4  xor     rcx, rsp; StackCookie
0x18008e8f7  call    __security_check_cookie
0x18008e8fc  lea     r11, [rsp+68h+var_8]
0x18008e901  mov     rbx, [r11+20h]
0x18008e905  mov     rsi, [r11+28h]
0x18008e909  mov     rsp, r11
0x18008e90c  pop     rdi
0x18008e90d  retn
```
