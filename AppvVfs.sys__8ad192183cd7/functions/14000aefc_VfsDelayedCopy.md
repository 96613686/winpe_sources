# VfsDelayedCopy

- ea: `0x14000aefc`
- end: `0x14000b116`
- name: `VfsDelayedCopy`
- size: `538`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140005d34`
- `0x140006064`
- `0x14000b1f0`
- `0x14000e18c`

## callees

- `0x140002e90`
- `0x140008c04`
- `0x140009368`
- `0x14000aefc`
- `0x14000d9cc`
- `0x14000fd38`
- `0x140010aa8`
- `0x140012acc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000b0ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014fb9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b0ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014fb9`
- `FLTMGR!FltObjectDereference` at `0x14000b0cf`
- `FLTMGR!FltObjectDereference` at `0x140014f9f`
- `FLTMGR!FltObjectDereference` at `0x14000b0cf`
- `FLTMGR!FltObjectDereference` at `0x140014f9f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000b0bb`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140014f89`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000b0bb`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140014f89`

## string_xrefs

- `0x14000af71`: `VfsDelayedCopy() - Failed to get filename info for fileobject: %p\n IRP: %d\n Status: 0x%08X`
- `0x14000aff3`: `VfsDelayedCopy() - Failed to map filename: %wZ%\n for mapping: %wZ\n Status: 0x%08X`
- `0x14000b045`: `VfsDelayedCopy() - Failed to create parent directories for %wZ\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsDelayedCopy(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 Mapping; // rdi
  void *v7; // rsi
  int FileNameInfoForFileObject; // ebx
  UNICODE_STRING *p_Name; // r12
  int MappedTarget; // eax
  int ParentDirectories; // eax
  __int64 v13; // [rsp+20h] [rbp-98h]
  __int64 v14; // [rsp+20h] [rbp-98h]
  int v15; // [rsp+28h] [rbp-90h]
  __int64 v16; // [rsp+28h] [rbp-90h]
  __int64 v17; // [rsp+68h] [rbp-50h] BYREF
  __int64 v18; // [rsp+70h] [rbp-48h]
  __int64 v19[3]; // [rsp+78h] [rbp-40h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+D8h] [rbp+20h] BYREF

  Mapping = 0;
  v18 = 0;
  FileNameInformation = 0;
  v7 = 0;
  v17 = 0;
  *(_OWORD *)v19 = 0;
  FileNameInfoForFileObject = VfsGetFileNameInfoForFileObject(
                                a1,
                                *(_QWORD *)(a3 + 48),
                                *(_QWORD *)(a3 + 40),
                                257,
                                &FileNameInformation);
  if ( FileNameInfoForFileObject >= 0 )
  {
    Mapping = VfsScbGetMapping(a2);
    v18 = Mapping;
    if ( Mapping )
    {
      p_Name = &FileNameInformation->Name;
      MappedTarget = VfsGetMappedTarget(
                       *(PVOID *)(*(_QWORD *)(a1 + 16) + 16LL),
                       &FileNameInformation->Name.Length,
                       0,
                       Mapping,
                       (__int64)v19,
                       &v17);
      FileNameInfoForFileObject = MappedTarget;
      if ( MappedTarget >= 0 )
      {
        v7 = (void *)v17;
        ParentDirectories = VfsCreateParentDirectories(
                              *(_QWORD *)(a3 + 40),
                              v17,
                              Mapping,
                              (unsigned int)v19,
                              *(_WORD *)(Mapping + 24));
        FileNameInfoForFileObject = ParentDirectories;
        if ( ParentDirectories >= 0 )
        {
          FileNameInfoForFileObject = VfsCowCopyFileForScb(a2, 0, *(struct _FLT_INSTANCE **)(a3 + 40));
          if ( FileNameInfoForFileObject >= 0 && *(int *)(a3 + 32) < 0 )
            FileNameInfoForFileObject = *(_DWORD *)(a3 + 32);
        }
        else
        {
          LODWORD(v14) = ParentDirectories;
          LogWrite(1, 0, L"VfsDelayedCopy() - Failed to create parent directories for %wZ\n Status: 0x%08X", v19, v14);
        }
      }
      else
      {
        LODWORD(v16) = MappedTarget;
        LogWrite(
          1,
          0,
          L"VfsDelayedCopy() - Failed to map filename: %wZ%\n for mapping: %wZ\n Status: 0x%08X",
          p_Name,
          *(_QWORD *)(Mapping + 40),
          v16);
        v7 = (void *)v17;
      }
    }
  }
  else
  {
    v15 = FileNameInfoForFileObject;
    LODWORD(v13) = *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 4LL);
    LogWrite(
      1,
      0,
      L"VfsDelayedCopy() - Failed to get filename info for fileobject: %p\n IRP: %d\n Status: 0x%08X",
      *(_QWORD *)(a3 + 72),
      v13,
      v15);
  }
  if ( Mapping )
    VfsReleaseMappingEntry((PVOID)Mapping);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( v7 )
  {
    FltObjectDereference(v7);
    if ( v19[1] )
      ExFreePoolWithTag((PVOID)v19[1], 0);
  }
  return (unsigned int)FileNameInfoForFileObject;
}

```

