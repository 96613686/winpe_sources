# CSpellerGlobalState::CreateSpellerInternal(void)

- ea: `0x18026f8a0`
- end: `0x18026f999`
- name: `?CreateSpellerInternal@CSpellerGlobalState@@AEAAXXZ`
- size: `249`
- prototype: `void __fastcall(CSpellerGlobalState *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18026f9a0`

## callees

- `0x180048d5c`
- `0x180123e3c`
- `0x18026f8a0`
- `0x18026faf8`
- `0x180276b74`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18026f8b6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18026f8b6`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18026f983`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18026f983`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18026f939`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18026f939`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18026f958`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18026f958`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x18026f8ed`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x18026f8ed`

## pseudocode

```c
void __fastcall CSpellerGlobalState::CreateSpellerInternal(CSpellerGlobalState *this)
{
  HRESULT v2; // eax
  HRESULT *v3; // rsi
  HRESULT InterfaceAndReleaseStream; // eax
  unsigned int v5; // ebx
  HSTRING CurrentInputMethodLanguageTag; // rax
  IUnknown *Speller; // rax
  IUnknown *v8; // rbx
  LPVOID ppv; // [rsp+30h] [rbp+8h] BYREF

  v2 = CoInitializeEx(0, 0);
  v3 = (HRESULT *)((char *)this + 68);
  *((_DWORD *)this + 17) = v2;
  if ( v2 < 0 )
  {
    LODWORD(ppv) = 4;
    CSpellCheckerTelemetry::LogSpellerBackCoInitStatus<enum TelemetrySpellCheckerBackFailure,long &>(
      &ppv,
      (char *)this + 68);
    CoReleaseMarshalData(*((LPSTREAM *)this + 14));
  }
  else
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(
                                  *((LPSTREAM *)this + 14),
                                  &GUID_8e018a9d_2415_4677_bf08_794ea61f94bb,
                                  &ppv);
    *v3 = InterfaceAndReleaseStream;
    if ( InterfaceAndReleaseStream >= 0 )
    {
      v5 = *((_DWORD *)this + 84);
      CurrentInputMethodLanguageTag = CSpellerGlobalState::GetCurrentInputMethodLanguageTag(this, v5);
      Speller = (IUnknown *)CreateSpeller(
                              (struct ISpellCheckerFactory *)ppv,
                              v5,
                              CurrentInputMethodLanguageTag,
                              *((_BYTE *)this + 340) == 0);
      v8 = Speller;
      if ( Speller )
      {
        *v3 = CoMarshalInterThreadInterfaceInStream(
                &GUID_b6fd0b71_e2bc_4653_8d05_f197e412770b,
                Speller,
                (LPSTREAM *)this + 15);
        ((void (__fastcall *)(IUnknown *))v8->lpVtbl->Release)(v8);
      }
    }
    *((_QWORD *)this + 14) = 0;
    CoUninitialize();
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  }
}

```

## disassembly

```asm
0x18026f8a0  mov     [rsp+arg_8], rbx
0x18026f8a5  mov     [rsp+arg_10], rsi
0x18026f8aa  push    rdi
0x18026f8ab  sub     rsp, 20h
0x18026f8af  mov     rdi, rcx
0x18026f8b2  xor     edx, edx; dwCoInit
0x18026f8b4  xor     ecx, ecx; pvReserved
0x18026f8b6  call    cs:__imp_CoInitializeEx
0x18026f8bc  lea     rsi, [rdi+44h]
0x18026f8c0  mov     [rsi], eax
0x18026f8c2  test    eax, eax
0x18026f8c4  js      loc_18026F96A
0x18026f8ca  lea     rcx, [rsp+28h+ppv]
0x18026f8cf  mov     [rsp+28h+ppv], 0
0x18026f8d8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18026f8dd  mov     rcx, [rdi+70h]; pStm
0x18026f8e1  lea     r8, [rsp+28h+ppv]; ppv
0x18026f8e6  lea     rdx, _GUID_8e018a9d_2415_4677_bf08_794ea61f94bb; iid
0x18026f8ed  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x18026f8f3  mov     [rsi], eax
0x18026f8f5  test    eax, eax
0x18026f8f7  js      short loc_18026F950
0x18026f8f9  mov     ebx, [rdi+150h]
0x18026f8ff  mov     rcx, rdi; this
0x18026f902  mov     edx, ebx; unsigned int
0x18026f904  call    ?GetCurrentInputMethodLanguageTag@CSpellerGlobalState@@AEBAPEAUHSTRING__@@K@Z; CSpellerGlobalState::GetCurrentInputMethodLanguageTag(ulong)
0x18026f909  cmp     byte ptr [rdi+154h], 0
0x18026f910  mov     r8, rax; HSTRING
0x18026f913  mov     rcx, [rsp+28h+ppv]; struct ISpellCheckerFactory *
0x18026f918  mov     edx, ebx; unsigned int
0x18026f91a  setz    r9b; bool
0x18026f91e  call    ?CreateSpeller@@YAPEAUISpellChecker@@PEAUISpellCheckerFactory@@KPEAUHSTRING__@@_N@Z; CreateSpeller(ISpellCheckerFactory *,ulong,HSTRING__ *,bool)
0x18026f923  mov     rbx, rax
0x18026f926  test    rax, rax
0x18026f929  jz      short loc_18026F950
0x18026f92b  lea     r8, [rdi+78h]; ppStm
0x18026f92f  mov     rdx, rax; pUnk
0x18026f932  lea     rcx, _GUID_b6fd0b71_e2bc_4653_8d05_f197e412770b; riid
0x18026f939  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x18026f93f  mov     [rsi], eax
0x18026f941  mov     rcx, [rbx]
0x18026f944  mov     rax, [rcx+10h]
0x18026f948  mov     rcx, rbx
0x18026f94b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026f950  mov     qword ptr [rdi+70h], 0
0x18026f958  call    cs:__imp_CoUninitialize
0x18026f95e  lea     rcx, [rsp+28h+ppv]
0x18026f963  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18026f968  jmp     short loc_18026F989
0x18026f96a  mov     rdx, rsi
0x18026f96d  mov     dword ptr [rsp+28h+ppv], 4
0x18026f975  lea     rcx, [rsp+28h+ppv]
0x18026f97a  call    ??$LogSpellerBackCoInitStatus@W4TelemetrySpellCheckerBackFailure@@AEAJ@CSpellCheckerTelemetry@@SAX$$QEAW4TelemetrySpellCheckerBackFailure@@AEAJ@Z; CSpellCheckerTelemetry::LogSpellerBackCoInitStatus<TelemetrySpellCheckerBackFailure,long &>(TelemetrySpellCheckerBackFailure &&,long &)
0x18026f97f  mov     rcx, [rdi+70h]; pStm
0x18026f983  call    cs:__imp_CoReleaseMarshalData
0x18026f989  mov     rbx, [rsp+28h+arg_8]
0x18026f98e  mov     rsi, [rsp+28h+arg_10]
0x18026f993  add     rsp, 20h
0x18026f997  pop     rdi
0x18026f998  retn
```
