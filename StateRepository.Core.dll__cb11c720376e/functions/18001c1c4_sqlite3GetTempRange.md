# sqlite3GetTempRange

- ea: `0x18001c1c4`
- end: `0x18001c217`
- name: `sqlite3GetTempRange`
- size: `83`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `19`
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
- `0x180058070`
- `0x18005c958`
- `0x18005e000`
- `0x18006f8a4`
- `0x180070350`
- `0x1800706dc`
- `0x180082bf0`
- `0x1800972dc`
- `0x180097878`
- `0x180097fa4`

## callees

- `0x18001c1c4`

## pseudocode

```c
__int64 __fastcall sqlite3GetTempRange(__int64 a1, int a2)
{
  char v3; // al
  unsigned __int8 v5; // al
  int v6; // ecx
  int v7; // ecx
  unsigned int v8; // r9d

  if ( a2 == 1 )
  {
    v3 = *(_BYTE *)(a1 + 31);
    if ( v3 )
    {
      v5 = v3 - 1;
      *(_BYTE *)(a1 + 31) = v5;
      return *(unsigned int *)(a1 + 4LL * v5 + 232);
    }
    else
    {
      return (unsigned int)++*(_DWORD *)(a1 + 60);
    }
  }
  else
  {
    v6 = *(_DWORD *)(a1 + 44);
    if ( a2 <= v6 )
    {
      v8 = *(_DWORD *)(a1 + 48);
      *(_DWORD *)(a1 + 44) = v6 - a2;
      *(_DWORD *)(a1 + 48) = v8 + a2;
    }
    else
    {
      v7 = *(_DWORD *)(a1 + 60);
      v8 = v7 + 1;
      *(_DWORD *)(a1 + 60) = a2 + v7;
    }
    return v8;
  }
}

```

## disassembly

```asm
0x18001c1c4  mov     r8, rcx
0x18001c1c7  cmp     edx, 1
0x18001c1ca  jnz     short loc_18001C1EA
0x18001c1cc  mov     al, [rcx+1Fh]
0x18001c1cf  test    al, al
0x18001c1d1  jnz     short loc_18001C1DA
0x18001c1d3  inc     dword ptr [rcx+3Ch]
0x18001c1d6  mov     eax, [rcx+3Ch]
0x18001c1d9  retn
0x18001c1da  dec     al
0x18001c1dc  movzx   eax, al
0x18001c1df  mov     [rcx+1Fh], al
0x18001c1e2  mov     eax, [rcx+rax*4+0E8h]
0x18001c1e9  retn
0x18001c1ea  mov     ecx, [rcx+2Ch]
0x18001c1ed  cmp     edx, ecx
0x18001c1ef  jle     short loc_18001C203
0x18001c1f1  mov     ecx, [r8+3Ch]
0x18001c1f5  lea     r9d, [rcx+1]
0x18001c1f9  add     ecx, edx
0x18001c1fb  mov     [r8+3Ch], ecx
0x18001c1ff  mov     eax, r9d
0x18001c202  retn
0x18001c203  mov     r9d, [r8+30h]
0x18001c207  sub     ecx, edx
0x18001c209  mov     [r8+2Ch], ecx
0x18001c20d  lea     eax, [r9+rdx]
0x18001c211  mov     [r8+30h], eax
0x18001c215  jmp     short loc_18001C1FF
```
