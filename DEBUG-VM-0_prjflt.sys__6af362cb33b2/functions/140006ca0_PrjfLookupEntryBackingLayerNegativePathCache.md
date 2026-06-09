# PrjfLookupEntryBackingLayerNegativePathCache

- ea: `0x140006ca0`
- end: `0x1400072f9`
- name: `PrjfLookupEntryBackingLayerNegativePathCache`
- size: `1625`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, __int64, PUNICODE_STRING DestinationString, PULONG HashValue, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140024184`

## callees

- `0x1400037e0`
- `0x140003e6c`
- `0x140006ca0`
- `0x14000bb80`
- `0x14000f984`
- `0x140011d2c`
- `0x140012058`
- `0x1400122d4`
- `0x14003775c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400072bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400072d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400072bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400072d6`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140007230`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140007230`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400071fa`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400071fa`
- `ntoskrnl!RtlHashUnicodeString` at `0x1400071af`
- `ntoskrnl!RtlHashUnicodeString` at `0x1400071af`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x140007193`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x140007193`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140007219`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140007219`
- `ntoskrnl!ObfDereferenceObject` at `0x140007280`
- `ntoskrnl!ObfDereferenceObject` at `0x140007280`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140006ef5`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140006ef5`
- `FLTMGR!FltCreateFileEx2` at `0x140006e4c`
- `FLTMGR!FltCreateFileEx2` at `0x140006e4c`
- `FLTMGR!FltClose` at `0x14000726b`
- `FLTMGR!FltClose` at `0x14000726b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140007295`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140007295`
- `FLTMGR!FltReleaseResource` at `0x14000724a`
- `FLTMGR!FltReleaseResource` at `0x14000724a`
- `FLTMGR!FltAcquireResourceShared` at `0x1400071d7`
- `FLTMGR!FltAcquireResourceShared` at `0x1400071d7`

## pseudocode

