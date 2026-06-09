# __report_gsfailure

- ea: `0x180003ff0`
- end: `0x1800040c2`
- name: `__report_gsfailure`
- size: `210`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003950`

## callees

- `0x180003fbc`
- `0x180003ff0`
- `0x1800040c4`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x180003ffe`
- `KERNEL32!IsProcessorFeaturePresent` at `0x180003ffe`

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
  qword_1800072C0 = retaddr;
  ContextRecord.Rcx = v2;
  dword_1800072B0 = -1073740791;
  dword_1800072B4 = 1;
  dword_1800072C8 = 1;
  qword_1800072D0[0] = 2;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180003ff0  mov     [rsp+arg_0], rcx
0x180003ff5  sub     rsp, 38h
0x180003ff9  mov     ecx, 17h; ProcessorFeature
0x180003ffe  call    cs:__imp_IsProcessorFeaturePresent
0x180004004  test    eax, eax
0x180004006  jz      short loc_18000400F
0x180004008  mov     ecx, 2
0x18000400d  int     29h; Win8: RtlFailFast(ecx)
0x18000400f  lea     rcx, ContextRecord; ContextRecord
0x180004016  call    capture_previous_context
0x18000401b  mov     rax, [rsp+38h]
0x180004020  mov     cs:ContextRecord.Rip, rax
0x180004027  lea     rax, [rsp+38h]
0x18000402c  add     rax, 8
0x180004030  mov     cs:ContextRecord.Rsp, rax
0x180004037  mov     rax, cs:ContextRecord.Rip
0x18000403e  mov     cs:qword_1800072C0, rax
0x180004045  mov     rax, [rsp+38h+arg_0]
0x18000404a  mov     cs:ContextRecord.Rcx, rax
0x180004051  mov     cs:dword_1800072B0, 0C0000409h
0x18000405b  mov     cs:dword_1800072B4, 1
0x180004065  mov     cs:dword_1800072C8, 1
0x18000406f  mov     eax, 8
0x180004074  imul    rax, 0
0x180004078  lea     rcx, qword_1800072D0
0x18000407f  mov     qword ptr [rcx+rax], 2
0x180004087  mov     eax, 8
0x18000408c  imul    rax, 0
0x180004090  mov     rcx, cs:__security_cookie
0x180004097  mov     [rsp+rax+38h+var_18], rcx
0x18000409c  mov     eax, 8
0x1800040a1  imul    rax, 1
0x1800040a5  mov     rcx, cs:__security_cookie_complement
0x1800040ac  mov     [rsp+rax+38h+var_18], rcx
0x1800040b1  lea     rcx, ExceptionInfo; ExceptionInfo
0x1800040b8  call    __raise_securityfailure
0x1800040bd  add     rsp, 38h
0x1800040c1  retn
```
