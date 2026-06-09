# CSwitchThumbnailDeviceManager::_EnsureDevice(void)

- ea: `0x1800559e8`
- end: `0x180055f05`
- name: `?_EnsureDevice@CSwitchThumbnailDeviceManager@@AEAAJXZ`
- size: `1309`
- prototype: `__int64 __fastcall(CSwitchThumbnailDeviceManager *__hidden this)`
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180055590`
- `0x18009728c`
- `0x1801e4a60`

## callees

- `0x180009dd0`
- `0x180009dfc`
- `0x18001c710`
- `0x1800559e8`
- `0x180055f0c`
- `0x180055f74`
- `0x180056000`
- `0x1800a561c`
- `0x180108558`
- `0x18010c820`
- `0x180142e10`
- `0x1801e4c18`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180055ec9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180055ec9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055d0f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055d49`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055dbb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055d0f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055d49`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055dbb`
- `dcomp!DCompositionCreateDevice2` at `0x180055cd5`
- `dcomp!DCompositionCreateDevice2` at `0x180055cd5`
- `d3d11!D3D11CreateDevice` at `0x180055abf`
- `d3d11!D3D11CreateDevice` at `0x180055b0a`
- `d3d11!D3D11CreateDevice` at `0x180055abf`
- `d3d11!D3D11CreateDevice` at `0x180055b0a`
- `d2d1!__imp_D2D1CreateFactory` at `0x180055b6c`
- `d2d1!__imp_D2D1CreateFactory` at `0x180055b6c`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180055a44`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180055a44`

## string_xrefs

- `0x180055be6`: `Windows.UI.Composition.Compositor`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CSwitchThumbnailDeviceManager::_EnsureDevice(CSwitchThumbnailDeviceManager *this)
{
  HRESULT Device; // ebx
  void *v3; // rbx
  _QWORD *v4; // r15
  __int64 (__fastcall *v5)(void *, __int64, char *); // rdi
  __int64 (__fastcall ***v6)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, _QWORD, GUID *, char *); // rbx
  char *v10; // r12
  __int64 (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v12)(_QWORD, GUID *, char *); // rbx
  void *v13; // rcx
  __int64 v14; // rcx
  _QWORD *v15; // r14
  __int64 (__fastcall ***v16)(_QWORD, GUID *, void **); // rdi
  __int64 (__fastcall *v17)(_QWORD, GUID *, void **); // rbx
  __int64 pvParam; // [rsp+50h] [rbp-39h] BYREF
  void *ppIFactory; // [rsp+58h] [rbp-31h] BYREF
  __int64 v21; // [rsp+60h] [rbp-29h] BYREF
  __int64 (__fastcall ***v22)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-19h] BYREF
  __int64 v24; // [rsp+88h] [rbp-1h]

  Device = 0;
  if ( (int)CSwitchThumbnailDeviceManager::_ValidateDevice(this) < 0 )
    CSwitchThumbnailDeviceManager::_DestroyDevice(this);
  if ( !*((_DWORD *)this + 56) )
  {
    LODWORD(pvParam) = 0;
    SystemParametersInfoW(0x1042u, 0, &pvParam, 0);
    *((_BYTE *)this + 256) = (_DWORD)pvParam != 0;
  }
  if ( !*((_QWORD *)this + 13) )
  {
    if ( (*((_BYTE *)this + 260) & 4) == 0 )
    {
      LODWORD(pvParam) = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 112);
      Device = D3D11CreateDevice(
                 0,
                 D3D_DRIVER_TYPE_HARDWARE,
                 0,
                 0x20u,
                 0,
                 0,
                 7u,
                 (ID3D11Device **)this + 14,
                 (D3D_FEATURE_LEVEL *)&pvParam,
                 0);
      if ( Device == -2005270523 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 112);
        Device = D3D11CreateDevice(
                   0,
                   D3D_DRIVER_TYPE_WARP,
                   0,
                   0x20u,
                   0,
                   0,
                   7u,
                   (ID3D11Device **)this + 14,
                   (D3D_FEATURE_LEVEL *)&pvParam,
                   0);
      }
      if ( Device < 0 )
        goto LABEL_40;
    }
    v21 = 0;
    if ( (*((_BYTE *)this + 260) & 4) == 0 )
    {
      Device = Microsoft::WRL::ComPtr<ID3D11Device>::As<IDXGIDevice>((char *)this + 112, &v21);
      if ( Device < 0 )
      {
LABEL_30:
        v14 = v21;
        if ( v21 )
        {
          v21 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
        if ( Device >= 0 )
        {
          v15 = (_QWORD *)((char *)this + 144);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 144);
          Device = CoCreateInstance(
                     &CLSID_UIAnimationTimer,
                     0,
                     1u,
                     &GUID_6b0efad1_a053_41d6_9085_33a689144665,
                     (LPVOID *)this + 18);
          if ( Device >= 0 )
          {
            ppIFactory = 0;
            v16 = (__int64 (__fastcall ***)(_QWORD, GUID *, void **))*((_QWORD *)this + 17);
            v17 = **v16;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppIFactory);
            Device = v17(v16, &GUID_195509b7_5d5e_4e3e_b278_ee3759b367ad, &ppIFactory);
            if ( Device >= 0 )
            {
              Device = (*(__int64 (__fastcall **)(_QWORD, void *, __int64))(*(_QWORD *)*v15 + 24LL))(
                         *v15,
                         ppIFactory,
                         1);
              if ( Device >= 0 )
              {
                v21 = 0;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
                Device = Microsoft::WRL::Details::MakeAndInitialize<CDCompThumbnailTimerEventHandler,IUIAnimationTimerEventHandler,>(&v21);
                if ( Device >= 0 )
                  Device = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v15 + 32LL))(*v15, v21);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
              }
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppIFactory);
          }
        }
