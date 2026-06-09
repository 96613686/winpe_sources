# CWorkflowAppSession::RequestForegroundUI(IInspectable *)

- ea: `0x18001faa0`
- end: `0x18001fe30`
- name: `?RequestForegroundUI@CWorkflowAppSession@@UEAAJPEAUIInspectable@@@Z`
- size: `912`
- prototype: `__int64 __fastcall(CWorkflowAppSession *__hidden this, struct IInspectable *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001614`
- `0x180003ca0`
- `0x18000dfd0`
- `0x180010b0c`
- `0x180012820`
- `0x1800166a8`
- `0x18001a910`
- `0x18001c3e8`
- `0x18001d570`
- `0x18001faa0`
- `0x1800205b8`
- `0x180023000`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001fc92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001fc92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fc2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fc80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fde6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fc2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fc80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fde6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001fd10`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001fd10`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001fd74`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001fd74`

## string_xrefs

- `0x18001fb01`: `onecoreuap\printscan\print\workflow\broker\lib\workflowappsession.cpp`
- `0x18001fbcc`: `onecoreuap\printscan\print\workflow\broker\lib\workflowappsession.cpp`
- `0x18001fc50`: `onecoreuap\printscan\print\workflow\broker\lib\workflowappsession.cpp`
- `0x18001fd32`: `onecoreuap\printscan\print\workflow\broker\lib\workflowappsession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CWorkflowAppSession::RequestForegroundUI(CWorkflowAppSession *this, struct IInspectable *a2)
{
  char *v4; // r14
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  int WorkflowAppPropertiesFromDevPropStore; // eax
  __int64 v13; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v15; // r8
  __int64 v16; // r9
  HANDLE v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  int dwCreationFlags; // [rsp+20h] [rbp-E0h]
  int dwCreationFlagsa; // [rsp+20h] [rbp-E0h]
  _BYTE v24[8]; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  int v26; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE v28; // [rsp+50h] [rbp-B0h] BYREF
  __int128 Parameter; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v30; // [rsp+68h] [rbp-98h]
  HANDLE Handles[2]; // [rsp+78h] [rbp-88h] BYREF
  _OWORD v32[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v33; // [rsp+A8h] [rbp-58h] BYREF
  __m128i si128; // [rsp+B8h] [rbp-48h]
  _QWORD v35[42]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  v24[0] = 0;
  v4 = (char *)this - 24;
  v5 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3), v24);
  if ( (v5 & 0x80000000) == 0 )
  {
    if ( !v24[0] )
    {
      v5 = -2147023436;
      v6 = 948;
      goto LABEL_3;
    }
    wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
      v35,
      "RequestForegroundUI");
    v35[0] = &PrintWorkFlowTelemetry::RequestForegroundUI::`vftable';
    PrintWorkFlowTelemetry::RequestForegroundUI::StartActivity(
      (PrintWorkFlowTelemetry::RequestForegroundUI *)v35,
      *((_DWORD *)this + 8));
    if ( (unsigned int)dword_180083038 > 5 )
    {
      v26 = *((_DWORD *)this + 8);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180083038,
        (__int64)&unk_1800718B8,
        v7,
        v8,
        (__int64)&v26);
    }
    Parameter = 0;
    v30 = 0;
    v27 = 0;
    Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(&v27);
    v9 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           &GUID_c79b63d0_f8ec_4ceb_953a_c8876157dd33,
           &v27);
    v5 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3BF,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowappsession.cpp",
        (const char *)(unsigned int)v9,
        dwCreationFlags);
