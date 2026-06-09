# Common::Deployment::GetManifestReaderFromManifestPath(ushort const *,IAppxManifestReader * *)

- ea: `0x180045edc`
- end: `0x18004611f`
- name: `?GetManifestReaderFromManifestPath@Deployment@Common@@YAJPEBGPEAPEAUIAppxManifestReader@@@Z`
- size: `579`
- prototype: `__int64 __fastcall(Common::Deployment *__hidden this, const unsigned __int16 *, struct IAppxManifestReader **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180046128`
- `0x180046244`

## callees

- `0x180018248`
- `0x18001a6a0`
- `0x18001ca24`
- `0x180020bb4`
- `0x180045edc`
- `0x1800475f0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180045f22`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180046040`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180045f22`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180046040`

## string_xrefs

- `0x180045f32`: `onecore\admin\appmodel\common\headlesspackageutilities.cpp`
- `0x180045f66`: `onecore\admin\appmodel\common\headlesspackageutilities.cpp`
- `0x180045fef`: `onecore\admin\appmodel\common\headlesspackageutilities.cpp`
- `0x180046050`: `onecore\admin\appmodel\common\headlesspackageutilities.cpp`
- `0x1800460a9`: `onecore\admin\appmodel\common\headlesspackageutilities.cpp`
- `0x180045fe3`: `Path %ws`
- `0x18004608c`: `Path %ws`
- `0x1800460bc`: `Path %ws`

## pseudocode

```c
__int64 __fastcall Common::Deployment::GetManifestReaderFromManifestPath(
        Common::Deployment *this,
        const unsigned __int16 *a2,
        struct IAppxManifestReader **a3)
{
  HRESULT v5; // eax
  void *v6; // rdx
  int v7; // ebx
  int v8; // eax
  LPVOID v9; // rdi
  __int64 (__fastcall *v10)(LPVOID, Common::Deployment *, __int64); // rbx
  HRESULT v11; // eax
  int v12; // eax
  int ppv; // [rsp+20h] [rbp-40h]
  int ppva; // [rsp+20h] [rbp-40h]
  LPVOID v16; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v17[3]; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  __int64 v19; // [rsp+A0h] [rbp+40h] BYREF
  LPVOID v20; // [rsp+A8h] [rbp+48h] BYREF

  v16 = 0;
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v16);
  v5 = CoCreateInstance(
         &GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e,
         0,
         1u,
         &GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154,
         &v16);
  v7 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAD,
      (unsigned int)"onecore\\admin\\appmodel\\common\\headlesspackageutilities.cpp",
      (const char *)(unsigned int)v5,
      ppv);
    goto LABEL_21;
  }
  v17[0] = 0;
  v17[1] = 0;
  v8 = Common::ImpersonationContext::Impersonate((Common::ImpersonationContext *)v17, v6);
  v7 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB1,
      (unsigned int)"onecore\\admin\\appmodel\\common\\headlesspackageutilities.cpp",
      (const char *)(unsigned int)v8,
      ppv);
    goto LABEL_5;
  }
  v9 = v16;
  v19 = 0;
  v10 = *(__int64 (__fastcall **)(LPVOID, Common::Deployment *, __int64))(*(_QWORD *)v16 + 40LL);
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v19);
  v7 = v10(v9, this, 1);
  Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v17);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xBA,
      (unsigned int)"onecore\\admin\\appmodel\\common\\headlesspackageutilities.cpp",
      (const char *)(unsigned int)v7,
      (int)"Path %ws",
      (const char *)this);
LABEL_9:
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v19);
LABEL_5:
    if ( LODWORD(v17[0]) )
      Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v17);
    goto LABEL_21;
  }
  v20 = 0;
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v20);
  v11 = CoCreateInstance(
          &GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781,
          0,
          1u,
          &GUID_beb94909_e451_438b_b5a7_d79e767b75d8,
          &v20);
  v7 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC0,
      (unsigned int)"onecore\\admin\\appmodel\\common\\headlesspackageutilities.cpp",
      (const char *)(unsigned int)v11,
      ppva);
