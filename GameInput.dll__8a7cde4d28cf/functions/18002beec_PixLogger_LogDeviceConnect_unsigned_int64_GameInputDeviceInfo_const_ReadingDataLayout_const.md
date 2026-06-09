# PixLogger::LogDeviceConnect(unsigned __int64,GameInputDeviceInfo const *,ReadingDataLayout const *)

- ea: `0x18002beec`
- end: `0x18002c08b`
- name: `?LogDeviceConnect@PixLogger@@QEAAX_KPEBUGameInputDeviceInfo@@PEBVReadingDataLayout@@@Z`
- size: `415`
- prototype: `void __fastcall(PixLogger *__hidden this, unsigned __int64, const struct GameInputDeviceInfo *, const struct ReadingDataLayout *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180008860`
- `0x180009050`

## callees

- `0x18002bdcc`
- `0x18002beec`
- `0x18004c8a5`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002bf0e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002bf0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c07f`

## pseudocode

```c
void __fastcall PixLogger::LogDeviceConnect(
        RTL_SRWLOCK *this,
        __int64 a2,
        const struct GameInputDeviceInfo *a3,
        const struct ReadingDataLayout *a4)
{
  RTL_SRWLOCK *v4; // rbp
  enum byte *EventBufferPtr; // rbx

  v4 = this + 1;
  AcquireSRWLockExclusive(this + 1);
  if ( LOBYTE(this[6].Ptr) && this[2].Ptr )
  {
    EventBufferPtr = PixLogger::GetEventBufferPtr((PixLogger *)this, 0x208u);
    memset_0((char *)EventBufferPtr + 24, 0, 0x148u);
    memset_0((char *)EventBufferPtr + 352, 0, 0xA8u);
    *(_QWORD *)EventBufferPtr = 520;
    *((_QWORD *)EventBufferPtr + 1) = a2;
    *((_DWORD *)EventBufferPtr + 4) = 24;
    *((_DWORD *)EventBufferPtr + 5) = 352;
    *(_OWORD *)((char *)EventBufferPtr + 24) = *(_OWORD *)a3;
    *(_OWORD *)((char *)EventBufferPtr + 40) = *((_OWORD *)a3 + 1);
    *(_OWORD *)((char *)EventBufferPtr + 56) = *((_OWORD *)a3 + 2);
    *(_OWORD *)((char *)EventBufferPtr + 72) = *((_OWORD *)a3 + 3);
    *(_OWORD *)((char *)EventBufferPtr + 88) = *((_OWORD *)a3 + 4);
    *(_OWORD *)((char *)EventBufferPtr + 104) = *((_OWORD *)a3 + 5);
    *(_OWORD *)((char *)EventBufferPtr + 120) = *((_OWORD *)a3 + 6);
    *(_OWORD *)((char *)EventBufferPtr + 136) = *((_OWORD *)a3 + 7);
    *(_OWORD *)((char *)EventBufferPtr + 152) = *((_OWORD *)a3 + 8);
    *(_OWORD *)((char *)EventBufferPtr + 168) = *((_OWORD *)a3 + 9);
    memset_0((char *)EventBufferPtr + 184, 0, 0xA8u);
    *((_OWORD *)EventBufferPtr + 22) = *(_OWORD *)a4;
    *((_OWORD *)EventBufferPtr + 23) = *((_OWORD *)a4 + 1);
    *((_OWORD *)EventBufferPtr + 24) = *((_OWORD *)a4 + 2);
    *((_OWORD *)EventBufferPtr + 25) = *((_OWORD *)a4 + 3);
    *((_OWORD *)EventBufferPtr + 26) = *((_OWORD *)a4 + 4);
    *((_OWORD *)EventBufferPtr + 27) = *((_OWORD *)a4 + 5);
    *((_OWORD *)EventBufferPtr + 28) = *((_OWORD *)a4 + 6);
    *((_OWORD *)EventBufferPtr + 29) = *((_OWORD *)a4 + 7);
    *((_OWORD *)EventBufferPtr + 30) = *((_OWORD *)a4 + 8);
    *((_OWORD *)EventBufferPtr + 31) = *((_OWORD *)a4 + 9);
    *((_QWORD *)EventBufferPtr + 64) = *((_QWORD *)a4 + 20);
  }
  ReleaseSRWLockExclusive(v4);
}

