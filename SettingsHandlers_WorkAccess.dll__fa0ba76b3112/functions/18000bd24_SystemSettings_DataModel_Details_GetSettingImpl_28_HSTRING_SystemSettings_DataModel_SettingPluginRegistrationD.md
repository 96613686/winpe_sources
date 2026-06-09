# SystemSettings::DataModel::Details::GetSettingImpl<28>(HSTRING__ *,SystemSettings::DataModel::SettingPluginRegistrationData const (&)[28],SystemSettings::DataModel::ISettingItem * *)

- ea: `0x18000bd24`
- end: `0x18000be3a`
- name: `??$GetSettingImpl@$0BM@@Details@DataModel@SystemSettings@@YAJPEAUHSTRING__@@AEAY0BM@$$CBUSettingPluginRegistrationData@12@PEAPEAUISettingItem@12@@Z`
- size: `278`
- prototype: `__int64 __fastcall(HSTRING string)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c8f0`

## callees

- `0x1800076ac`
- `0x18000bd24`
- `0x18000c12c`
- `0x18000c518`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bd5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bdd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bd5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bdd5`

## string_xrefs

- `0x18000bd84`: `onecoreuap\internal\shell\inc\SettingsDBCommonThreshold.h`
- `0x18000bdfa`: `onecoreuap\internal\shell\inc\SettingsDBCommonThreshold.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::Details::GetSettingImpl<28>(
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
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
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
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
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
0x18000bd24  mov     rax, rsp
0x18000bd27  mov     [rax+8], rbx
0x18000bd2b  mov     [rax+10h], rdx
0x18000bd2f  push    rbp
0x18000bd30  push    rsi
0x18000bd31  push    rdi
0x18000bd32  sub     rsp, 30h
0x18000bd36  mov     rsi, r8
0x18000bd39  mov     rbp, rcx
0x18000bd3c  mov     qword ptr [r8], 0
0x18000bd43  mov     qword ptr [rax+18h], 0
0x18000bd4b  lea     r9, [rax+18h]; struct SystemSettings::DataModel::SettingPluginRegistrationData *
0x18000bd4f  call    ?FindPluginRegistrationData@Details@DataModel@SystemSettings@@YAJPEAUHSTRING__@@_KPEBUSettingPluginRegistrationData@23@PEAPEBUSettingDBItem@23@@Z; SystemSettings::DataModel::Details::FindPluginRegistrationData(HSTRING__ *,unsigned __int64,SystemSettings::DataModel::SettingPluginRegistrationData const *,SystemSettings::DataModel::SettingDBItem const * *)
0x18000bd54  mov     ebx, eax
0x18000bd56  test    eax, eax
0x18000bd58  jns     short loc_18000BD9A
0x18000bd5a  xor     edx, edx; length
0x18000bd5c  mov     rcx, rbp; string
0x18000bd5f  call    cs:__imp_WindowsGetStringRawBuffer
0x18000bd66  nop     dword ptr [rax+rax+00h]
0x18000bd6b  mov     rcx, [rsp+48h]; this
0x18000bd70  mov     [rsp+48h+var_20], rax; char *
0x18000bd75  lea     rax, aLs; "%ls"
0x18000bd7c  mov     qword ptr [rsp+48h+var_28], rax; int
0x18000bd81  mov     r9d, ebx; char *
0x18000bd84  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18000bd8b  mov     edx, 0DCh; void *
0x18000bd90  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000bd95  jmp     loc_18000BE2A
0x18000bd9a  mov     [rsp+48h+arg_8], 0
0x18000bda3  mov     rdi, [rsp+48h+arg_10]
0x18000bda8  mov     rax, [rdi+28h]
0x18000bdac  mov     rbx, [rax+8]
0x18000bdb0  lea     rcx, [rsp+48h+arg_8]
0x18000bdb5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000bdba  lea     rdx, [rsp+48h+arg_8]
0x18000bdbf  mov     rcx, rdi
0x18000bdc2  mov     rax, rbx
0x18000bdc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdca  mov     ebx, eax
0x18000bdcc  test    eax, eax
0x18000bdce  jns     short loc_18000BE0D
0x18000bdd0  xor     edx, edx; length
0x18000bdd2  mov     rcx, rbp; string
0x18000bdd5  call    cs:__imp_WindowsGetStringRawBuffer
0x18000bddc  nop     dword ptr [rax+rax+00h]
0x18000bde1  mov     rcx, [rsp+48h]; this
0x18000bde6  mov     [rsp+48h+var_20], rax; char *
0x18000bdeb  lea     rax, aLs; "%ls"
0x18000bdf2  mov     qword ptr [rsp+48h+var_28], rax; int
0x18000bdf7  mov     r9d, ebx; char *
0x18000bdfa  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18000be01  mov     edx, 0E1h; void *
0x18000be06  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000be0b  jmp     short loc_18000BE20
0x18000be0d  mov     rax, [rsp+48h+arg_8]
0x18000be12  mov     [rsp+48h+arg_8], 0
0x18000be1b  mov     [rsi], rax
0x18000be1e  xor     ebx, ebx
0x18000be20  lea     rcx, [rsp+48h+arg_8]
0x18000be25  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000be2a  mov     eax, ebx
0x18000be2c  mov     rbx, [rsp+48h+arg_0]
0x18000be31  add     rsp, 30h
0x18000be35  pop     rdi
0x18000be36  pop     rsi
0x18000be37  pop     rbp
0x18000be38  retn
```
