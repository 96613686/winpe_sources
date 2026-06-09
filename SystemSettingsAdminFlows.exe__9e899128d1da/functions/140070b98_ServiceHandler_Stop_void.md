# ServiceHandler::Stop(void)

- ea: `0x140070b98`
- end: `0x140070d91`
- name: `?Stop@ServiceHandler@@QEBAXXZ`
- size: `505`
- prototype: `void __fastcall(ServiceHandler *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x14006f494`
- `0x1400708a8`
- `0x1400709d4`

## callees

- `0x140005f30`
- `0x14002a2c0`
- `0x140055c64`
- `0x1400707d0`
- `0x140070b98`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x140070c12`
- `KERNEL32!GetTickCount` at `0x140070c7e`
- `KERNEL32!GetTickCount` at `0x140070c8f`
- `KERNEL32!GetTickCount` at `0x140070cfd`
- `KERNEL32!GetTickCount` at `0x140070c12`
- `KERNEL32!GetTickCount` at `0x140070c7e`
- `KERNEL32!GetTickCount` at `0x140070c8f`
- `KERNEL32!GetTickCount` at `0x140070cfd`
- `KERNEL32!Sleep` at `0x140070d16`
- `KERNEL32!Sleep` at `0x140070d16`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x140070c26`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x140070c26`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x140070be4`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x140070c6f`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x140070d38`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x140070be4`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x140070c6f`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x140070d38`

## string_xrefs

- `0x140070bf2`: `pcshell\shell\systemsettings\adminflows\accessibility\brlapiservice.cpp`
- `0x140070c38`: `pcshell\shell\systemsettings\adminflows\accessibility\brlapiservice.cpp`
- `0x140070cb1`: `pcshell\shell\systemsettings\adminflows\accessibility\brlapiservice.cpp`
- `0x140070ccf`: `pcshell\shell\systemsettings\adminflows\accessibility\brlapiservice.cpp`
- `0x140070ce4`: `pcshell\shell\systemsettings\adminflows\accessibility\brlapiservice.cpp`
- `0x140070d61`: `pcshell\shell\systemsettings\adminflows\accessibility\brlapiservice.cpp`
- `0x140070d7c`: `pcshell\shell\systemsettings\adminflows\accessibility\brlapiservice.cpp`

## pseudocode

```c
void __fastcall ServiceHandler::Stop(SC_HANDLE *this)
{
  SC_HANDLE v2; // rcx
  const char *v3; // r9
  DWORD v4; // edi
  const char *v5; // r9
  unsigned int WaitTime; // r15d
  const char *v7; // r9
  DWORD TickCount; // eax
  unsigned int v9; // ebx
  DWORD v10; // edi
  ServiceHandler *v11; // rcx
  DWORD v12; // eax
  const char *v13; // r9
  int pcbBytesNeeded; // [rsp+20h] [rbp-58h]
  DWORD v15; // [rsp+30h] [rbp-48h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-40h] BYREF
  unsigned int v17[4]; // [rsp+48h] [rbp-30h]
  int v18; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  v18 = 0;
  v15 = 0;
  v2 = *this;
  *(_OWORD *)Buffer = 0;
  *(_OWORD *)v17 = 0;
  if ( !QueryServiceStatusEx(v2, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &v15) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x35,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\brlapiservice.cpp",
      v3);
  if ( *(_DWORD *)&Buffer[4] != 1 )
  {
    if ( *(_DWORD *)&Buffer[4] == 3 )
    {
LABEL_9:
      TickCount = GetTickCount();
      v9 = v17[1];
      v10 = TickCount;
      while ( *(_DWORD *)&Buffer[4] == 3 )
      {
        WaitTime = ServiceHandler::GetWaitTime((ServiceHandler *)3, v17[2]);
        if ( !QueryServiceStatusEx(*this, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &v15) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x4B,
            (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\brlapiservice.cpp",
            v7);
        if ( v17[1] > v9 )
          goto LABEL_9;
        if ( GetTickCount() - v10 > WaitTime )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x55,
            (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\brlapiservice.cpp",
            (const char *)0x80070102LL,
            pcbBytesNeeded);
      }
      if ( *(_DWORD *)&Buffer[4] != 1 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x71,
          (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\brlapiservice.cpp",
          (const char *)0x80004005LL,
          pcbBytesNeeded);
    }
    else
    {
      v4 = GetTickCount();
      if ( !ControlService(*this, 1u, (LPSERVICE_STATUS)Buffer) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x61,
          (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\brlapiservice.cpp",
          v5);
      while ( *(_DWORD *)&Buffer[4] != 1 )
      {
        if ( GetTickCount() - v4 > 0x7530 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x65,
            (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\brlapiservice.cpp",
            (const char *)0x80070102LL,
            pcbBytesNeeded);
        v12 = ServiceHandler::GetWaitTime(v11, v17[2]);
        Sleep(v12);
        if ( !QueryServiceStatusEx(*this, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &v15) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x6E,
            (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\brlapiservice.cpp",
            v13);
      }
    }
  }
}

```

## disassembly

```asm
0x140070b98  push    rbp
0x140070b9a  push    rbx
0x140070b9b  push    rsi
0x140070b9c  push    rdi
0x140070b9d  push    r14
0x140070b9f  push    r15
0x140070ba1  mov     rbp, rsp
0x140070ba4  sub     rsp, 78h
0x140070ba8  mov     rax, cs:__security_cookie
0x140070baf  xor     rax, rsp
0x140070bb2  mov     [rbp+var_18], rax
0x140070bb6  xor     eax, eax
0x140070bb8  lea     r8, [rbp+Buffer]; lpBuffer
0x140070bbc  xorps   xmm0, xmm0
0x140070bbf  mov     [rbp+var_20], eax
0x140070bc2  mov     [rbp+var_48], eax
0x140070bc5  mov     r14, rcx
0x140070bc8  mov     rcx, [rcx]; hService
0x140070bcb  lea     rax, [rbp+var_48]
0x140070bcf  mov     r9d, 24h ; '$'; cbBufSize
0x140070bd5  mov     qword ptr [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x140070bda  xor     edx, edx; InfoLevel
0x140070bdc  movups  xmmword ptr [rbp+Buffer], xmm0
0x140070be0  movups  xmmword ptr [rbp+var_30], xmm0
0x140070be4  call    cs:__imp_QueryServiceStatusEx
0x140070bea  test    eax, eax
0x140070bec  jnz     short loc_140070C02
0x140070bee  mov     rcx, [rbp+30h]; this
0x140070bf2  lea     r8, aPcshellShellSy_7; "pcshell\\shell\\systemsettings\\adminfl"...
0x140070bf9  lea     edx, [rax+35h]; void *
0x140070bfc  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140070c02  cmp     dword ptr [rbp+Buffer+4], 1
0x140070c06  jz      loc_140070D48
0x140070c0c  cmp     dword ptr [rbp+Buffer+4], 3
0x140070c10  jz      short loc_140070C7E
0x140070c12  call    cs:__imp_GetTickCount
0x140070c18  mov     rcx, [r14]; hService
0x140070c1b  lea     r8, [rbp+Buffer]; lpServiceStatus
0x140070c1f  mov     edx, 1; dwControl
0x140070c24  mov     edi, eax
0x140070c26  call    cs:__imp_ControlService
0x140070c2c  test    eax, eax
0x140070c2e  jnz     loc_140070D42
0x140070c34  mov     rcx, [rbp+30h]; this
0x140070c38  lea     r8, aPcshellShellSy_7; "pcshell\\shell\\systemsettings\\adminfl"...
0x140070c3f  lea     edx, [rax+61h]; void *
0x140070c42  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140070c48  mov     edx, [rbp+var_30+8]; unsigned int
0x140070c4b  call    ?GetWaitTime@ServiceHandler@@AEBAKK@Z; ServiceHandler::GetWaitTime(ulong)
0x140070c50  mov     rcx, [r14]; hService
0x140070c53  lea     r8, [rbp+Buffer]; lpBuffer
0x140070c57  mov     rsi, [rbp+30h]
0x140070c5b  mov     r15d, eax
0x140070c5e  lea     rax, [rbp+var_48]
0x140070c62  mov     r9d, 24h ; '$'; cbBufSize
0x140070c68  xor     edx, edx; InfoLevel
0x140070c6a  mov     qword ptr [rsp+78h+pcbBytesNeeded], rax; int
0x140070c6f  call    cs:__imp_QueryServiceStatusEx
0x140070c75  test    eax, eax
0x140070c77  jz      short loc_140070CE4
0x140070c79  cmp     [rbp+var_30+4], ebx
0x140070c7c  jbe     short loc_140070C8B
0x140070c7e  call    cs:__imp_GetTickCount
0x140070c84  mov     ebx, [rbp+var_30+4]
0x140070c87  mov     edi, eax
0x140070c89  jmp     short loc_140070C9C
0x140070c8b  mov     rsi, [rbp+30h]
0x140070c8f  call    cs:__imp_GetTickCount
0x140070c95  sub     eax, edi
0x140070c97  cmp     eax, r15d
0x140070c9a  ja      short loc_140070CC9
0x140070c9c  mov     ecx, dword ptr [rbp+Buffer+4]; this
0x140070c9f  cmp     ecx, 3
0x140070ca2  jz      short loc_140070C48
0x140070ca4  cmp     ecx, 1
0x140070ca7  jz      loc_140070D48
0x140070cad  mov     rcx, [rbp+30h]; this
0x140070cb1  lea     r8, aPcshellShellSy_7; "pcshell\\shell\\systemsettings\\adminfl"...
0x140070cb8  mov     r9d, 80004005h; char *
0x140070cbe  mov     edx, 71h ; 'q'; void *
0x140070cc3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140070cc9  mov     r9d, 80070102h; char *
0x140070ccf  lea     r8, aPcshellShellSy_7; "pcshell\\shell\\systemsettings\\adminfl"...
0x140070cd6  mov     edx, 55h ; 'U'; void *
0x140070cdb  mov     rcx, rsi; this
0x140070cde  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140070ce4  lea     r8, aPcshellShellSy_7; "pcshell\\shell\\systemsettings\\adminfl"...
0x140070ceb  mov     edx, 4Bh ; 'K'; void *
0x140070cf0  mov     rcx, rsi; this
0x140070cf3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140070cf9  mov     rbx, [rbp+30h]
0x140070cfd  call    cs:__imp_GetTickCount
0x140070d03  sub     eax, edi
0x140070d05  cmp     eax, 7530h
0x140070d0a  ja      short loc_140070D76
0x140070d0c  mov     edx, [rbp+var_30+8]; unsigned int
0x140070d0f  call    ?GetWaitTime@ServiceHandler@@AEBAKK@Z; ServiceHandler::GetWaitTime(ulong)
0x140070d14  mov     ecx, eax; dwMilliseconds
0x140070d16  call    cs:__imp_Sleep
0x140070d1c  mov     rcx, [r14]; hService
0x140070d1f  lea     rax, [rbp+var_48]
0x140070d23  mov     rbx, [rbp+30h]
0x140070d27  lea     r8, [rbp+Buffer]; lpBuffer
0x140070d2b  mov     r9d, 24h ; '$'; cbBufSize
0x140070d31  mov     qword ptr [rsp+78h+pcbBytesNeeded], rax; int
0x140070d36  xor     edx, edx; InfoLevel
0x140070d38  call    cs:__imp_QueryServiceStatusEx
0x140070d3e  test    eax, eax
0x140070d40  jz      short loc_140070D61
0x140070d42  cmp     dword ptr [rbp+Buffer+4], 1
0x140070d46  jnz     short loc_140070CF9
0x140070d48  mov     rcx, [rbp+var_18]
0x140070d4c  xor     rcx, rsp; StackCookie
0x140070d4f  call    __security_check_cookie
0x140070d54  add     rsp, 78h
0x140070d58  pop     r15
0x140070d5a  pop     r14
0x140070d5c  pop     rdi
0x140070d5d  pop     rsi
0x140070d5e  pop     rbx
0x140070d5f  pop     rbp
0x140070d60  retn
0x140070d61  lea     r8, aPcshellShellSy_7; "pcshell\\shell\\systemsettings\\adminfl"...
0x140070d68  mov     edx, 6Eh ; 'n'; void *
0x140070d6d  mov     rcx, rbx; this
0x140070d70  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140070d76  mov     r9d, 80070102h; char *
0x140070d7c  lea     r8, aPcshellShellSy_7; "pcshell\\shell\\systemsettings\\adminfl"...
0x140070d83  mov     edx, 65h ; 'e'; void *
0x140070d88  mov     rcx, rbx; this
0x140070d8b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
