# __report_securityfailure

- ea: `0x18007b050`
- end: `0x18007b0f0`
- name: `__report_securityfailure`
- size: `160`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18007b038`

## callees

- `0x18007af1c`
- `0x18007b050`
- `0x18007b0f0`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x18007b05d`
- `KERNEL32!IsProcessorFeaturePresent` at `0x18007b05d`

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
  qword_1800BA210 = retaddr;
  dword_1800BA200 = -1073740791;
  dword_1800BA204 = 1;
  dword_1800BA218 = 1;
  qword_1800BA220[0] = v2;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x18007b050  mov     [rsp+arg_0], ecx
0x18007b054  sub     rsp, 28h
0x18007b058  mov     ecx, 17h; ProcessorFeature
0x18007b05d  call    cs:IsProcessorFeaturePresent
0x18007b063  test    eax, eax
0x18007b065  jz      short loc_18007B06F
0x18007b067  mov     eax, [rsp+28h+arg_0]
0x18007b06b  mov     ecx, eax
0x18007b06d  int     29h; Win8: RtlFailFast(ecx)
0x18007b06f  lea     rcx, ContextRecord; ContextRecord
0x18007b076  call    capture_current_context
0x18007b07b  mov     rax, [rsp+28h]
0x18007b080  mov     cs:ContextRecord.Rip, rax
0x18007b087  lea     rax, [rsp+28h]
0x18007b08c  add     rax, 8
0x18007b090  mov     cs:ContextRecord.Rsp, rax
0x18007b097  mov     rax, cs:ContextRecord.Rip
0x18007b09e  mov     cs:qword_1800BA210, rax
0x18007b0a5  mov     cs:dword_1800BA200, 0C0000409h
0x18007b0af  mov     cs:dword_1800BA204, 1
0x18007b0b9  mov     cs:dword_1800BA218, 1
0x18007b0c3  mov     eax, 8
0x18007b0c8  imul    rax, 0
0x18007b0cc  lea     rcx, qword_1800BA220
0x18007b0d3  mov     edx, [rsp+28h+arg_0]
0x18007b0d7  mov     [rcx+rax], rdx
0x18007b0db  lea     rcx, ExceptionInfo; ExceptionInfo
0x18007b0e2  call    __raise_securityfailure
0x18007b0e7  nop
0x18007b0e8  jmp     short $+2
0x18007b0ea  nop
0x18007b0eb  add     rsp, 28h
0x18007b0ef  retn
```
