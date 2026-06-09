# StringIdDict_Remove(_MMDRV *)

- ea: `0x180001514`
- end: `0x18000155b`
- name: `?StringIdDict_Remove@@YAXPEAU_MMDRV@@@Z`
- size: `71`
- prototype: `void __fastcall(struct _MMDRV *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001564`

## callees

- `0x180001514`

## pseudocode

```c
void __fastcall StringIdDict_Remove(struct _MMDRV * near *a1)
{
  struct _MMDRV *v1; // r8
  struct _MMDRV *v2; // r8
  int i; // eax

  v1 = a1[2];
  if ( v1 )
    *((_QWORD *)v1 + 3) = a1[3];
  v2 = a1[3];
  if ( v2 )
  {
    *((_QWORD *)v2 + 2) = a1[2];
  }
  else
  {
    for ( i = 0; i < 127; ++i )
    {
      if ( a1 == (&StringIdDict)[i] )
      {
        (&StringIdDict)[i] = (struct _MMDRV * near *)a1[2];
        return;
      }
    }
  }
}

```

## disassembly

```asm
0x180001514  mov     r8, [rcx+10h]
0x180001518  test    r8, r8
0x18000151b  jz      short loc_180001525
0x18000151d  mov     rax, [rcx+18h]
0x180001521  mov     [r8+18h], rax
0x180001525  mov     r8, [rcx+18h]
0x180001529  test    r8, r8
0x18000152c  jz      short loc_180001537
0x18000152e  mov     rax, [rcx+10h]
0x180001532  mov     [r8+10h], rax
0x180001536  retn
0x180001537  xor     eax, eax
0x180001539  cmp     eax, 7Fh
0x18000153c  jge     short locret_18000155A
0x18000153e  movsxd  rdx, eax
0x180001541  lea     r8, ?StringIdDict@@3PAPEAU_MMDRV@@A; _MMDRV * near * StringIdDict
0x180001548  cmp     rcx, [r8+rdx*8]
0x18000154c  jz      short loc_180001552
0x18000154e  inc     eax
0x180001550  jmp     short loc_180001539
0x180001552  mov     rax, [rcx+10h]
0x180001556  mov     [r8+rdx*8], rax
0x18000155a  retn
```
