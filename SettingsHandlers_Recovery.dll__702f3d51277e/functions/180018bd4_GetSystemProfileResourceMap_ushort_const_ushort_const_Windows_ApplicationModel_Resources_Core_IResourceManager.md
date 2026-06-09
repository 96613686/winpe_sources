# GetSystemProfileResourceMap(ushort const *,ushort const *,Windows::ApplicationModel::Resources::Core::IResourceManager * *,Windows::ApplicationModel::Resources::Core::IResourceMap * *)

- ea: `0x180018bd4`
- end: `0x180018e48`
- name: `?GetSystemProfileResourceMap@@YAJPEBG0PEAPEAUIResourceManager@Core@Resources@ApplicationModel@Windows@@PEAPEAUIResourceMap@2345@@Z`
- size: `628`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct IResourceManager **, struct Windows::ApplicationModel::Resources::Core::IResourceMap **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001868c`

## callees

- `0x180002350`
- `0x180018bd4`
- `0x18001d6bc`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018c0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018ce8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018d33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018c0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018ce8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018d33`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180018c49`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180018c49`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall GetSystemProfileResourceMap(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct IResourceManager **a3,
        struct Windows::ApplicationModel::Resources::Core::IResourceMap **a4)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int ActivationFactory; // ebx
  _QWORD *v8; // rbx
  __int64 v9; // rdi
  HRESULT v10; // eax
  int v11; // edx
  unsigned int v12; // r8d
  _QWORD *v13; // rbx
  __int64 v14; // rdi
  HRESULT v15; // eax
  int v16; // edx
  unsigned int v17; // r8d
  struct Windows::ApplicationModel::Resources::Core::IResourceMap *v18; // rcx
  _QWORD *v19; // rcx
  _QWORD *v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 (__fastcall ***v23)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // [rsp+20h] [rbp-49h] BYREF
  struct Windows::ApplicationModel::Resources::Core::IResourceMap *v26; // [rsp+28h] [rbp-41h] BYREF
  _QWORD *v27; // [rsp+30h] [rbp-39h] BYREF
  _QWORD *v28; // [rsp+38h] [rbp-31h] BYREF
  __int64 v29; // [rsp+40h] [rbp-29h] BYREF
  __int64 v30; // [rsp+48h] [rbp-21h] BYREF
  HSTRING_HEADER v31; // [rsp+50h] [rbp-19h] BYREF
  HSTRING v32; // [rsp+68h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+7h] BYREF
  HSTRING string; // [rsp+88h] [rbp+1Fh] BYREF

  v25 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(
         L"Windows.ApplicationModel.Resources.Core.ResourceManager",
         0x37u,
         &hstringHeader,
         &string);
  if ( v4 < 0 )
    goto LABEL_28;
  ActivationFactory = RoGetActivationFactory(string, &GUID_1cc0fdfc_69ee_4e43_9901_47f12687baf7, &v25);
  if ( ActivationFactory < 0 )
  {
LABEL_23:
    SystemSettings::DataModel::Details::s_handlersResourceMap = 0;
    goto LABEL_24;
  }
  v30 = 0;
  ActivationFactory = (**v25)(v25, &GUID_4a8eac58_b652_459d_8de1_239471e8b22b, &v30);
  if ( ActivationFactory >= 0 )
  {
    v29 = 0;
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 48LL))(v30, &v29);
    if ( ActivationFactory < 0 )
    {
LABEL_18:
      v21 = v29;
      if ( v29 )
      {
        v29 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      goto LABEL_20;
    }
    v28 = 0;
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v29 + 56LL))(v29, &v28);
    if ( ActivationFactory < 0 )
    {
LABEL_16:
      v20 = v28;
      if ( v28 )
      {
        v28 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v20 + 16LL))(v20);
      }
      goto LABEL_18;
    }
    v27 = 0;
    v8 = v28;
    v9 = *v28;
    v32 = 0;
    v10 = WindowsCreateStringReference(L"Windows.UI.SettingsHandlers-nt", 0x1Eu, &v31, &v32);
    if ( v10 < 0 )
    {
LABEL_29:
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v10, v11, v12);
      JUMPOUT(0x180018E47LL);
    }
    ActivationFactory = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, _QWORD **))(v9 + 48))(v8, v32, &v27);
    if ( ActivationFactory < 0 )
    {
LABEL_14:
      v19 = v27;
      if ( v27 )
      {
        v27 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
      }
      goto LABEL_16;
    }
    v26 = 0;
    v13 = v27;
    v14 = *v27;
    v32 = 0;
    v15 = WindowsCreateStringReference(L"Resources", 9u, &v31, &v32);
    if ( v15 >= 0 )
    {
      ActivationFactory = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, struct Windows::ApplicationModel::Resources::Core::IResourceMap **))(v14 + 72))(
                            v13,
                            v32,
                            &v26);
      if ( ActivationFactory < 0 )
      {
        v18 = v26;
      }
      else
      {
        v18 = 0;
        SystemSettings::DataModel::Details::s_handlersResourceMap = v26;
      }
      if ( v18 )
      {
        v26 = 0;
        (*(void (__fastcall **)(struct Windows::ApplicationModel::Resources::Core::IResourceMap *))(*(_QWORD *)v18 + 16LL))(v18);
      }
      goto LABEL_14;
    }
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v15, v16, v17);
LABEL_28:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    goto LABEL_29;
  }
