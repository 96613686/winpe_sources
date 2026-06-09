# wil::GetActivationFactory<Windows::Internal::Devices::Lights::BacklightServer::IBacklightServerHostStatics>(ushort const *)

- ea: `0x18001d3c8`
- end: `0x18001d480`
- name: `??$GetActivationFactory@UIBacklightServerHostStatics@BacklightServer@Lights@Devices@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIBacklightServerHostStatics@BacklightServer@Lights@Devices@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z`
- size: `184`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800194b0`

## callees

- `0x18001bbe0`
- `0x18001d3c8`
- `0x1800289dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001d42f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001d42f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d419`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d419`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d445`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001d445`

## string_xrefs

- `0x18001d457`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
_QWORD *__fastcall wil::GetActivationFactory<Windows::Internal::Devices::Lights::BacklightServer::IBacklightServerHostStatics>(
        _QWORD *a1)
{
  HRESULT v2; // eax
  int ActivationFactory; // eax
  HSTRING_HEADER v5; // [rsp+30h] [rbp-38h] BYREF
  HSTRING v6; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *a1 = 0;
  v6 = 0;
  v2 = WindowsCreateStringReference(
         L"Windows.Internal.Devices.Lights.BacklightServer.BacklightServerHost",
         0x43u,
         &v5,
         &v6);
  if ( v2 < 0 )
    RaiseException(v2, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(v6, &GUID_cae695c6_333a_5a99_8148_ba9214157583, a1);
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
0x18001d3c8  mov     r11, rsp
0x18001d3cb  push    rbx
0x18001d3cc  sub     rsp, 60h
0x18001d3d0  mov     rax, cs:__security_cookie
0x18001d3d7  xor     rax, rsp
0x18001d3da  mov     [rsp+68h+var_18], rax
0x18001d3df  mov     rbx, rcx
0x18001d3e2  mov     [r11-40h], rcx
0x18001d3e6  mov     [rsp+68h+var_48], 0
0x18001d3ee  mov     [rsp+68h+var_48], 1; int
0x18001d3f6  mov     qword ptr [rcx], 0
0x18001d3fd  mov     qword ptr [r11-20h], 0
0x18001d405  lea     r9, [r11-20h]; string
0x18001d409  lea     r8, [r11-38h]; hstringHeader
0x18001d40d  mov     edx, 43h ; 'C'; length
0x18001d412  lea     rcx, ?RuntimeClass_Windows_Internal_Devices_Lights_BacklightServer_BacklightServerHost@@3QBGB; "Windows.Internal.Devices.Lights.Backlig"...
0x18001d419  call    cs:__imp_WindowsCreateStringReference
0x18001d41f  test    eax, eax
0x18001d421  jns     short loc_18001D436
0x18001d423  xor     r9d, r9d; lpArguments
0x18001d426  xor     r8d, r8d; nNumberOfArguments
0x18001d429  lea     edx, [r9+1]; dwExceptionFlags
0x18001d42d  mov     ecx, eax; dwExceptionCode
0x18001d42f  call    cs:__imp_RaiseException
0x18001d435  nop
0x18001d436  mov     r8, rbx
0x18001d439  lea     rdx, _GUID_cae695c6_333a_5a99_8148_ba9214157583
0x18001d440  mov     rcx, [rsp+68h+var_20]
0x18001d445  call    cs:__imp_RoGetActivationFactory
0x18001d44b  mov     rcx, [rsp+68h]; this
0x18001d450  test    eax, eax
0x18001d452  jns     short loc_18001D469
0x18001d454  mov     r9d, eax; char *
0x18001d457  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001d45e  mov     edx, 744h; void *
0x18001d463  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001d469  mov     rax, rbx
0x18001d46c  mov     rcx, [rsp+68h+var_18]
0x18001d471  xor     rcx, rsp; StackCookie
0x18001d474  call    __security_check_cookie
0x18001d479  add     rsp, 60h
0x18001d47d  pop     rbx
0x18001d47e  retn
```
