# std::vector<DISPLAYCONFIG_PATH_INFO,std::allocator<DISPLAYCONFIG_PATH_INFO>>::_Tidy(void)

- ea: `0x14000f1b0`
- end: `0x14000f204`
- name: `?_Tidy@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAXXZ`
- size: `84`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000e178`
- `0x14000e7e4`

## callees

- `0x14000dff4`
- `0x14000f1b0`

## pseudocode

```c
__int64 __fastcall std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy(__int64 *a1)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *a1;
  if ( v2 )
  {
    result = std::_Deallocate<16>(v2, 8 * ((a1[2] - v2) >> 3));
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000f1b0  push    rbx
0x14000f1b2  sub     rsp, 20h
0x14000f1b6  mov     rbx, rcx
0x14000f1b9  mov     rcx, [rcx]
0x14000f1bc  test    rcx, rcx
0x14000f1bf  jz      short loc_14000F1FE
0x14000f1c1  mov     rax, [rbx+10h]
0x14000f1c5  mov     rdx, 8E38E38E38E38E39h
0x14000f1cf  sub     rax, rcx
0x14000f1d2  sar     rax, 3
0x14000f1d6  imul    rax, rdx
0x14000f1da  lea     rdx, [rax+rax*8]
0x14000f1de  shl     rdx, 3
0x14000f1e2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14000f1e7  mov     qword ptr [rbx], 0
0x14000f1ee  mov     qword ptr [rbx+8], 0
0x14000f1f6  mov     qword ptr [rbx+10h], 0
0x14000f1fe  add     rsp, 20h
0x14000f202  pop     rbx
0x14000f203  retn
```
