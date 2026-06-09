# int `Concurrency::details::SchedulerBase::InternalCreateScheduleGroup(details::location *)'::`1'::dtor$1

- ea: `0x1800292cc`
- end: `0x1800292d8`
- name: `?dtor$1@?0??InternalCreateScheduleGroup@SchedulerBase@details@Concurrency@@AEAAPEAVScheduleGroup@3@PEAVlocation@3@@Z@4HA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000d24c`

## pseudocode

```c
void __fastcall `Concurrency::details::SchedulerBase::InternalCreateScheduleGroup'::`1'::dtor$1(__int64 a1, __int64 a2)
{
  std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Tidy(*(_QWORD *)(a2 + 80));
}

```

## disassembly

```asm
0x1800292cc  mov     rcx, [rdx+50h]
0x1800292d3  jmp     ?_Tidy@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAAXXZ
```
