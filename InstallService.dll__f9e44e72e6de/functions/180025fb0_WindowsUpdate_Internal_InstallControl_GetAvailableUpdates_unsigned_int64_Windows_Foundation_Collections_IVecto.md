# WindowsUpdate::Internal::InstallControl::GetAvailableUpdates(unsigned __int64,Windows::Foundation::Collections::IVectorView<HSTRING__ *> *,uchar,uchar,uchar,HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IVectorView<HSTRING__ *> * *)

- ea: `0x180025fb0`
- end: `0x1800264a9`
- name: `?GetAvailableUpdates@InstallControl@Internal@WindowsUpdate@@UEAAJ_KPEAU?$IVectorView@PEAUHSTRING__@@@Collections@Foundation@Windows@@EEEPEAUHSTRING__@@2PEAPEAU4567@@Z`
- size: `1273`
- prototype: `__int64 __fastcall(int, int, int, int, char, char, __int64, HSTRING, __int64)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x18001bf24`
- `0x18001c414`
- `0x18001df54`
- `0x18001f784`
- `0x180020960`
- `0x1800225e4`
- `0x180022f00`
- `0x180024fe0`
- `0x180025fb0`
- `0x1800265e0`
- `0x18002c310`
- `0x18002ec2c`
- `0x18002f214`
- `0x1800309b0`
- `0x180032318`
- `0x180073110`
- `0x180076628`
- `0x180215010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x18002617e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x18002617e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800260c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800260e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800260ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800263dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800260c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800260e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800260ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800263dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026167`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026336`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002637e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026167`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026336`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002637e`

## string_xrefs

