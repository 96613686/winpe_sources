# CSyncSettingsProvider::InitializeProcessInformation(ulong)

- ea: `0x1802e6ed8`
- end: `0x1802e70df`
- name: `?InitializeProcessInformation@CSyncSettingsProvider@@AEAAJK@Z`
- size: `519`
- prototype: `int(CSyncSettingsProvider *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1802e6df4`

## callees

- `0x1800416a0`
- `0x1800a0f20`
- `0x18010e138`
- `0x18018e5b4`
- `0x1802e6ed8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e6f7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e6f8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e7000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e7063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e6f7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e6f8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e7000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802e7063`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1802e6f30`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1802e6f30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802e70a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1802e70a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1802e6fbc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1802e6fbc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802e6f6a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802e6ff0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802e6f6a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1802e6ff0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802e6ef9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802e6ef9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1802e7053`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1802e7053`

## pseudocode

```c
__int64 __fastcall CSyncSettingsProvider::InitializeProcessInformation(CSyncSettingsProvider *this, DWORD a2)
{
  signed int Error; // edi
  void *v4; // rbx
  PSID *v5; // rbx
  signed int LastError; // eax
  signed int v7; // eax
  signed int v8; // eax
  LPWSTR StringSid; // [rsp+30h] [rbp-20h] BYREF
  __int64 v11; // [rsp+38h] [rbp-18h]
  __int64 v12; // [rsp+40h] [rbp-10h]
  void *TokenHandle; // [rsp+70h] [rbp+20h] BYREF
  DWORD TokenInformationLength; // [rsp+78h] [rbp+28h] BYREF
  HANDLE v15; // [rsp+80h] [rbp+30h] BYREF

  *((_DWORD *)this + 8) = a2;
  Error = 0;
  v15 = OpenProcess(0x400u, 0, a2);
  v4 = v15;
  if ( !v15 )
    Error = ResultFromLastError();
  TokenHandle = 0;
  if ( Error >= 0 && !OpenProcessToken(v4, 8u, &TokenHandle) )
    Error = ResultFromLastError();
  v5 = 0;
  if ( Error >= 0 )
  {
    TokenInformationLength = 0;
    if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength) || GetLastError() == 122 )
      goto LABEL_12;
    LastError = GetLastError();
    Error = LastError;
    if ( LastError > 0 )
      Error = (unsigned __int16)LastError | 0x80070000;
    if ( Error >= 0 )
    {
LABEL_12:
      if ( TokenInformationLength > 8 )
      {
        v5 = (PSID *)LocalAlloc(0, TokenInformationLength);
        if ( v5 )
        {
          if ( !GetTokenInformation(
                  TokenHandle,
                  TokenAppContainerSid,
                  v5,
                  TokenInformationLength,
                  &TokenInformationLength) )
          {
            v7 = GetLastError();
            Error = v7;
            if ( v7 > 0 )
              Error = (unsigned __int16)v7 | 0x80070000;
          }
        }
        else
        {
          Error = -2147024882;
        }
      }
      else
      {
        Error = -2147024809;
      }
    }
  }
  StringSid = 0;
  v11 = 0;
  v12 = 0;
  if ( Error >= 0 )
  {
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&StringSid);
    v11 = -1;
    v12 = -1;
    if ( ConvertSidToStringSidW(*v5, &StringSid) )
      goto LABEL_24;
    v8 = GetLastError();
    Error = v8;
    if ( v8 > 0 )
      Error = (unsigned __int16)v8 | 0x80070000;
    if ( Error >= 0 )
    {
LABEL_24:
      if ( StringSid )
        Error = Windows::Internal::String::_InitializeHelper((HSTRING *)this + 3, StringSid);
      else
        Error = -2147467261;
    }
  }
  if ( v5 )
    LocalFree(v5);
  Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&StringSid);
  CAutoHandle<void *>::~CAutoHandle<void *>(&TokenHandle);
  CAutoHandle<void *>::~CAutoHandle<void *>(&v15);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1802e6ed8  mov     [rsp-18h+arg_18], rbx
