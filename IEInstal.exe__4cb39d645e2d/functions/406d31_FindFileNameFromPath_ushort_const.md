# FindFileNameFromPath(ushort const *)

- ea: `0x406d31`
- end: `0x406d8b`
- name: `?FindFileNameFromPath@@YGPAGPBG@Z`
- size: `90`
- prototype: `LPWSTR __thiscall(WCHAR *this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x407d14`
- `0x407eab`
- `0x408fe0`

## callees

- `0x406d31`

## import_xrefs

- `USER32!CharNextW` at `0x406d75`
- `USER32!CharNextW` at `0x406d75`

## pseudocode

```c
LPWSTR __thiscall FindFileNameFromPath(WCHAR *this)
{
  LPWSTR v1; // eax
  LPWSTR v2; // esi
  WCHAR v3; // cx
  WCHAR v4; // dx
  int v5; // ecx
  WCHAR v6; // cx

  v1 = this;
  v2 = this;
  if ( this )
  {
    v3 = *this;
    if ( v3 )
    {
      v4 = v3;
      do
      {
        if ( v4 == 92 || (v5 = *v1, v5 == 58) || (_WORD)v5 == 47 )
        {
          v6 = v1[1];
          if ( v6 && v6 != 92 && v6 != 47 )
            v2 = v1 + 1;
        }
        v1 = CharNextW(v1);
        v4 = *v1;
      }
      while ( *v1 );
    }
  }
  return v2;
}

```

## disassembly

```asm
0x406d31  mov     eax, ecx
0x406d33  push    esi
0x406d34  mov     esi, eax
0x406d36  test    eax, eax
0x406d38  jz      short loc_406D87
0x406d3a  movzx   ecx, word ptr [eax]
0x406d3d  test    cx, cx
0x406d40  jz      short loc_406D87
0x406d42  push    ebx
0x406d43  push    edi
0x406d44  push    5Ch ; '\'
0x406d46  pop     edi
0x406d47  push    2Fh ; '/'
0x406d49  mov     edx, ecx
0x406d4b  pop     ebx
0x406d4c  cmp     dx, di
0x406d4f  jz      short loc_406D5E
0x406d51  movzx   ecx, word ptr [eax]
0x406d54  cmp     ecx, 3Ah ; ':'
0x406d57  jz      short loc_406D5E
0x406d59  cmp     cx, bx
0x406d5c  jnz     short loc_406D74
0x406d5e  lea     edx, [eax+2]
0x406d61  movzx   ecx, word ptr [edx]
0x406d64  test    cx, cx
0x406d67  jz      short loc_406D74
0x406d69  cmp     cx, di
0x406d6c  jz      short loc_406D74
0x406d6e  cmp     cx, bx
0x406d71  cmovnz  esi, edx
0x406d74  push    eax; lpsz
0x406d75  call    ds:__imp__CharNextW@4; CharNextW(x)
0x406d7b  movzx   ecx, word ptr [eax]
0x406d7e  mov     edx, ecx
0x406d80  test    cx, cx
0x406d83  jnz     short loc_406D4C
0x406d85  pop     edi
0x406d86  pop     ebx
0x406d87  mov     eax, esi
0x406d89  pop     esi
0x406d8a  retn
```
