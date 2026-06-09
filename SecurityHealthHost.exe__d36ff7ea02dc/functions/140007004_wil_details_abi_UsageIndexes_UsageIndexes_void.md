# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x140007004`
- end: `0x1400070c4`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `192`
- prototype: `wil::details_abi::UsageIndexes *__fastcall(wil::details_abi::UsageIndexes *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1400072b0`
- `0x140007cbc`
- `0x140009804`
- `0x14000a318`

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
0x140007004  mov     dword ptr [rcx], 40000h
0x14000700a  xor     r8d, r8d
0x14000700d  mov     byte ptr [rcx+4], 1
0x140007011  mov     rax, rcx
0x140007014  mov     [rcx+8], r8b
0x140007018  mov     [rcx+38h], r8w
0x14000701d  mov     [rcx+3Ah], r8b
0x140007021  lea     edx, [r8+4]
0x140007025  mov     [rcx+6], dx
0x140007029  mov     [rcx+18h], r8
0x14000702d  mov     [rcx+20h], r8
0x140007031  mov     [rcx+28h], r8
0x140007035  mov     [rcx+30h], r8
0x140007039  mov     [rcx+10h], rdx
0x14000703d  mov     dword ptr [rcx+40h], 40000h
0x140007044  mov     byte ptr [rcx+44h], 1
0x140007048  mov     [rcx+46h], dx
0x14000704c  mov     byte ptr [rcx+48h], 2
0x140007050  mov     [rcx+58h], r8
0x140007054  mov     [rcx+60h], r8
0x140007058  mov     [rcx+68h], r8
0x14000705c  mov     [rcx+70h], r8
0x140007060  mov     qword ptr [rcx+50h], 8
0x140007068  mov     [rcx+78h], r8w
0x14000706d  mov     [rcx+7Ah], r8b
0x140007071  mov     dword ptr [rcx+80h], 40000h
0x14000707b  mov     byte ptr [rcx+84h], 1
0x140007082  mov     [rcx+86h], r8w
0x14000708a  mov     byte ptr [rcx+88h], 1
0x140007091  mov     [rcx+98h], r8
0x140007098  mov     [rcx+0A0h], r8
0x14000709f  mov     [rcx+0A8h], r8
0x1400070a6  mov     [rcx+0B0h], r8
0x1400070ad  mov     [rcx+90h], r8
0x1400070b4  mov     [rcx+0B8h], r8w
0x1400070bc  mov     [rcx+0BAh], r8b
0x1400070c3  retn
```
