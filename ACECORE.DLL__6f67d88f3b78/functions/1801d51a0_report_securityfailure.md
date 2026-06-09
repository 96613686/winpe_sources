# __report_securityfailure

- ea: `0x1801d51a0`
- end: `0x1801d5240`
- name: `__report_securityfailure`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1801d5188`

## callees

- `0x1801d5078`
- `0x1801d51a0`
- `0x1801d5240`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x1801d51ad`
- `KERNEL32!IsProcessorFeaturePresent` at `0x1801d51ad`

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
  qword_18022C6A0 = retaddr;
  dword_18022C690 = -1073740791;
  dword_18022C694 = 1;
  dword_18022C6A8 = 1;
  qword_18022C6B0[0] = v2;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1801d51a0  mov     [rsp+arg_0], ecx
0x1801d51a4  sub     rsp, 28h
0x1801d51a8  mov     ecx, 17h; ProcessorFeature
0x1801d51ad  call    cs:IsProcessorFeaturePresent
0x1801d51b3  test    eax, eax
0x1801d51b5  jz      short loc_1801D51BF
0x1801d51b7  mov     eax, [rsp+28h+arg_0]
0x1801d51bb  mov     ecx, eax
0x1801d51bd  int     29h; Win8: RtlFailFast(ecx)
0x1801d51bf  lea     rcx, ContextRecord; ContextRecord
0x1801d51c6  call    capture_current_context
0x1801d51cb  mov     rax, [rsp+28h]
0x1801d51d0  mov     cs:ContextRecord.Rip, rax
0x1801d51d7  lea     rax, [rsp+28h]
0x1801d51dc  add     rax, 8
0x1801d51e0  mov     cs:ContextRecord.Rsp, rax
0x1801d51e7  mov     rax, cs:ContextRecord.Rip
0x1801d51ee  mov     cs:qword_18022C6A0, rax
0x1801d51f5  mov     cs:dword_18022C690, 0C0000409h
0x1801d51ff  mov     cs:dword_18022C694, 1
0x1801d5209  mov     cs:dword_18022C6A8, 1
0x1801d5213  mov     eax, 8
0x1801d5218  imul    rax, 0
0x1801d521c  lea     rcx, qword_18022C6B0
0x1801d5223  mov     edx, [rsp+28h+arg_0]
0x1801d5227  mov     [rcx+rax], rdx
0x1801d522b  lea     rcx, ExceptionInfo; ExceptionInfo
0x1801d5232  call    __raise_securityfailure
0x1801d5237  nop
0x1801d5238  jmp     short $+2
0x1801d523a  nop
0x1801d523b  add     rsp, 28h
0x1801d523f  retn
```
