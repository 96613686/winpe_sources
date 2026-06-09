# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppRestoreAsync(HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppIdType,uchar,HSTRING__ *,HSTRING__ *,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> * *)

- ea: `0x1800c3190`
- end: `0x1800c34a9`
- name: `?StartAppRestoreAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@UEAAJPEAUHSTRING__@@W4AppIdType@Internal@23456@E00PEAPEAU?$IAsyncOperation@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@6@@Z`
- size: `793`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180010b74`
- `0x18001c414`
- `0x180020274`
- `0x180023a9c`
- `0x18002548c`
- `0x180028cd4`
- `0x18003b08c`
- `0x18006e510`
- `0x180082af0`
- `0x18008df48`
- `0x18008f7b0`
- `0x180095c3c`
- `0x1800c3190`
- `0x1801473f4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3222`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3321`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3473`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3222`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3321`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3473`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c3360`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c3360`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3271`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c328a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3298`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c33f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3271`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c328a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3298`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c33f7`

## string_xrefs

- `0x1800c3251`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c32ef`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c3443`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c3232`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppRestoreAsync`
- `0x1800c32e2`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppRestoreAsync`
- `0x1800c3436`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppRestoreAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppRestoreAsync(
        __int64 a1,
        HSTRING a2,
        char *a3,
        __int64 a4,
        HSTRING a5,
        WindowsUpdate::CommonTelemetry *a6,
        _QWORD *a7)
{
  unsigned __int32 v9; // r12d
  int CallingProcessAndFunction; // eax
  unsigned int v11; // ebx
  HSTRING v12; // r14
  wchar_t *StringRawBuffer; // rax
  const unsigned __int16 *v14; // rdx
  bool v15; // r8
  PCWSTR v16; // rdi
  PCWSTR v17; // rbx
  __int64 v18; // rax
  TraceLoggingCorrelationVector *v19; // rsi
  int v21; // edi
  __int64 v22; // r8
  PCWSTR v23; // rbx
  __int64 v24; // rax
  unsigned int v25; // edx
  int v26; // [rsp+20h] [rbp-E0h]
  bool IsCallerInteractive; // [rsp+60h] [rbp-A0h]
  unsigned __int32 v28; // [rsp+64h] [rbp-9Ch] BYREF
  HSTRING string; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h] BYREF
  __int64 v31; // [rsp+78h] [rbp-88h] BYREF
  HSTRING newString; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v33; // [rsp+88h] [rbp-78h] BYREF
  __m128i si128; // [rsp+90h] [rbp-70h] BYREF
  int v35; // [rsp+A0h] [rbp-60h]
  TraceLoggingCorrelationVector *v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h] BYREF
  char v38[8]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v39[2]; // [rsp+C0h] [rbp-40h] BYREF
  bool v40; // [rsp+D0h] [rbp-30h]
  HSTRING v41; // [rsp+D8h] [rbp-28h]
  HSTRING__ v42; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v33 = a2;
  *a7 = 0;
  if ( !a2 || (unsigned int)a3 > 4 )
    return 2147942487LL;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v35 = 4;
  v9 = si128.m128i_u32[(int)a3];
  v28 = v9;
  WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(a6, &v42, a3);
  WindowsDeleteString(0);
  string = 0;
  CallingProcessAndFunction = GetCallingProcessAndFunction(
                                a5,
                                L"Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppRestoreAsync",
                                &string);
  v11 = CallingProcessAndFunction;
  if ( CallingProcessAndFunction < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C18,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)CallingProcessAndFunction,
      v26);
