# SystemSettings::WorkAccess::CEnrollmentRemoveProfileSetting::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x18003e780`
- end: `0x18003e92f`
- name: `?GetProperty@CEnrollmentRemoveProfileSetting@WorkAccess@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `431`
- prototype: `int(SystemSettings::WorkAccess::CEnrollmentRemoveProfileSetting *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800096ec`
- `0x1800119c0`
- `0x180011a14`
- `0x180015000`
- `0x180016e84`
- `0x18003e780`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e87e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e90e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e87e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e90e`
- `policymanager!PolicyManager_GetPolicyInt` at `0x18003e815`
- `policymanager!PolicyManager_GetPolicyInt` at `0x18003e815`

## string_xrefs

- `0x18003e7c8`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003e86d`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003e8f0`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003e851`: `SystemSettings_WorkAccess_DisconnectConfirmation`
- `0x18003e838`: `CorpDeviceManagementRemoveNotAllowedText`
- `0x18003e7ad`: `SystemSettings_WorkAccess_DisconnectButton`
- `0x18003e8b5`: `SystemSettings_WorkAccess_DisconnectButton`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::CEnrollmentRemoveProfileSetting::GetProperty(
        SystemSettings::WorkAccess::CEnrollmentRemoveProfileSetting *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  const unsigned __int16 *v5; // r8
  int v6; // eax
  unsigned int v7; // ebx
  const unsigned __int16 *v9; // r8
  int PolicyInt; // eax
  __int64 v11; // rdx
  HSTRING v12; // rcx
  HSTRING v13; // rcx
  int v14; // eax
  __int64 v15; // rdx
  int v16; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HSTRING string; // [rsp+40h] [rbp+18h] BYREF

  *a3 = 0;
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005E0F0, (const unsigned __int16 *)a3) )
  {
    v6 = SystemSettings::DataModel::PropValueHelper::CreateString(L"SystemSettings_WorkAccess_DisconnectButton", a3);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x225,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
        (const char *)(unsigned int)v6,
        v16);
      return v7;
    }
    return 0;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005E188, v5) )
  {
    LODWORD(string) = 0;
    PolicyInt = PolicyManager_GetPolicyInt(L"Experience", L"AllowManualMDMUnenrollment", &string);
    v7 = PolicyInt;
    if ( PolicyInt < 0 )
    {
      v11 = 555;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
        (const char *)(unsigned int)PolicyInt,
        v16);
      v12 = 0;
LABEL_14:
      WindowsDeleteString(v12);
      return v7;
    }
    if ( (_DWORD)string == 1 )
    {
      PolicyInt = SystemSettings::DataModel::PropValueHelper::CreateString(
                    L"SystemSettings_WorkAccess_DisconnectConfirmation",
                    a3);
      v7 = PolicyInt;
      if ( PolicyInt < 0 )
      {
        v11 = 562;
        goto LABEL_13;
      }
    }
    else
    {
      PolicyInt = SystemSettings::DataModel::PropValueHelper::CreateString(
                    L"CorpDeviceManagementRemoveNotAllowedText",
                    a3);
      v7 = PolicyInt;
      if ( PolicyInt < 0 )
      {
        v11 = 558;
        goto LABEL_13;
      }
    }
    v13 = 0;
LABEL_23:
    WindowsDeleteString(v13);
    return 0;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005E148, v9) )
  {
    string = 0;
    v14 = Microsoft::WRL::Wrappers::HString::Set(
            (Microsoft::WRL::Wrappers::HString *)&string,
            L"SystemSettings_WorkAccess_DisconnectButton",
            0x2Au);
    v7 = v14;
    if ( v14 >= 0 )
    {
      v14 = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
      v7 = v14;
      if ( v14 >= 0 )
      {
        v13 = string;
        goto LABEL_23;
      }
      v15 = 569;
    }
    else
    {
      v15 = 568;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
      (const char *)(unsigned int)v14,
      v16);
    v12 = string;
    goto LABEL_14;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18003e780  mov     [rsp+arg_0], rbx
0x18003e785  push    rdi; int
0x18003e786  sub     rsp, 20h
0x18003e78a  mov     rbx, rdx
0x18003e78d  mov     qword ptr [r8], 0
0x18003e794  mov     rcx, rbx; this
0x18003e797  lea     rdx, stru_18005E0F0; HSTRING
0x18003e79e  mov     rdi, r8
0x18003e7a1  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18003e7a6  test    al, al
0x18003e7a8  jz      short loc_18003E7E3
0x18003e7aa  mov     rdx, rdi; struct IInspectable **
0x18003e7ad  lea     rcx, aSystemsettings_47; "SystemSettings_WorkAccess_DisconnectBut"...
0x18003e7b4  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18003e7b9  mov     ebx, eax
0x18003e7bb  test    eax, eax
0x18003e7bd  jns     loc_18003E91A
0x18003e7c3  mov     rcx, [rsp+28h]; this
0x18003e7c8  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003e7cf  mov     r9d, eax; char *
0x18003e7d2  mov     edx, 225h; void *
0x18003e7d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e7dc  mov     eax, ebx
0x18003e7de  jmp     loc_18003E923
0x18003e7e3  lea     rdx, stru_18005E188; HSTRING
0x18003e7ea  mov     rcx, rbx; this
0x18003e7ed  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18003e7f2  test    al, al
0x18003e7f4  jz      loc_18003E893
0x18003e7fa  lea     r8, [rsp+28h+string]
0x18003e7ff  mov     dword ptr [rsp+28h+string], 0
0x18003e807  lea     rdx, aAllowmanualmdm; "AllowManualMDMUnenrollment"
0x18003e80e  lea     rcx, aExperience; "Experience"
0x18003e815  call    cs:__imp_PolicyManager_GetPolicyInt
0x18003e81c  nop     dword ptr [rax+rax+00h]
0x18003e821  mov     ebx, eax
0x18003e823  test    eax, eax
0x18003e825  jns     short loc_18003E82E
0x18003e827  mov     edx, 22Bh
0x18003e82c  jmp     short loc_18003E868
0x18003e82e  cmp     dword ptr [rsp+28h+string], 1
0x18003e833  mov     rdx, rdi; struct IInspectable **
0x18003e836  jz      short loc_18003E851
0x18003e838  lea     rcx, aCorpdevicemana; "CorpDeviceManagementRemoveNotAllowedTex"...
0x18003e83f  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18003e844  mov     ebx, eax
0x18003e846  test    eax, eax
0x18003e848  jns     short loc_18003E88F
0x18003e84a  mov     edx, 22Eh
0x18003e84f  jmp     short loc_18003E868
0x18003e851  lea     rcx, aSystemsettings_7; "SystemSettings_WorkAccess_DisconnectCon"...
0x18003e858  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18003e85d  mov     ebx, eax
0x18003e85f  test    eax, eax
0x18003e861  jns     short loc_18003E88F
0x18003e863  mov     edx, 232h; void *
0x18003e868  mov     rcx, [rsp+28h]; this
0x18003e86d  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003e874  mov     r9d, eax; char *
0x18003e877  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e87c  xor     ecx, ecx; string
0x18003e87e  call    cs:__imp_WindowsDeleteString
0x18003e885  nop     dword ptr [rax+rax+00h]
0x18003e88a  jmp     loc_18003E7DC
0x18003e88f  xor     ecx, ecx
0x18003e891  jmp     short loc_18003E90E
0x18003e893  lea     rdx, stru_18005E148; HSTRING
0x18003e89a  mov     rcx, rbx; this
0x18003e89d  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18003e8a2  test    al, al
0x18003e8a4  jz      short loc_18003E91E
0x18003e8a6  mov     r8d, 2Ah ; '*'; unsigned int
0x18003e8ac  mov     [rsp+28h+string], 0
0x18003e8b5  lea     rdx, aSystemsettings_47; "SystemSettings_WorkAccess_DisconnectBut"...
0x18003e8bc  lea     rcx, [rsp+28h+string]; this
0x18003e8c1  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18003e8c6  mov     ebx, eax
0x18003e8c8  test    eax, eax
0x18003e8ca  jns     short loc_18003E8D3
0x18003e8cc  mov     edx, 238h
0x18003e8d1  jmp     short loc_18003E8EB
0x18003e8d3  mov     rcx, [rsp+28h+string]; HSTRING
0x18003e8d8  mov     rdx, rdi; struct IInspectable **
0x18003e8db  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x18003e8e0  mov     ebx, eax
0x18003e8e2  test    eax, eax
0x18003e8e4  jns     short loc_18003E909
0x18003e8e6  mov     edx, 239h; void *
0x18003e8eb  mov     rcx, [rsp+28h]; this
0x18003e8f0  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003e8f7  mov     r9d, eax; char *
0x18003e8fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e8ff  mov     rcx, [rsp+28h+string]
0x18003e904  jmp     loc_18003E87E
0x18003e909  mov     rcx, [rsp+28h+string]; string
0x18003e90e  call    cs:__imp_WindowsDeleteString
0x18003e915  nop     dword ptr [rax+rax+00h]
0x18003e91a  xor     eax, eax
0x18003e91c  jmp     short loc_18003E923
0x18003e91e  mov     eax, 80070057h
0x18003e923  mov     rbx, [rsp+28h+arg_0]
0x18003e928  add     rsp, 20h
0x18003e92c  pop     rdi
0x18003e92d  retn
```
