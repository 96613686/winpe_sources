# CSearchPaneTypeToSearchService::HandleMessage(TypeToSearchOptions const *,TYPE_TO_SEARCH_MSG const *,uint)

- ea: `0x180027440`
- end: `0x180027978`
- name: `?HandleMessage@CSearchPaneTypeToSearchService@@UEAAJPEBUTypeToSearchOptions@@PEBUTYPE_TO_SEARCH_MSG@@I@Z`
- size: `1336`
- prototype: `__int64 __fastcall(CSearchPaneTypeToSearchService *__hidden this, const struct TypeToSearchOptions *, const struct TYPE_TO_SEARCH_MSG *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180007b3c`
- `0x180016ca0`
- `0x180026574`
- `0x180027440`
- `0x180028920`
- `0x180028968`
- `0x1800289bc`
- `0x18003e3c4`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002771f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002771f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002757b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002757b`
- `SHCORE!IUnknown_QueryService` at `0x180027510`
- `SHCORE!IUnknown_QueryService` at `0x180027510`
- `ntdll!iswalnum` at `0x1800277ed`
- `ntdll!iswalnum` at `0x1800277ed`
- `USER32!PostMessageW` at `0x1800278fb`
- `USER32!PostMessageW` at `0x1800278fb`
- `USER32!DispatchMessageW` at `0x180027622`
- `USER32!DispatchMessageW` at `0x1800276e8`
- `USER32!DispatchMessageW` at `0x180027622`
- `USER32!DispatchMessageW` at `0x1800276e8`
- `USER32!PeekMessageW` at `0x180027638`
- `USER32!PeekMessageW` at `0x1800276da`
- `USER32!PeekMessageW` at `0x180027638`
- `USER32!PeekMessageW` at `0x1800276da`
- `USER32!GetKeyboardLayout` at `0x1800275d9`
- `USER32!GetKeyboardLayout` at `0x1800275ef`
- `USER32!GetKeyboardLayout` at `0x1800275d9`
- `USER32!GetKeyboardLayout` at `0x1800275ef`
- `USER32!ActivateKeyboardLayout` at `0x1800275e7`
- `USER32!ActivateKeyboardLayout` at `0x1800275e7`
- `USER32!SystemParametersInfoW` at `0x1800275ca`
- `USER32!SystemParametersInfoW` at `0x1800275ca`
- `USER32!SetForegroundWindow` at `0x180027542`
- `USER32!SetForegroundWindow` at `0x180027542`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CSearchPaneTypeToSearchService::HandleMessage(
        CSearchPaneTypeToSearchService *this,
        const struct TypeToSearchOptions *a2,
        const struct TYPE_TO_SEARCH_MSG *a3,
        unsigned int a4)
{
  unsigned int v7; // r14d
  char v8; // bl
  char v9; // r10
  unsigned int i; // edx
  HRESULT Instance; // ebx
  struct ITfKeystrokeMgr **v12; // r12
  HKL KeyboardLayout; // rax
  struct ITfKeystrokeMgr *v14; // rdi
  HRESULT (__stdcall *QueryInterface)(ITfKeystrokeMgr *, const IID *const, void **); // rbx
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned int v18; // edi
  char v19; // si
  __int64 v20; // rcx
  PVOID *v21; // r10
  const struct TYPE_TO_SEARCH_MSG *v22; // rsi
  char *v23; // rdi
  __int64 v24; // rdx
  __int64 v25; // r8
  unsigned __int64 v26; // rsi
  int v27; // eax
  _BYTE v29[4]; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v30; // [rsp+44h] [rbp-45h] BYREF
  __int64 v31; // [rsp+48h] [rbp-41h] BYREF
  __int64 v32; // [rsp+50h] [rbp-39h] BYREF
  int pvParam; // [rsp+58h] [rbp-31h] BYREF
  HWND hWnd; // [rsp+60h] [rbp-29h] BYREF
  void *ppvOut; // [rsp+68h] [rbp-21h] BYREF
  HRESULT v36; // [rsp+70h] [rbp-19h]
  MSG Msg; // [rsp+78h] [rbp-11h] BYREF
  char v39; // [rsp+108h] [rbp+7Fh] BYREF

  v7 = 0;
  hWnd = 0;
  v8 = 0;
  v9 = 0;
  v39 = 0;
  for ( i = 0; i < a4; ++i )
  {
    if ( *((_DWORD *)a3 + 18 * i + 2) != *((_DWORD *)this + 30) )
    {
      v8 = 0;
      goto LABEL_10;
    }
    v8 = 1;
  }
  if ( v8 )
  {
    v31 = 0;
    if ( (int)Microsoft::WRL::ComPtr<Windows::UI::Xaml::Controls::IControl>::As<Windows::UI::Xaml::Controls::ISearchBoxPriv>(
                (char *)this + 40,
                &v31) >= 0 )
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v31 + 56LL))(v31, &v39);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v31);
    v9 = v39;
  }
LABEL_10:
  ppvOut = 0;
  if ( v8 && !v9 )
  {
    Instance = -2147467260;
    goto LABEL_81;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
  Instance = IUnknown_QueryService(
               *((IUnknown **)this - 3),
               &GUID_c3852ed5_c926_4cac_98c4_b7afc5d289d6,
               &GUID_00000114_0000_0000_c000_000000000046,
               &ppvOut);
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(void *, HWND *))(*(_QWORD *)ppvOut + 24LL))(ppvOut, &hWnd);
    if ( Instance >= 0 )
    {
      if ( !SetForegroundWindow(hWnd) )
      {
        Instance = -2147024891;
        goto LABEL_81;
      }
      v12 = (struct ITfKeystrokeMgr **)((char *)this + 48);
      if ( *((_QWORD *)this + 6)
        || (Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 48),
            Instance = CoCreateInstance(
                         &CLSID_TF_ThreadMgr,
                         0,
                         1u,
                         &GUID_aa80e7f0_2021_11d2_93e0_0060b067b86e,
                         (LPVOID *)this + 6),
            Instance >= 0) )
      {
        v29[0] = 0;
        Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, _BYTE *))(**((_QWORD **)this + 5) + 368LL))(
                     *((_QWORD *)this + 5),
                     3,
                     v29);
        if ( Instance >= 0 )
        {
          pvParam = 1;
          SystemParametersInfoW(0x104Eu, 0, &pvParam, 0);
          if ( pvParam )
          {
            KeyboardLayout = GetKeyboardLayout(*((_DWORD *)a3 + 16));
            ActivateKeyboardLayout(KeyboardLayout, 0x80u);
          }
          if ( ((unsigned __int16)GetKeyboardLayout(0) & 0x3FF) == 0x11 )
          {
            memset(&Msg, 0, sizeof(Msg));
            while ( PeekMessageW(&Msg, 0, 0x7FFFu, 0x7FFFu, 0x980001u) )
              DispatchMessageW(&Msg);
          }
          v31 = 0;
          v14 = *v12;
          QueryInterface = (*v12)->lpVtbl->QueryInterface;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v31);
          Instance = ((__int64 (__fastcall *)(struct ITfKeystrokeMgr *, GUID *, __int64 *))QueryInterface)(
                       v14,
                       &GUID_aa80e801_2021_11d2_93e0_0060b067b86e,
                       &v31);
          v36 = Instance;
          if ( Instance < 0 )
            goto LABEL_79;
          v18 = 0;
          v30 = 0;
          while ( !v30 )
          {
            if ( v18 >= 0xA )
              goto LABEL_41;
            if ( (*(unsigned int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v31 + 80LL))(v31, &v30) )
            {
              v30 = 0;
              goto LABEL_41;
            }
            if ( v30 )
              break;
            v19 = 0;
            memset(&Msg, 0, sizeof(Msg));
            while ( PeekMessageW(&Msg, 0, 0, 0, 0xD80001u) )
            {
              DispatchMessageW(&Msg);
              if ( (*(unsigned int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v31 + 80LL))(v31, &v30) )
              {
                v30 = 0;
                break;
              }
              v19 = 1;
            }
            if ( !v19 )
            {
              ++v18;
              Sleep(0x32u);
            }
          }
          v20 = *((_QWORD *)this + 14);
          if ( v20 )
            (*(void (__fastcall **)(__int64, HWND))(*(_QWORD *)v20 + 32LL))(v20, hWnd);
LABEL_41:
          v21 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, &WPP_bf51d773c27e3ecacbbf91ef8b589f1d_Traceguids, v30);
              v21 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 68) & 1) != 0 && *((_BYTE *)v21 + 65) >= 4u )
            {
              WPP_SF_D(v21[7], v16, v17, a4);
              v21 = (PVOID *)WPP_GLOBAL_Control;
            }
          }
          if ( !a4 )
          {
LABEL_79:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v31);
            goto LABEL_81;
          }
          v22 = a3;
          while ( 1 )
          {
            v23 = (char *)v22 + 72 * v7;
            if ( (*((_BYTE *)v21 + 68) & 1) != 0 && *((_BYTE *)v21 + 65) >= 4u )
            {
              LODWORD(v32) = 0;
              LOWORD(v32) = *((_WORD *)v23 + 8);
              if ( !iswalnum(v32) )
                LOWORD(v32) = 45;
              v21 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
              {
                WPP_SF_DiSi(
                  *((_QWORD *)WPP_GLOBAL_Control + 7),
                  v24,
                  v25,
                  *((_DWORD *)v23 + 2),
                  *((_QWORD *)v23 + 2),
                  (__int64)&v32,
                  *((_QWORD *)v23 + 3));
                v21 = (PVOID *)WPP_GLOBAL_Control;
              }
              v26 = 0;
              if ( *((_DWORD *)v23 + 12) )
              {
                do
                {
                  if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 68) & 1) != 0 && *((_BYTE *)v21 + 65) >= 4u )
                  {
                    WPP_SF_DD(
                      v21[7],
                      v24,
                      v25,
                      *(unsigned int *)(*((_QWORD *)v23 + 7) + 8 * v26),
                      *(__int16 *)(*((_QWORD *)v23 + 7) + 8 * v26 + 4));
                    v21 = (PVOID *)WPP_GLOBAL_Control;
                  }
                  ++v26;
                }
                while ( v26 < *((unsigned int *)v23 + 12) );
                v12 = (struct ITfKeystrokeMgr **)((char *)this + 48);
              }
              v22 = a3;
            }
            v27 = *((_DWORD *)v23 + 2);
            if ( *((_DWORD *)this + 30) == v27 )
            {
              v32 = 0;
              if ( (int)Microsoft::WRL::ComPtr<Windows::UI::Xaml::Controls::IControl>::As<Windows::UI::Xaml::Controls::ISearchBoxPriv>(
                          (char *)this + 40,
                          &v32) >= 0 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 48LL))(v32);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v32);
            }
            else if ( *((_DWORD *)this + 31) == v27 )
            {
              PostMessageW(hWnd, 0x102u, *((_QWORD *)v23 + 2), *((_QWORD *)v23 + 3));
            }
            else
            {
              if ( *((_DWORD *)v23 + 4) >= 0xFFu || (*((_BYTE *)&qword_18008D860 + *((unsigned int *)v23 + 4)) & 2) == 0 )
                goto LABEL_77;
              ProcessForwardedMessage(*v12, hWnd, (const struct TYPE_TO_SEARCH_MSG *)v23);
            }
            v21 = (PVOID *)WPP_GLOBAL_Control;
LABEL_77:
            if ( ++v7 >= a4 )
            {
              Instance = v36;
              goto LABEL_79;
            }
          }
        }
      }
    }
  }
LABEL_81:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180027440  mov     [rsp-8+arg_0], rbx
0x180027445  mov     [rsp-8+arg_10], r8
0x18002744a  push    rbp
0x18002744b  push    rsi
0x18002744c  push    rdi
0x18002744d  push    r12
0x18002744f  push    r13
0x180027451  push    r14
0x180027453  push    r15
0x180027455  lea     rbp, [rsp-27h]
0x18002745a  sub     rsp, 0B0h
0x180027461  mov     r13d, r9d
0x180027464  mov     rsi, r8
0x180027467  mov     r15, rcx
0x18002746a  xor     r14d, r14d
0x18002746d  mov     [rbp+57h+hWnd], r14
0x180027471  mov     bl, r14b
0x180027474  mov     r10b, r14b
0x180027477  mov     [rbp+57h+arg_18], r14b
0x18002747b  mov     edx, r14d
0x18002747e  cmp     edx, r13d
0x180027481  jnb     short loc_18002749F
0x180027483  mov     eax, edx
0x180027485  lea     rcx, [rax+rax*8]
0x180027489  mov     eax, [r15+78h]
0x18002748d  cmp     [r8+rcx*8+8], eax
0x180027492  jnz     short loc_18002749A
0x180027494  mov     bl, 1
0x180027496  inc     edx
0x180027498  jmp     short loc_18002747E
0x18002749a  mov     bl, r14b
0x18002749d  jmp     short loc_1800274DA
0x18002749f  test    bl, bl
0x1800274a1  jz      short loc_1800274DA
0x1800274a3  mov     [rbp+57h+var_98], r14
0x1800274a7  lea     rcx, [r15+28h]
0x1800274ab  lea     rdx, [rbp+57h+var_98]
0x1800274af  call    ??$As@UISearchBoxPriv@Controls@Xaml@UI@Windows@@@?$ComPtr@UIControl@Controls@Xaml@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISearchBoxPriv@Controls@Xaml@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Xaml::Controls::IControl>::As<Windows::UI::Xaml::Controls::ISearchBoxPriv>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Xaml::Controls::ISearchBoxPriv>>)
0x1800274b4  test    eax, eax
0x1800274b6  js      short loc_1800274CD
0x1800274b8  mov     rcx, [rbp+57h+var_98]
0x1800274bc  mov     rax, [rcx]
0x1800274bf  lea     rdx, [rbp+57h+arg_18]
0x1800274c3  mov     rax, [rax+38h]
0x1800274c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274cc  nop
0x1800274cd  lea     rcx, [rbp+57h+var_98]
0x1800274d1  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800274d6  mov     r10b, [rbp+57h+arg_18]
0x1800274da  mov     [rbp+57h+ppvOut], r14
0x1800274de  test    bl, bl
0x1800274e0  jz      short loc_1800274F1
0x1800274e2  test    r10b, r10b
0x1800274e5  jnz     short loc_1800274F1
0x1800274e7  mov     ebx, 80004004h
0x1800274ec  jmp     loc_180027952
0x1800274f1  lea     rcx, [rbp+57h+ppvOut]
0x1800274f5  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800274fa  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x1800274fe  lea     r8, _GUID_00000114_0000_0000_c000_000000000046; riid
0x180027505  lea     rdx, _GUID_c3852ed5_c926_4cac_98c4_b7afc5d289d6; guidService
0x18002750c  mov     rcx, [r15-18h]; punk
0x180027510  call    cs:__imp_IUnknown_QueryService
0x180027516  mov     ebx, eax
0x180027518  test    eax, eax
0x18002751a  js      loc_180027952
0x180027520  mov     rcx, [rbp+57h+ppvOut]
0x180027524  mov     rax, [rcx]
0x180027527  lea     rdx, [rbp+57h+hWnd]
0x18002752b  mov     rax, [rax+18h]
0x18002752f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027534  mov     ebx, eax
0x180027536  test    eax, eax
0x180027538  js      loc_180027952
0x18002753e  mov     rcx, [rbp+57h+hWnd]; hWnd
0x180027542  call    cs:__imp_SetForegroundWindow
0x180027548  test    eax, eax
0x18002754a  jz      loc_18002794D
0x180027550  lea     r12, [r15+30h]
0x180027554  cmp     [r12], r14
0x180027558  jnz     short loc_18002758B
0x18002755a  mov     rcx, r12
0x18002755d  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180027562  mov     [rsp+0E0h+ppv], r12; ppv
0x180027567  lea     r9, _GUID_aa80e7f0_2021_11d2_93e0_0060b067b86e; riid
0x18002756e  xor     edx, edx; pUnkOuter
0x180027570  lea     r8d, [rdx+1]; dwClsContext
0x180027574  lea     rcx, CLSID_TF_ThreadMgr; rclsid
0x18002757b  call    cs:__imp_CoCreateInstance
0x180027581  mov     ebx, eax
0x180027583  test    eax, eax
0x180027585  js      loc_180027952
0x18002758b  mov     [rbp+57h+var_A0], r14b
0x18002758f  mov     rcx, [r15+28h]
0x180027593  mov     rax, [rcx]
0x180027596  lea     r8, [rbp+57h+var_A0]
0x18002759a  mov     edx, 3
0x18002759f  mov     rax, [rax+170h]
0x1800275a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275ab  mov     ebx, eax
0x1800275ad  test    eax, eax
0x1800275af  js      loc_180027952
0x1800275b5  mov     [rbp+57h+pvParam], 1
0x1800275bc  xor     r9d, r9d; fWinIni
0x1800275bf  lea     r8, [rbp+57h+pvParam]; pvParam
0x1800275c3  xor     edx, edx; uiParam
0x1800275c5  mov     ecx, 104Eh; uiAction
0x1800275ca  call    cs:__imp_SystemParametersInfoW
0x1800275d0  cmp     [rbp+57h+pvParam], r14d
0x1800275d4  jz      short loc_1800275ED
0x1800275d6  mov     ecx, [rsi+40h]; idThread
0x1800275d9  call    cs:__imp_GetKeyboardLayout
0x1800275df  mov     rcx, rax; hkl
0x1800275e2  mov     edx, 80h; Flags
0x1800275e7  call    cs:__imp_ActivateKeyboardLayout
0x1800275ed  xor     ecx, ecx; idThread
0x1800275ef  call    cs:__imp_GetKeyboardLayout
0x1800275f5  mov     ecx, 3FFh
0x1800275fa  and     ax, cx
0x1800275fd  cmp     ax, 11h
0x180027601  jnz     short loc_180027642
0x180027603  xorps   xmm0, xmm0
0x180027606  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x18002760a  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x18002760e  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x180027612  mov     edi, 980001h
0x180027617  mov     ebx, 7FFFh
0x18002761c  jmp     short loc_180027628
0x18002761e  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180027622  call    cs:__imp_DispatchMessageW
0x180027628  mov     dword ptr [rsp+0E0h+ppv], edi; wRemoveMsg
0x18002762c  mov     r9d, ebx; wMsgFilterMax
0x18002762f  mov     r8d, ebx; wMsgFilterMin
0x180027632  xor     edx, edx; hWnd
0x180027634  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180027638  call    cs:__imp_PeekMessageW
0x18002763e  test    eax, eax
0x180027640  jnz     short loc_18002761E
0x180027642  mov     [rbp+57h+var_98], r14
0x180027646  mov     rdi, [r12]
0x18002764a  mov     rax, [rdi]
0x18002764d  mov     rbx, [rax]
0x180027650  lea     rcx, [rbp+57h+var_98]
0x180027654  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180027659  lea     r8, [rbp+57h+var_98]
0x18002765d  lea     rdx, _GUID_aa80e801_2021_11d2_93e0_0060b067b86e
0x180027664  mov     rcx, rdi
0x180027667  mov     rax, rbx
0x18002766a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002766f  mov     ebx, eax
0x180027671  mov     [rbp+57h+var_70], eax
0x180027674  test    eax, eax
0x180027676  js      loc_180027942
0x18002767c  mov     edi, r14d
0x18002767f  mov     [rbp+57h+var_9C], r14d
0x180027683  cmp     [rbp+57h+var_9C], r14d
0x180027687  jnz     loc_180027730
0x18002768d  cmp     edi, 0Ah
0x180027690  jnb     loc_180027749
0x180027696  mov     rcx, [rbp+57h+var_98]
0x18002769a  mov     rax, [rcx]
0x18002769d  lea     rdx, [rbp+57h+var_9C]
0x1800276a1  mov     rax, [rax+50h]
0x1800276a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276aa  test    eax, eax
0x1800276ac  jnz     short loc_18002772A
0x1800276ae  cmp     [rbp+57h+var_9C], r14d
0x1800276b2  jnz     short loc_180027730
0x1800276b4  mov     sil, r14b
0x1800276b7  xorps   xmm0, xmm0
0x1800276ba  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x1800276be  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x1800276c2  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x1800276c6  mov     dword ptr [rsp+0E0h+ppv], 0D80001h; wRemoveMsg
0x1800276ce  xor     r9d, r9d; wMsgFilterMax
0x1800276d1  xor     r8d, r8d; wMsgFilterMin
0x1800276d4  xor     edx, edx; hWnd
0x1800276d6  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800276da  call    cs:__imp_PeekMessageW
0x1800276e0  test    eax, eax
0x1800276e2  jz      short loc_18002770F
0x1800276e4  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800276e8  call    cs:__imp_DispatchMessageW
0x1800276ee  mov     rcx, [rbp+57h+var_98]
0x1800276f2  mov     rax, [rcx]
0x1800276f5  lea     rdx, [rbp+57h+var_9C]
0x1800276f9  mov     rax, [rax+50h]
0x1800276fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027702  test    eax, eax
0x180027704  jnz     short loc_18002770B
0x180027706  mov     sil, 1
0x180027709  jmp     short loc_1800276C6
0x18002770b  mov     [rbp+57h+var_9C], r14d
0x18002770f  test    sil, sil
0x180027712  jnz     loc_180027683
0x180027718  inc     edi
0x18002771a  mov     ecx, 32h ; '2'; dwMilliseconds
0x18002771f  call    cs:__imp_Sleep
0x180027725  jmp     loc_180027683
0x18002772a  mov     [rbp+57h+var_9C], r14d
0x18002772e  jmp     short loc_180027749
0x180027730  mov     rcx, [r15+70h]
0x180027734  test    rcx, rcx
0x180027737  jz      short loc_180027749
0x180027739  mov     rax, [rcx]
0x18002773c  mov     rdx, [rbp+57h+hWnd]
0x180027740  mov     rax, [rax+20h]
0x180027744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027749  lea     rdi, WPP_GLOBAL_Control
0x180027750  mov     r10, cs:WPP_GLOBAL_Control
0x180027757  cmp     r10, rdi
0x18002775a  jz      short loc_1800277B0
0x18002775c  test    byte ptr [r10+44h], 1
0x180027761  jz      short loc_18002778A
0x180027763  cmp     byte ptr [r10+41h], 4
0x180027768  jb      short loc_18002778A
0x18002776a  mov     edx, 0Bh
0x18002776f  mov     r9d, [rbp+57h+var_9C]
0x180027773  lea     r8, WPP_bf51d773c27e3ecacbbf91ef8b589f1d_Traceguids
0x18002777a  mov     rcx, [r10+38h]
0x18002777e  call    WPP_SF_d
0x180027783  mov     r10, cs:WPP_GLOBAL_Control
0x18002778a  cmp     r10, rdi
0x18002778d  jz      short loc_1800277B0
0x18002778f  test    byte ptr [r10+44h], 1
0x180027794  jz      short loc_1800277B0
0x180027796  cmp     byte ptr [r10+41h], 4
0x18002779b  jb      short loc_1800277B0
0x18002779d  mov     r9d, r13d
0x1800277a0  mov     rcx, [r10+38h]
0x1800277a4  call    WPP_SF_D
0x1800277a9  mov     r10, cs:WPP_GLOBAL_Control
0x1800277b0  test    r13d, r13d
0x1800277b3  jz      loc_180027942
0x1800277b9  mov     rsi, [rbp+57h+arg_10]
0x1800277bd  mov     eax, r14d
0x1800277c0  lea     rcx, [rax+rax*8]
0x1800277c4  lea     rdi, [rsi+rcx*8]
0x1800277c8  test    byte ptr [r10+44h], 1
0x1800277cd  jz      loc_1800278A6
0x1800277d3  cmp     byte ptr [r10+41h], 4
0x1800277d8  jb      loc_1800278A6
0x1800277de  mov     dword ptr [rbp+57h+var_90], 0
0x1800277e5  movzx   ecx, word ptr [rdi+10h]; C
0x1800277e9  mov     word ptr [rbp+57h+var_90], cx
0x1800277ed  call    cs:__imp_iswalnum
0x1800277f3  test    eax, eax
0x1800277f5  jnz     short loc_180027800
0x1800277f7  mov     eax, 2Dh ; '-'
0x1800277fc  mov     word ptr [rbp+57h+var_90], ax
0x180027800  mov     r10, cs:WPP_GLOBAL_Control
0x180027807  lea     rax, WPP_GLOBAL_Control
0x18002780e  cmp     r10, rax
0x180027811  jz      short loc_180027850
0x180027813  test    byte ptr [r10+44h], 1
0x180027818  jz      short loc_180027850
0x18002781a  cmp     byte ptr [r10+41h], 4
0x18002781f  jb      short loc_180027850
0x180027821  mov     rax, [rdi+18h]
0x180027825  mov     [rsp+0E0h+var_B0], rax
0x18002782a  lea     rax, [rbp+57h+var_90]
0x18002782e  mov     [rsp+0E0h+var_B8], rax
0x180027833  mov     rax, [rdi+10h]
0x180027837  mov     [rsp+0E0h+ppv], rax
0x18002783c  mov     r9d, [rdi+8]
0x180027840  mov     rcx, [r10+38h]
0x180027844  call    WPP_SF_DiSi
0x180027849  mov     r10, cs:WPP_GLOBAL_Control
0x180027850  xor     esi, esi
0x180027852  cmp     [rdi+30h], esi
0x180027855  jbe     short loc_1800278A2
0x180027857  lea     r12, WPP_GLOBAL_Control
0x18002785e  cmp     r10, r12
0x180027861  jz      short loc_180027893
0x180027863  test    byte ptr [r10+44h], 1
0x180027868  jz      short loc_180027893
0x18002786a  cmp     byte ptr [r10+41h], 4
0x18002786f  jb      short loc_180027893
0x180027871  mov     r9, [rdi+38h]
0x180027875  movsx   eax, word ptr [r9+rsi*8+4]
0x18002787b  mov     dword ptr [rsp+0E0h+ppv], eax
0x18002787f  mov     r9d, [r9+rsi*8]
0x180027883  mov     rcx, [r10+38h]
0x180027887  call    WPP_SF_DD
0x18002788c  mov     r10, cs:WPP_GLOBAL_Control
0x180027893  inc     rsi
0x180027896  mov     eax, [rdi+30h]
0x180027899  cmp     rsi, rax
0x18002789c  jb      short loc_18002785E
0x18002789e  lea     r12, [r15+30h]
0x1800278a2  mov     rsi, [rbp+57h+arg_10]
0x1800278a6  mov     eax, [rdi+8]
0x1800278a9  cmp     [r15+78h], eax
0x1800278ad  jnz     short loc_1800278E4
0x1800278af  mov     [rbp+57h+var_90], 0
0x1800278b7  lea     rdx, [rbp+57h+var_90]
0x1800278bb  lea     rcx, [r15+28h]
0x1800278bf  call    ??$As@UISearchBoxPriv@Controls@Xaml@UI@Windows@@@?$ComPtr@UIControl@Controls@Xaml@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISearchBoxPriv@Controls@Xaml@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Xaml::Controls::IControl>::As<Windows::UI::Xaml::Controls::ISearchBoxPriv>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Xaml::Controls::ISearchBoxPriv>>)
0x1800278c4  test    eax, eax
0x1800278c6  js      short loc_1800278D9
  ... truncated ...
```
