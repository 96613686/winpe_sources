# CCbsWorker::StopIdleProcessing(void)

- ea: `0x14000caa0`
- end: `0x14000cb0d`
- name: `?StopIdleProcessing@CCbsWorker@@SAJXZ`
- size: `109`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b174`
- `0x14000cd48`

## callees

- `0x14000caa0`
- `0x14000e328`
- `0x14002b010`

## string_xrefs

- `0x14000caed`: `Error: Not reversed from impersonation on func: %s`

## pseudocode

```c
__int64 CCbsWorker::StopIdleProcessing(void)
{
  unsigned int v0; // ebx

  if ( vpfnCbsCoreStopIdleProcessing )
  {
    v0 = vpfnCbsCoreStopIdleProcessing();
  }
  else
  {
    v0 = -2147467263;
    CBSWdsLog(0x4000000u, -2147467263, (size_t *)1, "CbsCoreStopIdleProcessing is not implemented.");
  }
  if ( NtCurrentTeb()->IsImpersonating )
    CBSWdsLog(0x4000000u, 0, 0, "Error: Not reversed from impersonation on func: %s", "CCbsWorker::StopIdleProcessing");
  return v0;
}

```

## disassembly

```asm
0x14000caa0  push    rbx
0x14000caa2  sub     rsp, 30h
0x14000caa6  mov     rax, cs:?vpfnCbsCoreStopIdleProcessing@@3P6AJXZEA; long (*vpfnCbsCoreStopIdleProcessing)(void)
0x14000caad  test    rax, rax
0x14000cab0  jnz     short loc_14000CAD0
0x14000cab2  mov     ebx, 80004001h
0x14000cab7  lea     r9, aCbscorestopidl; "CbsCoreStopIdleProcessing is not implem"...
0x14000cabe  mov     edx, ebx
0x14000cac0  lea     r8d, [rax+1]
0x14000cac4  mov     ecx, 4000000h
0x14000cac9  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000cace  jmp     short loc_14000CAD7
0x14000cad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cad5  mov     ebx, eax
0x14000cad7  mov     edx, gs:179Ch
0x14000cadf  test    edx, edx
0x14000cae1  jz      short loc_14000CB05
0x14000cae3  lea     rax, aCcbsworkerStop; "CCbsWorker::StopIdleProcessing"
0x14000caea  xor     r8d, r8d
0x14000caed  lea     r9, aErrorNotRevers; "Error: Not reversed from impersonation "...
0x14000caf4  mov     [rsp+38h+var_18], rax
0x14000caf9  xor     edx, edx
0x14000cafb  mov     ecx, 4000000h
0x14000cb00  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000cb05  mov     eax, ebx
0x14000cb07  add     rsp, 30h
0x14000cb0b  pop     rbx
0x14000cb0c  retn
```
