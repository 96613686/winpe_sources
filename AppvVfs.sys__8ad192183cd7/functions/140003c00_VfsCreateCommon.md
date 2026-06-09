# VfsCreateCommon

- ea: `0x140003c00`
- end: `0x140003f1d`
- name: `VfsCreateCommon`
- size: `797`
- prototype: `__int64 __fastcall(int, int, struct _FLT_CALLBACK_DATA *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140001380`

## callees

- `0x140003c00`
- `0x14000414c`
- `0x140004484`
- `0x140004598`
- `0x1400046bc`
- `0x1400049b4`
- `0x140004d1c`
- `0x14000502c`
- `0x140009368`
- `0x14000f124`
- `0x140010bac`
- `0x140012acc`
- `0x140014000`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140003ef1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400148e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003ef1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400148e3`
- `FLTMGR!FltObjectDereference` at `0x140003ed6`
- `FLTMGR!FltObjectDereference` at `0x1400148c9`
- `FLTMGR!FltObjectDereference` at `0x140003ed6`
- `FLTMGR!FltObjectDereference` at `0x1400148c9`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003eae`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400148a1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003eae`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400148a1`

## string_xrefs

- `0x140003cc9`: `VfsCreateCommon() - Failed to get filename info for data: %p\n IRP: %d\n Status: 0x%08X`
- `0x140003d32`: `VfsCreateCommon() - Failed to create context setup for file: %wZ\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsCreateCommon(int a1, int a2, struct _FLT_CALLBACK_DATA *a3, __int64 a4, _QWORD *a5)
{
  unsigned int v8; // esi
  __int64 v9; // r14
  int FileNameInformation; // ebx
  int ContextSetup; // eax
  PFLT_IO_PARAMETER_BLOCK Iopb; // r8
  unsigned int FsInformationClass_high; // edx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  _QWORD *v17; // r15
  __int64 v19; // [rsp+20h] [rbp-A8h]
  __int64 v20; // [rsp+20h] [rbp-A8h]
  PVOID v21[10]; // [rsp+50h] [rbp-78h] BYREF
  int v22; // [rsp+E8h] [rbp+20h] BYREF

  v8 = 1;
  v9 = *(_QWORD *)(*(_QWORD *)(a4 + 32) + 64LL);
  v22 = 0;
  memset(v21, 0, sizeof(v21));
  *a5 = 0;
  if ( v9 )
    VfsDecodeFileObject(v9, 0, 0);
  FileNameInformation = VfsGetFileNameInformation(a3, 0);
  if ( FileNameInformation < 0 )
  {
    LODWORD(v19) = a3->Iopb->MajorFunction;
    LogWrite(
      1,
      0,
      L"VfsCreateCommon() - Failed to get filename info for data: %p\n IRP: %d\n Status: 0x%08X",
      a3,
      v19,
      FileNameInformation);
    goto LABEL_33;
  }
  ContextSetup = VfsCreateContextSetup(a2, a1, (_DWORD)a3, 24, 8, 56, (__int64)v21);
  FileNameInformation = ContextSetup;
  if ( ContextSetup < 0 )
  {
    if ( ContextSetup != -1073741773 )
    {
      LODWORD(v20) = ContextSetup;
      LogWrite(1, 0, L"VfsCreateCommon() - Failed to create context setup for file: %wZ\n Status: 0x%08X", 8, v20);
    }
    goto LABEL_33;
  }
  FileNameInformation = VfsCreateContextValidate(a3, v21, &v22);
  if ( FileNameInformation < 0 )
    goto LABEL_33;
  if ( v22 == 1 )
    goto LABEL_29;
  Iopb = a3->Iopb;
  FsInformationClass_high = HIBYTE(Iopb->Parameters.SetVolumeInformation.FsInformationClass);
  if ( FsInformationClass_high <= 5 )
  {
    v14 = 41;
    if ( _bittest(&v14, FsInformationClass_high) )
    {
      if ( (WORD2(v21[9]) & 0x200) != 0 || (BYTE4(v21[9]) & 0xC0) == 0 )
      {
        FsInformationClass_high = 2;
      }
      else
      {
        v15 = 4;
        if ( FsInformationClass_high == 3 )
          v15 = 1;
        FsInformationClass_high = v15;
      }
    }
  }
  if ( (Iopb->OperationFlags & 4) != 0 )
  {
    v16 = VfsCreateForOpenTargetDirectory(a3);
LABEL_25:
    FileNameInformation = v16;
    goto LABEL_27;
  }
  switch ( FsInformationClass_high )
  {
    case 1u:
      v16 = VfsCreateForOpen(a3);
      goto LABEL_25;
    case 4u:
      v16 = VfsCreateForOverwrite(a3);
      goto LABEL_25;
    case 2u:
      v16 = VfsCreateForCreate(a3);
      goto LABEL_25;
  }
  FileNameInformation = -1073741811;
LABEL_27:
  if ( FileNameInformation < 0 )
    goto LABEL_33;
  if ( v22 == 1 )
  {
LABEL_29:
    v17 = a5;
    FileNameInformation = VfsCreateCompletionContext(a3, v21, 0, a5);
    if ( FileNameInformation >= 0 )
      v8 = *v17 == 0;
    goto LABEL_33;
  }
  v8 = 4;
  if ( v22 == 2 )
  {
    a3->IoStatus.Status = 260;
    a3->IoStatus.Information = 0;
  }
LABEL_33:
  if ( FileNameInformation < 0 )
  {
    a3->IoStatus.Status = FileNameInformation;
    a3->IoStatus.Information = 0;
    v8 = 4;
  }
  if ( v21[2] )
    VfsReleaseMappingEntry(v21[2]);
  if ( v21[6] )
  {
    FltObjectDereference(v21[6]);
    if ( v21[8] )
      ExFreePoolWithTag(v21[8], 0);
  }
  return v8;
}

```

