# BfNormalizeNameComponentExCallback

- ea: `0x140023420`
- end: `0x140023b76`
- name: `BfNormalizeNameComponentExCallback`
- size: `1878`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PUNICODE_STRING FileName, PVOID FileInformation, ULONG Length, char)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140001348`
- `0x140001990`
- `0x140001fd0`
- `0x140002e0c`
- `0x140003304`
- `0x140004cc0`
- `0x1400172f0`
- `0x1400194b0`
- `0x14001c904`
- `0x14001d130`
- `0x140021550`
- `0x140022a04`
- `0x140023420`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14002386e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002386e`
- `ntoskrnl!PsGetHostSilo` at `0x1400235a1`
- `ntoskrnl!PsGetHostSilo` at `0x1400239b9`
- `ntoskrnl!PsGetHostSilo` at `0x1400235a1`
- `ntoskrnl!PsGetHostSilo` at `0x1400239b9`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400237fb`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400237fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400234ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023510`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400234ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023510`
- `ntoskrnl!IoGetSilo` at `0x1400239ab`
- `ntoskrnl!IoGetSilo` at `0x1400239ab`
- `ntoskrnl!ObfDereferenceObject` at `0x140023710`
- `ntoskrnl!ObfDereferenceObject` at `0x140023710`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400237da`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140023818`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400237da`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140023818`
- `FLTMGR!FltQueryDirectoryFile` at `0x1400236e4`
- `FLTMGR!FltQueryDirectoryFile` at `0x1400236e4`
- `FLTMGR!FltCreateFileEx2` at `0x14002363d`
- `FLTMGR!FltCreateFileEx2` at `0x140023a55`
- `FLTMGR!FltCreateFileEx2` at `0x14002363d`
- `FLTMGR!FltCreateFileEx2` at `0x140023a55`
- `FLTMGR!FltClose` at `0x1400236fb`
- `FLTMGR!FltClose` at `0x1400236fb`
- `FLTMGR!FltGetStreamHandleContext` at `0x14002349d`
- `FLTMGR!FltGetStreamHandleContext` at `0x14002349d`
- `FLTMGR!FltReleaseContext` at `0x140023b65`
- `FLTMGR!FltReleaseContext` at `0x140023b65`

## pseudocode

```c
__int64 __fastcall BfNormalizeNameComponentExCallback(
        PFLT_INSTANCE Instance,
        struct _FILE_OBJECT *a2,
        struct _UNICODE_STRING *a3,
        unsigned __int16 a4,
        PUNICODE_STRING FileName,
        _DWORD *FileInformation,
        ULONG Length,
        char a8)
{
  __int64 v8; // r12
  struct _FLT_INSTANCE *v9; // r15
  UNICODE_STRING *v11; // rdi
  NTSTATUS StreamHandleContext; // ebx
  int v13; // edx
  PFLT_CONTEXT v14; // rcx
  int v16; // edx
  int v17; // r9d
  int v18; // r9d
  int v19; // r8d
  __int64 v20; // r15
  WCHAR *v21; // rax
  __int64 v22; // rcx
  int v23; // eax
  int v24; // edx
  size_t v25; // r8
  const void *v26; // rdx
  char v27; // r12
  __int64 *i; // rsi
  int v29; // edx
  __int64 Silo; // rax
  NTSTATUS v31; // eax
  char IoStatusBlock; // [rsp+30h] [rbp-D0h]
  char IoStatusBlocka; // [rsp+30h] [rbp-D0h]
  PVOID *AllocationSize; // [rsp+38h] [rbp-C8h]
  char AllocationSizea; // [rsp+38h] [rbp-C8h]
  char FileAttributes; // [rsp+40h] [rbp-C0h]
  PVOID v37[2]; // [rsp+80h] [rbp-80h] BYREF
  PFILE_OBJECT FileObject; // [rsp+90h] [rbp-70h] BYREF
  PVOID P[2]; // [rsp+98h] [rbp-68h] BYREF
  const UNICODE_STRING *v40; // [rsp+A8h] [rbp-58h] BYREF
  void *FileHandle; // [rsp+B0h] [rbp-50h] BYREF
  PFLT_CONTEXT Context; // [rsp+B8h] [rbp-48h] BYREF
  UNICODE_STRING Source; // [rsp+C0h] [rbp-40h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+D0h] [rbp-30h] BYREF
  __int64 HostSilo; // [rsp+F0h] [rbp-10h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F8h] [rbp-8h] BYREF
  void *Src[2]; // [rsp+128h] [rbp+28h] BYREF
  struct _IO_STATUS_BLOCK v48; // [rsp+138h] [rbp+38h] BYREF

  v8 = a4;
  v9 = Instance;
  Context = 0;
  LOWORD(HostSilo) = 0;
  FileHandle = 0;
  FileObject = 0;
  v11 = 0;
  v40 = 0;
  Source = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  memset(&ObjectAttributes, 0, 44);
  v48 = 0;
  *(_OWORD *)v37 = 0;
  *(_OWORD *)P = 0;
  StreamHandleContext = FltGetStreamHandleContext(Instance, a2, &Context);
  v13 = -1073741275;
  v14 = (PFLT_CONTEXT)(StreamHandleContext + 0x80000000);
  if ( (int)v14 >= 0 && StreamHandleContext != -1073741275 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_4;
    AllocationSizea = StreamHandleContext;
    v18 = 52;
    IoStatusBlocka = -22;
    goto LABEL_26;
  }
  HostSilo = 1;
  memset(&DriverContext, 0, sizeof(DriverContext));
  DriverContext.Size = 40;
  if ( StreamHandleContext != -1073741275 && (v14 = Context, (*((_DWORD *)Context + 20) & 1) != 0) )
  {
    v20 = *((_QWORD *)Context + 15);
    v21 = (PWSTR)((char *)a3->Buffer + v8);
    Source.Length = a3->Length - v8;
    Source.MaximumLength = Source.Length;
    v22 = (unsigned __int16)(FileName->Length + Source.Length + 2);
    *(_OWORD *)Src = 0;
    Source.Buffer = v21;
    StreamHandleContext = BfAllocateUnicodeString(v22, v37);
    if ( StreamHandleContext >= 0 )
    {
      StreamHandleContext = RtlAppendUnicodeStringToString((PUNICODE_STRING)v37, &Source);
      if ( StreamHandleContext >= 0 )
      {
        StreamHandleContext = RtlAppendUnicodeToString((PUNICODE_STRING)v37, L"\\");
        if ( StreamHandleContext >= 0 )
        {
          StreamHandleContext = RtlAppendUnicodeStringToString((PUNICODE_STRING)v37, FileName);
          if ( StreamHandleContext >= 0 )
          {
            v23 = BfMappingLookup(v20, Instance, 0, v37, (a8 & 1) == 0, &v40);
            v11 = (UNICODE_STRING *)v40;
            StreamHandleContext = v23;
            if ( v23 >= 0 )
            {
              if ( !RtlEqualUnicodeString((PCUNICODE_STRING)v37, v40 + 1, 0) )
              {
                v27 = 1;
                for ( i = *(__int64 **)(*(_QWORD *)&v11[2].Length + 64LL); ; i = (__int64 *)*i )
                {
                  if ( i == (__int64 *)(*(_QWORD *)&v11[2].Length + 64LL) )
                  {
                    v9 = Instance;
                    goto LABEL_19;
                  }
                  if ( v27 )
                    v27 = 0;
                  else
                    BfFreeUnicodeString(P);
                  StreamHandleContext = BfReplaceFirstSubstring(&Source, &v11[1], i + 5, P);
                  if ( StreamHandleContext < 0 )
                  {
                    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    {
                      LOBYTE(v29) = 2;
                      WPP_RECORDER_SF_sDZZZd(
                        WPP_GLOBAL_Control->DeviceExtension,
                        v29,
                        9,
                        55,
                        (__int64)WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids,
                        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\namesup.c",
                        132,
                        (__int64)&v11[1],
                        (__int64)(i + 5),
                        (__int64)&Source,
                        StreamHandleContext);
                    }
                    goto LABEL_4;
                  }
                  StreamHandleContext = BfPrependVolumeDeviceName(i[2], P);
                  if ( StreamHandleContext < 0 )
                    break;
                  if ( (*(_DWORD *)(*(_QWORD *)&v11[2].Length + 8LL) & 4) != 0 )
                    Silo = IoGetSilo(a2);
                  else
                    Silo = ((__int64 (*)(void))PsGetHostSilo)();
                  HostSilo = Silo;
                  ObjectAttributes.Length = 48;
                  ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
                  ObjectAttributes.RootDirectory = 0;
                  ObjectAttributes.Attributes = 512;
                  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                  v31 = FltCreateFileEx2(
                          g_BindFltState,
                          *(PFLT_INSTANCE *)i[2],
                          &FileHandle,
                          &FileObject,
                          0x80u,
                          &ObjectAttributes,
                          &v48,
                          0,
                          0,
                          7u,
                          1u,
                          0x20u,
                          0,
                          0,
                          0,
                          &DriverContext);
                  StreamHandleContext = v31;
                  if ( v31 != -1073741772 && v31 != -1073741766 && v31 < 0 )
                  {
                    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                      goto LABEL_4;
                    FileAttributes = v31;
                    AllocationSize = P;
                    v17 = 57;
                    IoStatusBlock = -76;
                    goto LABEL_18;
                  }
                }
                if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  goto LABEL_4;
                v18 = 56;
                AllocationSizea = StreamHandleContext;
                IoStatusBlocka = -116;
                v19 = 5;
                goto LABEL_27;
              }
              StreamHandleContext = BfRemoveFinalComponent(&v11[1], 0, Src);
              if ( StreamHandleContext >= 0 )
              {
                v24 = LOWORD(Src[0]);
                if ( Length >= (unsigned int)LOWORD(Src[0]) + 12 )
                {
                  v25 = LOWORD(Src[0]);
                  FileInformation[2] = LOWORD(Src[0]);
                  v26 = Src[1];
                  *(_QWORD *)FileInformation = 0;
                  memmove(FileInformation + 3, v26, v25);
                }
                else
                {
                  StreamHandleContext = -2147483643;
                  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  {
                    LOBYTE(v24) = 2;
                    WPP_RECORDER_SF_sD(
                      WPP_GLOBAL_Control->DeviceExtension,
                      v24,
                      9,
                      54,
                      (__int64)WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids,
                      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\namesup.c",
                      96);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    HostSilo = PsGetHostSilo(v14, 3221226021LL);
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = (((a8 & 1) == 0) << 6) | 0x200;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = a3;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    StreamHandleContext = FltCreateFileEx2(
                            g_BindFltState,
                            v9,
                            &FileHandle,
                            &FileObject,
                            0x21u,
                            &ObjectAttributes,
                            &v48,
                            0,
                            0x80u,
                            0,
                            1u,
                            1u,
                            0,
                            0,
                            0x800u,
                            &DriverContext);
    if ( StreamHandleContext >= 0 )
    {
LABEL_19:
      StreamHandleContext = FltQueryDirectoryFile(
                              v9,
                              FileObject,
                              FileInformation,
                              Length,
                              FileNamesInformation,
                              1u,
                              FileName,
                              1u,
                              0);
      if ( FileHandle )
        FltClose(FileHandle);
      if ( FileObject )
        ObfDereferenceObject(FileObject);
      if ( StreamHandleContext < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        AllocationSizea = StreamHandleContext;
        v18 = 58;
        IoStatusBlocka = -51;
LABEL_26:
        v19 = 9;
LABEL_27:
        LOBYTE(v13) = 2;
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v13,
          v19,
          v18,
          (__int64)WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\namesup.c",
          IoStatusBlocka,
          AllocationSizea);
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      FileAttributes = StreamHandleContext;
      v17 = 53;
      AllocationSize = (PVOID *)a3;
      IoStatusBlock = 18;
LABEL_18:
      LOBYTE(v16) = 2;
      WPP_RECORDER_SF_sDZd(
        WPP_GLOBAL_Control->DeviceExtension,
        v16,
        9,
        v17,
        (__int64)WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\namesup.c",
        IoStatusBlock,
        (__int64)AllocationSize,
        FileAttributes);
    }
  }
LABEL_4:
  if ( P[1] )
  {
    ExFreePoolWithTag(P[1], 0x74734642u);
    P[1] = 0;
  }
  LODWORD(P[0]) = 0;
  if ( v37[1] )
  {
    ExFreePoolWithTag(v37[1], 0x74734642u);
    v37[1] = 0;
  }
  LODWORD(v37[0]) = 0;
  if ( v11 )
    BfFreeMappingLookupEntry(v11);
  if ( Context )
    FltReleaseContext(Context);
  return (unsigned int)StreamHandleContext;
}

```

## disassembly

```asm
0x140023420  mov     [rsp-8+arg_10], rbx
0x140023425  mov     [rsp-8+arg_8], rdx
0x14002342a  mov     [rsp-8+arg_0], rcx
0x14002342f  push    rbp
0x140023430  push    rsi
0x140023431  push    rdi
0x140023432  push    r12
0x140023434  push    r13
0x140023436  push    r14
0x140023438  push    r15
0x14002343a  lea     rbp, [rsp-50h]
0x14002343f  sub     rsp, 150h
0x140023446  xorps   xmm0, xmm0
0x140023449  movzx   r12d, r9w
0x14002344d  mov     r15, rcx
0x140023450  mov     [rbp+80h+Context], 0
0x140023458  xor     ecx, ecx
0x14002345a  mov     r14, r8
0x14002345d  mov     word ptr [rbp+80h+var_90], cx
0x140023461  lea     r8, [rbp+80h+Context]; Context
0x140023465  mov     [rbp+80h+FileHandle], rcx
0x140023469  xorps   xmm1, xmm1
0x14002346c  mov     [rbp+80h+FileObject], rcx
0x140023470  xor     edi, edi
0x140023472  movups  xmmword ptr [rbp+80h+var_88.ObjectName], xmm0
0x140023476  mov     rcx, r15; Instance
0x140023479  mov     [rbp+80h+var_D8], rdi
0x14002347d  movups  xmmword ptr [rbp+80h+Source.Length], xmm0
0x140023481  movups  xmmword ptr [rbp+80h+var_B0.Size], xmm0
0x140023485  movups  xmmword ptr [rbp+80h+var_B0.DeviceObjectHint], xmm0
0x140023489  movups  xmmword ptr [rbp+80h+var_88.Length], xmm0
0x14002348d  movups  xmmword ptr [rbp+80h+var_88+1Ch], xmm0
0x140023491  movups  xmmword ptr [rbp+80h+var_48], xmm0
0x140023495  movups  xmmword ptr [rbp+80h+var_100], xmm0
0x140023499  movups  xmmword ptr [rbp+80h+P], xmm1
0x14002349d  call    cs:__imp_FltGetStreamHandleContext
0x1400234a4  nop     dword ptr [rax+rax+00h]
0x1400234a9  mov     ebx, eax
0x1400234ab  mov     edx, 0C0000225h
0x1400234b0  mov     eax, 80000000h
0x1400234b5  lea     ecx, [rbx+rax]
0x1400234b8  test    eax, ecx
0x1400234ba  jnz     loc_14002355D
0x1400234c0  cmp     ebx, edx
0x1400234c2  jz      loc_14002355D
0x1400234c8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400234cf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400234d6  jnz     loc_14002377F
0x1400234dc  mov     rcx, [rbp+80h+P+8]; P
0x1400234e0  mov     esi, 74734642h
0x1400234e5  test    rcx, rcx
0x1400234e8  jz      short loc_140023500
0x1400234ea  mov     edx, esi; Tag
0x1400234ec  call    cs:__imp_ExFreePoolWithTag
0x1400234f3  nop     dword ptr [rax+rax+00h]
0x1400234f8  mov     [rbp+80h+P+8], 0
0x140023500  mov     rcx, [rbp+80h+var_100+8]; P
0x140023504  xor     eax, eax
0x140023506  mov     dword ptr [rbp+80h+P], eax
0x140023509  test    rcx, rcx
0x14002350c  jz      short loc_140023524
0x14002350e  mov     edx, esi; Tag
0x140023510  call    cs:__imp_ExFreePoolWithTag
0x140023517  nop     dword ptr [rax+rax+00h]
0x14002351c  mov     [rbp+80h+var_100+8], 0
0x140023524  xor     eax, eax
0x140023526  mov     dword ptr [rbp+80h+var_100], eax
0x140023529  test    rdi, rdi
0x14002352c  jnz     loc_140023B58
0x140023532  mov     rcx, [rbp+80h+Context]; Context
0x140023536  test    rcx, rcx
0x140023539  jnz     loc_140023B65
0x14002353f  mov     eax, ebx
0x140023541  mov     rbx, [rsp+180h+arg_10]
0x140023549  add     rsp, 150h
0x140023550  pop     r15
0x140023552  pop     r14
0x140023554  pop     r13
0x140023556  pop     r12
0x140023558  pop     rdi
0x140023559  pop     rsi
0x14002355a  pop     rbp
0x14002355b  retn
0x14002355d  mov     sil, [rbp+80h+arg_38]
0x140023564  xorps   xmm0, xmm0
0x140023567  mov     r13, [rbp+80h+FileName]
0x14002356e  not     sil
0x140023571  and     sil, 1
0x140023575  mov     [rbp+80h+var_90], 1
0x14002357d  mov     eax, 28h ; '('
0x140023582  movups  xmmword ptr [rbp+80h+var_B0.Size], xmm0
0x140023586  mov     [rbp+80h+var_B0.Size], ax
0x14002358a  movups  xmmword ptr [rbp+80h+var_B0.DeviceObjectHint], xmm0
0x14002358e  cmp     ebx, edx
0x140023590  jz      short loc_1400235A1
0x140023592  mov     rcx, [rbp+80h+Context]
0x140023596  mov     eax, [rcx+50h]
0x140023599  test    al, 1
0x14002359b  jnz     loc_140023793
0x1400235a1  call    cs:__imp_PsGetHostSilo
0x1400235a8  nop     dword ptr [rax+rax+00h]
0x1400235ad  mov     rcx, cs:g_BindFltState; Filter
0x1400235b4  lea     r9, [rbp+80h+FileObject]; FileObject
0x1400235b8  mov     [rbp+80h+var_90], rax
0x1400235bc  lea     r8, [rbp+80h+FileHandle]; FileHandle
0x1400235c0  movzx   eax, sil
0x1400235c4  xorps   xmm0, xmm0
0x1400235c7  shl     eax, 6
0x1400235ca  mov     rdx, r15; Instance
0x1400235cd  bts     eax, 9
0x1400235d1  mov     [rbp+80h+var_88.Length], 30h ; '0'
0x1400235d8  mov     [rbp+80h+var_88.Attributes], eax
0x1400235db  lea     rax, [rbp+80h+var_B0]
0x1400235df  mov     [rsp+180h+DriverContext], rax; DriverContext
0x1400235e4  lea     rax, [rbp+80h+var_48]
0x1400235e8  mov     [rsp+180h+Flags], 800h; Flags
0x1400235f0  mov     [rsp+180h+EaLength], edi; EaLength
0x1400235f4  mov     [rsp+180h+EaBuffer], rdi; EaBuffer
0x1400235f9  mov     [rsp+180h+CreateOptions], 1; CreateOptions
0x140023601  mov     [rsp+180h+CreateDisposition], 1; CreateDisposition
0x140023609  mov     [rsp+180h+ShareAccess], edi; ShareAccess
0x14002360d  mov     [rsp+180h+FileAttributes], 80h; FileAttributes
0x140023615  mov     [rsp+180h+AllocationSize], rdi; AllocationSize
0x14002361a  mov     [rsp+180h+IoStatusBlock], rax; IoStatusBlock
0x14002361f  lea     rax, [rbp+80h+var_88]
0x140023623  mov     [rsp+180h+ObjectAttributes], rax; ObjectAttributes
0x140023628  mov     [rsp+180h+DesiredAccess], 21h ; '!'; DesiredAccess
0x140023630  mov     [rbp+80h+var_88.RootDirectory], rdi
0x140023634  mov     [rbp+80h+var_88.ObjectName], r14
0x140023638  movdqu  xmmword ptr [rbp+80h+var_88.SecurityDescriptor], xmm0
0x14002363d  call    cs:__imp_FltCreateFileEx2
0x140023644  nop     dword ptr [rax+rax+00h]
0x140023649  mov     ebx, eax
0x14002364b  test    eax, eax
0x14002364d  jns     short loc_1400236AF
0x14002364f  lea     rax, WPP_RECORDER_INITIALIZED
0x140023656  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002365d  jz      loc_1400234DC
0x140023663  mov     [rsp+180h+FileAttributes], ebx
0x140023667  mov     r9d, 35h ; '5'
0x14002366d  mov     [rsp+180h+AllocationSize], r14
0x140023672  mov     dword ptr [rsp+180h+IoStatusBlock], 612h
0x14002367a  mov     rcx, cs:WPP_GLOBAL_Control
0x140023681  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140023688  mov     [rsp+180h+ObjectAttributes], rax
0x14002368d  mov     r8d, 9
0x140023693  lea     rax, WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids
0x14002369a  mov     dl, 2
0x14002369c  mov     qword ptr [rsp+180h+DesiredAccess], rax
0x1400236a1  mov     rcx, [rcx+40h]
0x1400236a5  call    WPP_RECORDER_SF_sDZd
0x1400236aa  jmp     loc_1400234DC
0x1400236af  mov     r9d, [rbp+80h+Length]; Length
0x1400236b6  mov     rcx, r15; Instance
0x1400236b9  mov     r8, [rbp+80h+FileInformation]; FileInformation
0x1400236c0  mov     rdx, [rbp+80h+FileObject]; FileObject
0x1400236c4  mov     qword ptr [rsp+180h+FileAttributes], 0; LengthReturned
0x1400236cd  mov     byte ptr [rsp+180h+AllocationSize], 1; RestartScan
0x1400236d2  mov     [rsp+180h+IoStatusBlock], r13; FileName
0x1400236d7  mov     byte ptr [rsp+180h+ObjectAttributes], 1; ReturnSingleEntry
0x1400236dc  mov     [rsp+180h+DesiredAccess], 0Ch; FileInformationClass
0x1400236e4  call    cs:__imp_FltQueryDirectoryFile
0x1400236eb  nop     dword ptr [rax+rax+00h]
0x1400236f0  mov     rcx, [rbp+80h+FileHandle]; FileHandle
0x1400236f4  mov     ebx, eax
0x1400236f6  test    rcx, rcx
0x1400236f9  jz      short loc_140023707
0x1400236fb  call    cs:__imp_FltClose
0x140023702  nop     dword ptr [rax+rax+00h]
0x140023707  mov     rcx, [rbp+80h+FileObject]; Object
0x14002370b  test    rcx, rcx
0x14002370e  jz      short loc_14002371C
0x140023710  call    cs:__imp_ObfDereferenceObject
0x140023717  nop     dword ptr [rax+rax+00h]
0x14002371c  test    ebx, ebx
0x14002371e  jns     loc_1400234DC
0x140023724  lea     rax, WPP_RECORDER_INITIALIZED
0x14002372b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023732  jz      loc_1400234DC
0x140023738  mov     dword ptr [rsp+180h+AllocationSize], ebx
0x14002373c  mov     r9d, 3Ah ; ':'
0x140023742  mov     dword ptr [rsp+180h+IoStatusBlock], 6CDh
0x14002374a  mov     r8d, 9
0x140023750  mov     rcx, cs:WPP_GLOBAL_Control
0x140023757  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14002375e  mov     [rsp+180h+ObjectAttributes], rax
0x140023763  mov     dl, 2
0x140023765  lea     rax, WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids
0x14002376c  mov     qword ptr [rsp+180h+DesiredAccess], rax
0x140023771  mov     rcx, [rcx+40h]
0x140023775  call    WPP_RECORDER_SF_sDd
0x14002377a  jmp     loc_1400234DC
0x14002377f  mov     dword ptr [rsp+180h+AllocationSize], ebx
0x140023783  mov     r9d, 34h ; '4'
0x140023789  mov     dword ptr [rsp+180h+IoStatusBlock], 5EAh
0x140023791  jmp     short loc_14002374A
0x140023793  mov     r15, [rcx+78h]
0x140023797  lea     rdx, [rbp+80h+var_100]
0x14002379b  movzx   ecx, word ptr [r14]
0x14002379f  mov     rax, r12
0x1400237a2  add     rax, [r14+8]
0x1400237a6  sub     cx, r12w
0x1400237aa  mov     [rbp+80h+Source.Length], cx
0x1400237ae  mov     [rbp+80h+Source.MaximumLength], cx
0x1400237b2  add     cx, 2
0x1400237b6  add     cx, [r13+0]
0x1400237bb  movups  xmmword ptr [rbp+80h+Src], xmm0
0x1400237bf  mov     [rbp+80h+Source.Buffer], rax
0x1400237c3  call    BfAllocateUnicodeString
0x1400237c8  mov     ebx, eax
0x1400237ca  test    eax, eax
0x1400237cc  js      loc_1400234DC
0x1400237d2  lea     rdx, [rbp+80h+Source]; Source
0x1400237d6  lea     rcx, [rbp+80h+var_100]; Destination
0x1400237da  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400237e1  nop     dword ptr [rax+rax+00h]
0x1400237e6  mov     ebx, eax
0x1400237e8  test    eax, eax
0x1400237ea  js      loc_1400234DC
0x1400237f0  lea     rdx, Source; "\\"
0x1400237f7  lea     rcx, [rbp+80h+var_100]; Destination
0x1400237fb  call    cs:__imp_RtlAppendUnicodeToString
0x140023802  nop     dword ptr [rax+rax+00h]
0x140023807  mov     ebx, eax
0x140023809  test    eax, eax
0x14002380b  js      loc_1400234DC
0x140023811  mov     rdx, r13; Source
0x140023814  lea     rcx, [rbp+80h+var_100]; Destination
0x140023818  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002381f  nop     dword ptr [rax+rax+00h]
0x140023824  mov     ebx, eax
0x140023826  test    eax, eax
0x140023828  js      loc_1400234DC
0x14002382e  mov     rdx, [rbp+80h+arg_0]
0x140023835  lea     rax, [rbp+80h+var_D8]
0x140023839  mov     [rsp+180h+ObjectAttributes], rax
0x14002383e  lea     r9, [rbp+80h+var_100]
0x140023842  xor     r8d, r8d
0x140023845  mov     byte ptr [rsp+180h+DesiredAccess], sil
0x14002384a  mov     rcx, r15
0x14002384d  call    BfMappingLookup
0x140023852  mov     rdi, [rbp+80h+var_D8]
0x140023856  mov     ebx, eax
0x140023858  test    eax, eax
0x14002385a  js      loc_1400234DC
0x140023860  lea     r14, [rdi+10h]
0x140023864  xor     r8d, r8d; CaseInSensitive
0x140023867  mov     rdx, r14; String2
0x14002386a  lea     rcx, [rbp+80h+var_100]; String1
0x14002386e  call    cs:__imp_RtlEqualUnicodeString
0x140023875  nop     dword ptr [rax+rax+00h]
0x14002387a  test    al, al
0x14002387c  jz      loc_14002392B
0x140023882  xor     edx, edx
0x140023884  lea     r8, [rbp+80h+Src]
0x140023888  mov     rcx, r14
0x14002388b  call    BfRemoveFinalComponent
0x140023890  mov     ebx, eax
0x140023892  test    eax, eax
0x140023894  js      loc_1400234DC
0x14002389a  movzx   edx, word ptr [rbp+80h+Src]
0x14002389e  lea     eax, [rdx+0Ch]
0x1400238a1  cmp     [rbp+80h+Length], eax
0x1400238a7  jnb     short loc_140023903
0x1400238a9  mov     ebx, 80000005h
0x1400238ae  lea     rax, WPP_RECORDER_INITIALIZED
0x1400238b5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400238bc  jz      loc_1400234DC
0x1400238c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400238c9  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x1400238d0  mov     r9d, 36h ; '6'
0x1400238d6  mov     dword ptr [rsp+180h+IoStatusBlock], 660h
0x1400238de  mov     [rsp+180h+ObjectAttributes], rax
0x1400238e3  mov     dl, 2
0x1400238e5  lea     rax, WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids
0x1400238ec  mov     rcx, [rcx+40h]
0x1400238f0  lea     r8d, [r9-2Dh]
0x1400238f4  mov     qword ptr [rsp+180h+DesiredAccess], rax
0x1400238f9  call    WPP_RECORDER_SF_sD
0x1400238fe  jmp     loc_1400234DC
0x140023903  mov     rcx, [rbp+80h+FileInformation]
0x14002390a  movzx   r8d, word ptr [rbp+80h+Src]; Size
0x14002390f  mov     [rcx+8], edx
0x140023912  mov     rdx, [rbp+80h+Src+8]; Src
0x140023916  mov     qword ptr [rcx], 0
0x14002391d  add     rcx, 0Ch; void *
0x140023921  call    memmove
0x140023926  jmp     loc_1400234DC
0x14002392b  mov     rax, [rdi+20h]
0x14002392f  mov     r12b, 1
0x140023932  xor     r15d, r15d
0x140023935  mov     rsi, [rax+40h]
0x140023939  mov     rax, [rdi+20h]
0x14002393d  add     rax, 40h ; '@'
0x140023941  cmp     rsi, rax
0x140023944  jz      loc_140023B4C
0x14002394a  test    r12b, r12b
0x14002394d  jz      short loc_140023954
0x14002394f  mov     r12b, r15b
0x140023952  jmp     short loc_14002395D
  ... truncated ...
```
