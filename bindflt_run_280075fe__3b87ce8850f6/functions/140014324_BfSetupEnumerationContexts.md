# BfSetupEnumerationContexts

- ea: `0x140014324`
- end: `0x14001499f`
- name: `BfSetupEnumerationContexts`
- size: `1659`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140024e40`

## callees

- `0x140001010`
- `0x140001348`
- `0x140003304`
- `0x140014324`
- `0x1400149a8`
- `0x140014a70`
- `0x1400152f0`
- `0x140017920`
- `0x140020a98`

## import_xrefs

- `ntoskrnl!PsGetHostSilo` at `0x140014563`
- `ntoskrnl!PsGetHostSilo` at `0x140014563`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014664`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014737`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400147bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014664`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014737`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400147bc`
- `ntoskrnl!IoGetSilo` at `0x1400147d6`
- `ntoskrnl!IoGetSilo` at `0x1400147d6`
- `ntoskrnl!ObfDereferenceObject` at `0x140014812`
- `ntoskrnl!ObfDereferenceObject` at `0x140014812`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x1400143e9`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x1400143e9`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400146ba`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400146ba`
- `FLTMGR!FltCreateFileEx2` at `0x1400145ef`
- `FLTMGR!FltCreateFileEx2` at `0x1400145ef`
- `FLTMGR!FltClose` at `0x140014802`
- `FLTMGR!FltClose` at `0x140014802`
- `FLTMGR!FltReleaseContext` at `0x14001469c`
- `FLTMGR!FltReleaseContext` at `0x14001469c`
- `FLTMGR!FltGetInstanceContext` at `0x140014415`
- `FLTMGR!FltGetInstanceContext` at `0x140014415`

## pseudocode