LABEL_7:
    WindowsDeleteString(string);
    return v11;
  }
  v12 = string;
  StringRawBuffer = (wchar_t *)WindowsGetStringRawBuffer(string, 0);
  LOBYTE(v14) = 1;
  IsCallerInteractive = Utils::IsCallerInteractive(StringRawBuffer, v14, v15);
  v16 = WindowsGetStringRawBuffer(v12, 0);
  v17 = WindowsGetStringRawBuffer(a2, 0);
  v18 = AppId::IdTypeName(v9);
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
    0x1C21u,
    "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppRestoreAsync",
    -1,
    L"request: %s = %s, CV = %hs, clientAppId = %s",
    0,
    0,
    v18,
    v17,
    &v42,
    v16);
  v19 = TraceLoggingCorrelationVector::Extend((const char *)&v42, 0);
  v36 = v19;
  if ( !v19 )
  {
    v11 = -2147024882;
    goto LABEL_7;
  }
  v31 = 0;
  v21 = Microsoft::WRL::Details::MakeAndInitialize<AppId,AppId,HSTRING__ * &,enum AppId::Type &>(&v31, &v33, &v28);
  if ( v21 < 0 )
    goto LABEL_12;
  newString = 0;
  if ( v12 )
    WindowsDuplicateString(v12, &newString);
  v30 = a1 - 136;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(&v30);
  v37 = a1 - 136;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>(
    v38,
    &v30);
  v39[0] = v31;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(v39);
  v36 = 0;
  v39[1] = v19;
  v40 = IsCallerInteractive;
  v41 = newString;
  si128.m128i_i64[0] = 2;
  si128.m128i_i32[2] = 0;
  v21 = Windows::Internal::MakeAsyncOperation_Windows::Internal::CMarshaledInterfaceResult_Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem__Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem___Windows::Internal::ComTaskPoolHandler__lambda_cbb8ca23c1f6e9ec4bde9e58220753fe___(
          &si128,
          a7,
          v22,
          &v37);
  lambda_cbb8ca23c1f6e9ec4bde9e58220753fe_::__lambda_cbb8ca23c1f6e9ec4bde9e58220753fe_(&v37);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v30);
  v19 = 0;
  if ( v21 < 0 )
  {
LABEL_12:
    v23 = WindowsGetStringRawBuffer(v33, 0);
    v24 = AppId::IdTypeName(v28);
    LogMessage(
      1u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      0x1C6Bu,
      "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppRestoreAsync",
      v21,
      L"initialization failed: %s = %s, CV = %hs",
      0,
      0,
      v24,
      v23,
      &v42);
  }
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v31);
  if ( v19 )
    TraceLoggingCorrelationVector::`scalar deleting destructor'(v19, v25);
  WindowsDeleteString(string);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x1800c3190  mov     [rsp-8+arg_0], rbx
0x1800c3195  push    rbp
0x1800c3196  push    rsi
0x1800c3197  push    rdi
0x1800c3198  push    r12
0x1800c319a  push    r13
0x1800c319c  push    r14
0x1800c319e  push    r15
0x1800c31a0  lea     rbp, [rsp-80h]
0x1800c31a5  sub     rsp, 180h
0x1800c31ac  mov     rax, cs:__security_cookie
0x1800c31b3  xor     rax, rsp
0x1800c31b6  mov     [rbp+0B0h+var_40], rax
0x1800c31ba  mov     rsi, rdx
0x1800c31bd  mov     r13, rcx
0x1800c31c0  mov     [rbp+0B0h+var_128], rdx
0x1800c31c4  mov     rbx, [rbp+0B0h+arg_20]
0x1800c31cb  mov     rcx, [rbp+0B0h+arg_28]; this
0x1800c31d2  mov     r15, [rbp+0B0h+arg_30]
0x1800c31d9  xor     edi, edi
0x1800c31db  mov     [r15], rdi
0x1800c31de  test    rdx, rdx
0x1800c31e1  jz      loc_1800C347D
0x1800c31e7  cmp     r8d, 4
0x1800c31eb  ja      loc_1800C347D
0x1800c31f1  movdqa  xmm0, cs:__xmm@00000003000000020000000100000000
0x1800c31f9  movdqu  [rbp+0B0h+var_120], xmm0
0x1800c31fe  mov     [rbp+0B0h+var_110], 4
0x1800c3205  movsxd  rax, r8d
0x1800c3208  mov     r12d, dword ptr [rbp+rax*4+0B0h+var_120]
0x1800c320d  mov     [rsp+1B0h+var_14C], r12d
0x1800c3212  lea     rdx, [rbp+0B0h+var_D0]; HSTRING
0x1800c3216  call    ?GenerateIfMissingCorrelationVector@CommonTelemetry@WindowsUpdate@@YAXPEAUHSTRING__@@QEAD@Z; WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(HSTRING__ *,char * const)
0x1800c321b  mov     [rsp+1B0h+string], rdi
0x1800c3220  xor     ecx, ecx; string
0x1800c3222  call    cs:__imp_WindowsDeleteString
0x1800c3228  mov     [rsp+1B0h+string], rdi
0x1800c322d  lea     r8, [rsp+1B0h+string]; HSTRING *
0x1800c3232  lea     rdx, aWindowsApplica_67; "Windows::ApplicationModel::Store::Previ"...
0x1800c3239  mov     rcx, rbx; HSTRING
0x1800c323c  call    ?GetCallingProcessAndFunction@@YAJPEAUHSTRING__@@PEBGPEAPEAU1@@Z; GetCallingProcessAndFunction(HSTRING__ *,ushort const *,HSTRING__ * *)
0x1800c3241  mov     ebx, eax
0x1800c3243  test    eax, eax
0x1800c3245  jns     short loc_1800C3267
0x1800c3247  mov     rcx, [rbp+0B8h]; this
0x1800c324e  mov     r9d, eax; char *
0x1800c3251  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c3258  mov     edx, 1C18h; void *
0x1800c325d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c3262  jmp     loc_1800C331C
0x1800c3267  mov     r14, [rsp+1B0h+string]
0x1800c326c  xor     edx, edx; length
0x1800c326e  mov     rcx, r14; string
0x1800c3271  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c3277  mov     rcx, rax; Str
0x1800c327a  mov     dl, 1; unsigned __int16 *
0x1800c327c  call    ?IsCallerInteractive@Utils@@YA_NPEBG_N@Z; Utils::IsCallerInteractive(ushort const *,bool)
0x1800c3281  mov     [rsp+1B0h+var_150], al
0x1800c3285  xor     edx, edx; length
0x1800c3287  mov     rcx, r14; string
0x1800c328a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c3290  mov     rdi, rax
0x1800c3293  xor     edx, edx; length
0x1800c3295  mov     rcx, rsi; string
0x1800c3298  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c329e  mov     rbx, rax
0x1800c32a1  mov     ecx, r12d
0x1800c32a4  call    ?IdTypeName@AppId@@SAPEBGW4Type@1@@Z; AppId::IdTypeName(AppId::Type)
0x1800c32a9  mov     [rsp+1B0h+var_158], rdi
0x1800c32ae  lea     rcx, [rbp+0B0h+var_D0]
0x1800c32b2  mov     [rsp+1B0h+var_160], rcx
0x1800c32b7  mov     [rsp+1B0h+var_168], rbx
0x1800c32bc  mov     [rsp+1B0h+var_170], rax
0x1800c32c1  xor     r12d, r12d
0x1800c32c4  mov     [rsp+1B0h+var_178], r12; unsigned __int16 *
0x1800c32c9  mov     [rsp+1B0h+var_180], r12; char *
0x1800c32ce  lea     rax, aRequestSSCvHsC; "request: %s = %s, CV = %hs, clientAppId"...
0x1800c32d5  mov     [rsp+1B0h+var_188], rax; unsigned __int16 *
0x1800c32da  mov     [rsp+1B0h+var_190], 0FFFFFFFFh; int
0x1800c32e2  lea     r9, aWindowsApplica_68; "Windows::ApplicationModel::Store::Previ"...
0x1800c32e9  mov     r8d, 1C21h; unsigned int
0x1800c32ef  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c32f6  lea     ecx, [r12+3]; unsigned int
0x1800c32fb  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800c3300  xor     edx, edx; bool
0x1800c3302  lea     rcx, [rbp+0B0h+var_D0]; char *
0x1800c3306  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x1800c330b  mov     rsi, rax
0x1800c330e  mov     [rbp+0B0h+var_108], rax
0x1800c3312  test    rax, rax
0x1800c3315  jnz     short loc_1800C332E
0x1800c3317  mov     ebx, 8007000Eh
0x1800c331c  mov     rcx, [rsp+1B0h+string]; string
0x1800c3321  call    cs:__imp_WindowsDeleteString
0x1800c3327  mov     eax, ebx
0x1800c3329  jmp     loc_1800C3482
0x1800c332e  mov     [rsp+1B0h+var_138], r12
0x1800c3333  lea     r8, [rsp+1B0h+var_14C]
0x1800c3338  lea     rdx, [rbp+0B0h+var_128]
0x1800c333c  lea     rcx, [rsp+1B0h+var_138]
0x1800c3341  call    ??$MakeAndInitialize@VAppId@@V1@AEAPEAUHSTRING__@@AEAW4Type@1@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VAppId@@@WRL@Microsoft@@@012@AEAPEAUHSTRING__@@AEAW4Type@AppId@@@Z; Microsoft::WRL::Details::MakeAndInitialize<AppId,AppId,HSTRING__ * &,AppId::Type &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<AppId>>,HSTRING__ * &,AppId::Type &)
0x1800c3346  mov     edi, eax
0x1800c3348  test    eax, eax
0x1800c334a  js      loc_1800C33F1
0x1800c3350  mov     [rbp+0B0h+newString], r12
0x1800c3354  test    r14, r14
0x1800c3357  jz      short loc_1800C3366
0x1800c3359  lea     rdx, [rbp+0B0h+newString]; newString
0x1800c335d  mov     rcx, r14; string
0x1800c3360  call    cs:__imp_WindowsDuplicateString
0x1800c3366  lea     rbx, [r13-88h]
0x1800c336d  mov     [rsp+1B0h+var_140], rbx
0x1800c3372  lea     rcx, [rsp+1B0h+var_140]
0x1800c3377  call    ?InternalAddRef@?$ComPtr@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(void)
0x1800c337c  nop
0x1800c337d  mov     [rbp+0B0h+var_100], rbx
0x1800c3381  lea     rdx, [rsp+1B0h+var_140]
0x1800c3386  lea     rcx, [rbp+0B0h+var_F8]
0x1800c338a  call    ??0?$ComPtr@VAppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>(Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl> &&)
0x1800c338f  mov     rcx, [rsp+1B0h+var_138]
0x1800c3394  mov     [rbp+0B0h+var_F0], rcx
0x1800c3398  lea     rcx, [rbp+0B0h+var_F0]
0x1800c339c  call    ?InternalAddRef@?$ComPtr@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(void)
0x1800c33a1  mov     [rbp+0B0h+var_108], r12
0x1800c33a5  mov     [rbp+0B0h+var_E8], rsi
0x1800c33a9  mov     al, [rsp+1B0h+var_150]
0x1800c33ad  mov     [rbp+0B0h+var_E0], al
0x1800c33b0  mov     rax, [rbp+0B0h+newString]
0x1800c33b4  mov     [rbp+0B0h+var_D8], rax
0x1800c33b8  mov     qword ptr [rbp+0B0h+var_120], 2
0x1800c33c0  mov     dword ptr [rbp+0B0h+var_120+8], r12d
0x1800c33c4  lea     r9, [rbp+0B0h+var_100]
0x1800c33c8  mov     rdx, r15
0x1800c33cb  lea     rcx, [rbp+0B0h+var_120]
0x1800c33cf  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CMarshaledInterfaceResult_Windows__ApplicationModel__Store__Preview__InstallControl__IAppInstallItem__Windows__ApplicationModel__Store__Preview__InstallControl__AppInstallItem___Windows__Internal__ComTaskPoolHandler__lambda_cbb8ca23c1f6e9ec4bde9e58220753fe___
0x1800c33d4  mov     edi, eax
0x1800c33d6  lea     rcx, [rbp+0B0h+var_100]
0x1800c33da  call    _lambda_cbb8ca23c1f6e9ec4bde9e58220753fe_____lambda_cbb8ca23c1f6e9ec4bde9e58220753fe_
0x1800c33df  nop
0x1800c33e0  lea     rcx, [rsp+1B0h+var_140]
0x1800c33e5  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c33ea  mov     rsi, r12
0x1800c33ed  test    edi, edi
0x1800c33ef  jns     short loc_1800C3455
0x1800c33f1  xor     edx, edx; length
0x1800c33f3  mov     rcx, [rbp+0B0h+var_128]; string
0x1800c33f7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c33fd  mov     rbx, rax
0x1800c3400  mov     ecx, [rsp+1B0h+var_14C]
0x1800c3404  call    ?IdTypeName@AppId@@SAPEBGW4Type@1@@Z; AppId::IdTypeName(AppId::Type)
0x1800c3409  lea     rdx, [rbp+0B0h+var_D0]
0x1800c340d  mov     [rsp+1B0h+var_160], rdx
0x1800c3412  mov     [rsp+1B0h+var_168], rbx
0x1800c3417  mov     [rsp+1B0h+var_170], rax
0x1800c341c  mov     [rsp+1B0h+var_178], r12; unsigned __int16 *
0x1800c3421  mov     [rsp+1B0h+var_180], r12; char *
0x1800c3426  lea     rax, aInitialization_10; "initialization failed: %s = %s, CV = %h"...
0x1800c342d  mov     [rsp+1B0h+var_188], rax; unsigned __int16 *
0x1800c3432  mov     [rsp+1B0h+var_190], edi; int
0x1800c3436  lea     r9, aWindowsApplica_68; "Windows::ApplicationModel::Store::Previ"...
0x1800c343d  mov     r8d, 1C6Bh; unsigned int
0x1800c3443  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c344a  mov     ecx, 1; unsigned int
0x1800c344f  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800c3454  nop
0x1800c3455  lea     rcx, [rsp+1B0h+var_138]
0x1800c345a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c345f  nop
0x1800c3460  test    rsi, rsi
0x1800c3463  jz      short loc_1800C346E
0x1800c3465  mov     rcx, rsi; this
0x1800c3468  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x1800c346d  nop
0x1800c346e  mov     rcx, [rsp+1B0h+string]; string
0x1800c3473  call    cs:__imp_WindowsDeleteString
0x1800c3479  mov     eax, edi
0x1800c347b  jmp     short loc_1800C3482
0x1800c347d  mov     eax, 80070057h
0x1800c3482  mov     rcx, [rbp+0B0h+var_40]
0x1800c3486  xor     rcx, rsp; StackCookie
0x1800c3489  call    __security_check_cookie
0x1800c348e  mov     rbx, [rsp+1B0h+arg_0]
0x1800c3496  add     rsp, 180h
0x1800c349d  pop     r15
0x1800c349f  pop     r14
0x1800c34a1  pop     r13
0x1800c34a3  pop     r12
0x1800c34a5  pop     rdi
0x1800c34a6  pop     rsi
0x1800c34a7  pop     rbp
0x1800c34a8  retn
```
