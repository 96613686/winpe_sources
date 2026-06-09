# Windows::Internal::CustomPopupWindowOperation::InitializeBridgeToCoreWindow(Windows::Internal::GitEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::CoreWindowPopupShowingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> *,IPopupWindow *)

- ea: `0x1800498d8`
- end: `0x180049b7e`
- name: `?InitializeBridgeToCoreWindow@CustomPopupWindowOperation@Internal@Windows@@QEAAJPEAV?$GitEventSource@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAVCoreWindowPopupShowingEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@23@PEAUIPopupWindow@@@Z`
- size: `678`
- prototype: `__int64 __fastcall(Windows::Internal::CustomPopupWindowOperation *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800881e8`

## callees

- `0x18003217c`
- `0x1800498d8`
- `0x180050ba0`
- `0x18005659c`
- `0x1800742ac`
- `0x1800801a0`
- `0x180080fac`
- `0x180084894`
- `0x180084eac`
- `0x180085ae0`
- `0x180087cec`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049a8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049a8b`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180049a81`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x180049a81`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004997c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004997c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180049aa8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180049aa8`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x180049adf`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x180049adf`
- `DUI70!?SetHeight@Element@DirectUI@@QEAAJH@Z` at `0x180049aeb`
- `DUI70!?SetHeight@Element@DirectUI@@QEAAJH@Z` at `0x180049aeb`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180049ad0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180049ad0`
- `DUI70!StrToID` at `0x180049ac4`
- `DUI70!StrToID` at `0x180049ac4`
- `DUI70!?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180049ab4`
- `DUI70!?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180049ab4`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x180049a5a`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x180049a5a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::CustomPopupWindowOperation::InitializeBridgeToCoreWindow(
        void **this,
        __int64 a2,
        IUnknown *a3)
{
  __int64 v6; // rax
  int Window; // ebx
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  signed int LastError; // eax
  DirectUI::Element *Root; // rbx
  unsigned __int16 v12; // ax
  DirectUI::Element *Descendent; // rbx
  int v14; // eax
  __int64 v15; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-40h] BYREF
  __int64 v18; // [rsp+38h] [rbp-38h] BYREF
  __int64 *v19; // [rsp+40h] [rbp-30h] BYREF
  HWND v20; // [rsp+48h] [rbp-28h] BYREF
  struct DirectUI::Element *v21; // [rsp+50h] [rbp-20h] BYREF
  __int128 v22; // [rsp+58h] [rbp-18h] BYREF

  v18 = 0;
  v19 = &v18;
  v6 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v19);
  Window = Microsoft::WRL::AsWeak<IPopupCoreWindowCallback>(this, v6);
  if ( Window >= 0 )
  {
    v20 = 0;
    Window = Windows::Internal::CustomPopupWindowOperation::CreateFrameWindow(
               (Windows::Internal::CustomPopupWindowOperation *)this,
               &v20);
    if ( Window >= 0 )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      Window = CoCreateInstance(&CLSID_HostedWindowFactory, 0, 1u, &GUID_9dce39e2_e7d3_46bc_b1b8_1f0d0803da3d, &ppv);
      if ( Window >= 0 )
      {
        v22 = 0;
        Window = (*(__int64 (__fastcall **)(LPVOID, __int64, __int128 *, HWND, GUID *))(*(_QWORD *)ppv + 24LL))(
                   ppv,
                   v18,
                   &v22,
                   v20,
                   &GUID_NULL);
        if ( Window >= 0 )
        {
          v21 = 0;
          Window = Windows::Internal::CustomPopupWindowOperation::SetUpHostDUI(
                     (Windows::Internal::CustomPopupWindowOperation *)this,
                     &v21);
          if ( Window >= 0 )
          {
            v8 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
            v9 = v8;
            if ( v8 )
            {
              *v8 = 0;
              v8[1] = 0;
              v8[3] = 0;
            }
            else
            {
              v9 = 0;
            }
            v19 = v9;
            if ( v9 )
            {
              v9[5] = 0;
              Window = CMarshaledInterface::Marshal(v9, &GUID_cd292360_2763_4085_8a9f_74b224a29175, ppv, 1);
              if ( Window >= 0 )
              {
                v9[4] = a2;
                Window = IUnknown_GetWindow(a3, (HWND *)v9 + 2);
                if ( Window >= 0 )
                {
                  if ( SHCreateThread(
                         Windows::Internal::CustomPopupWindowOperation::s_CoreWindowThreadProc,
                         v9,
                         0x40u,
                         Windows::Internal::CustomPopupWindowOperation::s_CoreWindowInitThreadProc) )
                  {
                    goto LABEL_17;
                  }
                  LastError = GetLastError();
                  Window = LastError;
                  if ( LastError > 0 )
                    Window = (unsigned __int16)LastError | 0x80070000;
                  if ( Window >= 0 )
                  {
LABEL_17:
                    Root = DirectUI::Element::GetRoot(v21);
                    v12 = StrToID(L"ContentArea");
                    Descendent = DirectUI::Element::FindDescendent(Root, v12);
                    DirectUI::Element::SetWidth(Descendent, *((_DWORD *)v9 + 10));
                    DirectUI::Element::SetHeight(Descendent, *((_DWORD *)v9 + 11));
                    v14 = CMarshaledInterface::Unmarshal<Windows::UI::Core::ICoreWindow>(
                            (CMarshaledInterface *)(v9 + 1),
                            this + 19);
                    Window = v14;
                    if ( v14 >= 0 )
                      (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)this[20] + 56LL))(this[20], (unsigned int)v14);
                    v19 = 0;
                  }
                  else
                  {
                    RoOriginateError((unsigned int)Window, 0);
                  }
                }
              }
            }
            else
            {
              Window = -2147024882;
            }
            CAutoMemPtr<Windows::Internal::CUSTOM_POPUP_CORE_WINDOW_THREAD_PARA>::~CAutoMemPtr<Windows::Internal::CUSTOM_POPUP_CORE_WINDOW_THREAD_PARA>(&v19);
          }
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    }
  }
  v15 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return (unsigned int)Window;
}