- `0x1800260a3`: `onecoreuap\enduser\winstore\installservice\lib\installcontrol.cpp`
- `0x18002612d`: `onecoreuap\enduser\winstore\installservice\lib\installcontrol.cpp`
- `0x180026276`: `onecoreuap\enduser\winstore\installservice\lib\installcontrol.cpp`
- `0x180026369`: `onecoreuap\enduser\winstore\installservice\lib\installcontrol.cpp`
- `0x1800263b1`: `onecoreuap\enduser\winstore\installservice\lib\installcontrol.cpp`
- `0x180026393`: `Found update for categoryId = %s`
- `0x18002635c`: `WindowsUpdate::Internal::InstallControl::GetAvailableUpdates`
- `0x1800263a4`: `WindowsUpdate::Internal::InstallControl::GetAvailableUpdates`
- `0x18002634b`: `Scan for Updates (not applicability) returned Update that is not in list of scanned for Apps: categoryId = %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall WindowsUpdate::Internal::InstallControl::GetAvailableUpdates(
        __int64 a1,
        __int64 a2,
        HSTRING a3,
        char a4,
        char a5,
        char a6,
        __int64 a7,
        HSTRING a8,
        _QWORD *a9)
{
  int i; // eax
  HSTRING *v12; // rax
  int v13; // eax
  __int64 v14; // rcx
  int v15; // eax
  PCWSTR StringRawBuffer; // rax
  unsigned int ClientHandleOrNullIfLocalSystem; // eax
  unsigned int v18; // ebx
  int v19; // eax
  unsigned int j; // esi
  __int64 v21; // rdi
  int (__fastcall *v22)(__int64, _QWORD, HSTRING *); // rbx
  HSTRING v23; // r8
  HSTRING v24; // rcx
  Microsoft::WRL::Wrappers::HString *v25; // rdi
  Microsoft::WRL::Wrappers::Details **v26; // rbx
  PCWSTR v27; // rax
  PCWSTR v28; // rax
  int v30; // [rsp+20h] [rbp-1F8h]
  int v31; // [rsp+20h] [rbp-1F8h]
  HSTRING string; // [rsp+50h] [rbp-1C8h] BYREF
  int v33; // [rsp+58h] [rbp-1C0h] BYREF
  HSTRING v34; // [rsp+60h] [rbp-1B8h] BYREF
  __int64 v35; // [rsp+68h] [rbp-1B0h] BYREF
  Microsoft::WRL::Wrappers::HString *v36[2]; // [rsp+70h] [rbp-1A8h] BYREF
  __int64 v37; // [rsp+80h] [rbp-198h]
  __int64 v38; // [rsp+88h] [rbp-190h] BYREF
  HSTRING v39; // [rsp+90h] [rbp-188h] BYREF
  int v40; // [rsp+98h] [rbp-180h]
  HSTRING v41; // [rsp+A0h] [rbp-178h]
  _BYTE v42[8]; // [rsp+A8h] [rbp-170h] BYREF
  int v43; // [rsp+B0h] [rbp-168h]
  HSTRING v44; // [rsp+B8h] [rbp-160h]
  _BYTE v45[144]; // [rsp+C0h] [rbp-158h] BYREF
  _BYTE v46[144]; // [rsp+150h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  *a9 = 0;
  CallerContext::Create((__int64)v45, a2);
  std::vector<ChainedInstallServiceWork::SubTaskCheckpointData>::vector<ChainedInstallServiceWork::SubTaskCheckpointData>(v36);
  string = a3;
  v39 = a3;
  v40 = 0;
  v41 = 0;
  wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::Notifications::ToastNotification *>,wil::err_exception_policy>::end(
    &string,
    v42);
  for ( i = v40; i != v43; i = ++v40 )
  {
    v12 = (HSTRING *)wil::vector_range<Windows::Foundation::Collections::IVectorView<HSTRING__ *>,wil::err_exception_policy>::vector_iterator::operator*(&v39);
    string = 0;
    v34 = *v12;
    v13 = Microsoft::WRL::Wrappers::HString::Set(&string, &v34);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1F1,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installcontrol.cpp",
        (const char *)(unsigned int)v13,
        v30);
    std::vector<Microsoft::WRL::Wrappers::HString>::push_back(v36, &string);
    WindowsDeleteString(string);
  }
  WindowsDeleteString(v44);
  v44 = 0;
  WindowsDeleteString(v41);
  v35 = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
  v15 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(
          v14,
          &v35);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F6,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installcontrol.cpp",
      (const char *)(unsigned int)v15,
      v30);
  StringRawBuffer = WindowsGetStringRawBuffer(a8, 0);
  _o_wcstombs(v46, StringRawBuffer, 129);
  ClientHandleOrNullIfLocalSystem = (unsigned int)CallerContext::GetClientHandleOrNullIfLocalSystem((CallerContext *)v45);
  ScanForUpdates(
    (unsigned int)&v38,
    ClientHandleOrNullIfLocalSystem,
    (unsigned int)v36,
    (a5 != 0 ? 0x10 : 0) | (a4 != 0 ? 6 : 2) | (a6 != 0 ? 0x800 : 0),
    a7,
    (__int64)v46);
  if ( v38 )
  {
    v33 = 0;
    v19 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v38 + 80LL))(v38, &v33);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x202,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installcontrol.cpp",
        (const char *)(unsigned int)v19,
        v31);
    for ( j = 0; (int)j < v33; ++j )
    {
      string = 0;
      v21 = v38;
      v22 = *(int (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v38 + 56LL);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&string);
      if ( v22(v21, j, &string) >= 0 )
      {
        AppIdFromUpdateOrEmpty(&v34, string);
        v24 = v34;
        if ( v34 )
        {
          if ( a4 )
            goto LABEL_25;
          v25 = v36[1];
          v26 = (Microsoft::WRL::Wrappers::Details **)v36[0];
          if ( v36[0] == v36[1] )
            goto LABEL_24;
          while ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(*v26, v24, v23) )
          {
            if ( ++v26 == (Microsoft::WRL::Wrappers::Details **)v25 )
              break;
            v24 = v34;
          }
          v24 = v34;
          if ( v26 == (Microsoft::WRL::Wrappers::Details **)v36[1] )
          {
LABEL_24:
            v27 = WindowsGetStringRawBuffer(v24, 0);
            LogMessage(
              3u,
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\installcontrol.cpp",
              0x21Bu,
              "WindowsUpdate::Internal::InstallControl::GetAvailableUpdates",
              -1,
              L"Scan for Updates (not applicability) returned Update that is not in list of scanned for Apps: categoryId = %s",
              0,
              0,
              v27);
          }
          else
          {
LABEL_25:
            v28 = WindowsGetStringRawBuffer(v24, 0);
            LogMessage(
              3u,
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\installcontrol.cpp",
              0x216u,
              "WindowsUpdate::Internal::InstallControl::GetAvailableUpdates",
              -1,
              L"Found update for categoryId = %s",
              0,
              0,
              v28);
            (*(void (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v35 + 104LL))(v35, v34);
          }
          v24 = v34;
        }
        WindowsDeleteString(v24);
        v34 = 0;
      }
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&string);
    }
    v18 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v35 + 64LL))(v35, a9);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v38);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
    if ( v36[0] )
    {
      std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HString>>(v36[0]);
      std::_Deallocate<16>(v36[0], (v37 - (unsigned __int64)v36[0]) & 0xFFFFFFFFFFFFFFF8uLL);
      *(_OWORD *)v36 = 0;
      v37 = 0;
    }
  }
  else
  {
    v18 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v35 + 64LL))(v35, a9);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v38);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
    if ( v36[0] )
    {
      std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HString>>(v36[0]);
      std::_Deallocate<16>(v36[0], (v37 - (unsigned __int64)v36[0]) & 0xFFFFFFFFFFFFFFF8uLL);
      *(_OWORD *)v36 = 0;
      v37 = 0;
    }
  }
  CallerContext::~CallerContext((CallerContext *)v45);
  return v18;
}

```

