# FlowUIBase::InitializeUI(HWND__ *,long,IPopupWindow *,IDataTransferBroker *,IUnknown *)

- ea: `0x18030a6f0`
- end: `0x18030ab17`
- name: `?InitializeUI@FlowUIBase@@UEAAJPEAUHWND__@@JPEAUIPopupWindow@@PEAUIDataTransferBroker@@PEAUIUnknown@@@Z`
- size: `1063`
- prototype: `__int64 __usercall@<rax>(FlowUIBase *__hidden this@<rcx>, HWND hWnd@<rdx>, int@<r8d>, struct IPopupWindow *@<r9>, struct IDataTransferBroker *, struct IUnknown *)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1803a59d0`
- `0x1803a9630`

## callees

- `0x180009dd0`
- `0x18000edd4`
- `0x18008ef10`
- `0x180090bc8`
- `0x1800a0f20`
- `0x1800ed2c0`
- `0x180142e10`
- `0x180159110`
- `0x1802fea1c`
- `0x180309294`
- `0x180309320`
- `0x180309394`
- `0x18030a6f0`
- `0x18030cac8`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18030a83a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18030a83a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030aa7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18030aa7f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18030a89e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18030a89e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x18030a763`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x18030a763`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18030a8ef`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18030a91b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18030a8ef`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18030a91b`
- `DUI70!StrToID` at `0x18030a8dd`
- `DUI70!StrToID` at `0x18030a909`
- `DUI70!StrToID` at `0x18030a8dd`
- `DUI70!StrToID` at `0x18030a909`

## pseudocode

```c
__int64 __fastcall FlowUIBase::InitializeUI(
        FlowUIBase *this,
        HWND hWnd,
        int a3,
        struct IPopupWindow *a4,
        struct IDataTransferBroker *a5,
        struct IUnknown *a6)
{
  _QWORD *v6; // r15
  HWND Ancestor; // rax
  int (__fastcall *v12)(struct IPopupWindow *, GUID *, __int64 *); // rbx
  HANDLE EventW; // rdi
  __int64 v14; // rcx
  __int64 v15; // r8
  HRESULT Instance; // edi
  unsigned __int16 v17; // ax
  unsigned __int16 v18; // ax
  struct DirectUI::Element *Descendent; // rax
  _lambda_aec159daf75c9a566e43618f77172940_ *v20; // rax
  double v21; // xmm0_8
  struct IUnknownVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  __int64 v24; // r14
  __int64 (__fastcall *v25)(__int64, char *, char *); // rdi
  int v26; // eax
  struct IPopupWindow *v28; // [rsp+30h] [rbp-50h] BYREF
  __int64 v29; // [rsp+38h] [rbp-48h] BYREF
  __int64 v30; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v31[2]; // [rsp+48h] [rbp-38h] BYREF
  int v32; // [rsp+58h] [rbp-28h] BYREF
  __int64 v33; // [rsp+60h] [rbp-20h] BYREF
  __int128 v34; // [rsp+68h] [rbp-18h] BYREF

