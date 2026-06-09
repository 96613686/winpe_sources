# RetailDemoStartup::StartupAppManager::ManagePackagedItem(RetailDemoStartup::StartupAppInfo const &,bool)

- ea: `0x180045828`
- end: `0x180045bc2`
- name: `?ManagePackagedItem@StartupAppManager@RetailDemoStartup@@AEAAJAEBUStartupAppInfo@2@_N@Z`
- size: `922`
- prototype: `__int64 __fastcall(RetailDemoStartup::StartupAppManager *__hidden this, const struct RetailDemoStartup::StartupAppInfo *, bool)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180045ce4`

## callees

- `0x180003390`
- `0x180008bbc`
- `0x18000aa7c`
- `0x18000db70`
- `0x18001092c`
- `0x18001bf68`
- `0x18002666c`
- `0x180042f28`
- `0x180043580`
- `0x180043710`
- `0x18004449c`
- `0x180045828`
- `0x180050010`

## string_xrefs

- `0x180045891`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\startupappmanager.cpp`
- `0x1800458f6`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\startupappmanager.cpp`
- `0x1800459a2`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\startupappmanager.cpp`
- `0x180045a5d`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\startupappmanager.cpp`
- `0x180045b13`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\startupappmanager.cpp`
- `0x180045b5f`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\startupappmanager.cpp`
- `0x1800458c5`: `Windows.ApplicationModel.Internal.StartupTaskInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall RetailDemoStartup::StartupAppManager::ManagePackagedItem(
        RetailDemoStartup::StartupAppManager *this,
        const struct RetailDemoStartup::StartupAppInfo *a2,
        unsigned __int8 a3)
{
  int v3; // r12d
  char *v6; // r14
  __int64 v7; // rax
  int IsRegistered; // eax
  unsigned int v9; // ebx
  __int64 v11; // r8
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int v15; // ebx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rsi
  __int64 (__fastcall *v19)(__int64, _QWORD, __int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rdi
  __int64 v20; // rbx
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  unsigned int v25; // ebx
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rdx
  __int64 v29; // r8
  int (__fastcall ***v30)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v31; // rdx
  __int64 v32; // r8
  int v33; // ebx
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rdi
  __int64 (__fastcall *v37)(__int64, _QWORD, _QWORD); // rbx
  int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // r8
  unsigned int v41; // ebx
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // rdx
  __int64 v49; // r8
  int (__fastcall ***v50)(_QWORD, GUID *, __int64 *); // rdi
  int v51; // ebx
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // rdx
  __int64 v61; // r8
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // rdx
  __int64 v71; // r8
  __int64 v72; // rdx
  __int64 v73; // r8
  int v74; // [rsp+20h] [rbp-B8h]
  int (__fastcall ***v75)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-A8h] BYREF
  __int64 v76; // [rsp+38h] [rbp-A0h] BYREF
  int v77; // [rsp+40h] [rbp-98h] BYREF
  __int64 v78; // [rsp+48h] [rbp-90h] BYREF
  int (__fastcall ***v79)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-88h] BYREF
  __int64 v80; // [rsp+58h] [rbp-80h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-78h] BYREF
  __int64 v82; // [rsp+78h] [rbp-60h]
  _BYTE v83[32]; // [rsp+80h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v3 = a3;
  v6 = (char *)a2 + 64;
  if ( this != (const struct RetailDemoStartup::StartupAppInfo *)((char *)a2 + 64) )
  {
    v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)a2 + 64);
    std::wstring::_Assign<unsigned short>(this, v7, *((_QWORD *)v6 + 2));
  }
  IsRegistered = RetailDemoStartup::StartupAppManager::EnsurePackageIsRegistered(this);
  v9 = IsRegistered;
  if ( IsRegistered >= 0 )
  {
    v76 = 0;
    v82 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.ApplicationModel.Internal.StartupTaskInternal",
      0x36u,
      0x35u);
    v12 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Internal::IStartupTaskInternalStatics>>(
            v82,
            (__int64)&v76,
            v11);
    v15 = v12;
    if ( v12 >= 0 )
    {
      v75 = 0;
      v18 = v76;
      v19 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v76 + 80LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75, v13, v14);
      v80 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)a2 + 32);
      v20 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v80) + 24);
      v80 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6);
      v21 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v83, &v80);
      v22 = v19(v18, *(_QWORD *)(v21 + 24), v20, &v75);
      v25 = v22;
      if ( v22 >= 0 )
      {
        v78 = 0;
        v30 = v75;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v78, v23, v24);
        v33 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Internal::StartupTaskInternal *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Internal::StartupTaskInternal *>>(
                v30,
                v31,
                v32);
        if ( v33 < 0
          || (v33 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v30)[8])(
                      v30,
                      &v78),
              v33 < 0) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1A0,
            (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\startupappmanager.cpp",
            (const char *)(unsigned int)v33,
            v74);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v78, v68, v69);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75, v70, v71);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v76, v72, v73);
          return (unsigned int)v33;
        }
        else
        {
          v79 = 0;
          v36 = v78;
          v37 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v78 + 48LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79, v34, v35);
          v38 = v37(v36, (unsigned int)(2 * v3), &v79);
          v41 = v38;
          if ( v38 >= 0 )
          {
            v77 = 0;
            v50 = v79;
            v51 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::StartupTaskState>,Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::StartupTaskState>>(
                    v79,
                    v39,
                    v40);
            if ( v51 < 0
              || (v51 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), int *))(*v50)[8])(
                          v50,
                          &v77),
                  v51 < 0) )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1A6,
                (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\startupappmanager.cpp",
                (const char *)(unsigned int)v51,
                v74);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79, v60, v61);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v78, v62, v63);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75, v64, v65);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v76, v66, v67);
              return (unsigned int)v51;
            }
            else
            {
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79, v52, v53);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v78, v54, v55);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75, v56, v57);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v76, v58, v59);
              return 0;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1A3,
              (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\startupappmanager.cpp",
              (const char *)(unsigned int)v38,
              v74);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79, v42, v43);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v78, v44, v45);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75, v46, v47);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v76, v48, v49);
            return v41;
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x19D,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\startupappmanager.cpp",
          (const char *)(unsigned int)v22,
          v74);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75, v26, v27);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v76, v28, v29);
        return v25;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x197,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\startupappmanager.cpp",
        (const char *)(unsigned int)v12,
        v74);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v76, v16, v17);
      return v15;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x192,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\startupappmanager.cpp",
      (const char *)(unsigned int)IsRegistered,
      v74);
    return v9;
  }
}

```

