# SystemSettings::BatteryUsageHandlers::VideoQualityControl::GetValue(IInspectable * *)

- ea: `0x180036e10`
- end: `0x180036f82`
- name: `?GetValue@VideoQualityControl@BatteryUsageHandlers@SystemSettings@@MEAAJPEAPEAUIInspectable@@@Z`
- size: `370`
- prototype: `__int64 __fastcall(SystemSettings::BatteryUsageHandlers::VideoQualityControl *__hidden this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180004cfc`
- `0x18000a13c`
- `0x180017834`
- `0x1800228bc`
- `0x180036e10`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036f46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036f68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036f46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036f68`
- `POWRPROF!PowerGetActiveScheme` at `0x180036e55`
- `POWRPROF!PowerGetActiveScheme` at `0x180036e55`
- `POWRPROF!PowerReadDCValue` at `0x180036ea9`
- `POWRPROF!PowerReadDCValue` at `0x180036ea9`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatteryUsageHandlers::VideoQualityControl::GetValue(
        SystemSettings::BatteryUsageHandlers::VideoQualityControl *this,
        struct IInspectable **a2)
{
  signed int ActiveScheme; // ebx
  GUID *v4; // rcx
  bool v5; // zf
  int v6; // eax
  bool v7; // bl
  const unsigned __int16 *v8; // rcx
  int v9; // eax
  GUID *v10; // rcx
  int Type; // [rsp+20h] [rbp-50h]
  GUID *SchemeGuid; // [rsp+40h] [rbp-30h] BYREF
  struct IInspectable *v14; // [rsp+48h] [rbp-28h] BYREF
  GUID **p_SchemeGuid; // [rsp+50h] [rbp-20h] BYREF
  GUID *ActivePolicyGuid; // [rsp+58h] [rbp-18h] BYREF
  char v17; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  int Buffer; // [rsp+90h] [rbp+20h] BYREF
  DWORD BufferSize; // [rsp+98h] [rbp+28h] BYREF

  SchemeGuid = 0;
  Buffer = 0;
  p_SchemeGuid = &SchemeGuid;
  BufferSize = 4;
  ActivePolicyGuid = 0;
  v17 = 1;
  ActiveScheme = PowerGetActiveScheme(0, &ActivePolicyGuid);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_SchemeGuid);
  v4 = SchemeGuid;
  if ( ActiveScheme )
  {
    if ( ActiveScheme > 0 )
      ActiveScheme = (unsigned __int16)ActiveScheme | 0x80070000;
    goto LABEL_15;
  }
  v5 = SchemeGuid == 0;
  if ( !SchemeGuid )
  {
LABEL_16:
    SchemeGuid = 0;
    if ( !v5 )
      LocalFree(v4);
    return (unsigned int)ActiveScheme;
  }
  if ( PowerReadDCValue(
         0,
         SchemeGuid,
         &GUID_MULTIMEDIA_SUBGROUP,
         &GUID_VIDEO_PLAYBACK_QUALITY_BIAS,
         0,
         (PUCHAR)&Buffer,
         &BufferSize) )
  {
    v6 = 0;
    Buffer = 0;
  }
  else
  {
    v6 = Buffer;
  }
  v14 = 0;
  v7 = v6 == 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  v8 = L"SystemSettings_BatterySaver_VideoQuality_Battery";
  if ( !v7 )
    v8 = L"SystemSettings_BatterySaver_VideoQuality_Video";
  v9 = SystemSettings::DataModel::PropValueHelper::CreateString(v8, &v14);
  ActiveScheme = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\videoqualitycontrol.cpp",
      (const char *)(unsigned int)v9,
      Type);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    v4 = SchemeGuid;
LABEL_15:
    v5 = v4 == 0;
    goto LABEL_16;
  }
  *a2 = v14;
  v14 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  v10 = SchemeGuid;
  SchemeGuid = 0;
  if ( v10 )
    LocalFree(v10);
  return 0;
}

```

## disassembly

