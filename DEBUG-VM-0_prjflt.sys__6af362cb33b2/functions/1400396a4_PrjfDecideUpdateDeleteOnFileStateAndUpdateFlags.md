# PrjfDecideUpdateDeleteOnFileStateAndUpdateFlags

- ea: `0x1400396a4`
- end: `0x140039de0`
- name: `PrjfDecideUpdateDeleteOnFileStateAndUpdateFlags`
- size: `1852`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14002f5f0`
- `0x140035238`

## callees

- `0x140002f3c`
- `0x14000b1d0`
- `0x14000d754`
- `0x140010360`
- `0x1400122d4`
- `0x1400396a4`
- `0x14003be88`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140039c5c`
- `ntoskrnl!ObfDereferenceObject` at `0x140039c5c`
- `FLTMGR!FltCreateFileEx2` at `0x14003997f`
- `FLTMGR!FltCreateFileEx2` at `0x14003997f`
- `FLTMGR!FltClose` at `0x140039c47`
- `FLTMGR!FltClose` at `0x140039c47`
- `FLTMGR!FltReleaseContext` at `0x140039c70`
- `FLTMGR!FltReleaseContext` at `0x140039c85`
- `FLTMGR!FltReleaseContext` at `0x140039c70`
- `FLTMGR!FltReleaseContext` at `0x140039c85`

## pseudocode