  v6 = (_QWORD *)((char *)this + 216);
  Microsoft::WRL::ComPtr<Windows::UI::Xaml::Interop::IBindableObservableVector>::operator=((char *)this + 216, a5);
  if ( *v6 )
    (*(void (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v6 + 160LL))(*v6, (char *)this + 392);
  *((_QWORD *)this + 30) = hWnd;
  Ancestor = GetAncestor(hWnd, 2u);
  *((_QWORD *)this + 31) = Ancestor;
  if ( !Ancestor )
    *((_QWORD *)this + 31) = *((_QWORD *)this + 30);
  *((_DWORD *)this + 64) = a3;
  v28 = a4;
  Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&v28);
  v28 = (struct IPopupWindow *)*((_QWORD *)this + 29);
  *((_QWORD *)this + 29) = a4;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v28);
  v33 = 0;
  *((_OWORD *)this + 17) = 0;
  *((_QWORD *)this + 36) = 0;
  v30 = 0;
  v12 = **(int (__fastcall ***)(struct IPopupWindow *, GUID *, __int64 *))a4;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v30);
  if ( v12(a4, &GUID_00000114_0000_0000_c000_000000000046, &v30) >= 0
    && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 24LL))(v30, &v33) >= 0 )
  {
    v31[0] = v33;
    CCrashDetector::StartMonitoringThreadOfWindow__lambda_551f9ca1d164ebc7a8842e8be5fd9117___((char *)this + 408, hWnd);
  }
  EventW = CreateEventW(0, 1, 0, 0);
  CAutoHandle<void *>::~CAutoHandle<void *>((char *)this + 336);
  *((_QWORD *)this + 42) = EventW;
  v31[0] = hWnd;
  v31[1] = EventW;
  Windows::Internal::ComTaskPool::QueueTask__lambda_cda27e61a93913f810783a155b1f9306___(v14, 3, v15, v31);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease((char *)this + 320);
  Instance = CoCreateInstance(
               &CLSID_ShellTaskScheduler,
               0,
               1u,
               &GUID_6ccb7be0_6807_11d0_b810_00c04fd706ec,
               (LPVOID *)this + 40);
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 40) + 48LL))(
                 *((_QWORD *)this + 40),
                 1,
                 4294967294LL);
    if ( Instance >= 0 )
    {
      v17 = StrToID(L"eProgressLauncher");
      *((_QWORD *)this + 47) = DirectUI::Element::FindDescendent(this, v17);
      v18 = StrToID(L"eProgressLauncherBlank");
      Descendent = DirectUI::Element::FindDescendent(this, v18);
      v28 = 0;
      *((_QWORD *)this + 48) = Descendent;
      v31[0] = 0;
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v28);
      if ( (int)BehaviorEngineHelper::EnsureObject((BehaviorEngineHelper *)v31) >= 0
        && (*(int (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, _QWORD, struct IPopupWindow **))(*(_QWORD *)v31[0] + 40LL))(
             v31[0],
             L"PVL",
             L"AnimationTrap",
             0,
             &v28) >= 0 )
      {
        (*(void (__fastcall **)(FlowUIBase *, struct IPopupWindow *))(*(_QWORD *)this + 176LL))(this, v28);
      }
      v20 = _lambda_aec159daf75c9a566e43618f77172940_::_lambda_aec159daf75c9a566e43618f77172940_(
              (_lambda_aec159daf75c9a566e43618f77172940_ *)&v32,
              this);
      if ( (int)DirectUI::SimpleTimer::SetHandler__lambda_c7441d9f82d1d6c562ddd4763737fe37___((char *)this + 344, v20) >= 0 )
      {
        v21 = (*(double (__fastcall **)(FlowUIBase *))(*(_QWORD *)this + 408LL))(this);
        *((_DWORD *)this + 90) = LODWORD(v21);
        DirectUI::SimpleTimer::DelayedStart((FlowUIBase *)((char *)this + 344), *(float *)&v21);
      }
      lpVtbl = a6->lpVtbl;
      v29 = 0;
      QueryInterface = lpVtbl->QueryInterface;
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v29);
      if ( ((int (__fastcall *)(struct IUnknown *, GUID *, __int64 *))QueryInterface)(
             a6,
             &GUID_b9b939fe_429a_45a0_8934_247a0c66348f,
             &v29) >= 0 )
      {
        v32 = 0;
        v34 = 0;
        Instance = (*(__int64 (__fastcall **)(__int64, int *, __int128 *))(*(_QWORD *)v29 + 32LL))(v29, &v32, &v34);
        if ( Instance >= 0 )
        {
          if ( v32 == 1 )
          {
            (*(void (__fastcall **)(FlowUIBase *, __int64, __int128 *))(*(_QWORD *)this + 384LL))(this, 1, &v34);
          }
          else
          {
            v24 = *v6;
            if ( !*v6
              || (v25 = *(__int64 (__fastcall **)(__int64, char *, char *))(*(_QWORD *)v24 + 24LL),
                  CoTaskMemFree(*((LPVOID *)this + 33)),
                  Instance = v25(v24, (char *)this + 328, (char *)this + 264),
                  Instance >= 0) )
            {
              v26 = (*(__int64 (__fastcall **)(FlowUIBase *, struct IUnknown *))(*(_QWORD *)this + 400LL))(this, a6);
              Instance = v26;
              if ( *((_DWORD *)this + 74) && v26 >= 0 )
                FlowUIBase::_InitializeRunningShares(this);
            }
          }
        }
      }
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v29);
      DirectUI::DuiPVLTrigger::~DuiPVLTrigger((DirectUI::DuiPVLTrigger *)v31);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v28);
    }
  }
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v30);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18030a6f0  push    rbp
0x18030a6f2  push    rbx
0x18030a6f3  push    rsi
0x18030a6f4  push    rdi
0x18030a6f5  push    r12
0x18030a6f7  push    r14
0x18030a6f9  push    r15
0x18030a6fb  mov     rbp, rsp
0x18030a6fe  sub     rsp, 80h
0x18030a705  mov     rax, cs:__security_cookie
0x18030a70c  xor     rax, rsp
0x18030a70f  mov     [rbp+var_8], rax
0x18030a713  mov     r12, [rbp+arg_28]
0x18030a717  lea     r15, [rcx+0D8h]
0x18030a71e  mov     r14, rdx
0x18030a721  mov     rsi, rcx
0x18030a724  mov     rdx, [rbp+arg_20]
0x18030a728  mov     rcx, r15
0x18030a72b  mov     rdi, r9
0x18030a72e  mov     ebx, r8d
0x18030a731  call    ??4?$ComPtr@UIBindableObservableVector@Interop@Xaml@UI@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAUIBindableObservableVector@Interop@Xaml@UI@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::UI::Xaml::Interop::IBindableObservableVector>::operator=(Windows::UI::Xaml::Interop::IBindableObservableVector *)
0x18030a736  mov     rcx, [r15]
0x18030a739  test    rcx, rcx
0x18030a73c  jz      short loc_18030A754
0x18030a73e  mov     rax, [rcx]
0x18030a741  lea     rdx, [rsi+188h]
0x18030a748  mov     rax, [rax+0A0h]
0x18030a74f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18030a754  mov     edx, 2; gaFlags
0x18030a759  mov     [rsi+0F0h], r14
0x18030a760  mov     rcx, r14; hwnd
0x18030a763  call    cs:__imp_GetAncestor
0x18030a76a  nop     dword ptr [rax+rax+00h]
0x18030a76f  mov     [rsi+0F8h], rax
0x18030a776  test    rax, rax
0x18030a779  jnz     short loc_18030A789
0x18030a77b  mov     rax, [rsi+0F0h]
0x18030a782  mov     [rsi+0F8h], rax
0x18030a789  lea     rcx, [rbp+var_50]
0x18030a78d  mov     [rsi+100h], ebx
0x18030a793  mov     [rbp+var_50], rdi
0x18030a797  call    ?InternalAddRef@?$ComPtr@UIWindowingEnvironmentConfig@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(void)
0x18030a79c  mov     rax, [rsi+0E8h]
0x18030a7a3  lea     rcx, [rbp+var_50]
0x18030a7a7  mov     [rbp+var_50], rax
0x18030a7ab  mov     [rsi+0E8h], rdi
0x18030a7b2  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18030a7b7  xor     eax, eax
0x18030a7b9  lea     rcx, [rbp+var_40]
0x18030a7bd  xorps   xmm0, xmm0
0x18030a7c0  mov     [rbp+var_20], rax
0x18030a7c4  movups  xmmword ptr [rsi+110h], xmm0
0x18030a7cb  mov     [rsi+120h], rax
0x18030a7d2  mov     [rbp+var_40], rax
0x18030a7d6  mov     rax, [rdi]
0x18030a7d9  mov     rbx, [rax]
0x18030a7dc  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18030a7e1  lea     r8, [rbp+var_40]
0x18030a7e5  mov     rcx, rdi
0x18030a7e8  lea     rdx, _GUID_00000114_0000_0000_c000_000000000046
0x18030a7ef  mov     rax, rbx
0x18030a7f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18030a7f7  test    eax, eax
0x18030a7f9  js      short loc_18030A82E
0x18030a7fb  mov     rcx, [rbp+var_40]
0x18030a7ff  lea     rdx, [rbp+var_20]
0x18030a803  mov     rax, [rcx]
0x18030a806  mov     rax, [rax+18h]
0x18030a80a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18030a80f  test    eax, eax
0x18030a811  js      short loc_18030A82E
0x18030a813  mov     rax, [rbp+var_20]
0x18030a817  lea     rcx, [rsi+198h]; pv
0x18030a81e  lea     r8, [rbp+var_38]
0x18030a822  mov     [rbp+var_38], rax
0x18030a826  mov     rdx, r14; hWnd
0x18030a829  call    CCrashDetector__StartMonitoringThreadOfWindow__lambda_551f9ca1d164ebc7a8842e8be5fd9117___
0x18030a82e  xor     r9d, r9d; lpName
0x18030a831  xor     r8d, r8d; bInitialState
0x18030a834  xor     ecx, ecx; lpEventAttributes
0x18030a836  lea     edx, [r9+1]; bManualReset
0x18030a83a  call    cs:__imp_CreateEventW
0x18030a841  nop     dword ptr [rax+rax+00h]
0x18030a846  lea     rbx, [rsi+150h]
0x18030a84d  mov     rdi, rax
0x18030a850  mov     rcx, rbx
0x18030a853  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x18030a858  lea     r9, [rbp+var_38]
0x18030a85c  mov     [rbx], rdi
0x18030a85f  mov     edx, 3
0x18030a864  mov     [rbp+var_38], r14
0x18030a868  mov     [rbp+var_30], rdi
0x18030a86c  call    Windows__Internal__ComTaskPool__QueueTask__lambda_cda27e61a93913f810783a155b1f9306___
0x18030a871  lea     rbx, [rsi+140h]
0x18030a878  mov     rcx, rbx
0x18030a87b  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18030a880  mov     r14d, 1
0x18030a886  mov     [rsp+80h+ppv], rbx; ppv
0x18030a88b  mov     r8d, r14d; dwClsContext
0x18030a88e  lea     r9, _GUID_6ccb7be0_6807_11d0_b810_00c04fd706ec; riid
0x18030a895  xor     edx, edx; pUnkOuter
0x18030a897  lea     rcx, CLSID_ShellTaskScheduler; rclsid
0x18030a89e  call    cs:__imp_CoCreateInstance
0x18030a8a5  nop     dword ptr [rax+rax+00h]
0x18030a8aa  mov     edi, eax
0x18030a8ac  test    eax, eax
0x18030a8ae  js      loc_18030AAED
0x18030a8b4  mov     rcx, [rbx]
0x18030a8b7  mov     r8d, 0FFFFFFFEh
0x18030a8bd  mov     edx, r14d
0x18030a8c0  mov     rax, [rcx]
0x18030a8c3  mov     rax, [rax+30h]
0x18030a8c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18030a8cc  mov     edi, eax
0x18030a8ce  test    eax, eax
0x18030a8d0  js      loc_18030AAED
0x18030a8d6  lea     rcx, aEprogresslaunc; "eProgressLauncher"
0x18030a8dd  call    cs:__imp_StrToID
0x18030a8e4  nop     dword ptr [rax+rax+00h]
0x18030a8e9  movzx   edx, ax
0x18030a8ec  mov     rcx, rsi
0x18030a8ef  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18030a8f6  nop     dword ptr [rax+rax+00h]
0x18030a8fb  lea     rcx, aEprogresslaunc_0; "eProgressLauncherBlank"
0x18030a902  mov     [rsi+178h], rax
0x18030a909  call    cs:__imp_StrToID
0x18030a910  nop     dword ptr [rax+rax+00h]
0x18030a915  movzx   edx, ax
0x18030a918  mov     rcx, rsi
0x18030a91b  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18030a922  nop     dword ptr [rax+rax+00h]
0x18030a927  lea     rcx, [rbp+var_50]
0x18030a92b  mov     [rbp+var_50], 0
0x18030a933  mov     [rsi+180h], rax
0x18030a93a  mov     [rbp+var_38], 0
0x18030a942  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18030a947  lea     rcx, [rbp+var_38]; this
0x18030a94b  call    ?EnsureObject@BehaviorEngineHelper@@IEAAJXZ; BehaviorEngineHelper::EnsureObject(void)
0x18030a950  test    eax, eax
0x18030a952  js      short loc_18030A998
0x18030a954  mov     rcx, [rbp+var_38]
0x18030a958  lea     rdx, [rbp+var_50]
0x18030a95c  mov     [rsp+80h+ppv], rdx
0x18030a961  lea     r8, aAnimationtrap; "AnimationTrap"
0x18030a968  xor     r9d, r9d
0x18030a96b  lea     rdx, aPvl; "PVL"
0x18030a972  mov     rax, [rcx]
0x18030a975  mov     rax, [rax+28h]
0x18030a979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18030a97e  test    eax, eax
0x18030a980  js      short loc_18030A998
0x18030a982  mov     rax, [rsi]
0x18030a985  mov     rcx, rsi
0x18030a988  mov     rdx, [rbp+var_50]
0x18030a98c  mov     rax, [rax+0B0h]
0x18030a993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18030a998  mov     rdx, rsi; struct CSearchSuggestionsProvider *
0x18030a99b  lea     rcx, [rbp+var_28]; this
0x18030a99f  lea     rbx, [rsi+158h]
0x18030a9a6  call    ??0_lambda_aec159daf75c9a566e43618f77172940_@@QEAA@PEAVCSearchSuggestionsProvider@@@Z; _lambda_aec159daf75c9a566e43618f77172940_::_lambda_aec159daf75c9a566e43618f77172940_(CSearchSuggestionsProvider *)
0x18030a9ab  mov     rdx, rax
0x18030a9ae  mov     rcx, rbx
0x18030a9b1  call    DirectUI__SimpleTimer__SetHandler__lambda_c7441d9f82d1d6c562ddd4763737fe37___
0x18030a9b6  test    eax, eax
0x18030a9b8  js      short loc_18030A9DF
0x18030a9ba  mov     rax, [rsi]
0x18030a9bd  mov     rcx, rsi
0x18030a9c0  mov     rax, [rax+198h]
0x18030a9c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18030a9cc  movaps  xmm1, xmm0; float
0x18030a9cf  movss   dword ptr [rsi+168h], xmm0
0x18030a9d7  mov     rcx, rbx; this
0x18030a9da  call    ?DelayedStart@SimpleTimer@DirectUI@@QEAAXM@Z; DirectUI::SimpleTimer::DelayedStart(float)
0x18030a9df  mov     rax, [r12]
0x18030a9e3  lea     rcx, [rbp+var_48]
0x18030a9e7  mov     [rbp+var_48], 0
0x18030a9ef  mov     rbx, [rax]
0x18030a9f2  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18030a9f7  lea     r8, [rbp+var_48]
0x18030a9fb  mov     rcx, r12
0x18030a9fe  lea     rdx, _GUID_b9b939fe_429a_45a0_8934_247a0c66348f
0x18030aa05  mov     rax, rbx
0x18030aa08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18030aa0d  test    eax, eax
0x18030aa0f  js      loc_18030AAD2
0x18030aa15  mov     rcx, [rbp+var_48]
0x18030aa19  lea     r8, [rbp+var_18]
0x18030aa1d  xorps   xmm0, xmm0
0x18030aa20  mov     [rbp+var_28], 0
0x18030aa27  movups  [rbp+var_18], xmm0
0x18030aa2b  lea     rdx, [rbp+var_28]
0x18030aa2f  mov     rax, [rcx]
0x18030aa32  mov     rax, [rax+20h]
0x18030aa36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18030aa3b  mov     edi, eax
0x18030aa3d  test    eax, eax
0x18030aa3f  js      loc_18030AAD2
0x18030aa45  cmp     [rbp+var_28], r14d
0x18030aa49  jnz     short loc_18030AA66
0x18030aa4b  mov     rax, [rsi]
0x18030aa4e  lea     r8, [rbp+var_18]
0x18030aa52  mov     edx, r14d
0x18030aa55  mov     rcx, rsi
0x18030aa58  mov     rax, [rax+180h]
0x18030aa5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18030aa64  jmp     short loc_18030AAD2
0x18030aa66  mov     r14, [r15]
0x18030aa69  test    r14, r14
0x18030aa6c  jz      short loc_18030AAA6
0x18030aa6e  mov     rax, [r14]
0x18030aa71  lea     rbx, [rsi+108h]
0x18030aa78  mov     rcx, [rbx]; pv
0x18030aa7b  mov     rdi, [rax+18h]
0x18030aa7f  call    cs:__imp_CoTaskMemFree
0x18030aa86  nop     dword ptr [rax+rax+00h]
0x18030aa8b  lea     rdx, [rsi+148h]
0x18030aa92  mov     r8, rbx
0x18030aa95  mov     rcx, r14
0x18030aa98  mov     rax, rdi
0x18030aa9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18030aaa0  mov     edi, eax
0x18030aaa2  test    eax, eax
0x18030aaa4  js      short loc_18030AAD2
0x18030aaa6  mov     rax, [rsi]
0x18030aaa9  mov     rdx, r12
0x18030aaac  mov     rcx, rsi
0x18030aaaf  mov     rax, [rax+190h]
0x18030aab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18030aabb  cmp     dword ptr [rsi+128h], 0
0x18030aac2  mov     edi, eax
0x18030aac4  jz      short loc_18030AAD2
0x18030aac6  test    eax, eax
0x18030aac8  js      short loc_18030AAD2
0x18030aaca  mov     rcx, rsi; this
0x18030aacd  call    ?_InitializeRunningShares@FlowUIBase@@IEAAJXZ; FlowUIBase::_InitializeRunningShares(void)
0x18030aad2  lea     rcx, [rbp+var_48]
0x18030aad6  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18030aadb  lea     rcx, [rbp+var_38]; this
0x18030aadf  call    ??1DuiPVLTrigger@DirectUI@@QEAA@XZ; DirectUI::DuiPVLTrigger::~DuiPVLTrigger(void)
0x18030aae4  lea     rcx, [rbp+var_50]
0x18030aae8  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18030aaed  lea     rcx, [rbp+var_40]
0x18030aaf1  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18030aaf6  mov     eax, edi
0x18030aaf8  mov     rcx, [rbp+var_8]
0x18030aafc  xor     rcx, rsp; StackCookie
0x18030aaff  call    __security_check_cookie
0x18030ab04  add     rsp, 80h
0x18030ab0b  pop     r15
0x18030ab0d  pop     r14
0x18030ab0f  pop     r12
0x18030ab11  pop     rdi
0x18030ab12  pop     rsi
0x18030ab13  pop     rbx
0x18030ab14  pop     rbp
0x18030ab15  retn
```
