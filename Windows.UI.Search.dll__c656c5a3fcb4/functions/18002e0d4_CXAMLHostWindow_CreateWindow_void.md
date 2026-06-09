# CXAMLHostWindow::_CreateWindow(void)

- ea: `0x18002e0d4`
- end: `0x18002e658`
- name: `?_CreateWindow@CXAMLHostWindow@@AEAAJXZ`
- size: `1412`
- prototype: `__int64 __fastcall(CXAMLHostWindow *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002da50`

## callees

- `0x1800030b6`
- `0x180007b3c`
- `0x18000f2a8`
- `0x180010fd0`
- `0x1800120dc`
- `0x1800127ac`
- `0x180012800`
- `0x18002df54`
- `0x18002e014`
- `0x18002e0d4`
- `0x18002fa58`
- `0x18002fb9c`
- `0x18003080c`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e4bb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e4bb`
- `SHCORE!IUnknown_QueryService` at `0x18002e50d`
- `SHCORE!IUnknown_QueryService` at `0x18002e50d`
- `SHCORE!__imp_RegisterScaleChangeNotificationsForWindow` at `0x18002e3f2`
- `SHCORE!__imp_RegisterScaleChangeNotificationsForWindow` at `0x18002e3f2`
- `USER32!CreateWindowInBandEx` at `0x18002e2ae`
- `USER32!CreateWindowInBandEx` at `0x18002e2ae`
- `USER32!RegisterClassExW` at `0x18002e194`
- `USER32!RegisterClassExW` at `0x18002e194`
- `USER32!SetPropW` at `0x18002e41a`
- `USER32!SetPropW` at `0x18002e43c`
- `USER32!SetPropW` at `0x18002e41a`
- `USER32!SetPropW` at `0x18002e43c`
- `SHELL32!SHGetPropertyStoreForWindow` at `0x18002e363`
- `SHELL32!SHGetPropertyStoreForWindow` at `0x18002e363`
- `dwmapi!DwmSetWindowAttribute` at `0x18002e461`
- `dwmapi!DwmSetWindowAttribute` at `0x18002e461`
- `dwmapi!__imp_DwmpTransitionWindow` at `0x18002e3d4`
- `dwmapi!__imp_DwmpTransitionWindow` at `0x18002e3d4`
- `ext-ms-win-com-ole32-l1-1-2!RegisterDragDrop` at `0x18002e4d3`
- `ext-ms-win-com-ole32-l1-1-2!RegisterDragDrop` at `0x18002e4d3`
- `ext-ms-win-com-ole32-l1-1-0!OleInitialize` at `0x18002e481`
- `ext-ms-win-com-ole32-l1-1-0!OleInitialize` at `0x18002e481`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x18002e54b`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x18002e54b`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CXAMLHostWindow::_CreateWindow(CXAMLHostWindow *this, __int64 a2, __int64 a3)
{
  __int64 v4; // rdi
  HRESULT ResourceStringById; // r14d
  unsigned __int16 **v6; // r8
  int v7; // r11d
  __int64 WindowInBand; // rax
  __int64 (__fastcall ***v9)(_QWORD, GUID *, void **); // r14
  __int64 (__fastcall *v10)(_QWORD, GUID *, void **); // rbx
  void *v11; // rdi
  int (__fastcall *v12)(void *, _QWORD, GUID *, void **); // rbx
  void *v13; // rsi
  void (__fastcall *v14)(void *, __int64, void *, _BYTE *); // rdi
  void *v15; // rbx
  __int64 v16; // rcx
  void *ppv; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v19[8]; // [rsp+78h] [rbp-88h] BYREF
  void *v20; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v21[4]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v22; // [rsp+90h] [rbp-70h]
  __int64 v23; // [rsp+98h] [rbp-68h]
  WNDCLASSEXW v24; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING_HEADER propvar; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v26; // [rsp+108h] [rbp+8h]
  void *ppvOut[2]; // [rsp+110h] [rbp+10h] BYREF

  if ( (Microsoft_Windows_UI_SearchEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_SEARCHUI_PUBLISHER_Context, XamlHostCreateWindow_Start, a3, 1, ppvOut);
  v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 24LL))(*((_QWORD *)this + 26));
  v24.cbSize = 80;
  memset_0(&v24.style, 0, 0x4Cu);
  v24.style = 3;
  v24.lpfnWndProc = (WNDPROC)CImpWndProc::s_WndProc;
  v24.hInstance = (HINSTANCE)&_ImageBase;
  v24.hCursor = 0;
  v24.lpszClassName = *(LPCWSTR *)(v4 + 8);
  v24.cbWndExtra = 8;
  RegisterClassExW(&v24);
  ResourceStringById = CXAMLHostWindow::_AcquirePositionController((IUnknown *)this);
  if ( ResourceStringById < 0 )
    goto LABEL_39;
  *(_OWORD *)ppvOut = 0;
  ResourceStringById = (*(__int64 (__fastcall **)(_QWORD, void **))(**((_QWORD **)this + 27) + 24LL))(
                         *((_QWORD *)this + 27),
                         ppvOut);
  if ( ResourceStringById < 0 )
    goto LABEL_39;
  ResourceStringById = CXAMLHostWindow::_AcquireResourceManager(this);
  if ( ResourceStringById < 0 )
    goto LABEL_39;
  *(_QWORD *)v21 = 0;
  v22 = 0;
  v23 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v21);
  v22 = -1;
  v23 = -1;
  ResourceStringById = SearchUI::ThreadResourceHelpers::LoadResourceStringById(
                         *(SearchUI::ThreadResourceHelpers **)(v4 + 24),
                         v21,
                         v6);
  if ( ResourceStringById >= 0 )
  {
    v7 = *(_DWORD *)v4;
    if ( *(_DWORD *)v4 == 8 )
      v7 = 1;
    WindowInBand = CreateWindowInBandEx(
                     (*(_DWORD *)(v4 + 40) >> 6) & 8 | (2 * (*(_DWORD *)(v4 + 40) & 0x40 | 0x100000u)),
                     *(_QWORD *)(v4 + 8),
                     *(_QWORD *)v21,
                     2181038080LL,
                     ppvOut[0],
                     HIDWORD(ppvOut[0]),
                     LODWORD(ppvOut[1]) - LODWORD(ppvOut[0]),
                     HIDWORD(ppvOut[1]) - HIDWORD(ppvOut[0]),
                     0,
                     0,
                     &_ImageBase,
                     (char *)this + 184,
                     v7,
                     ((*(_DWORD *)(v4 + 40) >> 10) & 1) == 0);
    *((_QWORD *)this + 24) = WindowInBand;
    if ( WindowInBand || (ResourceStringById = ResultFromKnownLastError(), ResourceStringById >= 0) )
    {
      v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, void **))*((_QWORD *)this + 62);
      if ( !v9 )
        goto LABEL_45;
      ppv = 0;
      v10 = **v9;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
      ResourceStringById = v10(v9, &GUID_0bd4579f_fc8a_48ab_b3c9_aedaee3f63f2, &ppv);
      if ( ResourceStringById >= 0 )
        (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, *((_QWORD *)this + 24));
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
      if ( ResourceStringById >= 0 )
      {
LABEL_45:
        if ( !*(_QWORD *)(v4 + 32) )
          goto LABEL_19;
        ppv = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
        ResourceStringById = SHGetPropertyStoreForWindow(
                               *((HWND *)this + 24),
                               &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                               &ppv);
        if ( ResourceStringById >= 0 )
        {
          memset(&propvar, 0, sizeof(propvar));
          *(_QWORD *)&propvar.Reserved.Reserved2[8] = *(_QWORD *)(v4 + 32);
          LOWORD(propvar.Reserved.Reserved1) = 31;
          ResourceStringById = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, HSTRING_HEADER *))(*(_QWORD *)ppv + 48LL))(
                                 ppv,
                                 &PKEY_AppUserModel_ID,
                                 &propvar);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
        if ( ResourceStringById >= 0 )
        {
LABEL_19:
          CXAMLHostWindow::_UpdateAccentPolicy(this);
          DwmpTransitionWindow(*((_QWORD *)this + 24), 33558527);
          ResourceStringById = RegisterScaleChangeNotificationsForWindow(
                                 *((_QWORD *)this + 24),
                                 *((_QWORD *)this + 24),
                                 *((unsigned int *)this + 114),
                                 (char *)this + 452);
          if ( ResourceStringById >= 0 )
          {
            if ( (*(_BYTE *)(v4 + 40) & 1) != 0 )
              SetPropW(*((HWND *)this + 24), L"ForceShowInAltTab", HANDLE_FLAG_INHERIT);
            if ( (*(_BYTE *)(v4 + 40) & 8) != 0 )
              SetPropW(*((HWND *)this + 24), L"AppWindowTransitionType", (HANDLE)4);
            if ( (*(_BYTE *)(v4 + 40) & 0x20) != 0 )
            {
              LODWORD(ppv) = 1;
              DwmSetWindowAttribute(*((HWND *)this + 24), 0xDu, &ppv, 4u);
            }
            ResourceStringById = CXAMLHostWindow::_StartupXAML(this);
            if ( ResourceStringById >= 0 && (*(_DWORD *)(v4 + 40) & 0x100) != 0 )
            {
              ResourceStringById = OleInitialize(0);
              *((_DWORD *)this + 128) = ResourceStringById;
              if ( ResourceStringById >= 0 )
              {
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 272);
                ResourceStringById = CoCreateInstance(
                                       &CLSID_DragDropHelper,
                                       0,
                                       1u,
                                       &GUID_4657278b_411b_11d2_839a_00c04fd918d0,
                                       (LPVOID *)this + 34);
                if ( ResourceStringById >= 0 )
                  ResourceStringById = RegisterDragDrop(*((HWND *)this + 24), (LPDROPTARGET)this + 2);
              }
            }
          }
        }
      }
    }
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v21);
  if ( ResourceStringById < 0 )
  {
LABEL_39:
    (*(void (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 16) + 40LL))((char *)this + 128, 0);
  }
  else
  {
    ppvOut[0] = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(ppvOut);
    if ( IUnknown_QueryService(
           *((IUnknown **)this + 14),
           &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
           &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
           ppvOut) >= 0 )
    {
      v20 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v20);
      LOWORD(propvar.Reserved.Reserved1) = 21;
      *(_QWORD *)&propvar.Reserved.Reserved2[8] = *((_QWORD *)this + 24);
      if ( PropVariantToWinRTPropertyValue(
             &propvar.Reserved.Reserved1,
             &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
             &v20) >= 0 )
      {
        ppv = 0;
        v11 = ppvOut[0];
        v12 = *(int (__fastcall **)(void *, _QWORD, GUID *, void **))(*(_QWORD *)ppvOut[0] + 40LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
        if ( v12(v11, *((unsigned int *)this + 108), &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &ppv) >= 0 )
        {
          v19[0] = 0;
          v13 = ppv;
          v14 = *(void (__fastcall **)(void *, __int64, void *, _BYTE *))(*(_QWORD *)ppv + 80LL);
          v15 = v20;
          v26 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&propvar, L"XAMLHostHwnd", 0xDu, 0xCu);
          v14(v13, v26, v15, v19);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v20);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(ppvOut);
  }
  if ( (Microsoft_Windows_UI_SearchEnableBits & 1) != 0 )
    McTemplateU0q_EventWriteTransfer(v16, XamlHostCreateWindow_Stop, (unsigned int)ResourceStringById);
  return (unsigned int)ResourceStringById;
}

```