```c
__int64 __fastcall PrjfDecideUpdateDeleteOnFileStateAndUpdateFlags(
        struct _FLT_INSTANCE *a1,
        char a2,
        struct _UNICODE_STRING *a3,
        _QWORD *a4,
        PFILE_OBJECT *a5,
        _DWORD *a6,
        _BYTE *a7,
        _OWORD *a8,
        _BYTE *a9)
{
  _QWORD *v10; // r13
  int v11; // eax
  __int64 v12; // rcx
  int v13; // r8d
  unsigned int v14; // ebx
  __int64 *v15; // rdx
  NTSTATUS v16; // eax
  int v17; // edx
  char v18; // cl
  int SetContextFileObject; // eax
  int v20; // edx
  __int64 v21; // rcx
  int v22; // r8d
  __int64 v23; // rcx
  __int64 v24; // rdi
  _OWORD *v25; // rax
  _OWORD *v26; // rcx
  __int128 v27; // xmm1
  void *v28; // rax
  PFILE_OBJECT v29; // rax
  PFLT_CONTEXT v30; // rcx
  __int64 DesiredAccess; // [rsp+28h] [rbp-C9h]
  char v33; // [rsp+88h] [rbp-69h] BYREF
  char v34; // [rsp+89h] [rbp-68h] BYREF
  char v35; // [rsp+8Ah] [rbp-67h] BYREF
  _BYTE v36[5]; // [rsp+8Bh] [rbp-66h] BYREF
  PFILE_OBJECT FileObject; // [rsp+90h] [rbp-61h] BYREF
  void *FileHandle; // [rsp+98h] [rbp-59h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-51h] BYREF
  int v40; // [rsp+A8h] [rbp-49h] BYREF
  PFLT_CONTEXT Context; // [rsp+B0h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E8h] [rbp-9h] BYREF

  *a4 = 0;
  v33 = 0;
  v34 = 0;
  *a6 = 0;
  v10 = 0;
  v39 = 0;
  Context = 0;
  FileHandle = 0;
  *a5 = 0;
  FileObject = 0;
  v40 = 0x80000000;
  *a9 = 0;
  v11 = PrjfOpenAsReparsePoint(
          (__int64)a3,
          0,
          a1,
          65920,
          DesiredAccess,
          &FileHandle,
          &FileObject,
          &v33,
          v36,
          &v35,
          &v34,
          &v40);
  v14 = v11;
  v15 = WPP_f518d8db80f83e9c1a62003295e898de_Traceguids;
  if ( v11 < 0 )
  {
    if ( v11 == -1073741183 )
    {
      v14 = -1073741766;
      if ( (BYTE1(xmmword_14001A3E0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = BYTE1(xmmword_14001A3E0) & 0x40;
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZd(1038, (_DWORD)v15, v13, *((_QWORD *)WPP_GLOBAL_Control + 8), 4, 14, 157);
      }
      goto LABEL_48;
    }
    if ( v11 != -1073741191 )
    {
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = BYTE1(xmmword_14001A3D0) & 0x40;
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          526,
          (_DWORD)v15,
          v13,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          14,
          158,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          170,
          v11,
          (__int64)a3);
      }
      goto LABEL_48;
    }
    if ( v33 || v34 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v12);
      v15 = WPP_f518d8db80f83e9c1a62003295e898de_Traceguids;
    }
    if ( (BYTE9(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v15) = BYTE9(xmmword_14001A3D0) & 0x40;
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDdZ(
        782,
        (_DWORD)v15,
        v13,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        3,
        14,
        159,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        188,
        121,
        (__int64)a3);
    }
    *(_QWORD *)&ObjectAttributes.Length = 48;
    *(_QWORD *)&ObjectAttributes.Attributes = 576;
    IoStatusBlock = 0;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = a3;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v16 = FltCreateFileEx2(
            Globals,
            a1,
            &FileHandle,
            &FileObject,
            0x10180u,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            0,
            3u,
            1u,
            0x200028u,
            0,
            0,
            1u,
            0);
    v14 = v16;
    if ( v16 < 0 )
    {
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v17) = BYTE1(xmmword_14001A3D0) & 0x40;
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          526,
          v17,
          v13,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          14,
          160,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          224,
          v16,
          (__int64)a3);
      }
      goto LABEL_48;
    }
    v15 = WPP_f518d8db80f83e9c1a62003295e898de_Traceguids;
  }
  v18 = v33;
  if ( v33 )
  {
    SetContextFileObject = PrjfGetSetContextFileObject(a1, FileObject, 0x80000000, 0, 0, 0, 0, &v39, &Context);
    v14 = SetContextFileObject;
    if ( SetContextFileObject < 0 )
    {
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v20) = BYTE1(xmmword_14001A3D0) & 0x40;
        LOBYTE(v22) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          526,
          v20,
          v22,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          14,
          161,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          10,
          SetContextFileObject,
          (__int64)a3);
      }
      v10 = (_QWORD *)v39;
      goto LABEL_48;
    }
    v10 = (_QWORD *)v39;
    if ( !v39 || *(_DWORD *)(v39 + 64) == 3 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v21);
    v23 = v10[9];
    if ( !v23 )
    {
      v14 = -1073741790;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v20) = BYTE1(xmmword_14001A3D0) & 0x40;
        LOBYTE(v22) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          526,
          v20,
          v22,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          14,
          162,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          30,
          34,
          (__int64)a3);
      }
      goto LABEL_48;
    }
    v24 = 2;
    if ( (*(_DWORD *)(v23 + 12) & 2) != 0 && (a2 & 1) == 0 )
    {
      v14 = -1073689083;
      if ( (BYTE9(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v20) = BYTE9(xmmword_14001A3D0) & 0x40;
        LOBYTE(v22) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdDZ(
          782,
          v20,
          v22,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          3,
          14,
          163,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          46,
          5,
          a2,
          (__int64)a3);
      }
      *a6 = 1;
      goto LABEL_48;
    }
    v25 = a8;
    if ( a8 )
    {
      v26 = (_OWORD *)(v23 + 32);
      do
      {
        *v25 = *v26;
        v25[1] = v26[1];
        v25[2] = v26[2];
        v25[3] = v26[3];
        v25[4] = v26[4];
        v25[5] = v26[5];
        v25[6] = v26[6];
        v27 = v26[7];
        v26 += 8;
        v25[7] = v27;
        v25 += 8;
        --v24;
      }
      while ( v24 );
    }
    v18 = v33;
    goto LABEL_45;
  }
  if ( v34 )
  {
    if ( (a2 & 4) == 0 )
    {
      v14 = -1073689083;
      if ( (BYTE9(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = BYTE9(xmmword_14001A3D0) & 0x40;
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdDZ(
          782,
          (_DWORD)v15,
          v13,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          3,
          14,
          164,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          69,
          5,
          a2,
          (__int64)a3);
      }
      *a6 = 4;
      goto LABEL_48;
    }
    *a9 = 1;
LABEL_45:
    if ( a7 )
      *a7 = v18;
    v28 = FileHandle;
    FileHandle = 0;
    *a4 = v28;
    v29 = FileObject;
    FileObject = 0;
    *a5 = v29;
    goto LABEL_48;
  }
  if ( (a2 & 2) != 0 )
    goto LABEL_45;
  v14 = -1073689083;
  if ( (BYTE9(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v15) = BYTE9(xmmword_14001A3D0) & 0x40;
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDdDZ(
      782,
      (_DWORD)v15,
      v13,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      3,
      14,
      165,
      (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
      87,
      5,
      a2,
      (__int64)a3);
  }
  *a6 = 2;
LABEL_48:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( v10 )
    FltReleaseContext(v10);
  v30 = Context;
  if ( Context )
    FltReleaseContext(Context);
  if ( v14 == -1073741191 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v30);
  return v14;
}

```

