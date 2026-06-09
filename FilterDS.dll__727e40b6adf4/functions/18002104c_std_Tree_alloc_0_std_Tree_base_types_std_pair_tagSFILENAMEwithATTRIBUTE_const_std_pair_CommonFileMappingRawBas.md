# std::_Tree_alloc<0,std::_Tree_base_types<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>>>::_Buyheadnode(void)

- ea: `0x18002104c`
- end: `0x180021085`
- name: `?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAX@2@XZ`
- size: `57`
- prototype: `_QWORD *()`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800019d0`

## callees

- `0x180001a30`
- `0x180001bd8`
- `0x18002104c`

## pseudocode

```c
_QWORD *std::_Tree_alloc<0,std::_Tree_base_types<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>>>::_Buyheadnode()
{
  _QWORD *result; // rax

  result = operator new(0x58u);
  if ( !result )
    std::_Xbad_alloc();
  *result = result;
  result[1] = result;
  result[2] = result;
  *((_WORD *)result + 12) = 257;
  return result;
}

```

## disassembly

```asm
0x18002104c  mov     [rsp+arg_0], rcx
0x180021051  sub     rsp, 28h
0x180021055  mov     ecx, 58h ; 'X'; Size
0x18002105a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002105f  mov     [rsp+28h+arg_0], rax
0x180021064  test    rax, rax
0x180021067  jz      short loc_18002107F
0x180021069  mov     [rax], rax
0x18002106c  mov     [rax+8], rax
0x180021070  mov     [rax+10h], rax
0x180021074  mov     word ptr [rax+18h], 101h
0x18002107a  add     rsp, 28h
0x18002107e  retn
0x18002107f  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
