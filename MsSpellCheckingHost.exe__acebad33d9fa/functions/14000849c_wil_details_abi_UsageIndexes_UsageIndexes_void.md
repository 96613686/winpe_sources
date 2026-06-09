# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x14000849c`
- end: `0x14000855c`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `192`
- prototype: `wil::details_abi::UsageIndexes *__fastcall(wil::details_abi::UsageIndexes *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140008a34`
- `0x14000942c`
- `0x14000c560`
- `0x14000d0ac`

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
0x14000849c  mov     dword ptr [rcx], 40000h
0x1400084a2  xor     r8d, r8d
0x1400084a5  mov     byte ptr [rcx+4], 1
0x1400084a9  mov     rax, rcx
0x1400084ac  mov     [rcx+8], r8b
0x1400084b0  mov     [rcx+38h], r8w
0x1400084b5  mov     [rcx+3Ah], r8b
0x1400084b9  lea     edx, [r8+4]
0x1400084bd  mov     [rcx+6], dx
0x1400084c1  mov     [rcx+18h], r8
0x1400084c5  mov     [rcx+20h], r8
0x1400084c9  mov     [rcx+28h], r8
0x1400084cd  mov     [rcx+30h], r8
0x1400084d1  mov     [rcx+10h], rdx
0x1400084d5  mov     dword ptr [rcx+40h], 40000h
0x1400084dc  mov     byte ptr [rcx+44h], 1
0x1400084e0  mov     [rcx+46h], dx
0x1400084e4  mov     byte ptr [rcx+48h], 2
0x1400084e8  mov     [rcx+58h], r8
0x1400084ec  mov     [rcx+60h], r8
0x1400084f0  mov     [rcx+68h], r8
0x1400084f4  mov     [rcx+70h], r8
0x1400084f8  mov     qword ptr [rcx+50h], 8
0x140008500  mov     [rcx+78h], r8w
0x140008505  mov     [rcx+7Ah], r8b
0x140008509  mov     dword ptr [rcx+80h], 40000h
0x140008513  mov     byte ptr [rcx+84h], 1
0x14000851a  mov     [rcx+86h], r8w
0x140008522  mov     byte ptr [rcx+88h], 1
0x140008529  mov     [rcx+98h], r8
0x140008530  mov     [rcx+0A0h], r8
0x140008537  mov     [rcx+0A8h], r8
0x14000853e  mov     [rcx+0B0h], r8
0x140008545  mov     [rcx+90h], r8
0x14000854c  mov     [rcx+0B8h], r8w
0x140008554  mov     [rcx+0BAh], r8b
0x14000855b  retn
```
