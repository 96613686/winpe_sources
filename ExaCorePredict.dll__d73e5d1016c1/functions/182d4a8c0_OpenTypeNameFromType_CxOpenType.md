# OpenTypeNameFromType(CxOpenType)

- ea: `0x182d4a8c0`
- end: `0x182d4a923`
- name: `?OpenTypeNameFromType@@YAPEBDW4CxOpenType@@@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x182d4a8c0`

## string_xrefs

- `0x182d4a8db`: `OpenType_Read:`
- `0x182d4a8e3`: `OpenType_Write:`
- `0x182d4a8eb`: `OpenType_ReadWrite:`
- `0x182d4a8f3`: `OpenType_AppendRows:`
- `0x182d4a8fb`: `OpenType_ModifyOrAppendCols:`
- `0x182d4a903`: `OpenType_AllowRead:`
- `0x182d4a90b`: `OpenType_AllowWrite:`
- `0x182d4a913`: `OpenType_Uninitialized:`
- `0x182d4a91b`: `Unknown OpenType`

## pseudocode

```c
const char *__fastcall OpenTypeNameFromType(int a1)
{
  const char *result; // rax

  switch ( a1 )
  {
    case 0:
      result = "OpenType_Read:";
      break;
    case 1:
      result = "OpenType_Write:";
      break;
    case 2:
      result = "OpenType_ReadWrite:";
      break;
    case 3:
      result = "OpenType_AppendRows:";
      break;
    case 4:
      result = "OpenType_ModifyOrAppendCols:";
      break;
    case 5:
      result = "OpenType_AllowRead:";
      break;
    case 6:
      result = "OpenType_AllowWrite:";
      break;
    case 7:
      result = "OpenType_Uninitialized:";
      break;
    default:
      result = "Unknown OpenType";
      break;
  }
  return result;
}

```

## disassembly

```asm
0x182d4a8c0  cmp     ecx, 7; switch 8 cases
0x182d4a8c3  ja      short def_182D4A8D9; jumptable 0000000182D4A8D9 default case
0x182d4a8c5  movsxd  rax, ecx
0x182d4a8c8  lea     rdx, cs:180000000h
0x182d4a8cf  mov     ecx, ds:(jpt_182D4A8D9 - 180000000h)[rdx+rax*4]
0x182d4a8d6  add     rcx, rdx
0x182d4a8d9  jmp     rcx; switch jump
0x182d4a8db  lea     rax, aOpentypeRead; jumptable 0000000182D4A8D9 case 0
0x182d4a8e2  retn
0x182d4a8e3  lea     rax, aOpentypeWrite; jumptable 0000000182D4A8D9 case 1
0x182d4a8ea  retn
0x182d4a8eb  lea     rax, aOpentypeReadwr; jumptable 0000000182D4A8D9 case 2
0x182d4a8f2  retn
0x182d4a8f3  lea     rax, aOpentypeAppend; jumptable 0000000182D4A8D9 case 3
0x182d4a8fa  retn
0x182d4a8fb  lea     rax, aOpentypeModify; jumptable 0000000182D4A8D9 case 4
0x182d4a902  retn
0x182d4a903  lea     rax, aOpentypeAllowr; jumptable 0000000182D4A8D9 case 5
0x182d4a90a  retn
0x182d4a90b  lea     rax, aOpentypeAlloww; jumptable 0000000182D4A8D9 case 6
0x182d4a912  retn
0x182d4a913  lea     rax, aOpentypeUninit; jumptable 0000000182D4A8D9 case 7
0x182d4a91a  retn
0x182d4a91b  lea     rax, aUnknownOpentyp; jumptable 0000000182D4A8D9 default case
0x182d4a922  retn
```
