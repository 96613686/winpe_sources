# GetCurrentFwConfig(void)

- ea: `0x180028f60`
- end: `0x180028fc4`
- name: `?GetCurrentFwConfig@@YAKXZ`
- size: `100`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800229a0`
- `0x180026784`

## callees

- `0x180028f60`
- `0x18002937c`

## import_xrefs

- `FirewallAPI!FWGetGlobalConfig` at `0x180028f9e`
- `FirewallAPI!FWGetGlobalConfig` at `0x180028f9e`

## pseudocode

```c
__int64 GetCurrentFwConfig(void)
{
  unsigned int v0; // eax
  unsigned int v1; // r8d
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v0 = FWGetGlobalConfig(545, 0, 5, 2);
  if ( v0 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x50, v1, (const char *)v0, 0);
  return 0;
}

```

## disassembly

```asm
0x180028f60  mov     r11, rsp
0x180028f63  sub     rsp, 48h
0x180028f67  lea     rax, [r11+10h]
0x180028f6b  mov     [rsp+48h+arg_0], 0
0x180028f73  mov     [r11-18h], rax
0x180028f77  xor     edx, edx
0x180028f79  lea     rax, [r11+8]
0x180028f7d  mov     [rsp+48h+arg_8], 4
0x180028f85  mov     [r11-20h], rax
0x180028f89  mov     ecx, 221h
0x180028f8e  mov     [rsp+48h+var_28], 0; unsigned int
0x180028f96  lea     r9d, [rdx+2]
0x180028f9a  lea     r8d, [rdx+5]
0x180028f9e  call    cs:__imp_FWGetGlobalConfig
0x180028fa4  test    eax, eax
0x180028fa6  jnz     short loc_180028FB1
0x180028fa8  mov     eax, [rsp+48h+arg_0]
0x180028fac  add     rsp, 48h
0x180028fb0  retn
0x180028fb1  mov     rcx, [rsp+48h]; this
0x180028fb6  mov     r9d, eax; char *
0x180028fb9  mov     edx, 50h ; 'P'; void *
0x180028fbe  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
