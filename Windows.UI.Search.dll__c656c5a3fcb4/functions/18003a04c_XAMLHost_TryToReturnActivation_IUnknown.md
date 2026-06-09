# XAMLHost_TryToReturnActivation(IUnknown *)

- ea: `0x18003a04c`
- end: `0x18003a0d7`
- name: `?XAMLHost_TryToReturnActivation@@YAXPEAUIUnknown@@@Z`
- size: `139`
- prototype: `void __fastcall(IUnknown *punk)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180027980`
- `0x18002f9ac`

## callees

- `0x180007b3c`
- `0x180014ed0`
- `0x180014f98`
- `0x18003a04c`
- `0x18007b010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x18003a07e`
- `SHCORE!IUnknown_QueryService` at `0x18003a07e`
- `ext-ms-win-com-ole32-l1-1-1!CoAllowSetForegroundWindow` at `0x18003a09f`
- `ext-ms-win-com-ole32-l1-1-1!CoAllowSetForegroundWindow` at `0x18003a09f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall XAMLHost_TryToReturnActivation(IUnknown *punk)
{
  _BYTE v2[40]; // [rsp+20h] [rbp-28h] BYREF
  void *ppvOut; // [rsp+58h] [rbp+10h] BYREF

  ppvOut = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
  if ( IUnknown_QueryService(punk, &IID_IRealmActivationHistory, &GUID_67136e8b_6914_43f0_8f25_05619927d22e, &ppvOut) >= 0 )
  {
    CRPCTimeout::CRPCTimeout((CRPCTimeout *)v2, 0x1388u);
    CoAllowSetForegroundWindow((IUnknown *)ppvOut, 0);
    (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)ppvOut + 24LL))(ppvOut, 0xFFFF);
    CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)v2);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppvOut);
}

```

## disassembly

```asm
0x18003a04c  push    rbx
0x18003a04e  sub     rsp, 40h
0x18003a052  mov     rbx, rcx
0x18003a055  mov     [rsp+48h+ppvOut], 0
0x18003a05e  lea     rcx, [rsp+48h+ppvOut]
0x18003a063  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003a068  lea     r9, [rsp+48h+ppvOut]; ppvOut
0x18003a06d  lea     r8, _GUID_67136e8b_6914_43f0_8f25_05619927d22e; riid
0x18003a074  lea     rdx, IID_IRealmActivationHistory; guidService
0x18003a07b  mov     rcx, rbx; punk
0x18003a07e  call    cs:__imp_IUnknown_QueryService
0x18003a084  test    eax, eax
0x18003a086  js      short loc_18003A0C7
0x18003a088  mov     edx, 1388h; DueTime
0x18003a08d  lea     rcx, [rsp+48h+var_28]; this
0x18003a092  call    ??0CRPCTimeout@@QEAA@K@Z; CRPCTimeout::CRPCTimeout(ulong)
0x18003a097  nop
0x18003a098  xor     edx, edx; lpvReserved
0x18003a09a  mov     rcx, [rsp+48h+ppvOut]; pUnk
0x18003a09f  call    cs:__imp_CoAllowSetForegroundWindow
0x18003a0a5  mov     rcx, [rsp+48h+ppvOut]
0x18003a0aa  mov     rax, [rcx]
0x18003a0ad  mov     edx, 0FFFFh
0x18003a0b2  mov     rax, [rax+18h]
0x18003a0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a0bb  nop
0x18003a0bc  lea     rcx, [rsp+48h+var_28]; this
0x18003a0c1  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x18003a0c6  nop
0x18003a0c7  lea     rcx, [rsp+48h+ppvOut]
0x18003a0cc  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003a0d1  add     rsp, 40h
0x18003a0d5  pop     rbx
0x18003a0d6  retn
```
