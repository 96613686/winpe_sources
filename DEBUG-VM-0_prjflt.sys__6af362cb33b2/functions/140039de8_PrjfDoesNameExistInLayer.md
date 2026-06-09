# PrjfDoesNameExistInLayer

- ea: `0x140039de8`
- end: `0x14003a4c8`
- name: `PrjfDoesNameExistInLayer`
- size: `1760`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, PFLT_INSTANCE Instance)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140007cec`
- `0x14003cc14`

## callees

- `0x140002f3c`
- `0x1400037e0`
- `0x140003e6c`
- `0x14000752c`
- `0x14000b1d0`
- `0x14000ba20`
- `0x14000d128`
- `0x14000d754`
- `0x140034428`
- `0x1400346f0`
- `0x140034e88`
- `0x140035060`
- `0x140039de8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003a479`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a492`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a479`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a492`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a410`
- `ntoskrnl!ObfDereferenceObject` at `0x14003a410`
- `ntoskrnl!ExAllocatePool2` at `0x14003a239`
- `ntoskrnl!ExAllocatePool2` at `0x14003a239`
- `ntoskrnl!ExUuidCreate` at `0x14003a25c`
- `ntoskrnl!ExUuidCreate` at `0x14003a25c`
- `FLTMGR!FltParseFileNameInformation` at `0x14003a1c1`
- `FLTMGR!FltParseFileNameInformation` at `0x14003a1c1`
- `FLTMGR!FltClose` at `0x14003a3fc`
- `FLTMGR!FltClose` at `0x14003a3fc`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003a429`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003a429`
- `FLTMGR!FltGetFileNameInformation` at `0x140039e5b`
- `FLTMGR!FltGetFileNameInformation` at `0x140039e5b`
- `FLTMGR!FltReleaseContext` at `0x14003a43e`
- `FLTMGR!FltReleaseContext` at `0x14003a452`
- `FLTMGR!FltReleaseContext` at `0x14003a43e`
- `FLTMGR!FltReleaseContext` at `0x14003a452`

## pseudocode

```c
__int64 __fastcall PrjfDoesNameExistInLayer(PFLT_CALLBACK_DATA CallbackData, PFLT_INSTANCE Instance, _BYTE *a3)
{
  char *v6; // rdi
  void *v7; // r15
  void *v8; // r12
  int v9; // edx
  int UnionContextByFileName; // ebx
  int v11; // r8d
  int v12; // edx
  int v13; // r8d
  int v14; // edx
  int v15; // r8d
  int v16; // eax
  int v17; // edx
  int v18; // r8d
  PVOID v19; // r15
  int v20; // edx
  __int64 v21; // rcx
  int v22; // r8d
  int v23; // edx
  int v24; // r8d
  int v25; // edx
  int v26; // r8d
  int v27; // edx
  int v28; // r8d
  _BYTE v30[8]; // [rsp+60h] [rbp-69h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+68h] [rbp-61h] BYREF
  __int64 v32; // [rsp+70h] [rbp-59h] BYREF
  __int64 v33; // [rsp+78h] [rbp-51h] BYREF
  void *Pool2; // [rsp+80h] [rbp-49h]
  PVOID Object[2]; // [rsp+90h] [rbp-39h] BYREF
  int v36; // [rsp+A0h] [rbp-29h] BYREF
  PFLT_CONTEXT Context; // [rsp+A8h] [rbp-21h] BYREF
  HANDLE FileHandle[2]; // [rsp+B0h] [rbp-19h] BYREF
  PVOID P[2]; // [rsp+C0h] [rbp-9h] BYREF
  UUID Uuid; // [rsp+D0h] [rbp+7h] BYREF

  *a3 = 0;
  v32 = 0;
  Pool2 = 0;
  v36 = 0;
  FileNameInformation = 0;
  v6 = 0;
  Object[0] = 0;
  *(_OWORD *)P = 0;
  v7 = 0;
  FileHandle[0] = 0;
  Uuid = 0;
  Context = 0;
  v8 = 0;
  v33 = 0;
  UnionContextByFileName = FltGetFileNameInformation(CallbackData, 0x101u, &FileNameInformation);
  if ( UnionContextByFileName >= 0 )
  {
    UnionContextByFileName = PrjfGetUnionContextByFileNameEx(CallbackData, (__int64)&v32, (__int64)P, 0);
    if ( UnionContextByFileName >= 0 )
    {
      v6 = (char *)v32;
      if ( v32 )
      {
        if ( (*(_DWORD *)(v32 + 56) & 0x20000) != 0 )
        {
          *(_OWORD *)FileHandle = *(_OWORD *)v32;
          UnionContextByFileName = PrjfSendQueryFileNameCommand(
                                     (_DWORD)CallbackData,
                                     (_DWORD)Instance,
                                     (unsigned int)FileHandle,
                                     (unsigned int)P,
                                     (__int64)a3);
          if ( UnionContextByFileName < 0
            && ((xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
          {
            LOBYTE(v14) = xmmword_14001A3D0 & 0x20;
            LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDdZ(
              517,
              v14,
              v15,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              5,
              107,
              (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
              149,
              UnionContextByFileName,
              (__int64)P);
          }
        }
        else
        {
          v30[0] = 0;
          v16 = PrjfOpenParentPlaceHolder(
                  (_DWORD)CallbackData,
                  (_DWORD)Instance,
                  (unsigned int)FileHandle,
                  (unsigned int)Object,
                  (__int64)v30);
          v19 = Object[0];
          UnionContextByFileName = v16;
          if ( v16 >= 0 )
          {
            if ( v30[0] )
            {
              UnionContextByFileName = PrjfGetSetContextFileObject(
                                         Instance,
                                         (PFILE_OBJECT)Object[0],
                                         0x80000000,
                                         0,
                                         0,
                                         0,
                                         0,
                                         &Context,
                                         &v33);
              if ( UnionContextByFileName >= 0 )
              {
                v8 = (void *)v33;
                if ( *(_DWORD *)v33 != 1 )
                  MicrosoftTelemetryAssertTriggeredNoArgsKM(v21);
                UnionContextByFileName = FltParseFileNameInformation(FileNameInformation);
                if ( UnionContextByFileName >= 0 )
                {
                  Pool2 = (void *)ExAllocatePool2(256, 522, 1701071440);
                  if ( Pool2 )
                  {
                    UnionContextByFileName = ExUuidCreate(&Uuid);
                    if ( UnionContextByFileName >= 0 )
                    {
                      *(UUID *)Object = Uuid;
                      UnionContextByFileName = PrjfSendStartDirectoryEnumerationCommand(
                                                 CallbackData,
                                                 Instance,
                                                 v19,
                                                 Object);
                      if ( UnionContextByFileName == -1073741772 )
                      {
                        UnionContextByFileName = 0;
                      }
                      else if ( UnionContextByFileName >= 0 )
                      {
                        *(UUID *)Object = Uuid;
                        UnionContextByFileName = PrjfSendGetDirectoryEnumerationCommand(
                                                   (_DWORD)CallbackData,
                                                   (_DWORD)Instance,
                                                   (_DWORD)v19,
                                                   12,
                                                   (__int64)&FileNameInformation->FinalComponent,
                                                   1,
                                                   522,
                                                   (__int64)Object,
                                                   (__int64)Pool2,
                                                   (__int64)&v36);
                        if ( UnionContextByFileName == -2147483642 )
                        {
                          UnionContextByFileName = 0;
                        }
                        else if ( UnionContextByFileName >= 0 )
                        {
                          *a3 = 1;
                        }
                        else if ( (xmmword_14001A3D0 & 0x20) != 0
                               || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                        {
                          LOBYTE(v27) = xmmword_14001A3D0 & 0x20;
                          LOBYTE(v28) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                          WPP_RECORDER_AND_TRACE_SF_sDL(
                            517,
                            v27,
                            v28,
                            *((_QWORD *)WPP_GLOBAL_Control + 8),
                            2,
                            5,
                            112,
                            (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
                            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
                            29,
                            UnionContextByFileName);
                        }
                        *(UUID *)Object = Uuid;
                        PrjfSendEndDirectoryEnumerationCommand(
                          (_DWORD)CallbackData,
                          (_DWORD)Instance,
                          (_DWORD)v19,
                          0,
                          (__int64)Object);
                      }
                      else if ( (xmmword_14001A3D0 & 0x20) != 0
                             || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                      {
                        LOBYTE(v25) = xmmword_14001A3D0 & 0x20;
                        LOBYTE(v26) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                        WPP_RECORDER_AND_TRACE_SF_sDL(
                          517,
                          v25,
                          v26,
                          *((_QWORD *)WPP_GLOBAL_Control + 8),
                          2,
                          5,
                          111,
                          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
                          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
                          2,
                          UnionContextByFileName);
                      }
                    }
                  }
                  else
                  {
                    UnionContextByFileName = -1073741670;
                  }
                }
                else if ( (xmmword_14001A3D0 & 0x20) != 0
                       || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v23) = xmmword_14001A3D0 & 0x20;
                  LOBYTE(v24) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                  WPP_RECORDER_AND_TRACE_SF_sDL(
                    517,
                    v23,
                    v24,
                    *((_QWORD *)WPP_GLOBAL_Control + 8),
                    2,
                    5,
                    110,
                    (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
                    (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
                    218,
                    UnionContextByFileName);
                }
              }
              else
              {
                if ( (xmmword_14001A3D0 & 0x20) != 0
                  || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v20) = xmmword_14001A3D0 & 0x20;
                  LOBYTE(v22) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                  WPP_RECORDER_AND_TRACE_SF_sDL(
                    517,
                    v20,
                    v22,
                    *((_QWORD *)WPP_GLOBAL_Control + 8),
                    2,
                    5,
                    109,
                    (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
                    (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
                    207,
                    UnionContextByFileName);
                }
                v8 = (void *)v33;
              }
            }
          }
          else if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
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
              108,
              (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
              177,
              v16);
          }
          if ( FileHandle[0] )
            FltClose(FileHandle[0]);
          if ( v19 )
            ObfDereferenceObject(v19);
          v7 = Pool2;
        }
      }
    }
    else
    {
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = xmmword_14001A3D0 & 0x20;
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          517,
          v12,
          v13,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          106,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          118,
          UnionContextByFileName);
      }
      v6 = (char *)v32;
    }
  }
  else if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = xmmword_14001A3D0 & 0x20;
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      517,
      v9,
      v11,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      5,
      105,
      (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
      104,
      UnionContextByFileName);
  }
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( Context )
    FltReleaseContext(Context);
  if ( v8 )
    FltReleaseContext(v8);
  if ( v6 )
    PrjfReleaseUnionContext(v6);
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x6E664A50u);
  if ( v7 )
    ExFreePoolWithTag(v7, 0x65644A50u);
  return (unsigned int)UnionContextByFileName;
}

```

## disassembly

```asm
0x140039de8  mov     [rsp-8+arg_18], rbx
0x140039ded  push    rbp
0x140039dee  push    rsi
0x140039def  push    rdi
0x140039df0  push    r12
0x140039df2  push    r13
0x140039df4  push    r14
0x140039df6  push    r15
0x140039df8  lea     rbp, [rsp-27h]
0x140039dfd  sub     rsp, 0F0h
0x140039e04  mov     rax, cs:__security_cookie
0x140039e0b  xor     rax, rsp
0x140039e0e  mov     [rbp+57h+var_40], rax
0x140039e12  xor     eax, eax
0x140039e14  xorps   xmm0, xmm0
0x140039e17  mov     [r8], al
0x140039e1a  mov     r13, r8
0x140039e1d  mov     rsi, rdx
0x140039e20  mov     [rbp+57h+var_B0], rax
0x140039e24  lea     r8, [rbp+57h+FileNameInformation]; FileNameInformation
0x140039e28  mov     [rbp+57h+var_A0], rax
0x140039e2c  mov     edx, 101h; NameOptions
0x140039e31  mov     [rbp+57h+var_80], eax
0x140039e34  mov     r14, rcx
0x140039e37  mov     [rbp+57h+FileNameInformation], rax
0x140039e3b  mov     edi, eax
0x140039e3d  mov     [rbp+57h+Object], rax
0x140039e41  movups  xmmword ptr [rbp+57h+P], xmm0
0x140039e45  mov     r15d, eax
0x140039e48  mov     [rbp+57h+FileHandle], rax
0x140039e4c  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x140039e50  mov     [rbp+57h+Context], rax
0x140039e54  mov     r12d, eax
0x140039e57  mov     [rbp+57h+var_A8], rax
0x140039e5b  call    cs:__imp_FltGetFileNameInformation
0x140039e62  nop     dword ptr [rax+rax+00h]
0x140039e67  mov     ebx, eax
0x140039e69  test    eax, eax
0x140039e6b  jns     short loc_140039EE5
0x140039e6d  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140039e73  lea     rax, WPP_RECORDER_INITIALIZED
0x140039e7a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140039e81  setnz   r8b
0x140039e85  and     dl, 20h
0x140039e88  jnz     short loc_140039E93
0x140039e8a  test    r8b, r8b
0x140039e8d  jz      loc_14003A420
0x140039e93  mov     r9, cs:WPP_GLOBAL_Control
0x140039e9a  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140039ea1  mov     [rsp+120h+var_D0], ebx
0x140039ea5  mov     ecx, 205h
0x140039eaa  mov     dword ptr [rsp+120h+var_D8], 1268h
0x140039eb2  mov     [rsp+120h+var_E0], rax
0x140039eb7  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140039ebe  mov     r9, [r9+40h]
0x140039ec2  mov     [rsp+120h+var_E8], rax
0x140039ec7  mov     word ptr [rsp+120h+var_F0], 69h ; 'i'
0x140039ece  mov     dword ptr [rsp+120h+var_F8], 5
0x140039ed6  mov     [rsp+120h+var_100], 2
0x140039edb  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140039ee0  jmp     loc_14003A420
0x140039ee5  mov     r9, [rbp+57h+FileNameInformation]
0x140039ee9  lea     rax, [rbp+57h+P]
0x140039eed  mov     [rsp+120h+var_F0], rdi; __int64
0x140039ef2  add     r9, 8
0x140039ef6  mov     [rsp+120h+var_F8], rax; __int64
0x140039efb  mov     r8, rsi
0x140039efe  lea     rax, [rbp+57h+var_B0]
0x140039f02  xor     edx, edx
0x140039f04  mov     rcx, r14; CallbackData
0x140039f07  mov     qword ptr [rsp+120h+var_100], rax; __int64
0x140039f0c  call    PrjfGetUnionContextByFileNameEx
0x140039f11  mov     ebx, eax
0x140039f13  test    eax, eax
0x140039f15  jns     short loc_140039F8F
0x140039f17  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140039f1d  lea     rax, WPP_RECORDER_INITIALIZED
0x140039f24  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140039f2b  setnz   r8b
0x140039f2f  and     dl, 20h
0x140039f32  jnz     short loc_140039F39
0x140039f34  test    r8b, r8b
0x140039f37  jz      short loc_140039F86
0x140039f39  mov     r9, cs:WPP_GLOBAL_Control
0x140039f40  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140039f47  mov     [rsp+120h+var_D0], ebx
0x140039f4b  mov     ecx, 205h
0x140039f50  mov     dword ptr [rsp+120h+var_D8], 1276h
0x140039f58  mov     [rsp+120h+var_E0], rax
0x140039f5d  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140039f64  mov     r9, [r9+40h]
0x140039f68  mov     [rsp+120h+var_E8], rax
0x140039f6d  mov     word ptr [rsp+120h+var_F0], 6Ah ; 'j'
0x140039f74  mov     dword ptr [rsp+120h+var_F8], 5
0x140039f7c  mov     [rsp+120h+var_100], 2
0x140039f81  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140039f86  mov     rdi, [rbp+57h+var_B0]
0x140039f8a  jmp     loc_14003A420
0x140039f8f  mov     rdi, [rbp+57h+var_B0]
0x140039f93  test    rdi, rdi
0x140039f96  jz      loc_14003A420
0x140039f9c  test    dword ptr [rdi+38h], 20000h
0x140039fa3  mov     rdx, rsi
0x140039fa6  mov     rcx, r14
0x140039fa9  jz      loc_14003A054
0x140039faf  movups  xmm0, xmmword ptr [rdi]
0x140039fb2  lea     r9, [rbp+57h+P]
0x140039fb6  mov     qword ptr [rsp+120h+var_100], r13
0x140039fbb  lea     r8, [rbp+57h+FileHandle]
0x140039fbf  movdqu  xmmword ptr [rbp+57h+FileHandle], xmm0
0x140039fc4  call    PrjfSendQueryFileNameCommand
0x140039fc9  mov     ebx, eax
0x140039fcb  test    eax, eax
0x140039fcd  jns     loc_14003A420
0x140039fd3  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140039fd9  lea     rax, WPP_RECORDER_INITIALIZED
0x140039fe0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140039fe7  setnz   r8b
0x140039feb  and     dl, 20h
0x140039fee  jnz     short loc_140039FF9
0x140039ff0  test    r8b, r8b
0x140039ff3  jz      loc_14003A420
0x140039ff9  mov     r9, cs:WPP_GLOBAL_Control
0x14003a000  lea     rax, [rbp+57h+P]
0x14003a004  mov     [rsp+120h+var_C8], rax
0x14003a009  mov     ecx, 205h
0x14003a00e  mov     [rsp+120h+var_D0], ebx
0x14003a012  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003a019  mov     dword ptr [rsp+120h+var_D8], 1295h
0x14003a021  mov     r9, [r9+40h]
0x14003a025  mov     [rsp+120h+var_E0], rax
0x14003a02a  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003a031  mov     [rsp+120h+var_E8], rax
0x14003a036  mov     word ptr [rsp+120h+var_F0], 6Bh ; 'k'
0x14003a03d  mov     dword ptr [rsp+120h+var_F8], 5
0x14003a045  mov     [rsp+120h+var_100], 2
0x14003a04a  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x14003a04f  jmp     loc_14003A420
0x14003a054  lea     rax, [rbp+57h+var_C0]
0x14003a058  mov     [rbp+57h+var_C0], r12b
0x14003a05c  lea     r9, [rbp+57h+Object]
0x14003a060  mov     qword ptr [rsp+120h+var_100], rax
0x14003a065  lea     r8, [rbp+57h+FileHandle]
0x14003a069  call    PrjfOpenParentPlaceHolder
0x14003a06e  mov     r15, [rbp+57h+Object]
0x14003a072  xor     ecx, ecx
0x14003a074  mov     ebx, eax
0x14003a076  test    eax, eax
0x14003a078  jns     short loc_14003A0F2
0x14003a07a  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14003a080  lea     rax, WPP_RECORDER_INITIALIZED
0x14003a087  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003a08e  setnz   r8b
0x14003a092  and     dl, 20h
0x14003a095  jnz     short loc_14003A0A0
0x14003a097  test    r8b, r8b
0x14003a09a  jz      loc_14003A3F3
0x14003a0a0  mov     [rsp+120h+var_D0], ebx
0x14003a0a4  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003a0ab  mov     dword ptr [rsp+120h+var_D8], 12B1h
0x14003a0b3  mov     [rsp+120h+var_E0], rax
0x14003a0b8  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003a0bf  mov     [rsp+120h+var_E8], rax
0x14003a0c4  mov     word ptr [rsp+120h+var_F0], 6Ch ; 'l'
0x14003a0cb  mov     r9, cs:WPP_GLOBAL_Control
0x14003a0d2  mov     ecx, 205h
0x14003a0d7  mov     dword ptr [rsp+120h+var_F8], 5
0x14003a0df  mov     [rsp+120h+var_100], 2
0x14003a0e4  mov     r9, [r9+40h]
0x14003a0e8  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14003a0ed  jmp     loc_14003A3F3
0x14003a0f2  cmp     [rbp+57h+var_C0], cl
0x14003a0f5  jz      loc_14003A3F3
0x14003a0fb  lea     rax, [rbp+57h+var_A8]
0x14003a0ff  xor     r9d, r9d
0x14003a102  mov     [rsp+120h+var_E0], rax; __int64
0x14003a107  mov     r8d, 80000000h
0x14003a10d  lea     rax, [rbp+57h+Context]
0x14003a111  mov     rdx, r15; FileObject
0x14003a114  mov     [rsp+120h+var_E8], rax; __int64
0x14003a119  mov     [rsp+120h+var_F0], rcx; __int64
0x14003a11e  mov     [rsp+120h+var_F8], rcx; __int64
0x14003a123  mov     [rsp+120h+var_100], cl; char
0x14003a127  mov     rcx, rsi; Instance
0x14003a12a  call    PrjfGetSetContextFileObject
0x14003a12f  mov     ebx, eax
0x14003a131  test    eax, eax
0x14003a133  jns     short loc_14003A1AD
0x14003a135  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14003a13b  lea     rax, WPP_RECORDER_INITIALIZED
0x14003a142  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003a149  setnz   r8b
0x14003a14d  and     dl, 20h
0x14003a150  jnz     short loc_14003A157
0x14003a152  test    r8b, r8b
0x14003a155  jz      short loc_14003A1A4
0x14003a157  mov     r9, cs:WPP_GLOBAL_Control
0x14003a15e  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003a165  mov     [rsp+120h+var_D0], ebx
0x14003a169  mov     ecx, 205h
0x14003a16e  mov     dword ptr [rsp+120h+var_D8], 12CFh
0x14003a176  mov     [rsp+120h+var_E0], rax
0x14003a17b  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003a182  mov     r9, [r9+40h]
0x14003a186  mov     [rsp+120h+var_E8], rax
0x14003a18b  mov     word ptr [rsp+120h+var_F0], 6Dh ; 'm'
0x14003a192  mov     dword ptr [rsp+120h+var_F8], 5
0x14003a19a  mov     [rsp+120h+var_100], 2
0x14003a19f  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14003a1a4  mov     r12, [rbp+57h+var_A8]
0x14003a1a8  jmp     loc_14003A3F3
0x14003a1ad  mov     r12, [rbp+57h+var_A8]
0x14003a1b1  cmp     dword ptr [r12], 1
0x14003a1b6  jz      short loc_14003A1BD
0x14003a1b8  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003a1bd  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x14003a1c1  call    cs:__imp_FltParseFileNameInformation
0x14003a1c8  nop     dword ptr [rax+rax+00h]
0x14003a1cd  mov     ebx, eax
0x14003a1cf  test    eax, eax
0x14003a1d1  jns     short loc_14003A229
0x14003a1d3  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14003a1d9  lea     rax, WPP_RECORDER_INITIALIZED
0x14003a1e0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003a1e7  setnz   r8b
0x14003a1eb  and     dl, 20h
0x14003a1ee  jnz     short loc_14003A1F9
0x14003a1f0  test    r8b, r8b
0x14003a1f3  jz      loc_14003A3F3
0x14003a1f9  mov     [rsp+120h+var_D0], ebx
0x14003a1fd  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003a204  mov     dword ptr [rsp+120h+var_D8], 12DAh
0x14003a20c  mov     [rsp+120h+var_E0], rax
0x14003a211  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003a218  mov     [rsp+120h+var_E8], rax
0x14003a21d  mov     word ptr [rsp+120h+var_F0], 6Eh ; 'n'
0x14003a224  jmp     loc_14003A0CB
0x14003a229  mov     edx, 20Ah
0x14003a22e  mov     ecx, 100h
0x14003a233  mov     r8d, 65644A50h
0x14003a239  call    cs:__imp_ExAllocatePool2
0x14003a240  nop     dword ptr [rax+rax+00h]
0x14003a245  mov     [rbp+57h+var_A0], rax
0x14003a249  test    rax, rax
0x14003a24c  jnz     short loc_14003A258
0x14003a24e  mov     ebx, 0C000009Ah
0x14003a253  jmp     loc_14003A3F3
0x14003a258  lea     rcx, [rbp+57h+Uuid]; Uuid
0x14003a25c  call    cs:__imp_ExUuidCreate
0x14003a263  nop     dword ptr [rax+rax+00h]
0x14003a268  mov     ebx, eax
0x14003a26a  test    eax, eax
0x14003a26c  js      loc_14003A3F3
0x14003a272  movaps  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x14003a276  lea     r9, [rbp+57h+Object]
0x14003a27a  mov     r8, r15
0x14003a27d  movdqa  xmmword ptr [rbp+57h+Object], xmm0
0x14003a282  mov     rdx, rsi
0x14003a285  mov     rcx, r14
0x14003a288  call    PrjfSendStartDirectoryEnumerationCommand
0x14003a28d  mov     ebx, eax
0x14003a28f  cmp     eax, 0C0000034h
0x14003a294  jnz     short loc_14003A29D
0x14003a296  xor     ebx, ebx
0x14003a298  jmp     loc_14003A3F3
0x14003a29d  test    ebx, ebx
0x14003a29f  jns     short loc_14003A2F7
0x14003a2a1  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14003a2a7  lea     rax, WPP_RECORDER_INITIALIZED
0x14003a2ae  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003a2b5  setnz   r8b
0x14003a2b9  and     dl, 20h
0x14003a2bc  jnz     short loc_14003A2C7
0x14003a2be  test    r8b, r8b
0x14003a2c1  jz      loc_14003A3F3
0x14003a2c7  mov     [rsp+120h+var_D0], ebx
0x14003a2cb  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003a2d2  mov     dword ptr [rsp+120h+var_D8], 1302h
0x14003a2da  mov     [rsp+120h+var_E0], rax
0x14003a2df  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14003a2e6  mov     [rsp+120h+var_E8], rax
0x14003a2eb  mov     word ptr [rsp+120h+var_F0], 6Fh ; 'o'
0x14003a2f2  jmp     loc_14003A0CB
0x14003a2f7  mov     rax, [rbp+57h+FileNameInformation]
0x14003a2fb  lea     rcx, [rbp+57h+var_80]
0x14003a2ff  movaps  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x14003a303  add     rax, 58h ; 'X'
0x14003a307  mov     [rsp+120h+var_D8], rcx
0x14003a30c  mov     r9d, 0Ch
0x14003a312  mov     rcx, [rbp+57h+var_A0]
0x14003a316  mov     r8, r15
0x14003a319  mov     [rsp+120h+var_E0], rcx
0x14003a31e  mov     rdx, rsi
0x14003a321  lea     rcx, [rbp+57h+Object]
0x14003a325  movdqa  xmmword ptr [rbp+57h+Object], xmm0
0x14003a32a  mov     [rsp+120h+var_E8], rcx
0x14003a32f  mov     rcx, r14
0x14003a332  mov     dword ptr [rsp+120h+var_F0], 20Ah
0x14003a33a  mov     byte ptr [rsp+120h+var_F8], 1
0x14003a33f  mov     qword ptr [rsp+120h+var_100], rax
  ... truncated ...
```
