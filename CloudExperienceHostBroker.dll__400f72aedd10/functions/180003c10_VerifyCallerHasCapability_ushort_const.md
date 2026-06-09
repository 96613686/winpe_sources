# VerifyCallerHasCapability(ushort const *)

- ea: `0x180003c10`
- end: `0x180003eff`
- name: `?VerifyCallerHasCapability@@YAJPEBG@Z`
- size: `751`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003ae0`
- `0x18001c714`
- `0x18002009c`
- `0x180030454`
- `0x180031fac`

## callees

- `0x180003c10`
- `0x180004000`
- `0x180006330`
- `0x180008320`
- `0x180008344`
- `0x180035768`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180003cdf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180003cdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180003dda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180003dda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ec1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ecc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ec1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ecc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180003c60`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180003c60`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180003c8a`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180003c8a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180003d10`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180003d10`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180003d4d`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180003d4d`

## string_xrefs

- `0x180003c2f`: `TestIsCxhBrokerUnderTest`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall VerifyCallerHasCapability(const unsigned __int16 *a1)
{
  HRESULT v2; // eax
  int Error; // ebx
  void *v4; // rcx
  char *v5; // rcx
  int v6; // eax
  bool v7; // di
  void *v9; // rcx
  int pdwType; // [rsp+20h] [rbp-30h]
  HANDLE ProcessHandle; // [rsp+40h] [rbp-10h] BYREF
  void *phNewToken; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  void *ppInterface; // [rsp+78h] [rbp+28h] BYREF
  int pvData; // [rsp+80h] [rbp+30h] BYREF
  DWORD pcbData; // [rsp+88h] [rbp+38h] BYREF

  pcbData = 4;
  pvData = 0;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\TestHooks",
          L"TestIsCxhBrokerUnderTest",
          0x20000010u,
          0,
          &pvData,
          &pcbData)
    && pvData == 1 )
  {
    return 0;
  }
  ProcessHandle = 0;
  ppInterface = 0;
  Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(&ppInterface);
  v2 = CoGetCallContext(&GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, &ppInterface);
  Error = v2;
  if ( v2 >= 0 )
  {
    Error = (*(__int64 (__fastcall **)(void *, __int64, HANDLE *))(*(_QWORD *)ppInterface + 24LL))(
              ppInterface,
              4096,
              &ProcessHandle);
    if ( Error >= 0 )
      goto LABEL_4;
    Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(&ppInterface);
LABEL_29:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity_capability.cpp",
      (const char *)(unsigned int)Error,
      pdwType);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ProcessHandle);
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\ActivatableClassRestrictedToCapability.h",
      (const char *)(unsigned int)Error,
      pdwType);
    return (unsigned int)Error;
  }
  if ( v2 != -2147417833 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
      (const char *)(unsigned int)v2,
      pdwType);
    v9 = ppInterface;
    if ( ppInterface )
    {
      ppInterface = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
    }
    goto LABEL_29;
  }
  ProcessHandle = GetCurrentProcess();
