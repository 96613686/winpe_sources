# BfGenerateFileNameCallback

- ea: `0x140012c60`
- end: `0x14001360a`
- name: `BfGenerateFileNameCallback`
- size: `2474`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, int@<edx>, PFLT_CALLBACK_DATA CallbackData@<r8>, __int64, PFLT_NAME_CONTROL NameCtrl)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x140001010`
- `0x140001348`
- `0x140003304`
- `0x1400127a0`
- `0x140012c60`
- `0x140013610`
- `0x140013780`
- `0x140013864`
- `0x140017bf0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140012f26`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140013150`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140012f26`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140013150`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140013103`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140013103`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012f8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012f8e`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x140012f05`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x14001312f`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x140012f05`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x14001312f`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140013008`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x1400130aa`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140013008`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x1400130aa`
- `FLTMGR!FltGetFileNameInformation` at `0x140012ec2`
- `FLTMGR!FltGetFileNameInformation` at `0x140012ec2`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140012f3b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140012fe1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140012f3b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140012fe1`
- `FLTMGR!FltAcquireResourceShared` at `0x140012d3b`
- `FLTMGR!FltAcquireResourceShared` at `0x140012e3a`
- `FLTMGR!FltAcquireResourceShared` at `0x140013563`
- `FLTMGR!FltAcquireResourceShared` at `0x140012d3b`
- `FLTMGR!FltAcquireResourceShared` at `0x140012e3a`
- `FLTMGR!FltAcquireResourceShared` at `0x140013563`
- `FLTMGR!FltGetStreamHandleContext` at `0x140012d8a`
- `FLTMGR!FltGetStreamHandleContext` at `0x140012d8a`
- `FLTMGR!FltReleaseContext` at `0x140012dc1`
- `FLTMGR!FltReleaseContext` at `0x140012ddd`
- `FLTMGR!FltReleaseContext` at `0x140012faf`
- `FLTMGR!FltReleaseContext` at `0x140012fcc`
- `FLTMGR!FltReleaseContext` at `0x140012dc1`
- `FLTMGR!FltReleaseContext` at `0x140012ddd`
- `FLTMGR!FltReleaseContext` at `0x140012faf`
- `FLTMGR!FltReleaseContext` at `0x140012fcc`
- `FLTMGR!FltReleaseResource` at `0x140012d54`
- `FLTMGR!FltReleaseResource` at `0x140012e53`
- `FLTMGR!FltReleaseResource` at `0x14001357c`
- `FLTMGR!FltReleaseResource` at `0x14001358d`
- `FLTMGR!FltReleaseResource` at `0x140012d54`
- `FLTMGR!FltReleaseResource` at `0x140012e53`
- `FLTMGR!FltReleaseResource` at `0x14001357c`
- `FLTMGR!FltReleaseResource` at `0x14001358d`
- `FLTMGR!FltGetInstanceContext` at `0x140012cc7`
- `FLTMGR!FltGetInstanceContext` at `0x140012cc7`

## pseudocode

