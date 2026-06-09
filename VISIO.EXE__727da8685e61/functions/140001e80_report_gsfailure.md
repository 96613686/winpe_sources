# __report_gsfailure

- ea: `0x140001e80`
- end: `0x140001f56`
- name: `__report_gsfailure`
- size: `214`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400019f0`

## callees

- `0x140001e3c`
- `0x140001e80`
- `0x140001f58`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x140001e8e`
- `KERNEL32!IsProcessorFeaturePresent` at `0x140001e8e`

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
  qword_140004150 = retaddr;
  ContextRecord.Rcx = v2;
  dword_140004140 = -1073740791;
  dword_140004144 = 1;
  dword_140004158 = 1;
  qword_140004160[0] = 2;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x140001e80  mov     [rsp+arg_0], rcx
0x140001e85  sub     rsp, 38h
0x140001e89  mov     ecx, 17h; ProcessorFeature
0x140001e8e  call    cs:IsProcessorFeaturePresent
0x140001e94  test    eax, eax
0x140001e96  jz      short loc_140001E9F
0x140001e98  mov     ecx, 2
0x140001e9d  int     29h; Win8: RtlFailFast(ecx)
0x140001e9f  lea     rcx, ContextRecord; ContextRecord
0x140001ea6  call    capture_previous_context
0x140001eab  mov     rax, [rsp+38h]
0x140001eb0  mov     cs:ContextRecord.Rip, rax
0x140001eb7  lea     rax, [rsp+38h]
0x140001ebc  add     rax, 8
0x140001ec0  mov     cs:ContextRecord.Rsp, rax
0x140001ec7  mov     rax, cs:ContextRecord.Rip
0x140001ece  mov     cs:qword_140004150, rax
0x140001ed5  mov     rax, [rsp+38h+arg_0]
0x140001eda  mov     cs:ContextRecord.Rcx, rax
0x140001ee1  mov     cs:dword_140004140, 0C0000409h
0x140001eeb  mov     cs:dword_140004144, 1
0x140001ef5  mov     cs:dword_140004158, 1
0x140001eff  mov     eax, 8
0x140001f04  imul    rax, 0
0x140001f08  lea     rcx, qword_140004160
0x140001f0f  mov     qword ptr [rcx+rax], 2
0x140001f17  mov     eax, 8
0x140001f1c  imul    rax, 0
0x140001f20  mov     rcx, cs:__security_cookie
0x140001f27  mov     [rsp+rax+38h+var_18], rcx
0x140001f2c  mov     eax, 8
0x140001f31  imul    rax, 1
0x140001f35  mov     rcx, cs:qword_140004080
0x140001f3c  mov     [rsp+rax+38h+var_18], rcx
0x140001f41  lea     rcx, ExceptionInfo; ExceptionInfo
0x140001f48  call    __raise_securityfailure
0x140001f4d  nop
0x140001f4e  jmp     short $+2
0x140001f50  nop
0x140001f51  add     rsp, 38h
0x140001f55  retn
```
