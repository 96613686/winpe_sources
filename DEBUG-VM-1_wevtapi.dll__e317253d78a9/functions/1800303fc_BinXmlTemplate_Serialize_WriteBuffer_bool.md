# BinXmlTemplate::Serialize(WriteBuffer &,bool)

- ea: `0x1800303fc`
- end: `0x18003051c`
- name: `?Serialize@BinXmlTemplate@@QEBAXAEAVWriteBuffer@@_N@Z`
- size: `288`
- prototype: `void(BinXmlTemplate *__hidden this, struct WriteBuffer *, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002f84c`
- `0x1800359f0`

## callees

- `0x180003780`
- `0x180003dc0`
- `0x180008b20`
- `0x18000a4b4`
- `0x18000b95c`
- `0x18002404c`
- `0x18002e234`
- `0x1800303fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall BinXmlTemplate::Serialize(BinXmlTemplate *this, struct WriteBuffer *a2, char a3)
{
  __int64 v5; // rbx
  __int64 v6; // r8
  BinXmlTemplate *v7; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v8; // [rsp+48h] [rbp-B8h]
  __int128 v9; // [rsp+58h] [rbp-A8h]
  WriteBuffer *v10[6]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v11[64]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v12[224]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v13; // [rsp+1E0h] [rbp+E0h] BYREF

  LOBYTE(v13) = a3;
  WriteBuffer::Write(a2, (char *)this + 16, 0x10u);
  if ( *((_QWORD *)this + 4) == *((_QWORD *)this + 5) )
  {
    v13 = *((_DWORD *)this + 2);
    WriteBuffer::Write(a2, &v13, 4u);
    WriteBuffer::Write(a2, *(const void **)this, v13);
  }
  else
  {
    v5 = *((unsigned int *)a2 + 4);
    WriteBuffer::SetCurrentIndex(a2, v5 + 4);
    v8 = 0;
    v9 = 0;
    v7 = this;
    BinXmlReader::BinXmlReader(
      (BinXmlReader *)v12,
      (struct BinXmlReaderData *)&v7,
      v6,
      0,
      *((struct BinXmlStringTable **)this + 4),
      0);
    BinXmlWriter::BinXmlWriter((BinXmlWriter *)v10, 1, a2, *((struct BinXmlStringTable **)this + 5), 0, 0, 0);
    BinXmlReader::CopyInto((BinXmlReader *)v12, v10);
    *(_DWORD *)(v5 + *((_QWORD *)a2 + 1)) = *((_DWORD *)a2 + 4) - v5 - 4;
    utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(v11);
    BinXmlReader::~BinXmlReader((BinXmlReader *)v12);
  }
}

```

## disassembly

