# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::UnblockLowPriorityWorkItems(HSTRING__ *,HSTRING__ *)

- ea: `0x1800c5f10`
- end: `0x1800c61a5`
- name: `?UnblockLowPriorityWorkItems@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@UEAAJPEAUHSTRING__@@0@Z`
- size: `661`
- prototype: `int(Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *__hidden this, HSTRING, HSTRING)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180010b74`
- `0x18001c414`
- `0x180037200`
- `0x18003b08c`
- `0x1800453bc`
- `0x180045588`
- `0x18004c5d8`
- `0x18008fc28`
- `0x1800c5f10`
- `0x1800c893c`
- `0x1800cd008`
- `0x1801473f4`
- `0x180215010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x1800c5f6d`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x1800c5f6d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800c614d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800c614d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800c6122`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800c6122`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c5f7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c5fc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c610e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c5f7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c5fc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c610e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c5fdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c5fdd`

## string_xrefs

- `0x1800c5fb2`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c6028`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800c5f92`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::UnblockLowPriorityWorkItems`
- `0x1800c601b`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::UnblockLowPriorityWorkItems`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::UnblockLowPriorityWorkItems(
        RTL_SRWLOCK *this,
        HSTRING a2,
        WindowsUpdate::CommonTelemetry *a3)
{
  char *v6; // r8
  int CallingProcessAndFunction; // eax
  unsigned int v8; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 *InstallControl2; // rdi
  __int64 v12; // rbx
  _QWORD *v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // eax
  PVOID Ptr; // rbx
  unsigned int v17; // ebx
  int v18; // [rsp+20h] [rbp-278h]
  HSTRING v19; // [rsp+50h] [rbp-248h] BYREF
  HSTRING string; // [rsp+58h] [rbp-240h] BYREF
  PVOID v21; // [rsp+60h] [rbp-238h] BYREF
  char v22[8]; // [rsp+68h] [rbp-230h] BYREF
  _BYTE v23[16]; // [rsp+70h] [rbp-228h] BYREF
  int v24; // [rsp+80h] [rbp-218h] BYREF
  __int128 v25; // [rsp+88h] [rbp-210h]
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-200h] BYREF
  __int64 v27; // [rsp+B0h] [rbp-1E8h]
  HSTRING__ v28; // [rsp+C0h] [rbp-1D8h] BYREF
  WCHAR sourceString[136]; // [rsp+150h] [rbp-148h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  if ( Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ShouldUseInstallControl2((Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *)this) )
  {
    WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(a3, &v28, v6);
    _o_mbstowcs(sourceString, &v28, 129);
    WindowsDeleteString(0);
    string = 0;
    CallingProcessAndFunction = GetCallingProcessAndFunction(
                                  a2,
                                  L"Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::Unbl"
                                   "ockLowPriorityWorkItems",
                                  &string);
    v8 = CallingProcessAndFunction;
    if ( CallingProcessAndFunction >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
        0x1B9Bu,
        "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::UnblockLowPriorityWorkItems",
        -1,
        L"UnblockLowPriorityWorkItems request: clientAppId: %s, CV = %hs",
        0,
        0,
        StringRawBuffer,
        &v28);
      InstallControl2 = (__int64 *)Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(
                                     &this[-15],
                                     &v21);
      v19 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, sourceString) + 24);
      v12 = *(_QWORD *)ToWinRTType<HSTRING__ *>(v23, &v19);
      v19 = string;
      v13 = (_QWORD *)ToWinRTType<HSTRING__ *>(v22, &v19);
      v14 = *InstallControl2;
      v24 = 0;
      v25 = 0;
      v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v14 + 176LL))(v14, *v13, v12);
      winrt::check_hresult(&v19, v15, &v24);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v22);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v23);
      v27 = 0;
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v21);
      WindowsDeleteString(string);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B9A,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
        (const char *)(unsigned int)CallingProcessAndFunction,
        v18);
      WindowsDeleteString(string);
      return v8;
    }
  }
  else
  {
    AcquireSRWLockShared(this + 15);
    Ptr = this[18].Ptr;
    v21 = Ptr;
    if ( Ptr )
      (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 8LL))(Ptr);
    ReleaseSRWLockShared(this + 15);
    if ( Ptr )
      v17 = (*(__int64 (__fastcall **)(PVOID, HSTRING, WindowsUpdate::CommonTelemetry *))(*(_QWORD *)Ptr + 248LL))(
              Ptr,
              a2,
              a3);
    else
      v17 = -2147467259;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v21);
    return v17;
  }
}

```

