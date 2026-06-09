# BaseSrvRemoveDOSRecord

- ea: `0x18000c128`
- end: `0x18000c162`
- name: `BaseSrvRemoveDOSRecord`
- size: `58`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b620`
- `0x18000c434`

## callees

- `0x18000c128`

## pseudocode

```c
void __fastcall BaseSrvRemoveDOSRecord(__int64 a1, _QWORD *a2)
{
  _QWORD **v2; // r8
  _QWORD *i; // rax

  if ( a1 )
  {
    v2 = *(_QWORD ***)(a1 + 72);
    if ( v2 == a2 )
    {
      *(_QWORD *)(a1 + 72) = *a2;
    }
    else if ( v2 )
    {
      for ( i = *v2; i; i = (_QWORD *)*i )
      {
        if ( i == a2 )
        {
          *v2 = (_QWORD *)*a2;
          return;
        }
        v2 = (_QWORD **)i;
      }
    }
  }
}

```

## disassembly

```asm
0x18000c128  test    rcx, rcx
0x18000c12b  jz      short locret_18000C161
0x18000c12d  mov     r8, [rcx+48h]
0x18000c131  cmp     r8, rdx
0x18000c134  jnz     short loc_18000C13F
0x18000c136  mov     rax, [rdx]
0x18000c139  mov     [rcx+48h], rax
0x18000c13d  retn
0x18000c13f  test    r8, r8
0x18000c142  jz      short locret_18000C161
0x18000c144  mov     rax, [r8]
0x18000c147  jmp     short loc_18000C154
0x18000c149  cmp     rax, rdx
0x18000c14c  jz      short loc_18000C15B
0x18000c14e  mov     r8, rax
0x18000c151  mov     rax, [rax]
0x18000c154  test    rax, rax
0x18000c157  jnz     short loc_18000C149
0x18000c159  retn
0x18000c15b  mov     rax, [rdx]
0x18000c15e  mov     [r8], rax
0x18000c161  retn
```
