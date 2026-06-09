# EffectiveWebAccountContext::GetTokenBrokerInternalStatics(void)

- ea: `0x1800433b0`
- end: `0x180043467`
- name: `?GetTokenBrokerInternalStatics@EffectiveWebAccountContext@@SA?AV?$com_ptr_t@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@XZ`
- size: `183`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180042d28`
- `0x180042ec0`
- `0x18005facc`
- `0x1800e1d4c`
- `0x180106674`
- `0x18017a2f0`

## callees

- `0x180016cf4`
- `0x1800433b0`
- `0x1801201a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180043460`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180043460`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004341a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004341a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180043401`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180043401`

## string_xrefs

- `0x1800433fa`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`
- `0x180043442`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall EffectiveWebAccountContext::GetTokenBrokerInternalStatics(_QWORD *a1)
{
  HRESULT v2; // eax
  int ActivationFactory; // eax
  HSTRING_HEADER v5; // [rsp+30h] [rbp-38h] BYREF
  HSTRING v6; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *a1 = 0;
  v6 = 0;
  v2 = WindowsCreateStringReference(
         L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
         0x40u,
         &v5,
         &v6);
  if ( v2 < 0 )
  {
    RaiseException(v2, 1u, 0, 0);
    JUMPOUT(0x180043466LL);
  }
  ActivationFactory = RoGetActivationFactory(v6, &GUID_07650a66_66ea_489d_aa90_0dabc75f3567, a1);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
      (const char *)(unsigned int)ActivationFactory,
      1);
  return a1;
}

```

## disassembly

```asm
0x1800433b0  mov     r11, rsp
0x1800433b3  push    rbx
0x1800433b4  sub     rsp, 60h
0x1800433b8  mov     rax, cs:__security_cookie
0x1800433bf  xor     rax, rsp
0x1800433c2  mov     [rsp+68h+var_18], rax
0x1800433c7  mov     rbx, rcx
0x1800433ca  mov     [r11-40h], rcx
0x1800433ce  mov     [rsp+68h+var_48], 0
0x1800433d6  mov     [rsp+68h+var_48], 1; int
0x1800433de  mov     qword ptr [rcx], 0
0x1800433e5  mov     qword ptr [r11-20h], 0
0x1800433ed  lea     r9, [r11-20h]; string
0x1800433f1  lea     r8, [r11-38h]; hstringHeader
0x1800433f5  mov     edx, 40h ; '@'; length
0x1800433fa  lea     rcx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x180043401  call    cs:__imp_WindowsCreateStringReference
0x180043407  test    eax, eax
0x180043409  js      short loc_180043454
0x18004340b  mov     r8, rbx
0x18004340e  lea     rdx, _GUID_07650a66_66ea_489d_aa90_0dabc75f3567
0x180043415  mov     rcx, [rsp+68h+var_20]
0x18004341a  call    cs:__imp_RoGetActivationFactory
0x180043420  mov     rcx, [rsp+68h]; this
0x180043425  test    eax, eax
0x180043427  js      short loc_18004343F
0x180043429  mov     rax, rbx
0x18004342c  mov     rcx, [rsp+68h+var_18]
0x180043431  xor     rcx, rsp; StackCookie
0x180043434  call    __security_check_cookie
0x180043439  add     rsp, 60h
0x18004343d  pop     rbx
0x18004343e  retn
0x18004343f  mov     r9d, eax; char *
0x180043442  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180043449  mov     edx, 27h ; '''; void *
0x18004344e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180043454  xor     r9d, r9d; lpArguments
0x180043457  xor     r8d, r8d; nNumberOfArguments
0x18004345a  lea     edx, [r9+1]; dwExceptionFlags
0x18004345e  mov     ecx, eax; dwExceptionCode
0x180043460  call    cs:__imp_RaiseException
```
