# CRegistry::SetDefaultValues(void)

- ea: `0x140013b00`
- end: `0x140013b31`
- name: `?SetDefaultValues@CRegistry@@AEAAXXZ`
- size: `49`
- prototype: `void __fastcall(CRegistry *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140011be0`
- `0x140012040`
- `0x1400134b0`

## callees

- `0x140010bc0`

## pseudocode

```c
void __fastcall CRegistry::SetDefaultValues(CRegistry *this)
{
  *((_QWORD *)this + 70) = 260;
  *((_WORD *)this + 19) = 0;
  *((_QWORD *)this + 71) = 0;
  *((_QWORD *)this + 72) = 0;
  *((_DWORD *)this + 146) = 0;
  *((_DWORD *)this + 8) = 0;
  CHString::Empty((CRegistry *)((char *)this + 24));
}

```

## disassembly

```asm
0x140013b00  xor     edx, edx
0x140013b02  mov     qword ptr [rcx+230h], 104h
0x140013b0d  mov     [rcx+26h], dx
0x140013b11  mov     [rcx+238h], rdx
0x140013b18  mov     [rcx+240h], rdx
0x140013b1f  mov     [rcx+248h], edx
0x140013b25  mov     [rcx+20h], edx
0x140013b28  add     rcx, 18h; this
0x140013b2c  jmp     ?Empty@CHString@@QEAAXXZ; CHString::Empty(void)
```
