# wil::GetActivationFactory<Microsoft::Bluetooth::Profiles::MediaControl::Interface::IMediaControlServiceStatics>(ushort const *)

- ea: `0x18002c40c`
- end: `0x18002c4a3`
- name: `??$GetActivationFactory@UIMediaControlServiceStatics@Interface@MediaControl@Profiles@Bluetooth@Microsoft@@@wil@@YA?AV?$com_ptr_t@UIMediaControlServiceStatics@Interface@MediaControl@Profiles@Bluetooth@Microsoft@@Uerr_exception_policy@wil@@@0@PEBG@Z`
- size: `151`
- prototype: `const WCHAR *__fastcall(const WCHAR *, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002de00`

## callees

- `0x180001dd0`
- `0x18000e0c0`
- `0x18002c218`
- `0x18002c40c`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002c468`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002c468`

## string_xrefs

- `0x18002c432`: `Microsoft.Bluetooth.Profiles.MediaControl.Interface.MediaControlService`
- `0x18002c47a`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
const WCHAR *__fastcall wil::GetActivationFactory<Microsoft::Bluetooth::Profiles::MediaControl::Interface::IMediaControlServiceStatics>(
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
  v7[0] = L"Microsoft.Bluetooth.Profiles.MediaControl.Interface.MediaControlService";
  *(_QWORD *)a1 = 0;
  v4 = Microsoft::WRL::Wrappers::HStringReference::HStringReference((__int64)&v8, v7, a3);
  ActivationFactory = RoGetActivationFactory(*(_QWORD *)(v4 + 24), &GUID_207bd008_9ffa_5d4b_961e_29851b9f9e5f, a1);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
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
0x18002c40c  mov     r11, rsp
0x18002c40f  push    rbx
0x18002c410  sub     rsp, 70h
0x18002c414  mov     rax, cs:__security_cookie
0x18002c41b  xor     rax, rsp
0x18002c41e  mov     [rsp+78h+var_10], rax
0x18002c423  mov     rbx, rcx
0x18002c426  mov     [r11-38h], rcx
0x18002c42a  mov     [rsp+78h+var_58], 0
0x18002c432  lea     rax, ?RuntimeClass_Microsoft_Bluetooth_Profiles_MediaControl_Interface_MediaControlService@@3QBGB; "Microsoft.Bluetooth.Profiles.MediaContr"...
0x18002c439  mov     [r11-48h], rax
0x18002c43d  mov     [rsp+78h+var_58], 1; int
0x18002c445  mov     qword ptr [rcx], 0
0x18002c44c  lea     rdx, [r11-48h]
0x18002c450  lea     rcx, [r11-30h]
0x18002c454  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002c459  nop
0x18002c45a  mov     r8, rbx
0x18002c45d  lea     rdx, _GUID_207bd008_9ffa_5d4b_961e_29851b9f9e5f
0x18002c464  mov     rcx, [rax+18h]
0x18002c468  call    cs:__imp_RoGetActivationFactory
0x18002c46e  mov     rcx, [rsp+78h]; this
0x18002c473  test    eax, eax
0x18002c475  jns     short loc_18002C48C
0x18002c477  mov     r9d, eax; char *
0x18002c47a  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002c481  mov     edx, 744h; void *
0x18002c486  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002c48c  mov     rax, rbx
0x18002c48f  mov     rcx, [rsp+78h+var_10]
0x18002c494  xor     rcx, rsp; StackCookie
0x18002c497  call    __security_check_cookie
0x18002c49c  add     rsp, 70h
0x18002c4a0  pop     rbx
0x18002c4a1  retn
```
