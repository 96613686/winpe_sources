# Mpeg2DemuxAttributes::TCDynamicProdCons<Mpeg2DemuxAttributes::CDemuxIMediaSample>::DeleteObj_(Mpeg2DemuxAttributes::CDemuxIMediaSample *)

- ea: `0x180022b40`
- end: `0x180022b68`
- name: `?DeleteObj_@?$TCDynamicProdCons@VCDemuxIMediaSample@Mpeg2DemuxAttributes@@@Mpeg2DemuxAttributes@@MEAAXPEAVCDemuxIMediaSample@2@@Z`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180022b40`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall Mpeg2DemuxAttributes::TCDynamicProdCons<Mpeg2DemuxAttributes::CDemuxIMediaSample>::DeleteObj_(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax

  if ( a2 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a2 + 176LL))(a2, 1);
  return result;
}

```

## disassembly

```asm
0x180022b40  sub     rsp, 28h
0x180022b44  mov     r8, rdx
0x180022b47  test    rdx, rdx
0x180022b4a  jz      short loc_180022B63
0x180022b4c  mov     rax, [rdx]
0x180022b4f  mov     rcx, r8
0x180022b52  mov     edx, 1
0x180022b57  mov     rax, [rax+0B0h]
0x180022b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b63  add     rsp, 28h
0x180022b67  retn
```
