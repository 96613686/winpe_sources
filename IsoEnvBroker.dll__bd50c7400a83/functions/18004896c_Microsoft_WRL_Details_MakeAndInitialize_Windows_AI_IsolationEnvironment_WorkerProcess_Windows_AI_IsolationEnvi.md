# Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::WorkerProcess,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,ulong &,HSTRING__ * &>(Windows::AI::IsolationEnvironment::IIsolationWorkerProcess * *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,ulong &,HSTRING__ * &)

- ea: `0x18004896c`
- end: `0x180048af8`
- name: `??$MakeAndInitialize@VWorkerProcess@IsolationEnvironment@AI@Windows@@UIIsolationWorkerProcess@234@V?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEAKAEAPEAUHSTRING__@@@Details@WRL@Microsoft@@YAJPEAPEAUIIsolationWorkerProcess@IsolationEnvironment@AI@Windows@@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEAKAEAPEAUHSTRING__@@@Z`
- size: `396`
- prototype: `__int64 __fastcall(_QWORD *, void **, int *, HSTRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180049e70`

## callees

- `0x180002a30`
- `0x18004896c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048a5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048a5c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180048a6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180048a6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048a67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048ab4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048a67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048ab4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048a93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048a93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180048aa6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180048aa6`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::WorkerProcess,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,unsigned long &,HSTRING__ * &>(
        _QWORD *a1,
        void **a2,
        int *a3,
        HSTRING *a4)
{
  _QWORD *v7; // r12
  _QWORD *v8; // rax
  _QWORD *v9; // rsi
  HSTRING *v11; // r14
  void **v12; // r15
  HSTRING v13; // rbp
  int v14; // r13d
  void *v15; // rbx
  void *v16; // r12
  DWORD LastError; // edi
  unsigned int v18; // ebx
  char v19; // [rsp+20h] [rbp-58h] BYREF

  v7 = a1;
  *a1 = 0;
  v8 = operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( !v8 )
    return 2147942414LL;
  v8[5] = 1;
  *v8 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::Foundation::IClosable>::`vftable'{for `Windows::AI::IsolationEnvironment::IIsolationWorkerProcess'};
  v8[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::Foundation::IClosable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::Foundation::IClosable>'};
  v8[2] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::Foundation::IClosable>::`vftable'{for `Windows::AI::IsolationEnvironment::IIsolationWorkerProcess's `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::Foundation::IClosable>'};
  v8[3] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::Foundation::IClosable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *v9 = &Windows::AI::IsolationEnvironment::WorkerProcess::`vftable'{for `Windows::AI::IsolationEnvironment::IIsolationWorkerProcess'};
  v9[1] = &Windows::AI::IsolationEnvironment::WorkerProcess::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::Foundation::IClosable>'};
  v9[2] = &Windows::AI::IsolationEnvironment::WorkerProcess::`vftable'{for `Windows::AI::IsolationEnvironment::IIsolationWorkerProcess's `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::Foundation::IClosable>'};
  v9[3] = &Windows::AI::IsolationEnvironment::WorkerProcess::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'};
  v11 = (HSTRING *)(v9 + 6);
  v9[6] = 0;
  v12 = (void **)(v9 + 8);
  v9[8] = 0;
  v13 = *a4;
  v14 = *a3;
  v15 = *a2;
  *a2 = 0;
  if ( v9 + 8 != (_QWORD *)&v19 )
  {
    v16 = *v12;
    if ( *v12 )
    {
      LastError = GetLastError();
      CloseHandle(v16);
      SetLastError(LastError);
    }
    *v12 = v15;
    v15 = 0;
    v7 = a1;
  }
  *((_DWORD *)v9 + 14) = v14;
  if ( !v13 || v13 != *v11 )
  {
    WindowsDeleteString(*v11);
    *v11 = 0;
    WindowsDuplicateString(v13, (HSTRING *)v9 + 6);
  }
  if ( v15 )
    CloseHandle(v15);
  v18 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD *))*v9)(v9, &GUID_fd85241e_2273_51b7_bc6c_39b7497b6b56, v7);
  (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
  return v18;
}

