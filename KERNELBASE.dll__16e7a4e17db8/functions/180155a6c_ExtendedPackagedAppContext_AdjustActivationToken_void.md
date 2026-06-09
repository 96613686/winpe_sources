# ExtendedPackagedAppContext::AdjustActivationToken(void *)

- ea: `0x180155a6c`
- end: `0x180155c98`
- name: `?AdjustActivationToken@ExtendedPackagedAppContext@@AEAAJPEAX@Z`
- size: `556`
- prototype: `__int64 __fastcall(ExtendedPackagedAppContext *__hidden this, void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180028df0`

## callees

- `0x18002af0c`
- `0x180032f18`
- `0x180033d70`
- `0x18004cb70`
- `0x180058768`
- `0x1800765d0`
- `0x1800c9af0`
- `0x180107b98`
- `0x180123770`
- `0x18012d119`
- `0x180155a6c`
- `0x180188f10`

## import_xrefs

- `ntdll!_wcsicmp` at `0x180155c13`
- `ntdll!_wcsicmp` at `0x180155c13`
- `ext-ms-win-kernelbase-processthread-l1-2-0!BasepFreeActivationTokenInfo` at `0x180155b79`
- `ext-ms-win-kernelbase-processthread-l1-2-0!BasepFreeActivationTokenInfo` at `0x180155bc0`
- `ext-ms-win-kernelbase-processthread-l1-2-0!BasepFreeActivationTokenInfo` at `0x180155c58`
- `ext-ms-win-kernelbase-processthread-l1-2-0!BasepFreeActivationTokenInfo` at `0x180155c62`
- `ext-ms-win-kernelbase-processthread-l1-2-0!BasepFreeActivationTokenInfo` at `0x180155b79`
- `ext-ms-win-kernelbase-processthread-l1-2-0!BasepFreeActivationTokenInfo` at `0x180155bc0`
- `ext-ms-win-kernelbase-processthread-l1-2-0!BasepFreeActivationTokenInfo` at `0x180155c58`
- `ext-ms-win-kernelbase-processthread-l1-2-0!BasepFreeActivationTokenInfo` at `0x180155c62`
- `ext-ms-win-kernelbase-processthread-l1-2-0!BasepGetPackageActivationTokenForFilePath2` at `0x180155b04`
- `ext-ms-win-kernelbase-processthread-l1-2-0!BasepGetPackageActivationTokenForFilePath2` at `0x180155b95`
- `ext-ms-win-kernelbase-processthread-l1-2-0!BasepGetPackageActivationTokenForFilePath2` at `0x180155b04`
- `ext-ms-win-kernelbase-processthread-l1-2-0!BasepGetPackageActivationTokenForFilePath2` at `0x180155b95`

## string_xrefs

- `0x180155ad0`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180155b48`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180155b60`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180155bad`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`

## pseudocode

