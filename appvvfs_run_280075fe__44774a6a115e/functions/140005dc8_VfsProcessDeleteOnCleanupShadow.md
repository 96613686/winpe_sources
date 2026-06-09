# VfsProcessDeleteOnCleanupShadow

- ea: `0x140005dc8`
- end: `0x14000605e`
- name: `VfsProcessDeleteOnCleanupShadow`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1400018c4`

## callees

- `0x140002080`
- `0x140005dc8`
- `0x1400061b4`
- `0x14000f7ac`
- `0x14000fa88`
- `0x140010aa8`
- `0x140012acc`

## import_xrefs

- `FLTMGR!FltSetInformationFile` at `0x140005e68`
- `FLTMGR!FltSetInformationFile` at `0x140005e68`
- `FLTMGR!FltClose` at `0x140005f28`
- `FLTMGR!FltClose` at `0x140005f28`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140006038`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140014a55`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140006038`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140014a55`
- `FLTMGR!FltReleaseContext` at `0x140006023`
- `FLTMGR!FltReleaseContext` at `0x140006023`

## string_xrefs

- `0x140006011`: `VfsDelayMarkFileDeleted() - Failed to get stream context for fileobject: %p\n Status: 0x%08X`
- `0x140005e2c`: `VfsMoveDeleteoncloseToScb() - Failed to check directory empty. Status: 0x%08X`
- `0x140005f07`: `VfsProcessDeleteOnCleanupShadow() - Failed to get filename info for fileobject: %p\n IRP: %d\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsProcessDeleteOnCleanupShadow(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // eax
  char v7; // r14
  int v8; // eax
  bool v10; // r14
  int FileNameInfoForFileObject; // eax
  unsigned int v12; // r15d
  struct _FLT_FILE_NAME_INFORMATION *v13; // rsi
  struct _FLT_INSTANCE *v14; // rcx
  __int64 v15; // rax
  int StreamContext; // eax
  PFLT_CONTEXT v17; // rcx
  FILE_INFORMATION_CLASS FileInformationClass[2]; // [rsp+20h] [rbp-48h]
  char FileInformation; // [rsp+78h] [rbp+10h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+80h] [rbp+18h] BYREF
  PFLT_CONTEXT Context; // [rsp+88h] [rbp+20h]

  FileNameInformation = 0;
  if ( (*(_DWORD *)(a3 + 4) & 0x40) == 0 )
    goto LABEL_12;
  v6 = *(_DWORD *)(a2 + 272);
  if ( (v6 & 8) != 0 )
    goto LABEL_12;
  if ( (v6 & 2) == 0 )
  {
    FileInformation = 1;
    FltSetInformationFile(
      *(PFLT_INSTANCE *)(a3 + 64),
      *(PFILE_OBJECT *)(a3 + 72),
      &FileInformation,
      1u,
      FileDispositionInformation);
LABEL_9:
    v7 = 1;
    goto LABEL_10;
  }
  v7 = 0;
  FileInformation = 0;
  v8 = VfsCheckDirectoryEmpty(a1, a3, 0, &FileInformation);
  if ( v8 < 0 )
  {
    LogWrite(1, 0, L"VfsMoveDeleteoncloseToScb() - Failed to check directory empty. Status: 0x%08X", (unsigned int)v8);
    goto LABEL_10;
  }
  if ( FileInformation )
    goto LABEL_9;
LABEL_10:
  if ( v7 )
    _InterlockedOr((volatile signed __int32 *)(a2 + 272), 8u);
LABEL_12:
  if ( *(_DWORD *)(a2 + 280) || (*(_BYTE *)(a2 + 272) & 0xC) != 0xC )
    return 0;
  if ( !*(_QWORD *)(a3 + 80) )
    return 3221225701LL;
  v10 = 0;
  FileInformation = 0;
  FileNameInfoForFileObject = VfsGetFileNameInfoForFileObject(
                                a1,
                                *(_QWORD *)(a3 + 72),
                                *(_QWORD *)(a3 + 64),
                                257,
                                &FileNameInformation);
  v12 = FileNameInfoForFileObject;
  if ( FileNameInfoForFileObject >= 0 )
  {
    FltClose(*(HANDLE *)(a3 + 80));
    *(_QWORD *)(a3 + 80) = 0;
    v14 = *(struct _FLT_INSTANCE **)(a3 + 64);
    if ( (*(_DWORD *)(a2 + 272) & 2) != 0 )
    {
      v13 = FileNameInformation;
      v10 = (int)VfsMarkFileDeleted(v14, 1) < 0;
    }
    else
    {
      VfsCheckFileDeleted(v14, *(_QWORD *)(a3 + 72), &FileInformation);
      v13 = FileNameInformation;
      if ( FileInformation )
        VfsMarkFileDeleted(*(PFLT_INSTANCE *)(a3 + 64), 1);
      else
        v10 = 1;
    }
    if ( v10 )
    {
      v15 = *(_QWORD *)(a3 + 24);
      if ( (*(_DWORD *)(v15 + 272) & 1) != 0 )
      {
        Context = 0;
        StreamContext = VfsGetStreamContext(*(PFLT_INSTANCE *)(a3 + 64), *(PFILE_OBJECT *)(a3 + 72));
        v17 = Context;
        _InterlockedOr((volatile signed __int32 *)Context + 1, 4u);
        if ( StreamContext >= 0 )
        {
          FltReleaseContext(v17);
        }
        else
        {
          FileInformationClass[0] = StreamContext;
          LogWrite(
            1,
            0,
            L"VfsDelayMarkFileDeleted() - Failed to get stream context for fileobject: %p\n Status: 0x%08X",
            *(_QWORD *)(a3 + 72),
            *(_QWORD *)FileInformationClass);
        }
      }
      else
      {
        _InterlockedOr((volatile signed __int32 *)(*(_QWORD *)(v15 + 128) + 4LL), 4u);
      }
    }
  }
  else
  {
    FileInformationClass[0] = *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 4LL);
    LogWrite(
      1,
      0,
      L"VfsProcessDeleteOnCleanupShadow() - Failed to get filename info for fileobject: %p\n IRP: %d\n Status: 0x%08X",
      *(_QWORD *)(a3 + 72),
      *(_QWORD *)FileInformationClass,
      FileNameInfoForFileObject,
      0);
    v13 = FileNameInformation;
  }
  if ( v13 )
    FltReleaseFileNameInformation(v13);
  return v12;
}

