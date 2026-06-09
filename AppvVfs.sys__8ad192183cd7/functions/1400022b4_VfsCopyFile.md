# VfsCopyFile

- ea: `0x1400022b4`
- end: `0x1400028ce`
- name: `VfsCopyFile`
- size: `1562`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, __int64, struct _UNICODE_STRING *, struct _FLT_INSTANCE *, void *, struct _UNICODE_STRING *, char, int, int, char, char)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140002b4c`
- `0x140002e90`
- `0x14000fd38`

## callees

- `0x140002228`
- `0x1400022b4`
- `0x1400028d4`
- `0x1400029f0`
- `0x140013b00`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140002815`
- `ntoskrnl!ObfDereferenceObject` at `0x14000282e`
- `ntoskrnl!ObfDereferenceObject` at `0x1400145fe`
- `ntoskrnl!ObfDereferenceObject` at `0x140014617`
- `ntoskrnl!ObfDereferenceObject` at `0x140002815`
- `ntoskrnl!ObfDereferenceObject` at `0x14000282e`
- `ntoskrnl!ObfDereferenceObject` at `0x1400145fe`
- `ntoskrnl!ObfDereferenceObject` at `0x140014617`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000287e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000289c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014667`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014685`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000287e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000289c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014667`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014685`
- `FLTMGR!FltQueryInformationFile` at `0x140002495`
- `FLTMGR!FltQueryInformationFile` at `0x14000268b`
- `FLTMGR!FltQueryInformationFile` at `0x140002495`
- `FLTMGR!FltQueryInformationFile` at `0x14000268b`
- `FLTMGR!FltSetInformationFile` at `0x1400026b4`
- `FLTMGR!FltSetInformationFile` at `0x1400027b2`
- `FLTMGR!FltSetInformationFile` at `0x1400027fc`
- `FLTMGR!FltSetInformationFile` at `0x1400145e5`
- `FLTMGR!FltSetInformationFile` at `0x1400026b4`
- `FLTMGR!FltSetInformationFile` at `0x1400027b2`
- `FLTMGR!FltSetInformationFile` at `0x1400027fc`
- `FLTMGR!FltSetInformationFile` at `0x1400145e5`
- `FLTMGR!FltCreateFileEx2` at `0x140002454`
- `FLTMGR!FltCreateFileEx2` at `0x14000261c`
- `FLTMGR!FltCreateFileEx2` at `0x140002454`
- `FLTMGR!FltCreateFileEx2` at `0x14000261c`
- `FLTMGR!FltClose` at `0x140002847`
- `FLTMGR!FltClose` at `0x140002860`
- `FLTMGR!FltClose` at `0x140014630`
- `FLTMGR!FltClose` at `0x140014649`
- `FLTMGR!FltClose` at `0x140002847`
- `FLTMGR!FltClose` at `0x140002860`
- `FLTMGR!FltClose` at `0x140014630`
- `FLTMGR!FltClose` at `0x140014649`

## pseudocode

