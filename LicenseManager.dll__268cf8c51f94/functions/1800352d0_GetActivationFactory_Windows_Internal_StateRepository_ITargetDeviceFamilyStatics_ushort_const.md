# GetActivationFactory<Windows::Internal::StateRepository::ITargetDeviceFamilyStatics>(ushort const *)

- ea: `0x1800352d0`
- end: `0x1800353ac`
- name: `??$GetActivationFactory@UITargetDeviceFamilyStatics@StateRepository@Internal@Windows@@@@YA?AV?$ComPtr@UITargetDeviceFamilyStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@PEBG@Z`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180034ef8`

## callees

- `0x180004738`
- `0x1800352d0`
- `0x1800353b4`
- `0x1800593bc`
- `0x180075e60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003534b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003534b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003536c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003536c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180035336`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180035336`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall GetActivationFactory<Windows::Internal::StateRepository::ITargetDeviceFamilyStatics>(_QWORD *a1)
{
  unsigned int v2; // eax
  UINT32 v3; // edx
  HRESULT v4; // eax
  HSTRING v5; // rbx
  int ActivationFactory; // eax
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF
  HSTRING string; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *a1 = 0;
  string = 0;
  v2 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x33u);
  v3 = v2 - 1;
  if ( v2 > 0x33 )
    v3 = 51;
  v4 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.TargetDeviceFamily", v3, &hstringHeader, &string);
  if ( v4 < 0 )
    RaiseException(v4, 1u, 0, 0);
  v5 = string;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a1);
  ActivationFactory = RoGetActivationFactory(v5, &GUID_cb3a2a28_41c0_4687_9ea6_c248191321de, a1);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\util.h",
      (const char *)(unsigned int)ActivationFactory,
      1);
  return a1;
}

```

## disassembly

```asm
0x1800352d0  mov     [rsp+arg_8], rbx
0x1800352d5  push    rdi
0x1800352d6  sub     rsp, 60h
0x1800352da  mov     rax, cs:__security_cookie
0x1800352e1  xor     rax, rsp
0x1800352e4  mov     [rsp+68h+var_18], rax
0x1800352e9  mov     rdi, rcx
0x1800352ec  mov     [rsp+68h+var_40], rcx
0x1800352f1  mov     [rsp+68h+var_48], 0
0x1800352f9  mov     qword ptr [rcx], 0
0x180035300  mov     [rsp+68h+var_48], 1; int
0x180035308  mov     [rsp+68h+string], 0
0x180035311  mov     ebx, 33h ; '3'
0x180035316  mov     ecx, ebx; unsigned int
0x180035318  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18003531d  lea     edx, [rax-1]
0x180035320  cmp     eax, ebx
0x180035322  cmova   edx, ebx; length
0x180035325  lea     r9, [rsp+68h+string]; string
0x18003532a  lea     r8, [rsp+68h+hstringHeader]; hstringHeader
0x18003532f  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_TargetDeviceFamily@@3QBGB; "Windows.Internal.StateRepository.Target"...
0x180035336  call    cs:__imp_WindowsCreateStringReference
0x18003533c  test    eax, eax
0x18003533e  jns     short loc_180035352
0x180035340  xor     r9d, r9d; lpArguments
0x180035343  xor     r8d, r8d; nNumberOfArguments
0x180035346  lea     edx, [rbx-32h]; dwExceptionFlags
0x180035349  mov     ecx, eax; dwExceptionCode
0x18003534b  call    cs:__imp_RaiseException
0x180035351  nop
0x180035352  mov     rbx, [rsp+68h+string]
0x180035357  mov     rcx, rdi
0x18003535a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003535f  mov     r8, rdi
0x180035362  lea     rdx, _GUID_cb3a2a28_41c0_4687_9ea6_c248191321de
0x180035369  mov     rcx, rbx
0x18003536c  call    cs:__imp_RoGetActivationFactory
0x180035372  mov     rcx, [rsp+68h]; this
0x180035377  test    eax, eax
0x180035379  jns     short loc_180035390
0x18003537b  mov     r9d, eax; char *
0x18003537e  lea     r8, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\licensem"...
0x180035385  mov     edx, 98h; void *
0x18003538a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180035390  mov     rax, rdi
0x180035393  mov     rcx, [rsp+68h+var_18]
0x180035398  xor     rcx, rsp; StackCookie
0x18003539b  call    __security_check_cookie
0x1800353a0  mov     rbx, [rsp+68h+arg_8]
0x1800353a5  add     rsp, 60h
0x1800353a9  pop     rdi
0x1800353aa  retn
```
