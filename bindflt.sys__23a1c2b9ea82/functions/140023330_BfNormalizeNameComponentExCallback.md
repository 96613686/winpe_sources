# BfNormalizeNameComponentExCallback

- ea: `0x140023330`
- end: `0x140023a86`
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
- `0x140022910`
- `0x140023330`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14002377e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002377e`
- `ntoskrnl!PsGetHostSilo` at `0x1400234b1`
- `ntoskrnl!PsGetHostSilo` at `0x1400238c9`
- `ntoskrnl!PsGetHostSilo` at `0x1400234b1`
- `ntoskrnl!PsGetHostSilo` at `0x1400238c9`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002370b`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002370b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400233fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023420`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400233fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023420`
- `ntoskrnl!IoGetSilo` at `0x1400238bb`
- `ntoskrnl!IoGetSilo` at `0x1400238bb`
- `ntoskrnl!ObfDereferenceObject` at `0x140023620`
- `ntoskrnl!ObfDereferenceObject` at `0x140023620`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400236ea`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140023728`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400236ea`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140023728`
- `FLTMGR!FltQueryDirectoryFile` at `0x1400235f4`
- `FLTMGR!FltQueryDirectoryFile` at `0x1400235f4`
- `FLTMGR!FltCreateFileEx2` at `0x14002354d`
- `FLTMGR!FltCreateFileEx2` at `0x140023965`
- `FLTMGR!FltCreateFileEx2` at `0x14002354d`
- `FLTMGR!FltCreateFileEx2` at `0x140023965`
- `FLTMGR!FltClose` at `0x14002360b`
- `FLTMGR!FltClose` at `0x14002360b`
- `FLTMGR!FltGetStreamHandleContext` at `0x1400233ad`
- `FLTMGR!FltGetStreamHandleContext` at `0x1400233ad`
- `FLTMGR!FltReleaseContext` at `0x140023a75`
- `FLTMGR!FltReleaseContext` at `0x140023a75`

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
  __int64 v13; // rdx
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
  __int64 v30; // rcx
  __int64 Silo; // rax
  NTSTATUS v32; // eax
  char IoStatusBlock; // [rsp+30h] [rbp-D0h]
  char IoStatusBlocka; // [rsp+30h] [rbp-D0h]
  PVOID *AllocationSize; // [rsp+38h] [rbp-C8h]
  char AllocationSizea; // [rsp+38h] [rbp-C8h]
  char FileAttributes; // [rsp+40h] [rbp-C0h]
  PVOID v38[2]; // [rsp+80h] [rbp-80h] BYREF
  PFILE_OBJECT FileObject; // [rsp+90h] [rbp-70h] BYREF
  PVOID P[2]; // [rsp+98h] [rbp-68h] BYREF
  const UNICODE_STRING *v41; // [rsp+A8h] [rbp-58h] BYREF
  void *FileHandle; // [rsp+B0h] [rbp-50h] BYREF
  PFLT_CONTEXT Context; // [rsp+B8h] [rbp-48h] BYREF
  UNICODE_STRING Source; // [rsp+C0h] [rbp-40h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+D0h] [rbp-30h] BYREF
  __int64 HostSilo; // [rsp+F0h] [rbp-10h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F8h] [rbp-8h] BYREF
  void *Src[2]; // [rsp+128h] [rbp+28h] BYREF
  struct _IO_STATUS_BLOCK v49; // [rsp+138h] [rbp+38h] BYREF

  v8 = a4;
  v9 = Instance;
  Context = 0;
  LOWORD(HostSilo) = 0;
  FileHandle = 0;
  FileObject = 0;
  v11 = 0;
  v41 = 0;
  Source = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  memset(&ObjectAttributes, 0, 44);
  v49 = 0;
  *(_OWORD *)v38 = 0;
  *(_OWORD *)P = 0;
  StreamHandleContext = FltGetStreamHandleContext(Instance, a2, &Context);
  LODWORD(v13) = -1073741275;
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
    StreamHandleContext = BfAllocateUnicodeString(v22, v38);
    if ( StreamHandleContext >= 0 )
    {
      StreamHandleContext = RtlAppendUnicodeStringToString((PUNICODE_STRING)v38, &Source);
      if ( StreamHandleContext >= 0 )
      {
        StreamHandleContext = RtlAppendUnicodeToString((PUNICODE_STRING)v38, L"\\");
        if ( StreamHandleContext >= 0 )
        {
          StreamHandleContext = RtlAppendUnicodeStringToString((PUNICODE_STRING)v38, FileName);
          if ( StreamHandleContext >= 0 )
          {
            v23 = BfMappingLookup(v20, Instance, 0, v38, (a8 & 1) == 0, &v41);
            v11 = (UNICODE_STRING *)v41;
            StreamHandleContext = v23;
            if ( v23 >= 0 )
            {
              if ( !RtlEqualUnicodeString((PCUNICODE_STRING)v38, v41 + 1, 0) )
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
                  v30 = *(unsigned int *)(*(_QWORD *)&v11[2].Length + 8LL);
                  if ( (v30 & 4) != 0 )
                    Silo = IoGetSilo(a2);
                  else
                    Silo = PsGetHostSilo(v30, v13);
                  HostSilo = Silo;
                  ObjectAttributes.Length = 48;
                  ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
                  ObjectAttributes.RootDirectory = 0;
                  ObjectAttributes.Attributes = 512;
                  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                  v32 = FltCreateFileEx2(
                          g_BindFltState,
                          *(PFLT_INSTANCE *)i[2],
                          &FileHandle,
                          &FileObject,
                          0x80u,
                          &ObjectAttributes,
                          &v49,
                          0,
                          0,
                          7u,
                          1u,
                          0x20u,
                          0,
                          0,
                          0,
                          &DriverContext);
                  StreamHandleContext = v32;
                  if ( v32 != -1073741772 && v32 != -1073741766 && v32 < 0 )
                  {
                    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                      goto LABEL_4;
                    FileAttributes = v32;
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
                            &v49,
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
  if ( v38[1] )
  {
    ExFreePoolWithTag(v38[1], 0x74734642u);
    v38[1] = 0;
  }
  LODWORD(v38[0]) = 0;
  if ( v11 )
    BfFreeMappingLookupEntry(v11);
  if ( Context )
    FltReleaseContext(Context);
  return (unsigned int)StreamHandleContext;
}

```

## disassembly

```asm
0x140023330  mov     [rsp-8+arg_10], rbx
0x140023335  mov     [rsp-8+arg_8], rdx
0x14002333a  mov     [rsp-8+arg_0], rcx
0x14002333f  push    rbp
0x140023340  push    rsi
0x140023341  push    rdi
0x140023342  push    r12
0x140023344  push    r13
0x140023346  push    r14
0x140023348  push    r15
0x14002334a  lea     rbp, [rsp-50h]
0x14002334f  sub     rsp, 150h
0x140023356  xorps   xmm0, xmm0
0x140023359  movzx   r12d, r9w
0x14002335d  mov     r15, rcx
0x140023360  mov     [rbp+80h+Context], 0
0x140023368  xor     ecx, ecx
0x14002336a  mov     r14, r8
0x14002336d  mov     word ptr [rbp+80h+var_90], cx
0x140023371  lea     r8, [rbp+80h+Context]; Context
0x140023375  mov     [rbp+80h+FileHandle], rcx
0x140023379  xorps   xmm1, xmm1
0x14002337c  mov     [rbp+80h+FileObject], rcx
0x140023380  xor     edi, edi
0x140023382  movups  xmmword ptr [rbp+80h+var_88.ObjectName], xmm0
0x140023386  mov     rcx, r15; Instance
0x140023389  mov     [rbp+80h+var_D8], rdi
0x14002338d  movups  xmmword ptr [rbp+80h+Source.Length], xmm0
0x140023391  movups  xmmword ptr [rbp+80h+var_B0.Size], xmm0
0x140023395  movups  xmmword ptr [rbp+80h+var_B0.DeviceObjectHint], xmm0
0x140023399  movups  xmmword ptr [rbp+80h+var_88.Length], xmm0
0x14002339d  movups  xmmword ptr [rbp+80h+var_88+1Ch], xmm0
0x1400233a1  movups  xmmword ptr [rbp+80h+var_48], xmm0
0x1400233a5  movups  xmmword ptr [rbp+80h+var_100], xmm0
0x1400233a9  movups  xmmword ptr [rbp+80h+P], xmm1
0x1400233ad  call    cs:__imp_FltGetStreamHandleContext
0x1400233b4  nop     dword ptr [rax+rax+00h]
0x1400233b9  mov     ebx, eax
0x1400233bb  mov     edx, 0C0000225h
0x1400233c0  mov     eax, 80000000h
0x1400233c5  lea     ecx, [rbx+rax]
0x1400233c8  test    eax, ecx
0x1400233ca  jnz     loc_14002346D
0x1400233d0  cmp     ebx, edx
0x1400233d2  jz      loc_14002346D
0x1400233d8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400233df  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400233e6  jnz     loc_14002368F
0x1400233ec  mov     rcx, [rbp+80h+P+8]; P
0x1400233f0  mov     esi, 74734642h
0x1400233f5  test    rcx, rcx
0x1400233f8  jz      short loc_140023410
0x1400233fa  mov     edx, esi; Tag
0x1400233fc  call    cs:__imp_ExFreePoolWithTag
0x140023403  nop     dword ptr [rax+rax+00h]
0x140023408  mov     [rbp+80h+P+8], 0
0x140023410  mov     rcx, [rbp+80h+var_100+8]; P
0x140023414  xor     eax, eax
0x140023416  mov     dword ptr [rbp+80h+P], eax
0x140023419  test    rcx, rcx
0x14002341c  jz      short loc_140023434
0x14002341e  mov     edx, esi; Tag
0x140023420  call    cs:__imp_ExFreePoolWithTag
0x140023427  nop     dword ptr [rax+rax+00h]
0x14002342c  mov     [rbp+80h+var_100+8], 0
0x140023434  xor     eax, eax
0x140023436  mov     dword ptr [rbp+80h+var_100], eax
0x140023439  test    rdi, rdi
0x14002343c  jnz     loc_140023A68
0x140023442  mov     rcx, [rbp+80h+Context]; Context
0x140023446  test    rcx, rcx
0x140023449  jnz     loc_140023A75
0x14002344f  mov     eax, ebx
0x140023451  mov     rbx, [rsp+180h+arg_10]
0x140023459  add     rsp, 150h
0x140023460  pop     r15
0x140023462  pop     r14
0x140023464  pop     r13
0x140023466  pop     r12
0x140023468  pop     rdi
0x140023469  pop     rsi
0x14002346a  pop     rbp
0x14002346b  retn
0x14002346d  mov     sil, [rbp+80h+arg_38]
0x140023474  xorps   xmm0, xmm0
0x140023477  mov     r13, [rbp+80h+FileName]
0x14002347e  not     sil
0x140023481  and     sil, 1
0x140023485  mov     [rbp+80h+var_90], 1
0x14002348d  mov     eax, 28h ; '('
0x140023492  movups  xmmword ptr [rbp+80h+var_B0.Size], xmm0
0x140023496  mov     [rbp+80h+var_B0.Size], ax
0x14002349a  movups  xmmword ptr [rbp+80h+var_B0.DeviceObjectHint], xmm0
0x14002349e  cmp     ebx, edx
0x1400234a0  jz      short loc_1400234B1
0x1400234a2  mov     rcx, [rbp+80h+Context]
0x1400234a6  mov     eax, [rcx+50h]
0x1400234a9  test    al, 1
0x1400234ab  jnz     loc_1400236A3
0x1400234b1  call    cs:__imp_PsGetHostSilo
0x1400234b8  nop     dword ptr [rax+rax+00h]
0x1400234bd  mov     rcx, cs:g_BindFltState; Filter
0x1400234c4  lea     r9, [rbp+80h+FileObject]; FileObject
0x1400234c8  mov     [rbp+80h+var_90], rax
0x1400234cc  lea     r8, [rbp+80h+FileHandle]; FileHandle
0x1400234d0  movzx   eax, sil
0x1400234d4  xorps   xmm0, xmm0
0x1400234d7  shl     eax, 6
0x1400234da  mov     rdx, r15; Instance
0x1400234dd  bts     eax, 9
0x1400234e1  mov     [rbp+80h+var_88.Length], 30h ; '0'
0x1400234e8  mov     [rbp+80h+var_88.Attributes], eax
0x1400234eb  lea     rax, [rbp+80h+var_B0]
0x1400234ef  mov     [rsp+180h+DriverContext], rax; DriverContext
0x1400234f4  lea     rax, [rbp+80h+var_48]
0x1400234f8  mov     [rsp+180h+Flags], 800h; Flags
0x140023500  mov     [rsp+180h+EaLength], edi; EaLength
0x140023504  mov     [rsp+180h+EaBuffer], rdi; EaBuffer
0x140023509  mov     [rsp+180h+CreateOptions], 1; CreateOptions
0x140023511  mov     [rsp+180h+CreateDisposition], 1; CreateDisposition
0x140023519  mov     [rsp+180h+ShareAccess], edi; ShareAccess
0x14002351d  mov     [rsp+180h+FileAttributes], 80h; FileAttributes
0x140023525  mov     [rsp+180h+AllocationSize], rdi; AllocationSize
0x14002352a  mov     [rsp+180h+IoStatusBlock], rax; IoStatusBlock
0x14002352f  lea     rax, [rbp+80h+var_88]
0x140023533  mov     [rsp+180h+ObjectAttributes], rax; ObjectAttributes
0x140023538  mov     [rsp+180h+DesiredAccess], 21h ; '!'; DesiredAccess
0x140023540  mov     [rbp+80h+var_88.RootDirectory], rdi
0x140023544  mov     [rbp+80h+var_88.ObjectName], r14
0x140023548  movdqu  xmmword ptr [rbp+80h+var_88.SecurityDescriptor], xmm0
0x14002354d  call    cs:__imp_FltCreateFileEx2
0x140023554  nop     dword ptr [rax+rax+00h]
0x140023559  mov     ebx, eax
0x14002355b  test    eax, eax
0x14002355d  jns     short loc_1400235BF
0x14002355f  lea     rax, WPP_RECORDER_INITIALIZED
0x140023566  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002356d  jz      loc_1400233EC
0x140023573  mov     [rsp+180h+FileAttributes], ebx
0x140023577  mov     r9d, 35h ; '5'
0x14002357d  mov     [rsp+180h+AllocationSize], r14
0x140023582  mov     dword ptr [rsp+180h+IoStatusBlock], 612h
0x14002358a  mov     rcx, cs:WPP_GLOBAL_Control
0x140023591  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140023598  mov     [rsp+180h+ObjectAttributes], rax
0x14002359d  mov     r8d, 9
0x1400235a3  lea     rax, WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids
0x1400235aa  mov     dl, 2
0x1400235ac  mov     qword ptr [rsp+180h+DesiredAccess], rax
0x1400235b1  mov     rcx, [rcx+40h]
0x1400235b5  call    WPP_RECORDER_SF_sDZd
0x1400235ba  jmp     loc_1400233EC
0x1400235bf  mov     r9d, [rbp+80h+Length]; Length
0x1400235c6  mov     rcx, r15; Instance
0x1400235c9  mov     r8, [rbp+80h+FileInformation]; FileInformation
0x1400235d0  mov     rdx, [rbp+80h+FileObject]; FileObject
0x1400235d4  mov     qword ptr [rsp+180h+FileAttributes], 0; LengthReturned
0x1400235dd  mov     byte ptr [rsp+180h+AllocationSize], 1; RestartScan
0x1400235e2  mov     [rsp+180h+IoStatusBlock], r13; FileName
0x1400235e7  mov     byte ptr [rsp+180h+ObjectAttributes], 1; ReturnSingleEntry
0x1400235ec  mov     [rsp+180h+DesiredAccess], 0Ch; FileInformationClass
0x1400235f4  call    cs:__imp_FltQueryDirectoryFile
0x1400235fb  nop     dword ptr [rax+rax+00h]
0x140023600  mov     rcx, [rbp+80h+FileHandle]; FileHandle
0x140023604  mov     ebx, eax
0x140023606  test    rcx, rcx
0x140023609  jz      short loc_140023617
0x14002360b  call    cs:__imp_FltClose
0x140023612  nop     dword ptr [rax+rax+00h]
0x140023617  mov     rcx, [rbp+80h+FileObject]; Object
0x14002361b  test    rcx, rcx
0x14002361e  jz      short loc_14002362C
0x140023620  call    cs:__imp_ObfDereferenceObject
0x140023627  nop     dword ptr [rax+rax+00h]
0x14002362c  test    ebx, ebx
0x14002362e  jns     loc_1400233EC
0x140023634  lea     rax, WPP_RECORDER_INITIALIZED
0x14002363b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023642  jz      loc_1400233EC
0x140023648  mov     dword ptr [rsp+180h+AllocationSize], ebx
0x14002364c  mov     r9d, 3Ah ; ':'
0x140023652  mov     dword ptr [rsp+180h+IoStatusBlock], 6CDh
0x14002365a  mov     r8d, 9
0x140023660  mov     rcx, cs:WPP_GLOBAL_Control
0x140023667  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14002366e  mov     [rsp+180h+ObjectAttributes], rax
0x140023673  mov     dl, 2
0x140023675  lea     rax, WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids
0x14002367c  mov     qword ptr [rsp+180h+DesiredAccess], rax
0x140023681  mov     rcx, [rcx+40h]
0x140023685  call    WPP_RECORDER_SF_sDd
0x14002368a  jmp     loc_1400233EC
0x14002368f  mov     dword ptr [rsp+180h+AllocationSize], ebx
0x140023693  mov     r9d, 34h ; '4'
0x140023699  mov     dword ptr [rsp+180h+IoStatusBlock], 5EAh
0x1400236a1  jmp     short loc_14002365A
0x1400236a3  mov     r15, [rcx+78h]
0x1400236a7  lea     rdx, [rbp+80h+var_100]
0x1400236ab  movzx   ecx, word ptr [r14]
0x1400236af  mov     rax, r12
0x1400236b2  add     rax, [r14+8]
0x1400236b6  sub     cx, r12w
0x1400236ba  mov     [rbp+80h+Source.Length], cx
0x1400236be  mov     [rbp+80h+Source.MaximumLength], cx
0x1400236c2  add     cx, 2
0x1400236c6  add     cx, [r13+0]
0x1400236cb  movups  xmmword ptr [rbp+80h+Src], xmm0
0x1400236cf  mov     [rbp+80h+Source.Buffer], rax
0x1400236d3  call    BfAllocateUnicodeString
0x1400236d8  mov     ebx, eax
0x1400236da  test    eax, eax
0x1400236dc  js      loc_1400233EC
0x1400236e2  lea     rdx, [rbp+80h+Source]; Source
0x1400236e6  lea     rcx, [rbp+80h+var_100]; Destination
0x1400236ea  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400236f1  nop     dword ptr [rax+rax+00h]
0x1400236f6  mov     ebx, eax
0x1400236f8  test    eax, eax
0x1400236fa  js      loc_1400233EC
0x140023700  lea     rdx, Source; "\\"
0x140023707  lea     rcx, [rbp+80h+var_100]; Destination
0x14002370b  call    cs:__imp_RtlAppendUnicodeToString
0x140023712  nop     dword ptr [rax+rax+00h]
0x140023717  mov     ebx, eax
0x140023719  test    eax, eax
0x14002371b  js      loc_1400233EC
0x140023721  mov     rdx, r13; Source
0x140023724  lea     rcx, [rbp+80h+var_100]; Destination
0x140023728  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002372f  nop     dword ptr [rax+rax+00h]
0x140023734  mov     ebx, eax
0x140023736  test    eax, eax
0x140023738  js      loc_1400233EC
0x14002373e  mov     rdx, [rbp+80h+arg_0]
0x140023745  lea     rax, [rbp+80h+var_D8]
0x140023749  mov     [rsp+180h+ObjectAttributes], rax
0x14002374e  lea     r9, [rbp+80h+var_100]
0x140023752  xor     r8d, r8d
0x140023755  mov     byte ptr [rsp+180h+DesiredAccess], sil
0x14002375a  mov     rcx, r15
0x14002375d  call    BfMappingLookup
0x140023762  mov     rdi, [rbp+80h+var_D8]
0x140023766  mov     ebx, eax
0x140023768  test    eax, eax
0x14002376a  js      loc_1400233EC
0x140023770  lea     r14, [rdi+10h]
0x140023774  xor     r8d, r8d; CaseInSensitive
0x140023777  mov     rdx, r14; String2
0x14002377a  lea     rcx, [rbp+80h+var_100]; String1
0x14002377e  call    cs:__imp_RtlEqualUnicodeString
0x140023785  nop     dword ptr [rax+rax+00h]
0x14002378a  test    al, al
0x14002378c  jz      loc_14002383B
0x140023792  xor     edx, edx
0x140023794  lea     r8, [rbp+80h+Src]
0x140023798  mov     rcx, r14
0x14002379b  call    BfRemoveFinalComponent
0x1400237a0  mov     ebx, eax
0x1400237a2  test    eax, eax
0x1400237a4  js      loc_1400233EC
0x1400237aa  movzx   edx, word ptr [rbp+80h+Src]
0x1400237ae  lea     eax, [rdx+0Ch]
0x1400237b1  cmp     [rbp+80h+Length], eax
0x1400237b7  jnb     short loc_140023813
0x1400237b9  mov     ebx, 80000005h
0x1400237be  lea     rax, WPP_RECORDER_INITIALIZED
0x1400237c5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400237cc  jz      loc_1400233EC
0x1400237d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400237d9  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x1400237e0  mov     r9d, 36h ; '6'
0x1400237e6  mov     dword ptr [rsp+180h+IoStatusBlock], 660h
0x1400237ee  mov     [rsp+180h+ObjectAttributes], rax
0x1400237f3  mov     dl, 2
0x1400237f5  lea     rax, WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids
0x1400237fc  mov     rcx, [rcx+40h]
0x140023800  lea     r8d, [r9-2Dh]
0x140023804  mov     qword ptr [rsp+180h+DesiredAccess], rax
0x140023809  call    WPP_RECORDER_SF_sD
0x14002380e  jmp     loc_1400233EC
0x140023813  mov     rcx, [rbp+80h+FileInformation]
0x14002381a  movzx   r8d, word ptr [rbp+80h+Src]; Size
0x14002381f  mov     [rcx+8], edx
0x140023822  mov     rdx, [rbp+80h+Src+8]; Src
0x140023826  mov     qword ptr [rcx], 0
0x14002382d  add     rcx, 0Ch; void *
0x140023831  call    memmove
0x140023836  jmp     loc_1400233EC
0x14002383b  mov     rax, [rdi+20h]
0x14002383f  mov     r12b, 1
0x140023842  xor     r15d, r15d
0x140023845  mov     rsi, [rax+40h]
0x140023849  mov     rax, [rdi+20h]
0x14002384d  add     rax, 40h ; '@'
0x140023851  cmp     rsi, rax
0x140023854  jz      loc_140023A5C
0x14002385a  test    r12b, r12b
0x14002385d  jz      short loc_140023864
0x14002385f  mov     r12b, r15b
0x140023862  jmp     short loc_14002386D
  ... truncated ...
```