## disassembly

```asm
0x1400396a4  mov     rax, rsp
0x1400396a7  mov     [rax+20h], r9
0x1400396ab  mov     [rax+10h], edx
0x1400396ae  mov     [rax+8], rcx
0x1400396b2  push    rbp
0x1400396b3  push    rbx
0x1400396b4  push    rdi
0x1400396b5  push    r12
0x1400396b7  push    r13
0x1400396b9  push    r14
0x1400396bb  push    r15
0x1400396bd  lea     rbp, [rax-3Fh]
0x1400396c1  sub     rsp, 0F0h
0x1400396c8  mov     rax, [rbp+37h+arg_28]
0x1400396cc  xor     edi, edi
0x1400396ce  mov     r12, r8
0x1400396d1  mov     [r9], rdi
0x1400396d4  mov     r8, rcx
0x1400396d7  mov     [rbp+37h+var_A0], dil
0x1400396db  mov     r9d, 10180h
0x1400396e1  mov     [rbp+37h+var_9F], dil
0x1400396e5  mov     [rax], edi
0x1400396e7  xor     edx, edx
0x1400396e9  mov     rax, [rbp+37h+arg_20]
0x1400396ed  mov     rcx, r12
0x1400396f0  mov     r13d, edi
0x1400396f3  mov     [rbp+37h+var_88], rdi
0x1400396f7  mov     [rbp+37h+Context], rdi
0x1400396fb  mov     [rbp+37h+FileHandle], rdi
0x1400396ff  mov     [rax], rdi
0x140039702  mov     rax, [rbp+37h+arg_40]
0x140039709  mov     [rbp+37h+FileObject], rdi
0x14003970d  mov     [rbp+37h+var_80], 80000000h
0x140039714  mov     [rax], dil
0x140039717  lea     rax, [rbp+37h+var_80]
0x14003971b  mov     qword ptr [rsp+120h+CreateOptions], rax
0x140039720  lea     rax, [rbp+37h+var_9F]
0x140039724  mov     qword ptr [rsp+120h+CreateDisposition], rax
0x140039729  lea     rax, [rbp+37h+var_9E]
0x14003972d  mov     qword ptr [rsp+120h+ShareAccess], rax
0x140039732  lea     rax, [rbp+37h+var_9D]
0x140039736  mov     qword ptr [rsp+120h+FileAttributes], rax
0x14003973b  lea     rax, [rbp+37h+var_A0]
0x14003973f  mov     [rsp+120h+AllocationSize], rax
0x140039744  lea     rax, [rbp+37h+FileObject]
0x140039748  mov     [rsp+120h+IoStatusBlock], rax
0x14003974d  lea     rax, [rbp+37h+FileHandle]
0x140039751  mov     [rsp+120h+ObjectAttributes], rax
0x140039756  call    PrjfOpenAsReparsePoint
0x14003975b  xor     r11d, r11d
0x14003975e  lea     r15d, [rdi+0Eh]
0x140039762  lea     r14, WPP_RECORDER_INITIALIZED
0x140039769  mov     ebx, eax
0x14003976b  lea     rdi, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140039772  lea     rdx, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140039779  test    eax, eax
0x14003977b  jns     loc_1400399E8
0x140039781  mov     r9d, 0C0000281h
0x140039787  cmp     eax, r9d
0x14003978a  jnz     short loc_1400397F8
0x14003978c  mov     ebx, 0C000003Ah
0x140039791  mov     dl, byte ptr cs:xmmword_14001A3E0+1
0x140039797  lea     r14, WPP_RECORDER_INITIALIZED
0x14003979e  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400397a5  setnz   r8b
0x1400397a9  and     dl, 40h
0x1400397ac  jnz     short loc_1400397B7
0x1400397ae  test    r8b, r8b
0x1400397b1  jz      loc_140039C3E
0x1400397b7  mov     dword ptr [rsp+120h+EaBuffer], r9d
0x1400397bc  mov     ecx, 40Eh
0x1400397c1  mov     r9, cs:WPP_GLOBAL_Control
0x1400397c8  mov     qword ptr [rsp+120h+CreateOptions], r12
0x1400397cd  mov     [rsp+120h+CreateDisposition], ebx
0x1400397d1  mov     [rsp+120h+ShareAccess], 19A0h
0x1400397d9  mov     r9, [r9+40h]
0x1400397dd  mov     word ptr [rsp+120h+IoStatusBlock], 9Dh
0x1400397e4  mov     dword ptr [rsp+120h+ObjectAttributes], r15d
0x1400397e9  mov     byte ptr [rsp+120h+DesiredAccess], 4
0x1400397ee  call    WPP_RECORDER_AND_TRACE_SF_sDdZd
0x1400397f3  jmp     loc_140039C3E
0x1400397f8  cmp     eax, 0C0000279h
0x1400397fd  jz      short loc_140039879
0x1400397ff  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140039805  lea     r14, WPP_RECORDER_INITIALIZED
0x14003980c  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140039813  setnz   r8b
0x140039817  and     dl, 40h
0x14003981a  jnz     short loc_140039825
0x14003981c  test    r8b, r8b
0x14003981f  jz      loc_140039C3E
0x140039825  mov     qword ptr [rsp+120h+CreateOptions], r12
0x14003982a  mov     [rsp+120h+CreateDisposition], eax
0x14003982e  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140039835  mov     [rsp+120h+ShareAccess], 19AAh
0x14003983d  mov     qword ptr [rsp+120h+FileAttributes], rax
0x140039842  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140039849  mov     [rsp+120h+AllocationSize], rax
0x14003984e  mov     word ptr [rsp+120h+IoStatusBlock], 9Eh
0x140039855  mov     r9, cs:WPP_GLOBAL_Control
0x14003985c  mov     ecx, 20Eh
0x140039861  mov     dword ptr [rsp+120h+ObjectAttributes], r15d
0x140039866  mov     byte ptr [rsp+120h+DesiredAccess], 2
0x14003986b  mov     r9, [r9+40h]
0x14003986f  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140039874  jmp     loc_140039C3E
0x140039879  cmp     [rbp+37h+var_A0], r11b
0x14003987d  jnz     short loc_140039885
0x14003987f  cmp     [rbp+37h+var_9F], r11b
0x140039883  jz      short loc_140039894
0x140039885  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003988a  lea     rdx, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140039891  xor     r11d, r11d
0x140039894  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14003989b  mov     al, byte ptr cs:xmmword_14001A3D0+9
0x1400398a1  setnz   r8b
0x1400398a5  and     al, 40h
0x1400398a7  jnz     short loc_1400398AE
0x1400398a9  test    r8b, r8b
0x1400398ac  jz      short loc_1400398F8
0x1400398ae  mov     r9, cs:WPP_GLOBAL_Control
0x1400398b5  mov     ecx, 30Eh
0x1400398ba  mov     qword ptr [rsp+120h+CreateOptions], r12
0x1400398bf  mov     [rsp+120h+CreateDisposition], 0C0000279h
0x1400398c7  mov     [rsp+120h+ShareAccess], 19BCh
0x1400398cf  mov     r9, [r9+40h]
0x1400398d3  mov     qword ptr [rsp+120h+FileAttributes], rdi
0x1400398d8  mov     [rsp+120h+AllocationSize], rdx
0x1400398dd  mov     dl, al
0x1400398df  mov     word ptr [rsp+120h+IoStatusBlock], 9Fh
0x1400398e6  mov     dword ptr [rsp+120h+ObjectAttributes], r15d
0x1400398eb  mov     byte ptr [rsp+120h+DesiredAccess], 3
0x1400398f0  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x1400398f5  xor     r11d, r11d
0x1400398f8  mov     rdx, [rbp+37h+Instance]; Instance
0x1400398fc  lea     r9, [rbp+37h+FileObject]; FileObject
0x140039900  mov     rcx, cs:Globals; Filter
0x140039907  lea     r8, [rbp+37h+FileHandle]; FileHandle
0x14003990b  mov     [rsp+78h], r11; DriverContext
0x140039910  mov     eax, 1
0x140039915  mov     [rsp+120h+Flags], eax; Flags
0x140039919  xorps   xmm0, xmm0
0x14003991c  mov     [rsp+120h+EaLength], r11d; EaLength
0x140039921  mov     [rsp+120h+EaBuffer], r11; EaBuffer
0x140039926  mov     [rsp+120h+CreateOptions], 200028h; CreateOptions
0x14003992e  mov     [rsp+120h+CreateDisposition], eax; CreateDisposition
0x140039932  lea     rax, [rbp+37h+var_40]
0x140039936  mov     [rsp+120h+ShareAccess], 3; ShareAccess
0x14003993e  mov     [rsp+120h+FileAttributes], r11d; FileAttributes
0x140039943  mov     [rsp+120h+AllocationSize], r11; AllocationSize
0x140039948  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x14003994d  lea     rax, [rbp+37h+var_70]
0x140039951  mov     [rsp+120h+ObjectAttributes], rax; ObjectAttributes
0x140039956  mov     [rsp+120h+DesiredAccess], 10180h; DesiredAccess
0x14003995e  mov     qword ptr [rbp+37h+var_70.Length], 30h ; '0'
0x140039966  mov     qword ptr [rbp+37h+var_70.Attributes], 240h
0x14003996e  movups  xmmword ptr [rbp+37h+var_40], xmm0
0x140039972  mov     [rbp+37h+var_70.RootDirectory], r11
0x140039976  mov     [rbp+37h+var_70.ObjectName], r12
0x14003997a  movdqu  xmmword ptr [rbp+37h+var_70.SecurityDescriptor], xmm0
0x14003997f  call    cs:__imp_FltCreateFileEx2
0x140039986  nop     dword ptr [rax+rax+00h]
0x14003998b  xor     r11d, r11d
0x14003998e  mov     ebx, eax
0x140039990  test    eax, eax
0x140039992  jns     short loc_1400399E1
0x140039994  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14003999b  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400399a1  setnz   r8b
0x1400399a5  and     dl, 40h
0x1400399a8  jnz     short loc_1400399B3
0x1400399aa  test    r8b, r8b
0x1400399ad  jz      loc_140039C3E
0x1400399b3  mov     qword ptr [rsp+120h+CreateOptions], r12
0x1400399b8  mov     [rsp+120h+CreateDisposition], eax
0x1400399bc  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x1400399c3  mov     [rsp+120h+ShareAccess], 19E0h
0x1400399cb  mov     qword ptr [rsp+120h+FileAttributes], rdi
0x1400399d0  mov     [rsp+120h+AllocationSize], rax
0x1400399d5  mov     word ptr [rsp+120h+IoStatusBlock], 0A0h
0x1400399dc  jmp     loc_140039855
0x1400399e1  lea     rdx, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x1400399e8  mov     cl, [rbp+37h+var_A0]
0x1400399eb  test    cl, cl
0x1400399ed  jz      loc_140039CB4
0x1400399f3  mov     rdx, [rbp+37h+FileObject]; FileObject
0x1400399f7  lea     rax, [rbp+37h+Context]
0x1400399fb  mov     rcx, [rbp+37h+Instance]; Instance
0x1400399ff  xor     r9d, r9d
0x140039a02  mov     qword ptr [rsp+120h+FileAttributes], rax; __int64
0x140039a07  mov     r8d, 80000000h
0x140039a0d  lea     rax, [rbp+37h+var_88]
0x140039a11  mov     [rsp+120h+AllocationSize], rax; __int64
0x140039a16  mov     [rsp+120h+IoStatusBlock], r11; __int64
0x140039a1b  mov     [rsp+120h+ObjectAttributes], r11; __int64
0x140039a20  mov     byte ptr [rsp+120h+DesiredAccess], r11b; char
0x140039a25  call    PrjfGetSetContextFileObject
0x140039a2a  xor     r11d, r11d
0x140039a2d  mov     ebx, eax
0x140039a2f  test    eax, eax
0x140039a31  jns     short loc_140039A9F
0x140039a33  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140039a3a  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140039a40  setnz   r8b
0x140039a44  and     dl, 40h
0x140039a47  jnz     short loc_140039A4E
0x140039a49  test    r8b, r8b
0x140039a4c  jz      short loc_140039A96
0x140039a4e  mov     r9, cs:WPP_GLOBAL_Control
0x140039a55  mov     ecx, 20Eh
0x140039a5a  mov     qword ptr [rsp+120h+CreateOptions], r12
0x140039a5f  mov     [rsp+120h+CreateDisposition], eax
0x140039a63  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140039a6a  mov     [rsp+120h+ShareAccess], 1A0Ah
0x140039a72  mov     r9, [r9+40h]
0x140039a76  mov     qword ptr [rsp+120h+FileAttributes], rdi
0x140039a7b  mov     [rsp+120h+AllocationSize], rax
0x140039a80  mov     word ptr [rsp+120h+IoStatusBlock], 0A1h
0x140039a87  mov     dword ptr [rsp+120h+ObjectAttributes], r15d
0x140039a8c  mov     byte ptr [rsp+120h+DesiredAccess], 2
0x140039a91  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140039a96  mov     r13, [rbp+37h+var_88]
0x140039a9a  jmp     loc_140039C3E
0x140039a9f  mov     r13, [rbp+37h+var_88]
0x140039aa3  test    r13, r13
0x140039aa6  jz      short loc_140039AAF
0x140039aa8  cmp     dword ptr [r13+40h], 3
0x140039aad  jnz     short loc_140039AB7
0x140039aaf  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140039ab4  xor     r11d, r11d
0x140039ab7  mov     rcx, [r13+48h]
0x140039abb  test    rcx, rcx
0x140039abe  jnz     short loc_140039B12
0x140039ac0  mov     ebx, 0C0000022h
0x140039ac5  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140039acc  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140039ad2  setnz   r8b
0x140039ad6  and     dl, 40h
0x140039ad9  jnz     short loc_140039AE4
0x140039adb  test    r8b, r8b
0x140039ade  jz      loc_140039C3E
0x140039ae4  mov     qword ptr [rsp+120h+CreateOptions], r12
0x140039ae9  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140039af0  mov     [rsp+120h+CreateDisposition], ebx
0x140039af4  mov     [rsp+120h+ShareAccess], 1A1Eh
0x140039afc  mov     qword ptr [rsp+120h+FileAttributes], rdi
0x140039b01  mov     [rsp+120h+AllocationSize], rax
0x140039b06  mov     word ptr [rsp+120h+IoStatusBlock], 0A2h
0x140039b0d  jmp     loc_140039855
0x140039b12  mov     eax, [rcx+0Ch]
0x140039b15  mov     edi, 2
0x140039b1a  test    dil, al
0x140039b1d  jz      loc_140039BB6
0x140039b23  mov     r9d, [rbp+37h+arg_8]
0x140039b27  test    r9b, 1
0x140039b2b  jnz     loc_140039BB6
0x140039b31  mov     eax, 0C000CE05h
0x140039b36  mov     ebx, eax
0x140039b38  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140039b3f  mov     dl, byte ptr cs:xmmword_14001A3D0+9
0x140039b45  setnz   r8b
0x140039b49  and     dl, 40h
0x140039b4c  jnz     short loc_140039B53
0x140039b4e  test    r8b, r8b
0x140039b51  jz      short loc_140039BA7
0x140039b53  mov     [rsp+120h+EaBuffer], r12
0x140039b58  mov     ecx, 30Eh
0x140039b5d  mov     [rsp+120h+CreateOptions], r9d
0x140039b62  mov     r9, cs:WPP_GLOBAL_Control
0x140039b69  mov     [rsp+120h+CreateDisposition], eax
0x140039b6d  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140039b74  mov     [rsp+120h+ShareAccess], 1A2Eh
0x140039b7c  mov     qword ptr [rsp+120h+FileAttributes], rax
0x140039b81  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140039b88  mov     r9, [r9+40h]
0x140039b8c  mov     [rsp+120h+AllocationSize], rax
0x140039b91  mov     word ptr [rsp+120h+IoStatusBlock], 0A3h
0x140039b98  mov     dword ptr [rsp+120h+ObjectAttributes], r15d
0x140039b9d  mov     byte ptr [rsp+120h+DesiredAccess], 3
0x140039ba2  call    WPP_RECORDER_AND_TRACE_SF_sDdDZ
0x140039ba7  mov     rax, [rbp+37h+arg_28]
0x140039bab  mov     dword ptr [rax], 1
0x140039bb1  jmp     loc_140039C3E
0x140039bb6  mov     rax, [rbp+37h+arg_38]
0x140039bba  test    rax, rax
0x140039bbd  jz      short loc_140039C12
0x140039bbf  add     rcx, 20h ; ' '
0x140039bc3  mov     edx, 80h
0x140039bc8  movups  xmm0, xmmword ptr [rcx]
0x140039bcb  movups  xmmword ptr [rax], xmm0
0x140039bce  movups  xmm1, xmmword ptr [rcx+10h]
0x140039bd2  movups  xmmword ptr [rax+10h], xmm1
0x140039bd6  movups  xmm0, xmmword ptr [rcx+20h]
0x140039bda  movups  xmmword ptr [rax+20h], xmm0
0x140039bde  movups  xmm1, xmmword ptr [rcx+30h]
0x140039be2  movups  xmmword ptr [rax+30h], xmm1
0x140039be6  movups  xmm0, xmmword ptr [rcx+40h]
0x140039bea  movups  xmmword ptr [rax+40h], xmm0
0x140039bee  movups  xmm1, xmmword ptr [rcx+50h]
0x140039bf2  movups  xmmword ptr [rax+50h], xmm1
  ... truncated ...
```
