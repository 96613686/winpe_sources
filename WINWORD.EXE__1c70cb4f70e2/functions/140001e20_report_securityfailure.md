# __report_securityfailure

- ea: `0x140001e20`
- end: `0x140001ec0`
- name: `__report_securityfailure`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140001e08`

## callees

- `0x140001cec`
- `0x140001e20`
- `0x140001ec0`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x140001e2d`
- `KERNEL32!IsProcessorFeaturePresent` at `0x140001e2d`

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
  qword_1400091D0 = retaddr;
  dword_1400091C0 = -1073740791;
  dword_1400091C4 = 1;
  dword_1400091D8 = 1;
  qword_1400091E0[0] = v2;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x140001e20  mov     [rsp+arg_0], ecx
0x140001e24  sub     rsp, 28h
0x140001e28  mov     ecx, 17h; ProcessorFeature
0x140001e2d  call    cs:__imp_IsProcessorFeaturePresent
0x140001e33  test    eax, eax
0x140001e35  jz      short loc_140001E3F
0x140001e37  mov     eax, [rsp+28h+arg_0]
0x140001e3b  mov     ecx, eax
0x140001e3d  int     29h; Win8: RtlFailFast(ecx)
0x140001e3f  lea     rcx, ContextRecord; ContextRecord
0x140001e46  call    capture_current_context
0x140001e4b  mov     rax, [rsp+28h]
0x140001e50  mov     cs:ContextRecord.Rip, rax
0x140001e57  lea     rax, [rsp+28h]
0x140001e5c  add     rax, 8
0x140001e60  mov     cs:ContextRecord.Rsp, rax
0x140001e67  mov     rax, cs:ContextRecord.Rip
0x140001e6e  mov     cs:qword_1400091D0, rax
0x140001e75  mov     cs:dword_1400091C0, 0C0000409h
0x140001e7f  mov     cs:dword_1400091C4, 1
0x140001e89  mov     cs:dword_1400091D8, 1
0x140001e93  mov     eax, 8
0x140001e98  imul    rax, 0
0x140001e9c  lea     rcx, qword_1400091E0
0x140001ea3  mov     edx, [rsp+28h+arg_0]
0x140001ea7  mov     [rcx+rax], rdx
0x140001eab  lea     rcx, ExceptionInfo; ExceptionInfo
0x140001eb2  call    __raise_securityfailure
0x140001eb7  nop
0x140001eb8  jmp     short $+2
0x140001eba  nop
0x140001ebb  add     rsp, 28h
0x140001ebf  retn
```
