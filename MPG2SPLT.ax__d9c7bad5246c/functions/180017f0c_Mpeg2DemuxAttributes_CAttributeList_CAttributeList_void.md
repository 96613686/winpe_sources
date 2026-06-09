# Mpeg2DemuxAttributes::CAttributeList::~CAttributeList(void)

- ea: `0x180017f0c`
- end: `0x180017f3e`
- name: `??1CAttributeList@Mpeg2DemuxAttributes@@UEAA@XZ`
- size: `50`
- prototype: `void __fastcall(Mpeg2DemuxAttributes::CAttributeList *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001800c`
- `0x1800180d0`
- `0x18002851c`
- `0x18002d4e0`
- `0x18002d710`

## callees

- `0x180017db4`
- `0x180019a60`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180017f2b`
- `KERNEL32!DeleteCriticalSection` at `0x180017f2b`

## pseudocode

```c
void __fastcall Mpeg2DemuxAttributes::CAttributeList::~CAttributeList(Mpeg2DemuxAttributes::CAttributeList *this)
{
  *(_QWORD *)this = &Mpeg2DemuxAttributes::CAttributeList::`vftable';
  Mpeg2DemuxAttributes::CAttributeList::Reset(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  Mpeg2DemuxAttributes::TCDynamicProdCons<Mpeg2DemuxAttributes::CAttribute>::~TCDynamicProdCons<Mpeg2DemuxAttributes::CAttribute>(this);
}

```

## disassembly

```asm
0x180017f0c  push    rbx
0x180017f0e  sub     rsp, 20h
0x180017f12  lea     rax, ??_7CAttributeList@Mpeg2DemuxAttributes@@6B@; const Mpeg2DemuxAttributes::CAttributeList::`vftable'
0x180017f19  mov     rbx, rcx
0x180017f1c  mov     [rcx], rax
0x180017f1f  call    ?Reset@CAttributeList@Mpeg2DemuxAttributes@@QEAAXXZ; Mpeg2DemuxAttributes::CAttributeList::Reset(void)
0x180017f24  lea     rcx, [rbx+0A8h]; lpCriticalSection
0x180017f2b  call    cs:__imp_DeleteCriticalSection
0x180017f31  mov     rcx, rbx
0x180017f34  add     rsp, 20h
0x180017f38  pop     rbx
0x180017f39  jmp     ??1?$TCDynamicProdCons@VCAttribute@Mpeg2DemuxAttributes@@@Mpeg2DemuxAttributes@@UEAA@XZ; Mpeg2DemuxAttributes::TCDynamicProdCons<Mpeg2DemuxAttributes::CAttribute>::~TCDynamicProdCons<Mpeg2DemuxAttributes::CAttribute>(void)
```
