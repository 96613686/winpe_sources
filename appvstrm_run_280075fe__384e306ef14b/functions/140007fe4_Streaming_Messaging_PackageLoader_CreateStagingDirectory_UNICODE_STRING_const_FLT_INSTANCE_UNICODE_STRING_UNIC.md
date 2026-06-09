# Streaming::Messaging::PackageLoader::CreateStagingDirectory(_UNICODE_STRING const &,_FLT_INSTANCE *,_UNICODE_STRING *,_UNICODE_STRING const &,uchar)

- ea: `0x140007fe4`
- end: `0x1400084a9`
- name: `?CreateStagingDirectory@PackageLoader@Messaging@Streaming@@CAJAEBU_UNICODE_STRING@@PEAU_FLT_INSTANCE@@PEAU4@0E@Z`
- size: `1221`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, PFLT_INSTANCE Instance, struct _UNICODE_STRING *, const struct _UNICODE_STRING *, char)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1400084b0`

## callees

- `0x14000279c`
- `0x140002864`
- `0x140002910`
- `0x140003284`
- `0x140003368`
- `0x140007fe4`
- `0x1400147fc`
- `0x140014b00`
- `0x1400153c4`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140008193`
- `ntoskrnl!ObfDereferenceObject` at `0x140008303`
- `ntoskrnl!ObfDereferenceObject` at `0x14000847e`
- `ntoskrnl!ObfDereferenceObject` at `0x140008193`
- `ntoskrnl!ObfDereferenceObject` at `0x140008303`
- `ntoskrnl!ObfDereferenceObject` at `0x14000847e`
- `FLTMGR!FltClose` at `0x140008176`
- `FLTMGR!FltClose` at `0x1400082e6`
- `FLTMGR!FltClose` at `0x140008331`
- `FLTMGR!FltClose` at `0x140008465`
- `FLTMGR!FltClose` at `0x140008176`
- `FLTMGR!FltClose` at `0x1400082e6`
- `FLTMGR!FltClose` at `0x140008331`
- `FLTMGR!FltClose` at `0x140008465`

## string_xrefs

- `0x1400080dc`: `PackageLoader::CreateStagingDirectory() - Failed to create package file %s. Failure status = 0x%08X.`
- `0x1400081fa`: `PackageLoader::CreateStagingDirectory() - Could not set short name %s on file %s. Failure status = 0x%08X.`
- `0x14000838d`: `PackageLoader::CreateStagingDirectory() - Failed to set extended attributes on file %s with error code 0x%08X.`
- `0x1400083c7`: `PackageLoader::CreateStagingDirectory() - Failed to query offline attributes for file %s with error code 0x%08X.`

## pseudocode