```c
__int64 __fastcall ExtendedPackagedAppContext::AdjustActivationToken(ExtendedPackagedAppContext *this, void *a2)
{
  bool v2; // zf
  HANDLE v3; // rdi
  const char *v5; // r9
  unsigned int LastError; // ebx
  __int64 v7; // rcx
  unsigned int PackageActivationTokenForFilePath2; // esi
  const unsigned __int16 *v9; // r8
  int PackagedDataForFileInternal; // eax
  unsigned int v11; // esi
  unsigned __int64 v12; // r9
  __int64 v13; // rdx
  unsigned int PackageFullNameFromToken; // eax
  __int128 v15; // xmm1
  HANDLE token[2]; // [rsp+20h] [rbp-E0h] BYREF
  HANDLE TokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 packageFullNameLength; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR packageFullName[128]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v2 = *((_DWORD *)this + 137) == 4;
  v3 = a2;
  TokenHandle = 0;
  if ( !v2 && !a2 )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(&TokenHandle);
    if ( !OpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0xAFu, &TokenHandle) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x3A9,
                    (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
                    v5);
      goto LABEL_19;
    }
    v3 = TokenHandle;
  }
  v7 = *((_QWORD *)this + 65);
  *(_OWORD *)token = 0;
  PackageActivationTokenForFilePath2 = BasepGetPackageActivationTokenForFilePath2(v7, v3, token);
  if ( PackageActivationTokenForFilePath2 - 2 <= 1 && !PathFileExistsW(*((LPCWSTR *)this + 65)) )
  {
    v9 = (const unsigned __int16 *)*((_QWORD *)this + 79);
    *(_BYTE *)this = 0;
    PackagedDataForFileInternal = PackagedCreateProcess::GetPackagedDataForFileInternal(0, v3, v9, this);
    v11 = PackagedDataForFileInternal;
    if ( PackagedDataForFileInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x170,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
        (const char *)(unsigned int)PackagedDataForFileInternal,
        (int)token[0]);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B4,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
        (const char *)v11,
        (int)token[0]);
      BasepFreeActivationTokenInfo(token);
      LastError = v11;
      goto LABEL_19;
    }
    PackageActivationTokenForFilePath2 = BasepGetPackageActivationTokenForFilePath2(*((_QWORD *)this + 65), v3, token);
  }
  if ( PackageActivationTokenForFilePath2 )
  {
    v12 = PackageActivationTokenForFilePath2;
    v13 = 953;
LABEL_13:
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)v13,
                  (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
                  (const char *)v12,
                  (unsigned int)token[0]);
    BasepFreeActivationTokenInfo(token);
    goto LABEL_19;
  }
  memset_0(packageFullName, 0, sizeof(packageFullName));
  packageFullNameLength = 128;
  PackageFullNameFromToken = GetPackageFullNameFromToken(token[0], &packageFullNameLength, packageFullName);
  if ( PackageFullNameFromToken )
  {
    v12 = PackageFullNameFromToken;
    v13 = 957;
    goto LABEL_13;
  }
  if ( _wcsicmp(packageFullName, (const wchar_t *)this + 131) )
  {
    BasepFreeActivationTokenInfo(token);
    LastError = -2147023728;
  }
  else
  {
    v15 = *((_OWORD *)this + 40);
    *((_OWORD *)this + 40) = *(_OWORD *)token;
    *((_QWORD *)this + 69) = *((_QWORD *)this + 80);
    *((_QWORD *)this + 70) = *((_QWORD *)this + 81);
    *(_OWORD *)token = v15;
    BasepFreeActivationTokenInfo(token);
    LastError = 0;
  }
LABEL_19:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x180155a6c  mov     [rsp-8+arg_10], rbx
0x180155a71  push    rbp
0x180155a72  push    rsi
0x180155a73  push    rdi
0x180155a74  lea     rbp, [rsp-50h]
0x180155a79  sub     rsp, 150h
0x180155a80  mov     rax, cs:__security_cookie
0x180155a87  xor     rax, rsp
0x180155a8a  mov     [rbp+60h+var_20], rax
0x180155a8e  cmp     dword ptr [rcx+224h], 4
0x180155a95  mov     rdi, rdx
0x180155a98  mov     rbx, rcx
0x180155a9b  mov     [rsp+160h+TokenHandle], 0
0x180155aa4  jz      short loc_180155AED
0x180155aa6  test    rdx, rdx
0x180155aa9  jnz     short loc_180155AED
0x180155aab  lea     rcx, [rsp+160h+TokenHandle]
0x180155ab0  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180155ab5  lea     r8, [rsp+160h+TokenHandle]; TokenHandle
0x180155aba  mov     edx, 0AFh; DesiredAccess
0x180155abf  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180155ac3  call    OpenProcessToken
0x180155ac8  test    eax, eax
0x180155aca  jnz     short loc_180155AE8
0x180155acc  mov     rcx, [rbp+68h]; this
0x180155ad0  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\processcreatio"...
0x180155ad7  mov     edx, 3A9h; void *
0x180155adc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180155ae1  mov     ebx, eax
0x180155ae3  jmp     loc_180155C6D
0x180155ae8  mov     rdi, [rsp+160h+TokenHandle]
0x180155aed  mov     rcx, [rbx+208h]
0x180155af4  lea     r8, [rsp+160h+token]
0x180155af9  xorps   xmm0, xmm0
0x180155afc  mov     rdx, rdi
0x180155aff  movups  xmmword ptr [rsp+160h+token], xmm0; unsigned int
0x180155b04  call    cs:__imp_BasepGetPackageActivationTokenForFilePath2
0x180155b0a  mov     esi, eax
0x180155b0c  lea     ecx, [rax-2]
0x180155b0f  cmp     ecx, 1
0x180155b12  ja      loc_180155B9D
0x180155b18  mov     rcx, [rbx+208h]; pszPath
0x180155b1f  call    PathFileExistsW
0x180155b24  test    eax, eax
0x180155b26  jnz     short loc_180155B9D
0x180155b28  mov     r8, [rbx+278h]; unsigned __int16 *
0x180155b2f  mov     r9, rbx; struct ExtendedPackagedAppContext *
0x180155b32  mov     rdx, rdi; void *
0x180155b35  mov     [rbx], al
0x180155b37  xor     ecx, ecx; Source
0x180155b39  call    ?GetPackagedDataForFileInternal@PackagedCreateProcess@@CAJPEBGPEAX0PEAVExtendedPackagedAppContext@@@Z; PackagedCreateProcess::GetPackagedDataForFileInternal(ushort const *,void *,ushort const *,ExtendedPackagedAppContext *)
0x180155b3e  mov     esi, eax
0x180155b40  test    eax, eax
0x180155b42  jns     short loc_180155B86
0x180155b44  mov     rcx, [rbp+68h]; this
0x180155b48  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\processcreatio"...
0x180155b4f  mov     r9d, eax; char *
0x180155b52  mov     edx, 170h; void *
0x180155b57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180155b5c  mov     rcx, [rbp+68h]; this
0x180155b60  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\processcreatio"...
0x180155b67  mov     r9d, esi; char *
0x180155b6a  mov     edx, 3B4h; void *
0x180155b6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180155b74  lea     rcx, [rsp+160h+token]
0x180155b79  call    cs:__imp_BasepFreeActivationTokenInfo
0x180155b7f  mov     ebx, esi
0x180155b81  jmp     loc_180155C6D
0x180155b86  mov     rcx, [rbx+208h]
0x180155b8d  lea     r8, [rsp+160h+token]
0x180155b92  mov     rdx, rdi
0x180155b95  call    cs:__imp_BasepGetPackageActivationTokenForFilePath2
0x180155b9b  mov     esi, eax
0x180155b9d  test    esi, esi
0x180155b9f  jz      short loc_180155BCB
0x180155ba1  mov     r9d, esi; char *
0x180155ba4  mov     edx, 3B9h; void *
0x180155ba9  mov     rcx, [rbp+68h]; this
0x180155bad  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\processcreatio"...
0x180155bb4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180155bb9  lea     rcx, [rsp+160h+token]
0x180155bbe  mov     ebx, eax
0x180155bc0  call    cs:__imp_BasepFreeActivationTokenInfo
0x180155bc6  jmp     loc_180155C6D
0x180155bcb  xor     edx, edx; Val
0x180155bcd  lea     rcx, [rsp+160h+packageFullName]; void *
0x180155bd2  mov     r8d, 100h; Size
0x180155bd8  call    memset_0
0x180155bdd  mov     rcx, [rsp+160h+token]; token
0x180155be2  lea     r8, [rsp+160h+packageFullName]; packageFullName
0x180155be7  lea     rdx, [rsp+160h+packageFullNameLength]; packageFullNameLength
0x180155bec  mov     [rsp+160h+packageFullNameLength], 80h
0x180155bf4  call    GetPackageFullNameFromToken
0x180155bf9  test    eax, eax
0x180155bfb  jz      short loc_180155C07
0x180155bfd  mov     r9d, eax
0x180155c00  mov     edx, 3BDh
0x180155c05  jmp     short loc_180155BA9
0x180155c07  lea     rdx, [rbx+106h]; String2
0x180155c0e  lea     rcx, [rsp+160h+packageFullName]; String1
0x180155c13  call    cs:__imp__wcsicmp
0x180155c19  lea     rcx, [rsp+160h+token]
0x180155c1e  test    eax, eax
0x180155c20  jnz     short loc_180155C62
0x180155c22  movups  xmm1, xmmword ptr [rbx+280h]
0x180155c29  movaps  xmm0, xmmword ptr [rsp+160h+token]
0x180155c2e  movdqu  xmmword ptr [rbx+280h], xmm0
0x180155c36  mov     rax, [rbx+280h]
0x180155c3d  mov     [rbx+228h], rax
0x180155c44  mov     rax, [rbx+288h]
0x180155c4b  mov     [rbx+230h], rax
0x180155c52  movdqa  xmmword ptr [rsp+160h+token], xmm1
0x180155c58  call    cs:__imp_BasepFreeActivationTokenInfo
0x180155c5e  xor     ebx, ebx
0x180155c60  jmp     short loc_180155C6D
0x180155c62  call    cs:__imp_BasepFreeActivationTokenInfo
0x180155c68  mov     ebx, 80070490h
0x180155c6d  lea     rcx, [rsp+160h+TokenHandle]
0x180155c72  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180155c77  mov     eax, ebx
0x180155c79  mov     rcx, [rbp+60h+var_20]
0x180155c7d  xor     rcx, rsp; StackCookie
0x180155c80  call    __security_check_cookie
0x180155c85  mov     rbx, [rsp+160h+arg_10]
0x180155c8d  add     rsp, 150h
0x180155c94  pop     rdi
0x180155c95  pop     rsi
0x180155c96  pop     rbp
0x180155c97  retn
```