## disassembly

```asm
0x1800c5f10  push    rbx
0x1800c5f12  push    rsi
0x1800c5f13  push    rdi
0x1800c5f14  push    r14
0x1800c5f16  push    r15
0x1800c5f18  sub     rsp, 270h
0x1800c5f1f  mov     rax, cs:__security_cookie
0x1800c5f26  xor     rax, rsp
0x1800c5f29  mov     [rsp+298h+var_38], rax
0x1800c5f31  mov     r14, r8
0x1800c5f34  mov     r15, rdx
0x1800c5f37  mov     rdi, rcx
0x1800c5f3a  call    ?_ShouldUseInstallControl2@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAA_NXZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ShouldUseInstallControl2(void)
0x1800c5f3f  test    al, al
0x1800c5f41  jz      loc_1800C611E
0x1800c5f47  lea     rdx, [rsp+298h+var_1D8]; HSTRING
0x1800c5f4f  mov     rcx, r14; this
0x1800c5f52  call    ?GenerateIfMissingCorrelationVector@CommonTelemetry@WindowsUpdate@@YAXPEAUHSTRING__@@QEAD@Z; WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(HSTRING__ *,char * const)
0x1800c5f57  mov     r8d, 81h
0x1800c5f5d  lea     rdx, [rsp+298h+var_1D8]
0x1800c5f65  lea     rcx, [rsp+298h+sourceString]
0x1800c5f6d  call    cs:__imp__o_mbstowcs
0x1800c5f73  mov     [rsp+298h+string], 0
0x1800c5f7c  xor     ecx, ecx; string
0x1800c5f7e  call    cs:__imp_WindowsDeleteString
0x1800c5f84  mov     [rsp+298h+string], 0
0x1800c5f8d  lea     r8, [rsp+298h+string]; HSTRING *
0x1800c5f92  lea     rdx, aWindowsApplica_110; "Windows::ApplicationModel::Store::Previ"...
0x1800c5f99  mov     rcx, r15; HSTRING
0x1800c5f9c  call    ?GetCallingProcessAndFunction@@YAJPEAUHSTRING__@@PEBGPEAPEAU1@@Z; GetCallingProcessAndFunction(HSTRING__ *,ushort const *,HSTRING__ * *)
0x1800c5fa1  mov     ebx, eax
0x1800c5fa3  test    eax, eax
0x1800c5fa5  jns     short loc_1800C5FD6
0x1800c5fa7  mov     rcx, [rsp+298h]; this
0x1800c5faf  mov     r9d, eax; char *
0x1800c5fb2  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c5fb9  mov     edx, 1B9Ah; void *
0x1800c5fbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c5fc3  nop
0x1800c5fc4  mov     rcx, [rsp+298h+string]; string
0x1800c5fc9  call    cs:__imp_WindowsDeleteString
0x1800c5fcf  mov     eax, ebx
0x1800c5fd1  jmp     loc_1800C6185
0x1800c5fd6  xor     edx, edx; length
0x1800c5fd8  mov     rcx, [rsp+298h+string]; string
0x1800c5fdd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c5fe3  lea     rcx, [rsp+298h+var_1D8]
0x1800c5feb  mov     [rsp+298h+var_250], rcx
0x1800c5ff0  mov     [rsp+298h+var_258], rax
0x1800c5ff5  mov     [rsp+298h+var_260], 0; unsigned __int16 *
0x1800c5ffe  mov     [rsp+298h+var_268], 0; char *
0x1800c6007  lea     rax, aUnblocklowprio_0; "UnblockLowPriorityWorkItems request: cl"...
0x1800c600e  mov     [rsp+298h+var_270], rax; unsigned __int16 *
0x1800c6013  mov     [rsp+298h+var_278], 0FFFFFFFFh; int
0x1800c601b  lea     r9, aWindowsApplica_153; "Windows::ApplicationModel::Store::Previ"...
0x1800c6022  mov     r8d, 1B9Bh; unsigned int
0x1800c6028  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800c602f  mov     ecx, 3; unsigned int
0x1800c6034  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800c6039  lea     rcx, [rdi-78h]
0x1800c603d  lea     rdx, [rsp+298h+var_238]
0x1800c6042  call    ?_GetInstallControl2@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAA?AUInstallServiceControl@Control@InstallService@Internal@6winrt@@XZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(void)
0x1800c6047  mov     rdi, rax
0x1800c604a  lea     rdx, [rsp+298h+sourceString]; sourceString
0x1800c6052  lea     rcx, [rsp+298h+hstringHeader]; hstringHeader
0x1800c605a  call    ??$?0$0ICE@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0ICE@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[2084])
0x1800c605f  nop
0x1800c6060  mov     rcx, [rax+18h]
0x1800c6064  mov     [rsp+298h+var_248], rcx
0x1800c6069  lea     rdx, [rsp+298h+var_248]
0x1800c606e  lea     rcx, [rsp+298h+var_228]
0x1800c6073  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800c6078  nop
0x1800c6079  mov     rbx, [rax]
0x1800c607c  mov     rax, [rsp+298h+string]
0x1800c6081  mov     [rsp+298h+var_248], rax
0x1800c6086  lea     rdx, [rsp+298h+var_248]
0x1800c608b  lea     rcx, [rsp+298h+var_230]
0x1800c6090  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800c6095  mov     r9, rax
0x1800c6098  mov     rcx, [rdi]
0x1800c609b  mov     [rsp+298h+var_218], 0
0x1800c60a6  xorps   xmm0, xmm0
0x1800c60a9  movdqu  [rsp+298h+var_210], xmm0
0x1800c60b2  mov     rdx, [rcx]
0x1800c60b5  mov     rax, [rdx+0B0h]
0x1800c60bc  mov     r8, rbx
0x1800c60bf  mov     rdx, [r9]
0x1800c60c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c60c7  lea     r8, [rsp+298h+var_218]
0x1800c60cf  mov     edx, eax
0x1800c60d1  lea     rcx, [rsp+298h+var_248]
0x1800c60d6  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800c60db  nop
0x1800c60dc  lea     rcx, [rsp+298h+var_230]
0x1800c60e1  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800c60e6  nop
0x1800c60e7  lea     rcx, [rsp+298h+var_228]
0x1800c60ec  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800c60f1  nop
0x1800c60f2  mov     [rsp+298h+var_1E8], 0
0x1800c60fe  lea     rcx, [rsp+298h+var_238]; void *
0x1800c6103  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1800c6108  nop
0x1800c6109  mov     rcx, [rsp+298h+string]; string
0x1800c610e  call    cs:__imp_WindowsDeleteString
0x1800c6114  xor     eax, eax
0x1800c6116  jmp     short loc_1800C6185
0x1800c6118  mov     eax, dword ptr [rsp+298h+var_248]
0x1800c611c  jmp     short loc_1800C6185
0x1800c611e  lea     rcx, [rdi+78h]; SRWLock
0x1800c6122  call    cs:__imp_AcquireSRWLockShared
0x1800c6128  mov     rbx, [rdi+90h]
0x1800c612f  mov     [rsp+298h+var_238], rbx
0x1800c6134  test    rbx, rbx
0x1800c6137  jz      short loc_1800C6149
0x1800c6139  mov     rax, [rbx]
0x1800c613c  mov     rcx, rbx
0x1800c613f  mov     rax, [rax+8]
0x1800c6143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6148  nop
0x1800c6149  lea     rcx, [rdi+78h]; SRWLock
0x1800c614d  call    cs:__imp_ReleaseSRWLockShared
0x1800c6153  test    rbx, rbx
0x1800c6156  jz      short loc_1800C6174
0x1800c6158  mov     rax, [rbx]
0x1800c615b  mov     r8, r14
0x1800c615e  mov     rdx, r15
0x1800c6161  mov     rcx, rbx
0x1800c6164  mov     rax, [rax+0F8h]
0x1800c616b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6170  mov     ebx, eax
0x1800c6172  jmp     short loc_1800C6179
0x1800c6174  mov     ebx, 80004005h
0x1800c6179  lea     rcx, [rsp+298h+var_238]
0x1800c617e  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800c6183  mov     eax, ebx
0x1800c6185  mov     rcx, [rsp+298h+var_38]
0x1800c618d  xor     rcx, rsp; StackCookie
0x1800c6190  call    __security_check_cookie
0x1800c6195  add     rsp, 270h
0x1800c619c  pop     r15
0x1800c619e  pop     r14
0x1800c61a0  pop     rdi
0x1800c61a1  pop     rsi
0x1800c61a2  pop     rbx
0x1800c61a3  retn
```
