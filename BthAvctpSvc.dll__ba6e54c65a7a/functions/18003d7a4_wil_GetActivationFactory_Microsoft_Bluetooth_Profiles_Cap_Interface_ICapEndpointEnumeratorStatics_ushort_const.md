# wil::GetActivationFactory<Microsoft::Bluetooth::Profiles::Cap::Interface::ICapEndpointEnumeratorStatics>(ushort const *)

- ea: `0x18003d7a4`
- end: `0x18003d83b`
- name: `??$GetActivationFactory@UICapEndpointEnumeratorStatics@Interface@Cap@Profiles@Bluetooth@Microsoft@@@wil@@YA?AV?$com_ptr_t@UICapEndpointEnumeratorStatics@Interface@Cap@Profiles@Bluetooth@Microsoft@@Uerr_exception_policy@wil@@@0@PEBG@Z`
- size: `151`
- prototype: `const WCHAR *__fastcall(const WCHAR *, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180041bb4`

## callees

- `0x180001dd0`
- `0x18000e0c0`
- `0x18002c218`
- `0x18003d7a4`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003d800`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003d800`

## string_xrefs

- `0x18003d812`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
const WCHAR *__fastcall wil::GetActivationFactory<Microsoft::Bluetooth::Profiles::Cap::Interface::ICapEndpointEnumeratorStatics>(
        const WCHAR *a1,
        __int64 a2,
        char a3)
{
  __int64 v4; // rax
  int ActivationFactory; // eax
  const WCHAR *v7[3]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v8; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v7[2] = a1;
  v7[0] = L"Microsoft.Bluetooth.Profiles.Cap.Interface.CapEndpointEnumerator";
  *(_QWORD *)a1 = 0;
  v4 = Microsoft::WRL::Wrappers::HStringReference::HStringReference((__int64)&v8, v7, a3);
  ActivationFactory = RoGetActivationFactory(*(_QWORD *)(v4 + 24), &GUID_72c6deb6_1453_5f17_b681_a7cacea9755c, a1);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x744,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)(unsigned int)ActivationFactory,
      1);
  return a1;
}

```

## disassembly

```asm
0x18003d7a4  mov     r11, rsp
0x18003d7a7  push    rbx
0x18003d7a8  sub     rsp, 70h
0x18003d7ac  mov     rax, cs:__security_cookie
0x18003d7b3  xor     rax, rsp
0x18003d7b6  mov     [rsp+78h+var_10], rax
0x18003d7bb  mov     rbx, rcx
0x18003d7be  mov     [r11-38h], rcx
0x18003d7c2  mov     [rsp+78h+var_58], 0
0x18003d7ca  lea     rax, ?RuntimeClass_Microsoft_Bluetooth_Profiles_Cap_Interface_CapEndpointEnumerator@@3QBGB; "Microsoft.Bluetooth.Profiles.Cap.Interf"...
0x18003d7d1  mov     [r11-48h], rax
0x18003d7d5  mov     [rsp+78h+var_58], 1; int
0x18003d7dd  mov     qword ptr [rcx], 0
0x18003d7e4  lea     rdx, [r11-48h]
0x18003d7e8  lea     rcx, [r11-30h]
0x18003d7ec  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003d7f1  nop
0x18003d7f2  mov     r8, rbx
0x18003d7f5  lea     rdx, _GUID_72c6deb6_1453_5f17_b681_a7cacea9755c
0x18003d7fc  mov     rcx, [rax+18h]
0x18003d800  call    cs:__imp_RoGetActivationFactory
0x18003d806  mov     rcx, [rsp+78h]; this
0x18003d80b  test    eax, eax
0x18003d80d  jns     short loc_18003D824
0x18003d80f  mov     r9d, eax; char *
0x18003d812  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003d819  mov     edx, 744h; void *
0x18003d81e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003d824  mov     rax, rbx
0x18003d827  mov     rcx, [rsp+78h+var_10]
0x18003d82c  xor     rcx, rsp; StackCookie
0x18003d82f  call    __security_check_cookie
0x18003d834  add     rsp, 70h
0x18003d838  pop     rbx
0x18003d839  retn
```
