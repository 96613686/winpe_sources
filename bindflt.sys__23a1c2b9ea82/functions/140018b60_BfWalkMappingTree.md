# BfWalkMappingTree

- ea: `0x140018b60`
- end: `0x1400194a3`
- name: `BfWalkMappingTree`
- size: `2371`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140017f00`

## callees

- `0x140002e0c`
- `0x140004cc0`
- `0x140004fc0`
- `0x1400172f0`
- `0x140018b60`
- `0x140019bf0`
- `0x140019c20`
- `0x14001d130`
- `0x14002184c`
- `0x140022edc`

## import_xrefs

- `ntoskrnl!PsGetCurrentSilo` at `0x1400193ef`
- `ntoskrnl!PsGetCurrentSilo` at `0x1400193ef`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x140018eca`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x140018eca`
- `ntoskrnl!PsGetHostSilo` at `0x140019041`
- `ntoskrnl!PsGetHostSilo` at `0x140019144`
- `ntoskrnl!PsGetHostSilo` at `0x140019041`
- `ntoskrnl!PsGetHostSilo` at `0x140019144`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018f0a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018f0a`
- `ntoskrnl!ExAllocatePool2` at `0x140018d9f`
- `ntoskrnl!ExAllocatePool2` at `0x140018d9f`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140019492`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140019492`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140018cea`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140018cea`
- `ntoskrnl!ObfDereferenceObject` at `0x140018f79`
- `ntoskrnl!ObfDereferenceObject` at `0x140018f79`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140018dc8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140018fb7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140018dc8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140018fb7`
- `FLTMGR!FltAcquireResourceShared` at `0x140018d20`
- `FLTMGR!FltAcquireResourceShared` at `0x140018d20`
- `FLTMGR!FltCreateFileEx2` at `0x1400190ef`
- `FLTMGR!FltCreateFileEx2` at `0x1400191f0`
- `FLTMGR!FltCreateFileEx2` at `0x1400190ef`
- `FLTMGR!FltCreateFileEx2` at `0x1400191f0`
- `FLTMGR!FltClose` at `0x140018f6b`
- `FLTMGR!FltClose` at `0x140018f6b`
- `FLTMGR!FltSetStreamContext` at `0x14001932c`
- `FLTMGR!FltSetStreamContext` at `0x14001932c`
- `FLTMGR!FltGetStreamContext` at `0x140018c1c`
- `FLTMGR!FltGetStreamContext` at `0x140018c1c`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140019292`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140019292`
- `FLTMGR!FltReleaseContext` at `0x140018f47`
- `FLTMGR!FltReleaseContext` at `0x14001940b`
- `FLTMGR!FltReleaseContext` at `0x140019426`
- `FLTMGR!FltReleaseContext` at `0x140018f47`
- `FLTMGR!FltReleaseContext` at `0x14001940b`
- `FLTMGR!FltReleaseContext` at `0x140019426`
- `FLTMGR!FltReleaseResource` at `0x140018d63`
- `FLTMGR!FltReleaseResource` at `0x140018eda`
- `FLTMGR!FltReleaseResource` at `0x140018d63`
- `FLTMGR!FltReleaseResource` at `0x140018eda`

## pseudocode

```c
__int64 __fastcall BfWalkMappingTree(__int64 a1, __int64 a2)
{
  int v3; // ecx
  NTSTATUS appended; // r15d
  char *v6; // r12
  char *v7; // rsi
  struct _FLT_INSTANCE *v8; // rdi
  struct _FILE_OBJECT *v9; // rbx
  NTSTATUS StreamContext; // eax
  __int64 v11; // rdx
  _QWORD *v12; // rbx
  int v13; // eax
  char *v14; // rax
  _QWORD *v15; // rbx
  int v16; // eax
  __int64 v17; // r9
  unsigned __int16 v18; // di
  __int64 Pool2; // rax
  __int64 v20; // rcx
  _QWORD *v21; // rax
  __int64 v22; // r8
  int UnicodeString; // eax
  __int64 v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rcx
  __int64 *v29; // rbx
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rcx
  _QWORD *v33; // rax
  _QWORD *v34; // r14
  _QWORD *v35; // rbx
  _QWORD *v36; // rax
  int v37; // eax
  NTSTATUS v38; // eax
  PVOID Object; // [rsp+80h] [rbp-80h] BYREF
  HANDLE FileHandle; // [rsp+88h] [rbp-78h] BYREF
  PVOID P[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD *v42; // [rsp+A0h] [rbp-60h]
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+A8h] [rbp-58h] BYREF
  __int64 HostSilo; // [rsp+C8h] [rbp-38h]
  PFLT_CONTEXT OldContext; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v46; // [rsp+D8h] [rbp-28h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+E0h] [rbp-20h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int8 v50; // [rsp+178h] [rbp+78h]
  char *v51; // [rsp+180h] [rbp+80h]
  PFLT_CONTEXT Context; // [rsp+188h] [rbp+88h] BYREF

  FileHandle = 0;
  LOWORD(HostSilo) = 0;
  v3 = *(_DWORD *)(a1 - 8);
  Object = 0;
  appended = 0;
  v51 = 0;
  v6 = 0;
  v7 = 0;
  *(_OWORD *)P = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( (v3 & 2) != 0 || (v3 & 1) == 0 && (v3 & 4) == 0 )
    goto LABEL_37;
  v46 = *(_QWORD *)(a2 + 16);
  v42 = 0;
  if ( (v3 & 1) == 0 || (*(_DWORD *)(*(_QWORD *)(a1 + 64) + 8LL) & 0x80u) == 0 )
  {
    v50 = 0;
    goto LABEL_11;
  }
  v8 = *(struct _FLT_INSTANCE **)(a2 + 8);
  v9 = *(struct _FILE_OBJECT **)a2;
  Context = 0;
  OldContext = 0;
  StreamContext = FltGetStreamContext(v8, v9, &Context);
  appended = StreamContext;
  if ( StreamContext == -1073741275 )
  {
    v37 = BfCreateStreamContext(v9, 0, &Context);
    LOBYTE(appended) = v37;
    if ( v37 < 0 )
      goto LABEL_7;
    v38 = FltSetStreamContext(v8, v9, FLT_SET_CONTEXT_REPLACE_IF_EXISTS, Context, &OldContext);
    appended = v38;
    if ( v38 < 0 )
    {
      if ( v38 != -1071906814 )
      {
        FltReleaseContext(Context);
        goto LABEL_7;
      }
      FltReleaseContext(OldContext);
      appended = 0;
    }
    goto LABEL_76;
  }
  if ( StreamContext >= 0 )
  {
LABEL_76:
    v7 = (char *)Context;
    v51 = (char *)Context;
    v42 = Context;
    v50 = 1;
LABEL_11:
    v12 = **(_QWORD ***)(a2 + 24);
    while ( v12 )
    {
      v13 = BfReturnedWalkContextAvlCompareRoutine(a1 + 24, v12);
      if ( v13 < 0 )
      {
        v12 = (_QWORD *)*v12;
      }
      else
      {
        if ( v13 <= 0 )
          goto LABEL_35;
        v12 = (_QWORD *)v12[1];
      }
    }
    v14 = (char *)ExAllocateFromPagedLookasideList(&stru_14000B380);
    v6 = v14;
    if ( !v14 )
    {
      LOBYTE(appended) = -102;
      goto LABEL_7;
    }
    memset(v14, 0, 0x100u);
    if ( v50 )
    {
      FltAcquireResourceShared((PERESOURCE)(v7 + 8));
      v15 = (_QWORD *)*v42;
      if ( *v42 )
      {
        do
        {
          v16 = BfCachedWalkContextAvlCompareRoutine(a1 + 24, v15);
          if ( v16 < 0 )
          {
            v15 = (_QWORD *)*v15;
          }
          else
          {
            if ( v16 <= 0 )
              break;
            v15 = (_QWORD *)v15[1];
          }
        }
        while ( v15 );
      }
      FltReleaseResource((PERESOURCE)(v7 + 8));
      if ( v15 )
      {
        v18 = *((_WORD *)v15 + 21);
        *((_DWORD *)v6 + 20) = 0;
        if ( !v18 )
          v18 = 1;
        Pool2 = ExAllocatePool2(256, v18, 1953711682, v17);
        *((_QWORD *)v6 + 11) = Pool2;
        if ( Pool2 )
        {
          *((_WORD *)v6 + 41) = v18;
          appended = RtlAppendUnicodeStringToString((PUNICODE_STRING)v6 + 5, (PCUNICODE_STRING)(v15 + 5));
          if ( appended >= 0 )
          {
            v6[96] = *((_BYTE *)v15 + 56);
            *((_QWORD *)v6 + 9) = v15[4];
            v20 = v46;
            *(_OWORD *)(v6 + 120) = *((_OWORD *)v15 + 5);
            *(_OWORD *)(v6 + 132) = *(_OWORD *)((char *)v15 + 92);
            *(_OWORD *)(v6 + 152) = *((_OWORD *)v15 + 7);
            *(_OWORD *)(v6 + 168) = *((_OWORD *)v15 + 8);
            *(_OWORD *)(v6 + 184) = *((_OWORD *)v15 + 9);
            *(_OWORD *)(v6 + 200) = *((_OWORD *)v15 + 10);
            *(_OWORD *)(v6 + 216) = *((_OWORD *)v15 + 11);
            *(_OWORD *)(v6 + 232) = *((_OWORD *)v15 + 12);
            *((_QWORD *)v6 + 31) = v15[26];
            *((_QWORD *)v6 + 8) = 1;
            v21 = *(_QWORD **)(v20 + 8);
            if ( *v21 == v20 )
            {
              *(_QWORD *)v6 = v20;
              *((_QWORD *)v6 + 1) = v21;
              *v21 = v6;
              *(_QWORD *)(v20 + 8) = v6;
              v6 = 0;
              **(_BYTE **)(a2 + 32) = 1;
LABEL_36:
              v7 = v51;
              goto LABEL_37;
            }
LABEL_79:
            __fastfail(3u);
          }
        }
        else
        {
          LOBYTE(appended) = -102;
        }
LABEL_48:
        v7 = v51;
        goto LABEL_7;
      }
    }
    WORD1(P[0]) = *(_WORD *)(a1 + 24);
    UnicodeString = BfAllocateUnicodeString(WORD1(P[0]), P);
    LOBYTE(appended) = UnicodeString;
    if ( UnicodeString < 0 )
      goto LABEL_48;
    appended = RtlAppendUnicodeStringToString((PUNICODE_STRING)P, (PCUNICODE_STRING)(a1 + 24));
    if ( appended < 0 )
      goto LABEL_48;
    *((_OWORD *)v6 + 5) = *(_OWORD *)P;
    v26 = *(_QWORD *)(a1 + 80);
    P[1] = 0;
    if ( v26 )
    {
      *((_DWORD *)v6 + 30) = *(unsigned __int16 *)(v26 + 32);
      memmove(
        v6 + 124,
        *(const void **)(*(_QWORD *)(a1 + 80) + 40LL),
        *(unsigned __int16 *)(*(_QWORD *)(a1 + 80) + 32LL));
    }
    else
    {
      *((_DWORD *)v6 + 30) = 0;
    }
    v27 = *(_DWORD *)(a1 - 8);
    if ( (v27 & 1) != 0 )
    {
      v28 = a1;
      v29 = *(__int64 **)(*(_QWORD *)(a1 + 64) + 64LL);
      while ( 1 )
      {
        v30 = *(_QWORD *)(v28 + 64);
        if ( v29 == (__int64 *)(v30 + 64) )
          goto LABEL_62;
        HostSilo = 1;
        memset(&DriverContext, 0, sizeof(DriverContext));
        DriverContext.Size = 40;
        v31 = (*(_DWORD *)(v30 + 8) & 4) != 0 ? PsGetCurrentSilo() : PsGetHostSilo(v30, v11);
        HostSilo = v31;
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = (PUNICODE_STRING)(v29 + 3);
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        appended = FltCreateFileEx2(
                     g_BindFltState,
                     *(PFLT_INSTANCE *)v29[2],
                     &FileHandle,
                     (PFILE_OBJECT *)&Object,
                     0x80u,
                     &ObjectAttributes,
                     &IoStatusBlock,
                     0,
                     0,
                     7u,
                     1u,
                     0,
                     0,
                     0,
                     0,
                     &DriverContext);
        if ( appended >= 0 )
          break;
        v29 = (__int64 *)*v29;
        v28 = a1;
      }
      *((_QWORD *)v6 + 9) = *(_QWORD *)v29[2];
    }
    else if ( (v27 & 4) != 0 )
    {
      *((_QWORD *)v6 + 9) = *(_QWORD *)(a1 + 40);
      memset(&DriverContext, 0, sizeof(DriverContext));
      DriverContext.Size = 40;
      HostSilo = 1;
      HostSilo = PsGetHostSilo(v25, v11);
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)(a1 + 48);
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      appended = FltCreateFileEx2(
                   g_BindFltState,
                   *((PFLT_INSTANCE *)v6 + 9),
                   &FileHandle,
                   (PFILE_OBJECT *)&Object,
                   0x80u,
                   &ObjectAttributes,
                   &IoStatusBlock,
                   0,
                   0,
                   7u,
                   1u,
                   0,
                   0,
                   0,
                   0,
                   &DriverContext);
LABEL_62:
      if ( appended == -1073741772 || appended == -1073741766 )
      {
        LODWORD(v11) = v50;
        if ( !v50 )
        {
LABEL_35:
          if ( appended >= 0 )
            goto LABEL_36;
          goto LABEL_48;
        }
        appended = 0;
        v6[96] = 0;
LABEL_67:
        v32 = v46;
        *((_QWORD *)v6 + 8) = 1;
        v33 = *(_QWORD **)(v32 + 8);
        if ( *v33 != v32 )
          goto LABEL_79;
        *(_QWORD *)v6 = v32;
        *((_QWORD *)v6 + 1) = v33;
        *v33 = v6;
        *(_QWORD *)(v32 + 8) = v6;
        **(_BYTE **)(a2 + 32) = 1;
        if ( (_BYTE)v11 )
        {
          FltAcquireResourceExclusive((PERESOURCE)(v51 + 8));
          if ( _InterlockedIncrement64((volatile signed __int64 *)v6 + 8) <= 1 )
            __fastfail(0xEu);
          v34 = v42;
          LOBYTE(v22) = 0;
          v35 = (_QWORD *)*v42;
          if ( *v42 )
          {
            while ( 1 )
            {
              if ( (int)BfCachedWalkContextAvlCompareRoutine(v6 + 80, v35) < 0 )
              {
                v36 = (_QWORD *)*v35;
                if ( !*v35 )
                {
                  LOBYTE(v22) = 0;
                  break;
                }
              }
              else
              {
                v36 = (_QWORD *)v35[1];
                if ( !v36 )
                {
                  LOBYTE(v22) = 1;
                  break;
                }
              }
              v35 = v36;
            }
          }
          RtlAvlInsertNodeEx(v34, v35, v22, v6 + 40);
          FltReleaseResource((PERESOURCE)(v51 + 8));
        }
        v6 = 0;
        goto LABEL_35;
      }
      if ( appended < 0 )
        goto LABEL_48;
    }
    LODWORD(v11) = v50;
    v6[96] = 1;
    *((_QWORD *)v6 + 13) = Object;
    *((_QWORD *)v6 + 14) = FileHandle;
    if ( v50 )
    {
      appended = BfGenerateDirectoryEntryForCache(v6);
      if ( appended < 0 )
        goto LABEL_48;
      LODWORD(v11) = v50;
      *((_QWORD *)v6 + 13) = 0;
      *((_QWORD *)v6 + 14) = 0;
    }
    else
    {
      Object = 0;
      FileHandle = 0;
    }
    goto LABEL_67;
  }
