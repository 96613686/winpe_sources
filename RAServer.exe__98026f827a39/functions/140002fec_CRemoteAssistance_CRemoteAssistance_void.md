# CRemoteAssistance::CRemoteAssistance(void)

- ea: `0x140002fec`
- end: `0x14000304f`
- name: `??0CRemoteAssistance@@QEAA@XZ`
- size: `99`
- prototype: `CRemoteAssistance *__fastcall(CRemoteAssistance *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140005944`
- `0x140005c6c`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x140003026`
- `KERNEL32!CreateEventW` at `0x14000303c`
- `KERNEL32!CreateEventW` at `0x140003026`
- `KERNEL32!CreateEventW` at `0x14000303c`

## pseudocode

```c
CRemoteAssistance *__fastcall CRemoteAssistance::CRemoteAssistance(CRemoteAssistance *this)
{
  *((_DWORD *)this + 4) = 0;
  *(_OWORD *)((char *)this + 24) = 0;
  *(_OWORD *)((char *)this + 40) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_BYTE *)this + 64) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_QWORD *)this + 11) = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 12) = CreateEventW(0, 1, 0, 0);
  return this;
}

```

## disassembly

```asm
0x140002fec  push    rbx
0x140002fee  sub     rsp, 20h
0x140002ff2  mov     rbx, rcx
0x140002ff5  xorps   xmm0, xmm0
0x140002ff8  xor     ecx, ecx; lpEventAttributes
0x140002ffa  xor     eax, eax
0x140002ffc  xor     r9d, r9d; lpName
0x140002fff  xor     r8d, r8d; bInitialState
0x140003002  mov     [rbx+10h], ecx
0x140003005  movups  xmmword ptr [rbx+18h], xmm0
0x140003009  lea     edx, [rcx+1]; bManualReset
0x14000300c  movups  xmmword ptr [rbx+28h], xmm0
0x140003010  mov     [rbx+38h], rax
0x140003014  mov     [rbx+40h], cl
0x140003017  mov     [rbx+48h], rcx
0x14000301b  mov     [rbx+68h], rcx
0x14000301f  mov     [rbx+70h], rcx
0x140003023  mov     [rbx+50h], ecx
0x140003026  call    cs:__imp_CreateEventW
0x14000302c  xor     r9d, r9d; lpName
0x14000302f  xor     r8d, r8d; bInitialState
0x140003032  xor     ecx, ecx; lpEventAttributes
0x140003034  mov     [rbx+58h], rax
0x140003038  lea     edx, [r9+1]; bManualReset
0x14000303c  call    cs:__imp_CreateEventW
0x140003042  mov     [rbx+60h], rax
0x140003046  mov     rax, rbx
0x140003049  add     rsp, 20h
0x14000304d  pop     rbx
0x14000304e  retn
```
