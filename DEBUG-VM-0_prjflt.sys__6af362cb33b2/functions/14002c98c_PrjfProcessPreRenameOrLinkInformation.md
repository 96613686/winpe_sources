# PrjfProcessPreRenameOrLinkInformation

- ea: `0x14002c98c`
- end: `0x14002d03f`
- name: `PrjfProcessPreRenameOrLinkInformation`
- size: `1715`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x14002c090`
- `0x14002c1f4`

## callees

- `0x140001b3c`
- `0x140003d9c`
- `0x140006570`
- `0x140007694`
- `0x140007cec`
- `0x1400081f0`
- `0x14000b1d0`
- `0x14000d128`
- `0x14000d5e8`
- `0x14002c98c`
- `0x14003005c`
- `0x14003df88`
- `0x140041e28`
- `0x140043844`

## import_xrefs

- `FLTMGR!FltGetRequestorProcess` at `0x14002cb3e`
- `FLTMGR!FltGetRequestorProcess` at `0x14002cb3e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002d012`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002d012`
- `FLTMGR!FltGetFileNameInformation` at `0x14002c9c1`
- `FLTMGR!FltGetFileNameInformation` at `0x14002c9c1`

## pseudocode

```c
__int64 __fastcall PrjfProcessPreRenameOrLinkInformation(
        PFLT_CALLBACK_DATA CallbackData,
        __int64 a2,
        struct _FLT_FILE_NAME_INFORMATION *a3,
        int a4,
        _QWORD *a5)
{
  PVOID v7; // rbx
  NTSTATUS v10; // eax
  int v11; // edx
  int v12; // r8d
  unsigned int v13; // edi
  int RenameOrLinkCompletionContext; // eax
  int v15; // edx
  __int64 v16; // rcx
  int v17; // r8d
  PEPROCESS RequestorProcess; // rax
  int v19; // edx
  int v20; // r8d
  __int64 v21; // rcx
  int v22; // eax
  int v23; // edx
  int v24; // r8d
  int v25; // eax
  int v26; // edx
  int v27; // r8d
  int v28; // eax
  int v29; // edx
  int v30; // r8d
  int v31; // eax
  int v32; // edx
  int v33; // r8d
  int v34; // eax
  int v35; // edx
  int v36; // r8d
  int v37; // eax
  int v38; // edx
  int v39; // r8d
  int v40; // edx
  int v41; // r8d
  __int64 v42; // rdx
  struct _FILE_OBJECT *v43; // r8
  int v44; // edx
  int v45; // r8d
  PVOID Entry; // [rsp+60h] [rbp-58h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+68h] [rbp-50h] BYREF

  FileNameInformation = 0;
  v7 = 0;
  Entry = 0;
  v10 = FltGetFileNameInformation(CallbackData, 0x101u, &FileNameInformation);
  v13 = v10;
  if ( v10 < 0 )
  {
    if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = BYTE1(xmmword_14001A3D0) & 2;
      LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        521,
        v11,
        v12,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        9,
        12,
        (__int64)WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fileinfo.c",
        198,
        v10);
    }
    goto LABEL_49;
  }
  RenameOrLinkCompletionContext = PrjfCreateRenameOrLinkCompletionContext(
                                    (__int64)CallbackData,
                                    *(struct _FLT_INSTANCE **)(a2 + 24),
                                    (__int64)FileNameInformation,
                                    (__int64)a3,
                                    (PFILE_OBJECT **)&Entry);
  v13 = RenameOrLinkCompletionContext;
  if ( RenameOrLinkCompletionContext < 0 )
  {
    if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v15) = BYTE1(xmmword_14001A3D0) & 0x20;
      LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        525,
        v15,
        v17,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        13,
        13,
        (__int64)WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fileinfo.c",
        212,
        RenameOrLinkCompletionContext);
      v7 = Entry;
    }
    else
    {
      v7 = Entry;
    }
    goto LABEL_49;
  }
  v7 = Entry;
  if ( !Entry )
    goto LABEL_64;
  if ( !*((_QWORD *)Entry + 7) && !*(_QWORD *)Entry )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v16);
  if ( !*((_QWORD *)v7 + 7) )
    goto LABEL_27;
  if ( a4 != 64
    || (RequestorProcess = FltGetRequestorProcess(CallbackData),
        v21 = *((_QWORD *)v7 + 7),
        *(PEPROCESS *)(v21 + 32) != RequestorProcess)
    || (*(_DWORD *)(v21 + 800) & 0x400) != 0 )
  {
    v22 = PrjfPopulateDestinationForRenameOrLink(CallbackData, *(PFLT_INSTANCE *)(a2 + 24), a3);
    v13 = v22;
    if ( v22 < 0 )
    {
      if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v23) = BYTE1(xmmword_14001A3D0) & 0x20;
        LOBYTE(v24) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          525,
          v23,
          v24,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          13,
          14,
          (__int64)WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fileinfo.c",
          6,
          v22);
      }
      goto LABEL_49;
    }
LABEL_27:
    if ( a4 == 32 )
    {
      if ( *(_QWORD *)v7 )
      {
        v25 = PrjfPrepareSourceForRename(
                CallbackData,
                *(PFLT_INSTANCE *)(a2 + 24),
                *(PFILE_OBJECT *)(a2 + 32),
                FileNameInformation,
                (__int64)v7);
        v13 = v25;
        if ( v25 < 0 )
        {
          if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0
            || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v26) = BYTE1(xmmword_14001A3D0) & 0x20;
            LOBYTE(v27) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDL(
              525,
              v26,
              v27,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              13,
              16,
              (__int64)WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fileinfo.c",
              41,
              v25);
          }
          goto LABEL_49;
        }
      }
      v28 = PrjfSetParentPlaceHolderFlagsSynchronized(CallbackData, *(PFLT_INSTANCE *)(a2 + 24));
      v13 = v28;
      if ( v28 < 0 )
      {
        if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v29) = BYTE1(xmmword_14001A3D0) & 0x20;
          LOBYTE(v30) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDL(
            525,
            v29,
            v30,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            13,
            17,
            (__int64)WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fileinfo.c",
            65,
            v28);
        }
        goto LABEL_49;
      }
      v31 = PrjfSetPlaceHolderFlagsSynchronized(
              CallbackData,
              *(PFLT_INSTANCE *)(a2 + 24),
              CallbackData->Iopb->TargetFileObject);
      v13 = v31;
      if ( v31 < 0 )
      {
        if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v32) = BYTE1(xmmword_14001A3D0) & 0x20;
          LOBYTE(v33) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDL(
            525,
            v32,
            v33,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            13,
            18,
            (__int64)WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fileinfo.c",
            95,
            v31);
        }
        goto LABEL_49;
      }
    }
    goto LABEL_41;
  }
  if ( (BYTE1(xmmword_14001A3E0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v19) = BYTE1(xmmword_14001A3E0) & 0x20;
    LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      1037,
      v19,
      v20,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      4,
      13,
      15,
      (__int64)WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fileinfo.c",
      15,
      64);
  }
LABEL_41:
  v34 = PrjfSetPlaceHolderFlagsSynchronized(CallbackData, *(PFLT_INSTANCE *)(a2 + 24), *((PFILE_OBJECT *)v7 + 10));
  if ( v34 < 0
    && ((BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
  {
    LOBYTE(v35) = BYTE1(xmmword_14001A3D0) & 0x20;
    LOBYTE(v36) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      525,
      v35,
      v36,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      13,
      19,
      (__int64)WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fileinfo.c",
      113,
      v34);
  }
  v37 = PrjfNotifyRenameOrLinkOperation(
          (__int64)CallbackData,
          *(struct _FLT_INSTANCE **)(a2 + 24),
          *(struct _FILE_OBJECT **)(a2 + 32),
          a4,
          (__int128 **)v7);
  v13 = v37;
  if ( v37 >= 0 )
  {
    *a5 = v7;
    v7 = 0;
    goto LABEL_64;
  }
  if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v38) = BYTE1(xmmword_14001A3D0) & 0x20;
    LOBYTE(v39) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      525,
      v38,
      v39,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      13,
      20,
      (__int64)WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fileinfo.c",
      130,
      v37);
  }
LABEL_49:
  if ( v7 )
  {
    if ( *((_QWORD *)v7 + 7)
      && (int)PrjfCleanUpRenameLinkTargetTombstone((__int64)CallbackData, a2, (__int64)v7, 1) < 0
      && ((BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
    {
      LOBYTE(v40) = BYTE2(xmmword_14001A3D0) & 8;
      LOBYTE(v41) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDdd(531, v40, v41, *((_QWORD *)WPP_GLOBAL_Control + 8));
    }
    if ( *(_QWORD *)v7 )
    {
      v42 = *((_QWORD *)v7 + 4);
      if ( v42 )
      {
        v43 = (struct _FILE_OBJECT *)*((_QWORD *)v7 + 3);
        if ( v43 )
        {
          if ( (int)PrjfRemoveInMemoryTombstone(*(PFLT_INSTANCE *)(a2 + 24), v42, v43) < 0 )
          {
            if ( (xmmword_14001A3D0 & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v44) = xmmword_14001A3D0 & 0x40;
              LOBYTE(v45) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_sDdd(518, v44, v45, *((_QWORD *)WPP_GLOBAL_Control + 8));
            }
            PrjfTelemetryTombstoneFailureOperation(2, 9, v13);
          }
        }
      }
    }
  }
LABEL_64:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( v7 )
    PrjfReleaseRenameOrLinkCompletionContext((char **)v7);
  return v13;
}

```

