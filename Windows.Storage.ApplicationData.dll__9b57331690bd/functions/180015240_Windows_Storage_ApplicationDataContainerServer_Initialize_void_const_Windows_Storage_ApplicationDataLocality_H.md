# Windows::Storage::ApplicationDataContainerServer::Initialize(void * const,Windows::Storage::ApplicationDataLocality,HSTRING__ *,Windows::Storage::ApplicationDataCreateDisposition,Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> const &,bool *)

- ea: `0x180015240`
- end: `0x1800156bd`
- name: `?Initialize@ApplicationDataContainerServer@Storage@Windows@@UEAAJQEAXW4ApplicationDataLocality@23@PEAUHSTRING__@@W4ApplicationDataCreateDisposition@23@AEBV?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@PEA_N@Z`
- size: `1149`
- prototype: `HRESULT __fastcall(Windows::Storage::ApplicationDataContainerServer *this, void *const parentContainer, const Windows::Storage::ApplicationDataLocality locality, HSTRING__ *name, const Windows::Storage::ApplicationDataCreateDisposition disposition, const Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> *propertyValueStaticInterfaceParameter, bool *containerCreated)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800022b0`
- `0x180005ee0`
- `0x180009778`
- `0x180015240`
- `0x180041620`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180015311`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180015311`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800152df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800155e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015632`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015670`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800152df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800155e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015632`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015670`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180015279`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180015279`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001532e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001532e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180015432`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180015494`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180015526`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180015432`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180015494`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180015526`
- `ext-ms-win-appmodel-state-ext-l1-2-0!QueryStateContainerCreatedNew` at `0x180015349`
- `ext-ms-win-appmodel-state-ext-l1-2-0!QueryStateContainerCreatedNew` at `0x180015349`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CreateStateSubcontainer` at `0x1800152ee`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CreateStateSubcontainer` at `0x1800152ee`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CloseStateContainer` at `0x1800156b0`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CloseStateContainer` at `0x1800156b0`

## string_xrefs

