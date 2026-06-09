# SetSearchViewProperty

- ea: `0x180030f9c`
- end: `0x1800310e8`
- name: `SetSearchViewProperty`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180022a60`

## callees

- `0x180007b3c`
- `0x180030f9c`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003101b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003101b`
- `SHCORE!IUnknown_QueryService` at `0x180030fe1`
- `SHCORE!IUnknown_QueryService` at `0x180030fe1`

## pseudocode

```c
__int64 __fastcall SetSearchViewProperty(__int64 a1, __int64 a2, IUnknown *a3, __int64 a4, __int64 a5)
{
  HRESULT v7; // ebx
  LPVOID v8; // rdi
  __int64 (__fastcall *v9)(LPVOID, GUID *, GUID *, void **); // rbx
  void *v10; // rdi
  __int64 (__fastcall *v11)(void *, _QWORD, GUID *, LPVOID *); // rbx
  _BYTE v13[8]; // [rsp+30h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-18h] BYREF
  void *ppvOut[2]; // [rsp+40h] [rbp-10h] BYREF

  ppvOut[0] = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(ppvOut);
  if ( IUnknown_QueryService(
         a3,
         &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
         &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
         ppvOut) >= 0 )
    goto LABEL_5;
  ppv = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
  v7 = CoCreateInstance(
         &GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239,
         0,
         0x404u,
         &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
         &ppv);
  if ( v7 >= 0 )
  {
    v8 = ppv;
    v9 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, void **))(*(_QWORD *)ppv + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(ppvOut);
    v7 = v9(v8, &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd, &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd, ppvOut);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
  if ( v7 >= 0 )
  {
LABEL_5:
    ppv = 0;
    v10 = ppvOut[0];
    v11 = *(__int64 (__fastcall **)(void *, _QWORD, GUID *, LPVOID *))(*(_QWORD *)ppvOut[0] + 40LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
    v7 = v11(v10, 0, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &ppv);
    if ( v7 >= 0 )
    {
      v13[0] = 0;
      v7 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, _BYTE *))(*(_QWORD *)ppv + 80LL))(ppv, a4, a5, v13);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(ppvOut);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180030f9c  mov     [rsp-18h+arg_0], rbx
0x180030fa1  mov     [rsp-18h+arg_8], rsi
0x180030fa6  push    rbp
0x180030fa7  push    rdi
0x180030fa8  push    r14
0x180030faa  mov     rbp, rsp
0x180030fad  sub     rsp, 50h
0x180030fb1  mov     rsi, r9
0x180030fb4  mov     rbx, r8
0x180030fb7  mov     r14, [rbp+arg_20]
0x180030fbb  mov     [rbp+ppvOut], 0
0x180030fc3  lea     rcx, [rbp+ppvOut]
0x180030fc7  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180030fcc  lea     r9, [rbp+ppvOut]; ppvOut
0x180030fd0  lea     r8, _GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd; riid
0x180030fd7  lea     rdx, _GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd; guidService
0x180030fde  mov     rcx, rbx; punk
0x180030fe1  call    cs:__imp_IUnknown_QueryService
0x180030fe7  test    eax, eax
0x180030fe9  jns     short loc_180031067
0x180030feb  mov     [rbp+var_18], 0
0x180030ff3  lea     rcx, [rbp+var_18]
0x180030ff7  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180030ffc  lea     rax, [rbp+var_18]
0x180031000  mov     [rsp+50h+ppv], rax; ppv
0x180031005  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x18003100c  xor     edx, edx; pUnkOuter
0x18003100e  mov     r8d, 404h; dwClsContext
0x180031014  lea     rcx, _GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239; rclsid
0x18003101b  call    cs:__imp_CoCreateInstance
0x180031021  mov     ebx, eax
0x180031023  test    eax, eax
0x180031025  js      short loc_18003105A
0x180031027  mov     rdi, [rbp+var_18]
0x18003102b  mov     rax, [rdi]
0x18003102e  mov     rbx, [rax+18h]
0x180031032  lea     rcx, [rbp+ppvOut]
0x180031036  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003103b  lea     r9, [rbp+ppvOut]
0x18003103f  lea     r8, _GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd
0x180031046  lea     rdx, _GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd
0x18003104d  mov     rcx, rdi
0x180031050  mov     rax, rbx
0x180031053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031058  mov     ebx, eax
0x18003105a  lea     rcx, [rbp+var_18]
0x18003105e  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180031063  test    ebx, ebx
0x180031065  js      short loc_1800310CA
0x180031067  mov     [rbp+var_18], 0
0x18003106f  mov     rdi, [rbp+ppvOut]
0x180031073  mov     rax, [rdi]
0x180031076  mov     rbx, [rax+28h]
0x18003107a  lea     rcx, [rbp+var_18]
0x18003107e  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180031083  lea     r9, [rbp+var_18]
0x180031087  lea     r8, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18003108e  xor     edx, edx
0x180031090  mov     rcx, rdi
0x180031093  mov     rax, rbx
0x180031096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003109b  mov     ebx, eax
0x18003109d  test    eax, eax
0x18003109f  js      short loc_1800310C1
0x1800310a1  mov     [rbp+var_20], 0
0x1800310a5  mov     rcx, [rbp+var_18]
0x1800310a9  mov     rax, [rcx]
0x1800310ac  lea     r9, [rbp+var_20]
0x1800310b0  mov     r8, r14
0x1800310b3  mov     rdx, rsi
0x1800310b6  mov     rax, [rax+50h]
0x1800310ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800310bf  mov     ebx, eax
0x1800310c1  lea     rcx, [rbp+var_18]
0x1800310c5  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800310ca  lea     rcx, [rbp+ppvOut]
0x1800310ce  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800310d3  mov     eax, ebx
0x1800310d5  mov     rbx, [rsp+50h+arg_0]
0x1800310da  mov     rsi, [rsp+50h+arg_8]
0x1800310df  add     rsp, 50h
0x1800310e3  pop     r14
0x1800310e5  pop     rdi
0x1800310e6  pop     rbp
0x1800310e7  retn
```
