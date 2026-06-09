# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140004088`
- end: `0x140004173`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `235`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x140004020`
- `0x14000c350`
- `0x14000c384`

## callees

- `0x140003f10`
- `0x140004088`
- `0x14000417c`
- `0x140004d8c`
- `0x1400079c4`
- `0x140008120`

## pseudocode

```c
bool __fastcall wil::details_abi::RawUsageIndex::RecordUsage(
        wil::details **this,
        void *a2,
        unsigned __int64 a3,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  unsigned __int64 v11; // rdx
  void *v12; // rdx
  void *v13[2]; // [rsp+30h] [rbp-58h] BYREF
  wil::details *v14[2]; // [rsp+40h] [rbp-48h] BYREF

  if ( wil::details_abi::RawUsageIndex::RecordUsageInternal((wil::details_abi::RawUsageIndex *)this, a2, a3, a4, a5, a6) )
    return 1;
  v11 = a3 + a5 + 32;
  if ( this[3] )
  {
    if ( *((_BYTE *)this + 58) )
      wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)(this + 3), v11);
  }
  else
  {
    *(_OWORD *)v13 = 0;
    *(_OWORD *)v14 = 0;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)v13, v11 + 10) )
    {
      wil::details_abi::RawUsageIndex::SetBuffer(
        (wil::details_abi::RawUsageIndex *)this,
        v13[0],
        0,
        (char *)v14[0] - (char *)v13[0]);
      wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(this + 6, &v14[1]);
      *((_BYTE *)this + 58) = 1;
    }
    if ( v14[1] )
      wil::details::FreeProcessHeap(v14[1], v12);
  }
  return wil::details_abi::RawUsageIndex::RecordUsageInternal(
           (wil::details_abi::RawUsageIndex *)this,
           a2,
           a3,
           a4,
           a5,
           a6);
}

```

## disassembly

```asm
0x140004088  push    rbx
0x14000408a  push    rbp
0x14000408b  push    rsi
0x14000408c  push    rdi
0x14000408d  push    r12
0x14000408f  push    r14
0x140004091  push    r15
0x140004093  sub     rsp, 50h
0x140004097  mov     r12d, [rsp+88h+arg_28]
0x14000409f  mov     r14, r9
0x1400040a2  mov     rbp, [rsp+88h+arg_20]
0x1400040aa  mov     rsi, r8
0x1400040ad  mov     [rsp+88h+var_60], r12d; unsigned int
0x1400040b2  mov     r15, rdx
0x1400040b5  mov     [rsp+88h+var_68], rbp; unsigned __int64
0x1400040ba  mov     rbx, rcx
0x1400040bd  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1400040c2  test    al, al
0x1400040c4  jz      short loc_1400040CD
0x1400040c6  mov     al, 1
0x1400040c8  jmp     loc_140004164
0x1400040cd  lea     rdx, [rbp+20h]
0x1400040d1  add     rdx, rsi; unsigned __int64
0x1400040d4  cmp     qword ptr [rbx+18h], 0
0x1400040d9  jnz     short loc_14000413A
0x1400040db  xorps   xmm0, xmm0
0x1400040de  lea     rcx, [rsp+88h+var_58]; this
0x1400040e3  xorps   xmm1, xmm1
0x1400040e6  add     rdx, 0Ah; unsigned __int64
0x1400040ea  movdqu  xmmword ptr [rsp+88h+var_58], xmm0
0x1400040f0  movdqu  xmmword ptr [rsp+88h+var_48], xmm1
0x1400040f6  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1400040fb  test    al, al
0x1400040fd  jz      short loc_140004129
0x1400040ff  mov     rdx, [rsp+88h+var_58]; void *
0x140004104  xor     r8d, r8d; unsigned __int64
0x140004107  mov     r9, [rsp+88h+var_48]
0x14000410c  mov     rcx, rbx; this
0x14000410f  sub     r9, rdx; unsigned __int64
0x140004112  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x140004117  lea     rcx, [rbx+30h]
0x14000411b  lea     rdx, [rsp+88h+var_48+8]
0x140004120  call    ??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x140004125  mov     byte ptr [rbx+3Ah], 1
0x140004129  mov     rcx, [rsp+88h+var_48+8]; this
0x14000412e  test    rcx, rcx
0x140004131  jz      short loc_140004149
0x140004133  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140004138  jmp     short loc_140004149
0x14000413a  cmp     byte ptr [rbx+3Ah], 0
0x14000413e  jz      short loc_140004149
0x140004140  lea     rcx, [rbx+18h]; this
0x140004144  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140004149  mov     [rsp+88h+var_60], r12d; unsigned int
0x14000414e  mov     r9, r14; void *
0x140004151  mov     r8, rsi; unsigned __int64
0x140004154  mov     [rsp+88h+var_68], rbp; unsigned __int64
0x140004159  mov     rdx, r15; void *
0x14000415c  mov     rcx, rbx; this
0x14000415f  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140004164  add     rsp, 50h
0x140004168  pop     r15
0x14000416a  pop     r14
0x14000416c  pop     r12
0x14000416e  pop     rdi
0x14000416f  pop     rsi
0x140004170  pop     rbp
0x140004171  pop     rbx
0x140004172  retn
```
