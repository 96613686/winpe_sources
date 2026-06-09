# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x180003ec4`
- end: `0x180003f84`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `192`
- prototype: `wil::details_abi::UsageIndexes *__fastcall(wil::details_abi::UsageIndexes *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180004308`
- `0x180004d38`
- `0x180007560`
- `0x18000807c`

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
0x180003ec4  mov     dword ptr [rcx], 40000h
0x180003eca  xor     r8d, r8d
0x180003ecd  mov     byte ptr [rcx+4], 1
0x180003ed1  mov     rax, rcx
0x180003ed4  mov     [rcx+8], r8b
0x180003ed8  mov     [rcx+38h], r8w
0x180003edd  mov     [rcx+3Ah], r8b
0x180003ee1  lea     edx, [r8+4]
0x180003ee5  mov     [rcx+6], dx
0x180003ee9  mov     [rcx+18h], r8
0x180003eed  mov     [rcx+20h], r8
0x180003ef1  mov     [rcx+28h], r8
0x180003ef5  mov     [rcx+30h], r8
0x180003ef9  mov     [rcx+10h], rdx
0x180003efd  mov     dword ptr [rcx+40h], 40000h
0x180003f04  mov     byte ptr [rcx+44h], 1
0x180003f08  mov     [rcx+46h], dx
0x180003f0c  mov     byte ptr [rcx+48h], 2
0x180003f10  mov     [rcx+58h], r8
0x180003f14  mov     [rcx+60h], r8
0x180003f18  mov     [rcx+68h], r8
0x180003f1c  mov     [rcx+70h], r8
0x180003f20  mov     qword ptr [rcx+50h], 8
0x180003f28  mov     [rcx+78h], r8w
0x180003f2d  mov     [rcx+7Ah], r8b
0x180003f31  mov     dword ptr [rcx+80h], 40000h
0x180003f3b  mov     byte ptr [rcx+84h], 1
0x180003f42  mov     [rcx+86h], r8w
0x180003f4a  mov     byte ptr [rcx+88h], 1
0x180003f51  mov     [rcx+98h], r8
0x180003f58  mov     [rcx+0A0h], r8
0x180003f5f  mov     [rcx+0A8h], r8
0x180003f66  mov     [rcx+0B0h], r8
0x180003f6d  mov     [rcx+90h], r8
0x180003f74  mov     [rcx+0B8h], r8w
0x180003f7c  mov     [rcx+0BAh], r8b
0x180003f83  retn
```
