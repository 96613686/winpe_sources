# PrjfSetDeleteDisposition

- ea: `0x14003d620`
- end: `0x14003dd81`
- name: `PrjfSetDeleteDisposition`
- size: `1889`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, __int64, __int64)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, reparse_path`

## callers

- `0x140022320`
- `0x14002f5f0`
- `0x140035238`

## callees

- `0x140002f3c`
- `0x140006660`
- `0x1400066a4`
- `0x1400080e4`
- `0x14000d008`
- `0x14000d128`
- `0x14000d754`
- `0x14000dab0`
- `0x140021550`
- `0x1400377c4`
- `0x14003d620`
- `0x140043b24`
- `0x140043d88`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x14003d924`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14003d924`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14003dc20`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14003dc20`
- `ntoskrnl!KeClearEvent` at `0x14003d800`
- `ntoskrnl!KeClearEvent` at `0x14003d800`
- `ntoskrnl!KeSetEvent` at `0x14003dc07`
- `ntoskrnl!KeSetEvent` at `0x14003dc07`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003d915`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003d915`
- `FLTMGR!FltSetInformationFile` at `0x14003d837`
- `FLTMGR!FltSetInformationFile` at `0x14003d8d7`
- `FLTMGR!FltSetInformationFile` at `0x14003d837`
- `FLTMGR!FltSetInformationFile` at `0x14003d8d7`
- `FLTMGR!FltReleaseContext` at `0x14003dc35`
- `FLTMGR!FltReleaseContext` at `0x14003dc49`
- `FLTMGR!FltReleaseContext` at `0x14003dc35`
- `FLTMGR!FltReleaseContext` at `0x14003dc49`

## pseudocode

```c
__int64 __fastcall PrjfSetDeleteDisposition(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        char a3,
        char a4,
        __int64 a5,
        _DWORD *a6)
{
  char v6; // r12
  struct _FLT_INSTANCE *v8; // rdi
  __int64 v9; // rdx
  PFLT_CONTEXT v10; // rcx
  int SetFileContext; // ebx
  __int64 v12; // r8
  __int64 v13; // r9
  char *v14; // rsi
  char v15; // r13
  int v16; // edx
  int v17; // r8d
  NTSTATUS v18; // eax
  NTSTATUS v19; // ebx
  int v20; // edi
  int Attributes; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // edx
  int v26; // r8d
  int v27; // eax
  int v28; // edx
  int v29; // r8d
  unsigned int v30; // edi
  char v32; // [rsp+60h] [rbp-20h]
  char v33; // [rsp+61h] [rbp-1Fh]
  char v34[2]; // [rsp+62h] [rbp-1Eh] BYREF
  int FileInformation; // [rsp+64h] [rbp-1Ch] BYREF
  PFLT_CONTEXT v36; // [rsp+68h] [rbp-18h] BYREF
  PFLT_CONTEXT Context[2]; // [rsp+70h] [rbp-10h] BYREF
  int v40; // [rsp+D8h] [rbp+58h] BYREF

  LOBYTE(v40) = a4;
  v6 = 0;
  FileInformation = 0;
  v34[0] = 0;
  v36 = 0;
  v8 = Instance;
  Context[0] = 0;
  v32 = 0;
  if ( a4 )
  {
    SetFileContext = PrjfGetSetFileContext(Instance, FileObject, 1, 0, 0, 0, 0, &v36);
    if ( SetFileContext < 0 )
    {
      LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v9) = BYTE1(xmmword_14001A3D0) & 0x40;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          526,
          v9,
          v12,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          14,
          192,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          103,
          SetFileContext,
          (__int64)&FileObject->FileName);
      v14 = (char *)v36;
      goto LABEL_66;
    }
  }
  else
  {
    SetFileContext = PrjfGetSetContextFileObject(Instance, FileObject, 0x80000000, 0, 0, 0, 0, &v36, Context);
    if ( SetFileContext < 0 )
    {
      LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v9) = BYTE1(xmmword_14001A3D0) & 0x40;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          526,
          v9,
          v12,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          14,
          191,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          77,
          SetFileContext,
          (__int64)&FileObject->FileName);
      v14 = (char *)v36;
      goto LABEL_64;
    }
  }
  v15 = 1;
  v33 = 0;
  if ( a5 )
    tlgDefineProvider_annotation__TlgProjfsTelemetryProviderProv(v10, v9, v12, v13);
  v14 = (char *)v36;
  KeClearEvent((PRKEVENT)v36 + 12);
  while ( 1 )
  {
    while ( 1 )
    {
      if ( !v15
        || (FileInformation = 3,
            v18 = FltSetInformationFile(v8, FileObject, &FileInformation, 4u, (FILE_INFORMATION_CLASS)64),
            v19 = v18,
            v18 == -1073741156)
        || v18 == -1073741811 )
      {
        if ( (BYTE9(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v16) = BYTE9(xmmword_14001A3D0) & 0x40;
          LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sD(
            782,
            v16,
            v17,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            3,
            14,
            193,
            (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
            162);
        }
        v34[0] = 1;
        v15 = 0;
        v19 = FltSetInformationFile(v8, FileObject, v34, 1u, FileDispositionInformation);
        if ( !(_BYTE)v40 && !v33 )
        {
          while ( !ExAcquireRundownProtection((PEX_RUNDOWN_REF)v14 + 42) )
            KeWaitForSingleObject(v14 + 312, Executive, 0, 0, 0);
          v33 = 1;
        }
      }
      v20 = 0;
      if ( v19 != -1073741533 )
        v20 = v19;
      if ( v20 != -1073741535 )
        break;
      if ( v6 )
        goto LABEL_78;
      LODWORD(v36) = 0;
      Attributes = PrjfQueryAttributes(FileObject, Instance);
      SetFileContext = Attributes;
      if ( Attributes < 0 )
      {
        if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v16) = BYTE1(xmmword_14001A3D0) & 0x40;
          LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDqd(
            526,
            v16,
            v17,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            14,
            194,
            (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
            225,
            (char)FileObject,
            Attributes);
LABEL_48:
          v8 = Instance;
          goto LABEL_62;
        }
        goto LABEL_61;
      }
      if ( ((unsigned __int8)v36 & 1) == 0 )
        goto LABEL_78;
      v8 = Instance;
      if ( (a3 & 0x20) == 0 )
      {
        SetFileContext = -1073741535;
        *a6 = 8;
        goto LABEL_62;
      }
      v22 = PrjfClearAttributes(FileObject, Instance);
      SetFileContext = v22;
      if ( v22 < 0 )
      {
        if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v16) = BYTE1(xmmword_14001A3D0) & 0x40;
          LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDqd(
            526,
            v16,
            v17,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            14,
            195,
            (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
            239,
            (char)FileObject,
            v22);
        }
        goto LABEL_62;
      }
      v6 = 1;
    }
    if ( v20 != -1073741567 )
    {
      if ( v20 < 0 )
      {
LABEL_78:
        if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v16) = BYTE1(xmmword_14001A3D0) & 0x40;
          LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDqd(
            526,
            v16,
            v17,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            14,
            198,
            (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
            66,
            (char)FileObject,
            v20);
        }
        SetFileContext = v20;
        goto LABEL_48;
      }
      v14[282] = 1;
      SetFileContext = v20;
LABEL_61:
      v8 = Instance;
      goto LABEL_62;
    }
    if ( v32 )
      goto LABEL_78;
    v8 = Instance;
    if ( (a3 & 4) == 0 )
      break;
    v23 = PrjfRemoveTombstonesFromDirectory(Instance, FileObject);
    SetFileContext = v23;
    if ( v23 < 0 )
    {
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v16) = BYTE1(xmmword_14001A3D0) & 0x40;
        LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          526,
          v16,
          v17,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          14,
          196,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          21,
          v23);
      }
      goto LABEL_62;
    }
    v32 = 1;
  }
  v40 = 0;
  v24 = PrjfCheckDirectoryContentReparseTags(Instance, FileObject, &v40);
  SetFileContext = v24;
  if ( v24 >= 0 )
  {
    if ( v40 == 4 )
      *a6 = 4;
    SetFileContext = -1073741567;
  }
  else if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v25) = BYTE1(xmmword_14001A3D0) & 0x40;
    LOBYTE(v26) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      526,
      v25,
      v26,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      14,
      197,
      (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
      44,
      v24);
  }
