# avcodec_get_supported_config

- ea: `0x1800040d0`
- end: `0x180004133`
- name: `avcodec_get_supported_config`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180009948`
- `0x180009d58`

## callees

- `0x1800040d0`
- `0x180005288`
- `0x180024140`

## pseudocode

```c
__int64 __fastcall avcodec_get_supported_config(__int64 a1, __int64 a2, int a3, int a4, __int64 a5, int *a6)
{
  int *v6; // r10
  __int64 (__fastcall *v7)(__int64); // rax
  int v9; // [rsp+58h] [rbp+10h] BYREF

  v9 = 0;
  if ( !a2 )
    a2 = *(_QWORD *)(a1 + 16);
  v6 = &v9;
  if ( a6 )
    v6 = a6;
  v7 = *(__int64 (__fastcall **)(__int64))(a2 + 184);
  if ( v7 )
    return v7(a1);
  else
    return sub_180005288(a1, a2, a3, a4, a5, (__int64)v6);
}

```

## disassembly

```asm
0x1800040d0  sub     rsp, 48h
0x1800040d4  mov     [rsp+48h+arg_8], 0
0x1800040dc  mov     r11, rcx
0x1800040df  test    rdx, rdx
0x1800040e2  jnz     short loc_1800040E8
0x1800040e4  mov     rdx, [rcx+10h]
0x1800040e8  mov     rax, [rsp+48h+arg_28]
0x1800040ed  lea     r10, [rsp+48h+arg_8]
0x1800040f2  test    rax, rax
0x1800040f5  cmovnz  r10, rax
0x1800040f9  mov     rax, [rdx+0B8h]
0x180004100  mov     [rsp+48h+var_20], r10
0x180004105  test    rax, rax
0x180004108  jz      short loc_18000411F
0x18000410a  mov     rcx, [rsp+48h+arg_20]
0x18000410f  mov     [rsp+48h+var_28], rcx
0x180004114  mov     rcx, r11
0x180004117  call    cs:__guard_dispatch_icall_fptr
0x18000411d  jmp     short loc_18000412E
0x18000411f  mov     rax, [rsp+48h+arg_20]
0x180004124  mov     [rsp+48h+var_28], rax
0x180004129  call    sub_180005288
0x18000412e  add     rsp, 48h
0x180004132  retn
```
