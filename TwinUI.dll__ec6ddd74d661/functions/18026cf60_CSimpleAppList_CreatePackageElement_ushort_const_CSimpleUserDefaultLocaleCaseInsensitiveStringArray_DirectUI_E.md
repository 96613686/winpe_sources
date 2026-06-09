# CSimpleAppList::_CreatePackageElement(ushort const *,CSimpleUserDefaultLocaleCaseInsensitiveStringArray *,DirectUI::Element * *)

- ea: `0x18026cf60`
- end: `0x18026d257`
- name: `?_CreatePackageElement@CSimpleAppList@@AEAAJPEBGPEAVCSimpleUserDefaultLocaleCaseInsensitiveStringArray@@PEAPEAVElement@DirectUI@@@Z`
- size: `759`
- prototype: `__int64 __fastcall(CSimpleAppList *__hidden this, const unsigned __int16 *, struct CSimpleUserDefaultLocaleCaseInsensitiveStringArray *, struct DirectUI::Element **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18026ca6c`

## callees

- `0x180009dfc`
- `0x1800a94b0`
- `0x18010e7ec`
- `0x180144f2c`
- `0x180144f94`
- `0x180269bdc`
- `0x18026c360`
- `0x18026cf60`
- `0x18036fde0`
- `0x1803709f4`
- `0x180370a5c`
- `0x1803bb010`

## import_xrefs

- `GDI32!DeleteObject` at `0x18026d146`
- `GDI32!DeleteObject` at `0x18026d146`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18026d089`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18026d089`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18026d1da`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18026cfbe`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18026d1be`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18026cfbe`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18026d1be`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18026d1fc`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18026d1fc`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x18026cfdb`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x18026cfdb`
- `SHCORE!__imp_SHCreateStreamOnModuleResourceW` at `0x18026d0d1`
- `SHCORE!__imp_SHCreateStreamOnModuleResourceW` at `0x18026d0d1`

## pseudocode

```c
__int64 __fastcall CSimpleAppList::_CreatePackageElement(
        CSimpleAppList *this,
        const unsigned __int16 *a2,
        struct CSimpleUserDefaultLocaleCaseInsensitiveStringArray *a3,
        struct DirectUI::Element **a4)
{
  DirectUI::DUIXmlParser *ParserForThread; // rax
  HRESULT Instance; // ebx
  __int64 v9; // rdi
  struct IWICImagingFactory *v10; // rsi
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdi
  DirectUI::DUIXmlParser *v14; // rax
  struct IWICImagingFactory *ppv; // [rsp+30h] [rbp-10h] BYREF
  struct IWICBitmapSource *v17; // [rsp+38h] [rbp-8h] BYREF
  struct DirectUI::Element *v18; // [rsp+70h] [rbp+30h] BYREF
  HGDIOBJ ho; // [rsp+88h] [rbp+48h] BYREF