LABEL_4:
  v4 = ppInterface;
  if ( ppInterface )
  {
    ppInterface = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 16LL))(v4);
  }
  phNewToken = 0;
  ppInterface = 0;
  if ( OpenProcessToken(ProcessHandle, 0xEu, &ppInterface) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    if ( DuplicateTokenEx(ppInterface, 0xCu, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
      Error = 0;
    else
      Error = ResultFromKnownLastError();
  }
  v5 = (char *)ppInterface;
  ppInterface = 0;
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  if ( Error < 0 )
  {
    v7 = 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity_capability.cpp",
      (const char *)(unsigned int)Error,
      pdwType);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
  }
  else
  {
    LOBYTE(ppInterface) = 0;
    v6 = CapabilityCheck(phNewToken, a1, &ppInterface);
    if ( v6 < 0 )
    {
      v7 = 0;
      Error = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0xE,
                (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity_capability.cpp",
                (const char *)(unsigned int)v6,
                pdwType);
    }
    else
    {
      Error = 0;
      v7 = (_BYTE)ppInterface != 0;
    }
    if ( (char *)phNewToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(phNewToken);
  }
  if ( (char *)ProcessHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(ProcessHandle);
  if ( Error < 0 )
    goto LABEL_19;
  if ( v7 )
    return 0;
  return 2147942405LL;
}

```

## disassembly

```asm
0x180003c10  mov     [rsp-18h+arg_0], rbx
0x180003c15  push    rbp
0x180003c16  push    rsi
0x180003c17  push    rdi
0x180003c18  mov     rbp, rsp
0x180003c1b  sub     rsp, 50h
0x180003c1f  lea     rax, [rbp+arg_18]
0x180003c23  mov     [rbp+arg_18], 4
0x180003c2a  mov     [rsp+50h+pcbData], rax; pcbData
0x180003c2f  lea     r8, Value; "TestIsCxhBrokerUnderTest"
0x180003c36  lea     rax, [rbp+arg_10]
0x180003c3a  mov     rdi, rcx
0x180003c3d  xor     esi, esi
0x180003c3f  mov     [rsp+50h+pvData], rax; pvData
0x180003c44  mov     r9d, 20000010h; dwFlags
0x180003c4a  mov     [rsp+50h+pdwType], rsi; int
0x180003c4f  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180003c56  mov     [rbp+arg_10], esi
0x180003c59  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180003c60  call    cs:__imp_RegGetValueW
0x180003c66  test    eax, eax
0x180003c68  jz      loc_180003DFD
0x180003c6e  lea     rcx, [rbp+ppInterface]
0x180003c72  mov     [rbp+ProcessHandle], rsi
0x180003c76  mov     [rbp+ppInterface], rsi
0x180003c7a  call    ?InternalRelease@?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(void)
0x180003c7f  lea     rdx, [rbp+ppInterface]; ppInterface
0x180003c83  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x180003c8a  call    cs:__imp_CoGetCallContext
0x180003c90  mov     ebx, eax
0x180003c92  test    eax, eax
0x180003c94  js      loc_180003DD3
0x180003c9a  mov     rcx, [rbp+ppInterface]
0x180003c9e  lea     r8, [rbp+ProcessHandle]
0x180003ca2  mov     edx, 1000h
0x180003ca7  mov     rax, [rcx]
0x180003caa  mov     rax, [rax+18h]
0x180003cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cb3  mov     ebx, eax
0x180003cb5  test    eax, eax
0x180003cb7  js      loc_180003E61
0x180003cbd  mov     rcx, [rbp+ppInterface]
0x180003cc1  test    rcx, rcx
0x180003cc4  jnz     loc_180003E6C
0x180003cca  mov     rcx, [rbp+ProcessHandle]; ProcessHandle
0x180003cce  lea     r8, [rbp+ppInterface]; TokenHandle
0x180003cd2  mov     edx, 0Eh; DesiredAccess
0x180003cd7  mov     [rbp+phNewToken], rsi
0x180003cdb  mov     [rbp+ppInterface], rsi
0x180003cdf  call    cs:__imp_OpenProcessToken
0x180003ce5  test    eax, eax
0x180003ce7  jz      loc_180003DE9
0x180003ced  mov     rcx, [rbp+ppInterface]; hExistingToken
0x180003cf1  lea     rax, [rbp+phNewToken]
0x180003cf5  mov     [rsp+50h+pvData], rax; phNewToken
0x180003cfa  mov     r9d, 2; ImpersonationLevel
0x180003d00  xor     r8d, r8d; lpTokenAttributes
0x180003d03  mov     dword ptr [rsp+50h+pdwType], 2; int
0x180003d0b  mov     edx, 0Ch; dwDesiredAccess
0x180003d10  call    cs:__imp_DuplicateTokenEx
0x180003d16  test    eax, eax
0x180003d18  jz      loc_180003E81
0x180003d1e  mov     ebx, esi
0x180003d20  mov     rcx, [rbp+ppInterface]; hObject
0x180003d24  mov     [rbp+ppInterface], rsi
0x180003d28  lea     rax, [rcx-1]
0x180003d2c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003d30  jbe     loc_180003E8D
0x180003d36  test    ebx, ebx
0x180003d38  js      loc_180003E98
0x180003d3e  mov     rcx, [rbp+phNewToken]
0x180003d42  lea     r8, [rbp+ppInterface]
0x180003d46  mov     rdx, rdi
0x180003d49  mov     byte ptr [rbp+ppInterface], sil
0x180003d4d  call    cs:__imp_CapabilityCheck
0x180003d53  test    eax, eax
0x180003d55  js      short loc_180003DB4
0x180003d57  cmp     byte ptr [rbp+ppInterface], sil
0x180003d5b  mov     ebx, esi
0x180003d5d  setnz   dil
0x180003d61  mov     rcx, [rbp+phNewToken]; hObject
0x180003d65  lea     rax, [rcx-1]
0x180003d69  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003d6d  jbe     loc_180003EC1
0x180003d73  mov     rcx, [rbp+ProcessHandle]; hObject
0x180003d77  lea     rax, [rcx-1]
0x180003d7b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003d7f  jbe     loc_180003ECC
0x180003d85  test    ebx, ebx
0x180003d87  jns     loc_180003ED7
0x180003d8d  mov     rcx, [rbp+18h]; this
0x180003d91  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\Activ"...
0x180003d98  mov     r9d, ebx; char *
0x180003d9b  mov     edx, 27h ; '''; void *
0x180003da0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003da5  mov     eax, ebx
0x180003da7  mov     rbx, [rsp+50h+arg_0]
0x180003dac  add     rsp, 50h
0x180003db0  pop     rdi
0x180003db1  pop     rsi
0x180003db2  pop     rbp
0x180003db3  retn
0x180003db4  mov     rcx, [rbp+18h]; this
0x180003db8  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180003dbf  xor     dil, dil
0x180003dc2  mov     r9d, eax; char *
0x180003dc5  mov     edx, 0Eh; void *
0x180003dca  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180003dcf  mov     ebx, eax
0x180003dd1  jmp     short loc_180003D61
0x180003dd3  cmp     eax, 80010117h
0x180003dd8  jnz     short loc_180003E16
0x180003dda  call    cs:__imp_GetCurrentProcess
0x180003de0  mov     [rbp+ProcessHandle], rax
0x180003de4  jmp     loc_180003CBD
0x180003de9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180003dee  mov     ebx, eax
0x180003df0  test    eax, eax
0x180003df2  js      loc_180003D20
0x180003df8  jmp     loc_180003CED
0x180003dfd  cmp     [rbp+arg_10], 1
0x180003e01  jnz     loc_180003C6E
0x180003e07  mov     rbx, [rsp+50h+arg_0]
0x180003e0c  xor     eax, eax
0x180003e0e  add     rsp, 50h
0x180003e12  pop     rdi
0x180003e13  pop     rsi
0x180003e14  pop     rbp
0x180003e15  retn
0x180003e16  mov     rcx, [rbp+18h]; this
0x180003e1a  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180003e21  mov     r9d, eax; char *
0x180003e24  mov     edx, 58h ; 'X'; void *
0x180003e29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e2e  mov     rcx, [rbp+ppInterface]
0x180003e32  test    rcx, rcx
0x180003e35  jnz     loc_180003EEA
0x180003e3b  mov     rcx, [rbp+18h]; this
0x180003e3f  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180003e46  mov     r9d, ebx; char *
0x180003e49  mov     edx, 23h ; '#'; void *
0x180003e4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e53  lea     rcx, [rbp+ProcessHandle]
0x180003e57  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180003e5c  jmp     loc_180003D8D
0x180003e61  lea     rcx, [rbp+ppInterface]
0x180003e65  call    ?InternalRelease@?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(void)
0x180003e6a  jmp     short loc_180003E3B
0x180003e6c  mov     [rbp+ppInterface], rsi
0x180003e70  mov     rax, [rcx]
0x180003e73  mov     rax, [rax+10h]
0x180003e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e7c  jmp     loc_180003CCA
0x180003e81  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180003e86  mov     ebx, eax
0x180003e88  jmp     loc_180003D20
0x180003e8d  call    cs:__imp_CloseHandle
0x180003e93  jmp     loc_180003D36
0x180003e98  mov     rcx, [rbp+18h]; this
0x180003e9c  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180003ea3  mov     r9d, ebx; char *
0x180003ea6  mov     edx, 19h; void *
0x180003eab  xor     dil, dil
0x180003eae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003eb3  lea     rcx, [rbp+phNewToken]
0x180003eb7  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180003ebc  jmp     loc_180003D73
0x180003ec1  call    cs:__imp_CloseHandle
0x180003ec7  jmp     loc_180003D73
0x180003ecc  call    cs:__imp_CloseHandle
0x180003ed2  jmp     loc_180003D85
0x180003ed7  test    dil, dil
0x180003eda  jnz     loc_180003E07
0x180003ee0  mov     eax, 80070005h
0x180003ee5  jmp     loc_180003DA7
0x180003eea  mov     [rbp+ppInterface], rsi
0x180003eee  mov     rax, [rcx]
0x180003ef1  mov     rax, [rax+10h]
0x180003ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003efa  jmp     loc_180003E3B
```
