# Streaming::StrmFltInterface::CreateFile(_FLT_INSTANCE *,_FILE_OBJECT &,_FLT_CALLBACK_DATA &,appv::shared::kernel::auto_ptr<Streaming::StrmCreateContext,appv::shared::kernel::AllocDelete<Streaming::StrmCreateContext>> &)

- ea: `0x140012b18`
- end: `0x140013029`
- name: `?CreateFile@StrmFltInterface@Streaming@@QEAAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAU_FLT_CALLBACK_DATA@@AEAV?$auto_ptr@UStrmCreateContext@Streaming@@U?$AllocDelete@UStrmCreateContext@Streaming@@@kernel@shared@appv@@@kernel@shared@appv@@@Z`
- size: `1297`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x140001780`

## callees

- `0x1400034fc`
- `0x140005e3c`
- `0x14000a1ac`
- `0x14000abd8`
- `0x14000ba94`
- `0x140011cb0`
- `0x140012b18`
- `0x1400147fc`
- `0x140014b00`
- `0x1400153c4`
- `0x140015af0`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!IoReplaceFileObjectName` at `0x140012fcd`
- `ntoskrnl!IoReplaceFileObjectName` at `0x140012fcd`
- `ntoskrnl!EtwActivityIdControl` at `0x140012b9c`
- `ntoskrnl!EtwActivityIdControl` at `0x140012cfe`
- `ntoskrnl!EtwActivityIdControl` at `0x140012b9c`
- `ntoskrnl!EtwActivityIdControl` at `0x140012cfe`
- `ntoskrnl!RtlInitUnicodeString` at `0x140012c51`
- `ntoskrnl!RtlInitUnicodeString` at `0x140012c51`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012caa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012caa`
- `FLTMGR!FltCancelFileOpen` at `0x140012eba`
- `FLTMGR!FltCancelFileOpen` at `0x140012eba`
- `FLTMGR!FltReissueSynchronousIo` at `0x140012be2`
- `FLTMGR!FltReissueSynchronousIo` at `0x140012c93`
- `FLTMGR!FltReissueSynchronousIo` at `0x140012d52`
- `FLTMGR!FltReissueSynchronousIo` at `0x140012fdf`
- `FLTMGR!FltReissueSynchronousIo` at `0x140012be2`
- `FLTMGR!FltReissueSynchronousIo` at `0x140012c93`
- `FLTMGR!FltReissueSynchronousIo` at `0x140012d52`
- `FLTMGR!FltReissueSynchronousIo` at `0x140012fdf`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140012d40`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140012f98`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140012fa7`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140012d40`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140012f98`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140012fa7`
- `FLTMGR!FltReleaseContext` at `0x140012cbf`
- `FLTMGR!FltReleaseContext` at `0x140012dea`
- `FLTMGR!FltReleaseContext` at `0x140012ff3`
- `FLTMGR!FltReleaseContext` at `0x140012cbf`
- `FLTMGR!FltReleaseContext` at `0x140012dea`
- `FLTMGR!FltReleaseContext` at `0x140012ff3`

## string_xrefs

- `0x140012e25`: `StrmFltInterface::CreateFile() - Streaming filter could not track the streamable file '%s'. This can cause I/O failures. Please try to pre-stream the application. Failure status = 0x%08X.`

## pseudocode

```c
__int64 __fastcall Streaming::StrmFltInterface::CreateFile(
        __int64 a1,
        struct _FLT_INSTANCE *a2,
        struct _FILE_OBJECT *a3,
        struct _FLT_CALLBACK_DATA *a4,
        __int64 a5)
{
  const PFLT_IO_PARAMETER_BLOCK *p_Iopb; // r14
  unsigned int StreamContext; // esi
  NTSTATUS Status; // edx
  Streaming::InstanceContextFactory *SecurityContext; // rcx
  NTSTATUS v12; // ecx
  ULONG_PTR Information; // rax
  _BYTE *FsContext; // rax
  __int64 v16; // rbx
  __int64 *CurrentActivityID; // rax
  volatile signed __int32 *v18; // rbx
  volatile signed __int32 *v19; // rbx
  __int64 v20; // [rsp+38h] [rbp-48h] BYREF
  PVOID P; // [rsp+40h] [rbp-40h]
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-38h] BYREF
  char v23[8]; // [rsp+58h] [rbp-28h] BYREF
  volatile signed __int32 *v24; // [rsp+60h] [rbp-20h]
  GUID ActivityId; // [rsp+68h] [rbp-18h] BYREF

  p_Iopb = &a4->Iopb;
  StreamContext = 0;
  Status = a4->IoStatus.Status;
  if ( (Status == -1073741772
     || ((*p_Iopb)->Parameters.Create.Options & 0xFF000000) != 0x1000000 && Status == -1073741790)
    && *(_DWORD *)(*(_QWORD *)a5 + 8LL) > 2u )
  {
    EtwActivityIdControl(3u, &ActivityId);
    if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
      McTemplateK0_EtwWriteTransfer(
        PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
        StrmFlt_IRP_CREATE_START,
        &ActivityId);
    if ( (int)Streaming::StagingManager::StageDirectoryUnsafe(a2) >= 0 )
      FltReissueSynchronousIo(a2, a4);
    if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
      McTemplateK0_EtwWriteTransfer(
        PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
        StrmFlt_IRP_CREATE_STOP,
        &ActivityId);
  }
  SecurityContext = (Streaming::InstanceContextFactory *)(*p_Iopb)->Parameters.Create.SecurityContext;
  if ( (*((_DWORD *)SecurityContext + 4) & 0x10000) != 0 && a4->IoStatus.Status == -1073741738 )
  {
    *(_QWORD *)&ActivityId.Data1 = 0;
    if ( Streaming::InstanceContextFactory::GetContext(
           SecurityContext,
           a2,
           (struct Streaming::InstanceContext *)&ActivityId) >= 0 )
    {
      v20 = 0;
      P = 0;
      RtlInitUnicodeString(&DestinationString, 0);
      if ( (int)appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(
                  &v20,
                  &a3->FileName) >= 0
        && (int)Streaming::StreamingTargetFileCache::Close(
                  *(_QWORD *)(*(_QWORD *)&ActivityId.Data1 + 272LL),
                  &ActivityId,
                  &v20,
                  0) >= 0 )
      {
        FltReissueSynchronousIo(a2, a4);
      }
      if ( P )
        ExFreePoolWithTag(P, 0);
    }
    if ( *(_QWORD *)&ActivityId.Data1 )
      FltReleaseContext(*(PFLT_CONTEXT *)&ActivityId.Data1);
  }
  v12 = a4->IoStatus.Status;
  if ( v12 != 260 )
    goto LABEL_58;
  Information = a4->IoStatus.Information;
  if ( !Information )
    return 0;
  if ( Information != 3221225492 )
  {
LABEL_58:
    if ( **(_BYTE **)a5 && v12 && v12 != 264 )
    {
      if ( *p_Iopb )
      {
        (*p_Iopb)->Parameters.Create.Options |= 0x200000u;
        FltSetCallbackDataDirty(a4);
      }
      FltSetCallbackDataDirty(a4);
      if ( *(_DWORD *)(*(_QWORD *)a5 + 40LL) > 2u )
        IoReplaceFileObjectName(
          (*p_Iopb)->TargetFileObject,
          *(PWSTR *)(*(_QWORD *)a5 + 64LL),
          *(_WORD *)(*(_QWORD *)a5 + 56LL));
      FltReissueSynchronousIo(a2, a4);
    }
    return StreamContext;
  }
  EtwActivityIdControl(3u, &ActivityId);
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(
      PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
      StrmFlt_IRP_CREATE_START,
      &ActivityId);
  if ( *p_Iopb )
  {
    (*p_Iopb)->Parameters.Create.Options |= 0x200000u;
    FltSetCallbackDataDirty(a4);
  }
  FltReissueSynchronousIo(a2, a4);
  StreamContext = a4->IoStatus.Status;
  if ( (StreamContext & 0x80000000) != 0 )
  {
    if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) == 0 )
      return StreamContext;
