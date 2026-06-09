# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartProductInstallWithOptionsForUserAsync(Windows::System::IUser *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions *,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> * *)

- ea: `0x1800c4ed0`
- end: `0x1800c5173`
- name: `?StartProductInstallWithOptionsForUserAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@UEAAJPEAUIUser@System@6@PEAUHSTRING__@@111PEAUIAppInstallOptions@23456@PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@6@@Z`
- size: `675`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180009ea0`
- `0x180010b74`
- `0x18002ec2c`
- `0x18003b08c`
- `0x18006e510`
- `0x180084280`
- `0x1800c4ed0`
- `0x1800cd634`
- `0x1800d630c`
- `0x18012efb0`
- `0x1801473f4`
- `0x1801477b4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4f83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4f94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4fa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4fe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c502c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c503c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c5048`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c5054`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c50dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c50ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c50f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c5102`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4f83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4f94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4fa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c4fe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c502c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c503c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c5048`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c5054`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c50dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c50ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c50f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c5102`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4f50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c5068`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c4f50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c5068`

## string_xrefs

- `0x1800c5015`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c5136`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c514b`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c5160`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c4ff5`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartProductInstallWithOptionsForUserAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartProductInstallWithOptionsForUserAsync(
        __int64 a1,
        UserHelpers *a2,
        char *a3,
        __int64 a4,
        HSTRING a5,
        WindowsUpdate::CommonTelemetry *a6,
        int (__fastcall ***a7)(_QWORD, GUID *, __int64 *),
        _QWORD *a8)
{
  HSTRING ClientIdIfMissing; // rbx
  WindowsUpdate::CommonTelemetry *StringRawBuffer; // rax
  const char *v14; // r9
  struct Windows::System::IUser *v15; // rdx
  int v16; // eax
  int v17; // eax
  int CallingProcessAndFunction; // eax
  unsigned int v19; // ebx
  const char *v20; // r9
  __int64 result; // rax
  wchar_t *v22; // rax
  const unsigned __int16 *v23; // rdx
  bool v24; // r8
  char IsCallerInteractive; // al
  HSTRING v26; // rbx
  int started; // eax
  int v28; // [rsp+20h] [rbp-148h]
  int v29; // [rsp+20h] [rbp-148h]
  HSTRING string; // [rsp+60h] [rbp-108h] BYREF
  HSTRING v31; // [rsp+68h] [rbp-100h] BYREF
  HSTRING v32; // [rsp+70h] [rbp-F8h] BYREF
  HSTRING v33; // [rsp+78h] [rbp-F0h] BYREF
  int (__fastcall ***v34)(_QWORD, GUID *, __int64 *); // [rsp+80h] [rbp-E8h]
  HSTRING__ v35; // [rsp+90h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v34 = a7;
  *a8 = 0;
  try
  {
    WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(a6, &v35, a3);
    ClientIdIfMissing = CreateClientIdIfMissing(a5);
    StringRawBuffer = (WindowsUpdate::CommonTelemetry *)WindowsGetStringRawBuffer(ClientIdIfMissing, 0);
    WindowsUpdate::CommonTelemetry::InstallRequestReceived(StringRawBuffer, (const unsigned __int16 *)a3, &v35, v14);
    v16 = UserHelpers::ValidateMultiUserApiCall(a2, v15);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7BB,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
        (const char *)(unsigned int)v16,
        v28);
    WindowsDeleteString(0);
    v33 = 0;
    WindowsDeleteString(0);
    v31 = 0;
    WindowsDeleteString(0);
    v32 = 0;
    v17 = AppId::SplitStoreId((HSTRING)a3, &v32, &v31, &v33);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7BD,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
        (const char *)(unsigned int)v17,
        v28);
    WindowsDeleteString(0);
    string = 0;
    CallingProcessAndFunction = GetCallingProcessAndFunction(
                                  ClientIdIfMissing,
                                  L"Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::Star"
                                   "tProductInstallWithOptionsForUserAsync",
                                  &string);
    v19 = CallingProcessAndFunction;
    if ( CallingProcessAndFunction >= 0 )
    {
      v22 = (wchar_t *)WindowsGetStringRawBuffer(string, 0);
      LOBYTE(v23) = 1;
      IsCallerInteractive = Utils::IsCallerInteractive(v22, v23, v24);
      v26 = v33;
      started = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallWithOptionsAsync(
                  (RTL_SRWLOCK *)(a1 - 40),
                  (__int64)a2,
                  (__int64)v32,
                  (__int64)v31,
                  (__int64)v33,
                  a4,
                  (__int64)string,
                  IsCallerInteractive,
                  0,
                  (__int64)a6,
                  v34,
                  (__int64)a8);
      if ( started < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x7CE,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
          (const char *)(unsigned int)started,
          v29);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v26);
      WindowsDeleteString(v31);
      WindowsDeleteString(v32);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7C0,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
        (const char *)(unsigned int)CallingProcessAndFunction,
        v28);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v33);
      WindowsDeleteString(v31);
      WindowsDeleteString(v32);
      result = v19;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x7D1,
                           (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
                           v20);
  }
  return result;
}

