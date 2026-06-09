# AslFileSecSetEaByPath

- ea: `0x140034418`
- end: `0x1400344c5`
- name: `AslFileSecSetEaByPath`
- size: `173`
- prototype: `__int64 __fastcall(__int64, _OWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140029954`

## callees

- `0x14003427c`
- `0x140034418`
- `0x140034590`
- `0x14003e364`
- `0x140045df8`
- `0x140046074`

## string_xrefs

- `0x140034448`: `AslFileMappingCreate failed [%x]`
- `0x140034459`: `AslFileSecSetEaByPath`
- `0x140034498`: `AslFileSecSetEaByPath`

## pseudocode

```c
__int64 __fastcall AslFileSecSetEaByPath(__int64 a1, _OWORD *a2, __int64 a3, __int64 a4)
{
  int v5; // eax
  unsigned int v6; // ebx
  char *FileHandle; // rax
  void *v8; // rcx
  __int64 v9; // r8
  int v10; // eax
  PVOID P; // [rsp+40h] [rbp+8h] BYREF

  P = 0;
  v5 = AslFileMappingCreate(&P, a4, 0);
  v6 = v5;
  if ( v5 >= 0 )
  {
    FileHandle = (char *)AslFileMappingGetFileHandle(P);
    v10 = AslFileSecSetEaByHandle(v8, a2, v9, FileHandle);
    v6 = v10;
    if ( v10 >= 0 )
      v6 = 0;
    else
      AslLogCallPrintf(1, "AslFileSecSetEaByPath", 510, "AslFileSecSetEaByHandle failed [%x]", v10);
    AslFileMappingDelete(P);
  }
  else
  {
    AslLogCallPrintf(1, "AslFileSecSetEaByPath", 504, "AslFileMappingCreate failed [%x]", v5);
  }
  return v6;
}

```

## disassembly

```asm
0x140034418  mov     rax, rsp
0x14003441b  mov     [rax+10h], rbx
0x14003441f  mov     [rax+8], rcx
0x140034423  push    rdi
0x140034424  sub     rsp, 30h
0x140034428  mov     rdi, rdx
0x14003442b  mov     qword ptr [rax+8], 0
0x140034433  mov     rdx, r9
0x140034436  lea     rcx, [rax+8]
0x14003443a  xor     r8d, r8d
0x14003443d  call    AslFileMappingCreate
0x140034442  mov     ebx, eax
0x140034444  test    eax, eax
0x140034446  jns     short loc_14003446C
0x140034448  lea     r9, aAslfilemapping_5; "AslFileMappingCreate failed [%x]"
0x14003444f  mov     [rsp+38h+var_18], eax
0x140034453  mov     r8d, 1F8h
0x140034459  lea     rdx, aAslfilesecsete_1; "AslFileSecSetEaByPath"
0x140034460  mov     ecx, 1
0x140034465  call    AslLogCallPrintf
0x14003446a  jmp     short loc_1400344B7
0x14003446c  mov     rcx, [rsp+38h+P]
0x140034471  call    AslFileMappingGetFileHandle
0x140034476  mov     r9, rax
0x140034479  mov     rdx, rdi
0x14003447c  call    AslFileSecSetEaByHandle
0x140034481  mov     ebx, eax
0x140034483  test    eax, eax
0x140034485  jns     short loc_1400344AB
0x140034487  lea     r9, aAslfilesecsete_0; "AslFileSecSetEaByHandle failed [%x]"
0x14003448e  mov     [rsp+38h+var_18], eax
0x140034492  mov     r8d, 1FEh
0x140034498  lea     rdx, aAslfilesecsete_1; "AslFileSecSetEaByPath"
0x14003449f  mov     ecx, 1
0x1400344a4  call    AslLogCallPrintf
0x1400344a9  jmp     short loc_1400344AD
0x1400344ab  xor     ebx, ebx
0x1400344ad  mov     rcx, [rsp+38h+P]; P
0x1400344b2  call    AslFileMappingDelete
0x1400344b7  mov     eax, ebx
0x1400344b9  mov     rbx, [rsp+38h+arg_8]
0x1400344be  add     rsp, 30h
0x1400344c2  pop     rdi
0x1400344c3  retn
```
