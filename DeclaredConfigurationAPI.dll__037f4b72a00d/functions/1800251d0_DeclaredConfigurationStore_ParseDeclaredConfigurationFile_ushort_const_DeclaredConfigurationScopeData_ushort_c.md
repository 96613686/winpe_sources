# DeclaredConfigurationStore_ParseDeclaredConfigurationFile(ushort const *,DeclaredConfigurationScopeData *,ushort const *,DCDocument &)

- ea: `0x1800251d0`
- end: `0x180025707`
- name: `?DeclaredConfigurationStore_ParseDeclaredConfigurationFile@@YAJPEBGPEAUDeclaredConfigurationScopeData@@0AEAVDCDocument@@@Z`
- size: `1335`
- prototype: `int(const unsigned __int16 *, struct DeclaredConfigurationScopeData *, const unsigned __int16 *, struct DCDocument *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801223f0`

## callees

- `0x18000b9e0`
- `0x18000c8f4`
- `0x1800117dc`
- `0x18001c704`
- `0x18001c9a4`
- `0x18001cd00`
- `0x18001e56c`
- `0x1800251d0`
- `0x1800370d4`
- `0x180048cd8`
- `0x18004a660`
- `0x18004a76c`
- `0x1800f5c8c`
- `0x1800f64a4`
- `0x180139010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180025556`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180025584`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800255b7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180025556`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180025584`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800255b7`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180025282`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180025282`
- `XmlLite!CreateXmlReader` at `0x1800253ab`
- `XmlLite!CreateXmlReader` at `0x1800253ab`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x180025345`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x180025345`

## string_xrefs

