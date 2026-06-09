# __acrt_SetThreadStackGuarantee

- ea: `0x18000d9c8`
- end: `0x18000da1a`
- name: `__acrt_SetThreadStackGuarantee`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000c8f8`
- `0x18000d9c8`
- `0x180060150`

## string_xrefs

- `0x18000d9e3`: `SetThreadStackGuarantee`
- `0x18000d9f1`: `SetThreadStackGuarantee`

## pseudocode

```c
__int64 __fastcall _acrt_SetThreadStackGuarantee(__int64 a1)
{
  FARPROC function_slow; // rax

  function_slow = (FARPROC)qword_18007F0F0;
  if ( qword_18007F0F0 != -1
    && (qword_18007F0F0
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
0x18000d9c8  push    rbx
0x18000d9ca  sub     rsp, 20h
0x18000d9ce  mov     rax, cs:qword_18007F0F0
0x18000d9d5  mov     rbx, rcx
0x18000d9d8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d9dc  jz      short loc_18000DA12
0x18000d9de  test    rax, rax
0x18000d9e1  jnz     short loc_18000DA05
0x18000d9e3  lea     r9, aSetthreadstack; "SetThreadStackGuarantee"
0x18000d9ea  lea     r8, asc_1800644B0; "\a"
0x18000d9f1  lea     rdx, aSetthreadstack; "SetThreadStackGuarantee"
0x18000d9f8  lea     ecx, [rax+1Eh]
0x18000d9fb  call    try_get_function_slow
0x18000da00  test    rax, rax
0x18000da03  jz      short loc_18000DA12
0x18000da05  mov     rcx, rbx
0x18000da08  add     rsp, 20h
0x18000da0c  pop     rbx
0x18000da0d  jmp     _guard_dispatch_icall
0x18000da12  xor     eax, eax
0x18000da14  add     rsp, 20h
0x18000da18  pop     rbx
0x18000da19  retn
```