LABEL_62:
  v6 = v32;
  KeSetEvent((PRKEVENT)v14 + 12, 0, 0);
  if ( v33 )
    ExReleaseRundownProtection((PEX_RUNDOWN_REF)v14 + 42);
LABEL_64:
  v10 = Context[0];
  if ( Context[0] )
    FltReleaseContext(Context[0]);
LABEL_66:
  if ( v14 )
    FltReleaseContext(v14);
  if ( SetFileContext < 0 && v6 )
  {
    if ( a5 )
      tlgDefineProvider_annotation__TlgProjfsTelemetryProviderProv(v10, v9, v12, v13);
    v27 = PrjfRevertInMemoryTombstonesForDirectory(v8, FileObject);
    v30 = v27;
    if ( v27 < 0 )
    {
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v28) = BYTE1(xmmword_14001A3D0) & 0x40;
        LOBYTE(v29) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          526,
          v28,
          v29,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          14,
          199,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          133,
          v27);
      }
      return v30;
    }
  }
  return (unsigned int)SetFileContext;
}

```

## disassembly

```asm
0x14003d620  mov     r11, rsp
0x14003d623  mov     [r11+10h], rbx
0x14003d627  mov     [r11+20h], r9b
0x14003d62b  mov     [r11+18h], r8d
0x14003d62f  mov     [r11+8], rcx
0x14003d633  push    rbp
0x14003d634  push    rsi
0x14003d635  push    rdi
0x14003d636  push    r12
0x14003d638  push    r13
0x14003d63a  push    r14
0x14003d63c  push    r15
0x14003d63e  mov     rbp, rsp
0x14003d641  sub     rsp, 80h
0x14003d648  xor     r12b, r12b
0x14003d64b  mov     [rbp+FileInformation], 0
0x14003d652  mov     [rbp+var_1E], 0
0x14003d656  mov     r15, rdx
0x14003d659  mov     [rbp+var_18], 0
0x14003d661  mov     rdi, rcx
0x14003d664  mov     [rbp+Context], 0
0x14003d66c  lea     r13, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003d673  mov     [rbp+var_20], r12b
0x14003d677  lea     rsi, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003d67e  test    r9b, r9b
0x14003d681  jnz     loc_14003D739
0x14003d687  lea     rax, [rbp+Context]
0x14003d68b  xor     r9d, r9d
0x14003d68e  mov     [r11-78h], rax
0x14003d692  mov     r8d, 80000000h
0x14003d698  lea     rax, [rbp+var_18]
0x14003d69c  mov     [r11-80h], rax
0x14003d6a0  mov     [rsp+80h+var_50], 0; __int64
0x14003d6a9  mov     [rsp+80h+var_58], 0; __int64
0x14003d6b2  mov     byte ptr [rsp+80h+FileInformationClass], r12b; char
0x14003d6b7  call    PrjfGetSetContextFileObject
0x14003d6bc  mov     ebx, eax
0x14003d6be  test    eax, eax
0x14003d6c0  jns     loc_14003D7E1
0x14003d6c6  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003d6cc  lea     r14, WPP_RECORDER_INITIALIZED
0x14003d6d3  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14003d6da  setnz   r8b
0x14003d6de  and     dl, 40h
0x14003d6e1  jnz     short loc_14003D6E8
0x14003d6e3  test    r8b, r8b
0x14003d6e6  jz      short loc_14003D730
0x14003d6e8  mov     r9, cs:WPP_GLOBAL_Control
0x14003d6ef  lea     rax, [r15+58h]
0x14003d6f3  mov     [rsp+80h+var_28], rax
0x14003d6f8  mov     ecx, 20Eh
0x14003d6fd  mov     dword ptr [rsp+80h+var_30], ebx
0x14003d701  mov     [rsp+80h+var_38], 204Dh
0x14003d709  mov     r9, [r9+40h]
0x14003d70d  mov     [rsp+80h+var_40], r13
0x14003d712  mov     [rsp+80h+var_48], rsi
0x14003d717  mov     word ptr [rsp+80h+var_50], 0BFh
0x14003d71e  mov     dword ptr [rsp+80h+var_58], 0Eh
0x14003d726  mov     byte ptr [rsp+80h+FileInformationClass], 2
0x14003d72b  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x14003d730  mov     rsi, [rbp+var_18]
0x14003d734  jmp     loc_14003DC2C
0x14003d739  lea     rax, [rbp+var_18]
0x14003d73d  xor     r9d, r9d
0x14003d740  mov     [rsp+80h+var_48], rax; __int64
0x14003d745  mov     r8b, 1
0x14003d748  mov     [rsp+80h+var_50], 0; __int64
0x14003d751  mov     [rsp+80h+var_58], 0; __int64
0x14003d75a  mov     qword ptr [rsp+80h+FileInformationClass], 0; __int64
0x14003d763  call    PrjfGetSetFileContext
0x14003d768  mov     ebx, eax
0x14003d76a  test    eax, eax
0x14003d76c  jns     short loc_14003D7E1
0x14003d76e  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003d774  lea     r14, WPP_RECORDER_INITIALIZED
0x14003d77b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14003d782  setnz   r8b
0x14003d786  and     dl, 40h
0x14003d789  jnz     short loc_14003D790
0x14003d78b  test    r8b, r8b
0x14003d78e  jz      short loc_14003D7D8
0x14003d790  mov     r9, cs:WPP_GLOBAL_Control
0x14003d797  lea     rax, [r15+58h]
0x14003d79b  mov     [rsp+80h+var_28], rax
0x14003d7a0  mov     ecx, 20Eh
0x14003d7a5  mov     dword ptr [rsp+80h+var_30], ebx
0x14003d7a9  mov     [rsp+80h+var_38], 2067h
0x14003d7b1  mov     r9, [r9+40h]
0x14003d7b5  mov     [rsp+80h+var_40], r13
0x14003d7ba  mov     [rsp+80h+var_48], rsi
0x14003d7bf  mov     word ptr [rsp+80h+var_50], 0C0h
0x14003d7c6  mov     dword ptr [rsp+80h+var_58], 0Eh
0x14003d7ce  mov     byte ptr [rsp+80h+FileInformationClass], 2
0x14003d7d3  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x14003d7d8  mov     rsi, [rbp+var_18]
0x14003d7dc  jmp     loc_14003DC41
0x14003d7e1  xor     al, al
0x14003d7e3  mov     r13b, 1
0x14003d7e6  cmp     [rbp+arg_20], 0
0x14003d7eb  mov     [rbp+var_1F], al
0x14003d7ee  jz      short loc_14003D7F5
0x14003d7f0  call    _tlgDefineProvider_annotation__TlgProjfsTelemetryProviderProv
0x14003d7f5  mov     rsi, [rbp+var_18]
0x14003d7f9  lea     rcx, [rsi+120h]; Event
0x14003d800  call    cs:__imp_KeClearEvent
0x14003d807  nop     dword ptr [rax+rax+00h]
0x14003d80c  lea     r14, WPP_RECORDER_INITIALIZED
0x14003d813  test    r13b, r13b
0x14003d816  jz      short loc_14003D857
0x14003d818  mov     r9d, 4; Length
0x14003d81e  mov     [rbp+FileInformation], 3
0x14003d825  lea     r8, [rbp+FileInformation]; FileInformation
0x14003d829  mov     [rsp+80h+FileInformationClass], 40h ; '@'; FileInformationClass
0x14003d831  mov     rdx, r15; FileObject
0x14003d834  mov     rcx, rdi; Instance
0x14003d837  call    cs:__imp_FltSetInformationFile
0x14003d83e  nop     dword ptr [rax+rax+00h]
0x14003d843  mov     ebx, eax
0x14003d845  cmp     eax, 0C000029Ch
0x14003d84a  jz      short loc_14003D857
0x14003d84c  cmp     eax, 0C000000Dh
0x14003d851  jnz     loc_14003D938
0x14003d857  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14003d85e  mov     dl, byte ptr cs:xmmword_14001A3D0+9
0x14003d864  setnz   r8b
0x14003d868  and     dl, 40h
0x14003d86b  jnz     short loc_14003D872
0x14003d86d  test    r8b, r8b
0x14003d870  jz      short loc_14003D8BB
0x14003d872  mov     [rsp+80h+var_38], 20A2h
0x14003d87a  lea     r9, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003d881  mov     [rsp+80h+var_40], r9
0x14003d886  mov     ecx, 30Eh
0x14003d88b  lea     r9, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003d892  mov     [rsp+80h+var_48], r9
0x14003d897  mov     r9, cs:WPP_GLOBAL_Control
0x14003d89e  mov     word ptr [rsp+80h+var_50], 0C1h
0x14003d8a5  mov     dword ptr [rsp+80h+var_58], 0Eh
0x14003d8ad  mov     byte ptr [rsp+80h+FileInformationClass], 3
0x14003d8b2  mov     r9, [r9+40h]
0x14003d8b6  call    WPP_RECORDER_AND_TRACE_SF_sD
0x14003d8bb  mov     r9d, 1; Length
0x14003d8c1  mov     [rbp+var_1E], 1
0x14003d8c5  lea     r8, [rbp+var_1E]; FileInformation
0x14003d8c9  mov     [rsp+80h+FileInformationClass], 0Dh; FileInformationClass
0x14003d8d1  mov     rdx, r15; FileObject
0x14003d8d4  mov     rcx, rdi; Instance
0x14003d8d7  call    cs:__imp_FltSetInformationFile
0x14003d8de  nop     dword ptr [rax+rax+00h]
0x14003d8e3  xor     r13b, r13b
0x14003d8e6  mov     ebx, eax
0x14003d8e8  cmp     byte ptr [rbp+arg_18], r13b
0x14003d8ec  jnz     short loc_14003D938
0x14003d8ee  cmp     [rbp+var_1F], r13b
0x14003d8f2  jnz     short loc_14003D938
0x14003d8f4  lea     rdi, [rsi+150h]
0x14003d8fb  jmp     short loc_14003D921
0x14003d8fd  lea     rcx, [rsi+138h]; Object
0x14003d904  mov     qword ptr [rsp+80h+FileInformationClass], 0; Timeout
0x14003d90d  xor     r9d, r9d; Alertable
0x14003d910  xor     r8d, r8d; WaitMode
0x14003d913  xor     edx, edx; WaitReason
0x14003d915  call    cs:__imp_KeWaitForSingleObject
0x14003d91c  nop     dword ptr [rax+rax+00h]
0x14003d921  mov     rcx, rdi; RunRef
0x14003d924  call    cs:__imp_ExAcquireRundownProtection
0x14003d92b  nop     dword ptr [rax+rax+00h]
0x14003d930  test    al, al
0x14003d932  jz      short loc_14003D8FD
0x14003d934  mov     [rbp+var_1F], 1
0x14003d938  xor     edi, edi
0x14003d93a  cmp     ebx, 0C0000123h
0x14003d940  cmovnz  edi, ebx
0x14003d943  cmp     edi, 0C0000121h
0x14003d949  jnz     short loc_14003D9AC
0x14003d94b  test    r12b, r12b
0x14003d94e  jnz     loc_14003DD04
0x14003d954  mov     rdx, [rbp+Instance]; Instance
0x14003d958  lea     r8, [rbp+var_18]
0x14003d95c  mov     rcx, r15; FileObject
0x14003d95f  mov     dword ptr [rbp+var_18], 0
0x14003d966  call    PrjfQueryAttributes
0x14003d96b  mov     ebx, eax
0x14003d96d  test    eax, eax
0x14003d96f  js      loc_14003DA78
0x14003d975  test    byte ptr [rbp+var_18], 1
0x14003d979  jz      loc_14003DD04
0x14003d97f  test    [rbp+arg_10], 20h
0x14003d983  mov     rdi, [rbp+Instance]
0x14003d987  jz      loc_14003DA64
0x14003d98d  mov     r8d, 1
0x14003d993  mov     rdx, rdi; Instance
0x14003d996  mov     rcx, r15; FileObject
0x14003d999  call    PrjfClearAttributes
0x14003d99e  mov     ebx, eax
0x14003d9a0  test    eax, eax
0x14003d9a2  js      short loc_14003D9EE
0x14003d9a4  mov     r12b, 1
0x14003d9a7  jmp     loc_14003D813
0x14003d9ac  cmp     edi, 0C0000101h
0x14003d9b2  jnz     loc_14003DBDB
0x14003d9b8  cmp     [rbp+var_20], 0
0x14003d9bc  jnz     loc_14003DD04
0x14003d9c2  test    [rbp+arg_10], 4
0x14003d9c6  mov     rdx, r15; FileObject
0x14003d9c9  mov     rdi, [rbp+Instance]
0x14003d9cd  mov     rcx, rdi; Instance
0x14003d9d0  jz      loc_14003DB63
0x14003d9d6  call    PrjfRemoveTombstonesFromDirectory
0x14003d9db  mov     ebx, eax
0x14003d9dd  test    eax, eax
0x14003d9df  js      loc_14003DAF2
0x14003d9e5  mov     [rbp+var_20], 1
0x14003d9e9  jmp     loc_14003D813
0x14003d9ee  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14003d9f5  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003d9fb  setnz   r8b
0x14003d9ff  and     dl, 40h
0x14003da02  jnz     short loc_14003DA0D
0x14003da04  test    r8b, r8b
0x14003da07  jz      loc_14003DBF0
0x14003da0d  mov     dword ptr [rsp+80h+var_28], eax
0x14003da11  lea     r9, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003da18  mov     [rsp+80h+var_30], r15
0x14003da1d  lea     r13, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003da24  mov     [rsp+80h+var_38], 20EFh
0x14003da2c  mov     ecx, 20Eh
0x14003da31  mov     [rsp+80h+var_40], r13
0x14003da36  mov     [rsp+80h+var_48], r9
0x14003da3b  mov     r9, cs:WPP_GLOBAL_Control
0x14003da42  mov     word ptr [rsp+80h+var_50], 0C3h
0x14003da49  mov     dword ptr [rsp+80h+var_58], 0Eh
0x14003da51  mov     byte ptr [rsp+80h+FileInformationClass], 2
0x14003da56  mov     r9, [r9+40h]
0x14003da5a  call    WPP_RECORDER_AND_TRACE_SF_sDqd
0x14003da5f  jmp     loc_14003DBF7
0x14003da64  mov     rax, [rbp+arg_28]
0x14003da68  mov     ebx, 0C0000121h
0x14003da6d  mov     dword ptr [rax], 8
0x14003da73  jmp     loc_14003DBF0
0x14003da78  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14003da7f  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003da85  setnz   r8b
0x14003da89  and     dl, 40h
0x14003da8c  jnz     short loc_14003DA97
0x14003da8e  test    r8b, r8b
0x14003da91  jz      loc_14003DBEC
0x14003da97  mov     dword ptr [rsp+80h+var_28], eax
0x14003da9b  lea     r9, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003daa2  mov     [rsp+80h+var_30], r15
0x14003daa7  lea     r13, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003daae  mov     [rsp+80h+var_38], 20E1h
0x14003dab6  mov     ecx, 20Eh
0x14003dabb  mov     [rsp+80h+var_40], r13
0x14003dac0  mov     [rsp+80h+var_48], r9
0x14003dac5  mov     r9, cs:WPP_GLOBAL_Control
0x14003dacc  mov     word ptr [rsp+80h+var_50], 0C2h
0x14003dad3  mov     dword ptr [rsp+80h+var_58], 0Eh
0x14003dadb  mov     byte ptr [rsp+80h+FileInformationClass], 2
0x14003dae0  mov     r9, [r9+40h]
0x14003dae4  call    WPP_RECORDER_AND_TRACE_SF_sDqd
0x14003dae9  mov     rdi, [rbp+Instance]
0x14003daed  jmp     loc_14003DBF7
0x14003daf2  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14003daf9  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003daff  setnz   r8b
0x14003db03  and     dl, 40h
0x14003db06  jnz     short loc_14003DB11
0x14003db08  test    r8b, r8b
0x14003db0b  jz      loc_14003DBF0
0x14003db11  mov     dword ptr [rsp+80h+var_30], eax
0x14003db15  lea     r13, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003db1c  mov     [rsp+80h+var_38], 2115h
0x14003db24  lea     r9, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003db2b  mov     [rsp+80h+var_40], r13
0x14003db30  mov     [rsp+80h+var_48], r9
0x14003db35  mov     word ptr [rsp+80h+var_50], 0C4h
0x14003db3c  mov     r9, cs:WPP_GLOBAL_Control
0x14003db43  mov     ecx, 20Eh
0x14003db48  mov     dword ptr [rsp+80h+var_58], 0Eh
0x14003db50  mov     byte ptr [rsp+80h+FileInformationClass], 2
0x14003db55  mov     r9, [r9+40h]
0x14003db59  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14003db5e  jmp     loc_14003DBF7
0x14003db63  lea     r8, [rbp+arg_18]
0x14003db67  mov     [rbp+arg_18], 0
0x14003db6e  call    PrjfCheckDirectoryContentReparseTags
0x14003db73  mov     ebx, eax
0x14003db75  test    eax, eax
0x14003db77  jns     short loc_14003DBC4
0x14003db79  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14003db80  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003db86  setnz   r8b
0x14003db8a  and     dl, 40h
0x14003db8d  jnz     short loc_14003DB94
0x14003db8f  test    r8b, r8b
0x14003db92  jz      short loc_14003DBF0
0x14003db94  mov     dword ptr [rsp+80h+var_30], eax
0x14003db98  lea     r13, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003db9f  mov     [rsp+80h+var_38], 212Ch
  ... truncated ...
```
