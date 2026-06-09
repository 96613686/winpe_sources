# CASTAThreadHost::s_ASTAThreadHostStartThreadProc(void *)

- ea: `0x180016760`
- end: `0x18001691c`
- name: `?s_ASTAThreadHostStartThreadProc@CASTAThreadHost@@CAKPEAX@Z`
- size: `444`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180007b3c`
- `0x180010fd0`
- `0x18001285c`
- `0x1800160d4`
- `0x180016760`
- `0x18002a9dc`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016783`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016783`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800168ab`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800168ab`
- `SHCORE!IUnknown_SetSite` at `0x1800168f8`
- `SHCORE!IUnknown_SetSite` at `0x1800168f8`
- `USER32!__imp_EnableMouseInPointerForThread` at `0x1800167aa`
- `USER32!__imp_EnableMouseInPointerForThread` at `0x1800167aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CASTAThreadHost::s_ASTAThreadHostStartThreadProc(char *Parameter)
{
  unsigned int *v2; // rdi
  unsigned int v3; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v5; // rcx
  int AgileReference; // ebx
  char *v7; // r14
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v9)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v10; // rdi
  char **v11; // rax
  char **v12; // rbx
  __int64 v14; // [rsp+50h] [rbp+30h] BYREF
  char *v15; // [rsp+58h] [rbp+38h] BYREF
  __int64 v16; // [rsp+60h] [rbp+40h] BYREF

  v2 = (unsigned int *)(Parameter + 160);
  if ( (Microsoft_Windows_UI_SearchEnableBits & 1) != 0 )
  {
    v3 = *v2;
    CurrentThreadId = GetCurrentThreadId();
    McTemplateU0qq_EventWriteTransfer(v5, ASTAThread_Start, CurrentThreadId, v3);
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)Parameter + 8LL))(Parameter);
  if ( (unsigned int)EnableMouseInPointerForThread()
    || (AgileReference = ResultFromKnownLastError(), AgileReference >= 0) )
  {
    v7 = Parameter + 152;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(Parameter + 152);
    LODWORD(v14) = *v2;
    v16 = *((_QWORD *)Parameter + 12);
    *((_QWORD *)Parameter + 19) = 0;
    v15 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v15);
    AgileReference = Microsoft::WRL::Details::MakeAndInitialize<CXAMLHostWindow,IServiceProvider,IViewDefinition * &,enum SearchView &>(
                       &v15,
                       &v16,
                       (unsigned int *)&v14);
    if ( AgileReference >= 0 )
      AgileReference = (**(__int64 (__fastcall ***)(char *, GUID *, char *))v15)(
                         v15,
                         &GUID_662a21f0_4ad5_4fcf_b790_7b83d7d9ee2f,
                         Parameter + 152);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v15);
    if ( AgileReference >= 0 )
    {
      v14 = 0;
      v8 = *(__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))v7;
      v9 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v7;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v14);
      AgileReference = v9(v8, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &v14);
      if ( AgileReference >= 0 )
      {
        v10 = v14;
        v15 = Parameter + 144;
        v11 = (char **)Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(&v15);
        v12 = v11;
        if ( v10 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(v11);
          AgileReference = RoGetAgileReference(0, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, v10, v12);
          if ( AgileReference < 0 )
            goto LABEL_14;
        }
        else
        {
          v16 = 0;
          v15 = *v11;
          *v11 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v15);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v16);
        }
        AgileReference = IUnknown_SetSite(
                           *((IUnknown **)Parameter + 19),
                           (IUnknown *)((unsigned __int64)(Parameter + 80)
                                      & ((unsigned __int128)-(__int128)(unsigned __int64)Parameter >> 64)));
      }
LABEL_14:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v14);
    }
  }
  *((_DWORD *)Parameter + 34) = AgileReference;
  return 0;
}

