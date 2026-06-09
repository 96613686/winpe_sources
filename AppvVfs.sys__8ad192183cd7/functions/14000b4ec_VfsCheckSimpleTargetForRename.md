# VfsCheckSimpleTargetForRename

- ea: `0x14000b4ec`
- end: `0x14000bbed`
- name: `VfsCheckSimpleTargetForRename`
- size: `1793`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, struct _UNICODE_STRING *, _DWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14000ca28`

## callees

- `0x140008c04`
- `0x140008e7c`
- `0x140009368`
- `0x14000b4ec`
- `0x14000bbf4`
- `0x14000d9cc`
- `0x140010aa8`
- `0x140011134`
- `0x140012acc`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000b82c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000b9dd`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000b82c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000b9dd`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000b64b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000b64b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bb92`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bbb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015089`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400150ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bb92`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bbb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015089`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400150ab`
- `ntoskrnl!ExAllocatePool2` at `0x14000b7ad`
- `ntoskrnl!ExAllocatePool2` at `0x14000b964`
- `ntoskrnl!ExAllocatePool2` at `0x14000b7ad`
- `ntoskrnl!ExAllocatePool2` at `0x14000b964`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000b7ee`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000b9a2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000b7ee`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000b9a2`
- `FLTMGR!FltObjectReference` at `0x14000ba04`
- `FLTMGR!FltObjectReference` at `0x14000ba04`
- `FLTMGR!FltObjectDereference` at `0x14000bb5e`
- `FLTMGR!FltObjectDereference` at `0x14000bb7a`
- `FLTMGR!FltObjectDereference` at `0x140015058`
- `FLTMGR!FltObjectDereference` at `0x140015071`
- `FLTMGR!FltObjectDereference` at `0x14000bb5e`
- `FLTMGR!FltObjectDereference` at `0x14000bb7a`
- `FLTMGR!FltObjectDereference` at `0x140015058`
- `FLTMGR!FltObjectDereference` at `0x140015071`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000bb3d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140015039`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14000bb3d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140015039`

## string_xrefs

- `0x14000b5fd`: `VfsCheckSimpleTargetForRename() - Failed to get filename info for fileobject: %p\n IRP: %d\n Status: 0x%08X`
- `0x14000b8a2`: `VfsCheckSimpleTargetForRename() - Failed to map filename: %wZ\n for mapping: %wZ\n Status: 0x%08X`
- `0x14000ba25`: `VfsCheckSimpleTargetForRename() - Failed to reference instance: %p\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsCheckSimpleTargetForRename(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        struct _UNICODE_STRING *a4,
        _DWORD *a5)
{
  __int64 v6; // r12
  _QWORD *Mapping; // r13
  char v8; // r14
  __int64 v9; // r8
  unsigned __int64 v10; // rdi
  int FileNameInfoForFileObject; // ebx
  unsigned __int16 v12; // di
  struct _FLT_INSTANCE *v13; // r10
  __int64 v14; // rcx
  char v15; // al
  unsigned __int64 v16; // rax
  int v17; // ebx
  int v18; // ecx
  int Length; // edi
  unsigned int v20; // edi
  unsigned __int16 v21; // ax
  int MappedTarget; // eax
  int v23; // ebx
  int v24; // ecx
  int v25; // edi
  unsigned int v26; // edi
  unsigned __int16 v27; // ax
  NTSTATUS v28; // eax
  void *v29; // rdi
  PVOID v30; // rdi
  char v32[8]; // [rsp+20h] [rbp-148h]
  __int64 v33; // [rsp+28h] [rbp-140h]
  char v34; // [rsp+60h] [rbp-108h]
  struct _UNICODE_STRING Destination; // [rsp+68h] [rbp-100h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-F0h] BYREF
  int v37; // [rsp+88h] [rbp-E0h]
  int v38; // [rsp+8Ch] [rbp-DCh]
  PVOID v39; // [rsp+90h] [rbp-D8h] BYREF
  unsigned int v40; // [rsp+98h] [rbp-D0h]
  unsigned int v41; // [rsp+9Ch] [rbp-CCh]
  int v42; // [rsp+A0h] [rbp-C8h] BYREF
  PVOID FltObject; // [rsp+A8h] [rbp-C0h] BYREF
  UNICODE_STRING String2; // [rsp+B0h] [rbp-B8h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+C0h] [rbp-A8h] BYREF
  wchar_t *Buffer; // [rsp+C8h] [rbp-A0h]
  _QWORD *v47; // [rsp+D0h] [rbp-98h]
  UNICODE_STRING v48; // [rsp+E0h] [rbp-88h]
  UNICODE_STRING SourceString; // [rsp+F0h] [rbp-78h] BYREF
  UNICODE_STRING v50; // [rsp+100h] [rbp-68h] BYREF
  UNICODE_STRING Source; // [rsp+110h] [rbp-58h] BYREF
  UNICODE_STRING v52; // [rsp+120h] [rbp-48h] BYREF

  v6 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 56LL);
  FileNameInformation = 0;
  v48 = 0;
  *(_QWORD *)&String2.Length = 0;
  Destination = 0;
  v39 = 0;
  DestinationString = 0;
  FltObject = 0;
  Mapping = 0;
  v47 = 0;
  v42 = 0;
  v34 = 0;
  *a3 = 0;
  a4->Buffer = 0;
  String2.Buffer = (wchar_t *)(v6 + 20);
  String2.Length = *(_WORD *)(v6 + 16);
  String2.MaximumLength = String2.Length;
  if ( (*(_DWORD *)(a2 + 4) & 4) != 0 )
  {
    v8 = 1;
    v9 = 40;
  }
  else
  {
    v8 = 0;
    v9 = 64;
  }
  v10 = -(__int64)(v8 != 0) & 0xFFFFFFFFFFFFFFE8uLL;
  FileNameInfoForFileObject = VfsGetFileNameInfoForFileObject(
                                a1,
                                *(_QWORD *)(v10 + a2 + 72),
                                *(_QWORD *)(v9 + a2),
                                257,
                                &FileNameInformation);
  if ( FileNameInfoForFileObject < 0 )
  {
    *(_DWORD *)v32 = *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 4LL);
    LogWrite(
      1,
      0,
      L"VfsCheckSimpleTargetForRename() - Failed to get filename info for fileobject: %p\n IRP: %d\n Status: 0x%08X",
      *(_QWORD *)(v10 + a2 + 72),
      *(_QWORD *)v32,
      FileNameInfoForFileObject);
    goto LABEL_55;
  }
  Buffer = FileNameInformation->Name.Buffer;
  v48.Buffer = Buffer;
  v12 = FileNameInformation->Name.Length - FileNameInformation->FinalComponent.Length;
  v48.Length = v12;
  v48.MaximumLength = v12;
  if ( !RtlEqualUnicodeString(&FileNameInformation->FinalComponent, &String2, 1u) )
  {
    Mapping = (_QWORD *)VfsScbGetMapping(*(_QWORD *)(a2 + 24));
    v47 = Mapping;
    if ( !Mapping )
    {
      v13 = *(struct _FLT_INSTANCE **)(a2 + 64);
      v14 = *(_QWORD *)(a1 + 16);
      if ( *(struct _FLT_INSTANCE **)(v14 + 16) == v13 )
      {
        if ( *(_DWORD *)(v14 + 32) == 10 )
          v15 = *(_BYTE *)v6;
        else
          v15 = *(_DWORD *)v6 & 1;
        FileNameInfoForFileObject = VfsRenameFile(v13, *(PFILE_OBJECT *)(a2 + 72), v15);
      }
      else
      {
        FileNameInfoForFileObject = -1073741595;
      }
      goto LABEL_55;
    }
    v16 = (unsigned __int64)v12 >> 1;
    if ( v8 )
    {
      v40 = 0;
      v37 = 0;
      SourceString = v48;
      Source = String2;
      v17 = Buffer[v16 - 1] == 92;
      v37 = v17;
      if ( *(_WORD *)_mm_srli_si128((__m128i)String2, 8).m128i_i16[0] == 92 )
        v37 = ++v17;
      if ( v17 == 2 )
      {
        v12 -= 2;
        SourceString.Length = v12;
        v17 = 1;
        v37 = 1;
      }
      v18 = v12;
      Length = String2.Length;
      if ( !v17 )
        Length = String2.Length + 2;
      v20 = v18 + Length;
      v40 = v20;
      if ( v20 <= 0xFFFE )
      {
        DestinationString.Buffer = (wchar_t *)ExAllocatePool2(256, (unsigned __int16)v20, 1951614550);
        if ( DestinationString.Buffer )
        {
          DestinationString.Length = 0;
          DestinationString.MaximumLength = v20;
          v21 = SourceString.Length;
          if ( SourceString.Length )
          {
            RtlCopyUnicodeString(&DestinationString, &SourceString);
            v21 = SourceString.Length;
          }
          if ( !v17 )
          {
            DestinationString.Buffer[(unsigned __int64)v21 >> 1] = 92;
            DestinationString.Length += 2;
          }
          RtlAppendUnicodeStringToString(&DestinationString, &Source);
          FileNameInfoForFileObject = 0;
        }
        else
        {
          FileNameInfoForFileObject = -1073741670;
        }
      }
      else
      {
        FileNameInfoForFileObject = -1073741562;
      }
      if ( FileNameInfoForFileObject >= 0 )
      {
        FltObject = *(PVOID *)(a2 + 40);
        MappedTarget = VfsGetMappedTarget(
                         FltObject,
                         &DestinationString,
                         0,
                         (__int64)Mapping,
                         (__int64)&Destination,
                         &v39);
        FileNameInfoForFileObject = MappedTarget;
        if ( MappedTarget < 0 )
        {
          LODWORD(v33) = MappedTarget;
          LogWrite(
            1,
            0,
            L"VfsCheckSimpleTargetForRename() - Failed to map filename: %wZ\n for mapping: %wZ\n Status: 0x%08X",
            &DestinationString,
            Mapping[5],
            v33);
          goto LABEL_55;
        }
        goto LABEL_53;
      }
    }
    else
    {
      v41 = 0;
      v38 = 0;
      v50 = v48;
      v52 = String2;
      v23 = Buffer[v16 - 1] == 92;
      v38 = v23;
      if ( *(_WORD *)_mm_srli_si128((__m128i)String2, 8).m128i_i16[0] == 92 )
        v38 = ++v23;
      if ( v23 == 2 )
      {
        v12 -= 2;
        v50.Length = v12;
        v23 = 1;
        v38 = 1;
      }
      v24 = v12;
      v25 = String2.Length;
      if ( !v23 )
        v25 = String2.Length + 2;
      v26 = v24 + v25;
      v41 = v26;
      if ( v26 <= 0xFFFE )
      {
        Destination.Buffer = (wchar_t *)ExAllocatePool2(256, (unsigned __int16)v26, 1951614550);
        if ( Destination.Buffer )
        {
          Destination.Length = 0;
          Destination.MaximumLength = v26;
          v27 = v50.Length;
          if ( v50.Length )
          {
            RtlCopyUnicodeString(&Destination, &v50);
            v27 = v50.Length;
          }
          if ( !v23 )
          {
            Destination.Buffer[(unsigned __int64)v27 >> 1] = 92;
            Destination.Length += 2;
          }
          RtlAppendUnicodeStringToString(&Destination, &v52);
          FileNameInfoForFileObject = 0;
        }
        else
        {
          FileNameInfoForFileObject = -1073741670;
        }
      }
      else
      {
        FileNameInfoForFileObject = -1073741562;
      }
      if ( FileNameInfoForFileObject >= 0 )
      {
        v28 = FltObjectReference(*(PVOID *)(a2 + 64));
        FileNameInfoForFileObject = v28;
        v29 = *(void **)(a2 + 64);
        if ( v28 < 0 )
        {
          *(_DWORD *)v32 = v28;
          LogWrite(
            1,
            0,
            L"VfsCheckSimpleTargetForRename() - Failed to reference instance: %p\n Status: 0x%08X",
            v29,
            *(_QWORD *)v32);
          goto LABEL_55;
        }
        v39 = *(PVOID *)(a2 + 64);
        FileNameInfoForFileObject = VfsGetUnMappedSource(v29, (__int64)&DestinationString, (__int64)&FltObject);
        if ( FileNameInfoForFileObject >= 0 )
        {
          v34 = 1;
LABEL_53:
          v30 = v39;
          FileNameInfoForFileObject = VfsCheckTargetForRename(
                                        a1,
                                        FltObject,
                                        0,
                                        &DestinationString,
                                        v39,
                                        0,
                                        &Destination,
                                        *(_QWORD *)(a2 + 24) + 220LL,
                                        *(_QWORD *)(a2 + 24) + 152LL,
                                        Mapping,
                                        &v42);
          if ( FileNameInfoForFileObject >= 0 )
          {
            *a3 = v30;
            *a4 = Destination;
            *a5 = v42;
            v39 = 0;
            Destination.Buffer = 0;
          }
        }
      }
    }
  }
