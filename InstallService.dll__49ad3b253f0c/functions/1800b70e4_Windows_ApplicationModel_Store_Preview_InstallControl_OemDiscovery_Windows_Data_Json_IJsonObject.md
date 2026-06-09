# Windows::ApplicationModel::Store::Preview::InstallControl::OemDiscovery(Windows::Data::Json::IJsonObject * *)

- ea: `0x1800b70e4`
- end: `0x1800b739c`
- name: `?OemDiscovery@InstallControl@Preview@Store@ApplicationModel@Windows@@YAJPEAPEAUIJsonObject@Json@Data@5@@Z`
- size: `696`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::Store::Preview::InstallControl *__hidden this, struct Windows::Data::Json::IJsonObject **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18009e72c`

## callees

- `0x18000e44c`
- `0x1800101f4`
- `0x180021438`
- `0x18002d98c`
- `0x18007e714`
- `0x1800865d4`
- `0x1800b0e38`
- `0x1800b70e4`
- `0x1800d5db4`
- `0x180100014`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b7112`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b7137`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b715c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b7181`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b72b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b7338`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b735c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b736a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b7378`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b7386`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b7112`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b7137`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b715c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b7181`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b72b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b7338`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b735c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b736a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b7378`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b7386`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b71b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b71ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b71ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b7229`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b71b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b71ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b71ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b7229`

## string_xrefs

- `0x1800b718f`: `SystemProductName`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::OemDiscovery(
        Windows::ApplicationModel::Store::Preview::InstallControl *this,
        struct Windows::Data::Json::IJsonObject **a2)
{
  HSTRING *v3; // r9
  HSTRING *v4; // r9
  HSTRING *v5; // r9
  HSTRING *v6; // r9
  struct Windows::Data::Json::IJsonObject *v7; // rax
  TraceLoggingCorrelationVector *v8; // rax
  __int64 v9; // rdi
  int SLSUri; // ebx
  struct Windows::Data::Json::IJsonObject *v11; // rax
  __int64 v13; // [rsp+58h] [rbp-51h] BYREF
  HSTRING newString; // [rsp+60h] [rbp-49h] BYREF
  __int64 v15; // [rsp+68h] [rbp-41h] BYREF
  std::_Ref_count_base *v16; // [rsp+70h] [rbp-39h]
  _QWORD v17[16]; // [rsp+80h] [rbp-29h] BYREF
  HSTRING v18; // [rsp+110h] [rbp+67h] BYREF
  HSTRING v19; // [rsp+118h] [rbp+6Fh] BYREF
  HSTRING string; // [rsp+120h] [rbp+77h] BYREF
  struct Windows::Data::Json::IJsonObject *v21; // [rsp+128h] [rbp+7Fh] BYREF

  *(_QWORD *)this = 0;
  string = 0;
  v19 = 0;
  v18 = 0;
  WindowsDeleteString(0);
  newString = 0;
  Windows::ApplicationModel::Store::Preview::InstallControl::GetRegValueString(
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Store",
    L"OemId",
    &newString,
    v3);
  WindowsDeleteString(string);
  string = 0;
  Windows::ApplicationModel::Store::Preview::InstallControl::GetRegValueString(
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Store",
    L"StoreContentModifier",
    &string,
    v4);
  WindowsDeleteString(v19);
  v19 = 0;
  Windows::ApplicationModel::Store::Preview::InstallControl::GetRegValueString(
    L"System\\CurrentControlSet\\Control\\SystemInformation",
    L"SystemManufacturer",
    &v19,
    v5);
  WindowsDeleteString(v18);
  v18 = 0;
  Windows::ApplicationModel::Store::Preview::InstallControl::GetRegValueString(
    L"System\\CurrentControlSet\\Control\\SystemInformation",
    L"SystemProductName",
    &v18,
    v6);
  v17[0] = L"oemId";
  v17[1] = WindowsGetStringRawBuffer(newString, 0);
  v17[2] = L"scmId";
  v17[3] = WindowsGetStringRawBuffer(string, 0);
  v17[4] = L"phoneManufacturerName";
  v17[5] = &dword_18023C12C;
  v17[6] = L"smBiosManufacturerName";
  v17[7] = WindowsGetStringRawBuffer(v19, 0);
  v17[8] = L"phoneDeviceModel";
  v17[9] = &dword_18023C12C;
  v17[10] = L"smBiosDm";
  v17[11] = WindowsGetStringRawBuffer(v18, 0);
  v7 = (struct Windows::Data::Json::IJsonObject *)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  v21 = v7;
  if ( v7 )
    v8 = TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v7);
  else
    v8 = 0;
  std::shared_ptr<TraceLoggingCorrelationVector>::shared_ptr<TraceLoggingCorrelationVector>(&v15, v8);
  v9 = v15;
  if ( v15 )
  {
    v13 = 0;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v13);
    SLSUri = GetSLSUri(4, v17, 6);
    if ( SLSUri >= 0 )
    {
      WindowsDeleteString(0);
      SLSUri = FetchUriResponseWithAuthTicket(v9, v13, 0, 0);
      if ( SLSUri >= 0 )
      {
        v21 = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v21);
        SLSUri = Json_Parse(0, &v21);
        if ( SLSUri >= 0 )
        {
          v11 = v21;
          v21 = 0;
          *(_QWORD *)this = v11;
        }
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v21);
      }
      WindowsDeleteString(0);
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v13);
  }
  else
  {
    SLSUri = -2147024882;
  }
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  WindowsDeleteString(v18);
  v18 = 0;
  WindowsDeleteString(v19);
  v19 = 0;
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(newString);
  return (unsigned int)SLSUri;
}

```