## disassembly

```asm
0x14002c98c  push    rbx
0x14002c98e  push    rbp
0x14002c98f  push    rsi
0x14002c990  push    rdi
0x14002c991  push    r12
0x14002c993  push    r13
0x14002c995  push    r14
0x14002c997  push    r15
0x14002c999  sub     rsp, 78h
0x14002c99d  xor     esi, esi
0x14002c99f  mov     r14, r8
0x14002c9a2  mov     r13, rdx
0x14002c9a5  mov     [rsp+0B8h+FileNameInformation], rsi
0x14002c9aa  mov     ebx, esi
0x14002c9ac  lea     r8, [rsp+0B8h+FileNameInformation]; FileNameInformation
0x14002c9b1  mov     edx, 101h; NameOptions
0x14002c9b6  mov     [rsp+0B8h+Entry], rbx
0x14002c9bb  mov     r12d, r9d
0x14002c9be  mov     r15, rcx
0x14002c9c1  call    cs:__imp_FltGetFileNameInformation
0x14002c9c8  nop     dword ptr [rax+rax+00h]
0x14002c9cd  lea     rbp, aOnecoreBaseFsG_1; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002c9d4  mov     edi, eax
0x14002c9d6  lea     r9, WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids
0x14002c9dd  test    eax, eax
0x14002c9df  jns     short loc_14002CA4B
0x14002c9e1  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002c9e7  lea     rsi, WPP_RECORDER_INITIALIZED
0x14002c9ee  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002c9f5  setnz   r8b
0x14002c9f9  and     dl, 2
0x14002c9fc  jnz     short loc_14002CA07
0x14002c9fe  test    r8b, r8b
0x14002ca01  jz      loc_14002CEDA
0x14002ca07  mov     [rsp+0B8h+var_68], eax
0x14002ca0b  mov     ecx, 209h
0x14002ca10  mov     [rsp+0B8h+var_70], 0C6h
0x14002ca18  mov     [rsp+0B8h+var_78], rbp
0x14002ca1d  mov     [rsp+0B8h+var_80], r9
0x14002ca22  mov     r9, cs:WPP_GLOBAL_Control
0x14002ca29  mov     [rsp+0B8h+var_88], 0Ch
0x14002ca30  mov     dword ptr [rsp+0B8h+var_90], 9
0x14002ca38  mov     byte ptr [rsp+0B8h+var_98], 2
0x14002ca3d  mov     r9, [r9+40h]
0x14002ca41  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14002ca46  jmp     loc_14002CEDA
0x14002ca4b  mov     r8, [rsp+0B8h+FileNameInformation]
0x14002ca50  lea     rax, [rsp+0B8h+Entry]
0x14002ca55  mov     rdx, [r13+18h]
0x14002ca59  mov     r9, r14
0x14002ca5c  mov     rcx, r15
0x14002ca5f  mov     [rsp+0B8h+var_98], rax
0x14002ca64  call    PrjfCreateRenameOrLinkCompletionContext
0x14002ca69  mov     edi, eax
0x14002ca6b  test    eax, eax
0x14002ca6d  jns     loc_14002CAFC
0x14002ca73  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002ca79  lea     rsi, WPP_RECORDER_INITIALIZED
0x14002ca80  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002ca87  setnz   r8b
0x14002ca8b  and     dl, 20h
0x14002ca8e  jnz     short loc_14002CA9F
0x14002ca90  test    r8b, r8b
0x14002ca93  jnz     short loc_14002CA9F
0x14002ca95  mov     rbx, [rsp+0B8h+Entry]
0x14002ca9a  jmp     loc_14002CEDA
0x14002ca9f  mov     r9, cs:WPP_GLOBAL_Control
0x14002caa6  lea     r14, aOnecoreBaseFsG_1; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002caad  mov     [rsp+0B8h+var_68], eax
0x14002cab1  mov     ebp, 0Dh
0x14002cab6  mov     [rsp+0B8h+var_70], 0D4h
0x14002cabe  mov     ecx, 20Dh
0x14002cac3  mov     [rsp+0B8h+var_78], r14
0x14002cac8  lea     r14, WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids
0x14002cacf  mov     r9, [r9+40h]
0x14002cad3  mov     [rsp+0B8h+var_80], r14
0x14002cad8  mov     [rsp+0B8h+var_88], bp
0x14002cadd  mov     dword ptr [rsp+0B8h+var_90], ebp
0x14002cae1  mov     byte ptr [rsp+0B8h+var_98], 2
0x14002cae6  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14002caeb  mov     rbx, [rsp+0B8h+Entry]
0x14002caf0  lea     rbp, aOnecoreBaseFsG_1; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002caf7  jmp     loc_14002CEE1
0x14002cafc  mov     rbx, [rsp+0B8h+Entry]
0x14002cb01  test    rbx, rbx
0x14002cb04  jz      loc_14002D008
0x14002cb0a  cmp     [rbx+38h], rsi
0x14002cb0e  jnz     short loc_14002CB1A
0x14002cb10  cmp     [rbx], rsi
0x14002cb13  jnz     short loc_14002CB1A
0x14002cb15  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002cb1a  cmp     qword ptr [rbx+38h], 0
0x14002cb1f  lea     rsi, WPP_RECORDER_INITIALIZED
0x14002cb26  mov     ebp, 0Dh
0x14002cb2b  jz      loc_14002CC5D
0x14002cb31  cmp     r12d, 40h ; '@'
0x14002cb35  jnz     loc_14002CBD1
0x14002cb3b  mov     rcx, r15; CallbackData
0x14002cb3e  call    cs:__imp_FltGetRequestorProcess
0x14002cb45  nop     dword ptr [rax+rax+00h]
0x14002cb4a  mov     rcx, [rbx+38h]
0x14002cb4e  cmp     [rcx+20h], rax
0x14002cb52  jnz     short loc_14002CBD1
0x14002cb54  test    dword ptr [rcx+320h], 400h
0x14002cb5e  jnz     short loc_14002CBD1
0x14002cb60  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002cb67  mov     dl, byte ptr cs:xmmword_14001A3E0+1
0x14002cb6d  setnz   r8b
0x14002cb71  and     dl, 20h
0x14002cb74  jnz     short loc_14002CB7F
0x14002cb76  test    r8b, r8b
0x14002cb79  jz      loc_14002CDEF
0x14002cb7f  mov     r9, cs:WPP_GLOBAL_Control
0x14002cb86  lea     r14, aOnecoreBaseFsG_1; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002cb8d  mov     [rsp+0B8h+var_68], 40h ; '@'
0x14002cb95  lea     rdi, WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids
0x14002cb9c  mov     [rsp+0B8h+var_70], 10Fh
0x14002cba4  mov     ecx, 40Dh
0x14002cba9  mov     [rsp+0B8h+var_78], r14
0x14002cbae  mov     r9, [r9+40h]
0x14002cbb2  mov     [rsp+0B8h+var_80], rdi
0x14002cbb7  mov     [rsp+0B8h+var_88], 0Fh
0x14002cbbe  mov     dword ptr [rsp+0B8h+var_90], ebp
0x14002cbc2  mov     byte ptr [rsp+0B8h+var_98], 4
0x14002cbc7  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14002cbcc  jmp     loc_14002CDFD
0x14002cbd1  mov     rdx, [r13+18h]
0x14002cbd5  mov     r9, rbx
0x14002cbd8  mov     r8, r14
0x14002cbdb  mov     rcx, r15
0x14002cbde  call    PrjfPopulateDestinationForRenameOrLink
0x14002cbe3  mov     edi, eax
0x14002cbe5  test    eax, eax
0x14002cbe7  jns     short loc_14002CC5D
0x14002cbe9  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002cbef  lea     rsi, WPP_RECORDER_INITIALIZED
0x14002cbf6  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002cbfd  setnz   r8b
0x14002cc01  and     dl, 20h
0x14002cc04  jnz     short loc_14002CC0F
0x14002cc06  test    r8b, r8b
0x14002cc09  jz      loc_14002CED3
0x14002cc0f  mov     [rsp+0B8h+var_68], eax
0x14002cc13  lea     r14, aOnecoreBaseFsG_1; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002cc1a  mov     [rsp+0B8h+var_70], 106h
0x14002cc22  mov     [rsp+0B8h+var_78], r14
0x14002cc27  lea     r14, WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids
0x14002cc2e  mov     [rsp+0B8h+var_80], r14
0x14002cc33  mov     [rsp+0B8h+var_88], 0Eh
0x14002cc3a  mov     r9, cs:WPP_GLOBAL_Control
0x14002cc41  mov     ecx, 20Dh
0x14002cc46  mov     dword ptr [rsp+0B8h+var_90], ebp
0x14002cc4a  mov     byte ptr [rsp+0B8h+var_98], 2
0x14002cc4f  mov     r9, [r9+40h]
0x14002cc53  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14002cc58  jmp     loc_14002CAF0
0x14002cc5d  cmp     r12d, 20h ; ' '
0x14002cc61  jnz     loc_14002CDEF
0x14002cc67  mov     rdx, [rbx]
0x14002cc6a  test    rdx, rdx
0x14002cc6d  jz      loc_14002CD11
0x14002cc73  mov     rcx, [rbx+38h]
0x14002cc77  test    rcx, rcx
0x14002cc7a  jz      short loc_14002CC93
0x14002cc7c  mov     rax, [rdx]
0x14002cc7f  cmp     rax, [rcx]
0x14002cc82  jnz     short loc_14002CC93
0x14002cc84  mov     rax, [rdx+8]
0x14002cc88  cmp     rax, [rcx+8]
0x14002cc8c  jnz     short loc_14002CC93
0x14002cc8e  mov     r9b, 1
0x14002cc91  jmp     short loc_14002CC96
0x14002cc93  xor     r9b, r9b
0x14002cc96  mov     rax, [rsp+0B8h+FileNameInformation]
0x14002cc9b  mov     rcx, r15
0x14002cc9e  mov     r8, [r13+20h]
0x14002cca2  mov     rdx, [r13+18h]
0x14002cca6  mov     [rsp+0B8h+var_90], rbx
0x14002ccab  mov     [rsp+0B8h+var_98], rax
0x14002ccb0  call    PrjfPrepareSourceForRename
0x14002ccb5  mov     edi, eax
0x14002ccb7  test    eax, eax
0x14002ccb9  jns     short loc_14002CD11
0x14002ccbb  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002ccc1  lea     rsi, WPP_RECORDER_INITIALIZED
0x14002ccc8  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002cccf  setnz   r8b
0x14002ccd3  and     dl, 20h
0x14002ccd6  jnz     short loc_14002CCE1
0x14002ccd8  test    r8b, r8b
0x14002ccdb  jz      loc_14002CED3
0x14002cce1  mov     [rsp+0B8h+var_68], eax
0x14002cce5  lea     r14, aOnecoreBaseFsG_1; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002ccec  mov     [rsp+0B8h+var_70], 129h
0x14002ccf4  mov     [rsp+0B8h+var_78], r14
0x14002ccf9  lea     r14, WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids
0x14002cd00  mov     [rsp+0B8h+var_80], r14
0x14002cd05  mov     [rsp+0B8h+var_88], 10h
0x14002cd0c  jmp     loc_14002CC3A
0x14002cd11  mov     rdx, [r13+18h]
0x14002cd15  mov     rcx, r15
0x14002cd18  call    PrjfSetParentPlaceHolderFlagsSynchronized
0x14002cd1d  mov     edi, eax
0x14002cd1f  test    eax, eax
0x14002cd21  jns     short loc_14002CD79
0x14002cd23  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002cd29  lea     rsi, WPP_RECORDER_INITIALIZED
0x14002cd30  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002cd37  setnz   r8b
0x14002cd3b  and     dl, 20h
0x14002cd3e  jnz     short loc_14002CD49
0x14002cd40  test    r8b, r8b
0x14002cd43  jz      loc_14002CED3
0x14002cd49  mov     [rsp+0B8h+var_68], eax
0x14002cd4d  lea     r14, aOnecoreBaseFsG_1; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002cd54  mov     [rsp+0B8h+var_70], 141h
0x14002cd5c  mov     [rsp+0B8h+var_78], r14
0x14002cd61  lea     r14, WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids
0x14002cd68  mov     [rsp+0B8h+var_80], r14
0x14002cd6d  mov     [rsp+0B8h+var_88], 11h
0x14002cd74  jmp     loc_14002CC3A
0x14002cd79  mov     r8, [r15+10h]
0x14002cd7d  mov     r9d, 8
0x14002cd83  mov     rdx, [r13+18h]; Instance
0x14002cd87  mov     rcx, r15; CallbackData
0x14002cd8a  mov     r8, [r8+8]; FileObject
0x14002cd8e  call    PrjfSetPlaceHolderFlagsSynchronized
0x14002cd93  mov     edi, eax
0x14002cd95  test    eax, eax
0x14002cd97  jns     short loc_14002CDEF
0x14002cd99  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002cd9f  lea     rsi, WPP_RECORDER_INITIALIZED
0x14002cda6  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002cdad  setnz   r8b
0x14002cdb1  and     dl, 20h
0x14002cdb4  jnz     short loc_14002CDBF
0x14002cdb6  test    r8b, r8b
0x14002cdb9  jz      loc_14002CED3
0x14002cdbf  mov     [rsp+0B8h+var_68], eax
0x14002cdc3  lea     r14, aOnecoreBaseFsG_1; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002cdca  mov     [rsp+0B8h+var_70], 15Fh
0x14002cdd2  mov     [rsp+0B8h+var_78], r14
0x14002cdd7  lea     r14, WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids
0x14002cdde  mov     [rsp+0B8h+var_80], r14
0x14002cde3  mov     [rsp+0B8h+var_88], 12h
0x14002cdea  jmp     loc_14002CC3A
0x14002cdef  lea     r14, aOnecoreBaseFsG_1; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002cdf6  lea     rdi, WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids
0x14002cdfd  mov     r8, [rbx+50h]; FileObject
0x14002ce01  mov     r9d, 2
0x14002ce07  mov     rdx, [r13+18h]; Instance
0x14002ce0b  mov     rcx, r15; CallbackData
0x14002ce0e  call    PrjfSetPlaceHolderFlagsSynchronized
0x14002ce13  test    eax, eax
0x14002ce15  jns     short loc_14002CE6D
0x14002ce17  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002ce1e  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002ce24  setnz   r8b
0x14002ce28  and     dl, 20h
0x14002ce2b  jnz     short loc_14002CE32
0x14002ce2d  test    r8b, r8b
0x14002ce30  jz      short loc_14002CE6D
0x14002ce32  mov     r9, cs:WPP_GLOBAL_Control
0x14002ce39  mov     ecx, 20Dh
0x14002ce3e  mov     [rsp+0B8h+var_68], eax
0x14002ce42  mov     [rsp+0B8h+var_70], 171h
0x14002ce4a  mov     [rsp+0B8h+var_78], r14
0x14002ce4f  mov     r9, [r9+40h]
0x14002ce53  mov     [rsp+0B8h+var_80], rdi
0x14002ce58  mov     [rsp+0B8h+var_88], 13h
0x14002ce5f  mov     dword ptr [rsp+0B8h+var_90], ebp
0x14002ce63  mov     byte ptr [rsp+0B8h+var_98], 2
0x14002ce68  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14002ce6d  mov     r8, [r13+20h]
0x14002ce71  mov     r9d, r12d
0x14002ce74  mov     rdx, [r13+18h]
0x14002ce78  mov     rcx, r15
0x14002ce7b  mov     [rsp+0B8h+var_98], rbx
0x14002ce80  call    PrjfNotifyRenameOrLinkOperation
0x14002ce85  mov     edi, eax
0x14002ce87  test    eax, eax
0x14002ce89  jns     loc_14002CFFB
0x14002ce8f  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14002ce96  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002ce9c  setnz   r8b
0x14002cea0  and     dl, 20h
0x14002cea3  jnz     short loc_14002CEAA
0x14002cea5  test    r8b, r8b
0x14002cea8  jz      short loc_14002CED3
0x14002ceaa  mov     [rsp+0B8h+var_68], eax
0x14002ceae  mov     [rsp+0B8h+var_70], 182h
0x14002ceb6  mov     [rsp+0B8h+var_78], r14
0x14002cebb  lea     r14, WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids
0x14002cec2  mov     [rsp+0B8h+var_80], r14
0x14002cec7  mov     [rsp+0B8h+var_88], 14h
0x14002cece  jmp     loc_14002CC3A
0x14002ced3  lea     rbp, aOnecoreBaseFsG_1; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002ceda  lea     r14, WPP_9aa94875f0ba3c84ae0a423dcca6636f_Traceguids
0x14002cee1  test    rbx, rbx
0x14002cee4  jz      loc_14002D008
  ... truncated ...
```
