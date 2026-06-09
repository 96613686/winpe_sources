# AslAnsiStringCreate

- ea: `0x1400160ec`
- end: `0x14001618b`
- name: `AslAnsiStringCreate`
- size: `159`
- prototype: `__int64 __fastcall(PANSI_STRING DestinationString)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140011880`

## callees

- `0x1400151b0`
- `0x1400160ec`
- `0x1400164c4`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140016178`
- `ntdll!RtlFreeHeap` at `0x140016178`
- `ntdll!RtlInitAnsiString` at `0x140016159`
- `ntdll!RtlInitAnsiString` at `0x140016159`

## string_xrefs

- `0x140016134`: `AslAnsiStringCreate`

## pseudocode

```c
__int64 __fastcall AslAnsiStringCreate(PANSI_STRING DestinationString)
{
  int v2; // eax
  unsigned int v3; // ebx
  char *v4; // r8
  PCSZ SourceString; // [rsp+48h] [rbp+10h] BYREF

  SourceString = 0;
  *DestinationString = 0;
  v2 = AslStringDuplicateA(&SourceString);
  v3 = v2;
  if ( v2 >= 0 )
  {
    RtlInitAnsiString(DestinationString, SourceString);
    v4 = 0;
    v3 = 0;
  }
  else
  {
    AslLogCallPrintf(
      1,
      "AslAnsiStringCreate",
      1039,
      "AslStringDuplicate failed with \"%s\" [%x]",
      (const char *)&dword_1400ACDEC,
      v2);
    v4 = (char *)SourceString;
  }
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  return v3;
}

```

## disassembly

```asm
0x1400160ec  mov     rax, rsp
0x1400160ef  mov     [rax+8], rbx
0x1400160f3  mov     [rax+10h], rdx
0x1400160f7  push    rdi
0x1400160f8  sub     rsp, 30h
0x1400160fc  xorps   xmm0, xmm0
0x1400160ff  mov     qword ptr [rax+10h], 0
0x140016107  movups  xmmword ptr [rcx], xmm0
0x14001610a  mov     rdi, rcx
0x14001610d  lea     rcx, [rax+10h]
0x140016111  call    AslStringDuplicateA
0x140016116  mov     ebx, eax
0x140016118  test    eax, eax
0x14001611a  jns     short loc_140016151
0x14001611c  mov     [rsp+38h+var_10], eax
0x140016120  lea     r9, aAslstringdupli; "AslStringDuplicate failed with \"%s\" ["...
0x140016127  lea     rax, dword_1400ACDEC
0x14001612e  mov     r8d, 40Fh
0x140016134  lea     rdx, aAslansistringc; "AslAnsiStringCreate"
0x14001613b  mov     [rsp+38h+var_18], rax
0x140016140  mov     ecx, 1
0x140016145  call    AslLogCallPrintf
0x14001614a  mov     r8, [rsp+38h+SourceString]
0x14001614f  jmp     short loc_140016164
0x140016151  mov     rdx, [rsp+38h+SourceString]; SourceString
0x140016156  mov     rcx, rdi; DestinationString
0x140016159  call    cs:__imp_RtlInitAnsiString
0x14001615f  xor     r8d, r8d; P
0x140016162  xor     ebx, ebx
0x140016164  test    r8, r8
0x140016167  jz      short loc_14001617E
0x140016169  mov     rcx, gs:60h
0x140016172  xor     edx, edx; Flags
0x140016174  mov     rcx, [rcx+30h]; HeapHandle
0x140016178  call    cs:__imp_RtlFreeHeap
0x14001617e  mov     eax, ebx
0x140016180  mov     rbx, [rsp+38h+arg_0]
0x140016185  add     rsp, 30h
0x140016189  pop     rdi
0x14001618a  retn
```
