# CXHHostAppManagerBase::Initialize(_GUID const &,bool,ushort const *,ushort const *)

- ea: `0x180038f8c`
- end: `0x180039455`
- name: `?Initialize@CXHHostAppManagerBase@@QEAAJAEBU_GUID@@_NPEBG2@Z`
- size: `1225`
- prototype: `int(CXHHostAppManagerBase *__hidden this, const struct _GUID *, bool, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003adbc`

## callees

- `0x1800032b0`
- `0x1800041dc`
- `0x1800054ac`
- `0x1800056c8`
- `0x180005768`
- `0x1800067b0`
- `0x180007134`
- `0x180007e34`
- `0x18000e270`
- `0x18000ee5c`
- `0x18001136c`
- `0x1800113cc`
- `0x180012328`
- `0x180013688`
- `0x180014468`
- `0x180016878`
- `0x1800169b0`
- `0x18002d934`
- `0x180038c78`
- `0x180038f8c`
- `0x18003aea8`
- `0x18004e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800390ce`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800390ce`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180038fcb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180038fcb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800391d5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800391d5`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x1800390b9`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x1800390b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039375`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039375`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039322`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039322`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003927c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003927c`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CXHHostAppManagerBase::Initialize(
        CXHHostAppManagerBase *this,
        const struct _GUID *a2,
        char a3,
        const unsigned __int16 *a4)
{
  HANDLE EventW; // rax
  unsigned int v8; // ebx
  int v9; // eax
  unsigned __int64 v10; // r15
  int v11; // ebx
  wchar_t *v12; // rax
  int v13; // eax
  __int64 v14; // rdx
  unsigned __int64 v15; // rbx
  int v16; // eax
  unsigned int v17; // esi
  HRESULT v18; // eax
  __int64 v19; // rdx
  LPVOID v20; // rsi
  __int64 (__fastcall *v21)(LPVOID, __int64 *, GUID *, char *); // rdi
  const char *ActivationFactory; // rbx
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, _QWORD, __int64 *); // rbx
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rbx
  __int64 (__fastcall *v28)(__int64, HSTRING *); // rsi
  HSTRING v29; // rdi
  int v30; // eax
  PCWSTR StringRawBuffer; // rax
  const unsigned __int16 *v32; // rdi
  int ppv; // [rsp+20h] [rbp-71h]
  int ppvc; // [rsp+20h] [rbp-71h]
  int ppva; // [rsp+20h] [rbp-71h]
  int ppvb; // [rsp+20h] [rbp-71h]
  LPVOID v38; // [rsp+30h] [rbp-61h] BYREF
  HSTRING string; // [rsp+38h] [rbp-59h] BYREF
  __int64 v40; // [rsp+40h] [rbp-51h] BYREF
  HANDLE v41; // [rsp+48h] [rbp-49h] BYREF
  __int64 v42; // [rsp+50h] [rbp-41h] BYREF
  LPOLESTR lpsz; // [rsp+58h] [rbp-39h] BYREF
  __int64 v44; // [rsp+60h] [rbp-31h]
  __int64 v45; // [rsp+68h] [rbp-29h]
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-21h] BYREF
  __int64 v47; // [rsp+88h] [rbp-9h]
  IID Buf1; // [rsp+90h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+57h]

  EventW = CreateEventW(0, 1, 0, 0);
  v41 = EventW;
  if ( (HANDLE *)((char *)this + 32) != &v41 )
  {
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      (char *)this + 32,
      EventW);
    v41 = 0;
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v41);
  if ( *((_QWORD *)this + 4) )
  {
    v9 = SetFullscreenCXHRunning(1);
    if ( v9 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1E8,
        (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\appmanager.cpp",
        (const char *)(unsigned int)v9,
        ppv);
    *((_BYTE *)this + 112) = a3;
    Buf1 = *GetFirstRunTelemetryCorrelationId((struct _GUID *)&hstringHeader);
    lpsz = 0;
    v44 = 0;
    v45 = 0;
    v10 = -1;
    if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u)
      || (Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpsz),
          v44 = -1,
          v45 = -1,
          StringFromIID(&Buf1, &lpsz) < 0) )
    {
      if ( a4 )
      {
        v15 = -1;
        do
          ++v15;
        while ( a4[v15] );
        v16 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                (char *)this + 88,
                v15);
        v17 = v16;
        if ( v16 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1F3,
            (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\appmanager.cpp",
            (const char *)(unsigned int)v16,
            ppv);
          v8 = v17;
          goto LABEL_44;
        }
        StringCchCopyNW(*((unsigned __int16 **)this + 11), v15 + 1, a4, v15);
        *((_QWORD *)this + 12) = v15;
      }
      else
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 88);
      }
    }
    else
    {
      v11 = (int)lpsz;
      v12 = wcschr(a4, 0x3Fu);
      ppv = v11;
      v13 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
              (char *)this + 88,
              L"%s%ccorrelationId=%s",
              a4,
              v12 != 0 ? 38 : 63);
      v8 = v13;
      if ( v13 < 0 )
      {
        v14 = 495;
LABEL_43:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\appmanager.cpp",
          (const char *)(unsigned int)v13,
          ppv);
        goto LABEL_44;
      }
    }
    v13 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
            (char *)this + 120,
            37);
    v8 = v13;
    if ( v13 < 0 )
    {
      v14 = 502;
      goto LABEL_43;
    }
    StringCchCopyNW(*((unsigned __int16 **)this + 15), 0x26u, L"Windows.Internal.ShellExperience.OOBE", 0x25u);
    *((_QWORD *)this + 16) = 37;
    v38 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
    v18 = CoCreateInstance(
            &GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239,
            0,
            0x404u,
            &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
            &v38);
    v8 = v18;
    if ( v18 >= 0 )
    {
      v20 = v38;
      v21 = *(__int64 (__fastcall **)(LPVOID, __int64 *, GUID *, char *))(*(_QWORD *)v38 + 24LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 144);
      v18 = v21(v20, qword_18005C558, &GUID_8f352570_5bb7_4d72_921f_6fb3f2611c71, (char *)this + 144);
      v8 = v18;
      if ( v18 >= 0 )
      {
        string = 0;
        v42 = 0;
        v47 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"CloudExperienceHostAPI.Redirection.RedirectionManager",
          0x36u,
          0x35u);
        ActivationFactory = (const char *)(unsigned int)RoGetActivationFactory(
                                                          v47,
                                                          &GUID_dcaebdd1_c09b_5f76_9aae_b70b9809cbaf,
                                                          &v42);
        wil::details::in1diag3::Log_IfFailedWithExpected(
          retaddr,
          (void *)0x200,
          (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\appmanager.cpp",
          ActivationFactory,
          1,
          0x80040154);
        if ( (int)ActivationFactory >= 0 )
        {
          v40 = 0;
          v23 = v42;
          v24 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v42 + 48LL);
          v40 = 0;
          v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (char *)this + 88);
          v26 = v24(v23, *(_QWORD *)(v25 + 24), &v40);
          if ( v26 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x204,
              (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\appmanager.cpp",
              (const char *)(unsigned int)v26,
              ppvb);
          v27 = v40;
          if ( v40 )
          {
            v28 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v40 + 48LL);
            v29 = string;
            if ( string )
            {
              wil::last_error_context::last_error_context((wil::last_error_context *)&hstringHeader);
              WindowsDeleteString(v29);
              wil::last_error_context::~last_error_context((wil::last_error_context *)&hstringHeader);
            }
            string = 0;
            v30 = v28(v27, &string);
            if ( v30 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x208,
                (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\appmanager.cpp",
                (const char *)(unsigned int)v30,
                ppvb);
          }
          wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v40);
        }
        if ( string )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v32 = StringRawBuffer;
          if ( StringRawBuffer )
          {
            do
              ++v10;
            while ( StringRawBuffer[v10] );
            if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                        (char *)this + 64,
                        v10) >= 0 )
            {
              StringCchCopyNW(*((unsigned __int16 **)this + 8), v10 + 1, v32, v10);
              *((_QWORD *)this + 9) = v10;
            }
          }
          else
          {
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 64);
          }
        }
        else if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                         (char *)this + 64,
                         55) >= 0 )
        {
          StringCchCopyNW(
            *((unsigned __int16 **)this + 8),
            0x38u,
            L"Microsoft.Windows.CloudExperienceHost_cw5n1h2txyewy!App",
            0x37u);
          *((_QWORD *)this + 9) = 55;
        }
        wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v42);
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
        v8 = 0;
        goto LABEL_44;
      }
      v19 = 506;
    }
    else
    {
      v19 = 505;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\appmanager.cpp",
      (const char *)(unsigned int)v18,
      ppva);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
