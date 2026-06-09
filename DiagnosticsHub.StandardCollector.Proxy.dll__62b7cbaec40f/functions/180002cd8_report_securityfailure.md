# __report_securityfailure

- ea: `0x180002cd8`
- end: `0x180002d75`
- name: `__report_securityfailure`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002cc4`

## callees

- `0x180002bb0`
- `0x180002cd8`
- `0x180002e88`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x180002ce5`
- `KERNEL32!IsProcessorFeaturePresent` at `0x180002ce5`

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
  qword_18007B2E0 = retaddr;
  dword_18007B2D0 = -1073740791;
  dword_18007B2D4 = 1;
  dword_18007B2E8 = 1;
  qword_18007B2F0[0] = v2;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180002cd8  mov     [rsp+arg_0], ecx
0x180002cdc  sub     rsp, 28h
0x180002ce0  mov     ecx, 17h; ProcessorFeature
0x180002ce5  call    cs:__imp_IsProcessorFeaturePresent
0x180002ceb  test    eax, eax
0x180002ced  jz      short loc_180002CF7
0x180002cef  mov     eax, [rsp+28h+arg_0]
0x180002cf3  mov     ecx, eax
0x180002cf5  int     29h; Win8: RtlFailFast(ecx)
0x180002cf7  lea     rcx, ContextRecord; ContextRecord
0x180002cfe  call    capture_current_context
0x180002d03  mov     rax, [rsp+28h]
0x180002d08  mov     cs:ContextRecord.Rip, rax
0x180002d0f  lea     rax, [rsp+28h]
0x180002d14  add     rax, 8
0x180002d18  mov     cs:ContextRecord.Rsp, rax
0x180002d1f  mov     rax, cs:ContextRecord.Rip
0x180002d26  mov     cs:qword_18007B2E0, rax
0x180002d2d  mov     cs:dword_18007B2D0, 0C0000409h
0x180002d37  mov     cs:dword_18007B2D4, 1
0x180002d41  mov     cs:dword_18007B2E8, 1
0x180002d4b  mov     eax, 8
0x180002d50  imul    rax, 0
0x180002d54  lea     rcx, qword_18007B2F0
0x180002d5b  mov     edx, [rsp+28h+arg_0]
0x180002d5f  mov     [rcx+rax], rdx
0x180002d63  lea     rcx, ExceptionInfo; ExceptionInfo
0x180002d6a  call    __raise_securityfailure
0x180002d6f  nop
0x180002d70  add     rsp, 28h
0x180002d74  retn
```
