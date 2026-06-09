# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x140007af8`
- end: `0x140007bb8`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `192`
- prototype: `__int64 __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140007f3c`
- `0x140008710`
- `0x14000b440`
- `0x14000c13c`

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
0x140007af8  mov     dword ptr [rcx], 40000h
0x140007afe  xor     r8d, r8d
0x140007b01  mov     byte ptr [rcx+4], 1
0x140007b05  mov     rax, rcx
0x140007b08  mov     [rcx+8], r8b
0x140007b0c  mov     [rcx+38h], r8w
0x140007b11  mov     [rcx+3Ah], r8b
0x140007b15  lea     edx, [r8+4]
0x140007b19  mov     [rcx+6], dx
0x140007b1d  mov     [rcx+18h], r8
0x140007b21  mov     [rcx+20h], r8
0x140007b25  mov     [rcx+28h], r8
0x140007b29  mov     [rcx+30h], r8
0x140007b2d  mov     [rcx+10h], rdx
0x140007b31  mov     dword ptr [rcx+40h], 40000h
0x140007b38  mov     byte ptr [rcx+44h], 1
0x140007b3c  mov     [rcx+46h], dx
0x140007b40  mov     byte ptr [rcx+48h], 2
0x140007b44  mov     [rcx+58h], r8
0x140007b48  mov     [rcx+60h], r8
0x140007b4c  mov     [rcx+68h], r8
0x140007b50  mov     [rcx+70h], r8
0x140007b54  mov     qword ptr [rcx+50h], 8
0x140007b5c  mov     [rcx+78h], r8w
0x140007b61  mov     [rcx+7Ah], r8b
0x140007b65  mov     dword ptr [rcx+80h], 40000h
0x140007b6f  mov     byte ptr [rcx+84h], 1
0x140007b76  mov     [rcx+86h], r8w
0x140007b7e  mov     byte ptr [rcx+88h], 1
0x140007b85  mov     [rcx+98h], r8
0x140007b8c  mov     [rcx+0A0h], r8
0x140007b93  mov     [rcx+0A8h], r8
0x140007b9a  mov     [rcx+0B0h], r8
0x140007ba1  mov     [rcx+90h], r8
0x140007ba8  mov     [rcx+0B8h], r8w
0x140007bb0  mov     [rcx+0BAh], r8b
0x140007bb7  retn
```
