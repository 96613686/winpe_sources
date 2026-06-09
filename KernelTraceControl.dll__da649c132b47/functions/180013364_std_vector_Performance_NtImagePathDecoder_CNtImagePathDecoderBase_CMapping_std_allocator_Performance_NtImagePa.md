# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(void)

- ea: `0x180013364`
- end: `0x18001339d`
- name: `??1?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ`
- size: `57`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180027ea0`
- `0x180028cbf`
- `0x180028d52`

## callees

- `0x1800132ec`
- `0x180013364`
- `0x1800268f4`

## pseudocode

```c
void __fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>(
        __int64 a1)
{
  _QWORD *v1; // rdx

  v1 = *(_QWORD **)(a1 + 8);
  if ( v1 )
  {
    std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Destroy(
      a1,
      v1,
      *(_QWORD **)(a1 + 16));
    operator delete(*(void **)(a1 + 8));
  }
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
}

```

## disassembly

```asm
0x180013364  push    rbx
0x180013366  sub     rsp, 20h
0x18001336a  mov     rdx, [rcx+8]
0x18001336e  mov     rbx, rcx
0x180013371  test    rdx, rdx
0x180013374  jz      short loc_180013388
0x180013376  mov     r8, [rcx+10h]
0x18001337a  call    ?_Destroy@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@IEAAXPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@0@Z; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Destroy(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *)
0x18001337f  mov     rcx, [rbx+8]; Block
0x180013383  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013388  and     qword ptr [rbx+8], 0
0x18001338d  and     qword ptr [rbx+10h], 0
0x180013392  and     qword ptr [rbx+18h], 0
0x180013397  add     rsp, 20h
0x18001339b  pop     rbx
0x18001339c  retn
```
