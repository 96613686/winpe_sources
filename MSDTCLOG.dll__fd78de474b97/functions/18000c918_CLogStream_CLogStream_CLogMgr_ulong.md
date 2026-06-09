# CLogStream::CLogStream(CLogMgr *,ulong)

- ea: `0x18000c918`
- end: `0x18000ca11`
- name: `??0CLogStream@@QEAA@PEAVCLogMgr@@K@Z`
- size: `249`
- prototype: `CLogStream *__fastcall(CLogStream *__hidden this, struct CLogMgr *, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800042b4`
- `0x1800044c8`
- `0x1800047b0`
- `0x180004a00`

## callees

- `0x1800051f8`
- `0x18000e64c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
CLogStream *__fastcall CLogStream::CLogStream(CLogStream *this, struct CLogMgr *a2, int a3)
{
  int v6; // ecx

  *(_QWORD *)this = &CLogStream::`vftable';
  CSemExclusive::CSemExclusive((CLogStream *)((char *)this + 16));
  *((_QWORD *)this + 10) = &CILogRead::`vftable';
  *((_QWORD *)this + 11) = this;
  *((_QWORD *)this + 12) = a2;
  *((_QWORD *)this + 14) = &CILogWrite::`vftable';
  *((_QWORD *)this + 15) = this;
  *((_QWORD *)this + 16) = a2;
  CILogWriteAsynch::CILogWriteAsynch((CLogStream *)((char *)this + 144), this, a2);
  *((_QWORD *)this + 40) = a2;
  v6 = *((_DWORD *)a2 + 158);
  *((_QWORD *)this + 66) = *((_QWORD *)a2 + 49);
  *((_DWORD *)this + 134) = v6;
  *((_DWORD *)this + 99) = 0;
  *((_DWORD *)this + 90) = 0;
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 68) = 0;
  *((_DWORD *)this + 82) = a3;
  *(_OWORD *)((char *)this + 552) = 0;
  *((_QWORD *)this + 71) = 0;
  *((_DWORD *)this + 144) = 0;
  *((_QWORD *)this + 73) = 0;
  *((_QWORD *)this + 74) = 0;
  *((_DWORD *)this + 150) = -1;
  *((_DWORD *)this + 151) = -1;
  return this;
}

```

## disassembly

```asm
0x18000c918  mov     [rsp+arg_8], rbx
0x18000c91d  mov     [rsp+arg_10], rsi
0x18000c922  mov     [rsp+arg_0], rcx
0x18000c927  push    rdi
0x18000c928  sub     rsp, 20h
0x18000c92c  mov     edi, r8d
0x18000c92f  mov     rbx, rdx
0x18000c932  mov     rsi, rcx
0x18000c935  lea     rax, ??_7CLogStream@@6B@; const CLogStream::`vftable'
0x18000c93c  mov     [rcx], rax
0x18000c93f  add     rcx, 10h; this
0x18000c943  call    ??0CSemExclusive@@QEAA@K@Z; CSemExclusive::CSemExclusive(ulong)
0x18000c948  nop
0x18000c949  lea     rax, ??_7CILogRead@@6B@; const CILogRead::`vftable'
0x18000c950  mov     [rsi+50h], rax
0x18000c954  mov     [rsi+58h], rsi
0x18000c958  mov     [rsi+60h], rbx
0x18000c95c  lea     rax, ??_7CILogWrite@@6B@; const CILogWrite::`vftable'
0x18000c963  mov     [rsi+70h], rax
0x18000c967  mov     [rsi+78h], rsi
0x18000c96b  mov     [rsi+80h], rbx
0x18000c972  lea     rcx, [rsi+90h]; this
0x18000c979  mov     r8, rbx; struct CLogMgr *
0x18000c97c  mov     rdx, rsi; struct CLogStream *
0x18000c97f  call    ??0CILogWriteAsynch@@QEAA@PEAVCLogStream@@PEAVCLogMgr@@@Z; CILogWriteAsynch::CILogWriteAsynch(CLogStream *,CLogMgr *)
0x18000c984  nop
0x18000c985  mov     [rsi+140h], rbx
0x18000c98c  mov     ecx, [rbx+278h]
0x18000c992  mov     rax, [rbx+188h]
0x18000c999  mov     [rsi+210h], rax
0x18000c9a0  mov     [rsi+218h], ecx
0x18000c9a6  xor     ecx, ecx
0x18000c9a8  mov     [rsi+18Ch], ecx
0x18000c9ae  mov     [rsi+168h], ecx
0x18000c9b4  mov     [rsi+8], ecx
0x18000c9b7  mov     [rsi+48h], rcx
0x18000c9bb  mov     [rsi+220h], rcx
0x18000c9c2  mov     [rsi+148h], edi
0x18000c9c8  xorps   xmm0, xmm0
0x18000c9cb  xor     eax, eax
0x18000c9cd  movups  xmmword ptr [rsi+228h], xmm0
0x18000c9d4  mov     [rsi+238h], rax
0x18000c9db  mov     [rsi+240h], ecx
0x18000c9e1  mov     [rsi+248h], rcx
0x18000c9e8  mov     [rsi+250h], rcx
0x18000c9ef  or      eax, 0FFFFFFFFh
0x18000c9f2  mov     [rsi+258h], eax
0x18000c9f8  mov     [rsi+25Ch], eax
0x18000c9fe  mov     rax, rsi
0x18000ca01  mov     rbx, [rsp+28h+arg_8]
0x18000ca06  mov     rsi, [rsp+28h+arg_10]
0x18000ca0b  add     rsp, 20h
0x18000ca0f  pop     rdi
0x18000ca10  retn
```
