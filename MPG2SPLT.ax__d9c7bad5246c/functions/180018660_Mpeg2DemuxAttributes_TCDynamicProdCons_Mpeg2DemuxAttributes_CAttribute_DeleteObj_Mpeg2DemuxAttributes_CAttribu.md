# Mpeg2DemuxAttributes::TCDynamicProdCons<Mpeg2DemuxAttributes::CAttribute>::DeleteObj_(Mpeg2DemuxAttributes::CAttribute *)

- ea: `0x180018660`
- end: `0x180018691`
- name: `?DeleteObj_@?$TCDynamicProdCons@VCAttribute@Mpeg2DemuxAttributes@@@Mpeg2DemuxAttributes@@MEAAXPEAVCAttribute@2@@Z`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001048`
- `0x180018660`

## pseudocode

```c
void __fastcall Mpeg2DemuxAttributes::TCDynamicProdCons<Mpeg2DemuxAttributes::CAttribute>::DeleteObj_(
        __int64 a1,
        void **a2)
{
  if ( a2 )
  {
    operator delete(a2[2]);
    a2[2] = 0;
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x180018660  test    rdx, rdx
0x180018663  jz      short locret_180018690
0x180018665  push    rbx
0x180018666  sub     rsp, 20h
0x18001866a  mov     rcx, [rdx+10h]; void *
0x18001866e  mov     rbx, rdx
0x180018671  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018676  mov     edx, 30h ; '0'; unsigned __int64
0x18001867b  mov     qword ptr [rbx+10h], 0
0x180018683  mov     rcx, rbx; void *
0x180018686  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001868b  add     rsp, 20h
0x18001868f  pop     rbx
0x180018690  retn
```