0x1802e6edd  push    rbp
0x1802e6ede  push    rsi
0x1802e6edf  push    rdi
0x1802e6ee0  mov     rbp, rsp
0x1802e6ee3  sub     rsp, 50h
0x1802e6ee7  mov     [rcx+20h], edx
0x1802e6eea  mov     rsi, rcx
0x1802e6eed  mov     r8d, edx; dwProcessId
0x1802e6ef0  mov     ecx, 400h; dwDesiredAccess
0x1802e6ef5  xor     edx, edx; bInheritHandle
0x1802e6ef7  xor     edi, edi
0x1802e6ef9  call    cs:__imp_OpenProcess
0x1802e6f00  nop     dword ptr [rax+rax+00h]
0x1802e6f05  mov     [rbp+arg_10], rax
0x1802e6f09  mov     rbx, rax
0x1802e6f0c  test    rax, rax
0x1802e6f0f  jnz     short loc_1802E6F18
0x1802e6f11  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1802e6f16  mov     edi, eax
0x1802e6f18  mov     [rbp+TokenHandle], 0
0x1802e6f20  test    edi, edi
0x1802e6f22  js      short loc_1802E6F47
0x1802e6f24  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1802e6f28  mov     edx, 8; DesiredAccess
0x1802e6f2d  mov     rcx, rbx; ProcessHandle
0x1802e6f30  call    cs:__imp_OpenProcessToken
0x1802e6f37  nop     dword ptr [rax+rax+00h]
0x1802e6f3c  test    eax, eax
0x1802e6f3e  jnz     short loc_1802E6F47
0x1802e6f40  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1802e6f45  mov     edi, eax
0x1802e6f47  xor     ebx, ebx
0x1802e6f49  test    edi, edi
0x1802e6f4b  js      loc_1802E701B
0x1802e6f51  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1802e6f55  lea     rax, [rbp+TokenInformationLength]
0x1802e6f59  xor     r9d, r9d; TokenInformationLength
0x1802e6f5c  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x1802e6f61  xor     r8d, r8d; TokenInformation
0x1802e6f64  mov     [rbp+TokenInformationLength], ebx
0x1802e6f67  lea     edx, [rbx+1Fh]; TokenInformationClass
0x1802e6f6a  call    cs:__imp_GetTokenInformation
0x1802e6f71  nop     dword ptr [rax+rax+00h]
0x1802e6f76  test    eax, eax
0x1802e6f78  jnz     short loc_1802E6FAA
0x1802e6f7a  call    cs:__imp_GetLastError
0x1802e6f81  nop     dword ptr [rax+rax+00h]
0x1802e6f86  cmp     eax, 7Ah ; 'z'
0x1802e6f89  jz      short loc_1802E6FAA
0x1802e6f8b  call    cs:__imp_GetLastError
0x1802e6f92  nop     dword ptr [rax+rax+00h]
0x1802e6f97  mov     edi, eax
0x1802e6f99  test    eax, eax
0x1802e6f9b  jle     short loc_1802E6FA6
0x1802e6f9d  movzx   edi, ax
0x1802e6fa0  or      edi, 80070000h
0x1802e6fa6  test    edi, edi
0x1802e6fa8  js      short loc_1802E701B
0x1802e6faa  cmp     [rbp+TokenInformationLength], 8
0x1802e6fae  ja      short loc_1802E6FB7
0x1802e6fb0  mov     edi, 80070057h
0x1802e6fb5  jmp     short loc_1802E701B
0x1802e6fb7  mov     edx, [rbp+TokenInformationLength]; uBytes
0x1802e6fba  xor     ecx, ecx; uFlags
0x1802e6fbc  call    cs:__imp_LocalAlloc
0x1802e6fc3  nop     dword ptr [rax+rax+00h]
0x1802e6fc8  mov     rbx, rax
0x1802e6fcb  test    rax, rax
0x1802e6fce  jnz     short loc_1802E6FD7
0x1802e6fd0  mov     edi, 8007000Eh
0x1802e6fd5  jmp     short loc_1802E701B
0x1802e6fd7  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1802e6fdb  lea     rax, [rbp+TokenInformationLength]
0x1802e6fdf  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1802e6fe3  mov     r8, rbx; TokenInformation
0x1802e6fe6  mov     edx, 1Fh; TokenInformationClass
0x1802e6feb  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x1802e6ff0  call    cs:__imp_GetTokenInformation
0x1802e6ff7  nop     dword ptr [rax+rax+00h]
0x1802e6ffc  test    eax, eax
0x1802e6ffe  jnz     short loc_1802E701B
0x1802e7000  call    cs:__imp_GetLastError
0x1802e7007  nop     dword ptr [rax+rax+00h]
0x1802e700c  mov     edi, eax
0x1802e700e  test    eax, eax
0x1802e7010  jle     short loc_1802E701B
0x1802e7012  movzx   edi, ax
0x1802e7015  or      edi, 80070000h
0x1802e701b  mov     [rbp+StringSid], 0
0x1802e7023  mov     [rbp+var_18], 0
0x1802e702b  mov     [rbp+var_10], 0
0x1802e7033  test    edi, edi
0x1802e7035  js      short loc_1802E709D
0x1802e7037  lea     rcx, [rbp+StringSid]
0x1802e703b  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x1802e7040  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802e7044  lea     rdx, [rbp+StringSid]; StringSid
0x1802e7048  mov     [rbp+var_18], rax
0x1802e704c  mov     [rbp+var_10], rax
0x1802e7050  mov     rcx, [rbx]; Sid
0x1802e7053  call    cs:__imp_ConvertSidToStringSidW
0x1802e705a  nop     dword ptr [rax+rax+00h]
0x1802e705f  test    eax, eax
0x1802e7061  jnz     short loc_1802E7082
0x1802e7063  call    cs:__imp_GetLastError
0x1802e706a  nop     dword ptr [rax+rax+00h]
0x1802e706f  mov     edi, eax
0x1802e7071  test    eax, eax
0x1802e7073  jle     short loc_1802E707E
0x1802e7075  movzx   edi, ax
0x1802e7078  or      edi, 80070000h
0x1802e707e  test    edi, edi
0x1802e7080  js      short loc_1802E709D
0x1802e7082  mov     rdx, [rbp+StringSid]; unsigned __int16 *
0x1802e7086  test    rdx, rdx
0x1802e7089  jz      short loc_1802E7098
0x1802e708b  lea     rcx, [rsi+18h]; this
0x1802e708f  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x1802e7094  mov     edi, eax
0x1802e7096  jmp     short loc_1802E709D
0x1802e7098  mov     edi, 80004003h
0x1802e709d  test    rbx, rbx
0x1802e70a0  jz      short loc_1802E70B1
0x1802e70a2  mov     rcx, rbx; hMem
0x1802e70a5  call    cs:__imp_LocalFree
0x1802e70ac  nop     dword ptr [rax+rax+00h]
0x1802e70b1  lea     rcx, [rbp+StringSid]
0x1802e70b5  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x1802e70ba  lea     rcx, [rbp+TokenHandle]
0x1802e70be  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x1802e70c3  lea     rcx, [rbp+arg_10]
0x1802e70c7  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x1802e70cc  mov     rbx, [rsp+50h+arg_18]
0x1802e70d4  mov     eax, edi
0x1802e70d6  add     rsp, 50h
0x1802e70da  pop     rdi
0x1802e70db  pop     rsi
0x1802e70dc  pop     rbp
0x1802e70dd  retn
```
