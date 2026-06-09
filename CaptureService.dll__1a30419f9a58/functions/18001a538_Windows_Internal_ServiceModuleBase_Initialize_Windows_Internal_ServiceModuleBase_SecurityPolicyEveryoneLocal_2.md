# Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(uchar,uchar,uchar,uchar,void *,ulong)

- ea: `0x18001a538`
- end: `0x18001a7d9`
- name: `??$Initialize@USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@34@@ServiceModuleBase@Internal@Windows@@QEAAJEEEEPEAXK@Z`
- size: `673`
- prototype: `__int64(__int64, char, __int64, __int64, __int64, ...)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001adc0`

## callees

- `0x180003edc`
- `0x180007630`
- `0x18000907c`
- `0x18001a538`
- `0x18001a7e0`
- `0x18001b870`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a61f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a731`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a61f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a731`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18001a56f`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18001a56f`

## string_xrefs

- `0x18001a589`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18001a5c9`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18001a636`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18001a692`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18001a6ed`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18001a748`: `onecore\internal\com\inc\comservicehelper.h`
- `0x18001a7aa`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(
        __int64 a1,
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
  v7 = (Windows::Internal::ServiceModuleBase *)*wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                                  (__int64 *)va,
                                                  a1);
  v8 = RoInitialize(1);
  v9 = v8;
  *(_DWORD *)(a1 + 16) = v8;
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
    v11 = Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal>();
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
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
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
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
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
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
      Windows::Internal::ServiceModuleBase::Uninitialize(v7);
      return v9;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  }
  v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
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
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 24);
  Instance = CoCreateInstance(
               &CLSID_ContextSwitcher,
               0,
               1u,
               &GUID_000001da_0000_0000_c000_000000000046,
               (LPVOID *)(a1 + 24));
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
  v16 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(struct tagComCallData *), __int64, GUID *))(**(_QWORD **)(a1 + 24) + 24LL))(
          *(_QWORD *)(a1 + 24),
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
0x18001a538  mov     rax, rsp
0x18001a53b  push    rbx
0x18001a53c  push    rbp
0x18001a53d  push    rsi
0x18001a53e  push    rdi
0x18001a53f  push    r14
0x18001a541  push    r15
0x18001a543  sub     rsp, 58h
0x18001a547  mov     bpl, dl
0x18001a54a  mov     rsi, rcx
0x18001a54d  mov     rdx, rcx
0x18001a550  lea     rcx, [rax+30h]
0x18001a554  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18001a559  mov     rbx, [rax]
0x18001a55c  mov     [rsp+88h+var_48], rbx
0x18001a561  mov     r15d, 1
0x18001a567  mov     [rsp+88h+var_40], r15b
0x18001a56c  mov     ecx, r15d
0x18001a56f  call    cs:__imp_RoInitialize
0x18001a575  mov     edi, eax
0x18001a577  mov     [rsi+10h], eax
0x18001a57a  test    eax, eax
0x18001a57c  jns     short loc_18001A5AA
0x18001a57e  mov     rcx, [rsp+88h]; this
0x18001a586  mov     r9d, eax; char *
0x18001a589  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18001a590  lea     edx, [r15+62h]; void *
0x18001a594  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a599  nop
0x18001a59a  mov     rcx, rbx; this
0x18001a59d  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18001a5a2  nop
0x18001a5a3  mov     eax, edi
0x18001a5a5  jmp     loc_18001A7CC
0x18001a5aa  test    bpl, bpl
0x18001a5ad  jz      loc_18001A6CD
0x18001a5b3  call    ??$InitializeSecurity@USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@@ServiceModuleBase@Internal@Windows@@IEAAJXZ; Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal>(void)
0x18001a5b8  mov     edi, eax
0x18001a5ba  test    eax, eax
0x18001a5bc  jns     short loc_18001A5E6
0x18001a5be  mov     rcx, [rsp+88h]; this
0x18001a5c6  mov     r9d, eax; char *
0x18001a5c9  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18001a5d0  mov     edx, 6Ch ; 'l'; void *
0x18001a5d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a5da  nop
0x18001a5db  mov     rcx, rbx; this
0x18001a5de  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18001a5e3  nop
0x18001a5e4  jmp     short loc_18001A5A3
0x18001a5e6  mov     [rsp+88h+arg_0], 0
0x18001a5f2  lea     rcx, [rsp+88h+arg_0]
0x18001a5fa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a5ff  lea     rax, [rsp+88h+arg_0]
0x18001a607  mov     [rsp+88h+ppv], rax; int
0x18001a60c  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18001a613  mov     r8d, r15d; dwClsContext
0x18001a616  xor     edx, edx; pUnkOuter
0x18001a618  lea     rcx, CLSID_GlobalOptions; rclsid
0x18001a61f  call    cs:__imp_CoCreateInstance
0x18001a625  mov     edi, eax
0x18001a627  test    eax, eax
0x18001a629  jns     short loc_18001A664
0x18001a62b  mov     rcx, [rsp+88h]; this
0x18001a633  mov     r9d, eax; char *
0x18001a636  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18001a63d  mov     edx, 73h ; 's'; void *
0x18001a642  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a647  nop
0x18001a648  lea     rcx, [rsp+88h+arg_0]
0x18001a650  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a655  nop
0x18001a656  mov     rcx, rbx; this
0x18001a659  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18001a65e  nop
0x18001a65f  jmp     loc_18001A5A3
0x18001a664  mov     rcx, [rsp+88h+arg_0]
0x18001a66c  mov     rax, [rcx]
0x18001a66f  mov     r8d, 2
0x18001a675  mov     edx, r15d
0x18001a678  mov     rax, [rax+18h]
0x18001a67c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a681  mov     edi, eax
0x18001a683  test    eax, eax
0x18001a685  jns     short loc_18001A6C0
0x18001a687  mov     rcx, [rsp+88h]; this
0x18001a68f  mov     r9d, eax; char *
0x18001a692  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18001a699  mov     edx, 74h ; 't'; void *
0x18001a69e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a6a3  nop
0x18001a6a4  lea     rcx, [rsp+88h+arg_0]
0x18001a6ac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a6b1  nop
0x18001a6b2  mov     rcx, rbx; this
0x18001a6b5  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18001a6ba  nop
0x18001a6bb  jmp     loc_18001A5A3
0x18001a6c0  lea     rcx, [rsp+88h+arg_0]
0x18001a6c8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a6cd  mov     rax, [rsi]
0x18001a6d0  mov     rcx, rsi
0x18001a6d3  mov     rax, [rax+20h]
0x18001a6d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6dc  mov     edi, eax
0x18001a6de  test    eax, eax
0x18001a6e0  jns     short loc_18001A70D
0x18001a6e2  mov     rcx, [rsp+88h]; this
0x18001a6ea  mov     r9d, eax; char *
0x18001a6ed  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18001a6f4  mov     edx, 7Bh ; '{'; void *
0x18001a6f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a6fe  nop
0x18001a6ff  mov     rcx, rbx; this
0x18001a702  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18001a707  nop
0x18001a708  jmp     loc_18001A5A3
0x18001a70d  lea     r14, [rsi+18h]
0x18001a711  mov     rcx, r14
0x18001a714  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a719  mov     [rsp+88h+ppv], r14; int
0x18001a71e  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x18001a725  mov     r8d, r15d; dwClsContext
0x18001a728  xor     edx, edx; pUnkOuter
0x18001a72a  lea     rcx, CLSID_ContextSwitcher; rclsid
0x18001a731  call    cs:__imp_CoCreateInstance
0x18001a737  mov     edi, eax
0x18001a739  test    eax, eax
0x18001a73b  jns     short loc_18001A768
0x18001a73d  mov     rcx, [rsp+88h]; this
0x18001a745  mov     r9d, eax; char *
0x18001a748  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18001a74f  mov     edx, 8Dh; void *
0x18001a754  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a759  nop
0x18001a75a  mov     rcx, rbx; this
0x18001a75d  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18001a762  nop
0x18001a763  jmp     loc_18001A5A3
0x18001a768  mov     rcx, [r14]
0x18001a76b  mov     rax, [rcx]
0x18001a76e  mov     [rsp+88h+var_60], 0
0x18001a777  mov     dword ptr [rsp+88h+ppv], 5; int
0x18001a77f  lea     r9, IID_IContextCallback
0x18001a786  mov     r8, rsi
0x18001a789  lea     rdx, ?ConnectCallbackThunk@ServiceModuleBase@Internal@Windows@@SAJPEAUtagComCallData@@@Z; Windows::Internal::ServiceModuleBase::ConnectCallbackThunk(tagComCallData *)
0x18001a790  mov     rax, [rax+18h]
0x18001a794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a799  mov     edi, eax
0x18001a79b  test    eax, eax
0x18001a79d  jns     short loc_18001A7CA
0x18001a79f  mov     rcx, [rsp+88h]; this
0x18001a7a7  mov     r9d, eax; char *
0x18001a7aa  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18001a7b1  mov     edx, 90h; void *
0x18001a7b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a7bb  nop
0x18001a7bc  mov     rcx, rbx; this
0x18001a7bf  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18001a7c4  nop
0x18001a7c5  jmp     loc_18001A5A3
0x18001a7ca  xor     eax, eax
0x18001a7cc  add     rsp, 58h
0x18001a7d0  pop     r15
0x18001a7d2  pop     r14
0x18001a7d4  pop     rdi
0x18001a7d5  pop     rsi
0x18001a7d6  pop     rbp
0x18001a7d7  pop     rbx
0x18001a7d8  retn
```