LABEL_27:
      Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(&v27);
      PrintWorkFlowTelemetry::RequestForegroundUI::~RequestForegroundUI((PrintWorkFlowTelemetry::RequestForegroundUI *)v35);
      return v5;
    }
    *(_QWORD *)&Parameter = v27;
    *((_QWORD *)&Parameter + 1) = v4;
    string = 0;
    v33 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v33) = 0;
    v32[0] = 0;
    v32[1] = si128;
    LOWORD(v32[0]) = 0;
    v10 = *((_QWORD *)this + 3);
    v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v10 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    WorkflowAppPropertiesFromDevPropStore = v11(v10, &string);
    v5 = WorkflowAppPropertiesFromDevPropStore;
    if ( WorkflowAppPropertiesFromDevPropStore >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      WorkflowAppPropertiesFromDevPropStore = GetWorkflowAppPropertiesFromDevPropStore(StringRawBuffer, v32, &v33);
      v5 = WorkflowAppPropertiesFromDevPropStore;
      if ( WorkflowAppPropertiesFromDevPropStore >= 0 )
      {
        *((_QWORD *)&v30 + 1) = &v33;
        *(_QWORD *)&v30 = v32;
        if ( (unsigned int)dword_180083038 > 5 )
        {
          v26 = *((_DWORD *)this + 8);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_180083038,
            (__int64)&unk_180071848,
            v15,
            v16,
            (__int64)&v26);
        }
        v17 = CreateThread(0, 0, CWorkflowAppSession::LaunchUiFromSTAThread, &Parameter, 0, 0);
        v28 = v17;
        if ( (((unsigned __int64)v17 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
        {
          Handles[0] = v17;
          Handles[1] = *((HANDLE *)this + 5);
          if ( !WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF) )
          {
            if ( (unsigned int)dword_180083038 > 5 )
            {
              v26 = *((_DWORD *)this + 8);
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                (__int64)&dword_180083038,
                (__int64)byte_1800717DD,
                v19,
                v20,
                (__int64)&v26);
            }
            wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v35);
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v28);
            std::wstring::_Tidy_deallocate(v32);
            std::wstring::_Tidy_deallocate(&v33);
            WindowsDeleteString(string);
            v5 = 0;
            goto LABEL_26;
          }
          v5 = -2147467259;
          v18 = 992;
        }
        else
        {
          v5 = -2147024882;
          v18 = 978;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowappsession.cpp",
          (const char *)v5,
          dwCreationFlagsa);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v28);
LABEL_13:
        std::wstring::_Tidy_deallocate(v32);
        std::wstring::_Tidy_deallocate(&v33);
        WindowsDeleteString(string);
LABEL_26:
        string = 0;
        goto LABEL_27;
      }
      v13 = 966;
    }
    else
    {
      v13 = 965;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowappsession.cpp",
      (const char *)(unsigned int)WorkflowAppPropertiesFromDevPropStore,
      dwCreationFlags);
    goto LABEL_13;
  }
  v6 = 946;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowappsession.cpp",
    (const char *)v5,
    dwCreationFlags);
  return v5;
}

