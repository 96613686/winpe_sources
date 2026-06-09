# MpQueryLoopbackLocalPathByName

- ea: `0x140088da4`
- end: `0x140089512`
- name: `MpQueryLoopbackLocalPathByName`
- size: `1902`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140040680`
- `0x140046090`
- `0x140072f34`

## callees

- `0x1400026c0`
- `0x140004da8`
- `0x1400051bc`
- `0x140005228`
- `0x14000b704`
- `0x140011890`
- `0x1400118d0`
- `0x140038710`
- `0x140048efc`
- `0x140050850`
- `0x140066180`
- `0x140088da4`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140089325`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140089325`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14008937b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14008937b`
- `ntoskrnl!RtlIsNameLegalDOS8Dot3` at `0x1400890d3`
- `ntoskrnl!RtlIsNameLegalDOS8Dot3` at `0x1400890d3`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14008933c`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14008933c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140089217`
- `ntoskrnl!RtlInitUnicodeString` at `0x140089217`
- `ntoskrnl!ExFreePoolWithTag` at `0x140089101`
- `ntoskrnl!ExFreePoolWithTag` at `0x140089441`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008946b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140089101`
- `ntoskrnl!ExFreePoolWithTag` at `0x140089441`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008946b`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400894c5`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400894c5`
- `ntoskrnl!KeBugCheck` at `0x1400894df`
- `ntoskrnl!KeBugCheck` at `0x1400894df`
- `ntoskrnl!ObfDereferenceObject` at `0x140089495`
- `ntoskrnl!ObfDereferenceObject` at `0x140089495`
- `FLTMGR!FltQueryDirectoryFile` at `0x140089174`
- `FLTMGR!FltQueryDirectoryFile` at `0x140089174`
- `FLTMGR!FltParseFileNameInformation` at `0x140088e43`
- `FLTMGR!FltParseFileNameInformation` at `0x140088e43`
- `FLTMGR!FltClose` at `0x140089480`
- `FLTMGR!FltClose` at `0x140089480`

## pseudocode

