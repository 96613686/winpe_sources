# SdbReadWORDTag

- ea: `0x14003c62c`
- end: `0x14003c704`
- name: `SdbReadWORDTag`
- size: `216`
- prototype: ``
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x140002d38`
- `0x1400030d0`
- `0x140030304`
- `0x140039898`
- `0x14003af10`
- `0x14003bea8`
- `0x14003c710`
- `0x14004a1ac`

## callees

- `0x14003c62c`
- `0x14003e1f0`
- `0x14003e248`
- `0x14003e364`
- `0x14003ea80`

## string_xrefs

- `0x14003c6ae`: `Error reading data`
- `0x14003c6e4`: `SdbReadWORDTag`

## pseudocode

```c
__int64 __fastcall SdbReadWORDTag(__int64 a1, unsigned int a2, unsigned __int16 a3)
{
  int TagData; // eax
  unsigned __int16 v7; // cx
  unsigned __int16 TagFromTagID; // ax
  __int16 v10; // [rsp+50h] [rbp+18h] BYREF
  unsigned __int16 v11; // [rsp+58h] [rbp+20h] BYREF

  v11 = a3;
  v10 = 0;
  if ( !(unsigned int)SdbpReadMappedData(a1, a2, &v10, 2u) )
  {
    AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
    goto LABEL_7;
  }
  if ( (v10 & 0xF000) != 0x3000 )
  {
LABEL_7:
    TagFromTagID = SdbGetTagFromTagID(a1, a2);
    AslLogCallPrintf(1, "SdbReadWORDTag", 172, "TagID 0x%X, Tag 0x%X not of the expected type", a2, TagFromTagID);
    return a3;
  }
  TagData = SdbpReadTagData(a1, a2, (__int64)&v11, 2u);
  v7 = v11;
  if ( !TagData )
    return a3;
  return v7;
}

```

## disassembly

```asm
0x14003c62c  mov     [rsp+arg_0], rbx
0x14003c631  mov     [rsp+arg_8], rsi
0x14003c636  push    rdi
0x14003c637  sub     rsp, 30h
0x14003c63b  xor     eax, eax
0x14003c63d  mov     [rsp+38h+arg_18], r8w
0x14003c643  movzx   edi, r8w
0x14003c647  mov     [rsp+38h+arg_10], ax
0x14003c64c  lea     r8, [rsp+38h+arg_10]
0x14003c651  mov     ebx, edx
0x14003c653  mov     rsi, rcx
0x14003c656  lea     r9d, [rax+2]
0x14003c65a  call    SdbpReadMappedData
0x14003c65f  test    eax, eax
0x14003c661  jz      short loc_14003C6AE
0x14003c663  movzx   eax, [rsp+38h+arg_10]
0x14003c668  mov     ecx, 0F000h
0x14003c66d  and     ax, cx
0x14003c670  mov     edx, 3000h
0x14003c675  cmp     ax, dx
0x14003c678  jnz     short loc_14003C6CC
0x14003c67a  mov     r9d, 2
0x14003c680  lea     r8, [rsp+38h+arg_18]
0x14003c685  mov     edx, ebx
0x14003c687  mov     rcx, rsi
0x14003c68a  call    SdbpReadTagData
0x14003c68f  movzx   ecx, [rsp+38h+arg_18]
0x14003c694  test    eax, eax
0x14003c696  cmovz   cx, di
0x14003c69a  movzx   eax, cx
0x14003c69d  mov     rbx, [rsp+38h+arg_0]
0x14003c6a2  mov     rsi, [rsp+38h+arg_8]
0x14003c6a7  add     rsp, 30h
0x14003c6ab  pop     rdi
0x14003c6ac  retn
0x14003c6ae  lea     r9, aErrorReadingDa; "Error reading data"
0x14003c6b5  mov     r8d, 0BDFh
0x14003c6bb  lea     rdx, aSdbgettagfromt; "SdbGetTagFromTagID"
0x14003c6c2  mov     ecx, 1
0x14003c6c7  call    AslLogCallPrintf
0x14003c6cc  mov     edx, ebx
0x14003c6ce  mov     rcx, rsi
0x14003c6d1  call    SdbGetTagFromTagID
0x14003c6d6  movzx   eax, ax
0x14003c6d9  lea     r9, aTagid0xXTag0xX; "TagID 0x%X, Tag 0x%X not of the expecte"...
0x14003c6e0  mov     [rsp+38h+var_10], eax
0x14003c6e4  lea     rdx, aSdbreadwordtag_0; "SdbReadWORDTag"
0x14003c6eb  mov     r8d, 0ACh
0x14003c6f1  mov     [rsp+38h+var_18], ebx
0x14003c6f5  mov     ecx, 1
0x14003c6fa  call    AslLogCallPrintf
0x14003c6ff  movzx   eax, di
0x14003c702  jmp     short loc_14003C69D
```
