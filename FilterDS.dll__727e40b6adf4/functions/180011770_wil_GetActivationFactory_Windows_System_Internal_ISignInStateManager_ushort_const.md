# wil::GetActivationFactory<Windows::System::Internal::ISignInStateManager>(ushort const *)

- ea: `0x180011770`
- end: `0x18001181c`
- name: `??$GetActivationFactory@UISignInStateManager@Internal@System@Windows@@@wil@@YA?AV?$com_ptr_t@UISignInStateManager@Internal@System@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z`
- size: `172`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012f4c`
- `0x180014794`

## callees

- `0x18000cd18`
- `0x180011770`
- `0x1800157c0`
- `0x180021850`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800117c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800117c1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800117da`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800117da`

## string_xrefs

- `0x180011802`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
_QWORD *__fastcall wil::GetActivationFactory<Windows::System::Internal::ISignInStateManager>(_QWORD *a1)
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
  v2 = WindowsCreateStringReference(L"Windows.System.Internal.UserManager", 0x23u, &v7, &v8);
  if ( v2 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
    JUMPOUT(0x18001181BLL);
  }
  ActivationFactory = RoGetActivationFactory(v8, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, a1);
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
0x180011770  mov     r11, rsp
0x180011773  push    rbx
0x180011774  sub     rsp, 60h
0x180011778  mov     rax, cs:__security_cookie
0x18001177f  xor     rax, rsp
0x180011782  mov     [rsp+68h+var_18], rax
0x180011787  mov     rbx, rcx
0x18001178a  mov     [r11-40h], rcx
0x18001178e  mov     [rsp+68h+var_48], 0
0x180011796  mov     [rsp+68h+var_48], 1; int
0x18001179e  mov     qword ptr [rcx], 0
0x1800117a5  mov     qword ptr [r11-20h], 0
0x1800117ad  lea     r9, [r11-20h]; string
0x1800117b1  lea     r8, [r11-38h]; hstringHeader
0x1800117b5  mov     edx, 23h ; '#'; length
0x1800117ba  lea     rcx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x1800117c1  call    cs:__imp_WindowsCreateStringReference
0x1800117c7  test    eax, eax
0x1800117c9  js      short loc_180011814
0x1800117cb  mov     r8, rbx
0x1800117ce  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x1800117d5  mov     rcx, [rsp+68h+var_20]
0x1800117da  call    cs:__imp_RoGetActivationFactory
0x1800117e0  mov     rcx, [rsp+68h]; this
0x1800117e5  test    eax, eax
0x1800117e7  js      short loc_1800117FF
0x1800117e9  mov     rax, rbx
0x1800117ec  mov     rcx, [rsp+68h+var_18]
0x1800117f1  xor     rcx, rsp; StackCookie
0x1800117f4  call    __security_check_cookie
0x1800117f9  add     rsp, 60h
0x1800117fd  pop     rbx
0x1800117fe  retn
0x1800117ff  mov     r9d, eax; char *
0x180011802  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011809  mov     edx, 744h; void *
0x18001180e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180011814  mov     ecx, eax; this
0x180011816  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
