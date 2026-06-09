# Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>(uchar,uchar,uchar,uchar,void *,ulong)

- ea: `0x18000637c`
- end: `0x180006630`
- name: `??$Initialize@USecurityPolicyEveryoneLocalAndRemote@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@34@@ServiceModuleBase@Internal@Windows@@QEAAJEEEEPEAXK@Z`
- size: `692`
- prototype: `__int64(LPVOID *, char, __int64, __int64, __int64, ...)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000846c`

## callees

- `0x180005fe0`
- `0x18000637c`
- `0x180006638`
- `0x18000a040`
- `0x18000abc4`
- `0x18000bbb0`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006463`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006588`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006463`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006588`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800063b3`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800063b3`

## string_xrefs

- `0x1800063cd`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18000640d`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18000647a`: `onecore\internal\com\inc\comservicehelper.h`
- `0x1800064d6`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180006531`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18000659f`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180006601`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
__int64 Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote,2,Windows::Internal::DefaultServerDescriptor>(
        LPVOID *a1,
        char a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        ...)
{
  Windows::Internal::ServiceModuleBase *v7; // rbx
  int v8; // eax
  unsigned int v9; // edi
  int v11; // eax
  HRESULT v12; // eax
  int v13; // eax
  int v14; // eax
  HRESULT Instance; // eax
  int v16; // eax
  int ppv; // [rsp+20h] [rbp-68h]
  int ppva; // [rsp+20h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  LPVOID v20; // [rsp+90h] [rbp+8h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h] BYREF

  va_start(va, a5);
  v7 = *(Windows::Internal::ServiceModuleBase **)_lambda_249230bd792972bce8c42ec595a35649_::_lambda_249230bd792972bce8c42ec595a35649_(
                                                   (_lambda_249230bd792972bce8c42ec595a35649_ *)va,
                                                   (struct ConnectedStorageService *)a1);
  v8 = RoInitialize(1);
  v9 = v8;
  *((_DWORD *)a1 + 4) = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)v8,
      ppv);
    Windows::Internal::ServiceModuleBase::Uninitialize(v7);
    return v9;
  }
  if ( a2 )
  {
    v11 = Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote>();
    v9 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v11,
        ppv);
      Windows::Internal::ServiceModuleBase::Uninitialize(v7);
      return v9;
    }
    v20 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    v12 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &v20);
    v9 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v12,
        ppv);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
      Windows::Internal::ServiceModuleBase::Uninitialize(v7);
      return v9;
    }
    v13 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v20 + 24LL))(v20, 1, 2);
    v9 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v13,
        ppv);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
      Windows::Internal::ServiceModuleBase::Uninitialize(v7);
      return v9;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  }
  v14 = (*((__int64 (__fastcall **)(LPVOID *))*a1 + 4))(a1);
  v9 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)v14,
      ppv);
    Windows::Internal::ServiceModuleBase::Uninitialize(v7);
    return v9;
  }
  (*((void (__fastcall **)(LPVOID *))*a1 + 2))(a1);
  *((_BYTE *)a1 + 20) = 1;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 3);
  Instance = CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &GUID_000001da_0000_0000_c000_000000000046, a1 + 3);
  v9 = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)Instance,
      ppva);
    Windows::Internal::ServiceModuleBase::Uninitialize(v7);
    return v9;
  }
  v16 = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), LPVOID *, GUID *))(*(_QWORD *)a1[3] + 24LL))(
          a1[3],
          Windows::Internal::ServiceModuleBase::ConnectCallbackThunk,
          a1,
          &IID_IContextCallback);
  v9 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x90,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)v16,
      5);
    Windows::Internal::ServiceModuleBase::Uninitialize(v7);
    return v9;
  }
  return 0;
}

```

## disassembly

