# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x140007dac`
- end: `0x140007e6c`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `192`
- prototype: `wil::details_abi::UsageIndexes *__fastcall(wil::details_abi::UsageIndexes *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140008090`
- `0x140008ae8`
- `0x14000a4b8`
- `0x14000aff4`

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
0x140007dac  mov     dword ptr [rcx], 40000h
0x140007db2  xor     r8d, r8d
0x140007db5  mov     byte ptr [rcx+4], 1
0x140007db9  mov     rax, rcx
0x140007dbc  mov     [rcx+8], r8b
0x140007dc0  mov     [rcx+38h], r8w
0x140007dc5  mov     [rcx+3Ah], r8b
0x140007dc9  lea     edx, [r8+4]
0x140007dcd  mov     [rcx+6], dx
0x140007dd1  mov     [rcx+18h], r8
0x140007dd5  mov     [rcx+20h], r8
0x140007dd9  mov     [rcx+28h], r8
0x140007ddd  mov     [rcx+30h], r8
0x140007de1  mov     [rcx+10h], rdx
0x140007de5  mov     dword ptr [rcx+40h], 40000h
0x140007dec  mov     byte ptr [rcx+44h], 1
0x140007df0  mov     [rcx+46h], dx
0x140007df4  mov     byte ptr [rcx+48h], 2
0x140007df8  mov     [rcx+58h], r8
0x140007dfc  mov     [rcx+60h], r8
0x140007e00  mov     [rcx+68h], r8
0x140007e04  mov     [rcx+70h], r8
0x140007e08  mov     qword ptr [rcx+50h], 8
0x140007e10  mov     [rcx+78h], r8w
0x140007e15  mov     [rcx+7Ah], r8b
0x140007e19  mov     dword ptr [rcx+80h], 40000h
0x140007e23  mov     byte ptr [rcx+84h], 1
0x140007e2a  mov     [rcx+86h], r8w
0x140007e32  mov     byte ptr [rcx+88h], 1
0x140007e39  mov     [rcx+98h], r8
0x140007e40  mov     [rcx+0A0h], r8
0x140007e47  mov     [rcx+0A8h], r8
0x140007e4e  mov     [rcx+0B0h], r8
0x140007e55  mov     [rcx+90h], r8
0x140007e5c  mov     [rcx+0B8h], r8w
0x140007e64  mov     [rcx+0BAh], r8b
0x140007e6b  retn
```
