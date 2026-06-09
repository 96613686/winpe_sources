# sub_62FC7C

- ea: `0x62fc7c`
- end: `0x62fc87`
- name: `sub_62FC7C`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall sub_62FC7C(__int64 a1, __int64 a2, __int16 _DX, _BYTE *a4)
{
  __int64 v4; // rax

  *(_DWORD *)(v4 + 6) += v4;
  __asm { insd }
  *a4 = __ROL1__(*a4, 1);
  *a4 += v4;
  __asm { iret }
}

```

## disassembly

```asm
0x62fc7c  add     [rax+6], eax
0x62fc7f  insd
0x62fc80  rol     byte ptr [rcx], 1
0x62fc82  add     [rcx], al
0x62fc84  or      al, [rax]
0x62fc86  iret
```
