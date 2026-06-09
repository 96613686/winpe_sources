# _ActivateApplicationForLaunchHelperWithWindowFactory(IApplicationActivationManagerPriv *,ushort const *,ushort const *,ushort const *,ACTIVATEOPTIONSINTERNAL,HMONITOR__ *,Windows::UI::Core::ICoreWindowFactory *,ulong *)

- ea: `0x18004a7a0`
- end: `0x18004a9b9`
- name: `?_ActivateApplicationForLaunchHelperWithWindowFactory@@YAJPEAUIApplicationActivationManagerPriv@@PEBG11W4ACTIVATEOPTIONSINTERNAL@@PEAUHMONITOR__@@PEAUICoreWindowFactory@Core@UI@Windows@@PEAK@Z`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180049744`

## callees

- `0x180003390`
- `0x180008bbc`
- `0x18000aa7c`
- `0x180022448`
- `0x180024a48`
- `0x180025d04`
- `0x180046c84`
- `0x180048db4`
- `0x18004a1c4`
- `0x18004a7a0`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004a92b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004a92b`
- `SHCORE!IUnknown_GetSite` at `0x18004a8c9`
- `SHCORE!IUnknown_GetSite` at `0x18004a8c9`
- `SHCORE!IUnknown_SetSite` at `0x18004a973`
- `SHCORE!IUnknown_SetSite` at `0x18004a973`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004a912`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004a912`

## pseudocode

```c
__int64 __fastcall _ActivateApplicationForLaunchHelperWithWindowFactory(
        IUnknown *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        int a5,
        __int64 a6,
        __int64 a7,
        _DWORD *a8)
{
  _lambda_6d98a26ab645bb601d6c6842c9556ef9_ *v12; // rax
  __int64 v13; // rdx
  int v14; // ecx
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned int v18; // ebx
  HRESULT Site; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // r14
  HSTRING v24; // rbx
  int v26; // [rsp+20h] [rbp-D1h]
  void *ppv; // [rsp+40h] [rbp-B1h] BYREF
  __int64 v28; // [rsp+48h] [rbp-A9h] BYREF
  unsigned __int16 *v29; // [rsp+50h] [rbp-A1h] BYREF
  __int64 v30; // [rsp+58h] [rbp-99h]
  __int64 v31; // [rsp+60h] [rbp-91h]
  HSTRING v32; // [rsp+68h] [rbp-89h] BYREF
  HSTRING v33; // [rsp+70h] [rbp-81h] BYREF
  HSTRING string; // [rsp+80h] [rbp-71h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-69h] BYREF
  _QWORD v36[4]; // [rsp+A0h] [rbp-51h] BYREF
  HSTRING v37[4]; // [rsp+C0h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+47h]

  v29 = 0;
  v30 = 0;
  *a8 = 0;
  v31 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v29);
  v30 = -1;
  v31 = -1;
  v28 = 0;
  if ( (int)ParseAppUserModelId(a4, 0, &v29) >= 0 )
    a4 = v29;
  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v37, a4);
  v32 = v37[0];
  if ( !a3 )
    a3 = &qword_180057BE0;
  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v36, a3);
  v33 = (HSTRING)v36[0];
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v28);
  v12 = _lambda_6d98a26ab645bb601d6c6842c9556ef9_::_lambda_6d98a26ab645bb601d6c6842c9556ef9_(
          (_lambda_6d98a26ab645bb601d6c6842c9556ef9_ *)&string,
          &v33,
          &v32);
  v15 = Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<CLaunchActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_6d98a26ab645bb601d6c6842c9556ef9_>(
          v14,
          v13,
          &v28,
          (__int64)v12);
  v18 = v15;
  if ( v15 >= 0 )
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv, v16, v17);
    Site = IUnknown_GetSite(a1, &GUID_00000000_0000_0000_c000_000000000046, &ppv);
    v18 = Site;
    if ( Site >= 0 )
    {
      v22 = v28;
      QueryInterface = a1->lpVtbl[1].QueryInterface;
      if ( WindowsCreateStringReference(L"Windows.Launch", 0xEu, &hstringHeader, &string) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v24 = string;
      Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v36, a2);
      v18 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, __int64, HSTRING, __int64, int, _DWORD *))QueryInterface)(
              a1,
              v36[0],
              a7,
              v24,
              v22,
              a5,
              a8);
      IUnknown_SetSite(a1, (IUnknown *)ppv);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B,
        (unsigned int)"onecoreuap\\shell\\twinui\\activationhelper\\activationhelpers.cpp",
        (const char *)(unsigned int)Site,
        v26);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv, v20, v21);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecoreuap\\shell\\twinui\\activationhelper\\activationhelpers.cpp",
      (const char *)(unsigned int)v15,
      v26);
  }
  Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(&v28);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v29);
  return v18;
}

```

