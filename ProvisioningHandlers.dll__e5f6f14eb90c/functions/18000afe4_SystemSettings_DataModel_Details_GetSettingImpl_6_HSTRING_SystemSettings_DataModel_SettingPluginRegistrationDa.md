# SystemSettings::DataModel::Details::GetSettingImpl<6>(HSTRING__ *,SystemSettings::DataModel::SettingPluginRegistrationData const (&)[6],SystemSettings::DataModel::ISettingItem * *)

- ea: `0x18000afe4`
- end: `0x18000b0fa`
- name: `??$GetSettingImpl@$05@Details@DataModel@SystemSettings@@YAJPEAUHSTRING__@@AEAY05$$CBUSettingPluginRegistrationData@12@PEAPEAUISettingItem@12@@Z`
- size: `278`
- prototype: `__int64 __fastcall(HSTRING string)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000b390`

## callees

- `0x1800067fc`
- `0x18000afe4`
- `0x18000b1c0`
- `0x18000b2fc`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b01f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b095`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b01f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b095`

## string_xrefs

- `0x18000b044`: `onecoreuap\internal\shell\inc\SettingsDBCommonThreshold.h`
- `0x18000b0ba`: `onecoreuap\internal\shell\inc\SettingsDBCommonThreshold.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::Details::GetSettingImpl<6>(
        SystemSettings::DataModel::Details *string,
        HSTRING a2,
        HSTRING *a3)
{
  int PluginRegistrationData; // ebx
  const char *v6; // rax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  const char *StringRawBuffer; // rax
  HSTRING v10; // rax
  const struct SystemSettings::DataModel::SettingDBItem **v12; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HSTRING v14; // [rsp+58h] [rbp+10h] BYREF
  __int64 v15; // [rsp+60h] [rbp+18h] BYREF

  v14 = a2;
  *a3 = 0;
  v15 = 0;
  PluginRegistrationData = SystemSettings::DataModel::Details::FindPluginRegistrationData(
                             string,
                             a2,
                             (unsigned __int64)a3,
                             (const struct SystemSettings::DataModel::SettingPluginRegistrationData *)&v15,
                             v12);
  if ( PluginRegistrationData >= 0 )
  {
    v14 = 0;
    v7 = v15;
    v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)(v15 + 40) + 8LL);
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v14);
    PluginRegistrationData = v8(v7, &v14);
    if ( PluginRegistrationData >= 0 )
    {
      v10 = v14;
      v14 = 0;
      *a3 = v10;
      PluginRegistrationData = 0;
    }
    else
    {
      StringRawBuffer = (const char *)WindowsGetStringRawBuffer((HSTRING)string, 0);
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xE1,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingsDBCommonThreshold.h",
        (const char *)(unsigned int)PluginRegistrationData,
        (int)"%ls",
        StringRawBuffer);
    }
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v14);
  }
  else
  {
    v6 = (const char *)WindowsGetStringRawBuffer((HSTRING)string, 0);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingsDBCommonThreshold.h",
      (const char *)(unsigned int)PluginRegistrationData,
      (int)"%ls",
      v6);
  }
  return (unsigned int)PluginRegistrationData;
}

```

## disassembly

```asm
0x18000afe4  mov     rax, rsp
0x18000afe7  mov     [rax+8], rbx
0x18000afeb  mov     [rax+10h], rdx
0x18000afef  push    rbp
0x18000aff0  push    rsi
0x18000aff1  push    rdi
0x18000aff2  sub     rsp, 30h
0x18000aff6  mov     rsi, r8
0x18000aff9  mov     rbp, rcx
0x18000affc  mov     qword ptr [r8], 0
0x18000b003  mov     qword ptr [rax+18h], 0
0x18000b00b  lea     r9, [rax+18h]; struct SystemSettings::DataModel::SettingPluginRegistrationData *
0x18000b00f  call    ?FindPluginRegistrationData@Details@DataModel@SystemSettings@@YAJPEAUHSTRING__@@_KPEBUSettingPluginRegistrationData@23@PEAPEBUSettingDBItem@23@@Z; SystemSettings::DataModel::Details::FindPluginRegistrationData(HSTRING__ *,unsigned __int64,SystemSettings::DataModel::SettingPluginRegistrationData const *,SystemSettings::DataModel::SettingDBItem const * *)
0x18000b014  mov     ebx, eax
0x18000b016  test    eax, eax
0x18000b018  jns     short loc_18000B05A
0x18000b01a  xor     edx, edx; length
0x18000b01c  mov     rcx, rbp; string
0x18000b01f  call    cs:__imp_WindowsGetStringRawBuffer
0x18000b026  nop     dword ptr [rax+rax+00h]
0x18000b02b  mov     rcx, [rsp+48h]; this
0x18000b030  mov     [rsp+48h+var_20], rax; char *
0x18000b035  lea     rax, aLs; "%ls"
0x18000b03c  mov     qword ptr [rsp+48h+var_28], rax; int
0x18000b041  mov     r9d, ebx; char *
0x18000b044  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18000b04b  mov     edx, 0DCh; void *
0x18000b050  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000b055  jmp     loc_18000B0EA
0x18000b05a  mov     [rsp+48h+arg_8], 0
0x18000b063  mov     rdi, [rsp+48h+arg_10]
0x18000b068  mov     rax, [rdi+28h]
0x18000b06c  mov     rbx, [rax+8]
0x18000b070  lea     rcx, [rsp+48h+arg_8]
0x18000b075  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x18000b07a  lea     rdx, [rsp+48h+arg_8]
0x18000b07f  mov     rcx, rdi
0x18000b082  mov     rax, rbx
0x18000b085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b08a  mov     ebx, eax
0x18000b08c  test    eax, eax
0x18000b08e  jns     short loc_18000B0CD
0x18000b090  xor     edx, edx; length
0x18000b092  mov     rcx, rbp; string
0x18000b095  call    cs:__imp_WindowsGetStringRawBuffer
0x18000b09c  nop     dword ptr [rax+rax+00h]
0x18000b0a1  mov     rcx, [rsp+48h]; this
0x18000b0a6  mov     [rsp+48h+var_20], rax; char *
0x18000b0ab  lea     rax, aLs; "%ls"
0x18000b0b2  mov     qword ptr [rsp+48h+var_28], rax; int
0x18000b0b7  mov     r9d, ebx; char *
0x18000b0ba  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18000b0c1  mov     edx, 0E1h; void *
0x18000b0c6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000b0cb  jmp     short loc_18000B0E0
0x18000b0cd  mov     rax, [rsp+48h+arg_8]
0x18000b0d2  mov     [rsp+48h+arg_8], 0
0x18000b0db  mov     [rsi], rax
0x18000b0de  xor     ebx, ebx
0x18000b0e0  lea     rcx, [rsp+48h+arg_8]
0x18000b0e5  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x18000b0ea  mov     eax, ebx
0x18000b0ec  mov     rbx, [rsp+48h+arg_0]
0x18000b0f1  add     rsp, 30h
0x18000b0f5  pop     rdi
0x18000b0f6  pop     rsi
0x18000b0f7  pop     rbp
0x18000b0f8  retn
```
