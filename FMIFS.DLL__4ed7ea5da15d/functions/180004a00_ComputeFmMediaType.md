# ComputeFmMediaType

- ea: `0x180004a00`
- end: `0x180004b44`
- name: `ComputeFmMediaType`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006a00`

## callees

- `0x180004a00`

## pseudocode

```c
__int64 __fastcall ComputeFmMediaType(int a1)
{
  unsigned int v1; // edx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx

  v1 = 12;
  if ( a1 > 12 )
  {
    v1 = 18;
    if ( a1 > 18 )
    {
      v1 = 19;
      v14 = a1 - 19;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( !v15 )
          return 20;
        v16 = v15 - 1;
        if ( !v16 )
          return 21;
        v17 = v16 - 2;
        if ( !v17 )
          return 22;
        if ( v17 == 1 )
          return 23;
        return 0;
      }
      return v1;
    }
    if ( a1 == 18 )
      return v1;
    v1 = 13;
    v10 = a1 - 13;
    if ( !v10 )
      return v1;
    v11 = v10 - 1;
    if ( !v11 )
      return 14;
    v12 = v11 - 1;
    if ( !v12 )
      return 15;
    v13 = v12 - 1;
    if ( !v13 )
      return 16;
    if ( v13 == 1 )
      return 17;
    return 0;
  }
  if ( a1 == 12 )
    return v1;
  v1 = 6;
  if ( a1 > 6 )
  {
    v6 = a1 - 7;
    if ( !v6 )
      return 3;
    v7 = v6 - 1;
    if ( !v7 )
      return 4;
    v8 = v7 - 1;
    if ( !v8 )
      return 2;
    v9 = v8 - 1;
    if ( !v9 )
      return 1;
    if ( v9 == 1 )
      return 11;
    return 0;
  }
  if ( a1 == 6 )
    return 5;
  if ( !a1 )
    return 0;
  v2 = a1 - 1;
  if ( v2 )
  {
    v3 = v2 - 1;
    if ( v3 )
    {
      v4 = v3 - 1;
      if ( v4 )
      {
        v5 = v4 - 1;
        if ( v5 )
        {
          if ( v5 == 1 )
            return v1;
          return 0;
        }
        return 10;
      }
      else
      {
        return 9;
      }
    }
    else
    {
      return 8;
    }
  }
  else
  {
    return 7;
  }
}

```

## disassembly

```asm
0x180004a00  mov     edx, 0Ch
0x180004a05  cmp     ecx, edx
0x180004a07  jg      loc_180004AC4
0x180004a0d  jz      loc_180004B41
0x180004a13  mov     edx, 6
0x180004a18  cmp     ecx, edx
0x180004a1a  jg      short loc_180004A7A
0x180004a1c  jz      short loc_180004A70
0x180004a1e  test    ecx, ecx
0x180004a20  jz      loc_180004B23
0x180004a26  sub     ecx, 1
0x180004a29  jz      short loc_180004A66
0x180004a2b  sub     ecx, 1
0x180004a2e  jz      short loc_180004A5C
0x180004a30  sub     ecx, 1
0x180004a33  jz      short loc_180004A52
0x180004a35  sub     ecx, 1
0x180004a38  jz      short loc_180004A48
0x180004a3a  cmp     ecx, 1
0x180004a3d  jnz     loc_180004B23
0x180004a43  jmp     loc_180004B41
0x180004a48  mov     edx, 0Ah
0x180004a4d  jmp     loc_180004B41
0x180004a52  mov     edx, 9
0x180004a57  jmp     loc_180004B41
0x180004a5c  mov     edx, 8
0x180004a61  jmp     loc_180004B41
0x180004a66  mov     edx, 7
0x180004a6b  jmp     loc_180004B41
0x180004a70  mov     edx, 5
0x180004a75  jmp     loc_180004B41
0x180004a7a  sub     ecx, 7
0x180004a7d  jz      short loc_180004ABD
0x180004a7f  sub     ecx, 1
0x180004a82  jz      short loc_180004AB3
0x180004a84  sub     ecx, 1
0x180004a87  jz      short loc_180004AA9
0x180004a89  sub     ecx, 1
0x180004a8c  jz      short loc_180004A9F
0x180004a8e  cmp     ecx, 1
0x180004a91  jnz     loc_180004B23
0x180004a97  lea     edx, [rcx+0Ah]
0x180004a9a  jmp     loc_180004B41
0x180004a9f  mov     edx, 1
0x180004aa4  jmp     loc_180004B41
0x180004aa9  mov     edx, 2
0x180004aae  jmp     loc_180004B41
0x180004ab3  mov     edx, 4
0x180004ab8  jmp     loc_180004B41
0x180004abd  mov     edx, 3
0x180004ac2  jmp     short loc_180004B41
0x180004ac4  mov     edx, 12h
0x180004ac9  cmp     ecx, edx
0x180004acb  jg      short loc_180004B06
0x180004acd  jz      short loc_180004B41
0x180004acf  mov     edx, 0Dh
0x180004ad4  sub     ecx, edx
0x180004ad6  jz      short loc_180004B41
0x180004ad8  sub     ecx, 1
0x180004adb  jz      short loc_180004AFF
0x180004add  sub     ecx, 1
0x180004ae0  jz      short loc_180004AF8
0x180004ae2  sub     ecx, 1
0x180004ae5  jz      short loc_180004AF1
0x180004ae7  cmp     ecx, 1
0x180004aea  jnz     short loc_180004B23
0x180004aec  lea     edx, [rcx+10h]
0x180004aef  jmp     short loc_180004B41
0x180004af1  mov     edx, 10h
0x180004af6  jmp     short loc_180004B41
0x180004af8  mov     edx, 0Fh
0x180004afd  jmp     short loc_180004B41
0x180004aff  mov     edx, 0Eh
0x180004b04  jmp     short loc_180004B41
0x180004b06  mov     edx, 13h
0x180004b0b  sub     ecx, edx
0x180004b0d  jz      short loc_180004B41
0x180004b0f  sub     ecx, 1
0x180004b12  jz      short loc_180004B3C
0x180004b14  sub     ecx, 1
0x180004b17  jz      short loc_180004B35
0x180004b19  sub     ecx, 2
0x180004b1c  jz      short loc_180004B2E
0x180004b1e  cmp     ecx, 1
0x180004b21  jz      short loc_180004B27
0x180004b23  xor     edx, edx
0x180004b25  jmp     short loc_180004B41
0x180004b27  mov     edx, 17h
0x180004b2c  jmp     short loc_180004B41
0x180004b2e  mov     edx, 16h
0x180004b33  jmp     short loc_180004B41
0x180004b35  mov     edx, 15h
0x180004b3a  jmp     short loc_180004B41
0x180004b3c  mov     edx, 14h
0x180004b41  mov     eax, edx
0x180004b43  retn
```
