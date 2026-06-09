# sqlite3ReleaseTempReg

- ea: `0x18003ff00`
- end: `0x18003ff19`
- name: `sqlite3ReleaseTempReg`
- size: `25`
- prototype: ``
- caller_count: `34`
- callee_count: `1`
- tags: ``

## callers

- `0x18000eb78`
- `0x1800189c8`
- `0x1800355c0`
- `0x180037194`
- `0x1800399a0`
- `0x18003ac5c`
- `0x18003b070`
- `0x18003e5c0`
- `0x1800402cc`
- `0x180043968`
- `0x180058070`
- `0x18005c310`
- `0x18005d030`
- `0x18005e000`
- `0x18005f420`
- `0x180069e7c`
- `0x18006c53c`
- `0x18006dca4`
- `0x18006e4c8`
- `0x18006f8a4`
- `0x180070350`
- `0x1800706dc`
- `0x180072440`
- `0x180080628`
- `0x180082bf0`
- `0x1800866d4`
- `0x180087e6c`
- `0x1800972dc`
- `0x180097708`
- `0x180097878`
- `0x180097c40`
- `0x180097fa4`
- `0x180098540`
- `0x180098bfc`

## callees

- `0x18003ff00`

## pseudocode

```c
__int64 __fastcall sqlite3ReleaseTempReg(__int64 a1, int a2)
{
  __int64 result; // rax

  if ( a2 )
  {
    if ( *(_BYTE *)(a1 + 31) < 8u )
    {
      result = *(unsigned __int8 *)(a1 + 31);
      *(_DWORD *)(a1 + 4 * result + 232) = a2;
      ++*(_BYTE *)(a1 + 31);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003ff00  test    edx, edx
0x18003ff02  jz      short locret_18003FF18
0x18003ff04  cmp     byte ptr [rcx+1Fh], 8
0x18003ff08  jnb     short locret_18003FF18
0x18003ff0a  movzx   eax, byte ptr [rcx+1Fh]
0x18003ff0e  mov     [rcx+rax*4+0E8h], edx
0x18003ff15  inc     byte ptr [rcx+1Fh]
0x18003ff18  retn
```
