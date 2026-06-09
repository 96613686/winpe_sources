# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x180003320`
- end: `0x1800033e0`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `192`
- prototype: `wil::details_abi::UsageIndexes *__fastcall(wil::details_abi::UsageIndexes *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800036f4`
- `0x180003f94`
- `0x180006770`
- `0x180007274`

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
0x180003320  mov     dword ptr [rcx], 40000h
0x180003326  xor     r8d, r8d
0x180003329  mov     byte ptr [rcx+4], 1
0x18000332d  mov     rax, rcx
0x180003330  mov     [rcx+8], r8b
0x180003334  mov     [rcx+38h], r8w
0x180003339  mov     [rcx+3Ah], r8b
0x18000333d  lea     edx, [r8+4]
0x180003341  mov     [rcx+6], dx
0x180003345  mov     [rcx+18h], r8
0x180003349  mov     [rcx+20h], r8
0x18000334d  mov     [rcx+28h], r8
0x180003351  mov     [rcx+30h], r8
0x180003355  mov     [rcx+10h], rdx
0x180003359  mov     dword ptr [rcx+40h], 40000h
0x180003360  mov     byte ptr [rcx+44h], 1
0x180003364  mov     [rcx+46h], dx
0x180003368  mov     byte ptr [rcx+48h], 2
0x18000336c  mov     [rcx+58h], r8
0x180003370  mov     [rcx+60h], r8
0x180003374  mov     [rcx+68h], r8
0x180003378  mov     [rcx+70h], r8
0x18000337c  mov     qword ptr [rcx+50h], 8
0x180003384  mov     [rcx+78h], r8w
0x180003389  mov     [rcx+7Ah], r8b
0x18000338d  mov     dword ptr [rcx+80h], 40000h
0x180003397  mov     byte ptr [rcx+84h], 1
0x18000339e  mov     [rcx+86h], r8w
0x1800033a6  mov     byte ptr [rcx+88h], 1
0x1800033ad  mov     [rcx+98h], r8
0x1800033b4  mov     [rcx+0A0h], r8
0x1800033bb  mov     [rcx+0A8h], r8
0x1800033c2  mov     [rcx+0B0h], r8
0x1800033c9  mov     [rcx+90h], r8
0x1800033d0  mov     [rcx+0B8h], r8w
0x1800033d8  mov     [rcx+0BAh], r8b
0x1800033df  retn
```
