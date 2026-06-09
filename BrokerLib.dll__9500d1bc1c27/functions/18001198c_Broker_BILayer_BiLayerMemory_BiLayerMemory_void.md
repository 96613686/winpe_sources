# Broker::BILayer::BiLayerMemory::~BiLayerMemory(void)

- ea: `0x18001198c`
- end: `0x1800119a3`
- name: `??1BiLayerMemory@BILayer@Broker@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(Broker::BILayer::BiLayerMemory *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180014a7c`
- `0x18001c16d`
- `0x18001c1cb`
- `0x18001ca21`
- `0x18001ca74`

## callees

- `0x18001198c`

## import_xrefs

- `api-ms-win-core-bicltapi-l1-1-6!BiFreeMemory` at `0x180011998`
- `api-ms-win-core-bicltapi-l1-1-6!BiFreeMemory` at `0x180011998`

## pseudocode

```c
void __fastcall Broker::BILayer::BiLayerMemory::~BiLayerMemory(Broker::BILayer::BiLayerMemory *this)
{
  if ( *(_QWORD *)this )
    BiFreeMemory();
}

```

## disassembly

```asm
0x18001198c  sub     rsp, 28h
0x180011990  mov     rcx, [rcx]
0x180011993  test    rcx, rcx
0x180011996  jz      short loc_18001199E
0x180011998  call    cs:__imp_BiFreeMemory
0x18001199e  add     rsp, 28h
0x1800119a2  retn
```
