# WindowsInternal::ApplicationModel::Calls::AppLauncherInternal::_EnsureCallControlPublicApiFeatureAvailable(void)

- ea: `0x1800105ec`
- end: `0x180010798`
- name: `?_EnsureCallControlPublicApiFeatureAvailable@AppLauncherInternal@Calls@ApplicationModel@WindowsInternal@@IEAAJXZ`
- size: `428`
- prototype: `__int64 __fastcall(WindowsInternal::ApplicationModel::Calls::AppLauncherInternal *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800101d0`

## callees

- `0x1800012b8`
- `0x180001dc0`
- `0x18000cf2c`
- `0x18000e284`
- `0x1800105ec`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010630`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800106bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010630`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800106bd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001064d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001064d`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::AppLauncherInternal::_EnsureCallControlPublicApiFeatureAvailable(
        WindowsInternal::ApplicationModel::Calls::AppLauncherInternal *this)
{
  HRESULT v1; // eax
  int v2; // edx
  unsigned int v3; // r8d
  int ActivationFactory; // ebx
  _QWORD *v5; // rcx
  _QWORD *v7; // rbx
  __int64 v8; // rdi
  HRESULT v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  _QWORD *v15; // rcx
  _QWORD *v16; // rcx
  const char *v17; // [rsp+30h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-38h] BYREF
  HSTRING string; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v20[8]; // [rsp+58h] [rbp-18h] BYREF
  _QWORD *v21; // [rsp+60h] [rbp-10h] BYREF

  v21 = 0;
  string = 0;
  v1 = WindowsCreateStringReference(L"Windows.Foundation.Metadata.ApiInformation", 0x2Au, &hstringHeader, &string);
  if ( v1 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v1, v2, v3);
    JUMPOUT(0x180010797LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_997439fe_f681_4a11_b416_c13a47e8ba36, &v21);
  if ( ActivationFactory < 0 )
    goto LABEL_3;
  v7 = v21;
  v20[0] = 0;
  v8 = *v21;
  string = 0;
  v9 = WindowsCreateStringReference(
         L"Windows.ApplicationModel.Calls.CallsPhoneContract",
         0x31u,
         &hstringHeader,
         &string);
  if ( v9 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
    __debugbreak();
  }
  ActivationFactory = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, _BYTE *))(v8 + 112))(v7, string, 6, v20);
  if ( ActivationFactory < 0 )
  {
LABEL_3:
    Log_HREvent_0(
      (unsigned int)ActivationFactory,
      1,
      "onecoreuap\\net\\phone\\telephonyinteractiveuser\\lib\\applauncher.cpp");
    v5 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v5 + 16LL))(v5);
    }
    return (unsigned int)ActivationFactory;
  }
  else if ( v20[0] )
  {
    v16 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
    }
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_180025038 > 4 )
    {
      v17 = "Windows.ApplicationModel.Calls.CallsPhoneContract version does not contain this feature";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v12,
        (unsigned int)&byte_18002094F,
        v13,
        v14,
        (__int64)&v17);
    }
    v15 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
    }
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x1800105ec  mov     [rsp-8+arg_0], rbx
0x1800105f1  mov     [rsp-8+arg_8], rdi
0x1800105f6  push    rbp
0x1800105f7  mov     rbp, rsp
0x1800105fa  sub     rsp, 70h
0x1800105fe  mov     rax, cs:__security_cookie
0x180010605  xor     rax, rsp
0x180010608  mov     [rbp+var_8], rax
0x18001060c  lea     r9, [rbp+string]; string
0x180010610  mov     [rbp+var_10], 0
0x180010618  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001061c  mov     [rbp+string], 0
0x180010624  mov     edx, 2Ah ; '*'; length
0x180010629  lea     rcx, ?RuntimeClass_Windows_Foundation_Metadata_ApiInformation@@3QBGB; "Windows.Foundation.Metadata.ApiInformat"...
0x180010630  call    cs:__imp_WindowsCreateStringReference
0x180010636  test    eax, eax
0x180010638  js      loc_180010790
0x18001063e  mov     rcx, [rbp+string]
0x180010642  lea     r8, [rbp+var_10]
0x180010646  lea     rdx, _GUID_997439fe_f681_4a11_b416_c13a47e8ba36
0x18001064d  call    cs:__imp_RoGetActivationFactory
0x180010653  mov     ebx, eax
0x180010655  test    eax, eax
0x180010657  jns     short loc_180010696
0x180010659  mov     r9d, 3Dh ; '='
0x18001065f  lea     r8, aOnecoreuapNetP_3; "onecoreuap\\net\\phone\\telephonyintera"...
0x180010666  mov     edx, 1
0x18001066b  mov     ecx, ebx
0x18001066d  call    Log_HREvent_0
0x180010672  mov     rcx, [rbp+var_10]
0x180010676  test    rcx, rcx
0x180010679  jz      short loc_18001068F
0x18001067b  mov     [rbp+var_10], 0
0x180010683  mov     rax, [rcx]
0x180010686  mov     rax, [rax+10h]
0x18001068a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001068f  mov     eax, ebx
0x180010691  jmp     loc_18001076A
0x180010696  mov     rbx, [rbp+var_10]
0x18001069a  lea     r9, [rbp+string]; string
0x18001069e  mov     [rbp+var_18], 0
0x1800106a2  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800106a6  mov     edx, 31h ; '1'; length
0x1800106ab  lea     rcx, aWindowsApplica_0; "Windows.ApplicationModel.Calls.CallsPho"...
0x1800106b2  mov     rdi, [rbx]
0x1800106b5  mov     [rbp+string], 0
0x1800106bd  call    cs:__imp_WindowsCreateStringReference
0x1800106c3  test    eax, eax
0x1800106c5  js      loc_180010788
0x1800106cb  mov     rdx, [rbp+string]
0x1800106cf  lea     r9, [rbp+var_18]
0x1800106d3  mov     rax, [rdi+70h]
0x1800106d7  mov     r8d, 6
0x1800106dd  mov     rcx, rbx
0x1800106e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106e5  mov     ebx, eax
0x1800106e7  test    eax, eax
0x1800106e9  jns     short loc_1800106F6
0x1800106eb  mov     r9d, 41h ; 'A'
0x1800106f1  jmp     loc_18001065F
0x1800106f6  cmp     [rbp+var_18], 0
0x1800106fa  jnz     short loc_18001074B
0x1800106fc  mov     eax, cs:dword_180025038
0x180010702  cmp     eax, 4
0x180010705  jbe     short loc_180010727
0x180010707  lea     rax, aWindowsApplica; "Windows.ApplicationModel.Calls.CallsPho"...
0x18001070e  mov     [rbp+var_40], rax
0x180010712  lea     rdx, byte_18002094F
0x180010719  lea     rax, [rbp+var_40]
0x18001071d  mov     [rsp+70h+var_50], rax
0x180010722  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180010727  mov     rcx, [rbp+var_10]
0x18001072b  test    rcx, rcx
0x18001072e  jz      short loc_180010744
0x180010730  mov     [rbp+var_10], 0
0x180010738  mov     rax, [rcx]
0x18001073b  mov     rax, [rax+10h]
0x18001073f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010744  mov     eax, 80004001h
0x180010749  jmp     short loc_18001076A
0x18001074b  mov     rcx, [rbp+var_10]
0x18001074f  test    rcx, rcx
0x180010752  jz      short loc_180010768
0x180010754  mov     [rbp+var_10], 0
0x18001075c  mov     rax, [rcx]
0x18001075f  mov     rax, [rax+10h]
0x180010763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010768  xor     eax, eax
0x18001076a  mov     rcx, [rbp+var_8]
0x18001076e  xor     rcx, rsp; StackCookie
0x180010771  call    __security_check_cookie
0x180010776  lea     r11, [rsp+70h+var_s0]
0x18001077b  mov     rbx, [r11+10h]
0x18001077f  mov     rdi, [r11+18h]
0x180010783  mov     rsp, r11
0x180010786  pop     rbp
0x180010787  retn
0x180010788  mov     ecx, eax; this
0x18001078a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18001078f  int     3; Trap to Debugger
0x180010790  mov     ecx, eax; this
0x180010792  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
