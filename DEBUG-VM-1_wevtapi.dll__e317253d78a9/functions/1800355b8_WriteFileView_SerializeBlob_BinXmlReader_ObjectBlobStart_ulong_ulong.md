# WriteFileView::SerializeBlob(BinXmlReader &,ObjectBlobStart *,ulong,ulong &)

- ea: `0x1800355b8`
- end: `0x18003576e`
- name: `?SerializeBlob@WriteFileView@@QEAAKAEAVBinXmlReader@@PEAUObjectBlobStart@@KAEAK@Z`
- size: `438`
- prototype: `unsigned int __fastcall(WriteFileView *__hidden this, struct BinXmlReader *, struct ObjectBlobStart *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18003409c`

## callees

- `0x180003a68`
- `0x180008b20`
- `0x18000a4b4`
- `0x1800196a0`
- `0x18002404c`
- `0x18002e234`
- `0x180035470`
- `0x1800355b8`
- `0x180035780`
- `0x1800358e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WriteFileView::SerializeBlob(
        WriteFileView *this,
        struct BinXmlReader *a2,
        struct ObjectBlobStart *a3,
        unsigned int a4,
        unsigned int *a5)
{
  unsigned int v9; // eax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rax
  unsigned int v12; // r15d
  __int64 result; // rax
  unsigned int v14; // ecx
  _BYTE v15[16]; // [rsp+40h] [rbp-A8h] BYREF
  unsigned int v16; // [rsp+50h] [rbp-98h]
  EvtException *v17; // [rsp+58h] [rbp-90h] BYREF
  WriteBuffer *v18[6]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v19[64]; // [rsp+90h] [rbp-58h] BYREF
  int v20; // [rsp+108h] [rbp+20h] BYREF

  v9 = *((_DWORD *)this + 8) - *((_DWORD *)this + 6) - 128;
  if ( a4 >= v9 )
    return 111;
  v10 = v9 - a4;
  v11 = *((unsigned int *)a2 + 46) + 4LL;
  if ( v11 > v10 )
    return 111;
  try
  {
    WriteFileView::SetCurrentIndex(this, a4);
    v12 = *((_DWORD *)this + 14) - *((_DWORD *)this + 6);
    WriteFileView::Advance(this, 0x18u);
    WriteBuffer::WriteBuffer((WriteBuffer *)v15, this);
    WriteBuffer::SetCurrentIndex((WriteBuffer *)v15, v16 + *((_DWORD *)this + 14) - *((_DWORD *)this + 6));
    BinXmlWriter::BinXmlWriter(
      (BinXmlWriter *)v18,
      0,
      (struct WriteBuffer *)v15,
      (WriteFileView *)((char *)this + 64),
      (WriteFileView *)((char *)this + 344),
      0,
      0);
    BinXmlReader::Reset(a2);
    BinXmlReader::CopyInto(a2, v18);
    WriteFileView::SetCurrentIndex(this, v16);
    if ( ((*((_BYTE *)this + 56) - *((_BYTE *)this + 24) - 4) & 7) != 0 )
      WriteFileView::Advance(this, 8 - ((*((_BYTE *)this + 56) - *((_BYTE *)this + 24) - 4) & 7));
    v20 = *((_DWORD *)this + 14) - *((_DWORD *)this + 6) - a4 + 4;
    WriteFileView::Write(this, &v20, 4u);
    if ( *((_QWORD *)this + 7) < *((_QWORD *)this + 4) )
    {
      WriteFileView::SetCurrentIndex(this, v12);
      v14 = v20;
      *((_DWORD *)a3 + 1) = v20;
      *a5 = v14;
      WriteFileView::Write(this, a3, 0x18u);
      utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(v19);
      result = 0;
    }
    else
    {
      utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(v19);
      result = 111;
    }
  }
  catch ( EvtException *v17 )
  {
    if ( *((_DWORD *)v17 + 6) == 1359 )
      return 111;
    return (unsigned int)*((_DWORD *)v17 + 6);
  }
  return result;
}

```

## disassembly

