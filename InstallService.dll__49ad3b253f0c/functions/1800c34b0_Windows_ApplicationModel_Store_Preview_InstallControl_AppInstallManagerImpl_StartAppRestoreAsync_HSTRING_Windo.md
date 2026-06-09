# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppRestoreAsync(HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppIdType,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> * *)

- ea: `0x1800c34b0`
- end: `0x1800c3815`
- name: `?StartAppRestoreAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@UEAAJPEAUHSTRING__@@W4AppIdType@Internal@23456@PEAPEAU?$IAsyncOperation@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@6@@Z`
- size: `869`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180009ea0`
- `0x18000e44c`
- `0x1800101f4`
- `0x180010b74`
- `0x18001c414`
- `0x180020274`
- `0x180021438`
- `0x180023a9c`
- `0x180028cd4`
- `0x18003b08c`
- `0x18003f884`
- `0x18006e510`
- `0x180082af0`
- `0x18008df48`
- `0x18008f5bc`
- `0x180095c3c`
- `0x1800c34b0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3570`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c36b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c37cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3570`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c36b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c37cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c367d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c367d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c35be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c35cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3655`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c375d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c35be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c35cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c3655`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c375d`

## string_xrefs

- `0x1800c359e`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c3623`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c3693`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c37a9`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c3580`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppRestoreAsync`
- `0x1800c3616`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppRestoreAsync`
- `0x1800c379c`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppRestoreAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppRestoreAsync(
        __int64 a1,
        HSTRING a2,
        unsigned int a3,
        _QWORD *a4)
{
  unsigned __int32 v7; // r12d
  TraceLoggingCorrelationVector *v8; // rax
  TraceLoggingCorrelationVector *v9; // rsi
  int CallingProcessAndFunction; // eax
  unsigned int v12; // ebx
  int v13; // edi
  wchar_t *StringRawBuffer; // rax
  const unsigned __int16 *v15; // rdx
  bool v16; // r8
  bool IsCallerInteractive; // r14
  HRESULT v18; // eax
  unsigned int v19; // edx
  __int64 v20; // r8
  TraceLoggingCorrelationVector *v21; // rbx
  PCWSTR v22; // rbx
  __int64 v23; // rax
  unsigned int v24; // edx
  int v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int32 v28; // [rsp+68h] [rbp-98h] BYREF
  __int64 v29; // [rsp+70h] [rbp-90h] BYREF
  __int64 v30; // [rsp+78h] [rbp-88h] BYREF
  HSTRING newString; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v32; // [rsp+88h] [rbp-78h] BYREF
  TraceLoggingCorrelationVector *v33; // [rsp+90h] [rbp-70h]
  __m128i si128; // [rsp+98h] [rbp-68h] BYREF
  int v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h] BYREF
  char v37[8]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v38[3]; // [rsp+C0h] [rbp-40h] BYREF
  bool v39; // [rsp+D8h] [rbp-28h]
  char v40[144]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v32 = a2;
  *a4 = 0;
  if ( !a2 || a3 > 4 )
    return 2147942487LL;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v35 = 4;
  v7 = si128.m128i_u32[a3];
  v28 = v7;
  v8 = (TraceLoggingCorrelationVector *)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  v33 = v8;
  if ( v8 )
    v9 = TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v8);
  else
    v9 = 0;
  v33 = v9;
  if ( !v9 )
    return 2147942414LL;
  TraceLoggingCorrelationVector::Increment(v9, v40);
  WindowsDeleteString(0);
  string = 0;
  CallingProcessAndFunction = GetCallingProcessAndFunction(
                                0,
                                L"Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppRestoreAsync",
                                &string);
  v12 = CallingProcessAndFunction;
  if ( CallingProcessAndFunction < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1049,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)CallingProcessAndFunction,
      v25);
LABEL_13:
    WindowsDeleteString(string);
    string = 0;
    TraceLoggingCorrelationVector::`scalar deleting destructor'(v9, v19);
    return v12;
  }
  WindowsGetStringRawBuffer(string, 0);
  WindowsGetStringRawBuffer(a2, 0);
  AppId::IdTypeName(v7);
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
    0x1050u,
    "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppRestoreAsync",
    -1,
    L"request:  %s = %s, CV = %hs, clientAppId = %s",
    0,
    0);
  v29 = 0;
  v13 = Microsoft::WRL::Details::MakeAndInitialize<AppId,AppId,HSTRING__ * &,enum AppId::Type &>(&v29, &v32, &v28);
  StringRawBuffer = (wchar_t *)WindowsGetStringRawBuffer(string, 0);
  LOBYTE(v15) = 1;
  IsCallerInteractive = Utils::IsCallerInteractive(StringRawBuffer, v15, v16);
  if ( v13 < 0 )
    goto LABEL_15;
  newString = 0;
  v18 = WindowsDuplicateString(string, &newString);
  v12 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1058,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      (const char *)(unsigned int)v18,
      v26);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v29);
    goto LABEL_13;
  }
  v30 = a1 - 72;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(&v30);
  v36 = a1 - 72;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>(
    v37,
    &v30);
  v38[0] = v29;
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(v38);
  v33 = 0;
  v38[1] = v9;
  v38[2] = newString;
  v39 = IsCallerInteractive;
  si128.m128i_i64[0] = 2;
  si128.m128i_i32[2] = 0;
  v13 = Windows::Internal::MakeAsyncOperation_Windows::Internal::CMarshaledInterfaceResult_Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem__Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem___Windows::Internal::ComTaskPoolHandler__lambda_28d8e60b3d0822467f449ad206993a33___(
          &si128,
          a4,
          v20,
          &v36);
  lambda_cbb8ca23c1f6e9ec4bde9e58220753fe_::__lambda_cbb8ca23c1f6e9ec4bde9e58220753fe_(&v36);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v30);
  v9 = 0;
  v21 = 0;
  if ( v13 < 0 )
  {
LABEL_15:
    v22 = WindowsGetStringRawBuffer(v32, 0);
    v23 = AppId::IdTypeName(v28);
    LogMessage(
      1u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
      0x1092u,
      "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppRestoreAsync",
      v13,
      L"initialization failed: %s = %s, CV = %hs",
      0,
      0,
      v23,
      v22,
      v40);
    v21 = v9;
  }
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v29);
  WindowsDeleteString(string);
  string = 0;
  if ( v21 )
    TraceLoggingCorrelationVector::`scalar deleting destructor'(v21, v24);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800c34b0  mov     [rsp-8+arg_0], rbx
0x1800c34b5  push    rbp
0x1800c34b6  push    rsi
0x1800c34b7  push    rdi
0x1800c34b8  push    r12
0x1800c34ba  push    r13
0x1800c34bc  push    r14
0x1800c34be  push    r15
0x1800c34c0  lea     rbp, [rsp-80h]
0x1800c34c5  sub     rsp, 180h
0x1800c34cc  mov     rax, cs:__security_cookie
0x1800c34d3  xor     rax, rsp
0x1800c34d6  mov     [rbp+0B0h+var_40], rax
0x1800c34da  mov     r15, r9
0x1800c34dd  mov     r14, rdx
0x1800c34e0  mov     r13, rcx
0x1800c34e3  mov     [rbp+0B0h+var_128], rdx
0x1800c34e7  xor     edi, edi
0x1800c34e9  mov     [r9], rdi
0x1800c34ec  test    rdx, rdx
0x1800c34ef  jz      loc_1800C37E9
0x1800c34f5  cmp     r8d, 4
0x1800c34f9  ja      loc_1800C37E9
0x1800c34ff  movdqa  xmm0, cs:__xmm@00000003000000020000000100000000
0x1800c3507  movdqu  [rbp+0B0h+var_118], xmm0
0x1800c350c  mov     [rbp+0B0h+var_108], 4
0x1800c3513  movsxd  rax, r8d
0x1800c3516  mov     r12d, dword ptr [rbp+rax*4+0B0h+var_118]
0x1800c351b  mov     [rsp+1B0h+var_148], r12d
0x1800c3520  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800c3527  mov     ecx, 90h; unsigned __int64
0x1800c352c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800c3531  mov     [rbp+0B0h+var_120], rax
0x1800c3535  test    rax, rax
0x1800c3538  jz      short loc_1800C3547
0x1800c353a  mov     rcx, rax; this
0x1800c353d  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800c3542  mov     rsi, rax
0x1800c3545  jmp     short loc_1800C354A
0x1800c3547  mov     rsi, rdi
0x1800c354a  mov     [rbp+0B0h+var_120], rsi
0x1800c354e  test    rsi, rsi
0x1800c3551  jnz     short loc_1800C355D
0x1800c3553  mov     eax, 8007000Eh
0x1800c3558  jmp     loc_1800C37EE
0x1800c355d  lea     rdx, [rbp+0B0h+var_D0]; char *
0x1800c3561  mov     rcx, rsi; this
0x1800c3564  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x1800c3569  mov     [rsp+1B0h+string], rdi
0x1800c356e  xor     ecx, ecx; string
0x1800c3570  call    cs:__imp_WindowsDeleteString
0x1800c3576  mov     [rsp+1B0h+string], rdi
0x1800c357b  lea     r8, [rsp+1B0h+string]; HSTRING *
0x1800c3580  lea     rdx, aWindowsApplica_67; "Windows::ApplicationModel::Store::Previ"...
0x1800c3587  xor     ecx, ecx; HSTRING
0x1800c3589  call    ?GetCallingProcessAndFunction@@YAJPEAUHSTRING__@@PEBGPEAPEAU1@@Z; GetCallingProcessAndFunction(HSTRING__ *,ushort const *,HSTRING__ * *)
0x1800c358e  mov     ebx, eax
0x1800c3590  test    eax, eax
0x1800c3592  jns     short loc_1800C35B7
0x1800c3594  mov     rcx, [rbp+0B8h]; this
0x1800c359b  mov     r9d, eax; char *
0x1800c359e  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c35a5  mov     edx, 1049h; void *
0x1800c35aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c35af  xor     r12d, r12d
0x1800c35b2  jmp     loc_1800C36B0
0x1800c35b7  xor     edx, edx; length
0x1800c35b9  mov     rcx, [rsp+1B0h+string]; string
0x1800c35be  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c35c4  mov     rdi, rax
0x1800c35c7  xor     edx, edx; length
0x1800c35c9  mov     rcx, r14; string
0x1800c35cc  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c35d2  mov     rbx, rax
0x1800c35d5  mov     ecx, r12d
0x1800c35d8  call    ?IdTypeName@AppId@@SAPEBGW4Type@1@@Z; AppId::IdTypeName(AppId::Type)
0x1800c35dd  mov     [rsp+1B0h+var_158], rdi
0x1800c35e2  lea     rcx, [rbp+0B0h+var_D0]
0x1800c35e6  mov     [rsp+1B0h+var_160], rcx
0x1800c35eb  mov     [rsp+1B0h+var_168], rbx
0x1800c35f0  mov     [rsp+1B0h+var_170], rax
0x1800c35f5  xor     r12d, r12d
0x1800c35f8  mov     [rsp+1B0h+var_178], r12; unsigned __int16 *
0x1800c35fd  mov     [rsp+1B0h+var_180], r12; char *
0x1800c3602  lea     rax, aRequestSSCvHsC_0; "request:  %s = %s, CV = %hs, clientAppI"...
0x1800c3609  mov     [rsp+1B0h+var_188], rax; unsigned __int16 *
0x1800c360e  mov     [rsp+1B0h+var_190], 0FFFFFFFFh; int
0x1800c3616  lea     r9, aWindowsApplica_68; "Windows::ApplicationModel::Store::Previ"...
0x1800c361d  mov     r8d, 1050h; unsigned int
0x1800c3623  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c362a  lea     ecx, [r12+3]; unsigned int
0x1800c362f  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800c3634  mov     [rsp+1B0h+var_140], r12
0x1800c3639  lea     r8, [rsp+1B0h+var_148]
0x1800c363e  lea     rdx, [rbp+0B0h+var_128]
0x1800c3642  lea     rcx, [rsp+1B0h+var_140]
0x1800c3647  call    ??$MakeAndInitialize@VAppId@@V1@AEAPEAUHSTRING__@@AEAW4Type@1@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VAppId@@@WRL@Microsoft@@@012@AEAPEAUHSTRING__@@AEAW4Type@AppId@@@Z; Microsoft::WRL::Details::MakeAndInitialize<AppId,AppId,HSTRING__ * &,AppId::Type &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<AppId>>,HSTRING__ * &,AppId::Type &)
0x1800c364c  mov     edi, eax
0x1800c364e  xor     edx, edx; length
0x1800c3650  mov     rcx, [rsp+1B0h+string]; string
0x1800c3655  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c365b  mov     rcx, rax; Str
0x1800c365e  mov     dl, 1; unsigned __int16 *
0x1800c3660  call    ?IsCallerInteractive@Utils@@YA_NPEBG_N@Z; Utils::IsCallerInteractive(ushort const *,bool)
0x1800c3665  mov     r14b, al
0x1800c3668  test    edi, edi
0x1800c366a  js      loc_1800C3757
0x1800c3670  mov     [rbp+0B0h+newString], r12
0x1800c3674  lea     rdx, [rbp+0B0h+newString]; newString
0x1800c3678  mov     rcx, [rsp+1B0h+string]; string
0x1800c367d  call    cs:__imp_WindowsDuplicateString
0x1800c3683  mov     ebx, eax
0x1800c3685  test    eax, eax
0x1800c3687  jns     short loc_1800C36CF
0x1800c3689  mov     rcx, [rbp+0B8h]; this
0x1800c3690  mov     r9d, eax; char *
0x1800c3693  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c369a  mov     edx, 1058h; void *
0x1800c369f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c36a4  nop
0x1800c36a5  lea     rcx, [rsp+1B0h+var_140]
0x1800c36aa  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c36af  nop
0x1800c36b0  mov     rcx, [rsp+1B0h+string]; string
0x1800c36b5  call    cs:__imp_WindowsDeleteString
0x1800c36bb  mov     [rsp+1B0h+string], r12
0x1800c36c0  mov     rcx, rsi; this
0x1800c36c3  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x1800c36c8  mov     eax, ebx
0x1800c36ca  jmp     loc_1800C37EE
0x1800c36cf  lea     rbx, [r13-48h]
0x1800c36d3  mov     [rsp+1B0h+var_138], rbx
0x1800c36d8  lea     rcx, [rsp+1B0h+var_138]
0x1800c36dd  call    ?InternalAddRef@?$ComPtr@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(void)
0x1800c36e2  nop
0x1800c36e3  mov     [rbp+0B0h+var_100], rbx
0x1800c36e7  lea     rdx, [rsp+1B0h+var_138]
0x1800c36ec  lea     rcx, [rbp+0B0h+var_F8]
0x1800c36f0  call    ??0?$ComPtr@VAppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>(Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl> &&)
0x1800c36f5  mov     rcx, [rsp+1B0h+var_140]
0x1800c36fa  mov     [rbp+0B0h+var_F0], rcx
0x1800c36fe  lea     rcx, [rbp+0B0h+var_F0]
0x1800c3702  call    ?InternalAddRef@?$ComPtr@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(void)
0x1800c3707  mov     [rbp+0B0h+var_120], r12
0x1800c370b  mov     [rbp+0B0h+var_E8], rsi
0x1800c370f  mov     rax, [rbp+0B0h+newString]
0x1800c3713  mov     [rbp+0B0h+var_E0], rax
0x1800c3717  mov     [rbp+0B0h+var_D8], r14b
0x1800c371b  mov     qword ptr [rbp+0B0h+var_118], 2
0x1800c3723  mov     dword ptr [rbp+0B0h+var_118+8], r12d
0x1800c3727  lea     r9, [rbp+0B0h+var_100]
0x1800c372b  mov     rdx, r15
0x1800c372e  lea     rcx, [rbp+0B0h+var_118]
0x1800c3732  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CMarshaledInterfaceResult_Windows__ApplicationModel__Store__Preview__InstallControl__IAppInstallItem__Windows__ApplicationModel__Store__Preview__InstallControl__AppInstallItem___Windows__Internal__ComTaskPoolHandler__lambda_28d8e60b3d0822467f449ad206993a33___
0x1800c3737  mov     edi, eax
0x1800c3739  lea     rcx, [rbp+0B0h+var_100]
0x1800c373d  call    _lambda_cbb8ca23c1f6e9ec4bde9e58220753fe_____lambda_cbb8ca23c1f6e9ec4bde9e58220753fe_
0x1800c3742  nop
0x1800c3743  lea     rcx, [rsp+1B0h+var_138]
0x1800c3748  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c374d  mov     rsi, r12
0x1800c3750  mov     rbx, r12
0x1800c3753  test    edi, edi
0x1800c3755  jns     short loc_1800C37BD
0x1800c3757  xor     edx, edx; length
0x1800c3759  mov     rcx, [rbp+0B0h+var_128]; string
0x1800c375d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c3763  mov     rbx, rax
0x1800c3766  mov     ecx, [rsp+1B0h+var_148]
0x1800c376a  call    ?IdTypeName@AppId@@SAPEBGW4Type@1@@Z; AppId::IdTypeName(AppId::Type)
0x1800c376f  lea     rdx, [rbp+0B0h+var_D0]
0x1800c3773  mov     [rsp+1B0h+var_160], rdx
0x1800c3778  mov     [rsp+1B0h+var_168], rbx
0x1800c377d  mov     [rsp+1B0h+var_170], rax
0x1800c3782  mov     [rsp+1B0h+var_178], r12; unsigned __int16 *
0x1800c3787  mov     [rsp+1B0h+var_180], r12; char *
0x1800c378c  lea     rax, aInitialization_10; "initialization failed: %s = %s, CV = %h"...
0x1800c3793  mov     [rsp+1B0h+var_188], rax; unsigned __int16 *
0x1800c3798  mov     [rsp+1B0h+var_190], edi; int
0x1800c379c  lea     r9, aWindowsApplica_68; "Windows::ApplicationModel::Store::Previ"...
0x1800c37a3  mov     r8d, 1092h; unsigned int
0x1800c37a9  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c37b0  mov     ecx, 1; unsigned int
0x1800c37b5  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800c37ba  mov     rbx, rsi
0x1800c37bd  lea     rcx, [rsp+1B0h+var_140]
0x1800c37c2  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c37c7  nop
0x1800c37c8  mov     rcx, [rsp+1B0h+string]; string
0x1800c37cd  call    cs:__imp_WindowsDeleteString
0x1800c37d3  mov     [rsp+1B0h+string], r12
0x1800c37d8  test    rbx, rbx
0x1800c37db  jz      short loc_1800C37E5
0x1800c37dd  mov     rcx, rbx; this
0x1800c37e0  call    ??_GTraceLoggingCorrelationVector@@QEAAPEAXI@Z; TraceLoggingCorrelationVector::`scalar deleting destructor'(uint)
0x1800c37e5  mov     eax, edi
0x1800c37e7  jmp     short loc_1800C37EE
0x1800c37e9  mov     eax, 80070057h
0x1800c37ee  mov     rcx, [rbp+0B0h+var_40]
0x1800c37f2  xor     rcx, rsp; StackCookie
0x1800c37f5  call    __security_check_cookie
0x1800c37fa  mov     rbx, [rsp+1B0h+arg_0]
0x1800c3802  add     rsp, 180h
0x1800c3809  pop     r15
0x1800c380b  pop     r14
0x1800c380d  pop     r13
0x1800c380f  pop     r12
0x1800c3811  pop     rdi
0x1800c3812  pop     rsi
0x1800c3813  pop     rbp
0x1800c3814  retn
```
