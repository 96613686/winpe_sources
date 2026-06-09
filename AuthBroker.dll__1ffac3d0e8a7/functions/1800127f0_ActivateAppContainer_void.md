# ActivateAppContainer(void *)

- ea: `0x1800127f0`
- end: `0x1800129b1`
- name: `?ActivateAppContainer@@YAKPEAX@Z`
- size: `449`
- prototype: `__int64 __fastcall(IAuthBrokerUIContext *lpParam)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006060`
- `0x18000737c`
- `0x1800127f0`
- `0x18002039c`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001298e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001298e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001282d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001282d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012930`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012930`

## pseudocode

```c
__int64 __fastcall ActivateAppContainer(IAuthBrokerUIContext *lpParam)
{
  HRESULT v2; // eax
  HRESULT ProcessTypeFromWindow; // ebx
  WPP_PROJECT_CONTROL_BLOCK *v4; // rax
  unsigned __int16 v5; // dx
  unsigned __int8 v6; // si
  PROCESS_UICONTEXT pProcessUIContext; // [rsp+60h] [rbp+28h] BYREF
  Microsoft::WRL::ComPtr<IAuthBrokerUI> spBrokerUI; // [rsp+68h] [rbp+30h] BYREF
  HWND__ *hwndParent; // [rsp+70h] [rbp+38h] BYREF
  Microsoft::WRL::ComPtr<IAuthBrokerUIContext> pBrokerUIContext; // [rsp+78h] [rbp+40h] BYREF

  spBrokerUI.ptr_ = 0;
  pBrokerUIContext.ptr_ = lpParam;
  if ( lpParam )
    lpParam->AddRef(lpParam);
  hwndParent = 0;
  v2 = CoInitializeEx(0, 2u);
  if ( v2 >= 0 )
  {
    ProcessTypeFromWindow = lpParam->GetParentWindow(lpParam, &hwndParent);
    if ( ProcessTypeFromWindow >= 0 )
    {
      pProcessUIContext = PROCESS_UICONTEXT_DESKTOP;
      ProcessTypeFromWindow = CallerIdentity::GetProcessTypeFromWindow(hwndParent, &pProcessUIContext);
      if ( ProcessTypeFromWindow >= 0 )
      {
        if ( (pProcessUIContext & 0xFFFFFFFC) != 0 || (v6 = 1, pProcessUIContext == PROCESS_UICONTEXT_IMMERSIVE) )
          v6 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spBrokerUI);
        ProcessTypeFromWindow = CoCreateInstance(
                                  &GUID_0ea79562_d4f6_47ba_b7f2_1e9b06ba16a4,
                                  0,
                                  v6 != 0 ? 1 : 4,
                                  &GUID_208a214e_23f8_415e_801d_92a6a8e72553,
                                  (LPVOID *)&spBrokerUI.ptr_);
        if ( ProcessTypeFromWindow >= 0 )
          ProcessTypeFromWindow = spBrokerUI.ptr_->ShowAuthBrokerUI(spBrokerUI.ptr_, lpParam, v6);
        goto LABEL_24;
      }
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
        || WPP_GLOBAL_Control[1].Control.Level < 2u )
      {
LABEL_24:
        CoUninitialize();
        goto LABEL_25;
      }
      v5 = 65;
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) == 0
        || WPP_GLOBAL_Control[1].Control.Level < 2u )
      {
        goto LABEL_24;
      }
      v5 = 64;
    }
    WPP_SF_d(v4[1].Control.Logger, v5, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids, ProcessTypeFromWindow);
    goto LABEL_24;
  }
  ProcessTypeFromWindow = 0;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
    && WPP_GLOBAL_Control[1].Control.Level >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x3Fu, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids, v2);
  }
LABEL_25:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&pBrokerUIContext);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spBrokerUI);
  return (unsigned int)ProcessTypeFromWindow;
}

```

## disassembly

