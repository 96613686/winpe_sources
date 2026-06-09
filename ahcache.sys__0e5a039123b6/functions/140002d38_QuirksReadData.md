# QuirksReadData

- ea: `0x140002d38`
- end: `0x140002f53`
- name: `QuirksReadData`
- size: `539`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140002a00`

## callees

- `0x140002d38`
- `0x14003c54c`
- `0x14003c62c`
- `0x14003e1f0`
- `0x14003e364`
- `0x14003f570`
- `0x14003fc10`
- `0x140040820`
- `0x1400408c8`
- `0x1400425d8`

## string_xrefs

- `0x140002dfe`: `SdbReadWORDTag failed: 0x%x`
- `0x140002e2a`: `SdbReadWORDTag failed: 0x%x`
- `0x140002e87`: `SdbReadBinaryTag failed: 0x%x`
- `0x140002ed5`: `SdbReadStringTag failed: 0x%x`
- `0x140002f16`: `SdbReadStringTag failed: 0x%x`
- `0x140002f25`: `Quirk IDs reading failed: 0x%x`
- `0x140002f37`: `QuirksReadData`

## pseudocode

```c
__int64 __fastcall QuirksReadData(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int i; // eax
  unsigned int v7; // edi
  unsigned __int16 TagFromTagID; // ax
  __int16 WORDTag; // ax
  const char *v10; // r9
  __int64 v11; // r8
  __int16 v12; // ax
  unsigned int v13; // ebx

  *(_DWORD *)(a3 + 552) = 4;
  *(_DWORD *)(a3 + 276) = -1;
  for ( i = SdbGetFirstChild(); ; i = SdbGetNextChild(a1, a2, v7) )
  {
    v7 = i;
    if ( !i )
      break;
    TagFromTagID = SdbGetTagFromTagID(a1, i);
    switch ( TagFromTagID )
    {
      case 0x100Au:
        *(_DWORD *)(a3 + 552) &= ~4u;
        break;
      case 0x3002u:
        WORDTag = SdbReadWORDTag(a1, v7, 0xFFFF);
        *(_WORD *)(a3 + 278) = WORDTag;
        if ( WORDTag == -1 )
        {
          v10 = "SdbReadWORDTag failed: 0x%x";
          v11 = 185;
          goto LABEL_30;
        }
        break;
      case 0x3003u:
        v12 = SdbReadWORDTag(a1, v7, 0xFFFF);
        *(_WORD *)(a3 + 276) = v12;
        if ( v12 == -1 )
        {
          v10 = "SdbReadWORDTag failed: 0x%x";
          v11 = 194;
          goto LABEL_30;
        }
        break;
      case 0x4055u:
        *(_QWORD *)(a3 + 268) = (unsigned int)SdbReadDWORDTag(a1, v7, 0);
        break;
      case 0x501Cu:
        *(_QWORD *)(a3 + 260) = SdbReadQWORDTag(a1, v7, 0);
        break;
      case 0x6001u:
        if ( !(unsigned int)SdbReadStringTag(a1, v7, a3) )
        {
          v10 = "SdbReadStringTag failed: 0x%x";
          v11 = 160;
          goto LABEL_30;
        }
        break;
      case 0x6008u:
        if ( !(unsigned int)SdbReadStringTag(a1, v7, a3 + 296) )
        {
          v10 = "SdbReadStringTag failed: 0x%x";
          v11 = 202;
          goto LABEL_30;
        }
        break;
      default:
        if ( TagFromTagID == 36880 && !(unsigned int)SdbReadBinaryTag(a1, v7, a3 + 280, 16) )
        {
          v10 = "SdbReadBinaryTag failed: 0x%x";
          v11 = 168;
          goto LABEL_30;
        }
        break;
    }
  }
  if ( *(_WORD *)(a3 + 276) != 0xFFFF && *(_WORD *)(a3 + 278) != 0xFFFF )
    return 0;
  v10 = "Quirk IDs reading failed: 0x%x";
  v11 = 217;
LABEL_30:
  v13 = -1073741596;
  AslLogCallPrintf(1, "QuirksReadData", v11, v10, -1073741596);
  return v13;
}

