# wil::GetActivationFactory<Windows::Internal::StateRepository::IApplicationStatics>(ushort const *)

- ea: `0x18009a2b0`
- end: `0x18009a381`
- name: `??$GetActivationFactory@UIApplicationStatics@StateRepository@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIApplicationStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800107b0`

## callees

- `0x180016cf4`
- `0x180063ba0`
- `0x18009a2b0`
- `0x1801201a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18009a37a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18009a37a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009a32f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009a32f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009a316`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009a316`

## string_xrefs

- `0x18009a35c`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall wil::GetActivationFactory<Windows::Internal::StateRepository::IApplicationStatics>(_QWORD *a1)
{
  unsigned int v2; // eax
  UINT32 v3; // edx
  HRESULT v4; // eax
  int ActivationFactory; // eax
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF
  HSTRING string; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *a1 = 0;
  string = 0;
  v2 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x2Cu);
  v3 = v2 - 1;
  if ( v2 > 0x2C )
    v3 = 44;
  v4 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Application", v3, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    RaiseException(v4, 1u, 0, 0);
    JUMPOUT(0x18009A380LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, a1);
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
0x18009a2b0  mov     [rsp+arg_8], rbx
0x18009a2b5  push    rdi
0x18009a2b6  sub     rsp, 60h
0x18009a2ba  mov     rax, cs:__security_cookie
0x18009a2c1  xor     rax, rsp
0x18009a2c4  mov     [rsp+68h+var_18], rax
0x18009a2c9  mov     rbx, rcx
0x18009a2cc  mov     [rsp+68h+var_40], rcx
0x18009a2d1  mov     [rsp+68h+var_48], 0
0x18009a2d9  mov     [rsp+68h+var_48], 1; int
0x18009a2e1  mov     qword ptr [rcx], 0
0x18009a2e8  mov     [rsp+68h+string], 0
0x18009a2f1  mov     edi, 2Ch ; ','
0x18009a2f6  mov     ecx, edi; unsigned int
0x18009a2f8  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18009a2fd  lea     edx, [rax-1]
0x18009a300  cmp     eax, edi
0x18009a302  cmova   edx, edi; length
0x18009a305  lea     r9, [rsp+68h+string]; string
0x18009a30a  lea     r8, [rsp+68h+hstringHeader]; hstringHeader
0x18009a30f  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x18009a316  call    cs:__imp_WindowsCreateStringReference
0x18009a31c  test    eax, eax
0x18009a31e  js      short loc_18009A36E
0x18009a320  mov     r8, rbx
0x18009a323  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x18009a32a  mov     rcx, [rsp+68h+string]
0x18009a32f  call    cs:__imp_RoGetActivationFactory
0x18009a335  mov     rcx, [rsp+68h]; this
0x18009a33a  test    eax, eax
0x18009a33c  js      short loc_18009A359
0x18009a33e  mov     rax, rbx
0x18009a341  mov     rcx, [rsp+68h+var_18]
0x18009a346  xor     rcx, rsp; StackCookie
0x18009a349  call    __security_check_cookie
0x18009a34e  mov     rbx, [rsp+68h+arg_8]
0x18009a353  add     rsp, 60h
0x18009a357  pop     rdi
0x18009a358  retn
0x18009a359  mov     r9d, eax; char *
0x18009a35c  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18009a363  mov     edx, 744h; void *
0x18009a368  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009a36e  xor     r9d, r9d; lpArguments
0x18009a371  xor     r8d, r8d; nNumberOfArguments
0x18009a374  lea     edx, [r9+1]; dwExceptionFlags
0x18009a378  mov     ecx, eax; dwExceptionCode
0x18009a37a  call    cs:__imp_RaiseException
```
