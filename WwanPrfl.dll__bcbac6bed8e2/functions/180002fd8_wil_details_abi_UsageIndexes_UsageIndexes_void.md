# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x180002fd8`
- end: `0x180003098`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `192`
- prototype: `wil::details_abi::UsageIndexes *__fastcall(wil::details_abi::UsageIndexes *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180003484`
- `0x180003eac`
- `0x180006a00`
- `0x180007510`

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
0x180002fd8  mov     dword ptr [rcx], 40000h
0x180002fde  xor     r8d, r8d
0x180002fe1  mov     byte ptr [rcx+4], 1
0x180002fe5  mov     rax, rcx
0x180002fe8  mov     [rcx+8], r8b
0x180002fec  mov     [rcx+38h], r8w
0x180002ff1  mov     [rcx+3Ah], r8b
0x180002ff5  lea     edx, [r8+4]
0x180002ff9  mov     [rcx+6], dx
0x180002ffd  mov     [rcx+18h], r8
0x180003001  mov     [rcx+20h], r8
0x180003005  mov     [rcx+28h], r8
0x180003009  mov     [rcx+30h], r8
0x18000300d  mov     [rcx+10h], rdx
0x180003011  mov     dword ptr [rcx+40h], 40000h
0x180003018  mov     byte ptr [rcx+44h], 1
0x18000301c  mov     [rcx+46h], dx
0x180003020  mov     byte ptr [rcx+48h], 2
0x180003024  mov     [rcx+58h], r8
0x180003028  mov     [rcx+60h], r8
0x18000302c  mov     [rcx+68h], r8
0x180003030  mov     [rcx+70h], r8
0x180003034  mov     qword ptr [rcx+50h], 8
0x18000303c  mov     [rcx+78h], r8w
0x180003041  mov     [rcx+7Ah], r8b
0x180003045  mov     dword ptr [rcx+80h], 40000h
0x18000304f  mov     byte ptr [rcx+84h], 1
0x180003056  mov     [rcx+86h], r8w
0x18000305e  mov     byte ptr [rcx+88h], 1
0x180003065  mov     [rcx+98h], r8
0x18000306c  mov     [rcx+0A0h], r8
0x180003073  mov     [rcx+0A8h], r8
0x18000307a  mov     [rcx+0B0h], r8
0x180003081  mov     [rcx+90h], r8
0x180003088  mov     [rcx+0B8h], r8w
0x180003090  mov     [rcx+0BAh], r8b
0x180003097  retn
```
