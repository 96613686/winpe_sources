# StateRepository::WinRT::CoreApplication::GetPrivateProperties(Windows::Foundation::Collections::IPropertySet * *)

- ea: `0x180026330`
- end: `0x180026404`
- name: `?GetPrivateProperties@CoreApplication@WinRT@StateRepository@@YAJPEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(StateRepository::WinRT::CoreApplication *__hidden this, struct Windows::Foundation::Collections::IPropertySet **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180026268`

## callees

- `0x180002980`
- `0x1800075e4`
- `0x180009cb0`
- `0x18000b348`
- `0x180026330`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180026396`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180026396`

## string_xrefs

- `0x1800263cd`: `onecore\base\appmodel\staterepository\winrt\common\src\winrt-coreapplication.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::WinRT::CoreApplication::GetPrivateProperties(
        StateRepository::WinRT::CoreApplication *this,
        struct Windows::Foundation::Collections::IPropertySet **a2)
{
  __int64 v3; // rbx
  int ActivationFactory; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v8; // [rsp+20h] [rbp-38h] BYREF
  HSTRING_HEADER v9; // [rsp+28h] [rbp-30h] BYREF
  __int64 v10; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v8 = 0;
  v10 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v9,
    L"Windows.ApplicationModel.Core.CoreApplication",
    0x2Eu,
    0x2Du);
  v3 = v10;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v8);
  ActivationFactory = RoGetActivationFactory(v3, &GUID_17b0e613_942a_422d_904c_f90dc71a7dae, &v8);
  v5 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, StateRepository::WinRT::CoreApplication *))(*(_QWORD *)v8 + 56LL))(
                          v8,
                          this);
    v5 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v5 = 0;
      goto LABEL_7;
    }
    v6 = 70;
  }
  else
  {
    v6 = 69;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\common\\src\\winrt-coreapplication.cpp",
    (const char *)(unsigned int)ActivationFactory,
    v8);
LABEL_7:
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v8);
  return v5;
}

```

## disassembly

```asm
0x180026330  mov     r11, rsp
0x180026333  mov     [r11+10h], rbx
0x180026337  push    rdi
0x180026338  sub     rsp, 50h
0x18002633c  mov     rax, cs:__security_cookie
0x180026343  xor     rax, rsp
0x180026346  mov     [rsp+58h+var_10], rax
0x18002634b  mov     r9d, 2Dh ; '-'; unsigned int
0x180026351  mov     qword ptr [r11-38h], 0
0x180026359  mov     rdi, rcx
0x18002635c  mov     qword ptr [r11-18h], 0
0x180026364  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Core_CoreApplication@@3QBGB; "Windows.ApplicationModel.Core.CoreAppli"...
0x18002636b  lea     rcx, [r11-30h]; hstringHeader
0x18002636f  lea     r8d, [r9+1]; unsigned int
0x180026373  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180026378  mov     rbx, [rsp+58h+var_18]
0x18002637d  lea     rcx, [rsp+58h+var_38]
0x180026382  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x180026387  lea     r8, [rsp+58h+var_38]
0x18002638c  mov     rcx, rbx
0x18002638f  lea     rdx, _GUID_17b0e613_942a_422d_904c_f90dc71a7dae
0x180026396  call    cs:__imp_RoGetActivationFactory
0x18002639c  mov     ebx, eax
0x18002639e  test    eax, eax
0x1800263a0  jns     short loc_1800263A9
0x1800263a2  mov     edx, 45h ; 'E'
0x1800263a7  jmp     short loc_1800263C8
0x1800263a9  mov     rcx, [rsp+58h+var_38]
0x1800263ae  mov     rdx, rdi
0x1800263b1  mov     rax, [rcx]
0x1800263b4  mov     rax, [rax+38h]
0x1800263b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263bd  mov     ebx, eax
0x1800263bf  test    eax, eax
0x1800263c1  jns     short loc_1800263DE
0x1800263c3  mov     edx, 46h ; 'F'; void *
0x1800263c8  mov     rcx, [rsp+58h]; this
0x1800263cd  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\staterepositor"...
0x1800263d4  mov     r9d, eax; char *
0x1800263d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800263dc  jmp     short loc_1800263E0
0x1800263de  xor     ebx, ebx
0x1800263e0  lea     rcx, [rsp+58h+var_38]
0x1800263e5  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x1800263ea  mov     eax, ebx
0x1800263ec  mov     rcx, [rsp+58h+var_10]
0x1800263f1  xor     rcx, rsp; StackCookie
0x1800263f4  call    __security_check_cookie
0x1800263f9  mov     rbx, [rsp+58h+arg_8]
0x1800263fe  add     rsp, 50h
0x180026402  pop     rdi
0x180026403  retn
```
