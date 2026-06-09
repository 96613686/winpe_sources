# sqlite3GetTempRange

- ea: `0x18004a438`
- end: `0x18004a472`
- name: `sqlite3GetTempRange`
- size: `58`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x180005650`
- `0x180016ef0`
- `0x180017938`
- `0x180019470`
- `0x180049d94`
- `0x18004b7cc`
- `0x1800504a8`
- `0x18005a538`
- `0x180060ddc`
- `0x180062494`
- `0x180067500`
- `0x18006cc88`
- `0x18007ee44`
- `0x18007f9a0`
- `0x18007fcec`
- `0x180093bb0`
- `0x1800a514c`
- `0x1800a5a50`

## callees

- `0x18004a438`
- `0x18004a478`

## pseudocode

```c
__int64 __fastcall sqlite3GetTempRange(_DWORD *a1, int a2)
{
  int v3; // ecx
  int v4; // ecx
  unsigned int v5; // r9d

  if ( a2 == 1 )
    return sqlite3GetTempReg((__int64)a1);
  v3 = a1[10];
  if ( a2 <= v3 )
  {
    v5 = a1[11];
    a1[10] = v3 - a2;
    a1[11] = v5 + a2;
  }
  else
  {
    v4 = a1[14];
    v5 = v4 + 1;
    a1[14] = a2 + v4;
  }
  return v5;
}

```

## disassembly

```asm
0x18004a438  mov     r8, rcx
0x18004a43b  cmp     edx, 1
0x18004a43e  jz      short loc_18004A46D
0x18004a440  mov     ecx, [rcx+28h]
0x18004a443  cmp     edx, ecx
0x18004a445  jle     short loc_18004A459
0x18004a447  mov     ecx, [r8+38h]
0x18004a44b  lea     r9d, [rcx+1]
0x18004a44f  add     ecx, edx
0x18004a451  mov     [r8+38h], ecx
0x18004a455  mov     eax, r9d
0x18004a458  retn
0x18004a459  mov     r9d, [r8+2Ch]
0x18004a45d  sub     ecx, edx
0x18004a45f  mov     [r8+28h], ecx
0x18004a463  lea     eax, [r9+rdx]
0x18004a467  mov     [r8+2Ch], eax
0x18004a46b  jmp     short loc_18004A455
0x18004a46d  jmp     sqlite3GetTempReg
```
