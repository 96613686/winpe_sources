# SyntaxIdToString(ulong)

- ea: `0x18001bbc8`
- end: `0x18001bc4c`
- name: `?SyntaxIdToString@@YAPEBGK@Z`
- size: `132`
- prototype: `const unsigned __int16 *__fastcall(unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180009d90`
- `0x18000bee0`
- `0x18001a34c`

## callees

- `0x18001bbc8`

## string_xrefs

- `0x18001bc2c`: `NTAcl`

## pseudocode

```c
const unsigned __int16 *__fastcall SyntaxIdToString(unsigned int a1)
{
  unsigned int v1; // ecx
  unsigned int v2; // ecx
  unsigned int v3; // ecx
  unsigned int v4; // ecx
  unsigned int v6; // ecx
  unsigned int v7; // ecx
  unsigned int v8; // ecx

  if ( a1 <= 6 )
  {
    if ( a1 != 6 )
    {
      v1 = a1 - 1;
      if ( !v1 )
        return L"Integer";
      v2 = v1 - 1;
      if ( !v2 )
        return L"String";
      v3 = v2 - 1;
      if ( !v3 )
        return L"ExpandSz";
      v4 = v3 - 1;
      if ( !v4 )
        return L"List";
      if ( v4 == 1 )
        return L"Binary";
      return L"(ERROR -- UNDEFINED SYNTAX ID)";
    }
    return L"Boolean";
  }
  v6 = a1 - 7;
  if ( !v6 )
    return L"Boolean";
  v7 = v6 - 1;
  if ( !v7 )
    return L"MimeMapList";
  v8 = v7 - 1;
  if ( !v8 )
    return L"IPSec";
  if ( v8 != 1 )
    return L"(ERROR -- UNDEFINED SYNTAX ID)";
  return L"NTAcl";
}

```

## disassembly

```asm
0x18001bbc8  cmp     ecx, 6
0x18001bbcb  ja      short loc_18001BC10
0x18001bbcd  jz      short loc_18001BC44
0x18001bbcf  sub     ecx, 1
0x18001bbd2  jz      short loc_18001BC08
0x18001bbd4  sub     ecx, 1
0x18001bbd7  jz      short loc_18001BC00
0x18001bbd9  sub     ecx, 1
0x18001bbdc  jz      short loc_18001BBF8
0x18001bbde  sub     ecx, 1
0x18001bbe1  jz      short loc_18001BBF0
0x18001bbe3  cmp     ecx, 1
0x18001bbe6  jnz     short loc_18001BC24
0x18001bbe8  lea     rax, aBinary; "Binary"
0x18001bbef  retn
0x18001bbf0  lea     rax, aList; "List"
0x18001bbf7  retn
0x18001bbf8  lea     rax, aExpandsz; "ExpandSz"
0x18001bbff  retn
0x18001bc00  lea     rax, aString; "String"
0x18001bc07  retn
0x18001bc08  lea     rax, aInteger; "Integer"
0x18001bc0f  retn
0x18001bc10  sub     ecx, 7
0x18001bc13  jz      short loc_18001BC44
0x18001bc15  sub     ecx, 1
0x18001bc18  jz      short loc_18001BC3C
0x18001bc1a  sub     ecx, 1
0x18001bc1d  jz      short loc_18001BC34
0x18001bc1f  cmp     ecx, 1
0x18001bc22  jz      short loc_18001BC2C
0x18001bc24  lea     rax, aErrorUndefined; "(ERROR -- UNDEFINED SYNTAX ID)"
0x18001bc2b  retn
0x18001bc2c  lea     rax, aNtacl; "NTAcl"
0x18001bc33  retn
0x18001bc34  lea     rax, aIpsec; "IPSec"
0x18001bc3b  retn
0x18001bc3c  lea     rax, aMimemaplist; "MimeMapList"
0x18001bc43  retn
0x18001bc44  lea     rax, aBoolean; "Boolean"
0x18001bc4b  retn
```