## disassembly

```asm
0x180045828  mov     [rsp+arg_10], rbx
0x18004582d  push    rsi
0x18004582e  push    rdi
0x18004582f  push    r12
0x180045831  push    r14
0x180045833  push    r15
0x180045835  sub     rsp, 0B0h
0x18004583c  mov     rax, cs:__security_cookie
0x180045843  xor     rax, rsp
0x180045846  mov     [rsp+0D8h+var_38], rax
0x18004584e  movzx   r12d, r8b
0x180045852  mov     r15, rdx
0x180045855  mov     rbx, rcx
0x180045858  lea     r14, [rdx+40h]
0x18004585c  cmp     rcx, r14
0x18004585f  jz      short loc_180045878
0x180045861  mov     rcx, r14
0x180045864  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180045869  mov     r8, [r14+10h]
0x18004586d  mov     rdx, rax
0x180045870  mov     rcx, rbx
0x180045873  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180045878  mov     rcx, rbx; this
0x18004587b  call    ?EnsurePackageIsRegistered@StartupAppManager@RetailDemoStartup@@AEAAJXZ; RetailDemoStartup::StartupAppManager::EnsurePackageIsRegistered(void)
0x180045880  mov     ebx, eax
0x180045882  test    eax, eax
0x180045884  jns     short loc_1800458A9
0x180045886  mov     rcx, [rsp+0D8h]; this
0x18004588e  mov     r9d, eax; char *
0x180045891  lea     r8, aPcshellShellRe_16; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180045898  mov     edx, 192h; void *
0x18004589d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800458a2  mov     eax, ebx
0x1800458a4  jmp     loc_180045B99
0x1800458a9  mov     [rsp+0D8h+var_A0], 0
0x1800458b2  mov     [rsp+0D8h+var_60], 0
0x1800458bb  mov     r9d, 35h ; '5'; unsigned int
0x1800458c1  lea     r8d, [r9+1]; unsigned int
0x1800458c5  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Internal_StartupTaskInternal@@3QBGB; "Windows.ApplicationModel.Internal.Start"...
0x1800458cc  lea     rcx, [rsp+0D8h+hstringHeader]; hstringHeader
0x1800458d1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800458d6  lea     rdx, [rsp+0D8h+var_A0]
0x1800458db  mov     rcx, [rsp+0D8h+var_60]
0x1800458e0  call    ??$GetActivationFactory@V?$ComPtr@UIStartupTaskInternalStatics@Internal@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIStartupTaskInternalStatics@Internal@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Internal::IStartupTaskInternalStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Internal::IStartupTaskInternalStatics>>)
0x1800458e5  mov     ebx, eax
0x1800458e7  test    eax, eax
0x1800458e9  jns     short loc_180045919
0x1800458eb  mov     rcx, [rsp+0D8h]; this
0x1800458f3  mov     r9d, eax; char *
0x1800458f6  lea     r8, aPcshellShellRe_16; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800458fd  mov     edx, 197h; void *
0x180045902  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045907  nop
0x180045908  lea     rcx, [rsp+0D8h+var_A0]
0x18004590d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045912  mov     eax, ebx
0x180045914  jmp     loc_180045B99
0x180045919  mov     [rsp+0D8h+var_A8], 0
0x180045922  mov     rsi, [rsp+0D8h+var_A0]
0x180045927  mov     rax, [rsi]
0x18004592a  mov     rdi, [rax+50h]
0x18004592e  lea     rcx, [rsp+0D8h+var_A8]
0x180045933  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045938  lea     rcx, [r15+20h]
0x18004593c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180045941  mov     [rsp+0D8h+var_80], rax
0x180045946  lea     rdx, [rsp+0D8h+var_80]
0x18004594b  lea     rcx, [rsp+0D8h+hstringHeader]
0x180045950  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180045955  nop
0x180045956  mov     rbx, [rax+18h]
0x18004595a  mov     rcx, r14
0x18004595d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180045962  mov     [rsp+0D8h+var_80], rax
0x180045967  lea     rdx, [rsp+0D8h+var_80]
0x18004596c  lea     rcx, [rsp+0D8h+var_58]
0x180045974  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180045979  nop
0x18004597a  lea     r9, [rsp+0D8h+var_A8]
0x18004597f  mov     r8, rbx
0x180045982  mov     rdx, [rax+18h]
0x180045986  mov     rcx, rsi
0x180045989  mov     rax, rdi
0x18004598c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045991  mov     ebx, eax
0x180045993  test    eax, eax
0x180045995  jns     short loc_1800459D0
0x180045997  mov     rcx, [rsp+0D8h]; this
0x18004599f  mov     r9d, eax; char *
0x1800459a2  lea     r8, aPcshellShellRe_16; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800459a9  mov     edx, 19Dh; void *
0x1800459ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800459b3  nop
0x1800459b4  lea     rcx, [rsp+0D8h+var_A8]
0x1800459b9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800459be  nop
0x1800459bf  lea     rcx, [rsp+0D8h+var_A0]
0x1800459c4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800459c9  mov     eax, ebx
0x1800459cb  jmp     loc_180045B99
0x1800459d0  mov     [rsp+0D8h+var_90], 0
0x1800459d9  mov     rdi, [rsp+0D8h+var_A8]
0x1800459de  lea     rcx, [rsp+0D8h+var_90]
0x1800459e3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800459e8  mov     rcx, rdi
0x1800459eb  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Internal::StartupTaskInternal *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Internal::StartupTaskInternal *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Internal::StartupTaskInternal *> *,tagCOWAIT_FLAGS,void *)
0x1800459f0  mov     ebx, eax
0x1800459f2  test    eax, eax
0x1800459f4  js      loc_180045B54
0x1800459fa  mov     rax, [rdi]
0x1800459fd  lea     rdx, [rsp+0D8h+var_90]
0x180045a02  mov     rcx, rdi
0x180045a05  mov     rax, [rax+40h]
0x180045a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a0e  mov     ebx, eax
0x180045a10  test    eax, eax
0x180045a12  js      loc_180045B54
0x180045a18  mov     [rsp+0D8h+var_88], 0
0x180045a21  mov     rdi, [rsp+0D8h+var_90]
0x180045a26  mov     rax, [rdi]
0x180045a29  mov     rbx, [rax+30h]
0x180045a2d  lea     rcx, [rsp+0D8h+var_88]
0x180045a32  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045a37  mov     edx, r12d
0x180045a3a  add     edx, edx
0x180045a3c  lea     r8, [rsp+0D8h+var_88]
0x180045a41  mov     rcx, rdi
0x180045a44  mov     rax, rbx
0x180045a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a4c  mov     ebx, eax
0x180045a4e  test    eax, eax
0x180045a50  jns     short loc_180045AA1
0x180045a52  mov     rcx, [rsp+0D8h]; this
0x180045a5a  mov     r9d, eax; char *
0x180045a5d  lea     r8, aPcshellShellRe_16; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180045a64  mov     edx, 1A3h; void *
0x180045a69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045a6e  nop
0x180045a6f  lea     rcx, [rsp+0D8h+var_88]
0x180045a74  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045a79  nop
0x180045a7a  lea     rcx, [rsp+0D8h+var_90]
0x180045a7f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045a84  nop
0x180045a85  lea     rcx, [rsp+0D8h+var_A8]
0x180045a8a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045a8f  nop
0x180045a90  lea     rcx, [rsp+0D8h+var_A0]
0x180045a95  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045a9a  mov     eax, ebx
0x180045a9c  jmp     loc_180045B99
0x180045aa1  mov     [rsp+0D8h+var_98], 0
0x180045aa9  mov     rdi, [rsp+0D8h+var_88]
0x180045aae  mov     rcx, rdi
0x180045ab1  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4StartupTaskState@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4StartupTaskState@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4StartupTaskState@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::StartupTaskState>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::StartupTaskState>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::StartupTaskState> *,tagCOWAIT_FLAGS,void *)
0x180045ab6  mov     ebx, eax
0x180045ab8  test    eax, eax
0x180045aba  js      short loc_180045B08
0x180045abc  mov     rax, [rdi]
0x180045abf  lea     rdx, [rsp+0D8h+var_98]
0x180045ac4  mov     rcx, rdi
0x180045ac7  mov     rax, [rax+40h]
0x180045acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045ad0  mov     ebx, eax
0x180045ad2  test    eax, eax
0x180045ad4  js      short loc_180045B08
0x180045ad6  lea     rcx, [rsp+0D8h+var_88]
0x180045adb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045ae0  nop
0x180045ae1  lea     rcx, [rsp+0D8h+var_90]
0x180045ae6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045aeb  nop
0x180045aec  lea     rcx, [rsp+0D8h+var_A8]
0x180045af1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045af6  nop
0x180045af7  lea     rcx, [rsp+0D8h+var_A0]
0x180045afc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045b01  xor     eax, eax
0x180045b03  jmp     loc_180045B99
0x180045b08  mov     rcx, [rsp+0D8h]; this
0x180045b10  mov     r9d, ebx; char *
0x180045b13  lea     r8, aPcshellShellRe_16; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180045b1a  mov     edx, 1A6h; void *
0x180045b1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045b24  nop
0x180045b25  lea     rcx, [rsp+0D8h+var_88]
0x180045b2a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045b2f  nop
0x180045b30  lea     rcx, [rsp+0D8h+var_90]
0x180045b35  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045b3a  nop
0x180045b3b  lea     rcx, [rsp+0D8h+var_A8]
0x180045b40  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045b45  nop
0x180045b46  lea     rcx, [rsp+0D8h+var_A0]
0x180045b4b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045b50  mov     eax, ebx
0x180045b52  jmp     short loc_180045B99
0x180045b54  mov     rcx, [rsp+0D8h]; this
0x180045b5c  mov     r9d, ebx; char *
0x180045b5f  lea     r8, aPcshellShellRe_16; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180045b66  mov     edx, 1A0h; void *
0x180045b6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045b70  nop
0x180045b71  lea     rcx, [rsp+0D8h+var_90]
0x180045b76  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045b7b  nop
0x180045b7c  lea     rcx, [rsp+0D8h+var_A8]
0x180045b81  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045b86  nop
0x180045b87  lea     rcx, [rsp+0D8h+var_A0]
0x180045b8c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045b91  mov     eax, ebx
0x180045b93  jmp     short loc_180045B99
0x180045b95  mov     eax, [rsp+0D8h+var_98]
0x180045b99  mov     rcx, [rsp+0D8h+var_38]
0x180045ba1  xor     rcx, rsp; StackCookie
0x180045ba4  call    __security_check_cookie
0x180045ba9  mov     rbx, [rsp+0D8h+arg_10]
0x180045bb1  add     rsp, 0B0h
0x180045bb8  pop     r15
0x180045bba  pop     r14
0x180045bbc  pop     r12
0x180045bbe  pop     rdi
0x180045bbf  pop     rsi
0x180045bc0  retn
```
