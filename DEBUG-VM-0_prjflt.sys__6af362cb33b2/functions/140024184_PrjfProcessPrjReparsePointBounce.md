# PrjfProcessPrjReparsePointBounce

- ea: `0x140024184`
- end: `0x14002474f`
- name: `PrjfProcessPrjReparsePointBounce`
- size: `1483`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140022320`

## callees

- `0x140002f3c`
- `0x140003e6c`
- `0x140006570`
- `0x1400069a4`
- `0x140006ca0`
- `0x14000b1d0`
- `0x14000d008`
- `0x14000d128`
- `0x14000d754`
- `0x140024184`
- `0x14002aecc`
- `0x14003c4b8`
- `0x14003caa4`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14002472c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14002472c`
- `ntoskrnl!ObfDereferenceObject` at `0x14002470e`
- `ntoskrnl!ObfDereferenceObject` at `0x14002470e`
- `FLTMGR!FltParseFileNameInformation` at `0x140024206`
- `FLTMGR!FltParseFileNameInformation` at `0x140024206`
- `FLTMGR!FltClose` at `0x1400246fa`
- `FLTMGR!FltClose` at `0x1400246fa`
- `FLTMGR!FltReleaseContext` at `0x1400246d0`
- `FLTMGR!FltReleaseContext` at `0x1400246e5`
- `FLTMGR!FltReleaseContext` at `0x1400246d0`
- `FLTMGR!FltReleaseContext` at `0x1400246e5`

## string_xrefs

- `0x140024242`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x1400242f1`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x140024405`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x1400244a9`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x140024575`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x14002461c`: `onecore\base\fs\gvflt\filter\sys\create.c`

## pseudocode

```c
__int64 __fastcall PrjfProcessPrjReparsePointBounce(
        PFLT_CALLBACK_DATA CallbackData,
        PFLT_INSTANCE Instance,
        PFLT_FILE_NAME_INFORMATION FileNameInformation,
        USHORT a4,
        _DWORD *a5,
        _BYTE *a6,
        struct _FILE_OBJECT **a7,
        _BYTE *a8)
{
  _BYTE *v8; // r12
  int v13; // edx
  __int64 v14; // rcx
  int ComponentPathName; // ebx
  int v16; // r8d
  int v17; // edx
  int v18; // r8d
  char v19; // si
  char v20; // r14
  int v21; // eax
  int v22; // edx
  int v23; // r8d
  struct _FILE_OBJECT *v24; // rdi
  int v25; // edx
  int v26; // edx
  int v27; // r8d
  int v28; // eax
  int v29; // edx
  int v30; // r8d
  char v32; // [rsp+60h] [rbp-71h] BYREF
  _BYTE v33[3]; // [rsp+61h] [rbp-70h] BYREF
  ULONG HashValue; // [rsp+64h] [rbp-6Dh] BYREF
  PVOID Object; // [rsp+68h] [rbp-69h] BYREF
  PVOID P; // [rsp+70h] [rbp-61h] BYREF
  PFLT_CONTEXT Context; // [rsp+78h] [rbp-59h] BYREF
  PFLT_CONTEXT v38; // [rsp+80h] [rbp-51h] BYREF
  HANDLE FileHandle; // [rsp+88h] [rbp-49h] BYREF
  struct _UNICODE_STRING v40; // [rsp+90h] [rbp-41h] BYREF
  __int128 v41; // [rsp+A0h] [rbp-31h] BYREF
  struct _UNICODE_STRING FileName; // [rsp+B0h] [rbp-21h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+C0h] [rbp-11h] BYREF

  v8 = a8;
  FileHandle = 0;
  Object = 0;
  v33[0] = 0;
  *a8 = 0;
  v32 = 0;
  Context = 0;
  v38 = 0;
  v40 = 0;
  P = 0;
  v41 = 0;
  HashValue = 0;
  FileName = 0;
  UnicodeString = 0;
  ComponentPathName = FltParseFileNameInformation(FileNameInformation);
  if ( ComponentPathName < 0 )
  {
    if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = xmmword_14001A3D0 & 0x20;
      LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        517,
        v13,
        v16,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        5,
        17,
        (__int64)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
        151,
        ComponentPathName);
    }
    goto LABEL_61;
  }
  if ( a4 < FileNameInformation->FinalComponent.Length )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v14);
  ComponentPathName = PrjfParseParentAndNextComponentPathName(
                        (int)FileNameInformation + 8,
                        a4,
                        (unsigned int)&v40,
                        (unsigned int)&v41,
                        (__int64)&FileName,
                        (__int64)&v32);
  if ( ComponentPathName < 0 )
  {
    if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v17) = xmmword_14001A3D0 & 0x20;
      LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        517,
        v17,
        v18,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        5,
        18,
        (__int64)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
        167,
        ComponentPathName);
    }
    goto LABEL_61;
  }
  v19 = v32;
  if ( HIBYTE(CallbackData->Iopb->Parameters.SetVolumeInformation.FsInformationClass) != 1 && v32 )
  {
    v20 = 0;
    goto LABEL_15;
  }
  LOBYTE(a8) = 0;
  ComponentPathName = PrjfLookupEntryBackingLayerNegativePathCache(
                        Instance,
                        &v40,
                        &FileName.Length,
                        (__int64)&v41,
                        &P,
                        &UnicodeString,
                        &HashValue,
                        &a8);
  if ( ComponentPathName < 0 )
  {
    if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v25) = xmmword_14001A3D0 & 0x20;
      LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDdZ(
        517,
        v25,
        v18,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        5,
        19,
        (__int64)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
        201,
        ComponentPathName,
        (__int64)&v41);
    }
    goto LABEL_59;
  }
  v20 = 1;
  if ( !(_BYTE)a8 )
  {
LABEL_15:
    v21 = PrjfOpenPlaceHolder(
            (_DWORD)Instance,
            (unsigned int)&v40,
            v18,
            (unsigned int)&FileHandle,
            (__int64)&Object,
            (__int64)v33);
    ComponentPathName = v21;
    if ( v21 < 0 )
    {
      if ( v21 == -1073741191 )
      {
        ComponentPathName = -1073741766;
      }
      else if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v22) = xmmword_14001A3D0 & 0x20;
        LOBYTE(v23) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          517,
          v22,
          v23,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          20,
          (__int64)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
          9,
          v21,
          (__int64)&v40);
      }
      v24 = (struct _FILE_OBJECT *)Object;