```asm
0x1800355b8  mov     [rsp+arg_0], rbx
0x1800355bd  mov     [rsp+arg_8], rsi
0x1800355c2  push    rdi
0x1800355c3  push    r14
0x1800355c5  push    r15
0x1800355c7  sub     rsp, 0D0h
0x1800355ce  mov     edi, r9d
0x1800355d1  mov     r14, r8
0x1800355d4  mov     rsi, rdx
0x1800355d7  mov     rbx, rcx
0x1800355da  mov     eax, [rcx+20h]
0x1800355dd  sub     eax, [rcx+18h]
0x1800355e0  add     eax, 0FFFFFF80h
0x1800355e3  cmp     r9d, eax
0x1800355e6  jnb     loc_18003574F
0x1800355ec  sub     eax, r9d
0x1800355ef  mov     ecx, eax
0x1800355f1  mov     eax, [rdx+0B8h]
0x1800355f7  add     rax, 4
0x1800355fb  cmp     rax, rcx
0x1800355fe  ja      loc_18003574F
0x180035604  mov     edx, r9d; unsigned int
0x180035607  mov     rcx, rbx; this
0x18003560a  call    ?SetCurrentIndex@WriteFileView@@UEAAXK@Z; WriteFileView::SetCurrentIndex(ulong)
0x18003560f  mov     r15d, [rbx+38h]
0x180035613  sub     r15d, [rbx+18h]
0x180035617  mov     edx, 18h; unsigned int
0x18003561c  mov     rcx, rbx; this
0x18003561f  call    ?Advance@WriteFileView@@UEAAXK@Z; WriteFileView::Advance(ulong)
0x180035624  mov     rdx, rbx; struct BufferStream *
0x180035627  lea     rcx, [rsp+0E8h+var_A8]; this
0x18003562c  call    ??0WriteBuffer@@QEAA@AEAVBufferStream@@@Z; WriteBuffer::WriteBuffer(BufferStream &)
0x180035631  mov     edx, [rbx+38h]
0x180035634  sub     edx, [rbx+18h]
0x180035637  add     edx, [rsp+0E8h+var_98]; unsigned int
0x18003563b  lea     rcx, [rsp+0E8h+var_A8]; this
0x180035640  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x180035645  lea     rax, [rbx+158h]
0x18003564c  lea     r9, [rbx+40h]; struct BinXmlStringTable *
0x180035650  mov     [rsp+0E8h+var_B8], 0; unsigned int
0x180035658  mov     [rsp+0E8h+var_C0], 0; unsigned int *
0x180035661  mov     [rsp+0E8h+var_C8], rax; struct BinXmlTemplateTable *
0x180035666  lea     r8, [rsp+0E8h+var_A8]; struct WriteBuffer *
0x18003566b  xor     edx, edx; bool
0x18003566d  lea     rcx, [rsp+0E8h+var_88]; this
0x180035672  call    ??0BinXmlWriter@@QEAA@_NAEAVWriteBuffer@@PEAVBinXmlStringTable@@PEAVBinXmlTemplateTable@@PEBKK@Z; BinXmlWriter::BinXmlWriter(bool,WriteBuffer &,BinXmlStringTable *,BinXmlTemplateTable *,ulong const *,ulong)
0x180035677  nop
0x180035678  mov     rcx, rsi; this
0x18003567b  call    ?Reset@BinXmlReader@@QEAAXXZ; BinXmlReader::Reset(void)
0x180035680  lea     rdx, [rsp+0E8h+var_88]; struct BinXmlWriter *
0x180035685  mov     rcx, rsi; this
0x180035688  call    ?CopyInto@BinXmlReader@@QEAAXAEAVBinXmlWriter@@@Z; BinXmlReader::CopyInto(BinXmlWriter &)
0x18003568d  mov     edx, [rsp+0E8h+var_98]; unsigned int
0x180035691  mov     rcx, rbx; this
0x180035694  call    ?SetCurrentIndex@WriteFileView@@UEAAXK@Z; WriteFileView::SetCurrentIndex(ulong)
0x180035699  mov     eax, [rbx+38h]
0x18003569c  sub     eax, [rbx+18h]
0x18003569f  sub     eax, 4
0x1800356a2  and     eax, 7
0x1800356a5  jz      short loc_1800356B6
0x1800356a7  mov     edx, 8
0x1800356ac  sub     edx, eax; unsigned int
0x1800356ae  mov     rcx, rbx; this
0x1800356b1  call    ?Advance@WriteFileView@@UEAAXK@Z; WriteFileView::Advance(ulong)
0x1800356b6  mov     eax, [rbx+38h]
0x1800356b9  sub     eax, [rbx+18h]
0x1800356bc  sub     eax, edi
0x1800356be  add     eax, 4
0x1800356c1  mov     [rsp+0E8h+arg_18], eax
0x1800356c8  mov     r8d, 4; unsigned int
0x1800356ce  lea     rdx, [rsp+0E8h+arg_18]; void *
0x1800356d6  mov     rcx, rbx; this
0x1800356d9  call    ?Write@WriteFileView@@UEAAXQEBXK@Z; WriteFileView::Write(void const * const,ulong)
0x1800356de  mov     rax, [rbx+20h]
0x1800356e2  cmp     [rbx+38h], rax
0x1800356e6  jb      short loc_1800356FC
0x1800356e8  lea     rcx, [rsp+0E8h+var_58]
0x1800356f0  call    ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
0x1800356f5  mov     eax, 6Fh ; 'o'
0x1800356fa  jmp     short loc_180035754
0x1800356fc  mov     edx, r15d; unsigned int
0x1800356ff  mov     rcx, rbx; this
0x180035702  call    ?SetCurrentIndex@WriteFileView@@UEAAXK@Z; WriteFileView::SetCurrentIndex(ulong)
0x180035707  mov     ecx, [rsp+0E8h+arg_18]
0x18003570e  mov     [r14+4], ecx
0x180035712  mov     rax, [rsp+0E8h+arg_20]
0x18003571a  mov     [rax], ecx
0x18003571c  mov     r8d, 18h; unsigned int
0x180035722  mov     rdx, r14; void *
0x180035725  mov     rcx, rbx; this
0x180035728  call    ?Write@WriteFileView@@UEAAXQEBXK@Z; WriteFileView::Write(void const * const,ulong)
0x18003572d  nop
0x18003572e  lea     rcx, [rsp+0E8h+var_58]
0x180035736  call    ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
0x18003573b  xor     eax, eax
0x18003573d  jmp     short loc_180035754
0x18003573f  mov     eax, 6Fh ; 'o'
0x180035744  jmp     short loc_18003574D
0x180035746  mov     eax, [rsp+0E8h+arg_18]
0x18003574d  jmp     short loc_180035754
0x18003574f  mov     eax, 6Fh ; 'o'
0x180035754  lea     r11, [rsp+0E8h+var_18]
0x18003575c  mov     rbx, [r11+20h]
0x180035760  mov     rsi, [r11+28h]
0x180035764  mov     rsp, r11
0x180035767  pop     r15
0x180035769  pop     r14
0x18003576b  pop     rdi
0x18003576c  retn
```