```

## disassembly

```asm
0x140005dc8  mov     r11, rsp
0x140005dcb  mov     [r11+8], rbx
0x140005dcf  push    rsi
0x140005dd0  push    rdi
0x140005dd1  push    r13
0x140005dd3  push    r14
0x140005dd5  push    r15
0x140005dd7  sub     rsp, 40h
0x140005ddb  mov     rdi, r8
0x140005dde  mov     rsi, rdx
0x140005de1  mov     r13, rcx
0x140005de4  mov     qword ptr [r11+18h], 0
0x140005dec  mov     eax, [r8+4]
0x140005df0  test    al, 40h
0x140005df2  jz      loc_140005E86
0x140005df8  mov     eax, [rdx+110h]
0x140005dfe  test    al, 8
0x140005e00  jnz     loc_140005E86
0x140005e06  test    al, 2
0x140005e08  jz      short loc_140005E47
0x140005e0a  xor     r14b, r14b
0x140005e0d  mov     [r11+10h], r14b
0x140005e11  lea     r9, [r11+10h]
0x140005e15  xor     r8d, r8d
0x140005e18  mov     rdx, rdi
0x140005e1b  call    VfsCheckDirectoryEmpty
0x140005e20  mov     ebx, 1
0x140005e25  test    eax, eax
0x140005e27  jns     short loc_140005E3E
0x140005e29  mov     r9d, eax
0x140005e2c  lea     r8, aVfsmovedeleteo; "VfsMoveDeleteoncloseToScb() - Failed to"...
0x140005e33  xor     edx, edx
0x140005e35  mov     ecx, ebx
0x140005e37  call    LogWrite
0x140005e3c  jmp     short loc_140005E77
0x140005e3e  cmp     [rsp+68h+FileInformation], r14b
0x140005e43  jnz     short loc_140005E74
0x140005e45  jmp     short loc_140005E77
0x140005e47  mov     ebx, 1
0x140005e4c  mov     [rsp+68h+FileInformation], bl
0x140005e50  mov     [rsp+68h+FileInformationClass], 0Dh; FileInformationClass
0x140005e58  mov     r9d, ebx; Length
0x140005e5b  lea     r8, [rsp+68h+FileInformation]; FileInformation
0x140005e60  mov     rdx, [rdi+48h]; FileObject
0x140005e64  mov     rcx, [rdi+40h]; Instance
0x140005e68  call    cs:__imp_FltSetInformationFile
0x140005e6f  nop     dword ptr [rax+rax+00h]
0x140005e74  mov     r14b, bl
0x140005e77  test    r14b, r14b
0x140005e7a  jz      short loc_140005E8B
0x140005e7c  lock or dword ptr [rsi+110h], 8
0x140005e84  jmp     short loc_140005E8B
0x140005e86  mov     ebx, 1
0x140005e8b  cmp     dword ptr [rsi+118h], 0
0x140005e92  jnz     loc_140006049
0x140005e98  mov     eax, [rsi+110h]
0x140005e9e  and     eax, 0Ch
0x140005ea1  cmp     al, 0Ch
0x140005ea3  jnz     loc_140006049
0x140005ea9  cmp     qword ptr [rdi+50h], 0
0x140005eae  jnz     short loc_140005EBA
0x140005eb0  mov     eax, 0C00000E5h
0x140005eb5  jmp     loc_14000604B
0x140005eba  xor     r14b, r14b
0x140005ebd  mov     [rsp+68h+var_38], r14b
0x140005ec2  mov     [rsp+68h+FileInformation], r14b
0x140005ec7  lea     rax, [rsp+68h+FileNameInformation]
0x140005ecf  mov     qword ptr [rsp+68h+FileInformationClass], rax
0x140005ed4  mov     r9d, 101h
0x140005eda  mov     r8, [rdi+40h]
0x140005ede  mov     rdx, [rdi+48h]
0x140005ee2  mov     rcx, r13
0x140005ee5  call    VfsGetFileNameInfoForFileObject
0x140005eea  mov     r15d, eax
0x140005eed  test    eax, eax
0x140005eef  jns     short loc_140005F24
0x140005ef1  mov     rdx, [r13+10h]
0x140005ef5  movzx   r8d, byte ptr [rdx+4]
0x140005efa  mov     [rsp+68h+var_40], eax
0x140005efe  mov     [rsp+68h+FileInformationClass], r8d
0x140005f03  mov     r9, [rdi+48h]
0x140005f07  lea     r8, aVfsprocessdele; "VfsProcessDeleteOnCleanupShadow() - Fai"...
0x140005f0e  xor     edx, edx
0x140005f10  mov     ecx, ebx
0x140005f12  call    LogWrite
0x140005f17  mov     rsi, [rsp+68h+FileNameInformation]
0x140005f1f  jmp     loc_140006030
0x140005f24  mov     rcx, [rdi+50h]; FileHandle
0x140005f28  call    cs:__imp_FltClose
0x140005f2f  nop     dword ptr [rax+rax+00h]
0x140005f34  mov     qword ptr [rdi+50h], 0
0x140005f3c  mov     rcx, [rdi+40h]; Instance
0x140005f40  mov     eax, [rsi+110h]
0x140005f46  test    al, 2
0x140005f48  jnz     short loc_140005F86
0x140005f4a  lea     r8, [rsp+68h+FileInformation]
0x140005f4f  mov     rdx, [rdi+48h]
0x140005f53  call    VfsCheckFileDeleted
0x140005f58  mov     rsi, [rsp+68h+FileNameInformation]
0x140005f60  cmp     [rsp+68h+FileInformation], r14b
0x140005f65  jz      short loc_140005F7D
0x140005f67  lea     r8, [rsi+8]
0x140005f6b  mov     byte ptr [rsp+68h+FileInformationClass], bl; char
0x140005f6f  xor     r9d, r9d
0x140005f72  mov     rcx, [rdi+40h]; Instance
0x140005f76  call    VfsMarkFileDeleted
0x140005f7b  jmp     short loc_140005FAD
0x140005f7d  mov     r14b, bl
0x140005f80  mov     [rsp+68h+var_38], bl
0x140005f84  jmp     short loc_140005FAD
0x140005f86  mov     rsi, [rsp+68h+FileNameInformation]
0x140005f8e  lea     r8, [rsi+8]
0x140005f92  mov     byte ptr [rsp+68h+FileInformationClass], bl; char
0x140005f96  mov     r9b, bl
0x140005f99  call    VfsMarkFileDeleted
0x140005f9e  movzx   r14d, r14b
0x140005fa2  test    eax, eax
0x140005fa4  cmovs   r14d, ebx
0x140005fa8  mov     [rsp+68h+var_38], r14b
0x140005fad  test    r14b, r14b
0x140005fb0  jz      short loc_140006030
0x140005fb2  mov     rax, [rdi+18h]
0x140005fb6  mov     r8d, [rax+110h]
0x140005fbd  test    bl, r8b
0x140005fc0  jnz     short loc_140005FD3
0x140005fc2  mov     rax, [rax+80h]
0x140005fc9  add     rax, 4
0x140005fcd  lock or dword ptr [rax], 4
0x140005fd1  jmp     short loc_140006030
0x140005fd3  mov     [rsp+68h+Context], 0
0x140005fdf  and     r8d, 2
0x140005fe3  lea     r9, [rsp+68h+Context]
0x140005feb  mov     rdx, [rdi+48h]; FileObject
0x140005fef  mov     rcx, [rdi+40h]; Instance
0x140005ff3  call    VfsGetStreamContext
0x140005ff8  mov     rcx, [rsp+68h+Context]; Context
0x140006000  lock or dword ptr [rcx+4], 4
0x140006005  test    eax, eax
0x140006007  jns     short loc_140006023
0x140006009  mov     [rsp+68h+FileInformationClass], eax
0x14000600d  mov     r9, [rdi+48h]
0x140006011  lea     r8, aVfsdelaymarkfi; "VfsDelayMarkFileDeleted() - Failed to g"...
0x140006018  xor     edx, edx
0x14000601a  mov     ecx, ebx
0x14000601c  call    LogWrite
0x140006021  jmp     short loc_140006030
0x140006023  call    cs:__imp_FltReleaseContext
0x14000602a  nop     dword ptr [rax+rax+00h]
0x14000602f  nop
0x140006030  test    rsi, rsi
0x140006033  jz      short loc_140006044
0x140006035  mov     rcx, rsi; FileNameInformation
0x140006038  call    cs:__imp_FltReleaseFileNameInformation
0x14000603f  nop     dword ptr [rax+rax+00h]
0x140006044  mov     eax, r15d
0x140006047  jmp     short loc_14000604B
0x140006049  xor     eax, eax
0x14000604b  mov     rbx, [rsp+68h+arg_0]
0x140006050  add     rsp, 40h
0x140006054  pop     r15
0x140006056  pop     r14
0x140006058  pop     r13
0x14000605a  pop     rdi
0x14000605b  pop     rsi
0x14000605c  retn
0x140014a40  push    rbp
0x140014a42  sub     rsp, 30h
0x140014a46  mov     rbp, rdx
0x140014a49  mov     rcx, [rbp+80h]; FileNameInformation
0x140014a50  test    rcx, rcx
0x140014a53  jz      short loc_140014A62
0x140014a55  call    cs:__imp_FltReleaseFileNameInformation
0x140014a5c  nop     dword ptr [rax+rax+00h]
0x140014a61  nop
0x140014a62  add     rsp, 30h
0x140014a66  pop     rbp
0x140014a67  retn
```
