# SystemSettings::DataModel::Details::GetSettingImpl<26>(HSTRING__ *,SystemSettings::DataModel::SettingPluginRegistrationData const (&)[26],SystemSettings::DataModel::ISettingItem * *)

- ea: `0x180010ed8`
- end: `0x180011038`
- name: `??$GetSettingImpl@$0BK@@Details@DataModel@SystemSettings@@YAJPEAUHSTRING__@@AEAY0BK@$$CBUSettingPluginRegistrationData@12@PEAPEAUISettingItem@12@@Z`
- size: `352`
- prototype: `__int64 __fastcall(HSTRING string, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800145a0`

## callees

- `0x18000cfa4`
- `0x180010ed8`
- `0x1800135cc`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180010f02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180010f93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180010ff4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180010f02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180010f93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180010ff4`

## string_xrefs

- `0x180010fb2`: `OneCoreUap\Internal\Shell\inc\SettingsDBCommonThreshold.h`
- `0x180011018`: `OneCoreUap\Internal\Shell\inc\SettingsDBCommonThreshold.h`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::Details::GetSettingImpl<26>(HSTRING string, __int64 a2, _QWORD *a3)
{
  PCWSTR StringRawBuffer; // r10
  wchar_t **v6; // rdi
  wchar_t *v7; // r8
  _WORD *v8; // rcx
  wchar_t *v9; // rdx
  wchar_t *v10; // rdi
  __int64 (__fastcall *v11)(wchar_t *, __int64 *); // rbx
  int v12; // ebx
  const char *v13; // rax
  __int64 v14; // rax
  const char *v16; // rax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  UINT32 v18; // [rsp+58h] [rbp+10h] BYREF
  int v19; // [rsp+5Ch] [rbp+14h]
  __int64 v20; // [rsp+60h] [rbp+18h] BYREF

  v19 = HIDWORD(a2);
  *a3 = 0;
  v18 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, &v18);
  v6 = &off_180064350;
  while ( 1 )
  {
    v7 = v6[1];
    if ( (wchar_t *)v18 == v7 )
      break;
LABEL_6:
    v6 += 3;
    if ( v6 == (wchar_t **)&SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::s_SUPPORTED_RESOLUTIONS )
      goto LABEL_7;
  }
  v8 = &StringRawBuffer[v18];
  v9 = &(*v6)[(_QWORD)v7];
  while ( v8 != StringRawBuffer )
  {
    if ( *--v8 != *--v9 )
      goto LABEL_6;
  }
LABEL_7:
  if ( v6 == (wchar_t **)&SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::s_SUPPORTED_RESOLUTIONS )
  {
    v16 = (const char *)WindowsGetStringRawBuffer(string, 0);
    v12 = -2147024809;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xDC,
      (unsigned int)"OneCoreUap\\Internal\\Shell\\inc\\SettingsDBCommonThreshold.h",
      (const char *)0x80070057LL,
      (int)"%ls",
      v16);
  }
  else
  {
    v10 = v6[2];
    v20 = 0;
    v11 = *(__int64 (__fastcall **)(wchar_t *, __int64 *))(*((_QWORD *)v10 + 5) + 8LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    v12 = v11(v10, &v20);
    if ( v12 >= 0 )
    {
      v14 = v20;
      v20 = 0;
      *a3 = v14;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
      return 0;
    }
    v13 = (const char *)WindowsGetStringRawBuffer(string, 0);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xE1,
      (unsigned int)"OneCoreUap\\Internal\\Shell\\inc\\SettingsDBCommonThreshold.h",
      (const char *)(unsigned int)v12,
      (int)"%ls",
      v13);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180010ed8  mov     rax, rsp
0x180010edb  mov     [rax+8], rbx
0x180010edf  mov     [rax+10h], rdx
0x180010ee3  push    rbp
0x180010ee4  push    rsi
0x180010ee5  push    rdi
0x180010ee6  sub     rsp, 30h
0x180010eea  mov     rsi, r8
0x180010eed  mov     rbp, rcx
0x180010ef0  mov     qword ptr [r8], 0
0x180010ef7  mov     dword ptr [rax+10h], 0
0x180010efe  lea     rdx, [rax+10h]; length
0x180010f02  call    cs:__imp_WindowsGetStringRawBuffer
0x180010f08  mov     r10, rax
0x180010f0b  lea     rdi, off_180064350; "SystemSettings_BatterySaver_LandingPage"...
0x180010f12  mov     r9d, [rsp+48h+arg_8]
0x180010f17  lea     r11, ?s_SUPPORTED_RESOLUTIONS@CBatterySaverDynamicResolution@BatterySaverOneCoreDataModel@SystemSettings@@0QBUSUPPORTED_RESOLUTION@23@B; SystemSettings::BatterySaverOneCoreDataModel::SUPPORTED_RESOLUTION const near * const SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverDynamicResolution::s_SUPPORTED_RESOLUTIONS
0x180010f1e  mov     r8, [rdi+8]
0x180010f22  cmp     r9, r8
0x180010f25  jnz     short loc_180010F47
0x180010f27  lea     rcx, [r10+r9*2]
0x180010f2b  mov     rdx, [rdi]
0x180010f2e  lea     rdx, [rdx+r8*2]
0x180010f32  cmp     rcx, r10
0x180010f35  jz      short loc_180010F50
0x180010f37  add     rdx, 0FFFFFFFFFFFFFFFEh
0x180010f3b  add     rcx, 0FFFFFFFFFFFFFFFEh
0x180010f3f  movzx   eax, word ptr [rdx]
0x180010f42  cmp     [rcx], ax
0x180010f45  jz      short loc_180010F32
0x180010f47  add     rdi, 18h
0x180010f4b  cmp     rdi, r11
0x180010f4e  jnz     short loc_180010F1E
0x180010f50  cmp     rdi, r11
0x180010f53  jz      loc_180010FEF
0x180010f59  mov     rdi, [rdi+10h]
0x180010f5d  mov     [rsp+48h+arg_10], 0
0x180010f66  mov     rax, [rdi+28h]
0x180010f6a  mov     rbx, [rax+8]
0x180010f6e  lea     rcx, [rsp+48h+arg_10]
0x180010f73  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010f78  lea     rdx, [rsp+48h+arg_10]
0x180010f7d  mov     rcx, rdi
0x180010f80  mov     rax, rbx
0x180010f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f88  mov     ebx, eax
0x180010f8a  test    eax, eax
0x180010f8c  jns     short loc_180010FD0
0x180010f8e  xor     edx, edx; length
0x180010f90  mov     rcx, rbp; string
0x180010f93  call    cs:__imp_WindowsGetStringRawBuffer
0x180010f99  mov     rcx, [rsp+48h]; this
0x180010f9e  mov     [rsp+48h+var_20], rax; char *
0x180010fa3  lea     rdx, aLs; "%ls"
0x180010faa  mov     qword ptr [rsp+48h+var_28], rdx; int
0x180010faf  mov     r9d, ebx; char *
0x180010fb2  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\Shell\\inc\\Setti"...
0x180010fb9  mov     edx, 0E1h; void *
0x180010fbe  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180010fc3  nop
0x180010fc4  lea     rcx, [rsp+48h+arg_10]
0x180010fc9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010fce  jmp     short loc_180011029
0x180010fd0  mov     rax, [rsp+48h+arg_10]
0x180010fd5  mov     [rsp+48h+arg_10], 0
0x180010fde  mov     [rsi], rax
0x180010fe1  lea     rcx, [rsp+48h+arg_10]
0x180010fe6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010feb  xor     eax, eax
0x180010fed  jmp     short loc_18001102B
0x180010fef  xor     edx, edx; length
0x180010ff1  mov     rcx, rbp; string
0x180010ff4  call    cs:__imp_WindowsGetStringRawBuffer
0x180010ffa  mov     rcx, [rsp+48h]; this
0x180010fff  mov     [rsp+48h+var_20], rax; char *
0x180011004  lea     rdx, aLs; "%ls"
0x18001100b  mov     qword ptr [rsp+48h+var_28], rdx; int
0x180011010  mov     ebx, 80070057h
0x180011015  mov     r9d, ebx; char *
0x180011018  lea     r8, aOnecoreuapInte_0; "OneCoreUap\\Internal\\Shell\\inc\\Setti"...
0x18001101f  mov     edx, 0DCh; void *
0x180011024  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180011029  mov     eax, ebx
0x18001102b  mov     rbx, [rsp+48h+arg_0]
0x180011030  add     rsp, 30h
0x180011034  pop     rdi
0x180011035  pop     rsi
0x180011036  pop     rbp
0x180011037  retn
```
