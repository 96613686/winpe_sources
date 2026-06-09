# AslFileSecGetEaByPath

- ea: `0x1400341b0`
- end: `0x140034273`
- name: `AslFileSecGetEaByPath`
- size: `195`
- prototype: `__int64 __fastcall(void *, unsigned int *, __int64, const WCHAR *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140029954`
- `0x1400591c4`

## callees

- `0x140033f98`
- `0x1400341b0`
- `0x140034590`
- `0x14003e364`
- `0x140045df8`
- `0x140046074`

## string_xrefs

- `0x1400341e7`: `AslFileMappingCreate failed [%x]`
- `0x1400341f8`: `AslFileSecGetEaByPath`
- `0x140034241`: `AslFileSecGetEaByPath`

## pseudocode

```c
__int64 __fastcall AslFileSecGetEaByPath(void *a1, unsigned int *a2, __int64 a3, const WCHAR *a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  char *FileHandle; // rax
  __int64 v9; // r8
  int EaByHandle; // eax
  PVOID P; // [rsp+50h] [rbp+18h] BYREF

  P = 0;
  v6 = AslFileMappingCreate((__int64 *)&P, a4, 0);
  v7 = v6;
  if ( v6 >= 0 )
  {
    FileHandle = (char *)AslFileMappingGetFileHandle(P);
    EaByHandle = AslFileSecGetEaByHandle(a1, a2, v9, FileHandle);
    v7 = EaByHandle;
    if ( EaByHandle >= 0 )
    {
      v7 = 0;
    }
    else if ( EaByHandle != -1073741275 )
    {
      AslLogCallPrintf(1, "AslFileSecGetEaByPath", 174, "AslFileSecGetEaByHandle failed [%x]", EaByHandle);
    }
    AslFileMappingDelete((PVOID *)P);
  }
  else
  {
    AslLogCallPrintf(1, "AslFileSecGetEaByPath", 167, "AslFileMappingCreate failed [%x]", v6);
  }
  return v7;
}

```

## disassembly

```asm
0x1400341b0  mov     rax, rsp
0x1400341b3  mov     [rax+8], rbx
0x1400341b7  mov     [rax+10h], rsi
0x1400341bb  mov     [rax+18h], r8
0x1400341bf  push    rdi
0x1400341c0  sub     rsp, 30h
0x1400341c4  mov     rdi, rdx
0x1400341c7  mov     qword ptr [rax+18h], 0
0x1400341cf  mov     rsi, rcx
0x1400341d2  mov     rdx, r9
0x1400341d5  lea     rcx, [rax+18h]
0x1400341d9  xor     r8d, r8d
0x1400341dc  call    AslFileMappingCreate
0x1400341e1  mov     ebx, eax
0x1400341e3  test    eax, eax
0x1400341e5  jns     short loc_14003420B
0x1400341e7  lea     r9, aAslfilemapping_5; "AslFileMappingCreate failed [%x]"
0x1400341ee  mov     [rsp+38h+var_18], eax
0x1400341f2  mov     r8d, 0A7h
0x1400341f8  lea     rdx, aAslfilesecgete_0; "AslFileSecGetEaByPath"
0x1400341ff  mov     ecx, 1
0x140034204  call    AslLogCallPrintf
0x140034209  jmp     short loc_140034260
0x14003420b  mov     rcx, [rsp+38h+P]
0x140034210  call    AslFileMappingGetFileHandle
0x140034215  mov     r9, rax
0x140034218  mov     rdx, rdi
0x14003421b  mov     rcx, rsi; void *
0x14003421e  call    AslFileSecGetEaByHandle
0x140034223  mov     ebx, eax
0x140034225  test    eax, eax
0x140034227  jns     short loc_140034254
0x140034229  cmp     eax, 0C0000225h
0x14003422e  jz      short loc_140034256
0x140034230  lea     r9, aAslfilesecgete_1; "AslFileSecGetEaByHandle failed [%x]"
0x140034237  mov     [rsp+38h+var_18], eax
0x14003423b  mov     r8d, 0AEh
0x140034241  lea     rdx, aAslfilesecgete_0; "AslFileSecGetEaByPath"
0x140034248  mov     ecx, 1
0x14003424d  call    AslLogCallPrintf
0x140034252  jmp     short loc_140034256
0x140034254  xor     ebx, ebx
0x140034256  mov     rcx, [rsp+38h+P]; P
0x14003425b  call    AslFileMappingDelete
0x140034260  mov     rsi, [rsp+38h+arg_8]
0x140034265  mov     eax, ebx
0x140034267  mov     rbx, [rsp+38h+arg_0]
0x14003426c  add     rsp, 30h
0x140034270  pop     rdi
0x140034271  retn
```
