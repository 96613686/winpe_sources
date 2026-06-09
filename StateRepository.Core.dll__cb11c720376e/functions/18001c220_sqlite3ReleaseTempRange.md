# sqlite3ReleaseTempRange

- ea: `0x18001c220`
- end: `0x18001c24d`
- name: `sqlite3ReleaseTempRange`
- size: `45`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x1800189c8`
- `0x18001a8dc`
- `0x18001c02c`
- `0x1800355c0`
- `0x180037194`
- `0x1800399a0`
- `0x18003b070`
- `0x180050420`
- `0x180056ed8`
- `0x18005e000`
- `0x18006f8a4`
- `0x1800706dc`
- `0x180082bf0`
- `0x1800972dc`
- `0x180097878`
- `0x180097fa4`

## callees

- `0x18001c220`

## pseudocode

```c
__int64 __fastcall sqlite3ReleaseTempRange(__int64 a1, int a2, int a3)
{
  __int64 result; // rax

  if ( a3 == 1 )
  {
    if ( a2 )
    {
      if ( *(_BYTE *)(a1 + 31) < 8u )
      {
        result = *(unsigned __int8 *)(a1 + 31);
        *(_DWORD *)(a1 + 4 * result + 232) = a2;
        ++*(_BYTE *)(a1 + 31);
      }
    }
  }
  else if ( a3 > *(_DWORD *)(a1 + 44) )
  {
    *(_DWORD *)(a1 + 44) = a3;
    *(_DWORD *)(a1 + 48) = a2;
  }
  return result;
}

```

## disassembly

```asm
0x18001c220  cmp     r8d, 1
0x18001c224  jnz     short loc_18001C23F
0x18001c226  test    edx, edx
0x18001c228  jz      short locret_18001C23E
0x18001c22a  cmp     byte ptr [rcx+1Fh], 8
0x18001c22e  jnb     short locret_18001C23E
0x18001c230  movzx   eax, byte ptr [rcx+1Fh]
0x18001c234  mov     [rcx+rax*4+0E8h], edx
0x18001c23b  inc     byte ptr [rcx+1Fh]
0x18001c23e  retn
0x18001c23f  cmp     r8d, [rcx+2Ch]
0x18001c243  jle     short locret_18001C23E
0x18001c245  mov     [rcx+2Ch], r8d
0x18001c249  mov     [rcx+30h], edx
0x18001c24c  retn
```