## disassembly

```asm
0x180025fb0  mov     [rsp+arg_0], rbx
0x180025fb5  mov     [rsp+arg_10], rsi
0x180025fba  push    rdi
0x180025fbb  push    r12
0x180025fbd  push    r13
0x180025fbf  push    r14
0x180025fc1  push    r15
0x180025fc3  sub     rsp, 1F0h
0x180025fca  mov     rax, cs:__security_cookie
0x180025fd1  xor     rax, rsp
0x180025fd4  mov     [rsp+218h+var_38], rax
0x180025fdc  mov     r13b, r9b
0x180025fdf  mov     rbx, r8
0x180025fe2  mov     r15b, [rsp+218h+arg_20]
0x180025fea  mov     sil, [rsp+218h+arg_28]
0x180025ff2  mov     rdi, [rsp+218h+arg_30]
0x180025ffa  mov     r12, [rsp+218h+arg_38]
0x180026002  mov     r14, [rsp+218h+arg_40]
0x18002600a  mov     qword ptr [r14], 0
0x180026011  lea     rcx, [rsp+218h+var_158]
0x180026019  call    ?Create@CallerContext@@SA?AV1@_K@Z; CallerContext::Create(unsigned __int64)
0x18002601e  nop
0x18002601f  lea     rcx, [rsp+218h+var_1A8]; void *
0x180026024  call    ??0?$vector@USubTaskCheckpointData@ChainedInstallServiceWork@@V?$allocator@USubTaskCheckpointData@ChainedInstallServiceWork@@@std@@@std@@QEAA@XZ; std::vector<ChainedInstallServiceWork::SubTaskCheckpointData>::vector<ChainedInstallServiceWork::SubTaskCheckpointData>(void)
0x180026029  nop
0x18002602a  mov     [rsp+218h+string], rbx
0x18002602f  mov     [rsp+218h+var_188], rbx
0x180026037  xor     ebx, ebx
0x180026039  mov     [rsp+218h+var_180], ebx
0x180026040  mov     [rsp+218h+var_178], rbx
0x180026048  lea     rdx, [rsp+218h+var_170]
0x180026050  lea     rcx, [rsp+218h+string]
0x180026055  call    ?end@?$vector_range@U?$IVectorView@PEAVToastNotification@Notifications@UI@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::Notifications::ToastNotification *>,wil::err_exception_policy>::end(void)
0x18002605a  nop
0x18002605b  mov     eax, [rsp+218h+var_180]
0x180026062  cmp     eax, [rsp+218h+var_168]
0x180026069  jz      short loc_1800260E1
0x18002606b  lea     rcx, [rsp+218h+var_188]
0x180026073  call    ??Dvector_iterator@?$vector_range@U?$IVectorView@PEAUHSTRING__@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBVHStringWithRelease@?$MapToSmartType@PEAUHSTRING__@@X@details@2@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<HSTRING__ *>,wil::err_exception_policy>::vector_iterator::operator*(void)
0x180026078  mov     [rsp+218h+string], rbx
0x18002607d  mov     rax, [rax]
0x180026080  mov     [rsp+218h+var_1B8], rax
0x180026085  lea     rdx, [rsp+218h+var_1B8]; HSTRING *
0x18002608a  lea     rcx, [rsp+218h+string]; newString
0x18002608f  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180026094  mov     rcx, [rsp+218h]; this
0x18002609c  test    eax, eax
0x18002609e  jns     short loc_1800260B4
0x1800260a0  mov     r9d, eax; char *
0x1800260a3  lea     r8, aOnecoreuapEndu_49; "onecoreuap\\enduser\\winstore\\installs"...
0x1800260aa  mov     edx, 1F1h; void *
0x1800260af  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800260b4  lea     rdx, [rsp+218h+string]
0x1800260b9  lea     rcx, [rsp+218h+var_1A8]
0x1800260be  call    ?push_back@?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@QEAAX$$QEAVHString@Wrappers@WRL@Microsoft@@@Z; std::vector<Microsoft::WRL::Wrappers::HString>::push_back(Microsoft::WRL::Wrappers::HString &&)
0x1800260c3  nop
0x1800260c4  mov     rcx, [rsp+218h+string]; string
0x1800260c9  call    cs:__imp_WindowsDeleteString
0x1800260cf  mov     eax, [rsp+218h+var_180]
0x1800260d6  inc     eax
0x1800260d8  mov     [rsp+218h+var_180], eax
0x1800260df  jmp     short loc_180026062
0x1800260e1  mov     rcx, [rsp+218h+var_160]; string
0x1800260e9  call    cs:__imp_WindowsDeleteString
0x1800260ef  mov     [rsp+218h+var_160], rbx
0x1800260f7  mov     rcx, [rsp+218h+var_178]; string
0x1800260ff  call    cs:__imp_WindowsDeleteString
0x180026105  mov     [rsp+218h+var_1B0], rbx
0x18002610a  lea     rcx, [rsp+218h+var_1B0]
0x18002610f  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180026114  lea     rdx, [rsp+218h+var_1B0]
0x180026119  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)
0x18002611e  mov     rcx, [rsp+218h]; this
0x180026126  test    eax, eax
0x180026128  jns     short loc_18002613E
0x18002612a  mov     r9d, eax; char *
0x18002612d  lea     r8, aOnecoreuapEndu_49; "onecoreuap\\enduser\\winstore\\installs"...
0x180026134  mov     edx, 1F6h; void *
0x180026139  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002613e  neg     sil
0x180026141  sbb     ebx, ebx
0x180026143  and     ebx, 800h
0x180026149  mov     al, r13b
0x18002614c  neg     al
0x18002614e  sbb     edx, edx
0x180026150  and     edx, 4
0x180026153  add     edx, 2
0x180026156  or      ebx, edx
0x180026158  neg     r15b
0x18002615b  sbb     eax, eax
0x18002615d  and     eax, 10h
0x180026160  or      ebx, eax
0x180026162  xor     edx, edx; length
0x180026164  mov     rcx, r12; string
0x180026167  call    cs:__imp_WindowsGetStringRawBuffer
0x18002616d  mov     rdx, rax
0x180026170  mov     r8d, 81h
0x180026176  lea     rcx, [rsp+218h+var_C8]
0x18002617e  call    cs:__imp__o_wcstombs
0x180026184  lea     rcx, [rsp+218h+var_158]; this
0x18002618c  call    ?GetClientHandleOrNullIfLocalSystem@CallerContext@@QEAAPEAXXZ; CallerContext::GetClientHandleOrNullIfLocalSystem(void)
0x180026191  lea     rcx, [rsp+218h+var_C8]
0x180026199  mov     [rsp+218h+var_1F0], rcx
0x18002619e  mov     qword ptr [rsp+218h+var_1F8], rdi; int
0x1800261a3  mov     r9d, ebx
0x1800261a6  lea     r8, [rsp+218h+var_1A8]
0x1800261ab  mov     rdx, rax
0x1800261ae  lea     rcx, [rsp+218h+var_190]
0x1800261b6  call    ?ScanForUpdates@@YA?AV?$ComPtr@UIUpdateCollection@@@WRL@Microsoft@@PEAXAEAV?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@KPEAUHSTRING__@@PEBD@Z; ScanForUpdates(void *,std::vector<Microsoft::WRL::Wrappers::HString> &,ulong,HSTRING__ *,char const *)
0x1800261bb  nop
0x1800261bc  mov     rcx, [rsp+218h+var_190]
0x1800261c4  xor     r15d, r15d
0x1800261c7  test    rcx, rcx
0x1800261ca  jnz     loc_180026251
0x1800261d0  mov     rcx, [rsp+218h+var_1B0]
0x1800261d5  mov     rax, [rcx]
0x1800261d8  mov     rdx, r14
0x1800261db  mov     rax, [rax+40h]
0x1800261df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261e4  mov     ebx, eax
0x1800261e6  lea     rcx, [rsp+218h+var_190]
0x1800261ee  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800261f3  nop
0x1800261f4  lea     rcx, [rsp+218h+var_1B0]
0x1800261f9  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800261fe  nop
0x1800261ff  mov     rcx, [rsp+218h+var_1A8]; this
0x180026204  test    rcx, rcx
0x180026207  jz      short loc_18002623D
0x180026209  mov     rdx, [rsp+218h+var_1A8+8]
0x18002620e  call    ??$_Destroy_range@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@YAXPEAVHString@Wrappers@WRL@Microsoft@@QEAV1234@AEAV?$allocator@VHString@Wrappers@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HString>>(Microsoft::WRL::Wrappers::HString *,Microsoft::WRL::Wrappers::HString * const,std::allocator<Microsoft::WRL::Wrappers::HString> &)
0x180026213  mov     rcx, [rsp+218h+var_1A8]
0x180026218  mov     rdx, [rsp+218h+var_198]
0x180026220  sub     rdx, rcx
0x180026223  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180026227  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002622c  xorps   xmm0, xmm0
0x18002622f  movdqu  xmmword ptr [rsp+218h+var_1A8], xmm0
0x180026235  mov     [rsp+218h+var_198], r15
0x18002623d  lea     rcx, [rsp+218h+var_158]; this
0x180026245  call    ??1CallerContext@@QEAA@XZ; CallerContext::~CallerContext(void)
0x18002624a  mov     eax, ebx
0x18002624c  jmp     loc_18002647B
0x180026251  mov     [rsp+218h+var_1C0], r15d
0x180026256  mov     rax, [rcx]
0x180026259  lea     rdx, [rsp+218h+var_1C0]
0x18002625e  mov     rax, [rax+50h]
0x180026262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026267  mov     rcx, [rsp+218h]; this
0x18002626f  test    eax, eax
0x180026271  jns     short loc_180026287
0x180026273  mov     r9d, eax; char *
0x180026276  lea     r8, aOnecoreuapEndu_49; "onecoreuap\\enduser\\winstore\\installs"...
0x18002627d  mov     edx, 202h; void *
0x180026282  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026287  mov     esi, r15d
0x18002628a  or      r12d, 0FFFFFFFFh
0x18002628e  cmp     esi, [rsp+218h+var_1C0]
0x180026292  jge     loc_1800263F9
0x180026298  mov     [rsp+218h+string], r15
0x18002629d  mov     rdi, [rsp+218h+var_190]
0x1800262a5  mov     rax, [rdi]
0x1800262a8  mov     rbx, [rax+38h]
0x1800262ac  lea     rcx, [rsp+218h+string]
0x1800262b1  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800262b6  lea     r8, [rsp+218h+string]
0x1800262bb  mov     edx, esi
0x1800262bd  mov     rcx, rdi
0x1800262c0  mov     rax, rbx
0x1800262c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262c8  test    eax, eax
0x1800262ca  js      loc_1800263E8
0x1800262d0  mov     rdx, [rsp+218h+string]
0x1800262d5  lea     rcx, [rsp+218h+var_1B8]
0x1800262da  call    ?AppIdFromUpdateOrEmpty@@YA?AVHString@Wrappers@WRL@Microsoft@@PEAUIUpdate@@@Z; AppIdFromUpdateOrEmpty(IUpdate *)
0x1800262df  nop
0x1800262e0  mov     rcx, [rsp+218h+var_1B8]; string
0x1800262e5  test    rcx, rcx
0x1800262e8  jz      loc_1800263DD
0x1800262ee  test    r13b, r13b
0x1800262f1  jnz     loc_18002637C
0x1800262f7  mov     rdi, [rsp+218h+var_1A8+8]
0x1800262fc  mov     rbx, [rsp+218h+var_1A8]
0x180026301  cmp     rbx, rdi
0x180026304  jz      short loc_180026334
0x180026306  mov     rdx, rcx; HSTRING
0x180026309  mov     rcx, [rbx]; this
0x18002630c  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180026311  test    eax, eax
0x180026313  jz      short loc_180026325
0x180026315  add     rbx, 8
0x180026319  cmp     rbx, rdi
0x18002631c  jz      short loc_180026325
0x18002631e  mov     rcx, [rsp+218h+var_1B8]
0x180026323  jmp     short loc_180026306
0x180026325  mov     rdi, [rsp+218h+var_1A8+8]
0x18002632a  mov     rcx, [rsp+218h+var_1B8]; string
0x18002632f  cmp     rbx, rdi
0x180026332  jnz     short loc_18002637C
0x180026334  xor     edx, edx; length
0x180026336  call    cs:__imp_WindowsGetStringRawBuffer
0x18002633c  mov     [rsp+218h+var_1D8], rax
0x180026341  mov     [rsp+218h+var_1E0], r15; unsigned __int16 *
0x180026346  mov     [rsp+218h+var_1E8], r15; char *
0x18002634b  lea     rax, aScanForUpdates; "Scan for Updates (not applicability) re"...
0x180026352  mov     [rsp+218h+var_1F0], rax; unsigned __int16 *
0x180026357  mov     [rsp+218h+var_1F8], r12d; int
0x18002635c  lea     r9, aWindowsupdateI_5; "WindowsUpdate::Internal::InstallControl"...
0x180026363  mov     r8d, 21Bh; unsigned int
0x180026369  lea     rdx, aOnecoreuapEndu_49; "onecoreuap\\enduser\\winstore\\installs"...
0x180026370  mov     ecx, 3; unsigned int
0x180026375  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18002637a  jmp     short loc_1800263D8
0x18002637c  xor     edx, edx; length
0x18002637e  call    cs:__imp_WindowsGetStringRawBuffer
0x180026384  mov     [rsp+218h+var_1D8], rax
0x180026389  mov     [rsp+218h+var_1E0], r15; unsigned __int16 *
0x18002638e  mov     [rsp+218h+var_1E8], r15; char *
0x180026393  lea     rax, aFoundUpdateFor; "Found update for categoryId = %s"
0x18002639a  mov     [rsp+218h+var_1F0], rax; unsigned __int16 *
0x18002639f  mov     [rsp+218h+var_1F8], r12d; int
0x1800263a4  lea     r9, aWindowsupdateI_5; "WindowsUpdate::Internal::InstallControl"...
0x1800263ab  mov     r8d, 216h; unsigned int
0x1800263b1  lea     rdx, aOnecoreuapEndu_49; "onecoreuap\\enduser\\winstore\\installs"...
0x1800263b8  mov     ecx, 3; unsigned int
0x1800263bd  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800263c2  mov     rcx, [rsp+218h+var_1B0]
0x1800263c7  mov     rax, [rcx]
0x1800263ca  mov     rdx, [rsp+218h+var_1B8]
0x1800263cf  mov     rax, [rax+68h]
0x1800263d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263d8  mov     rcx, [rsp+218h+var_1B8]; string
0x1800263dd  call    cs:__imp_WindowsDeleteString
0x1800263e3  mov     [rsp+218h+var_1B8], r15
0x1800263e8  lea     rcx, [rsp+218h+string]
0x1800263ed  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800263f2  inc     esi
0x1800263f4  jmp     loc_18002628E
0x1800263f9  mov     rcx, [rsp+218h+var_1B0]
0x1800263fe  mov     rax, [rcx]
0x180026401  mov     rdx, r14
0x180026404  mov     rax, [rax+40h]
0x180026408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002640d  mov     ebx, eax
0x18002640f  lea     rcx, [rsp+218h+var_190]
0x180026417  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18002641c  nop
0x18002641d  lea     rcx, [rsp+218h+var_1B0]
0x180026422  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180026427  nop
0x180026428  mov     rcx, [rsp+218h+var_1A8]; this
0x18002642d  test    rcx, rcx
0x180026430  jz      short loc_180026466
0x180026432  mov     rdx, [rsp+218h+var_1A8+8]
0x180026437  call    ??$_Destroy_range@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@YAXPEAVHString@Wrappers@WRL@Microsoft@@QEAV1234@AEAV?$allocator@VHString@Wrappers@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HString>>(Microsoft::WRL::Wrappers::HString *,Microsoft::WRL::Wrappers::HString * const,std::allocator<Microsoft::WRL::Wrappers::HString> &)
0x18002643c  mov     rcx, [rsp+218h+var_1A8]
0x180026441  mov     rdx, [rsp+218h+var_198]
0x180026449  sub     rdx, rcx
0x18002644c  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180026450  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180026455  xorps   xmm0, xmm0
0x180026458  movdqu  xmmword ptr [rsp+218h+var_1A8], xmm0
0x18002645e  mov     [rsp+218h+var_198], r15
0x180026466  lea     rcx, [rsp+218h+var_158]; this
0x18002646e  call    ??1CallerContext@@QEAA@XZ; CallerContext::~CallerContext(void)
0x180026473  mov     eax, ebx
0x180026475  jmp     short loc_18002647B
0x180026477  mov     eax, [rsp+218h+var_1C0]
0x18002647b  mov     rcx, [rsp+218h+var_38]
0x180026483  xor     rcx, rsp; StackCookie
0x180026486  call    __security_check_cookie
0x18002648b  lea     r11, [rsp+218h+var_28]
0x180026493  mov     rbx, [r11+30h]
0x180026497  mov     rsi, [r11+40h]
0x18002649b  mov     rsp, r11
0x18002649e  pop     r15
0x1800264a0  pop     r14
0x1800264a2  pop     r13
0x1800264a4  pop     r12
0x1800264a6  pop     rdi
0x1800264a7  retn
```
