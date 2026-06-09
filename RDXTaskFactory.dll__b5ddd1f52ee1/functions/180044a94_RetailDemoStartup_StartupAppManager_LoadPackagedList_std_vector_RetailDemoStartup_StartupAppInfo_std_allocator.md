# RetailDemoStartup::StartupAppManager::LoadPackagedList(std::vector<RetailDemoStartup::StartupAppInfo,std::allocator<RetailDemoStartup::StartupAppInfo>> &)

- ea: `0x180044a94`
- end: `0x18004511b`
- name: `?LoadPackagedList@StartupAppManager@RetailDemoStartup@@AEAAJAEAV?$vector@UStartupAppInfo@RetailDemoStartup@@V?$allocator@UStartupAppInfo@RetailDemoStartup@@@std@@@std@@@Z`
- size: `1671`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800453ac`

## callees

- `0x180003390`
- `0x180008bbc`
- `0x18000aa7c`
- `0x18000db70`
- `0x18001bf68`
- `0x180036a40`
- `0x180042f28`
- `0x1800433f0`
- `0x1800438dc`
- `0x180043c9c`
- `0x1800440ec`
- `0x180044a94`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180044f7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180044fa3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180044fcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180044f7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180044fa3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180044fcd`

## string_xrefs

- `0x180044b08`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\startupappmanager.cpp`
- `0x180044b67`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\startupappmanager.cpp`
- `0x180044c05`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\startupappmanager.cpp`
- `0x180044c97`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\startupappmanager.cpp`
- `0x180044d0c`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\startupappmanager.cpp`
- `0x180044d8f`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\startupappmanager.cpp`
- `0x180044e1a`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\startupappmanager.cpp`
- `0x180044eae`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\startupappmanager.cpp`
- `0x1800450e3`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\startupappmanager.cpp`
- `0x180044ff6`: `UWP-StartupTask`
- `0x180044ad5`: `Windows.ApplicationModel.Internal.StartupTaskInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall RetailDemoStartup::StartupAppManager::LoadPackagedList(__int64 a1, __int64 a2)
{
  __int64 v3; // r8
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int v16; // ebx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  int (__fastcall ***v21)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v22; // rdx
  __int64 v23; // r8
  int v24; // ebx
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // r8
  unsigned int v28; // ebx
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rdx
  __int64 v34; // r8
  unsigned int v35; // r14d
  __m128i si128; // xmm6
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, _QWORD, int *); // rbx
  int v39; // eax
  unsigned int v40; // ebx
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // rax
  int v50; // eax
  unsigned int v51; // ebx
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // rax
  int v61; // eax
  unsigned int v62; // ebx
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 v65; // rdx
  __int64 v66; // r8
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 v69; // rdx
  __int64 v70; // r8
  __int64 v71; // rax
  int v72; // eax
  unsigned int v73; // ebx
  __int64 v74; // rdx
  __int64 v75; // r8
  __int64 v76; // rdx
  __int64 v77; // r8
  __int64 v78; // rdx
  __int64 v79; // r8
  __int64 v80; // rdx
  __int64 v81; // r8
  int v82; // eax
  unsigned int v83; // ebx
  __int64 v84; // rdx
  __int64 v85; // r8
  __int64 v86; // rdx
  __int64 v87; // r8
  __int64 v88; // rdx
  __int64 v89; // r8
  __int64 v90; // rdx
  __int64 v91; // r8
  PCWSTR StringRawBuffer; // rax
  __int64 v93; // r8
  PCWSTR v94; // rax
  __int64 v95; // r8
  PCWSTR v96; // rax
  __int64 v97; // r8
  __int64 v98; // rcx
  __int64 v99; // rdx
  __int64 v100; // rdx
  __int64 v101; // r8
  __int64 v102; // rdx
  __int64 v103; // r8
  __int64 v104; // rdx
  __int64 v105; // r8
  __int64 v106; // rdx
  __int64 v107; // r8
  __int64 v108; // rdx
  __int64 v109; // r8
  __int64 v110; // rdx
  __int64 v111; // r8
  int v112[2]; // [rsp+20h] [rbp-148h] BYREF
  __int64 v113; // [rsp+28h] [rbp-140h] BYREF
  int (__fastcall ***v114)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-138h] BYREF
  __int64 v115; // [rsp+38h] [rbp-130h] BYREF
  HSTRING string; // [rsp+40h] [rbp-128h] BYREF
  HSTRING v117; // [rsp+48h] [rbp-120h] BYREF
  HSTRING v118; // [rsp+50h] [rbp-118h] BYREF
  unsigned int v119; // [rsp+58h] [rbp-110h] BYREF
  int v120; // [rsp+5Ch] [rbp-10Ch] BYREF
  _OWORD v121[2]; // [rsp+60h] [rbp-108h] BYREF
  _OWORD v122[2]; // [rsp+80h] [rbp-E8h] BYREF
  _OWORD v123[2]; // [rsp+A0h] [rbp-C8h] BYREF
  _OWORD v124[2]; // [rsp+C0h] [rbp-A8h] BYREF
  bool v125; // [rsp+E0h] [rbp-88h]
  char v126; // [rsp+E1h] [rbp-87h]
  __int64 v127; // [rsp+E4h] [rbp-84h]
  HSTRING_HEADER v128; // [rsp+F0h] [rbp-78h] BYREF
  __int64 v129; // [rsp+108h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v115 = 0;
  v129 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v128,
    L"Windows.ApplicationModel.Internal.StartupTaskInternal",
    0x36u,
    0x35u);
  v4 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Internal::IStartupTaskInternalStatics>>(
         v129,
         (__int64)&v115,
         v3);
  v7 = v4;
  if ( v4 >= 0 )
  {
    v114 = 0;
    v11 = v115;
    v12 = *(__int64 (__fastcall **)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v115 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v114, v5, v6);
    v13 = v12(v11, &v114);
    v16 = v13;
    if ( v13 >= 0 )
    {
      v113 = 0;
      v21 = v114;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v113, v14, v15);
      v24 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *>>(
              v21,
              v22,
              v23);
      if ( v24 < 0
        || (v24 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v21)[8])(
                    v21,
                    &v113),
            v24 < 0) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14E,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\startupappmanager.cpp",
          (const char *)(unsigned int)v24,
          v112[0]);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v113, v106, v107);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v114, v108, v109);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v115, v110, v111);
        return (unsigned int)v24;
      }
      else
      {
        v119 = 0;
        v25 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v113 + 56LL))(v113, &v119);
        v28 = v25;
        if ( v25 >= 0 )
        {
          v35 = 0;
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          while ( v35 < v119 )
          {
            *(_QWORD *)v112 = 0;
            v37 = v113;
            v38 = *(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v113 + 48LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v112, v26, v27);
            v39 = v38(v37, v35, v112);
            v40 = v39;
            if ( v39 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x155,
                (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\startupappmanager.cpp",
                (const char *)(unsigned int)v39,
                v112[0]);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v112, v41, v42);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v113, v43, v44);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v114, v45, v46);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v115, v47, v48);
              return v40;
            }
            string = 0;
            v49 = **(_QWORD **)v112;
            string = 0;
            v50 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(v49 + 64))(*(_QWORD *)v112, &string);
            v51 = v50;
            if ( v50 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x158,
                (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\startupappmanager.cpp",
                (const char *)(unsigned int)v50,
                v112[0]);
              Windows::Internal::String::~String((Windows::Internal::String *)&string);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v112, v52, v53);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v113, v54, v55);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v114, v56, v57);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v115, v58, v59);
              return v51;
            }
            v117 = 0;
            v60 = **(_QWORD **)v112;
            v117 = 0;
            v61 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(v60 + 144))(*(_QWORD *)v112, &v117);
            v62 = v61;
            if ( v61 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x15B,
                (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\startupappmanager.cpp",
                (const char *)(unsigned int)v61,
                v112[0]);
              Windows::Internal::String::~String((Windows::Internal::String *)&v117);
              Windows::Internal::String::~String((Windows::Internal::String *)&string);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v112, v63, v64);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v113, v65, v66);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v114, v67, v68);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v115, v69, v70);
              return v62;
            }
            v118 = 0;
            v71 = **(_QWORD **)v112;
            v118 = 0;
            v72 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(v71 + 112))(*(_QWORD *)v112, &v118);
            v73 = v72;
            if ( v72 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x15E,
                (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\startupappmanager.cpp",
                (const char *)(unsigned int)v72,
                v112[0]);
              Windows::Internal::String::~String((Windows::Internal::String *)&v118);
              Windows::Internal::String::~String((Windows::Internal::String *)&v117);
              Windows::Internal::String::~String((Windows::Internal::String *)&string);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v112, v74, v75);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v113, v76, v77);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v114, v78, v79);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v115, v80, v81);
              return v73;
            }
            v120 = 0;
            v82 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v112 + 128LL))(*(_QWORD *)v112, &v120);
            v83 = v82;
            if ( v82 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x161,
                (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\startupappmanager.cpp",
                (const char *)(unsigned int)v82,
                v112[0]);
              Windows::Internal::String::~String((Windows::Internal::String *)&v118);
              Windows::Internal::String::~String((Windows::Internal::String *)&v117);
              Windows::Internal::String::~String((Windows::Internal::String *)&string);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v112, v84, v85);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v113, v86, v87);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v114, v88, v89);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v115, v90, v91);
              return v83;
            }
            v121[0] = 0;
            v121[1] = si128;
            LOWORD(v121[0]) = 0;
            v122[0] = 0;
            v122[1] = si128;
            LOWORD(v122[0]) = 0;
            v123[0] = 0;
            v123[1] = si128;
            LOWORD(v123[0]) = 0;
            v124[0] = 0;
            v124[1] = si128;
            LOWORD(v124[0]) = 0;
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            v93 = -1;
            do
              ++v93;
            while ( StringRawBuffer[v93] );
            std::wstring::_Assign<unsigned short>(v121, StringRawBuffer, v93);
            v94 = WindowsGetStringRawBuffer(v117, 0);
            v95 = -1;
            do
              ++v95;
            while ( v94[v95] );
            std::wstring::_Assign<unsigned short>(v122, v94, v95);
            v96 = WindowsGetStringRawBuffer(v118, 0);
            v97 = -1;
            do
              ++v97;
            while ( v96[v97] );
            std::wstring::_Assign<unsigned short>(v123, v96, v97);
            std::wstring::_Assign<unsigned short>(v124, L"UWP-StartupTask", 15);
            v125 = v120 == 2;
            v126 = 1;
            v127 = 0;
            v99 = *(_QWORD *)(a2 + 8);
            if ( v99 == *(_QWORD *)(a2 + 16) )
            {
              std::vector<RetailDemoStartup::StartupAppInfo>::_Emplace_reallocate<RetailDemoStartup::StartupAppInfo const &>(
                a2,
                v99,
                v121);
            }
            else
            {
              std::_Default_allocator_traits<std::allocator<RetailDemoStartup::StartupAppInfo>>::construct<RetailDemoStartup::StartupAppInfo,RetailDemoStartup::StartupAppInfo const &>(
                v98,
                v99,
                v121);
              *(_QWORD *)(a2 + 8) += 144LL;
            }
            RetailDemoStartup::StartupAppInfo::~StartupAppInfo((RetailDemoStartup::StartupAppInfo *)v121);
            Windows::Internal::String::~String((Windows::Internal::String *)&v118);
            Windows::Internal::String::~String((Windows::Internal::String *)&v117);
            Windows::Internal::String::~String((Windows::Internal::String *)&string);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v112, v100, v101);
            ++v35;
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v113, v26, v27);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v114, v102, v103);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v115, v104, v105);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x151,
            (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\startupappmanager.cpp",
            (const char *)(unsigned int)v25,
            v112[0]);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v113, v29, v30);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v114, v31, v32);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v115, v33, v34);
          return v28;
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14B,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\startupappmanager.cpp",
        (const char *)(unsigned int)v13,
        v112[0]);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v114, v17, v18);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v115, v19, v20);
      return v16;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x148,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\startupappmanager.cpp",
      (const char *)(unsigned int)v4,
      v112[0]);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v115, v8, v9);
    return v7;
  }
}

