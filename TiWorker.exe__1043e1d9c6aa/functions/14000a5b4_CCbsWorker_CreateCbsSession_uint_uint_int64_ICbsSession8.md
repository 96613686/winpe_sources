# CCbsWorker::CreateCbsSession(uint,uint,__int64,ICbsSession8 * *)

- ea: `0x14000a5b4`
- end: `0x14000a87b`
- name: `?CreateCbsSession@CCbsWorker@@UEAAJII_JPEAPEAUICbsSession8@@@Z`
- size: `711`
- prototype: `__int64 __fastcall(CCbsWorker *this, __int64, DWORD, void *, struct ICbsSession8 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x140009350`

## callees

- `0x140002310`
- `0x140007eb8`
- `0x14000914c`
- `0x1400091d8`
- `0x14000a5b4`
- `0x14000e328`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a67c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a6e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a67c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a6e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000a6a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000a6a7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14000a6d2`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14000a6d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a7cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a7cd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14000a66e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14000a66e`

## string_xrefs

- `0x14000a838`: `Error: Not reversed from impersonation on func: %s`
- `0x14000a693`: `Failed to open TrustedInstaller process.`
- `0x14000a741`: `Failed to create cbs session`
- `0x14000a76c`: `Failed to query private session interface, wrong cbscore.dll`
- `0x14000a82e`: `CCbsWorker::CreateCbsSession`

## pseudocode

