# __report_securityfailure

- ea: `0x18000a468`
- end: `0x18000a505`
- name: `__report_securityfailure`
- size: `157`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a454`

## callees

- `0x18000a340`
- `0x18000a468`
- `0x18000a508`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x18000a475`
- `KERNEL32!IsProcessorFeaturePresent` at `0x18000a475`

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
  qword_180099760 = retaddr;
  dword_180099750 = -1073740791;
  dword_180099754 = 1;
  dword_180099768 = 1;
  qword_180099770[0] = v2;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x18000a468  mov     [rsp+arg_0], ecx
0x18000a46c  sub     rsp, 28h
0x18000a470  mov     ecx, 17h; ProcessorFeature
0x18000a475  call    cs:IsProcessorFeaturePresent
0x18000a47b  test    eax, eax
0x18000a47d  jz      short loc_18000A487
0x18000a47f  mov     eax, [rsp+28h+arg_0]
0x18000a483  mov     ecx, eax
0x18000a485  int     29h; Win8: RtlFailFast(ecx)
0x18000a487  lea     rcx, ContextRecord; ContextRecord
0x18000a48e  call    capture_current_context
0x18000a493  mov     rax, [rsp+28h]
0x18000a498  mov     cs:ContextRecord.Rip, rax
0x18000a49f  lea     rax, [rsp+28h]
0x18000a4a4  add     rax, 8
0x18000a4a8  mov     cs:ContextRecord.Rsp, rax
0x18000a4af  mov     rax, cs:ContextRecord.Rip
0x18000a4b6  mov     cs:qword_180099760, rax
0x18000a4bd  mov     cs:dword_180099750, 0C0000409h
0x18000a4c7  mov     cs:dword_180099754, 1
0x18000a4d1  mov     cs:dword_180099768, 1
0x18000a4db  mov     eax, 8
0x18000a4e0  imul    rax, 0
0x18000a4e4  lea     rcx, qword_180099770
0x18000a4eb  mov     edx, [rsp+28h+arg_0]
0x18000a4ef  mov     [rcx+rax], rdx
0x18000a4f3  lea     rcx, ExceptionInfo; ExceptionInfo
0x18000a4fa  call    __raise_securityfailure
0x18000a4ff  nop
0x18000a500  add     rsp, 28h
0x18000a504  retn
```
