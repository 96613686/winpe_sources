# TiInitialize

- ea: `0x140006e70`
- end: `0x140006ffe`
- name: `TiInitialize`
- size: `398`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140007004`

## callees

- `0x140001fa0`
- `0x140002cf8`
- `0x14000601c`
- `0x140006e70`
- `0x14000e328`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006ea5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006eec`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006f33`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006ea5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006eec`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006eb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006efe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006f45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006eb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006efe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006f45`

## string_xrefs

- `0x140006ece`: `Failed to create servicing event.`
- `0x140006f15`: `Failed to create exiting event.`
- `0x140006f5c`: `Failed to create shutdown event.`

## pseudocode

```c
__int64 TiInitialize()
{
  signed int LastError; // eax
  signed int v1; // ebx
  const char *v2; // r9
  signed int v3; // eax
  signed int v4; // eax
  CCbsClassFactory *v5; // rax
  CCbsClassFactory *v6; // rbx
  CCbsClassFactory *v7; // rax

  CBSWdsLog(0x4000000, 0, 0, "Starting TiWorker initialization.");
  vhWorkerServicingEvent = CreateEventW(0, 1, 0, 0);
  if ( !vhWorkerServicingEvent )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    v2 = "Failed to create servicing event.";
    if ( v1 >= 0 )
      v1 = -2147467259;
    goto LABEL_25;
  }
  vhWorkerExitEvent = CreateEventW(0, 1, 0, 0);
  if ( !vhWorkerExitEvent )
  {
    v3 = GetLastError();
    v1 = v3;
    if ( v3 > 0 )
      v1 = (unsigned __int16)v3 | 0x80070000;
    v2 = "Failed to create exiting event.";
    if ( v1 >= 0 )
      v1 = -2147467259;
    goto LABEL_25;
  }
  vhShutdownEvent = CreateEventW(0, 1, 0, 0);
  if ( !vhShutdownEvent )
  {
    v4 = GetLastError();
    v1 = v4;
    if ( v4 > 0 )
      v1 = (unsigned __int16)v4 | 0x80070000;
    v2 = "Failed to create shutdown event.";
    if ( v1 >= 0 )
      v1 = -2147467259;
    goto LABEL_25;
  }
  v5 = (CCbsClassFactory *)operator new(0x58u);
  v6 = v5;
  if ( !v5 || (memset_0(v5, 0, 0x58u), (v7 = CCbsClassFactory::CCbsClassFactory(v6)) == 0) )
  {
    vpWorkerFactory = 0;
LABEL_24:
    v1 = -2147024882;
    v2 = "Failed to allocate new CBS worker factory.";
LABEL_25:
    CBSWdsLog(0x4000000, (unsigned int)v1, 1, v2);
    goto LABEL_26;
  }
  v1 = 0;
  vpWorkerFactory = (LPUNKNOWN)((char *)v7 + *(int *)(*((_QWORD *)v7 + 1) + 4LL) + 8);
  if ( !vpWorkerFactory )
    goto LABEL_24;
