# VfsCheckDirectoryEmpty

- ea: `0x1400061b4`
- end: `0x1400063d4`
- name: `VfsCheckDirectoryEmpty`
- size: `544`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x140005dc8`
- `0x140006064`
- `0x140006104`

## callees

- `0x1400061b4`
- `0x140006a60`
- `0x140008e7c`
- `0x140009368`
- `0x14000d9cc`
- `0x140010aa8`
- `0x140012acc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000638c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014ac0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000638c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014ac0`
- `FLTMGR!FltObjectDereference` at `0x1400063ab`
- `FLTMGR!FltObjectDereference` at `0x140014add`
- `FLTMGR!FltObjectDereference` at `0x1400063ab`
- `FLTMGR!FltObjectDereference` at `0x140014add`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140006367`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140014a9a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140006367`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140014a9a`

## string_xrefs

- `0x14000624d`: `VfsCheckDirectoryEmpty() - Failed to get filename info for fileobject: %p\n IRP: %d\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsCheckDirectoryEmpty(__int64 a1, __int64 a2, char a3, _BYTE *a4)
{
  void *Mapping; // r14
  __int64 v8; // r12
  int FileNameInfoForFileObject; // edi
  struct _FLT_FILE_NAME_INFORMATION *v10; // rsi
  int v11; // eax
  __int64 v12; // rdx
  __int64 v14; // [rsp+20h] [rbp-78h]
  int v15; // [rsp+30h] [rbp-68h]
  PVOID FltObject; // [rsp+38h] [rbp-60h] BYREF
  void *v17; // [rsp+40h] [rbp-58h]
  __int64 v18; // [rsp+48h] [rbp-50h]
  PVOID P[2]; // [rsp+50h] [rbp-48h] BYREF
  UNICODE_STRING Name; // [rsp+60h] [rbp-38h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+B8h] [rbp+20h] BYREF

  FileNameInformation = 0;
  Mapping = 0;
  v17 = 0;
  *(_OWORD *)P = 0;
  FltObject = 0;
  Name = 0;
  v8 = 0;
  *a4 = 0;
  if ( a3 || (*(_DWORD *)(a2 + 4) & 4) != 0 )
  {
    FileNameInfoForFileObject = VfsGetFileNameInfoForFileObject(
                                  a1,
                                  *(_QWORD *)(a2 + 48),
                                  *(_QWORD *)(a2 + 40),
                                  258,
                                  &FileNameInformation);
    v15 = FileNameInfoForFileObject;
    if ( FileNameInfoForFileObject >= 0 )
    {
      FltObject = *(PVOID *)(a2 + 40);
      v10 = FileNameInformation;
      *(UNICODE_STRING *)P = FileNameInformation->Name;
LABEL_11:
      FileNameInfoForFileObject = VfsQueryDirectoryEmpty(
                                    (_DWORD)FltObject,
                                    (unsigned __int64)P
                                  & ((unsigned __int128)-(__int128)(unsigned __int64)FltObject >> 64),
                                    v8,
                                    (unsigned __int64)&Name & -(__int64)(v8 != 0),
                                    (__int64)a4);
      goto LABEL_12;
    }
LABEL_5:
    LODWORD(v14) = *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 4LL);
    LogWrite(
      1,
      0,
      L"VfsCheckDirectoryEmpty() - Failed to get filename info for fileobject: %p\n IRP: %d\n Status: 0x%08X",
      *(_QWORD *)(a2 + 72),
      v14,
      FileNameInfoForFileObject,
      v15);
    v10 = FileNameInformation;
    goto LABEL_12;
  }
  v11 = VfsGetFileNameInfoForFileObject(a1, *(_QWORD *)(a2 + 72), *(_QWORD *)(a2 + 64), 257, &FileNameInformation);
  FileNameInfoForFileObject = v11;
  v15 = v11;
  if ( v11 < 0 )
    goto LABEL_5;
  v10 = FileNameInformation;
  Name = FileNameInformation->Name;
  v8 = *(_QWORD *)(a2 + 64);
  v18 = v8;
  Mapping = (void *)VfsScbGetMapping(*(_QWORD *)(a2 + 24), v12);
  v17 = Mapping;
  if ( Mapping )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(a2 + 24) + 272LL) & 4) == 0 )
      goto LABEL_11;
    FileNameInfoForFileObject = VfsGetUnMappedSource(*(PVOID *)(a2 + 64), (__int64)P, (__int64)&FltObject);
    if ( FileNameInfoForFileObject >= 0 )
      goto LABEL_11;
  }
LABEL_12:
  if ( v10 )
    FltReleaseFileNameInformation(v10);
  if ( Mapping )
  {
    VfsReleaseMappingEntry(Mapping);
    if ( P[1] )
    {
      ExFreePoolWithTag(P[1], 0);
      P[1] = 0;
    }
    if ( FltObject )
      FltObjectDereference(FltObject);
  }
  return (unsigned int)FileNameInfoForFileObject;
}

```