## disassembly

```asm
0x18004a7a0  push    rbp
0x18004a7a2  push    rbx
0x18004a7a3  push    rsi
0x18004a7a4  push    rdi
0x18004a7a5  push    r12
0x18004a7a7  push    r13
0x18004a7a9  push    r14
0x18004a7ab  push    r15
0x18004a7ad  lea     rbp, [rsp-7]
0x18004a7b2  sub     rsp, 0F8h
0x18004a7b9  mov     rax, cs:__security_cookie
0x18004a7c0  xor     rax, rsp
0x18004a7c3  mov     [rbp+3Fh+var_50], rax
0x18004a7c7  mov     r15, [rbp+3Fh+arg_38]
0x18004a7ce  xor     r14d, r14d
0x18004a7d1  mov     r13, [rbp+3Fh+arg_30]
0x18004a7d5  mov     rsi, rcx
0x18004a7d8  lea     rcx, [rsp+130h+var_E0]
0x18004a7dd  mov     [rsp+130h+var_E0], r14
0x18004a7e2  mov     rbx, r9
0x18004a7e5  mov     [rsp+130h+var_D8], r14
0x18004a7ea  mov     [r15], r14d
0x18004a7ed  mov     rdi, r8
0x18004a7f0  mov     r12, rdx
0x18004a7f3  mov     [rsp+130h+var_D0], r14
0x18004a7f8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004a7fd  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004a801  lea     r8, [rsp+130h+var_E0]; unsigned __int16 **
0x18004a806  xor     edx, edx; unsigned __int16 **
0x18004a808  mov     [rsp+130h+var_D8], rax
0x18004a80d  mov     rcx, rbx; unsigned __int16 *
0x18004a810  mov     [rsp+130h+var_D0], rax
0x18004a815  call    ?ParseAppUserModelId@@YAJPEBGPEAPEAG1@Z; ParseAppUserModelId(ushort const *,ushort * *,ushort * *)
0x18004a81a  test    eax, eax
0x18004a81c  mov     [rsp+130h+var_E8], r14
0x18004a821  lea     rcx, [rbp+3Fh+var_70]; this
0x18004a825  cmovns  rbx, [rsp+130h+var_E0]
0x18004a82b  mov     rdx, rbx; unsigned __int16 *
0x18004a82e  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18004a833  mov     rax, [rbp+3Fh+var_70]
0x18004a837  lea     rcx, [rbp+3Fh+var_90]; this
0x18004a83b  mov     [rsp+130h+var_C8], rax
0x18004a840  test    rdi, rdi
0x18004a843  lea     rax, qword_180057BE0
0x18004a84a  cmovz   rdi, rax
0x18004a84e  mov     rdx, rdi; unsigned __int16 *
0x18004a851  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18004a856  mov     rax, [rbp+3Fh+var_90]
0x18004a85a  lea     rcx, [rsp+130h+var_E8]
0x18004a85f  mov     [rsp+130h+var_C0], rax
0x18004a864  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18004a869  lea     r8, [rsp+130h+var_C8]; HSTRING *
0x18004a86e  lea     rdx, [rsp+130h+var_C0]; HSTRING *
0x18004a873  lea     rcx, [rbp+3Fh+string]; this
0x18004a877  call    ??0_lambda_6d98a26ab645bb601d6c6842c9556ef9_@@QEAA@AEAPEAUHSTRING__@@0@Z; _lambda_6d98a26ab645bb601d6c6842c9556ef9_::_lambda_6d98a26ab645bb601d6c6842c9556ef9_(HSTRING__ * &,HSTRING__ * &)
0x18004a87c  mov     r9, rax
0x18004a87f  lea     r8, [rsp+130h+var_E8]
0x18004a884  call    ??$_MakeAndInitializeOnSTAThread@VCLaunchActivatedEventArgs@@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@V_lambda_6d98a26ab645bb601d6c6842c9556ef9_@@@ComTaskPool@Internal@Windows@@CAJW4TaskOptions@12@KPEAPEAUIActivatedEventArgs@Activation@ApplicationModel@2@AEBV_lambda_6d98a26ab645bb601d6c6842c9556ef9_@@@Z; Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<CLaunchActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_6d98a26ab645bb601d6c6842c9556ef9_>(Windows::Internal::TaskOptions,ulong,Windows::ApplicationModel::Activation::IActivatedEventArgs * *,_lambda_6d98a26ab645bb601d6c6842c9556ef9_ const &)
0x18004a889  mov     ebx, eax
0x18004a88b  test    eax, eax
0x18004a88d  jns     short loc_18004A8AB
0x18004a88f  mov     rcx, [rbp+47h]; this
0x18004a893  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\twinui\\activationhe"...
0x18004a89a  mov     r9d, eax; char *
0x18004a89d  lea     edx, [r14+22h]; void *
0x18004a8a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a8a6  jmp     loc_18004A983
0x18004a8ab  lea     rcx, [rsp+130h+ppv]
0x18004a8b0  mov     [rsp+130h+ppv], r14
0x18004a8b5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a8ba  lea     r8, [rsp+130h+ppv]; ppv
0x18004a8bf  mov     rcx, rsi; punk
0x18004a8c2  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18004a8c9  call    cs:__imp_IUnknown_GetSite
0x18004a8cf  mov     ebx, eax
0x18004a8d1  test    eax, eax
0x18004a8d3  jns     short loc_18004A8F2
0x18004a8d5  mov     rcx, [rbp+47h]; this
0x18004a8d9  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\twinui\\activationhe"...
0x18004a8e0  mov     r9d, eax; char *
0x18004a8e3  mov     edx, 2Bh ; '+'; void *
0x18004a8e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a8ed  jmp     loc_18004A979
0x18004a8f2  mov     rax, [rsi]
0x18004a8f5  lea     r9, [rbp+3Fh+string]; string
0x18004a8f9  mov     rdi, [rsp+130h+var_E8]
0x18004a8fe  lea     r8, [rbp+3Fh+hstringHeader]; hstringHeader
0x18004a902  mov     edx, 0Eh; length
0x18004a907  lea     rcx, sourceString; "Windows.Launch"
0x18004a90e  mov     r14, [rax+18h]
0x18004a912  call    cs:__imp_WindowsCreateStringReference
0x18004a918  test    eax, eax
0x18004a91a  jns     short loc_18004A931
0x18004a91c  xor     r9d, r9d; lpArguments
0x18004a91f  xor     r8d, r8d; nNumberOfArguments
0x18004a922  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004a927  lea     edx, [r9+1]; dwExceptionFlags
0x18004a92b  call    cs:__imp_RaiseException
0x18004a931  mov     rbx, [rbp+3Fh+string]
0x18004a935  lea     rcx, [rbp+3Fh+var_90]; this
0x18004a939  mov     rdx, r12; unsigned __int16 *
0x18004a93c  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18004a941  mov     r10d, [rbp+3Fh+arg_20]
0x18004a945  mov     r9, rbx
0x18004a948  mov     rdx, [rbp+3Fh+var_90]
0x18004a94c  mov     r8, r13
0x18004a94f  mov     [rsp+130h+var_100], r15
0x18004a954  mov     rcx, rsi
0x18004a957  mov     [rsp+130h+var_108], r10d
0x18004a95c  mov     rax, r14
0x18004a95f  mov     [rsp+130h+var_110], rdi
0x18004a964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a969  mov     rdx, [rsp+130h+ppv]; punkSite
0x18004a96e  mov     rcx, rsi; punk
0x18004a971  mov     ebx, eax
0x18004a973  call    cs:__imp_IUnknown_SetSite
0x18004a979  lea     rcx, [rsp+130h+ppv]
0x18004a97e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a983  lea     rcx, [rsp+130h+var_E8]
0x18004a988  call    ?InternalRelease@?$ComPtr@UITileActivatedInfo@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::ITileActivatedInfo>::InternalRelease(void)
0x18004a98d  lea     rcx, [rsp+130h+var_E0]
0x18004a992  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004a997  mov     eax, ebx
0x18004a999  mov     rcx, [rbp+3Fh+var_50]
0x18004a99d  xor     rcx, rsp; StackCookie
0x18004a9a0  call    __security_check_cookie
0x18004a9a5  add     rsp, 0F8h
0x18004a9ac  pop     r15
0x18004a9ae  pop     r14
0x18004a9b0  pop     r13
0x18004a9b2  pop     r12
0x18004a9b4  pop     rdi
0x18004a9b5  pop     rsi
0x18004a9b6  pop     rbx
0x18004a9b7  pop     rbp
0x18004a9b8  retn
```
