# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x140005a08`
- end: `0x140005ac8`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `192`
- prototype: `wil::details_abi::UsageIndexes *__fastcall(wil::details_abi::UsageIndexes *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140005be8`
- `0x140006064`
- `0x140006f14`
- `0x140007910`

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
0x140005a08  mov     dword ptr [rcx], 40000h
0x140005a0e  xor     r8d, r8d
0x140005a11  mov     byte ptr [rcx+4], 1
0x140005a15  mov     rax, rcx
0x140005a18  mov     [rcx+8], r8b
0x140005a1c  mov     [rcx+38h], r8w
0x140005a21  mov     [rcx+3Ah], r8b
0x140005a25  lea     edx, [r8+4]
0x140005a29  mov     [rcx+6], dx
0x140005a2d  mov     [rcx+18h], r8
0x140005a31  mov     [rcx+20h], r8
0x140005a35  mov     [rcx+28h], r8
0x140005a39  mov     [rcx+30h], r8
0x140005a3d  mov     [rcx+10h], rdx
0x140005a41  mov     dword ptr [rcx+40h], 40000h
0x140005a48  mov     byte ptr [rcx+44h], 1
0x140005a4c  mov     [rcx+46h], dx
0x140005a50  mov     byte ptr [rcx+48h], 2
0x140005a54  mov     [rcx+58h], r8
0x140005a58  mov     [rcx+60h], r8
0x140005a5c  mov     [rcx+68h], r8
0x140005a60  mov     [rcx+70h], r8
0x140005a64  mov     qword ptr [rcx+50h], 8
0x140005a6c  mov     [rcx+78h], r8w
0x140005a71  mov     [rcx+7Ah], r8b
0x140005a75  mov     dword ptr [rcx+80h], 40000h
0x140005a7f  mov     byte ptr [rcx+84h], 1
0x140005a86  mov     [rcx+86h], r8w
0x140005a8e  mov     byte ptr [rcx+88h], 1
0x140005a95  mov     [rcx+98h], r8
0x140005a9c  mov     [rcx+0A0h], r8
0x140005aa3  mov     [rcx+0A8h], r8
0x140005aaa  mov     [rcx+0B0h], r8
0x140005ab1  mov     [rcx+90h], r8
0x140005ab8  mov     [rcx+0B8h], r8w
0x140005ac0  mov     [rcx+0BAh], r8b
0x140005ac7  retn
```
