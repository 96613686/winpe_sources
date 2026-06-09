# EdpInitPluginRuntimeConfig

- ea: `0x14002bf44`
- end: `0x14002bfe3`
- name: `EdpInitPluginRuntimeConfig`
- size: `159`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14002bb30`
- `0x14002cc34`

## callees

- `0x140024530`
- `0x14002459c`
- `0x14002d1bc`

## pseudocode

```c
__int64 EdpInitPluginRuntimeConfig()
{
  __int64 v0; // rcx
  __int64 v1; // rcx
  int v3; // [rsp+40h] [rbp+10h] BYREF
  int v4; // [rsp+48h] [rbp+18h] BYREF
  __int64 v5; // [rsp+50h] [rbp+20h] BYREF

  v5 = 0;
  v4 = 0;
  v3 = 0;
  EdpReadPluginConfig((__int64)byte_140019508);
  SrpLoadPlugin(v0, &AiCategoryExe, &v5, (unsigned int *)&v3, &v4);
  dword_140019530 = v3;
  SrpFreePlugin(v5, (unsigned int)v3);
  v5 = 0;
  v3 = 0;
  SrpLoadPlugin(v1, &AiCategoryAppx, &v5, (unsigned int *)&v3, &v4);
  dword_140019534 = v3;
  return SrpFreePlugin(v5, (unsigned int)v3);
}

```

## disassembly

```asm
0x14002bf44  push    rbp
0x14002bf46  mov     rbp, rsp
0x14002bf49  sub     rsp, 30h
0x14002bf4d  lea     rcx, byte_140019508
0x14002bf54  mov     [rbp+arg_10], 0
0x14002bf5c  mov     [rbp+arg_8], 0
0x14002bf63  mov     [rbp+arg_0], 0
0x14002bf6a  call    EdpReadPluginConfig
0x14002bf6f  lea     rax, [rbp+arg_8]
0x14002bf73  lea     r9, [rbp+arg_0]
0x14002bf77  mov     [rsp+30h+var_10], rax
0x14002bf7c  lea     r8, [rbp+arg_10]
0x14002bf80  lea     rdx, AiCategoryExe
0x14002bf87  call    SrpLoadPlugin
0x14002bf8c  mov     edx, [rbp+arg_0]
0x14002bf8f  mov     rcx, [rbp+arg_10]
0x14002bf93  mov     cs:dword_140019530, edx
0x14002bf99  call    SrpFreePlugin
0x14002bf9e  lea     rax, [rbp+arg_8]
0x14002bfa2  mov     [rbp+arg_10], 0
0x14002bfaa  lea     r9, [rbp+arg_0]
0x14002bfae  mov     [rsp+30h+var_10], rax
0x14002bfb3  lea     r8, [rbp+arg_10]
0x14002bfb7  mov     [rbp+arg_0], 0
0x14002bfbe  lea     rdx, AiCategoryAppx
0x14002bfc5  call    SrpLoadPlugin
0x14002bfca  mov     edx, [rbp+arg_0]
0x14002bfcd  mov     rcx, [rbp+arg_10]
0x14002bfd1  mov     cs:dword_140019534, edx
0x14002bfd7  call    SrpFreePlugin
0x14002bfdc  add     rsp, 30h
0x14002bfe0  pop     rbp
0x14002bfe1  retn
```
