# FSMedicServiceDrivenAction::InitializeParameters(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &)

- ea: `0x1800ac4d0`
- end: `0x1800ac6e0`
- name: `?InitializeParameters@FSMedicServiceDrivenAction@@MEAAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `528`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x180010fe0`
- `0x1800168c8`
- `0x18002299c`
- `0x18009bc4c`
- `0x1800a4148`
- `0x1800a4194`
- `0x1800a596c`
- `0x1800ac4d0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ac5be`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ac5be`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ac51f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ac51f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ac5d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ac5d2`

## string_xrefs

- `0x1800ac562`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsmedicservicedrivenaction.cpp`
- `0x1800ac6a0`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsmedicservicedrivenaction.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FSMedicServiceDrivenAction::InitializeParameters(__int64 a1, __int64 *a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // r15
  __int64 (__fastcall *v8)(__int64, HSTRING, __int64 *); // r12
  unsigned __int64 v9; // rcx
  int v10; // esi
  int inited; // eax
  __int64 v12; // rdx
  HSTRING *v13; // rax
  HSTRING *v14; // rax
  __int64 v15; // r9
  int ppv; // [rsp+20h] [rbp-50h]
  UINT32 length[2]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v19; // [rsp+38h] [rbp-38h] BYREF
  HSTRING string; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  *(_QWORD *)length = 0;
  CoCreateInstance(
    &GUID_72566e27_1abb_4eb3_b4f0_eb431cb1cb32,
    0,
    4u,
    &GUID_5556b1f9_4763_498e_aa9d_339a63392366,
    (LPVOID *)length);
  v4 = *(_QWORD *)length;
  *(_QWORD *)length = 0;
  v5 = *(_QWORD *)(a1 + 112);
  *(_QWORD *)(a1 + 112) = v4;
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(length);
  if ( *(_QWORD *)(a1 + 112) )
  {
    v19 = 0;
    v7 = *a2;
    v8 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)*a2 + 80LL);
    length[0] = 0;
    v9 = -1;
    do
      ++v9;
    while ( FSMedicServiceDrivenAction::s_operationTag[v9] );
    v10 = 1;
    if ( (int)ULongLongToUInt(v9, length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(FSMedicServiceDrivenAction::s_operationTag, length[0], &hstringHeader, &string);
    inited = v8(v7, string, &v19);
    v6 = inited;
    if ( inited >= 0 )
    {
      v13 = Windows::Internal::StringReference::StringReference(&string, L"INITIALIZE");
      if ( (unsigned int)Windows::Internal::String::CompareOrdinal(
                           (Windows::Internal::String *)&v19,
                           (const struct Windows::Internal::String *)v13) )
      {
        v14 = Windows::Internal::StringReference::StringReference(&string, L"CLEANUP");
        if ( (unsigned int)Windows::Internal::String::CompareOrdinal(
                             (Windows::Internal::String *)&v19,
                             (const struct Windows::Internal::String *)v14) )
        {
          v6 = -2146698740;
          v15 = 2148268556LL;
          v12 = 59;
          goto LABEL_21;
        }
      }
      else
      {
        v10 = 0;
      }
      *(_DWORD *)(a1 + 104) = v10;
      inited = FSServiceDrivenAction::InitStringFromJson(a2, L"CallerApplicationName", a1 + 56);
      v6 = inited;
      if ( inited >= 0 )
      {
        inited = FSServiceDrivenAction::InitStringFromJson(a2, L"CorrelationVector", a1 + 80);
        v6 = inited;
        if ( inited >= 0 )
        {
          Windows::Internal::String::~String((Windows::Internal::String *)&v19);
          return 0;
        }
        v12 = 63;
      }
      else
      {
        v12 = 62;
      }
    }
    else
    {
      v12 = 48;
    }
    v15 = (unsigned int)inited;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsmedicservicedrivenaction.cpp",
      (const char *)v15,
      ppv);
    Windows::Internal::String::~String((Windows::Internal::String *)&v19);
    return v6;
  }
  v6 = -2146698713;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2D,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsmedicservicedrivenaction.cpp",
    (const char *)0x800BFA27LL,
    ppv);
  return v6;
}

```

## disassembly