- `0x180025299`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x1800252e8`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x18002535c`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x1800253c2`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x180025427`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x18002548a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x1800254f2`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x1800255f1`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`
- `0x18002565b`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcparse.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall DeclaredConfigurationStore_ParseDeclaredConfigurationFile(
        unsigned __int16 *a1,
        struct DeclaredConfigurationScopeData *a2,
        const unsigned __int16 *a3,
        struct DCDocument *a4)
{
  CDeclaredConfigurationLogger *Logger; // rax
  HRESULT v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  HRESULT v10; // eax
  HRESULT v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  struct DCDocument *v15; // rcx
  char *v16; // rbx
  char *v17; // rdx
  int IsAllowed; // eax
  struct DeclaredConfigurationScopeData *v19; // rcx
  int v20; // eax
  int pwszBaseUri; // [rsp+20h] [rbp-E0h]
  int pwszBaseUria; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+30h] [rbp-D0h] BYREF
  void *ppvObject; // [rsp+38h] [rbp-C8h] BYREF
  IXmlReaderInput *ppInput; // [rsp+40h] [rbp-C0h] BYREF
  struct DeclaredConfigurationScopeData *v27; // [rsp+48h] [rbp-B8h] BYREF
  IStream *ppstm; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v29[5]; // [rsp+58h] [rbp-A8h] BYREF
  char v30; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v31; // [rsp+88h] [rbp-78h] BYREF
  __int64 v32; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v33[3]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v34[56]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v35[16]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v36; // [rsp+100h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v31 = a1;
  v27 = a2;
  v24 = 0;
  v32 = 0;
  memset_0(v35, 0, 0x50u);
  Logger = CDeclaredConfigurationLogger::GetLogger();
  CDeclaredConfigurationLogger::LogDeclaredConfigurationBeginDCParsingFromFileEvent(
    Logger,
    v31,
    *(const unsigned __int16 **)v27,
    *((const unsigned __int16 **)v27 + 1),
    *((_DWORD *)v27 + 4),
    *((_DWORD *)v27 + 5));
  ppstm = 0;
  v29[0] = a4;
  v29[1] = &v31;
  v29[2] = &v27;
  v29[3] = &v32;
  v29[4] = &v24;
  v30 = 1;
  v7 = SHCreateStreamOnFileW(a3, 0, &ppstm);
  v8 = v7;
  v24 = v7;
  if ( v7 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(IStream *, _BYTE *, _QWORD))(*(_QWORD *)ppstm + 96LL))(ppstm, v35, 0);
    v8 = v9;
    v24 = v9;
    if ( v9 >= 0 )
    {
      v32 = v36;
      ppInput = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
      v10 = CreateXmlReaderInputWithEncodingName((IUnknown *)ppstm, 0, L"UTF-8", 0, 0, &ppInput);
      v8 = v10;
      v24 = v10;
      if ( v10 >= 0 )
      {
        ppvObject = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
        v11 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
        v8 = v11;
        v24 = v11;
        if ( v11 >= 0 )
        {
          v12 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
          v8 = v12;
          v24 = v12;
          if ( v12 >= 0 )
          {
            v13 = (*(__int64 (__fastcall **)(void *, IXmlReaderInput *))(*(_QWORD *)ppvObject + 24LL))(
                    ppvObject,
                    ppInput);
            v8 = v13;
            v24 = v13;
            if ( v13 >= 0 )
            {
              ParseDCCSPPayload::ParseDCCSPPayload((ParseDCCSPPayload *)v33, (struct IXmlReader *)ppvObject, a4);
              v14 = XmlParseFactory::ParseXmlNodesTypes((XmlParseFactory *)v33);
              v8 = v14;
              v24 = v14;
              if ( v14 >= 0 )
              {
                if ( *((_QWORD *)a4 + 3) <= 7u )
                  v15 = a4;
                else
                  v15 = *(struct DCDocument **)a4;
                if ( (unsigned int)_o__wcsicmp(v15, v31) )
                {
                  v24 = -2102460415;
                }
                else
                {
                  v16 = (char *)a4 + 32;
                  if ( *((_QWORD *)a4 + 7) <= 7u )
                    v17 = (char *)a4 + 32;
                  else
                    v17 = *(char **)v16;
                  if ( (unsigned int)_o__wcsicmp(L"User", v17) )
                  {
                    if ( *((_QWORD *)a4 + 7) > 7u )
                      v16 = *(char **)v16;
                    if ( !(unsigned int)_o__wcsicmp(L"Device", v16) && *((_DWORD *)v27 + 4) )
                      v24 = -2102460413;
                  }
                  else if ( *((_DWORD *)v27 + 4) != 1 )
                  {
                    v24 = -2102460414;
                  }
                }
                IsAllowed = ValidateConfigurationProviderIsAllowed(v27, a4);
                v8 = IsAllowed;
                v24 = IsAllowed;
                if ( IsAllowed >= 0 )
                {
                  v20 = ValidateOSDefinedScenarioCapabilities(v19, a4);
                  v8 = v20;
                  v24 = v20;
                  if ( v20 < 0 )
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x7B6,
                      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
                      (const char *)(unsigned int)v20,
                      pwszBaseUria);
                  v33[0] = &XmlParseFactory::`vftable';
                  std::deque<std::wstring>::~deque<std::wstring>(v34);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
                  v30 = 0;
                  lambda_89f51b290cec3f29a4c36ce8d3079ece_::operator()(v29);
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x7B0,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
                    (const char *)(unsigned int)IsAllowed,
                    pwszBaseUria);
                  v33[0] = &XmlParseFactory::`vftable';
                  std::deque<std::wstring>::~deque<std::wstring>(v34);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
                  v30 = 0;
                  lambda_89f51b290cec3f29a4c36ce8d3079ece_::operator()(v29);
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x798,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
                  (const char *)(unsigned int)v14,
                  pwszBaseUria);
                v33[0] = &XmlParseFactory::`vftable';
                std::deque<std::wstring>::~deque<std::wstring>(v34);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
                v30 = 0;
                lambda_89f51b290cec3f29a4c36ce8d3079ece_::operator()(v29);
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x793,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
                (const char *)(unsigned int)v13,
                pwszBaseUria);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
              v30 = 0;
              lambda_89f51b290cec3f29a4c36ce8d3079ece_::operator()(v29);
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x790,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
              (const char *)(unsigned int)v12,
              pwszBaseUria);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
            v30 = 0;
            lambda_89f51b290cec3f29a4c36ce8d3079ece_::operator()(v29);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x78D,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
            (const char *)(unsigned int)v11,
            pwszBaseUria);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
          v30 = 0;
          lambda_89f51b290cec3f29a4c36ce8d3079ece_::operator()(v29);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x789,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
          (const char *)(unsigned int)v10,
          pwszBaseUria);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
        v30 = 0;
        lambda_89f51b290cec3f29a4c36ce8d3079ece_::operator()(v29);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x781,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
        (const char *)(unsigned int)v9,
        pwszBaseUri);
      v30 = 0;
      lambda_89f51b290cec3f29a4c36ce8d3079ece_::operator()(v29);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x77E,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcparse.cpp",
      (const char *)(unsigned int)v7,
      pwszBaseUri);
    v30 = 0;
    lambda_89f51b290cec3f29a4c36ce8d3079ece_::operator()(v29);
  }
  ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&ppstm);
  return v8;
}

