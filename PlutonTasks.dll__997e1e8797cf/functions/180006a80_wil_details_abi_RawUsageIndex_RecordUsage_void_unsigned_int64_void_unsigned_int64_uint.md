# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180006a80`
- end: `0x180006b6b`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `235`
- prototype: `bool __fastcall(wil::details **this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180003a90`
- `0x1800069ac`
- `0x1800069e0`

## callees

- `0x180003a58`
- `0x180004bcc`
- `0x180006a80`
- `0x180006b74`
- `0x1800076ac`
- `0x180008ba0`

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
0x180006a80  push    rbx
0x180006a82  push    rbp
0x180006a83  push    rsi
0x180006a84  push    rdi
0x180006a85  push    r12
0x180006a87  push    r14
0x180006a89  push    r15
0x180006a8b  sub     rsp, 50h
0x180006a8f  mov     r12d, [rsp+88h+arg_28]
0x180006a97  mov     r14, r9
0x180006a9a  mov     rbp, [rsp+88h+arg_20]
0x180006aa2  mov     rsi, r8
0x180006aa5  mov     [rsp+88h+var_60], r12d; unsigned int
0x180006aaa  mov     r15, rdx
0x180006aad  mov     [rsp+88h+var_68], rbp; unsigned __int64
0x180006ab2  mov     rbx, rcx
0x180006ab5  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180006aba  test    al, al
0x180006abc  jz      short loc_180006AC5
0x180006abe  mov     al, 1
0x180006ac0  jmp     loc_180006B5C
0x180006ac5  lea     rdx, [rbp+20h]
0x180006ac9  add     rdx, rsi; unsigned __int64
0x180006acc  cmp     qword ptr [rbx+18h], 0
0x180006ad1  jnz     short loc_180006B32
0x180006ad3  xorps   xmm0, xmm0
0x180006ad6  lea     rcx, [rsp+88h+var_58]; this
0x180006adb  xorps   xmm1, xmm1
0x180006ade  add     rdx, 0Ah; unsigned __int64
0x180006ae2  movdqu  xmmword ptr [rsp+88h+var_58], xmm0
0x180006ae8  movdqu  xmmword ptr [rsp+88h+var_48], xmm1
0x180006aee  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006af3  test    al, al
0x180006af5  jz      short loc_180006B21
0x180006af7  mov     rdx, [rsp+88h+var_58]; void *
0x180006afc  xor     r8d, r8d; unsigned __int64
0x180006aff  mov     r9, [rsp+88h+var_48]
0x180006b04  mov     rcx, rbx; this
0x180006b07  sub     r9, rdx; unsigned __int64
0x180006b0a  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180006b0f  lea     rcx, [rbx+30h]
0x180006b13  lea     rdx, [rsp+88h+var_48+8]
0x180006b18  call    ??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x180006b1d  mov     byte ptr [rbx+3Ah], 1
0x180006b21  mov     rcx, [rsp+88h+var_48+8]; this
0x180006b26  test    rcx, rcx
0x180006b29  jz      short loc_180006B41
0x180006b2b  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180006b30  jmp     short loc_180006B41
0x180006b32  cmp     byte ptr [rbx+3Ah], 0
0x180006b36  jz      short loc_180006B41
0x180006b38  lea     rcx, [rbx+18h]; this
0x180006b3c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006b41  mov     [rsp+88h+var_60], r12d; unsigned int
0x180006b46  mov     r9, r14; void *
0x180006b49  mov     r8, rsi; unsigned __int64
0x180006b4c  mov     [rsp+88h+var_68], rbp; unsigned __int64
0x180006b51  mov     rdx, r15; void *
0x180006b54  mov     rcx, rbx; this
0x180006b57  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180006b5c  add     rsp, 50h
0x180006b60  pop     r15
0x180006b62  pop     r14
0x180006b64  pop     r12
0x180006b66  pop     rdi
0x180006b67  pop     rsi
0x180006b68  pop     rbp
0x180006b69  pop     rbx
0x180006b6a  retn
```