LABEL_55:
      if ( FileHandle )
        FltClose(FileHandle);
      if ( v24 )
        ObfDereferenceObject(v24);
      goto LABEL_59;
    }
    v24 = (struct _FILE_OBJECT *)Object;
    if ( !v33[0] )
      goto LABEL_48;
    ComponentPathName = PrjfGetSetContextFileObject(
                          Instance,
                          (PFILE_OBJECT)Object,
                          0x80000000,
                          1,
                          0,
                          0,
                          0,
                          &Context,
                          &v38);
    if ( ComponentPathName < 0 )
    {
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v26) = xmmword_14001A3D0 & 0x20;
        LOBYTE(v27) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          517,
          v26,
          v27,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          21,
          (__int64)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
          32,
          ComponentPathName,
          (__int64)&v24->FileName);
      }
      goto LABEL_51;
    }
    v28 = PrjfPartiallyExpandDirectory(CallbackData, Instance, v24, &FileName);
    ComponentPathName = v28;
    if ( v28 >= 0 )
    {
      *v8 = 1;
LABEL_48:
      *a6 = v19;
      if ( v19 )
      {
        *a7 = v24;
        v24 = 0;
      }
      else
      {
        *a7 = 0;
      }
      goto LABEL_51;
    }
    if ( v28 == -1073741267 )
    {
      if ( *a5 < 0x14u )
      {
        ++*a5;
        v19 = 0;
      }
      else
      {
        if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v29) = xmmword_14001A3D0 & 0x20;
          LOBYTE(v30) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sD(
            517,
            v29,
            v30,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            5,
            22,
            (__int64)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
            54);
        }
        PrjfTelemetryTombstoneFailureOperation(4, 8, 3221226029LL);
      }
LABEL_40:
      ComponentPathName = 0;
      goto LABEL_48;
    }
    if ( v28 == -1073741772 )
    {
      if ( !v19 )
        ComponentPathName = -1073741766;
      if ( !v20 )
        goto LABEL_40;
      PrjfInsertEntryBackingLayerNegativePathCache(P, &UnicodeString, HashValue);
    }
