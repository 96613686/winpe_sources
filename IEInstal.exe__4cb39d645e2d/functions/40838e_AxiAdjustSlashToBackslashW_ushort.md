# AxiAdjustSlashToBackslashW(ushort *)

- ea: `0x40838e`
- end: `0x4083b6`
- name: `?AxiAdjustSlashToBackslashW@@YGXPAG@Z`
- size: `40`
- prototype: `void __thiscall(__int16 *this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x403d84`
- `0x404214`
- `0x4044ae`
- `0x407d14`

## callees

- `0x40838e`

## pseudocode

```c
void __thiscall AxiAdjustSlashToBackslashW(__int16 *this)
{
  __int16 v1; // dx

  if ( this && *this )
  {
    v1 = *this;
    do
    {
      if ( v1 == 47 )
        *this = 92;
      v1 = *++this;
    }
    while ( *this );
  }
}

```

## disassembly

```asm
0x40838e  test    ecx, ecx
0x408390  jz      short locret_4083B5
0x408392  movzx   eax, word ptr [ecx]
0x408395  test    ax, ax
0x408398  jz      short locret_4083B5
0x40839a  mov     edx, eax
0x40839c  cmp     dx, 2Fh ; '/'
0x4083a0  jnz     short loc_4083A8
0x4083a2  push    5Ch ; '\'
0x4083a4  pop     eax
0x4083a5  mov     [ecx], ax
0x4083a8  add     ecx, 2
0x4083ab  movzx   eax, word ptr [ecx]
0x4083ae  mov     edx, eax
0x4083b0  test    ax, ax
0x4083b3  jnz     short loc_40839C
0x4083b5  retn
```
