# CCbsWorker::SetRebootInProgressFlag(void)

- ea: `0x14000c648`
- end: `0x14000c6b5`
- name: `?SetRebootInProgressFlag@CCbsWorker@@UEAAJXZ`
- size: `109`
- prototype: `__int64 __fastcall(CCbsWorker *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140009950`

## callees

- `0x14000c648`
- `0x14000e328`
- `0x14002b010`

## string_xrefs

- `0x14000c695`: `Error: Not reversed from impersonation on func: %s`

## pseudocode

```c
__int64 __fastcall CCbsWorker::SetRebootInProgressFlag(CCbsWorker *this)
{
  unsigned int v1; // ebx

  if ( vpfnCbsCoreSetRebootInProgressFlag )
  {
    v1 = vpfnCbsCoreSetRebootInProgressFlag();
  }
  else
  {
    v1 = -2147467263;
    CBSWdsLog(0x4000000u, -2147467263, (size_t *)1, "SetRebootInProgressFlag is not implemented.");
  }
  if ( NtCurrentTeb()->IsImpersonating )
    CBSWdsLog(
      0x4000000u,
      0,
      0,
      "Error: Not reversed from impersonation on func: %s",
      "CCbsWorker::SetRebootInProgressFlag");
  return v1;
}

```

## disassembly

```asm
0x14000c648  push    rbx
0x14000c64a  sub     rsp, 30h
0x14000c64e  mov     rax, cs:?vpfnCbsCoreSetRebootInProgressFlag@@3P6AJXZEA; long (*vpfnCbsCoreSetRebootInProgressFlag)(void)
0x14000c655  test    rax, rax
0x14000c658  jnz     short loc_14000C678
0x14000c65a  mov     ebx, 80004001h
0x14000c65f  lea     r9, aSetrebootinpro_0; "SetRebootInProgressFlag is not implemen"...
0x14000c666  mov     edx, ebx
0x14000c668  lea     r8d, [rax+1]
0x14000c66c  mov     ecx, 4000000h
0x14000c671  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000c676  jmp     short loc_14000C67F
0x14000c678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c67d  mov     ebx, eax
0x14000c67f  mov     edx, gs:179Ch
0x14000c687  test    edx, edx
0x14000c689  jz      short loc_14000C6AD
0x14000c68b  lea     rax, aCcbsworkerSetr; "CCbsWorker::SetRebootInProgressFlag"
0x14000c692  xor     r8d, r8d
0x14000c695  lea     r9, aErrorNotRevers; "Error: Not reversed from impersonation "...
0x14000c69c  mov     [rsp+38h+var_18], rax
0x14000c6a1  xor     edx, edx
0x14000c6a3  mov     ecx, 4000000h
0x14000c6a8  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000c6ad  mov     eax, ebx
0x14000c6af  add     rsp, 30h
0x14000c6b3  pop     rbx
0x14000c6b4  retn
```
