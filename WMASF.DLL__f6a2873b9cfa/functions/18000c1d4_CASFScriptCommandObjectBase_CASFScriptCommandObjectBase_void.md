# CASFScriptCommandObjectBase::~CASFScriptCommandObjectBase(void)

- ea: `0x18000c1d4`
- end: `0x18000c1ff`
- name: `??1CASFScriptCommandObjectBase@@UEAA@XZ`
- size: `43`
- prototype: `void __fastcall(CASFScriptCommandObjectBase *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c208`
- `0x18000c2bc`
- `0x18000cc88`

## callees

- `0x18000431c`
- `0x18000c150`
- `0x18000c1b0`

## pseudocode

```c
void __fastcall CASFScriptCommandObjectBase::~CASFScriptCommandObjectBase(CASFScriptCommandObjectBase *this)
{
  CTSparseBlock<unsigned long,CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20,0>::~CTSparseBlock<unsigned long,CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20,0>((char *)this + 304);
  CTSparseBlock<unsigned long,CASFStreamSelector::STREAM_GROUP *,20,0>::~CTSparseBlock<unsigned long,CASFStreamSelector::STREAM_GROUP *,20,0>((char *)this + 80);
  CASFUnknown<IASFPrioritizationObject>::~CASFUnknown<IASFPrioritizationObject>(this);
}

```

## disassembly

```asm
0x18000c1d4  push    rbx
0x18000c1d6  sub     rsp, 20h
0x18000c1da  mov     rbx, rcx
0x18000c1dd  add     rcx, 130h
0x18000c1e4  call    ??1?$CTSparseBlock@KUCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@$0A@@@QEAA@XZ; CTSparseBlock<ulong,CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20,0>::~CTSparseBlock<ulong,CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20,0>(void)
0x18000c1e9  lea     rcx, [rbx+50h]
0x18000c1ed  call    ??1?$CTSparseBlock@KPEAUSTREAM_GROUP@CASFStreamSelector@@$0BE@$0A@@@QEAA@XZ; CTSparseBlock<ulong,CASFStreamSelector::STREAM_GROUP *,20,0>::~CTSparseBlock<ulong,CASFStreamSelector::STREAM_GROUP *,20,0>(void)
0x18000c1f2  mov     rcx, rbx
0x18000c1f5  add     rsp, 20h
0x18000c1f9  pop     rbx
0x18000c1fa  jmp     ??1?$CASFUnknown@UIASFPrioritizationObject@@@@UEAA@XZ; CASFUnknown<IASFPrioritizationObject>::~CASFUnknown<IASFPrioritizationObject>(void)
```
