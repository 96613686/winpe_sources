# __acrt_SetThreadStackGuarantee

- ea: `0x18000e128`
- end: `0x18000e17a`
- name: `__acrt_SetThreadStackGuarantee`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000d058`
- `0x18000e128`
- `0x180060430`

## string_xrefs

- `0x18000e143`: `SetThreadStackGuarantee`
- `0x18000e151`: `SetThreadStackGuarantee`

## pseudocode

```c
__int64 __fastcall _acrt_SetThreadStackGuarantee(__int64 a1)
{
  FARPROC function_slow; // rax

  function_slow = (FARPROC)qword_1800820F0;
  if ( qword_1800820F0 != -1
    && (qword_1800820F0
     || (function_slow = try_get_function_slow(
                           0x1Eu,
                           "SetThreadStackGuarantee",
                           (unsigned int *)"\a",
                           (unsigned int *)"SetThreadStackGuarantee")) != 0) )
  {
    return ((__int64 (__fastcall *)(__int64))function_slow)(a1);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x18000e128  push    rbx
0x18000e12a  sub     rsp, 20h
0x18000e12e  mov     rax, cs:qword_1800820F0
0x18000e135  mov     rbx, rcx
0x18000e138  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e13c  jz      short loc_18000E172
0x18000e13e  test    rax, rax
0x18000e141  jnz     short loc_18000E165
0x18000e143  lea     r9, aSetthreadstack; "SetThreadStackGuarantee"
0x18000e14a  lea     r8, asc_180067B90; "\a"
0x18000e151  lea     rdx, aSetthreadstack; "SetThreadStackGuarantee"
0x18000e158  lea     ecx, [rax+1Eh]
0x18000e15b  call    try_get_function_slow
0x18000e160  test    rax, rax
0x18000e163  jz      short loc_18000E172
0x18000e165  mov     rcx, rbx
0x18000e168  add     rsp, 20h
0x18000e16c  pop     rbx
0x18000e16d  jmp     _guard_dispatch_icall
0x18000e172  xor     eax, eax
0x18000e174  add     rsp, 20h
0x18000e178  pop     rbx
0x18000e179  retn
```