LABEL_20:
  v22 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  if ( ActivationFactory < 0 )
    goto LABEL_23;
LABEL_24:
  string = 0;
  v23 = v25;
  if ( v25 )
  {
    v25 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v23)[2])(v23);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180018bd4  push    rbp
0x180018bd6  push    rbx
0x180018bd7  push    rsi
0x180018bd8  push    rdi
0x180018bd9  lea     rbp, [rsp-3Fh]
0x180018bde  sub     rsp, 0A8h
0x180018be5  mov     rax, cs:__security_cookie
0x180018bec  xor     rax, rsp
0x180018bef  mov     [rbp+57h+var_30], rax
0x180018bf3  xor     esi, esi
0x180018bf5  mov     [rbp+57h+var_A0], rsi
0x180018bf9  mov     [rbp+57h+string], rsi
0x180018bfd  lea     r9, [rbp+57h+string]; string
0x180018c01  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180018c05  lea     edx, [rsi+37h]; length
0x180018c08  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Resources_Core_ResourceManager@@3QBGB; "Windows.ApplicationModel.Resources.Core"...
0x180018c0f  call    cs:__imp_WindowsCreateStringReference
0x180018c15  test    eax, eax
0x180018c17  js      loc_180018E38
0x180018c1d  mov     rbx, [rbp+57h+string]
0x180018c21  mov     rcx, [rbp+57h+var_A0]
0x180018c25  test    rcx, rcx
0x180018c28  jz      short loc_180018C3B
0x180018c2a  mov     [rbp+57h+var_A0], rsi
0x180018c2e  mov     rax, [rcx]
0x180018c31  mov     rax, [rax+10h]
0x180018c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c3a  nop
0x180018c3b  lea     r8, [rbp+57h+var_A0]
0x180018c3f  lea     rdx, _GUID_1cc0fdfc_69ee_4e43_9901_47f12687baf7
0x180018c46  mov     rcx, rbx
0x180018c49  call    cs:__imp_RoGetActivationFactory
0x180018c4f  mov     ebx, eax
0x180018c51  test    eax, eax
0x180018c53  js      loc_180018DF1
0x180018c59  mov     [rbp+57h+var_78], rsi
0x180018c5d  mov     rcx, [rbp+57h+var_A0]
0x180018c61  mov     rax, [rcx]
0x180018c64  lea     r8, [rbp+57h+var_78]
0x180018c68  lea     rdx, _GUID_4a8eac58_b652_459d_8de1_239471e8b22b
0x180018c6f  mov     rax, [rax]
0x180018c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c77  mov     ebx, eax
0x180018c79  test    eax, eax
0x180018c7b  js      loc_180018DD3
0x180018c81  mov     [rbp+57h+var_80], rsi
0x180018c85  mov     rcx, [rbp+57h+var_78]
0x180018c89  mov     rax, [rcx]
0x180018c8c  lea     rdx, [rbp+57h+var_80]
0x180018c90  mov     rax, [rax+30h]
0x180018c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c99  mov     ebx, eax
0x180018c9b  test    eax, eax
0x180018c9d  js      loc_180018DB9
0x180018ca3  mov     [rbp+57h+var_88], rsi
0x180018ca7  mov     rcx, [rbp+57h+var_80]
0x180018cab  mov     rax, [rcx]
0x180018cae  lea     rdx, [rbp+57h+var_88]
0x180018cb2  mov     rax, [rax+38h]
0x180018cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018cbb  mov     ebx, eax
0x180018cbd  test    eax, eax
0x180018cbf  js      loc_180018D9F
0x180018cc5  mov     [rbp+57h+var_90], rsi
0x180018cc9  mov     rbx, [rbp+57h+var_88]
0x180018ccd  mov     rdi, [rbx]
0x180018cd0  mov     [rbp+57h+var_58], rsi
0x180018cd4  lea     r9, [rbp+57h+var_58]; string
0x180018cd8  lea     r8, [rbp+57h+var_70]; hstringHeader
0x180018cdc  mov     edx, 1Eh; length
0x180018ce1  lea     rcx, aWindowsUiSetti; "Windows.UI.SettingsHandlers-nt"
0x180018ce8  call    cs:__imp_WindowsCreateStringReference
0x180018cee  test    eax, eax
0x180018cf0  js      loc_180018E40
0x180018cf6  lea     r8, [rbp+57h+var_90]
0x180018cfa  mov     rdx, [rbp+57h+var_58]
0x180018cfe  mov     rcx, rbx
0x180018d01  mov     rax, [rdi+30h]
0x180018d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d0a  mov     ebx, eax
0x180018d0c  test    eax, eax
0x180018d0e  js      short loc_180018D85
0x180018d10  mov     [rbp+57h+var_98], rsi
0x180018d14  mov     rbx, [rbp+57h+var_90]
0x180018d18  mov     rdi, [rbx]
0x180018d1b  mov     [rbp+57h+var_58], rsi
0x180018d1f  lea     r9, [rbp+57h+var_58]; string
0x180018d23  lea     r8, [rbp+57h+var_70]; hstringHeader
0x180018d27  mov     edx, 9; length
0x180018d2c  lea     rcx, aResources; "Resources"
0x180018d33  call    cs:__imp_WindowsCreateStringReference
0x180018d39  test    eax, eax
0x180018d3b  js      loc_180018E30
0x180018d41  lea     r8, [rbp+57h+var_98]
0x180018d45  mov     rdx, [rbp+57h+var_58]
0x180018d49  mov     rcx, rbx
0x180018d4c  mov     rax, [rdi+48h]
0x180018d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d55  mov     ebx, eax
0x180018d57  test    eax, eax
0x180018d59  js      short loc_180018D6B
0x180018d5b  mov     rax, [rbp+57h+var_98]
0x180018d5f  mov     rcx, rsi
0x180018d62  mov     cs:?s_handlersResourceMap@Details@DataModel@SystemSettings@@3PEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@EA, rax; Windows::ApplicationModel::Resources::Core::IResourceMap * SystemSettings::DataModel::Details::s_handlersResourceMap
0x180018d69  jmp     short loc_180018D6F
0x180018d6b  mov     rcx, [rbp+57h+var_98]
0x180018d6f  test    rcx, rcx
0x180018d72  jz      short loc_180018D85
0x180018d74  mov     [rbp+57h+var_98], rsi
0x180018d78  mov     rax, [rcx]
0x180018d7b  mov     rax, [rax+10h]
0x180018d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d84  nop
0x180018d85  mov     rcx, [rbp+57h+var_90]
0x180018d89  test    rcx, rcx
0x180018d8c  jz      short loc_180018D9F
0x180018d8e  mov     [rbp+57h+var_90], rsi
0x180018d92  mov     rax, [rcx]
0x180018d95  mov     rax, [rax+10h]
0x180018d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d9e  nop
0x180018d9f  mov     rcx, [rbp+57h+var_88]
0x180018da3  test    rcx, rcx
0x180018da6  jz      short loc_180018DB9
0x180018da8  mov     [rbp+57h+var_88], rsi
0x180018dac  mov     rax, [rcx]
0x180018daf  mov     rax, [rax+10h]
0x180018db3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018db8  nop
0x180018db9  mov     rcx, [rbp+57h+var_80]
0x180018dbd  test    rcx, rcx
0x180018dc0  jz      short loc_180018DD3
0x180018dc2  mov     [rbp+57h+var_80], rsi
0x180018dc6  mov     rax, [rcx]
0x180018dc9  mov     rax, [rax+10h]
0x180018dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018dd2  nop
0x180018dd3  mov     rcx, [rbp+57h+var_78]
0x180018dd7  test    rcx, rcx
0x180018dda  jz      short loc_180018DED
0x180018ddc  mov     [rbp+57h+var_78], rsi
0x180018de0  mov     rax, [rcx]
0x180018de3  mov     rax, [rax+10h]
0x180018de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018dec  nop
0x180018ded  test    ebx, ebx
0x180018def  jns     short loc_180018DF8
0x180018df1  mov     cs:?s_handlersResourceMap@Details@DataModel@SystemSettings@@3PEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@EA, rsi; Windows::ApplicationModel::Resources::Core::IResourceMap * SystemSettings::DataModel::Details::s_handlersResourceMap
0x180018df8  mov     [rbp+57h+string], rsi
0x180018dfc  mov     rcx, [rbp+57h+var_A0]
0x180018e00  test    rcx, rcx
0x180018e03  jz      short loc_180018E16
0x180018e05  mov     [rbp+57h+var_A0], rsi
0x180018e09  mov     rax, [rcx]
0x180018e0c  mov     rax, [rax+10h]
0x180018e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e15  nop
0x180018e16  mov     eax, ebx
0x180018e18  mov     rcx, [rbp+57h+var_30]
0x180018e1c  xor     rcx, rsp; StackCookie
0x180018e1f  call    __security_check_cookie
0x180018e24  add     rsp, 0A8h
0x180018e2b  pop     rdi
0x180018e2c  pop     rsi
0x180018e2d  pop     rbx
0x180018e2e  pop     rbp
0x180018e2f  retn
0x180018e30  mov     ecx, eax; this
0x180018e32  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180018e37  nop
0x180018e38  mov     ecx, eax; this
0x180018e3a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180018e3f  nop
0x180018e40  mov     ecx, eax; this
0x180018e42  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
