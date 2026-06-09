# __report_gsfailure

- ea: `0x180001ba0`
- end: `0x180001c72`
- name: `__report_gsfailure`
- size: `210`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001540`

## callees

- `0x180001b64`
- `0x180001ba0`
- `0x180001c74`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x180001bae`
- `KERNEL32!IsProcessorFeaturePresent` at `0x180001bae`

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
  qword_1800030E0 = retaddr;
  ContextRecord.Rcx = v2;
  dword_1800030D0 = -1073740791;
  dword_1800030D4 = 1;
  dword_1800030E8 = 1;
  qword_1800030F0[0] = 2;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001ba0  mov     [rsp+arg_0], rcx
0x180001ba5  sub     rsp, 38h
0x180001ba9  mov     ecx, 17h; ProcessorFeature
0x180001bae  call    cs:__imp_IsProcessorFeaturePresent
0x180001bb4  test    eax, eax
0x180001bb6  jz      short loc_180001BBF
0x180001bb8  mov     ecx, 2
0x180001bbd  int     29h; Win8: RtlFailFast(ecx)
0x180001bbf  lea     rcx, ContextRecord; ContextRecord
0x180001bc6  call    capture_previous_context
0x180001bcb  mov     rax, [rsp+38h]
0x180001bd0  mov     cs:ContextRecord.Rip, rax
0x180001bd7  lea     rax, [rsp+38h]
0x180001bdc  add     rax, 8
0x180001be0  mov     cs:ContextRecord.Rsp, rax
0x180001be7  mov     rax, cs:ContextRecord.Rip
0x180001bee  mov     cs:qword_1800030E0, rax
0x180001bf5  mov     rax, [rsp+38h+arg_0]
0x180001bfa  mov     cs:ContextRecord.Rcx, rax
0x180001c01  mov     cs:dword_1800030D0, 0C0000409h
0x180001c0b  mov     cs:dword_1800030D4, 1
0x180001c15  mov     cs:dword_1800030E8, 1
0x180001c1f  mov     eax, 8
0x180001c24  imul    rax, 0
0x180001c28  lea     rcx, qword_1800030F0
0x180001c2f  mov     qword ptr [rcx+rax], 2
0x180001c37  mov     eax, 8
0x180001c3c  imul    rax, 0
0x180001c40  mov     rcx, cs:__security_cookie
0x180001c47  mov     [rsp+rax+38h+var_18], rcx
0x180001c4c  mov     eax, 8
0x180001c51  imul    rax, 1
0x180001c55  mov     rcx, cs:__security_cookie_complement
0x180001c5c  mov     [rsp+rax+38h+var_18], rcx
0x180001c61  lea     rcx, ExceptionInfo; ExceptionInfo
0x180001c68  call    __raise_securityfailure
0x180001c6d  add     rsp, 38h
0x180001c71  retn
```
