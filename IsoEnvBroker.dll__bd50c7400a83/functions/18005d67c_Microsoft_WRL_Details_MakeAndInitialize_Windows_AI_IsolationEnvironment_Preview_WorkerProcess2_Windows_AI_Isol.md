# Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::Preview::WorkerProcess2,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,ulong &,HSTRING__ * &>(Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2 * *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,ulong &,HSTRING__ * &)

- ea: `0x18005d67c`
- end: `0x18005d808`
- name: `??$MakeAndInitialize@VWorkerProcess2@Preview@IsolationEnvironment@AI@Windows@@UIIsolationWorkerProcess_Exp2@2345@V?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEAKAEAPEAUHSTRING__@@@Details@WRL@Microsoft@@YAJPEAPEAUIIsolationWorkerProcess_Exp2@Preview@IsolationEnvironment@AI@Windows@@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEAKAEAPEAUHSTRING__@@@Z`
- size: `396`
- prototype: `__int64 __fastcall(_QWORD *, void **, int *, HSTRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005e6a0`

## callees

- `0x180002a30`
- `0x18005d67c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d76c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d76c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d77f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d77f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d777`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d7c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d777`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d7c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d7a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d7a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18005d7b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18005d7b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::Preview::WorkerProcess2,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,unsigned long &,HSTRING__ * &>(
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
  *v8 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::Foundation::IClosable>::`vftable'{for `Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2'};
  v8[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::Foundation::IClosable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::Foundation::IClosable>'};
  v8[2] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::Foundation::IClosable>::`vftable'{for `Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2's `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::Foundation::IClosable>'};
  v8[3] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::Foundation::IClosable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *v9 = &Windows::AI::IsolationEnvironment::Preview::WorkerProcess2::`vftable'{for `Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2'};
  v9[1] = &Windows::AI::IsolationEnvironment::Preview::WorkerProcess2::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::Foundation::IClosable>'};
  v9[2] = &Windows::AI::IsolationEnvironment::Preview::WorkerProcess2::`vftable'{for `Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2's `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::Foundation::IClosable>'};
  v9[3] = &Windows::AI::IsolationEnvironment::Preview::WorkerProcess2::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'};
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
  v18 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD *))*v9)(v9, &GUID_ef1b5446_c26d_51da_891e_499df0a9eb5f, v7);
  (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
  return v18;
}

