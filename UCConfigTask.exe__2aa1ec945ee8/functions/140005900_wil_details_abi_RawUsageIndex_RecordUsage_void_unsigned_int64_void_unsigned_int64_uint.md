# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140005900`
- end: `0x1400059eb`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `235`
- prototype: `bool __fastcall(wil::details **this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x140003300`
- `0x14000582c`
- `0x140005860`

## callees

- `0x1400032c8`
- `0x140003ccc`
- `0x140005900`
- `0x1400059f4`
- `0x1400061ac`
- `0x14000737c`

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
0x140005900  push    rbx
0x140005902  push    rbp
0x140005903  push    rsi
0x140005904  push    rdi
0x140005905  push    r12
0x140005907  push    r14
0x140005909  push    r15
0x14000590b  sub     rsp, 50h
0x14000590f  mov     r12d, [rsp+88h+arg_28]
0x140005917  mov     r14, r9
0x14000591a  mov     rbp, [rsp+88h+arg_20]
0x140005922  mov     rsi, r8
0x140005925  mov     [rsp+88h+var_60], r12d; unsigned int
0x14000592a  mov     r15, rdx
0x14000592d  mov     [rsp+88h+var_68], rbp; unsigned __int64
0x140005932  mov     rbx, rcx
0x140005935  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x14000593a  test    al, al
0x14000593c  jz      short loc_140005945
0x14000593e  mov     al, 1
0x140005940  jmp     loc_1400059DC
0x140005945  lea     rdx, [rbp+20h]
0x140005949  add     rdx, rsi; unsigned __int64
0x14000594c  cmp     qword ptr [rbx+18h], 0
0x140005951  jnz     short loc_1400059B2
0x140005953  xorps   xmm0, xmm0
0x140005956  lea     rcx, [rsp+88h+var_58]; this
0x14000595b  xorps   xmm1, xmm1
0x14000595e  add     rdx, 0Ah; unsigned __int64
0x140005962  movdqu  xmmword ptr [rsp+88h+var_58], xmm0
0x140005968  movdqu  xmmword ptr [rsp+88h+var_48], xmm1
0x14000596e  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140005973  test    al, al
0x140005975  jz      short loc_1400059A1
0x140005977  mov     rdx, [rsp+88h+var_58]; void *
0x14000597c  xor     r8d, r8d; unsigned __int64
0x14000597f  mov     r9, [rsp+88h+var_48]
0x140005984  mov     rcx, rbx; this
0x140005987  sub     r9, rdx; unsigned __int64
0x14000598a  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x14000598f  lea     rcx, [rbx+30h]
0x140005993  lea     rdx, [rsp+88h+var_48+8]
0x140005998  call    ??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x14000599d  mov     byte ptr [rbx+3Ah], 1
0x1400059a1  mov     rcx, [rsp+88h+var_48+8]; this
0x1400059a6  test    rcx, rcx
0x1400059a9  jz      short loc_1400059C1
0x1400059ab  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1400059b0  jmp     short loc_1400059C1
0x1400059b2  cmp     byte ptr [rbx+3Ah], 0
0x1400059b6  jz      short loc_1400059C1
0x1400059b8  lea     rcx, [rbx+18h]; this
0x1400059bc  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1400059c1  mov     [rsp+88h+var_60], r12d; unsigned int
0x1400059c6  mov     r9, r14; void *
0x1400059c9  mov     r8, rsi; unsigned __int64
0x1400059cc  mov     [rsp+88h+var_68], rbp; unsigned __int64
0x1400059d1  mov     rdx, r15; void *
0x1400059d4  mov     rcx, rbx; this
0x1400059d7  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1400059dc  add     rsp, 50h
0x1400059e0  pop     r15
0x1400059e2  pop     r14
0x1400059e4  pop     r12
0x1400059e6  pop     rdi
0x1400059e7  pop     rsi
0x1400059e8  pop     rbp
0x1400059e9  pop     rbx
0x1400059ea  retn
```