```c
__int64 __fastcall CCbsWorker::CreateCbsSession(
        CCbsWorker *this,
        __int64 a2,
        DWORD a3,
        void *a4,
        struct ICbsSession8 **a5)
{
  signed int v8; // ebx
  const char *v9; // r9
  __int64 v10; // rdx
  int v11; // eax
  HANDLE v12; // rsi
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  signed int v15; // eax
  const char *v16; // r9
  __int64 v17; // rdx
  int v18; // eax
  _BYTE v20[24]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v21; // [rsp+58h] [rbp-28h] BYREF
  struct ICbsSession8 *v22; // [rsp+60h] [rbp-20h] BYREF
  __int64 v23; // [rsp+68h] [rbp-18h] BYREF
  HANDLE TargetHandle; // [rsp+70h] [rbp-10h] BYREF

  v21 = 0;
  v22 = 0;
  v23 = 0;
  TargetHandle = 0;
  MonitoredCritSecLocker::MonitoredCritSecLocker((MonitoredCritSecLocker *)v20, (CCbsWorker *)((char *)this - 64), a3);
  if ( !a5 )
  {
    v8 = -2147467261;
    v9 = "No session result specified";
LABEL_3:
    v10 = (unsigned int)v8;
LABEL_4:
    CBSWdsLog(0x4000000, v10, 1, v9);
    goto LABEL_31;
  }
  if ( !vpCbsSessionClassFactory )
  {
    v11 = TiWorkerCoreInitialize(*((unsigned int *)this - 6), &vpCbsSessionClassFactory);
    v8 = v11;
    if ( v11 < 0 )
    {
      v9 = "Failed to initialize CBS class factory.";
      v10 = (unsigned int)v11;
      goto LABEL_4;
    }
  }
  v12 = OpenProcess(0x40u, 0, a3);
  if ( !v12 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v9 = "Failed to open TrustedInstaller process.";
    if ( v8 >= 0 )
      v8 = -2147467259;
    goto LABEL_3;
  }
  CurrentProcess = GetCurrentProcess();
  if ( !DuplicateHandle(v12, a4, CurrentProcess, &TargetHandle, 0, 0, 2u) )
  {
    v15 = GetLastError();
    v8 = v15;
    if ( v15 > 0 )
      v8 = (unsigned __int16)v15 | 0x80070000;
    v16 = "Failed to duplicate handle.";
    if ( v8 >= 0 )
      v8 = -2147467259;
    v17 = (unsigned int)v8;
    goto LABEL_20;
  }
  v18 = ((__int64 (__fastcall *)(struct IClassFactory *, _QWORD, GUID *, __int64 *))vpCbsSessionClassFactory->lpVtbl->CreateInstance)(
          vpCbsSessionClassFactory,
          0,
          &IID_ICbsSession,
          &v21);
  v8 = v18;
  if ( v18 < 0 )
  {
    v16 = "Failed to create cbs session";
LABEL_23:
    v17 = (unsigned int)v18;
LABEL_20:
    CBSWdsLog(0x4000000, v17, 1, v16);
    goto LABEL_29;
  }
  v18 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v21)(
          v21,
          &GUID_fc2c7e52_df06_445e_8d83_ba125880ea0d,
          &v23);
  v8 = v18;
  if ( v18 < 0 )
  {
    v16 = "Failed to query private session interface, wrong cbscore.dll";
    goto LABEL_23;
  }
  (*(void (__fastcall **)(__int64, HANDLE))(*(_QWORD *)v23 + 208LL))(v23, TargetHandle);
  v18 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct ICbsSession8 **))v21)(v21, &IID_ICbsSession8, &v22);
  v8 = v18;
  if ( v18 < 0 )
  {
    v16 = "Failed to query ICbsSession8 interface";
    goto LABEL_23;
  }
  *a5 = v22;
  v22 = 0;
LABEL_29:
  if ( v12 != (HANDLE)-1LL )
    CloseHandle(v12);
LABEL_31:
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(struct ICbsSession8 *))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  if ( NtCurrentTeb()->IsImpersonating )
    CBSWdsLog(0x4000000, 0, 0, "Error: Not reversed from impersonation on func: %s", "CCbsWorker::CreateCbsSession");
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v20);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000a5b4  mov     [rsp-28h+arg_8], rbx
0x14000a5b9  push    rbp
0x14000a5ba  push    rsi
0x14000a5bb  push    rdi
0x14000a5bc  push    r14
0x14000a5be  push    r15
0x14000a5c0  mov     rbp, rsp
0x14000a5c3  sub     rsp, 80h
0x14000a5ca  mov     rax, cs:__security_cookie
0x14000a5d1  xor     rax, rsp
0x14000a5d4  mov     [rbp+var_8], rax
0x14000a5d8  mov     r14, [rbp+arg_20]
0x14000a5dc  lea     rdx, [rcx-40h]; struct AutoMonitoredCritSec *
0x14000a5e0  mov     rbx, rcx
0x14000a5e3  mov     [rbp+var_28], 0
0x14000a5eb  lea     rcx, [rbp+var_40]; this
0x14000a5ef  mov     [rbp+var_20], 0
0x14000a5f7  mov     r15, r9
0x14000a5fa  mov     [rbp+var_18], 0
0x14000a602  mov     edi, r8d
0x14000a605  mov     [rbp+TargetHandle], 0
0x14000a60d  call    ??0MonitoredCritSecLocker@@QEAA@AEAVAutoMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(AutoMonitoredCritSec &,bool)
0x14000a612  test    r14, r14
0x14000a615  jnz     short loc_14000A63C
0x14000a617  mov     ebx, 80004003h
0x14000a61c  lea     r9, aNoSessionResul; "No session result specified"
0x14000a623  mov     edx, ebx
0x14000a625  mov     edi, 4000000h
0x14000a62a  mov     r8d, 1
0x14000a630  mov     ecx, edi
0x14000a632  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000a637  jmp     loc_14000A7D3
0x14000a63c  cmp     cs:?vpCbsSessionClassFactory@@3PEAUIClassFactory@@EA, 0; IClassFactory * vpCbsSessionClassFactory
0x14000a644  jnz     short loc_14000A666
0x14000a646  mov     ecx, [rbx-18h]
0x14000a649  lea     rdx, ?vpCbsSessionClassFactory@@3PEAUIClassFactory@@EA; IClassFactory * vpCbsSessionClassFactory
0x14000a650  call    TiWorkerCoreInitialize
0x14000a655  mov     ebx, eax
0x14000a657  test    eax, eax
0x14000a659  jns     short loc_14000A666
0x14000a65b  lea     r9, aFailedToInitia_8; "Failed to initialize CBS class factory."
0x14000a662  mov     edx, eax
0x14000a664  jmp     short loc_14000A625
0x14000a666  xor     edx, edx; bInheritHandle
0x14000a668  mov     r8d, edi; dwProcessId
0x14000a66b  lea     ecx, [rdx+40h]; dwDesiredAccess
0x14000a66e  call    cs:__imp_OpenProcess
0x14000a674  mov     rsi, rax
0x14000a677  test    rax, rax
0x14000a67a  jnz     short loc_14000A6A7
0x14000a67c  call    cs:__imp_GetLastError
0x14000a682  mov     ebx, eax
0x14000a684  test    eax, eax
0x14000a686  jle     short loc_14000A691
0x14000a688  movzx   ebx, ax
0x14000a68b  or      ebx, 80070000h
0x14000a691  test    ebx, ebx
0x14000a693  lea     r9, aFailedToOpenTr; "Failed to open TrustedInstaller process"...
0x14000a69a  mov     eax, 80004005h
0x14000a69f  cmovns  ebx, eax
0x14000a6a2  jmp     loc_14000A623
0x14000a6a7  call    cs:__imp_GetCurrentProcess
0x14000a6ad  mov     [rsp+80h+dwOptions], 2; dwOptions
0x14000a6b5  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x14000a6b9  mov     r8, rax; hTargetProcessHandle
0x14000a6bc  mov     [rsp+80h+bInheritHandle], 0; bInheritHandle
0x14000a6c4  mov     rdx, r15; hSourceHandle
0x14000a6c7  mov     [rsp+80h+dwDesiredAccess], 0; dwDesiredAccess
0x14000a6cf  mov     rcx, rsi; hSourceProcessHandle
0x14000a6d2  call    cs:__imp_DuplicateHandle
0x14000a6d8  mov     edi, 4000000h
0x14000a6dd  test    eax, eax
0x14000a6df  jnz     short loc_14000A71B
0x14000a6e1  call    cs:__imp_GetLastError
0x14000a6e7  mov     ebx, eax
0x14000a6e9  test    eax, eax
0x14000a6eb  jle     short loc_14000A6F6
0x14000a6ed  movzx   ebx, ax
0x14000a6f0  or      ebx, 80070000h
0x14000a6f6  test    ebx, ebx
0x14000a6f8  lea     r9, aFailedToDuplic_0; "Failed to duplicate handle."
0x14000a6ff  mov     eax, 80004005h
0x14000a704  cmovns  ebx, eax
0x14000a707  mov     edx, ebx
0x14000a709  mov     r8d, 1
0x14000a70f  mov     ecx, edi
0x14000a711  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000a716  jmp     loc_14000A7C4
0x14000a71b  mov     rcx, cs:?vpCbsSessionClassFactory@@3PEAUIClassFactory@@EA; IClassFactory * vpCbsSessionClassFactory
0x14000a722  lea     r9, [rbp+var_28]
0x14000a726  lea     r8, IID_ICbsSession
0x14000a72d  xor     edx, edx
0x14000a72f  mov     rax, [rcx]
0x14000a732  mov     rax, [rax+18h]
0x14000a736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a73b  mov     ebx, eax
0x14000a73d  test    eax, eax
0x14000a73f  jns     short loc_14000A74C
0x14000a741  lea     r9, aFailedToCreate_5; "Failed to create cbs session"
0x14000a748  mov     edx, eax
0x14000a74a  jmp     short loc_14000A709
0x14000a74c  mov     rcx, [rbp+var_28]
0x14000a750  lea     r8, [rbp+var_18]
0x14000a754  lea     rdx, _GUID_fc2c7e52_df06_445e_8d83_ba125880ea0d
0x14000a75b  mov     rax, [rcx]
0x14000a75e  mov     rax, [rax]
0x14000a761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a766  mov     ebx, eax
0x14000a768  test    eax, eax
0x14000a76a  jns     short loc_14000A775
0x14000a76c  lea     r9, aFailedToQueryP; "Failed to query private session interfa"...
0x14000a773  jmp     short loc_14000A748
0x14000a775  mov     rcx, [rbp+var_18]
0x14000a779  mov     rdx, [rbp+TargetHandle]
0x14000a77d  mov     rax, [rcx]
0x14000a780  mov     rax, [rax+0D0h]
0x14000a787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a78c  mov     rcx, [rbp+var_28]
0x14000a790  lea     r8, [rbp+var_20]
0x14000a794  lea     rdx, IID_ICbsSession8
0x14000a79b  mov     rax, [rcx]
0x14000a79e  mov     rax, [rax]
0x14000a7a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a7a6  mov     ebx, eax
0x14000a7a8  test    eax, eax
0x14000a7aa  jns     short loc_14000A7B5
0x14000a7ac  lea     r9, aFailedToQueryI; "Failed to query ICbsSession8 interface"
0x14000a7b3  jmp     short loc_14000A748
0x14000a7b5  mov     rax, [rbp+var_20]
0x14000a7b9  mov     [r14], rax
0x14000a7bc  mov     [rbp+var_20], 0
0x14000a7c4  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14000a7c8  jz      short loc_14000A7D3
0x14000a7ca  mov     rcx, rsi; hObject
0x14000a7cd  call    cs:__imp_CloseHandle
0x14000a7d3  mov     rcx, [rbp+var_28]
0x14000a7d7  test    rcx, rcx
0x14000a7da  jz      short loc_14000A7F0
0x14000a7dc  mov     rax, [rcx]
0x14000a7df  mov     rax, [rax+10h]
0x14000a7e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a7e8  mov     [rbp+var_28], 0
0x14000a7f0  mov     rcx, [rbp+var_20]
0x14000a7f4  test    rcx, rcx
0x14000a7f7  jz      short loc_14000A80D
0x14000a7f9  mov     rax, [rcx]
0x14000a7fc  mov     rax, [rax+10h]
0x14000a800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a805  mov     [rbp+var_20], 0
0x14000a80d  mov     rcx, [rbp+var_18]
0x14000a811  test    rcx, rcx
0x14000a814  jz      short loc_14000A822
0x14000a816  mov     rax, [rcx]
0x14000a819  mov     rax, [rax+10h]
0x14000a81d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a822  mov     eax, gs:179Ch
0x14000a82a  test    eax, eax
0x14000a82c  jz      short loc_14000A84D
0x14000a82e  lea     rax, aCcbsworkerCrea; "CCbsWorker::CreateCbsSession"
0x14000a835  xor     r8d, r8d
0x14000a838  lea     r9, aErrorNotRevers; "Error: Not reversed from impersonation "...
0x14000a83f  mov     qword ptr [rsp+80h+dwDesiredAccess], rax
0x14000a844  xor     edx, edx
0x14000a846  mov     ecx, edi
0x14000a848  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000a84d  lea     rcx, [rbp+var_40]; this
0x14000a851  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x14000a856  mov     eax, ebx
0x14000a858  mov     rcx, [rbp+var_8]
0x14000a85c  xor     rcx, rsp; StackCookie
0x14000a85f  call    __security_check_cookie
0x14000a864  mov     rbx, [rsp+80h+arg_8]
0x14000a86c  add     rsp, 80h
0x14000a873  pop     r15
0x14000a875  pop     r14
0x14000a877  pop     rdi
0x14000a878  pop     rsi
0x14000a879  pop     rbp
0x14000a87a  retn
```