```

## disassembly

```asm
0x18005d67c  mov     [rsp+arg_0], rcx
0x18005d681  push    rbx
0x18005d682  push    rbp
0x18005d683  push    rsi
0x18005d684  push    rdi
0x18005d685  push    r12
0x18005d687  push    r13
0x18005d689  push    r14
0x18005d68b  push    r15
0x18005d68d  sub     rsp, 38h
0x18005d691  mov     rbp, r9
0x18005d694  mov     r13, r8
0x18005d697  mov     rdi, rdx
0x18005d69a  mov     r12, rcx
0x18005d69d  xor     ebx, ebx
0x18005d69f  mov     [rcx], rbx
0x18005d6a2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005d6a9  lea     ecx, [rbx+48h]; unsigned __int64
0x18005d6ac  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005d6b1  mov     rsi, rax
0x18005d6b4  test    rax, rax
0x18005d6b7  jnz     short loc_18005D6C3
0x18005d6b9  mov     eax, 8007000Eh
0x18005d6be  jmp     loc_18005D7F7
0x18005d6c3  mov     qword ptr [rax+28h], 1
0x18005d6cb  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIsolationWorkerProcess_Exp2@Preview@IsolationEnvironment@AI@Windows@@U45678@UIClosable@Foundation@8@@WRL@Microsoft@@6BIIsolationWorkerProcess_Exp2@Preview@IsolationEnvironment@AI@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::Foundation::IClosable>::`vftable'{for `Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2'}
0x18005d6d2  mov     [rsi], rax
0x18005d6d5  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIsolationWorkerProcess_Exp2@Preview@IsolationEnvironment@AI@Windows@@U45678@UIClosable@Foundation@8@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIIsolationWorkerProcess_Exp2@Preview@IsolationEnvironment@AI@Windows@@UIClosable@Foundation@9@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::Foundation::IClosable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::Foundation::IClosable>'}
0x18005d6dc  mov     [rsi+8], rax
0x18005d6e0  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIsolationWorkerProcess_Exp2@Preview@IsolationEnvironment@AI@Windows@@U45678@UIClosable@Foundation@8@@WRL@Microsoft@@6BIIsolationWorkerProcess_Exp2@Preview@IsolationEnvironment@AI@Windows@@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIIsolationWorkerProcess_Exp2@Preview@IsolationEnvironment@AI@Windows@@UIClosable@Foundation@9@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::Foundation::IClosable>::`vftable'{for `Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2's `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::Foundation::IClosable>'}
0x18005d6e7  mov     [rsi+10h], rax
0x18005d6eb  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIsolationWorkerProcess_Exp2@Preview@IsolationEnvironment@AI@Windows@@U45678@UIClosable@Foundation@8@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::Foundation::IClosable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'}
0x18005d6f2  mov     [rsi+18h], rax
0x18005d6f6  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18005d6fd  test    rcx, rcx
0x18005d700  jz      short loc_18005D70F
0x18005d702  mov     rax, [rcx]
0x18005d705  mov     rax, [rax+8]
0x18005d709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d70e  nop
0x18005d70f  lea     rax, ??_7WorkerProcess2@Preview@IsolationEnvironment@AI@Windows@@6BIIsolationWorkerProcess_Exp2@1234@@; const Windows::AI::IsolationEnvironment::Preview::WorkerProcess2::`vftable'{for `Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2'}
0x18005d716  mov     [rsi], rax
0x18005d719  lea     rax, ??_7WorkerProcess2@Preview@IsolationEnvironment@AI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIIsolationWorkerProcess_Exp2@Preview@IsolationEnvironment@AI@Windows@@UIClosable@Foundation@9@@Details@WRL@Microsoft@@@; const Windows::AI::IsolationEnvironment::Preview::WorkerProcess2::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::Foundation::IClosable>'}
0x18005d720  mov     [rsi+8], rax
0x18005d724  lea     rax, ??_7WorkerProcess2@Preview@IsolationEnvironment@AI@Windows@@6BIIsolationWorkerProcess_Exp2@1234@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIIsolationWorkerProcess_Exp2@Preview@IsolationEnvironment@AI@Windows@@UIClosable@Foundation@9@@Details@WRL@Microsoft@@@; const Windows::AI::IsolationEnvironment::Preview::WorkerProcess2::`vftable'{for `Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2's `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,Windows::Foundation::IClosable>'}
0x18005d72b  mov     [rsi+10h], rax
0x18005d72f  lea     rax, ??_7WorkerProcess2@Preview@IsolationEnvironment@AI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@@Details@WRL@Microsoft@@@; const Windows::AI::IsolationEnvironment::Preview::WorkerProcess2::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'}
0x18005d736  mov     [rsi+18h], rax
0x18005d73a  lea     r14, [rsi+30h]
0x18005d73e  mov     [r14], rbx
0x18005d741  lea     r15, [rsi+40h]
0x18005d745  mov     [r15], rbx
0x18005d748  mov     rbp, [rbp+0]
0x18005d74c  mov     r13d, [r13+0]
0x18005d750  mov     rbx, [rdi]
0x18005d753  mov     qword ptr [rdi], 0
0x18005d75a  lea     rax, [rsp+78h+var_58]
0x18005d75f  cmp     r15, rax
0x18005d762  jz      short loc_18005D792
0x18005d764  mov     r12, [r15]
0x18005d767  test    r12, r12
0x18005d76a  jz      short loc_18005D785
0x18005d76c  call    cs:__imp_GetLastError
0x18005d772  mov     edi, eax
0x18005d774  mov     rcx, r12; hObject
0x18005d777  call    cs:__imp_CloseHandle
0x18005d77d  mov     ecx, edi; dwErrCode
0x18005d77f  call    cs:__imp_SetLastError
0x18005d785  mov     [r15], rbx
0x18005d788  xor     ebx, ebx
0x18005d78a  mov     r12, [rsp+78h+arg_0]
0x18005d792  mov     [rsi+38h], r13d
0x18005d796  test    rbp, rbp
0x18005d799  jz      short loc_18005D7A0
0x18005d79b  cmp     rbp, [r14]
0x18005d79e  jz      short loc_18005D7BC
0x18005d7a0  mov     rcx, [r14]; string
0x18005d7a3  call    cs:__imp_WindowsDeleteString
0x18005d7a9  mov     qword ptr [r14], 0
0x18005d7b0  mov     rdx, r14; newString
0x18005d7b3  mov     rcx, rbp; string
0x18005d7b6  call    cs:__imp_WindowsDuplicateString
0x18005d7bc  test    rbx, rbx
0x18005d7bf  jz      short loc_18005D7CB
0x18005d7c1  mov     rcx, rbx; hObject
0x18005d7c4  call    cs:__imp_CloseHandle
0x18005d7ca  nop
0x18005d7cb  mov     rax, [rsi]
0x18005d7ce  mov     r8, r12
0x18005d7d1  lea     rdx, _GUID_ef1b5446_c26d_51da_891e_499df0a9eb5f
0x18005d7d8  mov     rcx, rsi
0x18005d7db  mov     rax, [rax]
0x18005d7de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d7e3  mov     ebx, eax
0x18005d7e5  mov     rcx, [rsi]
0x18005d7e8  mov     rax, [rcx+10h]
0x18005d7ec  mov     rcx, rsi
0x18005d7ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d7f4  nop
0x18005d7f5  mov     eax, ebx
0x18005d7f7  add     rsp, 38h
0x18005d7fb  pop     r15
0x18005d7fd  pop     r14
0x18005d7ff  pop     r13
0x18005d801  pop     r12
0x18005d803  pop     rdi
0x18005d804  pop     rsi
0x18005d805  pop     rbp
0x18005d806  pop     rbx
0x18005d807  retn
```
