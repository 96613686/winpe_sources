# CRegSetting::CRegSetting(void)

- ea: `0x140004770`
- end: `0x1400047b6`
- name: `??0CRegSetting@@QEAA@XZ`
- size: `70`
- prototype: `CRegSetting *__fastcall(CRegSetting *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
CRegSetting *__fastcall CRegSetting::CRegSetting(CRegSetting *this)
{
  _WORD *v1; // rdx
  CRegSetting *result; // rax
  _WORD *v3; // rcx

  v1 = (_WORD *)((char *)this + 48);
  *(_WORD *)this = 0;
  *((_DWORD *)this + 1) = 0;
  *((_QWORD *)this + 1) = -1;
  *((_QWORD *)this + 2) = -1;
  *((_QWORD *)this + 3) = -1;
  result = this;
  *((_QWORD *)this + 4) = (char *)this + 48;
  *((_QWORD *)this + 5) = (char *)this + 48;
  v3 = (_WORD *)((char *)this + 80);
  *v1 = 0;
  *((_QWORD *)result + 8) = v3;
  *((_QWORD *)result + 9) = v3;
  *v3 = 0;
  *((_QWORD *)result + 12) = 0;
  return result;
}

```

## disassembly

```asm
0x140004770  xor     r9d, r9d
0x140004773  lea     rdx, [rcx+30h]
0x140004777  mov     r8, rcx
0x14000477a  mov     [rcx], r9w
0x14000477e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004782  mov     [rcx+4], r9d
0x140004786  mov     [rcx+8], rax
0x14000478a  mov     [rcx+10h], rax
0x14000478e  mov     [rcx+18h], rax
0x140004792  mov     rax, r8
0x140004795  mov     [rcx+20h], rdx
0x140004799  mov     [rcx+28h], rdx
0x14000479d  add     rcx, 50h ; 'P'
0x1400047a1  mov     [rdx], r9w
0x1400047a5  mov     [r8+40h], rcx
0x1400047a9  mov     [r8+48h], rcx
0x1400047ad  mov     [rcx], r9w
0x1400047b1  mov     [r8+60h], r9
0x1400047b5  retn
```