```c
__int64 __fastcall BfGenerateFileNameCallback(
        PFLT_INSTANCE Instance,
        struct _FILE_OBJECT *a2,
        PFLT_CALLBACK_DATA CallbackData,
        int a4,
        _BYTE *a5,
        PFLT_NAME_CONTROL NameCtrl)
{
  _BYTE *v9; // r13
  NTSTATUS InstanceContext; // eax
  struct _FLT_INSTANCE *v11; // rdx
  NTSTATUS v12; // ebx
  int MappingContexts; // eax
  _QWORD *v14; // rbx
  _QWORD *v15; // rbx
  _QWORD *v16; // rbx
  struct _ERESOURCE *v17; // rcx
  int v18; // edx
  NTSTATUS StreamHandleContext; // eax
  PFLT_CONTEXT v20; // rcx
  PFLT_INSTANCE v21; // rdx
  _WORD *v22; // rax
  struct _FILE_OBJECT *v23; // r10
  int v24; // r9d
  int v25; // r8d
  FLT_FILE_NAME_OPTIONS v26; // edi
  NTSTATUS FileNameInformationUnsafe; // eax
  PFLT_NAME_CONTROL v28; // rdi
  NTSTATUS v29; // eax
  int v31; // r9d
  PVOID FsContext2; // rax
  unsigned int v33; // edi
  int v34; // eax
  USHORT v35; // dx
  PFLT_NAME_CONTROL v36; // rdi
  NTSTATUS v37; // eax
  int v38; // eax
  int v39; // eax
  int Name; // eax
  int v41; // eax
  int NormalizedName; // eax
  int OpenedName; // eax
  char v44; // [rsp+38h] [rbp-39h]
  char v45; // [rsp+38h] [rbp-39h]
  __int64 v46; // [rsp+40h] [rbp-31h]
  char v47; // [rsp+40h] [rbp-31h]
  PFLT_CONTEXT v48; // [rsp+48h] [rbp-29h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-21h] BYREF
  __int64 v50; // [rsp+58h] [rbp-19h] BYREF
  PFLT_INSTANCE v51; // [rsp+60h] [rbp-11h] BYREF
  PVOID FsContext; // [rsp+68h] [rbp-9h]
  PVOID P[2]; // [rsp+70h] [rbp-1h] BYREF
  PFLT_CONTEXT Context; // [rsp+D0h] [rbp+5Fh] BYREF
  ULONG Flags; // [rsp+E0h] [rbp+6Fh]

  FsContext = a2->FsContext;
  FileNameInformation = 0;
  v9 = 0;
  Context = 0;
  v48 = 0;
  v50 = 0;
  v51 = 0;
  *(_OWORD *)P = 0;
  InstanceContext = FltGetInstanceContext(Instance, &Context);
  v12 = InstanceContext;
  if ( InstanceContext < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_37;
    LODWORD(v46) = InstanceContext;
    v24 = 38;
    v44 = 30;
    goto LABEL_100;
  }
  MappingContexts = BfGetMappingContexts(
                      (_DWORD)a2,
                      (_DWORD)Context,
                      (_DWORD)CallbackData,
                      (unsigned int)&v48,
                      (__int64)&v50,
                      (__int64)&v51);
  v12 = MappingContexts;
  if ( MappingContexts < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_37;
    LODWORD(v46) = MappingContexts;
    v44 = 38;
    v24 = 39;
    v25 = 5;
    goto LABEL_101;
  }
  v14 = v48;
  if ( v48 )
  {
    FltAcquireResourceShared((PERESOURCE)((char *)v48 + 16));
    v17 = (struct _ERESOURCE *)(v14 + 2);
    if ( (_QWORD *)*v14 != v14 )
      goto LABEL_7;
    FltReleaseResource(v17);
  }
  v15 = (_QWORD *)v50;
  if ( v50 )
  {
    FltAcquireResourceShared((PERESOURCE)(v50 + 16));
    v17 = (struct _ERESOURCE *)(v15 + 2);
    if ( (_QWORD *)*v15 != v15 )
      goto LABEL_7;
    FltReleaseResource(v17);
  }
  v16 = v51;
  if ( !v51 )
    goto LABEL_27;
  FltAcquireResourceShared((PERESOURCE)((char *)v51 + 16));
  v17 = (struct _ERESOURCE *)(v16 + 2);
  if ( (_QWORD *)*v16 == v16 )
  {
    FltReleaseResource(v17);
LABEL_27:
    v48 = 0;
    v26 = a4 & 0xFE00FFFF;
    if ( CallbackData )
      FileNameInformationUnsafe = FltGetFileNameInformation(CallbackData, v26, (PFLT_FILE_NAME_INFORMATION *)&v48);
    else
      FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(a2, Instance, v26, (PFLT_FILE_NAME_INFORMATION *)&v48);
    v12 = FileNameInformationUnsafe;
    if ( FileNameInformationUnsafe >= 0 )
    {
      LODWORD(v11) = *((unsigned __int16 *)v48 + 4);
      if ( (_WORD)v11 || !*((_WORD *)v48 + 12) )
      {
        v28 = NameCtrl;
        v29 = FltCheckAndGrowNameControl(NameCtrl, (USHORT)v11);
        v12 = v29;
        if ( v29 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_33;
          v47 = v29;
          v31 = 37;
          v45 = -69;
          goto LABEL_49;
        }
        RtlCopyUnicodeString(&v28->Name, (PCUNICODE_STRING)((char *)v48 + 8));
LABEL_33:
        if ( v48 )
          FltReleaseFileNameInformation((PFLT_FILE_NAME_INFORMATION)v48);
        if ( v12 >= 0 )
          goto LABEL_36;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_37;
        LODWORD(v46) = v12;
        v24 = 40;
        v44 = 57;
        goto LABEL_100;
      }
      v12 = -1073741811;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v47 = v12;
      v31 = 36;
      v45 = -77;
LABEL_49:
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v11,
        9,
        v31,
        (__int64)WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\namesup.c",
        v45,
        v47);
      goto LABEL_33;
    }
    goto LABEL_33;
  }
LABEL_7:
  FltReleaseResource(v17);
  Flags = a2->Flags;
  if ( (Flags & 0x400000) != 0 )
    goto LABEL_27;
  if ( !FsContext )
  {
    if ( CallbackData )
    {
      if ( (unsigned __int8)a4 == 1 )
      {
        NormalizedName = BfpGeneratePreCreateNormalizedName(
                           (__int64)Instance,
                           (__int64)a2,
                           CallbackData,
                           a4 & 0xFC00FF00 | 0x2000000,
                           (__int64)Context,
                           NameCtrl);
        v12 = NormalizedName;
        if ( NormalizedName >= 0 )
          goto LABEL_36;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v46) = NormalizedName;
          v24 = 43;
          v44 = -126;
          goto LABEL_100;
        }
      }
      else if ( (unsigned __int8)a4 == 2 )
      {
        OpenedName = BfpGeneratePreCreateOpenedName((__int64)Instance, NameCtrl);
        v12 = OpenedName;
        if ( OpenedName >= 0 )
          goto LABEL_36;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v46) = OpenedName;
          v24 = 42;
          v44 = 112;
          goto LABEL_100;
        }
      }
      else
      {
        v12 = -1073741811;
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v18) = 2;
        WPP_RECORDER_SF_sD(
          WPP_GLOBAL_Control->DeviceExtension,
          v18,
          9,
          41,
          (__int64)WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\namesup.c",
          88);
      }
      v12 = -1073741811;
    }
    goto LABEL_37;
  }
  v48 = 0;
  StreamHandleContext = FltGetStreamHandleContext(Instance, a2, &v48);
  v12 = StreamHandleContext;
  if ( StreamHandleContext == -1073741275 )
  {
    v9 = v48;
LABEL_13:
    v20 = 0;
    v48 = 0;
    v12 = 0;
    goto LABEL_14;
  }
  if ( StreamHandleContext >= 0 )
  {
    v9 = v48;
    if ( (*((_DWORD *)v48 + 20) & 1) == 0 )
    {
      FltReleaseContext(v48);
      v9 = 0;
    }
    goto LABEL_13;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v11) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v11,
      7,
      25,
      (__int64)WPP_ab4056511ca038337f1519c30a6fffbb_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\context.c",
      173,
      StreamHandleContext);
  }
  v20 = v48;
LABEL_14:
  if ( v20 )
    FltReleaseContext(v20);
  if ( v12 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_37;
    LODWORD(v46) = v12;
    v24 = 44;
    v44 = -84;
    goto LABEL_100;
  }
  if ( Context )
  {
    v21 = *(PFLT_INSTANCE *)Context;
    v51 = *(PFLT_INSTANCE *)Context;
  }
  else
  {
    v21 = Instance;
    v51 = Instance;
  }
  if ( !v9 )
  {
    v38 = BfpPassthroughNameQuery(CallbackData, a2, v21, a4 & 0xFE00FFFF, NameCtrl);
    v12 = v38;
    if ( v38 >= 0 )
      goto LABEL_36;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_37;
    LODWORD(v46) = v38;
    v24 = 45;
    v44 = -49;
LABEL_100:
    v25 = 9;
LABEL_101:
    LOBYTE(v11) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v11,
      v25,
      v24,
      (__int64)WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\namesup.c",
      v44,
      v46,
      v48);
    goto LABEL_37;
  }
  v22 = a2->FsContext;
  if ( v22 && *v22 == 25649 && (v9[80] & 1) != 0 )
  {
    FsContext2 = a2->FsContext2;
    v23 = (struct _FILE_OBJECT *)*((_QWORD *)FsContext2 + 1);
    v11 = (struct _FLT_INSTANCE *)*((_QWORD *)FsContext2 + 2);
  }
  else
  {
    v23 = a2;
    v11 = Instance;
  }
  if ( (unsigned __int8)a4 == 3 )
  {
    FileNameInformation = 0;
    if ( v23 )
    {
      v33 = a4 & 0xFE00FF00;
      v12 = FltGetFileNameInformationUnsafe(v23, v11, v33 | 1, &FileNameInformation);
      if ( v12 < 0 )
        goto LABEL_103;
      if ( FileNameInformation->Name.Length || !FileNameInformation->Volume.Length )
      {
        v34 = BfFormatPathFromFileNameInfo(FileNameInformation, 0, P);
        v12 = v34;
        if ( v34 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_37;
          LODWORD(v46) = v34;
          v24 = 49;
          v44 = 43;
          goto LABEL_100;
        }
        if ( RtlCompareUnicodeString(
               (PCUNICODE_STRING)P,
               (PCUNICODE_STRING)(*((_QWORD *)v9 + 6) + 40LL),
               (Flags & 0x20000) == 0) )
        {
          v41 = BfpPassthroughNameQuery(CallbackData, a2, v51, v33 | 3, NameCtrl);
          v12 = v41;
          if ( v41 >= 0 )
            goto LABEL_36;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LODWORD(v46) = v41;
            v24 = 51;
            v44 = 93;
            goto LABEL_100;
          }
        }
        else
        {
          v35 = *(_WORD *)(*((_QWORD *)v9 + 5) + 32LL);
          if ( !v35 )
          {
            v12 = -1073741772;
            goto LABEL_37;
          }
          v36 = NameCtrl;
          v37 = FltCheckAndGrowNameControl(NameCtrl, v35);
          v12 = v37;
          if ( v37 >= 0 )
          {
            RtlCopyUnicodeString(&v36->Name, (PCUNICODE_STRING)(*((_QWORD *)v9 + 5) + 32LL));
LABEL_36:
            v12 = 0;
            *a5 = 1;
            goto LABEL_37;
          }
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LODWORD(v46) = v37;
            v24 = 50;
            v44 = 71;
            goto LABEL_100;
          }
        }
        goto LABEL_37;
      }
    }
    v12 = -1073741811;
LABEL_103:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v46) = v12;
      v24 = 48;
      v44 = 31;
      goto LABEL_100;
    }
    goto LABEL_37;
  }
  if ( (unsigned __int8)a4 == 1 )
  {
    Name = BfpGeneratePostCreateName((int)v23, (int)v11, a4 & 0xFE00FF00 | 1, (int)v9, (__int64)Instance, NameCtrl);
    v12 = Name;
    if ( Name >= 0 )
      goto LABEL_36;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v46) = Name;
      v24 = 47;
      v44 = 2;
      goto LABEL_100;
    }
    goto LABEL_37;
  }
  if ( (unsigned __int8)a4 != 2 )
  {
    v12 = -1073741811;
    goto LABEL_37;
  }
  v39 = BfpGeneratePostCreateName((int)v23, (int)v11, a4 & 0xFE00FF00 | 2, (int)v9, (__int64)Instance, NameCtrl);
  v12 = v39;
  if ( v39 >= 0 )
    goto LABEL_36;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v46) = v39;
    v24 = 46;
    v44 = -16;
    goto LABEL_100;
  }
LABEL_37:
  if ( P[1] )
  {
    ExFreePoolWithTag(P[1], 0x74734642u);
    P[1] = 0;
  }
  LODWORD(P[0]) = 0;
  if ( v9 )
    FltReleaseContext(v9);
  if ( Context )
    FltReleaseContext(Context);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140012c60  mov     rax, rsp
0x140012c63  mov     [rax+8], rcx
0x140012c67  push    rbp
0x140012c68  push    rbx
0x140012c69  lea     rbp, [rax-4Fh]
0x140012c6d  sub     rsp, 0A8h
0x140012c74  mov     [rax+18h], rsi
0x140012c78  xorps   xmm0, xmm0
0x140012c7b  mov     [rax-18h], rdi
0x140012c7f  mov     rsi, r8
0x140012c82  mov     [rax-20h], r12
0x140012c86  mov     edi, r9d
0x140012c89  mov     [rax-28h], r13
0x140012c8d  mov     [rax-30h], r14
0x140012c91  mov     [rax-38h], r15
0x140012c95  mov     r15, rdx
0x140012c98  mov     rax, rcx
0x140012c9b  mov     rcx, [rdx+18h]
0x140012c9f  mov     [rbp+47h+var_50], rcx
0x140012ca3  lea     rdx, [rbp+47h+Context]; Context
0x140012ca7  xor     ecx, ecx
0x140012ca9  mov     [rbp+47h+FileNameInformation], rcx
0x140012cad  mov     r13d, ecx
0x140012cb0  mov     [rbp+47h+Context], rcx
0x140012cb4  mov     [rbp+47h+var_70], rcx
0x140012cb8  mov     [rbp+47h+var_60], rcx
0x140012cbc  mov     [rbp+47h+var_58], rcx
0x140012cc0  mov     rcx, rax; Instance
0x140012cc3  movups  xmmword ptr [rbp+47h+P], xmm0
0x140012cc7  call    cs:__imp_FltGetInstanceContext
0x140012cce  nop     dword ptr [rax+rax+00h]
0x140012cd3  mov     ebx, eax
0x140012cd5  test    eax, eax
0x140012cd7  js      loc_140013161
0x140012cdd  mov     rdx, [rbp+47h+Context]
0x140012ce1  lea     rax, [rbp+47h+var_58]
0x140012ce5  mov     [rsp+0B0h+var_88], rax
0x140012cea  lea     r9, [rbp+47h+var_70]
0x140012cee  lea     rax, [rbp+47h+var_60]
0x140012cf2  mov     r8, rsi
0x140012cf5  mov     rcx, r15
0x140012cf8  mov     [rsp+0B0h+var_90], rax
0x140012cfd  call    BfGetMappingContexts
0x140012d02  mov     ebx, eax
0x140012d04  test    eax, eax
0x140012d06  js      loc_140012E64
0x140012d0c  mov     rbx, [rbp+47h+var_70]
0x140012d10  movzx   r14d, dil
0x140012d14  test    rbx, rbx
0x140012d17  jnz     loc_140012E36
0x140012d1d  mov     rbx, [rbp+47h+var_60]
0x140012d21  test    rbx, rbx
0x140012d24  jnz     loc_14001355F
0x140012d2a  mov     rbx, [rbp+47h+var_58]
0x140012d2e  test    rbx, rbx
0x140012d31  jz      loc_140012EA3
0x140012d37  lea     rcx, [rbx+10h]; Resource
0x140012d3b  call    cs:__imp_FltAcquireResourceShared
0x140012d42  nop     dword ptr [rax+rax+00h]
0x140012d47  lea     rcx, [rbx+10h]; Resource
0x140012d4b  cmp     [rbx], rbx
0x140012d4e  jz      loc_14001358D
0x140012d54  call    cs:__imp_FltReleaseResource
0x140012d5b  nop     dword ptr [rax+rax+00h]
0x140012d60  mov     eax, [r15+50h]
0x140012d64  mov     [rbp+47h+arg_18], eax
0x140012d67  bt      eax, 16h
0x140012d6b  jb      loc_140012EA3
0x140012d71  cmp     [rbp+47h+var_50], r13
0x140012d75  jz      loc_1400133D9
0x140012d7b  mov     rcx, [rbp+47h+Instance]; Instance
0x140012d7f  lea     r8, [rbp+47h+var_70]; Context
0x140012d83  mov     rdx, r15; FileObject
0x140012d86  mov     [rbp+47h+var_70], r13
0x140012d8a  call    cs:__imp_FltGetStreamHandleContext
0x140012d91  nop     dword ptr [rax+rax+00h]
0x140012d96  lea     r12, WPP_RECORDER_INITIALIZED
0x140012d9d  mov     ebx, eax
0x140012d9f  cmp     eax, 0C0000225h
0x140012da4  jz      loc_14001318C
0x140012daa  test    eax, eax
0x140012dac  js      loc_1400131F2
0x140012db2  mov     r13, [rbp+47h+var_70]
0x140012db6  mov     eax, [r13+50h]
0x140012dba  test    al, 1
0x140012dbc  jnz     short loc_140012DD0
0x140012dbe  mov     rcx, r13; Context
0x140012dc1  call    cs:__imp_FltReleaseContext
0x140012dc8  nop     dword ptr [rax+rax+00h]
0x140012dcd  xor     r13d, r13d
0x140012dd0  xor     ecx, ecx; Context
0x140012dd2  mov     [rbp+47h+var_70], rcx
0x140012dd6  xor     ebx, ebx
0x140012dd8  test    rcx, rcx
0x140012ddb  jz      short loc_140012DE9
0x140012ddd  call    cs:__imp_FltReleaseContext
0x140012de4  nop     dword ptr [rax+rax+00h]
0x140012de9  test    ebx, ebx
0x140012deb  js      loc_1400132C7
0x140012df1  cmp     [rbp+47h+Context], 0
0x140012df6  mov     rcx, [rbp+47h+Instance]
0x140012dfa  jz      loc_1400131E6
0x140012e00  mov     rax, [rbp+47h+Context]
0x140012e04  mov     rdx, [rax]
0x140012e07  mov     [rbp+47h+var_58], rdx
0x140012e0b  test    r13, r13
0x140012e0e  jz      loc_140013195
0x140012e14  mov     rax, [r15+18h]
0x140012e18  test    rax, rax
0x140012e1b  jz      short loc_140012E2B
0x140012e1d  mov     edx, 6431h
0x140012e22  cmp     [rax], dx
0x140012e25  jz      loc_140013064
0x140012e2b  mov     r10, r15
0x140012e2e  mov     rdx, rcx
0x140012e31  jmp     loc_14001307B
0x140012e36  lea     rcx, [rbx+10h]; Resource
0x140012e3a  call    cs:__imp_FltAcquireResourceShared
0x140012e41  nop     dword ptr [rax+rax+00h]
0x140012e46  lea     rcx, [rbx+10h]; Resource
0x140012e4a  cmp     [rbx], rbx
0x140012e4d  jnz     loc_140012D54
0x140012e53  call    cs:__imp_FltReleaseResource
0x140012e5a  nop     dword ptr [rax+rax+00h]
0x140012e5f  jmp     loc_140012D1D
0x140012e64  lea     r12, WPP_RECORDER_INITIALIZED
0x140012e6b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140012e72  jz      loc_140012F58
0x140012e78  mov     [rsp+38h], eax
0x140012e7c  lea     rsi, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140012e83  mov     dword ptr [rsp+0B0h+var_80], 426h
0x140012e8b  lea     r14, WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids
0x140012e92  mov     r9d, 27h ; '''
0x140012e98  mov     r8d, 5
0x140012e9e  jmp     loc_14001345E
0x140012ea3  and     edi, 0FE00FF00h
0x140012ea9  mov     [rbp+47h+var_70], r13
0x140012ead  or      edi, r14d
0x140012eb0  test    rsi, rsi
0x140012eb3  jz      loc_140012FFA
0x140012eb9  lea     r8, [rbp+47h+var_70]; FileNameInformation
0x140012ebd  mov     edx, edi; NameOptions
0x140012ebf  mov     rcx, rsi; CallbackData
0x140012ec2  call    cs:__imp_FltGetFileNameInformation
0x140012ec9  nop     dword ptr [rax+rax+00h]
0x140012ece  lea     rsi, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140012ed5  mov     ebx, eax
0x140012ed7  lea     r14, WPP_c7f51acdbd3738713a5b9ea834ad885a_Traceguids
0x140012ede  lea     r12, WPP_RECORDER_INITIALIZED
0x140012ee5  test    eax, eax
0x140012ee7  js      loc_14001301E
0x140012eed  mov     rcx, [rbp+47h+var_70]
0x140012ef1  movzx   edx, word ptr [rcx+8]; NewSize
0x140012ef5  test    dx, dx
0x140012ef8  jz      loc_14001322C
0x140012efe  mov     rdi, [rbp+47h+NameCtrl]
0x140012f02  mov     rcx, rdi; NameCtrl
0x140012f05  call    cs:__imp_FltCheckAndGrowNameControl
0x140012f0c  nop     dword ptr [rax+rax+00h]
0x140012f11  mov     ebx, eax
0x140012f13  test    eax, eax
0x140012f15  js      loc_140013208
0x140012f1b  mov     rdx, [rbp+47h+var_70]
0x140012f1f  mov     rcx, rdi; DestinationString
0x140012f22  add     rdx, 8; SourceString
0x140012f26  call    cs:__imp_RtlCopyUnicodeString
0x140012f2d  nop     dword ptr [rax+rax+00h]
0x140012f32  mov     rcx, [rbp+47h+var_70]; FileNameInformation
0x140012f36  test    rcx, rcx
0x140012f39  jz      short loc_140012F47
0x140012f3b  call    cs:__imp_FltReleaseFileNameInformation
0x140012f42  nop     dword ptr [rax+rax+00h]
0x140012f47  test    ebx, ebx
0x140012f49  js      loc_1400132A3
0x140012f4f  mov     rax, [rbp+47h+arg_20]
0x140012f53  xor     ebx, ebx
0x140012f55  mov     byte ptr [rax], 1
0x140012f58  mov     rcx, [rbp+47h+P+8]; P
0x140012f5c  mov     r15, [rsp+0B0h+var_30]
0x140012f64  mov     r14, [rsp+0B0h+var_28]
0x140012f6c  mov     r12, [rsp+0B0h+var_18]
0x140012f74  mov     rdi, [rsp+0A0h]
0x140012f7c  mov     rsi, [rsp+0B0h+arg_10]
0x140012f84  test    rcx, rcx
0x140012f87  jz      short loc_140012FA2
0x140012f89  mov     edx, 74734642h; Tag
0x140012f8e  call    cs:__imp_ExFreePoolWithTag
0x140012f95  nop     dword ptr [rax+rax+00h]
0x140012f9a  mov     [rbp+47h+P+8], 0
0x140012fa2  xor     eax, eax
0x140012fa4  mov     dword ptr [rbp+47h+P], eax
0x140012fa7  test    r13, r13
0x140012faa  jz      short loc_140012FBB
0x140012fac  mov     rcx, r13; Context
0x140012faf  call    cs:__imp_FltReleaseContext
0x140012fb6  nop     dword ptr [rax+rax+00h]
0x140012fbb  mov     rcx, [rbp+47h+Context]; Context
0x140012fbf  mov     r13, [rsp+0B0h+var_20]
0x140012fc7  test    rcx, rcx
0x140012fca  jz      short loc_140012FD8
0x140012fcc  call    cs:__imp_FltReleaseContext
0x140012fd3  nop     dword ptr [rax+rax+00h]
0x140012fd8  mov     rcx, [rbp+47h+FileNameInformation]; FileNameInformation
0x140012fdc  test    rcx, rcx
0x140012fdf  jz      short loc_140012FED
0x140012fe1  call    cs:__imp_FltReleaseFileNameInformation
0x140012fe8  nop     dword ptr [rax+rax+00h]
0x140012fed  mov     eax, ebx
0x140012fef  add     rsp, 0A8h
0x140012ff6  pop     rbx
0x140012ff7  pop     rbp
0x140012ff8  retn
0x140012ffa  mov     rdx, [rbp+47h+Instance]; Instance
0x140012ffe  lea     r9, [rbp+47h+var_70]; FileNameInformation
0x140013002  mov     r8d, edi; NameOptions
0x140013005  mov     rcx, r15; FileObject
0x140013008  call    cs:__imp_FltGetFileNameInformationUnsafe
0x14001300f  nop     dword ptr [rax+rax+00h]
0x140013014  jmp     loc_140012ECE
0x140013019  mov     ebx, 0C000000Dh
0x14001301e  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140013025  jz      loc_140012F32
0x14001302b  mov     [rsp+38h], ebx
0x14001302f  mov     r9d, 24h ; '$'
0x140013035  mov     dword ptr [rsp+0B0h+var_80], 3B3h
0x14001303d  mov     rcx, cs:WPP_GLOBAL_Control
0x140013044  mov     r8d, 9
0x14001304a  mov     [rsp+0B0h+var_88], rsi
0x14001304f  mov     dl, 2
0x140013051  mov     [rsp+0B0h+var_90], r14
0x140013056  mov     rcx, [rcx+40h]
0x14001305a  call    WPP_RECORDER_SF_sDd
0x14001305f  jmp     loc_140012F32
0x140013064  test    byte ptr [r13+50h], 1
0x140013069  jz      loc_140012E2B
0x14001306f  mov     rax, [r15+20h]
0x140013073  mov     r10, [rax+8]
0x140013077  mov     rdx, [rax+10h]; int
0x14001307b  cmp     r14d, 3
0x14001307f  jnz     loc_14001323C
0x140013085  mov     [rbp+47h+FileNameInformation], 0
0x14001308d  test    r10, r10
0x140013090  jz      loc_1400134C6
0x140013096  and     edi, 0FE00FF00h
0x14001309c  lea     r9, [rbp+47h+FileNameInformation]; FileNameInformation
0x1400130a0  mov     r8d, edi
0x1400130a3  mov     rcx, r10; FileObject
0x1400130a6  or      r8d, 1; NameOptions
0x1400130aa  call    cs:__imp_FltGetFileNameInformationUnsafe
0x1400130b1  nop     dword ptr [rax+rax+00h]
0x1400130b6  mov     ebx, eax
0x1400130b8  test    eax, eax
0x1400130ba  js      loc_1400134CB
0x1400130c0  mov     rcx, [rbp+47h+FileNameInformation]
0x1400130c4  cmp     word ptr [rcx+8], 0
0x1400130c9  jz      loc_1400134EF
0x1400130cf  mov     rcx, [rbp+47h+FileNameInformation]
0x1400130d3  lea     r8, [rbp+47h+P]
0x1400130d7  xor     edx, edx
0x1400130d9  call    BfFormatPathFromFileNameInfo
0x1400130de  mov     ebx, eax
0x1400130e0  test    eax, eax
0x1400130e2  js      loc_1400132EB
0x1400130e8  mov     r8d, [rbp+47h+arg_18]
0x1400130ec  lea     rcx, [rbp+47h+P]; String1
0x1400130f0  mov     rdx, [r13+30h]
0x1400130f4  shr     r8d, 11h
0x1400130f8  add     rdx, 28h ; '('; String2
0x1400130fc  not     r8b
0x1400130ff  and     r8b, 1; CaseInSensitive
0x140013103  call    cs:__imp_RtlCompareUnicodeString
0x14001310a  nop     dword ptr [rax+rax+00h]
0x14001310f  test    eax, eax
0x140013111  jnz     loc_140013390
0x140013117  mov     rax, [r13+28h]
0x14001311b  movzx   edx, word ptr [rax+20h]; NewSize
0x14001311f  test    dx, dx
0x140013122  jz      loc_14001330F
0x140013128  mov     rdi, [rbp+47h+NameCtrl]
0x14001312c  mov     rcx, rdi; NameCtrl
0x14001312f  call    cs:__imp_FltCheckAndGrowNameControl
0x140013136  nop     dword ptr [rax+rax+00h]
0x14001313b  mov     ebx, eax
0x14001313d  test    eax, eax
0x14001313f  js      loc_140013319
0x140013145  mov     rdx, [r13+28h]
0x140013149  mov     rcx, rdi; DestinationString
0x14001314c  add     rdx, 20h ; ' '; SourceString
0x140013150  call    cs:__imp_RtlCopyUnicodeString
0x140013157  nop     dword ptr [rax+rax+00h]
0x14001315c  jmp     loc_140012F4F
0x140013161  lea     r12, WPP_RECORDER_INITIALIZED
0x140013168  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001316f  jz      loc_140012F58
0x140013175  mov     [rsp+38h], eax
0x140013179  mov     r9d, 26h ; '&'
0x14001317f  mov     dword ptr [rsp+0B0h+var_80], 41Eh
0x140013187  jmp     loc_14001344A
0x14001318c  mov     r13, [rbp+47h+var_70]
0x140013190  jmp     loc_140012DD0
  ... truncated ...
```
