# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x1800325b4`
- end: `0x180032798`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *indexData, unsigned __int64 indexSize, void *valueData, unsigned __int64 valueSize, unsigned int addend)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800324c0`

## callees

- `0x1800304a8`
- `0x180030884`
- `0x180031228`
- `0x180032004`
- `0x1800325b4`
- `0x180032fdc`
- `0x180033674`
- `0x180033900`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800326f6`
- `msvcrt!memmove_s` at `0x1800326f6`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsageInternal(
        wil::details_abi::RawUsageIndex *this,
        void *indexData,
        size_t indexSize,
        void *valueData,
        unsigned __int64 valueSize,
        unsigned int addend)
{
  unsigned __int8 *v6; // rdi
  unsigned __int8 *v11; // rdi
  unsigned __int8 *bufferEnd; // r8
  char v13; // r14
  int v14; // eax
  unsigned __int8 *v15; // rax
  wil::details_abi::CountSize c_valueCountSize; // cl
  unsigned __int64 Size; // rax
  unsigned __int8 *bufferAllocEnd; // rdx
  unsigned __int8 *v20; // r9
  __int64 v21; // r8
  __int64 v22; // rsi
  wil::details_abi::UsageIndexProperty index; // [rsp+30h] [rbp-48h] BYREF
  wil::details_abi::UsageIndexProperty value; // [rsp+50h] [rbp-28h] BYREF
  unsigned __int8 *buffer; // [rsp+C0h] [rbp+48h] BYREF

  v6 = this->m_buffer.buffer;
  if ( v6 )
  {
    v11 = v6 + 10;
    bufferEnd = this->m_buffer.bufferEnd;
    index.c_size = this->c_indexSize;
    index.c_countSize = this->c_indexCountSize;
    index.size = 0;
    v13 = 0;
    buffer = v11;
    index.count = 0;
    *(_OWORD *)&index.countBuffer = 0;
    while ( 1 )
    {
      if ( !wil::details_abi::UsageIndexProperty::Read(&index, &buffer, bufferEnd) )
      {
        v11 = buffer;
        this->m_buffer.bufferEnd = buffer;
        goto LABEL_8;
      }
      v14 = wil::details_abi::UsageIndexProperty::Compare(&index, indexData, indexSize);
      if ( v14 < 0 )
      {
        buffer = v11;
        goto LABEL_8;
      }
      if ( !v14 )
        break;
      v15 = wil::details_abi::RawUsageIndex::SkipValues(this, &index, buffer);
      bufferEnd = this->m_buffer.bufferEnd;
      v11 = v15;
      buffer = v15;
    }
    buffer = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
               this,
               &index,
               buffer,
               valueData,
               valueSize,
               addend);
    v11 = buffer;
    if ( !buffer )
      return 1;
    v13 = 1;
LABEL_8:
    if ( !v13 )
    {
      index.count = 1;
      index.size = indexSize;
      index.countBuffer = 0;
      index.value = indexData;
      wil::details_abi::UsageIndexProperty::GetSize(&index);
    }
    value.c_size = this->c_valueSize;
    c_valueCountSize = this->c_valueCountSize;
    value.count = addend;
    value.c_countSize = c_valueCountSize;
    value.size = valueSize;
    value.countBuffer = 0;
    value.value = valueData;
    Size = wil::details_abi::UsageIndexProperty::GetSize(&value);
    bufferAllocEnd = this->m_buffer.bufferAllocEnd;
    v20 = this->m_buffer.bufferEnd;
    v22 = Size + v21;
    if ( ((bufferAllocEnd - v20) & (unsigned __int64)-(__int64)(v20 < bufferAllocEnd)) >= Size + v21 )
    {
      memmove_s(&v11[v22], &bufferAllocEnd[-v22] - v11, v11, v20 - v11);
      this->m_buffer.bufferEnd += v22;
      if ( v13 )
      {
        if ( index.c_countSize )
          wil::details_abi::UsageIndexProperty::UpdateCount(&index, index.count + 1);
      }
      else
      {
        wil::details_abi::UsageIndexProperty::Write(&index, &buffer, this->m_buffer.bufferEnd);
      }
      wil::details_abi::UsageIndexProperty::Write(&value, &buffer, this->m_buffer.bufferEnd);
      this->m_isDirty = 1;
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800325b4  push    rbp
0x1800325b6  push    rbx
0x1800325b7  push    rsi
0x1800325b8  push    rdi
0x1800325b9  push    r12
0x1800325bb  push    r13
0x1800325bd  push    r14
0x1800325bf  push    r15
0x1800325c1  mov     rbp, rsp
0x1800325c4  sub     rsp, 78h
0x1800325c8  mov     rdi, [this+18h]
0x1800325cc  mov     r13, valueData
0x1800325cf  mov     r15, indexSize
0x1800325d2  mov     r12, indexData
0x1800325d5  mov     rbx, this
0x1800325d8  test    rdi, rdi
0x1800325db  jz      loc_180032785
0x1800325e1  movzx   eax, word ptr [this+2]
0x1800325e5  add     rdi, 0Ah
0x1800325e9  mov     indexSize, [this+20h]
0x1800325ed  xorps   xmm0, xmm0
0x1800325f0  mov     [rbp+index.c_size], ax
0x1800325f4  mov     al, [this+4]
0x1800325f7  mov     [rbp+index.c_countSize], al
0x1800325fa  xor     eax, eax
0x1800325fc  mov     [rbp+index.size], ax
0x180032600  xor     r14b, r14b
0x180032603  mov     [rbp+buffer], rdi
0x180032607  mov     [rbp+index.count], 0
0x18003260e  movdqu  xmmword ptr [rbp+index.countBuffer], xmm0
0x180032613  jmp     short loc_18003264D
0x180032615  mov     indexSize, r15; indexSize
0x180032618  lea     this, [rbp+index]; this
0x18003261c  mov     indexData, r12; indexData
0x18003261f  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180032624  test    eax, eax
0x180032626  js      loc_180032748
0x18003262c  mov     indexSize, [rbp+buffer]; buffer
0x180032630  lea     indexData, [rbp+index]; index
0x180032634  jz      loc_180032718
0x18003263a  mov     this, rbx; this
0x18003263d  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180032642  mov     indexSize, [rbx+20h]; bufferEnd
0x180032646  mov     rdi, rax
0x180032649  mov     [rbp+buffer], rax
0x18003264d  lea     indexData, [rbp+buffer]; bufferParam
0x180032651  lea     this, [rbp+index]; this
0x180032655  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18003265a  mov     sil, al
0x18003265d  test    al, al
0x18003265f  jnz     short loc_180032615
0x180032661  mov     rdi, [rbp+buffer]
0x180032665  mov     [rbx+20h], rdi
0x180032669  xor     r8d, r8d
0x18003266c  test    r14b, r14b
0x18003266f  jnz     short loc_180032691
0x180032671  lea     this, [rbp+index]; this
0x180032675  mov     [rbp+index.count], 1
0x18003267c  mov     [rbp+index.size], r15w
0x180032681  mov     [rbp+index.countBuffer], indexSize
0x180032685  mov     [rbp+index.value], r12
0x180032689  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18003268e  mov     indexSize, rax
0x180032691  movzx   ecx, word ptr [rbx+6]
0x180032695  mov     eax, [rbp+arg_28]
0x180032698  mov     [rbp+value.c_size], cx
0x18003269c  mov     cl, [rbx+8]
0x18003269f  mov     [rbp+value.count], eax
0x1800326a2  mov     rax, [rbp+arg_20]
0x1800326a6  mov     [rbp+value.c_countSize], cl
0x1800326a9  lea     this, [rbp+value]; this
0x1800326ad  mov     [rbp+value.size], ax
0x1800326b1  mov     [rbp+value.countBuffer], 0
0x1800326b9  mov     [rbp+value.value], r13
0x1800326bd  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x1800326c2  mov     indexData, [rbx+28h]
0x1800326c6  mov     valueData, [rbx+20h]
0x1800326ca  mov     this, indexData
0x1800326cd  sub     this, valueData
0x1800326d0  lea     rsi, [rax+indexSize]
0x1800326d4  cmp     valueData, indexData
0x1800326d7  sbb     rax, rax
0x1800326da  and     rax, this
0x1800326dd  cmp     rax, rsi
0x1800326e0  jb      loc_180032785
0x1800326e6  sub     indexData, rsi
0x1800326e9  lea     this, [rsi+rdi]; Destination
0x1800326ed  sub     indexData, rdi; DestinationSize
0x1800326f0  sub     valueData, rdi; SourceSize
0x1800326f3  mov     indexSize, rdi; Source
0x1800326f6  call    cs:__imp_memmove_s
0x1800326fc  add     [rbx+20h], rsi
0x180032700  test    r14b, r14b
0x180032703  jnz     short loc_18003275A
0x180032705  mov     indexSize, [rbx+20h]; bufferEnd
0x180032709  lea     indexData, [rbp+buffer]; bufferParam
0x18003270d  lea     this, [rbp+index]; this
0x180032711  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180032716  jmp     short loc_18003276E
0x180032718  mov     ecx, [rbp+arg_28]
0x18003271b  mov     valueData, r13; valueData
0x18003271e  mov     [rsp+78h+var_50], ecx; addend
0x180032722  mov     this, [rbp+arg_20]
0x180032726  mov     [rsp+78h+var_58], this; valueSize
0x18003272b  mov     this, rbx; this
0x18003272e  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180032733  mov     [rbp+buffer], rax
0x180032737  mov     rdi, rax
0x18003273a  test    rax, rax
0x18003273d  jnz     short loc_180032743
0x18003273f  mov     al, 1
0x180032741  jmp     short loc_180032787
0x180032743  mov     r14b, 1
0x180032746  jmp     short loc_18003274C
0x180032748  mov     [rbp+buffer], rdi
0x18003274c  test    sil, sil
0x18003274f  jnz     loc_180032669
0x180032755  jmp     loc_180032665
0x18003275a  cmp     [rbp+index.c_countSize], 0
0x18003275e  jz      short loc_18003276E
0x180032760  mov     edx, [rbp+index.count]
0x180032763  lea     this, [rbp+index]; this
0x180032767  inc     edx; newCount
0x180032769  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18003276e  mov     indexSize, [rbx+20h]; bufferEnd
0x180032772  lea     indexData, [rbp+buffer]; bufferParam
0x180032776  lea     this, [rbp+value]; this
0x18003277a  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18003277f  mov     byte ptr [rbx+38h], 1
0x180032783  jmp     short loc_18003273F
0x180032785  xor     al, al
0x180032787  add     rsp, 78h
0x18003278b  pop     r15
0x18003278d  pop     r14
0x18003278f  pop     r13
0x180032791  pop     r12
0x180032793  pop     rdi
0x180032794  pop     rsi
0x180032795  pop     rbx
0x180032796  pop     rbp
0x180032797  retn
```
