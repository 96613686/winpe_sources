# Windows::Internal::CPopupWindowImpl::_Initialize(Windows::Internal::PositionTraits *,Windows::Internal::DismissTraits *,Windows::Internal::WindowTraits *,Windows::Internal::AnimationTraits *,HWND__ *,POPUP_PERSONALITY,bool,POPUP_OPTIONS,XamlPopupOptions,HMONITOR__ *)

- ea: `0x180044ff4`
- end: `0x180045add`
- name: `?_Initialize@CPopupWindowImpl@Internal@Windows@@AEAAJPEAUPositionTraits@23@PEAUDismissTraits@23@PEAUWindowTraits@23@PEAUAnimationTraits@23@PEAUHWND__@@W4POPUP_PERSONALITY@@_NW4POPUP_OPTIONS@@W4XamlPopupOptions@@PEAUHMONITOR__@@@Z`
- size: `2793`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18008d1a4`

## callees

- `0x180013244`
- `0x18002a4dc`
- `0x18002fb44`
- `0x180030348`
- `0x180030494`
- `0x180030d98`
- `0x18003217c`
- `0x180037210`
- `0x180037a4c`
- `0x18003aa08`
- `0x18003b9ec`
- `0x180044ff4`
- `0x180045cec`
- `0x180048694`
- `0x180048f0c`
- `0x18004a10c`
- `0x18005b434`
- `0x18008b7f4`
- `0x18008ba54`
- `0x18008bcac`
- `0x18008e2d4`
- `0x18008e8e4`
- `0x18008e928`
- `0x18008ea5c`
- `0x18008f504`
- `0x18009177c`
- `0x18009201c`
- `0x18009aef4`
- `0x1800dbf28`
- `0x1800dc844`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004599f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004599f`
- `USER32!MonitorFromWindow` at `0x1800451af`
- `USER32!MonitorFromWindow` at `0x1800451af`
- `USER32!SetPropW` at `0x1800451e1`
- `USER32!SetPropW` at `0x180045206`
- `USER32!SetPropW` at `0x1800451e1`
- `USER32!SetPropW` at `0x180045206`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180045a1f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180045a1f`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x180045456`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x1800454dd`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x180045520`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x180045567`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x180045593`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x1800455d6`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x180045793`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x180045969`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x180045456`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x1800454dd`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x180045520`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x180045567`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x180045593`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x1800455d6`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x180045793`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x180045969`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18004546f`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800454f0`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180045533`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800457a8`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180045806`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180045811`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180045989`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180045994`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18004546f`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800454f0`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180045533`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800457a8`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180045806`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180045811`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180045989`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180045994`
- `DUI70!?SetPadding@Element@DirectUI@@QEAAJHHHH@Z` at `0x1800454b8`
- `DUI70!?SetPadding@Element@DirectUI@@QEAAJHHHH@Z` at `0x1800454b8`
- `DUI70!?SetForegroundStdColor@Element@DirectUI@@QEAAJH@Z` at `0x18004586b`
- `DUI70!?SetForegroundStdColor@Element@DirectUI@@QEAAJH@Z` at `0x18004586b`
- `DUI70!?SetBackgroundStdColor@Element@DirectUI@@QEAAJH@Z` at `0x180045859`
- `DUI70!?SetBackgroundStdColor@Element@DirectUI@@QEAAJH@Z` at `0x180045859`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800455af`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800455af`
- `DUI70!?SetAccRole@Element@DirectUI@@QEAAJH@Z` at `0x180045379`
- `DUI70!?SetAccRole@Element@DirectUI@@QEAAJH@Z` at `0x180045379`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x1800451a1`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x1800451ce`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x1800451f3`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x18004528b`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x1800458ef`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180045a5a`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x1800451a1`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x1800451ce`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x1800451f3`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x18004528b`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x1800458ef`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180045a5a`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x18004561f`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180045656`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x1800456d3`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x18004561f`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180045656`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x1800456d3`
- `DUI70!?Initialize@NativeHWNDHost@DirectUI@@QEAAJPEBGPEAUHWND__@@PEAUHICON__@@HHHHHHI@Z` at `0x18004513c`
- `DUI70!?Initialize@NativeHWNDHost@DirectUI@@QEAAJPEBGPEAUHWND__@@PEAUHICON__@@HHHHHHI@Z` at `0x18004513c`
- `DUI70!?Host@NativeHWNDHost@DirectUI@@QEAAXPEAVElement@2@@Z` at `0x1800453ad`
- `DUI70!?Host@NativeHWNDHost@DirectUI@@QEAAXPEAVElement@2@@Z` at `0x1800453ad`
- `DUI70!?SetLightDismissIHM@TouchHWNDElement@DirectUI@@QEAAJ_N@Z` at `0x18004539a`
- `DUI70!?SetLightDismissIHM@TouchHWNDElement@DirectUI@@QEAAJ_N@Z` at `0x18004539a`
- `DUI70!RegisterPVLBehaviorFactory` at `0x180045091`
- `DUI70!RegisterPVLBehaviorFactory` at `0x180045091`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x180045644`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x18004567e`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x180045698`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x1800456bf`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x1800456dc`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x18004572e`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x180045644`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x18004567e`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x180045698`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x1800456bf`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x1800456dc`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x18004572e`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800453b9`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18004547a`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800454fb`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18004553e`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800453b9`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18004547a`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800454fb`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18004553e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18004534d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180045446`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800454a0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800454d1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180045514`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180045557`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180045587`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800455c8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18004563b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180045672`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180045720`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180045787`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180045960`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18004534d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180045446`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800454a0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800454d1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180045514`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180045557`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180045587`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800455c8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18004563b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180045672`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180045720`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180045787`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180045960`
- `DUI70!StrToID` at `0x180045341`
- `DUI70!StrToID` at `0x18004543a`
- `DUI70!StrToID` at `0x180045494`
- `DUI70!StrToID` at `0x1800454c5`
- `DUI70!StrToID` at `0x180045508`
- `DUI70!StrToID` at `0x18004554b`
- `DUI70!StrToID` at `0x18004557b`
- `DUI70!StrToID` at `0x1800455bc`
- `DUI70!StrToID` at `0x18004562f`
- `DUI70!StrToID` at `0x180045666`
- `DUI70!StrToID` at `0x180045714`
- `DUI70!StrToID` at `0x18004577b`
- `DUI70!StrToID` at `0x180045954`
- `DUI70!StrToID` at `0x180045341`
- `DUI70!StrToID` at `0x18004543a`
- `DUI70!StrToID` at `0x180045494`
- `DUI70!StrToID` at `0x1800454c5`
- `DUI70!StrToID` at `0x180045508`
- `DUI70!StrToID` at `0x18004554b`
- `DUI70!StrToID` at `0x18004557b`
- `DUI70!StrToID` at `0x1800455bc`
- `DUI70!StrToID` at `0x18004562f`
- `DUI70!StrToID` at `0x180045666`
- `DUI70!StrToID` at `0x180045714`
- `DUI70!StrToID` at `0x18004577b`
- `DUI70!StrToID` at `0x180045954`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x180045316`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x180045362`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x180045316`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x180045362`
- `DUser!SetGadgetFlags` at `0x1800456a9`
- `DUser!SetGadgetFlags` at `0x18004573f`
- `DUser!SetGadgetFlags` at `0x1800456a9`
- `DUser!SetGadgetFlags` at `0x18004573f`
- `DUser!SetHardwareDeviceUsage` at `0x1800451b8`
- `DUser!SetHardwareDeviceUsage` at `0x1800451b8`
- `DUser!AddLayeredRef` at `0x18004564d`
- `DUser!AddLayeredRef` at `0x180045687`
- `DUser!AddLayeredRef` at `0x1800456c8`
- `DUser!AddLayeredRef` at `0x1800456e5`
- `DUser!AddLayeredRef` at `0x18004564d`
- `DUser!AddLayeredRef` at `0x180045687`
- `DUser!AddLayeredRef` at `0x1800456c8`
- `DUser!AddLayeredRef` at `0x1800456e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::CPopupWindowImpl::_Initialize(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        struct DirectUI::Element *a5,
        HWND a6,
        int a7,
        char a8,
        int a9,
        int a10,
        DirectUI::Element *a11)
{
  __int64 v15; // rdx
  int Instance; // edi
  __int64 *v17; // rax
  __int64 v18; // rcx
  struct DirectUI::Element *v19; // rcx
  int v20; // eax
  HWND HWND; // rax
  HMONITOR v22; // rax
  HWND v23; // rax
  HWND v24; // rax
  Windows::Internal::CPopupWindowImpl *v25; // rcx
  int v26; // esi
  bool v27; // di
  HWND v28; // rax
  bool v29; // dl
  unsigned int v30; // r9d
  int v31; // eax
  DirectUI::Element *v32; // rsi
  int v33; // eax
  DirectUI::Element *v34; // rcx
  const unsigned __int16 *v35; // rdx
  unsigned __int16 v36; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::TouchHWNDElement *v38; // rax
  __int64 v39; // r15
  void (__fastcall *v40)(__int64, __int64); // rbx
  __int64 v41; // rdx
  unsigned __int16 v42; // ax
  unsigned __int16 v43; // ax
  DirectUI::Element *v44; // rax
  unsigned __int16 v45; // ax
  DirectUI::Element *v46; // rbx
  unsigned __int16 v47; // ax
  DirectUI::Element *v48; // rbx
  unsigned __int16 v49; // ax
  unsigned __int16 v50; // ax
  DirectUI::Element *v51; // r12
  unsigned __int16 v52; // ax
  DirectUI::Element *v53; // rax
  Windows::Internal *v54; // rcx
  DirectUI::Element *Element; // rbx
  unsigned __int16 v56; // ax
  DirectUI::Element *v57; // rax
  struct HGADGET__ *DisplayNode; // rax
  DirectUI::Element *v59; // rbx
  unsigned __int16 v60; // ax
  DirectUI::Element *v61; // rbx
  struct HGADGET__ *v62; // rax
  unsigned int v63; // edx
  struct HGADGET__ *v64; // rax
  struct HGADGET__ *v65; // rax
  DirectUI::Element *v66; // rax
  struct HGADGET__ *v67; // rax
  unsigned __int16 v68; // ax
  DirectUI::Element *v69; // rcx
  struct HGADGET__ *v70; // rax
  int v71; // eax
  int v72; // eax
  int v73; // eax
  unsigned __int16 v74; // ax
  DirectUI::Element *v75; // rbx
  CShellItemThumbnailElement *v76; // rax
  Windows::Internal::CBackButton *v77; // rax
  _QWORD *v78; // rax
  __int64 *v79; // r15
  struct DirectUI::Element *v80; // rcx
  unsigned __int16 v81; // ax
  DirectUI::Element *v82; // rax
  Windows::Internal *CurrentProcess; // rax
  void *v84; // rdx
  HWND v85; // rdx
  Windows::Internal *v86; // rcx
  struct DirectUI::Element *v87; // rsi
  __int64 (__fastcall *v88)(struct DirectUI::Element *, HWND, __int64, __int64, __int64); // rdi
  __int64 v89; // rbx
  HWND v90; // rax
  bool ShouldUseRestrictedModeKeyboard; // al
  LPVOID *ppv; // [rsp+20h] [rbp-40h]
  DirectUI::Element *v94; // [rsp+90h] [rbp+30h]

  Windows::Internal::CPopupWindowImpl::_EnsureTabletModeSubscription((Windows::Internal::CPopupWindowImpl *)a1);
  *(_QWORD *)(a1 + 80) = a2;
  *(_QWORD *)(a1 + 88) = a3;
  *(_QWORD *)(a1 + 96) = a4;
  *(_QWORD *)(a1 + 104) = a5;
  *(_DWORD *)(a1 + 140) = a9;
  *(_DWORD *)(a1 + 144) = a10;
  *(_BYTE *)(a1 + 136) = a8;
  *(_QWORD *)(a1 + 160) = a11;
  *(_BYTE *)(a1 + 701) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a4 + 144LL))(a4);
  LOBYTE(v15) = *(_BYTE *)(a1 + 705);
  (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 96) + 152LL))(*(_QWORD *)(a1 + 96), v15);
  Instance = RegisterPVLBehaviorFactory();
  if ( Instance < 0 )
    return (unsigned int)Instance;
  v17 = Microsoft::WRL::Details::Make<Windows::Internal::CCustomDefaultDismissEvent,>(&a5);
  v18 = *v17;
  *v17 = 0;
  a11 = *(DirectUI::Element **)(a1 + 432);
  *(_QWORD *)(a1 + 432) = v18;
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&a11);
  v19 = a5;
  if ( a5 )
  {
    a5 = 0;
    (*(void (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v19 + 16LL))(v19);
  }
  if ( !*(_QWORD *)(a1 + 432) )
    return (unsigned int)-2147024882;
  v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a4 + 96LL))(a4);
  Instance = DirectUI::NativeHWNDHost::Initialize(
               (DirectUI::NativeHWNDHost *)a1,
               0,
               a6,
               0,
               0x80000000,
               0x80000000,
               0x80000000,
               0x80000000,
               v20,
               0x80000000,
               0x13u);
  if ( Instance < 0 )
    return (unsigned int)Instance;
  if ( (*(_DWORD *)(a1 + 140) & 0x800) == 0
    && ((*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96)) == 1
     || (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96)) == 3
     || (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96)) == 2) )
  {
    HWND = DirectUI::NativeHWNDHost::GetHWND((DirectUI::NativeHWNDHost *)a1);
    v22 = MonitorFromWindow(HWND, 2u);
    SetHardwareDeviceUsage(v22);
  }
  if ( (*(_DWORD *)(a1 + 140) & 0x2000) != 0 )
  {
    v23 = DirectUI::NativeHWNDHost::GetHWND((DirectUI::NativeHWNDHost *)a1);
    SetPropW(v23, L"IHM_AutoInvokeKeyboard", HANDLE_FLAG_INHERIT);
  }
  if ( !*(_BYTE *)(a1 + 136) )
  {
    v24 = DirectUI::NativeHWNDHost::GetHWND((DirectUI::NativeHWNDHost *)a1);
    SetPropW(v24, L"UIA_WindowPatternEnabled", HANDLE_FLAG_INHERIT);
  }
  if ( a7 == 1 )
  {
    a8 = 1;
  }
  else
  {
    a8 = 0;
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96)) == 1 )
    {
      *(_DWORD *)(a1 + 344) |= 8u;
      if ( (int)Windows::Internal::CPopupWindowImpl::_GetImmersiveApplicationBackgroundColor(
                  v25,
                  a6,
                  (unsigned int *)(a1 + 568)) < 0 )
      {
        *(_DWORD *)(a1 + 568) = 0xFFFFFF;
        *(_DWORD *)(a1 + 344) &= ~8u;
      }
    }
  }
  v26 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 112LL))(*(_QWORD *)(a1 + 96));
  a5 = 0;
  v27 = (*(_DWORD *)(a1 + 140) & 0x100000) != 0;
  v28 = DirectUI::NativeHWNDHost::GetHWND((DirectUI::NativeHWNDHost *)a1);
  Instance = Windows::Internal::FlyoutElement::Create(
               v28,
               v29,
               v26,
               v30,
               (struct DirectUI::Element *)ppv,
               v27,
               (unsigned int *)(a1 + 172),
               &a5);
  if ( Instance < 0 )
    return (unsigned int)Instance;
  v31 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96));
  v32 = a5;
  if ( v31 == 2 )
  {
    if ( a6 && (unsigned __int8)Windows::Internal::_anonymous_namespace_::IsHostingContainerInCharmWindow(a6) )
    {
      v33 = IsHighContrast();
      v34 = v32;
      if ( v33 )
        v35 = L"HighContrastHostingContainerInCharmWindow";
      else
        v35 = L"HostingContainerInCharmWindow";
      goto LABEL_29;
    }
    if ( (unsigned int)IsHighContrast() )
    {
      v35 = L"HighContrastHostingContainer";
      v34 = v32;
LABEL_29:
      DirectUI::Element::SetClass(v34, v35);
    }
  }
  if ( (unsigned int)IsHighContrast() )
  {
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96)) == 1 )
    {
      v36 = StrToID(L"PopupContent");
      Descendent = DirectUI::Element::FindDescendent(v32, v36);
      if ( Descendent )
        DirectUI::Element::SetClass(Descendent, L"HighContrast");
    }
  }
  if ( *(_BYTE *)(a1 + 136) )
    DirectUI::Element::SetAccRole(v32, 11);
  if ( (*(_DWORD *)(a1 + 140) & 0x1000) != 0 )
  {
    v38 = (DirectUI::TouchHWNDElement *)element_cast<DirectUI::TouchHWNDElement>(v32);
    DirectUI::TouchHWNDElement::SetLightDismissIHM(v38, 1);
  }
  ++*(_DWORD *)(a1 + 176);
  DirectUI::NativeHWNDHost::Host((DirectUI::NativeHWNDHost *)a1, v32);
  DirectUI::Element::SetVisible(v32, 1);
  Instance = -2147467259;
  if ( !*(_DWORD *)(a1 + 480) )
  {
    CSafeElementListenerPtr<UIBridgeWindow>::ReleaseListener(a1 + 456);
    *(_QWORD *)(a1 + 472) = (a1 + 48) & -(__int64)(a1 != 0);
    Instance = CSafeElementPtrBase<DirectUI::Element>::_Assign(a1 + 456, v32);
    if ( Instance < 0 )
    {
      *(_QWORD *)(a1 + 472) = 0;
      return (unsigned int)Instance;
    }
  }
  if ( Instance < 0 )
    return (unsigned int)Instance;
  v39 = a1 + 56;
  v40 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(a1 + 56) + 328LL);
  LOBYTE(v41) = (unsigned int)Windows::Internal::_anonymous_namespace_::GetPopupWindowLayoutDirection() == 1;
  v40(a1 + 56, v41);
  v42 = StrToID(L"UpButton");
  v94 = DirectUI::Element::FindDescendent(v32, v42);
  *(_DWORD *)(a1 + 396) = DirectUI::Element::GetLayoutPos(v94);
  DirectUI::Element::SetLayoutPos(v94, -3);
  DirectUI::Element::SetVisible(v94, 0);
  if ( (*(_DWORD *)(a1 + 140) & 0x8000000) != 0 )
  {
    v43 = StrToID(L"PopupContent");
    v44 = DirectUI::Element::FindDescendent(v32, v43);
    DirectUI::Element::SetPadding(v44, 24, 0, 24, 24);
  }
  v45 = StrToID(L"ButtonBar");
  v46 = DirectUI::Element::FindDescendent(v32, v45);
  *(_DWORD *)(a1 + 408) = DirectUI::Element::GetLayoutPos(v46);
  DirectUI::Element::SetLayoutPos(v46, -3);
  DirectUI::Element::SetVisible(v46, 0);
  v47 = StrToID(L"Title");
  v48 = DirectUI::Element::FindDescendent(v32, v47);
  *(_DWORD *)(a1 + 400) = DirectUI::Element::GetLayoutPos(v48);
  DirectUI::Element::SetLayoutPos(v48, -3);
  DirectUI::Element::SetVisible(v48, 0);
  v49 = StrToID(L"TitleBar");
  a11 = DirectUI::Element::FindDescendent(v32, v49);
  *(_DWORD *)(a1 + 404) = DirectUI::Element::GetLayoutPos(a11);
  v50 = StrToID(L"ContentArea");
  v51 = DirectUI::Element::FindDescendent(v32, v50);
  *(_DWORD *)(a1 + 412) = DirectUI::Element::GetLayoutPos(v51);
  if ( *(_BYTE *)(a1 + 136) )
    DirectUI::Element::SetAccessible(v51, 0);
  v52 = StrToID(L"Progress");
  v53 = DirectUI::Element::FindDescendent(v32, v52);
  if ( v53 )
  {
    *(_DWORD *)(a1 + 416) = DirectUI::Element::GetLayoutPos(v53);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v39 + 344LL))(a1 + 56, 0);
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96)) == 3 )
  {
    *(_BYTE *)(a1 + 700) = Windows::Internal::ImmersiveShellExists(v54);
    Element = DirectUI::NativeHWNDHost::GetElement((DirectUI::NativeHWNDHost *)a1);
    v56 = StrToID(L"TitleBarBackground");
    v57 = DirectUI::Element::FindDescendent(Element, v56);
    DisplayNode = DirectUI::Element::GetDisplayNode(v57);
    AddLayeredRef(DisplayNode);
    v59 = DirectUI::NativeHWNDHost::GetElement((DirectUI::NativeHWNDHost *)a1);
    v60 = StrToID(L"CharmWindowBorder");
    v61 = DirectUI::Element::FindDescendent(v59, v60);
    v62 = DirectUI::Element::GetDisplayNode(v61);
    AddLayeredRef(v62);
    DUI_SetGadgetZOrder(v61, v63);
    v64 = DirectUI::Element::GetDisplayNode(v61);
    SetGadgetFlags(v64, 8224, 8224);
    if ( (*(_DWORD *)(a1 + 140) & 0x500) == 0 )
    {
      v65 = DirectUI::Element::GetDisplayNode(v51);
      AddLayeredRef(v65);
      goto LABEL_57;
    }
  }
  else
  {
    v66 = DirectUI::NativeHWNDHost::GetElement((DirectUI::NativeHWNDHost *)a1);
    v67 = DirectUI::Element::GetDisplayNode(v66);
    AddLayeredRef(v67);
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96)) == 1
    && (*(_DWORD *)(a1 + 140) & 0x20000) != 0 )
  {
    v68 = StrToID(L"ContentAreaTSV");
    v69 = DirectUI::Element::FindDescendent(v32, v68);
  }
  else
  {
    v69 = v51;
  }
  v70 = DirectUI::Element::GetDisplayNode(v69);
  SetGadgetFlags(v70, 1025, 1025);
LABEL_57:
  v71 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96));
  if ( v71 )
  {
    v72 = v71 - 1;
    if ( !v72 )
    {
      DirectUI::Element::SetLayoutPos(a11, -3);
      DirectUI::Element::SetLayoutPos(v51, -3);
      goto LABEL_66;
    }
    v73 = v72 - 1;
    if ( !v73 )
    {
      v81 = StrToID(L"AppIcon");
      v82 = DirectUI::Element::FindDescendent(v32, v81);
      *(_DWORD *)(a1 + 392) = DirectUI::Element::GetLayoutPos(v82);
      goto LABEL_66;
    }
    if ( v73 != 1 )
      goto LABEL_66;
  }
  v74 = StrToID(L"AppIconContainer");
  v75 = DirectUI::Element::FindDescendent(v32, v74);
  *(_DWORD *)(a1 + 392) = DirectUI::Element::GetLayoutPos(v75);
  DirectUI::Element::SetLayoutPos(v75, -3);
  a5 = 0;
  Instance = shell::TaskScheduler::CreateInstance(&stru_180104448, &a5);
  if ( Instance >= 0 )
  {
    v76 = (CShellItemThumbnailElement *)FindDescendentElement<CShellItemThumbnailElement>(v75);
    Instance = CShellItemThumbnailElement::SetTaskScheduler(v76, *((struct IShellTaskScheduler **)a5 + 2));
  }
  if ( !(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96)) )
  {
    DirectUI::Element::SetLayoutPos(a11, -3);
    DirectUI::Element::SetLayoutPos(v51, -3);
  }
  CAutoMemPtr<shell::TaskScheduler>::~CAutoMemPtr<shell::TaskScheduler>(&a5);
LABEL_66:
  if ( ((*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96)) == 1
     || (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96)) == 2)
    && a8
    && (int)DirectUI::Element::SetBackgroundStdColor(v32, 20042) >= 0 )
  {
    DirectUI::Element::SetForegroundStdColor(v32, 20256);
  }
  Windows::Internal::CPopupWindowImpl::_InitializeDefaultColors((Windows::Internal::CPopupWindowImpl *)a1);
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v39 + 240LL))(a1 + 56, 0);
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v39 + 176LL))(a1 + 56, 0);
    if ( Instance >= 0 )
    {
      v77 = (Windows::Internal::CBackButton *)FindDescendentElement<Windows::Internal::CBackButton>(v94);
      Instance = Windows::Internal::CBackButton::ResetColors(v77);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v39 + 296LL))(a1 + 56, 0);
        if ( Instance >= 0 )
        {
          a11 = (DirectUI::Element *)DirectUI::NativeHWNDHost::GetHWND((DirectUI::NativeHWNDHost *)a1);
          v78 = Microsoft::WRL::Details::Make<Windows::Internal::CTouchKeyboardNotificationCallback,HWND__ *>(
                  &a5,
                  (__int64 *)&a11);
          v79 = (__int64 *)(a1 + 584);
          Microsoft::WRL::ComPtr<CRefCountedObject<Windows::Internal::String>>::operator=(a1 + 584, v78);
          v80 = a5;
          if ( a5 )
          {
            a5 = 0;
            (*(void (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v80 + 16LL))(v80);
          }
          if ( !*v79 )
            return (unsigned int)-2147024882;
          CurrentProcess = (Windows::Internal *)GetCurrentProcess();
          if ( Windows::Internal::IsProcessHighIL(CurrentProcess, v84)
            || !Windows::Internal::IsWindowImmersive((Windows::Internal *)a6, v85)
            || !(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96))
            || (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 88LL))(*(_QWORD *)(a1 + 96)) == 2 )
          {
            Instance = 0;
            ShouldUseRestrictedModeKeyboard = Windows::Internal::ShouldUseRestrictedModeKeyboard(v86);
            CTouchKeyboardNotifications::SubscribeToNotifications(
              a1 + 592,
              (*v79 + 16) & ((unsigned __int128)-(__int128)(unsigned __int64)*v79 >> 64),
              ShouldUseRestrictedModeKeyboard);
            CTouchKeyboardNotifications::RefreshKeyboardState((CTouchKeyboardNotifications *)(a1 + 592));
          }
          else
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 624);
            Instance = CoCreateInstance(
                         &CLSID_FrameworkInputPane,
                         0,
                         1u,
                         &GUID_5752238b_24f0_495a_82f1_2fd593056796,
                         (LPVOID *)(a1 + 624));
            if ( Instance >= 0 )
            {
              a5 = 0;
              Instance = Microsoft::WRL::ComPtr<IFrameworkInputPane>::As<IFrameworkInputPanePriv>(
                           (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))(a1 + 624),
                           (__int64)&a5);
              if ( Instance >= 0 )
              {
                v87 = a5;
                v88 = *(__int64 (__fastcall **)(struct DirectUI::Element *, HWND, __int64, __int64, __int64))(*(_QWORD *)a5 + 32LL);
                v89 = *v79;
                v90 = DirectUI::NativeHWNDHost::GetHWND((DirectUI::NativeHWNDHost *)a1);
                Instance = v88(v87, v90, 1, v89, a1 + 632);
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&a5);
            }
          }
        }
      }
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180044ff4  mov     [rsp-28h+arg_8], rbx
0x180044ff9  mov     [rsp-28h+arg_10], rsi
0x180044ffe  push    rbp
0x180044fff  push    rdi
0x180045000  push    r12
0x180045002  push    r14
0x180045004  push    r15
0x180045006  mov     rbp, rsp
0x180045009  sub     rsp, 60h
0x18004500d  mov     rsi, r9
0x180045010  mov     rdi, r8
0x180045013  mov     rbx, rdx
0x180045016  mov     r14, rcx
0x180045019  call    ?_EnsureTabletModeSubscription@CPopupWindowImpl@Internal@Windows@@AEAAXXZ; Windows::Internal::CPopupWindowImpl::_EnsureTabletModeSubscription(void)
0x18004501e  mov     [r14+50h], rbx
0x180045022  mov     [r14+58h], rdi
0x180045026  mov     [r14+60h], rsi
0x18004502a  mov     rax, [rbp+arg_20]
0x18004502e  mov     [r14+68h], rax
0x180045032  mov     eax, [rbp+arg_40]
0x180045035  mov     [r14+8Ch], eax
0x18004503c  mov     eax, [rbp+arg_48]
0x18004503f  mov     [r14+90h], eax
0x180045046  mov     al, [rbp+arg_38]
0x180045049  mov     [r14+88h], al
0x180045050  mov     rax, [rbp+arg_50]
0x180045057  mov     [r14+0A0h], rax
0x18004505e  mov     rax, [rsi]
0x180045061  mov     rcx, rsi
0x180045064  mov     rax, [rax+90h]
0x18004506b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045070  mov     [r14+2BDh], al
0x180045077  mov     rcx, [r14+60h]
0x18004507b  mov     rax, [rcx]
0x18004507e  mov     dl, [r14+2C1h]
0x180045085  mov     rax, [rax+98h]
0x18004508c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045091  call    cs:__imp_RegisterPVLBehaviorFactory
0x180045097  mov     edi, eax
0x180045099  xor     r12d, r12d
0x18004509c  test    eax, eax
0x18004509e  js      loc_180045AC2
0x1800450a4  lea     rcx, [rbp+arg_20]
0x1800450a8  call    ??$Make@VCCustomDefaultDismissEvent@Internal@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCCustomDefaultDismissEvent@Internal@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::Internal::CCustomDefaultDismissEvent,>(void)
0x1800450ad  mov     rcx, [rax]
0x1800450b0  mov     [rax], r12
0x1800450b3  mov     rax, [r14+1B0h]
0x1800450ba  mov     [rbp+arg_50], rax
0x1800450c1  mov     [r14+1B0h], rcx
0x1800450c8  lea     rcx, [rbp+arg_50]
0x1800450cf  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800450d4  nop
0x1800450d5  mov     rcx, [rbp+arg_20]
0x1800450d9  test    rcx, rcx
0x1800450dc  jz      short loc_1800450EF
0x1800450de  mov     [rbp+arg_20], r12
0x1800450e2  mov     rax, [rcx]
0x1800450e5  mov     rax, [rax+10h]
0x1800450e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800450ee  nop
0x1800450ef  cmp     [r14+1B0h], r12
0x1800450f6  jz      loc_180045943
0x1800450fc  mov     rax, [rsi]
0x1800450ff  mov     rcx, rsi
0x180045102  mov     rax, [rax+60h]
0x180045106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004510b  mov     [rsp+60h+var_10], 13h
0x180045113  mov     ecx, 80000000h
0x180045118  mov     [rsp+60h+var_18], ecx
0x18004511c  mov     [rsp+60h+var_20], eax
0x180045120  mov     dword ptr [rsp+60h+var_28], ecx
0x180045124  mov     dword ptr [rsp+60h+var_30], ecx
0x180045128  mov     dword ptr [rsp+60h+var_38], ecx
0x18004512c  mov     dword ptr [rsp+60h+ppv], ecx; struct DirectUI::Element *
0x180045130  xor     r9d, r9d
0x180045133  mov     r8, [rbp+arg_28]
0x180045137  xor     edx, edx
0x180045139  mov     rcx, r14
0x18004513c  call    cs:__imp_?Initialize@NativeHWNDHost@DirectUI@@QEAAJPEBGPEAUHWND__@@PEAUHICON__@@HHHHHHI@Z; DirectUI::NativeHWNDHost::Initialize(ushort const *,HWND__ *,HICON__ *,int,int,int,int,int,int,uint)
0x180045142  mov     edi, eax
0x180045144  test    eax, eax
0x180045146  js      loc_180045AC2
0x18004514c  mov     r15d, 1
0x180045152  test    dword ptr [r14+8Ch], 800h
0x18004515d  jnz     short loc_1800451BE
0x18004515f  mov     rcx, [r14+60h]
0x180045163  mov     rax, [rcx]
0x180045166  mov     rax, [rax+58h]
0x18004516a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004516f  cmp     eax, r15d
0x180045172  jz      short loc_18004519E
0x180045174  mov     rcx, [r14+60h]
0x180045178  mov     rax, [rcx]
0x18004517b  mov     rax, [rax+58h]
0x18004517f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045184  cmp     eax, 3
0x180045187  jz      short loc_18004519E
0x180045189  mov     rcx, [r14+60h]
0x18004518d  mov     rax, [rcx]
0x180045190  mov     rax, [rax+58h]
0x180045194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045199  cmp     eax, 2
0x18004519c  jnz     short loc_1800451BE
0x18004519e  mov     rcx, r14
0x1800451a1  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x1800451a7  mov     rcx, rax; hwnd
0x1800451aa  mov     edx, 2; dwFlags
0x1800451af  call    cs:__imp_MonitorFromWindow
0x1800451b5  mov     rcx, rax
0x1800451b8  call    cs:__imp_SetHardwareDeviceUsage
0x1800451be  test    dword ptr [r14+8Ch], 2000h
0x1800451c9  jz      short loc_1800451E7
0x1800451cb  mov     rcx, r14
0x1800451ce  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x1800451d4  mov     rcx, rax; hWnd
0x1800451d7  mov     r8, r15; hData
0x1800451da  lea     rdx, aIhmAutoinvokek; "IHM_AutoInvokeKeyboard"
0x1800451e1  call    cs:__imp_SetPropW
0x1800451e7  cmp     [r14+88h], r12b
0x1800451ee  jnz     short loc_18004520C
0x1800451f0  mov     rcx, r14
0x1800451f3  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x1800451f9  mov     rcx, rax; hWnd
0x1800451fc  mov     r8, r15; hData
0x1800451ff  lea     rdx, aUiaWindowpatte; "UIA_WindowPatternEnabled"
0x180045206  call    cs:__imp_SetPropW
0x18004520c  cmp     [rbp+arg_30], r15d
0x180045210  jnz     short loc_180045218
0x180045212  mov     [rbp+arg_38], r15b
0x180045216  jmp     short loc_18004525E
0x180045218  mov     [rbp+arg_38], r12b
0x18004521c  mov     rcx, [r14+60h]
0x180045220  mov     rax, [rcx]
0x180045223  mov     rax, [rax+58h]
0x180045227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004522c  cmp     eax, r15d
0x18004522f  jnz     short loc_18004525E
0x180045231  or      dword ptr [r14+158h], 8
0x180045239  lea     rbx, [r14+238h]
0x180045240  mov     r8, rbx; unsigned int *
0x180045243  mov     rdx, [rbp+arg_28]; HWND
0x180045247  call    ?_GetImmersiveApplicationBackgroundColor@CPopupWindowImpl@Internal@Windows@@AEAAJPEAUHWND__@@PEAK@Z; Windows::Internal::CPopupWindowImpl::_GetImmersiveApplicationBackgroundColor(HWND__ *,ulong *)
0x18004524c  test    eax, eax
0x18004524e  jns     short loc_18004525E
0x180045250  mov     dword ptr [rbx], 0FFFFFFh
0x180045256  and     dword ptr [r14+158h], 0FFFFFFF7h
0x18004525e  mov     rcx, [r14+60h]
0x180045262  mov     rax, [rcx]
0x180045265  mov     rax, [rax+70h]
0x180045269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004526e  mov     esi, eax
0x180045270  mov     [rbp+arg_20], r12
0x180045274  mov     edi, [r14+8Ch]
0x18004527b  shr     edi, 14h
0x18004527e  and     dil, r15b
0x180045281  lea     rbx, [r14+0ACh]
0x180045288  mov     rcx, r14
0x18004528b  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x180045291  mov     rcx, rax; HWND
0x180045294  lea     rax, [rbp+arg_20]
0x180045298  mov     [rsp+60h+var_28], rax; struct DirectUI::Element **
0x18004529d  mov     [rsp+60h+var_30], rbx; unsigned int *
0x1800452a2  mov     [rsp+60h+var_38], dil; bool
0x1800452a7  mov     r8d, esi; int
0x1800452aa  call    ?Create@FlyoutElement@Internal@Windows@@SAJPEAUHWND__@@_NHIPEAVElement@DirectUI@@1PEAKPEAPEAV56@@Z; Windows::Internal::FlyoutElement::Create(HWND__ *,bool,int,uint,DirectUI::Element *,bool,ulong *,DirectUI::Element * *)
0x1800452af  mov     edi, eax
0x1800452b1  test    eax, eax
0x1800452b3  js      loc_180045AC2
0x1800452b9  mov     rcx, [r14+60h]
0x1800452bd  mov     rax, [rcx]
0x1800452c0  mov     rax, [rax+58h]
0x1800452c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800452c9  mov     rsi, [rbp+arg_20]
0x1800452cd  cmp     eax, 2
0x1800452d0  jnz     short loc_18004531C
0x1800452d2  cmp     [rbp+arg_28], r12
0x1800452d6  jz      short loc_180045303
0x1800452d8  mov     rcx, [rbp+arg_28]
0x1800452dc  call    Windows__Internal___anonymous_namespace___IsHostingContainerInCharmWindow
0x1800452e1  test    al, al
0x1800452e3  jz      short loc_180045303
0x1800452e5  call    ?IsHighContrast@@YAHXZ; IsHighContrast(void)
0x1800452ea  mov     rcx, rsi
0x1800452ed  test    eax, eax
0x1800452ef  jz      short loc_1800452FA
0x1800452f1  lea     rdx, aHighcontrastho_0; "HighContrastHostingContainerInCharmWind"...
0x1800452f8  jmp     short loc_180045316
0x1800452fa  lea     rdx, aHostingcontain_1; "HostingContainerInCharmWindow"
0x180045301  jmp     short loc_180045316
0x180045303  call    ?IsHighContrast@@YAHXZ; IsHighContrast(void)
0x180045308  test    eax, eax
0x18004530a  jz      short loc_18004531C
0x18004530c  lea     rdx, aHighcontrastho; "HighContrastHostingContainer"
0x180045313  mov     rcx, rsi
0x180045316  call    cs:__imp_?SetClass@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetClass(ushort const *)
0x18004531c  call    ?IsHighContrast@@YAHXZ; IsHighContrast(void)
0x180045321  test    eax, eax
0x180045323  jz      short loc_180045368
0x180045325  mov     rcx, [r14+60h]
0x180045329  mov     rax, [rcx]
0x18004532c  mov     rax, [rax+58h]
0x180045330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045335  cmp     eax, r15d
0x180045338  jnz     short loc_180045368
0x18004533a  lea     rcx, aPopupcontent; "PopupContent"
0x180045341  call    cs:__imp_StrToID
0x180045347  movzx   edx, ax
0x18004534a  mov     rcx, rsi
0x18004534d  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180045353  test    rax, rax
0x180045356  jz      short loc_180045368
0x180045358  lea     rdx, aHighcontrast; "HighContrast"
0x18004535f  mov     rcx, rax
0x180045362  call    cs:__imp_?SetClass@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetClass(ushort const *)
0x180045368  cmp     [r14+88h], r12b
0x18004536f  jz      short loc_18004537F
0x180045371  mov     edx, 0Bh
0x180045376  mov     rcx, rsi
0x180045379  call    cs:__imp_?SetAccRole@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetAccRole(int)
0x18004537f  test    dword ptr [r14+8Ch], 1000h
0x18004538a  jz      short loc_1800453A0
0x18004538c  mov     rcx, rsi
0x18004538f  call    ??$element_cast@VTouchHWNDElement@DirectUI@@@@YAPEAVTouchHWNDElement@DirectUI@@PEAVElement@1@@Z; element_cast<DirectUI::TouchHWNDElement>(DirectUI::Element *)
0x180045394  mov     dl, r15b
0x180045397  mov     rcx, rax
0x18004539a  call    cs:__imp_?SetLightDismissIHM@TouchHWNDElement@DirectUI@@QEAAJ_N@Z; DirectUI::TouchHWNDElement::SetLightDismissIHM(bool)
0x1800453a0  add     [r14+0B0h], r15d
0x1800453a7  mov     rdx, rsi
0x1800453aa  mov     rcx, r14
0x1800453ad  call    cs:__imp_?Host@NativeHWNDHost@DirectUI@@QEAAXPEAVElement@2@@Z; DirectUI::NativeHWNDHost::Host(DirectUI::Element *)
0x1800453b3  mov     dl, r15b
0x1800453b6  mov     rcx, rsi
0x1800453b9  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x1800453bf  lea     rbx, [r14+1C8h]
0x1800453c6  mov     rax, r14
0x1800453c9  lea     rcx, [r14+30h]
0x1800453cd  neg     rax
0x1800453d0  sbb     r15, r15
0x1800453d3  and     r15, rcx
0x1800453d6  mov     edi, 80004005h
0x1800453db  cmp     [rbx+18h], r12d
0x1800453df  jnz     short loc_180045407
0x1800453e1  mov     rcx, rbx
0x1800453e4  call    ?ReleaseListener@?$CSafeElementListenerPtr@VUIBridgeWindow@@@@QEAAXXZ; CSafeElementListenerPtr<UIBridgeWindow>::ReleaseListener(void)
0x1800453e9  mov     [rbx+10h], r15
0x1800453ed  mov     rdx, rsi
0x1800453f0  mov     rcx, rbx
0x1800453f3  call    ?_Assign@?$CSafeElementPtrBase@VElement@DirectUI@@@@IEAAJPEAVElement@DirectUI@@@Z; CSafeElementPtrBase<DirectUI::Element>::_Assign(DirectUI::Element *)
0x1800453f8  mov     edi, eax
0x1800453fa  test    eax, eax
0x1800453fc  jns     short loc_180045407
0x1800453fe  mov     [rbx+10h], r12
0x180045402  jmp     loc_180045AC2
0x180045407  test    edi, edi
0x180045409  js      loc_180045AC2
0x18004540f  lea     r15, [r14+38h]
0x180045413  mov     rax, [r15]
0x180045416  mov     rbx, [rax+148h]
0x18004541d  call    Windows__Internal___anonymous_namespace___GetPopupWindowLayoutDirection
0x180045422  cmp     eax, 1
0x180045425  setz    dl
0x180045428  mov     rcx, r15
0x18004542b  mov     rax, rbx
0x18004542e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045433  lea     rcx, aUpbutton; "UpButton"
0x18004543a  call    cs:__imp_StrToID
0x180045440  movzx   edx, ax
0x180045443  mov     rcx, rsi
0x180045446  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18004544c  mov     rbx, rax
0x18004544f  mov     [rbp+arg_0], rax
0x180045453  mov     rcx, rax
0x180045456  call    cs:__imp_?GetLayoutPos@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetLayoutPos(void)
0x18004545c  mov     [r14+18Ch], eax
0x180045463  mov     r12d, 0FFFFFFFDh
0x180045469  mov     edx, r12d
0x18004546c  mov     rcx, rbx
0x18004546f  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180045475  xor     edx, edx
0x180045477  mov     rcx, rbx
0x18004547a  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x180045480  test    dword ptr [r14+8Ch], 8000000h
0x18004548b  jz      short loc_1800454BE
0x18004548d  lea     rcx, aPopupcontent; "PopupContent"
0x180045494  call    cs:__imp_StrToID
0x18004549a  movzx   edx, ax
0x18004549d  mov     rcx, rsi
0x1800454a0  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800454a6  lea     edx, [r12+1Bh]
0x1800454ab  mov     dword ptr [rsp+60h+ppv], edx
0x1800454af  mov     r9d, edx
0x1800454b2  xor     r8d, r8d
0x1800454b5  mov     rcx, rax
0x1800454b8  call    cs:__imp_?SetPadding@Element@DirectUI@@QEAAJHHHH@Z; DirectUI::Element::SetPadding(int,int,int,int)
0x1800454be  lea     rcx, aButtonbar; "ButtonBar"
0x1800454c5  call    cs:__imp_StrToID
0x1800454cb  movzx   edx, ax
0x1800454ce  mov     rcx, rsi
0x1800454d1  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800454d7  mov     rbx, rax
  ... truncated ...
```
