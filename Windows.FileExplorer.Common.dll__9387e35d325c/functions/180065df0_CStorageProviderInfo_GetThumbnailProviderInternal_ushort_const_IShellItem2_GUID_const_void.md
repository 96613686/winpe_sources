# CStorageProviderInfo::GetThumbnailProviderInternal(ushort const *,IShellItem2 *,_GUID const &,void * *)

- ea: `0x180065df0`
- end: `0x18006608c`
- name: `?GetThumbnailProviderInternal@CStorageProviderInfo@@AEAAJPEBGPEAUIShellItem2@@AEBU_GUID@@PEAPEAX@Z`
- size: `668`
- prototype: `int(CStorageProviderInfo *__hidden this, const unsigned __int16 *, struct IShellItem2 *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800278a0`
- `0x180065da0`

## callees

- `0x180004a54`
- `0x18000524c`
- `0x1800077c8`
- `0x18001d4d0`
- `0x180021c80`
- `0x180022d94`
- `0x1800236d4`
- `0x180037780`
- `0x18003d38c`
- `0x180065df0`
- `0x180089010`

## import_xrefs

- `Windows.Storage!__imp_SHExtCoCreateInstance` at `0x180065f3f`
- `Windows.Storage!__imp_SHExtCoCreateInstance` at `0x180065f3f`

## string_xrefs

- `0x180065ead`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180065f9b`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180065fb8`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180065ffc`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CStorageProviderInfo::GetThumbnailProviderInternal(
        CStorageProviderInfo *this,
        const unsigned __int16 *a2,
        struct IShellItem2 *a3,
        const struct _GUID *a4,
        void **a5)
{
  char *v8; // rsi
  int OutOfProcStorageProviderHandler; // eax
  unsigned int v11; // edi
  unsigned int v12; // ebx
  const unsigned __int16 *v13; // rdx
  unsigned int v14; // edx
  unsigned int v15; // r14d
  int Instance; // eax
  unsigned int v17; // esi
  int v18; // eax
  int v19; // eax
  __int64 v20; // rdx
  int v21; // [rsp+20h] [rbp-50h]
  __int64 v22; // [rsp+30h] [rbp-40h] BYREF
  void *v23; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v24[40]; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  *a5 = 0;
  v8 = (char *)this + 480;
  if ( *((_OWORD *)this + 30) == *(_OWORD *)&GUID_NULL )
    return 2147943568LL;
  if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&GUID_382848c8_110f_4402_b0dc_21f5d4cf3938.Data1
    && *(_QWORD *)a4->Data4 == *(_QWORD *)GUID_382848c8_110f_4402_b0dc_21f5d4cf3938.Data4
    || *(_QWORD *)&a4->Data1 == *(_QWORD *)&GUID_0f03f8fe_2b26_46f0_965a_212aa8d66b76.Data1
    && *(_QWORD *)a4->Data4 == *(_QWORD *)GUID_0f03f8fe_2b26_46f0_965a_212aa8d66b76.Data4 )
  {
    OutOfProcStorageProviderHandler = anonymous_namespace_::CreateOutOfProcStorageProviderHandler(
                                        (__int64)this + 480,
                                        (int)a4);
    v11 = OutOfProcStorageProviderHandler;
    if ( OutOfProcStorageProviderHandler < 0 )
    {
      v12 = -2147221164;
      if ( OutOfProcStorageProviderHandler != -2147221164 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x54D,
          (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
          (const char *)(unsigned int)OutOfProcStorageProviderHandler,
          v21);
        return v11;
      }
      return v12;
    }
    return 0;
  }
  CClsidFlagChecker::CClsidFlagChecker(v24, (char *)this + 480);
  v15 = 1;
  if ( (unsigned int)CClsidFlagChecker::IsSet((CClsidFlagChecker *)v24, v13) )
    v15 = 4;
  v23 = 0;
  if ( a3 )
  {
    v23 = a3;
    ((void (__fastcall *)(struct IShellItem2 *))a3->lpVtbl->AddRef)(a3);
  }
  else
  {
    if ( !a2 )
    {
      v12 = -2147024809;
      goto LABEL_29;
    }
    v23 = 0;
    v18 = SHSimpleItemFromAttributes(a2, v14, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &v23);
    v12 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x55F,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)(unsigned int)v18,
        v21);
      goto LABEL_29;
    }
  }
  v22 = 0;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v22);
  Instance = SHExtCoCreateInstance(v8, 0, v15, 1);
  v17 = Instance;
  if ( Instance >= 0 )
  {
    v19 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD))(*(_QWORD *)v22 + 24LL))(v22, v23, 0);
    v12 = v19;
    if ( v19 >= 0 )
    {
      v19 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v22)(v22, a4, a5);
      v12 = v19;
      if ( v19 >= 0 )
      {
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v22);
        wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v23);
        CClsidFlagChecker::~CClsidFlagChecker((CClsidFlagChecker *)v24);
        return 0;
      }
      v20 = 1387;
    }
    else
    {
      v20 = 1386;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v19,
      (int)&GUID_7f73be3f_fb79_493c_a6c7_7ee14e245841);
  }
  else
  {
    v12 = -2147221164;
    if ( Instance != -2147221164 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x569,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)(unsigned int)Instance,
        (int)&GUID_7f73be3f_fb79_493c_a6c7_7ee14e245841);
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v22);
      v12 = v17;
      goto LABEL_29;
    }
  }
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v22);
LABEL_29:
  wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v23);
  CClsidFlagChecker::~CClsidFlagChecker((CClsidFlagChecker *)v24);
  return v12;
}

```