```

## disassembly

```asm
0x18004896c  mov     [rsp+arg_0], rcx
0x180048971  push    rbx
0x180048972  push    rbp
0x180048973  push    rsi
0x180048974  push    rdi
0x180048975  push    r12
0x180048977  push    r13
0x180048979  push    r14
0x18004897b  push    r15
0x18004897d  sub     rsp, 38h
0x180048981  mov     rbp, r9
0x180048984  mov     r13, r8
0x180048987  mov     rdi, rdx
0x18004898a  mov     r12, rcx
0x18004898d  xor     ebx, ebx
0x18004898f  mov     [rcx], rbx
0x180048992  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180048999  lea     ecx, [rbx+48h]; unsigned __int64
0x18004899c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800489a1  mov     rsi, rax
0x1800489a4  test    rax, rax
0x1800489a7  jnz     short loc_1800489B3
0x1800489a9  mov     eax, 8007000Eh
0x1800489ae  jmp     loc_180048AE7
0x1800489b3  mov     qword ptr [rax+28h], 1
0x1800489bb  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIsolationWorkerProcess@IsolationEnvironment@AI@Windows@@U4567@UIClosable@Foundation@7@@WRL@Microsoft@@6BIIsolationWorkerProcess@IsolationEnvironment@AI@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::Foundation::IClosable>::`vftable'{for `Windows::AI::IsolationEnvironment::IIsolationWorkerProcess'}
0x1800489c2  mov     [rsi], rax
0x1800489c5  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIsolationWorkerProcess@IsolationEnvironment@AI@Windows@@U4567@UIClosable@Foundation@7@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIIsolationWorkerProcess@IsolationEnvironment@AI@Windows@@UIClosable@Foundation@8@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::Foundation::IClosable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::Foundation::IClosable>'}
0x1800489cc  mov     [rsi+8], rax
0x1800489d0  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIsolationWorkerProcess@IsolationEnvironment@AI@Windows@@U4567@UIClosable@Foundation@7@@WRL@Microsoft@@6BIIsolationWorkerProcess@IsolationEnvironment@AI@Windows@@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIIsolationWorkerProcess@IsolationEnvironment@AI@Windows@@UIClosable@Foundation@8@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::Foundation::IClosable>::`vftable'{for `Windows::AI::IsolationEnvironment::IIsolationWorkerProcess's `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::Foundation::IClosable>'}
0x1800489d7  mov     [rsi+10h], rax
0x1800489db  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIsolationWorkerProcess@IsolationEnvironment@AI@Windows@@U4567@UIClosable@Foundation@7@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::Foundation::IClosable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'}
0x1800489e2  mov     [rsi+18h], rax
0x1800489e6  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800489ed  test    rcx, rcx
0x1800489f0  jz      short loc_1800489FF
0x1800489f2  mov     rax, [rcx]
0x1800489f5  mov     rax, [rax+8]
0x1800489f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489fe  nop
0x1800489ff  lea     rax, ??_7WorkerProcess@IsolationEnvironment@AI@Windows@@6BIIsolationWorkerProcess@123@@; const Windows::AI::IsolationEnvironment::WorkerProcess::`vftable'{for `Windows::AI::IsolationEnvironment::IIsolationWorkerProcess'}
0x180048a06  mov     [rsi], rax
0x180048a09  lea     rax, ??_7WorkerProcess@IsolationEnvironment@AI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIIsolationWorkerProcess@IsolationEnvironment@AI@Windows@@UIClosable@Foundation@8@@Details@WRL@Microsoft@@@; const Windows::AI::IsolationEnvironment::WorkerProcess::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::Foundation::IClosable>'}
0x180048a10  mov     [rsi+8], rax
0x180048a14  lea     rax, ??_7WorkerProcess@IsolationEnvironment@AI@Windows@@6BIIsolationWorkerProcess@123@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIIsolationWorkerProcess@IsolationEnvironment@AI@Windows@@UIClosable@Foundation@8@@Details@WRL@Microsoft@@@; const Windows::AI::IsolationEnvironment::WorkerProcess::`vftable'{for `Windows::AI::IsolationEnvironment::IIsolationWorkerProcess's `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,Windows::Foundation::IClosable>'}
0x180048a1b  mov     [rsi+10h], rax
0x180048a1f  lea     rax, ??_7WorkerProcess@IsolationEnvironment@AI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@@Details@WRL@Microsoft@@@; const Windows::AI::IsolationEnvironment::WorkerProcess::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'}
0x180048a26  mov     [rsi+18h], rax
0x180048a2a  lea     r14, [rsi+30h]
0x180048a2e  mov     [r14], rbx
0x180048a31  lea     r15, [rsi+40h]
0x180048a35  mov     [r15], rbx
0x180048a38  mov     rbp, [rbp+0]
0x180048a3c  mov     r13d, [r13+0]
0x180048a40  mov     rbx, [rdi]
0x180048a43  mov     qword ptr [rdi], 0
0x180048a4a  lea     rax, [rsp+78h+var_58]
0x180048a4f  cmp     r15, rax
0x180048a52  jz      short loc_180048A82
0x180048a54  mov     r12, [r15]
0x180048a57  test    r12, r12
0x180048a5a  jz      short loc_180048A75
0x180048a5c  call    cs:__imp_GetLastError
0x180048a62  mov     edi, eax
0x180048a64  mov     rcx, r12; hObject
0x180048a67  call    cs:__imp_CloseHandle
0x180048a6d  mov     ecx, edi; dwErrCode
0x180048a6f  call    cs:__imp_SetLastError
0x180048a75  mov     [r15], rbx
0x180048a78  xor     ebx, ebx
0x180048a7a  mov     r12, [rsp+78h+arg_0]
0x180048a82  mov     [rsi+38h], r13d
0x180048a86  test    rbp, rbp
0x180048a89  jz      short loc_180048A90
0x180048a8b  cmp     rbp, [r14]
0x180048a8e  jz      short loc_180048AAC
0x180048a90  mov     rcx, [r14]; string
0x180048a93  call    cs:__imp_WindowsDeleteString
0x180048a99  mov     qword ptr [r14], 0
0x180048aa0  mov     rdx, r14; newString
0x180048aa3  mov     rcx, rbp; string
0x180048aa6  call    cs:__imp_WindowsDuplicateString
0x180048aac  test    rbx, rbx
0x180048aaf  jz      short loc_180048ABB
0x180048ab1  mov     rcx, rbx; hObject
0x180048ab4  call    cs:__imp_CloseHandle
0x180048aba  nop
0x180048abb  mov     rax, [rsi]
0x180048abe  mov     r8, r12
0x180048ac1  lea     rdx, _GUID_fd85241e_2273_51b7_bc6c_39b7497b6b56
0x180048ac8  mov     rcx, rsi
0x180048acb  mov     rax, [rax]
0x180048ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ad3  mov     ebx, eax
0x180048ad5  mov     rcx, [rsi]
0x180048ad8  mov     rax, [rcx+10h]
0x180048adc  mov     rcx, rsi
0x180048adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ae4  nop
0x180048ae5  mov     eax, ebx
0x180048ae7  add     rsp, 38h
0x180048aeb  pop     r15
0x180048aed  pop     r14
0x180048aef  pop     r13
0x180048af1  pop     r12
0x180048af3  pop     rdi
0x180048af4  pop     rsi
0x180048af5  pop     rbp
0x180048af6  pop     rbx
0x180048af7  retn
```