## disassembly

```asm
0x1400061b4  mov     rax, rsp
0x1400061b7  mov     [rax+8], rbx
0x1400061bb  mov     [rax+10h], rsi
0x1400061bf  push    rdi
0x1400061c0  push    r12
0x1400061c2  push    r13
0x1400061c4  push    r14
0x1400061c6  push    r15
0x1400061c8  sub     rsp, 70h
0x1400061cc  mov     r13, r9
0x1400061cf  mov     rbx, rdx
0x1400061d2  mov     rsi, rcx
0x1400061d5  xor     r15d, r15d
0x1400061d8  mov     [rax+20h], r15
0x1400061dc  mov     r14d, r15d
0x1400061df  mov     [rax-58h], r15
0x1400061e3  xorps   xmm0, xmm0
0x1400061e6  movups  xmmword ptr [rax-48h], xmm0
0x1400061ea  mov     [rax-60h], r15
0x1400061ee  xorps   xmm1, xmm1
0x1400061f1  movups  xmmword ptr [rax-38h], xmm1
0x1400061f5  mov     r12d, r15d
0x1400061f8  mov     [r9], r15b
0x1400061fb  test    r8b, r8b
0x1400061fe  jnz     short loc_14000620F
0x140006200  mov     eax, [rdx+4]
0x140006203  test    al, 4
0x140006205  jnz     short loc_14000620F
0x140006207  mov     r8b, r15b
0x14000620a  test    r15b, r15b
0x14000620d  jz      short loc_14000628B
0x14000620f  lea     rax, [rsp+98h+FileNameInformation]
0x140006217  mov     [rsp+98h+var_78], rax
0x14000621c  mov     r9d, 102h
0x140006222  mov     r8, [rdx+28h]
0x140006226  mov     rdx, [rdx+30h]
0x14000622a  call    VfsGetFileNameInfoForFileObject
0x14000622f  mov     edi, eax
0x140006231  mov     [rsp+98h+var_68], eax
0x140006235  test    eax, eax
0x140006237  jns     short loc_14000626B
0x140006239  mov     rax, [rsi+10h]
0x14000623d  movzx   ecx, byte ptr [rax+4]
0x140006241  mov     dword ptr [rsp+98h+var_70], edi
0x140006245  mov     dword ptr [rsp+98h+var_78], ecx
0x140006249  mov     r9, [rbx+48h]
0x14000624d  lea     r8, aVfscheckdirect; "VfsCheckDirectoryEmpty() - Failed to ge"...
0x140006254  xor     edx, edx
0x140006256  lea     ecx, [rdx+1]
0x140006259  call    LogWrite
0x14000625e  mov     rsi, [rsp+98h+FileNameInformation]
0x140006266  jmp     loc_14000635F
0x14000626b  mov     rax, [rbx+28h]
0x14000626f  mov     [rsp+98h+FltObject], rax
0x140006274  mov     rsi, [rsp+98h+FileNameInformation]
0x14000627c  movups  xmm0, xmmword ptr [rsi+8]
0x140006280  movdqu  xmmword ptr [rsp+98h+P], xmm0
0x140006286  jmp     loc_140006325
0x14000628b  lea     rax, [rsp+98h+FileNameInformation]
0x140006293  mov     [rsp+98h+var_78], rax
0x140006298  mov     r9d, 101h
0x14000629e  mov     r8, [rdx+40h]
0x1400062a2  mov     rdx, [rdx+48h]
0x1400062a6  call    VfsGetFileNameInfoForFileObject
0x1400062ab  mov     edi, eax
0x1400062ad  mov     [rsp+98h+var_68], eax
0x1400062b1  test    eax, eax
0x1400062b3  js      short loc_140006239
0x1400062b5  mov     rsi, [rsp+98h+FileNameInformation]
0x1400062bd  movups  xmm0, xmmword ptr [rsi+8]
0x1400062c1  movdqu  [rsp+98h+var_38], xmm0
0x1400062c7  mov     r12, [rbx+40h]
0x1400062cb  mov     [rsp+98h+var_50], r12
0x1400062d0  mov     rcx, [rbx+18h]
0x1400062d4  call    VfsScbGetMapping
0x1400062d9  mov     r14, rax
0x1400062dc  mov     [rsp+98h+var_58], rax
0x1400062e1  test    rax, rax
0x1400062e4  jz      short loc_14000635F
0x1400062e6  mov     rcx, [rbx+18h]
0x1400062ea  mov     r8d, [rcx+110h]
0x1400062f1  test    r8b, 4
0x1400062f5  jz      short loc_140006325
0x1400062f7  lea     rax, [rsp+98h+FltObject]
0x1400062fc  mov     [rsp+98h+var_70], rax; __int64
0x140006301  lea     rax, [rsp+98h+P]
0x140006306  mov     [rsp+98h+var_78], rax; __int64
0x14000630b  mov     r8, r14
0x14000630e  lea     rdx, [rsi+8]
0x140006312  mov     rcx, [rbx+40h]; FltObject
0x140006316  call    VfsGetUnMappedSource
0x14000631b  mov     edi, eax
0x14000631d  mov     [rsp+98h+var_68], eax
0x140006321  test    eax, eax
0x140006323  js      short loc_14000635F
0x140006325  mov     rax, r12
0x140006328  neg     rax
0x14000632b  sbb     r9, r9
0x14000632e  lea     rax, [rsp+98h+var_38]
0x140006333  and     r9, rax
0x140006336  mov     rcx, [rsp+98h+FltObject]
0x14000633b  mov     rax, rcx
0x14000633e  neg     rax
0x140006341  sbb     rdx, rdx
0x140006344  lea     rax, [rsp+98h+P]
0x140006349  and     rdx, rax
0x14000634c  mov     [rsp+98h+var_78], r13
0x140006351  mov     r8, r12
0x140006354  call    VfsQueryDirectoryEmpty
0x140006359  mov     edi, eax
0x14000635b  mov     [rsp+98h+var_68], eax
0x14000635f  test    rsi, rsi
0x140006362  jz      short loc_140006373
0x140006364  mov     rcx, rsi; FileNameInformation
0x140006367  call    cs:__imp_FltReleaseFileNameInformation
0x14000636e  nop     dword ptr [rax+rax+00h]
0x140006373  test    r14, r14
0x140006376  jz      short loc_1400063B7
0x140006378  mov     rcx, r14; P
0x14000637b  call    VfsReleaseMappingEntry
0x140006380  mov     rcx, [rsp+98h+P+8]; P
0x140006385  test    rcx, rcx
0x140006388  jz      short loc_1400063A1
0x14000638a  xor     edx, edx; Tag
0x14000638c  call    cs:__imp_ExFreePoolWithTag
0x140006393  nop     dword ptr [rax+rax+00h]
0x140006398  mov     [rsp+98h+P+8], 0
0x1400063a1  mov     rcx, [rsp+98h+FltObject]; FltObject
0x1400063a6  test    rcx, rcx
0x1400063a9  jz      short loc_1400063B7
0x1400063ab  call    cs:__imp_FltObjectDereference
0x1400063b2  nop     dword ptr [rax+rax+00h]
0x1400063b7  mov     eax, edi
0x1400063b9  lea     r11, [rsp+98h+var_28]
0x1400063be  mov     rbx, [r11+30h]
0x1400063c2  mov     rsi, [r11+38h]
0x1400063c6  mov     rsp, r11
0x1400063c9  pop     r15
0x1400063cb  pop     r14
0x1400063cd  pop     r13
0x1400063cf  pop     r12
0x1400063d1  pop     rdi
0x1400063d2  retn
0x140014a85  push    rbp
0x140014a87  sub     rsp, 30h
0x140014a8b  mov     rbp, rdx
0x140014a8e  mov     rcx, [rbp+0B8h]; FileNameInformation
0x140014a95  test    rcx, rcx
0x140014a98  jz      short loc_140014AA7
0x140014a9a  call    cs:__imp_FltReleaseFileNameInformation
0x140014aa1  nop     dword ptr [rax+rax+00h]
0x140014aa6  nop
0x140014aa7  mov     rcx, [rbp+40h]; P
0x140014aab  test    rcx, rcx
0x140014aae  jz      short loc_140014AEA
0x140014ab0  call    VfsReleaseMappingEntry
0x140014ab5  mov     rcx, [rbp+58h]; P
0x140014ab9  test    rcx, rcx
0x140014abc  jz      short loc_140014AD4
0x140014abe  xor     edx, edx; Tag
0x140014ac0  call    cs:__imp_ExFreePoolWithTag
0x140014ac7  nop     dword ptr [rax+rax+00h]
0x140014acc  mov     qword ptr [rbp+58h], 0
0x140014ad4  mov     rcx, [rbp+38h]; FltObject
0x140014ad8  test    rcx, rcx
0x140014adb  jz      short loc_140014AEA
0x140014add  call    cs:__imp_FltObjectDereference
0x140014ae4  nop     dword ptr [rax+rax+00h]
0x140014ae9  nop
0x140014aea  add     rsp, 30h
0x140014aee  pop     rbp
0x140014aef  retn
```
