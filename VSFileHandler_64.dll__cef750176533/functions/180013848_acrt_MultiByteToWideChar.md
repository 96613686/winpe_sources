# __acrt_MultiByteToWideChar

- ea: `0x180013848`
- end: `0x1800138a2`
- name: `__acrt_MultiByteToWideChar`
- size: `90`
- prototype: `int __fastcall(UINT, char, const CHAR *, int, WCHAR *, int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180010690`
- `0x180012144`
- `0x180016c18`
- `0x180017a54`

## callees

- `0x180013848`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x18001389b`

## pseudocode

```c
int __fastcall _acrt_MultiByteToWideChar(UINT a1, char a2, const CHAR *a3, int a4, WCHAR *a5, int a6)
{
  int v6; // r10d

  if ( a1 > 0xC435 )
  {
    if ( a1 != 54936 )
    {
      if ( a1 <= 0xDEA9 )
        return MultiByteToWideChar(a1, a2, a3, a4, a5, a6);
      if ( a1 <= 0xDEB3 || a1 == 65000 )
        goto LABEL_5;
      if ( a1 != 65001 )
        return MultiByteToWideChar(a1, a2, a3, a4, a5, a6);
    }
    a2 &= 8u;
    return MultiByteToWideChar(a1, a2, a3, a4, a5, a6);
  }
  if ( a1 - 50220 <= 9 && (v6 = 679, _bittest(&v6, a1 - 50220)) || a1 == 42 )
LABEL_5:
    a2 = 0;
  return MultiByteToWideChar(a1, a2, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x180013848  cmp     ecx, 0C435h
0x18001384e  ja      short loc_180013870
0x180013850  lea     eax, [rcx-0C42Ch]
0x180013856  cmp     eax, 9
0x180013859  ja      short loc_180013867
0x18001385b  mov     r10d, 2A7h
0x180013861  bt      r10d, eax
0x180013865  jb      short loc_18001386C
0x180013867  cmp     ecx, 2Ah ; '*'
0x18001386a  jnz     short loc_18001389B
0x18001386c  xor     edx, edx
0x18001386e  jmp     short loc_18001389B
0x180013870  cmp     ecx, 0D698h
0x180013876  jz      short loc_180013898
0x180013878  cmp     ecx, 0DEA9h
0x18001387e  jbe     short loc_18001389B
0x180013880  cmp     ecx, 0DEB3h
0x180013886  jbe     short loc_18001386C
0x180013888  cmp     ecx, 0FDE8h
0x18001388e  jz      short loc_18001386C
0x180013890  cmp     ecx, 0FDE9h
0x180013896  jnz     short loc_18001389B
0x180013898  and     edx, 8
0x18001389b  jmp     cs:__imp_MultiByteToWideChar
```
