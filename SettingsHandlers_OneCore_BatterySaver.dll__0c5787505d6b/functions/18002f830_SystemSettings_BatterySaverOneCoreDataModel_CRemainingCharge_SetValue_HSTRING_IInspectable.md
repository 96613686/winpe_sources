# SystemSettings::BatterySaverOneCoreDataModel::CRemainingCharge::SetValue(HSTRING__ *,IInspectable *)

- ea: `0x18002f830`
- end: `0x18002f9fd`
- name: `?SetValue@CRemainingCharge@BatterySaverOneCoreDataModel@SystemSettings@@MEAAJPEAUHSTRING__@@PEAUIInspectable@@@Z`
- size: `461`
- prototype: `__int64 __fastcall(SystemSettings::BatterySaverOneCoreDataModel::CRemainingCharge *__hidden this, HSTRING, struct IInspectable *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180009190`
- `0x18000cfa4`
- `0x18000eacc`
- `0x18001d0f8`
- `0x18002f830`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002f8ad`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002f96a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002f8ad`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002f96a`

## string_xrefs

- `0x18002f882`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SystemSettings::BatterySaverOneCoreDataModel::CRemainingCharge::SetValue(
        SystemSettings::BatterySaverOneCoreDataModel::CRemainingCharge *this,
        HSTRING a2,
        struct IInspectable *a3)
{
  __int64 v3; // rbx
  int ActivationFactory; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64, __int64 *); // rbx
  __int64 v9; // rbx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64, __int64 *); // rbx
  __int64 v13; // [rsp+20h] [rbp-50h] BYREF
  __int64 v14; // [rsp+28h] [rbp-48h] BYREF
  __int64 v15; // [rsp+30h] [rbp-40h] BYREF
  __int64 v16; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v18; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v16 = 0;
  v15 = 0;
  v14 = 0;
  v13 = 0;
  v18 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
  v3 = v18;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  ActivationFactory = RoGetActivationFactory(v3, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v13);
  v5 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v7 = v13;
    v8 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v13 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    v18 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"ms-settings:batterysaver",
      0x19u,
      0x18u);
    ActivationFactory = v8(v7, v18, &v14);
    v5 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v18 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.System.Launcher",
        0x18u,
        0x17u);
      v9 = v18;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
      ActivationFactory = RoGetActivationFactory(v9, &GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451, &v15);
      v5 = ActivationFactory;
      if ( ActivationFactory >= 0 )
      {
        v10 = v15;
        v11 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v15 + 64LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
        ActivationFactory = v11(v10, v14, &v16);
        v5 = ActivationFactory;
        if ( ActivationFactory >= 0 )
        {
          v5 = 0;
          goto LABEL_11;
        }
        v6 = 729;
      }
      else
      {
        v6 = 726;
      }
    }
    else
    {
      v6 = 721;
    }
  }
  else
  {
    v6 = 717;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batterysaver\\lib\\cremainingcharge.cpp",
    (const char *)(unsigned int)ActivationFactory,
    v13);
LABEL_11:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  return v5;
}

```

## disassembly

