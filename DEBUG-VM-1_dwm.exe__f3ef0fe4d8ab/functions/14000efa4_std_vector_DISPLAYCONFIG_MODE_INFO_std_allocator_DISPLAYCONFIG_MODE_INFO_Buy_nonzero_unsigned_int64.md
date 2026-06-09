# std::vector<DISPLAYCONFIG_MODE_INFO,std::allocator<DISPLAYCONFIG_MODE_INFO>>::_Buy_nonzero(unsigned __int64)

- ea: `0x14000efa4`
- end: `0x14000effd`
- name: `?_Buy_nonzero@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAX_K@Z`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000df24`

## callees

- `0x14000dce4`
- `0x14000efa4`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000efca`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000efca`

## pseudocode

```c
__int64 __fastcall std::vector<DISPLAYCONFIG_MODE_INFO>::_Buy_nonzero(__int64 *a1, unsigned __int64 a2)
{
  __int64 result; // rax
  unsigned __int64 v5; // [rsp+38h] [rbp+10h] BYREF

  if ( a2 > 0x3FFFFFFFFFFFFFFLL )
    std::_Xlength_error("vector too long");
  v5 = a2;
  result = std::_Allocate_at_least_helper<std::allocator<DISPLAYCONFIG_MODE_INFO>>((__int64)a1, &v5);
  *a1 = result;
  a1[1] = result;
  a1[2] = result + (a2 << 6);
  return result;
}

```

## disassembly

```asm
0x14000efa4  mov     [rsp+arg_0], rbx
0x14000efa9  push    rdi
0x14000efaa  sub     rsp, 20h
0x14000efae  mov     rax, 3FFFFFFFFFFFFFFh
0x14000efb8  mov     rbx, rdx
0x14000efbb  mov     rdi, rcx
0x14000efbe  cmp     rdx, rax
0x14000efc1  jbe     short loc_14000EFD1
0x14000efc3  lea     rcx, aVectorTooLong; "vector too long"
0x14000efca  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x14000efd1  lea     rdx, [rsp+28h+arg_8]
0x14000efd6  mov     [rsp+28h+arg_8], rbx
0x14000efdb  call    ??$_Allocate_at_least_helper@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@YAPEAUDISPLAYCONFIG_MODE_INFO@@AEAV?$allocator@UDISPLAYCONFIG_MODE_INFO@@@0@AEA_K@Z; std::_Allocate_at_least_helper<std::allocator<DISPLAYCONFIG_MODE_INFO>>(std::allocator<DISPLAYCONFIG_MODE_INFO> &,unsigned __int64 &)
0x14000efe0  shl     rbx, 6
0x14000efe4  add     rbx, rax
0x14000efe7  mov     [rdi], rax
0x14000efea  mov     [rdi+8], rax
0x14000efee  mov     [rdi+10h], rbx
0x14000eff2  mov     rbx, [rsp+28h+arg_0]
0x14000eff7  add     rsp, 20h
0x14000effb  pop     rdi
0x14000effc  retn
```