LABEL_40:
        *((_BYTE *)this + 258) = (unsigned int)Mirror_IsThreadRTL() != 0;
        if ( Device >= 0 )
        {
          Device = CSwitchThumbnailDeviceManager::_LoadPVLInfo(this);
          if ( Device >= 0 )
          {
            LODWORD(pvParam) = 0;
            LODWORD(ppIFactory) = 4;
            RegGetValueW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\ImmersiveShell\\Switcher",
              L"AllowSlowAnimations",
              0x10u,
              0,
              &pvParam,
              (LPDWORD)&ppIFactory);
            *((_BYTE *)this + 257) = (_DWORD)pvParam != 0;
          }
        }
        return (unsigned int)Device;
      }
    }
    ppIFactory = 0;
    if ( (*((_BYTE *)this + 260) & 4) != 0 )
      goto LABEL_15;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppIFactory);
    Device = D2D1CreateFactory(
               D2D1_FACTORY_TYPE_SINGLE_THREADED,
               &GUID_94f81a73_9212_4376_9c58_b16a3a0d3992,
               0,
               &ppIFactory);
    if ( Device >= 0 )
    {
      v3 = ppIFactory;
      if ( (*((_BYTE *)this + 260) & 4) != 0 )
      {
LABEL_15:
        v4 = (_QWORD *)((char *)this + 120);
LABEL_17:
        if ( (*((_BYTE *)this + 260) & 2) != 0 )
        {
          v22 = 0;
          v24 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            &hstringHeader,
            L"Windows.UI.Composition.Compositor",
            0x22u,
            0x21u);
          Device = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<IActivationFactory>>(v24, &v22);
          if ( Device >= 0 )
          {
            pvParam = 0;
            v6 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v22;
            v7 = **v22;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pvParam);
            Device = v7(v6, &GUID_22118adf_23f1_4801_bcfa_66cbf48cc51b, &pvParam);
            if ( Device >= 0 )
            {
              v8 = pvParam;
              v9 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, GUID *, char *))(*(_QWORD *)pvParam + 48LL);
              v10 = (char *)this + 128;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 128);
              Device = v9(v8, *v4, 0, &GUID_b403ca50_7f8c_4e83_985f_cc45060036d8, (char *)this + 128);
              if ( Device >= 0 )
              {
                v11 = *(__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))v10;
                v12 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, char *))v10;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 104);
                Device = v12(v11, &GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0, (char *)this + 104);
              }
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pvParam);
          }
          v24 = 0;
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v22);
        }
        else
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 104);
          Device = DCompositionCreateDevice2(*v4, &GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0, (char *)this + 104);
        }
        if ( Device >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 136);
          Device = CoCreateInstance(
                     &CLSID_UIAnimationManager2,
                     0,
                     1u,
                     &GUID_d8b6f7d4_4109_4d3f_acee_879926968cb1,
                     (LPVOID *)this + 17);
          if ( Device >= 0 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 152);
            Device = CoCreateInstance(
                       &CLSID_UIAnimationTransitionLibrary2,
                       0,
                       1u,
                       &GUID_03cfae53_9580_4ee3_b363_2ece51b4af6a,
                       (LPVOID *)this + 19);
          }
        }
        goto LABEL_28;
      }
      v5 = *(__int64 (__fastcall **)(void *, __int64, char *))(*(_QWORD *)ppIFactory + 136LL);
      v4 = (_QWORD *)((char *)this + 120);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 120);
      Device = v5(v3, v21, (char *)this + 120);
      if ( Device >= 0 )
        goto LABEL_17;
    }
