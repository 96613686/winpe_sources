# __acrt_AppPolicyGetThreadInitializationTypeInternal

- ea: `0x18000d568`
- end: `0x18000d5c4`
- name: `__acrt_AppPolicyGetThreadInitializationTypeInternal`
- size: `92`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800071f4`
- `0x180007310`
- `0x180007380`

## callees

- `0x18000d058`
- `0x18000d568`
- `0x180060430`

## string_xrefs

- `0x18000d591`: `AppPolicyGetThreadInitializationType`

## pseudocode

```c
__int64 __fastcall _acrt_AppPolicyGetThreadInitializationTypeInternal(__int64 a1)
{
  FARPROC function_slow; // rax

  function_slow = (FARPROC)qword_1800820D8;
  if ( qword_1800820D8 != -1
    && (qword_1800820D8
     || (function_slow = try_get_function_slow(
                           0x1Bu,
                           "AppPolicyGetThreadInitializationType",
                           (unsigned int *)byte_180067B10,
                           (unsigned int *)&dword_180067B14)) != 0) )
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
0x18000d568  push    rbx
0x18000d56a  sub     rsp, 20h
0x18000d56e  mov     rax, cs:qword_1800820D8
0x18000d575  mov     rbx, rcx
0x18000d578  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d57c  jz      short loc_18000D5B9
0x18000d57e  test    rax, rax
0x18000d581  jnz     short loc_18000D5A5
0x18000d583  lea     r9, dword_180067B14
0x18000d58a  lea     r8, byte_180067B10
0x18000d591  lea     rdx, aApppolicygetth; "AppPolicyGetThreadInitializationType"
0x18000d598  lea     ecx, [rax+1Bh]
0x18000d59b  call    try_get_function_slow
0x18000d5a0  test    rax, rax
0x18000d5a3  jz      short loc_18000D5B9
0x18000d5a5  mov     rdx, rbx
0x18000d5a8  mov     rcx, 0FFFFFFFFFFFFFFFAh
0x18000d5af  add     rsp, 20h
0x18000d5b3  pop     rbx
0x18000d5b4  jmp     _guard_dispatch_icall
0x18000d5b9  mov     eax, 0C0000225h
0x18000d5be  add     rsp, 20h
0x18000d5c2  pop     rbx
0x18000d5c3  retn
```