LABEL_12:
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v20);
    goto LABEL_9;
  }
  v12 = (*(__int64 (__fastcall **)(LPVOID, __int64, const unsigned __int16 *))(*(_QWORD *)v20 + 40LL))(v20, v19, a2);
  v7 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xC3,
      (unsigned int)"onecore\\admin\\appmodel\\common\\headlesspackageutilities.cpp",
      (const char *)(unsigned int)v12,
      (int)"Path %ws",
      (const char *)this);
    goto LABEL_12;
  }
  if ( !*(_QWORD *)a2 )
  {
    v7 = -2147467261;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xC4,
      (unsigned int)"onecore\\admin\\appmodel\\common\\headlesspackageutilities.cpp",
      (const char *)0x80004003LL,
      (int)"Path %ws",
      (const char *)this);
    goto LABEL_12;
  }
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v19);
  if ( LODWORD(v17[0]) )
    Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v17);
  v7 = 0;
LABEL_21:
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v16);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180045edc  mov     [rsp-28h+arg_0], rbx
0x180045ee1  push    rbp
0x180045ee2  push    rsi
0x180045ee3  push    rdi
0x180045ee4  push    r14
0x180045ee6  push    r15
0x180045ee8  mov     rbp, rsp
0x180045eeb  sub     rsp, 60h
0x180045eef  mov     rsi, rcx
0x180045ef2  xor     r15d, r15d
0x180045ef5  lea     rcx, [rbp+var_20]
0x180045ef9  mov     [rbp+var_20], r15
0x180045efd  mov     r14, rdx
0x180045f00  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180045f05  lea     rax, [rbp+var_20]
0x180045f09  xor     edx, edx; pUnkOuter
0x180045f0b  lea     r9, _GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154; riid
0x180045f12  mov     [rsp+60h+ppv], rax; int
0x180045f17  lea     r8d, [r15+1]; dwClsContext
0x180045f1b  lea     rcx, _GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e; rclsid
0x180045f22  call    cs:__imp_CoCreateInstance
0x180045f28  mov     ebx, eax
0x180045f2a  test    eax, eax
0x180045f2c  jns     short loc_180045F4B
0x180045f2e  mov     rcx, [rbp+28h]; this
0x180045f32  lea     r8, aOnecoreAdminAp_17; "onecore\\admin\\appmodel\\common\\headl"...
0x180045f39  mov     r9d, eax; char *
0x180045f3c  mov     edx, 0ADh; void *
0x180045f41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045f46  jmp     loc_180046100
0x180045f4b  lea     rcx, [rbp+var_18]; this
0x180045f4f  mov     [rbp+var_18], r15
0x180045f53  mov     [rbp+var_10], r15
0x180045f57  call    ?Impersonate@ImpersonationContext@Common@@QEAAJPEAX@Z; Common::ImpersonationContext::Impersonate(void *)
0x180045f5c  mov     ebx, eax
0x180045f5e  test    eax, eax
0x180045f60  jns     short loc_180045F92
0x180045f62  mov     rcx, [rbp+28h]; this
0x180045f66  lea     r8, aOnecoreAdminAp_17; "onecore\\admin\\appmodel\\common\\headl"...
0x180045f6d  mov     r9d, eax; char *
0x180045f70  mov     edx, 0B1h; void *
0x180045f75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045f7a  cmp     dword ptr [rbp+var_18], r15d
0x180045f7e  jz      loc_180046100
0x180045f84  lea     rcx, [rbp+var_18]; this
0x180045f88  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x180045f8d  jmp     loc_180046100
0x180045f92  mov     rdi, [rbp+var_20]
0x180045f96  lea     rcx, [rbp+arg_10]
0x180045f9a  mov     [rbp+arg_10], r15
0x180045f9e  mov     rax, [rdi]
0x180045fa1  mov     rbx, [rax+28h]
0x180045fa5  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180045faa  xor     r9d, r9d
0x180045fad  lea     rax, [rbp+arg_10]
0x180045fb1  mov     [rsp+60h+var_38], rax
0x180045fb6  mov     rdx, rsi
0x180045fb9  mov     rcx, rdi
0x180045fbc  mov     dword ptr [rsp+60h+ppv], 80h
0x180045fc4  mov     rax, rbx
0x180045fc7  lea     r8d, [r9+1]
0x180045fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045fd0  lea     rcx, [rbp+var_18]; this
0x180045fd4  mov     ebx, eax
0x180045fd6  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x180045fdb  test    ebx, ebx
0x180045fdd  jns     short loc_180046016
0x180045fdf  mov     rcx, [rbp+28h]; this
0x180045fe3  lea     rdx, aPathWs_0; "Path %ws"
0x180045fea  mov     [rsp+60h+var_38], rsi; char *
0x180045fef  lea     r8, aOnecoreAdminAp_17; "onecore\\admin\\appmodel\\common\\headl"...
0x180045ff6  mov     [rsp+60h+ppv], rdx; int
0x180045ffb  mov     r9d, ebx; char *
0x180045ffe  mov     edx, 0BAh; void *
0x180046003  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180046008  lea     rcx, [rbp+arg_10]
0x18004600c  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180046011  jmp     loc_180045F7A
0x180046016  lea     rcx, [rbp+arg_18]
0x18004601a  mov     [rbp+arg_18], r15
0x18004601e  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180046023  xor     edx, edx; pUnkOuter
0x180046025  lea     rax, [rbp+arg_18]
0x180046029  lea     r9, _GUID_beb94909_e451_438b_b5a7_d79e767b75d8; riid
0x180046030  mov     [rsp+60h+ppv], rax; int
0x180046035  lea     rcx, _GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781; rclsid
0x18004603c  lea     r8d, [rdx+1]; dwClsContext
0x180046040  call    cs:__imp_CoCreateInstance
0x180046046  mov     ebx, eax
0x180046048  test    eax, eax
0x18004604a  jns     short loc_18004606F
0x18004604c  mov     rcx, [rbp+28h]; this
0x180046050  lea     r8, aOnecoreAdminAp_17; "onecore\\admin\\appmodel\\common\\headl"...
0x180046057  mov     r9d, eax; char *
0x18004605a  mov     edx, 0C0h; void *
0x18004605f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046064  lea     rcx, [rbp+arg_18]
0x180046068  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18004606d  jmp     short loc_180046008
0x18004606f  mov     rcx, [rbp+arg_18]
0x180046073  mov     r8, r14
0x180046076  mov     rdx, [rbp+arg_10]
0x18004607a  mov     rax, [rcx]
0x18004607d  mov     rax, [rax+28h]
0x180046081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046086  mov     ebx, eax
0x180046088  test    eax, eax
0x18004608a  jns     short loc_1800460B7
0x18004608c  lea     rdx, aPathWs_0; "Path %ws"
0x180046093  mov     [rsp+60h+var_38], rsi; char *
0x180046098  mov     [rsp+60h+ppv], rdx; int
0x18004609d  mov     r9d, eax; char *
0x1800460a0  mov     edx, 0C3h; void *
0x1800460a5  mov     rcx, [rbp+28h]; this
0x1800460a9  lea     r8, aOnecoreAdminAp_17; "onecore\\admin\\appmodel\\common\\headl"...
0x1800460b0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800460b5  jmp     short loc_180046064
0x1800460b7  cmp     [r14], r15
0x1800460ba  jnz     short loc_1800460DC
0x1800460bc  lea     rdx, aPathWs_0; "Path %ws"
0x1800460c3  mov     [rsp+60h+var_38], rsi
0x1800460c8  mov     ebx, 80004003h
0x1800460cd  mov     [rsp+60h+ppv], rdx
0x1800460d2  mov     edx, 0C4h
0x1800460d7  mov     r9d, ebx
0x1800460da  jmp     short loc_1800460A5
0x1800460dc  lea     rcx, [rbp+arg_18]
0x1800460e0  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x1800460e5  lea     rcx, [rbp+arg_10]
0x1800460e9  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x1800460ee  cmp     dword ptr [rbp+var_18], r15d
0x1800460f2  jz      short loc_1800460FD
0x1800460f4  lea     rcx, [rbp+var_18]; this
0x1800460f8  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x1800460fd  mov     ebx, r15d
0x180046100  lea     rcx, [rbp+var_20]
0x180046104  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180046109  mov     eax, ebx
0x18004610b  mov     rbx, [rsp+60h+arg_0]
0x180046113  add     rsp, 60h
0x180046117  pop     r15
0x180046119  pop     r14
0x18004611b  pop     rdi
0x18004611c  pop     rsi
0x18004611d  pop     rbp
0x18004611e  retn
```