## disassembly

```asm
0x1800b70e4  push    rbp
0x1800b70e6  push    rbx
0x1800b70e7  push    rsi
0x1800b70e8  push    rdi
0x1800b70e9  push    r14
0x1800b70eb  lea     rbp, [rsp-37h]
0x1800b70f0  sub     rsp, 0E0h
0x1800b70f7  mov     rsi, rcx
0x1800b70fa  xor     r14d, r14d
0x1800b70fd  mov     [rcx], r14
0x1800b7100  mov     [rbp+57h+newString], r14
0x1800b7104  mov     [rbp+57h+string], r14
0x1800b7108  mov     [rbp+57h+arg_8], r14
0x1800b710c  mov     [rbp+57h+arg_0], r14
0x1800b7110  xor     ecx, ecx; string
0x1800b7112  call    cs:__imp_WindowsDeleteString
0x1800b7118  mov     [rbp+57h+newString], r14
0x1800b711c  lea     r8, [rbp+57h+newString]; newString
0x1800b7120  lea     rdx, aOemid_1; "OemId"
0x1800b7127  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800b712e  call    ?GetRegValueString@InstallControl@Preview@Store@ApplicationModel@Windows@@YAXPEBG0PEAPEAUHSTRING__@@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::GetRegValueString(ushort const *,ushort const *,HSTRING__ * *)
0x1800b7133  mov     rcx, [rbp+57h+string]; string
0x1800b7137  call    cs:__imp_WindowsDeleteString
0x1800b713d  mov     [rbp+57h+string], r14
0x1800b7141  lea     r8, [rbp+57h+string]; newString
0x1800b7145  lea     rdx, aStorecontentmo; "StoreContentModifier"
0x1800b714c  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800b7153  call    ?GetRegValueString@InstallControl@Preview@Store@ApplicationModel@Windows@@YAXPEBG0PEAPEAUHSTRING__@@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::GetRegValueString(ushort const *,ushort const *,HSTRING__ * *)
0x1800b7158  mov     rcx, [rbp+57h+arg_8]; string
0x1800b715c  call    cs:__imp_WindowsDeleteString
0x1800b7162  mov     [rbp+57h+arg_8], r14
0x1800b7166  lea     r8, [rbp+57h+arg_8]; newString
0x1800b716a  lea     rdx, aSystemmanufact; "SystemManufacturer"
0x1800b7171  lea     rcx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Sys"...
0x1800b7178  call    ?GetRegValueString@InstallControl@Preview@Store@ApplicationModel@Windows@@YAXPEBG0PEAPEAUHSTRING__@@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::GetRegValueString(ushort const *,ushort const *,HSTRING__ * *)
0x1800b717d  mov     rcx, [rbp+57h+arg_0]; string
0x1800b7181  call    cs:__imp_WindowsDeleteString
0x1800b7187  mov     [rbp+57h+arg_0], r14
0x1800b718b  lea     r8, [rbp+57h+arg_0]; newString
0x1800b718f  lea     rdx, aSystemproductn; "SystemProductName"
0x1800b7196  lea     rcx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Sys"...
0x1800b719d  call    ?GetRegValueString@InstallControl@Preview@Store@ApplicationModel@Windows@@YAXPEBG0PEAPEAUHSTRING__@@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::GetRegValueString(ushort const *,ushort const *,HSTRING__ * *)
0x1800b71a2  lea     rax, aOemid_0; "oemId"
0x1800b71a9  mov     [rbp+57h+var_80], rax
0x1800b71ad  xor     edx, edx; length
0x1800b71af  mov     rcx, [rbp+57h+newString]; string
0x1800b71b3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b71b9  mov     [rbp+57h+var_78], rax
0x1800b71bd  lea     rax, aScmid_0; "scmId"
0x1800b71c4  mov     [rbp+57h+var_70], rax
0x1800b71c8  xor     edx, edx; length
0x1800b71ca  mov     rcx, [rbp+57h+string]; string
0x1800b71ce  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b71d4  mov     [rbp+57h+var_68], rax
0x1800b71d8  lea     rax, aPhonemanufactu; "phoneManufacturerName"
0x1800b71df  mov     [rbp+57h+var_60], rax
0x1800b71e3  lea     rbx, dword_18023C12C
0x1800b71ea  mov     [rbp+57h+var_58], rbx
0x1800b71ee  lea     rax, aSmbiosmanufact; "smBiosManufacturerName"
0x1800b71f5  mov     [rbp+57h+var_50], rax
0x1800b71f9  xor     edx, edx; length
0x1800b71fb  mov     rcx, [rbp+57h+arg_8]; string
0x1800b71ff  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b7205  mov     [rbp+57h+var_48], rax
0x1800b7209  lea     rax, aPhonedevicemod; "phoneDeviceModel"
0x1800b7210  mov     [rbp+57h+var_40], rax
0x1800b7214  mov     [rbp+57h+var_38], rbx
0x1800b7218  lea     rax, aSmbiosdm; "smBiosDm"
0x1800b721f  mov     [rbp+57h+var_30], rax
0x1800b7223  xor     edx, edx; length
0x1800b7225  mov     rcx, [rbp+57h+arg_0]; string
0x1800b7229  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b722f  mov     [rbp+57h+var_28], rax
0x1800b7233  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b723a  mov     ecx, 90h; unsigned __int64
0x1800b723f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800b7244  mov     [rbp+57h+arg_18], rax
0x1800b7248  test    rax, rax
0x1800b724b  jz      short loc_1800B7257
0x1800b724d  mov     rcx, rax; this
0x1800b7250  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800b7255  jmp     short loc_1800B725A
0x1800b7257  mov     rax, r14
0x1800b725a  mov     rdx, rax
0x1800b725d  lea     rcx, [rbp+57h+var_98]
0x1800b7261  call    ??$?0VTraceLoggingCorrelationVector@@$0A@@?$shared_ptr@VTraceLoggingCorrelationVector@@@std@@QEAA@PEAVTraceLoggingCorrelationVector@@@Z; std::shared_ptr<TraceLoggingCorrelationVector>::shared_ptr<TraceLoggingCorrelationVector>(TraceLoggingCorrelationVector *)
0x1800b7266  nop
0x1800b7267  mov     rdi, [rbp+57h+var_98]
0x1800b726b  test    rdi, rdi
0x1800b726e  jnz     short loc_1800B727A
0x1800b7270  mov     ebx, 8007000Eh
0x1800b7275  jmp     loc_1800B7349
0x1800b727a  mov     [rbp+57h+var_A8], r14
0x1800b727e  lea     rcx, [rbp+57h+var_A8]
0x1800b7282  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800b7287  lea     rax, [rbp+57h+var_A8]
0x1800b728b  mov     [rsp+100h+var_D8], rax
0x1800b7290  mov     [rsp+100h+var_E0], rdi
0x1800b7295  xor     r9d, r9d
0x1800b7298  lea     r8d, [r9+6]
0x1800b729c  lea     rdx, [rbp+57h+var_80]
0x1800b72a0  lea     ecx, [r9+4]
0x1800b72a4  call    ?GetSLSUri@@YAJW4SLSIndex@@PEBUANNOTATION_VALUE@@_KPEBGPEAVTraceLoggingCorrelationVector@@PEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z; GetSLSUri(SLSIndex,ANNOTATION_VALUE const *,unsigned __int64,ushort const *,TraceLoggingCorrelationVector *,Windows::Foundation::IUriRuntimeClass * *)
0x1800b72a9  mov     ebx, eax
0x1800b72ab  test    eax, eax
0x1800b72ad  js      loc_1800B733F
0x1800b72b3  mov     [rbp+57h+var_B0], r14
0x1800b72b7  xor     ecx, ecx; string
0x1800b72b9  call    cs:__imp_WindowsDeleteString
0x1800b72bf  mov     [rbp+57h+var_B0], r14
0x1800b72c3  lea     rax, [rbp+57h+var_B0]
0x1800b72c7  mov     [rsp+100h+var_C0], rax
0x1800b72cc  mov     [rsp+100h+var_C8], r14
0x1800b72d1  lea     rax, aOemdiscovery; "OemDiscovery"
0x1800b72d8  mov     [rsp+100h+var_D0], rax
0x1800b72dd  mov     byte ptr [rsp+100h+var_D8], r14b
0x1800b72e2  mov     dword ptr [rsp+100h+var_E0], r14d
0x1800b72e7  xor     r9d, r9d
0x1800b72ea  xor     r8d, r8d
0x1800b72ed  mov     rdx, [rbp+57h+var_A8]
0x1800b72f1  mov     rcx, rdi
0x1800b72f4  call    ?FetchUriResponseWithAuthTicket@@YAJPEAVTraceLoggingCorrelationVector@@PEAUIUriRuntimeClass@Foundation@Windows@@PEAUHSTRING__@@PEAUIJsonObject@Json@Data@4@W4Http_Verb@@_NPEBG6PEAPEAU5@@Z; FetchUriResponseWithAuthTicket(TraceLoggingCorrelationVector *,Windows::Foundation::IUriRuntimeClass *,HSTRING__ *,Windows::Data::Json::IJsonObject *,Http_Verb,bool,ushort const *,ushort const *,HSTRING__ * *)
0x1800b72f9  mov     ebx, eax
0x1800b72fb  test    eax, eax
0x1800b72fd  js      short loc_1800B7334
0x1800b72ff  mov     [rbp+57h+arg_18], r14
0x1800b7303  lea     rcx, [rbp+57h+arg_18]
0x1800b7307  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800b730c  lea     rdx, [rbp+57h+arg_18]; struct Windows::Data::Json::IJsonObject **
0x1800b7310  mov     rcx, [rbp+57h+var_B0]; HSTRING
0x1800b7314  call    ?Json_Parse@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@Windows@@@Z; Json_Parse(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x1800b7319  mov     ebx, eax
0x1800b731b  test    eax, eax
0x1800b731d  js      short loc_1800B732A
0x1800b731f  mov     rax, [rbp+57h+arg_18]
0x1800b7323  mov     [rbp+57h+arg_18], r14
0x1800b7327  mov     [rsi], rax
0x1800b732a  lea     rcx, [rbp+57h+arg_18]
0x1800b732e  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800b7333  nop
0x1800b7334  mov     rcx, [rbp+57h+var_B0]; string
0x1800b7338  call    cs:__imp_WindowsDeleteString
0x1800b733e  nop
0x1800b733f  lea     rcx, [rbp+57h+var_A8]
0x1800b7343  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800b7348  nop
0x1800b7349  mov     rcx, [rbp+57h+var_90]; this
0x1800b734d  test    rcx, rcx
0x1800b7350  jz      short loc_1800B7358
0x1800b7352  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b7357  nop
0x1800b7358  mov     rcx, [rbp+57h+arg_0]; string
0x1800b735c  call    cs:__imp_WindowsDeleteString
0x1800b7362  mov     [rbp+57h+arg_0], r14
0x1800b7366  mov     rcx, [rbp+57h+arg_8]; string
0x1800b736a  call    cs:__imp_WindowsDeleteString
0x1800b7370  mov     [rbp+57h+arg_8], r14
0x1800b7374  mov     rcx, [rbp+57h+string]; string
0x1800b7378  call    cs:__imp_WindowsDeleteString
0x1800b737e  mov     [rbp+57h+string], r14
0x1800b7382  mov     rcx, [rbp+57h+newString]; string
0x1800b7386  call    cs:__imp_WindowsDeleteString
0x1800b738c  mov     eax, ebx
0x1800b738e  add     rsp, 0E0h
0x1800b7395  pop     r14
0x1800b7397  pop     rdi
0x1800b7398  pop     rsi
0x1800b7399  pop     rbx
0x1800b739a  pop     rbp
0x1800b739b  retn
```