## disassembly

```asm
0x14000aefc  mov     rax, rsp
0x14000aeff  mov     [rax+8], rbx
0x14000af03  mov     [rax+10h], rsi
0x14000af07  push    rdi
0x14000af08  push    r12
0x14000af0a  push    r13
0x14000af0c  push    r14
0x14000af0e  push    r15
0x14000af10  sub     rsp, 90h
0x14000af17  mov     r14, r8
0x14000af1a  mov     r13, rdx
0x14000af1d  mov     r15, rcx
0x14000af20  xor     edi, edi
0x14000af22  mov     [rax-48h], rdi
0x14000af26  mov     [rax+20h], rdi
0x14000af2a  xor     esi, esi
0x14000af2c  mov     [rax-50h], rsi
0x14000af30  xorps   xmm0, xmm0
0x14000af33  movups  xmmword ptr [rax-40h], xmm0
0x14000af37  lea     rax, [rax+20h]
0x14000af3b  mov     [rsp+0B8h+var_98], rax
0x14000af40  mov     r9d, 101h
0x14000af46  mov     r8, [r8+28h]
0x14000af4a  mov     rdx, [r14+30h]
0x14000af4e  call    VfsGetFileNameInfoForFileObject
0x14000af53  mov     ebx, eax
0x14000af55  mov     [rsp+0B8h+var_58], eax
0x14000af59  test    eax, eax
0x14000af5b  jns     short loc_14000AF87
0x14000af5d  mov     rax, [r15+10h]
0x14000af61  movzx   ecx, byte ptr [rax+4]
0x14000af65  mov     dword ptr [rsp+0B8h+var_90], ebx
0x14000af69  mov     dword ptr [rsp+0B8h+var_98], ecx
0x14000af6d  mov     r9, [r14+48h]
0x14000af71  lea     r8, aVfsdelayedcopy_1; "VfsDelayedCopy() - Failed to get filena"...
0x14000af78  xor     edx, edx
0x14000af7a  lea     ecx, [rdi+1]
0x14000af7d  call    LogWrite
0x14000af82  jmp     loc_14000B0A1
0x14000af87  mov     rcx, r13
0x14000af8a  call    VfsScbGetMapping
0x14000af8f  mov     rdi, rax
0x14000af92  mov     [rsp+0B8h+var_48], rax
0x14000af97  test    rax, rax
0x14000af9a  jz      loc_14000B0A1
0x14000afa0  mov     r12, [rsp+0B8h+FileNameInformation]
0x14000afa8  add     r12, 8
0x14000afac  mov     rcx, [r15+10h]
0x14000afb0  lea     rax, [rsp+0B8h+var_50]
0x14000afb5  mov     [rsp+0B8h+var_90], rax; __int64
0x14000afba  lea     rax, [rsp+0B8h+var_40]
0x14000afbf  mov     [rsp+0B8h+var_98], rax; __int64
0x14000afc4  mov     r9, rdi
0x14000afc7  xor     r8d, r8d
0x14000afca  mov     rdx, r12
0x14000afcd  mov     rcx, [rcx+10h]; FltObject
0x14000afd1  call    VfsGetMappedTarget
0x14000afd6  mov     ebx, eax
0x14000afd8  mov     [rsp+0B8h+var_58], eax
0x14000afdc  xor     r15d, r15d
0x14000afdf  test    eax, eax
0x14000afe1  jns     short loc_14000B00E
0x14000afe3  mov     dword ptr [rsp+0B8h+var_90], eax
0x14000afe7  mov     rax, [rdi+28h]
0x14000afeb  mov     [rsp+0B8h+var_98], rax
0x14000aff0  mov     r9, r12
0x14000aff3  lea     r8, aVfsdelayedcopy; "VfsDelayedCopy() - Failed to map filena"...
0x14000affa  xor     edx, edx
0x14000affc  lea     ecx, [rdx+1]
0x14000afff  call    LogWrite
0x14000b004  mov     rsi, [rsp+0B8h+var_50]
0x14000b009  jmp     loc_14000B0A1
0x14000b00e  movzx   eax, word ptr [rdi+18h]
0x14000b012  mov     word ptr [rsp+0B8h+var_98], ax
0x14000b017  lea     r9, [rsp+0B8h+var_40]
0x14000b01c  mov     r8, rdi
0x14000b01f  mov     rsi, [rsp+0B8h+var_50]
0x14000b024  mov     rdx, rsi
0x14000b027  mov     rcx, [r14+28h]
0x14000b02b  call    VfsCreateParentDirectories
0x14000b030  mov     ebx, eax
0x14000b032  mov     [rsp+0B8h+var_58], eax
0x14000b036  xor     edx, edx
0x14000b038  test    eax, eax
0x14000b03a  jns     short loc_14000B056
0x14000b03c  mov     dword ptr [rsp+0B8h+var_98], eax
0x14000b040  lea     r9, [rsp+0B8h+var_40]
0x14000b045  lea     r8, aVfsdelayedcopy_0; "VfsDelayedCopy() - Failed to create par"...
0x14000b04c  lea     ecx, [rdx+1]
0x14000b04f  call    LogWrite
0x14000b054  jmp     short loc_14000B0A1
0x14000b056  mov     [rsp+0B8h+var_68], r15
0x14000b05b  mov     [rsp+0B8h+var_70], r15b
0x14000b060  mov     [rsp+0B8h+var_78], 1
0x14000b065  lea     rax, [rsp+0B8h+var_40]
0x14000b06a  mov     [rsp+0B8h+var_80], rax
0x14000b06f  mov     [rsp+0B8h+var_88], r15
0x14000b074  mov     [rsp+0B8h+var_90], rsi
0x14000b079  mov     [rsp+0B8h+var_98], r12
0x14000b07e  mov     r8, [r14+28h]
0x14000b082  mov     rcx, r13
0x14000b085  call    VfsCowCopyFileForScb
0x14000b08a  mov     ebx, eax
0x14000b08c  mov     [rsp+0B8h+var_58], eax
0x14000b090  test    eax, eax
0x14000b092  js      short loc_14000B0A1
0x14000b094  mov     eax, [r14+20h]
0x14000b098  test    eax, eax
0x14000b09a  cmovs   ebx, eax
0x14000b09d  mov     [rsp+0B8h+var_58], ebx
0x14000b0a1  test    rdi, rdi
0x14000b0a4  jz      short loc_14000B0AE
0x14000b0a6  mov     rcx, rdi; P
0x14000b0a9  call    VfsReleaseMappingEntry
0x14000b0ae  mov     rcx, [rsp+0B8h+FileNameInformation]; FileNameInformation
0x14000b0b6  test    rcx, rcx
0x14000b0b9  jz      short loc_14000B0C7
0x14000b0bb  call    cs:__imp_FltReleaseFileNameInformation
0x14000b0c2  nop     dword ptr [rax+rax+00h]
0x14000b0c7  test    rsi, rsi
0x14000b0ca  jz      short loc_14000B0F6
0x14000b0cc  mov     rcx, rsi; FltObject
0x14000b0cf  call    cs:__imp_FltObjectDereference
0x14000b0d6  nop     dword ptr [rax+rax+00h]
0x14000b0db  mov     rcx, [rsp+0B8h+P]; P
0x14000b0e3  test    rcx, rcx
0x14000b0e6  jz      short loc_14000B0F6
0x14000b0e8  xor     edx, edx; Tag
0x14000b0ea  call    cs:__imp_ExFreePoolWithTag
0x14000b0f1  nop     dword ptr [rax+rax+00h]
0x14000b0f6  mov     eax, ebx
0x14000b0f8  lea     r11, [rsp+0B8h+var_28]
0x14000b100  mov     rbx, [r11+30h]
0x14000b104  mov     rsi, [r11+38h]
0x14000b108  mov     rsp, r11
0x14000b10b  pop     r15
0x14000b10d  pop     r14
0x14000b10f  pop     r13
0x14000b111  pop     r12
0x14000b113  pop     rdi
0x14000b114  retn
0x140014f65  push    rbp
0x140014f67  sub     rsp, 60h
0x140014f6b  mov     rbp, rdx
0x140014f6e  mov     rcx, [rbp+70h]; P
0x140014f72  test    rcx, rcx
0x140014f75  jz      short loc_140014F7D
0x140014f77  call    VfsReleaseMappingEntry
0x140014f7c  nop
0x140014f7d  mov     rcx, [rbp+0D8h]; FileNameInformation
0x140014f84  test    rcx, rcx
0x140014f87  jz      short loc_140014F96
0x140014f89  call    cs:__imp_FltReleaseFileNameInformation
0x140014f90  nop     dword ptr [rax+rax+00h]
0x140014f95  nop
0x140014f96  mov     rcx, [rbp+68h]; FltObject
0x140014f9a  test    rcx, rcx
0x140014f9d  jz      short loc_140014FC6
0x140014f9f  call    cs:__imp_FltObjectDereference
0x140014fa6  nop     dword ptr [rax+rax+00h]
0x140014fab  mov     rcx, [rbp+80h]; P
0x140014fb2  test    rcx, rcx
0x140014fb5  jz      short loc_140014FC6
0x140014fb7  xor     edx, edx; Tag
0x140014fb9  call    cs:__imp_ExFreePoolWithTag
0x140014fc0  nop     dword ptr [rax+rax+00h]
0x140014fc5  nop
0x140014fc6  add     rsp, 60h
0x140014fca  pop     rbp
0x140014fcb  retn
```
