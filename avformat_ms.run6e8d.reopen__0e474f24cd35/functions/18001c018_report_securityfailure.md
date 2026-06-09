# __report_securityfailure

- ea: `0x18001c018`
- end: `0x18001c0b5`
- name: `__report_securityfailure`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001c004`

## callees

- `0x18001bef0`
- `0x18001c018`
- `0x18001c0b8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x18001c025`
- `api-ms-win-core-processthreads-l1-1-1!IsProcessorFeaturePresent` at `0x18001c025`

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
  qword_180031100 = retaddr;
  dword_1800310F0 = -1073740791;
  dword_1800310F4 = 1;
  dword_180031108 = 1;
  qword_180031110[0] = v2;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x18001c018  mov     [rsp+arg_0], ecx
0x18001c01c  sub     rsp, 28h
0x18001c020  mov     ecx, 17h; ProcessorFeature
0x18001c025  call    cs:IsProcessorFeaturePresent
0x18001c02b  test    eax, eax
0x18001c02d  jz      short loc_18001C037
0x18001c02f  mov     eax, [rsp+28h+arg_0]
0x18001c033  mov     ecx, eax
0x18001c035  int     29h; Win8: RtlFailFast(ecx)
0x18001c037  lea     rcx, ContextRecord; ContextRecord
0x18001c03e  call    capture_current_context
0x18001c043  mov     rax, [rsp+28h]
0x18001c048  mov     cs:ContextRecord.Rip, rax
0x18001c04f  lea     rax, [rsp+28h]
0x18001c054  add     rax, 8
0x18001c058  mov     cs:ContextRecord.Rsp, rax
0x18001c05f  mov     rax, cs:ContextRecord.Rip
0x18001c066  mov     cs:qword_180031100, rax
0x18001c06d  mov     cs:dword_1800310F0, 0C0000409h
0x18001c077  mov     cs:dword_1800310F4, 1
0x18001c081  mov     cs:dword_180031108, 1
0x18001c08b  mov     eax, 8
0x18001c090  imul    rax, 0
0x18001c094  lea     rcx, qword_180031110
0x18001c09b  mov     edx, [rsp+28h+arg_0]
0x18001c09f  mov     [rcx+rax], rdx
0x18001c0a3  lea     rcx, ExceptionInfo; ExceptionInfo
0x18001c0aa  call    __raise_securityfailure
0x18001c0af  nop
0x18001c0b0  add     rsp, 28h
0x18001c0b4  retn
```