```c
__int64 __fastcall PrjfLookupEntryBackingLayerNegativePathCache(
        PFLT_INSTANCE Instance,
        struct _UNICODE_STRING *a2,
        unsigned __int16 *a3,
        __int64 a4,
        _QWORD *a5,
        PUNICODE_STRING DestinationString,
        PULONG HashValue,
        _BYTE *a8)
{
  int v11; // edx
  NTSTATUS UnionContextByFileName; // ebx
  int v13; // r8d
  char *v14; // rdi
  char v15; // si
  int v16; // edx
  int v17; // r8d
  NTSTATUS FileNameInformationUnsafe; // eax
  int v19; // edx
  int v20; // r8d
  int v21; // edx
  __int64 v22; // r8
  __int64 v23; // r9
  USHORT v24; // ax
  int v25; // edx
  int v26; // r8d
  PWSTR Buffer; // rcx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY i; // rax
  int DesiredAccess; // [rsp+20h] [rbp-E0h]
  int ObjectAttributes; // [rsp+28h] [rbp-D8h]
  int ObjectAttributesa; // [rsp+28h] [rbp-D8h]
  int IoStatusBlock; // [rsp+30h] [rbp-D0h]
  PLARGE_INTEGER AllocationSize; // [rsp+38h] [rbp-C8h]
  int FileAttributes; // [rsp+40h] [rbp-C0h]
  ULONG ShareAccess; // [rsp+48h] [rbp-B8h]
  __int64 v37; // [rsp+80h] [rbp-80h] BYREF
  PVOID P; // [rsp+88h] [rbp-78h] BYREF
  UNICODE_STRING SourceString; // [rsp+90h] [rbp-70h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+A0h] [rbp-60h] BYREF
  void *Src[2]; // [rsp+A8h] [rbp-58h] BYREF
  PFILE_OBJECT FileObject; // [rsp+B8h] [rbp-48h] BYREF
  void *FileHandle; // [rsp+C0h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES v44; // [rsp+C8h] [rbp-38h] BYREF
  _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+F8h] [rbp-8h] BYREF
  struct _IO_STATUS_BLOCK v46; // [rsp+110h] [rbp+10h] BYREF

  P = 0;
  *a5 = 0;
  LOBYTE(v37) = 0;
  FileHandle = 0;
  SourceString = 0;
  *HashValue = 0;
  *(_OWORD *)Src = 0;
  FileObject = 0;
  memset(&v44, 0, 32);
  FileNameInformation = 0;
  *a8 = 0;
  *(_OWORD *)&v44.SecurityDescriptor = 0;
  v46 = 0;
  UnionContextByFileName = PrjfGetUnionContextByFileNameEx(0, (__int64)&P, (__int64)&SourceString, (__int64)&v37);
  if ( UnionContextByFileName < 0 )
  {
    if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = xmmword_14001A3D0 & 0x20;
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDdZd(517, v11, v13, *((_QWORD *)WPP_GLOBAL_Control + 8), 2, 5, 167);
    }
LABEL_5:
    v14 = (char *)P;
    goto LABEL_45;
  }
  v14 = (char *)P;
  v15 = 1;
  if ( !P )
  {
    if ( !(_BYTE)v37 )
    {
      UnionContextByFileName = -1073689087;
      goto LABEL_45;
    }
    v44.RootDirectory = 0;
    v44.Length = 48;
    v44.Attributes = 576;
    v44.ObjectName = a2;
    *(_OWORD *)&v44.SecurityDescriptor = 0;
    UnionContextByFileName = FltCreateFileEx2(
                               Globals,
                               Instance,
                               &FileHandle,
                               &FileObject,
                               0x100001u,
                               &v44,
                               &v46,
                               0,
                               0x90u,
                               7u,
                               1u,
                               0x4021u,
                               0,
                               0,
                               0x800u,
                               0);
    if ( UnionContextByFileName < 0 )
    {
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v16) = xmmword_14001A3D0 & 0x20;
        LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZZ(
          517,
          v16,
          v17,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          168,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          67,
          UnionContextByFileName,
          (__int64)a2,
          (__int64)a3);
      }
      goto LABEL_45;
    }
    FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(FileObject, Instance, 0x101u, &FileNameInformation);
    UnionContextByFileName = FileNameInformationUnsafe;
    if ( FileNameInformationUnsafe < 0 )
    {
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v19) = xmmword_14001A3D0 & 0x20;
        LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZZq(
          0,
          v19,
          v20,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          DesiredAccess,
          ObjectAttributes,
          IoStatusBlock,
          (_DWORD)AllocationSize,
          FileAttributes,
          ShareAccess,
          FileNameInformationUnsafe,
          (__int64)a2,
          (__int64)a3,
          (char)Instance);
      }
      goto LABEL_45;
    }
    UnionContextByFileName = PrjfGetUnionContextByFileNameEx(0, (__int64)&P, (__int64)Src, 0);
    if ( UnionContextByFileName < 0 )
    {
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v21) = xmmword_14001A3D0 & 0x20;
        LOBYTE(v22) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZZZq(
          517,
          v21,
          v22,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          ObjectAttributesa,
          170,
          (__int64)AllocationSize,
          FileAttributes,
          116,
          UnionContextByFileName,
          (__int64)a2,
          (__int64)&FileNameInformation->Name,
          (__int64)a3,
          (char)Instance);
      }
      goto LABEL_5;
    }
    v14 = (char *)P;
    if ( !P )
    {
      UnionContextByFileName = -1073689087;
      LOBYTE(v21) = BYTE8(xmmword_14001A3E0) & 0x20;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !*((_WORD *)WPP_GLOBAL_Control + 36) )
        v15 = 0;
      if ( (_BYTE)v21 || v15 )
      {
        LOBYTE(v22) = v15;
        WPP_RECORDER_AND_TRACE_SF_sDdZZZq(
          1285,
          v21,
          v22,
          PrjfTraceRecorder,
          5,
          ObjectAttributesa,
          171,
          (__int64)AllocationSize,
          FileAttributes,
          134,
          1,
          (__int64)a2,
          (__int64)&FileNameInformation->Name,
          (__int64)a3,
          (char)Instance);
      }
      goto LABEL_45;
    }
    v24 = *a3;
    if ( LOWORD(Src[0]) )
      v24 += LOWORD(Src[0]) + 2;
    SourceString.MaximumLength = v24;
    UnionContextByFileName = PrjfAllocateUnicodeString(1852197456, &SourceString, v22, v23);
    if ( UnionContextByFileName < 0 )
    {
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v25) = xmmword_14001A3D0 & 0x20;
        LOBYTE(v26) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZZZq(
          517,
          v25,
          v26,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          ObjectAttributesa,
          172,
          (__int64)AllocationSize,
          FileAttributes,
          170,
          UnionContextByFileName,
          (__int64)a2,
          (__int64)a3,
          (__int64)Src,
          (char)Instance);
      }
      goto LABEL_45;
    }
    Buffer = SourceString.Buffer;
    SourceString.Length = SourceString.MaximumLength;
    if ( LOWORD(Src[0]) )
    {
      memmove(SourceString.Buffer, Src[1], LOWORD(Src[0]));
      SourceString.Buffer[(unsigned __int64)LOWORD(Src[0]) >> 1] = 92;
      Buffer = (PWSTR)((char *)SourceString.Buffer + LOWORD(Src[0]) + 2);
    }
    memmove(Buffer, *((const void **)a3 + 1), *a3);
  }
  if ( (*((_DWORD *)v14 + 14) & 1) != 0 )
  {
    RtlDowncaseUnicodeString(DestinationString, &SourceString, 1u);
    UnionContextByFileName = RtlHashUnicodeString(DestinationString, 1u, 0, HashValue);
    memset(&Context, 0, sizeof(Context));
    FltAcquireResourceShared((PERESOURCE)(v14 + 544));
    for ( i = RtlLookupEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(v14 + 648), *HashValue, &Context);
          i;
          i = RtlGetNextEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(v14 + 648), &Context) )
    {
      if ( !RtlCompareUnicodeString(DestinationString, (PCUNICODE_STRING)&i[1], 1u) )
      {
        *a8 = 1;
        break;
      }
    }
    FltReleaseResource((PERESOURCE)(v14 + 544));
    *a5 = v14;
    v14 = 0;
  }
LABEL_45:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( v14 )
    PrjfReleaseUnionContext(v14);
  if ( SourceString.Buffer )
    ExFreePoolWithTag(SourceString.Buffer, 0x6E664A50u);
  if ( Src[1] )
    ExFreePoolWithTag(Src[1], 0x6E664A50u);
  return (unsigned int)UnionContextByFileName;
}

```