## disassembly

```asm
0x140003c00  mov     r11, rsp
0x140003c03  mov     [r11+8], rbx
0x140003c07  mov     [r11+10h], rsi
0x140003c0b  mov     [r11+18h], r8
0x140003c0f  push    rdi
0x140003c10  push    r12
0x140003c12  push    r13
0x140003c14  push    r14
0x140003c16  push    r15
0x140003c18  sub     rsp, 0A0h
0x140003c1f  mov     rdi, r8
0x140003c22  mov     r12, rdx
0x140003c25  mov     r13, rcx
0x140003c28  mov     [rsp+0C8h+var_88], 0
0x140003c30  mov     esi, 1
0x140003c35  mov     qword ptr [r11-80h], 0
0x140003c3d  mov     rax, [r9+20h]
0x140003c41  mov     r14, [rax+40h]
0x140003c45  mov     dword ptr [r11+20h], 0
0x140003c4d  xor     edx, edx; Val
0x140003c4f  lea     r8d, [rsi+4Fh]; Size
0x140003c53  lea     rcx, [r11-78h]; void *
0x140003c57  call    memset
0x140003c5c  mov     rax, [rsp+0C8h+arg_20]
0x140003c64  mov     qword ptr [rax], 0
0x140003c6b  mov     ebx, 102h
0x140003c70  mov     [rsp+0C8h+var_84], ebx
0x140003c74  test    r14, r14
0x140003c77  jz      short loc_140003C94
0x140003c79  xor     r8d, r8d
0x140003c7c  xor     edx, edx
0x140003c7e  mov     rcx, r14
0x140003c81  call    VfsDecodeFileObject
0x140003c86  mov     ecx, 1000102h
0x140003c8b  test    al, al
0x140003c8d  cmovnz  ebx, ecx
0x140003c90  mov     [rsp+0C8h+var_84], ebx
0x140003c94  mov     [rsp+0C8h+var_A8], 0; __int64
0x140003c9d  lea     r8, [rsp+0C8h+FileNameInformation]
0x140003ca2  mov     edx, ebx
0x140003ca4  mov     rcx, rdi; CallbackData
0x140003ca7  call    VfsGetFileNameInformation
0x140003cac  mov     ebx, eax
0x140003cae  mov     [rsp+0C8h+var_88], eax
0x140003cb2  test    eax, eax
0x140003cb4  jns     short loc_140003CE3
0x140003cb6  mov     rax, [rdi+10h]
0x140003cba  movzx   ecx, byte ptr [rax+4]
0x140003cbe  mov     dword ptr [rsp+0C8h+var_A0], ebx
0x140003cc2  mov     dword ptr [rsp+0C8h+var_A8], ecx
0x140003cc6  mov     r9, rdi
0x140003cc9  lea     r8, aVfscreatecommo_0; "VfsCreateCommon() - Failed to get filen"...
0x140003cd0  xor     edx, edx
0x140003cd2  mov     ecx, esi
0x140003cd4  call    LogWrite
0x140003cd9  mov     r14, [rsp+0C8h+FileNameInformation]
0x140003cde  jmp     loc_140003E92
0x140003ce3  mov     r14, [rsp+0C8h+FileNameInformation]
0x140003ce8  lea     r15, [r14+8]
0x140003cec  lea     rax, [r14+38h]
0x140003cf0  lea     r9, [r14+18h]
0x140003cf4  lea     rcx, [rsp+0C8h+var_78]
0x140003cf9  mov     [rsp+0C8h+var_98], rcx
0x140003cfe  mov     [rsp+0C8h+var_A0], rax
0x140003d03  mov     [rsp+0C8h+var_A8], r15
0x140003d08  mov     r8, rdi
0x140003d0b  mov     rdx, r13
0x140003d0e  mov     rcx, r12
0x140003d11  call    VfsCreateContextSetup
0x140003d16  mov     ebx, eax
0x140003d18  mov     [rsp+0C8h+var_88], eax
0x140003d1c  test    eax, eax
0x140003d1e  jns     short loc_140003D47
0x140003d20  cmp     eax, 0C0000033h
0x140003d25  jz      loc_140003E92
0x140003d2b  mov     dword ptr [rsp+0C8h+var_A8], eax
0x140003d2f  mov     r9, r15
0x140003d32  lea     r8, aVfscreatecommo; "VfsCreateCommon() - Failed to create co"...
0x140003d39  xor     edx, edx
0x140003d3b  mov     ecx, esi
0x140003d3d  call    LogWrite
0x140003d42  jmp     loc_140003E92
0x140003d47  lea     r8, [rsp+0C8h+arg_18]
0x140003d4f  lea     rdx, [rsp+0C8h+var_78]
0x140003d54  mov     rcx, rdi
0x140003d57  call    VfsCreateContextValidate
0x140003d5c  mov     ebx, eax
0x140003d5e  mov     [rsp+0C8h+var_88], eax
0x140003d62  test    eax, eax
0x140003d64  js      loc_140003E92
0x140003d6a  cmp     [rsp+0C8h+arg_18], esi
0x140003d71  jz      loc_140003E44
0x140003d77  mov     r8, [rdi+10h]
0x140003d7b  movzx   edx, byte ptr [r8+23h]
0x140003d80  cmp     edx, 5
0x140003d83  ja      short loc_140003DBA
0x140003d85  mov     eax, 29h ; ')'
0x140003d8a  bt      eax, edx
0x140003d8d  jnb     short loc_140003DBA
0x140003d8f  mov     eax, [rsp+0C8h+var_2C]
0x140003d96  test    al, 0C0h
0x140003d98  setz    cl
0x140003d9b  bt      eax, 9
0x140003d9f  setb    al
0x140003da2  or      cl, al
0x140003da4  jz      short loc_140003DAD
0x140003da6  mov     edx, 2
0x140003dab  jmp     short loc_140003DBA
0x140003dad  mov     eax, 4
0x140003db2  cmp     edx, 3
0x140003db5  cmovz   eax, esi
0x140003db8  mov     edx, eax
0x140003dba  mov     al, [r8+6]
0x140003dbe  test    al, 4
0x140003dc0  jz      short loc_140003DD9
0x140003dc2  lea     r8, [rsp+0C8h+arg_18]
0x140003dca  lea     rdx, [rsp+0C8h+var_78]
0x140003dcf  mov     rcx, rdi; CallbackData
0x140003dd2  call    VfsCreateForOpenTargetDirectory
0x140003dd7  jmp     short loc_140003E2A
0x140003dd9  cmp     edx, esi
0x140003ddb  jnz     short loc_140003DF4
0x140003ddd  lea     r8, [rsp+0C8h+arg_18]
0x140003de5  lea     rdx, [rsp+0C8h+var_78]
0x140003dea  mov     rcx, rdi; CallbackData
0x140003ded  call    VfsCreateForOpen
0x140003df2  jmp     short loc_140003E2A
0x140003df4  cmp     edx, 4
0x140003df7  jnz     short loc_140003E10
0x140003df9  lea     r8, [rsp+0C8h+arg_18]
0x140003e01  lea     rdx, [rsp+0C8h+var_78]
0x140003e06  mov     rcx, rdi; CallbackData
0x140003e09  call    VfsCreateForOverwrite
0x140003e0e  jmp     short loc_140003E2A
0x140003e10  cmp     edx, 2
0x140003e13  jnz     short loc_140003E2E
0x140003e15  lea     r8, [rsp+0C8h+arg_18]
0x140003e1d  lea     rdx, [rsp+0C8h+var_78]
0x140003e22  mov     rcx, rdi; CallbackData
0x140003e25  call    VfsCreateForCreate
0x140003e2a  mov     ebx, eax
0x140003e2c  jmp     short loc_140003E33
0x140003e2e  mov     ebx, 0C000000Dh
0x140003e33  mov     [rsp+0C8h+var_88], ebx
0x140003e37  test    ebx, ebx
0x140003e39  js      short loc_140003E92
0x140003e3b  cmp     [rsp+0C8h+arg_18], esi
0x140003e42  jnz     short loc_140003E74
0x140003e44  mov     r15, [rsp+0C8h+arg_20]
0x140003e4c  mov     r9, r15
0x140003e4f  mov     r8, r14
0x140003e52  lea     rdx, [rsp+0C8h+var_78]
0x140003e57  mov     rcx, rdi
0x140003e5a  call    VfsCreateCompletionContext
0x140003e5f  mov     ebx, eax
0x140003e61  mov     [rsp+0C8h+var_88], eax
0x140003e65  test    eax, eax
0x140003e67  js      short loc_140003E92
0x140003e69  xor     esi, esi
0x140003e6b  cmp     [r15], rsi
0x140003e6e  setz    sil
0x140003e72  jmp     short loc_140003E92
0x140003e74  mov     esi, 4
0x140003e79  cmp     [rsp+0C8h+arg_18], 2
0x140003e81  jnz     short loc_140003E92
0x140003e83  mov     dword ptr [rdi+18h], 104h
0x140003e8a  mov     qword ptr [rdi+20h], 0
0x140003e92  test    ebx, ebx
0x140003e94  jns     short loc_140003EA6
0x140003e96  mov     [rdi+18h], ebx
0x140003e99  mov     qword ptr [rdi+20h], 0
0x140003ea1  mov     esi, 4
0x140003ea6  test    r14, r14
0x140003ea9  jz      short loc_140003EBA
0x140003eab  mov     rcx, r14; FileNameInformation
0x140003eae  call    cs:__imp_FltReleaseFileNameInformation
0x140003eb5  nop     dword ptr [rax+rax+00h]
0x140003eba  mov     rcx, [rsp+0C8h+var_68]; P
0x140003ebf  test    rcx, rcx
0x140003ec2  jz      short loc_140003EC9
0x140003ec4  call    VfsReleaseMappingEntry
0x140003ec9  mov     rcx, [rsp+0C8h+FltObject]; FltObject
0x140003ed1  test    rcx, rcx
0x140003ed4  jz      short loc_140003EFD
0x140003ed6  call    cs:__imp_FltObjectDereference
0x140003edd  nop     dword ptr [rax+rax+00h]
0x140003ee2  mov     rcx, [rsp+0C8h+P]; P
0x140003eea  test    rcx, rcx
0x140003eed  jz      short loc_140003EFD
0x140003eef  xor     edx, edx; Tag
0x140003ef1  call    cs:__imp_ExFreePoolWithTag
0x140003ef8  nop     dword ptr [rax+rax+00h]
0x140003efd  mov     eax, esi
0x140003eff  lea     r11, [rsp+0C8h+var_28]
0x140003f07  mov     rbx, [r11+30h]
0x140003f0b  mov     rsi, [r11+38h]
0x140003f0f  mov     rsp, r11
0x140003f12  pop     r15
0x140003f14  pop     r14
0x140003f16  pop     r13
0x140003f18  pop     r12
0x140003f1a  pop     rdi
0x140003f1b  retn
0x140014876  push    rbp
0x140014878  sub     rsp, 40h
0x14001487c  mov     rbp, rdx
0x14001487f  mov     ecx, [rbp+40h]
0x140014882  test    ecx, ecx
0x140014884  jns     short loc_140014898
0x140014886  mov     rax, [rbp+0E0h]
0x14001488d  mov     [rax+18h], ecx
0x140014890  mov     qword ptr [rax+20h], 0
0x140014898  mov     rcx, [rbp+48h]; FileNameInformation
0x14001489c  test    rcx, rcx
0x14001489f  jz      short loc_1400148AE
0x1400148a1  call    cs:__imp_FltReleaseFileNameInformation
0x1400148a8  nop     dword ptr [rax+rax+00h]
0x1400148ad  nop
0x1400148ae  mov     rcx, [rbp+60h]; P
0x1400148b2  test    rcx, rcx
0x1400148b5  jz      short loc_1400148BD
0x1400148b7  call    VfsReleaseMappingEntry
0x1400148bc  nop
0x1400148bd  mov     rcx, [rbp+80h]; FltObject
0x1400148c4  test    rcx, rcx
0x1400148c7  jz      short loc_1400148F0
0x1400148c9  call    cs:__imp_FltObjectDereference
0x1400148d0  nop     dword ptr [rax+rax+00h]
0x1400148d5  mov     rcx, [rbp+90h]; P
0x1400148dc  test    rcx, rcx
0x1400148df  jz      short loc_1400148F0
0x1400148e1  xor     edx, edx; Tag
0x1400148e3  call    cs:__imp_ExFreePoolWithTag
0x1400148ea  nop     dword ptr [rax+rax+00h]
0x1400148ef  nop
0x1400148f0  add     rsp, 40h
0x1400148f4  pop     rbp
0x1400148f5  retn
```
