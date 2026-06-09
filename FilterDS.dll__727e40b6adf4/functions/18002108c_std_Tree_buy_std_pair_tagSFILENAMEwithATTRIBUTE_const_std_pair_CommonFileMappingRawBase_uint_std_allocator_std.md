# std::_Tree_buy<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>>::_Buynode0(void)

- ea: `0x18002108c`
- end: `0x1800210da`
- name: `?_Buynode0@?$_Tree_buy@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAX@2@XZ`
- size: `78`
- prototype: `_QWORD *()`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180020398`

## callees

- `0x180001a30`
- `0x180001bd8`
- `0x18002108c`

## pseudocode

```c
_QWORD *std::_Tree_buy<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>>::_Buynode0()
{
  _QWORD *result; // rax

  result = operator new(0x58u);
  if ( !result )
    std::_Xbad_alloc();
  *result = CommonFileMapping::m_mapSingleton;
  result[1] = CommonFileMapping::m_mapSingleton;
  result[2] = CommonFileMapping::m_mapSingleton;
  return result;
}

```

## disassembly

```asm
0x18002108c  mov     [rsp+arg_0], rcx
0x180021091  sub     rsp, 28h
0x180021095  mov     ecx, 58h ; 'X'; Size
0x18002109a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002109f  mov     rcx, rax
0x1800210a2  mov     [rsp+28h+arg_0], rax
0x1800210a7  test    rax, rax
0x1800210aa  jz      short loc_1800210D4
0x1800210ac  mov     rax, cs:?m_mapSingleton@CommonFileMapping@@0V?$map@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@@std@@A; std::map<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>> CommonFileMapping::m_mapSingleton
0x1800210b3  mov     [rcx], rax
0x1800210b6  mov     rax, cs:?m_mapSingleton@CommonFileMapping@@0V?$map@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@@std@@A; std::map<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>> CommonFileMapping::m_mapSingleton
0x1800210bd  mov     [rcx+8], rax
0x1800210c1  mov     rax, cs:?m_mapSingleton@CommonFileMapping@@0V?$map@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@@std@@A; std::map<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>> CommonFileMapping::m_mapSingleton
0x1800210c8  mov     [rcx+10h], rax
0x1800210cc  mov     rax, rcx
0x1800210cf  add     rsp, 28h
0x1800210d3  retn
0x1800210d4  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