## disassembly

```asm
0x140006ca0  push    rbp
0x140006ca2  push    rbx
0x140006ca3  push    rsi
0x140006ca4  push    rdi
0x140006ca5  push    r12
0x140006ca7  push    r13
0x140006ca9  push    r14
0x140006cab  push    r15
0x140006cad  lea     rbp, [rsp-28h]
0x140006cb2  sub     rsp, 128h
0x140006cb9  mov     rax, [rbp+60h+arg_20]
0x140006cc0  xorps   xmm0, xmm0
0x140006cc3  mov     r13, [rbp+60h+arg_38]
0x140006cca  mov     r15, rcx
0x140006ccd  xor     ecx, ecx; CallbackData
0x140006ccf  mov     r14, r8
0x140006cd2  mov     r12, rdx
0x140006cd5  mov     [rbp+60h+P], rcx
0x140006cd9  mov     [rax], rcx
0x140006cdc  xorps   xmm1, xmm1
0x140006cdf  mov     rax, [rbp+60h+HashValue]
0x140006ce6  mov     r8, r15
0x140006ce9  xor     edx, edx
0x140006ceb  mov     byte ptr [rbp+60h+var_E0], cl
0x140006cee  mov     rdi, r9
0x140006cf1  mov     [rbp+60h+FileHandle], rcx
0x140006cf5  movups  xmmword ptr [rbp+60h+SourceString.Length], xmm0
0x140006cf9  mov     [rax], ecx
0x140006cfb  lea     rax, [rbp+60h+var_E0]
0x140006cff  mov     [rsp+160h+IoStatusBlock], rax; __int64
0x140006d04  lea     rax, [rbp+60h+SourceString]
0x140006d08  mov     [rsp+160h+ObjectAttributes], rax; __int64
0x140006d0d  lea     rax, [rbp+60h+P]
0x140006d11  mov     qword ptr [rsp+160h+DesiredAccess], rax; __int64
0x140006d16  movups  xmmword ptr [rbp+60h+Src], xmm1
0x140006d1a  mov     [rbp+60h+FileObject], rcx
0x140006d1e  movups  xmmword ptr [rbp+60h+var_98.Length], xmm0
0x140006d22  mov     [rbp+60h+FileNameInformation], rcx
0x140006d26  movups  xmmword ptr [rbp+60h+var_98.ObjectName], xmm0
0x140006d2a  mov     [r13+0], cl
0x140006d2e  movups  xmmword ptr [rbp+60h+var_98.SecurityDescriptor], xmm0
0x140006d32  movups  xmmword ptr [rbp+60h+var_50], xmm0
0x140006d36  call    PrjfGetUnionContextByFileNameEx
0x140006d3b  xor     ecx, ecx
0x140006d3d  mov     ebx, eax
0x140006d3f  test    eax, eax
0x140006d41  jns     short loc_140006DB0
0x140006d43  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140006d49  lea     rax, WPP_RECORDER_INITIALIZED
0x140006d50  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140006d57  setnz   r8b
0x140006d5b  and     dl, 20h
0x140006d5e  jnz     short loc_140006D65
0x140006d60  test    r8b, r8b
0x140006d63  jz      short loc_140006DA7
0x140006d65  movzx   eax, byte ptr [rbp+60h+var_E0]
0x140006d69  mov     ecx, 205h
0x140006d6e  mov     r9, cs:WPP_GLOBAL_Control
0x140006d75  mov     dword ptr [rsp+160h+EaBuffer], eax
0x140006d79  mov     qword ptr [rsp+160h+CreateOptions], rdi
0x140006d7e  mov     [rsp+160h+CreateDisposition], ebx
0x140006d82  mov     r9, [r9+40h]
0x140006d86  mov     [rsp+160h+ShareAccess], 1B0Bh
0x140006d8e  mov     word ptr [rsp+160h+IoStatusBlock], 0A7h
0x140006d95  mov     dword ptr [rsp+160h+ObjectAttributes], 5
0x140006d9d  mov     byte ptr [rsp+160h+DesiredAccess], 2
0x140006da2  call    WPP_RECORDER_AND_TRACE_SF_sDdZd
0x140006da7  mov     rdi, [rbp+60h+P]
0x140006dab  jmp     loc_140007262
0x140006db0  mov     rdi, [rbp+60h+P]
0x140006db4  mov     esi, 1
0x140006db9  test    rdi, rdi
0x140006dbc  jnz     loc_140007176
0x140006dc2  cmp     byte ptr [rbp+60h+var_E0], cl
0x140006dc5  jz      loc_140007208
0x140006dcb  mov     [rsp+160h+DriverContext], rcx; DriverContext
0x140006dd0  lea     rax, [rbp+60h+var_50]
0x140006dd4  mov     [rsp+160h+Flags], 800h; Flags
0x140006ddc  lea     r9, [rbp+60h+FileObject]; FileObject
0x140006de0  mov     [rsp+160h+EaLength], ecx; EaLength
0x140006de4  lea     r8, [rbp+60h+FileHandle]; FileHandle
0x140006de8  mov     [rsp+160h+EaBuffer], rcx; EaBuffer
0x140006ded  xorps   xmm0, xmm0
0x140006df0  mov     [rsp+160h+CreateOptions], 4021h; CreateOptions
0x140006df8  mov     rdx, r15; Instance
0x140006dfb  mov     [rsp+160h+CreateDisposition], esi; CreateDisposition
0x140006dff  mov     [rsp+160h+ShareAccess], 7; ShareAccess
0x140006e07  mov     [rsp+160h+FileAttributes], 90h; FileAttributes
0x140006e0f  mov     [rsp+160h+AllocationSize], rcx; AllocationSize
0x140006e14  mov     [rsp+160h+IoStatusBlock], rax; IoStatusBlock
0x140006e19  lea     rax, [rbp+60h+var_98]
0x140006e1d  mov     [rbp+60h+var_98.RootDirectory], rcx
0x140006e21  mov     rcx, cs:Globals; Filter
0x140006e28  mov     [rsp+160h+ObjectAttributes], rax; ObjectAttributes
0x140006e2d  mov     [rsp+160h+DesiredAccess], 100001h; DesiredAccess
0x140006e35  mov     [rbp+60h+var_98.Length], 30h ; '0'
0x140006e3c  mov     [rbp+60h+var_98.Attributes], 240h
0x140006e43  mov     [rbp+60h+var_98.ObjectName], r12
0x140006e47  movdqu  xmmword ptr [rbp+60h+var_98.SecurityDescriptor], xmm0
0x140006e4c  call    cs:__imp_FltCreateFileEx2
0x140006e53  nop     dword ptr [rax+rax+00h]
0x140006e58  mov     ebx, eax
0x140006e5a  test    eax, eax
0x140006e5c  jns     loc_140006EE4
0x140006e62  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140006e68  lea     rax, WPP_RECORDER_INITIALIZED
0x140006e6f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140006e76  setnz   r8b
0x140006e7a  and     dl, 20h
0x140006e7d  jnz     short loc_140006E88
0x140006e7f  test    r8b, r8b
0x140006e82  jz      loc_140007262
0x140006e88  mov     r9, cs:WPP_GLOBAL_Control
0x140006e8f  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140006e96  mov     [rsp+160h+EaBuffer], r14
0x140006e9b  mov     ecx, 205h
0x140006ea0  mov     qword ptr [rsp+160h+CreateOptions], r12
0x140006ea5  mov     [rsp+160h+CreateDisposition], ebx
0x140006ea9  mov     r9, [r9+40h]
0x140006ead  mov     [rsp+160h+ShareAccess], 1B43h
0x140006eb5  mov     qword ptr [rsp+160h+FileAttributes], rax
0x140006eba  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140006ec1  mov     [rsp+160h+AllocationSize], rax
0x140006ec6  mov     word ptr [rsp+160h+IoStatusBlock], 0A8h
0x140006ecd  mov     dword ptr [rsp+160h+ObjectAttributes], 5
0x140006ed5  mov     byte ptr [rsp+160h+DesiredAccess], 2
0x140006eda  call    WPP_RECORDER_AND_TRACE_SF_sDdZZ
0x140006edf  jmp     loc_140007262
0x140006ee4  mov     rcx, [rbp+60h+FileObject]; FileObject
0x140006ee8  lea     r9, [rbp+60h+FileNameInformation]; FileNameInformation
0x140006eec  mov     r8d, 101h; NameOptions
0x140006ef2  mov     rdx, r15; Instance
0x140006ef5  call    cs:__imp_FltGetFileNameInformationUnsafe
0x140006efc  nop     dword ptr [rax+rax+00h]
0x140006f01  xor     ecx, ecx; CallbackData
0x140006f03  mov     ebx, eax
0x140006f05  test    eax, eax
0x140006f07  jns     short loc_140006F57
0x140006f09  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140006f0f  lea     rax, WPP_RECORDER_INITIALIZED
0x140006f16  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140006f1d  setnz   r8b
0x140006f21  and     dl, 20h
0x140006f24  jnz     short loc_140006F2F
0x140006f26  test    r8b, r8b
0x140006f29  jz      loc_140007262
0x140006f2f  mov     r9, cs:WPP_GLOBAL_Control
0x140006f36  mov     qword ptr [rsp+160h+EaLength], r15
0x140006f3b  mov     [rsp+160h+EaBuffer], r14
0x140006f40  mov     qword ptr [rsp+160h+CreateOptions], r12
0x140006f45  mov     r9, [r9+40h]
0x140006f49  mov     [rsp+160h+CreateDisposition], ebx
0x140006f4d  call    WPP_RECORDER_AND_TRACE_SF_sDdZZq
0x140006f52  jmp     loc_140007262
0x140006f57  mov     r9, [rbp+60h+FileNameInformation]
0x140006f5b  lea     rax, [rbp+60h+Src]
0x140006f5f  mov     [rsp+160h+IoStatusBlock], rcx; __int64
0x140006f64  add     r9, 8
0x140006f68  mov     [rsp+160h+ObjectAttributes], rax; __int64
0x140006f6d  mov     r8, r15
0x140006f70  lea     rax, [rbp+60h+P]
0x140006f74  xor     edx, edx
0x140006f76  mov     qword ptr [rsp+160h+DesiredAccess], rax; __int64
0x140006f7b  call    PrjfGetUnionContextByFileNameEx
0x140006f80  xor     ecx, ecx
0x140006f82  mov     ebx, eax
0x140006f84  test    eax, eax
0x140006f86  jns     short loc_140006FFC
0x140006f88  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140006f8e  lea     rax, WPP_RECORDER_INITIALIZED
0x140006f95  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140006f9c  setnz   r8b
0x140006fa0  and     dl, 20h
0x140006fa3  jnz     short loc_140006FAE
0x140006fa5  test    r8b, r8b
0x140006fa8  jz      loc_140006DA7
0x140006fae  mov     rax, [rbp+60h+FileNameInformation]
0x140006fb2  mov     ecx, 205h
0x140006fb7  mov     r9, cs:WPP_GLOBAL_Control
0x140006fbe  add     rax, 8
0x140006fc2  mov     qword ptr [rsp+160h+Flags], r15
0x140006fc7  mov     qword ptr [rsp+160h+EaLength], r14
0x140006fcc  mov     [rsp+160h+EaBuffer], rax
0x140006fd1  mov     r9, [r9+40h]
0x140006fd5  mov     qword ptr [rsp+160h+CreateOptions], r12
0x140006fda  mov     [rsp+160h+CreateDisposition], ebx
0x140006fde  mov     [rsp+160h+ShareAccess], 1B74h
0x140006fe6  mov     word ptr [rsp+160h+IoStatusBlock], 0AAh
0x140006fed  mov     byte ptr [rsp+160h+DesiredAccess], 2
0x140006ff2  call    WPP_RECORDER_AND_TRACE_SF_sDdZZZq
0x140006ff7  jmp     loc_140006DA7
0x140006ffc  mov     rdi, [rbp+60h+P]
0x140007000  test    rdi, rdi
0x140007003  jnz     loc_140007091
0x140007009  mov     ebx, 0C000CE01h
0x14000700e  mov     dl, byte ptr cs:xmmword_14001A3E0+8
0x140007014  lea     rax, WPP_RECORDER_INITIALIZED
0x14000701b  and     dl, 20h
0x14000701e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007025  jz      short loc_140007034
0x140007027  mov     rax, cs:WPP_GLOBAL_Control
0x14000702e  cmp     [rax+48h], cx
0x140007032  jnz     short loc_140007037
0x140007034  mov     sil, cl
0x140007037  test    dl, dl
0x140007039  jnz     short loc_140007044
0x14000703b  test    sil, sil
0x14000703e  jz      loc_140007262
0x140007044  mov     rax, [rbp+60h+FileNameInformation]
0x140007048  mov     ecx, 505h
0x14000704d  mov     r9, cs:_PrjfTraceRecorder
0x140007054  add     rax, 8
0x140007058  mov     qword ptr [rsp+160h+Flags], r15
0x14000705d  mov     r8b, sil
0x140007060  mov     qword ptr [rsp+160h+EaLength], r14
0x140007065  mov     [rsp+160h+EaBuffer], rax
0x14000706a  mov     qword ptr [rsp+160h+CreateOptions], r12
0x14000706f  mov     [rsp+160h+CreateDisposition], ebx
0x140007073  mov     [rsp+160h+ShareAccess], 1B86h
0x14000707b  mov     word ptr [rsp+160h+IoStatusBlock], 0ABh
0x140007082  mov     byte ptr [rsp+160h+DesiredAccess], 5
0x140007087  call    WPP_RECORDER_AND_TRACE_SF_sDdZZZq
0x14000708c  jmp     loc_140007262
0x140007091  movzx   ecx, word ptr [rbp+60h+Src]
0x140007095  movzx   eax, word ptr [r14]
0x140007099  test    cx, cx
0x14000709c  jz      short loc_1400070A5
0x14000709e  add     ax, 2
0x1400070a2  add     ax, cx
0x1400070a5  lea     rdx, [rbp+60h+SourceString]
0x1400070a9  mov     [rbp+60h+SourceString.MaximumLength], ax
0x1400070ad  mov     ecx, 6E664A50h
0x1400070b2  call    PrjfAllocateUnicodeString
0x1400070b7  mov     ebx, eax
0x1400070b9  test    eax, eax
0x1400070bb  jns     short loc_140007128
0x1400070bd  mov     dl, byte ptr cs:xmmword_14001A3D0
0x1400070c3  lea     rax, WPP_RECORDER_INITIALIZED
0x1400070ca  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400070d1  setnz   r8b
0x1400070d5  and     dl, 20h
0x1400070d8  jnz     short loc_1400070E3
0x1400070da  test    r8b, r8b
0x1400070dd  jz      loc_140007262
0x1400070e3  mov     r9, cs:WPP_GLOBAL_Control
0x1400070ea  lea     rax, [rbp+60h+Src]
0x1400070ee  mov     qword ptr [rsp+160h+Flags], r15
0x1400070f3  mov     ecx, 205h
0x1400070f8  mov     qword ptr [rsp+160h+EaLength], rax
0x1400070fd  mov     [rsp+160h+EaBuffer], r14
0x140007102  mov     r9, [r9+40h]
0x140007106  mov     qword ptr [rsp+160h+CreateOptions], r12
0x14000710b  mov     [rsp+160h+CreateDisposition], ebx
0x14000710f  mov     [rsp+160h+ShareAccess], 1BAAh
0x140007117  mov     word ptr [rsp+160h+IoStatusBlock], 0ACh
0x14000711e  mov     byte ptr [rsp+160h+DesiredAccess], 2
0x140007123  jmp     loc_140007087
0x140007128  movzx   eax, [rbp+60h+SourceString.MaximumLength]
0x14000712c  mov     rcx, [rbp+60h+SourceString.Buffer]; void *
0x140007130  mov     [rbp+60h+SourceString.Length], ax
0x140007134  movzx   eax, word ptr [rbp+60h+Src]
0x140007138  test    ax, ax
0x14000713b  jz      short loc_140007169
0x14000713d  mov     rdx, [rbp+60h+Src+8]; Src
0x140007141  mov     r8d, eax; Size
0x140007144  call    memmove
0x140007149  movzx   ecx, word ptr [rbp+60h+Src]
0x14000714d  mov     rax, [rbp+60h+SourceString.Buffer]
0x140007151  shr     rcx, 1
0x140007154  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x14000715a  mov     rax, [rbp+60h+SourceString.Buffer]
0x14000715e  movzx   ecx, word ptr [rbp+60h+Src]
0x140007162  add     rax, 2
0x140007166  add     rcx, rax; void *
0x140007169  movzx   r8d, word ptr [r14]; Size
0x14000716d  mov     rdx, [r14+8]; Src
0x140007171  call    memmove
0x140007176  mov     eax, [rdi+38h]
0x140007179  test    sil, al
0x14000717c  jz      loc_140007262
0x140007182  mov     r15, [rbp+60h+DestinationString]
0x140007189  lea     rdx, [rbp+60h+SourceString]; SourceString
0x14000718d  mov     rcx, r15; DestinationString
0x140007190  mov     r8b, sil; AllocateDestinationString
0x140007193  call    cs:__imp_RtlDowncaseUnicodeString
0x14000719a  nop     dword ptr [rax+rax+00h]
0x14000719f  mov     r9, [rbp+60h+HashValue]; HashValue
0x1400071a6  xor     r8d, r8d; HashAlgorithm
0x1400071a9  mov     dl, sil; CaseInSensitive
0x1400071ac  mov     rcx, r15; String
0x1400071af  call    cs:__imp_RtlHashUnicodeString
0x1400071b6  nop     dword ptr [rax+rax+00h]
0x1400071bb  xorps   xmm0, xmm0
0x1400071be  mov     [rbp+60h+Context.Signature], 0
0x1400071c6  lea     r14, [rdi+220h]
0x1400071cd  mov     ebx, eax
0x1400071cf  mov     rcx, r14; Resource
0x1400071d2  movdqu  xmmword ptr [rbp+60h+Context.ChainHead], xmm0
0x1400071d7  call    cs:__imp_FltAcquireResourceShared
0x1400071de  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
