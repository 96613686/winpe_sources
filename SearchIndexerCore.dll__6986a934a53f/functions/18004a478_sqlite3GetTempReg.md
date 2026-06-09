# sqlite3GetTempReg

- ea: `0x18004a478`
- end: `0x18004a496`
- name: `sqlite3GetTempReg`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `31`
- callee_count: `1`
- tags: ``

## callers

- `0x180005650`
- `0x180016ef0`
- `0x18001cb6c`
- `0x18004a34c`
- `0x18004a438`
- `0x18004b7cc`
- `0x1800504a8`
- `0x1800544ac`
- `0x18005a538`
- `0x180062494`
- `0x180064df4`
- `0x180067500`
- `0x180068368`
- `0x18006cc88`
- `0x1800711f4`
- `0x180072020`
- `0x18007406c`
- `0x1800751b0`
- `0x18007ee44`
- `0x18007f9a0`
- `0x18007fcec`
- `0x180081778`
- `0x18008f958`
- `0x180090b7c`
- `0x180093bb0`
- `0x1800a514c`
- `0x1800a55d4`
- `0x1800a5744`
- `0x1800a5a50`
- `0x1800a5eb8`
- `0x1800a6344`

## callees

- `0x18004a478`

## pseudocode

```c
__int64 __fastcall sqlite3GetTempReg(__int64 a1)
{
  char v1; // al
  unsigned __int8 v2; // al

  v1 = *(_BYTE *)(a1 + 31);
  if ( v1 )
  {
    v2 = v1 - 1;
    *(_BYTE *)(a1 + 31) = v2;
    return *(unsigned int *)(a1 + 4LL * v2 + 232);
  }
  else
  {
    return (unsigned int)++*(_DWORD *)(a1 + 56);
  }
}

```

## disassembly

```asm
0x18004a478  mov     al, [rcx+1Fh]
0x18004a47b  test    al, al
0x18004a47d  jz      short loc_18004A48F
0x18004a47f  dec     al
0x18004a481  movzx   eax, al
0x18004a484  mov     [rcx+1Fh], al
0x18004a487  mov     eax, [rcx+rax*4+0E8h]
0x18004a48e  retn
0x18004a48f  inc     dword ptr [rcx+38h]
0x18004a492  mov     eax, [rcx+38h]
0x18004a495  retn
```