LABEL_28:
    v13 = ppIFactory;
    if ( ppIFactory )
    {
      ppIFactory = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
    }
    goto LABEL_30;
  }
  return (unsigned int)Device;
}

```

## disassembly

```asm
0x1800559e8  push    rbp
0x1800559ea  push    rbx
0x1800559eb  push    rsi
0x1800559ec  push    rdi
0x1800559ed  push    r12
0x1800559ef  push    r13
0x1800559f1  push    r14
0x1800559f3  push    r15
0x1800559f5  lea     rbp, [rsp-1Fh]
0x1800559fa  sub     rsp, 0A8h
0x180055a01  mov     rax, cs:__security_cookie
0x180055a08  xor     rax, rsp
0x180055a0b  mov     [rbp+57h+var_50], rax
0x180055a0f  mov     rsi, rcx
0x180055a12  xor     r13d, r13d
0x180055a15  mov     ebx, r13d
0x180055a18  call    ?_ValidateDevice@CSwitchThumbnailDeviceManager@@AEAAJXZ; CSwitchThumbnailDeviceManager::_ValidateDevice(void)
0x180055a1d  test    eax, eax
0x180055a1f  jns     short loc_180055A29
0x180055a21  mov     rcx, rsi; this
0x180055a24  call    ?_DestroyDevice@CSwitchThumbnailDeviceManager@@AEAAXXZ; CSwitchThumbnailDeviceManager::_DestroyDevice(void)
0x180055a29  cmp     [rsi+0E0h], r13d
0x180055a30  jnz     short loc_180055A5D
0x180055a32  mov     dword ptr [rbp+57h+pvParam], r13d
0x180055a36  xor     r9d, r9d; fWinIni
0x180055a39  lea     r8, [rbp+57h+pvParam]; pvParam
0x180055a3d  xor     edx, edx; uiParam
0x180055a3f  mov     ecx, 1042h; uiAction
0x180055a44  call    cs:__imp_SystemParametersInfoW
0x180055a4b  nop     dword ptr [rax+rax+00h]
0x180055a50  cmp     dword ptr [rbp+57h+pvParam], r13d
0x180055a54  setnz   al
0x180055a57  mov     [rsi+100h], al
0x180055a5d  lea     r14, [rsi+68h]
0x180055a61  cmp     [r14], r13
0x180055a64  jnz     loc_180055EE2
0x180055a6a  lea     rdi, [rsi+70h]
0x180055a6e  test    byte ptr [rsi+104h], 4
0x180055a75  jnz     loc_180055B20
0x180055a7b  mov     dword ptr [rbp+57h+pvParam], r13d
0x180055a7f  mov     rcx, rdi
0x180055a82  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055a87  mov     [rsp+0E0h+ppImmediateContext], r13; ppImmediateContext
0x180055a8c  lea     rax, [rbp+57h+pvParam]
0x180055a90  mov     [rsp+0E0h+pFeatureLevel], rax; pFeatureLevel
0x180055a95  mov     [rsp+0E0h+ppDevice], rdi; ppDevice
0x180055a9a  mov     r15d, 7
0x180055aa0  mov     [rsp+0E0h+SDKVersion], r15d; SDKVersion
0x180055aa5  mov     [rsp+0E0h+FeatureLevels], r13d; FeatureLevels
0x180055aaa  mov     [rsp+0E0h+pFeatureLevels], r13; pFeatureLevels
0x180055aaf  lea     r12d, [r15+19h]
0x180055ab3  mov     r9d, r12d; Flags
0x180055ab6  xor     r8d, r8d; Software
0x180055ab9  lea     edx, [r15-6]; DriverType
0x180055abd  xor     ecx, ecx; pAdapter
0x180055abf  call    cs:__imp_D3D11CreateDevice
0x180055ac6  nop     dword ptr [rax+rax+00h]
0x180055acb  mov     ebx, eax
0x180055acd  cmp     eax, 887A0005h
0x180055ad2  jnz     short loc_180055B18
0x180055ad4  mov     rcx, rdi
0x180055ad7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055adc  mov     [rsp+0E0h+ppImmediateContext], r13; ppImmediateContext
0x180055ae1  lea     rax, [rbp+57h+pvParam]
0x180055ae5  mov     [rsp+0E0h+pFeatureLevel], rax; pFeatureLevel
0x180055aea  mov     [rsp+0E0h+ppDevice], rdi; ppDevice
0x180055aef  mov     [rsp+0E0h+SDKVersion], r15d; SDKVersion
0x180055af4  mov     [rsp+0E0h+FeatureLevels], r13d; FeatureLevels
0x180055af9  mov     [rsp+0E0h+pFeatureLevels], r13; pFeatureLevels
0x180055afe  mov     r9d, r12d; Flags
0x180055b01  xor     r8d, r8d; Software
0x180055b04  lea     edx, [r15-2]; DriverType
0x180055b08  xor     ecx, ecx; pAdapter
0x180055b0a  call    cs:__imp_D3D11CreateDevice
0x180055b11  nop     dword ptr [rax+rax+00h]
0x180055b16  mov     ebx, eax
0x180055b18  test    ebx, ebx
0x180055b1a  js      loc_180055E6A
0x180055b20  mov     [rbp+57h+var_80], r13
0x180055b24  test    byte ptr [rsi+104h], 4
0x180055b2b  jnz     short loc_180055B43
0x180055b2d  lea     rdx, [rbp+57h+var_80]
0x180055b31  mov     rcx, rdi
0x180055b34  call    ??$As@UIDXGIDevice@@@?$ComPtr@UID3D11Device@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDXGIDevice@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ID3D11Device>::As<IDXGIDevice>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDXGIDevice>>)
0x180055b39  mov     ebx, eax
0x180055b3b  test    eax, eax
0x180055b3d  js      loc_180055D71
0x180055b43  mov     rbx, r13
0x180055b46  mov     [rbp+57h+ppIFactory], rbx
0x180055b4a  test    byte ptr [rsi+104h], 4
0x180055b51  jnz     short loc_180055B8F
0x180055b53  lea     rcx, [rbp+57h+ppIFactory]
0x180055b57  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055b5c  lea     r9, [rbp+57h+ppIFactory]; ppIFactory
0x180055b60  xor     r8d, r8d; pFactoryOptions
0x180055b63  lea     rdx, _GUID_94f81a73_9212_4376_9c58_b16a3a0d3992; riid
0x180055b6a  xor     ecx, ecx; factoryType
0x180055b6c  call    cs:__imp_D2D1CreateFactory
0x180055b73  nop     dword ptr [rax+rax+00h]
0x180055b78  mov     ebx, eax
0x180055b7a  test    eax, eax
0x180055b7c  js      loc_180055D57
0x180055b82  mov     rbx, [rbp+57h+ppIFactory]
0x180055b86  test    byte ptr [rsi+104h], 4
0x180055b8d  jz      short loc_180055B95
0x180055b8f  lea     r15, [rsi+78h]
0x180055b93  jmp     short loc_180055BC7
0x180055b95  mov     rax, [rbx]
0x180055b98  mov     rdi, [rax+88h]
0x180055b9f  lea     r15, [rsi+78h]
0x180055ba3  mov     rcx, r15
0x180055ba6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055bab  mov     r8, r15
0x180055bae  mov     rdx, [rbp+57h+var_80]
0x180055bb2  mov     rcx, rbx
0x180055bb5  mov     rax, rdi
0x180055bb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055bbd  mov     ebx, eax
0x180055bbf  test    eax, eax
0x180055bc1  js      loc_180055D57
0x180055bc7  test    byte ptr [rsi+104h], 2
0x180055bce  jz      loc_180055CC0
0x180055bd4  mov     [rbp+57h+var_78], r13
0x180055bd8  mov     [rbp+57h+var_58], r13
0x180055bdc  mov     r9d, 21h ; '!'; unsigned int
0x180055be2  lea     r8d, [r9+1]; unsigned int
0x180055be6  lea     rdx, ?RuntimeClass_Windows_UI_Composition_Compositor@@3QBGB; "Windows.UI.Composition.Compositor"
0x180055bed  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180055bf1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180055bf6  nop
0x180055bf7  lea     rdx, [rbp+57h+var_78]
0x180055bfb  mov     rcx, [rbp+57h+var_58]
0x180055bff  call    ??$GetActivationFactory@V?$ComPtr@UIActivationFactory@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIActivationFactory@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<IActivationFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IActivationFactory>>)
0x180055c04  mov     ebx, eax
0x180055c06  test    eax, eax
0x180055c08  js      loc_180055CB1
0x180055c0e  mov     [rbp+57h+pvParam], r13
0x180055c12  mov     rbx, [rbp+57h+var_78]
0x180055c16  mov     rax, [rbx]
0x180055c19  mov     rdi, [rax]
0x180055c1c  lea     rcx, [rbp+57h+pvParam]
0x180055c20  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055c25  lea     r8, [rbp+57h+pvParam]
0x180055c29  lea     rdx, _GUID_22118adf_23f1_4801_bcfa_66cbf48cc51b
0x180055c30  mov     rcx, rbx
0x180055c33  mov     rax, rdi
0x180055c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c3b  mov     ebx, eax
0x180055c3d  test    eax, eax
0x180055c3f  js      short loc_180055CA7
0x180055c41  mov     rdi, [rbp+57h+pvParam]
0x180055c45  mov     rax, [rdi]
0x180055c48  mov     rbx, [rax+30h]
0x180055c4c  lea     r12, [rsi+80h]
0x180055c53  mov     rcx, r12
0x180055c56  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055c5b  mov     [rsp+0E0h+pFeatureLevels], r12
0x180055c60  lea     r9, _GUID_b403ca50_7f8c_4e83_985f_cc45060036d8
0x180055c67  xor     r8d, r8d
0x180055c6a  mov     rdx, [r15]
0x180055c6d  mov     rcx, rdi
0x180055c70  mov     rax, rbx
0x180055c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c78  mov     ebx, eax
0x180055c7a  test    eax, eax
0x180055c7c  js      short loc_180055CA7
0x180055c7e  mov     rdi, [r12]
0x180055c82  mov     rax, [rdi]
0x180055c85  mov     rbx, [rax]
0x180055c88  mov     rcx, r14
0x180055c8b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055c90  mov     r8, r14
0x180055c93  lea     rdx, _GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0
0x180055c9a  mov     rcx, rdi
0x180055c9d  mov     rax, rbx
0x180055ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055ca5  mov     ebx, eax
0x180055ca7  lea     rcx, [rbp+57h+pvParam]
0x180055cab  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055cb0  nop
0x180055cb1  mov     [rbp+57h+var_58], r13
0x180055cb5  lea     rcx, [rbp+57h+var_78]
0x180055cb9  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180055cbe  jmp     short loc_180055CE3
0x180055cc0  mov     rcx, r14
0x180055cc3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055cc8  mov     r8, r14
0x180055ccb  lea     rdx, _GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0
0x180055cd2  mov     rcx, [r15]
0x180055cd5  call    cs:__imp_DCompositionCreateDevice2
0x180055cdc  nop     dword ptr [rax+rax+00h]
0x180055ce1  mov     ebx, eax
0x180055ce3  test    ebx, ebx
0x180055ce5  js      short loc_180055D57
0x180055ce7  lea     rbx, [rsi+88h]
0x180055cee  mov     rcx, rbx
0x180055cf1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055cf6  mov     [rsp+0E0h+pFeatureLevels], rbx; ppv
0x180055cfb  lea     r9, _GUID_d8b6f7d4_4109_4d3f_acee_879926968cb1; riid
0x180055d02  xor     edx, edx; pUnkOuter
0x180055d04  lea     r8d, [rdx+1]; dwClsContext
0x180055d08  lea     rcx, CLSID_UIAnimationManager2; rclsid
0x180055d0f  call    cs:__imp_CoCreateInstance
0x180055d16  nop     dword ptr [rax+rax+00h]
0x180055d1b  mov     ebx, eax
0x180055d1d  test    eax, eax
0x180055d1f  js      short loc_180055D57
0x180055d21  lea     rbx, [rsi+98h]
0x180055d28  mov     rcx, rbx
0x180055d2b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055d30  mov     [rsp+0E0h+pFeatureLevels], rbx; ppv
0x180055d35  lea     r9, _GUID_03cfae53_9580_4ee3_b363_2ece51b4af6a; riid
0x180055d3c  xor     edx, edx; pUnkOuter
0x180055d3e  lea     r8d, [rdx+1]; dwClsContext
0x180055d42  lea     rcx, CLSID_UIAnimationTransitionLibrary2; rclsid
0x180055d49  call    cs:__imp_CoCreateInstance
0x180055d50  nop     dword ptr [rax+rax+00h]
0x180055d55  mov     ebx, eax
0x180055d57  mov     rcx, [rbp+57h+ppIFactory]
0x180055d5b  test    rcx, rcx
0x180055d5e  jz      short loc_180055D71
0x180055d60  mov     [rbp+57h+ppIFactory], r13
0x180055d64  mov     rax, [rcx]
0x180055d67  mov     rax, [rax+10h]
0x180055d6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055d70  nop
0x180055d71  mov     rcx, [rbp+57h+var_80]
0x180055d75  test    rcx, rcx
0x180055d78  jz      short loc_180055D8B
0x180055d7a  mov     [rbp+57h+var_80], r13
0x180055d7e  mov     rax, [rcx]
0x180055d81  mov     rax, [rax+10h]
0x180055d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055d8a  nop
0x180055d8b  test    ebx, ebx
0x180055d8d  js      loc_180055E6A
0x180055d93  lea     r14, [rsi+90h]
0x180055d9a  mov     rcx, r14
0x180055d9d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055da2  mov     [rsp+0E0h+pFeatureLevels], r14; ppv
0x180055da7  lea     r9, _GUID_6b0efad1_a053_41d6_9085_33a689144665; riid
0x180055dae  xor     edx, edx; pUnkOuter
0x180055db0  lea     r8d, [rdx+1]; dwClsContext
0x180055db4  lea     rcx, CLSID_UIAnimationTimer; rclsid
0x180055dbb  call    cs:__imp_CoCreateInstance
0x180055dc2  nop     dword ptr [rax+rax+00h]
0x180055dc7  mov     ebx, eax
0x180055dc9  test    eax, eax
0x180055dcb  js      loc_180055E6A
0x180055dd1  mov     [rbp+57h+ppIFactory], r13
0x180055dd5  mov     rdi, [rsi+88h]
0x180055ddc  mov     rax, [rdi]
0x180055ddf  mov     rbx, [rax]
0x180055de2  lea     rcx, [rbp+57h+ppIFactory]
0x180055de6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055deb  lea     r8, [rbp+57h+ppIFactory]
0x180055def  lea     rdx, _GUID_195509b7_5d5e_4e3e_b278_ee3759b367ad
0x180055df6  mov     rcx, rdi
0x180055df9  mov     rax, rbx
0x180055dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055e01  mov     ebx, eax
0x180055e03  test    eax, eax
0x180055e05  js      short loc_180055E61
0x180055e07  mov     rcx, [r14]
0x180055e0a  mov     rax, [rcx]
0x180055e0d  mov     r8d, 1
0x180055e13  mov     rdx, [rbp+57h+ppIFactory]
0x180055e17  mov     rax, [rax+18h]
0x180055e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055e20  mov     ebx, eax
0x180055e22  test    eax, eax
0x180055e24  js      short loc_180055E61
0x180055e26  mov     [rbp+57h+var_80], r13
0x180055e2a  lea     rcx, [rbp+57h+var_80]
0x180055e2e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055e33  lea     rcx, [rbp+57h+var_80]
0x180055e37  call    ??$MakeAndInitialize@VCDCompThumbnailTimerEventHandler@@UIUIAnimationTimerEventHandler@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUIAnimationTimerEventHandler@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CDCompThumbnailTimerEventHandler,IUIAnimationTimerEventHandler,>(IUIAnimationTimerEventHandler * *)
0x180055e3c  mov     ebx, eax
0x180055e3e  test    eax, eax
0x180055e40  js      short loc_180055E57
0x180055e42  mov     rcx, [r14]
0x180055e45  mov     rax, [rcx]
0x180055e48  mov     rdx, [rbp+57h+var_80]
0x180055e4c  mov     rax, [rax+20h]
0x180055e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055e55  mov     ebx, eax
0x180055e57  lea     rcx, [rbp+57h+var_80]
0x180055e5b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055e60  nop
0x180055e61  lea     rcx, [rbp+57h+ppIFactory]
0x180055e65  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055e6a  call    Mirror_IsThreadRTL
0x180055e6f  test    eax, eax
0x180055e71  setnz   al
0x180055e74  mov     [rsi+102h], al
0x180055e7a  test    ebx, ebx
0x180055e7c  js      short loc_180055EE2
0x180055e7e  mov     rcx, rsi; this
0x180055e81  call    ?_LoadPVLInfo@CSwitchThumbnailDeviceManager@@AEAAJXZ; CSwitchThumbnailDeviceManager::_LoadPVLInfo(void)
0x180055e86  mov     ebx, eax
  ... truncated ...
```