LABEL_30:
    McTemplateK0_EtwWriteTransfer(
      PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
      StrmFlt_IRP_CREATE_STOP,
      &ActivityId);
    return StreamContext;
  }
  FsContext = a3->FsContext;
  if ( FsContext && (FsContext[6] & 2) != 0 )
  {
    StreamContext = Streaming::Context::StreamContextFactory::GetOrCreateStreamContext(a2);
    if ( StreamContext == -1073741195 )
    {
      if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
        McTemplateK0_EtwWriteTransfer(
          PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
          StrmFlt_IRP_CREATE_STOP,
          &ActivityId);
      return 0;
    }
    if ( (StreamContext & 0x80000000) != 0 )
    {
      v16 = *(_QWORD *)Streaming::Utils::GetNullTerminated(&v20, &a3->FileName);
      CurrentActivityID = (__int64 *)Streaming::Utils::GetCurrentActivityID(v23);
      LogWrite(
        1,
        *CurrentActivityID,
        L"StrmFltInterface::CreateFile() - Streaming filter could not track the streamable file '%s'. This can cause I/O f"
         "ailures. Please try to pre-stream the application. Failure status = 0x%08X.",
        v16,
        StreamContext);
      v18 = v24;
      if ( v24 )
      {
        if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
          if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 16LL))(v18);
        }
      }
      v19 = (volatile signed __int32 *)P;
      if ( P )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
          if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 16LL))(v19);
        }
      }
      FltCancelFileOpen(a2, a3);
      if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
        McTemplateK0_EtwWriteTransfer(
          PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
          StrmFlt_IRP_CREATE_STOP,
          &ActivityId);
      return StreamContext;
    }