  *a4 = 0;
  v18 = 0;
  ParserForThread = CDUIResourceManager::GetParserForThread((CDUIResourceManager *)g_resmgrLockScreenFlyoutDUI);
  Instance = DirectUI::DUIXmlParser::CreateElement(ParserForThread, L"LockScreenPackage", 0, 0, 0, &v18);
  if ( Instance >= 0 )
  {
    Instance = DirectUI::Element::SetAccName(v18, a2);
    if ( Instance >= 0 )
    {
      if ( dword_1804CF5F0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                       + 4LL) )
      {
        Init_thread_header(&dword_1804CF5F0);
        if ( dword_1804CF5F0 == -1 )
        {
          dword_1804CF5F4 = CLauncherSettings::GetScaleFactorForPart();
          Init_thread_footer(&dword_1804CF5F0);
        }
      }
      v9 = 10410;
      if ( dword_1804CF5F4 == 140 )
      {
        v9 = 10411;
      }
      else if ( dword_1804CF5F4 == 180 )
      {
        v9 = 10412;
      }
      ppv = 0;
      Instance = CoCreateInstance(
                   &CLSID_WICImagingFactory2,
                   0,
                   1u,
                   &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
                   (LPVOID *)&ppv);
      if ( Instance >= 0 )
      {
        v10 = ppv;
        v17 = 0;
        ho = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ho);
        Instance = SHCreateStreamOnModuleResourceW(&_ImageBase, v9, L"Image", &ho);
        if ( Instance >= 0 )
          Instance = LoadImageWithWIC(v10, ho, v11, &v17);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ho);
        if ( Instance >= 0 )
        {
          ho = 0;
          Instance = ConvertWICBitmapToHBITMAP(ppv, v17, (HBITMAP *)&ho);
          if ( Instance >= 0 )
          {
            LOBYTE(v12) = 2;
            Instance = DUI_SetDescendentElementBitmap(v18, L"LockScreenPackageImage", ho, v12, -1);
            DeleteObject(ho);
          }
          ((void (__fastcall *)(struct IWICBitmapSource *))v17->lpVtbl->Release)(v17);
        }
        ((void (__fastcall *)(struct IWICImagingFactory *))ppv->lpVtbl->Release)(ppv);
        if ( Instance >= 0 )
        {
          v13 = 0;
          while ( (unsigned __int64)(unsigned int)v13 < *((_QWORD *)a3 + 1) )
          {
            ho = 0;
            v14 = CDUIResourceManager::GetParserForThread((CDUIResourceManager *)g_resmgrLockScreenFlyoutDUI);
            Instance = DirectUI::DUIXmlParser::CreateElement(
                         v14,
                         L"LockScreenPackageApp",
                         0,
                         0,
                         0,
                         (struct DirectUI::Element **)&ho);
            if ( Instance >= 0 )
            {
              Instance = DUI_SetElementStringProperty(
                           (struct DirectUI::Element *)ho,
                           DirectUI::Element::ContentProp,
                           *(const unsigned __int16 **)(*(_QWORD *)a3 + 8 * v13),
                           (HINSTANCE)&_ImageBase);
              if ( Instance >= 0 )
              {
                Instance = DirectUI::Element::Add(v18, (struct DirectUI::Element *)ho);
                if ( Instance >= 0 )
                  ho = 0;
              }
              DUI_SafeDestroyElement((struct DirectUI::Element **)&ho);
            }
            v13 = (unsigned int)(v13 + 1);
            if ( Instance < 0 )
              goto LABEL_28;
          }
          *a4 = v18;
          v18 = 0;
        }
      }
    }
LABEL_28:
    DUI_SafeDestroyElement(&v18);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18026cf60  mov     [rsp-28h+arg_8], rbx
