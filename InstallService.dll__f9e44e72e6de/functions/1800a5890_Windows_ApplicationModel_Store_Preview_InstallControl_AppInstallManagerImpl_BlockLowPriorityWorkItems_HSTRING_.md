# Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::BlockLowPriorityWorkItems(HSTRING__ *,HSTRING__ *)

- ea: `0x1800a5890`
- end: `0x1800a5b25`
- name: `?BlockLowPriorityWorkItems@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@UEAAJPEAUHSTRING__@@0@Z`
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
- `0x1800a5890`
- `0x1800c893c`
- `0x1800cd008`
- `0x1801473f4`
- `0x180215010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x1800a58ed`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x1800a58ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a5acd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a5acd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800a5aa2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800a5aa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a58fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5949`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5a8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a58fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5949`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5a8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a595d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a595d`

## string_xrefs

- `0x1800a5932`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800a59a8`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800a5912`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::BlockLowPriorityWorkItems`
- `0x1800a599b`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::BlockLowPriorityWorkItems`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::BlockLowPriorityWorkItems(
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
                                  L"Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::Bloc"
                                   "kLowPriorityWorkItems",
                                  &string);
    v8 = CallingProcessAndFunction;
    if ( CallingProcessAndFunction >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
        0x1BB4u,
        "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::BlockLowPriorityWorkItems",
        -1,
        L"BlockLowPriorityWorkItems request: clientAppId: %s, CV = %hs",
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
      v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v14 + 184LL))(v14, *v13, v12);
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
        (void *)0x1BB3,
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
      v17 = (*(__int64 (__fastcall **)(PVOID, HSTRING, WindowsUpdate::CommonTelemetry *))(*(_QWORD *)Ptr + 256LL))(
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
0x1800a5890  push    rbx
0x1800a5892  push    rsi
0x1800a5893  push    rdi
0x1800a5894  push    r14
0x1800a5896  push    r15
0x1800a5898  sub     rsp, 270h
0x1800a589f  mov     rax, cs:__security_cookie
0x1800a58a6  xor     rax, rsp
0x1800a58a9  mov     [rsp+298h+var_38], rax
0x1800a58b1  mov     r14, r8
0x1800a58b4  mov     r15, rdx
0x1800a58b7  mov     rdi, rcx
0x1800a58ba  call    ?_ShouldUseInstallControl2@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAA_NXZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ShouldUseInstallControl2(void)
0x1800a58bf  test    al, al
0x1800a58c1  jz      loc_1800A5A9E
0x1800a58c7  lea     rdx, [rsp+298h+var_1D8]; HSTRING
0x1800a58cf  mov     rcx, r14; this
0x1800a58d2  call    ?GenerateIfMissingCorrelationVector@CommonTelemetry@WindowsUpdate@@YAXPEAUHSTRING__@@QEAD@Z; WindowsUpdate::CommonTelemetry::GenerateIfMissingCorrelationVector(HSTRING__ *,char * const)
0x1800a58d7  mov     r8d, 81h
0x1800a58dd  lea     rdx, [rsp+298h+var_1D8]
0x1800a58e5  lea     rcx, [rsp+298h+sourceString]
0x1800a58ed  call    cs:__imp__o_mbstowcs
0x1800a58f3  mov     [rsp+298h+string], 0
0x1800a58fc  xor     ecx, ecx; string
0x1800a58fe  call    cs:__imp_WindowsDeleteString
0x1800a5904  mov     [rsp+298h+string], 0
0x1800a590d  lea     r8, [rsp+298h+string]; HSTRING *
0x1800a5912  lea     rdx, aWindowsApplica_46; "Windows::ApplicationModel::Store::Previ"...
0x1800a5919  mov     rcx, r15; HSTRING
0x1800a591c  call    ?GetCallingProcessAndFunction@@YAJPEAUHSTRING__@@PEBGPEAPEAU1@@Z; GetCallingProcessAndFunction(HSTRING__ *,ushort const *,HSTRING__ * *)
0x1800a5921  mov     ebx, eax
0x1800a5923  test    eax, eax
0x1800a5925  jns     short loc_1800A5956
0x1800a5927  mov     rcx, [rsp+298h]; this
0x1800a592f  mov     r9d, eax; char *
0x1800a5932  lea     r8, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800a5939  mov     edx, 1BB3h; void *
0x1800a593e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5943  nop
0x1800a5944  mov     rcx, [rsp+298h+string]; string
0x1800a5949  call    cs:__imp_WindowsDeleteString
0x1800a594f  mov     eax, ebx
0x1800a5951  jmp     loc_1800A5B05
0x1800a5956  xor     edx, edx; length
0x1800a5958  mov     rcx, [rsp+298h+string]; string
0x1800a595d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a5963  lea     rcx, [rsp+298h+var_1D8]
0x1800a596b  mov     [rsp+298h+var_250], rcx
0x1800a5970  mov     [rsp+298h+var_258], rax
0x1800a5975  mov     [rsp+298h+var_260], 0; unsigned __int16 *
0x1800a597e  mov     [rsp+298h+var_268], 0; char *
0x1800a5987  lea     rax, aBlocklowpriori_0; "BlockLowPriorityWorkItems request: clie"...
0x1800a598e  mov     [rsp+298h+var_270], rax; unsigned __int16 *
0x1800a5993  mov     [rsp+298h+var_278], 0FFFFFFFFh; int
0x1800a599b  lea     r9, aWindowsApplica_16; "Windows::ApplicationModel::Store::Previ"...
0x1800a59a2  mov     r8d, 1BB4h; unsigned int
0x1800a59a8  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800a59af  mov     ecx, 3; unsigned int
0x1800a59b4  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800a59b9  lea     rcx, [rdi-78h]
0x1800a59bd  lea     rdx, [rsp+298h+var_238]
0x1800a59c2  call    ?_GetInstallControl2@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAA?AUInstallServiceControl@Control@InstallService@Internal@6winrt@@XZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(void)
0x1800a59c7  mov     rdi, rax
0x1800a59ca  lea     rdx, [rsp+298h+sourceString]; sourceString
0x1800a59d2  lea     rcx, [rsp+298h+hstringHeader]; hstringHeader
0x1800a59da  call    ??$?0$0ICE@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0ICE@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[2084])
0x1800a59df  nop
0x1800a59e0  mov     rcx, [rax+18h]
0x1800a59e4  mov     [rsp+298h+var_248], rcx
0x1800a59e9  lea     rdx, [rsp+298h+var_248]
0x1800a59ee  lea     rcx, [rsp+298h+var_228]
0x1800a59f3  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800a59f8  nop
0x1800a59f9  mov     rbx, [rax]
0x1800a59fc  mov     rax, [rsp+298h+string]
0x1800a5a01  mov     [rsp+298h+var_248], rax
0x1800a5a06  lea     rdx, [rsp+298h+var_248]
0x1800a5a0b  lea     rcx, [rsp+298h+var_230]
0x1800a5a10  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800a5a15  mov     r9, rax
0x1800a5a18  mov     rcx, [rdi]
0x1800a5a1b  mov     [rsp+298h+var_218], 0
0x1800a5a26  xorps   xmm0, xmm0
0x1800a5a29  movdqu  [rsp+298h+var_210], xmm0
0x1800a5a32  mov     rdx, [rcx]
0x1800a5a35  mov     rax, [rdx+0B8h]
0x1800a5a3c  mov     r8, rbx
0x1800a5a3f  mov     rdx, [r9]
0x1800a5a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5a47  lea     r8, [rsp+298h+var_218]
0x1800a5a4f  mov     edx, eax
0x1800a5a51  lea     rcx, [rsp+298h+var_248]
0x1800a5a56  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800a5a5b  nop
0x1800a5a5c  lea     rcx, [rsp+298h+var_230]
0x1800a5a61  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800a5a66  nop
0x1800a5a67  lea     rcx, [rsp+298h+var_228]
0x1800a5a6c  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800a5a71  nop
0x1800a5a72  mov     [rsp+298h+var_1E8], 0
0x1800a5a7e  lea     rcx, [rsp+298h+var_238]; void *
0x1800a5a83  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1800a5a88  nop
0x1800a5a89  mov     rcx, [rsp+298h+string]; string
0x1800a5a8e  call    cs:__imp_WindowsDeleteString
0x1800a5a94  xor     eax, eax
0x1800a5a96  jmp     short loc_1800A5B05
0x1800a5a98  mov     eax, dword ptr [rsp+298h+var_248]
0x1800a5a9c  jmp     short loc_1800A5B05
0x1800a5a9e  lea     rcx, [rdi+78h]; SRWLock
0x1800a5aa2  call    cs:__imp_AcquireSRWLockShared
0x1800a5aa8  mov     rbx, [rdi+90h]
0x1800a5aaf  mov     [rsp+298h+var_238], rbx
0x1800a5ab4  test    rbx, rbx
0x1800a5ab7  jz      short loc_1800A5AC9
0x1800a5ab9  mov     rax, [rbx]
0x1800a5abc  mov     rcx, rbx
0x1800a5abf  mov     rax, [rax+8]
0x1800a5ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5ac8  nop
0x1800a5ac9  lea     rcx, [rdi+78h]; SRWLock
0x1800a5acd  call    cs:__imp_ReleaseSRWLockShared
0x1800a5ad3  test    rbx, rbx
0x1800a5ad6  jz      short loc_1800A5AF4
0x1800a5ad8  mov     rax, [rbx]
0x1800a5adb  mov     r8, r14
0x1800a5ade  mov     rdx, r15
0x1800a5ae1  mov     rcx, rbx
0x1800a5ae4  mov     rax, [rax+100h]
0x1800a5aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5af0  mov     ebx, eax
0x1800a5af2  jmp     short loc_1800A5AF9
0x1800a5af4  mov     ebx, 80004005h
0x1800a5af9  lea     rcx, [rsp+298h+var_238]
0x1800a5afe  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800a5b03  mov     eax, ebx
0x1800a5b05  mov     rcx, [rsp+298h+var_38]
0x1800a5b0d  xor     rcx, rsp; StackCookie
0x1800a5b10  call    __security_check_cookie
0x1800a5b15  add     rsp, 270h
0x1800a5b1c  pop     r15
0x1800a5b1e  pop     r14
0x1800a5b20  pop     rdi
0x1800a5b21  pop     rsi
0x1800a5b22  pop     rbx
0x1800a5b23  retn
```
