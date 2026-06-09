# std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>,0>>::find(tagSFILENAMEwithATTRIBUTE const &)

- ea: `0x18002164c`
- end: `0x1800216d5`
- name: `?find@?$_Tree@V?$_Tmap_traits@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@std@@@std@@@2@AEBUtagSFILENAMEwithATTRIBUTE@@@Z`
- size: `137`
- prototype: `__int64 *__fastcall(__int64, __int64 *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180020810`
- `0x180020d5c`

## callees

- `0x180020eb0`
- `0x18002164c`

## pseudocode

```c
__int64 *__fastcall std::_Tree<std::_Tmap_traits<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,unsigned int>,std::less<tagSFILENAMEwithATTRIBUTE>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>>,0>>::find(
        __int64 a1,
        __int64 *a2,
        __int64 a3)
{
  __int64 v3; // rax
  __int64 v6; // rbx
  __int64 v7; // r11
  __int64 *v8; // r11
  __int64 *result; // rax

  v3 = CommonFileMapping::m_mapSingleton;
  v6 = CommonFileMapping::m_mapSingleton;
  v7 = *(_QWORD *)(CommonFileMapping::m_mapSingleton + 8);
  if ( !*(_BYTE *)(v7 + 25) )
  {
    do
    {
      if ( (unsigned __int8)std::less<tagSFILENAMEwithATTRIBUTE>::operator()(a1, v7 + 32, a3) )
      {
        v7 = v8[2];
      }
      else
      {
        v6 = (__int64)v8;
        v7 = *v8;
      }
    }
    while ( !*(_BYTE *)(v7 + 25) );
    v3 = CommonFileMapping::m_mapSingleton;
  }
  if ( v6 == v3 )
    goto LABEL_10;
  if ( (unsigned __int8)std::less<tagSFILENAMEwithATTRIBUTE>::operator()(a1, a3, v6 + 32) )
  {
    v3 = CommonFileMapping::m_mapSingleton;
LABEL_10:
    v6 = v3;
  }
  result = a2;
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x18002164c  mov     [rsp+arg_0], rbx
0x180021651  mov     [rsp+arg_8], rsi
0x180021656  push    rdi
0x180021657  sub     rsp, 20h
0x18002165b  mov     rax, cs:?m_mapSingleton@CommonFileMapping@@0V?$map@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@@std@@A; std::map<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>> CommonFileMapping::m_mapSingleton
0x180021662  mov     rsi, r8
0x180021665  mov     rdi, rdx
0x180021668  mov     rbx, rax
0x18002166b  mov     r11, [rax+8]
0x18002166f  cmp     byte ptr [r11+19h], 0
0x180021674  jnz     short loc_1800216A0
0x180021676  lea     rdx, [r11+20h]
0x18002167a  mov     r8, rsi
0x18002167d  call    ??R?$less@UtagSFILENAMEwithATTRIBUTE@@@std@@QEBA_NAEBUtagSFILENAMEwithATTRIBUTE@@0@Z; std::less<tagSFILENAMEwithATTRIBUTE>::operator()(tagSFILENAMEwithATTRIBUTE const &,tagSFILENAMEwithATTRIBUTE const &)
0x180021682  test    al, al
0x180021684  jz      short loc_18002168C
0x180021686  mov     r11, [r11+10h]
0x18002168a  jmp     short loc_180021692
0x18002168c  mov     rbx, r11
0x18002168f  mov     r11, [r11]
0x180021692  cmp     byte ptr [r11+19h], 0
0x180021697  jz      short loc_180021676
0x180021699  mov     rax, cs:?m_mapSingleton@CommonFileMapping@@0V?$map@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@@std@@A; std::map<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>> CommonFileMapping::m_mapSingleton
0x1800216a0  cmp     rbx, rax
0x1800216a3  jz      short loc_1800216BC
0x1800216a5  lea     r8, [rbx+20h]
0x1800216a9  mov     rdx, rsi
0x1800216ac  call    ??R?$less@UtagSFILENAMEwithATTRIBUTE@@@std@@QEBA_NAEBUtagSFILENAMEwithATTRIBUTE@@0@Z; std::less<tagSFILENAMEwithATTRIBUTE>::operator()(tagSFILENAMEwithATTRIBUTE const &,tagSFILENAMEwithATTRIBUTE const &)
0x1800216b1  test    al, al
0x1800216b3  jz      short loc_1800216BF
0x1800216b5  mov     rax, cs:?m_mapSingleton@CommonFileMapping@@0V?$map@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@U?$less@UtagSFILENAMEwithATTRIBUTE@@@3@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@3@@std@@A; std::map<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>> CommonFileMapping::m_mapSingleton
0x1800216bc  mov     rbx, rax
0x1800216bf  mov     rsi, [rsp+28h+arg_8]
0x1800216c4  mov     rax, rdi
0x1800216c7  mov     [rdi], rbx
0x1800216ca  mov     rbx, [rsp+28h+arg_0]
0x1800216cf  add     rsp, 20h
0x1800216d3  pop     rdi
0x1800216d4  retn
```
