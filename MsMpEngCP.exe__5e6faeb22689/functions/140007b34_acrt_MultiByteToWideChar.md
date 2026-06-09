# __acrt_MultiByteToWideChar

- ea: `0x140007b34`
- end: `0x140007bc4`
- name: `__acrt_MultiByteToWideChar`
- size: `144`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140004c98`
- `0x140008e18`
- `0x14000a4ac`
- `0x14000ade8`

## callees

- `0x140007b34`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x140007b85`

## pseudocode

```c
int __fastcall _acrt_MultiByteToWideChar(UINT a1, char a2, const CHAR *a3, int a4, WCHAR *a5, int a6)
{
  bool v6; // zf

  if ( a1 > 0xDEAC )
  {
    if ( a1 == 57005
      || a1 == 57006
      || a1 == 57007
      || a1 == 57008
      || a1 == 57009
      || a1 == 57010
      || a1 == 57011
      || a1 == 65000 )
    {
      goto LABEL_15;
    }
    if ( a1 != 65001 )
      return MultiByteToWideChar(a1, a2, a3, a4, a5, a6);
    goto LABEL_26;
  }
  if ( a1 == 57004 )
    goto LABEL_15;
  if ( a1 > 0xC433 )
  {
    if ( a1 == 50229 )
      goto LABEL_15;
    if ( a1 != 54936 )
    {
      if ( a1 != 57002 )
      {
        v6 = a1 == 57003;
        goto LABEL_14;
      }
LABEL_15:
      a2 = 0;
      return MultiByteToWideChar(a1, a2, a3, a4, a5, a6);
    }
LABEL_26:
    a2 &= 8u;
    return MultiByteToWideChar(a1, a2, a3, a4, a5, a6);
  }
  if ( a1 == 50227 || a1 == 42 || a1 == 50220 || a1 == 50221 || a1 == 50222 )
    goto LABEL_15;
  v6 = a1 == 50225;
LABEL_14:
  if ( v6 )
    goto LABEL_15;
  return MultiByteToWideChar(a1, a2, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x140007b34  mov     eax, 0DEACh
0x140007b39  cmp     ecx, eax
0x140007b3b  ja      short loc_140007B8C
0x140007b3d  jz      short loc_140007B83
0x140007b3f  mov     eax, 0C433h
0x140007b44  cmp     ecx, eax
0x140007b46  ja      short loc_140007B67
0x140007b48  jz      short loc_140007B83
0x140007b4a  mov     eax, ecx
0x140007b4c  sub     eax, 2Ah ; '*'
0x140007b4f  jz      short loc_140007B83
0x140007b51  sub     eax, 0C402h
0x140007b56  jz      short loc_140007B83
0x140007b58  sub     eax, 1
0x140007b5b  jz      short loc_140007B83
0x140007b5d  sub     eax, 1
0x140007b60  jz      short loc_140007B83
0x140007b62  cmp     eax, 3
0x140007b65  jmp     short loc_140007B81
0x140007b67  mov     eax, ecx
0x140007b69  sub     eax, 0C435h
0x140007b6e  jz      short loc_140007B83
0x140007b70  sub     eax, 1263h
0x140007b75  jz      short loc_140007BBF
0x140007b77  sub     eax, 812h
0x140007b7c  jz      short loc_140007B83
0x140007b7e  cmp     eax, 1
0x140007b81  jnz     short loc_140007B85
0x140007b83  xor     edx, edx
0x140007b85  jmp     cs:MultiByteToWideChar
0x140007b8c  mov     eax, ecx
0x140007b8e  sub     eax, 0DEADh
0x140007b93  jz      short loc_140007B83
0x140007b95  sub     eax, 1
0x140007b98  jz      short loc_140007B83
0x140007b9a  sub     eax, 1
0x140007b9d  jz      short loc_140007B83
0x140007b9f  sub     eax, 1
0x140007ba2  jz      short loc_140007B83
0x140007ba4  sub     eax, 1
0x140007ba7  jz      short loc_140007B83
0x140007ba9  sub     eax, 1
0x140007bac  jz      short loc_140007B83
0x140007bae  sub     eax, 1
0x140007bb1  jz      short loc_140007B83
0x140007bb3  sub     eax, 1F35h
0x140007bb8  jz      short loc_140007B83
0x140007bba  cmp     eax, 1
0x140007bbd  jnz     short loc_140007B85
0x140007bbf  and     edx, 8
0x140007bc2  jmp     short loc_140007B85
```