```asm
0x18000637c  mov     rax, rsp
0x18000637f  push    rbx
0x180006380  push    rbp
0x180006381  push    rsi
0x180006382  push    rdi
0x180006383  push    r14
0x180006385  push    r15
0x180006387  sub     rsp, 58h
0x18000638b  mov     bpl, dl
0x18000638e  mov     rsi, rcx
0x180006391  mov     rdx, rcx; struct ConnectedStorageService *
0x180006394  lea     rcx, [rax+30h]; this
0x180006398  call    ??0_lambda_249230bd792972bce8c42ec595a35649_@@QEAA@PEAVConnectedStorageService@@@Z; _lambda_249230bd792972bce8c42ec595a35649_::_lambda_249230bd792972bce8c42ec595a35649_(ConnectedStorageService *)
0x18000639d  mov     rbx, [rax]
0x1800063a0  mov     [rsp+88h+var_48], rbx
0x1800063a5  mov     r15d, 1
0x1800063ab  mov     [rsp+88h+var_40], r15b
0x1800063b0  mov     ecx, r15d
0x1800063b3  call    cs:__imp_RoInitialize
0x1800063b9  mov     edi, eax
0x1800063bb  mov     [rsi+10h], eax
0x1800063be  test    eax, eax
0x1800063c0  jns     short loc_1800063EE
0x1800063c2  mov     rcx, [rsp+88h]; this
0x1800063ca  mov     r9d, eax; char *
0x1800063cd  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x1800063d4  lea     edx, [r15+62h]; void *
0x1800063d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800063dd  nop
0x1800063de  mov     rcx, rbx; this
0x1800063e1  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x1800063e6  nop
0x1800063e7  mov     eax, edi
0x1800063e9  jmp     loc_180006623
0x1800063ee  test    bpl, bpl
0x1800063f1  jz      loc_180006511
0x1800063f7  call    ??$InitializeSecurity@USecurityPolicyEveryoneLocalAndRemote@ServiceModuleBase@Internal@Windows@@@ServiceModuleBase@Internal@Windows@@IEAAJXZ; Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocalAndRemote>(void)
0x1800063fc  mov     edi, eax
0x1800063fe  test    eax, eax
0x180006400  jns     short loc_18000642A
0x180006402  mov     rcx, [rsp+88h]; this
0x18000640a  mov     r9d, eax; char *
0x18000640d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x180006414  mov     edx, 6Ch ; 'l'; void *
0x180006419  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000641e  nop
0x18000641f  mov     rcx, rbx; this
0x180006422  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x180006427  nop
0x180006428  jmp     short loc_1800063E7
0x18000642a  mov     [rsp+88h+arg_0], 0
0x180006436  lea     rcx, [rsp+88h+arg_0]
0x18000643e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180006443  lea     rax, [rsp+88h+arg_0]
0x18000644b  mov     [rsp+88h+ppv], rax; int
0x180006450  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180006457  mov     r8d, r15d; dwClsContext
0x18000645a  xor     edx, edx; pUnkOuter
0x18000645c  lea     rcx, CLSID_GlobalOptions; rclsid
0x180006463  call    cs:__imp_CoCreateInstance
0x180006469  mov     edi, eax
0x18000646b  test    eax, eax
0x18000646d  jns     short loc_1800064A8
0x18000646f  mov     rcx, [rsp+88h]; this
0x180006477  mov     r9d, eax; char *
0x18000647a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x180006481  mov     edx, 73h ; 's'; void *
0x180006486  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000648b  nop
0x18000648c  lea     rcx, [rsp+88h+arg_0]
0x180006494  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180006499  nop
0x18000649a  mov     rcx, rbx; this
0x18000649d  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x1800064a2  nop
0x1800064a3  jmp     loc_1800063E7
0x1800064a8  mov     rcx, [rsp+88h+arg_0]
0x1800064b0  mov     rax, [rcx]
0x1800064b3  mov     r8d, 2
0x1800064b9  mov     edx, r15d
0x1800064bc  mov     rax, [rax+18h]
0x1800064c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064c5  mov     edi, eax
0x1800064c7  test    eax, eax
0x1800064c9  jns     short loc_180006504
0x1800064cb  mov     rcx, [rsp+88h]; this
0x1800064d3  mov     r9d, eax; char *
0x1800064d6  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x1800064dd  mov     edx, 74h ; 't'; void *
0x1800064e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800064e7  nop
0x1800064e8  lea     rcx, [rsp+88h+arg_0]
0x1800064f0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800064f5  nop
0x1800064f6  mov     rcx, rbx; this
0x1800064f9  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x1800064fe  nop
0x1800064ff  jmp     loc_1800063E7
0x180006504  lea     rcx, [rsp+88h+arg_0]
0x18000650c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180006511  mov     rax, [rsi]
0x180006514  mov     rcx, rsi
0x180006517  mov     rax, [rax+20h]
0x18000651b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006520  mov     edi, eax
0x180006522  test    eax, eax
0x180006524  jns     short loc_180006551
0x180006526  mov     rcx, [rsp+88h]; this
0x18000652e  mov     r9d, eax; char *
0x180006531  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x180006538  mov     edx, 7Bh ; '{'; void *
0x18000653d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006542  nop
0x180006543  mov     rcx, rbx; this
0x180006546  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18000654b  nop
0x18000654c  jmp     loc_1800063E7
0x180006551  mov     rax, [rsi]
0x180006554  mov     rcx, rsi
0x180006557  mov     rax, [rax+10h]
0x18000655b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006560  mov     [rsi+14h], r15b
0x180006564  lea     r14, [rsi+18h]
0x180006568  mov     rcx, r14
0x18000656b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180006570  mov     [rsp+88h+ppv], r14; int
0x180006575  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x18000657c  mov     r8d, r15d; dwClsContext
0x18000657f  xor     edx, edx; pUnkOuter
0x180006581  lea     rcx, CLSID_ContextSwitcher; rclsid
0x180006588  call    cs:__imp_CoCreateInstance
0x18000658e  mov     edi, eax
0x180006590  test    eax, eax
0x180006592  jns     short loc_1800065BF
0x180006594  mov     rcx, [rsp+88h]; this
0x18000659c  mov     r9d, eax; char *
0x18000659f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x1800065a6  mov     edx, 8Dh; void *
0x1800065ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800065b0  nop
0x1800065b1  mov     rcx, rbx; this
0x1800065b4  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x1800065b9  nop
0x1800065ba  jmp     loc_1800063E7
0x1800065bf  mov     rcx, [r14]
0x1800065c2  mov     rax, [rcx]
0x1800065c5  mov     [rsp+88h+var_60], 0
0x1800065ce  mov     dword ptr [rsp+88h+ppv], 5; int
0x1800065d6  lea     r9, IID_IContextCallback
0x1800065dd  mov     r8, rsi
0x1800065e0  lea     rdx, ?ConnectCallbackThunk@ServiceModuleBase@Internal@Windows@@SAJPEAUtagComCallData@@@Z; Windows::Internal::ServiceModuleBase::ConnectCallbackThunk(tagComCallData *)
0x1800065e7  mov     rax, [rax+18h]
0x1800065eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065f0  mov     edi, eax
0x1800065f2  test    eax, eax
0x1800065f4  jns     short loc_180006621
0x1800065f6  mov     rcx, [rsp+88h]; this
0x1800065fe  mov     r9d, eax; char *
0x180006601  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x180006608  mov     edx, 90h; void *
0x18000660d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006612  nop
0x180006613  mov     rcx, rbx; this
0x180006616  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18000661b  nop
0x18000661c  jmp     loc_1800063E7
0x180006621  xor     eax, eax
0x180006623  add     rsp, 58h
0x180006627  pop     r15
0x180006629  pop     r14
0x18000662b  pop     rdi
0x18000662c  pop     rsi
0x18000662d  pop     rbp
0x18000662e  pop     rbx
0x18000662f  retn
```