LABEL_7:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v11) = 3;
    WPP_RECORDER_SF_sDZd(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      12,
      14,
      (__int64)WPP_e12ce5656ffd33908c95ca7de20f6d85_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\dirctrl.c",
      203,
      a1 + 48,
      appended);
  }
  appended = 0;
LABEL_37:
  if ( P[1] )
  {
    ExFreePoolWithTag(P[1], 0x74734642u);
    P[1] = 0;
  }
  LODWORD(P[0]) = 0;
  if ( Object )
    ObfDereferenceObject(Object);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( v6 )
  {
    BfFreeUnicodeString(v6 + 80);
    ExFreeToPagedLookasideList(&stru_14000B380, v6);
  }
  if ( v7 )
    FltReleaseContext(v7);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140018b60  mov     [rsp-8+arg_0], rcx
0x140018b65  push    rbp
0x140018b66  push    rbx
0x140018b67  push    rsi
0x140018b68  push    rdi
0x140018b69  push    r12
0x140018b6b  push    r13
0x140018b6d  push    r14
0x140018b6f  push    r15
0x140018b71  lea     rbp, [rsp-28h]
0x140018b76  sub     rsp, 128h
0x140018b7d  xor     r8d, r8d
0x140018b80  xorps   xmm0, xmm0
0x140018b83  xor     eax, eax
0x140018b85  mov     [rbp+60h+FileHandle], r8
0x140018b89  mov     r14, rcx
0x140018b8c  mov     word ptr [rbp+60h+var_98], ax
0x140018b90  mov     ecx, [rcx-8]
0x140018b93  mov     r13, rdx
0x140018b96  mov     [rbp+60h+Object], r8
0x140018b9a  mov     r15d, r8d
0x140018b9d  mov     [rbp+60h+arg_10], r8
0x140018ba4  mov     r12d, r8d
0x140018ba7  mov     esi, r8d
0x140018baa  movups  xmmword ptr [rbp+60h+var_80.ObjectName], xmm0
0x140018bae  movups  xmmword ptr [rbp+60h+var_80+1Ch], xmm0
0x140018bb2  movups  xmmword ptr [rbp+60h+P], xmm0
0x140018bb6  movups  xmmword ptr [rbp+60h+var_B8.Size], xmm0
0x140018bba  movups  xmmword ptr [rbp+60h+var_B8.DeviceObjectHint], xmm0
0x140018bbe  movups  xmmword ptr [rbp+60h+var_80.Length], xmm0
0x140018bc2  movups  xmmword ptr [rbp+60h+var_50], xmm0
0x140018bc6  test    cl, 2
0x140018bc9  jnz     loc_140018EFC
0x140018bcf  mov     eax, ecx
0x140018bd1  and     eax, 1
0x140018bd4  jz      loc_14001943A
0x140018bda  mov     rcx, [rdx+10h]
0x140018bde  mov     [rbp+60h+var_88], rcx
0x140018be2  mov     [rbp+60h+var_C0], r8
0x140018be6  test    eax, eax
0x140018be8  jz      loc_140018CAC
0x140018bee  mov     rax, [r14+40h]
0x140018bf2  mov     ecx, [rax+8]
0x140018bf5  test    cl, cl
0x140018bf7  jns     loc_140018CAC
0x140018bfd  mov     rdi, [rdx+8]
0x140018c01  mov     rbx, [rdx]
0x140018c04  mov     rcx, rdi; Instance
0x140018c07  mov     [rbp+60h+Context], r8
0x140018c0e  mov     rdx, rbx; FileObject
0x140018c11  mov     [rbp+60h+OldContext], r8
0x140018c15  lea     r8, [rbp+60h+Context]; Context
0x140018c1c  call    cs:__imp_FltGetStreamContext
0x140018c23  nop     dword ptr [rax+rax+00h]
0x140018c28  mov     r15d, eax
0x140018c2b  cmp     eax, 0C0000225h
0x140018c30  jz      loc_1400192F7
0x140018c36  test    eax, eax
0x140018c38  jns     loc_140019343
0x140018c3e  xor     r8d, r8d
0x140018c41  lea     rax, WPP_RECORDER_INITIALIZED
0x140018c48  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140018c4f  jz      short loc_140018CA4
0x140018c51  mov     rcx, cs:WPP_GLOBAL_Control
0x140018c58  mov     r9d, 0Eh
0x140018c5e  mov     rax, [rbp+60h+arg_0]
0x140018c62  mov     r8d, 0Ch
0x140018c68  add     rax, 30h ; '0'
0x140018c6c  mov     [rsp+160h+FileAttributes], r15d
0x140018c71  mov     [rsp+160h+AllocationSize], rax
0x140018c76  mov     dl, 3
0x140018c78  mov     rcx, [rcx+40h]
0x140018c7c  lea     rax, aOnecoreBaseFsW_2; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140018c83  mov     dword ptr [rsp+160h+IoStatusBlock], 2CBh
0x140018c8b  mov     [rsp+160h+ObjectAttributes], rax
0x140018c90  lea     rax, WPP_e12ce5656ffd33908c95ca7de20f6d85_Traceguids
0x140018c97  mov     qword ptr [rsp+160h+DesiredAccess], rax
0x140018c9c  call    WPP_RECORDER_SF_sDZd
0x140018ca1  xor     r8d, r8d
0x140018ca4  mov     r15d, r8d
0x140018ca7  jmp     loc_140018EFC
0x140018cac  mov     [rbp+60h+arg_8], sil
0x140018cb0  mov     rbx, [r13+18h]
0x140018cb4  mov     rbx, [rbx]
0x140018cb7  test    rbx, rbx
0x140018cba  jz      short loc_140018CE3
0x140018cbc  nop     dword ptr [rax+00h]
0x140018cc0  mov     rdx, rbx
0x140018cc3  lea     rcx, [r14+18h]
0x140018cc7  call    BfReturnedWalkContextAvlCompareRoutine
0x140018ccc  test    eax, eax
0x140018cce  js      loc_140018EAC
0x140018cd4  jle     loc_140019448
0x140018cda  mov     rbx, [rbx+8]
0x140018cde  test    rbx, rbx
0x140018ce1  jnz     short loc_140018CC0
0x140018ce3  lea     rcx, stru_14000B380; Lookaside
0x140018cea  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140018cf1  nop     dword ptr [rax+rax+00h]
0x140018cf6  mov     r12, rax
0x140018cf9  test    rax, rax
0x140018cfc  jz      loc_140019459
0x140018d02  xor     edx, edx; Val
0x140018d04  mov     r8d, 100h; Size
0x140018d0a  mov     rcx, rax; void *
0x140018d0d  call    memset
0x140018d12  cmp     [rbp+60h+arg_8], 0
0x140018d16  jz      loc_140018F96
0x140018d1c  lea     rcx, [rsi+8]; Resource
0x140018d20  call    cs:__imp_FltAcquireResourceShared
0x140018d27  nop     dword ptr [rax+rax+00h]
0x140018d2c  mov     rbx, [rbp+60h+var_C0]
0x140018d30  mov     rbx, [rbx]
0x140018d33  test    rbx, rbx
0x140018d36  jz      short loc_140018D5F
0x140018d38  nop     dword ptr [rax+rax+00000000h]
0x140018d40  mov     rdx, rbx
0x140018d43  lea     rcx, [r14+18h]
0x140018d47  call    BfCachedWalkContextAvlCompareRoutine
0x140018d4c  test    eax, eax
0x140018d4e  js      loc_140018EB4
0x140018d54  jle     short loc_140018D5F
0x140018d56  mov     rbx, [rbx+8]
0x140018d5a  test    rbx, rbx
0x140018d5d  jnz     short loc_140018D40
0x140018d5f  lea     rcx, [rsi+8]; Resource
0x140018d63  call    cs:__imp_FltReleaseResource
0x140018d6a  nop     dword ptr [rax+rax+00h]
0x140018d6f  test    rbx, rbx
0x140018d72  jz      loc_140018F96
0x140018d78  movzx   edi, word ptr [rbx+2Ah]
0x140018d7c  xor     eax, eax
0x140018d7e  test    di, di
0x140018d81  mov     [r12+50h], eax
0x140018d86  mov     r14d, 1
0x140018d8c  mov     ecx, 100h
0x140018d91  cmovz   di, r14w
0x140018d96  mov     r8d, 74734642h
0x140018d9c  movzx   edx, di
0x140018d9f  call    cs:__imp_ExAllocatePool2
0x140018da6  nop     dword ptr [rax+rax+00h]
0x140018dab  mov     [r12+58h], rax
0x140018db0  test    rax, rax
0x140018db3  jz      loc_140019467
0x140018db9  lea     rdx, [rbx+28h]; Source
0x140018dbd  mov     [r12+52h], di
0x140018dc3  lea     rcx, [r12+50h]; Destination
0x140018dc8  call    cs:__imp_RtlAppendUnicodeStringToString
0x140018dcf  nop     dword ptr [rax+rax+00h]
0x140018dd4  mov     r15d, eax
0x140018dd7  test    eax, eax
0x140018dd9  js      loc_140018F87
0x140018ddf  movzx   ecx, byte ptr [rbx+38h]
0x140018de3  mov     [r12+60h], cl
0x140018de8  mov     rcx, [rbx+20h]
0x140018dec  mov     [r12+48h], rcx
0x140018df1  movups  xmm0, xmmword ptr [rbx+50h]
0x140018df5  mov     rcx, [rbp+60h+var_88]
0x140018df9  movups  xmmword ptr [r12+78h], xmm0
0x140018dff  movups  xmm1, xmmword ptr [rbx+5Ch]
0x140018e03  movups  xmmword ptr [r12+84h], xmm1
0x140018e0c  movups  xmm0, xmmword ptr [rbx+70h]
0x140018e10  movups  xmmword ptr [r12+98h], xmm0
0x140018e19  movups  xmm1, xmmword ptr [rbx+80h]
0x140018e20  movups  xmmword ptr [r12+0A8h], xmm1
0x140018e29  movups  xmm0, xmmword ptr [rbx+90h]
0x140018e30  movups  xmmword ptr [r12+0B8h], xmm0
0x140018e39  movups  xmm1, xmmword ptr [rbx+0A0h]
0x140018e40  movups  xmmword ptr [r12+0C8h], xmm1
0x140018e49  movups  xmm0, xmmword ptr [rbx+0B0h]
0x140018e50  movups  xmmword ptr [r12+0D8h], xmm0
0x140018e59  movups  xmm1, xmmword ptr [rbx+0C0h]
0x140018e60  movups  xmmword ptr [r12+0E8h], xmm1
0x140018e69  movsd   xmm0, qword ptr [rbx+0D0h]
0x140018e71  movsd   qword ptr [r12+0F8h], xmm0
0x140018e7b  mov     [r12+40h], r14
0x140018e80  mov     rax, [rcx+8]
0x140018e84  cmp     [rax], rcx
0x140018e87  jnz     loc_14001937A
0x140018e8d  mov     [r12], rcx
0x140018e91  xor     r8d, r8d
0x140018e94  mov     [r12+8], rax
0x140018e99  mov     [rax], r12
0x140018e9c  mov     [rcx+8], r12
0x140018ea0  mov     r12d, r8d
0x140018ea3  mov     rax, [r13+20h]
0x140018ea7  mov     [rax], r14b
0x140018eaa  jmp     short loc_140018EF5
0x140018eac  mov     rbx, [rbx]
0x140018eaf  jmp     loc_140018CDE
0x140018eb4  mov     rbx, [rbx]
0x140018eb7  jmp     loc_140018D5A
0x140018ebc  mov     r8b, 1
0x140018ebf  lea     r9, [r12+28h]
0x140018ec4  mov     rdx, rbx
0x140018ec7  mov     rcx, r14
0x140018eca  call    cs:__imp_RtlAvlInsertNodeEx
0x140018ed1  nop     dword ptr [rax+rax+00h]
0x140018ed6  lea     rcx, [rsi+8]; Resource
0x140018eda  call    cs:__imp_FltReleaseResource
0x140018ee1  nop     dword ptr [rax+rax+00h]
0x140018ee6  xor     r8d, r8d
0x140018ee9  mov     r12, r8
0x140018eec  test    r15d, r15d
0x140018eef  js      loc_140018F8A
0x140018ef5  mov     rsi, [rbp+60h+arg_10]
0x140018efc  mov     rcx, [rbp+60h+P+8]; P
0x140018f00  test    rcx, rcx
0x140018f03  jz      short loc_140018F1D
0x140018f05  mov     edx, 74734642h; Tag
0x140018f0a  call    cs:__imp_ExFreePoolWithTag
0x140018f11  nop     dword ptr [rax+rax+00h]
0x140018f16  xor     r8d, r8d
0x140018f19  mov     [rbp+60h+P+8], r8
0x140018f1d  mov     rcx, [rbp+60h+Object]; Object
0x140018f21  mov     dword ptr [rbp+60h+P], 0
0x140018f28  test    rcx, rcx
0x140018f2b  jnz     short loc_140018F79
0x140018f2d  mov     rcx, [rbp+60h+FileHandle]; FileHandle
0x140018f31  test    rcx, rcx
0x140018f34  jnz     short loc_140018F6B
0x140018f36  test    r12, r12
0x140018f39  jnz     loc_14001947E
0x140018f3f  test    rsi, rsi
0x140018f42  jz      short loc_140018F53
0x140018f44  mov     rcx, rsi; Context
0x140018f47  call    cs:__imp_FltReleaseContext
0x140018f4e  nop     dword ptr [rax+rax+00h]
0x140018f53  mov     eax, r15d
0x140018f56  add     rsp, 128h
0x140018f5d  pop     r15
0x140018f5f  pop     r14
0x140018f61  pop     r13
0x140018f63  pop     r12
0x140018f65  pop     rdi
0x140018f66  pop     rsi
0x140018f67  pop     rbx
0x140018f68  pop     rbp
0x140018f69  retn
0x140018f6b  call    cs:__imp_FltClose
0x140018f72  nop     dword ptr [rax+rax+00h]
0x140018f77  jmp     short loc_140018F36
0x140018f79  call    cs:__imp_ObfDereferenceObject
0x140018f80  nop     dword ptr [rax+rax+00h]
0x140018f85  jmp     short loc_140018F2D
0x140018f87  xor     r8d, r8d
0x140018f8a  mov     rsi, [rbp+60h+arg_10]
0x140018f91  jmp     loc_140018C41
0x140018f96  movzx   ecx, word ptr [r14+18h]
0x140018f9b  lea     rdx, [rbp+60h+P]
0x140018f9f  mov     word ptr [rbp+60h+P+2], cx
0x140018fa3  call    BfAllocateUnicodeString
0x140018fa8  mov     r15d, eax
0x140018fab  test    eax, eax
0x140018fad  js      short loc_140018F87
0x140018faf  lea     rdx, [r14+18h]; Source
0x140018fb3  lea     rcx, [rbp+60h+P]; Destination
0x140018fb7  call    cs:__imp_RtlAppendUnicodeStringToString
0x140018fbe  nop     dword ptr [rax+rax+00h]
0x140018fc3  mov     r15d, eax
0x140018fc6  test    eax, eax
0x140018fc8  js      short loc_140018F87
0x140018fca  movups  xmm0, xmmword ptr [rbp+60h+P]
0x140018fce  movups  xmmword ptr [r12+50h], xmm0
0x140018fd4  mov     rax, [r14+50h]
0x140018fd8  mov     [rbp+60h+P+8], 0
0x140018fe0  test    rax, rax
0x140018fe3  jnz     loc_1400193AA
0x140018fe9  mov     [r12+78h], eax
0x140018fee  mov     eax, [r14-8]
0x140018ff2  mov     r14d, 1
0x140018ff8  test    r14b, al
0x140018ffb  jz      loc_140019117
0x140019001  mov     rcx, [rbp+60h+arg_0]
0x140019005  mov     esi, 28h ; '('
0x14001900a  mov     rax, [rcx+40h]
0x14001900e  mov     rbx, [rax+40h]
0x140019012  mov     rcx, [rcx+40h]
0x140019016  lea     rax, [rcx+40h]
0x14001901a  cmp     rbx, rax
0x14001901d  jz      loc_1400191FF
0x140019023  xorps   xmm0, xmm0
0x140019026  mov     [rbp+60h+var_98], r14
0x14001902a  movups  xmmword ptr [rbp+60h+var_B8.Size], xmm0
0x14001902e  mov     [rbp+60h+var_B8.Size], si
0x140019032  movups  xmmword ptr [rbp+60h+var_B8.DeviceObjectHint], xmm0
0x140019036  mov     eax, [rcx+8]
0x140019039  test    al, 4
0x14001903b  jnz     loc_1400193EF
0x140019041  call    cs:__imp_PsGetHostSilo
0x140019048  nop     dword ptr [rax+rax+00h]
0x14001904d  mov     rcx, cs:g_BindFltState; Filter
0x140019054  lea     r9, [rbp+60h+Object]; FileObject
0x140019058  mov     [rbp+60h+var_98], rax
0x14001905c  lea     r8, [rbp+60h+FileHandle]; FileHandle
0x140019060  mov     [rbp+60h+var_80.Length], 30h ; '0'
0x140019067  lea     rax, [rbx+18h]
0x14001906b  mov     [rbp+60h+var_80.ObjectName], rax
0x14001906f  xorps   xmm0, xmm0
0x140019072  mov     [rbp+60h+var_80.RootDirectory], 0
  ... truncated ...
```
