# std::_Tree_buy<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>,std::allocator<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>>::_Buynode<std::pair<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>>>(std::pair<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,uint>> &&)

- ea: `0x180020398`
- end: `0x1800203f0`
- name: `??$_Buynode@U?$pair@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@?$_Tree_buy@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAX@1@$$QEAU?$pair@UtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@1@@Z`
- size: `88`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180020810`

## callees

- `0x1800124d8`
- `0x18002108c`

## pseudocode

```c
__int64 __fastcall std::_Tree_buy<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>>::_Buynode<std::pair<tagSFILENAMEwithATTRIBUTE,std::pair<CommonFileMappingRawBase *,unsigned int>>>(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // [rsp+30h] [rbp+8h]

  v4 = std::_Tree_buy<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,unsigned int>>>::_Buynode0();
  *(_WORD *)(v4 + 24) = 0;
  std::wstring::wstring(v4 + 32, a2);
  *(_DWORD *)(v4 + 64) = *(_DWORD *)(a2 + 32);
  *(_OWORD *)(v4 + 72) = *(_OWORD *)(a2 + 40);
  return v4;
}

```

## disassembly

```asm
0x180020398  mov     [rsp+arg_8], rbx
0x18002039d  mov     [rsp+arg_10], rsi
0x1800203a2  mov     [rsp+arg_0], rcx
0x1800203a7  push    rdi
0x1800203a8  sub     rsp, 20h
0x1800203ac  mov     rsi, rdx
0x1800203af  call    ?_Buynode0@?$_Tree_buy@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@V?$allocator@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBUtagSFILENAMEwithATTRIBUTE@@U?$pair@PEAVCommonFileMappingRawBase@@I@std@@@std@@PEAX@2@XZ; std::_Tree_buy<std::pair<tagSFILENAMEwithATTRIBUTE const,std::pair<CommonFileMappingRawBase *,uint>>>::_Buynode0(void)
0x1800203b4  mov     rdi, rax
0x1800203b7  mov     [rsp+28h+arg_0], rax
0x1800203bc  mov     word ptr [rax+18h], 0
0x1800203c2  mov     rdx, rsi
0x1800203c5  lea     rcx, [rax+20h]
0x1800203c9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800203ce  mov     ecx, [rsi+20h]
0x1800203d1  mov     [rdi+40h], ecx
0x1800203d4  movups  xmm0, xmmword ptr [rsi+28h]
0x1800203d8  movdqu  xmmword ptr [rdi+48h], xmm0
0x1800203dd  mov     rax, rdi
0x1800203e0  mov     rbx, [rsp+28h+arg_8]
0x1800203e5  mov     rsi, [rsp+28h+arg_10]
0x1800203ea  add     rsp, 20h
0x1800203ee  pop     rdi
0x1800203ef  retn
```