```

## disassembly

```asm
0x1800251d0  push    rbp
0x1800251d2  push    rbx
0x1800251d3  push    rsi
0x1800251d4  push    rdi
0x1800251d5  lea     rbp, [rsp-58h]
0x1800251da  sub     rsp, 158h
0x1800251e1  mov     rax, cs:__security_cookie
0x1800251e8  xor     rax, rsp
0x1800251eb  mov     [rbp+70h+var_30], rax
0x1800251ef  mov     rdi, r9
0x1800251f2  mov     rbx, r8
0x1800251f5  mov     [rbp+70h+var_E8], rcx
0x1800251f9  mov     [rsp+170h+var_128], rdx
0x1800251fe  xor     esi, esi
0x180025200  mov     [rsp+170h+var_140], esi
0x180025204  mov     [rbp+70h+var_E0], rsi
0x180025208  xor     edx, edx; Val
0x18002520a  lea     r8d, [rsi+50h]; Size
0x18002520e  lea     rcx, [rbp+70h+var_80]; void *
0x180025212  call    memset_0
0x180025217  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x18002521c  mov     r8, [rsp+170h+var_128]
0x180025221  mov     ecx, [r8+14h]
0x180025225  mov     dword ptr [rsp+170h+ppInput], ecx; unsigned int
0x180025229  mov     ecx, [r8+10h]
0x18002522d  mov     dword ptr [rsp+170h+pwszBaseUri], ecx; int
0x180025231  mov     r9, [r8+8]; unsigned __int16 *
0x180025235  mov     r8, [r8]; unsigned __int16 *
0x180025238  mov     rdx, [rbp+70h+var_E8]; unsigned __int16 *
0x18002523c  mov     rcx, rax; this
0x18002523f  call    ?LogDeclaredConfigurationBeginDCParsingFromFileEvent@CDeclaredConfigurationLogger@@QEAAXPEBG00KK@Z; CDeclaredConfigurationLogger::LogDeclaredConfigurationBeginDCParsingFromFileEvent(ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180025244  mov     [rsp+170h+ppstm], rsi
0x180025249  mov     [rsp+170h+var_118], rdi
0x18002524e  lea     rax, [rbp+70h+var_E8]
0x180025252  mov     [rsp+170h+var_110], rax
0x180025257  lea     rax, [rsp+170h+var_128]
0x18002525c  mov     [rsp+170h+var_108], rax
0x180025261  lea     rax, [rbp+70h+var_E0]
0x180025265  mov     [rsp+170h+var_100], rax
0x18002526a  lea     rax, [rsp+170h+var_140]
0x18002526f  mov     [rsp+170h+var_F8], rax
0x180025274  mov     [rbp+70h+var_F0], 1
0x180025278  lea     r8, [rsp+170h+ppstm]; ppstm
0x18002527d  xor     edx, edx; grfMode
0x18002527f  mov     rcx, rbx; pszFile
0x180025282  call    cs:__imp_SHCreateStreamOnFileW
0x180025288  mov     ebx, eax
0x18002528a  mov     [rsp+170h+var_140], eax
0x18002528e  test    eax, eax
0x180025290  jns     short loc_1800252BF
0x180025292  mov     rcx, [rbp+78h]; this
0x180025296  mov     r9d, eax; char *
0x180025299  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800252a0  mov     edx, 77Eh; void *
0x1800252a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800252aa  nop
0x1800252ab  mov     [rbp+70h+var_F0], sil
0x1800252af  lea     rcx, [rsp+170h+var_118]
0x1800252b4  call    _lambda_89f51b290cec3f29a4c36ce8d3079ece___operator__
0x1800252b9  nop
0x1800252ba  jmp     loc_1800256E3
0x1800252bf  mov     rcx, [rsp+170h+ppstm]
0x1800252c4  mov     rax, [rcx]
0x1800252c7  xor     r8d, r8d
0x1800252ca  lea     rdx, [rbp+70h+var_80]
0x1800252ce  mov     rax, [rax+60h]
0x1800252d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252d7  mov     ebx, eax
0x1800252d9  mov     [rsp+170h+var_140], eax
0x1800252dd  test    eax, eax
0x1800252df  jns     short loc_18002530E
0x1800252e1  mov     rcx, [rbp+78h]; this
0x1800252e5  mov     r9d, eax; char *
0x1800252e8  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800252ef  mov     edx, 781h; void *
0x1800252f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800252f9  nop
0x1800252fa  mov     [rbp+70h+var_F0], sil
0x1800252fe  lea     rcx, [rsp+170h+var_118]
0x180025303  call    _lambda_89f51b290cec3f29a4c36ce8d3079ece___operator__
0x180025308  nop
0x180025309  jmp     loc_1800256E3
0x18002530e  mov     rax, [rbp+70h+var_70]
0x180025312  mov     [rbp+70h+var_E0], rax
0x180025316  mov     [rsp+170h+var_130], rsi
0x18002531b  lea     rcx, [rsp+170h+var_130]
0x180025320  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025325  lea     rax, [rsp+170h+var_130]
0x18002532a  mov     [rsp+170h+ppInput], rax; ppInput
0x18002532f  mov     [rsp+170h+pwszBaseUri], rsi; int
0x180025334  xor     r9d, r9d; fEncodingHint
0x180025337  lea     r8, aUtf8; "UTF-8"
0x18002533e  xor     edx, edx; pMalloc
0x180025340  mov     rcx, [rsp+170h+ppstm]; pInputStream
0x180025345  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x18002534b  mov     ebx, eax
0x18002534d  mov     [rsp+170h+var_140], eax
0x180025351  test    eax, eax
0x180025353  jns     short loc_18002538D
0x180025355  mov     rcx, [rbp+78h]; this
0x180025359  mov     r9d, eax; char *
0x18002535c  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180025363  mov     edx, 789h; void *
0x180025368  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002536d  nop
0x18002536e  lea     rcx, [rsp+170h+var_130]
0x180025373  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025378  nop
0x180025379  mov     [rbp+70h+var_F0], sil
0x18002537d  lea     rcx, [rsp+170h+var_118]
0x180025382  call    _lambda_89f51b290cec3f29a4c36ce8d3079ece___operator__
0x180025387  nop
0x180025388  jmp     loc_1800256E3
0x18002538d  mov     [rsp+170h+ppvObject], rsi
0x180025392  lea     rcx, [rsp+170h+ppvObject]
0x180025397  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002539c  xor     r8d, r8d; pMalloc
0x18002539f  lea     rdx, [rsp+170h+ppvObject]; ppvObject
0x1800253a4  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1800253ab  call    cs:__imp_CreateXmlReader
0x1800253b1  mov     ebx, eax
0x1800253b3  mov     [rsp+170h+var_140], eax
0x1800253b7  test    eax, eax
0x1800253b9  jns     short loc_1800253FE
0x1800253bb  mov     rcx, [rbp+78h]; this
0x1800253bf  mov     r9d, eax; char *
0x1800253c2  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800253c9  mov     edx, 78Dh; void *
0x1800253ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800253d3  nop
0x1800253d4  lea     rcx, [rsp+170h+ppvObject]
0x1800253d9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800253de  nop
0x1800253df  lea     rcx, [rsp+170h+var_130]
0x1800253e4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800253e9  nop
0x1800253ea  mov     [rbp+70h+var_F0], sil
0x1800253ee  lea     rcx, [rsp+170h+var_118]
0x1800253f3  call    _lambda_89f51b290cec3f29a4c36ce8d3079ece___operator__
0x1800253f8  nop
0x1800253f9  jmp     loc_1800256E3
0x1800253fe  mov     rcx, [rsp+170h+ppvObject]
0x180025403  mov     rax, [rcx]
0x180025406  xor     r8d, r8d
0x180025409  lea     edx, [r8+4]
0x18002540d  mov     rax, [rax+28h]
0x180025411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025416  mov     ebx, eax
0x180025418  mov     [rsp+170h+var_140], eax
0x18002541c  test    eax, eax
0x18002541e  jns     short loc_180025463
0x180025420  mov     rcx, [rbp+78h]; this
0x180025424  mov     r9d, eax; char *
0x180025427  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18002542e  mov     edx, 790h; void *
0x180025433  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025438  nop
0x180025439  lea     rcx, [rsp+170h+ppvObject]
0x18002543e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025443  nop
0x180025444  lea     rcx, [rsp+170h+var_130]
0x180025449  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002544e  nop
0x18002544f  mov     [rbp+70h+var_F0], sil
0x180025453  lea     rcx, [rsp+170h+var_118]
0x180025458  call    _lambda_89f51b290cec3f29a4c36ce8d3079ece___operator__
0x18002545d  nop
0x18002545e  jmp     loc_1800256E3
0x180025463  mov     rcx, [rsp+170h+ppvObject]
0x180025468  mov     rax, [rcx]
0x18002546b  mov     rdx, [rsp+170h+var_130]
0x180025470  mov     rax, [rax+18h]
0x180025474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025479  mov     ebx, eax
0x18002547b  mov     [rsp+170h+var_140], eax
0x18002547f  test    eax, eax
0x180025481  jns     short loc_1800254C6
0x180025483  mov     rcx, [rbp+78h]; this
0x180025487  mov     r9d, eax; char *
0x18002548a  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180025491  mov     edx, 793h; void *
0x180025496  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002549b  nop
0x18002549c  lea     rcx, [rsp+170h+ppvObject]
0x1800254a1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800254a6  nop
0x1800254a7  lea     rcx, [rsp+170h+var_130]
0x1800254ac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800254b1  nop
0x1800254b2  mov     [rbp+70h+var_F0], sil
0x1800254b6  lea     rcx, [rsp+170h+var_118]
0x1800254bb  call    _lambda_89f51b290cec3f29a4c36ce8d3079ece___operator__
0x1800254c0  nop
0x1800254c1  jmp     loc_1800256E3
0x1800254c6  mov     r8, rdi; struct DCDocument *
0x1800254c9  mov     rdx, [rsp+170h+ppvObject]; struct IXmlReader *
0x1800254ce  lea     rcx, [rbp+70h+var_D0]; this
0x1800254d2  call    ??0ParseDCCSPPayload@@QEAA@PEAUIXmlReader@@AEAVDCDocument@@@Z; ParseDCCSPPayload::ParseDCCSPPayload(IXmlReader *,DCDocument &)
0x1800254d7  nop
0x1800254d8  lea     rcx, [rbp+70h+var_D0]; this
0x1800254dc  call    ?ParseXmlNodesTypes@XmlParseFactory@@QEAAJXZ; XmlParseFactory::ParseXmlNodesTypes(void)
0x1800254e1  mov     ebx, eax
0x1800254e3  mov     [rsp+170h+var_140], eax
0x1800254e7  test    eax, eax
0x1800254e9  jns     short loc_180025543
0x1800254eb  mov     rcx, [rbp+78h]; this
0x1800254ef  mov     r9d, eax; char *
0x1800254f2  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800254f9  mov     edx, 798h; void *
0x1800254fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025503  nop
0x180025504  lea     rax, ??_7XmlParseFactory@@6B@; const XmlParseFactory::`vftable'
0x18002550b  mov     [rbp+70h+var_D0], rax
0x18002550f  lea     rcx, [rbp+70h+var_B8]
0x180025513  call    ??1?$deque@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::deque<std::wstring>::~deque<std::wstring>(void)
0x180025518  nop
0x180025519  lea     rcx, [rsp+170h+ppvObject]
0x18002551e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025523  nop
0x180025524  lea     rcx, [rsp+170h+var_130]
0x180025529  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002552e  nop
0x18002552f  mov     [rbp+70h+var_F0], sil
0x180025533  lea     rcx, [rsp+170h+var_118]
0x180025538  call    _lambda_89f51b290cec3f29a4c36ce8d3079ece___operator__
0x18002553d  nop
0x18002553e  jmp     loc_1800256E3
0x180025543  cmp     qword ptr [rdi+18h], 7
0x180025548  jbe     short loc_18002554F
0x18002554a  mov     rcx, [rdi]
0x18002554d  jmp     short loc_180025552
0x18002554f  mov     rcx, rdi
0x180025552  mov     rdx, [rbp+70h+var_E8]
0x180025556  call    cs:__imp__o__wcsicmp
0x18002555c  test    eax, eax
0x18002555e  jz      short loc_18002556A
0x180025560  mov     [rsp+170h+var_140], 82AF0001h
0x180025568  jmp     short loc_1800255D3
0x18002556a  lea     rbx, [rdi+20h]
0x18002556e  cmp     qword ptr [rbx+18h], 7
0x180025573  jbe     short loc_18002557A
0x180025575  mov     rdx, [rbx]
0x180025578  jmp     short loc_18002557D
0x18002557a  mov     rdx, rbx
0x18002557d  lea     rcx, aUser_4; "User"
0x180025584  call    cs:__imp__o__wcsicmp
0x18002558a  test    eax, eax
0x18002558c  jnz     short loc_1800255A3
0x18002558e  mov     rax, [rsp+170h+var_128]
0x180025593  cmp     dword ptr [rax+10h], 1
0x180025597  jz      short loc_1800255D3
0x180025599  mov     [rsp+170h+var_140], 82AF0002h
0x1800255a1  jmp     short loc_1800255D3
0x1800255a3  cmp     qword ptr [rbx+18h], 7
0x1800255a8  jbe     short loc_1800255AD
0x1800255aa  mov     rbx, [rbx]
0x1800255ad  mov     rdx, rbx
0x1800255b0  lea     rcx, aDevice_2; "Device"
0x1800255b7  call    cs:__imp__o__wcsicmp
0x1800255bd  test    eax, eax
0x1800255bf  jnz     short loc_1800255D3
0x1800255c1  mov     rax, [rsp+170h+var_128]
0x1800255c6  cmp     [rax+10h], esi
0x1800255c9  jz      short loc_1800255D3
0x1800255cb  mov     [rsp+170h+var_140], 82AF0003h
0x1800255d3  mov     rdx, rdi; struct DCDocument *
0x1800255d6  mov     rcx, [rsp+170h+var_128]; struct DeclaredConfigurationScopeData *
0x1800255db  call    ?ValidateConfigurationProviderIsAllowed@@YAJPEAUDeclaredConfigurationScopeData@@AEAVDCDocument@@@Z; ValidateConfigurationProviderIsAllowed(DeclaredConfigurationScopeData *,DCDocument &)
0x1800255e0  mov     ebx, eax
0x1800255e2  mov     [rsp+170h+var_140], eax
0x1800255e6  test    eax, eax
0x1800255e8  jns     short loc_180025642
0x1800255ea  mov     rcx, [rbp+78h]; this
0x1800255ee  mov     r9d, eax; char *
0x1800255f1  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800255f8  mov     edx, 7B0h; void *
0x1800255fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025602  nop
0x180025603  lea     rax, ??_7XmlParseFactory@@6B@; const XmlParseFactory::`vftable'
0x18002560a  mov     [rbp+70h+var_D0], rax
0x18002560e  lea     rcx, [rbp+70h+var_B8]
0x180025612  call    ??1?$deque@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::deque<std::wstring>::~deque<std::wstring>(void)
0x180025617  nop
0x180025618  lea     rcx, [rsp+170h+ppvObject]
0x18002561d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025622  nop
0x180025623  lea     rcx, [rsp+170h+var_130]
0x180025628  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002562d  nop
0x18002562e  mov     [rbp+70h+var_F0], sil
0x180025632  lea     rcx, [rsp+170h+var_118]
0x180025637  call    _lambda_89f51b290cec3f29a4c36ce8d3079ece___operator__
0x18002563c  nop
0x18002563d  jmp     loc_1800256E3
0x180025642  mov     rdx, rdi; struct DCDocument *
0x180025645  call    ?ValidateOSDefinedScenarioCapabilities@@YAJPEAUDeclaredConfigurationScopeData@@AEAVDCDocument@@@Z; ValidateOSDefinedScenarioCapabilities(DeclaredConfigurationScopeData *,DCDocument &)
0x18002564a  mov     ebx, eax
0x18002564c  mov     [rsp+170h+var_140], eax
0x180025650  test    eax, eax
0x180025652  jns     short loc_1800256A9
  ... truncated ...
```
