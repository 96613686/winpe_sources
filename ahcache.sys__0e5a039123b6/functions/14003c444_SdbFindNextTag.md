# SdbFindNextTag

- ea: `0x14003c444`
- end: `0x14003c543`
- name: `SdbFindNextTag`
- size: `255`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x140002a00`
- `0x1400030d0`
- `0x140038fd4`
- `0x14003a154`
- `0x14003af10`
- `0x14003c710`

## callees

- `0x14003c444`
- `0x14003c54c`
- `0x14003e248`
- `0x14003e364`

## string_xrefs

- `0x14003c4d0`: `Error reading data`
- `0x14003c520`: `Error reading data`

## pseudocode

```c
__int64 __fastcall SdbFindNextTag(__int64 a1, unsigned int a2, unsigned int a3)
{
  unsigned int v3; // ebx
  __int16 v6; // si
  unsigned int v7; // edi
  unsigned int NextChild; // eax
  __int16 v10; // [rsp+88h] [rbp+20h] BYREF

  v3 = a3;
  v10 = 0;
  if ( !(unsigned int)SdbpReadMappedData(a1, a3, &v10, 2u) )
  {
    AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
    goto LABEL_10;
  }
  v6 = v10;
  if ( !v10 )
  {
LABEL_10:
    AslLogCallPrintf(1, "SdbFindNextTag", 216, "Invalid tagid 0x%lx", v3);
    return 0;
  }
  v7 = 0;
  while ( 1 )
  {
    NextChild = SdbGetNextChild(a1, a2, v3);
    v3 = NextChild;
    if ( !NextChild )
      break;
    v10 = 0;
    if ( (unsigned int)SdbpReadMappedData(a1, NextChild, &v10, 2u) )
    {
      if ( v10 == v6 )
        return v3;
    }
    else
    {
      AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
    }
  }
  return v7;
}

```

## disassembly

```asm
0x14003c444  mov     rax, rsp
0x14003c447  push    rbx
0x14003c448  push    rbp
0x14003c449  push    rsi
0x14003c44a  push    rdi
0x14003c44b  push    r14
0x14003c44d  push    r15
0x14003c44f  sub     rsp, 38h
0x14003c453  mov     ebx, r8d
0x14003c456  xor     r15d, r15d
0x14003c459  mov     r14d, edx
0x14003c45c  mov     [rax+20h], r15w
0x14003c461  lea     r8, [rax+20h]
0x14003c465  mov     edx, ebx
0x14003c467  mov     rbp, rcx
0x14003c46a  lea     r9d, [r15+2]
0x14003c46e  call    SdbpReadMappedData
0x14003c473  test    eax, eax
0x14003c475  jz      short loc_14003C4D0
0x14003c477  movzx   esi, [rsp+68h+arg_18]
0x14003c47f  test    si, si
0x14003c482  jz      short loc_14003C4EE
0x14003c484  mov     edi, r15d
0x14003c487  mov     r8d, ebx
0x14003c48a  mov     edx, r14d
0x14003c48d  mov     rcx, rbp
0x14003c490  call    SdbGetNextChild
0x14003c495  mov     ebx, eax
0x14003c497  test    eax, eax
0x14003c499  jz      short loc_14003C4CC
0x14003c49b  mov     r9d, 2
0x14003c4a1  mov     [rsp+68h+arg_18], r15w
0x14003c4aa  lea     r8, [rsp+68h+arg_18]
0x14003c4b2  mov     edx, eax
0x14003c4b4  mov     rcx, rbp
0x14003c4b7  call    SdbpReadMappedData
0x14003c4bc  test    eax, eax
0x14003c4be  jz      short loc_14003C520
0x14003c4c0  cmp     [rsp+68h+arg_18], si
0x14003c4c8  jnz     short loc_14003C487
0x14003c4ca  mov     edi, ebx
0x14003c4cc  mov     eax, edi
0x14003c4ce  jmp     short loc_14003C512
0x14003c4d0  lea     r9, aErrorReadingDa; "Error reading data"
0x14003c4d7  mov     r8d, 0BDFh
0x14003c4dd  lea     rdx, aSdbgettagfromt; "SdbGetTagFromTagID"
0x14003c4e4  mov     ecx, 1
0x14003c4e9  call    AslLogCallPrintf
0x14003c4ee  lea     r9, aInvalidTagid0x; "Invalid tagid 0x%lx"
0x14003c4f5  mov     [rsp+68h+var_48], ebx
0x14003c4f9  mov     r8d, 0D8h
0x14003c4ff  lea     rdx, aSdbfindnexttag; "SdbFindNextTag"
0x14003c506  mov     ecx, 1
0x14003c50b  call    AslLogCallPrintf
0x14003c510  xor     eax, eax
0x14003c512  add     rsp, 38h
0x14003c516  pop     r15
0x14003c518  pop     r14
0x14003c51a  pop     rdi
0x14003c51b  pop     rsi
0x14003c51c  pop     rbp
0x14003c51d  pop     rbx
0x14003c51e  retn
0x14003c520  lea     r9, aErrorReadingDa; "Error reading data"
0x14003c527  mov     r8d, 0BDFh
0x14003c52d  lea     rdx, aSdbgettagfromt; "SdbGetTagFromTagID"
0x14003c534  mov     ecx, 1
0x14003c539  call    AslLogCallPrintf
0x14003c53e  jmp     loc_14003C487
```
