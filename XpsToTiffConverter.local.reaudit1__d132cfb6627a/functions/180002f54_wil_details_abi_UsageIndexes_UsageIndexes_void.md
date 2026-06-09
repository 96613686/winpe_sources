# wil::details_abi::UsageIndexes::UsageIndexes(void)

- ea: `0x180002f54`
- end: `0x180003014`
- name: `??0UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `192`
- prototype: `__int64 __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180003410`
- `0x180003e5c`
- `0x180006220`
- `0x180006d30`

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
0x180002f54  mov     dword ptr [rcx], 40000h
0x180002f5a  xor     r8d, r8d
0x180002f5d  mov     byte ptr [rcx+4], 1
0x180002f61  mov     rax, rcx
0x180002f64  mov     [rcx+8], r8b
0x180002f68  mov     [rcx+38h], r8w
0x180002f6d  mov     [rcx+3Ah], r8b
0x180002f71  lea     edx, [r8+4]
0x180002f75  mov     [rcx+6], dx
0x180002f79  mov     [rcx+18h], r8
0x180002f7d  mov     [rcx+20h], r8
0x180002f81  mov     [rcx+28h], r8
0x180002f85  mov     [rcx+30h], r8
0x180002f89  mov     [rcx+10h], rdx
0x180002f8d  mov     dword ptr [rcx+40h], 40000h
0x180002f94  mov     byte ptr [rcx+44h], 1
0x180002f98  mov     [rcx+46h], dx
0x180002f9c  mov     byte ptr [rcx+48h], 2
0x180002fa0  mov     [rcx+58h], r8
0x180002fa4  mov     [rcx+60h], r8
0x180002fa8  mov     [rcx+68h], r8
0x180002fac  mov     [rcx+70h], r8
0x180002fb0  mov     qword ptr [rcx+50h], 8
0x180002fb8  mov     [rcx+78h], r8w
0x180002fbd  mov     [rcx+7Ah], r8b
0x180002fc1  mov     dword ptr [rcx+80h], 40000h
0x180002fcb  mov     byte ptr [rcx+84h], 1
0x180002fd2  mov     [rcx+86h], r8w
0x180002fda  mov     byte ptr [rcx+88h], 1
0x180002fe1  mov     [rcx+98h], r8
0x180002fe8  mov     [rcx+0A0h], r8
0x180002fef  mov     [rcx+0A8h], r8
0x180002ff6  mov     [rcx+0B0h], r8
0x180002ffd  mov     [rcx+90h], r8
0x180003004  mov     [rcx+0B8h], r8w
0x18000300c  mov     [rcx+0BAh], r8b
0x180003013  retn
```
