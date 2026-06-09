# CViewPositionControllerBase::Invoke(Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::Collections::IMapChangedEventArgs<HSTRING__ *> *)

- ea: `0x1800296f0`
- end: `0x1800298fd`
- name: `?Invoke@CViewPositionControllerBase@@UEAAJPEAU?$IObservableMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEAU?$IMapChangedEventArgs@PEAUHSTRING__@@@345@@Z`
- size: `525`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180007b3c`
- `0x1800296f0`
- `0x180029ccc`
- `0x18002a040`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029721`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800298e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029721`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800298e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002974a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002974a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002976c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002976c`
- `SHCORE!IUnknown_QueryService` at `0x18002982a`
- `SHCORE!IUnknown_QueryService` at `0x18002982a`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CViewPositionControllerBase::Invoke(__int64 a1, __int64 a2, __int64 a3)
{
  HRESULT SourceMonitor; // esi
  __int64 (__fastcall *v6)(__int64, HSTRING *); // rbx
  const WCHAR *StringRawBuffer; // rax
  IUnknown **v8; // r14
  struct IImmersiveMonitor *v9; // rbx
  void *v10; // rdi
  __int64 (__fastcall *v11)(void *, _QWORD, GUID *, __int64 *); // rbx
  __int64 v12; // rdi
  int (__fastcall *v13)(__int64, HSTRING, struct IImmersiveMonitor **); // rbx
  __int64 v15; // [rsp+30h] [rbp-10h] BYREF
  void *ppvOut; // [rsp+38h] [rbp-8h] BYREF
  HSTRING string; // [rsp+80h] [rbp+40h] BYREF
  struct IImmersiveMonitor *v18; // [rsp+88h] [rbp+48h] BYREF

  SourceMonitor = 0;
  if ( a3 )
  {
    string = 0;
    v6 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a3 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    SourceMonitor = v6(a3, &string);
    if ( SourceMonitor >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v8 = (IUnknown **)(a1 - 32);
      if ( CompareStringOrdinal(StringRawBuffer, -1, L"sourceMonitor", -1, 0) == 2 )
      {
        v18 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v18);
        SourceMonitor = CViewPositionControllerBase::_GetSourceMonitor((CViewPositionControllerBase *)(a1 - 32), &v18);
        if ( SourceMonitor >= 0 )
        {
          v9 = v18;
          if ( *(struct IImmersiveMonitor **)(a1 + 64) != v18 )
          {
            if ( v18 )
              (*(void (__fastcall **)(struct IImmersiveMonitor *))(*(_QWORD *)v18 + 8LL))(v18);
            ppvOut = *(void **)(a1 + 64);
            *(_QWORD *)(a1 + 64) = v9;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
          }
          ((void (__fastcall *)(__int64))(*v8)[8].lpVtbl)(a1 - 32);
          ((void (__fastcall *)(__int64))(*v8)[6].lpVtbl)(a1 - 32);
          CViewPositionControllerBase::_SendPositionUpdates((CViewPositionControllerBase *)(a1 - 32));
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v18);
      }
      else
      {
        ppvOut = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
        SourceMonitor = IUnknown_QueryService(
                          v8[2],
                          &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
                          &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
                          &ppvOut);
        if ( SourceMonitor >= 0 )
        {
          v15 = 0;
          v10 = ppvOut;
          v11 = *(__int64 (__fastcall **)(void *, _QWORD, GUID *, __int64 *))(*(_QWORD *)ppvOut + 40LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v15);
          SourceMonitor = v11(v10, *(unsigned int *)(a1 + 72), &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v15);
          if ( SourceMonitor >= 0 )
          {
            v18 = 0;
            v12 = v15;
            v13 = *(int (__fastcall **)(__int64, HSTRING, struct IImmersiveMonitor **))(*(_QWORD *)v15 + 48LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v18);
            if ( v13(v12, string, &v18) >= 0 )
              SourceMonitor = ((__int64 (__fastcall *)(__int64, HSTRING, struct IImmersiveMonitor *))(*v8)[5].lpVtbl)(
                                a1 - 32,
                                string,
                                v18);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v18);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v15);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
      }
    }
    WindowsDeleteString(string);
  }
  return (unsigned int)SourceMonitor;
}

