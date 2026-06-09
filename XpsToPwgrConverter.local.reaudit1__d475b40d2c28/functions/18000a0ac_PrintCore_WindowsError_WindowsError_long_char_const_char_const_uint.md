# PrintCore::WindowsError::WindowsError(long,char const *,char const *,uint)

- ea: `0x18000a0ac`
- end: `0x18000a0d3`
- name: `??0WindowsError@PrintCore@@QEAA@JPEBD0I@Z`
- size: `39`
- prototype: `__int64 __fastcall(PrintCore::WindowsError *__hidden this, int, const char *, const char *, unsigned int)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180009e3c`
- `0x18000c514`
- `0x18000c7c4`
- `0x18000c89c`
- `0x18000d8f8`
- `0x18000d93c`
- `0x18000d9dc`

## pseudocode

```c
PrintCore::WindowsError *__fastcall PrintCore::WindowsError::WindowsError(
        PrintCore::WindowsError *this,
        int a2,
        const char *a3,
        const char *a4,
        unsigned int a5)
{
  PrintCore::WindowsError *result; // rax

  *(_OWORD *)((char *)this + 8) = 0;
  *(_QWORD *)this = &PrintCore::WindowsError::`vftable';
  *((_DWORD *)this + 12) = a5;
  result = this;
  *((_DWORD *)this + 6) = a2;
  *((_QWORD *)this + 4) = a3;
  *((_QWORD *)this + 5) = a4;
  return result;
}

```

## disassembly

```asm
0x18000a0ac  lea     rax, ??_7WindowsError@PrintCore@@6B@; const PrintCore::WindowsError::`vftable'
0x18000a0b3  xorps   xmm0, xmm0
0x18000a0b6  movups  xmmword ptr [rcx+8], xmm0
0x18000a0ba  mov     [rcx], rax
0x18000a0bd  mov     eax, [rsp+arg_20]
0x18000a0c1  mov     [rcx+30h], eax
0x18000a0c4  mov     rax, rcx
0x18000a0c7  mov     [rcx+18h], edx
0x18000a0ca  mov     [rcx+20h], r8
0x18000a0ce  mov     [rcx+28h], r9
0x18000a0d2  retn
```
