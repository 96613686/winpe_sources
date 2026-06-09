# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x1800057d0`
- end: `0x180005890`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `192`
- prototype: `wil::details_abi::UsageIndexes *__fastcall(wil::details_abi::UsageIndexes *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180005a7c`
- `0x180006460`
- `0x1800087f0`
- `0x180009300`

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
0x1800057d0  mov     dword ptr [rcx], 40000h
0x1800057d6  xor     r8d, r8d
0x1800057d9  mov     byte ptr [rcx+4], 1
0x1800057dd  mov     rax, rcx
0x1800057e0  mov     [rcx+8], r8b
0x1800057e4  mov     [rcx+38h], r8w
0x1800057e9  mov     [rcx+3Ah], r8b
0x1800057ed  lea     edx, [r8+4]
0x1800057f1  mov     [rcx+6], dx
0x1800057f5  mov     [rcx+18h], r8
0x1800057f9  mov     [rcx+20h], r8
0x1800057fd  mov     [rcx+28h], r8
0x180005801  mov     [rcx+30h], r8
0x180005805  mov     [rcx+10h], rdx
0x180005809  mov     dword ptr [rcx+40h], 40000h
0x180005810  mov     byte ptr [rcx+44h], 1
0x180005814  mov     [rcx+46h], dx
0x180005818  mov     byte ptr [rcx+48h], 2
0x18000581c  mov     [rcx+58h], r8
0x180005820  mov     [rcx+60h], r8
0x180005824  mov     [rcx+68h], r8
0x180005828  mov     [rcx+70h], r8
0x18000582c  mov     qword ptr [rcx+50h], 8
0x180005834  mov     [rcx+78h], r8w
0x180005839  mov     [rcx+7Ah], r8b
0x18000583d  mov     dword ptr [rcx+80h], 40000h
0x180005847  mov     byte ptr [rcx+84h], 1
0x18000584e  mov     [rcx+86h], r8w
0x180005856  mov     byte ptr [rcx+88h], 1
0x18000585d  mov     [rcx+98h], r8
0x180005864  mov     [rcx+0A0h], r8
0x18000586b  mov     [rcx+0A8h], r8
0x180005872  mov     [rcx+0B0h], r8
0x180005879  mov     [rcx+90h], r8
0x180005880  mov     [rcx+0B8h], r8w
0x180005888  mov     [rcx+0BAh], r8b
0x18000588f  retn
```