0x18026cf65  mov     [rsp-28h+arg_0], rcx
0x18026cf6a  push    rbp
0x18026cf6b  push    rsi
0x18026cf6c  push    rdi
0x18026cf6d  push    r14
0x18026cf6f  push    r15
0x18026cf71  mov     rbp, rsp
0x18026cf74  sub     rsp, 40h
0x18026cf78  lea     rcx, ?g_resmgrLockScreenFlyoutDUI@@3VCDUIResourceManager@@A; this
0x18026cf7f  mov     qword ptr [r9], 0
0x18026cf86  mov     r14, r9
0x18026cf89  mov     [rbp+arg_0], 0
0x18026cf91  mov     r15, r8
0x18026cf94  mov     rdi, rdx
0x18026cf97  call    ?GetParserForThread@CDUIResourceManager@@QEBAPEAVDUIXmlParser@DirectUI@@XZ; CDUIResourceManager::GetParserForThread(void)
0x18026cf9c  lea     rcx, [rbp+arg_0]
0x18026cfa0  xor     r9d, r9d
0x18026cfa3  mov     [rsp+40h+var_18], rcx
0x18026cfa8  lea     rdx, aLockscreenpack_0; "LockScreenPackage"
0x18026cfaf  mov     rcx, rax
0x18026cfb2  mov     [rsp+40h+ppv], 0
0x18026cfbb  xor     r8d, r8d
0x18026cfbe  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18026cfc5  nop     dword ptr [rax+rax+00h]
0x18026cfca  mov     ebx, eax
0x18026cfcc  test    eax, eax
0x18026cfce  js      loc_18026D243
0x18026cfd4  mov     rcx, [rbp+arg_0]
0x18026cfd8  mov     rdx, rdi
0x18026cfdb  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x18026cfe2  nop     dword ptr [rax+rax+00h]
0x18026cfe7  mov     ebx, eax
0x18026cfe9  test    eax, eax
0x18026cfeb  js      loc_18026D23A
0x18026cff1  mov     ecx, cs:_tls_index
0x18026cff7  mov     rax, gs:58h
0x18026d000  mov     edx, 4
0x18026d005  mov     rax, [rax+rcx*8]
0x18026d009  mov     eax, [rdx+rax]
0x18026d00c  cmp     cs:dword_1804CF5F0, eax
0x18026d012  jle     short loc_18026D040
0x18026d014  lea     rcx, dword_1804CF5F0
0x18026d01b  call    _Init_thread_header
0x18026d020  cmp     cs:dword_1804CF5F0, 0FFFFFFFFh
0x18026d027  jnz     short loc_18026D040
0x18026d029  call    ?GetScaleFactorForPart@CLauncherSettings@@QEAA?AW4DEVICE_SCALE_FACTOR@@W4ScalablePart@@@Z; CLauncherSettings::GetScaleFactorForPart(ScalablePart)
0x18026d02e  lea     rcx, dword_1804CF5F0
0x18026d035  mov     cs:dword_1804CF5F4, eax
0x18026d03b  call    _Init_thread_footer
0x18026d040  mov     ecx, cs:dword_1804CF5F4
0x18026d046  mov     edi, 28AAh
0x18026d04b  sub     ecx, 8Ch
0x18026d051  jz      short loc_18026D05F
0x18026d053  cmp     ecx, 28h ; '('
0x18026d056  jnz     short loc_18026D064
0x18026d058  mov     edi, 28ACh
0x18026d05d  jmp     short loc_18026D064
0x18026d05f  mov     edi, 28ABh
0x18026d064  xor     edx, edx; pUnkOuter
0x18026d066  mov     [rbp+var_10], 0
0x18026d06e  lea     rax, [rbp+var_10]
0x18026d072  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18026d079  mov     [rsp+40h+ppv], rax; ppv
0x18026d07e  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18026d085  lea     r8d, [rdx+1]; dwClsContext
0x18026d089  call    cs:__imp_CoCreateInstance
0x18026d090  nop     dword ptr [rax+rax+00h]
0x18026d095  mov     ebx, eax
0x18026d097  test    eax, eax
0x18026d099  js      loc_18026D23A
0x18026d09f  mov     rsi, [rbp+var_10]
0x18026d0a3  lea     rcx, [rbp+ho]
0x18026d0a7  mov     [rbp+var_8], 0
0x18026d0af  mov     [rbp+ho], 0
0x18026d0b7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026d0bc  lea     r9, [rbp+ho]
0x18026d0c0  mov     rdx, rdi
0x18026d0c3  lea     r8, aImage_0; "Image"
0x18026d0ca  lea     rcx, __ImageBase
0x18026d0d1  call    cs:__imp_SHCreateStreamOnModuleResourceW
0x18026d0d8  nop     dword ptr [rax+rax+00h]
0x18026d0dd  mov     ebx, eax
0x18026d0df  test    eax, eax
0x18026d0e1  js      short loc_18026D0F5
0x18026d0e3  mov     rdx, [rbp+ho]
0x18026d0e7  lea     r9, [rbp+var_8]
0x18026d0eb  mov     rcx, rsi
0x18026d0ee  call    ?LoadImageWithWIC@@YAJPEAUIWICImagingFactory@@PEAUIStream@@W4LOAD_IMAGE_WITH_WIC_OPTION@@PEAPEAUIWICBitmapSource@@PEAPEAUIWICBitmapFrameDecode@@PEAU_GUID@@@Z; LoadImageWithWIC(IWICImagingFactory *,IStream *,LOAD_IMAGE_WITH_WIC_OPTION,IWICBitmapSource * *,IWICBitmapFrameDecode * *,_GUID *)
0x18026d0f3  mov     ebx, eax
0x18026d0f5  lea     rcx, [rbp+ho]
0x18026d0f9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026d0fe  test    ebx, ebx
0x18026d100  js      short loc_18026D162
0x18026d102  mov     rdx, [rbp+var_8]; struct IWICBitmapSource *
0x18026d106  lea     r8, [rbp+ho]; HBITMAP *
0x18026d10a  mov     rcx, [rbp+var_10]; struct IWICImagingFactory *
0x18026d10e  mov     [rbp+ho], 0
0x18026d116  call    ?ConvertWICBitmapToHBITMAP@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@PEAPEAUHBITMAP__@@@Z; ConvertWICBitmapToHBITMAP(IWICImagingFactory *,IWICBitmapSource *,HBITMAP__ * *)
0x18026d11b  mov     ebx, eax
0x18026d11d  test    eax, eax
0x18026d11f  js      short loc_18026D152
0x18026d121  mov     r8, [rbp+ho]
0x18026d125  lea     rdx, aLockscreenpack; "LockScreenPackageImage"
0x18026d12c  mov     rcx, [rbp+arg_0]
0x18026d130  mov     r9b, 2
0x18026d133  mov     dword ptr [rsp+40h+ppv], 0FFFFFFFFh
0x18026d13b  call    ?DUI_SetDescendentElementBitmap@@YAJPEAVElement@DirectUI@@PEBGPEAUHBITMAP__@@EIW4ImageRtlMode@@@Z; DUI_SetDescendentElementBitmap(DirectUI::Element *,ushort const *,HBITMAP__ *,uchar,uint,ImageRtlMode)
0x18026d140  mov     rcx, [rbp+ho]; ho
0x18026d144  mov     ebx, eax
0x18026d146  call    cs:__imp_DeleteObject
0x18026d14d  nop     dword ptr [rax+rax+00h]
0x18026d152  mov     rcx, [rbp+var_8]
0x18026d156  mov     rax, [rcx]
0x18026d159  mov     rax, [rax+10h]
0x18026d15d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026d162  mov     rcx, [rbp+var_10]
0x18026d166  mov     rax, [rcx]
0x18026d169  mov     rax, [rax+10h]
0x18026d16d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026d172  test    ebx, ebx
0x18026d174  js      loc_18026D23A
0x18026d17a  xor     edi, edi
0x18026d17c  mov     esi, edi
0x18026d17e  cmp     rsi, [r15+8]
0x18026d182  jnb     loc_18026D22B
0x18026d188  lea     rcx, ?g_resmgrLockScreenFlyoutDUI@@3VCDUIResourceManager@@A; this
0x18026d18f  mov     [rbp+ho], 0
0x18026d197  call    ?GetParserForThread@CDUIResourceManager@@QEBAPEAVDUIXmlParser@DirectUI@@XZ; CDUIResourceManager::GetParserForThread(void)
0x18026d19c  lea     rcx, [rbp+ho]
0x18026d1a0  xor     r9d, r9d
0x18026d1a3  mov     [rsp+40h+var_18], rcx
0x18026d1a8  lea     rdx, aLockscreenpack_1; "LockScreenPackageApp"
0x18026d1af  mov     rcx, rax
0x18026d1b2  mov     [rsp+40h+ppv], 0
0x18026d1bb  xor     r8d, r8d
0x18026d1be  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18026d1c5  nop     dword ptr [rax+rax+00h]
0x18026d1ca  mov     ebx, eax
0x18026d1cc  test    eax, eax
0x18026d1ce  js      short loc_18026D21F
0x18026d1d0  mov     r8, [r15]
0x18026d1d3  lea     r9, __ImageBase; HINSTANCE
0x18026d1da  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; const struct DirectUI::PropertyInfo *(*)(void)
0x18026d1e1  mov     rcx, [rbp+ho]; struct DirectUI::Element *
0x18026d1e5  mov     r8, [r8+rdi*8]; unsigned __int16 *
0x18026d1e9  call    ?DUI_SetElementStringProperty@@YAJPEAVElement@DirectUI@@P6APEBUPropertyInfo@2@XZPEBGPEAUHINSTANCE__@@@Z; DUI_SetElementStringProperty(DirectUI::Element *,DirectUI::PropertyInfo const * (*)(void),ushort const *,HINSTANCE__ *)
0x18026d1ee  mov     ebx, eax
0x18026d1f0  test    eax, eax
0x18026d1f2  js      short loc_18026D216
0x18026d1f4  mov     rdx, [rbp+ho]
0x18026d1f8  mov     rcx, [rbp+arg_0]
0x18026d1fc  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18026d203  nop     dword ptr [rax+rax+00h]
0x18026d208  mov     ebx, eax
0x18026d20a  test    eax, eax
0x18026d20c  js      short loc_18026D216
0x18026d20e  mov     [rbp+ho], 0
0x18026d216  lea     rcx, [rbp+ho]; struct DirectUI::Element **
0x18026d21a  call    ?DUI_SafeDestroyElement@@YAXPEAPEAVElement@DirectUI@@@Z; DUI_SafeDestroyElement(DirectUI::Element * *)
0x18026d21f  inc     edi
0x18026d221  test    ebx, ebx
0x18026d223  jns     loc_18026D17C
0x18026d229  jmp     short loc_18026D23A
0x18026d22b  mov     rax, [rbp+arg_0]
0x18026d22f  mov     [r14], rax
0x18026d232  mov     [rbp+arg_0], 0
0x18026d23a  lea     rcx, [rbp+arg_0]; struct DirectUI::Element **
0x18026d23e  call    ?DUI_SafeDestroyElement@@YAXPEAPEAVElement@DirectUI@@@Z; DUI_SafeDestroyElement(DirectUI::Element * *)
0x18026d243  mov     eax, ebx
0x18026d245  mov     rbx, [rsp+40h+arg_8]
0x18026d24a  add     rsp, 40h
0x18026d24e  pop     r15
0x18026d250  pop     r14
0x18026d252  pop     rdi
0x18026d253  pop     rsi
0x18026d254  pop     rbp
0x18026d255  retn
```
