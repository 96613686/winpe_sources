# GetActivationFactory<Windows::Internal::StateRepository::IPackageStatics>(ushort const *)

- ea: `0x180035200`
- end: `0x1800352c9`
- name: `??$GetActivationFactory@UIPackageStatics@StateRepository@Internal@Windows@@@@YA?AV?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@PEBG@Z`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180034ef8`

## callees

- `0x180035200`
- `0x1800353b4`
- `0x1800593bc`
- `0x18006d6a4`
- `0x180075e60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003527b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003527b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180035266`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180035266`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall GetActivationFactory<Windows::Internal::StateRepository::IPackageStatics>(_QWORD *a1)
{
  unsigned int v2; // eax
  UINT32 v3; // edx
  HRESULT v4; // eax
  int v5; // eax
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF
  HSTRING string; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *a1 = 0;
  string = 0;
  v2 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x28u);
  v3 = v2 - 1;
  if ( v2 > 0x28 )
    v3 = 40;
  v4 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Package", v3, &hstringHeader, &string);
  if ( v4 < 0 )
    RaiseException(v4, 1u, 0, 0);
  v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
         string,
         a1);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\util.h",
      (const char *)(unsigned int)v5,
      1);
  return a1;
}

```

## disassembly

```asm
0x180035200  mov     [rsp+arg_8], rbx
0x180035205  push    rdi
0x180035206  sub     rsp, 60h
0x18003520a  mov     rax, cs:__security_cookie
0x180035211  xor     rax, rsp
0x180035214  mov     [rsp+68h+var_18], rax
0x180035219  mov     rbx, rcx
0x18003521c  mov     [rsp+68h+var_40], rcx
0x180035221  mov     [rsp+68h+var_48], 0
0x180035229  mov     qword ptr [rcx], 0
0x180035230  mov     [rsp+68h+var_48], 1; int
0x180035238  mov     [rsp+68h+string], 0
0x180035241  mov     edi, 28h ; '('
0x180035246  mov     ecx, edi; unsigned int
0x180035248  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18003524d  lea     edx, [rax-1]
0x180035250  cmp     eax, edi
0x180035252  cmova   edx, edi; length
0x180035255  lea     r9, [rsp+68h+string]; string
0x18003525a  lea     r8, [rsp+68h+hstringHeader]; hstringHeader
0x18003525f  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x180035266  call    cs:__imp_WindowsCreateStringReference
0x18003526c  test    eax, eax
0x18003526e  jns     short loc_180035282
0x180035270  xor     r9d, r9d; lpArguments
0x180035273  xor     r8d, r8d; nNumberOfArguments
0x180035276  lea     edx, [rdi-27h]; dwExceptionFlags
0x180035279  mov     ecx, eax; dwExceptionCode
0x18003527b  call    cs:__imp_RaiseException
0x180035281  nop
0x180035282  mov     rdx, rbx
0x180035285  mov     rcx, [rsp+68h+string]
0x18003528a  call    ??$GetActivationFactory@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>)
0x18003528f  mov     rcx, [rsp+68h]; this
0x180035294  test    eax, eax
0x180035296  jns     short loc_1800352AD
0x180035298  mov     r9d, eax; char *
0x18003529b  lea     r8, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800352a2  mov     edx, 98h; void *
0x1800352a7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800352ad  mov     rax, rbx
0x1800352b0  mov     rcx, [rsp+68h+var_18]
0x1800352b5  xor     rcx, rsp; StackCookie
0x1800352b8  call    __security_check_cookie
0x1800352bd  mov     rbx, [rsp+68h+arg_8]
0x1800352c2  add     rsp, 60h
0x1800352c6  pop     rdi
0x1800352c7  retn
```