LABEL_44:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpsz);
    return v8;
  }
  v8 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x81,
    (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\appmanager.h",
    (const char *)0x8007000ELL,
    ppv);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1E6,
    (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\appmanager.cpp",
    (const char *)0x8007000ELL,
    ppvc);
  return v8;
}

```

## disassembly

```asm
0x180038f8c  mov     [rsp-8+arg_8], rbx
0x180038f91  push    rbp
0x180038f92  push    rsi
0x180038f93  push    rdi
0x180038f94  push    r12
0x180038f96  push    r13
0x180038f98  push    r14
0x180038f9a  push    r15
0x180038f9c  lea     rbp, [rsp-1Fh]
0x180038fa1  sub     rsp, 0B0h
0x180038fa8  mov     rax, cs:__security_cookie
0x180038faf  xor     rax, rsp
0x180038fb2  mov     [rbp+4Fh+var_40], rax
0x180038fb6  mov     r12, r9
0x180038fb9  mov     dil, r8b
0x180038fbc  mov     r13, rcx
0x180038fbf  xor     r9d, r9d; lpName
0x180038fc2  xor     r8d, r8d; bInitialState
0x180038fc5  lea     edx, [r9+1]; bManualReset
0x180038fc9  xor     ecx, ecx; lpEventAttributes
0x180038fcb  call    cs:__imp_CreateEventW
0x180038fd1  mov     [rbp+4Fh+var_98], rax
0x180038fd5  lea     rbx, [r13+20h]
0x180038fd9  lea     rcx, [rbp+4Fh+var_98]
0x180038fdd  xor     esi, esi
0x180038fdf  cmp     rbx, rcx
0x180038fe2  jz      short loc_180038FF3
0x180038fe4  mov     rdx, rax
0x180038fe7  mov     rcx, rbx
0x180038fea  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180038fef  mov     [rbp+4Fh+var_98], rsi
0x180038ff3  lea     rcx, [rbp+4Fh+var_98]
0x180038ff7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180038ffc  cmp     [rbx], rsi
0x180038fff  jnz     short loc_18003903B
0x180039001  mov     rcx, [rbp+57h]; this
0x180039005  mov     ebx, 8007000Eh
0x18003900a  mov     r9d, ebx; char *
0x18003900d  lea     r8, aShellLibCloude_0; "shell\\lib\\cloudexperiencehostappmanag"...
0x180039014  mov     edx, 81h; void *
0x180039019  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003901e  mov     rcx, [rbp+57h]; this
0x180039022  mov     r9d, ebx; char *
0x180039025  lea     r8, aShellLibCloude; "shell\\lib\\cloudexperiencehostappmanag"...
0x18003902c  mov     edx, 1E6h; void *
0x180039031  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039036  jmp     loc_18003942C
0x18003903b  mov     cl, 1; bool
0x18003903d  call    ?SetFullscreenCXHRunning@@YAJ_N@Z; SetFullscreenCXHRunning(bool)
0x180039042  mov     rcx, [rbp+57h]; this
0x180039046  lea     r14, aShellLibCloude; "shell\\lib\\cloudexperiencehostappmanag"...
0x18003904d  test    eax, eax
0x18003904f  jns     short loc_180039061
0x180039051  mov     r9d, eax; char *
0x180039054  mov     r8, r14; unsigned int
0x180039057  mov     edx, 1E8h; void *
0x18003905c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180039061  mov     [r13+70h], dil
0x180039065  lea     rcx, [rbp+4Fh+hstringHeader]; retstr
0x180039069  call    ?GetFirstRunTelemetryCorrelationId@@YA?AU_GUID@@XZ; GetFirstRunTelemetryCorrelationId(void)
0x18003906e  movups  xmm0, xmmword ptr [rax]
0x180039071  movdqu  [rbp+4Fh+Buf1], xmm0
0x180039076  mov     [rbp+4Fh+lpsz], rsi
0x18003907a  mov     [rbp+4Fh+var_80], rsi
0x18003907e  mov     [rbp+4Fh+var_78], rsi
0x180039082  mov     r8d, 10h; Size
0x180039088  lea     rdx, GUID_NULL; Buf2
0x18003908f  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x180039093  call    memcmp_0
0x180039098  or      r15, 0FFFFFFFFFFFFFFFFh
0x18003909c  test    eax, eax
0x18003909e  jz      short loc_18003910D
0x1800390a0  lea     rcx, [rbp+4Fh+lpsz]
0x1800390a4  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800390a9  mov     [rbp+4Fh+var_80], r15
0x1800390ad  mov     [rbp+4Fh+var_78], r15
0x1800390b1  lea     rdx, [rbp+4Fh+lpsz]; lplpsz
0x1800390b5  lea     rcx, [rbp+4Fh+Buf1]; rclsid
0x1800390b9  call    cs:__imp_StringFromIID
0x1800390bf  test    eax, eax
0x1800390c1  js      short loc_18003910D
0x1800390c3  mov     rbx, [rbp+4Fh+lpsz]
0x1800390c7  lea     edx, [r15+40h]; Ch
0x1800390cb  mov     rcx, r12; Str
0x1800390ce  call    cs:__imp_wcschr
0x1800390d4  neg     rax
0x1800390d7  sbb     r9d, r9d
0x1800390da  and     r9d, 0FFFFFFE7h
0x1800390de  add     r9d, 3Fh ; '?'
0x1800390e2  lea     rcx, [r13+58h]
0x1800390e6  mov     [rsp+0E0h+ppv], rbx
0x1800390eb  mov     r8, r12
0x1800390ee  lea     rdx, aSCcorrelationi; "%s%ccorrelationId=%s"
0x1800390f5  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800390fa  mov     ebx, eax
0x1800390fc  xor     r12d, r12d
0x1800390ff  test    eax, eax
0x180039101  jns     short loc_180039172
0x180039103  mov     edx, 1EFh
0x180039108  jmp     loc_180039413
0x18003910d  lea     rdi, [r13+58h]
0x180039111  test    r12, r12
0x180039114  jz      short loc_180039167
0x180039116  mov     rbx, r15
0x180039119  inc     rbx
0x18003911c  cmp     [r12+rbx*2], si
0x180039121  jnz     short loc_180039119
0x180039123  mov     rdx, rbx
0x180039126  mov     rcx, rdi
0x180039129  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x18003912e  mov     esi, eax
0x180039130  test    eax, eax
0x180039132  js      short loc_18003914C
0x180039134  lea     rdx, [rbx+1]; unsigned __int64
0x180039138  mov     r9, rbx; unsigned __int64
0x18003913b  mov     r8, r12; unsigned __int16 *
0x18003913e  mov     rcx, [rdi]; unsigned __int16 *
0x180039141  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180039146  mov     [rdi+8], rbx
0x18003914a  jmp     short loc_18003916F
0x18003914c  mov     rcx, [rbp+57h]; this
0x180039150  mov     r9d, esi; char *
0x180039153  mov     r8, r14; unsigned int
0x180039156  mov     edx, 1F3h; void *
0x18003915b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039160  mov     ebx, esi
0x180039162  jmp     loc_180039423
0x180039167  mov     rcx, rdi
0x18003916a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003916f  xor     r12d, r12d
0x180039172  mov     esi, 25h ; '%'
0x180039177  mov     edx, esi
0x180039179  lea     rcx, [r13+78h]
0x18003917d  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x180039182  mov     ebx, eax
0x180039184  test    eax, eax
0x180039186  js      loc_18003940E
0x18003918c  mov     r9d, esi; unsigned __int64
0x18003918f  lea     r8, aWindowsInterna_0; "Windows.Internal.ShellExperience.OOBE"
0x180039196  lea     edx, [rsi+1]; unsigned __int64
0x180039199  mov     rcx, [r13+78h]; unsigned __int16 *
0x18003919d  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800391a2  mov     [r13+80h], rsi
0x1800391a9  mov     [rbp+4Fh+var_B0], r12
0x1800391ad  lea     rcx, [rbp+4Fh+var_B0]
0x1800391b1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800391b6  lea     rax, [rbp+4Fh+var_B0]
0x1800391ba  mov     [rsp+0E0h+ppv], rax; int
0x1800391bf  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x1800391c6  xor     edx, edx; pUnkOuter
0x1800391c8  mov     r8d, 404h; dwClsContext
0x1800391ce  lea     rcx, _GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239; rclsid
0x1800391d5  call    cs:__imp_CoCreateInstance
0x1800391db  mov     ebx, eax
0x1800391dd  test    eax, eax
0x1800391df  jns     short loc_180039204
0x1800391e1  mov     edx, 1F9h; void *
0x1800391e6  mov     r8, r14; unsigned int
0x1800391e9  mov     r9d, eax; char *
0x1800391ec  mov     rcx, [rbp+57h]; this
0x1800391f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800391f5  nop
0x1800391f6  lea     rcx, [rbp+4Fh+var_B0]
0x1800391fa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800391ff  jmp     loc_180039423
0x180039204  mov     rsi, [rbp+4Fh+var_B0]
0x180039208  mov     rax, [rsi]
0x18003920b  mov     rdi, [rax+18h]
0x18003920f  lea     rbx, [r13+90h]
0x180039216  mov     rcx, rbx
0x180039219  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003921e  mov     r9, rbx
0x180039221  lea     r8, _GUID_8f352570_5bb7_4d72_921f_6fb3f2611c71
0x180039228  lea     rdx, qword_18005C558
0x18003922f  mov     rcx, rsi
0x180039232  mov     rax, rdi
0x180039235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003923a  mov     ebx, eax
0x18003923c  test    eax, eax
0x18003923e  jns     short loc_180039247
0x180039240  mov     edx, 1FAh
0x180039245  jmp     short loc_1800391E6
0x180039247  mov     [rbp+4Fh+string], r12
0x18003924b  mov     [rbp+4Fh+var_90], r12
0x18003924f  mov     [rbp+4Fh+var_58], r12
0x180039253  mov     r9d, 35h ; '5'; unsigned int
0x180039259  lea     r8d, [r9+1]; unsigned int
0x18003925d  lea     rdx, ?RuntimeClass_CloudExperienceHostAPI_Redirection_RedirectionManager@@3QBGB; "CloudExperienceHostAPI.Redirection.Redi"...
0x180039264  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x180039268  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003926d  lea     r8, [rbp+4Fh+var_90]
0x180039271  lea     rdx, _GUID_dcaebdd1_c09b_5f76_9aae_b70b9809cbaf
0x180039278  mov     rcx, [rbp+4Fh+var_58]
0x18003927c  call    cs:__imp_RoGetActivationFactory
0x180039282  mov     ebx, eax
0x180039284  mov     rcx, [rbp+57h]; this
0x180039288  mov     [rsp+0E0h+var_B8], 80040154h; unsigned int
0x180039290  mov     dword ptr [rsp+0E0h+ppv], 1; int
0x180039298  mov     r9d, eax; char *
0x18003929b  mov     r8, r14; unsigned int
0x18003929e  mov     edx, 200h; void *
0x1800392a3  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x1800392a8  test    ebx, ebx
0x1800392aa  js      loc_180039366
0x1800392b0  mov     [rbp+4Fh+var_A0], r12
0x1800392b4  mov     rdi, [rbp+4Fh+var_90]
0x1800392b8  mov     rax, [rdi]
0x1800392bb  mov     rbx, [rax+30h]
0x1800392bf  mov     [rbp+4Fh+var_A0], r12
0x1800392c3  lea     rdx, [r13+58h]
0x1800392c7  lea     rcx, [rbp+4Fh+hstringHeader]
0x1800392cb  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800392d0  nop
0x1800392d1  lea     r8, [rbp+4Fh+var_A0]
0x1800392d5  mov     rdx, [rax+18h]
0x1800392d9  mov     rcx, rdi
0x1800392dc  mov     rax, rbx
0x1800392df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392e4  mov     rcx, [rbp+57h]; this
0x1800392e8  test    eax, eax
0x1800392ea  jns     short loc_1800392FD
0x1800392ec  mov     r9d, eax; char *
0x1800392ef  mov     r8, r14; unsigned int
0x1800392f2  mov     edx, 204h; void *
0x1800392f7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800392fc  nop
0x1800392fd  mov     rbx, [rbp+4Fh+var_A0]
0x180039301  test    rbx, rbx
0x180039304  jz      short loc_18003935D
0x180039306  mov     rax, [rbx]
0x180039309  mov     rsi, [rax+30h]
0x18003930d  mov     rdi, [rbp+4Fh+string]
0x180039311  test    rdi, rdi
0x180039314  jz      short loc_180039331
0x180039316  lea     rcx, [rbp+4Fh+hstringHeader]; this
0x18003931a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003931f  mov     rcx, rdi; string
0x180039322  call    cs:__imp_WindowsDeleteString
0x180039328  lea     rcx, [rbp+4Fh+hstringHeader]; this
0x18003932c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180039331  mov     [rbp+4Fh+string], r12
0x180039335  lea     rdx, [rbp+4Fh+string]
0x180039339  mov     rcx, rbx
0x18003933c  mov     rax, rsi
0x18003933f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039344  mov     rcx, [rbp+57h]; this
0x180039348  test    eax, eax
0x18003934a  jns     short loc_18003935D
0x18003934c  mov     r9d, eax; char *
0x18003934f  mov     r8, r14; unsigned int
0x180039352  mov     edx, 208h; void *
0x180039357  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003935c  nop
0x18003935d  lea     rcx, [rbp+4Fh+var_A0]
0x180039361  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180039366  mov     rcx, [rbp+4Fh+string]; string
0x18003936a  test    rcx, rcx
0x18003936d  jz      short loc_1800393BE
0x18003936f  lea     rbx, [r13+40h]
0x180039373  xor     edx, edx; length
0x180039375  call    cs:__imp_WindowsGetStringRawBuffer
0x18003937b  mov     rdi, rax
0x18003937e  test    rax, rax
0x180039381  jz      short loc_1800393B4
0x180039383  inc     r15
0x180039386  cmp     [rax+r15*2], r12w
0x18003938b  jnz     short loc_180039383
0x18003938d  mov     rdx, r15
0x180039390  mov     rcx, rbx
0x180039393  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x180039398  test    eax, eax
0x18003939a  js      short loc_1800393EC
0x18003939c  lea     rdx, [r15+1]; unsigned __int64
0x1800393a0  mov     r9, r15; unsigned __int64
0x1800393a3  mov     r8, rdi; unsigned __int16 *
0x1800393a6  mov     rcx, [rbx]; unsigned __int16 *
0x1800393a9  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800393ae  mov     [rbx+8], r15
0x1800393b2  jmp     short loc_1800393EC
0x1800393b4  mov     rcx, rbx
0x1800393b7  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800393bc  jmp     short loc_1800393EC
0x1800393be  mov     edi, 37h ; '7'
0x1800393c3  mov     edx, edi
0x1800393c5  lea     rcx, [r13+40h]
0x1800393c9  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x1800393ce  test    eax, eax
0x1800393d0  js      short loc_1800393EC
0x1800393d2  mov     r9d, edi; unsigned __int64
0x1800393d5  lea     r8, aMicrosoftWindo; "Microsoft.Windows.CloudExperienceHost_c"...
0x1800393dc  lea     edx, [rdi+1]; unsigned __int64
0x1800393df  mov     rcx, [r13+40h]; unsigned __int16 *
0x1800393e3  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800393e8  mov     [r13+48h], rdi
0x1800393ec  lea     rcx, [rbp+4Fh+var_90]
0x1800393f0  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x1800393f5  nop
0x1800393f6  lea     rcx, [rbp+4Fh+string]; this
0x1800393fa  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800393ff  nop
  ... truncated ...
```