```

## disassembly

```asm
0x1800498d8  mov     [rsp-28h+arg_8], rbx
0x1800498dd  push    rbp
0x1800498de  push    rsi
0x1800498df  push    rdi
0x1800498e0  push    r14
0x1800498e2  push    r15
0x1800498e4  mov     rbp, rsp
0x1800498e7  sub     rsp, 70h
0x1800498eb  mov     rax, cs:__security_cookie
0x1800498f2  xor     rax, rsp
0x1800498f5  mov     [rbp+var_8], rax
0x1800498f9  mov     r15, r8
0x1800498fc  mov     r14, rdx
0x1800498ff  mov     rsi, rcx
0x180049902  mov     [rbp+var_38], 0
0x18004990a  lea     rax, [rbp+var_38]
0x18004990e  mov     [rbp+var_30], rax
0x180049912  lea     rcx, [rbp+var_30]
0x180049916  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18004991b  mov     rdx, rax
0x18004991e  mov     rcx, rsi
0x180049921  call    ??$AsWeak@UIPopupCoreWindowCallback@@@WRL@Microsoft@@YAJPEAUIPopupCoreWindowCallback@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<IPopupCoreWindowCallback>(IPopupCoreWindowCallback *,Microsoft::WRL::WeakRef *)
0x180049926  mov     ebx, eax
0x180049928  test    eax, eax
0x18004992a  js      loc_180049B3F
0x180049930  mov     [rbp+var_28], 0
0x180049938  lea     rdx, [rbp+var_28]; HWND *
0x18004993c  mov     rcx, rsi; this
0x18004993f  call    ?CreateFrameWindow@CustomPopupWindowOperation@Internal@Windows@@QEAAJPEAPEAUHWND__@@@Z; Windows::Internal::CustomPopupWindowOperation::CreateFrameWindow(HWND__ * *)
0x180049944  mov     ebx, eax
0x180049946  test    eax, eax
0x180049948  js      loc_180049B3F
0x18004994e  mov     [rbp+var_40], 0
0x180049956  lea     rcx, [rbp+var_40]
0x18004995a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004995f  lea     rax, [rbp+var_40]
0x180049963  mov     [rsp+70h+ppv], rax; ppv
0x180049968  lea     r9, _GUID_9dce39e2_e7d3_46bc_b1b8_1f0d0803da3d; riid
0x18004996f  xor     edx, edx; pUnkOuter
0x180049971  lea     r8d, [rdx+1]; dwClsContext
0x180049975  lea     rcx, CLSID_HostedWindowFactory; rclsid
0x18004997c  call    cs:__imp_CoCreateInstance
0x180049982  mov     ebx, eax
0x180049984  test    eax, eax
0x180049986  js      loc_180049B35
0x18004998c  xorps   xmm0, xmm0
0x18004998f  movups  [rbp+var_18], xmm0
0x180049993  mov     rcx, [rbp+var_40]
0x180049997  mov     rax, [rcx]
0x18004999a  lea     rdx, GUID_NULL
0x1800499a1  mov     [rsp+70h+ppv], rdx
0x1800499a6  mov     r9, [rbp+var_28]
0x1800499aa  lea     r8, [rbp+var_18]
0x1800499ae  mov     rdx, [rbp+var_38]
0x1800499b2  mov     rax, [rax+18h]
0x1800499b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800499bb  mov     ebx, eax
0x1800499bd  test    eax, eax
0x1800499bf  js      loc_180049B35
0x1800499c5  mov     [rbp+var_20], 0
0x1800499cd  lea     rdx, [rbp+var_20]; struct DirectUI::Element **
0x1800499d1  mov     rcx, rsi; this
0x1800499d4  call    ?SetUpHostDUI@CustomPopupWindowOperation@Internal@Windows@@QEAAJPEAPEAVElement@DirectUI@@@Z; Windows::Internal::CustomPopupWindowOperation::SetUpHostDUI(DirectUI::Element * *)
0x1800499d9  mov     ebx, eax
0x1800499db  test    eax, eax
0x1800499dd  js      loc_180049B35
0x1800499e3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800499ea  mov     ecx, 38h ; '8'; unsigned __int64
0x1800499ef  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800499f4  mov     rdi, rax
0x1800499f7  test    rax, rax
0x1800499fa  jz      short loc_180049A15
0x1800499fc  mov     qword ptr [rax], 0
0x180049a03  mov     qword ptr [rax+8], 0
0x180049a0b  mov     qword ptr [rax+18h], 0
0x180049a13  jmp     short loc_180049A17
0x180049a15  xor     edi, edi
0x180049a17  mov     [rbp+var_30], rdi
0x180049a1b  test    rdi, rdi
0x180049a1e  jz      loc_180049B26
0x180049a24  mov     qword ptr [rdi+28h], 0
0x180049a2c  mov     r9d, 1
0x180049a32  mov     r8, [rbp+var_40]
0x180049a36  lea     rdx, _GUID_cd292360_2763_4085_8a9f_74b224a29175
0x180049a3d  mov     rcx, rdi
0x180049a40  call    ?Marshal@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z; CMarshaledInterface::Marshal(_GUID const &,IUnknown *,MARSHAL_KIND)
0x180049a45  mov     ebx, eax
0x180049a47  test    eax, eax
0x180049a49  js      loc_180049B2B
0x180049a4f  mov     [rdi+20h], r14
0x180049a53  lea     rdx, [rdi+10h]; phwnd
0x180049a57  mov     rcx, r15; punk
0x180049a5a  call    cs:__imp_IUnknown_GetWindow
0x180049a60  mov     ebx, eax
0x180049a62  test    eax, eax
0x180049a64  js      loc_180049B2B
0x180049a6a  lea     r9, ?s_CoreWindowInitThreadProc@CustomPopupWindowOperation@Internal@Windows@@CAKPEAX@Z; pfnCallback
0x180049a71  mov     r8d, 40h ; '@'; flags
0x180049a77  mov     rdx, rdi; pData
0x180049a7a  lea     rcx, ?s_CoreWindowThreadProc@CustomPopupWindowOperation@Internal@Windows@@CAKPEAX@Z; pfnThreadProc
0x180049a81  call    cs:__imp_SHCreateThread
0x180049a87  test    eax, eax
0x180049a89  jnz     short loc_180049AB0
0x180049a8b  call    cs:__imp_GetLastError
0x180049a91  mov     ebx, eax
0x180049a93  test    eax, eax
0x180049a95  jle     short loc_180049AA0
0x180049a97  movzx   ebx, ax
0x180049a9a  or      ebx, 80070000h
0x180049aa0  test    ebx, ebx
0x180049aa2  jns     short loc_180049AB0
0x180049aa4  xor     edx, edx
0x180049aa6  mov     ecx, ebx
0x180049aa8  call    cs:__imp_RoOriginateError
0x180049aae  jmp     short loc_180049B2B
0x180049ab0  mov     rcx, [rbp+var_20]
0x180049ab4  call    cs:__imp_?GetRoot@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetRoot(void)
0x180049aba  mov     rbx, rax
0x180049abd  lea     rcx, aContentarea; "ContentArea"
0x180049ac4  call    cs:__imp_StrToID
0x180049aca  movzx   edx, ax
0x180049acd  mov     rcx, rbx
0x180049ad0  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180049ad6  mov     rbx, rax
0x180049ad9  mov     edx, [rdi+28h]
0x180049adc  mov     rcx, rax
0x180049adf  call    cs:__imp_?SetWidth@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetWidth(int)
0x180049ae5  mov     edx, [rdi+2Ch]
0x180049ae8  mov     rcx, rbx
0x180049aeb  call    cs:__imp_?SetHeight@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetHeight(int)
0x180049af1  lea     rdx, [rsi+98h]; void **
0x180049af8  lea     rcx, [rdi+8]; this
0x180049afc  call    ??$Unmarshal@UICoreWindow@Core@UI@Windows@@@CMarshaledInterface@@QEAAJV?$ComPtrRef@V?$ComPtr@UICoreWindow@Core@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; CMarshaledInterface::Unmarshal<Windows::UI::Core::ICoreWindow>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>>)
0x180049b01  mov     ebx, eax
0x180049b03  test    eax, eax
0x180049b05  js      short loc_180049B1C
0x180049b07  mov     rcx, [rsi+0A0h]
0x180049b0e  mov     rax, [rcx]
0x180049b11  mov     edx, ebx
0x180049b13  mov     rax, [rax+38h]
0x180049b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b1c  mov     [rbp+var_30], 0
0x180049b24  jmp     short loc_180049B2B
0x180049b26  mov     ebx, 8007000Eh
0x180049b2b  lea     rcx, [rbp+var_30]
0x180049b2f  call    ??1?$CAutoMemPtr@UCUSTOM_POPUP_CORE_WINDOW_THREAD_PARA@Internal@Windows@@@@QEAA@XZ; CAutoMemPtr<Windows::Internal::CUSTOM_POPUP_CORE_WINDOW_THREAD_PARA>::~CAutoMemPtr<Windows::Internal::CUSTOM_POPUP_CORE_WINDOW_THREAD_PARA>(void)
0x180049b34  nop
0x180049b35  lea     rcx, [rbp+var_40]
0x180049b39  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049b3e  nop
0x180049b3f  mov     rcx, [rbp+var_38]
0x180049b43  test    rcx, rcx
0x180049b46  jz      short loc_180049B5C
0x180049b48  mov     [rbp+var_38], 0
0x180049b50  mov     rax, [rcx]
0x180049b53  mov     rax, [rax+10h]
0x180049b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b5c  mov     eax, ebx
0x180049b5e  mov     rcx, [rbp+var_8]
0x180049b62  xor     rcx, rsp; StackCookie
0x180049b65  call    __security_check_cookie
0x180049b6a  mov     rbx, [rsp+70h+arg_8]
0x180049b72  add     rsp, 70h
0x180049b76  pop     r15
0x180049b78  pop     r14
0x180049b7a  pop     rdi
0x180049b7b  pop     rsi
0x180049b7c  pop     rbp
0x180049b7d  retn
```
