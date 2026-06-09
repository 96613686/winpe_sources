# AppV::Client::Service::AppVClientImpl::RemovePackage(wchar_t *,wchar_t *,short,unsigned __int64 *)

- ea: `0x140035c00`
- end: `0x140035e91`
- name: `?RemovePackage@AppVClientImpl@Service@Client@AppV@@UEAAJPEA_W0FPEA_K@Z`
- size: `657`
- prototype: `__int64 __fastcall(AppV::Client::Service::AppVClientImpl *this, wchar_t *, wchar_t *, __int16, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x140008224`
- `0x1400083b4`
- `0x1400090cc`
- `0x1400206f8`
- `0x1400233dc`
- `0x140026dd0`
- `0x140028e00`
- `0x14002a8a8`
- `0x140035c00`
- `0x1400360a0`
- `0x14003a198`
- `0x14003a24c`
- `0x14003a4dc`
- `0x14003b28c`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x140035cee`
- `ADVAPI32!EventActivityIdControl` at `0x140035e22`
- `ADVAPI32!EventActivityIdControl` at `0x140035e60`
- `ADVAPI32!EventActivityIdControl` at `0x140035cee`
- `ADVAPI32!EventActivityIdControl` at `0x140035e22`
- `ADVAPI32!EventActivityIdControl` at `0x140035e60`
- `OLEAUT32!__imp_SysStringLen` at `0x140035c53`
- `OLEAUT32!__imp_SysStringLen` at `0x140035c6d`
- `OLEAUT32!__imp_SysStringLen` at `0x140035c53`
- `OLEAUT32!__imp_SysStringLen` at `0x140035c6d`

## string_xrefs

- `0x140035c8a`: `RemovePackage`
- `0x140035e2c`: `RemovePackage`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppV::Client::Service::AppVClientImpl::RemovePackage(
        AppV::Client::Service::AppVClientImpl *this,
        wchar_t *a2,
        wchar_t *a3,
        __int16 a4,
        unsigned __int64 *a5)
{
  int v8; // eax
  unsigned int v9; // edi
  _QWORD *v11; // rax
  unsigned __int64 PackageIDAndPackageVersionID; // rax
  int v13; // eax
  unsigned int v14; // ebx
  _BYTE v15[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v16; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h]
  _BYTE v18[16]; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+60h] [rbp-A0h]
  _BYTE v20[4]; // [rsp+68h] [rbp-98h] BYREF
  GUID ActivityId; // [rsp+6Ch] [rbp-94h] BYREF
  _QWORD v22[3]; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID v23; // [rsp+A8h] [rbp-58h] BYREF
  struct _GUID v24; // [rsp+B8h] [rbp-48h] BYREF
  bool v25; // [rsp+C8h] [rbp-38h]
  __int128 v26; // [rsp+D0h] [rbp-30h]
  __int128 v27; // [rsp+E0h] [rbp-20h]
  __int128 v28; // [rsp+F0h] [rbp-10h]
  _QWORD v29[2]; // [rsp+100h] [rbp+0h] BYREF
  int v30; // [rsp+110h] [rbp+10h]
  bool v31; // [rsp+180h] [rbp+80h]

  AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>(v20);
  if ( !a2 || !SysStringLen(a2) || !a3 || !SysStringLen(a3) || !a5 )
  {
    AppV::Client::Service::SmartComMethodLogger::SmartComMethodLogger(
      (AppV::Client::Service::SmartComMethodLogger *)v18,
      L"RemovePackage");
    v19 = -2147024809;
    AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger((AppV::Client::Service::SmartComMethodLogger *)v18);
    goto LABEL_16;
  }
  AppV::Client::Service::SmartTelemetryPackageLogger::SmartTelemetryPackageLogger(
    (AppV::Client::Service::SmartTelemetryPackageLogger *)v29,
    L"RemovePackage",
    a2,
    a3);
  v29[0] = &AppV::Client::Service::SmartTelemetryRemovePackageLogger::`vftable';
  v31 = 0;
  v15[0] = 0;
  v8 = AppV::Client::Service::AppVClientImpl::APICaller::Initialize(
         (AppV::Client::Service::AppVClientImpl::APICaller *)v15,
         1,
         a5);
  v9 = v8;
  if ( v8 < 0 )
  {
    v30 = v8;
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v15);
    AppV::Client::Service::SmartTelemetryRemovePackageLogger::~SmartTelemetryRemovePackageLogger((AppV::Client::Service::SmartTelemetryRemovePackageLogger *)v29);
    if ( v20[0] )
      EventActivityIdControl(2u, &ActivityId);
    return v9;
  }
  AppV::Client::ActivityData::ActivityData((AppV::Client::ActivityData *)v22);
  v22[0] = &AppV::Client::RemovePackageData::`vftable';
  v23 = GUID_NULL;
  v24 = GUID_NULL;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v11 = operator new(0x78u);
  *v11 = v11;
  v11[1] = v11;
  *(_QWORD *)&v28 = v11;
  PackageIDAndPackageVersionID = AppV::Client::Service::AppVClientImpl::GetPackageIDAndPackageVersionID(
                                   a2,
                                   a3,
                                   &v23,
                                   &v24);
  v25 = a4 == -1;
  v31 = v25;
  if ( (PackageIDAndPackageVersionID & 0x8000000000LL) == 0 )
  {
    *a5 = PackageIDAndPackageVersionID;
    v30 = -2147024809;
    AppV::Client::RemovePackageData::~RemovePackageData((AppV::Client::RemovePackageData *)v22);
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v15);
    AppV::Client::Service::SmartTelemetryRemovePackageLogger::~SmartTelemetryRemovePackageLogger((AppV::Client::Service::SmartTelemetryRemovePackageLogger *)v29);
LABEL_16:
    if ( v20[0] )
      EventActivityIdControl(2u, &ActivityId);
    return 2147942487LL;
  }
  v16 = 0;
  v17 = 0;
  v13 = AppV::Client::Service::AppVClientImpl::RequestActivity(6, v22, &v16);
  v14 = AppV::Client::Service::AppVClientImpl::ProcessFullDeliveryErrors(
          (unsigned int)v29,
          v13,
          (unsigned int)&v16,
          (_DWORD)a5,
          (__int64)v29);
  v30 = v14;
  std::vector<std::pair<enum AppV::Client::ComponentType,unsigned __int64>>::~vector<std::pair<enum AppV::Client::ComponentType,unsigned __int64>>(&v16);
  AppV::Client::RemovePackageData::~RemovePackageData((AppV::Client::RemovePackageData *)v22);
  AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v15);
  AppV::Client::Service::SmartTelemetryRemovePackageLogger::~SmartTelemetryRemovePackageLogger((AppV::Client::Service::SmartTelemetryRemovePackageLogger *)v29);
  if ( v20[0] )
    EventActivityIdControl(2u, &ActivityId);
  return v14;
}

```