```

## disassembly

```asm
0x1800c4ed0  push    rbx
0x1800c4ed2  push    rsi
0x1800c4ed3  push    rdi
0x1800c4ed4  push    r12
0x1800c4ed6  push    r13
0x1800c4ed8  push    r14
0x1800c4eda  push    r15
0x1800c4edc  sub     rsp, 130h
0x1800c4ee3  mov     rax, cs:__security_cookie
0x1800c4eea  xor     rax, rsp
0x1800c4eed  mov     [rsp+168h+var_48], rax
0x1800c4ef5  mov     r12, r9
0x1800c4ef8  mov     r14, r8
0x1800c4efb  mov     r15, rdx
0x1800c4efe  mov     r13, rcx
0x1800c4f01  mov     rbx, [rsp+168h+arg_20]
0x1800c4f09  mov     rdi, [rsp+168h+arg_28]
0x1800c4f11  mov     rax, [rsp+168h+arg_30]
0x1800c4f19  mov     [rsp+168h+var_E8], rax
0x1800c4f21  mov     rsi, [rsp+168h+arg_38]
0x1800c4f29  mov     qword ptr [rsi], 0
0x1800c4f30  lea     rdx, [rsp+168h+var_D8]; HSTRING
0x1800c4f38  mov     rcx, rdi; this
0x1800c4f3b  call    ?GenerateIfMissingCorrelationVector@CommonTelemetry@WindowsUpdate@@YAXPEAUHSTRING__@@QEAD@Z; WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(HSTRING__ *,char * const)
0x1800c4f40  mov     rcx, rbx; HSTRING
0x1800c4f43  call    ?CreateClientIdIfMissing@@YAPEAUHSTRING__@@PEAU1@@Z; CreateClientIdIfMissing(HSTRING__ *)
0x1800c4f48  mov     rbx, rax
0x1800c4f4b  xor     edx, edx; length
0x1800c4f4d  mov     rcx, rax; string
0x1800c4f50  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c4f56  mov     rcx, rax; this
0x1800c4f59  lea     r8, [rsp+168h+var_D8]; HSTRING
0x1800c4f61  mov     rdx, r14; unsigned __int16 *
0x1800c4f64  call    ?InstallRequestReceived@CommonTelemetry@WindowsUpdate@@YAXPEBGPEAUHSTRING__@@PEBD@Z; WindowsUpdate::CommonTelemetry::InstallRequestReceived(ushort const *,HSTRING__ *,char const *)
0x1800c4f69  mov     rcx, r15; this
0x1800c4f6c  call    ?ValidateMultiUserApiCall@UserHelpers@@YAJPEAUIUser@System@Windows@@@Z; UserHelpers::ValidateMultiUserApiCall(Windows::System::IUser *)
0x1800c4f71  mov     rcx, [rsp+168h]; this
0x1800c4f79  test    eax, eax
0x1800c4f7b  js      loc_1800C5133
0x1800c4f81  xor     ecx, ecx; string
0x1800c4f83  call    cs:__imp_WindowsDeleteString
0x1800c4f89  mov     [rsp+168h+var_F0], 0
0x1800c4f92  xor     ecx, ecx; string
0x1800c4f94  call    cs:__imp_WindowsDeleteString
0x1800c4f9a  mov     [rsp+168h+var_100], 0
0x1800c4fa3  xor     ecx, ecx; string
0x1800c4fa5  call    cs:__imp_WindowsDeleteString
0x1800c4fab  mov     [rsp+168h+var_F8], 0
0x1800c4fb4  lea     r9, [rsp+168h+var_F0]; HSTRING *
0x1800c4fb9  lea     r8, [rsp+168h+var_100]; HSTRING *
0x1800c4fbe  lea     rdx, [rsp+168h+var_F8]; HSTRING *
0x1800c4fc3  mov     rcx, r14; HSTRING
0x1800c4fc6  call    ?SplitStoreId@AppId@@SAJPEAUHSTRING__@@PEAPEAU2@11@Z; AppId::SplitStoreId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)
0x1800c4fcb  mov     rcx, [rsp+168h]; this
0x1800c4fd3  xor     r14d, r14d
0x1800c4fd6  test    eax, eax
0x1800c4fd8  js      loc_1800C5148
0x1800c4fde  mov     [rsp+168h+string], r14
0x1800c4fe3  xor     ecx, ecx; string
0x1800c4fe5  call    cs:__imp_WindowsDeleteString
0x1800c4feb  mov     [rsp+168h+string], r14
0x1800c4ff0  lea     r8, [rsp+168h+string]; HSTRING *
0x1800c4ff5  lea     rdx, aWindowsApplica_34; "Windows::ApplicationModel::Store::Previ"...
0x1800c4ffc  mov     rcx, rbx; HSTRING
0x1800c4fff  call    ?GetCallingProcessAndFunction@@YAJPEAUHSTRING__@@PEBGPEAPEAU1@@Z; GetCallingProcessAndFunction(HSTRING__ *,ushort const *,HSTRING__ * *)
0x1800c5004  mov     ebx, eax
0x1800c5006  test    eax, eax
0x1800c5008  jns     short loc_1800C5061
0x1800c500a  mov     rcx, [rsp+168h]; this
0x1800c5012  mov     r9d, eax; char *
0x1800c5015  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c501c  mov     edx, 7C0h; void *
0x1800c5021  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c5026  nop
0x1800c5027  mov     rcx, [rsp+168h+string]; string
0x1800c502c  call    cs:__imp_WindowsDeleteString
0x1800c5032  mov     [rsp+168h+string], r14
0x1800c5037  mov     rcx, [rsp+168h+var_F0]; string
0x1800c503c  call    cs:__imp_WindowsDeleteString
0x1800c5042  nop
0x1800c5043  mov     rcx, [rsp+168h+var_100]; string
0x1800c5048  call    cs:__imp_WindowsDeleteString
0x1800c504e  nop
0x1800c504f  mov     rcx, [rsp+168h+var_F8]; string
0x1800c5054  call    cs:__imp_WindowsDeleteString
0x1800c505a  mov     eax, ebx
0x1800c505c  jmp     loc_1800C5110
0x1800c5061  xor     edx, edx; length
0x1800c5063  mov     rcx, [rsp+168h+string]; string
0x1800c5068  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c506e  mov     rcx, rax; Str
0x1800c5071  mov     dl, 1; unsigned __int16 *
0x1800c5073  call    ?IsCallerInteractive@Utils@@YA_NPEBG_N@Z; Utils::IsCallerInteractive(ushort const *,bool)
0x1800c5078  mov     r8, [rsp+168h+string]
0x1800c507d  lea     rcx, [r13-28h]
0x1800c5081  mov     [rsp+168h+var_110], rsi
0x1800c5086  mov     rdx, [rsp+168h+var_E8]
0x1800c508e  mov     [rsp+168h+var_118], rdx
0x1800c5093  mov     [rsp+168h+var_120], rdi
0x1800c5098  mov     [rsp+168h+var_128], r14b
0x1800c509d  mov     [rsp+168h+var_130], al
0x1800c50a1  mov     [rsp+168h+var_138], r8
0x1800c50a6  mov     [rsp+168h+var_140], r12
0x1800c50ab  mov     rbx, [rsp+168h+var_F0]
0x1800c50b0  mov     qword ptr [rsp+168h+var_148], rbx; int
0x1800c50b5  mov     r9, [rsp+168h+var_100]
0x1800c50ba  mov     r8, [rsp+168h+var_F8]
0x1800c50bf  mov     rdx, r15
0x1800c50c2  call    ?_StartBundleProductInstallWithOptionsAsync@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAJPEAUIUser@System@6@PEAUHSTRING__@@1111EE1PEAUIAppInstallOptions@23456@PEAPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@6@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_StartBundleProductInstallWithOptionsAsync(Windows::System::IUser *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,uchar,uchar,HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions *,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> * *)
0x1800c50c7  mov     rcx, [rsp+168h]; this
0x1800c50cf  test    eax, eax
0x1800c50d1  js      loc_1800C515D
0x1800c50d7  mov     rcx, [rsp+168h+string]; string
0x1800c50dc  call    cs:__imp_WindowsDeleteString
0x1800c50e2  mov     [rsp+168h+string], r14
0x1800c50e7  mov     rcx, rbx; string
0x1800c50ea  call    cs:__imp_WindowsDeleteString
0x1800c50f0  nop
0x1800c50f1  mov     rcx, [rsp+168h+var_100]; string
0x1800c50f6  call    cs:__imp_WindowsDeleteString
0x1800c50fc  nop
0x1800c50fd  mov     rcx, [rsp+168h+var_F8]; string
0x1800c5102  call    cs:__imp_WindowsDeleteString
0x1800c5108  xor     eax, eax
0x1800c510a  jmp     short loc_1800C5110
0x1800c510c  mov     eax, dword ptr [rsp+168h+string]
0x1800c5110  mov     rcx, [rsp+168h+var_48]
0x1800c5118  xor     rcx, rsp; StackCookie
0x1800c511b  call    __security_check_cookie
0x1800c5120  add     rsp, 130h
0x1800c5127  pop     r15
0x1800c5129  pop     r14
0x1800c512b  pop     r13
0x1800c512d  pop     r12
0x1800c512f  pop     rdi
0x1800c5130  pop     rsi
0x1800c5131  pop     rbx
0x1800c5132  retn
0x1800c5133  mov     r9d, eax; char *
0x1800c5136  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c513d  mov     edx, 7BBh; void *
0x1800c5142  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c5148  mov     r9d, eax; char *
0x1800c514b  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c5152  mov     edx, 7BDh; void *
0x1800c5157  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c515d  mov     r9d, eax; char *
0x1800c5160  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c5167  mov     edx, 7CEh; void *
0x1800c516c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
