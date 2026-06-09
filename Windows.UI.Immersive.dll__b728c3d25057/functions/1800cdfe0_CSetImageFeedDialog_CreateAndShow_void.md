# CSetImageFeedDialog::CreateAndShow(void)

- ea: `0x1800cdfe0`
- end: `0x1800ce388`
- name: `?CreateAndShow@CSetImageFeedDialog@@QEAAJXZ`
- size: `936`
- prototype: `__int64 __fastcall(CSetImageFeedDialog *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ceecc`

## callees

- `0x18000a910`
- `0x180013244`
- `0x18003217c`
- `0x18003cfb0`
- `0x18004d6c4`
- `0x180050ba0`
- `0x180080f5c`
- `0x1800840a0`
- `0x1800cdfe0`
- `0x1800cf05c`
- `0x1800cf168`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800ce1bc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800ce1bc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ce0e1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ce0e1`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x1800ce02f`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x1800ce02f`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800ce355`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800ce355`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1800ce054`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1800ce054`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1800ce08a`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1800ce08a`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800ce34a`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800ce34a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSetImageFeedDialog::CreateAndShow(CSetImageFeedDialog *this)
{
  HRESULT v2; // ebx
  LPVOID v3; // rdi
  __int64 (__fastcall *v4)(LPVOID, _QWORD, struct IPopupWindow **); // rbx
  UINT v5; // edx
  __int64 v6; // rbx
  int v7; // eax
  struct IPopupWindow *v8; // rbx
  __int64 (__fastcall *v9)(struct IPopupWindow *, CSetImageFeedDialog *); // r14
  CSetImageFeedDialog **v10; // rax
  CSetImageFeedDialog *v11; // rdi
  struct IPopupWindow *v13; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v14[2]; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  CSetImageFeedDialog *v16; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v17; // [rsp+50h] [rbp-B0h]
  __int64 v18; // [rsp+58h] [rbp-A8h]
  struct DirectUI::Element *v19; // [rsp+60h] [rbp-A0h] BYREF
  struct DirectUI::DUIXmlParser *v20; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Buffer[264]; // [rsp+70h] [rbp-90h] BYREF

  v20 = 0;
  v2 = DirectUI::DUIXmlParser::Create(&v20, 0, 0, 0, 0);
  if ( v2 >= 0 )
  {
    v2 = DirectUI::DUIXmlParser::SetXMLFromResource(v20, *((_DWORD *)this + 6), &_ImageBase, &_ImageBase);
    if ( v2 < 0 )
      goto LABEL_27;
    v19 = 0;
    v2 = DirectUI::DUIXmlParser::CreateElement(v20, L"main", 0, 0, 0, &v19);
    if ( v2 < 0 )
      goto LABEL_27;
    v2 = CSetImageFeedDialog::_SetDialogDUI(this, v19);
    if ( v2 < 0 )
      goto LABEL_26;
    ppv = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    v2 = CoCreateInstance(&CLSID_PopupWindowFactory, 0, 1u, &GUID_6a0017fe_df25_46eb_8a96_38df889cb5b1, &ppv);
    if ( v2 < 0 )
    {
LABEL_25:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      if ( v2 >= 0 )
      {
LABEL_27:
        DirectUI::DUIXmlParser::Destroy(v20);
        return (unsigned int)v2;
      }
LABEL_26:
      DirectUI::Element::Destroy(v19, 0);
      goto LABEL_27;
    }
    (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 1);
    v13 = 0;
    v3 = ppv;
    v4 = *(__int64 (__fastcall **)(LPVOID, _QWORD, struct IPopupWindow **))(*(_QWORD *)ppv + 72LL);
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v13);
    v2 = v4(v3, *((_QWORD *)this + 6), &v13);
    if ( v2 >= 0 )
    {
      v5 = *((_DWORD *)this + 8);
      if ( v5 == 38326 )
      {
        v16 = 0;
        v17 = 0;
        v18 = 0;
        v6 = *((_QWORD *)this + 7);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v16);
        v17 = -1;
        v18 = -1;
        if ( (int)ResourceStringCoAllocFormatMessage(&_ImageBase, 38326, &v16, v6) >= 0 )
          (*(void (__fastcall **)(struct IPopupWindow *, CSetImageFeedDialog *))(*(_QWORD *)v13 + 32LL))(v13, v16);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v16);
      }
      else if ( LoadStringW(&_ImageBase, v5, Buffer, 260) > 0 )
      {
        (*(void (__fastcall **)(struct IPopupWindow *, WCHAR *))(*(_QWORD *)v13 + 32LL))(v13, Buffer);
      }
      v2 = (*(__int64 (__fastcall **)(struct IPopupWindow *, struct DirectUI::Element *))(*(_QWORD *)v13 + 352LL))(
             v13,
             v19);
      if ( v2 >= 0 )
      {
        if ( *((_DWORD *)this + 6) != 38918 )
        {
          v14[0] = 38337;
          v7 = CSetImageFeedDialog::_SetCommands(this, v13, v14, 1u);
LABEL_19:
          v2 = v7;
          if ( v7 >= 0 )
          {
            v8 = v13;
            v9 = *(__int64 (__fastcall **)(struct IPopupWindow *, CSetImageFeedDialog *))(*(_QWORD *)v13 + 168LL);
            v16 = this;
            v17 = (__int64)CSetImageFeedDialog::OnDismissCommand;
            LODWORD(v18) = 0;
            HIDWORD(v18) = (unsigned __int64)CSetImageFeedDialog::OnDismissCommand >> 32;
            v10 = (CSetImageFeedDialog **)Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (IPopupEventHandler::*)(IPopupWindow *)>::DelegateInvokeHelper<IPopupEventHandler,_lambda_74447f3d681dc015fa527b5932f57c48_,-1,IPopupWindow *>,_lambda_74447f3d681dc015fa527b5932f57c48_>(
                                            v14,
                                            (__int64)&v16);
            v11 = *v10;
            v16 = *v10;
            *v10 = 0;
            if ( *(_QWORD *)v14 )
            {
              *(_QWORD *)v14 = 0;
              Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release();
            }
            v2 = v9(v8, v11);
            Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v16);
            if ( v2 >= 0 )
            {
              Microsoft::WRL::ComPtr<IPopupWindow>::operator=((char *)this + 16, &v13);
              v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 272LL))(*((_QWORD *)this + 2));
            }
          }
          goto LABEL_24;
        }
        v14[0] = 38330;
        v14[1] = 38329;
        v2 = CSetImageFeedDialog::_SetCommands(this, v13, v14, 2u);
        if ( v2 >= 0 )
        {
          v2 = (*(__int64 (__fastcall **)(struct IPopupWindow *, __int64))(*(_QWORD *)v13 + 88LL))(v13, 1);
          if ( v2 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(struct IPopupWindow *, __int64))(*(_QWORD *)v13 + 120LL))(v13, 1);
            goto LABEL_19;
          }
        }
      }
    }
