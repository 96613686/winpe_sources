# __report_gsfailure

- ea: `0x140002790`
- end: `0x140002866`
- name: `__report_gsfailure`
- size: `214`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002390`

## callees

- `0x14000274c`
- `0x140002790`
- `0x140002868`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x14000279e`
- `KERNEL32!IsProcessorFeaturePresent` at `0x14000279e`

## pseudocode

```c
void __cdecl __noreturn _report_gsfailure(uintptr_t StackCookie)
{
  DWORD64 retaddr; // [rsp+38h] [rbp+0h]
  uintptr_t v2; // [rsp+40h] [rbp+8h] BYREF

  v2 = StackCookie;
  if ( IsProcessorFeaturePresent(0x17u) )
    __fastfail(2u);
  capture_previous_context(&ContextRecord);
  ContextRecord.Rip = retaddr;
  ContextRecord.Rsp = (DWORD64)&v2;
  qword_1400051A0 = retaddr;
  ContextRecord.Rcx = v2;
  dword_140005190 = -1073740791;
  dword_140005194 = 1;
  dword_1400051A8 = 1;
  qword_1400051B0[0] = 2;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x140002790  mov     [rsp+arg_0], rcx
0x140002795  sub     rsp, 38h
0x140002799  mov     ecx, 17h; ProcessorFeature
0x14000279e  call    cs:__imp_IsProcessorFeaturePresent
0x1400027a4  test    eax, eax
0x1400027a6  jz      short loc_1400027AF
0x1400027a8  mov     ecx, 2
0x1400027ad  int     29h; Win8: RtlFailFast(ecx)
0x1400027af  lea     rcx, ContextRecord; ContextRecord
0x1400027b6  call    capture_previous_context
0x1400027bb  mov     rax, [rsp+38h]
0x1400027c0  mov     cs:ContextRecord.Rip, rax
0x1400027c7  lea     rax, [rsp+38h]
0x1400027cc  add     rax, 8
0x1400027d0  mov     cs:ContextRecord.Rsp, rax
0x1400027d7  mov     rax, cs:ContextRecord.Rip
0x1400027de  mov     cs:qword_1400051A0, rax
0x1400027e5  mov     rax, [rsp+38h+arg_0]
0x1400027ea  mov     cs:ContextRecord.Rcx, rax
0x1400027f1  mov     cs:dword_140005190, 0C0000409h
0x1400027fb  mov     cs:dword_140005194, 1
0x140002805  mov     cs:dword_1400051A8, 1
0x14000280f  mov     eax, 8
0x140002814  imul    rax, 0
0x140002818  lea     rcx, qword_1400051B0
0x14000281f  mov     qword ptr [rcx+rax], 2
0x140002827  mov     eax, 8
0x14000282c  imul    rax, 0
0x140002830  mov     rcx, cs:__security_cookie
0x140002837  mov     [rsp+rax+38h+var_18], rcx
0x14000283c  mov     eax, 8
0x140002841  imul    rax, 1
0x140002845  mov     rcx, cs:__security_cookie_complement
0x14000284c  mov     [rsp+rax+38h+var_18], rcx
0x140002851  lea     rcx, ExceptionInfo; ExceptionInfo
0x140002858  call    __raise_securityfailure
0x14000285d  nop
0x14000285e  jmp     short $+2
0x140002860  nop
0x140002861  add     rsp, 38h
0x140002865  retn
```