```c
__int64 __fastcall VfsCopyFile(
        PFLT_INSTANCE Instance,
        __int64 a2,
        struct _UNICODE_STRING *a3,
        struct _FLT_INSTANCE *a4,
        void *a5,
        struct _UNICODE_STRING *a6,
        char a7,
        int a8,
        int a9,
        char a10,
        char a11)
{
  NTSTATUS v13; // ebx
  ULONG FileAttributes; // r9d
  ULONG CreateDisposition; // edx
  ULONG v16; // r8d
  ACCESS_MASK DesiredAccess; // ecx
  struct _FILE_OBJECT *v18; // rbx
  NTSTATUS InformationFile; // eax
  char v21[4]; // [rsp+80h] [rbp-178h] BYREF
  NTSTATUS v22; // [rsp+84h] [rbp-174h]
  int CreateOptions; // [rsp+88h] [rbp-170h]
  PFILE_OBJECT v24; // [rsp+90h] [rbp-168h] BYREF
  ULONG EaLength; // [rsp+98h] [rbp-160h]
  PFILE_OBJECT FileObject; // [rsp+A0h] [rbp-158h] BYREF
  ULONG v27; // [rsp+A8h] [rbp-150h] BYREF
  PVOID P; // [rsp+B0h] [rbp-148h]
  PVOID Buffer; // [rsp+B8h] [rbp-140h] BYREF
  int v30; // [rsp+C0h] [rbp-138h]
  void *FileHandle; // [rsp+C8h] [rbp-130h] BYREF
  HANDLE v32; // [rsp+D0h] [rbp-128h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D8h] [rbp-120h] BYREF
  struct _FLT_INSTANCE *v34; // [rsp+108h] [rbp-F0h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+110h] [rbp-E8h] BYREF
  ULONG LengthReturned[4]; // [rsp+120h] [rbp-D8h] BYREF
  __int128 FileInformation; // [rsp+130h] [rbp-C8h] BYREF
  __int128 v38; // [rsp+140h] [rbp-B8h]
  __int64 v39[2]; // [rsp+150h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+160h] [rbp-98h]
  __int128 v41; // [rsp+168h] [rbp-90h] BYREF
  __int128 v42; // [rsp+178h] [rbp-80h]
  __int64 v43; // [rsp+188h] [rbp-70h]
  FILE_INFORMATION_CLASS FileInformationClass[8]; // [rsp+190h] [rbp-68h] BYREF

  v34 = a4;
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  IoStatusBlock = 0;
  EaLength = 0;
  FileInformation = 0;
  v38 = 0;
  *(_OWORD *)v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v32 = 0;
  FileHandle = 0;
  P = 0;
  Buffer = 0;
  v27 = 0;
  FileObject = 0;
  v24 = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = a3;
  CreateOptions = a7 != 0 ? 37 : 100;
  v13 = FltCreateFileEx2(
          VfsData,
          Instance,
          &v32,
          &FileObject,
          0x100081u,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          0x80u,
          7u,
          1u,
          CreateOptions,
          0,
          0,
          0x900u,
          0);
  v22 = v13;
  if ( v13 >= 0 )
  {
    v13 = FltQueryInformationFile(Instance, FileObject, &FileInformation, 0x38u, FileNetworkOpenInformation, 0);
    v22 = v13;
    if ( v13 >= 0 )
    {
      if ( a7 )
        *(_OWORD *)v39 = 0;
      if ( (int)VfsQueryEAs(Instance, FileObject) < 0 )
      {
        P = 0;
        EaLength = 0;
        v22 = 0;
      }
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = a5;
      ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = a6;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      FileAttributes = v40 & 0xFFFFEFFF;
      LODWORD(v40) = v40 & 0xFFFFEFFF;
      CreateOptions = 16420;
      if ( a7 )
      {
        CreateDisposition = 3;
        v16 = 16421;
      }
      else
      {
        CreateDisposition = a11 != 0 ? 0 : 2;
        v16 = 16484;
      }
      CreateOptions = v16;
      DesiredAccess = 1048850;
      v30 = 1048850;
      if ( !a7 )
        DesiredAccess = 1114386;
      v30 = DesiredAccess;
      v13 = FltCreateFileEx2(
              VfsData,
              a4,
              &FileHandle,
              &v24,
              DesiredAccess,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              FileAttributes,
              7u,
              CreateDisposition,
              v16,
              P,
              EaLength,
              0x100u,
              0);
      v22 = v13;
      if ( v13 >= 0 )
      {
        if ( a10 )
        {
          v18 = v24;
          *(_OWORD *)LengthReturned = 0;
          InformationFile = FltQueryInformationFile(
                              Instance,
                              FileObject,
                              FileInformationClass,
                              0x1Cu,
                              FileAlternateNameInformation,
                              &LengthReturned[2]);
          if ( InformationFile >= 0 )
            InformationFile = FltSetInformationFile(a4, v18, FileInformationClass, 0x1Cu, FileShortNameInformation);
          v22 = InformationFile;
        }
        if ( a7
          || !v39[1]
          || (v13 = VfsAllocateCopyBuffer(&Buffer, &v27), v22 = v13, v13 >= 0)
          && (v13 = VfsCopyStreamData(Instance, FileObject, a4, v24, (__int64)&v39[1], Buffer, v27), v22 = v13, v13 >= 0) )
        {
          v41 = FileInformation;
          v42 = v38;
          LODWORD(v43) = 0;
          v13 = FltSetInformationFile(a4, v24, &v41, 0x28u, FileBasicInformation);
          v22 = v13;
        }
      }
    }
  }
  if ( v13 < 0 && v24 )
  {
    v21[0] = 1;
    FltSetInformationFile(a4, v24, v21, 1u, FileDispositionInformation);
  }
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( v24 )
    ObfDereferenceObject(v24);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( v32 )
    FltClose(v32);
  if ( P )
    ExFreePoolWithTag(P, 0x6E474656u);
  if ( Buffer )
    ExFreePoolWithTag(Buffer, 0x70434656u);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400022b4  mov     r11, rsp
0x1400022b7  push    rbx
0x1400022b8  push    rsi
0x1400022b9  push    rdi
0x1400022ba  push    r12
0x1400022bc  push    r13
0x1400022be  push    r14
0x1400022c0  push    r15
0x1400022c2  sub     rsp, 1C0h
0x1400022c9  mov     rax, cs:__security_cookie
0x1400022d0  xor     rax, rsp
0x1400022d3  mov     [rsp+1F8h+var_48], rax
0x1400022db  mov     rsi, r9
0x1400022de  mov     r14, rcx
0x1400022e1  mov     [rsp+1F8h+var_F0], r9
0x1400022e9  mov     r15, [rsp+1F8h+arg_20]
0x1400022f1  mov     r12, [rsp+1F8h+arg_28]
0x1400022f9  xor     eax, eax
0x1400022fb  xorps   xmm0, xmm0
0x1400022fe  movups  xmmword ptr [rsp+1F8h+var_120.Length], xmm0
0x140002306  movups  xmmword ptr [rsp+1F8h+var_120.ObjectName], xmm0
0x14000230e  movups  xmmword ptr [rsp+1F8h+var_120+1Ch], xmm0
0x140002316  movups  xmmword ptr [rsp+1F8h+var_E8], xmm0
0x14000231e  xor     r13d, r13d
0x140002321  mov     [r11-160h], r13d
0x140002328  movups  [rsp+1F8h+FileInformation], xmm0
0x140002330  movups  [rsp+1F8h+var_B8], xmm0
0x140002338  movups  xmmword ptr [rsp+1F8h+var_A8], xmm0
0x140002340  mov     [r11-98h], rax
0x140002347  movups  [rsp+1F8h+var_90], xmm0
0x14000234f  movups  xmmword ptr [r11-80h], xmm0
0x140002354  mov     [r11-70h], rax
0x140002358  mov     [r11-174h], r13d
0x14000235f  mov     [r11-128h], r13
0x140002366  mov     [r11-130h], r13
0x14000236d  mov     [r11-148h], r13
0x140002374  mov     [r11-140h], r13
0x14000237b  mov     [r11-150h], r13d
0x140002382  mov     [r11-158h], r13
0x140002389  mov     [r11-168h], r13
0x140002390  mov     [rsp+1F8h+var_120.Length], 30h ; '0'
0x14000239b  mov     [r11-118h], r13
0x1400023a2  mov     [rsp+1F8h+var_120.Attributes], 240h
0x1400023ad  mov     [r11-110h], r8
0x1400023b4  movdqu  xmmword ptr [rsp+1F8h+var_120.SecurityDescriptor], xmm0
0x1400023bd  mov     [rsp+1F8h+var_170], 24h ; '$'
0x1400023c8  mov     dil, [rsp+1F8h+arg_30]
0x1400023d0  mov     al, dil
0x1400023d3  neg     al
0x1400023d5  sbb     ecx, ecx
0x1400023d7  and     ecx, 0FFFFFFC1h
0x1400023da  add     ecx, 64h ; 'd'
0x1400023dd  mov     [rsp+1F8h+var_170], ecx
0x1400023e4  mov     [rsp+1F8h+DriverContext], r13; DriverContext
0x1400023e9  mov     [rsp+1F8h+Flags], 900h; Flags
0x1400023f1  mov     [rsp+1F8h+EaLength], r13d; EaLength
0x1400023f6  mov     [rsp+1F8h+EaBuffer], r13; EaBuffer
0x1400023fb  mov     [rsp+1F8h+CreateOptions], ecx; CreateOptions
0x1400023ff  mov     [rsp+1F8h+CreateDisposition], 1; CreateDisposition
0x140002407  mov     [rsp+1F8h+ShareAccess], 7; ShareAccess
0x14000240f  mov     [rsp+1F8h+FileAttributes], 80h; FileAttributes
0x140002417  mov     [rsp+1F8h+AllocationSize], r13; AllocationSize
0x14000241c  lea     rax, [r11-0E8h]
0x140002423  mov     [rsp+1F8h+IoStatusBlock], rax; IoStatusBlock
0x140002428  lea     rax, [r11-120h]
0x14000242f  mov     [rsp+1F8h+ObjectAttributes], rax; ObjectAttributes
0x140002434  mov     [rsp+1F8h+DesiredAccess], 100081h; DesiredAccess
0x14000243c  lea     r9, [r11-158h]; FileObject
0x140002443  lea     r8, [r11-128h]; FileHandle
0x14000244a  mov     rdx, r14; Instance
0x14000244d  mov     rcx, cs:VfsData; Filter
0x140002454  call    cs:__imp_FltCreateFileEx2
0x14000245b  nop     dword ptr [rax+rax+00h]
0x140002460  mov     ebx, eax
0x140002462  mov     [rsp+1F8h+var_174], eax
0x140002469  test    eax, eax
0x14000246b  js      loc_1400027C7
0x140002471  mov     [rsp+1F8h+ObjectAttributes], r13; LengthReturned
0x140002476  mov     [rsp+1F8h+DesiredAccess], 22h ; '"'; FileInformationClass
0x14000247e  lea     r9d, [r13+38h]; Length
0x140002482  lea     r8, [rsp+1F8h+FileInformation]; FileInformation
0x14000248a  mov     rdx, [rsp+1F8h+FileObject]; FileObject
0x140002492  mov     rcx, r14; Instance
0x140002495  call    cs:__imp_FltQueryInformationFile
0x14000249c  nop     dword ptr [rax+rax+00h]
0x1400024a1  mov     ebx, eax
0x1400024a3  mov     [rsp+1F8h+var_174], eax
0x1400024aa  test    eax, eax
0x1400024ac  js      loc_1400027C7
0x1400024b2  test    dil, dil
0x1400024b5  jz      short loc_1400024C3
0x1400024b7  xorps   xmm0, xmm0
0x1400024ba  movdqu  xmmword ptr [rsp+1F8h+var_A8], xmm0
0x1400024c3  lea     r9, [rsp+1F8h+var_160]
0x1400024cb  lea     r8, [rsp+1F8h+P]
0x1400024d3  mov     rdx, [rsp+1F8h+FileObject]; FileObject
0x1400024db  mov     rcx, r14; Instance
0x1400024de  call    VfsQueryEAs
0x1400024e3  mov     [rsp+1F8h+var_174], eax
0x1400024ea  test    eax, eax
0x1400024ec  jns     short loc_140002506
0x1400024ee  mov     [rsp+1F8h+P], r13
0x1400024f6  mov     [rsp+1F8h+var_160], r13d
0x1400024fe  mov     [rsp+1F8h+var_174], r13d
0x140002506  mov     [rsp+1F8h+var_120.Length], 30h ; '0'
0x140002511  mov     [rsp+1F8h+var_120.RootDirectory], r15
0x140002519  mov     [rsp+1F8h+var_120.Attributes], 240h
0x140002524  mov     [rsp+1F8h+var_120.ObjectName], r12
0x14000252c  xorps   xmm0, xmm0
0x14000252f  movdqu  xmmword ptr [rsp+1F8h+var_120.SecurityDescriptor], xmm0
0x140002538  mov     r9d, dword ptr [rsp+1F8h+var_98]
0x140002540  btr     r9d, 0Ch
0x140002545  mov     dword ptr [rsp+1F8h+var_98], r9d
0x14000254d  mov     [rsp+1F8h+var_170], 4024h
0x140002558  test    dil, dil
0x14000255b  jz      short loc_14000256A
0x14000255d  mov     edx, 3
0x140002562  mov     r8d, 4025h
0x140002568  jmp     short loc_14000257E
0x14000256a  neg     [rsp+1F8h+arg_50]
0x140002571  sbb     edx, edx
0x140002573  not     edx
0x140002575  and     edx, 2
0x140002578  mov     r8d, 4064h
0x14000257e  mov     [rsp+1F8h+var_170], r8d
0x140002586  mov     ecx, 100112h
0x14000258b  mov     [rsp+1F8h+var_138], ecx
0x140002592  mov     eax, 110112h
0x140002597  test    dil, dil
0x14000259a  cmovz   ecx, eax
0x14000259d  mov     [rsp+1F8h+var_138], ecx
0x1400025a4  mov     [rsp+1F8h+DriverContext], r13; DriverContext
0x1400025a9  mov     [rsp+1F8h+Flags], 100h; Flags
0x1400025b1  mov     eax, [rsp+1F8h+var_160]
0x1400025b8  mov     [rsp+1F8h+EaLength], eax; EaLength
0x1400025bc  mov     rax, [rsp+1F8h+P]
0x1400025c4  mov     [rsp+1F8h+EaBuffer], rax; EaBuffer
0x1400025c9  mov     [rsp+1F8h+CreateOptions], r8d; CreateOptions
0x1400025ce  mov     [rsp+1F8h+CreateDisposition], edx; CreateDisposition
0x1400025d2  mov     [rsp+1F8h+ShareAccess], 7; ShareAccess
0x1400025da  mov     [rsp+1F8h+FileAttributes], r9d; FileAttributes
0x1400025df  mov     [rsp+1F8h+AllocationSize], r13; AllocationSize
0x1400025e4  lea     rax, [rsp+1F8h+var_E8]
0x1400025ec  mov     [rsp+1F8h+IoStatusBlock], rax; IoStatusBlock
0x1400025f1  lea     rax, [rsp+1F8h+var_120]
0x1400025f9  mov     [rsp+1F8h+ObjectAttributes], rax; ObjectAttributes
0x1400025fe  mov     [rsp+1F8h+DesiredAccess], ecx; DesiredAccess
0x140002602  lea     r9, [rsp+1F8h+var_168]; FileObject
0x14000260a  lea     r8, [rsp+1F8h+FileHandle]; FileHandle
0x140002612  mov     rdx, rsi; Instance
0x140002615  mov     rcx, cs:VfsData; Filter
0x14000261c  call    cs:__imp_FltCreateFileEx2
0x140002623  nop     dword ptr [rax+rax+00h]
0x140002628  mov     ebx, eax
0x14000262a  mov     [rsp+1F8h+var_174], eax
0x140002631  test    eax, eax
0x140002633  js      loc_1400027C7
0x140002639  cmp     [rsp+1F8h+arg_48], r13b
0x140002641  jz      loc_1400026C7
0x140002647  mov     rbx, [rsp+1F8h+var_168]
0x14000264f  xorps   xmm0, xmm0
0x140002652  movups  xmmword ptr [rsp+1F8h+LengthReturned], xmm0
0x14000265a  lea     rax, [rsp+1F8h+LengthReturned+8]
0x140002662  mov     [rsp+1F8h+ObjectAttributes], rax; LengthReturned
0x140002667  mov     [rsp+1F8h+DesiredAccess], 15h; FileInformationClass
0x14000266f  mov     r15d, 1Ch
0x140002675  mov     r9d, r15d; Length
0x140002678  lea     r8, [rsp+1F8h+FileInformationClass]; FileInformation
0x140002680  mov     rdx, [rsp+1F8h+FileObject]; FileObject
0x140002688  mov     rcx, r14; Instance
0x14000268b  call    cs:__imp_FltQueryInformationFile
0x140002692  nop     dword ptr [rax+rax+00h]
0x140002697  test    eax, eax
0x140002699  js      short loc_1400026C0
0x14000269b  mov     [rsp+1F8h+DesiredAccess], 28h ; '('; FileInformationClass
0x1400026a3  mov     r9d, r15d; Length
0x1400026a6  lea     r8, [rsp+1F8h+FileInformationClass]; FileInformation
0x1400026ae  mov     rdx, rbx; FileObject
0x1400026b1  mov     rcx, rsi; Instance
0x1400026b4  call    cs:__imp_FltSetInformationFile
0x1400026bb  nop     dword ptr [rax+rax+00h]
0x1400026c0  mov     [rsp+1F8h+var_174], eax
0x1400026c7  test    dil, dil
0x1400026ca  jnz     short loc_140002749
0x1400026cc  cmp     [rsp+1F8h+var_A8+8], r13
0x1400026d4  jz      short loc_140002749
0x1400026d6  lea     rdx, [rsp+1F8h+var_150]
0x1400026de  lea     rcx, [rsp+1F8h+Buffer]
0x1400026e6  call    VfsAllocateCopyBuffer
0x1400026eb  mov     ebx, eax
0x1400026ed  mov     [rsp+1F8h+var_174], eax
0x1400026f4  test    eax, eax
0x1400026f6  js      loc_1400027C7
0x1400026fc  mov     eax, [rsp+1F8h+var_150]
0x140002703  mov     dword ptr [rsp+1F8h+IoStatusBlock], eax; ULONG
0x140002707  mov     rax, [rsp+1F8h+Buffer]
0x14000270f  mov     [rsp+1F8h+ObjectAttributes], rax; Buffer
0x140002714  lea     rax, [rsp+1F8h+var_A8+8]
0x14000271c  mov     qword ptr [rsp+1F8h+DesiredAccess], rax; FileInformation
0x140002721  mov     r9, [rsp+1F8h+var_168]; PFILE_OBJECT
0x140002729  mov     r8, rsi; PFLT_INSTANCE
0x14000272c  mov     rdx, [rsp+1F8h+FileObject]; FileObject
0x140002734  mov     rcx, r14; InitiatingInstance
0x140002737  call    VfsCopyStreamData
0x14000273c  mov     ebx, eax
0x14000273e  mov     [rsp+1F8h+var_174], eax
0x140002745  test    eax, eax
0x140002747  js      short loc_1400027C7
0x140002749  mov     rax, qword ptr [rsp+1F8h+FileInformation]
0x140002751  mov     qword ptr [rsp+1F8h+var_90], rax
0x140002759  mov     rax, qword ptr [rsp+1F8h+FileInformation+8]
0x140002761  mov     qword ptr [rsp+1F8h+var_90+8], rax
0x140002769  mov     rax, qword ptr [rsp+1F8h+var_B8]
0x140002771  mov     qword ptr [rsp+1F8h+var_80], rax
0x140002779  mov     rax, qword ptr [rsp+1F8h+var_B8+8]
0x140002781  mov     qword ptr [rsp+1F8h+var_80+8], rax
0x140002789  mov     dword ptr [rsp+1F8h+var_70], r13d
0x140002791  mov     [rsp+1F8h+DesiredAccess], 4; FileInformationClass
0x140002799  mov     r9d, 28h ; '('; Length
0x14000279f  lea     r8, [rsp+1F8h+var_90]; FileInformation
0x1400027a7  mov     rdx, [rsp+1F8h+var_168]; FileObject
0x1400027af  mov     rcx, rsi; Instance
0x1400027b2  call    cs:__imp_FltSetInformationFile
0x1400027b9  nop     dword ptr [rax+rax+00h]
0x1400027be  mov     ebx, eax
0x1400027c0  mov     [rsp+1F8h+var_174], eax
0x1400027c7  test    ebx, ebx
0x1400027c9  jns     short loc_140002808
0x1400027cb  mov     rcx, [rsp+1F8h+var_168]
0x1400027d3  test    rcx, rcx
0x1400027d6  jz      short loc_140002808
0x1400027d8  mov     [rsp+1F8h+var_178], 1
0x1400027e0  mov     [rsp+1F8h+DesiredAccess], 0Dh; FileInformationClass
0x1400027e8  mov     r9d, 1; Length
0x1400027ee  lea     r8, [rsp+1F8h+var_178]; FileInformation
0x1400027f6  mov     rdx, rcx; FileObject
0x1400027f9  mov     rcx, rsi; Instance
0x1400027fc  call    cs:__imp_FltSetInformationFile
0x140002803  nop     dword ptr [rax+rax+00h]
0x140002808  mov     rcx, [rsp+1F8h+FileObject]; Object
0x140002810  test    rcx, rcx
0x140002813  jz      short loc_140002821
0x140002815  call    cs:__imp_ObfDereferenceObject
0x14000281c  nop     dword ptr [rax+rax+00h]
0x140002821  mov     rcx, [rsp+1F8h+var_168]; Object
0x140002829  test    rcx, rcx
0x14000282c  jz      short loc_14000283A
0x14000282e  call    cs:__imp_ObfDereferenceObject
0x140002835  nop     dword ptr [rax+rax+00h]
0x14000283a  mov     rcx, [rsp+1F8h+FileHandle]; FileHandle
0x140002842  test    rcx, rcx
0x140002845  jz      short loc_140002853
0x140002847  call    cs:__imp_FltClose
0x14000284e  nop     dword ptr [rax+rax+00h]
0x140002853  mov     rcx, [rsp+1F8h+var_128]; FileHandle
0x14000285b  test    rcx, rcx
0x14000285e  jz      short loc_14000286C
0x140002860  call    cs:__imp_FltClose
0x140002867  nop     dword ptr [rax+rax+00h]
0x14000286c  mov     rcx, [rsp+1F8h+P]; P
0x140002874  test    rcx, rcx
0x140002877  jz      short loc_14000288A
0x140002879  mov     edx, 6E474656h; Tag
0x14000287e  call    cs:__imp_ExFreePoolWithTag
0x140002885  nop     dword ptr [rax+rax+00h]
0x14000288a  mov     rcx, [rsp+1F8h+Buffer]; P
0x140002892  test    rcx, rcx
0x140002895  jz      short loc_1400028A8
0x140002897  mov     edx, 70434656h; Tag
0x14000289c  call    cs:__imp_ExFreePoolWithTag
0x1400028a3  nop     dword ptr [rax+rax+00h]
0x1400028a8  mov     eax, ebx
0x1400028aa  mov     rcx, [rsp+1F8h+var_48]
0x1400028b2  xor     rcx, rsp; StackCookie
0x1400028b5  call    __security_check_cookie
0x1400028ba  add     rsp, 1C0h
0x1400028c1  pop     r15
0x1400028c3  pop     r14
0x1400028c5  pop     r13
0x1400028c7  pop     r12
0x1400028c9  pop     rdi
0x1400028ca  pop     rsi
0x1400028cb  pop     rbx
0x1400028cc  retn
0x14001459e  push    rbp
0x1400145a0  sub     rsp, 80h
0x1400145a7  mov     rbp, rdx
0x1400145aa  cmp     dword ptr [rbp+84h], 0
0x1400145b1  jge     short loc_1400145F2
0x1400145b3  mov     rcx, [rbp+90h]
0x1400145ba  test    rcx, rcx
0x1400145bd  jz      short loc_1400145F2
0x1400145bf  mov     byte ptr [rbp+80h], 1
0x1400145c6  mov     [rsp+88h+FileInformationClass], 0Dh; FileInformationClass
0x1400145ce  mov     r9d, 1; Length
0x1400145d4  lea     r8, [rbp+80h]; FileInformation
0x1400145db  mov     rdx, rcx; FileObject
0x1400145de  mov     rcx, [rbp+108h]; Instance
0x1400145e5  call    cs:__imp_FltSetInformationFile
0x1400145ec  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
