# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x1800029c0`
- end: `0x180002a80`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `192`
- prototype: `__int64 __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002d94`
- `0x1800035c0`
- `0x180005d60`
- `0x180006814`

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
0x1800029c0  mov     dword ptr [rcx], 40000h
0x1800029c6  xor     r8d, r8d
0x1800029c9  mov     byte ptr [rcx+4], 1
0x1800029cd  mov     rax, rcx
0x1800029d0  mov     [rcx+8], r8b
0x1800029d4  mov     [rcx+38h], r8w
0x1800029d9  mov     [rcx+3Ah], r8b
0x1800029dd  lea     edx, [r8+4]
0x1800029e1  mov     [rcx+6], dx
0x1800029e5  mov     [rcx+18h], r8
0x1800029e9  mov     [rcx+20h], r8
0x1800029ed  mov     [rcx+28h], r8
0x1800029f1  mov     [rcx+30h], r8
0x1800029f5  mov     [rcx+10h], rdx
0x1800029f9  mov     dword ptr [rcx+40h], 40000h
0x180002a00  mov     byte ptr [rcx+44h], 1
0x180002a04  mov     [rcx+46h], dx
0x180002a08  mov     byte ptr [rcx+48h], 2
0x180002a0c  mov     [rcx+58h], r8
0x180002a10  mov     [rcx+60h], r8
0x180002a14  mov     [rcx+68h], r8
0x180002a18  mov     [rcx+70h], r8
0x180002a1c  mov     qword ptr [rcx+50h], 8
0x180002a24  mov     [rcx+78h], r8w
0x180002a29  mov     [rcx+7Ah], r8b
0x180002a2d  mov     dword ptr [rcx+80h], 40000h
0x180002a37  mov     byte ptr [rcx+84h], 1
0x180002a3e  mov     [rcx+86h], r8w
0x180002a46  mov     byte ptr [rcx+88h], 1
0x180002a4d  mov     [rcx+98h], r8
0x180002a54  mov     [rcx+0A0h], r8
0x180002a5b  mov     [rcx+0A8h], r8
0x180002a62  mov     [rcx+0B0h], r8
0x180002a69  mov     [rcx+90h], r8
0x180002a70  mov     [rcx+0B8h], r8w
0x180002a78  mov     [rcx+0BAh], r8b
0x180002a7f  retn
```
