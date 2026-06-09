# __report_securityfailure

- ea: `0x18000cf38`
- end: `0x18000cfd4`
- name: `__report_securityfailure`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000cf24`

## callees

- `0x18000ce1c`
- `0x18000cf38`
- `0x18000cfd4`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x18000cf45`
- `KERNEL32!IsProcessorFeaturePresent` at `0x18000cf45`

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
  qword_180018330 = retaddr;
  dword_180018320 = -1073740791;
  dword_180018324 = 1;
  dword_180018338 = 1;
  qword_180018340[0] = v2;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x18000cf38  mov     [rsp+arg_0], ecx
0x18000cf3c  sub     rsp, 28h
0x18000cf40  mov     ecx, 17h; ProcessorFeature
0x18000cf45  call    cs:__imp_IsProcessorFeaturePresent
0x18000cf4b  test    eax, eax
0x18000cf4d  jz      short loc_18000CF57
0x18000cf4f  mov     eax, [rsp+28h+arg_0]
0x18000cf53  mov     ecx, eax
0x18000cf55  int     29h; Win8: RtlFailFast(ecx)
0x18000cf57  lea     rcx, ContextRecord; ContextRecord
0x18000cf5e  call    capture_current_context
0x18000cf63  mov     rax, [rsp+28h]
0x18000cf68  mov     cs:ContextRecord.Rip, rax
0x18000cf6f  lea     rax, [rsp+28h]
0x18000cf74  add     rax, 8
0x18000cf78  mov     cs:ContextRecord.Rsp, rax
0x18000cf7f  mov     rax, cs:ContextRecord.Rip
0x18000cf86  mov     cs:qword_180018330, rax
0x18000cf8d  mov     cs:dword_180018320, 0C0000409h
0x18000cf97  mov     cs:dword_180018324, 1
0x18000cfa1  mov     cs:dword_180018338, 1
0x18000cfab  mov     eax, 8
0x18000cfb0  imul    rax, 0
0x18000cfb4  lea     rcx, qword_180018340
0x18000cfbb  mov     edx, [rsp+28h+arg_0]
0x18000cfbf  mov     [rcx+rax], rdx
0x18000cfc3  lea     rcx, ExceptionInfo; ExceptionInfo
0x18000cfca  call    __raise_securityfailure
0x18000cfcf  add     rsp, 28h
0x18000cfd3  retn
```