```

## disassembly

```asm
0x18001faa0  mov     [rsp-8+arg_10], rbx
0x18001faa5  push    rbp
0x18001faa6  push    rsi
0x18001faa7  push    rdi
0x18001faa8  push    r14
0x18001faaa  push    r15
0x18001faac  lea     rbp, [rsp-130h]
0x18001fab4  sub     rsp, 230h
0x18001fabb  mov     rax, cs:__security_cookie
0x18001fac2  xor     rax, rsp
0x18001fac5  mov     [rbp+150h+var_30], rax
0x18001facc  mov     rdi, rdx
0x18001facf  mov     rsi, rcx
0x18001fad2  xor     r15d, r15d
0x18001fad5  mov     [rsp+250h+var_220], r15b
0x18001fada  lea     r14, [rcx-18h]
0x18001fade  mov     rcx, [r14+30h]
0x18001fae2  mov     rax, [rcx]
0x18001fae5  lea     rdx, [rsp+250h+var_220]
0x18001faea  mov     rax, [rax+110h]
0x18001faf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001faf6  mov     ebx, eax
0x18001faf8  test    eax, eax
0x18001fafa  jns     short loc_18001FB1C
0x18001fafc  mov     edx, 3B2h; void *
0x18001fb01  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\workflow"...
0x18001fb08  mov     r9d, ebx; char *
0x18001fb0b  mov     rcx, [rbp+158h]; this
0x18001fb12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fb17  jmp     loc_18001FE08
0x18001fb1c  cmp     [rsp+250h+var_220], r15b
0x18001fb21  jnz     short loc_18001FB2F
0x18001fb23  mov     ebx, 800705B4h
0x18001fb28  mov     edx, 3B4h
0x18001fb2d  jmp     short loc_18001FB01
0x18001fb2f  lea     rdx, aRequestforegro; "RequestForegroundUI"
0x18001fb36  lea     rcx, [rbp+150h+var_180]
0x18001fb3a  call    ??0?$ActivityBase@VPrintWorkFlowLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001fb3f  lea     rax, ??_7RequestForegroundUI@PrintWorkFlowTelemetry@@6B@; const PrintWorkFlowTelemetry::RequestForegroundUI::`vftable'
0x18001fb46  mov     [rbp+150h+var_180], rax
0x18001fb4a  mov     edx, [rsi+20h]; unsigned int
0x18001fb4d  lea     rcx, [rbp+150h+var_180]; this
0x18001fb51  call    ?StartActivity@RequestForegroundUI@PrintWorkFlowTelemetry@@QEAAXK@Z; PrintWorkFlowTelemetry::RequestForegroundUI::StartActivity(ulong)
0x18001fb56  nop
0x18001fb57  mov     eax, cs:dword_180083038
0x18001fb5d  cmp     eax, 5
0x18001fb60  jbe     short loc_18001FB86
0x18001fb62  mov     eax, [rsi+20h]
0x18001fb65  mov     [rsp+250h+var_210], eax
0x18001fb69  lea     rax, [rsp+250h+var_210]
0x18001fb6e  mov     qword ptr [rsp+250h+dwCreationFlags], rax; int
0x18001fb73  lea     rdx, unk_1800718B8
0x18001fb7a  lea     rcx, dword_180083038
0x18001fb81  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001fb86  xorps   xmm0, xmm0
0x18001fb89  movups  [rsp+250h+Parameter], xmm0
0x18001fb8e  movups  [rsp+250h+var_1E8], xmm0
0x18001fb93  mov     [rsp+250h+var_208], r15
0x18001fb98  lea     rcx, [rsp+250h+var_208]
0x18001fb9d  call    ?InternalRelease@?$ComPtr@UIModalExperienceManagerStatic@ModalExperience@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(void)
0x18001fba2  mov     rax, [rdi]
0x18001fba5  lea     r8, [rsp+250h+var_208]
0x18001fbaa  lea     rdx, _GUID_c79b63d0_f8ec_4ceb_953a_c8876157dd33
0x18001fbb1  mov     rcx, rdi
0x18001fbb4  mov     rax, [rax]
0x18001fbb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbbc  mov     ebx, eax
0x18001fbbe  test    eax, eax
0x18001fbc0  jns     short loc_18001FBE2
0x18001fbc2  mov     rcx, [rbp+158h]; this
0x18001fbc9  mov     r9d, eax; char *
0x18001fbcc  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\workflow"...
0x18001fbd3  mov     edx, 3BFh; void *
0x18001fbd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fbdd  jmp     loc_18001FDF4
0x18001fbe2  mov     rax, [rsp+250h+var_208]
0x18001fbe7  mov     qword ptr [rsp+250h+Parameter], rax
0x18001fbec  mov     qword ptr [rsp+250h+Parameter+8], r14
0x18001fbf1  mov     [rsp+250h+string], r15
0x18001fbf6  xorps   xmm0, xmm0
0x18001fbf9  movups  [rbp+150h+var_1A8], xmm0
0x18001fbfd  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001fc05  movdqu  [rbp+150h+var_198], xmm1
0x18001fc0a  mov     word ptr [rbp+150h+var_1A8], r15w
0x18001fc0f  movups  [rbp+150h+var_1C8], xmm0
0x18001fc13  movdqu  [rbp+150h+var_1B8], xmm1
0x18001fc18  mov     word ptr [rbp+150h+var_1C8], r15w
0x18001fc1d  mov     rdi, [rsi+18h]
0x18001fc21  mov     rax, [rdi]
0x18001fc24  mov     rbx, [rax+30h]
0x18001fc28  xor     ecx, ecx; string
0x18001fc2a  call    cs:__imp_WindowsDeleteString
0x18001fc30  mov     [rsp+250h+string], r15
0x18001fc35  lea     rdx, [rsp+250h+string]
0x18001fc3a  mov     rcx, rdi
0x18001fc3d  mov     rax, rbx
0x18001fc40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc45  mov     ebx, eax
0x18001fc47  test    eax, eax
0x18001fc49  jns     short loc_18001FC8B
0x18001fc4b  mov     edx, 3C5h; void *
0x18001fc50  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\workflow"...
0x18001fc57  mov     r9d, eax; char *
0x18001fc5a  mov     rcx, [rbp+158h]; this
0x18001fc61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fc66  nop
0x18001fc67  lea     rcx, [rbp+150h+var_1C8]
0x18001fc6b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001fc70  nop
0x18001fc71  lea     rcx, [rbp+150h+var_1A8]
0x18001fc75  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001fc7a  nop
0x18001fc7b  mov     rcx, [rsp+250h+string]; string
0x18001fc80  call    cs:__imp_WindowsDeleteString
0x18001fc86  jmp     loc_18001FDEF
0x18001fc8b  xor     edx, edx; length
0x18001fc8d  mov     rcx, [rsp+250h+string]; string
0x18001fc92  call    cs:__imp_WindowsGetStringRawBuffer
0x18001fc98  lea     r8, [rbp+150h+var_1A8]
0x18001fc9c  lea     rdx, [rbp+150h+var_1C8]
0x18001fca0  mov     rcx, rax
0x18001fca3  call    ?GetWorkflowAppPropertiesFromDevPropStore@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; GetWorkflowAppPropertiesFromDevPropStore(ushort const *,std::wstring &,std::wstring &)
0x18001fca8  mov     ebx, eax
0x18001fcaa  test    eax, eax
0x18001fcac  jns     short loc_18001FCB5
0x18001fcae  mov     edx, 3C6h
0x18001fcb3  jmp     short loc_18001FC50
0x18001fcb5  lea     rax, [rbp+150h+var_1A8]
0x18001fcb9  mov     qword ptr [rsp+250h+var_1E8+8], rax
0x18001fcbe  lea     rax, [rbp+150h+var_1C8]
0x18001fcc2  mov     qword ptr [rsp+250h+var_1E8], rax
0x18001fcc7  mov     eax, cs:dword_180083038
0x18001fccd  cmp     eax, 5
0x18001fcd0  jbe     short loc_18001FCF6
0x18001fcd2  mov     eax, [rsi+20h]
0x18001fcd5  mov     [rsp+250h+var_210], eax
0x18001fcd9  lea     rax, [rsp+250h+var_210]
0x18001fcde  mov     qword ptr [rsp+250h+dwCreationFlags], rax
0x18001fce3  lea     rdx, unk_180071848
0x18001fcea  lea     rcx, dword_180083038
0x18001fcf1  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001fcf6  mov     [rsp+250h+lpThreadId], r15; lpThreadId
0x18001fcfb  mov     [rsp+250h+dwCreationFlags], r15d; int
0x18001fd00  lea     r9, [rsp+250h+Parameter]; lpParameter
0x18001fd05  lea     r8, ?LaunchUiFromSTAThread@CWorkflowAppSession@@SAKPEAX@Z; lpStartAddress
0x18001fd0c  xor     edx, edx; dwStackSize
0x18001fd0e  xor     ecx, ecx; lpThreadAttributes
0x18001fd10  call    cs:__imp_CreateThread
0x18001fd16  mov     [rsp+250h+var_200], rax
0x18001fd1b  lea     rcx, [rax+1]
0x18001fd1f  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18001fd26  jnz     short loc_18001FD57
0x18001fd28  mov     ebx, 8007000Eh
0x18001fd2d  mov     edx, 3D2h; void *
0x18001fd32  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\workflow"...
0x18001fd39  mov     r9d, ebx; char *
0x18001fd3c  mov     rcx, [rbp+158h]; this
0x18001fd43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fd48  lea     rcx, [rsp+250h+var_200]
0x18001fd4d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001fd52  jmp     loc_18001FC67
0x18001fd57  mov     [rsp+250h+Handles], rax
0x18001fd5c  mov     rax, [rsi+28h]
0x18001fd60  mov     [rbp+150h+var_1D0], rax
0x18001fd64  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001fd68  xor     r8d, r8d; bWaitAll
0x18001fd6b  lea     rdx, [rsp+250h+Handles]; lpHandles
0x18001fd70  lea     ecx, [r8+2]; nCount
0x18001fd74  call    cs:__imp_WaitForMultipleObjects
0x18001fd7a  test    eax, eax
0x18001fd7c  jz      short loc_18001FD8A
0x18001fd7e  mov     ebx, 80004005h
0x18001fd83  mov     edx, 3E0h
0x18001fd88  jmp     short loc_18001FD32
0x18001fd8a  mov     eax, cs:dword_180083038
0x18001fd90  cmp     eax, 5
0x18001fd93  jbe     short loc_18001FDB9
0x18001fd95  mov     eax, [rsi+20h]
0x18001fd98  mov     [rsp+250h+var_210], eax
0x18001fd9c  lea     rax, [rsp+250h+var_210]
0x18001fda1  mov     qword ptr [rsp+250h+dwCreationFlags], rax
0x18001fda6  lea     rdx, byte_1800717DD
0x18001fdad  lea     rcx, dword_180083038
0x18001fdb4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001fdb9  lea     rcx, [rbp+150h+var_180]
0x18001fdbd  call    ?Stop@?$ActivityBase@VPrintWorkFlowLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<PrintWorkFlowLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001fdc2  lea     rcx, [rsp+250h+var_200]
0x18001fdc7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001fdcc  nop
0x18001fdcd  lea     rcx, [rbp+150h+var_1C8]
0x18001fdd1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001fdd6  nop
0x18001fdd7  lea     rcx, [rbp+150h+var_1A8]
0x18001fddb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001fde0  nop
0x18001fde1  mov     rcx, [rsp+250h+string]; string
0x18001fde6  call    cs:__imp_WindowsDeleteString
0x18001fdec  mov     ebx, r15d
0x18001fdef  mov     [rsp+250h+string], r15
0x18001fdf4  lea     rcx, [rsp+250h+var_208]
0x18001fdf9  call    ?InternalRelease@?$ComPtr@UIModalExperienceManagerStatic@ModalExperience@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(void)
0x18001fdfe  nop
0x18001fdff  lea     rcx, [rbp+150h+var_180]; this
0x18001fe03  call    ??1RequestForegroundUI@PrintWorkFlowTelemetry@@QEAA@XZ; PrintWorkFlowTelemetry::RequestForegroundUI::~RequestForegroundUI(void)
0x18001fe08  mov     eax, ebx
0x18001fe0a  mov     rcx, [rbp+150h+var_30]
0x18001fe11  xor     rcx, rsp; StackCookie
0x18001fe14  call    __security_check_cookie
0x18001fe19  mov     rbx, [rsp+250h+arg_10]
0x18001fe21  add     rsp, 230h
0x18001fe28  pop     r15
0x18001fe2a  pop     r14
0x18001fe2c  pop     rdi
0x18001fe2d  pop     rsi
0x18001fe2e  pop     rbp
0x18001fe2f  retn
```
