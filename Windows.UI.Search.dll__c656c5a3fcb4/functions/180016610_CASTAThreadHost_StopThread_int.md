# CASTAThreadHost::StopThread(int)

- ea: `0x180016610`
- end: `0x180016752`
- name: `?StopThread@CASTAThreadHost@@EEAAJH@Z`
- size: `322`
- prototype: `__int64 __fastcall(CASTAThreadHost *__hidden this, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007b3c`
- `0x1800114f4`
- `0x1800164a4`
- `0x180016610`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001662c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001662c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001664c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001664c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001671f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001671f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016739`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016739`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180016672`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180016672`
- `SHCORE!IUnknown_QueryService` at `0x1800166a7`
- `SHCORE!IUnknown_QueryService` at `0x1800166a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CASTAThreadHost::StopThread(RTL_SRWLOCK *this, int a2)
{
  IUnknown **v4; // rax
  unsigned int v5; // ebx
  void *v6; // rdi
  int (__fastcall *v7)(void *, _QWORD, GUID *, __int64 *); // rbx
  DWORD dwindex; // [rsp+60h] [rbp+30h] BYREF
  __int64 v10; // [rsp+70h] [rbp+40h] BYREF
  void *ppvOut; // [rsp+78h] [rbp+48h] BYREF

  AcquireSRWLockExclusive(this + 4);
  if ( this[7].Ptr )
  {
    LOBYTE(this[6].Ptr) |= a2 != 0;
    SetEvent(this[5].Ptr);
    dwindex = 0;
    CoWaitForMultipleHandles(0x1Au, 0xFFFFFFFF, 1u, &this[7].Ptr, &dwindex);
    ppvOut = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
    v4 = (IUnknown **)CWRLObjectWithGITSite::SiteUnk(&this[-9], &v10);
    v5 = (unsigned int)IUnknown_QueryService(
                         *v4,
                         &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
                         &GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd,
                         &ppvOut) >> 31;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v10);
    if ( (unsigned __int8)v5 != 1 )
    {
      v10 = 0;
      v6 = ppvOut;
      v7 = *(int (__fastcall **)(void *, _QWORD, GUID *, __int64 *))(*(_QWORD *)ppvOut + 40LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v10);
      if ( v7(v6, LODWORD(this[11].Ptr), &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v10) >= 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 96LL))(v10);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v10);
    }
    CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&this[7]);
    ResetEvent(this[5].Ptr);
    LODWORD(this[8].Ptr) = -2147467259;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
  }
  ReleaseSRWLockExclusive(this + 4);
  return 0;
}

```

## disassembly

```asm
0x180016610  mov     [rsp-28h+arg_8], rbx
0x180016615  push    rbp
0x180016616  push    rsi
0x180016617  push    rdi
0x180016618  push    r14
0x18001661a  push    r15
0x18001661c  mov     rbp, rsp
0x18001661f  sub     rsp, 30h
0x180016623  mov     ebx, edx
0x180016625  mov     rsi, rcx
0x180016628  add     rcx, 20h ; ' '; SRWLock
0x18001662c  call    cs:__imp_AcquireSRWLockExclusive
0x180016632  lea     r14, [rsi+38h]
0x180016636  cmp     qword ptr [r14], 0
0x18001663a  jz      loc_180016735
0x180016640  test    ebx, ebx
0x180016642  setnz   al
0x180016645  or      [rsi+30h], al
0x180016648  mov     rcx, [rsi+28h]; hEvent
0x18001664c  call    cs:__imp_SetEvent
0x180016652  mov     [rbp+dwindex], 0
0x180016659  lea     rax, [rbp+dwindex]
0x18001665d  mov     [rsp+30h+lpdwindex], rax; lpdwindex
0x180016662  mov     r9, r14; pHandles
0x180016665  mov     r8d, 1; cHandles
0x18001666b  or      edx, 0FFFFFFFFh; dwTimeout
0x18001666e  lea     ecx, [r8+19h]; dwFlags
0x180016672  call    cs:__imp_CoWaitForMultipleHandles
0x180016678  mov     [rbp+ppvOut], 0
0x180016680  lea     rcx, [rbp+ppvOut]
0x180016684  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180016689  lea     rcx, [rsi-48h]
0x18001668d  lea     rdx, [rbp+arg_10]
0x180016691  call    ?SiteUnk@CWRLObjectWithGITSite@@IEAA?AV?$ComPtr@UIUnknown@@@WRL@Microsoft@@XZ; CWRLObjectWithGITSite::SiteUnk(void)
0x180016696  lea     r9, [rbp+ppvOut]; ppvOut
0x18001669a  lea     rdx, _GUID_3b228825_95e7_4ad9_8616_5f94bf6ea1fd; guidService
0x1800166a1  mov     r8, rdx; riid
0x1800166a4  mov     rcx, [rax]; punk
0x1800166a7  call    cs:__imp_IUnknown_QueryService
0x1800166ad  mov     ebx, eax
0x1800166af  shr     ebx, 1Fh
0x1800166b2  lea     rcx, [rbp+arg_10]
0x1800166b6  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800166bb  xor     bl, 1
0x1800166be  jz      short loc_180016713
0x1800166c0  mov     [rbp+arg_10], 0
0x1800166c8  mov     rdi, [rbp+ppvOut]
0x1800166cc  mov     rax, [rdi]
0x1800166cf  mov     rbx, [rax+28h]
0x1800166d3  lea     rcx, [rbp+arg_10]
0x1800166d7  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800166dc  lea     r9, [rbp+arg_10]
0x1800166e0  lea     r8, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x1800166e7  mov     edx, [rsi+58h]
0x1800166ea  mov     rcx, rdi
0x1800166ed  mov     rax, rbx
0x1800166f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166f5  test    eax, eax
0x1800166f7  js      short loc_18001670A
0x1800166f9  mov     rcx, [rbp+arg_10]
0x1800166fd  mov     rax, [rcx]
0x180016700  mov     rax, [rax+60h]
0x180016704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016709  nop
0x18001670a  lea     rcx, [rbp+arg_10]
0x18001670e  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180016713  mov     rcx, r14
0x180016716  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18001671b  mov     rcx, [rsi+28h]; hEvent
0x18001671f  call    cs:__imp_ResetEvent
0x180016725  mov     dword ptr [rsi+40h], 80004005h
0x18001672c  lea     rcx, [rbp+ppvOut]
0x180016730  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180016735  lea     rcx, [rsi+20h]; SRWLock
0x180016739  call    cs:__imp_ReleaseSRWLockExclusive
0x18001673f  xor     eax, eax
0x180016741  mov     rbx, [rsp+30h+arg_8]
0x180016746  add     rsp, 30h
0x18001674a  pop     r15
0x18001674c  pop     r14
0x18001674e  pop     rdi
0x18001674f  pop     rsi
0x180016750  pop     rbp
0x180016751  retn
```