```c
__int64 __fastcall Streaming::Messaging::PackageLoader::CreateStagingDirectory(
        struct _UNICODE_STRING *a1,
        PFLT_INSTANCE Instance,
        struct _FILE_OBJECT *a3,
        const struct _UNICODE_STRING *a4,
        char a5)
{
  struct _FLT_INSTANCE *v7; // rbx
  struct _FLT_FILTER *v8; // rdi
  NTSTATUS v10; // eax
  struct _UNICODE_STRING *v11; // r9
  NTSTATUS ParentDirectories; // r14d
  __int64 v13; // rbx
  __int64 *CurrentActivityID; // rax
  volatile signed __int32 *v15; // rbx
  volatile signed __int32 *v16; // rbx
  HANDLE v17; // rcx
  int v19; // r15d
  __int64 v20; // rdi
  __int64 v21; // rbx
  __int64 *v22; // rax
  volatile signed __int32 *v23; // rbx
  volatile signed __int32 *v24; // rbx
  volatile signed __int32 *v25; // rbx
  int v26; // edi
  struct _FILE_OBJECT *v27; // r8
  unsigned int v28; // r9d
  __int64 v29; // rbx
  __int64 *v30; // rax
  const WCHAR *v31; // r8
  volatile signed __int32 *v32; // rbx
  volatile signed __int32 *v33; // rbx
  struct _UNICODE_STRING *v34; // [rsp+20h] [rbp-60h]
  struct _UNICODE_STRING *v35; // [rsp+20h] [rbp-60h]
  __int64 v36; // [rsp+28h] [rbp-58h]
  __int64 v37; // [rsp+28h] [rbp-58h]
  HANDLE FileHandle; // [rsp+40h] [rbp-40h] BYREF
  PVOID Object; // [rsp+48h] [rbp-38h] BYREF
  __int64 v40; // [rsp+50h] [rbp-30h] BYREF
  char near **v41; // [rsp+58h] [rbp-28h]
  _BYTE v42[8]; // [rsp+60h] [rbp-20h] BYREF
  volatile signed __int32 *v43; // [rsp+68h] [rbp-18h]
  _BYTE v44[8]; // [rsp+70h] [rbp-10h] BYREF
  volatile signed __int32 *v45; // [rsp+78h] [rbp-8h]

  Object = 0;
  v7 = (struct _FLT_INSTANCE *)a1;
  FileHandle = 0;
  v8 = (struct _FLT_FILTER *)*((_QWORD *)Streaming::gStrmFltData + 1);
  v10 = Streaming::FileOperations::CreateDirectoryInternal(
          v8,
          Instance,
          a1,
          0x130116u,
          2u,
          v36,
          (PFILE_OBJECT *)&Object,
          &FileHandle);
  ParentDirectories = v10;
  if ( v10 == -1073741766 || v10 == -1073741772 )
  {
    ParentDirectories = Streaming::FileOperations::CreateParentDirectories(v8, Instance, v7, a4, v34);
    if ( ParentDirectories < 0 )
    {
LABEL_6:
      v13 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v42, v7);
      CurrentActivityID = (__int64 *)Streaming::Utils::GetCurrentActivityID(&v40);
      LODWORD(v34) = ParentDirectories;
      LogWrite(
        1,
        *CurrentActivityID,
        L"PackageLoader::CreateStagingDirectory() - Failed to create package file %s. Failure status = 0x%08X.",
        v13,
        v34);
      v15 = (volatile signed __int32 *)v41;
      if ( v41 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v41 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
          if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 16LL))(v15);
        }
      }
      v16 = v43;
      if ( v43 )
      {
        if ( _InterlockedExchangeAdd(v43 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
          if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 16LL))(v16);
        }
      }
      v17 = FileHandle;
      if ( !FileHandle )
        goto LABEL_16;
LABEL_15:
      FltClose(v17);
      FileHandle = 0;
LABEL_16:
      if ( Object )
        ObfDereferenceObject(Object);
      return (unsigned int)ParentDirectories;
    }
    ParentDirectories = Streaming::FileOperations::CreateDirectoryInternal(
                          v8,
                          Instance,
                          (struct _UNICODE_STRING *)v7,
                          0x130116u,
                          3u,
                          v37,
                          (PFILE_OBJECT *)&Object,
                          &FileHandle);
  }
  if ( ParentDirectories < 0 )
    goto LABEL_6;
  if ( a3 )
  {
    v19 = Streaming::FileOperations::SetShortName(Instance, (PFILE_OBJECT)Object, a3, v11);
    if ( v19 < 0 )
    {
      v20 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v44, a3);
      v21 = *(_QWORD *)Streaming::Utils::GetNullTerminated(&v40, v7);
      v22 = (__int64 *)Streaming::Utils::GetCurrentActivityID(v42);
      LODWORD(v34) = v20;
      LogWrite(
        1,
        *v22,
        L"PackageLoader::CreateStagingDirectory() - Could not set short name %s on file %s. Failure status = 0x%08X.",
        v21);
      v23 = v43;
      if ( v43 )
      {
        if ( _InterlockedExchangeAdd(v43 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
          if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 16LL))(v23);
        }
      }
      v24 = (volatile signed __int32 *)v41;
      if ( v41 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v41 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
          if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 16LL))(v24);
        }
      }
      v25 = v45;
      if ( v45 )
      {
        if ( _InterlockedExchangeAdd(v45 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
          if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 16LL))(v25);
        }
      }
      if ( v19 != -1073741409 && v19 != -1073741771 )
      {
        if ( FileHandle )
        {
          FltClose(FileHandle);
          FileHandle = 0;
        }
        if ( Object )
          ObfDereferenceObject(Object);
        return (unsigned int)v19;
      }
      v7 = (struct _FLT_INSTANCE *)a1;
    }
  }
  if ( a5 )
  {
    v17 = FileHandle;
    if ( !FileHandle )
      goto LABEL_16;
    goto LABEL_15;
  }
  v41 = &strmDirectoryEaName;
  v40 = 1114128;
  v26 = Streaming::FileOperations::SetEA(
          Instance,
          (PFILE_OBJECT)Object,
          (struct _FILE_OBJECT *)&v40,
          (const struct _STRING *)1,
          (unsigned int)v34);
  if ( v26 < 0 )
  {
    v29 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v42, v7);
    v30 = (__int64 *)Streaming::Utils::GetCurrentActivityID(v44);
    v31 = L"PackageLoader::CreateStagingDirectory() - Failed to set extended attributes on file %s with error code 0x%08X.";
    goto LABEL_48;
  }
  LOBYTE(v28) = 1;
  v26 = Streaming::FileOperations::ChangeFileAttribute(Instance, (PFILE_OBJECT)Object, v27, v28, (unsigned __int8)v35);
  if ( v26 < 0 )
  {
    v29 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v42, v7);
    v30 = (__int64 *)Streaming::Utils::GetCurrentActivityID(v44);
    v31 = L"PackageLoader::CreateStagingDirectory() - Failed to query offline attributes for file %s with error code 0x%08X.";
LABEL_48:
    LODWORD(v35) = v26;
    LogWrite(1, *v30, v31, v29, v35);
    v32 = v45;
    if ( v45 )
    {
      if ( _InterlockedExchangeAdd(v45 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
        if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 16LL))(v32);
      }
    }
    v33 = v43;
    if ( v43 )
    {
      if ( _InterlockedExchangeAdd(v43 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
        if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 16LL))(v33);
      }
    }
  }
  if ( FileHandle )
  {
    FltClose(FileHandle);
    FileHandle = 0;
  }
  if ( Object )
    ObfDereferenceObject(Object);
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x140007fe4  mov     r11, rsp
0x140007fe7  mov     [r11+10h], rbx
0x140007feb  mov     [r11+20h], rsi
0x140007fef  mov     [r11+18h], r8
0x140007ff3  mov     [r11+8], rcx
0x140007ff7  push    rbp
0x140007ff8  push    rdi
0x140007ff9  push    r13
0x140007ffb  push    r14
0x140007ffd  push    r15
0x140007fff  mov     rbp, rsp
0x140008002  sub     rsp, 80h
0x140008009  mov     rax, cs:?gStrmFltData@Streaming@@3PEAUStrmGlobalData@1@EA; Streaming::StrmGlobalData * Streaming::gStrmFltData
0x140008010  mov     r15, r8
0x140008013  mov     rsi, r9
0x140008016  mov     [rbp+Object], 0
0x14000801e  mov     rbx, rcx
0x140008021  mov     [rbp+FileHandle], 0
0x140008029  mov     r8, rcx
0x14000802c  mov     r9d, 130116h
0x140008032  mov     rdi, [rax+8]
0x140008036  mov     r13, rdx
0x140008039  lea     rax, [rbp+FileHandle]
0x14000803d  mov     rcx, rdi
0x140008040  mov     [r11-70h], rax
0x140008044  lea     rax, [rbp+Object]
0x140008048  mov     [r11-78h], rax
0x14000804c  mov     dword ptr [rsp+80h+var_60], 2; struct _UNICODE_STRING *
0x140008054  call    ?CreateDirectoryInternal@FileOperations@Streaming@@YAJPEAU_FLT_FILTER@@PEAU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@KKPEAXAEAV?$auto_ptr@U_FILE_OBJECT@@UObjectDelete@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$auto_ptr@XUObjectDelete@kernel@shared@appv@@@789@@Z; Streaming::FileOperations::CreateDirectoryInternal(_FLT_FILTER *,_FLT_INSTANCE *,_UNICODE_STRING const &,ulong,ulong,void *,appv::shared::kernel::auto_ptr<_FILE_OBJECT,appv::shared::kernel::ObjectDelete> &,appv::shared::kernel::auto_ptr<void,appv::shared::kernel::ObjectDelete> &)
0x140008059  mov     r14d, eax
0x14000805c  cmp     eax, 0C000003Ah
0x140008061  jz      short loc_14000806A
0x140008063  cmp     eax, 0C0000034h
0x140008068  jnz     short loc_1400080B3
0x14000806a  mov     r9, rsi; struct _UNICODE_STRING *
0x14000806d  mov     r8, rbx; struct _FLT_INSTANCE *
0x140008070  mov     rdx, r13; struct _FLT_FILTER *
0x140008073  mov     rcx, rdi; this
0x140008076  call    ?CreateParentDirectories@FileOperations@Streaming@@YAJPEAU_FLT_FILTER@@PEAU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@2@Z; Streaming::FileOperations::CreateParentDirectories(_FLT_FILTER *,_FLT_INSTANCE *,_UNICODE_STRING const &,_UNICODE_STRING const &)
0x14000807b  mov     r14d, eax
0x14000807e  test    eax, eax
0x140008080  js      short loc_1400080BC
0x140008082  lea     rax, [rbp+FileHandle]
0x140008086  mov     r9d, 130116h
0x14000808c  mov     [rsp+80h+var_48], rax
0x140008091  mov     r8, rbx
0x140008094  lea     rax, [rbp+Object]
0x140008098  mov     rdx, r13
0x14000809b  mov     [rsp+80h+var_50], rax
0x1400080a0  mov     rcx, rdi
0x1400080a3  mov     dword ptr [rsp+80h+var_60], 3
0x1400080ab  call    ?CreateDirectoryInternal@FileOperations@Streaming@@YAJPEAU_FLT_FILTER@@PEAU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@KKPEAXAEAV?$auto_ptr@U_FILE_OBJECT@@UObjectDelete@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$auto_ptr@XUObjectDelete@kernel@shared@appv@@@789@@Z; Streaming::FileOperations::CreateDirectoryInternal(_FLT_FILTER *,_FLT_INSTANCE *,_UNICODE_STRING const &,ulong,ulong,void *,appv::shared::kernel::auto_ptr<_FILE_OBJECT,appv::shared::kernel::ObjectDelete> &,appv::shared::kernel::auto_ptr<void,appv::shared::kernel::ObjectDelete> &)
0x1400080b0  mov     r14d, eax
0x1400080b3  test    r14d, r14d
0x1400080b6  jns     loc_1400081A7
0x1400080bc  mov     rdx, rbx
0x1400080bf  lea     rcx, [rbp+var_20]
0x1400080c3  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x1400080c8  lea     rcx, [rbp+var_30]
0x1400080cc  mov     rbx, [rax]
0x1400080cf  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x1400080d4  mov     r9, rbx
0x1400080d7  mov     dword ptr [rsp+80h+var_60], r14d
0x1400080dc  lea     r8, aPackageloaderC_8; "PackageLoader::CreateStagingDirectory()"...
0x1400080e3  mov     ecx, 1
0x1400080e8  mov     rdx, [rax]
0x1400080eb  call    LogWrite
0x1400080f0  mov     rbx, [rbp+var_28]
0x1400080f4  or      esi, 0FFFFFFFFh
0x1400080f7  test    rbx, rbx
0x1400080fa  jz      short loc_140008130
0x1400080fc  mov     eax, esi
0x1400080fe  lock xadd [rbx+8], eax
0x140008103  add     eax, esi
0x140008105  jnz     short loc_140008130
0x140008107  mov     rax, [rbx]
0x14000810a  mov     rcx, rbx
0x14000810d  mov     rax, [rax+8]
0x140008111  call    _guard_dispatch_icall
0x140008116  mov     eax, esi
0x140008118  lock xadd [rbx+0Ch], eax
0x14000811d  add     eax, esi
0x14000811f  jnz     short loc_140008130
0x140008121  mov     rax, [rbx]
0x140008124  mov     rcx, rbx
0x140008127  mov     rax, [rax+10h]
0x14000812b  call    _guard_dispatch_icall
0x140008130  mov     rbx, [rbp+var_18]
0x140008134  test    rbx, rbx
0x140008137  jz      short loc_14000816D
0x140008139  mov     eax, esi
0x14000813b  lock xadd [rbx+8], eax
0x140008140  add     eax, esi
0x140008142  jnz     short loc_14000816D
0x140008144  mov     rax, [rbx]
0x140008147  mov     rcx, rbx
0x14000814a  mov     rax, [rax+8]
0x14000814e  call    _guard_dispatch_icall
0x140008153  mov     eax, esi
0x140008155  lock xadd [rbx+0Ch], eax
0x14000815a  add     eax, esi
0x14000815c  jnz     short loc_14000816D
0x14000815e  mov     rax, [rbx]
0x140008161  mov     rcx, rbx
0x140008164  mov     rax, [rax+10h]
0x140008168  call    _guard_dispatch_icall
0x14000816d  mov     rcx, [rbp+FileHandle]; FileHandle
0x140008171  test    rcx, rcx
0x140008174  jz      short loc_14000818A
0x140008176  call    cs:__imp_FltClose
0x14000817d  nop     dword ptr [rax+rax+00h]
0x140008182  mov     [rbp+FileHandle], 0
0x14000818a  mov     rcx, [rbp+Object]; Object
0x14000818e  test    rcx, rcx
0x140008191  jz      short loc_14000819F
0x140008193  call    cs:__imp_ObfDereferenceObject
0x14000819a  nop     dword ptr [rax+rax+00h]
0x14000819f  mov     eax, r14d
0x1400081a2  jmp     loc_14000848C
0x1400081a7  or      esi, 0FFFFFFFFh
0x1400081aa  test    r15, r15
0x1400081ad  jz      loc_14000831B
0x1400081b3  mov     rdx, [rbp+Object]; FileObject
0x1400081b7  mov     r8, r15; struct _FILE_OBJECT *
0x1400081ba  mov     rcx, r13; Instance
0x1400081bd  call    ?SetShortName@FileOperations@Streaming@@YAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAU_UNICODE_STRING@@@Z; Streaming::FileOperations::SetShortName(_FLT_INSTANCE *,_FILE_OBJECT &,_UNICODE_STRING &)
0x1400081c2  mov     r15d, eax
0x1400081c5  test    eax, eax
0x1400081c7  jns     loc_14000831B
0x1400081cd  mov     rdx, [rbp+arg_10]
0x1400081d1  lea     rcx, [rbp+var_10]
0x1400081d5  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x1400081da  mov     rdx, rbx
0x1400081dd  lea     rcx, [rbp+var_30]
0x1400081e1  mov     rdi, [rax]
0x1400081e4  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x1400081e9  lea     rcx, [rbp+var_20]
0x1400081ed  mov     rbx, [rax]
0x1400081f0  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x1400081f5  mov     dword ptr [rsp+80h+var_58], r15d
0x1400081fa  lea     r8, aPackageloaderC_3; "PackageLoader::CreateStagingDirectory()"...
0x140008201  mov     r9, rbx
0x140008204  mov     [rsp+80h+var_60], rdi; unsigned __int8
0x140008209  lea     ecx, [rsi+2]
0x14000820c  mov     rdx, [rax]
0x14000820f  call    LogWrite
0x140008214  mov     rbx, [rbp+var_18]
0x140008218  test    rbx, rbx
0x14000821b  jz      short loc_140008251
0x14000821d  mov     eax, esi
0x14000821f  lock xadd [rbx+8], eax
0x140008224  add     eax, esi
0x140008226  jnz     short loc_140008251
0x140008228  mov     rax, [rbx]
0x14000822b  mov     rcx, rbx
0x14000822e  mov     rax, [rax+8]
0x140008232  call    _guard_dispatch_icall
0x140008237  mov     eax, esi
0x140008239  lock xadd [rbx+0Ch], eax
0x14000823e  add     eax, esi
0x140008240  jnz     short loc_140008251
0x140008242  mov     rax, [rbx]
0x140008245  mov     rcx, rbx
0x140008248  mov     rax, [rax+10h]
0x14000824c  call    _guard_dispatch_icall
0x140008251  mov     rbx, [rbp+var_28]
0x140008255  test    rbx, rbx
0x140008258  jz      short loc_14000828E
0x14000825a  mov     eax, esi
0x14000825c  lock xadd [rbx+8], eax
0x140008261  add     eax, esi
0x140008263  jnz     short loc_14000828E
0x140008265  mov     rax, [rbx]
0x140008268  mov     rcx, rbx
0x14000826b  mov     rax, [rax+8]
0x14000826f  call    _guard_dispatch_icall
0x140008274  mov     eax, esi
0x140008276  lock xadd [rbx+0Ch], eax
0x14000827b  add     eax, esi
0x14000827d  jnz     short loc_14000828E
0x14000827f  mov     rax, [rbx]
0x140008282  mov     rcx, rbx
0x140008285  mov     rax, [rax+10h]
0x140008289  call    _guard_dispatch_icall
0x14000828e  mov     rbx, [rbp+var_8]
0x140008292  test    rbx, rbx
0x140008295  jz      short loc_1400082CB
0x140008297  mov     eax, esi
0x140008299  lock xadd [rbx+8], eax
0x14000829e  add     eax, esi
0x1400082a0  jnz     short loc_1400082CB
0x1400082a2  mov     rax, [rbx]
0x1400082a5  mov     rcx, rbx
0x1400082a8  mov     rax, [rax+8]
0x1400082ac  call    _guard_dispatch_icall
0x1400082b1  mov     eax, esi
0x1400082b3  lock xadd [rbx+0Ch], eax
0x1400082b8  add     eax, esi
0x1400082ba  jnz     short loc_1400082CB
0x1400082bc  mov     rax, [rbx]
0x1400082bf  mov     rcx, rbx
0x1400082c2  mov     rax, [rax+10h]
0x1400082c6  call    _guard_dispatch_icall
0x1400082cb  cmp     r15d, 0C000019Fh
0x1400082d2  jz      short loc_140008317
0x1400082d4  cmp     r15d, 0C0000035h
0x1400082db  jz      short loc_140008317
0x1400082dd  mov     rcx, [rbp+FileHandle]; FileHandle
0x1400082e1  test    rcx, rcx
0x1400082e4  jz      short loc_1400082FA
0x1400082e6  call    cs:__imp_FltClose
0x1400082ed  nop     dword ptr [rax+rax+00h]
0x1400082f2  mov     [rbp+FileHandle], 0
0x1400082fa  mov     rcx, [rbp+Object]; Object
0x1400082fe  test    rcx, rcx
0x140008301  jz      short loc_14000830F
0x140008303  call    cs:__imp_ObfDereferenceObject
0x14000830a  nop     dword ptr [rax+rax+00h]
0x14000830f  mov     eax, r15d
0x140008312  jmp     loc_14000848C
0x140008317  mov     rbx, [rbp+arg_0]
0x14000831b  xor     r15d, r15d
0x14000831e  cmp     [rbp+arg_20], r15b
0x140008322  jz      short loc_140008346
0x140008324  mov     rcx, [rbp+FileHandle]; FileHandle
0x140008328  test    rcx, rcx
0x14000832b  jz      loc_14000818A
0x140008331  call    cs:__imp_FltClose
0x140008338  nop     dword ptr [rax+rax+00h]
0x14000833d  mov     [rbp+FileHandle], r15
0x140008341  jmp     loc_14000818A
0x140008346  mov     rdx, [rbp+Object]; FileObject
0x14000834a  lea     rax, ?strmDirectoryEaName@@3PADA; "appvstrmstagedir"
0x140008351  mov     r9d, 1; struct _STRING *
0x140008357  mov     [rbp+var_28], rax
0x14000835b  lea     r8, [rbp+var_30]; struct _FILE_OBJECT *
0x14000835f  mov     [rbp+var_30], 110010h
0x140008367  mov     rcx, r13; Instance
0x14000836a  call    ?SetEA@FileOperations@Streaming@@YAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEBU_STRING@@K@Z; Streaming::FileOperations::SetEA(_FLT_INSTANCE *,_FILE_OBJECT &,_STRING const &,ulong)
0x14000836f  mov     edi, eax
0x140008371  test    eax, eax
0x140008373  jns     short loc_140008396
0x140008375  mov     rdx, rbx
0x140008378  lea     rcx, [rbp+var_20]
0x14000837c  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x140008381  lea     rcx, [rbp+var_10]
0x140008385  mov     rbx, [rax]
0x140008388  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000838d  lea     r8, aPackageloaderC_6; "PackageLoader::CreateStagingDirectory()"...
0x140008394  jmp     short loc_1400083CE
0x140008396  mov     rdx, [rbp+Object]; FileObject
0x14000839a  mov     r9b, 1; unsigned int
0x14000839d  mov     rcx, r13; Instance
0x1400083a0  call    ?ChangeFileAttribute@FileOperations@Streaming@@YAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@KE@Z; Streaming::FileOperations::ChangeFileAttribute(_FLT_INSTANCE *,_FILE_OBJECT &,ulong,uchar)
0x1400083a5  mov     edi, eax
0x1400083a7  test    eax, eax
0x1400083a9  jns     loc_14000845C
0x1400083af  mov     rdx, rbx
0x1400083b2  lea     rcx, [rbp+var_20]
0x1400083b6  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x1400083bb  lea     rcx, [rbp+var_10]
0x1400083bf  mov     rbx, [rax]
0x1400083c2  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x1400083c7  lea     r8, aPackageloaderC_9; "PackageLoader::CreateStagingDirectory()"...
0x1400083ce  mov     rdx, [rax]
0x1400083d1  mov     r9, rbx
0x1400083d4  mov     ecx, 1
0x1400083d9  mov     dword ptr [rsp+80h+var_60], edi
0x1400083dd  call    LogWrite
0x1400083e2  mov     rbx, [rbp+var_8]
0x1400083e6  test    rbx, rbx
0x1400083e9  jz      short loc_14000841F
0x1400083eb  mov     eax, esi
0x1400083ed  lock xadd [rbx+8], eax
0x1400083f2  add     eax, esi
0x1400083f4  jnz     short loc_14000841F
0x1400083f6  mov     rax, [rbx]
0x1400083f9  mov     rcx, rbx
0x1400083fc  mov     rax, [rax+8]
0x140008400  call    _guard_dispatch_icall
0x140008405  mov     eax, esi
0x140008407  lock xadd [rbx+0Ch], eax
0x14000840c  add     eax, esi
0x14000840e  jnz     short loc_14000841F
0x140008410  mov     rax, [rbx]
0x140008413  mov     rcx, rbx
0x140008416  mov     rax, [rax+10h]
0x14000841a  call    _guard_dispatch_icall
0x14000841f  mov     rbx, [rbp+var_18]
0x140008423  test    rbx, rbx
0x140008426  jz      short loc_14000845C
0x140008428  mov     eax, esi
0x14000842a  lock xadd [rbx+8], eax
0x14000842f  add     eax, esi
0x140008431  jnz     short loc_14000845C
0x140008433  mov     rax, [rbx]
0x140008436  mov     rcx, rbx
0x140008439  mov     rax, [rax+8]
0x14000843d  call    _guard_dispatch_icall
0x140008442  mov     eax, esi
  ... truncated ...
```
