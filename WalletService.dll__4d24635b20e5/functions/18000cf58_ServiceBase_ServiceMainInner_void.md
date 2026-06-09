# ServiceBase::_ServiceMainInner(void)

- ea: `0x18000cf58`
- end: `0x18000d115`
- name: `?_ServiceMainInner@ServiceBase@@AEAAJXZ`
- size: `445`
- prototype: `signed int __fastcall(ServiceBase *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000caa8`

## callees

- `0x18000cc5c`
- `0x18000cd2c`
- `0x18000cf58`
- `0x18000d1e8`
- `0x18000d57c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000cf8f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000cf8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cfc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cfc1`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x18000d102`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x18000d102`

## pseudocode

```c
signed int __fastcall ServiceBase::_ServiceMainInner(ServiceBase *this)
{
  signed int result; // eax
  HANDLE EventW; // rbx
  bool v3; // sf
  __int64 v4; // rcx
  int v5; // ebx
  __int64 *v6; // rdx
  int v7; // eax
  signed int v8; // ecx

  if ( !qword_18006C0C0 )
    return -2147467263;
  result = ServiceBase::_CheckServiceShutdownAlready(this);
  if ( result >= 0 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    if ( EventW == (HANDLE)xmmword_18006C060 )
    {
      EventW = (HANDLE)xmmword_18006C060;
    }
    else
    {
      tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&xmmword_18006C060);
      *(_QWORD *)&xmmword_18006C060 = EventW;
    }
    if ( EventW )
      goto LABEL_11;
    result = GetLastError();
    v3 = result < 0;
    if ( result > 0 )
    {
      result = (unsigned __int16)result | 0x80070000;
      v3 = result < 0;
    }
    if ( !v3 )
    {
LABEL_11:
      result = ServiceBase::_UpdateStatus((ServiceBase *)&g_rwService, 2u);
      if ( result >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64 *))(g_rwService + 8))(&g_rwService);
        if ( v5 < 0 )
        {
          if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 0x20) == 0 )
            return v5;
          v6 = ServiceBaseServiceStartingError;
LABEL_15:
          McTemplateU0zq_EventWriteTransfer(v4, v6, &ServiceName, (unsigned int)v5);
          return v5;
        }
        LODWORD(qword_18006C08C) = 1;
        result = ServiceBase::_UpdateStatus((ServiceBase *)&g_rwService, 4u);
        if ( result >= 0 )
        {
          v5 = (*(__int64 (__fastcall **)(__int64 *))(g_rwService + 24))(&g_rwService);
          if ( v5 < 0 )
          {
            if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 0x20) == 0 )
              return v5;
            v6 = ServiceBaseServiceStartedError;
            goto LABEL_15;
          }
          v7 = (*(__int64 (__fastcall **)(char *, WCHAR *, _QWORD, __int64 (__fastcall *)(), __int64 *, int))(qword_18006C0C0 + 192))(
                 (char *)&xmmword_18006C060 + 8,
                 &ServiceName,
                 xmmword_18006C060,
                 StopCallback,
                 &g_rwService,
                 8);
          v8 = v7;
          if ( v7 > 0 )
            v8 = (unsigned __int16)v7 | 0x80070000;
          if ( v8 >= 0 )
            v8 = 0;
          if ( v8 >= 0 )
          {
            if ( HIDWORD(qword_18006C08C) )
              (*(void (__fastcall **)(__int64 *, _QWORD))(g_rwService + 32))(
                &g_rwService,
                (unsigned int)dword_18006C094);
            CoFreeUnusedLibrariesEx(0x7530u, 0);
            return 0;
          }
          else
          {
            return v8;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000cf58  mov     [rsp+arg_0], rbx
0x18000cf5d  push    rdi
0x18000cf5e  sub     rsp, 40h
0x18000cf62  cmp     cs:qword_18006C0C0, 0
0x18000cf6a  jnz     short loc_18000CF76
0x18000cf6c  mov     eax, 80004001h
0x18000cf71  jmp     loc_18000D10A
0x18000cf76  call    ?_CheckServiceShutdownAlready@ServiceBase@@AEAAJXZ; ServiceBase::_CheckServiceShutdownAlready(void)
0x18000cf7b  test    eax, eax
0x18000cf7d  js      loc_18000D10A
0x18000cf83  xor     r9d, r9d; lpName
0x18000cf86  xor     r8d, r8d; bInitialState
0x18000cf89  xor     ecx, ecx; lpEventAttributes
0x18000cf8b  lea     edx, [r9+1]; bManualReset
0x18000cf8f  call    cs:__imp_CreateEventW
0x18000cf95  mov     rbx, rax
0x18000cf98  mov     rax, qword ptr cs:xmmword_18006C060
0x18000cf9f  cmp     rbx, rax
0x18000cfa2  jz      short loc_18000CFB9
0x18000cfa4  lea     rcx, xmmword_18006C060
0x18000cfab  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18000cfb0  mov     qword ptr cs:xmmword_18006C060, rbx
0x18000cfb7  jmp     short loc_18000CFBC
0x18000cfb9  mov     rbx, rax
0x18000cfbc  test    rbx, rbx
0x18000cfbf  jnz     short loc_18000CFDB
0x18000cfc1  call    cs:__imp_GetLastError
0x18000cfc7  test    eax, eax
0x18000cfc9  jle     short loc_18000CFD5
0x18000cfcb  movzx   eax, ax
0x18000cfce  or      eax, 80070000h
0x18000cfd3  test    eax, eax
0x18000cfd5  js      loc_18000D10A
0x18000cfdb  lea     rdi, ?g_rwService@@3VRWService@@A; RWService g_rwService
0x18000cfe2  mov     edx, 2; unsigned int
0x18000cfe7  mov     rcx, rdi; this
0x18000cfea  call    ?_UpdateStatus@ServiceBase@@AEAAJK@Z; ServiceBase::_UpdateStatus(ulong)
0x18000cfef  test    eax, eax
0x18000cff1  js      loc_18000D10A
0x18000cff7  mov     rax, cs:?g_rwService@@3VRWService@@A; RWService g_rwService
0x18000cffe  mov     rcx, rdi
0x18000d001  mov     rax, [rax+8]
0x18000d005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d00a  mov     ebx, eax
0x18000d00c  test    eax, eax
0x18000d00e  jns     short loc_18000D036
0x18000d010  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 20h
0x18000d017  jz      short loc_18000D02F
0x18000d019  lea     rdx, ServiceBaseServiceStartingError
0x18000d020  lea     r8, ServiceName
0x18000d027  mov     r9d, ebx
0x18000d02a  call    McTemplateU0zq_EventWriteTransfer
0x18000d02f  mov     eax, ebx
0x18000d031  jmp     loc_18000D10A
0x18000d036  mov     edx, 4; unsigned int
0x18000d03b  mov     dword ptr cs:qword_18006C08C, 1
0x18000d045  mov     rcx, rdi; this
0x18000d048  call    ?_UpdateStatus@ServiceBase@@AEAAJK@Z; ServiceBase::_UpdateStatus(ulong)
0x18000d04d  test    eax, eax
0x18000d04f  js      loc_18000D10A
0x18000d055  mov     rax, cs:?g_rwService@@3VRWService@@A; RWService g_rwService
0x18000d05c  mov     rcx, rdi
0x18000d05f  mov     rax, [rax+18h]
0x18000d063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d068  mov     ebx, eax
0x18000d06a  test    eax, eax
0x18000d06c  jns     short loc_18000D080
0x18000d06e  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 20h
0x18000d075  jz      short loc_18000D02F
0x18000d077  lea     rdx, ServiceBaseServiceStartedError
0x18000d07e  jmp     short loc_18000D020
0x18000d080  mov     rax, cs:qword_18006C0C0
0x18000d087  lea     r9, StopCallback
0x18000d08e  mov     r8, qword ptr cs:xmmword_18006C060
0x18000d095  lea     rdx, ServiceName
0x18000d09c  mov     [rsp+48h+var_20], 8
0x18000d0a4  lea     rcx, xmmword_18006C060+8
0x18000d0ab  mov     [rsp+48h+var_28], rdi
0x18000d0b0  mov     rax, [rax+0C0h]
0x18000d0b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0bc  mov     ecx, eax
0x18000d0be  test    eax, eax
0x18000d0c0  jle     short loc_18000D0CB
0x18000d0c2  movzx   ecx, ax
0x18000d0c5  or      ecx, 80070000h
0x18000d0cb  xor     eax, eax
0x18000d0cd  test    ecx, ecx
0x18000d0cf  cmovns  ecx, eax
0x18000d0d2  test    ecx, ecx
0x18000d0d4  jns     short loc_18000D0DA
0x18000d0d6  mov     eax, ecx
0x18000d0d8  jmp     short loc_18000D10A
0x18000d0da  cmp     dword ptr cs:qword_18006C08C+4, eax
0x18000d0e0  jz      short loc_18000D0FB
0x18000d0e2  mov     rax, cs:?g_rwService@@3VRWService@@A; RWService g_rwService
0x18000d0e9  mov     rcx, rdi
0x18000d0ec  mov     edx, cs:dword_18006C094
0x18000d0f2  mov     rax, [rax+20h]
0x18000d0f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0fb  xor     edx, edx; dwReserved
0x18000d0fd  mov     ecx, 7530h; dwUnloadDelay
0x18000d102  call    cs:__imp_CoFreeUnusedLibrariesEx
0x18000d108  xor     eax, eax
0x18000d10a  mov     rbx, [rsp+48h+arg_0]
0x18000d10f  add     rsp, 40h
0x18000d113  pop     rdi
0x18000d114  retn
```