```c
__int64 __fastcall BfSetupEnumerationContexts(
        __int64 a1,
        struct _FLT_INSTANCE *a2,
        struct _FILE_OBJECT *a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7)
{
  int v11; // edx
  int EnumerationContext; // ebx
  char v13; // r12
  int v14; // eax
  _QWORD *v15; // r14
  unsigned int v16; // eax
  __int64 *v17; // r15
  __int64 *j; // rsi
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 Silo; // rax
  PFLT_INSTANCE *v23; // rdx
  NTSTATUS v24; // eax
  __int64 *i; // rax
  int v27; // r9d
  int v28; // r8d
  int ObjectAttributes; // [rsp+28h] [rbp-D8h]
  char IoStatusBlock; // [rsp+30h] [rbp-D0h]
  PLARGE_INTEGER AllocationSize; // [rsp+38h] [rbp-C8h]
  unsigned int v32; // [rsp+80h] [rbp-80h] BYREF
  PVOID P[2]; // [rsp+88h] [rbp-78h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+98h] [rbp-68h] BYREF
  void *FileHandle; // [rsp+A0h] [rbp-60h] BYREF
  PFILE_OBJECT FileObject; // [rsp+A8h] [rbp-58h] BYREF
  PFLT_CONTEXT Context; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v38[2]; // [rsp+B8h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK v39; // [rsp+C8h] [rbp-38h] BYREF
  struct _OBJECT_ATTRIBUTES v40; // [rsp+D8h] [rbp-28h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+108h] [rbp+8h] BYREF
  __int64 v42; // [rsp+128h] [rbp+28h]
  unsigned int v43; // [rsp+1B0h] [rbp+B0h]

  FileNameInformation = 0;
  Context = 0;
  v38[1] = v38;
  v38[0] = v38;
  v39.Pointer = 0;
  *(_OWORD *)P = 0;
  FileHandle = 0;
  FileObject = 0;
  v32 = 0;
  if ( *(_BYTE *)(a7 + 112) )
  {
    EnumerationContext = 0;
    for ( i = *(__int64 **)(a7 + 96); i != (__int64 *)(a7 + 96); i = (__int64 *)*i )
    {
      if ( !*((_DWORD *)i + 12) && *((_DWORD *)i + 14) < a6 )
      {
        *((_DWORD *)i + 14) = a6;
        *((_BYTE *)i + 17) = 0;
      }
    }
    goto LABEL_44;
  }
  EnumerationContext = BfCreateEnumerationContext(a4, a5, 0, 0, a6, a7);
  if ( EnumerationContext < 0 )
    goto LABEL_44;
  v13 = 1;
  if ( (*(_DWORD *)(a7 + 80) & 1) == 0 )
  {
LABEL_29:
    *(_BYTE *)(a7 + 112) = 1;
LABEL_30:
    if ( v13 )
      goto LABEL_44;
    goto LABEL_31;
  }
  FileNameInformation = 0;
  if ( !a3 )
    goto LABEL_57;
  EnumerationContext = FltGetFileNameInformationUnsafe(a3, a2, 0x1000102u, &FileNameInformation);
  if ( EnumerationContext < 0 )
    goto LABEL_58;
  if ( !FileNameInformation->Name.Length && FileNameInformation->Volume.Length )
  {
LABEL_57:
    EnumerationContext = -1073741811;
LABEL_58:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(AllocationSize) = EnumerationContext;
      v27 = 32;
      IoStatusBlock = -114;
      goto LABEL_60;
    }
    goto LABEL_44;
  }
  EnumerationContext = FltGetInstanceContext(a2, &Context);
  if ( EnumerationContext < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_44;
    LODWORD(AllocationSize) = EnumerationContext;
    v27 = 33;
    IoStatusBlock = -106;
    goto LABEL_64;
  }
  EnumerationContext = BfGetMappingContexts((__int64)a3, (__int64)Context, a1, &FileObject, &FileHandle, &v39);
  if ( EnumerationContext < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_44;
    LODWORD(AllocationSize) = EnumerationContext;
    v27 = 34;
    IoStatusBlock = -98;
LABEL_64:
    v28 = 5;
    goto LABEL_61;
  }
  v14 = BfCombinedMappingLookup(
          v39.Status,
          (_DWORD)FileHandle,
          (_DWORD)FileObject,
          (_DWORD)a2,
          (__int64)FileNameInformation,
          ObjectAttributes,
          (a3->Flags & 0x20000) == 0,
          (__int64)v38,
          (__int64)&v32);
  EnumerationContext = v14;
  if ( v14 == -1073741766 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        12,
        35,
        (__int64)WPP_7c51d40b00ec3a3e74a53df28c1d8c0d_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\dirctrl.c",
        180);
    }
    goto LABEL_44;
  }
  if ( v14 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(AllocationSize) = v14;
      v27 = 36;
      IoStatusBlock = -71;
      goto LABEL_60;
    }
    goto LABEL_44;
  }
  v15 = (_QWORD *)v38[0];
  v16 = 0;
LABEL_12:
  if ( v15 == v38 )
    goto LABEL_29;
  ++v16;
  v17 = (__int64 *)(v15[4] + 64LL);
  v43 = v16;
  for ( j = (__int64 *)*v17; ; j = (__int64 *)*j )
  {
    if ( j == v17 || v32 > 1 && v16 < v32 && (__int64 *)*j == v17 )
    {
      v15 = (_QWORD *)*v15;
      goto LABEL_12;
    }
    if ( j != *(__int64 **)(a7 + 48) )
      break;
LABEL_28:
    ;
  }
  EnumerationContext = BfRemapPath((_DWORD)FileNameInformation, (int)v15 + 16, *(_QWORD *)j[2], (int)j + 40, (__int64)P);
  if ( EnumerationContext < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(AllocationSize) = EnumerationContext;
      LOBYTE(v19) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v19,
        12,
        37,
        (__int64)WPP_7c51d40b00ec3a3e74a53df28c1d8c0d_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\dirctrl.c",
        235,
        AllocationSize);
    }
    goto LABEL_30;
  }
  v13 = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  FileHandle = 0;
  FileObject = 0;
  DriverContext.Size = 40;
  v20 = *(_QWORD *)(a7 + 40);
  memset(&v40, 0, 44);
  v42 = 1;
  v39 = 0;
  v21 = *(unsigned int *)(v20 + 8);
  if ( (v21 & 4) != 0 )
    Silo = IoGetSilo(a3);
  else
    Silo = PsGetHostSilo(v21, v19);
  v23 = (PFLT_INSTANCE *)j[2];
  v42 = Silo;
  v40.Length = 48;
  v40.ObjectName = (PUNICODE_STRING)P;
  v40.RootDirectory = 0;
  v40.Attributes = 512;
  *(_OWORD *)&v40.SecurityDescriptor = 0;
  v24 = FltCreateFileEx2(
          g_BindFltState,
          *v23,
          &FileHandle,
          &FileObject,
          1u,
          &v40,
          &v39,
          0,
          0,
          1u,
          1u,
          1u,
          0,
          0,
          0,
          &DriverContext);
  EnumerationContext = v24;
  if ( v24 == -1073741772 || v24 == -1073741766 || v24 == -1073741565 )
  {
    if ( P[1] )
    {
      ExFreePoolWithTag(P[1], 0x74734642u);
      P[1] = 0;
    }
    EnumerationContext = 0;
LABEL_27:
    v16 = v43;
    LODWORD(P[0]) = 0;
    goto LABEL_28;
  }
  if ( v24 >= 0 )
  {
    EnumerationContext = BfCreateEnumerationContext(
                           *(_QWORD *)j[2],
                           (__int64)FileObject,
                           (__int64)FileHandle,
                           1,
                           a6,
                           a7);
    if ( EnumerationContext < 0 )
    {
      FltClose(FileHandle);
      ObfDereferenceObject(FileObject);
      goto LABEL_44;
    }
    if ( P[1] )
    {
      ExFreePoolWithTag(P[1], 0x74734642u);
      P[1] = 0;
    }
    goto LABEL_27;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    goto LABEL_44;
  LODWORD(AllocationSize) = v24;
  v27 = 38;
  IoStatusBlock = 32;
LABEL_60:
  v28 = 12;
LABEL_61:
  LOBYTE(v11) = 2;
  WPP_RECORDER_SF_sDd(
    WPP_GLOBAL_Control->DeviceExtension,
    v11,
    v28,
    v27,
    (__int64)WPP_7c51d40b00ec3a3e74a53df28c1d8c0d_Traceguids,
    (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\dirctrl.c",
    IoStatusBlock,
    AllocationSize);
LABEL_44:
  if ( P[1] )
  {
    ExFreePoolWithTag(P[1], 0x74734642u);
    P[1] = 0;
  }
  LODWORD(P[0]) = 0;
LABEL_31:
  if ( Context )
    FltReleaseContext(Context);
  BfFreeMappingLookupList(v38);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( !*(_BYTE *)(a7 + 112) )
    BfFreeEnumerationContextList(a7 + 96);
  return (unsigned int)EnumerationContext;
}

```

