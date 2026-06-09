# CStorageProviderInfo::GetThumbnailProvider(ushort const *,_GUID const &,void * *)

- ea: `0x1800278a0`
- end: `0x180027b4d`
- name: `?GetThumbnailProvider@CStorageProviderInfo@@UEAAJPEBGAEBU_GUID@@PEAPEAX@Z`
- size: `685`
- prototype: `__int64 __fastcall(CStorageProviderInfo *__hidden this, const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004a54`
- `0x18000524c`
- `0x1800077c8`
- `0x18001d4d0`
- `0x180021c80`
- `0x180022d94`
- `0x1800236d4`
- `0x1800278a0`
- `0x180037780`
- `0x180043e04`
- `0x180065df0`
- `0x180089010`

## import_xrefs

- `Windows.Storage!__imp_SHExtCoCreateInstance` at `0x180027a60`
- `Windows.Storage!__imp_SHExtCoCreateInstance` at `0x180027a60`

## string_xrefs

- `0x180027901`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x1800279a8`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180027a16`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180027a7c`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180027ae2`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CStorageProviderInfo::GetThumbnailProvider(
        CStorageProviderInfo *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        void **a4)
{
  int ThumbnailProviderInternal; // eax
  unsigned int v9; // ebx
  _QWORD *v11; // rsi
  int OutOfProcStorageProviderHandler; // eax
  unsigned int v13; // edi
  const unsigned __int16 *v14; // rdx
  unsigned int v15; // r15d
  unsigned int v16; // edx
  int v17; // eax
  int Instance; // eax
  unsigned int v19; // esi
  int v20; // eax
  __int64 v21; // rdx
  int v22; // [rsp+20h] [rbp-58h]
  int v23; // [rsp+20h] [rbp-58h]
  __int64 v24; // [rsp+30h] [rbp-48h] BYREF
  void *v25; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v26[40]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56314744>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56314744>::GetImpl'::`2'::impl) )
  {
    ThumbnailProviderInternal = CStorageProviderInfo::GetThumbnailProviderInternal(this, a2, 0, a3, a4);
    v9 = ThumbnailProviderInternal;
    if ( ThumbnailProviderInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26B,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)(unsigned int)ThumbnailProviderInternal,
        v23);
      return v9;
    }
    return 0;
  }
  *a4 = 0;
  v11 = (_QWORD *)((char *)this + 480);
  if ( *v11 == *(_QWORD *)&GUID_NULL.Data1 && v11[1] == *(_QWORD *)GUID_NULL.Data4 )
    return 2147943568LL;
  if ( (*(_QWORD *)&a3->Data1 != *(_QWORD *)&GUID_382848c8_110f_4402_b0dc_21f5d4cf3938.Data1
     || *(_QWORD *)a3->Data4 != *(_QWORD *)GUID_382848c8_110f_4402_b0dc_21f5d4cf3938.Data4)
    && (*(_QWORD *)&a3->Data1 != *(_QWORD *)&GUID_0f03f8fe_2b26_46f0_965a_212aa8d66b76.Data1
     || *(_QWORD *)a3->Data4 != *(_QWORD *)GUID_0f03f8fe_2b26_46f0_965a_212aa8d66b76.Data4) )
  {
    CClsidFlagChecker::CClsidFlagChecker(v26, v11);
    v15 = 1;
    if ( (unsigned int)CClsidFlagChecker::IsSet((CClsidFlagChecker *)v26, v14) )
      v15 = 4;
    v25 = 0;
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v25);
    v17 = SHSimpleItemFromAttributes(a2, v16, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &v25);
    v9 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x283,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)(unsigned int)v17,
        v22);
LABEL_28:
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v25);
      CClsidFlagChecker::~CClsidFlagChecker((CClsidFlagChecker *)v26);
      return v9;
    }
    v24 = 0;
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v24);
    Instance = SHExtCoCreateInstance(v11, 0, v15, 1);
    v19 = Instance;
    if ( Instance >= 0 )
    {
      v20 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD))(*(_QWORD *)v24 + 24LL))(v24, v25, 0);
      v9 = v20;
      if ( v20 >= 0 )
      {
        v20 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v24)(v24, a3, a4);
        v9 = v20;
        if ( v20 >= 0 )
        {
          Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v24);
          Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v25);
          CClsidFlagChecker::~CClsidFlagChecker((CClsidFlagChecker *)v26);
          return 0;
        }
        v21 = 651;
      }
      else
      {
        v21 = 649;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)(unsigned int)v20,
        (int)&GUID_7f73be3f_fb79_493c_a6c7_7ee14e245841);
    }
    else
    {
      v9 = -2147221164;
      if ( Instance != -2147221164 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x288,
          (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
          (const char *)(unsigned int)Instance,
          (int)&GUID_7f73be3f_fb79_493c_a6c7_7ee14e245841);
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v24);
        v9 = v19;
        goto LABEL_28;
      }
    }
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v24);
    goto LABEL_28;
  }
  OutOfProcStorageProviderHandler = anonymous_namespace_::CreateOutOfProcStorageProviderHandler((__int64)v11, (int)a3);
  v13 = OutOfProcStorageProviderHandler;
  if ( OutOfProcStorageProviderHandler >= 0 )
    return 0;
  v9 = -2147221164;
  if ( OutOfProcStorageProviderHandler == -2147221164 )
    return v9;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x277,
    (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
    (const char *)(unsigned int)OutOfProcStorageProviderHandler,
    v22);
  return v13;
}

