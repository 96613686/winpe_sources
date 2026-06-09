# CSearchBoxControlService::SubscribeToServices(IServiceProvider *)

- ea: `0x18001e250`
- end: `0x18001e34d`
- name: `?SubscribeToServices@CSearchBoxControlService@@EEAAJPEAUIServiceProvider@@@Z`
- size: `253`
- prototype: `__int64 __fastcall(CSearchBoxControlService *__hidden this, struct IServiceProvider *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180007b3c`
- `0x18001e250`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e288`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e288`
- `USER32!SetPropW` at `0x18001e307`
- `USER32!SetPropW` at `0x18001e307`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSearchBoxControlService::SubscribeToServices(
        CSearchBoxControlService *this,
        struct IServiceProvider *a2)
{
  LPVOID *ppv; // rdi
  HRESULT (__stdcall *QueryService)(IServiceProvider *, const GUID *const, const IID *const, void **); // rbx
  __int64 v7; // [rsp+50h] [rbp+8h] BYREF
  HWND hWnd; // [rsp+60h] [rbp+18h] BYREF

  ppv = (LPVOID *)((char *)this + 48);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease((char *)this + 48);
  if ( CoCreateInstance(
         &GUID_807c1e6c_1d00_453f_b920_b61bb7cdd997,
         0,
         1u,
         &GUID_5e078e03_8265_4bbe_9487_d242edbef910,
         ppv) >= 0 )
  {
    v7 = 0;
    QueryService = a2->lpVtbl->QueryService;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v7);
    if ( ((int (__fastcall *)(struct IServiceProvider *, GUID *, GUID *, __int64 *))QueryService)(
           a2,
           &GUID_c3852ed5_c926_4cac_98c4_b7afc5d289d6,
           &GUID_00000114_0000_0000_c000_000000000046,
           &v7) >= 0 )
    {
      hWnd = 0;
      if ( (*(int (__fastcall **)(__int64, HWND *))(*(_QWORD *)v7 + 24LL))(v7, &hWnd) >= 0 )
      {
        SetPropW(hWnd, L"Microsoft TIP No Insert Option", HANDLE_FLAG_INHERIT);
        (*(void (__fastcall **)(LPVOID, HWND, unsigned __int64))(*(_QWORD *)*ppv + 24LL))(
          *ppv,
          hWnd,
          ((unsigned __int64)this + 16) & -(__int64)(this != (CSearchBoxControlService *)24));
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v7);
  }
  return 0;
}

```

## disassembly

```asm
0x18001e250  mov     [rsp+arg_8], rbx
0x18001e255  push    rsi
0x18001e256  push    rdi
0x18001e257  push    r14
0x18001e259  sub     rsp, 30h
0x18001e25d  mov     r14, rdx
0x18001e260  mov     rsi, rcx
0x18001e263  lea     rdi, [rcx+30h]
0x18001e267  mov     rcx, rdi
0x18001e26a  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18001e26f  mov     [rsp+48h+ppv], rdi; ppv
0x18001e274  lea     r9, _GUID_5e078e03_8265_4bbe_9487_d242edbef910; riid
0x18001e27b  xor     edx, edx; pUnkOuter
0x18001e27d  lea     r8d, [rdx+1]; dwClsContext
0x18001e281  lea     rcx, _GUID_807c1e6c_1d00_453f_b920_b61bb7cdd997; rclsid
0x18001e288  call    cs:__imp_CoCreateInstance
0x18001e28e  test    eax, eax
0x18001e290  js      loc_18001E33D
0x18001e296  mov     [rsp+48h+arg_0], 0
0x18001e29f  mov     rax, [r14]
0x18001e2a2  mov     rbx, [rax+18h]
0x18001e2a6  lea     rcx, [rsp+48h+arg_0]
0x18001e2ab  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18001e2b0  lea     r9, [rsp+48h+arg_0]
0x18001e2b5  lea     r8, _GUID_00000114_0000_0000_c000_000000000046
0x18001e2bc  lea     rdx, _GUID_c3852ed5_c926_4cac_98c4_b7afc5d289d6
0x18001e2c3  mov     rcx, r14
0x18001e2c6  mov     rax, rbx
0x18001e2c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2ce  test    eax, eax
0x18001e2d0  js      short loc_18001E333
0x18001e2d2  mov     [rsp+48h+hWnd], 0
0x18001e2db  mov     rcx, [rsp+48h+arg_0]
0x18001e2e0  mov     rax, [rcx]
0x18001e2e3  lea     rdx, [rsp+48h+hWnd]
0x18001e2e8  mov     rax, [rax+18h]
0x18001e2ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2f1  test    eax, eax
0x18001e2f3  js      short loc_18001E333
0x18001e2f5  mov     r8d, 1; hData
0x18001e2fb  lea     rdx, aMicrosoftTipNo; "Microsoft TIP No Insert Option"
0x18001e302  mov     rcx, [rsp+48h+hWnd]; hWnd
0x18001e307  call    cs:__imp_SetPropW
0x18001e30d  mov     rcx, [rdi]
0x18001e310  mov     r9, [rcx]
0x18001e313  lea     rax, [rsi-18h]
0x18001e317  lea     rdx, [rsi+10h]
0x18001e31b  neg     rax
0x18001e31e  sbb     r8, r8
0x18001e321  and     r8, rdx
0x18001e324  mov     rdx, [rsp+48h+hWnd]
0x18001e329  mov     rax, [r9+18h]
0x18001e32d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e332  nop
0x18001e333  lea     rcx, [rsp+48h+arg_0]
0x18001e338  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18001e33d  xor     eax, eax
0x18001e33f  mov     rbx, [rsp+48h+arg_8]
0x18001e344  add     rsp, 30h
0x18001e348  pop     r14
0x18001e34a  pop     rdi
0x18001e34b  pop     rsi
0x18001e34c  retn
```
