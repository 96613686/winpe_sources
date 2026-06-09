# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180006840`
- end: `0x180006a1a`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *indexData, unsigned __int64 indexSize, void *valueData, unsigned __int64 valueSize, unsigned int addend)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000674c`

## callees

- `0x180006840`
- `0x18000aa40`
- `0x18000ad50`
- `0x18000b800`
- `0x18000c970`
- `0x18000d770`
- `0x18000dd80`
- `0x18000e0b4`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800069b0`
- `msvcrt!memmove_s` at `0x1800069b0`

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
  unsigned __int8 *v10; // rdi
  char v11; // si
  bool v12; // al
  unsigned int v13; // r12d
  unsigned __int64 v14; // r13
  int v15; // eax
  unsigned __int64 Size; // rax
  unsigned __int8 *bufferAllocEnd; // rdx
  unsigned __int8 *bufferEnd; // r9
  __int64 v20; // r8
  __int64 v21; // r14
  wil::details_abi::UsageIndexProperty index; // [rsp+30h] [rbp-40h] BYREF
  wil::details_abi::UsageIndexProperty value; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int8 *buffer; // [rsp+B0h] [rbp+40h] BYREF
  void *v25; // [rsp+C8h] [rbp+58h]

  v25 = valueData;
  v6 = this->m_buffer.buffer;
  if ( v6 )
  {
    v10 = v6 + 10;
    index.c_size = this->c_indexSize;
    index.c_countSize = this->c_indexCountSize;
    index.size = 0;
    v11 = 0;
    buffer = v10;
    index.count = 0;
    *(_OWORD *)&index.countBuffer = 0;
    while ( 1 )
    {
      v12 = wil::details_abi::UsageIndexProperty::Read(&index, &buffer, this->m_buffer.bufferEnd);
      v13 = addend;
      v14 = valueSize;
      if ( !v12 )
      {
        v10 = buffer;
        this->m_buffer.bufferEnd = buffer;
        goto LABEL_14;
      }
      v15 = wil::details_abi::UsageIndexProperty::Compare(&index, indexData, indexSize);
      if ( v15 < 0 )
      {
        buffer = v10;
        goto LABEL_11;
      }
      if ( !v15 )
        break;
      v10 = wil::details_abi::RawUsageIndex::SkipValues(this, &index, buffer);
      buffer = v10;
    }
    buffer = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(this, &index, buffer, v25, v14, v13);
    v10 = buffer;
    if ( !buffer )
      return 1;
    v11 = 1;
LABEL_11:
    if ( v11 )
      goto LABEL_15;
LABEL_14:
    index.count = 1;
    index.size = indexSize;
    index.countBuffer = 0;
    index.value = indexData;
    wil::details_abi::UsageIndexProperty::GetSize(&index);
LABEL_15:
    value.c_size = this->c_valueSize;
    value.c_countSize = this->c_valueCountSize;
    value.count = v13;
    value.size = v14;
    value.countBuffer = 0;
    value.value = v25;
    Size = wil::details_abi::UsageIndexProperty::GetSize(&value);
    bufferAllocEnd = this->m_buffer.bufferAllocEnd;
    bufferEnd = this->m_buffer.bufferEnd;
    v21 = Size + v20;
    if ( ((bufferAllocEnd - bufferEnd) & (unsigned __int64)-(__int64)(bufferEnd < bufferAllocEnd)) >= Size + v20 )
    {
      memmove_s(&v10[v21], &bufferAllocEnd[-v21] - v10, v10, bufferEnd - v10);
      this->m_buffer.bufferEnd += v21;
      if ( v11 )
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
0x180006840  mov     [rsp-38h+arg_8], rbx
0x180006845  mov     [rsp-38h+arg_18], valueData
0x18000684a  push    rbp
0x18000684b  push    rsi
0x18000684c  push    rdi
0x18000684d  push    r12
0x18000684f  push    r13
0x180006851  push    r14
0x180006853  push    r15
0x180006855  mov     rbp, rsp
0x180006858  sub     rsp, 70h
0x18000685c  mov     rdi, [this+18h]
0x180006860  mov     r14, indexSize
0x180006863  mov     r15, indexData
0x180006866  mov     rbx, this
0x180006869  test    rdi, rdi
0x18000686c  jz      loc_180006A00
0x180006872  movzx   eax, word ptr [this+2]
0x180006876  add     rdi, 0Ah
0x18000687a  mov     [rbp+index.c_size], ax
0x18000687e  xorps   xmm0, xmm0
0x180006881  mov     al, [this+4]
0x180006884  mov     [rbp+index.c_countSize], al
0x180006887  xor     eax, eax
0x180006889  mov     [rbp+index.size], ax
0x18000688d  xor     sil, sil
0x180006890  mov     [rbp+buffer], rdi
0x180006894  mov     [rbp+index.count], 0
0x18000689b  movdqu  xmmword ptr [rbp+index.countBuffer], xmm0
0x1800068a0  mov     indexSize, [rbx+20h]; bufferEnd
0x1800068a4  lea     indexData, [rbp+buffer]; bufferParam
0x1800068a8  lea     this, [rbp+index]; this
0x1800068ac  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800068b1  mov     r12d, [rbp+arg_28]
0x1800068b5  mov     r13, [rbp+arg_20]
0x1800068b9  test    al, al
0x1800068bb  jz      short loc_180006924
0x1800068bd  mov     indexSize, r14; indexSize
0x1800068c0  lea     this, [rbp+index]; this
0x1800068c4  mov     indexData, r15; indexData
0x1800068c7  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x1800068cc  test    eax, eax
0x1800068ce  js      short loc_180006916
0x1800068d0  mov     indexSize, [rbp+buffer]; buffer
0x1800068d4  lea     indexData, [rbp+index]; index
0x1800068d8  mov     this, rbx; this
0x1800068db  jz      short loc_1800068EB
0x1800068dd  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x1800068e2  mov     rdi, rax
0x1800068e5  mov     [rbp+buffer], rax
0x1800068e9  jmp     short loc_1800068A0
0x1800068eb  mov     valueData, [rbp+arg_18]; valueData
0x1800068ef  mov     [rsp+70h+var_48], r12d; addend
0x1800068f4  mov     [rsp+70h+var_50], r13; valueSize
0x1800068f9  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x1800068fe  mov     [rbp+buffer], rax
0x180006902  mov     rdi, rax
0x180006905  test    rax, rax
0x180006908  jnz     short loc_180006911
0x18000690a  mov     al, 1
0x18000690c  jmp     loc_180006A02
0x180006911  mov     sil, 1
0x180006914  jmp     short loc_18000691A
0x180006916  mov     [rbp+buffer], rdi
0x18000691a  xor     r8d, r8d
0x18000691d  test    sil, sil
0x180006920  jnz     short loc_180006950
0x180006922  jmp     short loc_18000692C
0x180006924  mov     rdi, [rbp+buffer]
0x180006928  mov     [rbx+20h], rdi
0x18000692c  lea     this, [rbp+index]; this
0x180006930  mov     [rbp+index.count], 1
0x180006937  mov     [rbp+index.size], r14w
0x18000693c  mov     [rbp+index.countBuffer], 0
0x180006944  mov     [rbp+index.value], r15
0x180006948  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18000694d  mov     indexSize, rax
0x180006950  movzx   ecx, word ptr [rbx+6]
0x180006954  mov     rax, [rbp+arg_18]
0x180006958  mov     [rbp+value.c_size], cx
0x18000695c  mov     cl, [rbx+8]
0x18000695f  mov     [rbp+value.c_countSize], cl
0x180006962  lea     this, [rbp+value]; this
0x180006966  mov     [rbp+value.count], r12d
0x18000696a  mov     [rbp+value.size], r13w
0x18000696f  mov     [rbp+value.countBuffer], 0
0x180006977  mov     [rbp+value.value], rax
0x18000697b  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180006980  mov     indexData, [rbx+28h]
0x180006984  mov     valueData, [rbx+20h]
0x180006988  mov     this, indexData
0x18000698b  sub     this, valueData
0x18000698e  lea     r14, [rax+indexSize]
0x180006992  cmp     valueData, indexData
0x180006995  sbb     rax, rax
0x180006998  and     rax, this
0x18000699b  cmp     rax, r14
0x18000699e  jb      short loc_180006A00
0x1800069a0  sub     indexData, r14
0x1800069a3  lea     this, [r14+rdi]; Destination
0x1800069a7  sub     indexData, rdi; DestinationSize
0x1800069aa  sub     valueData, rdi; SourceSize
0x1800069ad  mov     indexSize, rdi; Source
0x1800069b0  call    cs:__imp_memmove_s
0x1800069b6  add     [rbx+20h], r14
0x1800069ba  test    sil, sil
0x1800069bd  jnz     short loc_1800069D2
0x1800069bf  mov     indexSize, [rbx+20h]; bufferEnd
0x1800069c3  lea     indexData, [rbp+buffer]; bufferParam
0x1800069c7  lea     this, [rbp+index]; this
0x1800069cb  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800069d0  jmp     short loc_1800069E6
0x1800069d2  cmp     [rbp+index.c_countSize], 0
0x1800069d6  jz      short loc_1800069E6
0x1800069d8  mov     edx, [rbp+index.count]
0x1800069db  lea     this, [rbp+index]; this
0x1800069df  inc     edx; newCount
0x1800069e1  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x1800069e6  mov     indexSize, [rbx+20h]; bufferEnd
0x1800069ea  lea     indexData, [rbp+buffer]; bufferParam
0x1800069ee  lea     this, [rbp+value]; this
0x1800069f2  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800069f7  mov     byte ptr [rbx+38h], 1
0x1800069fb  jmp     loc_18000690A
0x180006a00  xor     al, al
0x180006a02  mov     rbx, [rsp+70h+arg_8]
0x180006a0a  add     rsp, 70h
0x180006a0e  pop     r15
0x180006a10  pop     r14
0x180006a12  pop     r13
0x180006a14  pop     r12
0x180006a16  pop     rdi
0x180006a17  pop     rsi
0x180006a18  pop     rbp
0x180006a19  retn
```
