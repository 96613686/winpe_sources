# Common::Deployment::GetAppxBundleManifestReaderByPath(ushort const *,IAppxBundleManifestReader * *)

- ea: `0x1800198d4`
- end: `0x180019afd`
- name: `?GetAppxBundleManifestReaderByPath@Deployment@Common@@YAJPEBGPEAPEAUIAppxBundleManifestReader@@@Z`
- size: `553`
- prototype: `__int64 __fastcall(Common::Deployment *__hidden this, const unsigned __int16 *, struct IAppxBundleManifestReader **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001073c`

## callees

- `0x180018248`
- `0x1800198d4`
- `0x18001ca24`
- `0x18001fe04`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800198fa`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800198fa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019937`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019a21`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019937`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019a21`

## string_xrefs

- `0x180019947`: `onecore\admin\appmodel\common\bundleutilities.cpp`
- `0x18001996c`: `onecore\admin\appmodel\common\bundleutilities.cpp`
- `0x1800199d1`: `onecore\admin\appmodel\common\bundleutilities.cpp`
- `0x180019a31`: `onecore\admin\appmodel\common\bundleutilities.cpp`
- `0x180019a89`: `onecore\admin\appmodel\common\bundleutilities.cpp`

## pseudocode

```c
__int64 __fastcall Common::Deployment::GetAppxBundleManifestReaderByPath(
        Common::Deployment *this,
        unsigned __int16 *a2,
        struct IAppxBundleManifestReader **a3)
{
  HRESULT v5; // eax
  unsigned int v6; // ebx
  HRESULT Instance; // eax
  LPVOID v8; // rdi
  __int64 (__fastcall *v9)(LPVOID, Common::Deployment *, __int64); // rbx
  int v10; // eax
  HRESULT v11; // eax
  LPVOID v12; // rdi
  __int64 (__fastcall *v13)(LPVOID, __int64, __int64 *); // rbx
  int v14; // eax
  int ppv; // [rsp+20h] [rbp-40h]
  int ppva; // [rsp+20h] [rbp-40h]
  int ppvb; // [rsp+20h] [rbp-40h]
  __int64 v19; // [rsp+40h] [rbp-20h] BYREF
  LPVOID v20; // [rsp+48h] [rbp-18h] BYREF
  LPVOID v21[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  int v23; // [rsp+90h] [rbp+30h] BYREF
  __int64 v24; // [rsp+98h] [rbp+38h] BYREF

  v23 = -2147221008;
  v5 = CoInitializeEx(0, 0);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v23 = v5;
    goto LABEL_3;
  }
  if ( v5 == -2147417850 )
  {
LABEL_3:
    v21[0] = 0;
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(v21);
    Instance = CoCreateInstance(
                 &GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e,
                 0,
                 1u,
                 &GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154,
                 v21);
    v6 = Instance;
    if ( Instance >= 0 )
    {
      v8 = v21[0];
      v24 = 0;
      v9 = *(__int64 (__fastcall **)(LPVOID, Common::Deployment *, __int64))(*(_QWORD *)v21[0] + 40LL);
      Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v24);
      v10 = v9(v8, this, 1);
      v6 = v10;
      if ( v10 >= 0 )
      {
        v20 = 0;
        Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v20);
        v11 = CoCreateInstance(
                &GUID_378e0446_5384_43b7_8877_e7dbdd883446,
                0,
                1u,
                &GUID_bba65864_965f_4a5f_855f_f074bdbf3a7b,
                &v20);
        v6 = v11;
        if ( v11 >= 0 )
        {
          v12 = v20;
          v19 = 0;
          v13 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v20 + 40LL);
          Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v19);
          v14 = v13(v12, v24, &v19);
          v6 = v14;
          if ( v14 >= 0 )
          {
            *(_QWORD *)a2 = v19;
            v19 = 0;
            Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v19);
            Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v20);
            Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v24);
            v6 = 0;
            goto LABEL_16;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x68,
            (unsigned int)"onecore\\admin\\appmodel\\common\\bundleutilities.cpp",
            (const char *)(unsigned int)v14,
            ppvb);
          Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v19);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x65,
            (unsigned int)"onecore\\admin\\appmodel\\common\\bundleutilities.cpp",
            (const char *)(unsigned int)v11,
            ppvb);
        }
        Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v20);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5D,
          (unsigned int)"onecore\\admin\\appmodel\\common\\bundleutilities.cpp",
          (const char *)(unsigned int)v10,
          128);
      }
      Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v24);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x55,
        (unsigned int)"onecore\\admin\\appmodel\\common\\bundleutilities.cpp",
        (const char *)(unsigned int)Instance,
        ppva);
    }
