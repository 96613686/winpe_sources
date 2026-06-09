# AslAnsiStringCreate

- ea: `0x1400321ac`
- end: `0x14003223c`
- name: `AslAnsiStringCreate`
- size: `144`
- prototype: `__int64 __fastcall(PANSI_STRING DestinationString)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140033484`

## callees

- `0x1400266b0`
- `0x1400321ac`
- `0x14003e364`
- `0x140045d44`

## import_xrefs

- `ntoskrnl!RtlInitAnsiString` at `0x140032219`
- `ntoskrnl!RtlInitAnsiString` at `0x140032219`

## string_xrefs

- `0x1400321f4`: `AslAnsiStringCreate`

## pseudocode

```c
__int64 __fastcall AslAnsiStringCreate(PANSI_STRING DestinationString)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rcx
  PCSZ v5; // rdx
  PCSZ SourceString; // [rsp+48h] [rbp+10h] BYREF

  SourceString = 0;
  *DestinationString = 0;
  v2 = AslStringDuplicateA(&SourceString);
  v3 = v2;
  if ( v2 >= 0 )
  {
    RtlInitAnsiString(DestinationString, SourceString);
    v5 = 0;
    v3 = 0;
  }
  else
  {
    AslLogCallPrintf(1, "AslAnsiStringCreate", 1039, "AslStringDuplicate failed with \"%s\" [%x]", byte_14000DA20, v2);
    v5 = SourceString;
  }
  AslFree(v4, v5);
  return v3;
}

```

## disassembly

```asm
0x1400321ac  mov     rax, rsp
0x1400321af  mov     [rax+8], rbx
0x1400321b3  mov     [rax+10h], rdx
0x1400321b7  push    rdi
0x1400321b8  sub     rsp, 30h
0x1400321bc  xorps   xmm0, xmm0
0x1400321bf  mov     qword ptr [rax+10h], 0
0x1400321c7  movups  xmmword ptr [rcx], xmm0
0x1400321ca  mov     rdi, rcx
0x1400321cd  lea     rcx, [rax+10h]
0x1400321d1  call    AslStringDuplicateA
0x1400321d6  mov     ebx, eax
0x1400321d8  test    eax, eax
0x1400321da  jns     short loc_140032211
0x1400321dc  mov     [rsp+38h+var_10], eax
0x1400321e0  lea     r9, aAslstringdupli; "AslStringDuplicate failed with \"%s\" ["...
0x1400321e7  lea     rax, byte_14000DA20
0x1400321ee  mov     r8d, 40Fh
0x1400321f4  lea     rdx, aAslansistringc; "AslAnsiStringCreate"
0x1400321fb  mov     [rsp+38h+var_18], rax
0x140032200  mov     ecx, 1
0x140032205  call    AslLogCallPrintf
0x14003220a  mov     rdx, [rsp+38h+SourceString]
0x14003220f  jmp     short loc_140032229
0x140032211  mov     rdx, [rsp+38h+SourceString]; SourceString
0x140032216  mov     rcx, rdi; DestinationString
0x140032219  call    cs:__imp_RtlInitAnsiString
0x140032220  nop     dword ptr [rax+rax+00h]
0x140032225  xor     edx, edx
0x140032227  xor     ebx, ebx
0x140032229  call    AslFree
0x14003222e  mov     eax, ebx
0x140032230  mov     rbx, [rsp+38h+arg_0]
0x140032235  add     rsp, 30h
0x140032239  pop     rdi
0x14003223a  retn
```