```asm
0x1800303fc  mov     byte ptr [rsp-8+arg_10], r8b
0x180030401  push    rbp
0x180030402  push    rbx
0x180030403  push    rsi
0x180030404  push    rdi
0x180030405  lea     rbp, [rsp-0A8h]
0x18003040d  sub     rsp, 1A8h
0x180030414  mov     rsi, rdx
0x180030417  mov     rdi, rcx
0x18003041a  lea     rdx, [rcx+10h]; void *
0x18003041e  mov     r8d, 10h; unsigned int
0x180030424  mov     rcx, rsi; this
0x180030427  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x18003042c  mov     rax, [rdi+28h]
0x180030430  mov     rcx, rsi; this
0x180030433  cmp     [rdi+20h], rax
0x180030437  jz      loc_1800304E3
0x18003043d  mov     ebx, [rsi+10h]
0x180030440  lea     edx, [rbx+4]; unsigned int
0x180030443  call    ?SetCurrentIndex@WriteBuffer@@QEAAXK@Z; WriteBuffer::SetCurrentIndex(ulong)
0x180030448  xorps   xmm0, xmm0
0x18003044b  movdqu  [rsp+1C0h+var_178], xmm0
0x180030451  xorps   xmm1, xmm1
0x180030454  movdqu  [rsp+1C0h+var_168], xmm1
0x18003045a  mov     [rsp+1C0h+var_180], rdi
0x18003045f  mov     [rsp+1C0h+var_198], 0; struct BinXmlTemplateTable *
0x180030468  mov     rax, [rdi+20h]
0x18003046c  mov     [rsp+1C0h+var_1A0], rax; struct BinXmlStringTable *
0x180030471  xor     r9d, r9d; struct AbstractPublishedEventRecord *
0x180030474  lea     rdx, [rsp+1C0h+var_180]; struct BinXmlReaderData *
0x180030479  lea     rcx, [rbp+0C0h+var_E0]; this
0x18003047d  call    ??0BinXmlReader@@QEAA@PEAUBinXmlReaderData@@KPEAVAbstractPublishedEventRecord@@PEAVBinXmlStringTable@@PEAVBinXmlTemplateTable@@@Z; BinXmlReader::BinXmlReader(BinXmlReaderData *,ulong,AbstractPublishedEventRecord *,BinXmlStringTable *,BinXmlTemplateTable *)
0x180030482  nop
0x180030483  mov     [rsp+1C0h+var_190], 0; unsigned int
0x18003048b  mov     [rsp+1C0h+var_198], 0; unsigned int *
0x180030494  mov     [rsp+1C0h+var_1A0], 0; struct BinXmlTemplateTable *
0x18003049d  mov     r9, [rdi+28h]; struct BinXmlStringTable *
0x1800304a1  mov     r8, rsi; struct WriteBuffer *
0x1800304a4  mov     dl, 1; bool
0x1800304a6  lea     rcx, [rsp+1C0h+var_150]; this
0x1800304ab  call    ??0BinXmlWriter@@QEAA@_NAEAVWriteBuffer@@PEAVBinXmlStringTable@@PEAVBinXmlTemplateTable@@PEBKK@Z; BinXmlWriter::BinXmlWriter(bool,WriteBuffer &,BinXmlStringTable *,BinXmlTemplateTable *,ulong const *,ulong)
0x1800304b0  nop
0x1800304b1  lea     rdx, [rsp+1C0h+var_150]; struct BinXmlWriter *
0x1800304b6  lea     rcx, [rbp+0C0h+var_E0]; this
0x1800304ba  call    ?CopyInto@BinXmlReader@@QEAAXAEAVBinXmlWriter@@@Z; BinXmlReader::CopyInto(BinXmlWriter &)
0x1800304bf  mov     ecx, [rsi+10h]
0x1800304c2  sub     ecx, ebx
0x1800304c4  sub     ecx, 4
0x1800304c7  mov     rax, [rsi+8]
0x1800304cb  mov     [rbx+rax], ecx
0x1800304ce  lea     rcx, [rbp+0C0h+var_120]
0x1800304d2  call    ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
0x1800304d7  nop
0x1800304d8  lea     rcx, [rbp+0C0h+var_E0]; this
0x1800304dc  call    ??1BinXmlReader@@QEAA@XZ; BinXmlReader::~BinXmlReader(void)
0x1800304e1  jmp     short loc_180030510
0x1800304e3  mov     eax, [rdi+8]
0x1800304e6  mov     [rbp+0C0h+arg_10], eax
0x1800304ec  mov     r8d, 4; unsigned int
0x1800304f2  lea     rdx, [rbp+0C0h+arg_10]; void *
0x1800304f9  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x1800304fe  mov     r8d, [rbp+0C0h+arg_10]; unsigned int
0x180030505  mov     rdx, [rdi]; void *
0x180030508  mov     rcx, rsi; this
0x18003050b  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x180030510  add     rsp, 1A8h
0x180030517  pop     rdi
0x180030518  pop     rsi
0x180030519  pop     rbx
0x18003051a  pop     rbp
0x18003051b  retn
```
