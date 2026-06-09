# std::vector<DISPLAYCONFIG_PATH_INFO,std::allocator<DISPLAYCONFIG_PATH_INFO>>::_Buy_nonzero(unsigned __int64)

- ea: `0x14000f004`
- end: `0x14000f05e`
- name: `?_Buy_nonzero@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAX_K@Z`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000df8c`

## callees

- `0x14000dd14`
- `0x14000f004`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000f02a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000f02a`

## pseudocode

```c
unsigned __int64 __fastcall std::vector<DISPLAYCONFIG_PATH_INFO>::_Buy_nonzero(__int64 *a1, unsigned __int64 a2)
{
  __int64 v4; // rax
  unsigned __int64 result; // rax
  unsigned __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  if ( a2 > 0x38E38E38E38E38ELL )
    std::_Xlength_error("vector too long");
  v6 = a2;
  v4 = std::_Allocate_at_least_helper<std::allocator<DISPLAYCONFIG_PATH_INFO>>((__int64)a1, &v6);
  *a1 = v4;
  a1[1] = v4;
  result = v4 + 72 * a2;
  a1[2] = result;
  return result;
}

```

## disassembly

```asm
0x14000f004  mov     [rsp+arg_0], rbx
0x14000f009  push    rdi
0x14000f00a  sub     rsp, 20h
0x14000f00e  mov     rax, 38E38E38E38E38Eh
0x14000f018  mov     rbx, rdx
0x14000f01b  mov     rdi, rcx
0x14000f01e  cmp     rdx, rax
0x14000f021  jbe     short loc_14000F031
0x14000f023  lea     rcx, aVectorTooLong; "vector too long"
0x14000f02a  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x14000f031  lea     rdx, [rsp+28h+arg_8]
0x14000f036  mov     [rsp+28h+arg_8], rbx
0x14000f03b  call    ??$_Allocate_at_least_helper@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@YAPEAUDISPLAYCONFIG_PATH_INFO@@AEAV?$allocator@UDISPLAYCONFIG_PATH_INFO@@@0@AEA_K@Z; std::_Allocate_at_least_helper<std::allocator<DISPLAYCONFIG_PATH_INFO>>(std::allocator<DISPLAYCONFIG_PATH_INFO> &,unsigned __int64 &)
0x14000f040  mov     [rdi], rax
0x14000f043  lea     rcx, [rbx+rbx*8]
0x14000f047  mov     rbx, [rsp+28h+arg_0]
0x14000f04c  mov     [rdi+8], rax
0x14000f050  lea     rax, [rax+rcx*8]
0x14000f054  mov     [rdi+10h], rax
0x14000f058  add     rsp, 20h
0x14000f05c  pop     rdi
0x14000f05d  retn
```
