# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x180007da0`
- end: `0x180007df2`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `22`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002560`
- `0x1800030f0`
- `0x180003fb0`
- `0x1800043d0`
- `0x1800066f0`
- `0x180007bc0`
- `0x180007c90`
- `0x180007d20`
- `0x180009960`
- `0x18000c344`
- `0x18000caa0`
- `0x18000d51c`
- `0x18001374c`
- `0x180014c2c`
- `0x180015c94`
- `0x1800167c8`
- `0x180016b9c`
- `0x180016ec0`
- `0x180016f18`
- `0x180016f84`
- `0x180017004`
- `0x180017b4c`

## callees

- `0x180007da0`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180007de7`
- `ntdll!EtwEventWriteTransfer` at `0x180007de7`

## pseudocode

```c

```

## disassembly

```asm
0x180007da0  sub     rsp, 38h
0x180007da4  mov     rcx, cs:qword_180028008
0x180007dab  mov     rax, [rsp+38h+arg_20]
0x180007db0  test    rcx, rcx
0x180007db3  jnz     short loc_180007DBD
0x180007db5  mov     [rax], rcx
0x180007db8  xor     r8d, r8d
0x180007dbb  jmp     short loc_180007DC9
0x180007dbd  mov     [rax], rcx
0x180007dc0  mov     r8d, 2
0x180007dc6  movzx   ecx, word ptr [rcx]
0x180007dc9  mov     [rax+8], ecx
0x180007dcc  mov     [rax+0Ch], r8d
0x180007dd0  xor     r8d, r8d
0x180007dd3  mov     rcx, cs:Microsoft_Windows_CertPolEng_Context
0x180007dda  mov     [rsp+38h+var_10], rax
0x180007ddf  mov     [rsp+38h+var_18], r9d
0x180007de4  xor     r9d, r9d
0x180007de7  call    cs:__imp_EtwEventWriteTransfer
0x180007ded  add     rsp, 38h
0x180007df1  retn
```