```c
__int64 __fastcall MpQueryLoopbackLocalPathByName(
        __int64 a1,
        struct _FLT_FILE_NAME_INFORMATION *a2,
        PUNICODE_STRING *a3,
        _QWORD *a4)
{
  USHORT *PoolWithTag; // r12
  NTSTATUS v7; // eax
  NTSTATUS appended; // ebx
  __int64 v9; // rdx
  USHORT Length; // dx
  __int16 v11; // cx
  __int64 (__fastcall *v12)(_QWORD); // rax
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  int FileEx2; // eax
  unsigned __int64 v17; // r14
  NTSTATUS DirectoryFile; // eax
  WCHAR *Buffer; // rax
  char *v20; // r14
  __int64 v21; // r15
  __int64 v22; // rdx
  PUNICODE_STRING v23; // rax
  __int64 v24; // rdx
  USHORT v25; // ax
  int v26; // eax
  NTSTATUS FileInformationClass; // [rsp+20h] [rbp-E0h]
  int FileInformationClassa; // [rsp+20h] [rbp-E0h]
  int RestartScan; // [rsp+38h] [rbp-C8h]
  int LengthReturned; // [rsp+40h] [rbp-C0h]
  ULONG v32; // [rsp+50h] [rbp-B0h]
  int v33; // [rsp+60h] [rbp-A0h]
  int v34; // [rsp+68h] [rbp-98h]
  PUNICODE_STRING Destination; // [rsp+80h] [rbp-80h] BYREF
  PVOID P; // [rsp+88h] [rbp-78h] BYREF
  PUNICODE_STRING *v37; // [rsp+90h] [rbp-70h]
  UNICODE_STRING Source; // [rsp+98h] [rbp-68h] BYREF
  PFILE_OBJECT FileObject; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE FileHandle; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v41[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v42; // [rsp+C8h] [rbp-38h]
  __int64 v43; // [rsp+D8h] [rbp-28h]
  __int64 v44[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v45; // [rsp+F0h] [rbp-10h]
  __int128 v46; // [rsp+100h] [rbp+0h]
  ULONG v47[4]; // [rsp+110h] [rbp+10h] BYREF
  UNICODE_STRING SourceString; // [rsp+120h] [rbp+20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+130h] [rbp+30h] BYREF
  __int64 v50[2]; // [rsp+140h] [rbp+40h] BYREF

  v37 = a3;
  FileHandle = 0;
  FileObject = 0;
  Destination = 0;
  *(_QWORD *)&v46 = 0;
  *(_QWORD *)&SourceString.Length = a4;
  DWORD2(v46) = 0;
  PoolWithTag = 0;
  LOWORD(v43) = 0;
  P = 0;
  Source = 0;
  *(_OWORD *)v44 = 0;
  v45 = 0;
  *(_OWORD *)v50 = 0;
  *(_OWORD *)v41 = 0;
  v42 = 0;
  if ( !a1 || !a3 || !a2 )
    return 3221225485LL;
  *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v7 = FltParseFileNameInformation(a2);
  appended = v7;
  if ( v7 >= 0 )
  {
    _mm_lfence();
    Length = a2->Share.Length;
    if ( !Length )
    {
      appended = -1073741811;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_qZd(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          (unsigned int)WPP_7bbc5b2225a837977031aba3c9eddf35_Traceguids,
          (unsigned int)KeGetCurrentThread(),
          (__int64)&a2->Name,
          13);
      goto LABEL_74;
    }
    v11 = a2->Volume.Length + a2->ParentDir.Length;
    Source.Buffer = a2->Name.Buffer;
    Source.MaximumLength = a2->Name.MaximumLength;
    v43 = 0;
    *(_OWORD *)v41 = 0;
    LOWORD(v41[0]) = 40;
    Source.Length = Length + v11;
    v42 = 0;
    v12 = *(__int64 (__fastcall **)(_QWORD))(MpData + 192);
    if ( v12 && (v13 = v12(*(_QWORD *)(a1 + 32))) != 0 )
      v43 = *(_QWORD *)(v13 + 8);
    else
      v43 = 0;
    v14 = *(_QWORD *)(a1 + 24);
    LODWORD(v44[0]) = 48;
    v44[1] = 0;
    DWORD2(v45) = 576;
    *(_QWORD *)&v45 = &Source;
    v46 = 0;
    v15 = *(_QWORD *)(MpData + 16);
    if ( (*(_DWORD *)(MpData + 864) & 0x40) != 0 )
      FileEx2 = MpFltCreateFileEx2(
                  v15,
                  v14,
                  (int)&FileHandle,
                  (int)&FileObject,
                  9u,
                  (__int64)v44,
                  (__int64)v50,
                  RestartScan,
                  LengthReturned,
                  7u,
                  v32,
                  0,
                  v33,
                  v34,
                  0,
                  (__int64)v41);
    else
      FileEx2 = MpFltCreateFileEx(
                  v15,
                  v14,
                  (int)&FileHandle,
                  (int)&FileObject,
                  9u,
                  (__int64)v44,
                  (__int64)v50,
                  RestartScan,
                  0,
                  7u,
                  1u,
                  0,
                  v33,
                  v34,
                  0);
    appended = FileEx2;
    if ( FileEx2 >= 0 )
    {
      appended = MpQueryLoopbackEa(a1, FileObject, &P);
      if ( appended >= 0 )
      {
        _mm_lfence();
        if ( a2->FinalComponent.Length && RtlIsNameLegalDOS8Dot3(&a2->FinalComponent, 0, 0) )
        {
          LODWORD(v17) = 538;
          do
          {
            v47[0] = 0;
            if ( PoolWithTag )
            {
              ExFreePoolWithTag(PoolWithTag, 0x6E73504Du);
              PoolWithTag = 0;
              v17 = 2LL * (unsigned int)v17;
              if ( v17 > 0xFFFFFFFF )
              {
                appended = -1073741675;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
                {
                  v22 = 17;
                  FileInformationClassa = -1073741675;
                  goto LABEL_53;
                }
                goto LABEL_74;
              }
            }
            PoolWithTag = (USHORT *)MpAllocatePoolWithTag(1, (unsigned int)v17, 1853050957);
            if ( !PoolWithTag )
            {
              appended = -1073741670;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                v22 = 18;
                FileInformationClassa = -1073741670;
                goto LABEL_54;
              }
              goto LABEL_74;
            }
            DirectoryFile = FltQueryDirectoryFile(
                              *(PFLT_INSTANCE *)(a1 + 24),
                              FileObject,
                              PoolWithTag,
                              v17,
                              FileNamesInformation,
                              1u,
                              &a2->FinalComponent,
                              1u,
                              v47);
          }
          while ( DirectoryFile == -2147483643 || DirectoryFile == -1073741789 );
          if ( DirectoryFile < 0 )
          {
            if ( DirectoryFile != -1073741809
              && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
            {
              _mm_lfence();
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                19,
                WPP_7bbc5b2225a837977031aba3c9eddf35_Traceguids,
                KeGetCurrentThread(),
                DirectoryFile);
            }
            goto LABEL_44;
          }
          if ( !*((_DWORD *)PoolWithTag + 2) )
            goto LABEL_44;
          Source.Length = PoolWithTag[4];
          Source.MaximumLength = PoolWithTag[4];
          Buffer = PoolWithTag + 6;
        }
        else
        {
LABEL_44:
          Source.Length = a2->FinalComponent.Length;
          Source.MaximumLength = Source.Length;
          Buffer = a2->FinalComponent.Buffer;
        }
        v20 = (char *)P;
        Source.Buffer = Buffer;
        v21 = *((unsigned __int8 *)P + 5);
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, (PCWSTR)((char *)P + v21 + 21));
        appended = MpAllocateString((unsigned __int16)(Source.Length + DestinationString.Length + 2), &Destination);
        if ( appended >= 0 )
        {
          RtlCopyUnicodeString(Destination, &DestinationString);
          appended = RtlAppendUnicodeToString(Destination, L"\\");
          if ( appended >= 0 )
          {
            appended = RtlAppendUnicodeStringToString(Destination, &Source);
            if ( appended >= 0 )
            {
              v23 = Destination;
              v24 = *(_QWORD *)&SourceString.Length;
              Destination = 0;
              *v37 = v23;
              if ( v24 )
              {
                v25 = *(_WORD *)&v20[v21 + 17];
                SourceString = DestinationString;
                SourceString.Length = v25;
                v26 = MpDuplicateString(&SourceString);
                if ( v26 < 0
                  && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
                {
                  _mm_lfence();
                  WPP_SF_qD(
                    WPP_GLOBAL_Control->AttachedDevice,
                    23,
                    WPP_7bbc5b2225a837977031aba3c9eddf35_Traceguids,
                    KeGetCurrentThread(),
                    v26);
                }
              }
              appended = 0;
              goto LABEL_74;
            }
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
LABEL_74:
              if ( P )
                ExFreePoolWithTag(P, 0x6165504Du);
              if ( Destination )
                MpFreeString(Destination);
              if ( PoolWithTag )
                ExFreePoolWithTag(PoolWithTag, 0x6E73504Du);
              goto LABEL_80;
            }
            v22 = 22;
          }
          else
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
              goto LABEL_74;
            }
            v22 = 21;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_74;
          }
          v22 = 20;
        }
        FileInformationClassa = appended;
LABEL_53:
        _mm_lfence();
LABEL_54:
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          v22,
          WPP_7bbc5b2225a837977031aba3c9eddf35_Traceguids,
          KeGetCurrentThread(),
          FileInformationClassa);
        goto LABEL_74;
      }
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_74;
      v9 = 16;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_74;
      v9 = 15;
    }
    FileInformationClass = appended;
LABEL_10:
    _mm_lfence();
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      v9,
      WPP_7bbc5b2225a837977031aba3c9eddf35_Traceguids,
      KeGetCurrentThread(),
      FileInformationClass);
    goto LABEL_74;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v9 = 13;
    FileInformationClass = v7;
    goto LABEL_10;
  }
LABEL_80:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObject )
  {
    ObfDereferenceObject(FileObject);
    if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
    {
      if ( KdRefreshDebuggerNotPresent() )
        KeBugCheck(1u);
      __debugbreak();
    }
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140088da4  push    rbp
0x140088da6  push    rbx
0x140088da7  push    rsi
0x140088da8  push    rdi
0x140088da9  push    r12
0x140088dab  push    r13
0x140088dad  push    r14
0x140088daf  push    r15
0x140088db1  lea     rbp, [rsp-68h]
0x140088db6  sub     rsp, 168h
0x140088dbd  mov     rax, cs:__security_cookie
0x140088dc4  xor     rax, rsp
0x140088dc7  mov     [rbp+0A0h+var_50], rax
0x140088dcb  xor     r14d, r14d
0x140088dce  mov     [rbp+0A0h+var_110], r8
0x140088dd2  xorps   xmm0, xmm0
0x140088dd5  mov     [rbp+0A0h+FileHandle], r14
0x140088dd9  mov     r13, rcx
0x140088ddc  mov     [rbp+0A0h+FileObject], r14
0x140088de0  xor     ecx, ecx
0x140088de2  mov     [rbp+0A0h+Destination], r14
0x140088de6  mov     qword ptr [rbp+0A0h+var_A0], rcx
0x140088dea  mov     rax, r9
0x140088ded  mov     qword ptr [rbp+0A0h+SourceString.Length], rax
0x140088df1  mov     rsi, rdx
0x140088df4  mov     dword ptr [rbp+0A0h+var_A0+8], ecx
0x140088df7  mov     r12d, r14d
0x140088dfa  mov     word ptr [rbp+0A0h+var_C8], cx
0x140088dfe  mov     [rbp+0A0h+P], r14
0x140088e02  movups  xmmword ptr [rbp+0A0h+Source.Length], xmm0
0x140088e06  movups  xmmword ptr [rbp+0A0h+var_C0], xmm0
0x140088e0a  movups  [rbp+0A0h+var_B0], xmm0
0x140088e0e  movups  xmmword ptr [rbp+0A0h+var_60], xmm0
0x140088e12  movups  xmmword ptr [rbp+0A0h+var_E8], xmm0
0x140088e16  movups  [rbp+0A0h+var_D8], xmm0
0x140088e1a  test    r13, r13
0x140088e1d  jz      loc_1400894EC
0x140088e23  test    r8, r8
0x140088e26  jz      loc_1400894EC
0x140088e2c  test    rdx, rdx
0x140088e2f  jz      loc_1400894EC
0x140088e35  mov     [r8], r14
0x140088e38  test    rax, rax
0x140088e3b  jz      short loc_140088E40
0x140088e3d  mov     [r9], r14
0x140088e40  mov     rcx, rsi; FileNameInformation
0x140088e43  call    cs:__imp_FltParseFileNameInformation
0x140088e4a  nop     dword ptr [rax+rax+00h]
0x140088e4f  mov     ebx, eax
0x140088e51  test    eax, eax
0x140088e53  jns     short loc_140088EA9
0x140088e55  mov     rcx, cs:WPP_GLOBAL_Control
0x140088e5c  lea     rdi, WPP_GLOBAL_Control
0x140088e63  cmp     rcx, rdi
0x140088e66  jz      loc_140089477
0x140088e6c  mov     ecx, [rcx+2Ch]
0x140088e6f  test    cl, 1
0x140088e72  jz      loc_140089477
0x140088e78  mov     edx, 0Dh
0x140088e7d  mov     [rsp+1A0h+FileInformationClass], eax
0x140088e81  lfence
0x140088e84  mov     r9, gs:188h
0x140088e8d  lea     r8, WPP_7bbc5b2225a837977031aba3c9eddf35_Traceguids
0x140088e94  mov     rcx, cs:WPP_GLOBAL_Control
0x140088e9b  mov     rcx, [rcx+18h]
0x140088e9f  call    WPP_SF_qD
0x140088ea4  jmp     loc_140089430
0x140088ea9  lfence
0x140088eac  movzx   edx, word ptr [rsi+28h]
0x140088eb0  cmp     r14w, dx
0x140088eb4  jnz     short loc_140088F18
0x140088eb6  mov     ebx, 0C000000Dh
0x140088ebb  mov     rax, cs:WPP_GLOBAL_Control
0x140088ec2  lea     rdi, WPP_GLOBAL_Control
0x140088ec9  cmp     rax, rdi
0x140088ecc  jz      loc_140089430
0x140088ed2  mov     eax, [rax+2Ch]
0x140088ed5  test    al, 1
0x140088ed7  jz      loc_140089430
0x140088edd  mov     r9, gs:188h
0x140088ee6  lea     rax, [rsi+8]
0x140088eea  mov     rcx, cs:WPP_GLOBAL_Control
0x140088ef1  lea     r8, WPP_7bbc5b2225a837977031aba3c9eddf35_Traceguids
0x140088ef8  mov     edx, 0Eh
0x140088efd  mov     dword ptr [rsp+1A0h+ReturnSingleEntry], 0C000000Dh
0x140088f05  mov     qword ptr [rsp+1A0h+FileInformationClass], rax
0x140088f0a  mov     rcx, [rcx+18h]
0x140088f0e  call    WPP_SF_qZd
0x140088f13  jmp     loc_140089430
0x140088f18  mov     rax, [rsi+10h]
0x140088f1c  xorps   xmm0, xmm0
0x140088f1f  movzx   ecx, word ptr [rsi+68h]
0x140088f23  add     cx, [rsi+18h]
0x140088f27  mov     [rbp+0A0h+Source.Buffer], rax
0x140088f2b  add     cx, dx
0x140088f2e  movzx   eax, word ptr [rsi+0Ah]
0x140088f32  mov     [rbp+0A0h+Source.MaximumLength], ax
0x140088f36  xor     eax, eax
0x140088f38  mov     [rbp+0A0h+var_C8], rax
0x140088f3c  mov     eax, 28h ; '('
0x140088f41  movups  xmmword ptr [rbp+0A0h+var_E8], xmm0
0x140088f45  mov     word ptr [rbp+0A0h+var_E8], ax
0x140088f49  mov     rax, cs:MpData
0x140088f50  mov     [rbp+0A0h+Source.Length], cx
0x140088f54  movups  [rbp+0A0h+var_D8], xmm0
0x140088f58  mov     rax, [rax+0C0h]
0x140088f5f  test    rax, rax
0x140088f62  jz      short loc_140088F7D
0x140088f64  mov     rcx, [r13+20h]
0x140088f68  call    cs:__guard_dispatch_icall_fptr
0x140088f6e  test    rax, rax
0x140088f71  jz      short loc_140088F7D
0x140088f73  mov     rax, [rax+8]
0x140088f77  mov     [rbp+0A0h+var_C8], rax
0x140088f7b  jmp     short loc_140088F81
0x140088f7d  mov     [rbp+0A0h+var_C8], r14
0x140088f81  mov     rcx, cs:MpData
0x140088f88  lea     rax, [rbp+0A0h+Source]
0x140088f8c  mov     rdx, [r13+18h]; int
0x140088f90  lea     r9, [rbp+0A0h+FileObject]; int
0x140088f94  mov     dword ptr [rbp+0A0h+var_C0], 30h ; '0'
0x140088f9b  lea     r8, [rbp+0A0h+FileHandle]; int
0x140088f9f  mov     [rbp+0A0h+var_C0+8], r14
0x140088fa3  xorps   xmm0, xmm0
0x140088fa6  mov     dword ptr [rbp+0A0h+var_B0+8], 240h
0x140088fad  mov     qword ptr [rbp+0A0h+var_B0], rax
0x140088fb1  movdqu  [rbp+0A0h+var_A0], xmm0
0x140088fb6  mov     eax, [rcx+360h]
0x140088fbc  mov     rcx, [rcx+10h]; int
0x140088fc0  test    al, 40h
0x140088fc2  jz      short loc_140089000
0x140088fc4  lea     rax, [rbp+0A0h+var_E8]
0x140088fc8  mov     [rsp+1A0h+var_128], rax; __int64
0x140088fcd  lea     rax, [rbp+0A0h+var_60]
0x140088fd1  mov     [rsp+1A0h+var_130], r14d; ULONG
0x140088fd6  mov     [rsp+1A0h+var_148], r14d; ULONG
0x140088fdb  mov     [rsp+1A0h+var_158], 7; ULONG
0x140088fe3  mov     [rsp+1A0h+FileName], rax; __int64
0x140088fe8  lea     rax, [rbp+0A0h+var_C0]
0x140088fec  mov     qword ptr [rsp+1A0h+ReturnSingleEntry], rax; __int64
0x140088ff1  mov     [rsp+1A0h+FileInformationClass], 9; ACCESS_MASK
0x140088ff9  call    MpFltCreateFileEx2
0x140088ffe  jmp     short loc_14008903E
0x140089000  mov     [rsp+1A0h+var_130], r14d; ULONG
0x140089005  lea     rax, [rbp+0A0h+var_60]
0x140089009  mov     [rsp+1A0h+var_148], r14d; ULONG
0x14008900e  mov     [rsp+1A0h+var_150], 1; ULONG
0x140089016  mov     [rsp+1A0h+var_158], 7; ULONG
0x14008901e  mov     dword ptr [rsp+1A0h+LengthReturned], r14d; ULONG
0x140089023  mov     [rsp+1A0h+FileName], rax; __int64
0x140089028  lea     rax, [rbp+0A0h+var_C0]
0x14008902c  mov     qword ptr [rsp+1A0h+ReturnSingleEntry], rax; __int64
0x140089031  mov     [rsp+1A0h+FileInformationClass], 9; ACCESS_MASK
0x140089039  call    MpFltCreateFileEx
0x14008903e  mov     ebx, eax
0x140089040  test    eax, eax
0x140089042  jns     short loc_140089074
0x140089044  mov     rax, cs:WPP_GLOBAL_Control
0x14008904b  lea     rdi, WPP_GLOBAL_Control
0x140089052  cmp     rax, rdi
0x140089055  jz      loc_140089430
0x14008905b  mov     eax, [rax+2Ch]
0x14008905e  test    al, 1
0x140089060  jz      loc_140089430
0x140089066  mov     edx, 0Fh
0x14008906b  mov     [rsp+1A0h+FileInformationClass], ebx
0x14008906f  jmp     loc_140088E81
0x140089074  mov     rdx, [rbp+0A0h+FileObject]
0x140089078  lea     r8, [rbp+0A0h+P]
0x14008907c  mov     rcx, r13
0x14008907f  call    MpQueryLoopbackEa
0x140089084  mov     ebx, eax
0x140089086  test    eax, eax
0x140089088  jns     short loc_1400890B3
0x14008908a  mov     rax, cs:WPP_GLOBAL_Control
0x140089091  lea     rdi, WPP_GLOBAL_Control
0x140089098  cmp     rax, rdi
0x14008909b  jz      loc_140089430
0x1400890a1  mov     eax, [rax+2Ch]
0x1400890a4  test    al, 1
0x1400890a6  jz      loc_140089430
0x1400890ac  mov     edx, 10h
0x1400890b1  jmp     short loc_14008906B
0x1400890b3  lfence
0x1400890b6  lea     r15, [rsi+58h]
0x1400890ba  lea     rdi, WPP_GLOBAL_Control
0x1400890c1  cmp     [r15], r14w
0x1400890c5  jz      loc_1400891E8
0x1400890cb  xor     r8d, r8d; NameContainsSpaces
0x1400890ce  xor     edx, edx; OemName
0x1400890d0  mov     rcx, r15; Name
0x1400890d3  call    cs:__imp_RtlIsNameLegalDOS8Dot3
0x1400890da  nop     dword ptr [rax+rax+00h]
0x1400890df  test    al, al
0x1400890e1  jz      loc_1400891E8
0x1400890e7  mov     r14d, 21Ah
0x1400890ed  mov     [rbp+0A0h+var_90], 0
0x1400890f4  test    r12, r12
0x1400890f7  jz      short loc_140089124
0x1400890f9  mov     edx, 6E73504Dh; Tag
0x1400890fe  mov     rcx, r12; P
0x140089101  call    cs:__imp_ExFreePoolWithTag
0x140089108  nop     dword ptr [rax+rax+00h]
0x14008910d  mov     r14d, r14d
0x140089110  xor     r12d, r12d
0x140089113  add     r14, r14
0x140089116  mov     eax, 0FFFFFFFFh
0x14008911b  cmp     r14, rax
0x14008911e  ja      loc_140089268
0x140089124  mov     edx, r14d
0x140089127  mov     ecx, 1
0x14008912c  mov     r8d, 6E73504Dh
0x140089132  call    MpAllocatePoolWithTag
0x140089137  mov     r12, rax
0x14008913a  mov     rbx, rax
0x14008913d  test    rax, rax
0x140089140  jz      loc_1400892E7
0x140089146  mov     rdx, [rbp+0A0h+FileObject]; FileObject
0x14008914a  lea     rax, [rbp+0A0h+var_90]
0x14008914e  mov     rcx, [r13+18h]; Instance
0x140089152  mov     r9d, r14d; Length
0x140089155  mov     [rsp+1A0h+LengthReturned], rax; LengthReturned
0x14008915a  mov     r8, rbx; FileInformation
0x14008915d  mov     [rsp+1A0h+RestartScan], 1; RestartScan
0x140089162  mov     [rsp+1A0h+FileName], r15; FileName
0x140089167  mov     [rsp+1A0h+ReturnSingleEntry], 1; ReturnSingleEntry
0x14008916c  mov     [rsp+1A0h+FileInformationClass], 0Ch; FileInformationClass
0x140089174  call    cs:__imp_FltQueryDirectoryFile
0x14008917b  nop     dword ptr [rax+rax+00h]
0x140089180  mov     ecx, eax
0x140089182  cmp     eax, 80000005h
0x140089187  jz      loc_1400890ED
0x14008918d  cmp     eax, 0C0000023h
0x140089192  jz      loc_1400890ED
0x140089198  xor     r14d, r14d
0x14008919b  test    eax, eax
0x14008919d  jns     loc_1400892C4
0x1400891a3  cmp     eax, 0C000000Fh
0x1400891a8  jz      short loc_1400891E8
0x1400891aa  mov     rax, cs:WPP_GLOBAL_Control
0x1400891b1  cmp     rax, rdi
0x1400891b4  jz      short loc_1400891E8
0x1400891b6  mov     eax, [rax+2Ch]
0x1400891b9  test    al, 2
0x1400891bb  jz      short loc_1400891E8
0x1400891bd  lfence
0x1400891c0  mov     r9, gs:188h
0x1400891c9  lea     edx, [r14+13h]
0x1400891cd  mov     [rsp+1A0h+FileInformationClass], ecx
0x1400891d1  lea     r8, WPP_7bbc5b2225a837977031aba3c9eddf35_Traceguids
0x1400891d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400891df  mov     rcx, [rcx+18h]
0x1400891e3  call    WPP_SF_qD
0x1400891e8  movzx   eax, word ptr [r15]
0x1400891ec  mov     [rbp+0A0h+Source.Length], ax
0x1400891f0  mov     [rbp+0A0h+Source.MaximumLength], ax
0x1400891f4  mov     rax, [rsi+60h]
0x1400891f8  mov     r14, [rbp+0A0h+P]
0x1400891fc  lea     rcx, [rbp+0A0h+DestinationString]; DestinationString
0x140089200  mov     [rbp+0A0h+Source.Buffer], rax
0x140089204  xorps   xmm0, xmm0
0x140089207  movzx   r15d, byte ptr [r14+5]
0x14008920c  lea     rdx, [r14+15h]
0x140089210  add     rdx, r15; SourceString
0x140089213  movups  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm0
0x140089217  call    cs:__imp_RtlInitUnicodeString
0x14008921e  nop     dword ptr [rax+rax+00h]
0x140089223  movzx   ecx, [rbp+0A0h+DestinationString.Length]
0x140089227  lea     rdx, [rbp+0A0h+Destination]
0x14008922b  add     cx, 2
0x14008922f  add     cx, [rbp+0A0h+Source.Length]
0x140089233  call    MpAllocateString
0x140089238  mov     ebx, eax
0x14008923a  test    eax, eax
0x14008923c  jns     loc_14008931D
0x140089242  mov     rax, cs:WPP_GLOBAL_Control
0x140089249  cmp     rax, rdi
0x14008924c  jz      loc_140089430
0x140089252  mov     eax, [rax+2Ch]
0x140089255  test    al, 1
0x140089257  jz      loc_140089430
0x14008925d  mov     edx, 14h
0x140089262  mov     [rsp+1A0h+FileInformationClass], ebx
0x140089266  jmp     short loc_14008929C
0x140089268  mov     ebx, 0C0000095h
0x14008926d  mov     rax, cs:WPP_GLOBAL_Control
0x140089274  lea     rdi, WPP_GLOBAL_Control
0x14008927b  cmp     rax, rdi
0x14008927e  jz      loc_140089430
0x140089284  mov     eax, [rax+2Ch]
0x140089287  test    al, 1
0x140089289  jz      loc_140089430
0x14008928f  mov     edx, 11h
0x140089294  mov     [rsp+1A0h+FileInformationClass], 0C0000095h
0x14008929c  lfence
0x14008929f  mov     r9, gs:188h
0x1400892a8  lea     r8, WPP_7bbc5b2225a837977031aba3c9eddf35_Traceguids
0x1400892af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400892b6  mov     rcx, [rcx+18h]
0x1400892ba  call    WPP_SF_qD
  ... truncated ...
```