## disassembly

```asm
0x140035c00  mov     [rsp-8+arg_0], rbx
0x140035c05  push    rbp
0x140035c06  push    rsi
0x140035c07  push    rdi
0x140035c08  push    r14
0x140035c0a  push    r15
0x140035c0c  lea     rbp, [rsp-0A0h]
0x140035c14  sub     rsp, 1A0h
0x140035c1b  mov     rax, cs:__security_cookie
0x140035c22  xor     rax, rsp
0x140035c25  mov     [rbp+0C0h+var_30], rax
0x140035c2c  movzx   r15d, r9w
0x140035c30  mov     rsi, r8
0x140035c33  mov     r14, rdx
0x140035c36  mov     rbx, [rbp+0C0h+arg_20]
0x140035c3d  lea     rcx, [rsp+1C0h+var_158]
0x140035c42  call    ??0?$ScopedActivity@VUserModeActivityIdControl@ETW@AppV@@@ETW@AppV@@QEAA@XZ; AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>(void)
0x140035c47  test    r14, r14
0x140035c4a  jz      loc_140035E2C
0x140035c50  mov     rcx, r14; pbstr
0x140035c53  call    cs:__imp_SysStringLen
0x140035c59  test    eax, eax
0x140035c5b  jz      loc_140035E2C
0x140035c61  test    rsi, rsi
0x140035c64  jz      loc_140035E2C
0x140035c6a  mov     rcx, rsi; pbstr
0x140035c6d  call    cs:__imp_SysStringLen
0x140035c73  test    eax, eax
0x140035c75  jz      loc_140035E2C
0x140035c7b  test    rbx, rbx
0x140035c7e  jz      loc_140035E2C
0x140035c84  mov     r9, rsi; wchar_t *
0x140035c87  mov     r8, r14; wchar_t *
0x140035c8a  lea     rdx, aRemovepackage; "RemovePackage"
0x140035c91  lea     rcx, [rbp+0C0h+var_C0]; this
0x140035c95  call    ??0SmartTelemetryPackageLogger@Service@Client@AppV@@QEAA@PEB_WPEA_W1@Z; AppV::Client::Service::SmartTelemetryPackageLogger::SmartTelemetryPackageLogger(wchar_t const *,wchar_t *,wchar_t *)
0x140035c9a  lea     rax, ??_7SmartTelemetryRemovePackageLogger@Service@Client@AppV@@6B@; const AppV::Client::Service::SmartTelemetryRemovePackageLogger::`vftable'
0x140035ca1  mov     [rbp+0C0h+var_C0], rax
0x140035ca5  mov     [rbp+0C0h+var_40], 0
0x140035cac  mov     [rsp+1C0h+var_190], 0
0x140035cb1  mov     r8, rbx; unsigned __int64 *
0x140035cb4  mov     dl, 1; bool
0x140035cb6  lea     rcx, [rsp+1C0h+var_190]; this
0x140035cbb  call    ?Initialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJ_NAEA_K@Z; AppV::Client::Service::AppVClientImpl::APICaller::Initialize(bool,unsigned __int64 &)
0x140035cc0  mov     edi, eax
0x140035cc2  test    eax, eax
0x140035cc4  jns     short loc_140035CFB
0x140035cc6  mov     [rbp+0C0h+var_B0], eax
0x140035cc9  lea     rcx, [rsp+1C0h+var_190]; this
0x140035cce  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140035cd3  nop
0x140035cd4  lea     rcx, [rbp+0C0h+var_C0]; this
0x140035cd8  call    ??1SmartTelemetryRemovePackageLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartTelemetryRemovePackageLogger::~SmartTelemetryRemovePackageLogger(void)
0x140035cdd  cmp     [rsp+1C0h+var_158], 0
0x140035ce2  jz      short loc_140035CF4
0x140035ce4  lea     rdx, [rsp+1C0h+ActivityId]; ActivityId
0x140035ce9  mov     ecx, 2; ControlCode
0x140035cee  call    cs:__imp_EventActivityIdControl
0x140035cf4  mov     eax, edi
0x140035cf6  jmp     loc_140035E6B
0x140035cfb  lea     rcx, [rbp+0C0h+var_130]; this
0x140035cff  call    ??0ActivityData@Client@AppV@@QEAA@XZ; AppV::Client::ActivityData::ActivityData(void)
0x140035d04  lea     rax, ??_7RemovePackageData@Client@AppV@@6B@; const AppV::Client::RemovePackageData::`vftable'
0x140035d0b  mov     [rbp+0C0h+var_130], rax
0x140035d0f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140035d16  movdqu  xmmword ptr [rbp+0C0h+var_118.Data1], xmm0
0x140035d1b  movdqu  xmmword ptr [rbp+0C0h+var_108.Data1], xmm0
0x140035d20  mov     [rbp+0C0h+var_F8], 0
0x140035d24  xorps   xmm0, xmm0
0x140035d27  movdqa  [rbp+0C0h+var_F0], xmm0
0x140035d2c  xorps   xmm1, xmm1
0x140035d2f  movdqa  [rbp+0C0h+var_E0], xmm1
0x140035d34  movdqa  [rbp+0C0h+var_D0], xmm0
0x140035d39  mov     ecx, 78h ; 'x'; Size
0x140035d3e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140035d43  mov     [rax], rax
0x140035d46  mov     [rax+8], rax
0x140035d4a  mov     qword ptr [rbp+0C0h+var_D0], rax
0x140035d4e  lea     r9, [rbp+0C0h+var_108]; struct _GUID *
0x140035d52  lea     r8, [rbp+0C0h+var_118]; struct _GUID *
0x140035d56  mov     rdx, rsi; wchar_t *
0x140035d59  mov     rcx, r14; wchar_t *
0x140035d5c  call    ?GetPackageIDAndPackageVersionID@AppVClientImpl@Service@Client@AppV@@CA_KQEA_W0AEAU_GUID@@1@Z; AppV::Client::Service::AppVClientImpl::GetPackageIDAndPackageVersionID(wchar_t * const,wchar_t * const,_GUID &,_GUID &)
0x140035d61  cmp     r15w, 0FFFFh
0x140035d66  setz    cl
0x140035d69  mov     [rbp+0C0h+var_F8], cl
0x140035d6c  mov     [rbp+0C0h+var_40], cl
0x140035d72  bt      rax, 27h ; '''
0x140035d77  jb      short loc_140035DA6
0x140035d79  mov     [rbx], rax
0x140035d7c  mov     [rbp+0C0h+var_B0], 80070057h
0x140035d83  lea     rcx, [rbp+0C0h+var_130]; this
0x140035d87  call    ??1RemovePackageData@Client@AppV@@UEAA@XZ; AppV::Client::RemovePackageData::~RemovePackageData(void)
0x140035d8c  nop
0x140035d8d  lea     rcx, [rsp+1C0h+var_190]; this
0x140035d92  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140035d97  nop
0x140035d98  lea     rcx, [rbp+0C0h+var_C0]; this
0x140035d9c  call    ??1SmartTelemetryRemovePackageLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartTelemetryRemovePackageLogger::~SmartTelemetryRemovePackageLogger(void)
0x140035da1  jmp     loc_140035E4F
0x140035da6  xorps   xmm0, xmm0
0x140035da9  movdqu  [rsp+1C0h+var_188], xmm0
0x140035daf  mov     [rsp+1C0h+var_178], 0
0x140035db8  lea     r8, [rsp+1C0h+var_188]
0x140035dbd  lea     rdx, [rbp+0C0h+var_130]
0x140035dc1  mov     ecx, 6
0x140035dc6  call    ?RequestActivity@AppVClientImpl@Service@Client@AppV@@CA_KW4ActivityType@34@AEAVActivityData@34@AEAV?$vector@U?$pair@W4ComponentType@Client@AppV@@_K@std@@V?$allocator@U?$pair@W4ComponentType@Client@AppV@@_K@std@@@2@@std@@@Z; AppV::Client::Service::AppVClientImpl::RequestActivity(AppV::Client::ActivityType,AppV::Client::ActivityData &,std::vector<std::pair<AppV::Client::ComponentType,unsigned __int64>> &)
0x140035dcb  lea     rcx, [rbp+0C0h+var_C0]
0x140035dcf  mov     [rsp+1C0h+var_1A0], rcx
0x140035dd4  mov     r9, rbx
0x140035dd7  lea     r8, [rsp+1C0h+var_188]
0x140035ddc  mov     rdx, rax
0x140035ddf  call    ?ProcessFullDeliveryErrors@AppVClientImpl@Service@Client@AppV@@AEAAJ_KAEBV?$vector@U?$pair@W4ComponentType@Client@AppV@@_K@std@@V?$allocator@U?$pair@W4ComponentType@Client@AppV@@_K@std@@@2@@std@@AEA_KPEAVSmartTelemetryActivityLogger@234@@Z; AppV::Client::Service::AppVClientImpl::ProcessFullDeliveryErrors(unsigned __int64,std::vector<std::pair<AppV::Client::ComponentType,unsigned __int64>> const &,unsigned __int64 &,AppV::Client::Service::SmartTelemetryActivityLogger *)
0x140035de4  mov     ebx, eax
0x140035de6  mov     [rbp+0C0h+var_B0], eax
0x140035de9  lea     rcx, [rsp+1C0h+var_188]
0x140035dee  call    ??1?$vector@U?$pair@W4ComponentType@Client@AppV@@_K@std@@V?$allocator@U?$pair@W4ComponentType@Client@AppV@@_K@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<AppV::Client::ComponentType,unsigned __int64>>::~vector<std::pair<AppV::Client::ComponentType,unsigned __int64>>(void)
0x140035df3  lea     rcx, [rbp+0C0h+var_130]; this
0x140035df7  call    ??1RemovePackageData@Client@AppV@@UEAA@XZ; AppV::Client::RemovePackageData::~RemovePackageData(void)
0x140035dfc  nop
0x140035dfd  lea     rcx, [rsp+1C0h+var_190]; this
0x140035e02  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140035e07  nop
0x140035e08  lea     rcx, [rbp+0C0h+var_C0]; this
0x140035e0c  call    ??1SmartTelemetryRemovePackageLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartTelemetryRemovePackageLogger::~SmartTelemetryRemovePackageLogger(void)
0x140035e11  cmp     [rsp+1C0h+var_158], 0
0x140035e16  jz      short loc_140035E28
0x140035e18  lea     rdx, [rsp+1C0h+ActivityId]; ActivityId
0x140035e1d  mov     ecx, 2; ControlCode
0x140035e22  call    cs:__imp_EventActivityIdControl
0x140035e28  mov     eax, ebx
0x140035e2a  jmp     short loc_140035E6B
0x140035e2c  lea     rdx, aRemovepackage; "RemovePackage"
0x140035e33  lea     rcx, [rsp+1C0h+var_170]; this
0x140035e38  call    ??0SmartComMethodLogger@Service@Client@AppV@@QEAA@PEB_W@Z; AppV::Client::Service::SmartComMethodLogger::SmartComMethodLogger(wchar_t const *)
0x140035e3d  mov     [rsp+1C0h+var_160], 80070057h
0x140035e45  lea     rcx, [rsp+1C0h+var_170]; this
0x140035e4a  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x140035e4f  cmp     [rsp+1C0h+var_158], 0
0x140035e54  jz      short loc_140035E66
0x140035e56  lea     rdx, [rsp+1C0h+ActivityId]; ActivityId
0x140035e5b  mov     ecx, 2; ControlCode
0x140035e60  call    cs:__imp_EventActivityIdControl
0x140035e66  mov     eax, 80070057h
0x140035e6b  mov     rcx, [rbp+0C0h+var_30]
0x140035e72  xor     rcx, rsp; StackCookie
0x140035e75  call    __security_check_cookie
0x140035e7a  mov     rbx, [rsp+1C0h+arg_0]
0x140035e82  add     rsp, 1A0h
0x140035e89  pop     r15
0x140035e8b  pop     r14
0x140035e8d  pop     rdi
0x140035e8e  pop     rsi
0x140035e8f  pop     rbp
0x140035e90  retn
```