## disassembly

```asm
0x180065df0  push    rbp
0x180065df2  push    rbx
0x180065df3  push    rsi
0x180065df4  push    rdi
0x180065df5  push    r12
0x180065df7  push    r14
0x180065df9  push    r15
0x180065dfb  mov     rbp, rsp
0x180065dfe  sub     rsp, 70h
0x180065e02  mov     rax, cs:__security_cookie
0x180065e09  xor     rax, rsp
0x180065e0c  mov     [rbp+var_8], rax
0x180065e10  mov     rdi, r9
0x180065e13  mov     rbx, r8
0x180065e16  mov     r15, rdx
0x180065e19  mov     r12, [rbp+arg_20]
0x180065e1d  mov     qword ptr [r12], 0
0x180065e25  lea     rsi, [rcx+1E0h]
0x180065e2c  mov     rax, [rsi]
0x180065e2f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180065e36  jnz     short loc_180065E4F
0x180065e38  mov     rax, [rsi+8]
0x180065e3c  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180065e43  jnz     short loc_180065E4F
0x180065e45  mov     eax, 80070490h
0x180065e4a  jmp     loc_180066071
0x180065e4f  mov     rax, [r9]
0x180065e52  cmp     rax, qword ptr cs:_GUID_382848c8_110f_4402_b0dc_21f5d4cf3938.Data1
0x180065e59  jnz     short loc_180065E68
0x180065e5b  mov     rax, [r9+8]
0x180065e5f  cmp     rax, qword ptr cs:_GUID_382848c8_110f_4402_b0dc_21f5d4cf3938.Data4
0x180065e66  jz      short loc_180065E81
0x180065e68  mov     rax, [r9]
0x180065e6b  cmp     rax, qword ptr cs:_GUID_0f03f8fe_2b26_46f0_965a_212aa8d66b76.Data1
0x180065e72  jnz     short loc_180065EC5
0x180065e74  mov     rax, [r9+8]
0x180065e78  cmp     rax, qword ptr cs:_GUID_0f03f8fe_2b26_46f0_965a_212aa8d66b76.Data4
0x180065e7f  jnz     short loc_180065EC5
0x180065e81  mov     r8, r12
0x180065e84  mov     rdx, rdi
0x180065e87  mov     rcx, rsi
0x180065e8a  call    _anonymous_namespace___CreateOutOfProcStorageProviderHandler
0x180065e8f  mov     edi, eax
0x180065e91  test    eax, eax
0x180065e93  jns     loc_180066053
0x180065e99  mov     ebx, 80040154h
0x180065e9e  cmp     eax, ebx
0x180065ea0  jz      loc_18006606F
0x180065ea6  mov     rcx, [rbp+38h]; this
0x180065eaa  mov     r9d, eax; char *
0x180065ead  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180065eb4  mov     edx, 54Dh; void *
0x180065eb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065ebe  mov     eax, edi
0x180065ec0  jmp     loc_180066071
0x180065ec5  mov     rdx, rsi
0x180065ec8  lea     rcx, [rbp+var_30]
0x180065ecc  call    ??0CClsidFlagChecker@@QEAA@PEBU_GUID@@W4EnumCLSIDHive@0@@Z; CClsidFlagChecker::CClsidFlagChecker(_GUID const *,CClsidFlagChecker::EnumCLSIDHive)
0x180065ed1  nop
0x180065ed2  lea     rcx, [rbp+var_30]; this
0x180065ed6  call    ?IsSet@CClsidFlagChecker@@QEAAJPEBG@Z; CClsidFlagChecker::IsSet(ushort const *)
0x180065edb  mov     ecx, 4
0x180065ee0  lea     r14d, [rcx-3]
0x180065ee4  test    eax, eax
0x180065ee6  cmovnz  r14d, ecx
0x180065eea  mov     [rbp+var_38], 0
0x180065ef2  test    rbx, rbx
0x180065ef5  jz      short loc_180065F66
0x180065ef7  mov     [rbp+var_38], rbx
0x180065efb  mov     rax, [rbx]
0x180065efe  mov     rcx, rbx
0x180065f01  mov     rax, [rax+8]
0x180065f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065f0a  nop
0x180065f0b  mov     [rbp+var_40], 0
0x180065f13  lea     rcx, [rbp+var_40]
0x180065f17  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180065f1c  lea     rax, [rbp+var_40]
0x180065f20  mov     [rsp+70h+var_48], rax
0x180065f25  lea     rax, _GUID_7f73be3f_fb79_493c_a6c7_7ee14e245841
0x180065f2c  mov     qword ptr [rsp+70h+var_50], rax; int
0x180065f31  mov     r9d, 1
0x180065f37  mov     r8d, r14d
0x180065f3a  xor     edx, edx
0x180065f3c  mov     rcx, rsi
0x180065f3f  call    cs:__imp_SHExtCoCreateInstance
0x180065f45  mov     esi, eax
0x180065f47  test    eax, eax
0x180065f49  jns     loc_180065FDA
0x180065f4f  mov     ebx, 80040154h
0x180065f54  cmp     eax, ebx
0x180065f56  jnz     short loc_180065FB1
0x180065f58  lea     rcx, [rbp+var_40]
0x180065f5c  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180065f61  jmp     loc_18006605C
0x180065f66  test    r15, r15
0x180065f69  jz      loc_180066057
0x180065f6f  mov     [rbp+var_38], 0
0x180065f77  lea     r9, [rbp+var_38]; void **
0x180065f7b  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; struct _GUID *
0x180065f82  mov     rcx, r15; pszPath
0x180065f85  call    ?SHSimpleItemFromAttributes@@YAJPEBGKAEBU_GUID@@PEAPEAX@Z; SHSimpleItemFromAttributes(ushort const *,ulong,_GUID const &,void * *)
0x180065f8a  mov     ebx, eax
0x180065f8c  test    eax, eax
0x180065f8e  jns     loc_180065F0B
0x180065f94  mov     rcx, [rbp+38h]; this
0x180065f98  mov     r9d, eax; char *
0x180065f9b  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180065fa2  mov     edx, 55Fh; void *
0x180065fa7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065fac  jmp     loc_18006605C
0x180065fb1  mov     rcx, [rbp+38h]; this
0x180065fb5  mov     r9d, esi; char *
0x180065fb8  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180065fbf  mov     edx, 569h; void *
0x180065fc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065fc9  nop
0x180065fca  lea     rcx, [rbp+var_40]
0x180065fce  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180065fd3  mov     ebx, esi
0x180065fd5  jmp     loc_18006605C
0x180065fda  mov     rcx, [rbp+var_40]
0x180065fde  mov     rax, [rcx]
0x180065fe1  xor     r8d, r8d
0x180065fe4  mov     rdx, [rbp+var_38]
0x180065fe8  mov     rax, [rax+18h]
0x180065fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065ff1  mov     ebx, eax
0x180065ff3  test    eax, eax
0x180065ff5  jns     short loc_180066014
0x180065ff7  mov     edx, 56Ah; void *
0x180065ffc  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180066003  mov     r9d, eax; char *
0x180066006  mov     rcx, [rbp+38h]; this
0x18006600a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006600f  jmp     loc_180065F58
0x180066014  mov     rcx, [rbp+var_40]
0x180066018  mov     rax, [rcx]
0x18006601b  mov     r8, r12
0x18006601e  mov     rdx, rdi
0x180066021  mov     rax, [rax]
0x180066024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066029  mov     ebx, eax
0x18006602b  test    eax, eax
0x18006602d  jns     short loc_180066036
0x18006602f  mov     edx, 56Bh
0x180066034  jmp     short loc_180065FFC
0x180066036  lea     rcx, [rbp+var_40]
0x18006603a  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18006603f  nop
0x180066040  lea     rcx, [rbp+var_38]
0x180066044  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x180066049  nop
0x18006604a  lea     rcx, [rbp+var_30]; this
0x18006604e  call    ??1CClsidFlagChecker@@QEAA@XZ; CClsidFlagChecker::~CClsidFlagChecker(void)
0x180066053  xor     eax, eax
0x180066055  jmp     short loc_180066071
0x180066057  mov     ebx, 80070057h
0x18006605c  lea     rcx, [rbp+var_38]
0x180066060  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x180066065  nop
0x180066066  lea     rcx, [rbp+var_30]; this
0x18006606a  call    ??1CClsidFlagChecker@@QEAA@XZ; CClsidFlagChecker::~CClsidFlagChecker(void)
0x18006606f  mov     eax, ebx
0x180066071  mov     rcx, [rbp+var_8]
0x180066075  xor     rcx, rsp; StackCookie
0x180066078  call    __security_check_cookie
0x18006607d  add     rsp, 70h
0x180066081  pop     r15
0x180066083  pop     r14
0x180066085  pop     r12
0x180066087  pop     rdi
0x180066088  pop     rsi
0x180066089  pop     rbx
0x18006608a  pop     rbp
0x18006608b  retn
```
