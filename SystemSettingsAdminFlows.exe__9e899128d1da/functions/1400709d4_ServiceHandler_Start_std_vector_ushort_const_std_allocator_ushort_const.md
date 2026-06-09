# ServiceHandler::Start(std::vector<ushort const *,std::allocator<ushort const *>> &)

- ea: `0x1400709d4`
- end: `0x140070b92`
- name: `?Start@ServiceHandler@@QEBAXAEAV?$vector@PEBGV?$allocator@PEBG@std@@@std@@@Z`
- size: `446`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1400708a8`

## callees

- `0x140005f30`
- `0x14002a2c0`
- `0x140055c64`
- `0x1400707d0`
- `0x1400709d4`
- `0x140070b98`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x140070afb`
- `KERNEL32!GetTickCount` at `0x140070b0c`
- `KERNEL32!GetTickCount` at `0x140070afb`
- `KERNEL32!GetTickCount` at `0x140070b0c`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x140070a6d`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x140070a6d`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x140070a26`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x140070aa5`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x140070aec`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x140070a26`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x140070aa5`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x140070aec`

## string_xrefs

- `0x140070a34`: `pcshell\shell\systemsettings\adminflows\accessibility\brlapiservice.cpp`
- `0x140070a7b`: `pcshell\shell\systemsettings\adminflows\accessibility\brlapiservice.cpp`
- `0x140070ab3`: `pcshell\shell\systemsettings\adminflows\accessibility\brlapiservice.cpp`
- `0x140070b2a`: `pcshell\shell\systemsettings\adminflows\accessibility\brlapiservice.cpp`
- `0x140070b48`: `pcshell\shell\systemsettings\adminflows\accessibility\brlapiservice.cpp`
- `0x140070b5d`: `pcshell\shell\systemsettings\adminflows\accessibility\brlapiservice.cpp`

## pseudocode

```c
DWORD __fastcall ServiceHandler::Start(SC_HANDLE *this, __int64 a2)
{
  SC_HANDLE v4; // rcx
  const char *v5; // r9
  DWORD result; // eax
  const char *v7; // r9
  const char *v8; // r9
  unsigned int WaitTime; // r15d
  const char *v10; // r9
  unsigned int v11; // ebx
  DWORD v12; // edi
  int pcbBytesNeeded; // [rsp+20h] [rbp-50h]
  DWORD v14; // [rsp+30h] [rbp-40h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-38h] BYREF
  unsigned int v16[4]; // [rsp+48h] [rbp-28h]
  int v17; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v17 = 0;
  v14 = 0;
  v4 = *this;
  *(_OWORD *)Buffer = 0;
  *(_OWORD *)v16 = 0;
  if ( !QueryServiceStatusEx(v4, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &v14) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x7D,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\brlapiservice.cpp",
      v5);
  result = *(_DWORD *)&Buffer[4] - 1;
  if ( ((*(_DWORD *)&Buffer[4] - 1) & 0xFFFFFFFD) == 0 )
  {
    ServiceHandler::Stop(this);
    if ( !StartServiceW(*this, (__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 3, *(LPCWSTR **)a2) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x8D,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\brlapiservice.cpp",
        v7);
    if ( !QueryServiceStatusEx(*this, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &v14) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x95,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\brlapiservice.cpp",
        v8);
LABEL_10:
    result = GetTickCount();
    v11 = v16[1];
    v12 = result;
    while ( *(_DWORD *)&Buffer[4] == 2 )
    {
      WaitTime = ServiceHandler::GetWaitTime((ServiceHandler *)2, v16[2]);
      if ( !QueryServiceStatusEx(*this, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &v14) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0xA5,
          (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\brlapiservice.cpp",
          v10);
      if ( v16[1] > v11 )
        goto LABEL_10;
      result = GetTickCount() - v12;
      if ( result > WaitTime )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xAF,
          (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\brlapiservice.cpp",
          (const char *)0x80070102LL,
          pcbBytesNeeded);
    }
    if ( *(_DWORD *)&Buffer[4] != 4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB4,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\brlapiservice.cpp",
        (const char *)0x80004005LL,
        pcbBytesNeeded);
  }
  return result;
}

```

## disassembly