## disassembly

```asm
0x140014324  push    rbp
0x140014326  push    rbx
0x140014327  push    rsi
0x140014328  push    rdi
0x140014329  push    r12
0x14001432b  push    r13
0x14001432d  push    r14
0x14001432f  push    r15
0x140014331  lea     rbp, [rsp-38h]
0x140014336  sub     rsp, 138h
0x14001433d  mov     rdi, [rbp+70h+arg_30]
0x140014344  xor     r12d, r12d
0x140014347  mov     r14, rcx
0x14001434a  mov     [rbp+70h+FileNameInformation], r12
0x14001434e  lea     rcx, [rbp+70h+var_B8]
0x140014352  mov     [rbp+70h+Context], r12
0x140014356  mov     [rbp+70h+var_B0], rcx
0x14001435a  xorps   xmm0, xmm0
0x14001435d  lea     rcx, [rbp+70h+var_B8]
0x140014361  mov     rax, r9
0x140014364  mov     r13, r8
0x140014367  mov     [rbp+70h+var_B8], rcx
0x14001436b  mov     rsi, rdx
0x14001436e  mov     qword ptr [rbp+70h+var_A8], r12
0x140014372  movups  xmmword ptr [rbp+70h+P], xmm0
0x140014376  mov     [rbp+70h+FileHandle], r12
0x14001437a  mov     [rbp+70h+FileObject], r12
0x14001437e  mov     [rbp+70h+var_F0], r12d
0x140014382  cmp     [rdi+70h], r12b
0x140014386  jnz     loc_140014701
0x14001438c  mov     ecx, [rbp+70h+arg_28]
0x140014392  xor     r9d, r9d
0x140014395  mov     rdx, [rbp+70h+arg_20]
0x14001439c  xor     r8d, r8d
0x14001439f  mov     [rsp+170h+ObjectAttributes], rdi
0x1400143a4  mov     [rsp+170h+DesiredAccess], ecx
0x1400143a8  mov     rcx, rax
0x1400143ab  call    BfCreateEnumerationContext
0x1400143b0  mov     ebx, eax
0x1400143b2  test    eax, eax
0x1400143b4  js      loc_140014729
0x1400143ba  mov     ecx, [rdi+50h]
0x1400143bd  mov     r12b, 1
0x1400143c0  test    r12b, cl
0x1400143c3  jz      loc_140014686
0x1400143c9  xor     r15d, r15d
0x1400143cc  mov     [rbp+70h+FileNameInformation], r15
0x1400143d0  test    r13, r13
0x1400143d3  jz      loc_14001482E
0x1400143d9  lea     r9, [rbp+70h+FileNameInformation]; FileNameInformation
0x1400143dd  mov     r8d, 1000102h; NameOptions
0x1400143e3  mov     rdx, rsi; Instance
0x1400143e6  mov     rcx, r13; FileObject
0x1400143e9  call    cs:__imp_FltGetFileNameInformationUnsafe
0x1400143f0  nop     dword ptr [rax+rax+00h]
0x1400143f5  mov     ebx, eax
0x1400143f7  test    eax, eax
0x1400143f9  js      loc_140014833
0x1400143ff  mov     rax, [rbp+70h+FileNameInformation]
0x140014403  cmp     [rax+8], r15w
0x140014408  jz      loc_140014823
0x14001440e  lea     rdx, [rbp+70h+Context]; Context
0x140014412  mov     rcx, rsi; Instance
0x140014415  call    cs:__imp_FltGetInstanceContext
0x14001441c  nop     dword ptr [rax+rax+00h]
0x140014421  mov     ebx, eax
0x140014423  test    eax, eax
0x140014425  js      loc_14001488E
0x14001442b  mov     rdx, [rbp+70h+Context]
0x14001442f  lea     rax, [rbp+70h+var_A8]
0x140014433  mov     [rsp+170h+ObjectAttributes], rax
0x140014438  lea     r9, [rbp+70h+FileObject]
0x14001443c  lea     rax, [rbp+70h+FileHandle]
0x140014440  mov     r8, r14
0x140014443  mov     rcx, r13
0x140014446  mov     qword ptr [rsp+170h+DesiredAccess], rax
0x14001444b  call    BfGetMappingContexts
0x140014450  mov     ebx, eax
0x140014452  test    eax, eax
0x140014454  js      loc_1400148D0
0x14001445a  mov     eax, [r13+50h]
0x14001445e  lea     rcx, [rbp+70h+var_F0]
0x140014462  mov     r8, [rbp+70h+FileObject]
0x140014466  mov     r9, rsi
0x140014469  mov     rdx, [rbp+70h+FileHandle]
0x14001446d  mov     qword ptr [rsp+170h+FileAttributes], rcx
0x140014472  lea     rcx, [rbp+70h+var_B8]
0x140014476  shr     eax, 11h
0x140014479  mov     [rsp+170h+AllocationSize], rcx
0x14001447e  not     al
0x140014480  mov     rcx, qword ptr [rbp+70h+var_A8]
0x140014484  and     al, r12b
0x140014487  mov     byte ptr [rsp+170h+IoStatusBlock], al
0x14001448b  mov     rax, [rbp+70h+FileNameInformation]
0x14001448f  mov     qword ptr [rsp+170h+DesiredAccess], rax
0x140014494  call    BfCombinedMappingLookup
0x140014499  mov     ebx, eax
0x14001449b  cmp     eax, 0C000003Ah
0x1400144a0  jz      loc_1400148E6
0x1400144a6  test    eax, eax
0x1400144a8  js      loc_14001493B
0x1400144ae  mov     r14, [rbp+70h+var_B8]
0x1400144b2  mov     eax, r15d
0x1400144b5  lea     rcx, [rbp+70h+var_B8]
0x1400144b9  cmp     r14, rcx
0x1400144bc  jz      loc_140014686
0x1400144c2  mov     r15, [r14+20h]
0x1400144c6  inc     eax
0x1400144c8  add     r15, 40h ; '@'
0x1400144cc  mov     dword ptr [rbp+70h+arg_30], eax
0x1400144d2  mov     rsi, [r15]
0x1400144d5  cmp     rsi, r15
0x1400144d8  jz      loc_1400146F9
0x1400144de  cmp     [rbp+70h+var_F0], 1
0x1400144e2  ja      loc_1400146E7
0x1400144e8  cmp     rsi, [rdi+30h]
0x1400144ec  jz      loc_14001467E
0x1400144f2  mov     r8, [rsi+10h]
0x1400144f6  lea     rax, [rbp+70h+P]
0x1400144fa  mov     rcx, [rbp+70h+FileNameInformation]
0x1400144fe  lea     r9, [rsi+28h]
0x140014502  lea     rdx, [r14+10h]
0x140014506  mov     qword ptr [rsp+170h+DesiredAccess], rax
0x14001450b  mov     r8, [r8]
0x14001450e  call    BfRemapPath
0x140014513  mov     ebx, eax
0x140014515  test    eax, eax
0x140014517  js      loc_140014755
0x14001451d  xorps   xmm0, xmm0
0x140014520  xor     r12d, r12d
0x140014523  movups  xmmword ptr [rbp+70h+var_68.Size], xmm0
0x140014527  mov     [rbp+70h+FileHandle], r12
0x14001452b  movups  xmmword ptr [rbp+70h+var_98.ObjectName], xmm0
0x14001452f  lea     eax, [r12+28h]
0x140014534  mov     [rbp+70h+FileObject], r12
0x140014538  mov     [rbp+70h+var_68.Size], ax
0x14001453c  lea     ebx, [rax-27h]
0x14001453f  mov     rax, [rdi+28h]
0x140014543  movups  xmmword ptr [rbp+70h+var_98.Length], xmm0
0x140014547  mov     [rbp+70h+var_48], rbx
0x14001454b  movups  xmmword ptr [rbp+70h+var_98+1Ch], xmm0
0x14001454f  movups  xmmword ptr [rbp+70h+var_A8], xmm0
0x140014553  movups  xmmword ptr [rbp+70h+var_68.DeviceObjectHint], xmm0
0x140014557  mov     ecx, [rax+8]
0x14001455a  test    cl, 4
0x14001455d  jnz     loc_1400147D3
0x140014563  call    cs:__imp_PsGetHostSilo
0x14001456a  nop     dword ptr [rax+rax+00h]
0x14001456f  mov     rdx, [rsi+10h]
0x140014573  lea     r9, [rbp+70h+FileObject]; FileObject
0x140014577  mov     rcx, cs:g_BindFltState; Filter
0x14001457e  lea     r8, [rbp+70h+FileHandle]; FileHandle
0x140014582  mov     [rbp+70h+var_48], rax
0x140014586  xorps   xmm0, xmm0
0x140014589  lea     rax, [rbp+70h+P]
0x14001458d  mov     [rbp+70h+var_98.Length], 30h ; '0'
0x140014594  mov     [rbp+70h+var_98.ObjectName], rax
0x140014598  lea     rax, [rbp+70h+var_68]
0x14001459c  mov     [rsp+170h+DriverContext], rax; DriverContext
0x1400145a1  lea     rax, [rbp+70h+var_A8]
0x1400145a5  mov     [rsp+170h+Flags], r12d; Flags
0x1400145aa  mov     [rsp+170h+EaLength], r12d; EaLength
0x1400145af  mov     [rsp+170h+EaBuffer], r12; EaBuffer
0x1400145b4  mov     [rsp+170h+CreateOptions], ebx; CreateOptions
0x1400145b8  mov     [rsp+170h+CreateDisposition], ebx; CreateDisposition
0x1400145bc  mov     [rsp+170h+ShareAccess], ebx; ShareAccess
0x1400145c0  mov     [rsp+170h+FileAttributes], r12d; FileAttributes
0x1400145c5  mov     [rsp+170h+AllocationSize], r12; AllocationSize
0x1400145ca  mov     [rsp+170h+IoStatusBlock], rax; IoStatusBlock
0x1400145cf  lea     rax, [rbp+70h+var_98]
0x1400145d3  mov     [rbp+70h+var_98.RootDirectory], r12
0x1400145d7  mov     [rbp+70h+var_98.Attributes], 200h
0x1400145de  movdqu  xmmword ptr [rbp+70h+var_98.SecurityDescriptor], xmm0
0x1400145e3  mov     rdx, [rdx]; Instance
0x1400145e6  mov     [rsp+170h+ObjectAttributes], rax; ObjectAttributes
0x1400145eb  mov     [rsp+170h+DesiredAccess], ebx; DesiredAccess
0x1400145ef  call    cs:__imp_FltCreateFileEx2
0x1400145f6  nop     dword ptr [rax+rax+00h]
0x1400145fb  mov     ebx, eax
0x1400145fd  cmp     eax, 0C0000034h
0x140014602  jz      loc_1400147AE
0x140014608  cmp     eax, 0C000003Ah
0x14001460d  jz      loc_1400147AE
0x140014613  cmp     eax, 0C0000103h
0x140014618  jz      loc_1400147AE
0x14001461e  test    eax, eax
0x140014620  js      loc_140014966
0x140014626  mov     rcx, [rsi+10h]
0x14001462a  mov     r9b, 1
0x14001462d  mov     eax, [rbp+70h+arg_28]
0x140014633  mov     r8, [rbp+70h+FileHandle]
0x140014637  mov     rdx, [rbp+70h+FileObject]
0x14001463b  mov     rcx, [rcx]
0x14001463e  mov     [rsp+170h+ObjectAttributes], rdi
0x140014643  mov     [rsp+170h+DesiredAccess], eax
0x140014647  call    BfCreateEnumerationContext
0x14001464c  mov     ebx, eax
0x14001464e  test    eax, eax
0x140014650  js      loc_1400147FE
0x140014656  mov     rcx, [rbp+70h+P+8]; P
0x14001465a  test    rcx, rcx
0x14001465d  jz      short loc_140014674
0x14001465f  mov     edx, 74734642h; Tag
0x140014664  call    cs:__imp_ExFreePoolWithTag
0x14001466b  nop     dword ptr [rax+rax+00h]
0x140014670  mov     [rbp+70h+P+8], r12
0x140014674  mov     eax, dword ptr [rbp+70h+arg_30]
0x14001467a  mov     dword ptr [rbp+70h+P], r12d
0x14001467e  mov     rsi, [rsi]
0x140014681  jmp     loc_1400144D5
0x140014686  mov     byte ptr [rdi+70h], 1
0x14001468a  test    r12b, r12b
0x14001468d  jnz     loc_140014729
0x140014693  mov     rcx, [rbp+70h+Context]; Context
0x140014697  test    rcx, rcx
0x14001469a  jz      short loc_1400146A8
0x14001469c  call    cs:__imp_FltReleaseContext
0x1400146a3  nop     dword ptr [rax+rax+00h]
0x1400146a8  lea     rcx, [rbp+70h+var_B8]
0x1400146ac  call    BfFreeMappingLookupList
0x1400146b1  mov     rcx, [rbp+70h+FileNameInformation]; FileNameInformation
0x1400146b5  test    rcx, rcx
0x1400146b8  jz      short loc_1400146C6
0x1400146ba  call    cs:__imp_FltReleaseFileNameInformation
0x1400146c1  nop     dword ptr [rax+rax+00h]
0x1400146c6  cmp     byte ptr [rdi+70h], 0
0x1400146ca  jz      loc_140014991
0x1400146d0  mov     eax, ebx
0x1400146d2  add     rsp, 138h
0x1400146d9  pop     r15
0x1400146db  pop     r14
0x1400146dd  pop     r13
0x1400146df  pop     r12
0x1400146e1  pop     rdi
0x1400146e2  pop     rsi
0x1400146e3  pop     rbx
0x1400146e4  pop     rbp
0x1400146e5  retn
0x1400146e7  cmp     eax, [rbp+70h+var_F0]
0x1400146ea  jnb     loc_1400144E8
0x1400146f0  cmp     [rsi], r15
0x1400146f3  jnz     loc_1400144E8
0x1400146f9  mov     r14, [r14]
0x1400146fc  jmp     loc_1400144B5
0x140014701  lea     rcx, [rdi+60h]
0x140014705  mov     ebx, r12d
0x140014708  mov     rax, [rcx]
0x14001470b  cmp     rax, rcx
0x14001470e  jz      short loc_140014729
0x140014710  mov     r8d, [rbp+70h+arg_28]
0x140014717  cmp     [rax+30h], r12d
0x14001471b  jz      loc_1400147E7
0x140014721  mov     rax, [rax]
0x140014724  cmp     rax, rcx
0x140014727  jnz     short loc_140014717
0x140014729  mov     rcx, [rbp+70h+P+8]; P
0x14001472d  test    rcx, rcx
0x140014730  jz      short loc_14001474B
0x140014732  mov     edx, 74734642h; Tag
0x140014737  call    cs:__imp_ExFreePoolWithTag
0x14001473e  nop     dword ptr [rax+rax+00h]
0x140014743  mov     [rbp+70h+P+8], 0
0x14001474b  xor     eax, eax
0x14001474d  mov     dword ptr [rbp+70h+P], eax
0x140014750  jmp     loc_140014693
0x140014755  lea     rax, WPP_RECORDER_INITIALIZED
0x14001475c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140014763  jz      loc_14001468A
0x140014769  mov     rcx, cs:WPP_GLOBAL_Control
0x140014770  lea     rax, aOnecoreBaseFsW_2; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140014777  mov     dword ptr [rsp+170h+AllocationSize], ebx
0x14001477b  mov     r9d, 25h ; '%'
0x140014781  mov     dword ptr [rsp+170h+IoStatusBlock], 8EBh
0x140014789  mov     dl, 2
0x14001478b  mov     [rsp+170h+ObjectAttributes], rax
0x140014790  lea     rax, WPP_7c51d40b00ec3a3e74a53df28c1d8c0d_Traceguids
0x140014797  mov     rcx, [rcx+40h]
0x14001479b  lea     r8d, [r9-19h]
0x14001479f  mov     qword ptr [rsp+170h+DesiredAccess], rax
0x1400147a4  call    WPP_RECORDER_SF_sDd
0x1400147a9  jmp     loc_14001468A
0x1400147ae  mov     rcx, [rbp+70h+P+8]; P
0x1400147b2  test    rcx, rcx
0x1400147b5  jz      short loc_1400147CC
0x1400147b7  mov     edx, 74734642h; Tag
0x1400147bc  call    cs:__imp_ExFreePoolWithTag
0x1400147c3  nop     dword ptr [rax+rax+00h]
0x1400147c8  mov     [rbp+70h+P+8], r12
0x1400147cc  xor     ebx, ebx
0x1400147ce  jmp     loc_140014674
0x1400147d3  mov     rcx, r13
0x1400147d6  call    cs:__imp_IoGetSilo
0x1400147dd  nop     dword ptr [rax+rax+00h]
0x1400147e2  jmp     loc_14001456F
0x1400147e7  cmp     [rax+38h], r8d
0x1400147eb  jnb     loc_140014721
0x1400147f1  mov     [rax+38h], r8d
0x1400147f5  mov     [rax+11h], r12b
0x1400147f9  jmp     loc_140014721
0x1400147fe  mov     rcx, [rbp+70h+FileHandle]; FileHandle
  ... truncated ...
```