```

## disassembly

```asm
0x18002beec  push    rbx
0x18002beee  push    rbp
0x18002beef  push    rsi
0x18002bef0  push    rdi
0x18002bef1  push    r12
0x18002bef3  push    r14
0x18002bef5  push    r15
0x18002bef7  sub     rsp, 20h
0x18002befb  lea     rbp, [rcx+8]
0x18002beff  mov     rbx, rcx
0x18002bf02  mov     rcx, rbp; SRWLock
0x18002bf05  mov     r14, r9
0x18002bf08  mov     r15, r8
0x18002bf0b  mov     r12, rdx
0x18002bf0e  call    cs:__imp_AcquireSRWLockExclusive
0x18002bf15  nop     dword ptr [rax+rax+00h]
0x18002bf1a  cmp     byte ptr [rbx+30h], 0
0x18002bf1e  jz      loc_18002C06E
0x18002bf24  cmp     qword ptr [rbx+10h], 0
0x18002bf29  jz      loc_18002C06E
0x18002bf2f  mov     edx, 208h; unsigned __int64
0x18002bf34  mov     rcx, rbx; this
0x18002bf37  call    ?GetEventBufferPtr@PixLogger@@AEAAPEAW4byte@utl@@_K@Z; PixLogger::GetEventBufferPtr(unsigned __int64)
0x18002bf3c  xor     edx, edx; Val
0x18002bf3e  mov     r8d, 148h; Size
0x18002bf44  mov     rbx, rax
0x18002bf47  lea     rcx, [rax+18h]; void *
0x18002bf4b  call    memset_0
0x18002bf50  lea     rsi, [rbx+160h]
0x18002bf57  xor     edx, edx; Val
0x18002bf59  mov     rcx, rsi; void *
0x18002bf5c  mov     r8d, 0A8h; Size
0x18002bf62  call    memset_0
0x18002bf67  mov     qword ptr [rbx], 208h
0x18002bf6e  lea     rcx, [rbx+0B8h]; void *
0x18002bf75  mov     [rbx+8], r12
0x18002bf79  xor     edx, edx; Val
0x18002bf7b  mov     dword ptr [rbx+10h], 18h
0x18002bf82  mov     r8d, 0A8h; Size
0x18002bf88  mov     dword ptr [rbx+14h], 160h
0x18002bf8f  movups  xmm0, xmmword ptr [r15]
0x18002bf93  movups  xmmword ptr [rbx+18h], xmm0
0x18002bf97  movups  xmm1, xmmword ptr [r15+10h]
0x18002bf9c  movups  xmmword ptr [rbx+28h], xmm1
0x18002bfa0  movups  xmm0, xmmword ptr [r15+20h]
0x18002bfa5  movups  xmmword ptr [rbx+38h], xmm0
0x18002bfa9  movups  xmm1, xmmword ptr [r15+30h]
0x18002bfae  movups  xmmword ptr [rbx+48h], xmm1
0x18002bfb2  movups  xmm0, xmmword ptr [r15+40h]
0x18002bfb7  movups  xmmword ptr [rbx+58h], xmm0
0x18002bfbb  movups  xmm1, xmmword ptr [r15+50h]
0x18002bfc0  movups  xmmword ptr [rbx+68h], xmm1
0x18002bfc4  movups  xmm0, xmmword ptr [r15+60h]
0x18002bfc9  movups  xmmword ptr [rbx+78h], xmm0
0x18002bfcd  movups  xmm1, xmmword ptr [r15+70h]
0x18002bfd2  movups  xmmword ptr [rbx+88h], xmm1
0x18002bfd9  movups  xmm0, xmmword ptr [r15+80h]
0x18002bfe1  movups  xmmword ptr [rbx+98h], xmm0
0x18002bfe8  movups  xmm1, xmmword ptr [r15+90h]
0x18002bff0  movups  xmmword ptr [rbx+0A8h], xmm1
0x18002bff7  call    memset_0
0x18002bffc  movups  xmm0, xmmword ptr [r14]
0x18002c000  movups  xmmword ptr [rsi], xmm0
0x18002c003  movups  xmm1, xmmword ptr [r14+10h]
0x18002c008  movups  xmmword ptr [rsi+10h], xmm1
0x18002c00c  movups  xmm0, xmmword ptr [r14+20h]
0x18002c011  movups  xmmword ptr [rsi+20h], xmm0
0x18002c015  movups  xmm1, xmmword ptr [r14+30h]
0x18002c01a  movups  xmmword ptr [rsi+30h], xmm1
0x18002c01e  movups  xmm0, xmmword ptr [r14+40h]
0x18002c023  movups  xmmword ptr [rsi+40h], xmm0
0x18002c027  movups  xmm1, xmmword ptr [r14+50h]
0x18002c02c  movups  xmmword ptr [rsi+50h], xmm1
0x18002c030  movups  xmm0, xmmword ptr [r14+60h]
0x18002c035  movups  xmmword ptr [rsi+60h], xmm0
0x18002c039  movups  xmm1, xmmword ptr [r14+70h]
0x18002c03e  movups  xmmword ptr [rsi+70h], xmm1
0x18002c042  movups  xmm0, xmmword ptr [r14+80h]
0x18002c04a  movups  xmmword ptr [rsi+80h], xmm0
0x18002c051  movups  xmm1, xmmword ptr [r14+90h]
0x18002c059  movups  xmmword ptr [rsi+90h], xmm1
0x18002c060  mov     rax, [r14+0A0h]
0x18002c067  mov     [rsi+0A0h], rax
0x18002c06e  mov     rcx, rbp
0x18002c071  add     rsp, 20h
0x18002c075  pop     r15
0x18002c077  pop     r14
0x18002c079  pop     r12
0x18002c07b  pop     rdi
0x18002c07c  pop     rsi
0x18002c07d  pop     rbp
0x18002c07e  pop     rbx
0x18002c07f  jmp     cs:__imp_ReleaseSRWLockExclusive
```