```

## disassembly

```asm
0x180044a94  mov     r11, rsp
0x180044a97  push    rbx
0x180044a98  push    rsi
0x180044a99  push    rdi
0x180044a9a  push    r12
0x180044a9c  push    r14
0x180044a9e  push    r15
0x180044aa0  sub     rsp, 138h
0x180044aa7  movaps  xmmword ptr [r11-48h], xmm6
0x180044aac  mov     rax, cs:__security_cookie
0x180044ab3  xor     rax, rsp
0x180044ab6  mov     [rsp+168h+var_58], rax
0x180044abe  mov     rsi, rdx
0x180044ac1  xor     r15d, r15d
0x180044ac4  mov     [rsp+168h+var_130], r15
0x180044ac9  mov     [r11-60h], r15
0x180044acd  lea     r9d, [r15+35h]; unsigned int
0x180044ad1  lea     r8d, [r15+36h]; unsigned int
0x180044ad5  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Internal_StartupTaskInternal@@3QBGB; "Windows.ApplicationModel.Internal.Start"...
0x180044adc  lea     rcx, [r11-78h]; hstringHeader
0x180044ae0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180044ae5  lea     rdx, [rsp+168h+var_130]
0x180044aea  mov     rcx, [rsp+168h+var_60]
0x180044af2  call    ??$GetActivationFactory@V?$ComPtr@UIStartupTaskInternalStatics@Internal@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIStartupTaskInternalStatics@Internal@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Internal::IStartupTaskInternalStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Internal::IStartupTaskInternalStatics>>)
0x180044af7  mov     ebx, eax
0x180044af9  test    eax, eax
0x180044afb  jns     short loc_180044B2B
0x180044afd  mov     rcx, [rsp+168h]; this
0x180044b05  mov     r9d, eax; char *
0x180044b08  lea     r8, aPcshellShellRe_16; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180044b0f  mov     edx, 148h; void *
0x180044b14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044b19  nop
0x180044b1a  lea     rcx, [rsp+168h+var_130]
0x180044b1f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044b24  mov     eax, ebx
0x180044b26  jmp     loc_1800450AF
0x180044b2b  mov     [rsp+168h+var_138], r15
0x180044b30  mov     rdi, [rsp+168h+var_130]
0x180044b35  mov     rax, [rdi]
0x180044b38  mov     rbx, [rax+30h]
0x180044b3c  lea     rcx, [rsp+168h+var_138]
0x180044b41  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044b46  lea     rdx, [rsp+168h+var_138]
0x180044b4b  mov     rcx, rdi
0x180044b4e  mov     rax, rbx
0x180044b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b56  mov     ebx, eax
0x180044b58  test    eax, eax
0x180044b5a  jns     short loc_180044B95
0x180044b5c  mov     rcx, [rsp+168h]; this
0x180044b64  mov     r9d, eax; char *
0x180044b67  lea     r8, aPcshellShellRe_16; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180044b6e  mov     edx, 14Bh; void *
0x180044b73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044b78  nop
0x180044b79  lea     rcx, [rsp+168h+var_138]
0x180044b7e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044b83  nop
0x180044b84  lea     rcx, [rsp+168h+var_130]
0x180044b89  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044b8e  mov     eax, ebx
0x180044b90  jmp     loc_1800450AF
0x180044b95  mov     [rsp+168h+var_140], r15
0x180044b9a  mov     rdi, [rsp+168h+var_138]
0x180044b9f  lea     rcx, [rsp+168h+var_140]
0x180044ba4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044ba9  mov     rcx, rdi
0x180044bac  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *> *,tagCOWAIT_FLAGS,void *)
0x180044bb1  mov     ebx, eax
0x180044bb3  test    eax, eax
0x180044bb5  js      loc_1800450D8
0x180044bbb  mov     rax, [rdi]
0x180044bbe  lea     rdx, [rsp+168h+var_140]
0x180044bc3  mov     rcx, rdi
0x180044bc6  mov     rax, [rax+40h]
0x180044bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044bcf  mov     ebx, eax
0x180044bd1  test    eax, eax
0x180044bd3  js      loc_1800450D8
0x180044bd9  mov     [rsp+168h+var_110], r15d
0x180044bde  mov     rcx, [rsp+168h+var_140]
0x180044be3  mov     rax, [rcx]
0x180044be6  lea     rdx, [rsp+168h+var_110]
0x180044beb  mov     rax, [rax+38h]
0x180044bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044bf4  mov     ebx, eax
0x180044bf6  test    eax, eax
0x180044bf8  jns     short loc_180044C3E
0x180044bfa  mov     rcx, [rsp+168h]; this
0x180044c02  mov     r9d, eax; char *
0x180044c05  lea     r8, aPcshellShellRe_16; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180044c0c  mov     edx, 151h; void *
0x180044c11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044c16  nop
0x180044c17  lea     rcx, [rsp+168h+var_140]
0x180044c1c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044c21  nop
0x180044c22  lea     rcx, [rsp+168h+var_138]
0x180044c27  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044c2c  nop
0x180044c2d  lea     rcx, [rsp+168h+var_130]
0x180044c32  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044c37  mov     eax, ebx
0x180044c39  jmp     loc_1800450AF
0x180044c3e  mov     r14d, r15d
0x180044c41  or      r12, 0FFFFFFFFFFFFFFFFh
0x180044c45  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180044c4d  cmp     r14d, [rsp+168h+var_110]
0x180044c52  jnb     loc_18004508C
0x180044c58  mov     qword ptr [rsp+168h+var_148], r15; int
0x180044c5d  mov     rdi, [rsp+168h+var_140]
0x180044c62  mov     rax, [rdi]
0x180044c65  mov     rbx, [rax+30h]
0x180044c69  lea     rcx, [rsp+168h+var_148]
0x180044c6e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044c73  lea     r8, [rsp+168h+var_148]
0x180044c78  mov     edx, r14d
0x180044c7b  mov     rcx, rdi
0x180044c7e  mov     rax, rbx
0x180044c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c86  mov     ebx, eax
0x180044c88  test    eax, eax
0x180044c8a  jns     short loc_180044CDB
0x180044c8c  mov     rcx, [rsp+168h]; this
0x180044c94  mov     r9d, eax; char *
0x180044c97  lea     r8, aPcshellShellRe_16; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180044c9e  mov     edx, 155h; void *
0x180044ca3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044ca8  nop
0x180044ca9  lea     rcx, [rsp+168h+var_148]
0x180044cae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044cb3  nop
0x180044cb4  lea     rcx, [rsp+168h+var_140]
0x180044cb9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044cbe  nop
0x180044cbf  lea     rcx, [rsp+168h+var_138]
0x180044cc4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044cc9  nop
0x180044cca  lea     rcx, [rsp+168h+var_130]
0x180044ccf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044cd4  mov     eax, ebx
0x180044cd6  jmp     loc_1800450AF
0x180044cdb  mov     [rsp+168h+string], r15
0x180044ce0  mov     rcx, qword ptr [rsp+168h+var_148]
0x180044ce5  mov     rax, [rcx]
0x180044ce8  mov     [rsp+168h+string], r15
0x180044ced  lea     rdx, [rsp+168h+string]
0x180044cf2  mov     rax, [rax+40h]
0x180044cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044cfb  mov     ebx, eax
0x180044cfd  test    eax, eax
0x180044cff  jns     short loc_180044D5B
0x180044d01  mov     rcx, [rsp+168h]; this
0x180044d09  mov     r9d, eax; char *
0x180044d0c  lea     r8, aPcshellShellRe_16; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180044d13  mov     edx, 158h; void *
0x180044d18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044d1d  nop
0x180044d1e  lea     rcx, [rsp+168h+string]; this
0x180044d23  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180044d28  nop
0x180044d29  lea     rcx, [rsp+168h+var_148]
0x180044d2e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044d33  nop
0x180044d34  lea     rcx, [rsp+168h+var_140]
0x180044d39  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044d3e  nop
0x180044d3f  lea     rcx, [rsp+168h+var_138]
0x180044d44  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044d49  nop
0x180044d4a  lea     rcx, [rsp+168h+var_130]
0x180044d4f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044d54  mov     eax, ebx
0x180044d56  jmp     loc_1800450AF
0x180044d5b  mov     [rsp+168h+var_120], r15
0x180044d60  mov     rcx, qword ptr [rsp+168h+var_148]
0x180044d65  mov     rax, [rcx]
0x180044d68  mov     [rsp+168h+var_120], r15
0x180044d6d  lea     rdx, [rsp+168h+var_120]
0x180044d72  mov     rax, [rax+90h]
0x180044d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044d7e  mov     ebx, eax
0x180044d80  test    eax, eax
0x180044d82  jns     short loc_180044DE9
0x180044d84  mov     rcx, [rsp+168h]; this
0x180044d8c  mov     r9d, eax; char *
0x180044d8f  lea     r8, aPcshellShellRe_16; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180044d96  mov     edx, 15Bh; void *
0x180044d9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044da0  nop
0x180044da1  lea     rcx, [rsp+168h+var_120]; this
0x180044da6  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180044dab  nop
0x180044dac  lea     rcx, [rsp+168h+string]; this
0x180044db1  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180044db6  nop
0x180044db7  lea     rcx, [rsp+168h+var_148]
0x180044dbc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044dc1  nop
0x180044dc2  lea     rcx, [rsp+168h+var_140]
0x180044dc7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044dcc  nop
0x180044dcd  lea     rcx, [rsp+168h+var_138]
0x180044dd2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044dd7  nop
0x180044dd8  lea     rcx, [rsp+168h+var_130]
0x180044ddd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044de2  mov     eax, ebx
0x180044de4  jmp     loc_1800450AF
0x180044de9  mov     [rsp+168h+var_118], r15
0x180044dee  mov     rcx, qword ptr [rsp+168h+var_148]
0x180044df3  mov     rax, [rcx]
0x180044df6  mov     [rsp+168h+var_118], r15
0x180044dfb  lea     rdx, [rsp+168h+var_118]
0x180044e00  mov     rax, [rax+70h]
0x180044e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e09  mov     ebx, eax
0x180044e0b  test    eax, eax
0x180044e0d  jns     short loc_180044E7F
0x180044e0f  mov     rcx, [rsp+168h]; this
0x180044e17  mov     r9d, eax; char *
0x180044e1a  lea     r8, aPcshellShellRe_16; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180044e21  mov     edx, 15Eh; void *
0x180044e26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044e2b  nop
0x180044e2c  lea     rcx, [rsp+168h+var_118]; this
0x180044e31  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180044e36  nop
0x180044e37  lea     rcx, [rsp+168h+var_120]; this
0x180044e3c  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180044e41  nop
0x180044e42  lea     rcx, [rsp+168h+string]; this
0x180044e47  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180044e4c  nop
0x180044e4d  lea     rcx, [rsp+168h+var_148]
0x180044e52  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044e57  nop
0x180044e58  lea     rcx, [rsp+168h+var_140]
0x180044e5d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044e62  nop
0x180044e63  lea     rcx, [rsp+168h+var_138]
0x180044e68  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044e6d  nop
0x180044e6e  lea     rcx, [rsp+168h+var_130]
0x180044e73  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044e78  mov     eax, ebx
0x180044e7a  jmp     loc_1800450AF
0x180044e7f  mov     [rsp+168h+var_10C], r15d
0x180044e84  mov     rcx, qword ptr [rsp+168h+var_148]
0x180044e89  mov     rax, [rcx]
0x180044e8c  lea     rdx, [rsp+168h+var_10C]
0x180044e91  mov     rax, [rax+80h]
0x180044e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e9d  mov     ebx, eax
0x180044e9f  test    eax, eax
0x180044ea1  jns     short loc_180044F13
0x180044ea3  mov     rcx, [rsp+168h]; this
0x180044eab  mov     r9d, eax; char *
0x180044eae  lea     r8, aPcshellShellRe_16; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180044eb5  mov     edx, 161h; void *
0x180044eba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044ebf  nop
0x180044ec0  lea     rcx, [rsp+168h+var_118]; this
0x180044ec5  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180044eca  nop
0x180044ecb  lea     rcx, [rsp+168h+var_120]; this
0x180044ed0  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180044ed5  nop
0x180044ed6  lea     rcx, [rsp+168h+string]; this
0x180044edb  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180044ee0  nop
0x180044ee1  lea     rcx, [rsp+168h+var_148]
0x180044ee6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044eeb  nop
0x180044eec  lea     rcx, [rsp+168h+var_140]
0x180044ef1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044ef6  nop
0x180044ef7  lea     rcx, [rsp+168h+var_138]
0x180044efc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044f01  nop
0x180044f02  lea     rcx, [rsp+168h+var_130]
0x180044f07  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044f0c  mov     eax, ebx
0x180044f0e  jmp     loc_1800450AF
0x180044f13  xorps   xmm0, xmm0
0x180044f16  movups  [rsp+168h+var_108], xmm0
0x180044f1b  movdqa  [rsp+168h+var_F8], xmm6
0x180044f21  mov     word ptr [rsp+168h+var_108], r15w
0x180044f27  movups  [rsp+168h+var_E8], xmm0
0x180044f2f  movdqa  [rsp+168h+var_D8], xmm6
0x180044f38  mov     word ptr [rsp+168h+var_E8], r15w
0x180044f41  movups  [rsp+168h+var_C8], xmm0
0x180044f49  movdqa  [rsp+168h+var_B8], xmm6
0x180044f52  mov     word ptr [rsp+168h+var_C8], r15w
0x180044f5b  movups  [rsp+168h+var_A8], xmm0
0x180044f63  movdqa  [rsp+168h+var_98], xmm6
0x180044f6c  mov     word ptr [rsp+168h+var_A8], r15w
0x180044f75  xor     edx, edx; length
0x180044f77  mov     rcx, [rsp+168h+string]; string
  ... truncated ...
```