LABEL_51:
    if ( Context )
      FltReleaseContext(Context);
    if ( v38 )
      FltReleaseContext(v38);
    goto LABEL_55;
  }
  ComponentPathName = v19 != 0 ? -1073741772 : -1073741766;
LABEL_59:
  if ( P )
    PrjfReleaseUnionContext((char *)P);
LABEL_61:
  RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)ComponentPathName;
}

```

## disassembly

```asm
0x140024184  push    rbp
0x140024186  push    rbx
0x140024187  push    rsi
0x140024188  push    rdi
0x140024189  push    r12
0x14002418b  push    r13
0x14002418d  push    r14
0x14002418f  push    r15
0x140024191  lea     rbp, [rsp-7]
0x140024196  sub     rsp, 0D8h
0x14002419d  mov     r12, [rbp+3Fh+arg_38]
0x1400241a4  xorps   xmm0, xmm0
0x1400241a7  xorps   xmm1, xmm1
0x1400241aa  mov     [rbp+3Fh+FileHandle], 0
0x1400241b2  mov     r13, rcx
0x1400241b5  mov     [rbp+3Fh+Object], 0
0x1400241bd  mov     rcx, r8; FileNameInformation
0x1400241c0  mov     [rbp+3Fh+var_AF], 0
0x1400241c4  mov     byte ptr [r12], 0
0x1400241c9  movzx   esi, r9w
0x1400241cd  mov     rdi, r8
0x1400241d0  mov     [rbp+3Fh+var_B0], 0
0x1400241d4  mov     r15, rdx
0x1400241d7  mov     [rbp+3Fh+Context], 0
0x1400241df  mov     [rbp+3Fh+var_90], 0
0x1400241e7  movups  [rbp+3Fh+var_80], xmm0
0x1400241eb  mov     [rbp+3Fh+P], 0
0x1400241f3  movups  [rbp+3Fh+var_70], xmm1
0x1400241f7  mov     [rbp+3Fh+var_AC], 0
0x1400241fe  movups  xmmword ptr [rbp+3Fh+FileName.Length], xmm0
0x140024202  movups  xmmword ptr [rbp+3Fh+UnicodeString.Length], xmm1
0x140024206  call    cs:__imp_FltParseFileNameInformation
0x14002420d  nop     dword ptr [rax+rax+00h]
0x140024212  mov     ebx, eax
0x140024214  test    eax, eax
0x140024216  jns     short loc_140024290
0x140024218  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14002421e  lea     rax, WPP_RECORDER_INITIALIZED
0x140024225  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002422c  setnz   r8b
0x140024230  and     dl, 20h
0x140024233  jnz     short loc_14002423E
0x140024235  test    r8b, r8b
0x140024238  jz      loc_140024728
0x14002423e  mov     [rsp+110h+var_C0], ebx
0x140024242  lea     rax, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140024249  mov     [rsp+110h+var_C8], 297h
0x140024251  mov     [rsp+110h+var_D0], rax
0x140024256  lea     rax, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x14002425d  mov     [rsp+110h+var_D8], rax
0x140024262  mov     word ptr [rsp+110h+HashValue], 11h
0x140024269  mov     r9, cs:WPP_GLOBAL_Control
0x140024270  mov     ecx, 205h
0x140024275  mov     dword ptr [rsp+110h+DestinationString], 5
0x14002427d  mov     [rsp+110h+var_F0], 2
0x140024282  mov     r9, [r9+40h]
0x140024286  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14002428b  jmp     loc_140024728
0x140024290  cmp     si, [rdi+58h]
0x140024294  jnb     short loc_14002429B
0x140024296  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002429b  lea     rax, [rbp+3Fh+var_B0]
0x14002429f  movzx   edx, si
0x1400242a2  mov     [rsp+110h+DestinationString], rax
0x1400242a7  lea     rcx, [rdi+8]
0x1400242ab  lea     rax, [rbp+3Fh+FileName]
0x1400242af  lea     r9, [rbp+3Fh+var_70]
0x1400242b3  mov     qword ptr [rsp+110h+var_F0], rax
0x1400242b8  lea     r8, [rbp+3Fh+var_80]
0x1400242bc  call    PrjfParseParentAndNextComponentPathName
0x1400242c1  mov     ebx, eax
0x1400242c3  test    eax, eax
0x1400242c5  jns     short loc_14002431D
0x1400242c7  mov     dl, byte ptr cs:xmmword_14001A3D0
0x1400242cd  lea     rax, WPP_RECORDER_INITIALIZED
0x1400242d4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400242db  setnz   r8b
0x1400242df  and     dl, 20h
0x1400242e2  jnz     short loc_1400242ED
0x1400242e4  test    r8b, r8b
0x1400242e7  jz      loc_140024728
0x1400242ed  mov     [rsp+110h+var_C0], ebx
0x1400242f1  lea     rax, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400242f8  mov     [rsp+110h+var_C8], 2A7h
0x140024300  mov     [rsp+110h+var_D0], rax
0x140024305  lea     rax, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x14002430c  mov     [rsp+110h+var_D8], rax
0x140024311  mov     word ptr [rsp+110h+HashValue], 12h
0x140024318  jmp     loc_140024269
0x14002431d  mov     rax, [r13+10h]
0x140024321  mov     sil, [rbp+3Fh+var_B0]
0x140024325  cmp     byte ptr [rax+23h], 1
0x140024329  jz      short loc_14002437A
0x14002432b  test    sil, sil
0x14002432e  jz      short loc_14002437A
0x140024330  xor     r14b, r14b
0x140024333  lea     rax, [rbp+3Fh+var_AF]
0x140024337  mov     rcx, r15
0x14002433a  mov     [rsp+110h+DestinationString], rax
0x14002433f  lea     r9, [rbp+3Fh+FileHandle]
0x140024343  lea     rax, [rbp+3Fh+Object]
0x140024347  lea     rdx, [rbp+3Fh+var_80]
0x14002434b  mov     qword ptr [rsp+110h+var_F0], rax
0x140024350  call    PrjfOpenPlaceHolder
0x140024355  xor     ecx, ecx
0x140024357  mov     ebx, eax
0x140024359  test    eax, eax
0x14002435b  jns     loc_1400244EB
0x140024361  cmp     eax, 0C0000279h
0x140024366  jnz     loc_14002446A
0x14002436c  mov     ebx, 0C000003Ah
0x140024371  mov     rdi, [rbp+3Fh+Object]
0x140024375  jmp     loc_1400246F1
0x14002437a  lea     rax, [rbp+3Fh+arg_38]
0x140024381  mov     byte ptr [rbp+3Fh+arg_38], 0
0x140024388  mov     [rsp+110h+var_D8], rax; __int64
0x14002438d  lea     r9, [rbp+3Fh+var_70]
0x140024391  lea     rax, [rbp+3Fh+var_AC]
0x140024395  mov     rcx, r15; Instance
0x140024398  mov     [rsp+110h+HashValue], rax; HashValue
0x14002439d  lea     r8, [rbp+3Fh+FileName]
0x1400243a1  lea     rax, [rbp+3Fh+UnicodeString]
0x1400243a5  mov     [rsp+110h+DestinationString], rax; DestinationString
0x1400243aa  lea     rdx, [rbp+3Fh+var_80]
0x1400243ae  lea     rax, [rbp+3Fh+P]
0x1400243b2  mov     qword ptr [rsp+110h+var_F0], rax; __int64
0x1400243b7  call    PrjfLookupEntryBackingLayerNegativePathCache
0x1400243bc  mov     ebx, eax
0x1400243be  test    eax, eax
0x1400243c0  jns     loc_140024447
0x1400243c6  mov     dl, byte ptr cs:xmmword_14001A3D0
0x1400243cc  lea     rax, WPP_RECORDER_INITIALIZED
0x1400243d3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400243da  setnz   r8b
0x1400243de  and     dl, 20h
0x1400243e1  jnz     short loc_1400243EC
0x1400243e3  test    r8b, r8b
0x1400243e6  jz      loc_14002471A
0x1400243ec  mov     r9, cs:WPP_GLOBAL_Control
0x1400243f3  lea     rax, [rbp+3Fh+var_70]
0x1400243f7  mov     [rsp+110h+var_B8], rax
0x1400243fc  mov     ecx, 205h
0x140024401  mov     [rsp+110h+var_C0], ebx
0x140024405  lea     rax, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002440c  mov     [rsp+110h+var_C8], 2C9h
0x140024414  mov     r9, [r9+40h]
0x140024418  mov     [rsp+110h+var_D0], rax
0x14002441d  lea     rax, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x140024424  mov     [rsp+110h+var_D8], rax
0x140024429  mov     word ptr [rsp+110h+HashValue], 13h
0x140024430  mov     dword ptr [rsp+110h+DestinationString], 5
0x140024438  mov     [rsp+110h+var_F0], 2
0x14002443d  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140024442  jmp     loc_14002471A
0x140024447  cmp     byte ptr [rbp+3Fh+arg_38], 0
0x14002444e  mov     r14b, 1
0x140024451  jz      loc_140024333
0x140024457  neg     sil
0x14002445a  sbb     ebx, ebx
0x14002445c  and     ebx, 0FFFFFFFAh
0x14002445f  add     ebx, 0C000003Ah
0x140024465  jmp     loc_14002471A
0x14002446a  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140024470  lea     rax, WPP_RECORDER_INITIALIZED
0x140024477  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002447e  setnz   r8b
0x140024482  and     dl, 20h
0x140024485  jnz     short loc_140024490
0x140024487  test    r8b, r8b
0x14002448a  jz      loc_140024371
0x140024490  mov     r9, cs:WPP_GLOBAL_Control
0x140024497  lea     rax, [rbp+3Fh+var_80]
0x14002449b  mov     [rsp+110h+var_B8], rax
0x1400244a0  mov     ecx, 205h
0x1400244a5  mov     [rsp+110h+var_C0], ebx
0x1400244a9  lea     rax, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400244b0  mov     [rsp+110h+var_C8], 309h
0x1400244b8  mov     r9, [r9+40h]
0x1400244bc  mov     [rsp+110h+var_D0], rax
0x1400244c1  lea     rax, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x1400244c8  mov     [rsp+110h+var_D8], rax
0x1400244cd  mov     word ptr [rsp+110h+HashValue], 14h
0x1400244d4  mov     dword ptr [rsp+110h+DestinationString], 5
0x1400244dc  mov     [rsp+110h+var_F0], 2
0x1400244e1  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x1400244e6  jmp     loc_140024371
0x1400244eb  mov     rdi, [rbp+3Fh+Object]
0x1400244ef  cmp     [rbp+3Fh+var_AF], cl
0x1400244f2  jz      loc_1400246A9
0x1400244f8  lea     rax, [rbp+3Fh+var_90]
0x1400244fc  mov     r9b, 1
0x1400244ff  mov     [rsp+110h+var_D0], rax; __int64
0x140024504  mov     r8d, 80000000h
0x14002450a  lea     rax, [rbp+3Fh+Context]
0x14002450e  mov     rdx, rdi; FileObject
0x140024511  mov     [rsp+110h+var_D8], rax; __int64
0x140024516  mov     [rsp+110h+HashValue], rcx; __int64
0x14002451b  mov     [rsp+110h+DestinationString], rcx; __int64
0x140024520  mov     [rsp+110h+var_F0], cl; char
0x140024524  mov     rcx, r15; Instance
0x140024527  call    PrjfGetSetContextFileObject
0x14002452c  mov     ebx, eax
0x14002452e  test    eax, eax
0x140024530  jns     loc_1400245B7
0x140024536  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14002453c  lea     rax, WPP_RECORDER_INITIALIZED
0x140024543  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002454a  setnz   r8b
0x14002454e  and     dl, 20h
0x140024551  jnz     short loc_14002455C
0x140024553  test    r8b, r8b
0x140024556  jz      loc_1400246C7
0x14002455c  mov     r9, cs:WPP_GLOBAL_Control
0x140024563  lea     rax, [rdi+58h]
0x140024567  mov     [rsp+110h+var_B8], rax
0x14002456c  mov     ecx, 205h
0x140024571  mov     [rsp+110h+var_C0], ebx
0x140024575  lea     rax, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002457c  mov     [rsp+110h+var_C8], 320h
0x140024584  mov     r9, [r9+40h]
0x140024588  mov     [rsp+110h+var_D0], rax
0x14002458d  lea     rax, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x140024594  mov     [rsp+110h+var_D8], rax
0x140024599  mov     word ptr [rsp+110h+HashValue], 15h
0x1400245a0  mov     dword ptr [rsp+110h+DestinationString], 5
0x1400245a8  mov     [rsp+110h+var_F0], 2
0x1400245ad  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x1400245b2  jmp     loc_1400246C7
0x1400245b7  lea     r9, [rbp+3Fh+FileName]; FileName
0x1400245bb  mov     r8, rdi; FileObject
0x1400245be  mov     rdx, r15; Instance
0x1400245c1  mov     rcx, r13; CallbackData
0x1400245c4  call    PrjfPartiallyExpandDirectory
0x1400245c9  mov     ebx, eax
0x1400245cb  test    eax, eax
0x1400245cd  jns     loc_1400246A4
0x1400245d3  mov     r15d, 0C000022Dh
0x1400245d9  cmp     eax, r15d
0x1400245dc  jnz     loc_14002467B
0x1400245e2  mov     rcx, [rbp+3Fh+arg_20]
0x1400245e6  mov     r9d, 14h
0x1400245ec  mov     eax, [rcx]
0x1400245ee  cmp     eax, r9d
0x1400245f1  jb      short loc_140024672
0x1400245f3  mov     dl, byte ptr cs:xmmword_14001A3D0
0x1400245f9  lea     rax, WPP_RECORDER_INITIALIZED
0x140024600  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140024607  setnz   r8b
0x14002460b  and     dl, 20h
0x14002460e  jnz     short loc_140024615
0x140024610  test    r8b, r8b
0x140024613  jz      short loc_14002465E
0x140024615  mov     r9, cs:WPP_GLOBAL_Control
0x14002461c  lea     rax, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140024623  mov     [rsp+110h+var_C8], 336h
0x14002462b  mov     ecx, 205h
0x140024630  mov     [rsp+110h+var_D0], rax
0x140024635  lea     rax, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x14002463c  mov     [rsp+110h+var_D8], rax
0x140024641  mov     r9, [r9+40h]
0x140024645  mov     word ptr [rsp+110h+HashValue], 16h
0x14002464c  mov     dword ptr [rsp+110h+DestinationString], 5
0x140024654  mov     [rsp+110h+var_F0], 2
0x140024659  call    WPP_RECORDER_AND_TRACE_SF_sD
0x14002465e  mov     edx, 8
0x140024663  mov     r8d, r15d
0x140024666  lea     ecx, [rdx-4]
0x140024669  call    PrjfTelemetryTombstoneFailureOperation
0x14002466e  xor     ebx, ebx
0x140024670  jmp     short loc_1400246A9
0x140024672  inc     eax
0x140024674  mov     [rcx], eax
0x140024676  xor     sil, sil
0x140024679  jmp     short loc_14002466E
0x14002467b  cmp     ebx, 0C0000034h
0x140024681  jnz     short loc_1400246C7
0x140024683  test    sil, sil
0x140024686  lea     eax, [rbx+6]
0x140024689  cmovz   ebx, eax
0x14002468c  test    r14b, r14b
0x14002468f  jz      short loc_14002466E
0x140024691  mov     r8d, [rbp+3Fh+var_AC]
0x140024695  lea     rdx, [rbp+3Fh+UnicodeString]
0x140024699  mov     rcx, [rbp+3Fh+P]
0x14002469d  call    PrjfInsertEntryBackingLayerNegativePathCache
0x1400246a2  jmp     short loc_1400246C7
0x1400246a4  mov     byte ptr [r12], 1
0x1400246a9  mov     rax, [rbp+3Fh+arg_28]
0x1400246ad  mov     [rax], sil
0x1400246b0  mov     rax, [rbp+3Fh+arg_30]
0x1400246b4  test    sil, sil
0x1400246b7  jz      short loc_1400246C0
0x1400246b9  mov     [rax], rdi
0x1400246bc  xor     edi, edi
0x1400246be  jmp     short loc_1400246C7
0x1400246c0  mov     qword ptr [rax], 0
0x1400246c7  mov     rcx, [rbp+3Fh+Context]; Context
0x1400246cb  test    rcx, rcx
0x1400246ce  jz      short loc_1400246DC
0x1400246d0  call    cs:__imp_FltReleaseContext
  ... truncated ...
```
