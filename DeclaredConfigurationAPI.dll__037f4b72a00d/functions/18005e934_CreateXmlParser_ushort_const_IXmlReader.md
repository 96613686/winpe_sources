# CreateXmlParser(ushort const *,IXmlReader * *)

- ea: `0x18005e934`
- end: `0x18005ebe7`
- name: `?CreateXmlParser@@YAJPEBGPEAPEAUIXmlReader@@@Z`
- size: `691`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IXmlReader **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180080e90`

## callees

- `0x1800117dc`
- `0x18001f7e8`
- `0x1800370d4`
- `0x18004a5d4`
- `0x18004a630`
- `0x18005e934`
- `0x180139010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18005e9b4`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18005e9b4`
- `XmlLite!CreateXmlReader` at `0x18005ea8b`
- `XmlLite!CreateXmlReader` at `0x18005ea8b`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x18005ea21`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x18005ea21`

## string_xrefs

- `0x18005e972`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18005e9db`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18005ea34`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18005ea9e`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18005eaff`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18005eb60`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CreateXmlParser(const unsigned __int16 *a1, struct IXmlReader **a2)
{
  unsigned __int64 v3; // rdx
  int v4; // ebx
  __int64 v5; // rdx
  const BYTE *v7; // r11
  IStream *v8; // rax
  IUnknown *v9; // rbx
  HRESULT v10; // eax
  unsigned int v11; // edi
  HRESULT v12; // eax
  int v13; // eax
  int v14; // eax
  struct IXmlReader *v15; // rax
  int pwszBaseUri; // [rsp+20h] [rbp-20h]
  int pwszBaseUria; // [rsp+20h] [rbp-20h]
  IUnknown *pInputStream; // [rsp+30h] [rbp-10h] BYREF
  UINT cbInit[2]; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  void *ppvObject; // [rsp+70h] [rbp+30h] BYREF
  IXmlReaderInput *ppInput; // [rsp+78h] [rbp+38h] BYREF

  *(_QWORD *)cbInit = 0;
  pInputStream = 0;
  v4 = StringCchLengthW(a1, 0x7FFFFFFFu, (unsigned __int64 *)&pInputStream);
  if ( v4 < 0 )
  {
    v5 = 18404;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)(unsigned int)v4,
      pwszBaseUri);
    return (unsigned int)v4;
  }
  v4 = ULongLongMult((unsigned __int64)pInputStream, v3, (unsigned __int64 *)cbInit);
  if ( v4 < 0 )
  {
    v5 = 18405;
    goto LABEL_3;
  }
  pInputStream = 0;
  v8 = SHCreateMemStream(v7, cbInit[0]);
  Microsoft::WRL::ComPtr<IStream>::Attach(&pInputStream, v8);
  v9 = pInputStream;
  if ( !pInputStream )
  {
    v4 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47E9,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)0x8007000ELL,
      pwszBaseUri);
    return (unsigned int)v4;
  }
  ppInput = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
  v10 = CreateXmlReaderInputWithEncodingName(v9, 0, L"UTF-16", 0, 0, &ppInput);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47EC,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)(unsigned int)v10,
      pwszBaseUria);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
    if ( v9 )
      ((void (__fastcall *)(IUnknown *))v9->lpVtbl->Release)(v9);
    return v11;
  }
  ppvObject = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
  v12 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v11 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47EF,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)(unsigned int)v12,
      pwszBaseUria);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
    if ( v9 )
      ((void (__fastcall *)(IUnknown *))v9->lpVtbl->Release)(v9);
    return v11;
  }
  v13 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
  v11 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47F0,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)(unsigned int)v13,
      pwszBaseUria);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
    if ( v9 )
      ((void (__fastcall *)(IUnknown *))v9->lpVtbl->Release)(v9);
    return v11;
  }
  v14 = (*(__int64 (__fastcall **)(void *, IXmlReaderInput *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppInput);
  v11 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47F1,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)(unsigned int)v14,
      pwszBaseUria);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
    if ( v9 )
      ((void (__fastcall *)(IUnknown *))v9->lpVtbl->Release)(v9);
    return v11;
  }
  v15 = (struct IXmlReader *)ppvObject;
  ppvObject = 0;
  *a2 = v15;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvObject);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppInput);
  if ( v9 )
    ((void (__fastcall *)(IUnknown *))v9->lpVtbl->Release)(v9);
  return 0;
}

```

## disassembly

