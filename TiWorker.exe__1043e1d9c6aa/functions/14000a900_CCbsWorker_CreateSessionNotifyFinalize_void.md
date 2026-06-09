# CCbsWorker::CreateSessionNotifyFinalize(void)

- ea: `0x14000a900`
- end: `0x14000a96d`
- name: `?CreateSessionNotifyFinalize@CCbsWorker@@UEAAJXZ`
- size: `109`
- prototype: `__int64 __fastcall(CCbsWorker *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400094c0`

## callees

- `0x14000a900`
- `0x14000e328`
- `0x14002b010`

## string_xrefs

- `0x14000a94d`: `Error: Not reversed from impersonation on func: %s`
- `0x14000a917`: `CreateSessionNotifyFinalize is not implemented.`
- `0x14000a943`: `CCbsWorker::CreateSessionNotifyFinalize`

## pseudocode

```c
__int64 __fastcall CCbsWorker::CreateSessionNotifyFinalize(CCbsWorker *this)
{
  unsigned int SessionNotifyFinalize; // ebx

  if ( vpfnCbsCreateSessionNotifyFinalize )
  {
    SessionNotifyFinalize = vpfnCbsCreateSessionNotifyFinalize();
  }
  else
  {
    SessionNotifyFinalize = -2147467263;
    CBSWdsLog(0x4000000u, -2147467263, (size_t *)1, "CreateSessionNotifyFinalize is not implemented.");
  }
  if ( NtCurrentTeb()->IsImpersonating )
    CBSWdsLog(
      0x4000000u,
      0,
      0,
      "Error: Not reversed from impersonation on func: %s",
      "CCbsWorker::CreateSessionNotifyFinalize");
  return SessionNotifyFinalize;
}

```

## disassembly

```asm
0x14000a900  push    rbx
0x14000a902  sub     rsp, 30h
0x14000a906  mov     rax, cs:?vpfnCbsCreateSessionNotifyFinalize@@3P6AJXZEA; long (*vpfnCbsCreateSessionNotifyFinalize)(void)
0x14000a90d  test    rax, rax
0x14000a910  jnz     short loc_14000A930
0x14000a912  mov     ebx, 80004001h
0x14000a917  lea     r9, aCreatesessionn; "CreateSessionNotifyFinalize is not impl"...
0x14000a91e  mov     edx, ebx
0x14000a920  lea     r8d, [rax+1]
0x14000a924  mov     ecx, 4000000h
0x14000a929  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000a92e  jmp     short loc_14000A937
0x14000a930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a935  mov     ebx, eax
0x14000a937  mov     edx, gs:179Ch
0x14000a93f  test    edx, edx
0x14000a941  jz      short loc_14000A965
0x14000a943  lea     rax, aCcbsworkerCrea_2; "CCbsWorker::CreateSessionNotifyFinalize"
0x14000a94a  xor     r8d, r8d
0x14000a94d  lea     r9, aErrorNotRevers; "Error: Not reversed from impersonation "...
0x14000a954  mov     [rsp+38h+var_18], rax
0x14000a959  xor     edx, edx
0x14000a95b  mov     ecx, 4000000h
0x14000a960  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000a965  mov     eax, ebx
0x14000a967  add     rsp, 30h
0x14000a96b  pop     rbx
0x14000a96c  retn
```
