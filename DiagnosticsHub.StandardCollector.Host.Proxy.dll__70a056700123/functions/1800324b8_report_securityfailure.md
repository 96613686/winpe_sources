# __report_securityfailure

- ea: `0x1800324b8`
- end: `0x180032555`
- name: `__report_securityfailure`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800324a4`

## callees

- `0x180032390`
- `0x1800324b8`
- `0x180032668`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x1800324c5`
- `KERNEL32!IsProcessorFeaturePresent` at `0x1800324c5`

## pseudocode

```c
void __fastcall __noreturn _report_securityfailure(unsigned int a1)
{
  DWORD64 retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v2; // [rsp+30h] [rbp+8h] BYREF

  v2 = a1;
  if ( IsProcessorFeaturePresent(0x17u) )
    __fastfail(v2);
  capture_current_context_0(&ContextRecord);
  ContextRecord.Rip = retaddr;
  ContextRecord.Rsp = (DWORD64)&v2;
  qword_180079150 = retaddr;
  dword_180079140 = -1073740791;
  dword_180079144 = 1;
  dword_180079158 = 1;
  qword_180079160[0] = v2;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1800324b8  mov     [rsp+arg_0], ecx
0x1800324bc  sub     rsp, 28h
0x1800324c0  mov     ecx, 17h; ProcessorFeature
0x1800324c5  call    cs:__imp_IsProcessorFeaturePresent
0x1800324cb  test    eax, eax
0x1800324cd  jz      short loc_1800324D7
0x1800324cf  mov     eax, [rsp+28h+arg_0]
0x1800324d3  mov     ecx, eax
0x1800324d5  int     29h; Win8: RtlFailFast(ecx)
0x1800324d7  lea     rcx, ContextRecord; ContextRecord
0x1800324de  call    capture_current_context_0
0x1800324e3  mov     rax, [rsp+28h]
0x1800324e8  mov     cs:ContextRecord.Rip, rax
0x1800324ef  lea     rax, [rsp+28h]
0x1800324f4  add     rax, 8
0x1800324f8  mov     cs:ContextRecord.Rsp, rax
0x1800324ff  mov     rax, cs:ContextRecord.Rip
0x180032506  mov     cs:qword_180079150, rax
0x18003250d  mov     cs:dword_180079140, 0C0000409h
0x180032517  mov     cs:dword_180079144, 1
0x180032521  mov     cs:dword_180079158, 1
0x18003252b  mov     eax, 8
0x180032530  imul    rax, 0
0x180032534  lea     rcx, qword_180079160
0x18003253b  mov     edx, [rsp+28h+arg_0]
0x18003253f  mov     [rcx+rax], rdx
0x180032543  lea     rcx, ExceptionInfo; ExceptionInfo
0x18003254a  call    __raise_securityfailure
0x18003254f  nop
0x180032550  add     rsp, 28h
0x180032554  retn
```