```asm
0x180036e10  mov     [rsp-8+arg_0], rbx
0x180036e15  mov     [rsp-8+arg_8], rdi
0x180036e1a  push    rbp
0x180036e1b  mov     rbp, rsp
0x180036e1e  sub     rsp, 70h
0x180036e22  mov     rdi, rdx
0x180036e25  mov     [rbp+SchemeGuid], 0
0x180036e2d  lea     rax, [rbp+SchemeGuid]
0x180036e31  mov     [rbp+arg_10], 0
0x180036e38  lea     rdx, [rbp+ActivePolicyGuid]; ActivePolicyGuid
0x180036e3c  mov     [rbp+var_20], rax
0x180036e40  xor     ecx, ecx; UserRootPowerKey
0x180036e42  mov     [rbp+arg_18], 4
0x180036e49  mov     [rbp+ActivePolicyGuid], 0
0x180036e51  mov     [rbp+var_10], 1
0x180036e55  call    cs:__imp_PowerGetActiveScheme
0x180036e5b  lea     rcx, [rbp+var_20]
0x180036e5f  mov     ebx, eax
0x180036e61  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180036e66  mov     rcx, [rbp+SchemeGuid]; hMem
0x180036e6a  test    ebx, ebx
0x180036e6c  jnz     loc_180036F50
0x180036e72  test    rcx, rcx
0x180036e75  jz      loc_180036F5E
0x180036e7b  lea     rax, [rbp+arg_18]
0x180036e7f  mov     rdx, rcx; SchemeGuid
0x180036e82  mov     [rsp+70h+BufferSize], rax; BufferSize
0x180036e87  lea     r9, GUID_VIDEO_PLAYBACK_QUALITY_BIAS; PowerSettingGuid
0x180036e8e  lea     rax, [rbp+arg_10]
0x180036e92  xor     ecx, ecx; RootPowerKey
0x180036e94  mov     [rsp+70h+Buffer], rax; Buffer
0x180036e99  lea     r8, GUID_MULTIMEDIA_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180036ea0  mov     [rsp+70h+Type], 0; int
0x180036ea9  call    cs:__imp_PowerReadDCValue
0x180036eaf  test    eax, eax
0x180036eb1  jz      short loc_180036EBA
0x180036eb3  xor     eax, eax
0x180036eb5  mov     [rbp+arg_10], eax
0x180036eb8  jmp     short loc_180036EBD
0x180036eba  mov     eax, [rbp+arg_10]
0x180036ebd  test    eax, eax
0x180036ebf  mov     [rbp+var_28], 0
0x180036ec7  lea     rcx, [rbp+var_28]
0x180036ecb  setz    bl
0x180036ece  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180036ed3  lea     rax, aSystemsettings_19; "SystemSettings_BatterySaver_VideoQualit"...
0x180036eda  test    bl, bl
0x180036edc  lea     rcx, aSystemsettings_3; "SystemSettings_BatterySaver_VideoQualit"...
0x180036ee3  cmovz   rcx, rax; unsigned __int16 *
0x180036ee7  lea     rdx, [rbp+var_28]; struct IInspectable **
0x180036eeb  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180036ef0  mov     ebx, eax
0x180036ef2  test    eax, eax
0x180036ef4  jns     short loc_180036F1D
0x180036ef6  mov     rcx, [rbp+8]; this
0x180036efa  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\coresettinghandlers"...
0x180036f01  mov     r9d, eax; char *
0x180036f04  mov     edx, 60h ; '`'; void *
0x180036f09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036f0e  lea     rcx, [rbp+var_28]
0x180036f12  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180036f17  mov     rcx, [rbp+SchemeGuid]
0x180036f1b  jmp     short loc_180036F5B
0x180036f1d  mov     rax, [rbp+var_28]
0x180036f21  lea     rcx, [rbp+var_28]
0x180036f25  mov     [rdi], rax
0x180036f28  mov     [rbp+var_28], 0
0x180036f30  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180036f35  mov     rcx, [rbp+SchemeGuid]; hMem
0x180036f39  mov     [rbp+SchemeGuid], 0
0x180036f41  test    rcx, rcx
0x180036f44  jz      short loc_180036F4C
0x180036f46  call    cs:__imp_LocalFree
0x180036f4c  xor     eax, eax
0x180036f4e  jmp     short loc_180036F70
0x180036f50  jle     short loc_180036F5B
0x180036f52  movzx   ebx, bx
0x180036f55  or      ebx, 80070000h
0x180036f5b  test    rcx, rcx
0x180036f5e  mov     [rbp+SchemeGuid], 0
0x180036f66  jz      short loc_180036F6E
0x180036f68  call    cs:__imp_LocalFree
0x180036f6e  mov     eax, ebx
0x180036f70  lea     r11, [rsp+70h+var_s0]
0x180036f75  mov     rbx, [r11+10h]
0x180036f79  mov     rdi, [r11+18h]
0x180036f7d  mov     rsp, r11
0x180036f80  pop     rbp
0x180036f81  retn
```
