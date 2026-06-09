# SessionDataUtil::WUDeploymentSessionInfoWrapper::Initialize(ulong,wchar_t const *,_GUID,ulong,void const *,IUnknown *)

- ea: `0x18005e90c`
- end: `0x18005ec85`
- name: `?Initialize@WUDeploymentSessionInfoWrapper@SessionDataUtil@@AEAAJKPEB_WU_GUID@@KPEBXPEAUIUnknown@@@Z`
- size: `889`
- prototype: `int(SessionDataUtil::WUDeploymentSessionInfoWrapper *__hidden this, unsigned int, const wchar_t *, struct _GUID *__struct_ptr, unsigned int, const void *, struct IUnknown *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18005e764`

## callees

- `0x180003180`
- `0x180008f20`
- `0x18000dce4`
- `0x180054e84`
- `0x18005e254`
- `0x18005e90c`
- `0x18005ec8c`
- `0x18005efd4`
- `0x18005f1b4`
- `0x180061960`
- `0x180061d54`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ec3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ec3d`
- `RPCRT4!UuidFromStringW` at `0x18005eb3f`
- `RPCRT4!UuidFromStringW` at `0x18005eb3f`
- `RPCRT4!UuidToStringW` at `0x18005ead3`
- `RPCRT4!UuidToStringW` at `0x18005ead3`

## string_xrefs

- `0x18005ea94`: `SandboxPath`
- `0x18005eb17`: `InformationFactoryCLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall SessionDataUtil::WUDeploymentSessionInfoWrapper::Initialize(
        SessionDataUtil::WUDeploymentSessionInfoWrapper *this,
        __int64 a2,
        const wchar_t *a3,
        struct _GUID *a4,
        unsigned int a5,
        void *a6,
        struct IUnknown *a7)
{
  double v7; // xmm3_8
  UUID v10; // xmm6
  void **v11; // rdi
  void *v12; // rcx
  int v13; // eax
  const char *v14; // r9
  unsigned int Instance; // ebx
  __int64 v16; // rdx
  void *v17; // rbx
  struct IUnknownVtbl *lpVtbl; // rax
  int NumberPropertyWithDefault; // esi
  const wchar_t *v21; // r8
  __int64 v22; // rdx
  RPC_STATUS v23; // eax
  RPC_WSTR v24; // rdi
  __int64 v25; // rdx
  RPC_STATUS v26; // eax
  struct ABI::Windows::Data::Json::IJsonObject **v27; // r9
  int NamedObject; // eax
  struct IUnknown *v29; // rbx
  __int64 v30; // rdx
  void *v31; // rsi
  RPC_WSTR v32; // [rsp+20h] [rbp-40h] BYREF
  UUID *Uuid; // [rsp+28h] [rbp-38h] BYREF
  JsonUtil *v34; // [rsp+30h] [rbp-30h] BYREF
  RPC_WSTR StringUuid; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  Uuid = a4;
  v10 = *a4;
  *(_DWORD *)this = 1;
  v11 = (void **)((char *)this + 8);
  v12 = (void *)*((_QWORD *)this + 1);
  if ( v12 )
  {
    SusFree(v12);
    *v11 = 0;
  }
  v13 = DuplicateOptionalString<wchar_t const *,wchar_t *>(a3, v11);
  Instance = v13;
  if ( v13 < 0 )
  {
    v16 = 1010;
    v14 = (const char *)(unsigned int)v13;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      v14,
      (int)v32);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40C,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)Instance,
      (int)v32);
    return Instance;
  }
  *((UUID *)this + 1) = v10;
  if ( a6 )
  {
    v17 = (void *)*((_QWORD *)this + 4);
    if ( v17 )
    {
      SessionDataUtil::WUOptionalSessionInfoWrapper::~WUOptionalSessionInfoWrapper(*((SessionDataUtil::WUOptionalSessionInfoWrapper **)this
                                                                                   + 4));
      operator delete(v17, (const struct std::nothrow_t *)0x38);
      *((_QWORD *)this + 4) = 0;
    }
    Instance = SessionDataUtil::WUOptionalSessionInfoWrapper::CreateInstance(
                 a5,
                 a6,
                 0,
                 (struct SessionDataUtil::WUOptionalSessionInfoWrapper **)this + 4);
    v14 = (const char *)Instance;
    if ( (Instance & 0x80000000) != 0 )
    {
      v16 = 1019;
      goto LABEL_10;
    }
  }
  if ( !a7 )
    return 0;
  lpVtbl = a7->lpVtbl;
  v34 = 0;
  NumberPropertyWithDefault = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, JsonUtil **, const char *))lpVtbl->QueryInterface)(
                                a7,
                                &GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3,
                                &v34,
                                v14);
  if ( NumberPropertyWithDefault >= 0 )
  {
    NumberPropertyWithDefault = JsonUtil::GetNumberPropertyWithDefault(
                                  v34,
                                  (struct ABI::Windows::Data::Json::IJsonObject *)L"DeploymentSessionInfoVersion",
                                  v21,
                                  v7,
                                  0);
    if ( NumberPropertyWithDefault < 0 )
    {
      v22 = 1047;
      goto LABEL_21;
    }
    *(_DWORD *)this = (int)*(double *)&v32;
    if ( *v11 )
    {
      SusFree(*v11);
      *v11 = 0;
    }
    NumberPropertyWithDefault = JsonUtil::GetStringPropertyWithDefault(
                                  v34,
                                  (struct ABI::Windows::Data::Json::IJsonObject *)L"SandboxPath",
                                  a3,
                                  (wchar_t *)v11);
    if ( NumberPropertyWithDefault < 0 )
    {
      v22 = 1054;
      goto LABEL_21;
    }
    StringUuid = 0;
    v23 = UuidToStringW(Uuid, &StringUuid);
    NumberPropertyWithDefault = v23;
    if ( v23 >= 1 )
      NumberPropertyWithDefault = (unsigned __int16)v23 | 0x80010000;
    if ( NumberPropertyWithDefault < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x423,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
        (const char *)(unsigned int)NumberPropertyWithDefault,
        (int)v32);
LABEL_48:
      if ( StringUuid )
        CoTaskMemFree(StringUuid);
      goto LABEL_50;
    }
    *(double *)&v32 = 0.0;
    NumberPropertyWithDefault = JsonUtil::GetStringPropertyWithDefault(
                                  v34,
                                  (struct ABI::Windows::Data::Json::IJsonObject *)L"InformationFactoryCLSID",
                                  StringUuid,
                                  (wchar_t *)&v32);
    v24 = v32;
    if ( NumberPropertyWithDefault < 0 )
    {
      v25 = 1065;
LABEL_32:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
        (const char *)(unsigned int)NumberPropertyWithDefault,
        (int)v32);
      goto LABEL_46;
    }
    v26 = UuidFromStringW(v32, (UUID *)this + 1);
    NumberPropertyWithDefault = v26;
    if ( v26 >= 1 )
      NumberPropertyWithDefault = (unsigned __int16)v26 | 0x80010000;
    if ( NumberPropertyWithDefault < 0 )
    {
      v25 = 1069;
      goto LABEL_32;
    }
    if ( a6 )
    {
      Uuid = 0;
      NamedObject = JsonUtil::GetNamedObject(
                      v34,
                      (struct ABI::Windows::Data::Json::IJsonObject *)L"OptionalSessionInfo",
                      (const wchar_t *)&Uuid,
                      v27);
      NumberPropertyWithDefault = NamedObject;
      v29 = (struct IUnknown *)Uuid;
      if ( NamedObject < 0 )
      {
        v30 = 1077;
        goto LABEL_40;
      }
      v31 = (void *)*((_QWORD *)this + 4);
      if ( v31 )
      {
        SessionDataUtil::WUOptionalSessionInfoWrapper::~WUOptionalSessionInfoWrapper(*((SessionDataUtil::WUOptionalSessionInfoWrapper **)this
                                                                                     + 4));
        operator delete(v31, (const struct std::nothrow_t *)0x38);
        *((_QWORD *)this + 4) = 0;
      }
      NamedObject = SessionDataUtil::WUOptionalSessionInfoWrapper::CreateInstance(
                      a5,
                      a6,
                      v29,
                      (struct SessionDataUtil::WUOptionalSessionInfoWrapper **)this + 4);
      NumberPropertyWithDefault = NamedObject;
      if ( NamedObject < 0 )
      {
        v30 = 1083;
LABEL_40:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
          (const char *)(unsigned int)NamedObject,
          (int)v32);
        if ( v29 )
          ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->Release)(v29);
        goto LABEL_46;
      }
      if ( v29 )
        ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->Release)(v29);
    }
    NumberPropertyWithDefault = 0;
