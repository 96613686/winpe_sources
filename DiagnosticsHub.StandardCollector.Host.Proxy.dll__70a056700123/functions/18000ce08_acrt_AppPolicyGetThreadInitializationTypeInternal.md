# __acrt_AppPolicyGetThreadInitializationTypeInternal

- ea: `0x18000ce08`
- end: `0x18000ce64`
- name: `__acrt_AppPolicyGetThreadInitializationTypeInternal`
- size: `92`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180006a94`
- `0x180006bb0`
- `0x180006c20`

## callees

- `0x18000c8f8`
- `0x18000ce08`
- `0x180060150`

## string_xrefs

- `0x18000ce31`: `AppPolicyGetThreadInitializationType`

## pseudocode

```c
__int64 __fastcall _acrt_AppPolicyGetThreadInitializationTypeInternal(__int64 a1)
{
  FARPROC function_slow; // rax

  function_slow = (FARPROC)qword_18007F0D8;
  if ( qword_18007F0D8 != -1
    && (qword_18007F0D8
     || (function_slow = try_get_function_slow(
                           0x1Bu,
                           "AppPolicyGetThreadInitializationType",
                           (unsigned int *)byte_180064430,
                           (unsigned int *)&dword_180064434)) != 0) )
  {
    return ((__int64 (__fastcall *)(__int64, __int64))function_slow)(-6, a1);
  }
  else
  {
    return 3221226021LL;
  }
}

```

## disassembly

```asm
0x18000ce08  push    rbx
0x18000ce0a  sub     rsp, 20h
0x18000ce0e  mov     rax, cs:qword_18007F0D8
0x18000ce15  mov     rbx, rcx
0x18000ce18  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ce1c  jz      short loc_18000CE59
0x18000ce1e  test    rax, rax
0x18000ce21  jnz     short loc_18000CE45
0x18000ce23  lea     r9, dword_180064434
0x18000ce2a  lea     r8, byte_180064430
0x18000ce31  lea     rdx, aApppolicygetth; "AppPolicyGetThreadInitializationType"
0x18000ce38  lea     ecx, [rax+1Bh]
0x18000ce3b  call    try_get_function_slow
0x18000ce40  test    rax, rax
0x18000ce43  jz      short loc_18000CE59
0x18000ce45  mov     rdx, rbx
0x18000ce48  mov     rcx, 0FFFFFFFFFFFFFFFAh
0x18000ce4f  add     rsp, 20h
0x18000ce53  pop     rbx
0x18000ce54  jmp     _guard_dispatch_icall
0x18000ce59  mov     eax, 0C0000225h
0x18000ce5e  add     rsp, 20h
0x18000ce62  pop     rbx
0x18000ce63  retn
```