LABEL_24:
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v13);
    goto LABEL_25;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800cdfe0  mov     [rsp-8+arg_8], rbx
0x1800cdfe5  mov     [rsp-8+arg_10], rsi
0x1800cdfea  push    rbp
0x1800cdfeb  push    rdi
0x1800cdfec  push    r12
0x1800cdfee  push    r14
0x1800cdff0  push    r15
0x1800cdff2  lea     rbp, [rsp-190h]
0x1800cdffa  sub     rsp, 290h
0x1800ce001  mov     rax, cs:__security_cookie
0x1800ce008  xor     rax, rsp
0x1800ce00b  mov     [rbp+1B0h+var_30], rax
0x1800ce012  mov     rsi, rcx
0x1800ce015  xor     r15d, r15d
0x1800ce018  mov     [rsp+2B0h+var_248], r15
0x1800ce01d  mov     [rsp+2B0h+ppv], r15
0x1800ce022  xor     r9d, r9d
0x1800ce025  xor     r8d, r8d
0x1800ce028  xor     edx, edx
0x1800ce02a  lea     rcx, [rsp+2B0h+var_248]
0x1800ce02f  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x1800ce035  mov     ebx, eax
0x1800ce037  test    eax, eax
0x1800ce039  js      loc_1800CE35B
0x1800ce03f  lea     r14, __ImageBase
0x1800ce046  mov     r9, r14
0x1800ce049  mov     r8, r14
0x1800ce04c  mov     edx, [rsi+18h]
0x1800ce04f  mov     rcx, [rsp+2B0h+var_248]
0x1800ce054  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x1800ce05a  mov     ebx, eax
0x1800ce05c  test    eax, eax
0x1800ce05e  js      loc_1800CE350
0x1800ce064  mov     [rsp+2B0h+var_250], r15
0x1800ce069  lea     rax, [rsp+2B0h+var_250]
0x1800ce06e  mov     [rsp+2B0h+var_288], rax
0x1800ce073  mov     [rsp+2B0h+ppv], r15
0x1800ce078  xor     r9d, r9d
0x1800ce07b  xor     r8d, r8d
0x1800ce07e  lea     rdx, aMain; "main"
0x1800ce085  mov     rcx, [rsp+2B0h+var_248]
0x1800ce08a  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x1800ce090  mov     ebx, eax
0x1800ce092  test    eax, eax
0x1800ce094  js      loc_1800CE350
0x1800ce09a  mov     rdx, [rsp+2B0h+var_250]; struct DirectUI::Element *
0x1800ce09f  mov     rcx, rsi; this
0x1800ce0a2  call    ?_SetDialogDUI@CSetImageFeedDialog@@AEAAJPEAVElement@DirectUI@@@Z; CSetImageFeedDialog::_SetDialogDUI(DirectUI::Element *)
0x1800ce0a7  mov     ebx, eax
0x1800ce0a9  test    eax, eax
0x1800ce0ab  js      loc_1800CE343
0x1800ce0b1  mov     [rsp+2B0h+var_270], r15
0x1800ce0b6  lea     rcx, [rsp+2B0h+var_270]
0x1800ce0bb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ce0c0  lea     rax, [rsp+2B0h+var_270]
0x1800ce0c5  mov     [rsp+2B0h+ppv], rax; ppv
0x1800ce0ca  lea     r9, _GUID_6a0017fe_df25_46eb_8a96_38df889cb5b1; riid
0x1800ce0d1  lea     r12d, [r15+1]
0x1800ce0d5  mov     r8d, r12d; dwClsContext
0x1800ce0d8  xor     edx, edx; pUnkOuter
0x1800ce0da  lea     rcx, CLSID_PopupWindowFactory; rclsid
0x1800ce0e1  call    cs:__imp_CoCreateInstance
0x1800ce0e7  mov     ebx, eax
0x1800ce0e9  test    eax, eax
0x1800ce0eb  js      loc_1800CE335
0x1800ce0f1  mov     rcx, [rsp+2B0h+var_270]
0x1800ce0f6  mov     rax, [rcx]
0x1800ce0f9  mov     edx, r12d
0x1800ce0fc  mov     rax, [rax+18h]
0x1800ce100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce105  mov     [rsp+2B0h+var_280], r15
0x1800ce10a  mov     rdi, [rsp+2B0h+var_270]
0x1800ce10f  mov     rax, [rdi]
0x1800ce112  mov     rbx, [rax+48h]
0x1800ce116  lea     rcx, [rsp+2B0h+var_280]
0x1800ce11b  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800ce120  lea     r8, [rsp+2B0h+var_280]
0x1800ce125  mov     rdx, [rsi+30h]
0x1800ce129  mov     rcx, rdi
0x1800ce12c  mov     rax, rbx
0x1800ce12f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce134  mov     ebx, eax
0x1800ce136  test    eax, eax
0x1800ce138  js      loc_1800CE32A
0x1800ce13e  mov     edx, [rsi+20h]; uID
0x1800ce141  mov     edi, 95B6h
0x1800ce146  cmp     edx, edi
0x1800ce148  jnz     short loc_1800CE1AE
0x1800ce14a  mov     [rsp+2B0h+var_268], r15
0x1800ce14f  mov     [rsp+2B0h+var_260], r15
0x1800ce154  mov     [rsp+2B0h+var_258], r15
0x1800ce159  mov     rbx, [rsi+38h]
0x1800ce15d  lea     rcx, [rsp+2B0h+var_268]
0x1800ce162  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800ce167  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ce16b  mov     [rsp+2B0h+var_260], rax
0x1800ce170  mov     [rsp+2B0h+var_258], rax
0x1800ce175  mov     r9, rbx
0x1800ce178  lea     r8, [rsp+2B0h+var_268]
0x1800ce17d  mov     edx, edi
0x1800ce17f  mov     rcx, r14
0x1800ce182  call    ResourceStringCoAllocFormatMessage
0x1800ce187  test    eax, eax
0x1800ce189  js      short loc_1800CE1A2
0x1800ce18b  mov     rcx, [rsp+2B0h+var_280]
0x1800ce190  mov     rax, [rcx]
0x1800ce193  mov     rdx, [rsp+2B0h+var_268]
0x1800ce198  mov     rax, [rax+20h]
0x1800ce19c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce1a1  nop
0x1800ce1a2  lea     rcx, [rsp+2B0h+var_268]
0x1800ce1a7  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800ce1ac  jmp     short loc_1800CE1DC
0x1800ce1ae  mov     r9d, 104h; cchBufferMax
0x1800ce1b4  lea     r8, [rsp+2B0h+Buffer]; lpBuffer
0x1800ce1b9  mov     rcx, r14; hInstance
0x1800ce1bc  call    cs:__imp_LoadStringW
0x1800ce1c2  test    eax, eax
0x1800ce1c4  jle     short loc_1800CE1DC
0x1800ce1c6  mov     rcx, [rsp+2B0h+var_280]
0x1800ce1cb  mov     rax, [rcx]
0x1800ce1ce  lea     rdx, [rsp+2B0h+Buffer]
0x1800ce1d3  mov     rax, [rax+20h]
0x1800ce1d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce1dc  mov     rcx, [rsp+2B0h+var_280]
0x1800ce1e1  mov     rax, [rcx]
0x1800ce1e4  mov     rdx, [rsp+2B0h+var_250]
0x1800ce1e9  mov     rax, [rax+160h]
0x1800ce1f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce1f5  mov     ebx, eax
0x1800ce1f7  test    eax, eax
0x1800ce1f9  js      loc_1800CE32A
0x1800ce1ff  mov     rdx, [rsp+2B0h+var_280]; struct IPopupWindow *
0x1800ce204  mov     rcx, rsi; this
0x1800ce207  cmp     dword ptr [rsi+18h], 9806h
0x1800ce20e  jnz     short loc_1800CE26E
0x1800ce210  mov     [rsp+2B0h+var_278], 95BAh
0x1800ce218  mov     [rsp+2B0h+var_278+4], 95B9h
0x1800ce220  mov     r9d, 2; unsigned int
0x1800ce226  lea     r8, [rsp+2B0h+var_278]; unsigned int *
0x1800ce22b  call    ?_SetCommands@CSetImageFeedDialog@@AEAAJPEAUIPopupWindow@@PEAII@Z; CSetImageFeedDialog::_SetCommands(IPopupWindow *,uint *,uint)
0x1800ce230  mov     ebx, eax
0x1800ce232  test    eax, eax
0x1800ce234  js      loc_1800CE32A
0x1800ce23a  mov     rcx, [rsp+2B0h+var_280]
0x1800ce23f  mov     rax, [rcx]
0x1800ce242  mov     edx, r12d
0x1800ce245  mov     rax, [rax+58h]
0x1800ce249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce24e  mov     ebx, eax
0x1800ce250  test    eax, eax
0x1800ce252  js      loc_1800CE32A
0x1800ce258  mov     rcx, [rsp+2B0h+var_280]
0x1800ce25d  mov     rax, [rcx]
0x1800ce260  mov     edx, r12d
0x1800ce263  mov     rax, [rax+78h]
0x1800ce267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce26c  jmp     short loc_1800CE283
0x1800ce26e  mov     [rsp+2B0h+var_278], 95C1h
0x1800ce276  mov     r9d, r12d; unsigned int
0x1800ce279  lea     r8, [rsp+2B0h+var_278]; unsigned int *
0x1800ce27e  call    ?_SetCommands@CSetImageFeedDialog@@AEAAJPEAUIPopupWindow@@PEAII@Z; CSetImageFeedDialog::_SetCommands(IPopupWindow *,uint *,uint)
0x1800ce283  mov     ebx, eax
0x1800ce285  test    eax, eax
0x1800ce287  js      loc_1800CE32A
0x1800ce28d  mov     rbx, [rsp+2B0h+var_280]
0x1800ce292  mov     rax, [rbx]
0x1800ce295  mov     r14, [rax+0A8h]
0x1800ce29c  mov     [rsp+2B0h+var_268], rsi
0x1800ce2a1  lea     rax, ?OnDismissCommand@CSetImageFeedDialog@@QEAAJPEAUIPopupWindow@@@Z; CSetImageFeedDialog::OnDismissCommand(IPopupWindow *)
0x1800ce2a8  mov     [rsp+2B0h+var_260], rax
0x1800ce2ad  mov     dword ptr [rsp+2B0h+var_258], r15d
0x1800ce2b2  mov     eax, dword ptr [rsp+2B0h+var_260+4]
0x1800ce2b6  mov     dword ptr [rsp+2B0h+var_258+4], eax
0x1800ce2ba  lea     rdx, [rsp+2B0h+var_268]
0x1800ce2bf  lea     rcx, [rsp+2B0h+var_278]
0x1800ce2c4  call    ??$Make@U?$DelegateInvokeHelper@UIPopupEventHandler@@V_lambda_74447f3d681dc015fa527b5932f57c48_@@$0?0PEAUIPopupWindow@@@?$DelegateArgTraits@P8IPopupEventHandler@@EAAJPEAUIPopupWindow@@@Z@Details@WRL@Microsoft@@V_lambda_74447f3d681dc015fa527b5932f57c48_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@U?$DelegateInvokeHelper@UIPopupEventHandler@@V_lambda_74447f3d681dc015fa527b5932f57c48_@@$0?0PEAUIPopupWindow@@@?$DelegateArgTraits@P8IPopupEventHandler@@EAAJPEAUIPopupWindow@@@Z@Details@WRL@Microsoft@@@12@$$QEAV_lambda_74447f3d681dc015fa527b5932f57c48_@@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (IPopupEventHandler::*)(IPopupWindow *)>::DelegateInvokeHelper<IPopupEventHandler,_lambda_74447f3d681dc015fa527b5932f57c48_,-1,IPopupWindow *>,_lambda_74447f3d681dc015fa527b5932f57c48_>(_lambda_74447f3d681dc015fa527b5932f57c48_ &&)
0x1800ce2c9  mov     rdi, [rax]
0x1800ce2cc  mov     [rsp+2B0h+var_268], rdi
0x1800ce2d1  mov     [rax], r15
0x1800ce2d4  mov     rcx, qword ptr [rsp+2B0h+var_278]
0x1800ce2d9  test    rcx, rcx
0x1800ce2dc  jz      short loc_1800CE2E9
0x1800ce2de  mov     qword ptr [rsp+2B0h+var_278], r15
0x1800ce2e3  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDialogFirstFrameRenderedHandler@Dialogs@UI@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release(void)
0x1800ce2e8  nop
0x1800ce2e9  mov     rdx, rdi
0x1800ce2ec  mov     rcx, rbx
0x1800ce2ef  mov     rax, r14
0x1800ce2f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce2f7  mov     ebx, eax
0x1800ce2f9  lea     rcx, [rsp+2B0h+var_268]
0x1800ce2fe  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800ce303  test    ebx, ebx
0x1800ce305  js      short loc_1800CE32A
0x1800ce307  lea     rdx, [rsp+2B0h+var_280]
0x1800ce30c  lea     rcx, [rsi+10h]
0x1800ce310  call    ??4?$ComPtr@UIPopupWindow@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IPopupWindow>::operator=(Microsoft::WRL::ComPtr<IPopupWindow> const &)
0x1800ce315  mov     rcx, [rsi+10h]
0x1800ce319  mov     rax, [rcx]
0x1800ce31c  mov     rax, [rax+110h]
0x1800ce323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce328  mov     ebx, eax
0x1800ce32a  lea     rcx, [rsp+2B0h+var_280]
0x1800ce32f  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800ce334  nop
0x1800ce335  lea     rcx, [rsp+2B0h+var_270]
0x1800ce33a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ce33f  test    ebx, ebx
0x1800ce341  jns     short loc_1800CE350
0x1800ce343  xor     edx, edx
0x1800ce345  mov     rcx, [rsp+2B0h+var_250]
0x1800ce34a  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x1800ce350  mov     rcx, [rsp+2B0h+var_248]
0x1800ce355  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x1800ce35b  mov     eax, ebx
0x1800ce35d  mov     rcx, [rbp+1B0h+var_30]
0x1800ce364  xor     rcx, rsp; StackCookie
0x1800ce367  call    __security_check_cookie
0x1800ce36c  lea     r11, [rsp+2B0h+var_20]
0x1800ce374  mov     rbx, [r11+38h]
0x1800ce378  mov     rsi, [r11+40h]
0x1800ce37c  mov     rsp, r11
0x1800ce37f  pop     r15
0x1800ce381  pop     r14
0x1800ce383  pop     r12
0x1800ce385  pop     rdi
0x1800ce386  pop     rbp
0x1800ce387  retn
```
