# CSearchPaneTypeToSearchService::HandleXAMLWindowMessage(HWND__ *,uint,unsigned __int64,__int64,XAMLWindowMessageResult *)

- ea: `0x180027980`
- end: `0x180027aa6`
- name: `?HandleXAMLWindowMessage@CSearchPaneTypeToSearchService@@UEAAXPEAUHWND__@@I_K_JPEAUXAMLWindowMessageResult@@@Z`
- size: `294`
- prototype: `void __fastcall(CSearchPaneTypeToSearchService *__hidden this, HWND, unsigned int, unsigned __int64, HWND hWnd, struct XAMLWindowMessageResult *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180007b3c`
- `0x1800273e0`
- `0x180027980`
- `0x180028320`
- `0x18003a04c`
- `0x18007b010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x180027a22`
- `SHCORE!IUnknown_QueryService` at `0x180027a22`
- `USER32!GetWindow` at `0x180027a55`
- `USER32!GetWindow` at `0x180027a55`
- `USER32!GetForegroundWindow` at `0x180027a66`
- `USER32!GetForegroundWindow` at `0x180027a66`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSearchPaneTypeToSearchService::HandleXAMLWindowMessage(
        IUnknown **this,
        HWND a2,
        int a3,
        __int64 a4,
        HWND hWnd)
{
  HWND Window; // rax
  bool v8; // zf
  int v9; // eax
  void *ppvOut; // [rsp+20h] [rbp-10h] BYREF
  HWND v11; // [rsp+28h] [rbp-8h] BYREF
  int v12; // [rsp+50h] [rbp+20h] BYREF

  if ( a3 == 256 )
  {
    if ( (_DWORD)a4 == 27 )
    {
      if ( Microsoft::WRL::EventSource<IStartMenuXAMLViewActivationEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>::GetSize(
             this + 15,
             a2) )
      {
        v12 = 4;
        CSearchPaneTypeToSearchService::_FireActivationChangedOnBackgroundThread(
          (CSearchPaneTypeToSearchService *)(this - 6),
          (const struct StartMenuXAMLViewActivationEventArgs *)&v12);
      }
      else
      {
        XAMLHost_TryToReturnActivation(*(this - 4));
      }
    }
  }
  else if ( a3 == 6
         && Microsoft::WRL::EventSource<IStartMenuXAMLViewActivationEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>::GetSize(
              this + 15,
              a2) )
  {
    ppvOut = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
    if ( IUnknown_QueryService(
           *(this - 4),
           &GUID_c3852ed5_c926_4cac_98c4_b7afc5d289d6,
           &GUID_00000114_0000_0000_c000_000000000046,
           &ppvOut) >= 0 )
    {
      v11 = 0;
      if ( (*(int (__fastcall **)(void *, HWND *))(*(_QWORD *)ppvOut + 24LL))(ppvOut, &v11) >= 0 )
      {
        Window = GetWindow(hWnd, 4u);
        if ( Window != v11 )
        {
          if ( !a4 || (v8 = GetForegroundWindow() == v11, v9 = 3, !v8) )
            v9 = 2;
          v12 = v9;
          CSearchPaneTypeToSearchService::_FireActivationChangedOnBackgroundThread(
            (CSearchPaneTypeToSearchService *)(this - 6),
            (const struct StartMenuXAMLViewActivationEventArgs *)&v12);
        }
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
  }
}

```

## disassembly

```asm
0x180027980  mov     [rsp-8+arg_0], rbx
0x180027985  mov     [rsp-8+arg_8], rdi
0x18002798a  push    rbp
0x18002798b  mov     rbp, rsp
0x18002798e  sub     rsp, 30h
0x180027992  mov     rdi, r9
0x180027995  mov     rbx, rcx
0x180027998  cmp     r8d, 100h
0x18002799f  jnz     short loc_1800279DF
0x1800279a1  cmp     edi, 1Bh
0x1800279a4  jnz     loc_180027A96
0x1800279aa  add     rcx, 78h ; 'x'
0x1800279ae  call    ?GetSize@?$EventSource@UIStartMenuXAMLViewActivationEventHandler@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEBA_KXZ; Microsoft::WRL::EventSource<IStartMenuXAMLViewActivationEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>::GetSize(void)
0x1800279b3  test    rax, rax
0x1800279b6  jnz     short loc_1800279C6
0x1800279b8  mov     rcx, [rbx-20h]; punk
0x1800279bc  call    ?XAMLHost_TryToReturnActivation@@YAXPEAUIUnknown@@@Z; XAMLHost_TryToReturnActivation(IUnknown *)
0x1800279c1  jmp     loc_180027A96
0x1800279c6  mov     [rbp+arg_10], 4
0x1800279cd  lea     rdx, [rbp+arg_10]; struct StartMenuXAMLViewActivationEventArgs *
0x1800279d1  lea     rcx, [rbx-30h]; this
0x1800279d5  call    ?_FireActivationChangedOnBackgroundThread@CSearchPaneTypeToSearchService@@AEAAXAEBUStartMenuXAMLViewActivationEventArgs@@@Z; CSearchPaneTypeToSearchService::_FireActivationChangedOnBackgroundThread(StartMenuXAMLViewActivationEventArgs const &)
0x1800279da  jmp     loc_180027A96
0x1800279df  cmp     r8d, 6
0x1800279e3  jnz     loc_180027A96
0x1800279e9  add     rcx, 78h ; 'x'
0x1800279ed  call    ?GetSize@?$EventSource@UIStartMenuXAMLViewActivationEventHandler@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEBA_KXZ; Microsoft::WRL::EventSource<IStartMenuXAMLViewActivationEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>::GetSize(void)
0x1800279f2  test    rax, rax
0x1800279f5  jz      loc_180027A96
0x1800279fb  mov     [rbp+ppvOut], 0
0x180027a03  lea     rcx, [rbp+ppvOut]
0x180027a07  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180027a0c  lea     r9, [rbp+ppvOut]; ppvOut
0x180027a10  lea     r8, _GUID_00000114_0000_0000_c000_000000000046; riid
0x180027a17  lea     rdx, _GUID_c3852ed5_c926_4cac_98c4_b7afc5d289d6; guidService
0x180027a1e  mov     rcx, [rbx-20h]; punk
0x180027a22  call    cs:__imp_IUnknown_QueryService
0x180027a28  test    eax, eax
0x180027a2a  js      short loc_180027A8D
0x180027a2c  mov     [rbp+var_8], 0
0x180027a34  mov     rcx, [rbp+ppvOut]
0x180027a38  mov     rax, [rcx]
0x180027a3b  lea     rdx, [rbp+var_8]
0x180027a3f  mov     rax, [rax+18h]
0x180027a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a48  test    eax, eax
0x180027a4a  js      short loc_180027A8D
0x180027a4c  mov     edx, 4; uCmd
0x180027a51  mov     rcx, [rbp+hWnd]; hWnd
0x180027a55  call    cs:__imp_GetWindow
0x180027a5b  cmp     rax, [rbp+var_8]
0x180027a5f  jz      short loc_180027A8D
0x180027a61  test    rdi, rdi
0x180027a64  jz      short loc_180027A77
0x180027a66  call    cs:__imp_GetForegroundWindow
0x180027a6c  cmp     rax, [rbp+var_8]
0x180027a70  mov     eax, 3
0x180027a75  jz      short loc_180027A7C
0x180027a77  mov     eax, 2
0x180027a7c  mov     [rbp+arg_10], eax
0x180027a7f  lea     rdx, [rbp+arg_10]; struct StartMenuXAMLViewActivationEventArgs *
0x180027a83  lea     rcx, [rbx-30h]; this
0x180027a87  call    ?_FireActivationChangedOnBackgroundThread@CSearchPaneTypeToSearchService@@AEAAXAEBUStartMenuXAMLViewActivationEventArgs@@@Z; CSearchPaneTypeToSearchService::_FireActivationChangedOnBackgroundThread(StartMenuXAMLViewActivationEventArgs const &)
0x180027a8c  nop
0x180027a8d  lea     rcx, [rbp+ppvOut]
0x180027a91  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180027a96  mov     rbx, [rsp+30h+arg_0]
0x180027a9b  mov     rdi, [rsp+30h+arg_8]
0x180027aa0  add     rsp, 30h
0x180027aa4  pop     rbp
0x180027aa5  retn
```
