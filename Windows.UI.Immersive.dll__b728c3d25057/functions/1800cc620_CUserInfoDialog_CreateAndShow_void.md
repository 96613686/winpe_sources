# CUserInfoDialog::_CreateAndShow(void)

- ea: `0x1800cc620`
- end: `0x1800cc95f`
- name: `?_CreateAndShow@CUserInfoDialog@@AEAAJXZ`
- size: `831`
- prototype: `__int64 __fastcall(CUserInfoDialog *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800cc4c0`
- `0x1800cc540`

## callees

- `0x180013244`
- `0x18003217c`
- `0x18003cfb0`
- `0x180050ba0`
- `0x180080f5c`
- `0x1800840a0`
- `0x1800cc620`
- `0x1800ccaa8`
- `0x1800ccba0`
- `0x1800d5edc`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800cc7dd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800cc7dd`
- `USER32!GetWindowBand` at `0x1800cc762`
- `USER32!GetWindowBand` at `0x1800cc762`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800cc739`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800cc739`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x1800cc680`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x1800cc680`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800cc933`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800cc933`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1800cc6a5`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1800cc6a5`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1800cc6e0`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1800cc6e0`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800cc929`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800cc929`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CUserInfoDialog::_CreateAndShow(CUserInfoDialog *this)
{
  HRESULT v2; // ebx
  __int64 v3; // rcx
  BOOL v4; // ebx
  LPVOID v5; // rdi
  __int64 (__fastcall *v6)(LPVOID, _QWORD, struct IPopupWindow **); // rbx
  unsigned int v7; // r9d
  struct IPopupWindow *v8; // rbx
  __int64 (__fastcall *v9)(struct IPopupWindow *, __int64); // r14
  __int64 *v10; // rax
  __int64 v11; // rdi
  unsigned int v13[2]; // [rsp+30h] [rbp-89h] BYREF
  struct IPopupWindow *v14; // [rsp+38h] [rbp-81h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-79h] BYREF
  struct DirectUI::Element *v16; // [rsp+48h] [rbp-71h] BYREF
  struct DirectUI::DUIXmlParser *v17; // [rsp+50h] [rbp-69h] BYREF
  _QWORD v18[2]; // [rsp+58h] [rbp-61h] BYREF
  int v19; // [rsp+68h] [rbp-51h]
  int v20; // [rsp+6Ch] [rbp-4Dh]
  WCHAR Buffer[64]; // [rsp+70h] [rbp-49h] BYREF

  if ( *((_DWORD *)this + 6) != 38913
    || (v2 = DirectUI::ClassInfo<UserTile,DirectUI::Element,DirectUI::StandardCreator<UserTile>>::Register(), v2 >= 0) )
  {
    v17 = 0;
    v2 = DirectUI::DUIXmlParser::Create(&v17, 0, 0, 0, 0);
    if ( v2 >= 0 )
    {
      v2 = DirectUI::DUIXmlParser::SetXMLFromResource(v17, *((_DWORD *)this + 6), &_ImageBase, &_ImageBase);
      if ( v2 >= 0 )
      {
        v16 = 0;
        v2 = DirectUI::DUIXmlParser::CreateElement(v17, L"main", 0, 0, 0, &v16);
        if ( v2 >= 0 )
        {
          v2 = CUserInfoDialog::_SetDialogDUI(this, v16);
          if ( v2 < 0 )
            goto LABEL_25;
          ppv = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
          v2 = CoCreateInstance(&CLSID_PopupWindowFactory, 0, 1u, &GUID_6a0017fe_df25_46eb_8a96_38df889cb5b1, &ppv);
          if ( v2 >= 0 )
          {
            v3 = *((_QWORD *)this + 7);
            v13[0] = 0;
            v4 = 1;
            if ( v3 && (unsigned int)GetWindowBand(v3, v13) )
              v4 = v13[0] == 1;
            (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, (unsigned int)(8 * v4 + 1));
            v14 = 0;
            v5 = ppv;
            v6 = *(__int64 (__fastcall **)(LPVOID, _QWORD, struct IPopupWindow **))(*(_QWORD *)ppv + 72LL);
            Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v14);
            v2 = v6(v5, *((_QWORD *)this + 7), &v14);
            if ( v2 >= 0 )
            {
              if ( LoadStringW(&_ImageBase, *((_DWORD *)this + 7), Buffer, 64) > 0 )
                (*(void (__fastcall **)(struct IPopupWindow *, WCHAR *))(*(_QWORD *)v14 + 32LL))(v14, Buffer);
              v2 = (*(__int64 (__fastcall **)(struct IPopupWindow *, struct DirectUI::Element *))(*(_QWORD *)v14 + 352LL))(
                     v14,
                     v16);
              if ( v2 >= 0 )
              {
                if ( *((_DWORD *)this + 6) == 38913 )
                {
                  v13[0] = 38322;
                  v13[1] = 38321;
                  v7 = 2;
                }
                else
                {
                  v13[0] = 38337;
                  v7 = 1;
                }
                v2 = CUserInfoDialog::_SetCommands(this, v14, v13, v7);
                if ( v2 >= 0 )
                {
                  v8 = v14;
                  v9 = *(__int64 (__fastcall **)(struct IPopupWindow *, __int64))(*(_QWORD *)v14 + 168LL);
                  v18[0] = this;
                  v18[1] = CUserInfoDialog::CancelDialog;
                  v19 = 0;
                  v20 = (unsigned __int64)CUserInfoDialog::CancelDialog >> 32;
                  v10 = Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (IPopupEventHandler::*)(IPopupWindow *)>::DelegateInvokeHelper<IPopupEventHandler,_lambda_74447f3d681dc015fa527b5932f57c48_,-1,IPopupWindow *>,_lambda_74447f3d681dc015fa527b5932f57c48_>(
                          v13,
                          (__int64)v18);
                  v11 = *v10;
                  v18[0] = *v10;
                  *v10 = 0;
                  if ( *(_QWORD *)v13 )
                  {
                    *(_QWORD *)v13 = 0;
                    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release();
                  }
                  v2 = v9(v8, v11);
                  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(v18);
                  if ( v2 >= 0 )
                  {
                    Microsoft::WRL::ComPtr<IPopupWindow>::operator=((char *)this + 16, &v14);
                    v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 272LL))(*((_QWORD *)this + 2));
                  }
                }
              }
            }
            Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v14);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
          if ( v2 < 0 )
LABEL_25:
            DirectUI::Element::Destroy(v16, 0);
        }
      }
      DirectUI::DUIXmlParser::Destroy(v17);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800cc620  mov     [rsp-8+arg_8], rbx
0x1800cc625  mov     [rsp-8+arg_10], rsi
0x1800cc62a  push    rbp
0x1800cc62b  push    rdi
0x1800cc62c  push    r14
0x1800cc62e  lea     rbp, [rsp-47h]
0x1800cc633  sub     rsp, 100h
0x1800cc63a  mov     rax, cs:__security_cookie
0x1800cc641  xor     rax, rsp
0x1800cc644  mov     [rbp+57h+var_20], rax
0x1800cc648  mov     rsi, rcx
0x1800cc64b  cmp     dword ptr [rcx+18h], 9801h
0x1800cc652  jnz     short loc_1800CC663
0x1800cc654  call    ?Register@?$ClassInfo@VUserTile@@VElement@DirectUI@@V?$StandardCreator@VUserTile@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<UserTile,DirectUI::Element,DirectUI::StandardCreator<UserTile>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x1800cc659  mov     ebx, eax
0x1800cc65b  test    eax, eax
0x1800cc65d  js      loc_1800CC939
0x1800cc663  mov     [rbp+57h+var_C0], 0
0x1800cc66b  mov     [rsp+110h+ppv], 0
0x1800cc674  xor     r9d, r9d
0x1800cc677  xor     r8d, r8d
0x1800cc67a  xor     edx, edx
0x1800cc67c  lea     rcx, [rbp+57h+var_C0]
0x1800cc680  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x1800cc686  mov     ebx, eax
0x1800cc688  test    eax, eax
0x1800cc68a  js      loc_1800CC939
0x1800cc690  lea     r9, __ImageBase
0x1800cc697  lea     r8, __ImageBase
0x1800cc69e  mov     edx, [rsi+18h]
0x1800cc6a1  mov     rcx, [rbp+57h+var_C0]
0x1800cc6a5  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x1800cc6ab  mov     ebx, eax
0x1800cc6ad  test    eax, eax
0x1800cc6af  js      loc_1800CC92F
0x1800cc6b5  mov     [rbp+57h+var_C8], 0
0x1800cc6bd  lea     rax, [rbp+57h+var_C8]
0x1800cc6c1  mov     [rsp+110h+var_E8], rax
0x1800cc6c6  mov     [rsp+110h+ppv], 0
0x1800cc6cf  xor     r9d, r9d
0x1800cc6d2  xor     r8d, r8d
0x1800cc6d5  lea     rdx, aMain; "main"
0x1800cc6dc  mov     rcx, [rbp+57h+var_C0]
0x1800cc6e0  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x1800cc6e6  mov     ebx, eax
0x1800cc6e8  test    eax, eax
0x1800cc6ea  js      loc_1800CC92F
0x1800cc6f0  mov     rdx, [rbp+57h+var_C8]; struct DirectUI::Element *
0x1800cc6f4  mov     rcx, rsi; this
0x1800cc6f7  call    ?_SetDialogDUI@CUserInfoDialog@@AEAAJPEAVElement@DirectUI@@@Z; CUserInfoDialog::_SetDialogDUI(DirectUI::Element *)
0x1800cc6fc  mov     ebx, eax
0x1800cc6fe  test    eax, eax
0x1800cc700  js      loc_1800CC923
0x1800cc706  mov     [rbp+57h+var_D0], 0
0x1800cc70e  lea     rcx, [rbp+57h+var_D0]
0x1800cc712  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cc717  lea     rax, [rbp+57h+var_D0]
0x1800cc71b  mov     [rsp+110h+ppv], rax; ppv
0x1800cc720  lea     r9, _GUID_6a0017fe_df25_46eb_8a96_38df889cb5b1; riid
0x1800cc727  mov     r14d, 1
0x1800cc72d  mov     r8d, r14d; dwClsContext
0x1800cc730  xor     edx, edx; pUnkOuter
0x1800cc732  lea     rcx, CLSID_PopupWindowFactory; rclsid
0x1800cc739  call    cs:__imp_CoCreateInstance
0x1800cc73f  mov     ebx, eax
0x1800cc741  test    eax, eax
0x1800cc743  js      loc_1800CC916
0x1800cc749  mov     rcx, [rsi+38h]
0x1800cc74d  mov     [rsp+110h+var_E0], 0
0x1800cc755  mov     ebx, r14d
0x1800cc758  test    rcx, rcx
0x1800cc75b  jz      short loc_1800CC776
0x1800cc75d  lea     rdx, [rsp+110h+var_E0]
0x1800cc762  call    cs:__imp_GetWindowBand
0x1800cc768  test    eax, eax
0x1800cc76a  jz      short loc_1800CC776
0x1800cc76c  xor     ebx, ebx
0x1800cc76e  cmp     [rsp+110h+var_E0], r14d
0x1800cc773  setz    bl
0x1800cc776  mov     rcx, [rbp+57h+var_D0]
0x1800cc77a  mov     rax, [rcx]
0x1800cc77d  lea     edx, ds:1[rbx*8]
0x1800cc784  mov     rax, [rax+18h]
0x1800cc788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc78d  mov     [rsp+110h+var_D8], 0
0x1800cc796  mov     rdi, [rbp+57h+var_D0]
0x1800cc79a  mov     rax, [rdi]
0x1800cc79d  mov     rbx, [rax+48h]
0x1800cc7a1  lea     rcx, [rsp+110h+var_D8]
0x1800cc7a6  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800cc7ab  lea     r8, [rsp+110h+var_D8]
0x1800cc7b0  mov     rdx, [rsi+38h]
0x1800cc7b4  mov     rcx, rdi
0x1800cc7b7  mov     rax, rbx
0x1800cc7ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc7bf  mov     ebx, eax
0x1800cc7c1  test    eax, eax
0x1800cc7c3  js      loc_1800CC90B
0x1800cc7c9  mov     r9d, 40h ; '@'; cchBufferMax
0x1800cc7cf  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1800cc7d3  mov     edx, [rsi+1Ch]; uID
0x1800cc7d6  lea     rcx, __ImageBase; hInstance
0x1800cc7dd  call    cs:__imp_LoadStringW
0x1800cc7e3  test    eax, eax
0x1800cc7e5  jle     short loc_1800CC7FC
0x1800cc7e7  mov     rcx, [rsp+110h+var_D8]
0x1800cc7ec  mov     rax, [rcx]
0x1800cc7ef  lea     rdx, [rbp+57h+Buffer]
0x1800cc7f3  mov     rax, [rax+20h]
0x1800cc7f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc7fc  mov     rcx, [rsp+110h+var_D8]
0x1800cc801  mov     rax, [rcx]
0x1800cc804  mov     rdx, [rbp+57h+var_C8]
0x1800cc808  mov     rax, [rax+160h]
0x1800cc80f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc814  mov     ebx, eax
0x1800cc816  test    eax, eax
0x1800cc818  js      loc_1800CC90B
0x1800cc81e  mov     rdx, [rsp+110h+var_D8]; struct IPopupWindow *
0x1800cc823  mov     rcx, rsi; this
0x1800cc826  cmp     dword ptr [rsi+18h], 9801h
0x1800cc82d  jnz     short loc_1800CC84C
0x1800cc82f  mov     [rsp+110h+var_E0], 95B2h
0x1800cc837  mov     [rsp+110h+var_E0+4], 95B1h
0x1800cc83f  mov     r9d, 2
0x1800cc845  lea     r8, [rsp+110h+var_E0]
0x1800cc84a  jmp     short loc_1800CC85C
0x1800cc84c  mov     [rsp+110h+var_E0], 95C1h
0x1800cc854  mov     r9d, r14d; unsigned int
0x1800cc857  lea     r8, [rsp+110h+var_E0]; unsigned int *
0x1800cc85c  call    ?_SetCommands@CUserInfoDialog@@AEAAJPEAUIPopupWindow@@PEAII@Z; CUserInfoDialog::_SetCommands(IPopupWindow *,uint *,uint)
0x1800cc861  mov     ebx, eax
0x1800cc863  test    eax, eax
0x1800cc865  js      loc_1800CC90B
0x1800cc86b  mov     rbx, [rsp+110h+var_D8]
0x1800cc870  mov     rax, [rbx]
0x1800cc873  mov     r14, [rax+0A8h]
0x1800cc87a  mov     [rbp+57h+var_B8], rsi
0x1800cc87e  lea     rax, ?CancelDialog@CUserInfoDialog@@UEAAJXZ; CUserInfoDialog::CancelDialog(void)
0x1800cc885  mov     [rbp+57h+var_B0], rax
0x1800cc889  mov     [rbp+57h+var_A8], 0
0x1800cc890  mov     eax, dword ptr [rbp+57h+var_B0+4]
0x1800cc893  mov     [rbp+57h+var_A4], eax
0x1800cc896  lea     rdx, [rbp+57h+var_B8]
0x1800cc89a  lea     rcx, [rsp+110h+var_E0]
0x1800cc89f  call    ??$Make@U?$DelegateInvokeHelper@UIPopupEventHandler@@V_lambda_74447f3d681dc015fa527b5932f57c48_@@$0?0PEAUIPopupWindow@@@?$DelegateArgTraits@P8IPopupEventHandler@@EAAJPEAUIPopupWindow@@@Z@Details@WRL@Microsoft@@V_lambda_74447f3d681dc015fa527b5932f57c48_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@U?$DelegateInvokeHelper@UIPopupEventHandler@@V_lambda_74447f3d681dc015fa527b5932f57c48_@@$0?0PEAUIPopupWindow@@@?$DelegateArgTraits@P8IPopupEventHandler@@EAAJPEAUIPopupWindow@@@Z@Details@WRL@Microsoft@@@12@$$QEAV_lambda_74447f3d681dc015fa527b5932f57c48_@@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (IPopupEventHandler::*)(IPopupWindow *)>::DelegateInvokeHelper<IPopupEventHandler,_lambda_74447f3d681dc015fa527b5932f57c48_,-1,IPopupWindow *>,_lambda_74447f3d681dc015fa527b5932f57c48_>(_lambda_74447f3d681dc015fa527b5932f57c48_ &&)
0x1800cc8a4  mov     rdi, [rax]
0x1800cc8a7  mov     [rbp+57h+var_B8], rdi
0x1800cc8ab  mov     qword ptr [rax], 0
0x1800cc8b2  mov     rcx, qword ptr [rsp+110h+var_E0]
0x1800cc8b7  test    rcx, rcx
0x1800cc8ba  jz      short loc_1800CC8CB
0x1800cc8bc  mov     qword ptr [rsp+110h+var_E0], 0
0x1800cc8c5  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDialogFirstFrameRenderedHandler@Dialogs@UI@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::UI::Dialogs::IDialogFirstFrameRenderedHandler>::Release(void)
0x1800cc8ca  nop
0x1800cc8cb  mov     rdx, rdi
0x1800cc8ce  mov     rcx, rbx
0x1800cc8d1  mov     rax, r14
0x1800cc8d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc8d9  mov     ebx, eax
0x1800cc8db  lea     rcx, [rbp+57h+var_B8]
0x1800cc8df  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800cc8e4  test    ebx, ebx
0x1800cc8e6  js      short loc_1800CC90B
0x1800cc8e8  lea     rdx, [rsp+110h+var_D8]
0x1800cc8ed  lea     rcx, [rsi+10h]
0x1800cc8f1  call    ??4?$ComPtr@UIPopupWindow@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IPopupWindow>::operator=(Microsoft::WRL::ComPtr<IPopupWindow> const &)
0x1800cc8f6  mov     rcx, [rsi+10h]
0x1800cc8fa  mov     rax, [rcx]
0x1800cc8fd  mov     rax, [rax+110h]
0x1800cc904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc909  mov     ebx, eax
0x1800cc90b  lea     rcx, [rsp+110h+var_D8]
0x1800cc910  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800cc915  nop
0x1800cc916  lea     rcx, [rbp+57h+var_D0]
0x1800cc91a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cc91f  test    ebx, ebx
0x1800cc921  jns     short loc_1800CC92F
0x1800cc923  xor     edx, edx
0x1800cc925  mov     rcx, [rbp+57h+var_C8]
0x1800cc929  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x1800cc92f  mov     rcx, [rbp+57h+var_C0]
0x1800cc933  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x1800cc939  mov     eax, ebx
0x1800cc93b  mov     rcx, [rbp+57h+var_20]
0x1800cc93f  xor     rcx, rsp; StackCookie
0x1800cc942  call    __security_check_cookie
0x1800cc947  lea     r11, [rsp+110h+var_10]
0x1800cc94f  mov     rbx, [r11+28h]
0x1800cc953  mov     rsi, [r11+30h]
0x1800cc957  mov     rsp, r11
0x1800cc95a  pop     r14
0x1800cc95c  pop     rdi
0x1800cc95d  pop     rbp
0x1800cc95e  retn
```