LABEL_26:
  CBSWdsLog(0x4000000, 0, 0, "Ending TiWorker initialization.");
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140006e70  mov     [rsp+arg_0], rbx
0x140006e75  mov     [rsp+arg_8], rsi
0x140006e7a  push    rdi
0x140006e7b  sub     rsp, 20h
0x140006e7f  mov     esi, 4000000h
0x140006e84  lea     r9, aStartingTiwork_0; "Starting TiWorker initialization."
0x140006e8b  mov     ecx, esi
0x140006e8d  xor     r8d, r8d
0x140006e90  xor     edx, edx
0x140006e92  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140006e97  xor     r9d, r9d; lpName
0x140006e9a  xor     r8d, r8d; bInitialState
0x140006e9d  xor     ecx, ecx; lpEventAttributes
0x140006e9f  lea     edi, [r9+1]
0x140006ea3  mov     edx, edi; bManualReset
0x140006ea5  call    cs:__imp_CreateEventW
0x140006eab  mov     cs:?vhWorkerServicingEvent@@3PEAXEA, rax; void * vhWorkerServicingEvent
0x140006eb2  test    rax, rax
0x140006eb5  jnz     short loc_140006EE2
0x140006eb7  call    cs:__imp_GetLastError
0x140006ebd  mov     ebx, eax
0x140006ebf  test    eax, eax
0x140006ec1  jle     short loc_140006ECC
0x140006ec3  movzx   ebx, ax
0x140006ec6  or      ebx, 80070000h
0x140006ecc  test    ebx, ebx
0x140006ece  lea     r9, aFailedToCreate_2; "Failed to create servicing event."
0x140006ed5  mov     eax, 80004005h
0x140006eda  cmovns  ebx, eax
0x140006edd  jmp     loc_140006FCD
0x140006ee2  xor     r9d, r9d; lpName
0x140006ee5  xor     r8d, r8d; bInitialState
0x140006ee8  mov     edx, edi; bManualReset
0x140006eea  xor     ecx, ecx; lpEventAttributes
0x140006eec  call    cs:__imp_CreateEventW
0x140006ef2  mov     cs:?vhWorkerExitEvent@@3PEAXEA, rax; void * vhWorkerExitEvent
0x140006ef9  test    rax, rax
0x140006efc  jnz     short loc_140006F29
0x140006efe  call    cs:__imp_GetLastError
0x140006f04  mov     ebx, eax
0x140006f06  test    eax, eax
0x140006f08  jle     short loc_140006F13
0x140006f0a  movzx   ebx, ax
0x140006f0d  or      ebx, 80070000h
0x140006f13  test    ebx, ebx
0x140006f15  lea     r9, aFailedToCreate_9; "Failed to create exiting event."
0x140006f1c  mov     eax, 80004005h
0x140006f21  cmovns  ebx, eax
0x140006f24  jmp     loc_140006FCD
0x140006f29  xor     r9d, r9d; lpName
0x140006f2c  xor     r8d, r8d; bInitialState
0x140006f2f  mov     edx, edi; bManualReset
0x140006f31  xor     ecx, ecx; lpEventAttributes
0x140006f33  call    cs:__imp_CreateEventW
0x140006f39  mov     cs:?vhShutdownEvent@@3PEAXEA, rax; void * vhShutdownEvent
0x140006f40  test    rax, rax
0x140006f43  jnz     short loc_140006F6D
0x140006f45  call    cs:__imp_GetLastError
0x140006f4b  mov     ebx, eax
0x140006f4d  test    eax, eax
0x140006f4f  jle     short loc_140006F5A
0x140006f51  movzx   ebx, ax
0x140006f54  or      ebx, 80070000h
0x140006f5a  test    ebx, ebx
0x140006f5c  lea     r9, aFailedToCreate_3; "Failed to create shutdown event."
0x140006f63  mov     eax, 80004005h
0x140006f68  cmovns  ebx, eax
0x140006f6b  jmp     short loc_140006FCD
0x140006f6d  mov     ecx, 58h ; 'X'; Size
0x140006f72  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140006f77  mov     rbx, rax
0x140006f7a  test    rax, rax
0x140006f7d  jz      short loc_140006FB6
0x140006f7f  xor     edx, edx; Val
0x140006f81  mov     rcx, rax; void *
0x140006f84  lea     r8d, [rdx+58h]; Size
0x140006f88  call    memset_0
0x140006f8d  mov     rcx, rbx; this
0x140006f90  call    ??0CCbsClassFactory@@QEAA@XZ; CCbsClassFactory::CCbsClassFactory(void)
0x140006f95  test    rax, rax
0x140006f98  jz      short loc_140006FB6
0x140006f9a  mov     rcx, [rax+8]
0x140006f9e  xor     ebx, ebx
0x140006fa0  add     rax, 8
0x140006fa4  movsxd  rdx, dword ptr [rcx+4]
0x140006fa8  add     rax, rdx
0x140006fab  mov     cs:?vpWorkerFactory@@3PEAUIClassFactory@@EA, rax; IClassFactory * vpWorkerFactory
0x140006fb2  jnz     short loc_140006FD9
0x140006fb4  jmp     short loc_140006FC1
0x140006fb6  mov     cs:?vpWorkerFactory@@3PEAUIClassFactory@@EA, 0; IClassFactory * vpWorkerFactory
0x140006fc1  mov     ebx, 8007000Eh
0x140006fc6  lea     r9, aFailedToAlloca; "Failed to allocate new CBS worker facto"...
0x140006fcd  mov     r8d, edi
0x140006fd0  mov     edx, ebx
0x140006fd2  mov     ecx, esi
0x140006fd4  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140006fd9  lea     r9, aEndingTiworker_0; "Ending TiWorker initialization."
0x140006fe0  xor     r8d, r8d
0x140006fe3  xor     edx, edx
0x140006fe5  mov     ecx, esi
0x140006fe7  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140006fec  mov     rsi, [rsp+28h+arg_8]
0x140006ff1  mov     eax, ebx
0x140006ff3  mov     rbx, [rsp+28h+arg_0]
0x140006ff8  add     rsp, 20h
0x140006ffc  pop     rdi
0x140006ffd  retn
```
