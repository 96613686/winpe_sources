# TiFinalize

- ea: `0x140009334`
- end: `0x140009431`
- name: `TiFinalize`
- size: `253`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x140009650`

## callees

- `0x140009334`
- `0x14001681c`
- `0x140017658`
- `0x14001c74c`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009393`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400093b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009393`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400093b5`

## string_xrefs

- `0x14000933a`: `Starting TrustedInstaller finalization.`
- `0x1400093f7`: `Ending TrustedInstaller finalization.`
- `0x140009414`: `Ending TrustedInstaller finalization.`

## pseudocode

```c
__int64 TiFinalize()
{
  char *v0; // rcx
  unsigned int i; // ebx
  __int64 v2; // rcx
  __int128 v4; // [rsp+20h] [rbp-18h] BYREF

  CBSWdsLogLight(0x4000000u, 0, 0, "Starting TrustedInstaller finalization.");
  if ( vpCbsWorkerStream )
  {
    v0 = (char *)vpCbsWorkerStream + *(int *)(*((_QWORD *)vpCbsWorkerStream + 1) + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v0 + 16LL))(v0);
    vpCbsWorkerStream = 0;
  }
  if ( (char *)vhShutdownEvent - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(vhShutdownEvent);
    vhShutdownEvent = 0;
  }
  if ( (char *)vhServicingEvent - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(vhServicingEvent);
    vhServicingEvent = 0;
  }
  TiCoreWinlogonNotificationsFinalize();
  for ( i = 0; i < 4; ++i )
  {
    v2 = qword_14003F290[4 * (int)i];
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  CBSWdsLogLight(0x4000000u, 0, 0, "Ending TrustedInstaller finalization.");
  v4 = CbsTiFinalizeEvent;
  return CbsGenericEventReport(&v4, L"Ending TrustedInstaller finalization.");
}

```

## disassembly

```asm
0x140009334  push    rbx
0x140009336  sub     rsp, 30h
0x14000933a  lea     r9, aStartingTruste; "Starting TrustedInstaller finalization."
0x140009341  xor     r8d, r8d
0x140009344  xor     edx, edx
0x140009346  mov     ecx, 4000000h
0x14000934b  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140009350  mov     rdx, cs:?vpCbsWorkerStream@@3PEAVCCbsInprocIStream@@EA; CCbsInprocIStream * vpCbsWorkerStream
0x140009357  test    rdx, rdx
0x14000935a  jz      short loc_140009382
0x14000935c  mov     rax, [rdx+8]
0x140009360  add     rdx, 8
0x140009364  movsxd  rcx, dword ptr [rax+4]
0x140009368  add     rcx, rdx
0x14000936b  mov     rax, [rcx]
0x14000936e  mov     rax, [rax+10h]
0x140009372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009377  mov     cs:?vpCbsWorkerStream@@3PEAVCCbsInprocIStream@@EA, 0; CCbsInprocIStream * vpCbsWorkerStream
0x140009382  mov     rcx, cs:?vhShutdownEvent@@3PEAXEA; hObject
0x140009389  lea     rax, [rcx-1]
0x14000938d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140009391  ja      short loc_1400093A4
0x140009393  call    cs:__imp_CloseHandle
0x140009399  mov     cs:?vhShutdownEvent@@3PEAXEA, 0; void * vhShutdownEvent
0x1400093a4  mov     rcx, cs:?vhServicingEvent@@3PEAXEA; hObject
0x1400093ab  lea     rax, [rcx-1]
0x1400093af  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400093b3  ja      short loc_1400093C6
0x1400093b5  call    cs:__imp_CloseHandle
0x1400093bb  mov     cs:?vhServicingEvent@@3PEAXEA, 0; void * vhServicingEvent
0x1400093c6  call    TiCoreWinlogonNotificationsFinalize
0x1400093cb  xor     ebx, ebx
0x1400093cd  movsxd  rax, ebx
0x1400093d0  lea     rcx, qword_14003F290
0x1400093d7  shl     rax, 5
0x1400093db  mov     rcx, [rax+rcx]
0x1400093df  test    rcx, rcx
0x1400093e2  jz      short loc_1400093F0
0x1400093e4  mov     rax, [rcx]
0x1400093e7  mov     rax, [rax+10h]
0x1400093eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400093f0  inc     ebx
0x1400093f2  cmp     ebx, 4
0x1400093f5  jb      short loc_1400093CD
0x1400093f7  lea     r9, aEndingTrustedi_0; "Ending TrustedInstaller finalization."
0x1400093fe  xor     r8d, r8d
0x140009401  xor     edx, edx
0x140009403  mov     ecx, 4000000h
0x140009408  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000940d  movups  xmm0, cs:CbsTiFinalizeEvent
0x140009414  lea     rdx, aEndingTrustedi; "Ending TrustedInstaller finalization."
0x14000941b  lea     rcx, [rsp+38h+var_18]
0x140009420  movdqu  [rsp+38h+var_18], xmm0
0x140009426  call    CbsGenericEventReport
0x14000942b  add     rsp, 30h
0x14000942f  pop     rbx
0x140009430  retn
```
