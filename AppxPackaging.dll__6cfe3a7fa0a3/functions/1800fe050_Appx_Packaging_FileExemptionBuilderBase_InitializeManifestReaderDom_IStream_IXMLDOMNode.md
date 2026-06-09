# Appx::Packaging::FileExemptionBuilderBase::InitializeManifestReaderDom(IStream *,IXMLDOMNode * *)

- ea: `0x1800fe050`
- end: `0x1800fe1d5`
- name: `?InitializeManifestReaderDom@FileExemptionBuilderBase@Packaging@Appx@@AEAAJPEAUIStream@@PEAPEAUIXMLDOMNode@@@Z`
- size: `389`
- prototype: `__int64 __fastcall(Appx::Packaging::FileExemptionBuilderBase *__hidden this, struct IStream *, struct IXMLDOMNode **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800937dc`
- `0x1800fd708`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x180094a38`
- `0x180094a70`
- `0x1800fe050`
- `0x1800fe1dc`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800fe08e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800fe08e`
- `OLEAUT32!__imp_SysAllocString` at `0x1800fe108`
- `OLEAUT32!__imp_SysAllocString` at `0x1800fe108`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fe13c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fe183`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fe1a0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fe13c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fe183`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fe1a0`

## string_xrefs

- `0x1800fe0a3`: `(CoCreateInstance( __uuidof(AppxFactory), nullptr, CLSCTX_INPROC_SERVER, __uuidof(**(appxFactory.GetAddressOf())), IID_PPV_ARGS_Helper(appxFactory.GetAddressOf())))`
- `0x1800fe16d`: `root->selectSingleNode(query, manifestRootNode)`
- `0x1800fe0df`: `InitializeXmlDomFromStream(manifestFileStream, &root)`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::FileExemptionBuilderBase::InitializeManifestReaderDom(
        struct IXMLDOMNode *this,
        struct IStream *a2,
        struct IXMLDOMNode **a3)
{
  HRESULT v5; // eax
  bool v6; // cl
  unsigned int v7; // ebx
  int v8; // eax
  bool v9; // cl
  BSTR v10; // rax
  OLECHAR *v11; // rbx
  int v12; // eax
  bool v13; // cl
  unsigned int v14; // edi
  int v16; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  struct IXMLDOMNode *v18; // [rsp+40h] [rbp+8h] BYREF
  LPVOID v19; // [rsp+58h] [rbp+20h] BYREF

  v18 = this;
  v19 = 0;
  v5 = CoCreateInstance(
         &GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781,
         0,
         1u,
         &GUID_beb94909_e451_438b_b5a7_d79e767b75d8,
         &v19);
  v7 = v5;
  if ( v5 < 0 )
  {
    Appx::Packaging::SharedWithTools::Logging::WriteFailure(
      v6,
      v5,
      "(CoCreateInstance( __uuidof(AppxFactory), nullptr, CLSCTX_INPROC_SERVER, __uuidof(**(appxFactory.GetAddressOf())),"
      " IID_PPV_ARGS_Helper(appxFactory.GetAddressOf())))",
      0);
    goto LABEL_11;
  }
  v18 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v18);
  v8 = Appx::Packaging::FileExemptionBuilderBase::InitializeXmlDomFromStream(a2, &v18);
  v7 = v8;
  if ( v8 < 0 )
  {
    Appx::Packaging::SharedWithTools::Logging::WriteFailure(
      v9,
      v8,
      "InitializeXmlDomFromStream(manifestFileStream, &root)",
      0);
    Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo();
LABEL_5:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v18);
    goto LABEL_11;
  }
  v10 = SysAllocString(L"*[local-name()='Package']");
  v11 = v10;
  if ( !v10 )
  {
    v7 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56B,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\fileexemptionbuilderbase.cpp",
      (const char *)0x8007000ELL,
      v16);
    SysFreeString(0);
    goto LABEL_5;
  }
  v12 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR, struct IXMLDOMNode **))v18->lpVtbl->selectSingleNode)(
          v18,
          v10,
          a3);
  v14 = v12;
  if ( v12 >= 0 )
  {
    SysFreeString(v11);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v18);
    v7 = 0;
  }
  else
  {
    Appx::Packaging::SharedWithTools::Logging::WriteFailure(
      v13,
      v12,
      "root->selectSingleNode(query, manifestRootNode)",
      0);
    Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo();
    SysFreeString(v11);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v18);
    v7 = v14;
  }
LABEL_11:
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v19);
  return v7;
}

```

## disassembly