```asm
0x1800ac4d0  mov     [rsp-38h+arg_10], rbx
0x1800ac4d5  push    rbp
0x1800ac4d6  push    rsi
0x1800ac4d7  push    rdi
0x1800ac4d8  push    r12
0x1800ac4da  push    r13
0x1800ac4dc  push    r14
0x1800ac4de  push    r15
0x1800ac4e0  mov     rbp, rsp
0x1800ac4e3  sub     rsp, 70h
0x1800ac4e7  mov     rax, cs:__security_cookie
0x1800ac4ee  xor     rax, rsp
0x1800ac4f1  mov     [rbp+var_10], rax
0x1800ac4f5  mov     r14, rdx
0x1800ac4f8  mov     rdi, rcx
0x1800ac4fb  xor     r13d, r13d
0x1800ac4fe  mov     qword ptr [rbp+length], r13
0x1800ac502  lea     rax, [rbp+length]
0x1800ac506  mov     qword ptr [rsp+70h+ppv], rax; int
0x1800ac50b  lea     r9, _GUID_5556b1f9_4763_498e_aa9d_339a63392366; riid
0x1800ac512  xor     edx, edx; pUnkOuter
0x1800ac514  lea     r8d, [r13+4]; dwClsContext
0x1800ac518  lea     rcx, _GUID_72566e27_1abb_4eb3_b4f0_eb431cb1cb32; rclsid
0x1800ac51f  call    cs:__imp_CoCreateInstance
0x1800ac525  mov     rax, qword ptr [rbp+length]
0x1800ac529  mov     qword ptr [rbp+length], r13
0x1800ac52d  mov     rcx, [rdi+70h]
0x1800ac531  mov     [rdi+70h], rax
0x1800ac535  test    rcx, rcx
0x1800ac538  jz      short loc_1800AC547
0x1800ac53a  mov     rax, [rcx]
0x1800ac53d  mov     rax, [rax+10h]
0x1800ac541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac546  nop
0x1800ac547  lea     rcx, [rbp+length]
0x1800ac54b  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x1800ac550  cmp     [rdi+70h], r13
0x1800ac554  jnz     short loc_1800AC578
0x1800ac556  mov     rcx, [rbp+38h]; this
0x1800ac55a  mov     ebx, 800BFA27h
0x1800ac55f  mov     r9d, ebx; char *
0x1800ac562  lea     r8, aOnecoreBaseFli_91; "onecore\\base\\flighting\\flightsetting"...
0x1800ac569  mov     edx, 2Dh ; '-'; void *
0x1800ac56e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac573  jmp     loc_1800AC6BA
0x1800ac578  mov     [rbp+var_38], r13
0x1800ac57c  mov     r15, [r14]
0x1800ac57f  mov     rax, [r15]
0x1800ac582  mov     r12, [rax+50h]
0x1800ac586  mov     rbx, cs:?s_operationTag@FSMedicServiceDrivenAction@@0QEBGEB; ushort const * const FSMedicServiceDrivenAction::s_operationTag
0x1800ac58d  mov     [rbp+length], r13d
0x1800ac591  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800ac595  inc     rcx; unsigned __int64
0x1800ac598  cmp     [rbx+rcx*2], r13w
0x1800ac59d  jnz     short loc_1800AC595
0x1800ac59f  lea     rdx, [rbp+length]; unsigned int *
0x1800ac5a3  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800ac5a8  mov     esi, 1
0x1800ac5ad  test    eax, eax
0x1800ac5af  jns     short loc_1800AC5C4
0x1800ac5b1  xor     r9d, r9d; lpArguments
0x1800ac5b4  xor     r8d, r8d; nNumberOfArguments
0x1800ac5b7  mov     edx, esi; dwExceptionFlags
0x1800ac5b9  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800ac5be  call    cs:__imp_RaiseException
0x1800ac5c4  lea     r9, [rbp+string]; string
0x1800ac5c8  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800ac5cc  mov     edx, [rbp+length]; length
0x1800ac5cf  mov     rcx, rbx; sourceString
0x1800ac5d2  call    cs:__imp_WindowsCreateStringReference
0x1800ac5d8  lea     r8, [rbp+var_38]
0x1800ac5dc  mov     rdx, [rbp+string]
0x1800ac5e0  mov     rcx, r15
0x1800ac5e3  mov     rax, r12
0x1800ac5e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac5eb  mov     ebx, eax
0x1800ac5ed  test    eax, eax
0x1800ac5ef  jns     short loc_1800AC5FB
0x1800ac5f1  mov     edx, 30h ; '0'
0x1800ac5f6  jmp     loc_1800AC681
0x1800ac5fb  lea     rdx, aInitialize; "INITIALIZE"
0x1800ac602  lea     rcx, [rbp+string]; string
0x1800ac606  call    ??$?0$0L@@StringReference@Internal@Windows@@QEAA@AEAY0L@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[11])
0x1800ac60b  mov     rdx, rax; struct Windows::Internal::String *
0x1800ac60e  lea     rcx, [rbp+var_38]; this
0x1800ac612  call    ?CompareOrdinal@String@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::String::CompareOrdinal(Windows::Internal::String const &)
0x1800ac617  test    eax, eax
0x1800ac619  jnz     short loc_1800AC620
0x1800ac61b  mov     esi, r13d
0x1800ac61e  jmp     short loc_1800AC640
0x1800ac620  lea     rdx, aCleanup; "CLEANUP"
0x1800ac627  lea     rcx, [rbp+string]; string
0x1800ac62b  call    ??$?0$07@StringReference@Internal@Windows@@QEAA@AEAY07$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[8])
0x1800ac630  mov     rdx, rax; struct Windows::Internal::String *
0x1800ac633  lea     rcx, [rbp+var_38]; this
0x1800ac637  call    ?CompareOrdinal@String@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::String::CompareOrdinal(Windows::Internal::String const &)
0x1800ac63c  test    eax, eax
0x1800ac63e  jnz     short loc_1800AC693
0x1800ac640  mov     [rdi+68h], esi
0x1800ac643  lea     r8, [rdi+38h]
0x1800ac647  lea     rdx, aCallerapplicat; "CallerApplicationName"
0x1800ac64e  mov     rcx, r14
0x1800ac651  call    ?InitStringFromJson@FSServiceDrivenAction@@KAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; FSServiceDrivenAction::InitStringFromJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,ushort const *,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800ac656  mov     ebx, eax
0x1800ac658  test    eax, eax
0x1800ac65a  jns     short loc_1800AC663
0x1800ac65c  mov     edx, 3Eh ; '>'
0x1800ac661  jmp     short loc_1800AC681
0x1800ac663  lea     r8, [rdi+50h]
0x1800ac667  lea     rdx, aCorrelationvec; "CorrelationVector"
0x1800ac66e  mov     rcx, r14
0x1800ac671  call    ?InitStringFromJson@FSServiceDrivenAction@@KAJAEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; FSServiceDrivenAction::InitStringFromJson(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,ushort const *,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800ac676  mov     ebx, eax
0x1800ac678  test    eax, eax
0x1800ac67a  jns     short loc_1800AC686
0x1800ac67c  mov     edx, 3Fh ; '?'
0x1800ac681  mov     r9d, eax
0x1800ac684  jmp     short loc_1800AC6A0
0x1800ac686  lea     rcx, [rbp+var_38]; this
0x1800ac68a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800ac68f  xor     eax, eax
0x1800ac691  jmp     short loc_1800AC6BC
0x1800ac693  mov     ebx, 800BFA0Ch
0x1800ac698  mov     r9d, ebx; char *
0x1800ac69b  mov     edx, 3Bh ; ';'; void *
0x1800ac6a0  lea     r8, aOnecoreBaseFli_91; "onecore\\base\\flighting\\flightsetting"...
0x1800ac6a7  mov     rcx, [rbp+38h]; this
0x1800ac6ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac6b0  nop
0x1800ac6b1  lea     rcx, [rbp+var_38]; this
0x1800ac6b5  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800ac6ba  mov     eax, ebx
0x1800ac6bc  mov     rcx, [rbp+var_10]
0x1800ac6c0  xor     rcx, rsp; StackCookie
0x1800ac6c3  call    __security_check_cookie
0x1800ac6c8  mov     rbx, [rsp+70h+arg_10]
0x1800ac6d0  add     rsp, 70h
0x1800ac6d4  pop     r15
0x1800ac6d6  pop     r14
0x1800ac6d8  pop     r13
0x1800ac6da  pop     r12
0x1800ac6dc  pop     rdi
0x1800ac6dd  pop     rsi
0x1800ac6de  pop     rbp
0x1800ac6df  retn
```