```

## disassembly

```asm
0x1800278a0  push    rbp
0x1800278a2  push    rbx
0x1800278a3  push    rsi
0x1800278a4  push    rdi
0x1800278a5  push    r14
0x1800278a7  push    r15
0x1800278a9  mov     rbp, rsp
0x1800278ac  sub     rsp, 78h
0x1800278b0  mov     rax, cs:__security_cookie
0x1800278b7  xor     rax, rsp
0x1800278ba  mov     [rbp+var_10], rax
0x1800278be  mov     r14, r9
0x1800278c1  mov     rdi, r8
0x1800278c4  mov     rbx, rdx
0x1800278c7  mov     rsi, rcx
0x1800278ca  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56314744@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56314744@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56314744> `wil::Feature<__WilFeatureTraits_Feature_56314744>::GetImpl(void)'::`2'::impl
0x1800278d1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56314744@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56314744>::__private_IsEnabled(wil::ReportingKind)
0x1800278d6  test    al, al
0x1800278d8  jz      short loc_180027919
0x1800278da  mov     [rsp+78h+var_58], r14; int
0x1800278df  mov     r9, rdi; struct _GUID *
0x1800278e2  xor     r8d, r8d; struct IShellItem2 *
0x1800278e5  mov     rdx, rbx; unsigned __int16 *
0x1800278e8  mov     rcx, rsi; this
0x1800278eb  call    ?GetThumbnailProviderInternal@CStorageProviderInfo@@AEAAJPEBGPEAUIShellItem2@@AEBU_GUID@@PEAPEAX@Z; CStorageProviderInfo::GetThumbnailProviderInternal(ushort const *,IShellItem2 *,_GUID const &,void * *)
0x1800278f0  mov     ebx, eax
0x1800278f2  test    eax, eax
0x1800278f4  jns     loc_180027B32
0x1800278fa  mov     rcx, [rbp+30h]; this
0x1800278fe  mov     r9d, eax; char *
0x180027901  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180027908  mov     edx, 26Bh; void *
0x18002790d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027912  mov     eax, ebx
0x180027914  jmp     loc_180027B34
0x180027919  mov     qword ptr [r14], 0
0x180027920  add     rsi, 1E0h
0x180027927  mov     rax, [rsi]
0x18002792a  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180027931  jnz     short loc_18002794A
0x180027933  mov     rax, [rsi+8]
0x180027937  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18002793e  jnz     short loc_18002794A
0x180027940  mov     eax, 80070490h
0x180027945  jmp     loc_180027B34
0x18002794a  mov     rax, [rdi]
0x18002794d  cmp     rax, qword ptr cs:_GUID_382848c8_110f_4402_b0dc_21f5d4cf3938.Data1
0x180027954  jnz     short loc_180027963
0x180027956  mov     rax, [rdi+8]
0x18002795a  cmp     rax, qword ptr cs:_GUID_382848c8_110f_4402_b0dc_21f5d4cf3938.Data4
0x180027961  jz      short loc_18002797C
0x180027963  mov     rax, [rdi]
0x180027966  cmp     rax, qword ptr cs:_GUID_0f03f8fe_2b26_46f0_965a_212aa8d66b76.Data1
0x18002796d  jnz     short loc_1800279C0
0x18002796f  mov     rax, [rdi+8]
0x180027973  cmp     rax, qword ptr cs:_GUID_0f03f8fe_2b26_46f0_965a_212aa8d66b76.Data4
0x18002797a  jnz     short loc_1800279C0
0x18002797c  mov     r8, r14
0x18002797f  mov     rdx, rdi
0x180027982  mov     rcx, rsi
0x180027985  call    _anonymous_namespace___CreateOutOfProcStorageProviderHandler
0x18002798a  mov     edi, eax
0x18002798c  test    eax, eax
0x18002798e  jns     loc_180027B32
0x180027994  mov     ebx, 80040154h
0x180027999  cmp     eax, ebx
0x18002799b  jz      loc_180027912
0x1800279a1  mov     rcx, [rbp+30h]; this
0x1800279a5  mov     r9d, eax; char *
0x1800279a8  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x1800279af  mov     edx, 277h; void *
0x1800279b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800279b9  mov     eax, edi
0x1800279bb  jmp     loc_180027B34
0x1800279c0  mov     rdx, rsi
0x1800279c3  lea     rcx, [rbp+var_38]
0x1800279c7  call    ??0CClsidFlagChecker@@QEAA@PEBU_GUID@@W4EnumCLSIDHive@0@@Z; CClsidFlagChecker::CClsidFlagChecker(_GUID const *,CClsidFlagChecker::EnumCLSIDHive)
0x1800279cc  nop
0x1800279cd  lea     rcx, [rbp+var_38]; this
0x1800279d1  call    ?IsSet@CClsidFlagChecker@@QEAAJPEBG@Z; CClsidFlagChecker::IsSet(ushort const *)
0x1800279d6  mov     ecx, 4
0x1800279db  lea     r15d, [rcx-3]
0x1800279df  test    eax, eax
0x1800279e1  cmovnz  r15d, ecx
0x1800279e5  mov     [rbp+var_40], 0
0x1800279ed  lea     rcx, [rbp+var_40]
0x1800279f1  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800279f6  lea     r9, [rbp+var_40]; void **
0x1800279fa  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; struct _GUID *
0x180027a01  mov     rcx, rbx; pszPath
0x180027a04  call    ?SHSimpleItemFromAttributes@@YAJPEBGKAEBU_GUID@@PEAPEAX@Z; SHSimpleItemFromAttributes(ushort const *,ulong,_GUID const &,void * *)
0x180027a09  mov     ebx, eax
0x180027a0b  test    eax, eax
0x180027a0d  jns     short loc_180027A2C
0x180027a0f  mov     rcx, [rbp+30h]; this
0x180027a13  mov     r9d, eax; char *
0x180027a16  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180027a1d  mov     edx, 283h; void *
0x180027a22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027a27  jmp     loc_180027AFD
0x180027a2c  mov     [rbp+var_48], 0
0x180027a34  lea     rcx, [rbp+var_48]
0x180027a38  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180027a3d  lea     rax, [rbp+var_48]
0x180027a41  mov     [rsp+78h+var_50], rax
0x180027a46  lea     rax, _GUID_7f73be3f_fb79_493c_a6c7_7ee14e245841
0x180027a4d  mov     [rsp+78h+var_58], rax; int
0x180027a52  mov     r9d, 1
0x180027a58  mov     r8d, r15d
0x180027a5b  xor     edx, edx
0x180027a5d  mov     rcx, rsi
0x180027a60  call    cs:__imp_SHExtCoCreateInstance
0x180027a66  mov     esi, eax
0x180027a68  test    eax, eax
0x180027a6a  jns     short loc_180027A9B
0x180027a6c  mov     ebx, 80040154h
0x180027a71  cmp     eax, ebx
0x180027a73  jz      short loc_180027AF3
0x180027a75  mov     rcx, [rbp+30h]; this
0x180027a79  mov     r9d, eax; char *
0x180027a7c  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180027a83  mov     edx, 288h; void *
0x180027a88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027a8d  nop
0x180027a8e  lea     rcx, [rbp+var_48]
0x180027a92  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180027a97  mov     ebx, esi
0x180027a99  jmp     short loc_180027AFD
0x180027a9b  mov     rcx, [rbp+var_48]
0x180027a9f  mov     rax, [rcx]
0x180027aa2  xor     r8d, r8d
0x180027aa5  mov     rdx, [rbp+var_40]
0x180027aa9  mov     rax, [rax+18h]
0x180027aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ab2  mov     ebx, eax
0x180027ab4  test    eax, eax
0x180027ab6  jns     short loc_180027ABF
0x180027ab8  mov     edx, 289h
0x180027abd  jmp     short loc_180027ADF
0x180027abf  mov     rcx, [rbp+var_48]
0x180027ac3  mov     rax, [rcx]
0x180027ac6  mov     r8, r14
0x180027ac9  mov     rdx, rdi
0x180027acc  mov     rax, [rax]
0x180027acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ad4  mov     ebx, eax
0x180027ad6  test    eax, eax
0x180027ad8  jns     short loc_180027B15
0x180027ada  mov     edx, 28Bh; void *
0x180027adf  mov     r9d, eax; char *
0x180027ae2  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180027ae9  mov     rcx, [rbp+30h]; this
0x180027aed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027af2  nop
0x180027af3  lea     rcx, [rbp+var_48]
0x180027af7  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180027afc  nop
0x180027afd  lea     rcx, [rbp+var_40]
0x180027b01  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180027b06  nop
0x180027b07  lea     rcx, [rbp+var_38]; this
0x180027b0b  call    ??1CClsidFlagChecker@@QEAA@XZ; CClsidFlagChecker::~CClsidFlagChecker(void)
0x180027b10  jmp     loc_180027912
0x180027b15  lea     rcx, [rbp+var_48]
0x180027b19  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180027b1e  nop
0x180027b1f  lea     rcx, [rbp+var_40]
0x180027b23  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180027b28  nop
0x180027b29  lea     rcx, [rbp+var_38]; this
0x180027b2d  call    ??1CClsidFlagChecker@@QEAA@XZ; CClsidFlagChecker::~CClsidFlagChecker(void)
0x180027b32  xor     eax, eax
0x180027b34  mov     rcx, [rbp+var_10]
0x180027b38  xor     rcx, rsp; StackCookie
0x180027b3b  call    __security_check_cookie
0x180027b40  add     rsp, 78h
0x180027b44  pop     r15
0x180027b46  pop     r14
0x180027b48  pop     rdi
0x180027b49  pop     rsi
0x180027b4a  pop     rbx
0x180027b4b  pop     rbp
0x180027b4c  retn
```