```

## disassembly

```asm
0x140002d38  push    rbx
0x140002d3a  push    rbp
0x140002d3b  push    rsi
0x140002d3c  push    rdi
0x140002d3d  push    r14
0x140002d3f  sub     rsp, 30h
0x140002d43  mov     rbx, r8
0x140002d46  mov     dword ptr [r8+228h], 4
0x140002d51  mov     ebp, edx
0x140002d53  mov     dword ptr [r8+114h], 0FFFFFFFFh
0x140002d5e  mov     rsi, rcx
0x140002d61  mov     r14d, 0FFFFh
0x140002d67  call    SdbGetFirstChild
0x140002d6c  mov     edi, eax
0x140002d6e  test    eax, eax
0x140002d70  jz      loc_140002E3C
0x140002d76  mov     edx, eax
0x140002d78  mov     rcx, rsi
0x140002d7b  call    SdbGetTagFromTagID
0x140002d80  movzx   edx, ax
0x140002d83  sub     edx, 100Ah
0x140002d89  jz      loc_140002E99
0x140002d8f  sub     edx, 1FF8h
0x140002d95  jz      short loc_140002DE4
0x140002d97  sub     edx, 1
0x140002d9a  jz      short loc_140002E10
0x140002d9c  sub     edx, 1052h
0x140002da2  jz      loc_140002EA5
0x140002da8  sub     edx, 0FC7h
0x140002dae  jz      loc_140002EE4
0x140002db4  sub     edx, 0FE5h
0x140002dba  jz      loc_140002EC0
0x140002dc0  sub     edx, 7
0x140002dc3  jz      loc_140002EFD
0x140002dc9  cmp     edx, 3008h
0x140002dcf  jz      loc_140002E68
0x140002dd5  mov     r8d, edi
0x140002dd8  mov     edx, ebp
0x140002dda  mov     rcx, rsi
0x140002ddd  call    SdbGetNextChild
0x140002de2  jmp     short loc_140002D6C
0x140002de4  mov     r8d, r14d
0x140002de7  mov     edx, edi
0x140002de9  mov     rcx, rsi
0x140002dec  call    SdbReadWORDTag
0x140002df1  mov     [rbx+116h], ax
0x140002df8  cmp     ax, r14w
0x140002dfc  jnz     short loc_140002DD5
0x140002dfe  lea     r9, aSdbreadwordtag; "SdbReadWORDTag failed: 0x%x"
0x140002e05  mov     r8d, 0B9h
0x140002e0b  jmp     loc_140002F32
0x140002e10  mov     r8d, r14d
0x140002e13  mov     edx, edi
0x140002e15  mov     rcx, rsi
0x140002e18  call    SdbReadWORDTag
0x140002e1d  mov     [rbx+114h], ax
0x140002e24  cmp     ax, r14w
0x140002e28  jnz     short loc_140002DD5
0x140002e2a  lea     r9, aSdbreadwordtag; "SdbReadWORDTag failed: 0x%x"
0x140002e31  mov     r8d, 0C2h
0x140002e37  jmp     loc_140002F32
0x140002e3c  cmp     [rbx+114h], r14w
0x140002e44  jz      loc_140002F25
0x140002e4a  cmp     [rbx+116h], r14w
0x140002e52  jz      loc_140002F25
0x140002e58  xor     ebx, ebx
0x140002e5a  mov     eax, ebx
0x140002e5c  add     rsp, 30h
0x140002e60  pop     r14
0x140002e62  pop     rdi
0x140002e63  pop     rsi
0x140002e64  pop     rbp
0x140002e65  pop     rbx
0x140002e66  retn
0x140002e68  lea     r8, [rbx+118h]
0x140002e6f  mov     r9d, 10h
0x140002e75  mov     edx, edi
0x140002e77  mov     rcx, rsi
0x140002e7a  call    SdbReadBinaryTag
0x140002e7f  test    eax, eax
0x140002e81  jnz     loc_140002DD5
0x140002e87  lea     r9, aSdbreadbinaryt; "SdbReadBinaryTag failed: 0x%x"
0x140002e8e  mov     r8d, 0A8h
0x140002e94  jmp     loc_140002F32
0x140002e99  and     dword ptr [rbx+228h], 0FFFFFFFBh
0x140002ea0  jmp     loc_140002DD5
0x140002ea5  xor     r8d, r8d
0x140002ea8  mov     edx, edi
0x140002eaa  mov     rcx, rsi
0x140002ead  call    SdbReadDWORDTag
0x140002eb2  mov     eax, eax
0x140002eb4  mov     [rbx+10Ch], rax
0x140002ebb  jmp     loc_140002DD5
0x140002ec0  mov     r8, rbx
0x140002ec3  mov     edx, edi
0x140002ec5  mov     rcx, rsi
0x140002ec8  call    SdbReadStringTag
0x140002ecd  test    eax, eax
0x140002ecf  jnz     loc_140002DD5
0x140002ed5  lea     r9, aSdbreadstringt; "SdbReadStringTag failed: 0x%x"
0x140002edc  mov     r8d, 0A0h
0x140002ee2  jmp     short loc_140002F32
0x140002ee4  xor     r8d, r8d
0x140002ee7  mov     edx, edi
0x140002ee9  mov     rcx, rsi
0x140002eec  call    SdbReadQWORDTag
0x140002ef1  mov     [rbx+104h], rax
0x140002ef8  jmp     loc_140002DD5
0x140002efd  lea     r8, [rbx+128h]
0x140002f04  mov     edx, edi
0x140002f06  mov     rcx, rsi
0x140002f09  call    SdbReadStringTag
0x140002f0e  test    eax, eax
0x140002f10  jnz     loc_140002DD5
0x140002f16  lea     r9, aSdbreadstringt; "SdbReadStringTag failed: 0x%x"
0x140002f1d  mov     r8d, 0CAh
0x140002f23  jmp     short loc_140002F32
0x140002f25  lea     r9, aQuirkIdsReadin; "Quirk IDs reading failed: 0x%x"
0x140002f2c  mov     r8d, 0D9h
0x140002f32  mov     eax, 0C00000E4h
0x140002f37  lea     rdx, aQuirksreaddata_1; "QuirksReadData"
0x140002f3e  mov     ecx, 1
0x140002f43  mov     [rsp+58h+var_38], eax
0x140002f47  mov     ebx, eax
0x140002f49  call    AslLogCallPrintf
0x140002f4e  jmp     loc_140002E5A
```