```asm
0x1800fe050  mov     r11, rsp
0x1800fe053  mov     [r11+10h], rbx
0x1800fe057  mov     [r11+18h], rsi
0x1800fe05b  mov     [r11+8], rcx
0x1800fe05f  push    rdi
0x1800fe060  sub     rsp, 30h
0x1800fe064  mov     rdi, rdx
0x1800fe067  mov     qword ptr [r11+20h], 0
0x1800fe06f  xor     edx, edx; pUnkOuter
0x1800fe071  lea     rax, [r11+20h]
0x1800fe075  mov     rsi, r8
0x1800fe078  mov     [r11-18h], rax
0x1800fe07c  lea     r9, _GUID_beb94909_e451_438b_b5a7_d79e767b75d8; riid
0x1800fe083  lea     rcx, _GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781; rclsid
0x1800fe08a  lea     r8d, [rdx+1]; dwClsContext
0x1800fe08e  call    cs:__imp_CoCreateInstance
0x1800fe095  nop     dword ptr [rax+rax+00h]
0x1800fe09a  mov     ebx, eax
0x1800fe09c  test    eax, eax
0x1800fe09e  jns     short loc_1800FE0B6
0x1800fe0a0  xor     r9d, r9d; unsigned __int16 *
0x1800fe0a3  lea     r8, aCocreateinstan_1; "(CoCreateInstance( __uuidof(AppxFactory"...
0x1800fe0aa  mov     edx, eax; int
0x1800fe0ac  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x1800fe0b1  jmp     loc_1800FE1B8
0x1800fe0b6  lea     rcx, [rsp+38h+arg_0]
0x1800fe0bb  mov     [rsp+38h+arg_0], 0
0x1800fe0c4  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fe0c9  lea     rdx, [rsp+38h+arg_0]; struct IXMLDOMNode **
0x1800fe0ce  mov     rcx, rdi; this
0x1800fe0d1  call    ?InitializeXmlDomFromStream@FileExemptionBuilderBase@Packaging@Appx@@CAJPEAUIStream@@PEAPEAUIXMLDOMNode@@@Z; Appx::Packaging::FileExemptionBuilderBase::InitializeXmlDomFromStream(IStream *,IXMLDOMNode * *)
0x1800fe0d6  mov     ebx, eax
0x1800fe0d8  test    eax, eax
0x1800fe0da  jns     short loc_1800FE101
0x1800fe0dc  xor     r9d, r9d; unsigned __int16 *
0x1800fe0df  lea     r8, aInitializexmld_0; "InitializeXmlDomFromStream(manifestFile"...
0x1800fe0e6  mov     edx, eax; int
0x1800fe0e8  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x1800fe0ed  call    ?WriteLastErrorInfo@Logging@SharedWithTools@Packaging@Appx@@SAXXZ; Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo(void)
0x1800fe0f2  lea     rcx, [rsp+38h+arg_0]
0x1800fe0f7  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fe0fc  jmp     loc_1800FE1B8
0x1800fe101  lea     rcx, aLocalNamePacka_24; "*[local-name()='Package']"
0x1800fe108  call    cs:__imp_SysAllocString
0x1800fe10f  nop     dword ptr [rax+rax+00h]
0x1800fe114  mov     rbx, rax
0x1800fe117  test    rax, rax
0x1800fe11a  jnz     short loc_1800FE14A
0x1800fe11c  mov     rcx, [rsp+38h]; this
0x1800fe121  lea     r8, aOnecorePrintsc_108; "onecore\\printscan\\appxpackaging\\lib"...
0x1800fe128  mov     ebx, 8007000Eh
0x1800fe12d  mov     edx, 56Bh; void *
0x1800fe132  mov     r9d, ebx; char *
0x1800fe135  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fe13a  xor     ecx, ecx; bstrString
0x1800fe13c  call    cs:__imp_SysFreeString
0x1800fe143  nop     dword ptr [rax+rax+00h]
0x1800fe148  jmp     short loc_1800FE0F2
0x1800fe14a  mov     rcx, [rsp+38h+arg_0]
0x1800fe14f  mov     r8, rsi
0x1800fe152  mov     rdx, rbx
0x1800fe155  mov     rax, [rcx]
0x1800fe158  mov     rax, [rax+128h]
0x1800fe15f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe164  mov     edi, eax
0x1800fe166  test    eax, eax
0x1800fe168  jns     short loc_1800FE19D
0x1800fe16a  xor     r9d, r9d; unsigned __int16 *
0x1800fe16d  lea     r8, aRootSelectsing; "root->selectSingleNode(query, manifestR"...
0x1800fe174  mov     edx, eax; int
0x1800fe176  call    ?WriteFailure@Logging@SharedWithTools@Packaging@Appx@@SAX_NJPEBDPEBG@Z; Appx::Packaging::SharedWithTools::Logging::WriteFailure(bool,long,char const *,ushort const *)
0x1800fe17b  call    ?WriteLastErrorInfo@Logging@SharedWithTools@Packaging@Appx@@SAXXZ; Appx::Packaging::SharedWithTools::Logging::WriteLastErrorInfo(void)
0x1800fe180  mov     rcx, rbx; bstrString
0x1800fe183  call    cs:__imp_SysFreeString
0x1800fe18a  nop     dword ptr [rax+rax+00h]
0x1800fe18f  lea     rcx, [rsp+38h+arg_0]
0x1800fe194  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fe199  mov     ebx, edi
0x1800fe19b  jmp     short loc_1800FE1B8
0x1800fe19d  mov     rcx, rbx; bstrString
0x1800fe1a0  call    cs:__imp_SysFreeString
0x1800fe1a7  nop     dword ptr [rax+rax+00h]
0x1800fe1ac  lea     rcx, [rsp+38h+arg_0]
0x1800fe1b1  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fe1b6  xor     ebx, ebx
0x1800fe1b8  lea     rcx, [rsp+38h+arg_18]
0x1800fe1bd  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800fe1c2  mov     rsi, [rsp+38h+arg_10]
0x1800fe1c7  mov     eax, ebx
0x1800fe1c9  mov     rbx, [rsp+38h+arg_8]
0x1800fe1ce  add     rsp, 30h
0x1800fe1d2  pop     rdi
0x1800fe1d3  retn
```
