# __report_gsfailure

- ea: `0x180004350`
- end: `0x180004421`
- name: `__report_gsfailure`
- size: `209`
- prototype: `void __cdecl __noreturn(uintptr_t StackCookie)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003a70`

## callees

- `0x180004310`
- `0x180004350`
- `0x180004424`
- `0x1800049b4`

## pseudocode

```c
void __cdecl __noreturn _report_gsfailure(uintptr_t StackCookie)
{
  DWORD64 retaddr; // [rsp+38h] [rbp+0h]
  uintptr_t v2; // [rsp+40h] [rbp+8h] BYREF

  v2 = StackCookie;
  if ( IsProcessorFeaturePresent_0(0x17u) )
    __fastfail(2u);
  capture_previous_context(&ContextRecord);
  ContextRecord.Rip = retaddr;
  ContextRecord.Rsp = (DWORD64)&v2;
  qword_1800081C0 = retaddr;
  ContextRecord.Rcx = v2;
  dword_1800081B0 = -1073740791;
  dword_1800081B4 = 1;
  dword_1800081C8 = 1;
  unk_1800081D0 = 2;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180004350  mov     [rsp+arg_0], rcx
0x180004355  sub     rsp, 38h
0x180004359  mov     ecx, 17h; ProcessorFeature
0x18000435e  call    IsProcessorFeaturePresent_0
0x180004363  test    eax, eax
0x180004365  jz      short loc_18000436E
0x180004367  mov     ecx, 2
0x18000436c  int     29h; Win8: RtlFailFast(ecx)
0x18000436e  lea     rcx, ContextRecord; ContextRecord
0x180004375  call    capture_previous_context
0x18000437a  mov     rax, [rsp+38h]
0x18000437f  mov     cs:ContextRecord.Rip, rax
0x180004386  lea     rax, [rsp+38h]
0x18000438b  add     rax, 8
0x18000438f  mov     cs:ContextRecord.Rsp, rax
0x180004396  mov     rax, cs:ContextRecord.Rip
0x18000439d  mov     cs:qword_1800081C0, rax
0x1800043a4  mov     rax, [rsp+38h+arg_0]
0x1800043a9  mov     cs:ContextRecord.Rcx, rax
0x1800043b0  mov     cs:dword_1800081B0, 0C0000409h
0x1800043ba  mov     cs:dword_1800081B4, 1
0x1800043c4  mov     cs:dword_1800081C8, 1
0x1800043ce  mov     eax, 8
0x1800043d3  imul    rax, 0
0x1800043d7  lea     rcx, unk_1800081D0
0x1800043de  mov     qword ptr [rcx+rax], 2
0x1800043e6  mov     eax, 8
0x1800043eb  imul    rax, 0
0x1800043ef  mov     rcx, cs:__security_cookie
0x1800043f6  mov     [rsp+rax+38h+var_18], rcx
0x1800043fb  mov     eax, 8
0x180004400  imul    rax, 1
0x180004404  mov     rcx, cs:__security_cookie_complement
0x18000440b  mov     [rsp+rax+38h+var_18], rcx
0x180004410  lea     rcx, ExceptionInfo; ExceptionInfo
0x180004417  call    __raise_securityfailure
0x18000441c  add     rsp, 38h
0x180004420  retn
```