LABEL_46:
    if ( v24 )
      SusFree(v24);
    goto LABEL_48;
  }
  v22 = 1041;
LABEL_21:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v22,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
    (const char *)(unsigned int)NumberPropertyWithDefault,
    (int)v32);
LABEL_50:
  if ( v34 )
    (*(void (__fastcall **)(JsonUtil *))(*(_QWORD *)v34 + 16LL))(v34);
  return (unsigned int)NumberPropertyWithDefault;
}

```

## disassembly

```asm
0x18005e90c  mov     [rsp-38h+arg_8], rbx
0x18005e911  push    rbp
0x18005e912  push    rsi
0x18005e913  push    rdi
0x18005e914  push    r12
0x18005e916  push    r13
0x18005e918  push    r14
0x18005e91a  push    r15
0x18005e91c  mov     rbp, rsp
0x18005e91f  sub     rsp, 60h
0x18005e923  movaps  [rsp+60h+var_10], xmm6
0x18005e928  mov     rax, cs:__security_cookie
0x18005e92f  xor     rax, rsp
0x18005e932  mov     [rbp+var_20], rax
0x18005e936  mov     [rbp+Uuid], r9
0x18005e93a  mov     r13, r8
0x18005e93d  mov     r14, rcx
0x18005e940  mov     r15, [rbp+arg_28]
0x18005e944  mov     r12, [rbp+arg_30]
0x18005e948  movaps  xmm6, xmmword ptr [r9]
0x18005e94c  mov     dword ptr [rcx], 1
0x18005e952  lea     rdi, [rcx+8]
0x18005e956  mov     rcx, [rdi]; lpMem
0x18005e959  test    rcx, rcx
0x18005e95c  jz      short loc_18005E96A
0x18005e95e  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18005e963  mov     qword ptr [rdi], 0
0x18005e96a  mov     rdx, rdi
0x18005e96d  mov     rcx, r13
0x18005e970  call    ??$DuplicateOptionalString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x18005e975  mov     ebx, eax
0x18005e977  test    eax, eax
0x18005e979  jns     short loc_18005E985
0x18005e97b  mov     edx, 3F2h
0x18005e980  mov     r9d, eax
0x18005e983  jmp     short loc_18005E9D7
0x18005e985  movdqu  xmmword ptr [r14+10h], xmm6
0x18005e98b  test    r15, r15
0x18005e98e  jz      short loc_18005EA06
0x18005e990  lea     rsi, [r14+20h]
0x18005e994  mov     rbx, [rsi]
0x18005e997  test    rbx, rbx
0x18005e99a  jz      short loc_18005E9B8
0x18005e99c  mov     rcx, rbx; this
0x18005e99f  call    ??1WUOptionalSessionInfoWrapper@SessionDataUtil@@QEAA@XZ; SessionDataUtil::WUOptionalSessionInfoWrapper::~WUOptionalSessionInfoWrapper(void)
0x18005e9a4  mov     edx, 38h ; '8'; struct std::nothrow_t *
0x18005e9a9  mov     rcx, rbx; void *
0x18005e9ac  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005e9b1  mov     qword ptr [rsi], 0
0x18005e9b8  mov     r9, rsi; struct SessionDataUtil::WUOptionalSessionInfoWrapper **
0x18005e9bb  xor     r8d, r8d; struct IUnknown *
0x18005e9be  mov     rdx, r15; void *
0x18005e9c1  mov     ecx, [rbp+arg_20]; unsigned int
0x18005e9c4  call    ?CreateInstance@WUOptionalSessionInfoWrapper@SessionDataUtil@@SAJKPEBXPEAUIUnknown@@PEAPEAV12@@Z; SessionDataUtil::WUOptionalSessionInfoWrapper::CreateInstance(ulong,void const *,IUnknown *,SessionDataUtil::WUOptionalSessionInfoWrapper * *)
0x18005e9c9  mov     ebx, eax
0x18005e9cb  mov     r9d, eax; char *
0x18005e9ce  test    eax, eax
0x18005e9d0  jns     short loc_18005EA06
0x18005e9d2  mov     edx, 3FBh; void *
0x18005e9d7  mov     rcx, [rbp+38h]; this
0x18005e9db  lea     r8, aCW1SSrcClientL_14; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005e9e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e9e7  mov     rcx, [rbp+38h]; this
0x18005e9eb  mov     r9d, ebx; char *
0x18005e9ee  lea     r8, aCW1SSrcClientL_14; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005e9f5  mov     edx, 40Ch; void *
0x18005e9fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e9ff  mov     eax, ebx
0x18005ea01  jmp     loc_18005EC5C
0x18005ea06  test    r12, r12
0x18005ea09  jnz     short loc_18005EA12
0x18005ea0b  xor     eax, eax
0x18005ea0d  jmp     loc_18005EC5C
0x18005ea12  mov     rax, [r12]
0x18005ea16  mov     [rbp+var_30], 0
0x18005ea1e  lea     r8, [rbp+var_30]
0x18005ea22  lea     rdx, _GUID_064e24dd_29c2_4f83_9ac1_9ee11578beb3
0x18005ea29  mov     rcx, r12
0x18005ea2c  mov     rax, [rax]
0x18005ea2f  call    _guard_dispatch_icall
0x18005ea34  mov     esi, eax
0x18005ea36  xor     r12d, r12d
0x18005ea39  test    eax, eax
0x18005ea3b  jns     short loc_18005EA44
0x18005ea3d  mov     edx, 411h
0x18005ea42  jmp     short loc_18005EAAF
0x18005ea44  xorps   xmm0, xmm0
0x18005ea47  movsd   [rbp+var_40], xmm0
0x18005ea4c  lea     r9, [rbp+var_40]
0x18005ea50  movsd   xmm2, cs:__real@3ff0000000000000
0x18005ea58  lea     rdx, aDeploymentsess_0; "DeploymentSessionInfoVersion"
0x18005ea5f  mov     rcx, [rbp+var_30]; this
0x18005ea63  call    ?GetNumberPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WNPEAN@Z; JsonUtil::GetNumberPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,double,double *)
0x18005ea68  mov     esi, eax
0x18005ea6a  test    eax, eax
0x18005ea6c  jns     short loc_18005EA75
0x18005ea6e  mov     edx, 417h
0x18005ea73  jmp     short loc_18005EAAF
0x18005ea75  cvttsd2si rax, [rbp+var_40]
0x18005ea7b  mov     [r14], eax
0x18005ea7e  mov     rcx, [rdi]; lpMem
0x18005ea81  test    rcx, rcx
0x18005ea84  jz      short loc_18005EA8E
0x18005ea86  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18005ea8b  mov     [rdi], r12
0x18005ea8e  mov     r9, rdi; wchar_t *
0x18005ea91  mov     r8, r13; wchar_t *
0x18005ea94  lea     rdx, aSandboxpath; "SandboxPath"
0x18005ea9b  mov     rcx, [rbp+var_30]; this
0x18005ea9f  call    ?GetStringPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_W1PEAPEA_W@Z; JsonUtil::GetStringPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,wchar_t const *,wchar_t * *)
0x18005eaa4  mov     esi, eax
0x18005eaa6  test    eax, eax
0x18005eaa8  jns     short loc_18005EAC7
0x18005eaaa  mov     edx, 41Eh; void *
0x18005eaaf  mov     rcx, [rbp+38h]; this
0x18005eab3  mov     r9d, esi; char *
0x18005eab6  lea     r8, aCW1SSrcClientL_14; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005eabd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005eac2  jmp     loc_18005EC44
0x18005eac7  mov     [rbp+StringUuid], r12
0x18005eacb  lea     rdx, [rbp+StringUuid]; StringUuid
0x18005eacf  mov     rcx, [rbp+Uuid]; Uuid
0x18005ead3  call    cs:__imp_UuidToStringW
0x18005ead9  mov     esi, eax
0x18005eadb  mov     ebx, 80010000h
0x18005eae0  cmp     eax, 1
0x18005eae3  jl      short loc_18005EAEA
0x18005eae5  movzx   esi, ax
0x18005eae8  or      esi, ebx
0x18005eaea  test    esi, esi
0x18005eaec  jns     short loc_18005EB0B
0x18005eaee  mov     rcx, [rbp+38h]; this
0x18005eaf2  mov     r9d, esi; char *
0x18005eaf5  lea     r8, aCW1SSrcClientL_14; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005eafc  mov     edx, 423h; void *
0x18005eb01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005eb06  jmp     loc_18005EC34
0x18005eb0b  mov     [rbp+var_40], r12
0x18005eb0f  lea     r9, [rbp+var_40]; wchar_t *
0x18005eb13  mov     r8, [rbp+StringUuid]; wchar_t *
0x18005eb17  lea     rdx, aInformationfac; "InformationFactoryCLSID"
0x18005eb1e  mov     rcx, [rbp+var_30]; this
0x18005eb22  call    ?GetStringPropertyWithDefault@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_W1PEAPEA_W@Z; JsonUtil::GetStringPropertyWithDefault(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,wchar_t const *,wchar_t * *)
0x18005eb27  mov     esi, eax
0x18005eb29  mov     rdi, [rbp+var_40]
0x18005eb2d  test    eax, eax
0x18005eb2f  jns     short loc_18005EB38
0x18005eb31  mov     edx, 429h
0x18005eb36  jmp     short loc_18005EB5A
0x18005eb38  lea     rdx, [r14+10h]; Uuid
0x18005eb3c  mov     rcx, rdi; StringUuid
0x18005eb3f  call    cs:__imp_UuidFromStringW
0x18005eb45  mov     esi, eax
0x18005eb47  cmp     eax, 1
0x18005eb4a  jl      short loc_18005EB51
0x18005eb4c  movzx   esi, ax
0x18005eb4f  or      esi, ebx
0x18005eb51  test    esi, esi
0x18005eb53  jns     short loc_18005EB72
0x18005eb55  mov     edx, 42Dh; void *
0x18005eb5a  mov     rcx, [rbp+38h]; this
0x18005eb5e  mov     r9d, esi; char *
0x18005eb61  lea     r8, aCW1SSrcClientL_14; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005eb68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005eb6d  jmp     loc_18005EC26
0x18005eb72  test    r15, r15
0x18005eb75  jz      loc_18005EC23
0x18005eb7b  mov     [rbp+Uuid], r12
0x18005eb7f  lea     r8, [rbp+Uuid]; wchar_t *
0x18005eb83  lea     rdx, aOptionalsessio_1; "OptionalSessionInfo"
0x18005eb8a  mov     rcx, [rbp+var_30]; this
0x18005eb8e  call    ?GetNamedObject@JsonUtil@@YAJPEAUIJsonObject@Json@Data@Windows@ABI@@PEB_WPEAPEAU23456@@Z; JsonUtil::GetNamedObject(ABI::Windows::Data::Json::IJsonObject *,wchar_t const *,ABI::Windows::Data::Json::IJsonObject * *)
0x18005eb93  mov     esi, eax
0x18005eb95  mov     rbx, [rbp+Uuid]
0x18005eb99  test    eax, eax
0x18005eb9b  jns     short loc_18005EBA4
0x18005eb9d  mov     edx, 435h
0x18005eba2  jmp     short loc_18005EBE3
0x18005eba4  mov     rsi, [r14+20h]
0x18005eba8  test    rsi, rsi
0x18005ebab  jz      short loc_18005EBC6
0x18005ebad  mov     rcx, rsi; this
0x18005ebb0  call    ??1WUOptionalSessionInfoWrapper@SessionDataUtil@@QEAA@XZ; SessionDataUtil::WUOptionalSessionInfoWrapper::~WUOptionalSessionInfoWrapper(void)
0x18005ebb5  mov     edx, 38h ; '8'; struct std::nothrow_t *
0x18005ebba  mov     rcx, rsi; void *
0x18005ebbd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005ebc2  mov     [r14+20h], r12
0x18005ebc6  lea     r9, [r14+20h]; struct SessionDataUtil::WUOptionalSessionInfoWrapper **
0x18005ebca  mov     r8, rbx; struct IUnknown *
0x18005ebcd  mov     rdx, r15; void *
0x18005ebd0  mov     ecx, [rbp+arg_20]; unsigned int
0x18005ebd3  call    ?CreateInstance@WUOptionalSessionInfoWrapper@SessionDataUtil@@SAJKPEBXPEAUIUnknown@@PEAPEAV12@@Z; SessionDataUtil::WUOptionalSessionInfoWrapper::CreateInstance(ulong,void const *,IUnknown *,SessionDataUtil::WUOptionalSessionInfoWrapper * *)
0x18005ebd8  mov     esi, eax
0x18005ebda  test    eax, eax
0x18005ebdc  jns     short loc_18005EC0E
0x18005ebde  mov     edx, 43Bh; void *
0x18005ebe3  mov     r9d, eax; char *
0x18005ebe6  lea     r8, aCW1SSrcClientL_14; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18005ebed  mov     rcx, [rbp+38h]; this
0x18005ebf1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ebf6  nop
0x18005ebf7  test    rbx, rbx
0x18005ebfa  jz      short loc_18005EC0C
0x18005ebfc  mov     rax, [rbx]
0x18005ebff  mov     rcx, rbx
0x18005ec02  mov     rax, [rax+10h]
0x18005ec06  call    _guard_dispatch_icall
0x18005ec0b  nop
0x18005ec0c  jmp     short loc_18005EC26
0x18005ec0e  test    rbx, rbx
0x18005ec11  jz      short loc_18005EC23
0x18005ec13  mov     rax, [rbx]
0x18005ec16  mov     rcx, rbx
0x18005ec19  mov     rax, [rax+10h]
0x18005ec1d  call    _guard_dispatch_icall
0x18005ec22  nop
0x18005ec23  mov     esi, r12d
0x18005ec26  test    rdi, rdi
0x18005ec29  jz      short loc_18005EC34
0x18005ec2b  mov     rcx, rdi; lpMem
0x18005ec2e  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18005ec33  nop
0x18005ec34  mov     rcx, [rbp+StringUuid]; pv
0x18005ec38  test    rcx, rcx
0x18005ec3b  jz      short loc_18005EC44
0x18005ec3d  call    cs:__imp_CoTaskMemFree
0x18005ec43  nop
0x18005ec44  mov     rcx, [rbp+var_30]
0x18005ec48  test    rcx, rcx
0x18005ec4b  jz      short loc_18005EC5A
0x18005ec4d  mov     rdx, [rcx]
0x18005ec50  mov     rax, [rdx+10h]
0x18005ec54  call    _guard_dispatch_icall
0x18005ec59  nop
0x18005ec5a  mov     eax, esi
0x18005ec5c  mov     rcx, [rbp+var_20]
0x18005ec60  xor     rcx, rsp; StackCookie
0x18005ec63  call    __security_check_cookie
0x18005ec68  mov     rbx, [rsp+60h+arg_8]
0x18005ec70  movaps  xmm6, [rsp+60h+var_10]
0x18005ec75  add     rsp, 60h
0x18005ec79  pop     r15
0x18005ec7b  pop     r14
0x18005ec7d  pop     r13
0x18005ec7f  pop     r12
0x18005ec81  pop     rdi
0x18005ec82  pop     rsi
0x18005ec83  pop     rbp
0x18005ec84  retn
```