```asm
0x1800127f0  push    rbp
0x1800127f2  push    rbx
0x1800127f3  push    rsi
0x1800127f4  push    rdi
0x1800127f5  mov     rbp, rsp
0x1800127f8  sub     rsp, 38h
0x1800127fc  mov     [rbp+spBrokerUI.ptr_], 0
0x180012804  mov     rdi, lpParam
0x180012807  mov     [rbp+pBrokerUIContext.ptr_], lpParam
0x18001280b  test    lpParam, lpParam
0x18001280e  jz      short loc_18001281C
0x180012810  mov     rax, [lpParam]
0x180012813  mov     rax, [rax+8]
0x180012817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001281c  mov     esi, 2
0x180012821  mov     [rbp+hwndParent], 0
0x180012829  mov     edx, esi; dwCoInit
0x18001282b  xor     ecx, ecx; pvReserved
0x18001282d  call    cs:__imp_CoInitializeEx
0x180012833  test    eax, eax
0x180012835  jns     short loc_180012880
0x180012837  xor     ebx, ebx
0x180012839  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180012840  lea     lpParam, WPP_GLOBAL_Control
0x180012847  cmp     r10, lpParam
0x18001284a  jz      loc_180012994
0x180012850  test    byte ptr [r10+44h], 8
0x180012855  jz      loc_180012994
0x18001285b  cmp     [r10+41h], sil
0x18001285f  jb      loc_180012994
0x180012865  mov     lpParam, [r10+38h]; Logger
0x180012869  lea     edx, [rsi+3Dh]; id
0x18001286c  mov     r9d, eax; _a1
0x18001286f  lea     r8, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids; TraceGuid
0x180012876  call    WPP_SF_d
0x18001287b  jmp     loc_180012994
0x180012880  mov     rax, [rdi]
0x180012883  lea     rdx, [rbp+hwndParent]
0x180012887  mov     lpParam, rdi
0x18001288a  mov     rax, [rax+18h]
0x18001288e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012893  mov     ebx, eax
0x180012895  test    eax, eax
0x180012897  jns     short loc_1800128CE
0x180012899  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800128a0  lea     lpParam, WPP_GLOBAL_Control
0x1800128a7  cmp     rax, lpParam
0x1800128aa  jz      loc_18001298E
0x1800128b0  test    byte ptr [rax+44h], 8
0x1800128b4  jz      loc_18001298E
0x1800128ba  cmp     [rax+41h], sil
0x1800128be  jb      loc_18001298E
0x1800128c4  mov     edx, 40h ; '@'
0x1800128c9  jmp     loc_18001297B
0x1800128ce  mov     lpParam, [rbp+hwndParent]; hwnd
0x1800128d2  lea     rdx, [rbp+pProcessUIContext]; pProcessUIContext
0x1800128d6  mov     [rbp+pProcessUIContext], 0
0x1800128dd  call    ?GetProcessTypeFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAW4PROCESS_UICONTEXT@@@Z; CallerIdentity::GetProcessTypeFromWindow(HWND__ *,PROCESS_UICONTEXT *)
0x1800128e2  mov     ebx, eax
0x1800128e4  test    eax, eax
0x1800128e6  js      short loc_180012957
0x1800128e8  test    [rbp+pProcessUIContext], 0FFFFFFFCh
0x1800128ef  jnz     short loc_1800128FB
0x1800128f1  mov     esi, 1
0x1800128f6  cmp     [rbp+pProcessUIContext], esi
0x1800128f9  jnz     short loc_1800128FE
0x1800128fb  xor     sil, sil
0x1800128fe  lea     lpParam, [rbp+spBrokerUI]; this
0x180012902  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012907  mov     al, sil
0x18001290a  lea     r9, _GUID_208a214e_23f8_415e_801d_92a6a8e72553; riid
0x180012911  neg     al
0x180012913  lea     lpParam, _GUID_0ea79562_d4f6_47ba_b7f2_1e9b06ba16a4; rclsid
0x18001291a  lea     rax, [rbp+spBrokerUI]
0x18001291e  sbb     r8d, r8d
0x180012921  mov     [rsp+38h+ppv], rax; ppv
0x180012926  and     r8d, 0FFFFFFFDh
0x18001292a  xor     edx, edx; pUnkOuter
0x18001292c  add     r8d, 4; dwClsContext
0x180012930  call    cs:__imp_CoCreateInstance
0x180012936  mov     ebx, eax
0x180012938  test    eax, eax
0x18001293a  js      short loc_18001298E
0x18001293c  mov     lpParam, [rbp+spBrokerUI.ptr_]
0x180012940  mov     rdx, rdi
0x180012943  movzx   r8d, sil
0x180012947  mov     rax, [lpParam]
0x18001294a  mov     rax, [rax+18h]
0x18001294e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012953  mov     ebx, eax
0x180012955  jmp     short loc_18001298E
0x180012957  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001295e  lea     lpParam, WPP_GLOBAL_Control
0x180012965  cmp     rax, lpParam
0x180012968  jz      short loc_18001298E
0x18001296a  test    byte ptr [rax+44h], 8
0x18001296e  jz      short loc_18001298E
0x180012970  cmp     [rax+41h], sil
0x180012974  jb      short loc_18001298E
0x180012976  mov     edx, 41h ; 'A'; id
0x18001297b  mov     lpParam, [rax+38h]; Logger
0x18001297f  lea     r8, WPP_f7c801e2cbc1309287ae73e02ff729a7_Traceguids; TraceGuid
0x180012986  mov     r9d, ebx; _a1
0x180012989  call    WPP_SF_d
0x18001298e  call    cs:__imp_CoUninitialize
0x180012994  lea     lpParam, [rbp+pBrokerUIContext]; this
0x180012998  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001299d  lea     lpParam, [rbp+spBrokerUI]; this
0x1800129a1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800129a6  mov     eax, ebx
0x1800129a8  add     rsp, 38h
0x1800129ac  pop     rdi
0x1800129ad  pop     rsi
0x1800129ae  pop     rbx
0x1800129af  pop     rbp
0x1800129b0  retn
```
