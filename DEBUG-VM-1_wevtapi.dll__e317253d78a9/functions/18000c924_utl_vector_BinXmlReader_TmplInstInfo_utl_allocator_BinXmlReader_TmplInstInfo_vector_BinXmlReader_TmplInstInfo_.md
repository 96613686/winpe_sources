# utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::~vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(void)

- ea: `0x18000c924`
- end: `0x18000c929`
- name: `??1?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800390c8`
- `0x1800390e0`
- `0x180039100`
- `0x180039490`
- `0x1800394b0`
- `0x180039646`
- `0x180039eba`
- `0x18003a0d3`
- `0x18003a783`
- `0x18003ad8c`
- `0x18003aef5`

## callees

- `0x18000a4b4`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::~vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(
        __int64 a1)
{
  return utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(a1);
}

```

## disassembly

```asm
0x18000c924  jmp     ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
```