```asm
0x18005e934  mov     [rsp-18h+arg_0], rbx
0x18005e939  push    rbp
0x18005e93a  push    rsi
0x18005e93b  push    rdi
0x18005e93c  mov     rbp, rsp
0x18005e93f  sub     rsp, 40h
0x18005e943  mov     rsi, rdx
0x18005e946  mov     r11, rcx
0x18005e949  mov     qword ptr [rbp+cbInit], 0
0x18005e951  mov     [rbp+pInputStream], 0
0x18005e959  lea     r8, [rbp+pInputStream]; unsigned __int64 *
0x18005e95d  mov     edx, 7FFFFFFFh; unsigned __int64
0x18005e962  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18005e967  mov     ebx, eax
0x18005e969  test    eax, eax
0x18005e96b  jns     short loc_18005E98C
0x18005e96d  mov     edx, 47E4h; void *
0x18005e972  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18005e979  mov     r9d, ebx; char *
0x18005e97c  mov     rcx, [rbp+18h]; this
0x18005e980  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e985  mov     eax, ebx
0x18005e987  jmp     loc_18005EBDA
0x18005e98c  lea     r8, [rbp+cbInit]; unsigned __int64 *
0x18005e990  mov     rcx, [rbp+pInputStream]; unsigned __int64
0x18005e994  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18005e999  mov     ebx, eax
0x18005e99b  test    eax, eax
0x18005e99d  jns     short loc_18005E9A6
0x18005e99f  mov     edx, 47E5h
0x18005e9a4  jmp     short loc_18005E972
0x18005e9a6  mov     [rbp+pInputStream], 0
0x18005e9ae  mov     edx, [rbp+cbInit]; cbInit
0x18005e9b1  mov     rcx, r11; pInit
0x18005e9b4  call    cs:__imp_SHCreateMemStream
0x18005e9ba  mov     rdx, rax
0x18005e9bd  lea     rcx, [rbp+pInputStream]
0x18005e9c1  call    ?Attach@?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAXPEAUIStream@@@Z; Microsoft::WRL::ComPtr<IStream>::Attach(IStream *)
0x18005e9c6  mov     rbx, [rbp+pInputStream]
0x18005e9ca  test    rbx, rbx
0x18005e9cd  jnz     short loc_18005E9EF
0x18005e9cf  mov     rcx, [rbp+18h]; this
0x18005e9d3  mov     ebx, 8007000Eh
0x18005e9d8  mov     r9d, ebx; char *
0x18005e9db  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18005e9e2  mov     edx, 47E9h; void *
0x18005e9e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e9ec  nop
0x18005e9ed  jmp     short loc_18005E985
0x18005e9ef  mov     [rbp+arg_18], 0
0x18005e9f7  lea     rcx, [rbp+arg_18]
0x18005e9fb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005ea00  lea     rax, [rbp+arg_18]
0x18005ea04  mov     [rsp+40h+ppInput], rax; ppInput
0x18005ea09  mov     [rsp+40h+pwszBaseUri], 0; int
0x18005ea12  xor     r9d, r9d; fEncodingHint
0x18005ea15  lea     r8, pwszEncodingName; "UTF-16"
0x18005ea1c  xor     edx, edx; pMalloc
0x18005ea1e  mov     rcx, rbx; pInputStream
0x18005ea21  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x18005ea27  mov     edi, eax
0x18005ea29  test    eax, eax
0x18005ea2b  jns     short loc_18005EA6C
0x18005ea2d  mov     rcx, [rbp+18h]; this
0x18005ea31  mov     r9d, eax; char *
0x18005ea34  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18005ea3b  mov     edx, 47ECh; void *
0x18005ea40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ea45  nop
0x18005ea46  lea     rcx, [rbp+arg_18]
0x18005ea4a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005ea4f  nop
0x18005ea50  test    rbx, rbx
0x18005ea53  jz      short loc_18005EA65
0x18005ea55  mov     rax, [rbx]
0x18005ea58  mov     rcx, rbx
0x18005ea5b  mov     rax, [rax+10h]
0x18005ea5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea64  nop
0x18005ea65  mov     eax, edi
0x18005ea67  jmp     loc_18005EBDA
0x18005ea6c  mov     [rbp+ppvObject], 0
0x18005ea74  lea     rcx, [rbp+ppvObject]
0x18005ea78  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005ea7d  xor     r8d, r8d; pMalloc
0x18005ea80  lea     rdx, [rbp+ppvObject]; ppvObject
0x18005ea84  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18005ea8b  call    cs:__imp_CreateXmlReader
0x18005ea91  mov     edi, eax
0x18005ea93  test    eax, eax
0x18005ea95  jns     short loc_18005EADB
0x18005ea97  mov     rcx, [rbp+18h]; this
0x18005ea9b  mov     r9d, eax; char *
0x18005ea9e  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18005eaa5  mov     edx, 47EFh; void *
0x18005eaaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005eaaf  nop
0x18005eab0  lea     rcx, [rbp+ppvObject]
0x18005eab4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005eab9  nop
0x18005eaba  lea     rcx, [rbp+arg_18]
0x18005eabe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005eac3  nop
0x18005eac4  test    rbx, rbx
0x18005eac7  jz      short loc_18005EAD9
0x18005eac9  mov     rax, [rbx]
0x18005eacc  mov     rcx, rbx
0x18005eacf  mov     rax, [rax+10h]
0x18005ead3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ead8  nop
0x18005ead9  jmp     short loc_18005EA65
0x18005eadb  mov     rcx, [rbp+ppvObject]
0x18005eadf  mov     rax, [rcx]
0x18005eae2  xor     r8d, r8d
0x18005eae5  lea     edx, [r8+4]
0x18005eae9  mov     rax, [rax+28h]
0x18005eaed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eaf2  mov     edi, eax
0x18005eaf4  test    eax, eax
0x18005eaf6  jns     short loc_18005EB3F
0x18005eaf8  mov     rcx, [rbp+18h]; this
0x18005eafc  mov     r9d, eax; char *
0x18005eaff  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18005eb06  mov     edx, 47F0h; void *
0x18005eb0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005eb10  nop
0x18005eb11  lea     rcx, [rbp+ppvObject]
0x18005eb15  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005eb1a  nop
0x18005eb1b  lea     rcx, [rbp+arg_18]
0x18005eb1f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005eb24  nop
0x18005eb25  test    rbx, rbx
0x18005eb28  jz      short loc_18005EB3A
0x18005eb2a  mov     rax, [rbx]
0x18005eb2d  mov     rcx, rbx
0x18005eb30  mov     rax, [rax+10h]
0x18005eb34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eb39  nop
0x18005eb3a  jmp     loc_18005EA65
0x18005eb3f  mov     rcx, [rbp+ppvObject]
0x18005eb43  mov     rax, [rcx]
0x18005eb46  mov     rdx, [rbp+arg_18]
0x18005eb4a  mov     rax, [rax+18h]
0x18005eb4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eb53  mov     edi, eax
0x18005eb55  test    eax, eax
0x18005eb57  jns     short loc_18005EBA0
0x18005eb59  mov     rcx, [rbp+18h]; this
0x18005eb5d  mov     r9d, eax; char *
0x18005eb60  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18005eb67  mov     edx, 47F1h; void *
0x18005eb6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005eb71  nop
0x18005eb72  lea     rcx, [rbp+ppvObject]
0x18005eb76  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005eb7b  nop
0x18005eb7c  lea     rcx, [rbp+arg_18]
0x18005eb80  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005eb85  nop
0x18005eb86  test    rbx, rbx
0x18005eb89  jz      short loc_18005EB9B
0x18005eb8b  mov     rax, [rbx]
0x18005eb8e  mov     rcx, rbx
0x18005eb91  mov     rax, [rax+10h]
0x18005eb95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eb9a  nop
0x18005eb9b  jmp     loc_18005EA65
0x18005eba0  mov     rax, [rbp+ppvObject]
0x18005eba4  mov     [rbp+ppvObject], 0
0x18005ebac  mov     [rsi], rax
0x18005ebaf  lea     rcx, [rbp+ppvObject]
0x18005ebb3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005ebb8  nop
0x18005ebb9  lea     rcx, [rbp+arg_18]
0x18005ebbd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005ebc2  nop
0x18005ebc3  test    rbx, rbx
0x18005ebc6  jz      short loc_18005EBD8
0x18005ebc8  mov     rax, [rbx]
0x18005ebcb  mov     rcx, rbx
0x18005ebce  mov     rax, [rax+10h]
0x18005ebd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ebd7  nop
0x18005ebd8  xor     eax, eax
0x18005ebda  mov     rbx, [rsp+40h+arg_0]
0x18005ebdf  add     rsp, 40h
0x18005ebe3  pop     rdi
0x18005ebe4  pop     rsi
0x18005ebe5  pop     rbp
0x18005ebe6  retn
```
