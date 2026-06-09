# winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_ImpersonateUserIfNeeded(void)

- ea: `0x180022b44`
- end: `0x180022bc6`
- name: `?_ImpersonateUserIfNeeded@IppQueuePropertyBagHandler@implementation@PrintScanBroker@Printing@Internal@Graphics@Windows@winrt@@AEAA_NXZ`
- size: `130`
- prototype: `bool(winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001bad4`
- `0x18001cce4`

## callees

- `0x18001c60c`
- `0x18001cfd4`
- `0x18001d058`
- `0x180022b44`
- `0x180035450`
- `0x1800356cc`

## string_xrefs

- `0x180022b6b`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`
- `0x180022b8f`: `onecoreuap\printscan\print\printscanbroker\class\ippqueuepropertybaghandler.cpp`
- `0x180022b5f`: `ImpersonateUser failed!`

## pseudocode

```c
char __fastcall winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler::_ImpersonateUserIfNeeded(
        winrt::Windows::Graphics::Internal::Printing::PrintScanBroker::implementation::IppQueuePropertyBagHandler *this)
{
  ULONG CallerSessionId; // eax
  PrintScanBrokerUtilities *v2; // rcx
  unsigned int v3; // eax
  char v4; // bl
  int CallerIntegrityLevel; // eax
  const char *v7; // [rsp+28h] [rbp-10h]
  const char *v8; // [rsp+30h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  CallerSessionId = PrintScanBrokerUtilities::GetCallerSessionId(this);
  if ( CallerSessionId )
  {
    v3 = PrintCore::UserImpersonationHelpers::ImpersonateUser(CallerSessionId);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x3D5,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
      (const char *)v3,
      (int)"ImpersonateUser failed!",
      v7);
    return 1;
  }
  else
  {
    v4 = 0;
    CallerIntegrityLevel = PrintScanBrokerUtilities::GetCallerIntegrityLevel(v2);
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x3DC,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\ippqueuepropertybaghandler.cpp",
      (const char *)0x80070005LL,
      CallerIntegrityLevel != 0x4000,
      (bool)"Caller is not running with SYSTEM level integrity!",
      v8);
  }
  return v4;
}

```

## disassembly

```asm
0x180022b44  push    rbx; char *
0x180022b46  sub     rsp, 30h
0x180022b4a  call    ?GetCallerSessionId@PrintScanBrokerUtilities@@YAKXZ; PrintScanBrokerUtilities::GetCallerSessionId(void)
0x180022b4f  test    eax, eax
0x180022b51  jz      short loc_180022B83
0x180022b53  mov     ecx, eax; SessionId
0x180022b55  call    ?ImpersonateUser@UserImpersonationHelpers@PrintCore@@SAJK@Z; PrintCore::UserImpersonationHelpers::ImpersonateUser(ulong)
0x180022b5a  mov     rcx, [rsp+38h]; this
0x180022b5f  lea     rdx, aImpersonateuse_1; "ImpersonateUser failed!"
0x180022b66  mov     qword ptr [rsp+38h+var_18], rdx; int
0x180022b6b  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\printscan"...
0x180022b72  mov     edx, 3D5h; void *
0x180022b77  mov     r9d, eax; char *
0x180022b7a  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180022b7f  mov     bl, 1
0x180022b81  jmp     short loc_180022BBE
0x180022b83  xor     bl, bl
0x180022b85  call    ?GetCallerIntegrityLevel@PrintScanBrokerUtilities@@YAKXZ; PrintScanBrokerUtilities::GetCallerIntegrityLevel(void)
0x180022b8a  mov     rcx, [rsp+38h]; this
0x180022b8f  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\printscan"...
0x180022b96  cmp     eax, 4000h
0x180022b9b  mov     r9d, 80070005h; char *
0x180022ba1  lea     rax, aCallerIsNotRun; "Caller is not running with SYSTEM level"...
0x180022ba8  setnz   dl
0x180022bab  mov     qword ptr [rsp+38h+var_10], rax; bool
0x180022bb0  mov     [rsp+38h+var_18], dl; char
0x180022bb4  mov     edx, 3DCh; void *
0x180022bb9  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180022bbe  mov     al, bl
0x180022bc0  add     rsp, 30h
0x180022bc4  pop     rbx
0x180022bc5  retn
```
