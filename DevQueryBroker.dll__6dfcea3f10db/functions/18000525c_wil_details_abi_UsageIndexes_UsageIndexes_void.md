# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x18000525c`
- end: `0x18000531c`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `192`
- prototype: `wil::details_abi::UsageIndexes *__fastcall(wil::details_abi::UsageIndexes *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800054e4`
- `0x180005d10`
- `0x18000807c`
- `0x180008b30`

## pseudocode

```c
wil::details_abi::UsageIndexes *__fastcall wil::details_abi::UsageIndexes::UsageIndexes(
        wil::details_abi::UsageIndexes *this)
{
  wil::details_abi::UsageIndexes *result; // rax

  *(_DWORD *)this = 0x40000;
  *((_BYTE *)this + 4) = 1;
  result = this;
  *((_BYTE *)this + 8) = 0;
  *((_WORD *)this + 28) = 0;
  *((_BYTE *)this + 58) = 0;
  *((_WORD *)this + 3) = 4;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 2) = 4;
  *((_DWORD *)this + 16) = 0x40000;
  *((_BYTE *)this + 68) = 1;
  *((_WORD *)this + 35) = 4;
  *((_BYTE *)this + 72) = 2;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 10) = 8;
  *((_WORD *)this + 60) = 0;
  *((_BYTE *)this + 122) = 0;
  *((_DWORD *)this + 32) = 0x40000;
  *((_BYTE *)this + 132) = 1;
  *((_WORD *)this + 67) = 0;
  *((_BYTE *)this + 136) = 1;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_WORD *)this + 92) = 0;
  *((_BYTE *)this + 186) = 0;
  return result;
}

```

## disassembly

```asm
0x18000525c  mov     dword ptr [rcx], 40000h
0x180005262  xor     r8d, r8d
0x180005265  mov     byte ptr [rcx+4], 1
0x180005269  mov     rax, rcx
0x18000526c  mov     [rcx+8], r8b
0x180005270  mov     [rcx+38h], r8w
0x180005275  mov     [rcx+3Ah], r8b
0x180005279  lea     edx, [r8+4]
0x18000527d  mov     [rcx+6], dx
0x180005281  mov     [rcx+18h], r8
0x180005285  mov     [rcx+20h], r8
0x180005289  mov     [rcx+28h], r8
0x18000528d  mov     [rcx+30h], r8
0x180005291  mov     [rcx+10h], rdx
0x180005295  mov     dword ptr [rcx+40h], 40000h
0x18000529c  mov     byte ptr [rcx+44h], 1
0x1800052a0  mov     [rcx+46h], dx
0x1800052a4  mov     byte ptr [rcx+48h], 2
0x1800052a8  mov     [rcx+58h], r8
0x1800052ac  mov     [rcx+60h], r8
0x1800052b0  mov     [rcx+68h], r8
0x1800052b4  mov     [rcx+70h], r8
0x1800052b8  mov     qword ptr [rcx+50h], 8
0x1800052c0  mov     [rcx+78h], r8w
0x1800052c5  mov     [rcx+7Ah], r8b
0x1800052c9  mov     dword ptr [rcx+80h], 40000h
0x1800052d3  mov     byte ptr [rcx+84h], 1
0x1800052da  mov     [rcx+86h], r8w
0x1800052e2  mov     byte ptr [rcx+88h], 1
0x1800052e9  mov     [rcx+98h], r8
0x1800052f0  mov     [rcx+0A0h], r8
0x1800052f7  mov     [rcx+0A8h], r8
0x1800052fe  mov     [rcx+0B0h], r8
0x180005305  mov     [rcx+90h], r8
0x18000530c  mov     [rcx+0B8h], r8w
0x180005314  mov     [rcx+0BAh], r8b
0x18000531b  retn
```