## disassembly

```asm
0x18002e0d4  mov     [rsp-8+arg_8], rbx
0x18002e0d9  mov     [rsp-8+arg_10], rsi
0x18002e0de  push    rbp
0x18002e0df  push    rdi
0x18002e0e0  push    r12
0x18002e0e2  push    r14
0x18002e0e4  push    r15
0x18002e0e6  lea     rbp, [rsp-30h]
0x18002e0eb  sub     rsp, 130h
0x18002e0f2  mov     rax, cs:__security_cookie
0x18002e0f9  xor     rax, rsp
0x18002e0fc  mov     [rbp+50h+var_30], rax
0x18002e100  mov     rsi, rcx
0x18002e103  mov     r12d, 1
0x18002e109  test    byte ptr cs:Microsoft_Windows_UI_SearchEnableBits, r12b
0x18002e110  jz      short loc_18002E131
0x18002e112  lea     rax, [rbp+50h+ppvOut]
0x18002e116  mov     [rsp+150h+var_130], rax
0x18002e11b  mov     r9d, r12d
0x18002e11e  lea     rdx, XamlHostCreateWindow_Start
0x18002e125  lea     rcx, MICROSOFT_SEARCHUI_PUBLISHER_Context
0x18002e12c  call    McGenEventWrite_EventWriteTransfer
0x18002e131  mov     rcx, [rsi+0D0h]
0x18002e138  mov     rax, [rcx]
0x18002e13b  mov     rax, [rax+18h]
0x18002e13f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e144  mov     rdi, rax
0x18002e147  mov     [rbp+50h+var_B0.cbSize], 50h ; 'P'
0x18002e14e  xor     edx, edx; Val
0x18002e150  lea     r8d, [rdx+4Ch]; Size
0x18002e154  lea     rcx, [rbp+50h+var_B0.style]; void *
0x18002e158  call    memset_0
0x18002e15d  mov     [rbp+50h+var_B0.style], 3
0x18002e164  lea     rax, ?s_WndProc@CImpWndProc@@KA_JPEAUHWND__@@I_K_J@Z; CImpWndProc::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18002e16b  mov     [rbp+50h+var_B0.lpfnWndProc], rax
0x18002e16f  lea     rax, __ImageBase
0x18002e176  mov     [rbp+50h+var_B0.hInstance], rax
0x18002e17a  xor     r15d, r15d
0x18002e17d  mov     [rbp+50h+var_B0.hCursor], r15
0x18002e181  mov     rcx, [rdi+8]
0x18002e185  mov     [rbp+50h+var_B0.lpszClassName], rcx
0x18002e189  mov     [rbp+50h+var_B0.cbWndExtra], 8
0x18002e190  lea     rcx, [rbp+50h+var_B0]; WNDCLASSEXW *
0x18002e194  call    cs:__imp_RegisterClassExW
0x18002e19a  mov     rcx, rsi; punkSite
0x18002e19d  call    ?_AcquirePositionController@CXAMLHostWindow@@AEAAJXZ; CXAMLHostWindow::_AcquirePositionController(void)
0x18002e1a2  mov     r14d, eax
0x18002e1a5  test    eax, eax
0x18002e1a7  js      loc_18002E600
0x18002e1ad  xorps   xmm0, xmm0
0x18002e1b0  movups  xmmword ptr [rbp+50h+ppvOut], xmm0
0x18002e1b4  mov     rcx, [rsi+0D8h]
0x18002e1bb  mov     rax, [rcx]
0x18002e1be  lea     rdx, [rbp+50h+ppvOut]
0x18002e1c2  mov     rax, [rax+18h]
0x18002e1c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e1cb  mov     r14d, eax
0x18002e1ce  test    eax, eax
0x18002e1d0  js      loc_18002E600
0x18002e1d6  mov     rcx, rsi; this
0x18002e1d9  call    ?_AcquireResourceManager@CXAMLHostWindow@@AEAAJXZ; CXAMLHostWindow::_AcquireResourceManager(void)
0x18002e1de  mov     r14d, eax
0x18002e1e1  test    eax, eax
0x18002e1e3  js      loc_18002E600
0x18002e1e9  mov     qword ptr [rbp+50h+var_C8], r15
0x18002e1ed  mov     [rbp+50h+var_C0], r15
0x18002e1f1  mov     [rbp+50h+var_B8], r15
0x18002e1f5  lea     rcx, [rbp+50h+var_C8]
0x18002e1f9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002e1fe  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002e202  mov     [rbp+50h+var_C0], rax
0x18002e206  mov     [rbp+50h+var_B8], rax
0x18002e20a  lea     rdx, [rbp+50h+var_C8]; unsigned __int16 *
0x18002e20e  mov     rcx, [rdi+18h]; this
0x18002e212  call    ?LoadResourceStringById@ThreadResourceHelpers@SearchUI@@YAJPEBGPEAPEAG@Z; SearchUI::ThreadResourceHelpers::LoadResourceStringById(ushort const *,ushort * *)
0x18002e217  mov     r14d, eax
0x18002e21a  test    eax, eax
0x18002e21c  js      loc_18002E4DC
0x18002e222  mov     ebx, [rdi+28h]
0x18002e225  mov     ecx, ebx
0x18002e227  and     ecx, 40h
0x18002e22a  bts     ecx, 14h
0x18002e22e  add     ecx, ecx
0x18002e230  mov     eax, ebx
0x18002e232  shr     eax, 6
0x18002e235  and     eax, 8
0x18002e238  or      ecx, eax
0x18002e23a  mov     r11d, [rdi]
0x18002e23d  cmp     r11d, 8
0x18002e241  cmovz   r11d, r12d
0x18002e245  shr     ebx, 0Ah
0x18002e248  not     ebx
0x18002e24a  and     ebx, r12d
0x18002e24d  lea     rax, [rsi+0B8h]
0x18002e254  mov     r9d, dword ptr [rbp+50h+ppvOut+0Ch]
0x18002e258  mov     r10d, dword ptr [rbp+50h+ppvOut+4]
0x18002e25c  sub     r9d, r10d
0x18002e25f  mov     edx, dword ptr [rbp+50h+ppvOut+8]
0x18002e262  mov     r8d, dword ptr [rbp+50h+ppvOut]
0x18002e266  sub     edx, r8d
0x18002e269  mov     [rsp+150h+var_E8], ebx
0x18002e26d  mov     [rsp+150h+var_F0], r11d
0x18002e272  mov     [rsp+150h+var_F8], rax
0x18002e277  lea     rax, __ImageBase
0x18002e27e  mov     [rsp+150h+var_100], rax
0x18002e283  mov     [rsp+150h+var_108], r15
0x18002e288  mov     [rsp+150h+var_110], r15
0x18002e28d  mov     [rsp+150h+var_118], r9d
0x18002e292  mov     [rsp+150h+var_120], edx
0x18002e296  mov     [rsp+150h+var_128], r10d
0x18002e29b  mov     dword ptr [rsp+150h+var_130], r8d
0x18002e2a0  mov     r9d, 82000000h
0x18002e2a6  mov     r8, qword ptr [rbp+50h+var_C8]
0x18002e2aa  mov     rdx, [rdi+8]
0x18002e2ae  call    cs:__imp_CreateWindowInBandEx
0x18002e2b4  mov     [rsi+0C0h], rax
0x18002e2bb  test    rax, rax
0x18002e2be  jnz     short loc_18002E2D0
0x18002e2c0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002e2c5  mov     r14d, eax
0x18002e2c8  test    eax, eax
0x18002e2ca  js      loc_18002E4DC
0x18002e2d0  mov     r14, [rsi+1F0h]
0x18002e2d7  test    r14, r14
0x18002e2da  jz      short loc_18002E33B
0x18002e2dc  mov     [rsp+150h+ppv], r15
0x18002e2e1  mov     rax, [r14]
0x18002e2e4  mov     rbx, [rax]
0x18002e2e7  lea     rcx, [rsp+150h+ppv]
0x18002e2ec  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002e2f1  lea     r8, [rsp+150h+ppv]
0x18002e2f6  lea     rdx, _GUID_0bd4579f_fc8a_48ab_b3c9_aedaee3f63f2
0x18002e2fd  mov     rcx, r14
0x18002e300  mov     rax, rbx
0x18002e303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e308  mov     r14d, eax
0x18002e30b  test    eax, eax
0x18002e30d  js      short loc_18002E328
0x18002e30f  mov     rcx, [rsp+150h+ppv]
0x18002e314  mov     rax, [rcx]
0x18002e317  mov     rdx, [rsi+0C0h]
0x18002e31e  mov     rax, [rax+18h]
0x18002e322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e327  nop
0x18002e328  lea     rcx, [rsp+150h+ppv]
0x18002e32d  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002e332  test    r14d, r14d
0x18002e335  js      loc_18002E4DC
0x18002e33b  cmp     [rdi+20h], r15
0x18002e33f  jz      short loc_18002E3C0
0x18002e341  mov     [rsp+150h+ppv], r15
0x18002e346  lea     rcx, [rsp+150h+ppv]
0x18002e34b  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002e350  lea     r8, [rsp+150h+ppv]; ppv
0x18002e355  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18002e35c  mov     rcx, [rsi+0C0h]; hwnd
0x18002e363  call    cs:__imp_SHGetPropertyStoreForWindow
0x18002e369  mov     r14d, eax
0x18002e36c  test    eax, eax
0x18002e36e  js      short loc_18002E3AD
0x18002e370  xorps   xmm0, xmm0
0x18002e373  xor     eax, eax
0x18002e375  movups  xmmword ptr [rbp+50h+propvar], xmm0
0x18002e379  mov     [rbp+50h+var_50], rax
0x18002e37d  mov     rax, [rdi+20h]
0x18002e381  mov     [rbp+50h+propvar+8], rax
0x18002e385  mov     eax, 1Fh
0x18002e38a  mov     word ptr [rbp+50h+propvar], ax
0x18002e38e  mov     rcx, [rsp+150h+ppv]
0x18002e393  mov     rax, [rcx]
0x18002e396  lea     r8, [rbp+50h+propvar]
0x18002e39a  lea     rdx, PKEY_AppUserModel_ID
0x18002e3a1  mov     rax, [rax+30h]
0x18002e3a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3aa  mov     r14d, eax
0x18002e3ad  lea     rcx, [rsp+150h+ppv]
0x18002e3b2  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002e3b7  test    r14d, r14d
0x18002e3ba  js      loc_18002E4DC
0x18002e3c0  mov     rcx, rsi; this
0x18002e3c3  call    ?_UpdateAccentPolicy@CXAMLHostWindow@@AEAAXXZ; CXAMLHostWindow::_UpdateAccentPolicy(void)
0x18002e3c8  mov     edx, 2000FFFh
0x18002e3cd  mov     rcx, [rsi+0C0h]
0x18002e3d4  call    cs:__imp_DwmpTransitionWindow
0x18002e3da  mov     rcx, [rsi+0C0h]
0x18002e3e1  lea     r9, [rsi+1C4h]
0x18002e3e8  mov     r8d, [rsi+1C8h]
0x18002e3ef  mov     rdx, rcx
0x18002e3f2  call    cs:__imp_RegisterScaleChangeNotificationsForWindow
0x18002e3f8  mov     r14d, eax
0x18002e3fb  test    eax, eax
0x18002e3fd  js      loc_18002E4DC
0x18002e403  test    [rdi+28h], r12b
0x18002e407  jz      short loc_18002E420
0x18002e409  mov     r8, r12; hData
0x18002e40c  lea     rdx, aForceshowinalt; "ForceShowInAltTab"
0x18002e413  mov     rcx, [rsi+0C0h]; hWnd
0x18002e41a  call    cs:__imp_SetPropW
0x18002e420  mov     ebx, 4
0x18002e425  test    byte ptr [rdi+28h], 8
0x18002e429  jz      short loc_18002E442
0x18002e42b  mov     r8d, ebx; hData
0x18002e42e  lea     rdx, aAppwindowtrans; "AppWindowTransitionType"
0x18002e435  mov     rcx, [rsi+0C0h]; hWnd
0x18002e43c  call    cs:__imp_SetPropW
0x18002e442  test    byte ptr [rdi+28h], 20h
0x18002e446  jz      short loc_18002E467
0x18002e448  mov     dword ptr [rsp+150h+ppv], r12d
0x18002e44d  mov     r9d, ebx; cbAttribute
0x18002e450  lea     r8, [rsp+150h+ppv]; pvAttribute
0x18002e455  mov     edx, 0Dh; dwAttribute
0x18002e45a  mov     rcx, [rsi+0C0h]; hwnd
0x18002e461  call    cs:__imp_DwmSetWindowAttribute
0x18002e467  mov     rcx, rsi; this
0x18002e46a  call    ?_StartupXAML@CXAMLHostWindow@@AEAAJXZ; CXAMLHostWindow::_StartupXAML(void)
0x18002e46f  mov     r14d, eax
0x18002e472  test    eax, eax
0x18002e474  js      short loc_18002E4DC
0x18002e476  test    dword ptr [rdi+28h], 100h
0x18002e47d  jz      short loc_18002E4DC
0x18002e47f  xor     ecx, ecx; pvReserved
0x18002e481  call    cs:__imp_OleInitialize
0x18002e487  mov     r14d, eax
0x18002e48a  mov     [rsi+200h], eax
0x18002e490  test    eax, eax
0x18002e492  js      short loc_18002E4DC
0x18002e494  lea     rbx, [rsi+110h]
0x18002e49b  mov     rcx, rbx
0x18002e49e  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002e4a3  mov     [rsp+150h+var_130], rbx; ppv
0x18002e4a8  lea     r9, _GUID_4657278b_411b_11d2_839a_00c04fd918d0; riid
0x18002e4af  mov     r8d, r12d; dwClsContext
0x18002e4b2  xor     edx, edx; pUnkOuter
0x18002e4b4  lea     rcx, CLSID_DragDropHelper; rclsid
0x18002e4bb  call    cs:__imp_CoCreateInstance
0x18002e4c1  mov     r14d, eax
0x18002e4c4  test    eax, eax
0x18002e4c6  js      short loc_18002E4DC
0x18002e4c8  lea     rdx, [rsi+10h]; pDropTarget
0x18002e4cc  mov     rcx, [rsi+0C0h]; hwnd
0x18002e4d3  call    cs:__imp_RegisterDragDrop
0x18002e4d9  mov     r14d, eax
0x18002e4dc  lea     rcx, [rbp+50h+var_C8]
0x18002e4e0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002e4e5  test    r14d, r14d
0x18002e4e8  js      loc_18002E600
0x18002e4ee  mov     [rbp+50h+ppvOut], r15
0x18002e4f2  lea     rcx, [rbp+50h+ppvOut]
0x18002e4f6  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002e4fb  lea     r9, [rbp+50h+ppvOut]; ppvOut
0x18002e4ff  lea     rdx, _GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd; guidService
0x18002e506  mov     r8, rdx; riid
0x18002e509  mov     rcx, [rsi+70h]; punk
0x18002e50d  call    cs:__imp_IUnknown_QueryService
0x18002e513  test    eax, eax
0x18002e515  js      loc_18002E5F5
0x18002e51b  mov     [rbp+50h+var_D0], r15
0x18002e51f  lea     rcx, [rbp+50h+var_D0]
0x18002e523  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002e528  mov     eax, 15h
0x18002e52d  mov     word ptr [rbp+50h+propvar], ax
0x18002e531  mov     rax, [rsi+0C0h]
0x18002e538  mov     [rbp+50h+propvar+8], rax
0x18002e53c  lea     r8, [rbp+50h+var_D0]; ppv
0x18002e540  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; riid
0x18002e547  lea     rcx, [rbp+50h+propvar]; propvar
0x18002e54b  call    cs:__imp_PropVariantToWinRTPropertyValue
0x18002e551  test    eax, eax
0x18002e553  js      loc_18002E5EB
0x18002e559  mov     [rsp+150h+ppv], r15
0x18002e55e  mov     rdi, [rbp+50h+ppvOut]
0x18002e562  mov     rax, [rdi]
0x18002e565  mov     rbx, [rax+28h]
0x18002e569  lea     rcx, [rsp+150h+ppv]
0x18002e56e  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002e573  lea     r9, [rsp+150h+ppv]
0x18002e578  lea     r8, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18002e57f  mov     edx, [rsi+1B0h]
0x18002e585  mov     rcx, rdi
0x18002e588  mov     rax, rbx
0x18002e58b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e590  test    eax, eax
0x18002e592  js      short loc_18002E5E0
0x18002e594  mov     [rsp+150h+var_D8], r15b
0x18002e599  mov     rsi, [rsp+150h+ppv]
0x18002e59e  mov     rax, [rsi]
0x18002e5a1  mov     rdi, [rax+50h]
0x18002e5a5  mov     rbx, [rbp+50h+var_D0]
0x18002e5a9  mov     [rbp+50h+var_48], r15
0x18002e5ad  mov     r9d, 0Ch; unsigned int
0x18002e5b3  lea     r8d, [r9+1]; unsigned int
0x18002e5b7  lea     rdx, aXamlhosthwnd; "XAMLHostHwnd"
0x18002e5be  lea     rcx, [rbp+50h+propvar]; hstringHeader
0x18002e5c2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002e5c7  nop
0x18002e5c8  lea     r9, [rsp+150h+var_D8]
0x18002e5cd  mov     r8, rbx
0x18002e5d0  mov     rdx, [rbp+50h+var_48]
0x18002e5d4  mov     rcx, rsi
0x18002e5d7  mov     rax, rdi
  ... truncated ...
```