LABEL_49:
    if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) == 0 )
      return StreamContext;
    goto LABEL_30;
  }
  if ( a4->IoStatus.Status != 260 || a4->IoStatus.Information != 3221225492 )
    goto LABEL_49;
  a4->IoStatus.Information = 0;
  a4->IoStatus.Status = -1073741766;
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(
      PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
      StrmFlt_IRP_CREATE_STOP,
      &ActivityId);
  return 3221225530LL;
}

```

## disassembly

```asm
0x140012b18  mov     [rsp-38h+arg_0], rbx
0x140012b1d  push    rbp
0x140012b1e  push    rsi
0x140012b1f  push    rdi
0x140012b20  push    r12
0x140012b22  push    r13
0x140012b24  push    r14
0x140012b26  push    r15
0x140012b28  mov     rbp, rsp
0x140012b2b  sub     rsp, 80h
0x140012b32  mov     rax, cs:__security_cookie
0x140012b39  xor     rax, rsp
0x140012b3c  mov     [rbp+var_8], rax
0x140012b40  mov     r12, [rbp+arg_20]
0x140012b44  lea     r14, [r9+10h]
0x140012b48  xor     esi, esi
0x140012b4a  mov     r15, rdx
0x140012b4d  mov     edx, [r9+18h]
0x140012b51  mov     ebx, esi
0x140012b53  mov     [rbp+Context], rbx
0x140012b57  mov     rdi, r9
0x140012b5a  mov     r13, r8
0x140012b5d  cmp     edx, 0C0000034h
0x140012b63  jz      short loc_140012B89
0x140012b65  mov     rax, [r14]
0x140012b68  mov     ecx, [rax+20h]
0x140012b6b  and     ecx, 0FF000000h
0x140012b71  cmp     ecx, 1000000h
0x140012b77  jz      loc_140012C0E
0x140012b7d  cmp     edx, 0C0000022h
0x140012b83  jnz     loc_140012C0E
0x140012b89  mov     rax, [r12]
0x140012b8d  cmp     dword ptr [rax+8], 2
0x140012b91  jbe     short loc_140012C0E
0x140012b93  lea     rdx, [rbp+ActivityId]; ActivityId
0x140012b97  mov     ecx, 3; ControlCode
0x140012b9c  call    cs:__imp_EtwActivityIdControl
0x140012ba3  nop     dword ptr [rax+rax+00h]
0x140012ba8  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x140012baf  jz      short loc_140012BC8
0x140012bb1  lea     r8, [rbp+ActivityId]
0x140012bb5  lea     rdx, StrmFlt_IRP_CREATE_START
0x140012bbc  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140012bc3  call    McTemplateK0_EtwWriteTransfer
0x140012bc8  mov     rdx, [r12]
0x140012bcc  mov     rcx, r15; Instance
0x140012bcf  add     rdx, 8
0x140012bd3  call    ?StageDirectoryUnsafe@StagingManager@Streaming@@SAJPEAU_FLT_INSTANCE@@AEBV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@@Z; Streaming::StagingManager::StageDirectoryUnsafe(_FLT_INSTANCE *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> const &)
0x140012bd8  test    eax, eax
0x140012bda  js      short loc_140012BEE
0x140012bdc  mov     rdx, rdi; CallbackData
0x140012bdf  mov     rcx, r15; InitiatingInstance
0x140012be2  call    cs:__imp_FltReissueSynchronousIo
0x140012be9  nop     dword ptr [rax+rax+00h]
0x140012bee  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x140012bf5  jz      short loc_140012C0E
0x140012bf7  lea     r8, [rbp+ActivityId]
0x140012bfb  lea     rdx, StrmFlt_IRP_CREATE_STOP
0x140012c02  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140012c09  call    McTemplateK0_EtwWriteTransfer
0x140012c0e  mov     rax, [r14]
0x140012c11  mov     rcx, [rax+18h]; this
0x140012c15  test    dword ptr [rcx+10h], 10000h
0x140012c1c  jz      loc_140012CCB
0x140012c22  cmp     dword ptr [rdi+18h], 0C0000056h
0x140012c29  jnz     loc_140012CCB
0x140012c2f  lea     r8, [rbp+ActivityId]; struct Streaming::InstanceContext *
0x140012c33  mov     qword ptr [rbp+ActivityId.Data1], rsi
0x140012c37  mov     rdx, r15; struct _FLT_INSTANCE *
0x140012c3a  call    ?GetContext@InstanceContextFactory@Streaming@@QEAAJPEAU_FLT_INSTANCE@@AEAVInstanceContext@2@@Z; Streaming::InstanceContextFactory::GetContext(_FLT_INSTANCE *,Streaming::InstanceContext &)
0x140012c3f  test    eax, eax
0x140012c41  js      short loc_140012CB6
0x140012c43  xor     edx, edx; SourceString
0x140012c45  mov     [rbp+var_48], rsi
0x140012c49  lea     rcx, [rbp+DestinationString]; DestinationString
0x140012c4d  mov     [rbp+P], rsi
0x140012c51  call    cs:__imp_RtlInitUnicodeString
0x140012c58  nop     dword ptr [rax+rax+00h]
0x140012c5d  lea     rdx, [r13+58h]
0x140012c61  lea     rcx, [rbp+var_48]
0x140012c65  call    ?build_managed_unicode_string@?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(_UNICODE_STRING const &)
0x140012c6a  test    eax, eax
0x140012c6c  js      short loc_140012C9F
0x140012c6e  mov     rcx, qword ptr [rbp+ActivityId.Data1]
0x140012c72  lea     r8, [rbp+var_48]
0x140012c76  xor     r9d, r9d
0x140012c79  lea     rdx, [rbp+ActivityId]
0x140012c7d  mov     rcx, [rcx+110h]
0x140012c84  call    ?Close@StreamingTargetFileCache@Streaming@@QEAAJAEAVInstanceContext@2@AEBV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@_N@Z; Streaming::StreamingTargetFileCache::Close(Streaming::InstanceContext &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> const &,bool)
0x140012c89  test    eax, eax
0x140012c8b  js      short loc_140012C9F
0x140012c8d  mov     rdx, rdi; CallbackData
0x140012c90  mov     rcx, r15; InitiatingInstance
0x140012c93  call    cs:__imp_FltReissueSynchronousIo
0x140012c9a  nop     dword ptr [rax+rax+00h]
0x140012c9f  mov     rcx, [rbp+P]; P
0x140012ca3  test    rcx, rcx
0x140012ca6  jz      short loc_140012CB6
0x140012ca8  xor     edx, edx; Tag
0x140012caa  call    cs:__imp_ExFreePoolWithTag
0x140012cb1  nop     dword ptr [rax+rax+00h]
0x140012cb6  mov     rcx, qword ptr [rbp+ActivityId.Data1]; Context
0x140012cba  test    rcx, rcx
0x140012cbd  jz      short loc_140012CCB
0x140012cbf  call    cs:__imp_FltReleaseContext
0x140012cc6  nop     dword ptr [rax+rax+00h]
0x140012ccb  mov     ecx, [rdi+18h]
0x140012cce  cmp     ecx, 104h
0x140012cd4  jnz     loc_140012F70
0x140012cda  mov     rax, [rdi+20h]
0x140012cde  test    rax, rax
0x140012ce1  jz      loc_140012DF6
0x140012ce7  mov     edx, 0C0000014h
0x140012cec  cmp     rax, rdx
0x140012cef  jnz     loc_140012F70
0x140012cf5  lea     rdx, [rbp+ActivityId]; ActivityId
0x140012cf9  mov     ecx, 3; ControlCode
0x140012cfe  call    cs:__imp_EtwActivityIdControl
0x140012d05  nop     dword ptr [rax+rax+00h]
0x140012d0a  mov     r12d, 1
0x140012d10  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, r12b
0x140012d17  jz      short loc_140012D30
0x140012d19  lea     r8, [rbp+ActivityId]
0x140012d1d  lea     rdx, StrmFlt_IRP_CREATE_START
0x140012d24  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140012d2b  call    McTemplateK0_EtwWriteTransfer
0x140012d30  mov     rax, [r14]
0x140012d33  test    rax, rax
0x140012d36  jz      short loc_140012D4C
0x140012d38  bts     dword ptr [rax+20h], 15h
0x140012d3d  mov     rcx, rdi; Data
0x140012d40  call    cs:__imp_FltSetCallbackDataDirty
0x140012d47  nop     dword ptr [rax+rax+00h]
0x140012d4c  mov     rdx, rdi; CallbackData
0x140012d4f  mov     rcx, r15; InitiatingInstance
0x140012d52  call    cs:__imp_FltReissueSynchronousIo
0x140012d59  nop     dword ptr [rax+rax+00h]
0x140012d5e  mov     esi, [rdi+18h]
0x140012d61  test    esi, esi
0x140012d63  jns     short loc_140012D8E
0x140012d65  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, r12b
0x140012d6c  jz      loc_140012FFF
0x140012d72  lea     r8, [rbp+ActivityId]
0x140012d76  lea     rdx, StrmFlt_IRP_CREATE_STOP
0x140012d7d  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140012d84  call    McTemplateK0_EtwWriteTransfer
0x140012d89  jmp     loc_140012FFF
0x140012d8e  mov     rax, [r13+18h]
0x140012d92  test    rax, rax
0x140012d95  jz      loc_140012F25
0x140012d9b  mov     al, [rax+6]
0x140012d9e  test    al, 2
0x140012da0  jz      loc_140012F25
0x140012da6  lea     r9, [rbp+Context]
0x140012daa  mov     r8, r13
0x140012dad  mov     rdx, rdi
0x140012db0  mov     rcx, r15; Instance
0x140012db3  call    ?GetOrCreateStreamContext@StreamContextFactory@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEAU_FLT_CALLBACK_DATA@@AEAU_FILE_OBJECT@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@@Z; Streaming::Context::StreamContextFactory::GetOrCreateStreamContext(_FLT_INSTANCE *,_FLT_CALLBACK_DATA &,_FILE_OBJECT &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &)
0x140012db8  mov     esi, eax
0x140012dba  cmp     eax, 0C0000275h
0x140012dbf  jnz     short loc_140012DFD
0x140012dc1  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, r12b
0x140012dc8  jz      short loc_140012DE1
0x140012dca  lea     r8, [rbp+ActivityId]
0x140012dce  lea     rdx, StrmFlt_IRP_CREATE_STOP
0x140012dd5  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140012ddc  call    McTemplateK0_EtwWriteTransfer
0x140012de1  mov     rcx, [rbp+Context]; Context
0x140012de5  test    rcx, rcx
0x140012de8  jz      short loc_140012DF6
0x140012dea  call    cs:__imp_FltReleaseContext
0x140012df1  nop     dword ptr [rax+rax+00h]
0x140012df6  xor     eax, eax
0x140012df8  jmp     loc_140013001
0x140012dfd  test    esi, esi
0x140012dff  jns     loc_140012EF8
0x140012e05  lea     rdx, [r13+58h]
0x140012e09  lea     rcx, [rbp+var_48]
0x140012e0d  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x140012e12  lea     rcx, [rbp+var_28]
0x140012e16  mov     rbx, [rax]
0x140012e19  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140012e1e  mov     r9, rbx
0x140012e21  mov     [rsp+80h+var_60], esi
0x140012e25  lea     r8, aStrmfltinterfa; "StrmFltInterface::CreateFile() - Stream"...
0x140012e2c  mov     ecx, r12d
0x140012e2f  mov     rdx, [rax]
0x140012e32  call    LogWrite
0x140012e37  mov     rbx, [rbp+var_20]
0x140012e3b  or      edi, 0FFFFFFFFh
0x140012e3e  test    rbx, rbx
0x140012e41  jz      short loc_140012E77
0x140012e43  mov     eax, edi
0x140012e45  lock xadd [rbx+8], eax
0x140012e4a  add     eax, edi
0x140012e4c  jnz     short loc_140012E77
0x140012e4e  mov     rax, [rbx]
0x140012e51  mov     rcx, rbx
0x140012e54  mov     rax, [rax+8]
0x140012e58  call    _guard_dispatch_icall
0x140012e5d  mov     eax, edi
0x140012e5f  lock xadd [rbx+0Ch], eax
0x140012e64  add     eax, edi
0x140012e66  jnz     short loc_140012E77
0x140012e68  mov     rax, [rbx]
0x140012e6b  mov     rcx, rbx
0x140012e6e  mov     rax, [rax+10h]
0x140012e72  call    _guard_dispatch_icall
0x140012e77  mov     rbx, [rbp+P]
0x140012e7b  test    rbx, rbx
0x140012e7e  jz      short loc_140012EB4
0x140012e80  mov     eax, edi
0x140012e82  lock xadd [rbx+8], eax
0x140012e87  add     eax, edi
0x140012e89  jnz     short loc_140012EB4
0x140012e8b  mov     rax, [rbx]
0x140012e8e  mov     rcx, rbx
0x140012e91  mov     rax, [rax+8]
0x140012e95  call    _guard_dispatch_icall
0x140012e9a  mov     eax, edi
0x140012e9c  lock xadd [rbx+0Ch], eax
0x140012ea1  add     eax, edi
0x140012ea3  jnz     short loc_140012EB4
0x140012ea5  mov     rax, [rbx]
0x140012ea8  mov     rcx, rbx
0x140012eab  mov     rax, [rax+10h]
0x140012eaf  call    _guard_dispatch_icall
0x140012eb4  mov     rdx, r13; FileObject
0x140012eb7  mov     rcx, r15; Instance
0x140012eba  call    cs:__imp_FltCancelFileOpen
0x140012ec1  nop     dword ptr [rax+rax+00h]
0x140012ec6  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, r12b
0x140012ecd  jz      short loc_140012EE6
0x140012ecf  lea     r8, [rbp+ActivityId]
0x140012ed3  lea     rdx, StrmFlt_IRP_CREATE_STOP
0x140012eda  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140012ee1  call    McTemplateK0_EtwWriteTransfer
0x140012ee6  mov     rcx, [rbp+Context]
0x140012eea  test    rcx, rcx
0x140012eed  jz      loc_140012FFF
0x140012ef3  jmp     loc_140012FF3
0x140012ef8  mov     rbx, [rbp+Context]
0x140012efc  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, r12b
0x140012f03  jz      loc_140012FEB
0x140012f09  lea     r8, [rbp+ActivityId]
0x140012f0d  lea     rdx, StrmFlt_IRP_CREATE_STOP
0x140012f14  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140012f1b  call    McTemplateK0_EtwWriteTransfer
0x140012f20  jmp     loc_140012FEB
0x140012f25  cmp     dword ptr [rdi+18h], 104h
0x140012f2c  jnz     short loc_140012EFC
0x140012f2e  mov     eax, 0C0000014h
0x140012f33  cmp     [rdi+20h], rax
0x140012f37  jnz     short loc_140012EFC
0x140012f39  mov     ebx, 0C000003Ah
0x140012f3e  mov     qword ptr [rdi+20h], 0
0x140012f46  mov     [rdi+18h], ebx
0x140012f49  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, r12b
0x140012f50  jz      short loc_140012F69
0x140012f52  lea     r8, [rbp+ActivityId]
0x140012f56  lea     rdx, StrmFlt_IRP_CREATE_STOP
0x140012f5d  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140012f64  call    McTemplateK0_EtwWriteTransfer
0x140012f69  mov     eax, ebx
0x140012f6b  jmp     loc_140013001
0x140012f70  mov     rax, [r12]
0x140012f74  cmp     [rax], bl
0x140012f76  jz      loc_140012FFF
0x140012f7c  test    ecx, ecx
0x140012f7e  jz      short loc_140012FFF
0x140012f80  cmp     ecx, 108h
0x140012f86  jz      short loc_140012FFF
0x140012f88  mov     rax, [r14]
0x140012f8b  test    rax, rax
0x140012f8e  jz      short loc_140012FA4
0x140012f90  bts     dword ptr [rax+20h], 15h
0x140012f95  mov     rcx, rdi; Data
0x140012f98  call    cs:__imp_FltSetCallbackDataDirty
0x140012f9f  nop     dword ptr [rax+rax+00h]
0x140012fa4  mov     rcx, rdi; Data
0x140012fa7  call    cs:__imp_FltSetCallbackDataDirty
0x140012fae  nop     dword ptr [rax+rax+00h]
0x140012fb3  mov     rdx, [r12]
0x140012fb7  cmp     dword ptr [rdx+28h], 2
0x140012fbb  jbe     short loc_140012FD9
0x140012fbd  mov     rcx, [r14]
0x140012fc0  movzx   r8d, word ptr [rdx+38h]; FileNameLength
0x140012fc5  mov     rdx, [rdx+40h]; NewFileName
0x140012fc9  mov     rcx, [rcx+8]; FileObject
0x140012fcd  call    cs:__imp_IoReplaceFileObjectName
0x140012fd4  nop     dword ptr [rax+rax+00h]
0x140012fd9  mov     rdx, rdi; CallbackData
0x140012fdc  mov     rcx, r15; InitiatingInstance
0x140012fdf  call    cs:__imp_FltReissueSynchronousIo
0x140012fe6  nop     dword ptr [rax+rax+00h]
0x140012feb  test    rbx, rbx
0x140012fee  jz      short loc_140012FFF
0x140012ff0  mov     rcx, rbx; Context
0x140012ff3  call    cs:__imp_FltReleaseContext
0x140012ffa  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
