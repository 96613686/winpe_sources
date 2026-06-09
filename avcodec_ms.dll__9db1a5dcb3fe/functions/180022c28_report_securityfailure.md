# __report_securityfailure

- ea: `0x180022c28`
- end: `0x180022cc5`
- name: `__report_securityfailure`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180022c14`

## callees

- `0x180022b00`
- `0x180022c28`
- `0x180022cc8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x180022c35`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x180022c35`

## pseudocode

```c
void __fastcall __noreturn _report_securityfailure(unsigned int a1)
{
  DWORD64 retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v2; // [rsp+30h] [rbp+8h] BYREF

  v2 = a1;
  if ( IsProcessorFeaturePresent(0x17u) )
    __fastfail(v2);
  capture_current_context(&ContextRecord);
  ContextRecord.Rip = retaddr;
  ContextRecord.Rsp = (DWORD64)&v2;
  qword_18004C570 = retaddr;
  dword_18004C560 = -1073740791;
  dword_18004C564 = 1;
  dword_18004C578 = 1;
  qword_18004C580[0] = v2;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180022c28  mov     [rsp+arg_0], ecx
0x180022c2c  sub     rsp, 28h
0x180022c30  mov     ecx, 17h; ProcessorFeature
0x180022c35  call    cs:IsProcessorFeaturePresent
0x180022c3b  test    eax, eax
0x180022c3d  jz      short loc_180022C47
0x180022c3f  mov     eax, [rsp+28h+arg_0]
0x180022c43  mov     ecx, eax
0x180022c45  int     29h; Win8: RtlFailFast(ecx)
0x180022c47  lea     rcx, ContextRecord; ContextRecord
0x180022c4e  call    capture_current_context
0x180022c53  mov     rax, [rsp+28h]
0x180022c58  mov     cs:ContextRecord.Rip, rax
0x180022c5f  lea     rax, [rsp+28h]
0x180022c64  add     rax, 8
0x180022c68  mov     cs:ContextRecord.Rsp, rax
0x180022c6f  mov     rax, cs:ContextRecord.Rip
0x180022c76  mov     cs:qword_18004C570, rax
0x180022c7d  mov     cs:dword_18004C560, 0C0000409h
0x180022c87  mov     cs:dword_18004C564, 1
0x180022c91  mov     cs:dword_18004C578, 1
0x180022c9b  mov     eax, 8
0x180022ca0  imul    rax, 0
0x180022ca4  lea     rcx, qword_18004C580
0x180022cab  mov     edx, [rsp+28h+arg_0]
0x180022caf  mov     [rcx+rax], rdx
0x180022cb3  lea     rcx, ExceptionInfo; ExceptionInfo
0x180022cba  call    __raise_securityfailure
0x180022cbf  nop
0x180022cc0  add     rsp, 28h
0x180022cc4  retn
```