LABEL_55:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( v34 && FltObject )
    FltObjectDereference(FltObject);
  if ( v39 )
    FltObjectDereference(v39);
  if ( Destination.Buffer )
  {
    ExFreePoolWithTag(Destination.Buffer, 0);
    Destination.Buffer = 0;
  }
  if ( DestinationString.Buffer )
  {
    ExFreePoolWithTag(DestinationString.Buffer, 0);
    DestinationString.Buffer = 0;
  }
  if ( Mapping )
    VfsReleaseMappingEntry(Mapping);
  return (unsigned int)FileNameInfoForFileObject;
}

```

## disassembly

```asm
0x14000b4ec  mov     r11, rsp
0x14000b4ef  mov     [r11+20h], r9
0x14000b4f3  mov     [r11+18h], r8
0x14000b4f7  mov     [r11+8], rcx
0x14000b4fb  push    rbx
0x14000b4fc  push    rsi
0x14000b4fd  push    rdi
0x14000b4fe  push    r12
0x14000b500  push    r13
0x14000b502  push    r14
0x14000b504  push    r15
0x14000b506  sub     rsp, 130h
0x14000b50d  mov     r15, rdx
0x14000b510  mov     rax, [rcx+10h]
0x14000b514  mov     r12, [rax+38h]
0x14000b518  xor     edx, edx
0x14000b51a  mov     [r11-0A8h], rdx
0x14000b521  xorps   xmm0, xmm0
0x14000b524  movups  [rsp+168h+var_88], xmm0
0x14000b52c  mov     [r11-0B8h], rdx
0x14000b533  xorps   xmm1, xmm1
0x14000b536  movups  xmmword ptr [rsp+168h+Destination.Length], xmm1
0x14000b53b  mov     [r11-0D8h], rdx
0x14000b542  movups  xmmword ptr [rsp+168h+DestinationString.Length], xmm0
0x14000b547  mov     [r11-0C0h], rdx
0x14000b54e  mov     r13d, edx
0x14000b551  mov     [r11-98h], rdx
0x14000b558  mov     [rsp+168h+var_C8], edx
0x14000b55f  mov     [rsp+168h+var_108], dl
0x14000b563  mov     [r8], rdx
0x14000b566  mov     [r9+8], rdx
0x14000b56a  lea     rax, [r12+14h]
0x14000b56f  mov     [r11-0B0h], rax
0x14000b576  movzx   eax, word ptr [r12+10h]
0x14000b57c  mov     [rsp+168h+String2.Length], ax
0x14000b584  mov     [rsp+168h+String2.MaximumLength], ax
0x14000b58c  mov     eax, [r15+4]
0x14000b590  lea     esi, [rdx+1]
0x14000b593  test    al, 4
0x14000b595  jz      short loc_14000B5A0
0x14000b597  mov     r14b, sil
0x14000b59a  lea     r8d, [rdx+28h]
0x14000b59e  jmp     short loc_14000B5A9
0x14000b5a0  mov     r14b, dl
0x14000b5a3  mov     r8d, 40h ; '@'
0x14000b5a9  mov     al, r14b
0x14000b5ac  neg     al
0x14000b5ae  sbb     rdi, rdi
0x14000b5b1  and     rdi, 0FFFFFFFFFFFFFFE8h
0x14000b5b5  lea     rax, [rsp+168h+FileNameInformation]
0x14000b5bd  mov     qword ptr [rsp+168h+var_148], rax
0x14000b5c2  mov     r9d, 101h
0x14000b5c8  mov     r8, [r8+r15]
0x14000b5cc  mov     rdx, [rdi+r15+48h]
0x14000b5d1  call    VfsGetFileNameInfoForFileObject
0x14000b5d6  mov     ebx, eax
0x14000b5d8  mov     [rsp+168h+var_104], eax
0x14000b5dc  test    eax, eax
0x14000b5de  jns     short loc_14000B609
0x14000b5e0  mov     rcx, [rsp+168h+arg_0]
0x14000b5e8  mov     rax, [rcx+10h]
0x14000b5ec  movzx   edx, byte ptr [rax+4]
0x14000b5f0  mov     dword ptr [rsp+168h+var_140], ebx
0x14000b5f4  mov     dword ptr [rsp+168h+var_148], edx
0x14000b5f8  mov     r9, [rdi+r15+48h]
0x14000b5fd  lea     r8, aVfschecksimple_1; "VfsCheckSimpleTargetForRename() - Faile"...
0x14000b604  jmp     loc_14000B8A9
0x14000b609  mov     rdx, [rsp+168h+FileNameInformation]
0x14000b611  mov     rax, [rdx+10h]
0x14000b615  mov     [rsp+168h+var_A0], rax
0x14000b61d  mov     qword ptr [rsp+168h+var_88+8], rax
0x14000b625  lea     rcx, [rdx+58h]; String1
0x14000b629  movzx   edi, word ptr [rdx+8]
0x14000b62d  sub     di, [rcx]
0x14000b630  mov     word ptr [rsp+168h+var_88], di
0x14000b638  mov     word ptr [rsp+168h+var_88+2], di
0x14000b640  mov     r8b, sil; CaseInSensitive
0x14000b643  lea     rdx, [rsp+168h+String2]; String2
0x14000b64b  call    cs:__imp_RtlEqualUnicodeString
0x14000b652  nop     dword ptr [rax+rax+00h]
0x14000b657  xor     edx, edx
0x14000b659  test    al, al
0x14000b65b  jnz     loc_14000BB30
0x14000b661  mov     rcx, [r15+18h]
0x14000b665  call    VfsScbGetMapping
0x14000b66a  mov     r13, rax
0x14000b66d  mov     [rsp+168h+var_98], rax
0x14000b675  xor     edx, edx
0x14000b677  test    rax, rax
0x14000b67a  jnz     short loc_14000B6D9
0x14000b67c  mov     r10, [r15+40h]
0x14000b680  mov     rcx, [rsp+168h+arg_0]
0x14000b688  mov     rcx, [rcx+10h]
0x14000b68c  cmp     [rcx+10h], r10
0x14000b690  jz      short loc_14000B6A0
0x14000b692  mov     ebx, 0C00000E5h
0x14000b697  mov     [rsp+168h+var_104], ebx
0x14000b69b  jmp     loc_14000BB30
0x14000b6a0  cmp     dword ptr [rcx+20h], 0Ah
0x14000b6a4  jnz     short loc_14000B6AC
0x14000b6a6  mov     al, [r12]
0x14000b6aa  jmp     short loc_14000B6B3
0x14000b6ac  mov     eax, [r12]
0x14000b6b0  and     al, sil
0x14000b6b3  mov     [rsp+168h+var_148], al; char
0x14000b6b7  lea     r9, [rsp+168h+String2]
0x14000b6bf  xor     r8d, r8d
0x14000b6c2  mov     rdx, [r15+48h]; FileObject
0x14000b6c6  mov     rcx, r10; Instance
0x14000b6c9  call    VfsRenameFile
0x14000b6ce  mov     ebx, eax
0x14000b6d0  mov     [rsp+168h+var_104], eax
0x14000b6d4  jmp     loc_14000BA35
0x14000b6d9  movzx   eax, di
0x14000b6dc  shr     rax, 1
0x14000b6df  mov     ebx, edx
0x14000b6e1  movaps  xmm0, [rsp+168h+var_88]
0x14000b6e9  mov     r12d, 5Ch ; '\'
0x14000b6ef  mov     rcx, [rsp+168h+var_A0]
0x14000b6f7  test    r14b, r14b
0x14000b6fa  jz      loc_14000B8B7
0x14000b700  mov     [rsp+168h+var_D0], edx
0x14000b707  mov     [rsp+168h+var_E0], edx
0x14000b70e  movdqa  xmmword ptr [rsp+168h+SourceString.Length], xmm0
0x14000b717  movaps  xmm1, xmmword ptr [rsp+168h+String2.Length]
0x14000b71f  movdqa  xmmword ptr [rsp+168h+Source.Length], xmm1
0x14000b728  cmp     [rcx+rax*2-2], r12w
0x14000b72e  cmovz   ebx, esi
0x14000b731  mov     [rsp+168h+var_E0], ebx
0x14000b738  psrldq  xmm1, 8
0x14000b73d  movq    rax, xmm1
0x14000b742  cmp     [rax], r12w
0x14000b746  jnz     short loc_14000B751
0x14000b748  add     ebx, esi
0x14000b74a  mov     [rsp+168h+var_E0], ebx
0x14000b751  mov     r14d, 2
0x14000b757  cmp     ebx, r14d
0x14000b75a  jnz     short loc_14000B771
0x14000b75c  sub     di, r14w
0x14000b760  mov     [rsp+168h+SourceString.Length], di
0x14000b768  mov     ebx, esi
0x14000b76a  mov     [rsp+168h+var_E0], ebx
0x14000b771  movzx   ecx, di
0x14000b774  movzx   edi, [rsp+168h+String2.Length]
0x14000b77c  test    ebx, ebx
0x14000b77e  jnz     short loc_14000B783
0x14000b780  add     edi, r14d
0x14000b783  add     edi, ecx
0x14000b785  mov     eax, edi
0x14000b787  mov     [rsp+168h+var_D0], edi
0x14000b78e  cmp     eax, 0FFFEh
0x14000b793  jbe     short loc_14000B79F
0x14000b795  mov     ebx, 0C0000106h
0x14000b79a  jmp     loc_14000B843
0x14000b79f  movzx   edx, di
0x14000b7a2  mov     ecx, 100h
0x14000b7a7  mov     r8d, 74534656h
0x14000b7ad  call    cs:__imp_ExAllocatePool2
0x14000b7b4  nop     dword ptr [rax+rax+00h]
0x14000b7b9  mov     [rsp+168h+DestinationString.Buffer], rax
0x14000b7c1  xor     edx, edx
0x14000b7c3  test    rax, rax
0x14000b7c6  jz      short loc_14000B83E
0x14000b7c8  mov     eax, edx
0x14000b7ca  mov     [rsp+168h+DestinationString.Length], dx
0x14000b7cf  mov     [rsp+168h+DestinationString.MaximumLength], di
0x14000b7d4  movzx   eax, [rsp+168h+SourceString.Length]
0x14000b7dc  test    ax, ax
0x14000b7df  jz      short loc_14000B802
0x14000b7e1  lea     rdx, [rsp+168h+SourceString]; SourceString
0x14000b7e9  lea     rcx, [rsp+168h+DestinationString]; DestinationString
0x14000b7ee  call    cs:__imp_RtlCopyUnicodeString
0x14000b7f5  nop     dword ptr [rax+rax+00h]
0x14000b7fa  movzx   eax, [rsp+168h+SourceString.Length]
0x14000b802  test    ebx, ebx
0x14000b804  jnz     short loc_14000B81F
0x14000b806  movzx   ecx, ax
0x14000b809  shr     rcx, 1
0x14000b80c  mov     rax, [rsp+168h+DestinationString.Buffer]
0x14000b814  mov     [rax+rcx*2], r12w
0x14000b819  add     [rsp+168h+DestinationString.Length], r14w
0x14000b81f  lea     rdx, [rsp+168h+Source]; Source
0x14000b827  lea     rcx, [rsp+168h+DestinationString]; Destination
0x14000b82c  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000b833  nop     dword ptr [rax+rax+00h]
0x14000b838  xor     edx, edx
0x14000b83a  mov     ebx, edx
0x14000b83c  jmp     short loc_14000B843
0x14000b83e  mov     ebx, 0C000009Ah
0x14000b843  mov     [rsp+168h+var_104], ebx
0x14000b847  test    ebx, ebx
0x14000b849  js      loc_14000BB30
0x14000b84f  mov     rcx, [r15+28h]; FltObject
0x14000b853  mov     [rsp+168h+FltObject], rcx
0x14000b85b  lea     rax, [rsp+168h+var_D8]
0x14000b863  mov     [rsp+168h+var_140], rax; __int64
0x14000b868  lea     rax, [rsp+168h+Destination]
0x14000b86d  mov     qword ptr [rsp+168h+var_148], rax; __int64
0x14000b872  mov     r9, r13
0x14000b875  xor     r8d, r8d
0x14000b878  lea     rdx, [rsp+168h+DestinationString]
0x14000b87d  call    VfsGetMappedTarget
0x14000b882  mov     ebx, eax
0x14000b884  mov     [rsp+168h+var_104], eax
0x14000b888  test    eax, eax
0x14000b88a  jns     loc_14000BA80
0x14000b890  mov     dword ptr [rsp+168h+var_140], eax
0x14000b894  mov     rax, [r13+28h]
0x14000b898  mov     qword ptr [rsp+168h+var_148], rax
0x14000b89d  lea     r9, [rsp+168h+DestinationString]
0x14000b8a2  lea     r8, aVfschecksimple_0; "VfsCheckSimpleTargetForRename() - Faile"...
0x14000b8a9  xor     edx, edx
0x14000b8ab  mov     ecx, esi
0x14000b8ad  call    LogWrite
0x14000b8b2  jmp     loc_14000BA35
0x14000b8b7  mov     [rsp+168h+var_CC], edx
0x14000b8be  mov     [rsp+168h+var_DC], ebx
0x14000b8c5  movdqa  xmmword ptr [rsp+168h+var_68.Length], xmm0
0x14000b8ce  movaps  xmm1, xmmword ptr [rsp+168h+String2.Length]
0x14000b8d6  movdqa  xmmword ptr [rsp+168h+var_48.Length], xmm1
0x14000b8df  cmp     [rcx+rax*2-2], r12w
0x14000b8e5  cmovz   ebx, esi
0x14000b8e8  mov     [rsp+168h+var_DC], ebx
0x14000b8ef  psrldq  xmm1, 8
0x14000b8f4  movq    rax, xmm1
0x14000b8f9  cmp     [rax], r12w
0x14000b8fd  jnz     short loc_14000B908
0x14000b8ff  add     ebx, esi
0x14000b901  mov     [rsp+168h+var_DC], ebx
0x14000b908  mov     r14d, 2
0x14000b90e  cmp     ebx, r14d
0x14000b911  jnz     short loc_14000B928
0x14000b913  sub     di, r14w
0x14000b917  mov     [rsp+168h+var_68.Length], di
0x14000b91f  mov     ebx, esi
0x14000b921  mov     [rsp+168h+var_DC], ebx
0x14000b928  movzx   ecx, di
0x14000b92b  movzx   edi, [rsp+168h+String2.Length]
0x14000b933  test    ebx, ebx
0x14000b935  jnz     short loc_14000B93A
0x14000b937  add     edi, r14d
0x14000b93a  add     edi, ecx
0x14000b93c  mov     eax, edi
0x14000b93e  mov     [rsp+168h+var_CC], edi
0x14000b945  cmp     eax, 0FFFEh
0x14000b94a  jbe     short loc_14000B956
0x14000b94c  mov     ebx, 0C0000106h
0x14000b951  jmp     loc_14000B9F4
0x14000b956  movzx   edx, di
0x14000b959  mov     ecx, 100h
0x14000b95e  mov     r8d, 74534656h
0x14000b964  call    cs:__imp_ExAllocatePool2
0x14000b96b  nop     dword ptr [rax+rax+00h]
0x14000b970  mov     [rsp+168h+Destination.Buffer], rax
0x14000b975  xor     edx, edx
0x14000b977  test    rax, rax
0x14000b97a  jz      short loc_14000B9EF
0x14000b97c  mov     eax, edx
0x14000b97e  mov     [rsp+168h+Destination.Length], dx
0x14000b983  mov     [rsp+168h+Destination.MaximumLength], di
0x14000b988  movzx   eax, [rsp+168h+var_68.Length]
0x14000b990  test    ax, ax
0x14000b993  jz      short loc_14000B9B6
0x14000b995  lea     rdx, [rsp+168h+var_68]; SourceString
0x14000b99d  lea     rcx, [rsp+168h+Destination]; DestinationString
0x14000b9a2  call    cs:__imp_RtlCopyUnicodeString
0x14000b9a9  nop     dword ptr [rax+rax+00h]
0x14000b9ae  movzx   eax, [rsp+168h+var_68.Length]
0x14000b9b6  test    ebx, ebx
0x14000b9b8  jnz     short loc_14000B9D0
0x14000b9ba  movzx   ecx, ax
0x14000b9bd  shr     rcx, 1
0x14000b9c0  mov     rax, [rsp+168h+Destination.Buffer]
0x14000b9c5  mov     [rax+rcx*2], r12w
0x14000b9ca  add     [rsp+168h+Destination.Length], r14w
0x14000b9d0  lea     rdx, [rsp+168h+var_48]; Source
0x14000b9d8  lea     rcx, [rsp+168h+Destination]; Destination
0x14000b9dd  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000b9e4  nop     dword ptr [rax+rax+00h]
0x14000b9e9  xor     edx, edx
0x14000b9eb  mov     ebx, edx
0x14000b9ed  jmp     short loc_14000B9F4
0x14000b9ef  mov     ebx, 0C000009Ah
0x14000b9f4  mov     [rsp+168h+var_104], ebx
0x14000b9f8  test    ebx, ebx
0x14000b9fa  js      loc_14000BB30
0x14000ba00  mov     rcx, [r15+40h]; FltObject
0x14000ba04  call    cs:__imp_FltObjectReference
0x14000ba0b  nop     dword ptr [rax+rax+00h]
0x14000ba10  mov     ebx, eax
0x14000ba12  mov     [rsp+168h+var_104], eax
0x14000ba16  mov     rdi, [r15+40h]
0x14000ba1a  test    eax, eax
0x14000ba1c  jns     short loc_14000BA3C
0x14000ba1e  mov     dword ptr [rsp+168h+var_148], eax
0x14000ba22  mov     r9, rdi
0x14000ba25  lea     r8, aVfschecksimple; "VfsCheckSimpleTargetForRename() - Faile"...
0x14000ba2c  xor     edx, edx
0x14000ba2e  mov     ecx, esi
0x14000ba30  call    LogWrite
  ... truncated ...
```
