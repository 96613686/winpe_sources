# GetSystemProfileResourceMap(ushort const *,ushort const *,Windows::ApplicationModel::Resources::Core::IResourceManager * *,Windows::ApplicationModel::Resources::Core::IResourceMap * *)

- ea: `0x180020dcc`
- end: `0x18002100f`
- name: `?GetSystemProfileResourceMap@@YAJPEBG0PEAPEAUIResourceManager@Core@Resources@ApplicationModel@Windows@@PEAPEAUIResourceMap@2345@@Z`
- size: `579`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct IResourceManager **, struct Windows::ApplicationModel::Resources::Core::IResourceMap **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001e92c`

## callees

- `0x180009190`
- `0x18000cfa4`
- `0x1800149fc`
- `0x18001d0f8`
- `0x180020dcc`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180020e4d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180020e4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall GetSystemProfileResourceMap(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct IResourceManager **a3,
        struct Windows::ApplicationModel::Resources::Core::IResourceMap **a4)
{
  __int64 v4; // rbx
  int ActivationFactory; // ebx
  __int64 (__fastcall ***v6)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64 *); // rbx
  __int64 v14; // rax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, const wchar_t **); // rbx
  __int64 v17; // rax
  unsigned __int16 *v18; // rax
  const wchar_t *v20; // [rsp+20h] [rbp-29h] BYREF
  __int64 v21; // [rsp+28h] [rbp-21h] BYREF
  __int64 v22; // [rsp+30h] [rbp-19h] BYREF
  __int64 v23; // [rsp+38h] [rbp-11h] BYREF
  __int64 v24; // [rsp+40h] [rbp-9h] BYREF
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-1h] BYREF
  const wchar_t *v26; // [rsp+50h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v28; // [rsp+70h] [rbp+27h]
  _BYTE v29[32]; // [rsp+78h] [rbp+2Fh] BYREF

  v26 = L"Resources";
  v20 = L"Windows.UI.SettingsHandlers-nt";
  v25 = 0;
  v28 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.ApplicationModel.Resources.Core.ResourceManager",
    0x38u,
    0x37u);
  v4 = v28;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v25);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_1cc0fdfc_69ee_4e43_9901_47f12687baf7, &v25);
  if ( ActivationFactory < 0 )
    goto LABEL_13;
  v24 = 0;
  v6 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v25;
  v7 = **v25;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  ActivationFactory = v7(v6, &GUID_4a8eac58_b652_459d_8de1_239471e8b22b, &v24);
  if ( ActivationFactory >= 0 )
  {
    v23 = 0;
    v8 = v24;
    v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
    ActivationFactory = v9(v8, &v23);
    if ( ActivationFactory >= 0 )
    {
      v22 = 0;
      v10 = v23;
      v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 56LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
      ActivationFactory = v11(v10, &v22);
      if ( ActivationFactory >= 0 )
      {
        v21 = 0;
        v12 = v22;
        v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v22 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
        v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v29, &v20);
        ActivationFactory = v13(v12, *(_QWORD *)(v14 + 24), &v21);
        if ( ActivationFactory >= 0 )
        {
          v20 = 0;
          v15 = v21;
          v16 = *(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t **))(*(_QWORD *)v21 + 72LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v20);
          v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v29, &v26);
          ActivationFactory = v16(v15, *(_QWORD *)(v17 + 24), &v20);
          if ( ActivationFactory >= 0 )
          {
            v18 = (unsigned __int16 *)v20;
            v20 = 0;
            SystemSettings::DataModel::Details::s_handlersResourceMap = v18;
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v20);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  if ( ActivationFactory < 0 )
LABEL_13:
    SystemSettings::DataModel::Details::s_handlersResourceMap = 0;
  v28 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v25);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180020dcc  mov     [rsp-8+arg_0], rbx
0x180020dd1  mov     [rsp-8+arg_8], rdi
0x180020dd6  push    rbp
0x180020dd7  lea     rbp, [rsp-57h]
0x180020ddc  sub     rsp, 0A0h
0x180020de3  mov     rax, cs:__security_cookie
0x180020dea  xor     rax, rsp
0x180020ded  mov     [rbp+57h+var_8], rax
0x180020df1  lea     rax, aResources; "Resources"
0x180020df8  mov     [rbp+57h+var_50], rax
0x180020dfc  lea     rax, aWindowsUiSetti; "Windows.UI.SettingsHandlers-nt"
0x180020e03  mov     [rbp+57h+var_80], rax
0x180020e07  mov     [rbp+57h+var_58], 0
0x180020e0f  mov     [rbp+57h+var_30], 0
0x180020e17  mov     r9d, 37h ; '7'; unsigned int
0x180020e1d  lea     r8d, [r9+1]; unsigned int
0x180020e21  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Resources_Core_ResourceManager@@3QBGB; "Windows.ApplicationModel.Resources.Core"...
0x180020e28  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180020e2c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180020e31  nop
0x180020e32  mov     rbx, [rbp+57h+var_30]
0x180020e36  lea     rcx, [rbp+57h+var_58]
0x180020e3a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020e3f  lea     r8, [rbp+57h+var_58]
0x180020e43  lea     rdx, _GUID_1cc0fdfc_69ee_4e43_9901_47f12687baf7
0x180020e4a  mov     rcx, rbx
0x180020e4d  call    cs:__imp_RoGetActivationFactory
0x180020e53  mov     ebx, eax
0x180020e55  test    eax, eax
0x180020e57  js      loc_180020FD0
0x180020e5d  mov     [rbp+57h+var_60], 0
0x180020e65  mov     rbx, [rbp+57h+var_58]
0x180020e69  mov     rax, [rbx]
0x180020e6c  mov     rdi, [rax]
0x180020e6f  lea     rcx, [rbp+57h+var_60]
0x180020e73  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020e78  lea     r8, [rbp+57h+var_60]
0x180020e7c  lea     rdx, _GUID_4a8eac58_b652_459d_8de1_239471e8b22b
0x180020e83  mov     rcx, rbx
0x180020e86  mov     rax, rdi
0x180020e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e8e  mov     ebx, eax
0x180020e90  test    eax, eax
0x180020e92  js      loc_180020FC3
0x180020e98  mov     [rbp+57h+var_68], 0
0x180020ea0  mov     rdi, [rbp+57h+var_60]
0x180020ea4  mov     rax, [rdi]
0x180020ea7  mov     rbx, [rax+30h]
0x180020eab  lea     rcx, [rbp+57h+var_68]
0x180020eaf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020eb4  lea     rdx, [rbp+57h+var_68]
0x180020eb8  mov     rcx, rdi
0x180020ebb  mov     rax, rbx
0x180020ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ec3  mov     ebx, eax
0x180020ec5  test    eax, eax
0x180020ec7  js      loc_180020FB9
0x180020ecd  mov     [rbp+57h+var_70], 0
0x180020ed5  mov     rdi, [rbp+57h+var_68]
0x180020ed9  mov     rax, [rdi]
0x180020edc  mov     rbx, [rax+38h]
0x180020ee0  lea     rcx, [rbp+57h+var_70]
0x180020ee4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020ee9  lea     rdx, [rbp+57h+var_70]
0x180020eed  mov     rcx, rdi
0x180020ef0  mov     rax, rbx
0x180020ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ef8  mov     ebx, eax
0x180020efa  test    eax, eax
0x180020efc  js      loc_180020FAF
0x180020f02  mov     [rbp+57h+var_78], 0
0x180020f0a  mov     rdi, [rbp+57h+var_70]
0x180020f0e  mov     rax, [rdi]
0x180020f11  mov     rbx, [rax+30h]
0x180020f15  lea     rcx, [rbp+57h+var_78]
0x180020f19  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020f1e  lea     rdx, [rbp+57h+var_80]
0x180020f22  lea     rcx, [rbp+57h+var_28]
0x180020f26  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180020f2b  nop
0x180020f2c  lea     r8, [rbp+57h+var_78]
0x180020f30  mov     rdx, [rax+18h]
0x180020f34  mov     rcx, rdi
0x180020f37  mov     rax, rbx
0x180020f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f3f  mov     ebx, eax
0x180020f41  test    eax, eax
0x180020f43  js      short loc_180020FA5
0x180020f45  mov     [rbp+57h+var_80], 0
0x180020f4d  mov     rdi, [rbp+57h+var_78]
0x180020f51  mov     rax, [rdi]
0x180020f54  mov     rbx, [rax+48h]
0x180020f58  lea     rcx, [rbp+57h+var_80]
0x180020f5c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020f61  lea     rdx, [rbp+57h+var_50]
0x180020f65  lea     rcx, [rbp+57h+var_28]
0x180020f69  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180020f6e  nop
0x180020f6f  lea     r8, [rbp+57h+var_80]
0x180020f73  mov     rdx, [rax+18h]
0x180020f77  mov     rcx, rdi
0x180020f7a  mov     rax, rbx
0x180020f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f82  mov     ebx, eax
0x180020f84  test    eax, eax
0x180020f86  js      short loc_180020F9B
0x180020f88  mov     rax, [rbp+57h+var_80]
0x180020f8c  mov     [rbp+57h+var_80], 0
0x180020f94  mov     cs:?s_handlersResourceMap@Details@DataModel@SystemSettings@@3PEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@EA, rax; Windows::ApplicationModel::Resources::Core::IResourceMap * SystemSettings::DataModel::Details::s_handlersResourceMap
0x180020f9b  lea     rcx, [rbp+57h+var_80]
0x180020f9f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020fa4  nop
0x180020fa5  lea     rcx, [rbp+57h+var_78]
0x180020fa9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020fae  nop
0x180020faf  lea     rcx, [rbp+57h+var_70]
0x180020fb3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020fb8  nop
0x180020fb9  lea     rcx, [rbp+57h+var_68]
0x180020fbd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020fc2  nop
0x180020fc3  lea     rcx, [rbp+57h+var_60]
0x180020fc7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020fcc  test    ebx, ebx
0x180020fce  jns     short loc_180020FDB
0x180020fd0  mov     cs:?s_handlersResourceMap@Details@DataModel@SystemSettings@@3PEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@EA, 0; Windows::ApplicationModel::Resources::Core::IResourceMap * SystemSettings::DataModel::Details::s_handlersResourceMap
0x180020fdb  mov     [rbp+57h+var_30], 0
0x180020fe3  lea     rcx, [rbp+57h+var_58]
0x180020fe7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020fec  mov     eax, ebx
0x180020fee  mov     rcx, [rbp+57h+var_8]
0x180020ff2  xor     rcx, rsp; StackCookie
0x180020ff5  call    __security_check_cookie
0x180020ffa  lea     r11, [rsp+0A0h+var_s0]
0x180021002  mov     rbx, [r11+10h]
0x180021006  mov     rdi, [r11+18h]
0x18002100a  mov     rsp, r11
0x18002100d  pop     rbp
0x18002100e  retn
```