LABEL_16:
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(v21);
    Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v23);
    return v6;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4D,
    (unsigned int)"onecore\\admin\\appmodel\\common\\bundleutilities.cpp",
    (const char *)(unsigned int)v5,
    ppv);
  return v6;
}

```

## disassembly

```asm
0x1800198d4  mov     [rsp-18h+arg_0], rbx
0x1800198d9  mov     [rsp-18h+arg_8], rsi
0x1800198de  push    rbp
0x1800198df  push    rdi
0x1800198e0  push    r14
0x1800198e2  mov     rbp, rsp
0x1800198e5  sub     rsp, 60h
0x1800198e9  mov     rsi, rdx
0x1800198ec  mov     [rbp+arg_10], 800401F0h
0x1800198f3  mov     r14, rcx
0x1800198f6  xor     edx, edx; dwCoInit
0x1800198f8  xor     ecx, ecx; pvReserved
0x1800198fa  call    cs:__imp_CoInitializeEx
0x180019900  mov     ebx, eax
0x180019902  test    eax, eax
0x180019904  js      short loc_180019960
0x180019906  mov     [rbp+arg_10], eax
0x180019909  lea     rcx, [rbp+var_10]
0x18001990d  mov     [rbp+var_10], 0
0x180019915  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001991a  xor     edx, edx; pUnkOuter
0x18001991c  lea     rax, [rbp+var_10]
0x180019920  lea     r9, _GUID_6d0b4446_cd73_4ab3_94f4_8ccdf6116154; riid
0x180019927  mov     [rsp+60h+ppv], rax; int
0x18001992c  lea     rcx, _GUID_6b2d6ba0_9f3e_4f27_920b_313cc426a39e; rclsid
0x180019933  lea     r8d, [rdx+1]; dwClsContext
0x180019937  call    cs:__imp_CoCreateInstance
0x18001993d  mov     ebx, eax
0x18001993f  test    eax, eax
0x180019941  jns     short loc_180019985
0x180019943  mov     rcx, [rbp+18h]; this
0x180019947  lea     r8, aOnecoreAdminAp_28; "onecore\\admin\\appmodel\\common\\bundl"...
0x18001994e  mov     r9d, eax; char *
0x180019951  mov     edx, 55h ; 'U'; void *
0x180019956  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001995b  jmp     loc_180019AD4
0x180019960  cmp     ebx, 80010106h
0x180019966  jz      short loc_180019909
0x180019968  mov     rcx, [rbp+18h]; this
0x18001996c  lea     r8, aOnecoreAdminAp_28; "onecore\\admin\\appmodel\\common\\bundl"...
0x180019973  mov     r9d, ebx; char *
0x180019976  mov     edx, 4Dh ; 'M'; void *
0x18001997b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019980  jmp     loc_180019AE6
0x180019985  mov     rdi, [rbp+var_10]
0x180019989  lea     rcx, [rbp+arg_18]
0x18001998d  mov     [rbp+arg_18], 0
0x180019995  mov     rax, [rdi]
0x180019998  mov     rbx, [rax+28h]
0x18001999c  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x1800199a1  xor     r9d, r9d
0x1800199a4  lea     rax, [rbp+arg_18]
0x1800199a8  mov     [rsp+60h+var_38], rax
0x1800199ad  mov     rdx, r14
0x1800199b0  mov     rcx, rdi
0x1800199b3  mov     dword ptr [rsp+60h+ppv], 80h; int
0x1800199bb  mov     rax, rbx
0x1800199be  lea     r8d, [r9+1]
0x1800199c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199c7  mov     ebx, eax
0x1800199c9  test    eax, eax
0x1800199cb  jns     short loc_1800199F3
0x1800199cd  mov     rcx, [rbp+18h]; this
0x1800199d1  lea     r8, aOnecoreAdminAp_28; "onecore\\admin\\appmodel\\common\\bundl"...
0x1800199d8  mov     r9d, eax; char *
0x1800199db  mov     edx, 5Dh ; ']'; void *
0x1800199e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800199e5  lea     rcx, [rbp+arg_18]
0x1800199e9  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x1800199ee  jmp     loc_180019AD4
0x1800199f3  lea     rcx, [rbp+var_18]
0x1800199f7  mov     [rbp+var_18], 0
0x1800199ff  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180019a04  xor     edx, edx; pUnkOuter
0x180019a06  lea     rax, [rbp+var_18]
0x180019a0a  lea     r9, _GUID_bba65864_965f_4a5f_855f_f074bdbf3a7b; riid
0x180019a11  mov     [rsp+60h+ppv], rax; int
0x180019a16  lea     rcx, _GUID_378e0446_5384_43b7_8877_e7dbdd883446; rclsid
0x180019a1d  lea     r8d, [rdx+1]; dwClsContext
0x180019a21  call    cs:__imp_CoCreateInstance
0x180019a27  mov     ebx, eax
0x180019a29  test    eax, eax
0x180019a2b  jns     short loc_180019A50
0x180019a2d  mov     rcx, [rbp+18h]; this
0x180019a31  lea     r8, aOnecoreAdminAp_28; "onecore\\admin\\appmodel\\common\\bundl"...
0x180019a38  mov     r9d, eax; char *
0x180019a3b  mov     edx, 65h ; 'e'; void *
0x180019a40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019a45  lea     rcx, [rbp+var_18]
0x180019a49  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180019a4e  jmp     short loc_1800199E5
0x180019a50  mov     rdi, [rbp+var_18]
0x180019a54  lea     rcx, [rbp+var_20]
0x180019a58  mov     [rbp+var_20], 0
0x180019a60  mov     rax, [rdi]
0x180019a63  mov     rbx, [rax+28h]
0x180019a67  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180019a6c  mov     rdx, [rbp+arg_18]
0x180019a70  lea     r8, [rbp+var_20]
0x180019a74  mov     rcx, rdi
0x180019a77  mov     rax, rbx
0x180019a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a7f  mov     ebx, eax
0x180019a81  test    eax, eax
0x180019a83  jns     short loc_180019AA8
0x180019a85  mov     rcx, [rbp+18h]; this
0x180019a89  lea     r8, aOnecoreAdminAp_28; "onecore\\admin\\appmodel\\common\\bundl"...
0x180019a90  mov     r9d, eax; char *
0x180019a93  mov     edx, 68h ; 'h'; void *
0x180019a98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019a9d  lea     rcx, [rbp+var_20]
0x180019aa1  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180019aa6  jmp     short loc_180019A45
0x180019aa8  mov     rax, [rbp+var_20]
0x180019aac  lea     rcx, [rbp+var_20]
0x180019ab0  mov     [rsi], rax
0x180019ab3  mov     [rbp+var_20], 0
0x180019abb  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180019ac0  lea     rcx, [rbp+var_18]
0x180019ac4  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180019ac9  lea     rcx, [rbp+arg_18]
0x180019acd  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180019ad2  xor     ebx, ebx
0x180019ad4  lea     rcx, [rbp+var_10]
0x180019ad8  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x180019add  lea     rcx, [rbp+arg_10]; this
0x180019ae1  call    ??1AutoCoInitialize@Common@@QEAA@XZ; Common::AutoCoInitialize::~AutoCoInitialize(void)
0x180019ae6  lea     r11, [rsp+60h+var_s0]
0x180019aeb  mov     eax, ebx
0x180019aed  mov     rbx, [r11+20h]
0x180019af1  mov     rsi, [r11+28h]
0x180019af5  mov     rsp, r11
0x180019af8  pop     r14
0x180019afa  pop     rdi
0x180019afb  pop     rbp
0x180019afc  retn
```