```

## disassembly

```asm
0x1800296f0  mov     [rsp-28h+arg_0], rbx
0x1800296f5  push    rbp
0x1800296f6  push    rsi
0x1800296f7  push    rdi
0x1800296f8  push    r14
0x1800296fa  push    r15
0x1800296fc  mov     rbp, rsp
0x1800296ff  sub     rsp, 40h
0x180029703  mov     rdi, r8
0x180029706  mov     r15, rcx
0x180029709  xor     esi, esi
0x18002970b  test    r8, r8
0x18002970e  jz      loc_1800298EA
0x180029714  mov     [rbp+string], rsi
0x180029718  mov     rax, [r8]
0x18002971b  mov     rbx, [rax+38h]
0x18002971f  xor     ecx, ecx; string
0x180029721  call    cs:__imp_WindowsDeleteString
0x180029727  mov     [rbp+string], rsi
0x18002972b  lea     rdx, [rbp+string]
0x18002972f  mov     rcx, rdi
0x180029732  mov     rax, rbx
0x180029735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002973a  mov     esi, eax
0x18002973c  test    eax, eax
0x18002973e  js      loc_1800298E0
0x180029744  xor     edx, edx; length
0x180029746  mov     rcx, [rbp+string]; string
0x18002974a  call    cs:__imp_WindowsGetStringRawBuffer
0x180029750  lea     r14, [r15-20h]
0x180029754  mov     [rsp+40h+bIgnoreCase], 0; bIgnoreCase
0x18002975c  or      edx, 0FFFFFFFFh; cchCount1
0x18002975f  mov     r9d, edx; cchCount2
0x180029762  lea     r8, String2; "sourceMonitor"
0x180029769  mov     rcx, rax; lpString1
0x18002976c  call    cs:__imp_CompareStringOrdinal
0x180029772  cmp     eax, 2
0x180029775  jnz     loc_180029807
0x18002977b  mov     [rbp+arg_18], 0
0x180029783  lea     rcx, [rbp+arg_18]
0x180029787  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002978c  lea     rdx, [rbp+arg_18]; struct IImmersiveMonitor **
0x180029790  mov     rcx, r14; this
0x180029793  call    ?_GetSourceMonitor@CViewPositionControllerBase@@IEAAJPEAPEAUIImmersiveMonitor@@@Z; CViewPositionControllerBase::_GetSourceMonitor(IImmersiveMonitor * *)
0x180029798  mov     esi, eax
0x18002979a  test    eax, eax
0x18002979c  js      short loc_1800297F9
0x18002979e  mov     rbx, [rbp+arg_18]
0x1800297a2  cmp     [r15+40h], rbx
0x1800297a6  jz      short loc_1800297D2
0x1800297a8  test    rbx, rbx
0x1800297ab  jz      short loc_1800297BD
0x1800297ad  mov     rax, [rbx]
0x1800297b0  mov     rcx, rbx
0x1800297b3  mov     rax, [rax+8]
0x1800297b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297bc  nop
0x1800297bd  mov     rax, [r15+40h]
0x1800297c1  mov     [rbp+ppvOut], rax
0x1800297c5  mov     [r15+40h], rbx
0x1800297c9  lea     rcx, [rbp+ppvOut]
0x1800297cd  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800297d2  mov     rax, [r14]
0x1800297d5  mov     rcx, r14
0x1800297d8  mov     rax, [rax+40h]
0x1800297dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297e1  mov     rax, [r14]
0x1800297e4  mov     rcx, r14
0x1800297e7  mov     rax, [rax+30h]
0x1800297eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297f0  mov     rcx, r14; this
0x1800297f3  call    ?_SendPositionUpdates@CViewPositionControllerBase@@IEAAXXZ; CViewPositionControllerBase::_SendPositionUpdates(void)
0x1800297f8  nop
0x1800297f9  lea     rcx, [rbp+arg_18]
0x1800297fd  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180029802  jmp     loc_1800298E0
0x180029807  mov     [rbp+ppvOut], 0
0x18002980f  lea     rcx, [rbp+ppvOut]
0x180029813  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180029818  lea     r9, [rbp+ppvOut]; ppvOut
0x18002981c  lea     rdx, _GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd; guidService
0x180029823  mov     r8, rdx; riid
0x180029826  mov     rcx, [r14+10h]; punk
0x18002982a  call    cs:__imp_IUnknown_QueryService
0x180029830  mov     esi, eax
0x180029832  test    eax, eax
0x180029834  js      loc_1800298D6
0x18002983a  mov     [rbp+var_10], 0
0x180029842  mov     rdi, [rbp+ppvOut]
0x180029846  mov     rax, [rdi]
0x180029849  mov     rbx, [rax+28h]
0x18002984d  lea     rcx, [rbp+var_10]
0x180029851  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180029856  lea     r9, [rbp+var_10]
0x18002985a  lea     r8, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180029861  mov     edx, [r15+48h]
0x180029865  mov     rcx, rdi
0x180029868  mov     rax, rbx
0x18002986b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029870  mov     esi, eax
0x180029872  test    eax, eax
0x180029874  js      short loc_1800298CC
0x180029876  mov     [rbp+arg_18], 0
0x18002987e  mov     rdi, [rbp+var_10]
0x180029882  mov     rax, [rdi]
0x180029885  mov     rbx, [rax+30h]
0x180029889  lea     rcx, [rbp+arg_18]
0x18002988d  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180029892  lea     r8, [rbp+arg_18]
0x180029896  mov     rdx, [rbp+string]
0x18002989a  mov     rcx, rdi
0x18002989d  mov     rax, rbx
0x1800298a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298a5  test    eax, eax
0x1800298a7  js      short loc_1800298C2
0x1800298a9  mov     rax, [r14]
0x1800298ac  mov     r8, [rbp+arg_18]
0x1800298b0  mov     rdx, [rbp+string]
0x1800298b4  mov     rcx, r14
0x1800298b7  mov     rax, [rax+28h]
0x1800298bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298c0  mov     esi, eax
0x1800298c2  lea     rcx, [rbp+arg_18]
0x1800298c6  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800298cb  nop
0x1800298cc  lea     rcx, [rbp+var_10]
0x1800298d0  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800298d5  nop
0x1800298d6  lea     rcx, [rbp+ppvOut]
0x1800298da  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800298df  nop
0x1800298e0  mov     rcx, [rbp+string]; string
0x1800298e4  call    cs:__imp_WindowsDeleteString
0x1800298ea  mov     eax, esi
0x1800298ec  mov     rbx, [rsp+40h+arg_0]
0x1800298f1  add     rsp, 40h
0x1800298f5  pop     r15
0x1800298f7  pop     r14
0x1800298f9  pop     rdi
0x1800298fa  pop     rsi
0x1800298fb  pop     rbp
0x1800298fc  retn
```