```asm
0x18002f830  mov     [rsp-8+arg_0], rbx
0x18002f835  mov     [rsp-8+arg_8], rdi
0x18002f83a  push    rbp
0x18002f83b  mov     rbp, rsp
0x18002f83e  sub     rsp, 70h
0x18002f842  mov     rax, cs:__security_cookie
0x18002f849  xor     rax, rsp
0x18002f84c  mov     [rbp+var_10], rax
0x18002f850  mov     [rbp+var_38], 0
0x18002f858  mov     [rbp+var_40], 0
0x18002f860  mov     [rbp+var_48], 0
0x18002f868  mov     [rbp+var_50], 0
0x18002f870  mov     [rbp+var_18], 0
0x18002f878  mov     r9d, 16h; unsigned int
0x18002f87e  lea     r8d, [r9+1]; unsigned int
0x18002f882  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x18002f889  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18002f88d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002f892  mov     rbx, [rbp+var_18]
0x18002f896  lea     rcx, [rbp+var_50]
0x18002f89a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f89f  lea     r8, [rbp+var_50]
0x18002f8a3  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x18002f8aa  mov     rcx, rbx
0x18002f8ad  call    cs:__imp_RoGetActivationFactory
0x18002f8b3  mov     ebx, eax
0x18002f8b5  test    eax, eax
0x18002f8b7  jns     short loc_18002F8C0
0x18002f8b9  mov     edx, 2CDh
0x18002f8be  jmp     short loc_18002F915
0x18002f8c0  mov     rdi, [rbp+var_50]
0x18002f8c4  mov     rax, [rdi]
0x18002f8c7  mov     rbx, [rax+30h]
0x18002f8cb  lea     rcx, [rbp+var_48]
0x18002f8cf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f8d4  mov     [rbp+var_18], 0
0x18002f8dc  mov     r9d, 18h; unsigned int
0x18002f8e2  lea     r8d, [r9+1]; unsigned int
0x18002f8e6  lea     rdx, sourceString; "ms-settings:batterysaver"
0x18002f8ed  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18002f8f1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002f8f6  nop
0x18002f8f7  lea     r8, [rbp+var_48]
0x18002f8fb  mov     rdx, [rbp+var_18]
0x18002f8ff  mov     rcx, rdi
0x18002f902  mov     rax, rbx
0x18002f905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f90a  mov     ebx, eax
0x18002f90c  test    eax, eax
0x18002f90e  jns     short loc_18002F92D
0x18002f910  mov     edx, 2D1h; void *
0x18002f915  lea     r8, aOnecoreuapShel_11; "onecoreuap\\shell\\coresettinghandlers"...
0x18002f91c  mov     r9d, eax; char *
0x18002f91f  mov     rcx, [rbp+8]; this
0x18002f923  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f928  jmp     loc_18002F9B6
0x18002f92d  mov     [rbp+var_18], 0
0x18002f935  mov     r9d, 17h; unsigned int
0x18002f93b  lea     r8d, [r9+1]; unsigned int
0x18002f93f  lea     rdx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x18002f946  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18002f94a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002f94f  mov     rbx, [rbp+var_18]
0x18002f953  lea     rcx, [rbp+var_40]
0x18002f957  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f95c  lea     r8, [rbp+var_40]
0x18002f960  lea     rdx, _GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451
0x18002f967  mov     rcx, rbx
0x18002f96a  call    cs:__imp_RoGetActivationFactory
0x18002f970  mov     ebx, eax
0x18002f972  test    eax, eax
0x18002f974  jns     short loc_18002F97D
0x18002f976  mov     edx, 2D6h
0x18002f97b  jmp     short loc_18002F915
0x18002f97d  mov     rdi, [rbp+var_40]
0x18002f981  mov     rax, [rdi]
0x18002f984  mov     rbx, [rax+40h]
0x18002f988  lea     rcx, [rbp+var_38]
0x18002f98c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f991  lea     r8, [rbp+var_38]
0x18002f995  mov     rdx, [rbp+var_48]
0x18002f999  mov     rcx, rdi
0x18002f99c  mov     rax, rbx
0x18002f99f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f9a4  mov     ebx, eax
0x18002f9a6  test    eax, eax
0x18002f9a8  jns     short loc_18002F9B4
0x18002f9aa  mov     edx, 2D9h
0x18002f9af  jmp     loc_18002F915
0x18002f9b4  xor     ebx, ebx
0x18002f9b6  lea     rcx, [rbp+var_50]
0x18002f9ba  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f9bf  nop
0x18002f9c0  lea     rcx, [rbp+var_48]
0x18002f9c4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f9c9  nop
0x18002f9ca  lea     rcx, [rbp+var_40]
0x18002f9ce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f9d3  nop
0x18002f9d4  lea     rcx, [rbp+var_38]
0x18002f9d8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f9dd  mov     eax, ebx
0x18002f9df  mov     rcx, [rbp+var_10]
0x18002f9e3  xor     rcx, rsp; StackCookie
0x18002f9e6  call    __security_check_cookie
0x18002f9eb  lea     r11, [rsp+70h+var_s0]
0x18002f9f0  mov     rbx, [r11+10h]
0x18002f9f4  mov     rdi, [r11+18h]
0x18002f9f8  mov     rsp, r11
0x18002f9fb  pop     rbp
0x18002f9fc  retn
```