- `0x180015574`: `onecoreuap\base\appmodel\statemanager\winrt\lib\stateabicommonhelpers.cpp`
- `0x180015598`: `GetStateApiSetCreateDisposition %u`
- `0x180015610`: `CreateStateSubcontainer %u %ws %u`
- `0x180015640`: `QueryStateContainerCreatedNew %u %ws %u`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataContainerServer::Initialize(
        Windows::Storage::ApplicationDataContainerServer *this,
        void *const parentContainer,
        Windows::Storage::ApplicationDataLocality locality,
        HSTRING name,
        Windows::Storage::ApplicationDataCreateDisposition disposition,
        const Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> *propertyValueStaticInterfaceParameter,
        bool *containerCreated)
{
  unsigned int v11; // r14d
  PCWSTR StringRawBuffer; // rax
  void *StateSubcontainer; // rbx
  int LastErrorMsg; // edi
  HSTRING__ *hstring; // rcx
  Windows::Foundation::IPropertyValueStatics *ptr; // rbx
  Windows::Foundation::IPropertyValueStatics *v17; // rcx
  signed int LastError; // eax
  HRESULT v20; // ebx
  PCWSTR v21; // rax
  PCWSTR v22; // rax
  PCWSTR v23; // rax
  HSTRING wasContainerCreated; // [rsp+40h] [rbp-D8h] BYREF
  wchar_t v25; // [rsp+48h] [rbp-D0h]
  _OWORD v26[2]; // [rsp+50h] [rbp-C8h] BYREF
  _OWORD v27[3]; // [rsp+70h] [rbp-A8h] BYREF
  _OWORD v28[2]; // [rsp+A0h] [rbp-78h]
  void *retaddr; // [rsp+118h] [rbp+0h]

  if ( WindowsIsStringEmpty(name) )
  {
    wasContainerCreated = *(HSTRING *)L"name";
    v25 = aName[4];
    RoOriginateErrorW(2147942487LL, 4, &wasContainerCreated);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x95u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainer.server.cpp",
      -2147024809,
      "WindowsIsStringEmpty");
    return 2147942487LL;
  }
  if ( !parentContainer )
  {
    v26[0] = *(_OWORD *)L"parentContainer";
    v26[1] = *(_OWORD *)L"ntainer";
    RoOriginateErrorW(2147942487LL, 15, v26);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x9Du,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainer.server.cpp",
      -2147024809,
      "parentContainer");
    return 2147942487LL;
  }
  if ( !propertyValueStaticInterfaceParameter->ptr_ )
  {
    v27[0] = *(_OWORD *)L"propertyValueStaticInterfaceParameter";
    v27[2] = *(_OWORD *)L"ticInterfaceParameter";
    v27[1] = *(_OWORD *)L"ValueStaticInterfaceParameter";
    v28[0] = *(_OWORD *)L"faceParameter";
    *(_OWORD *)((char *)v28 + 12) = *(_OWORD *)L"rameter";
    RoOriginateErrorW(2147942487LL, 37, v27);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0xA4u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainer.server.cpp",
      -2147024809,
      "propertyValueStaticInterfaceParameter");
    return 2147942487LL;
  }
  if ( disposition )
  {
    if ( disposition != ApplicationDataCreateDisposition_Existing )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x50u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\stateabicommonhelpers.cpp",
        -2147024809,
        "Disposition %u",
        disposition);
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0xA9u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainer.server.cpp",
        -2147024809,
        "GetStateApiSetCreateDisposition %u",
        disposition);
      return 2147942487LL;
    }
    v11 = 2;
  }
  else
  {
    v11 = 1;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(name, 0);
  StateSubcontainer = (void *)CreateStateSubcontainer(parentContainer, StringRawBuffer, v11);
  if ( StateSubcontainer )
  {
    wasContainerCreated = 0;
    LastErrorMsg = WindowsDuplicateString(name, &wasContainerCreated);
    if ( LastErrorMsg < 0 )
    {
      v23 = WindowsGetStringRawBuffer(name, 0);
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0xC2u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainer.server.cpp",
        LastErrorMsg,
        "Initialize %u %ws %u",
        locality,
        v23,
        v11);
    }
    else
    {
      hstring = this->m_name._hstring;
      this->m_name._hstring = wasContainerCreated;
      WindowsDeleteString(hstring);
      if ( !containerCreated )
      {
LABEL_12:
        this->m_containerHandle = StateSubcontainer;
        this->m_locality = locality;
        ptr = propertyValueStaticInterfaceParameter->ptr_;
        if ( this->m_propertyValueStaticInterface.ptr_ != propertyValueStaticInterfaceParameter->ptr_ )
        {
          if ( ptr )
            ptr->AddRef(propertyValueStaticInterfaceParameter->ptr_);
          v17 = this->m_propertyValueStaticInterface.ptr_;
          this->m_propertyValueStaticInterface.ptr_ = ptr;
          if ( v17 )
            v17->Release(v17);
        }
        return 0;
      }
      LODWORD(wasContainerCreated) = 0;
      if ( (unsigned int)QueryStateContainerCreatedNew(StateSubcontainer, &wasContainerCreated) )
      {
        *containerCreated = (_DWORD)wasContainerCreated != 0;
        goto LABEL_12;
      }
      v22 = WindowsGetStringRawBuffer(name, 0);
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       0xCAu,
                       "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainer.server.cpp",
                       "QueryStateContainerCreatedNew %u %ws %u",
                       locality,
                       v22,
                       v11);
    }
    CloseStateContainer(StateSubcontainer);
    return (unsigned int)LastErrorMsg;
  }
  LastError = GetLastError();
  v20 = LastError;
  if ( LastError > 0 )
    v20 = (unsigned __int16)LastError | 0x80070000;
  if ( disposition == ApplicationDataCreateDisposition_Existing && v20 == -2147020584 )
    return 2147946712LL;
  Windows::Storage::StateABIHelpers::ReportError(v20, 5u);
  if ( v20 < 0 )
  {
    v21 = WindowsGetStringRawBuffer(name, 0);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0xBBu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainer.server.cpp",
      v20,
      "CreateStateSubcontainer %u %ws %u",
      locality,
      v21,
      v11);
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180015240  push    rbx
0x180015242  push    rbp
0x180015243  push    r12
0x180015245  push    r13
0x180015247  push    r15
0x180015249  sub     rsp, 0F0h
0x180015250  mov     rax, cs:__security_cookie
0x180015257  xor     rax, rsp
0x18001525a  mov     [rsp+118h+var_58], rax
0x180015262  mov     r12, [rsp+118h+arg_30]
0x18001526a  mov     rbp, this
0x18001526d  mov     this, name; string
0x180015270  mov     r15, name
0x180015273  mov     r13d, locality
0x180015276  mov     rbx, parentContainer
0x180015279  call    cs:__imp_WindowsIsStringEmpty
0x18001527f  test    eax, eax
0x180015281  jnz     loc_180015409
0x180015287  test    rbx, rbx
0x18001528a  jz      loc_18001546D
0x180015290  mov     [rsp+118h+var_30], rsi
0x180015298  mov     rsi, [rsp+118h+arg_28]
0x1800152a0  cmp     qword ptr [rsi], 0
0x1800152a4  jz      loc_1800154CF
0x1800152aa  mov     [rsp+118h+var_38], rdi
0x1800152b2  mov     edi, [rsp+118h+arg_20]
0x1800152b9  mov     eax, edi
0x1800152bb  mov     [rsp+118h+var_40], r14
0x1800152c3  test    edi, edi
0x1800152c5  jz      loc_1800155C9
0x1800152cb  cmp     eax, 1
0x1800152ce  jnz     loc_180015561
0x1800152d4  mov     r14d, 2
0x1800152da  xor     edx, edx; length
0x1800152dc  mov     this, r15; string
0x1800152df  call    cs:__imp_WindowsGetStringRawBuffer
0x1800152e5  mov     locality, r14d
0x1800152e8  mov     this, rbx
0x1800152eb  mov     parentContainer, rax
0x1800152ee  call    cs:__imp_CreateStateSubcontainer
0x1800152f4  mov     rbx, rax
0x1800152f7  test    rax, rax
0x1800152fa  jz      loc_1800153DB
0x180015300  lea     parentContainer, [rsp+118h+wasContainerCreated]; newString
0x180015305  mov     [rsp+118h+wasContainerCreated], 0
0x18001530e  mov     this, r15; string
0x180015311  call    cs:__imp_WindowsDuplicateString
0x180015317  mov     edi, eax
0x180015319  test    eax, eax
0x18001531b  js      loc_18001566B
0x180015321  mov     rax, [rsp+118h+wasContainerCreated]
0x180015326  mov     this, [rbp+48h]; string
0x18001532a  mov     [rbp+48h], rax
0x18001532e  call    cs:__imp_WindowsDeleteString
0x180015334  test    r12, r12
0x180015337  jz      short loc_180015363
0x180015339  lea     parentContainer, [rsp+118h+wasContainerCreated]
0x18001533e  mov     dword ptr [rsp+118h+wasContainerCreated], 0
0x180015346  mov     this, rbx
0x180015349  call    cs:__imp_QueryStateContainerCreatedNew
0x18001534f  test    eax, eax
0x180015351  jz      loc_18001562D
0x180015357  cmp     dword ptr [rsp+118h+wasContainerCreated], 0
0x18001535c  setnz   al
0x18001535f  mov     [r12], al
0x180015363  mov     [rbp+58h], rbx
0x180015367  mov     [rbp+50h], r13d
0x18001536b  mov     rbx, [rsi]
0x18001536e  cmp     [rbp+60h], rbx
0x180015372  jz      short loc_1800153A1
0x180015374  test    rbx, rbx
0x180015377  jz      short loc_180015388
0x180015379  mov     rax, [rbx]
0x18001537c  mov     this, rbx
0x18001537f  mov     rax, [rax+8]
0x180015383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015388  mov     this, [rbp+60h]
0x18001538c  mov     [rbp+60h], rbx
0x180015390  test    this, this
0x180015393  jz      short loc_1800153A1
0x180015395  mov     rax, [this]
0x180015398  mov     rax, [rax+10h]
0x18001539c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153a1  xor     eax, eax
0x1800153a3  mov     rdi, [rsp+118h+var_38]
0x1800153ab  mov     r14, [rsp+118h+var_40]
0x1800153b3  mov     rsi, [rsp+118h+var_30]
0x1800153bb  mov     this, [rsp+118h+var_58]
0x1800153c3  xor     this, rsp; StackCookie
0x1800153c6  call    __security_check_cookie
0x1800153cb  add     rsp, 0F0h
0x1800153d2  pop     r15
0x1800153d4  pop     r13
0x1800153d6  pop     r12
0x1800153d8  pop     rbp
0x1800153d9  pop     rbx
0x1800153da  retn
0x1800153db  call    cs:__imp_GetLastError
0x1800153e1  mov     ebx, eax
0x1800153e3  test    eax, eax
0x1800153e5  jle     short loc_1800153F0
0x1800153e7  movzx   ebx, ax
0x1800153ea  or      ebx, 80070000h
0x1800153f0  cmp     edi, 1
0x1800153f3  jnz     loc_1800155D4
0x1800153f9  cmp     ebx, 800710D8h
0x1800153ff  jnz     loc_1800155D4
0x180015405  mov     eax, ebx
0x180015407  jmp     short loc_1800153A3
0x180015409  movsd   xmm0, qword ptr cs:aName; "name"
0x180015411  lea     r8, [rsp+118h+wasContainerCreated]
0x180015416  movzx   eax, word ptr cs:aName+8; ""
0x18001541d  mov     edx, 4
0x180015422  mov     ecx, 80070057h
0x180015427  movsd   [rsp+118h+wasContainerCreated], xmm0
0x18001542d  mov     [rsp+118h+var_D0], ax
0x180015432  call    cs:__imp_RoOriginateErrorW
0x180015438  mov     this, [rsp+118h]; callerReturnAddress
0x180015440  lea     rax, aWindowsisstrin_0; "WindowsIsStringEmpty"
0x180015447  mov     r9d, 80070057h; hr
0x18001544d  mov     [rsp+118h+formatString], rax; formatString
0x180015452  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\statemanage"...
0x180015459  mov     edx, 95h; lineNumber
0x18001545e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180015463  mov     eax, 80070057h
0x180015468  jmp     loc_1800153BB
0x18001546d  movups  xmm0, xmmword ptr cs:aParentcontaine; "parentContainer"
0x180015474  lea     r8, [rsp+118h+var_C8]
0x180015479  mov     edx, 0Fh
0x18001547e  movups  xmm1, xmmword ptr cs:aParentcontaine+10h; "ntainer"
0x180015485  mov     ecx, 80070057h
0x18001548a  movups  [rsp+118h+var_C8], xmm0
0x18001548f  movups  [rsp+118h+var_B8], xmm1
0x180015494  call    cs:__imp_RoOriginateErrorW
0x18001549a  mov     this, [rsp+118h]; callerReturnAddress
0x1800154a2  lea     rax, aParentcontaine_0; "parentContainer"
0x1800154a9  mov     r9d, 80070057h; hr
0x1800154af  mov     [rsp+118h+formatString], rax; formatString
0x1800154b4  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800154bb  mov     edx, 9Dh; lineNumber
0x1800154c0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800154c5  mov     eax, 80070057h
0x1800154ca  jmp     loc_1800153BB
0x1800154cf  movaps  xmm0, xmmword ptr cs:aPropertyvalues; "propertyValueStaticInterfaceParameter"
0x1800154d6  lea     r8, [rsp+118h+var_A8]
0x1800154db  movaps  xmm1, xmmword ptr cs:aPropertyvalues+10h; "ValueStaticInterfaceParameter"
0x1800154e2  mov     edx, 25h ; '%'
0x1800154e7  movaps  [rsp+118h+var_A8], xmm0
0x1800154ec  mov     ecx, 80070057h
0x1800154f1  movaps  xmm0, xmmword ptr cs:aPropertyvalues+20h; "ticInterfaceParameter"
0x1800154f8  movaps  [rsp+118h+var_88], xmm0
0x180015500  movups  xmm0, xmmword ptr cs:aPropertyvalues+3Ch; "rameter"
0x180015507  movaps  [rsp+118h+var_98], xmm1
0x18001550f  movaps  xmm1, xmmword ptr cs:aPropertyvalues+30h; "faceParameter"
0x180015516  movaps  xmmword ptr [rsp+118h+var_78], xmm1
0x18001551e  movups  xmmword ptr [rsp+118h+var_78+0Ch], xmm0
0x180015526  call    cs:__imp_RoOriginateErrorW
0x18001552c  mov     this, [rsp+118h]; callerReturnAddress
0x180015534  lea     rax, aPropertyvalues_0; "propertyValueStaticInterfaceParameter"
0x18001553b  mov     r9d, 80070057h; hr
0x180015541  mov     [rsp+118h+formatString], rax; formatString
0x180015546  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\statemanage"...
0x18001554d  mov     edx, 0A4h; lineNumber
0x180015552  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180015557  mov     eax, 80070057h
0x18001555c  jmp     loc_1800153B3
0x180015561  mov     this, [rsp+118h]; callerReturnAddress
0x180015569  lea     rax, aDispositionU; "Disposition %u"
0x180015570  mov     dword ptr [rsp+118h+var_F0], edi
0x180015574  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\statemanage"...
0x18001557b  mov     r9d, 80070057h; hr
0x180015581  mov     [rsp+118h+formatString], rax; formatString
0x180015586  mov     edx, 50h ; 'P'; lineNumber
0x18001558b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180015590  mov     this, [rsp+118h]; callerReturnAddress
0x180015598  lea     rax, aGetstateapiset_1; "GetStateApiSetCreateDisposition %u"
0x18001559f  mov     dword ptr [rsp+118h+var_F0], edi
0x1800155a3  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800155aa  mov     r9d, 80070057h; hr
0x1800155b0  mov     [rsp+118h+formatString], rax; formatString
0x1800155b5  mov     edx, 0A9h; lineNumber
0x1800155ba  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800155bf  mov     eax, 80070057h
0x1800155c4  jmp     loc_1800153A3
0x1800155c9  mov     r14d, 1
0x1800155cf  jmp     loc_1800152DA
0x1800155d4  mov     edx, 5; idsValue
0x1800155d9  mov     ecx, ebx; hr
0x1800155db  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x1800155e0  test    ebx, ebx
0x1800155e2  jns     short loc_180015626
0x1800155e4  xor     edx, edx; length
0x1800155e6  mov     this, r15; string
0x1800155e9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800155ef  mov     this, [rsp+118h]; callerReturnAddress
0x1800155f7  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800155fe  mov     [rsp+118h+var_E0], r14d
0x180015603  mov     r9d, ebx; hr
0x180015606  mov     [rsp+118h+var_E8], rax
0x18001560b  mov     edx, 0BBh; lineNumber
0x180015610  lea     rax, aCreatestatesub_0; "CreateStateSubcontainer %u %ws %u"
0x180015617  mov     dword ptr [rsp+118h+var_F0], r13d
0x18001561c  mov     [rsp+118h+formatString], rax; formatString
0x180015621  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180015626  mov     eax, ebx
0x180015628  jmp     loc_1800153A3
0x18001562d  xor     edx, edx; length
0x18001562f  mov     this, r15; string
0x180015632  call    cs:__imp_WindowsGetStringRawBuffer
0x180015638  mov     this, [rsp+118h]; callerReturnAddress
0x180015640  lea     name, aQuerystatecont_1; "QueryStateContainerCreatedNew %u %ws %u"
0x180015647  mov     dword ptr [rsp+118h+var_E8], r14d
0x18001564c  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\statemanage"...
0x180015653  mov     [rsp+118h+var_F0], rax
0x180015658  mov     edx, 0CAh; lineNumber
0x18001565d  mov     dword ptr [rsp+118h+formatString], r13d
0x180015662  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180015667  mov     edi, eax
0x180015669  jmp     short loc_1800156AD
0x18001566b  xor     edx, edx; length
0x18001566d  mov     this, r15; string
0x180015670  call    cs:__imp_WindowsGetStringRawBuffer
0x180015676  mov     this, [rsp+118h]; callerReturnAddress
0x18001567e  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\statemanage"...
0x180015685  mov     [rsp+118h+var_E0], r14d
0x18001568a  mov     r9d, edi; hr
0x18001568d  mov     [rsp+118h+var_E8], rax
0x180015692  mov     edx, 0C2h; lineNumber
0x180015697  lea     rax, aInitializeUWsU; "Initialize %u %ws %u"
0x18001569e  mov     dword ptr [rsp+118h+var_F0], r13d
0x1800156a3  mov     [rsp+118h+formatString], rax; formatString
0x1800156a8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800156ad  mov     this, rbx
0x1800156b0  call    cs:__imp_CloseStateContainer
0x1800156b6  mov     eax, edi
0x1800156b8  jmp     loc_1800153A3
```
