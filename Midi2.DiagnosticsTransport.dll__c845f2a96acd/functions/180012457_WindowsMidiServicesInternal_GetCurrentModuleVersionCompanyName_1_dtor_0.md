# _WindowsMidiServicesInternal::GetCurrentModuleVersionCompanyName_::_1_::dtor$0

- ea: `0x180012457`
- end: `0x180012463`
- name: `_WindowsMidiServicesInternal::GetCurrentModuleVersionCompanyName_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800115c4`

## pseudocode

```c
__int64 __fastcall WindowsMidiServicesInternal::GetCurrentModuleVersionCompanyName_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return std::vector<unsigned char>::~vector<unsigned char>(a2 + 48);
}

```

## disassembly

```asm
0x180012457  lea     rcx, [rdx+30h]
0x18001245e  jmp     ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
```