```asm
0x1400709d4  mov     [rsp-28h+arg_10], rbx
0x1400709d9  push    rbp
0x1400709da  push    rsi
0x1400709db  push    rdi
0x1400709dc  push    r14
0x1400709de  push    r15
0x1400709e0  mov     rbp, rsp
0x1400709e3  sub     rsp, 70h
0x1400709e7  mov     rax, cs:__security_cookie
0x1400709ee  xor     rax, rsp
0x1400709f1  mov     [rbp+var_10], rax
0x1400709f5  xor     eax, eax
0x1400709f7  lea     r8, [rbp+Buffer]; lpBuffer
0x1400709fb  xorps   xmm0, xmm0
0x1400709fe  mov     [rbp+var_18], eax
0x140070a01  mov     [rbp+var_40], eax
0x140070a04  mov     rbx, rdx
0x140070a07  lea     rax, [rbp+var_40]
0x140070a0b  mov     rsi, rcx
0x140070a0e  mov     rcx, [rcx]; hService
0x140070a11  mov     r9d, 24h ; '$'; cbBufSize
0x140070a17  xor     edx, edx; InfoLevel
0x140070a19  mov     qword ptr [rsp+70h+pcbBytesNeeded], rax; pcbBytesNeeded
0x140070a1e  movups  xmmword ptr [rbp+Buffer], xmm0
0x140070a22  movups  xmmword ptr [rbp+var_28], xmm0
0x140070a26  call    cs:__imp_QueryServiceStatusEx
0x140070a2c  test    eax, eax
0x140070a2e  jnz     short loc_140070A44
0x140070a30  mov     rcx, [rbp+28h]; this
0x140070a34  lea     r8, aPcshellShellSy_7; "pcshell\\shell\\systemsettings\\adminfl"...
0x140070a3b  lea     edx, [rax+7Dh]; void *
0x140070a3e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140070a44  mov     eax, dword ptr [rbp+Buffer+4]
0x140070a47  dec     eax
0x140070a49  test    eax, 0FFFFFFFDh
0x140070a4e  jnz     loc_140070B72
0x140070a54  mov     rcx, rsi; this
0x140070a57  call    ?Stop@ServiceHandler@@QEBAXXZ; ServiceHandler::Stop(void)
0x140070a5c  mov     rdx, [rbx+8]
0x140070a60  sub     rdx, [rbx]
0x140070a63  mov     r8, [rbx]; lpServiceArgVectors
0x140070a66  mov     rcx, [rsi]; hService
0x140070a69  sar     rdx, 3; dwNumServiceArgs
0x140070a6d  call    cs:__imp_StartServiceW
0x140070a73  test    eax, eax
0x140070a75  jnz     short loc_140070A8D
0x140070a77  mov     rcx, [rbp+28h]; this
0x140070a7b  lea     r8, aPcshellShellSy_7; "pcshell\\shell\\systemsettings\\adminfl"...
0x140070a82  mov     edx, 8Dh; void *
0x140070a87  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140070a8d  mov     rcx, [rsi]; hService
0x140070a90  lea     rax, [rbp+var_40]
0x140070a94  mov     r9d, 24h ; '$'; cbBufSize
0x140070a9a  mov     qword ptr [rsp+70h+pcbBytesNeeded], rax; pcbBytesNeeded
0x140070a9f  lea     r8, [rbp+Buffer]; lpBuffer
0x140070aa3  xor     edx, edx; InfoLevel
0x140070aa5  call    cs:__imp_QueryServiceStatusEx
0x140070aab  test    eax, eax
0x140070aad  jnz     short loc_140070AFB
0x140070aaf  mov     rcx, [rbp+28h]; this
0x140070ab3  lea     r8, aPcshellShellSy_7; "pcshell\\shell\\systemsettings\\adminfl"...
0x140070aba  mov     edx, 95h; void *
0x140070abf  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140070ac5  mov     edx, [rbp+var_28+8]; unsigned int
0x140070ac8  call    ?GetWaitTime@ServiceHandler@@AEBAKK@Z; ServiceHandler::GetWaitTime(ulong)
0x140070acd  mov     rcx, [rsi]; hService
0x140070ad0  lea     r8, [rbp+Buffer]; lpBuffer
0x140070ad4  mov     r14, [rbp+28h]
0x140070ad8  mov     r15d, eax
0x140070adb  lea     rax, [rbp+var_40]
0x140070adf  mov     r9d, 24h ; '$'; cbBufSize
0x140070ae5  xor     edx, edx; InfoLevel
0x140070ae7  mov     qword ptr [rsp+70h+pcbBytesNeeded], rax; int
0x140070aec  call    cs:__imp_QueryServiceStatusEx
0x140070af2  test    eax, eax
0x140070af4  jz      short loc_140070B5D
0x140070af6  cmp     [rbp+var_28+4], ebx
0x140070af9  jbe     short loc_140070B08
0x140070afb  call    cs:__imp_GetTickCount
0x140070b01  mov     ebx, [rbp+var_28+4]
0x140070b04  mov     edi, eax
0x140070b06  jmp     short loc_140070B19
0x140070b08  mov     r14, [rbp+28h]
0x140070b0c  call    cs:__imp_GetTickCount
0x140070b12  sub     eax, edi
0x140070b14  cmp     eax, r15d
0x140070b17  ja      short loc_140070B42
0x140070b19  mov     ecx, dword ptr [rbp+Buffer+4]; this
0x140070b1c  cmp     ecx, 2
0x140070b1f  jz      short loc_140070AC5
0x140070b21  cmp     ecx, 4
0x140070b24  jz      short loc_140070B72
0x140070b26  mov     rcx, [rbp+28h]; this
0x140070b2a  lea     r8, aPcshellShellSy_7; "pcshell\\shell\\systemsettings\\adminfl"...
0x140070b31  mov     r9d, 80004005h; char *
0x140070b37  mov     edx, 0B4h; void *
0x140070b3c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140070b42  mov     r9d, 80070102h; char *
0x140070b48  lea     r8, aPcshellShellSy_7; "pcshell\\shell\\systemsettings\\adminfl"...
0x140070b4f  mov     edx, 0AFh; void *
0x140070b54  mov     rcx, r14; this
0x140070b57  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140070b5d  lea     r8, aPcshellShellSy_7; "pcshell\\shell\\systemsettings\\adminfl"...
0x140070b64  mov     edx, 0A5h; void *
0x140070b69  mov     rcx, r14; this
0x140070b6c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140070b72  mov     rcx, [rbp+var_10]
0x140070b76  xor     rcx, rsp; StackCookie
0x140070b79  call    __security_check_cookie
0x140070b7e  mov     rbx, [rsp+70h+arg_10]
0x140070b86  add     rsp, 70h
0x140070b8a  pop     r15
0x140070b8c  pop     r14
0x140070b8e  pop     rdi
0x140070b8f  pop     rsi
0x140070b90  pop     rbp
0x140070b91  retn
```
