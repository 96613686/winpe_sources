# wil::GetActivationFactory<Windows::System::IUserStatics>(ushort const *)

- ea: `0x180011824`
- end: `0x1800118d0`
- name: `??$GetActivationFactory@UIUserStatics@System@Windows@@@wil@@YA?AV?$com_ptr_t@UIUserStatics@System@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z`
- size: `172`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014c20`

## callees

- `0x18000cd18`
- `0x180011824`
- `0x1800157c0`
- `0x180021850`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011875`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011875`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001188e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001188e`

## string_xrefs

- `0x1800118b6`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
_QWORD *__fastcall wil::GetActivationFactory<Windows::System::IUserStatics>(_QWORD *a1)
{
  HRESULT v2; // eax
  int v3; // edx
  unsigned int v4; // r8d
  int ActivationFactory; // eax
  HSTRING_HEADER v7; // [rsp+30h] [rbp-38h] BYREF
  HSTRING v8; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *a1 = 0;
  v8 = 0;
  v2 = WindowsCreateStringReference(L"Windows.System.User", 0x13u, &v7, &v8);
  if ( v2 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
    JUMPOUT(0x1800118CFLL);
  }
  ActivationFactory = RoGetActivationFactory(v8, &GUID_155eb23b_242a_45e0_a2e9_3171fc6a7fdd, a1);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x744,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)ActivationFactory,
      1);
  return a1;
}

```

## disassembly

```asm
0x180011824  mov     r11, rsp
0x180011827  push    rbx
0x180011828  sub     rsp, 60h
0x18001182c  mov     rax, cs:__security_cookie
0x180011833  xor     rax, rsp
0x180011836  mov     [rsp+68h+var_18], rax
0x18001183b  mov     rbx, rcx
0x18001183e  mov     [r11-40h], rcx
0x180011842  mov     [rsp+68h+var_48], 0
0x18001184a  mov     [rsp+68h+var_48], 1; int
0x180011852  mov     qword ptr [rcx], 0
0x180011859  mov     qword ptr [r11-20h], 0
0x180011861  lea     r9, [r11-20h]; string
0x180011865  lea     r8, [r11-38h]; hstringHeader
0x180011869  mov     edx, 13h; length
0x18001186e  lea     rcx, ?RuntimeClass_Windows_System_User@@3QBGB; "Windows.System.User"
0x180011875  call    cs:__imp_WindowsCreateStringReference
0x18001187b  test    eax, eax
0x18001187d  js      short loc_1800118C8
0x18001187f  mov     r8, rbx
0x180011882  lea     rdx, _GUID_155eb23b_242a_45e0_a2e9_3171fc6a7fdd
0x180011889  mov     rcx, [rsp+68h+var_20]
0x18001188e  call    cs:__imp_RoGetActivationFactory
0x180011894  mov     rcx, [rsp+68h]; this
0x180011899  test    eax, eax
0x18001189b  js      short loc_1800118B3
0x18001189d  mov     rax, rbx
0x1800118a0  mov     rcx, [rsp+68h+var_18]
0x1800118a5  xor     rcx, rsp; StackCookie
0x1800118a8  call    __security_check_cookie
0x1800118ad  add     rsp, 60h
0x1800118b1  pop     rbx
0x1800118b2  retn
0x1800118b3  mov     r9d, eax; char *
0x1800118b6  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800118bd  mov     edx, 744h; void *
0x1800118c2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800118c8  mov     ecx, eax; this
0x1800118ca  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
