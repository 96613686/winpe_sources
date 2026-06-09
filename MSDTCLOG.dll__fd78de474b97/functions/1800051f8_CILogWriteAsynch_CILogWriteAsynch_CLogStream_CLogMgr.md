# CILogWriteAsynch::CILogWriteAsynch(CLogStream *,CLogMgr *)

- ea: `0x1800051f8`
- end: `0x18000526e`
- name: `??0CILogWriteAsynch@@QEAA@PEAVCLogStream@@PEAVCLogMgr@@@Z`
- size: `118`
- prototype: `CILogWriteAsynch *__fastcall(CILogWriteAsynch *__hidden this, struct CLogStream *, struct CLogMgr *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c918`

## callees

- `0x18000e64c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CILogWriteAsynch *__fastcall CILogWriteAsynch::CILogWriteAsynch(
        CILogWriteAsynch *this,
        struct CLogStream *a2,
        struct CLogMgr *a3)
{
  *(_QWORD *)this = &CILogWriteAsynch::`vftable';
  CSemExclusive::CSemExclusive((CILogWriteAsynch *)((char *)this + 32));
  CSemExclusive::CSemExclusive((CILogWriteAsynch *)((char *)this + 88));
  *((_QWORD *)this + 1) = a2;
  *((_QWORD *)this + 2) = a3;
  *((_DWORD *)this + 36) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 1;
  *((_QWORD *)this + 19) = 0;
  return this;
}

```

## disassembly

```asm
0x1800051f8  mov     [rsp+arg_8], rbx
0x1800051fd  mov     [rsp+arg_10], rsi
0x180005202  mov     [rsp+arg_0], rcx
0x180005207  push    rdi
0x180005208  sub     rsp, 20h
0x18000520c  mov     rdi, r8
0x18000520f  mov     rbx, rdx
0x180005212  mov     rsi, rcx
0x180005215  lea     rax, ??_7CILogWriteAsynch@@6B@; const CILogWriteAsynch::`vftable'
0x18000521c  mov     [rcx], rax
0x18000521f  add     rcx, 20h ; ' '; this
0x180005223  call    ??0CSemExclusive@@QEAA@K@Z; CSemExclusive::CSemExclusive(ulong)
0x180005228  nop
0x180005229  lea     rcx, [rsi+58h]; this
0x18000522d  call    ??0CSemExclusive@@QEAA@K@Z; CSemExclusive::CSemExclusive(ulong)
0x180005232  mov     [rsi+8], rbx
0x180005236  mov     [rsi+10h], rdi
0x18000523a  xor     eax, eax
0x18000523c  mov     [rsi+90h], eax
0x180005242  mov     [rsi+0A0h], rax
0x180005249  mov     qword ptr [rsi+0A8h], 1
0x180005254  mov     [rsi+98h], rax
0x18000525b  mov     rax, rsi
0x18000525e  mov     rbx, [rsp+28h+arg_8]
0x180005263  mov     rsi, [rsp+28h+arg_10]
0x180005268  add     rsp, 20h
0x18000526c  pop     rdi
0x18000526d  retn
```
