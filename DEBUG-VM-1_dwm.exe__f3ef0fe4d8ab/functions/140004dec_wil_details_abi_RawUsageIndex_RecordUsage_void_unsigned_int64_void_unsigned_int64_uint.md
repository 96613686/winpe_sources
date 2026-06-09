# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140004dec`
- end: `0x140004ed7`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `235`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x140007970`
- `0x14000a0e0`
- `0x14000a114`

## callees

- `0x140004dec`
- `0x140004ee0`
- `0x1400051a8`
- `0x14000886c`
- `0x14000aa9c`
- `0x14000b9a0`

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
0x140004dec  push    rbx
0x140004dee  push    rbp
0x140004def  push    rsi
0x140004df0  push    rdi
0x140004df1  push    r12
0x140004df3  push    r14
0x140004df5  push    r15
0x140004df7  sub     rsp, 50h
0x140004dfb  mov     r12d, [rsp+88h+arg_28]
0x140004e03  mov     r14, r9
0x140004e06  mov     rbp, [rsp+88h+arg_20]
0x140004e0e  mov     rsi, r8
0x140004e11  mov     [rsp+88h+var_60], r12d; unsigned int
0x140004e16  mov     r15, rdx
0x140004e19  mov     [rsp+88h+var_68], rbp; unsigned __int64
0x140004e1e  mov     rbx, rcx
0x140004e21  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140004e26  test    al, al
0x140004e28  jz      short loc_140004E31
0x140004e2a  mov     al, 1
0x140004e2c  jmp     loc_140004EC8
0x140004e31  lea     rdx, [rbp+20h]
0x140004e35  add     rdx, rsi; unsigned __int64
0x140004e38  cmp     qword ptr [rbx+18h], 0
0x140004e3d  jnz     short loc_140004E9E
0x140004e3f  xorps   xmm0, xmm0
0x140004e42  lea     rcx, [rsp+88h+var_58]; this
0x140004e47  xorps   xmm1, xmm1
0x140004e4a  add     rdx, 0Ah; unsigned __int64
0x140004e4e  movdqu  xmmword ptr [rsp+88h+var_58], xmm0
0x140004e54  movdqu  xmmword ptr [rsp+88h+var_48], xmm1
0x140004e5a  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140004e5f  test    al, al
0x140004e61  jz      short loc_140004E8D
0x140004e63  mov     rdx, [rsp+88h+var_58]; void *
0x140004e68  xor     r8d, r8d; unsigned __int64
0x140004e6b  mov     r9, [rsp+88h+var_48]
0x140004e70  mov     rcx, rbx; this
0x140004e73  sub     r9, rdx; unsigned __int64
0x140004e76  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x140004e7b  lea     rcx, [rbx+30h]
0x140004e7f  lea     rdx, [rsp+88h+var_48+8]
0x140004e84  call    ??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x140004e89  mov     byte ptr [rbx+3Ah], 1
0x140004e8d  mov     rcx, [rsp+88h+var_48+8]; this
0x140004e92  test    rcx, rcx
0x140004e95  jz      short loc_140004EAD
0x140004e97  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140004e9c  jmp     short loc_140004EAD
0x140004e9e  cmp     byte ptr [rbx+3Ah], 0
0x140004ea2  jz      short loc_140004EAD
0x140004ea4  lea     rcx, [rbx+18h]; this
0x140004ea8  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140004ead  mov     [rsp+88h+var_60], r12d; unsigned int
0x140004eb2  mov     r9, r14; void *
0x140004eb5  mov     r8, rsi; unsigned __int64
0x140004eb8  mov     [rsp+88h+var_68], rbp; unsigned __int64
0x140004ebd  mov     rdx, r15; void *
0x140004ec0  mov     rcx, rbx; this
0x140004ec3  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140004ec8  add     rsp, 50h
0x140004ecc  pop     r15
0x140004ece  pop     r14
0x140004ed0  pop     r12
0x140004ed2  pop     rdi
0x140004ed3  pop     rsi
0x140004ed4  pop     rbp
0x140004ed5  pop     rbx
0x140004ed6  retn
```