```

## disassembly

```asm
0x180016760  push    rbp
0x180016762  push    rbx
0x180016763  push    rsi
0x180016764  push    rdi
0x180016765  push    r14
0x180016767  mov     rbp, rsp
0x18001676a  sub     rsp, 20h
0x18001676e  mov     rsi, rcx
0x180016771  lea     rdi, [rcx+0A0h]
0x180016778  test    byte ptr cs:Microsoft_Windows_UI_SearchEnableBits, 1
0x18001677f  jz      short loc_18001679B
0x180016781  mov     ebx, [rdi]
0x180016783  call    cs:__imp_GetCurrentThreadId
0x180016789  mov     r9d, ebx
0x18001678c  mov     r8d, eax
0x18001678f  lea     rdx, ASTAThread_Start
0x180016796  call    McTemplateU0qq_EventWriteTransfer
0x18001679b  mov     rax, [rsi]
0x18001679e  mov     rcx, rsi
0x1800167a1  mov     rax, [rax+8]
0x1800167a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167aa  call    cs:__imp_EnableMouseInPointerForThread
0x1800167b0  test    eax, eax
0x1800167b2  jnz     short loc_1800167C3
0x1800167b4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800167b9  mov     ebx, eax
0x1800167bb  test    eax, eax
0x1800167bd  js      loc_180016909
0x1800167c3  lea     r14, [rsi+98h]
0x1800167ca  mov     rcx, r14
0x1800167cd  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800167d2  mov     eax, [rdi]
0x1800167d4  mov     dword ptr [rbp+arg_0], eax
0x1800167d7  mov     rax, [rsi+60h]
0x1800167db  mov     [rbp+arg_10], rax
0x1800167df  mov     qword ptr [r14], 0
0x1800167e6  mov     [rbp+arg_8], 0
0x1800167ee  lea     rcx, [rbp+arg_8]
0x1800167f2  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800167f7  lea     r8, [rbp+arg_0]
0x1800167fb  lea     rdx, [rbp+arg_10]
0x1800167ff  lea     rcx, [rbp+arg_8]
0x180016803  call    ??$MakeAndInitialize@VCXAMLHostWindow@@UIServiceProvider@@AEAPEAUIViewDefinition@@AEAW4SearchView@@@Details@WRL@Microsoft@@YAJPEAPEAUIServiceProvider@@AEAPEAUIViewDefinition@@AEAW4SearchView@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CXAMLHostWindow,IServiceProvider,IViewDefinition * &,SearchView &>(IServiceProvider * *,IViewDefinition * &,SearchView &)
0x180016808  mov     ebx, eax
0x18001680a  test    eax, eax
0x18001680c  js      short loc_180016829
0x18001680e  mov     rcx, [rbp+arg_8]
0x180016812  mov     rax, [rcx]
0x180016815  mov     r8, r14
0x180016818  lea     rdx, _GUID_662a21f0_4ad5_4fcf_b790_7b83d7d9ee2f
0x18001681f  mov     rax, [rax]
0x180016822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016827  mov     ebx, eax
0x180016829  lea     rcx, [rbp+arg_8]
0x18001682d  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180016832  test    ebx, ebx
0x180016834  js      loc_180016909
0x18001683a  mov     [rbp+arg_0], 0
0x180016842  mov     rdi, [r14]
0x180016845  mov     rax, [rdi]
0x180016848  mov     rbx, [rax]
0x18001684b  lea     rcx, [rbp+arg_0]
0x18001684f  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180016854  lea     r8, [rbp+arg_0]
0x180016858  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x18001685f  mov     rcx, rdi
0x180016862  mov     rax, rbx
0x180016865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001686a  mov     ebx, eax
0x18001686c  test    eax, eax
0x18001686e  js      loc_180016900
0x180016874  mov     rdi, [rbp+arg_0]
0x180016878  lea     rax, [rsi+90h]
0x18001687f  mov     [rbp+arg_8], rax
0x180016883  lea     rcx, [rbp+arg_8]
0x180016887  call    ??B?$ComPtrRef@VAgileRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVAgileRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(void)
0x18001688c  mov     rbx, rax
0x18001688f  test    rdi, rdi
0x180016892  jz      short loc_1800168B9
0x180016894  mov     rcx, rax
0x180016897  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18001689c  mov     r9, rbx
0x18001689f  mov     r8, rdi
0x1800168a2  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x1800168a9  xor     ecx, ecx
0x1800168ab  call    cs:__imp_RoGetAgileReference
0x1800168b1  mov     ebx, eax
0x1800168b3  test    eax, eax
0x1800168b5  jns     short loc_1800168E1
0x1800168b7  jmp     short loc_180016900
0x1800168b9  mov     [rbp+arg_10], 0
0x1800168c1  mov     rax, [rax]
0x1800168c4  mov     [rbp+arg_8], rax
0x1800168c8  mov     qword ptr [rbx], 0
0x1800168cf  lea     rcx, [rbp+arg_8]
0x1800168d3  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800168d8  lea     rcx, [rbp+arg_10]
0x1800168dc  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x1800168e1  mov     rax, rsi
0x1800168e4  lea     rcx, [rsi+50h]
0x1800168e8  neg     rax
0x1800168eb  sbb     rdx, rdx
0x1800168ee  and     rdx, rcx; punkSite
0x1800168f1  mov     rcx, [rsi+98h]; punk
0x1800168f8  call    cs:__imp_IUnknown_SetSite
0x1800168fe  mov     ebx, eax
0x180016900  lea     rcx, [rbp+arg_0]
0x180016904  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180016909  mov     [rsi+88h], ebx
0x18001690f  xor     eax, eax
0x180016911  add     rsp, 20h
0x180016915  pop     r14
0x180016917  pop     rdi
0x180016918  pop     rsi
0x180016919  pop     rbx
0x18001691a  pop     rbp
0x18001691b  retn
```
