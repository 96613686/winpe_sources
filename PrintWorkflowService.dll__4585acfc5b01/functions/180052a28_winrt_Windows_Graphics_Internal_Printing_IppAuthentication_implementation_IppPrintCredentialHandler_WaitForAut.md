# winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler::WaitForAuthResultOrProcessExit(ulong)

- ea: `0x180052a28`
- end: `0x180052aba`
- name: `?WaitForAuthResultOrProcessExit@IppPrintCredentialHandler@implementation@IppAuthentication@Printing@Internal@Graphics@Windows@winrt@@AEAAXK@Z`
- size: `146`
- prototype: `void(winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180051e00`

## callees

- `0x1800127a4`
- `0x1800166a8`
- `0x180023664`
- `0x180052a28`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180052a3b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180052a3b`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180052a73`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180052a73`

## string_xrefs

- `0x180052a93`: `onecoreuap\printscan\print\workflow\broker\ipp_auth_lib\ippprintcredentialhandler.cpp`
- `0x180052aa8`: `onecoreuap\printscan\print\workflow\broker\ipp_auth_lib\ippprintcredentialhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::Windows::Graphics::Internal::Printing::IppAuthentication::implementation::IppPrintCredentialHandler::WaitForAuthResultOrProcessExit(
        HANDLE *this,
        DWORD a2)
{
  HANDLE v3; // rax
  const char *v4; // r9
  HANDLE Handles[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HANDLE v7; // [rsp+50h] [rbp+18h] BYREF

  v3 = OpenProcess(0x101000u, 0, a2);
  v7 = v3;
  if ( !v3 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\ipp_auth_lib\\ippprintcredentialhandler.cpp",
      v4);
  Handles[0] = this[5];
  Handles[1] = v3;
  if ( WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\ipp_auth_lib\\ippprintcredentialhandler.cpp",
      (const char *)0x8000FFFFLL,
      (int)Handles[0]);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v7);
}

```

## disassembly

```asm
0x180052a28  push    rbx
0x180052a2a  sub     rsp, 30h
0x180052a2e  mov     rbx, rcx
0x180052a31  mov     r8d, edx; dwProcessId
0x180052a34  xor     edx, edx; bInheritHandle
0x180052a36  mov     ecx, 101000h; dwDesiredAccess
0x180052a3b  call    cs:__imp_OpenProcess
0x180052a41  mov     [rsp+38h+arg_10], rax
0x180052a46  mov     rcx, [rsp+38h]; this
0x180052a4b  test    rax, rax
0x180052a4e  jz      short loc_180052AA8
0x180052a50  mov     rcx, [rbx+28h]
0x180052a54  mov     [rsp+38h+Handles], rcx; int
0x180052a59  mov     [rsp+38h+var_10], rax
0x180052a5e  mov     rbx, [rsp+38h]
0x180052a63  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180052a67  xor     r8d, r8d; bWaitAll
0x180052a6a  lea     rdx, [rsp+38h+Handles]; lpHandles
0x180052a6f  lea     ecx, [r8+2]; nCount
0x180052a73  call    cs:__imp_WaitForMultipleObjects
0x180052a79  test    eax, eax
0x180052a7b  jnz     short loc_180052A8D
0x180052a7d  lea     rcx, [rsp+38h+arg_10]
0x180052a82  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180052a87  add     rsp, 30h
0x180052a8b  pop     rbx
0x180052a8c  retn
0x180052a8d  mov     r9d, 8000FFFFh; char *
0x180052a93  lea     r8, aOnecoreuapPrin_9; "onecoreuap\\printscan\\print\\workflow"...
0x180052a9a  mov     edx, 0C7h; void *
0x180052a9f  mov     rcx, rbx; this
0x180052aa2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180052aa8  lea     r8, aOnecoreuapPrin_9; "onecoreuap\\printscan\\print\\workflow"...
0x180052aaf  mov     edx, 0C1h; void *
0x180052ab4  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
