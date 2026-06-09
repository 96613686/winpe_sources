# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x14000798c`
- end: `0x140007a74`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x140005100`
- `0x1400078b8`
- `0x1400078ec`

## callees

- `0x140002c70`
- `0x1400050cc`
- `0x14000798c`
- `0x140007a7c`
- `0x14000852c`
- `0x1400096c4`

## pseudocode

```c
bool __fastcall wil::details_abi::RawUsageIndex::RecordUsage(
        void **this,
        void *a2,
        unsigned __int64 a3,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  unsigned __int64 v11; // rdx
  void *v12[2]; // [rsp+30h] [rbp-58h] BYREF
  _OWORD v13[4]; // [rsp+40h] [rbp-48h] BYREF

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
    *(_OWORD *)v12 = 0;
    v13[0] = 0;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)v12, v11 + 10) )
    {
      wil::details_abi::RawUsageIndex::SetBuffer(
        (wil::details_abi::RawUsageIndex *)this,
        v12[0],
        0,
        *(_QWORD *)&v13[0] - (unsigned __int64)v12[0]);
      wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(this + 6, (void **)v13 + 1);
      *((_BYTE *)this + 58) = 1;
    }
    wistd::unique_ptr<void,wil::process_heap_deleter>::reset((void **)v13 + 1, 0);
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
0x14000798c  push    rbx
0x14000798e  push    rbp
0x14000798f  push    rsi
0x140007990  push    rdi
0x140007991  push    r12
0x140007993  push    r14
0x140007995  push    r15
0x140007997  sub     rsp, 50h
0x14000799b  mov     r12d, [rsp+88h+arg_28]
0x1400079a3  mov     r14, r9
0x1400079a6  mov     rbp, [rsp+88h+arg_20]
0x1400079ae  mov     rsi, r8
0x1400079b1  mov     [rsp+88h+var_60], r12d; unsigned int
0x1400079b6  mov     r15, rdx
0x1400079b9  mov     [rsp+88h+var_68], rbp; unsigned __int64
0x1400079be  mov     rbx, rcx
0x1400079c1  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1400079c6  test    al, al
0x1400079c8  jz      short loc_1400079D1
0x1400079ca  mov     al, 1
0x1400079cc  jmp     loc_140007A65
0x1400079d1  lea     rdx, [rbp+20h]
0x1400079d5  add     rdx, rsi; unsigned __int64
0x1400079d8  cmp     qword ptr [rbx+18h], 0
0x1400079dd  jnz     short loc_140007A3B
0x1400079df  xorps   xmm0, xmm0
0x1400079e2  lea     rcx, [rsp+88h+var_58]; this
0x1400079e7  xorps   xmm1, xmm1
0x1400079ea  add     rdx, 0Ah; unsigned __int64
0x1400079ee  movdqu  xmmword ptr [rsp+88h+var_58], xmm0
0x1400079f4  movdqu  [rsp+88h+var_48], xmm1
0x1400079fa  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1400079ff  test    al, al
0x140007a01  jz      short loc_140007A2D
0x140007a03  mov     rdx, [rsp+88h+var_58]; void *
0x140007a08  xor     r8d, r8d; unsigned __int64
0x140007a0b  mov     r9, qword ptr [rsp+88h+var_48]
0x140007a10  mov     rcx, rbx; this
0x140007a13  sub     r9, rdx; unsigned __int64
0x140007a16  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x140007a1b  lea     rcx, [rbx+30h]
0x140007a1f  lea     rdx, [rsp+88h+var_48+8]
0x140007a24  call    ??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x140007a29  mov     byte ptr [rbx+3Ah], 1
0x140007a2d  xor     edx, edx
0x140007a2f  lea     rcx, [rsp+88h+var_48+8]
0x140007a34  call    ?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)
0x140007a39  jmp     short loc_140007A4A
0x140007a3b  cmp     byte ptr [rbx+3Ah], 0
0x140007a3f  jz      short loc_140007A4A
0x140007a41  lea     rcx, [rbx+18h]; this
0x140007a45  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140007a4a  mov     [rsp+88h+var_60], r12d; unsigned int
0x140007a4f  mov     r9, r14; void *
0x140007a52  mov     r8, rsi; unsigned __int64
0x140007a55  mov     [rsp+88h+var_68], rbp; unsigned __int64
0x140007a5a  mov     rdx, r15; void *
0x140007a5d  mov     rcx, rbx; this
0x140007a60  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140007a65  add     rsp, 50h
0x140007a69  pop     r15
0x140007a6b  pop     r14
0x140007a6d  pop     r12
0x140007a6f  pop     rdi
0x140007a70  pop     rsi
0x140007a71  pop     rbp
0x140007a72  pop     rbx
0x140007a73  retn
```
