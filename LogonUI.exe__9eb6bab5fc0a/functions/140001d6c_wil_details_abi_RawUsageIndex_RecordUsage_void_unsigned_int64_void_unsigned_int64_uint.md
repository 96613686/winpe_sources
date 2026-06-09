# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140001d6c`
- end: `0x140001e57`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `235`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x140003e00`
- `0x140005cd4`
- `0x140005d08`

## callees

- `0x140001d6c`
- `0x140001e60`
- `0x140002464`
- `0x14000469c`
- `0x1400063cc`
- `0x14000712c`

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
0x140001d6c  push    rbx
0x140001d6e  push    rbp
0x140001d6f  push    rsi
0x140001d70  push    rdi
0x140001d71  push    r12
0x140001d73  push    r14
0x140001d75  push    r15
0x140001d77  sub     rsp, 50h
0x140001d7b  mov     r12d, [rsp+88h+arg_28]
0x140001d83  mov     r14, r9
0x140001d86  mov     rbp, [rsp+88h+arg_20]
0x140001d8e  mov     rsi, r8
0x140001d91  mov     [rsp+88h+var_60], r12d; unsigned int
0x140001d96  mov     r15, rdx
0x140001d99  mov     [rsp+88h+var_68], rbp; unsigned __int64
0x140001d9e  mov     rbx, rcx
0x140001da1  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140001da6  test    al, al
0x140001da8  jz      short loc_140001DB1
0x140001daa  mov     al, 1
0x140001dac  jmp     loc_140001E48
0x140001db1  lea     rdx, [rbp+20h]
0x140001db5  add     rdx, rsi; unsigned __int64
0x140001db8  cmp     qword ptr [rbx+18h], 0
0x140001dbd  jnz     short loc_140001E1E
0x140001dbf  xorps   xmm0, xmm0
0x140001dc2  lea     rcx, [rsp+88h+var_58]; this
0x140001dc7  xorps   xmm1, xmm1
0x140001dca  add     rdx, 0Ah; unsigned __int64
0x140001dce  movdqu  xmmword ptr [rsp+88h+var_58], xmm0
0x140001dd4  movdqu  xmmword ptr [rsp+88h+var_48], xmm1
0x140001dda  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140001ddf  test    al, al
0x140001de1  jz      short loc_140001E0D
0x140001de3  mov     rdx, [rsp+88h+var_58]; void *
0x140001de8  xor     r8d, r8d; unsigned __int64
0x140001deb  mov     r9, [rsp+88h+var_48]
0x140001df0  mov     rcx, rbx; this
0x140001df3  sub     r9, rdx; unsigned __int64
0x140001df6  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x140001dfb  lea     rcx, [rbx+30h]
0x140001dff  lea     rdx, [rsp+88h+var_48+8]
0x140001e04  call    ??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x140001e09  mov     byte ptr [rbx+3Ah], 1
0x140001e0d  mov     rcx, [rsp+88h+var_48+8]; this
0x140001e12  test    rcx, rcx
0x140001e15  jz      short loc_140001E2D
0x140001e17  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140001e1c  jmp     short loc_140001E2D
0x140001e1e  cmp     byte ptr [rbx+3Ah], 0
0x140001e22  jz      short loc_140001E2D
0x140001e24  lea     rcx, [rbx+18h]; this
0x140001e28  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140001e2d  mov     [rsp+88h+var_60], r12d; unsigned int
0x140001e32  mov     r9, r14; void *
0x140001e35  mov     r8, rsi; unsigned __int64
0x140001e38  mov     [rsp+88h+var_68], rbp; unsigned __int64
0x140001e3d  mov     rdx, r15; void *
0x140001e40  mov     rcx, rbx; this
0x140001e43  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140001e48  add     rsp, 50h
0x140001e4c  pop     r15
0x140001e4e  pop     r14
0x140001e50  pop     r12
0x140001e52  pop     rdi
0x140001e53  pop     rsi
0x140001e54  pop     rbp
0x140001e55  pop     rbx
0x140001e56  retn
```
