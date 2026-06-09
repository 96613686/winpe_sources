# SystemSettings::WorkAccess::MDMExportSetting::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x180025e30`
- end: `0x18002612b`
- name: `?GetProperty@MDMExportSetting@WorkAccess@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `763`
- prototype: `int(SystemSettings::WorkAccess::MDMExportSetting *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800076ac`
- `0x1800096ec`
- `0x1800119c0`
- `0x1800136e8`
- `0x180015000`
- `0x180020584`
- `0x180024f44`
- `0x180025e30`
- `0x180026380`
- `0x180042e1c`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026029`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026029`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025e83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025ec6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025eea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025f8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002603c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002607e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002609c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800260d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800260f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025e83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025ec6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025eea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025f8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002603c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002607e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002609c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800260d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800260f2`

## string_xrefs

- `0x180025eb0`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`
- `0x180025f62`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`
- `0x180025fb8`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`
- `0x18002600c`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`
- `0x180026069`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`
- `0x180025e97`: `SystemSettings_WorkAccess_ExportMdm_ActionDescription`
- `0x180025ff3`: `SystemSettings_WorkAccess_ExportMdm_AdditionalDescriptionFormat`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SystemSettings::WorkAccess::MDMExportSetting::GetProperty(
        SystemSettings::WorkAccess::MDMExportSetting *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  struct IInspectable **v5; // rdx
  const unsigned __int16 *v6; // r8
  const unsigned __int16 *v7; // r8
  HSTRING *v8; // r8
  int ResourceStringById; // eax
  unsigned int v10; // ebx
  struct IInspectable **v12; // rdx
  struct IInspectable *v13; // rdi
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rbx
  int v18; // eax
  unsigned __int16 **v19; // r8
  int v20; // eax
  HSTRING *StringRawBuffer; // rbx
  int v22; // eax
  HSTRING v23; // [rsp+20h] [rbp-30h] BYREF
  __int64 v24; // [rsp+28h] [rbp-28h] BYREF
  struct IInspectable *v25; // [rsp+30h] [rbp-20h] BYREF
  LPCVOID lpSource; // [rsp+38h] [rbp-18h] BYREF
  __int64 v27; // [rsp+40h] [rbp-10h]
  __int64 v28; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  HSTRING string; // [rsp+88h] [rbp+38h] BYREF

  if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005C4F0, (const unsigned __int16 *)a3) )
  {
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005B4C0, v6) )
    {
      WindowsDeleteString(0);
      string = 0;
      ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                             (SystemSettings::DataModel *)L"SystemSettings_WorkAccess_ExportMdm_ActionDescription",
                             &string,
                             v8);
      v10 = ResourceStringById;
      if ( ResourceStringById >= 0 )
      {
        SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
        WindowsDeleteString(string);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x124,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
        (const char *)(unsigned int)ResourceStringById,
        (int)v23);
      WindowsDeleteString(string);
    }
    else
    {
      if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005B698, v7) )
        return 0;
      v25 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
      SystemSettings::WorkAccess::GetDiagnosticsDesktopDisplayPath(&v25, v12);
      v24 = 0;
      v13 = v25;
      QueryInterface = v25->lpVtbl->QueryInterface;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
      v15 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))QueryInterface)(
              v13,
              &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
              &v24);
      v10 = v15;
      if ( v15 >= 0 )
      {
        string = 0;
        v16 = v24;
        v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 152LL);
        WindowsDeleteString(0);
        string = 0;
        v18 = v17(v16, &string);
        v10 = v18;
        if ( v18 >= 0 )
        {
          lpSource = 0;
          v27 = 0;
          v28 = 0;
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpSource);
          v27 = -1;
          v28 = -1;
          v20 = SystemSettings::DataModel::GetResourceStringById(
                  (SystemSettings::DataModel *)L"SystemSettings_WorkAccess_ExportMdm_AdditionalDescriptionFormat",
                  (const unsigned __int16 *)&lpSource,
                  v19);
          v10 = v20;
          if ( v20 >= 0 )
          {
            StringRawBuffer = (HSTRING *)WindowsGetStringRawBuffer(string, 0);
            WindowsDeleteString(0);
            v23 = 0;
            v22 = SystemSettings::DataModel::FormatMessageArgAllocHString(
                    lpSource,
                    (const unsigned __int16 *)&v23,
                    StringRawBuffer);
            v10 = v22;
            if ( v22 >= 0 )
            {
              SystemSettings::DataModel::PropValueHelper::CreateString(v23, a3);
              WindowsDeleteString(v23);
              v23 = 0;
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpSource);
              WindowsDeleteString(string);
              string = 0;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
              return 0;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x139,
              (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
              (const char *)(unsigned int)v22,
              (int)v23);
            WindowsDeleteString(v23);
            v23 = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x135,
              (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
              (const char *)(unsigned int)v20,
              (int)v23);
          }
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpSource);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x131,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
            (const char *)(unsigned int)v18,
            (int)v23);
        }
        WindowsDeleteString(string);
        string = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12F,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
          (const char *)(unsigned int)v15,
          (int)v23);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    }
    return v10;
  }
  SystemSettings::WorkAccess::GetDiagnosticsDesktopDisplayPath(a3, v5);
  return 0;
}

```

## disassembly

```asm
0x180025e30  mov     [rsp-18h+arg_0], rbx
0x180025e35  mov     [rsp-18h+arg_8], rsi
0x180025e3a  push    rbp
0x180025e3b  push    rdi
0x180025e3c  push    r14
0x180025e3e  mov     rbp, rsp
0x180025e41  sub     rsp, 50h
0x180025e45  mov     rsi, r8
0x180025e48  mov     rbx, rdx
0x180025e4b  lea     rdx, stru_18005C4F0; HSTRING
0x180025e52  mov     rcx, rbx; this
0x180025e55  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180025e5a  xor     r14d, r14d
0x180025e5d  test    al, al
0x180025e5f  jz      short loc_180025E6E
0x180025e61  mov     rcx, rsi; this
0x180025e64  call    ?GetDiagnosticsDesktopDisplayPath@WorkAccess@SystemSettings@@YAJPEAPEAUIInspectable@@@Z; SystemSettings::WorkAccess::GetDiagnosticsDesktopDisplayPath(IInspectable * *)
0x180025e69  jmp     loc_180026115
0x180025e6e  lea     rdx, stru_18005B4C0; HSTRING
0x180025e75  mov     rcx, rbx; this
0x180025e78  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180025e7d  test    al, al
0x180025e7f  jz      short loc_180025EFB
0x180025e81  xor     ecx, ecx; string
0x180025e83  call    cs:__imp_WindowsDeleteString
0x180025e8a  nop     dword ptr [rax+rax+00h]
0x180025e8f  mov     [rbp+string], r14
0x180025e93  lea     rdx, [rbp+string]; HSTRING *
0x180025e97  lea     rcx, aSystemsettings_32; "SystemSettings_WorkAccess_ExportMdm_Act"...
0x180025e9e  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180025ea3  mov     ebx, eax
0x180025ea5  test    eax, eax
0x180025ea7  jns     short loc_180025ED9
0x180025ea9  mov     rcx, [rbp+18h]; this
0x180025ead  mov     r9d, eax; char *
0x180025eb0  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\settingshandlers\\w"...
0x180025eb7  mov     edx, 124h; void *
0x180025ebc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025ec1  nop
0x180025ec2  mov     rcx, [rbp+string]; string
0x180025ec6  call    cs:__imp_WindowsDeleteString
0x180025ecd  nop     dword ptr [rax+rax+00h]
0x180025ed2  mov     eax, ebx
0x180025ed4  jmp     loc_180026117
0x180025ed9  mov     rdx, rsi; struct IInspectable **
0x180025edc  mov     rcx, [rbp+string]; HSTRING
0x180025ee0  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x180025ee5  nop
0x180025ee6  mov     rcx, [rbp+string]; string
0x180025eea  call    cs:__imp_WindowsDeleteString
0x180025ef1  nop     dword ptr [rax+rax+00h]
0x180025ef6  jmp     loc_180026115
0x180025efb  lea     rdx, stru_18005B698; HSTRING
0x180025f02  mov     rcx, rbx; this
0x180025f05  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180025f0a  test    al, al
0x180025f0c  jz      loc_180026115
0x180025f12  mov     [rbp+var_20], r14
0x180025f16  lea     rcx, [rbp+var_20]
0x180025f1a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025f1f  lea     rcx, [rbp+var_20]; this
0x180025f23  call    ?GetDiagnosticsDesktopDisplayPath@WorkAccess@SystemSettings@@YAJPEAPEAUIInspectable@@@Z; SystemSettings::WorkAccess::GetDiagnosticsDesktopDisplayPath(IInspectable * *)
0x180025f28  mov     [rbp+var_28], r14
0x180025f2c  mov     rdi, [rbp+var_20]
0x180025f30  mov     rax, [rdi]
0x180025f33  mov     rbx, [rax]
0x180025f36  lea     rcx, [rbp+var_28]
0x180025f3a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025f3f  lea     r8, [rbp+var_28]
0x180025f43  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180025f4a  mov     rcx, rdi
0x180025f4d  mov     rax, rbx
0x180025f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f55  mov     ebx, eax
0x180025f57  test    eax, eax
0x180025f59  jns     short loc_180025F78
0x180025f5b  mov     rcx, [rbp+18h]; this
0x180025f5f  mov     r9d, eax; char *
0x180025f62  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\settingshandlers\\w"...
0x180025f69  mov     edx, 12Fh; void *
0x180025f6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025f73  jmp     loc_1800260AC
0x180025f78  mov     [rbp+string], r14
0x180025f7c  mov     rdi, [rbp+var_28]
0x180025f80  mov     rax, [rdi]
0x180025f83  mov     rbx, [rax+98h]
0x180025f8a  xor     ecx, ecx; string
0x180025f8c  call    cs:__imp_WindowsDeleteString
0x180025f93  nop     dword ptr [rax+rax+00h]
0x180025f98  mov     [rbp+string], r14
0x180025f9c  lea     rdx, [rbp+string]
0x180025fa0  mov     rcx, rdi
0x180025fa3  mov     rax, rbx
0x180025fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025fab  mov     ebx, eax
0x180025fad  test    eax, eax
0x180025faf  jns     short loc_180025FCE
0x180025fb1  mov     rcx, [rbp+18h]; this
0x180025fb5  mov     r9d, eax; char *
0x180025fb8  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\settingshandlers\\w"...
0x180025fbf  mov     edx, 131h; void *
0x180025fc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025fc9  jmp     loc_180026098
0x180025fce  mov     [rbp+lpSource], r14
0x180025fd2  mov     [rbp+var_10], r14
0x180025fd6  mov     [rbp+var_8], r14
0x180025fda  lea     rcx, [rbp+lpSource]
0x180025fde  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180025fe3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025fe7  mov     [rbp+var_10], rax
0x180025feb  mov     [rbp+var_8], rax
0x180025fef  lea     rdx, [rbp+lpSource]; unsigned __int16 *
0x180025ff3  lea     rcx, aSystemsettings_31; "SystemSettings_WorkAccess_ExportMdm_Add"...
0x180025ffa  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAG@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,ushort * *)
0x180025fff  mov     ebx, eax
0x180026001  test    eax, eax
0x180026003  jns     short loc_18002601F
0x180026005  mov     rcx, [rbp+18h]; this
0x180026009  mov     r9d, eax; char *
0x18002600c  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\settingshandlers\\w"...
0x180026013  mov     edx, 135h; void *
0x180026018  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002601d  jmp     short loc_18002608E
0x18002601f  mov     [rbp+var_30], r14
0x180026023  xor     edx, edx; length
0x180026025  mov     rcx, [rbp+string]; string
0x180026029  call    cs:__imp_WindowsGetStringRawBuffer
0x180026030  nop     dword ptr [rax+rax+00h]
0x180026035  mov     rbx, rax
0x180026038  mov     rcx, [rbp+var_30]; string
0x18002603c  call    cs:__imp_WindowsDeleteString
0x180026043  nop     dword ptr [rax+rax+00h]
0x180026048  mov     [rbp+var_30], r14
0x18002604c  mov     r8, rbx; HSTRING *
0x18002604f  lea     rdx, [rbp+var_30]; unsigned __int16 *
0x180026053  mov     rcx, [rbp+lpSource]; lpSource
0x180026057  call    ?FormatMessageArgAllocHString@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@ZZ; SystemSettings::DataModel::FormatMessageArgAllocHString(ushort const *,HSTRING__ * *,...)
0x18002605c  mov     ebx, eax
0x18002605e  test    eax, eax
0x180026060  jns     short loc_1800260C4
0x180026062  mov     rcx, [rbp+18h]; this
0x180026066  mov     r9d, eax; char *
0x180026069  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\settingshandlers\\w"...
0x180026070  mov     edx, 139h; void *
0x180026075  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002607a  mov     rcx, [rbp+var_30]; string
0x18002607e  call    cs:__imp_WindowsDeleteString
0x180026085  nop     dword ptr [rax+rax+00h]
0x18002608a  mov     [rbp+var_30], r14
0x18002608e  lea     rcx, [rbp+lpSource]
0x180026092  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180026097  nop
0x180026098  mov     rcx, [rbp+string]; string
0x18002609c  call    cs:__imp_WindowsDeleteString
0x1800260a3  nop     dword ptr [rax+rax+00h]
0x1800260a8  mov     [rbp+string], r14
0x1800260ac  lea     rcx, [rbp+var_28]
0x1800260b0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800260b5  nop
0x1800260b6  lea     rcx, [rbp+var_20]
0x1800260ba  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800260bf  jmp     loc_180025ED2
0x1800260c4  mov     rdx, rsi; struct IInspectable **
0x1800260c7  mov     rcx, [rbp+var_30]; HSTRING
0x1800260cb  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x1800260d0  mov     rcx, [rbp+var_30]; string
0x1800260d4  call    cs:__imp_WindowsDeleteString
0x1800260db  nop     dword ptr [rax+rax+00h]
0x1800260e0  mov     [rbp+var_30], r14
0x1800260e4  lea     rcx, [rbp+lpSource]
0x1800260e8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800260ed  nop
0x1800260ee  mov     rcx, [rbp+string]; string
0x1800260f2  call    cs:__imp_WindowsDeleteString
0x1800260f9  nop     dword ptr [rax+rax+00h]
0x1800260fe  mov     [rbp+string], r14
0x180026102  lea     rcx, [rbp+var_28]
0x180026106  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002610b  nop
0x18002610c  lea     rcx, [rbp+var_20]
0x180026110  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026115  xor     eax, eax
0x180026117  mov     rbx, [rsp+50h+arg_0]
0x18002611c  mov     rsi, [rsp+50h+arg_8]
0x180026121  add     rsp, 50h
0x180026125  pop     r14
0x180026127  pop     rdi
0x180026128  pop     rbp
0x180026129  retn
```
