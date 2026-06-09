# Streaming::InstanceContextFactory::CreateContext(_FLT_FILTER *,_FLT_INSTANCE *,_FLT_VOLUME *,Streaming::InstanceContext &)

- ea: `0x14000571c`
- end: `0x140005b1a`
- name: `?CreateContext@InstanceContextFactory@Streaming@@QEAAJPEAU_FLT_FILTER@@PEAU_FLT_INSTANCE@@PEAU_FLT_VOLUME@@AEAVInstanceContext@2@@Z`
- size: `1022`
- prototype: `__int64 __fastcall(PERESOURCE *this, struct _FLT_FILTER *, struct _FLT_INSTANCE *, struct _FLT_VOLUME *, PFLT_CONTEXT *ReturnedContext)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x140007700`

## callees

- `0x140003d40`
- `0x140005334`
- `0x14000571c`
- `0x140005b20`
- `0x14000600c`
- `0x140006158`
- `0x1400062bc`
- `0x1400064e4`
- `0x1400065d0`
- `0x14000d7a0`
- `0x1400147fc`
- `0x1400153c4`
- `0x140015af0`
- `0x140015b30`
- `0x140015f00`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005a74`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005a74`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005a68`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005a68`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140005a24`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140005a24`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140005a11`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140005a11`
- `ntoskrnl!ExAllocatePool2` at `0x140005810`
- `ntoskrnl!ExAllocatePool2` at `0x140005810`
- `FLTMGR!FltSetInstanceContext` at `0x140005a8c`
- `FLTMGR!FltSetInstanceContext` at `0x140005a8c`
- `FLTMGR!FltQueryVolumeInformation` at `0x1400059dc`
- `FLTMGR!FltQueryVolumeInformation` at `0x1400059dc`
- `FLTMGR!FltCbdqInitialize` at `0x14000599a`
- `FLTMGR!FltCbdqInitialize` at `0x14000599a`
- `FLTMGR!FltAllocateContext` at `0x140005766`
- `FLTMGR!FltAllocateContext` at `0x140005766`

## string_xrefs

- `0x140005781`: `InstanceContextFactory::CreateContext() - Could not allocate context. Failure code 0x%08X.`
- `0x1400057c8`: `InstanceContextFactory::CreateContext() - Couldn't get the dos name for the attached volume. Failure status = 0x%08X.`
- `0x1400057ee`: `InstanceContextFactory::CreateContext() - The streaming filter could not retrieve volume name. Failure Status 0x%08X.`
- `0x140005878`: `InstanceContextFactory::CreateContext() - Could not attach to volume. Failure code 0x%08X.`
- `0x1400058f1`: `InstanceContextFactory::CreateContext() - Could not attach to volume. Failure code 0x%08X.`
- `0x140005aa7`: `InstanceContextFactory::CreateContext() - Could not set an instance for a volume. Failure code 0x%08X.`

## pseudocode

```c
__int64 __fastcall Streaming::InstanceContextFactory::CreateContext(
        PERESOURCE *this,
        struct _FLT_FILTER *a2,
        struct _FLT_INSTANCE *a3,
        struct _FLT_VOLUME *a4,
        PFLT_CONTEXT *ReturnedContext)
{
  NTSTATUS Context; // esi
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  PFLT_CONTEXT v13; // r14
  void *Pool2; // rax
  __int64 v15; // rax
  void *v16; // rcx
  _QWORD *CurrentActivityID; // rax
  volatile signed __int32 *Information; // rdi
  _QWORD *v19; // rax
  bool v20; // sf
  _DWORD *v21; // rax
  int v22; // ecx
  bool v23; // si
  Streaming::InstanceContextFactory **v24; // rdx
  Streaming::InstanceContextFactory *v25; // rax
  struct _ERESOURCE *v26; // rcx
  _QWORD *v27; // rax
  struct _IO_STATUS_BLOCK Iosb; // [rsp+40h] [rbp-30h] BYREF
  __int128 FsInformation; // [rsp+50h] [rbp-20h] BYREF
  __int64 v31; // [rsp+60h] [rbp-10h]

  Context = FltAllocateContext(a2, 2u, 0x140u, PagedPool, ReturnedContext);
  if ( Context >= 0 )
  {
    memset(*ReturnedContext, 0, 0x140u);
    v10 = *ReturnedContext;
    v10[1] = v10;
    *v10 = v10;
    *((_QWORD *)*ReturnedContext + 2) = a3;
    Context = Streaming::InstanceContext::InitDosName((Streaming::InstanceContext *)ReturnedContext, a4);
    if ( Context >= 0 )
    {
      Context = Streaming::InstanceContext::InitVolumeName((Streaming::InstanceContext *)ReturnedContext, a4);
      if ( Context >= 0 )
      {
        v13 = *ReturnedContext;
        Context = 0;
        Iosb.Status = 0;
        Pool2 = (void *)ExAllocatePool2(64, 432, 1718838899);
        if ( Pool2 )
        {
          v15 = Streaming::StreamFaultManager::StreamFaultManager(Pool2, (int *)&Iosb.0);
          Context = Iosb.Status;
          v16 = (void *)v15;
        }
        else
        {
          v16 = 0;
        }
        Iosb.Pointer = v16;
        if ( Context >= 0 )
        {
          if ( v16 )
          {
            Context = 0;
            Iosb.Pointer = (PVOID)*((_QWORD *)v13 + 31);
            *((_QWORD *)v13 + 31) = v16;
          }
          else
          {
            Context = -1073741670;
          }
        }
        appv::shared::kernel::auto_ptr<Streaming::StreamFaultManager,appv::shared::kernel::AllocDelete<Streaming::StreamFaultManager>>::~auto_ptr<Streaming::StreamFaultManager,appv::shared::kernel::AllocDelete<Streaming::StreamFaultManager>>((void **)&Iosb);
        if ( Context < 0 )
        {
          CurrentActivityID = (_QWORD *)Streaming::Utils::GetCurrentActivityID(&Iosb);
          LogWrite(
            1,
            *CurrentActivityID,
            L"InstanceContextFactory::CreateContext() - Could not attach to volume. Failure code 0x%08X.",
            (unsigned int)Context);
          Information = (volatile signed __int32 *)Iosb.Information;
          if ( Iosb.Information )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(Iosb.Information + 8), 0xFFFFFFFF) == 1 )
            {
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)Information + 8LL))(Information);
              if ( _InterlockedExchangeAdd(Information + 3, 0xFFFFFFFF) == 1 )
                goto LABEL_44;
            }
          }
          return (unsigned int)Context;
        }
        Context = Streaming::StreamFaultWriterWorker::GetInstance((char *)*ReturnedContext + 256);
        if ( Context < 0
          || (Context = Streaming::FlushRequestManager::GetInstance((char *)*ReturnedContext + 288), Context < 0)
          || (Context = Streaming::StreamingTargetFileCache::GetInstance((char *)*ReturnedContext + 272), Context < 0)
          || (Context = Streaming::PackageWriter::GetInstance((char *)*ReturnedContext + 304), Context < 0) )
        {
          v19 = (_QWORD *)Streaming::Utils::GetCurrentActivityID(&Iosb);
          LogWrite(
            1,
            *v19,
            L"InstanceContextFactory::CreateContext() - Could not attach to volume. Failure code 0x%08X.",
            (unsigned int)Context);
          goto LABEL_41;
        }
        Context = Streaming::PendingQueue::CreateInstance((char *)*ReturnedContext + 232);
        if ( Context >= 0 )
          Context = FltCbdqInitialize(
                      *((PFLT_INSTANCE *)*ReturnedContext + 2),
                      (PFLT_CALLBACK_DATA_QUEUE)((char *)*ReturnedContext + 104),
                      CsqInsertIo,
                      CsqRemoveIo,
                      CsqPeekNextIo,
                      CsqAcquire,
                      CsqRelease,
                      CsqCompleteCanceledIo);
        if ( Context >= 0 )
        {
          v31 = 0;
          Iosb = 0;
          FsInformation = 0;
          v20 = FltQueryVolumeInformation(a3, &Iosb, &FsInformation, 0x18u, FileFsSizeInformation) < 0;
          v21 = *ReturnedContext;
          if ( v20 )
          {
            v21[24] = 512;
          }
          else
          {
            v22 = 512;
            if ( HIDWORD(v31) > 0x200 )
              v22 = HIDWORD(v31);
            v21[24] = v22;
          }
          v23 = 0;
          if ( this[3] )
          {
            KeEnterCriticalRegion();
            v23 = ExAcquireResourceExclusiveLite(this[3], 1u) == 1;
          }
          v24 = (Streaming::InstanceContextFactory **)this[1];
          if ( *v24 != (Streaming::InstanceContextFactory *)this )
            __fastfail(3u);
          v25 = (Streaming::InstanceContextFactory *)*ReturnedContext;
          *(_QWORD *)v25 = this;
          *((_QWORD *)v25 + 1) = v24;
          *v24 = v25;
          this[1] = (PERESOURCE)v25;
          if ( v23 )
          {
            v26 = this[3];
            if ( v26 )
            {
              ExReleaseResourceLite(v26);
              KeLeaveCriticalRegion();
            }
          }
          Context = FltSetInstanceContext(a3, FLT_SET_CONTEXT_KEEP_IF_EXISTS, *ReturnedContext, 0);
          if ( Context >= 0 )
            return (unsigned int)Context;
          v27 = (_QWORD *)Streaming::Utils::GetCurrentActivityID(&Iosb);
          LogWrite(
            1,
            *v27,
            L"InstanceContextFactory::CreateContext() - Could not set an instance for a volume. Failure code 0x%08X.",
            (unsigned int)Context);
          goto LABEL_41;
        }
      }
      v12 = (_QWORD *)Streaming::Utils::GetCurrentActivityID(&Iosb);
      LogWrite(
        1,
        *v12,
        L"InstanceContextFactory::CreateContext() - The streaming filter could not retrieve volume name. Failure Status 0x%08X.",
        (unsigned int)Context);
    }
    else
    {
      v11 = (_QWORD *)Streaming::Utils::GetCurrentActivityID(&Iosb);
      LogWrite(
        1,
        *v11,
        L"InstanceContextFactory::CreateContext() - Couldn't get the dos name for the attached volume. Failure status = 0x%08X.",
        (unsigned int)Context);
    }
  }
  else
  {
    v9 = (_QWORD *)Streaming::Utils::GetCurrentActivityID(&Iosb);
    LogWrite(
      1,
      *v9,
      L"InstanceContextFactory::CreateContext() - Could not allocate context. Failure code 0x%08X.",
      (unsigned int)Context);
  }
LABEL_41:
  Information = (volatile signed __int32 *)Iosb.Information;
  if ( Iosb.Information )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(Iosb.Information + 8), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)Information + 8LL))(Information);
      if ( _InterlockedExchangeAdd(Information + 3, 0xFFFFFFFF) == 1 )
LABEL_44:
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)Information + 16LL))(Information);
    }
  }
  return (unsigned int)Context;
}

```

## disassembly

```asm
0x14000571c  push    rbp
0x14000571e  push    rbx
0x14000571f  push    rsi
0x140005720  push    rdi
0x140005721  push    r12
0x140005723  push    r14
0x140005725  push    r15
0x140005727  mov     rbp, rsp
0x14000572a  sub     rsp, 70h
0x14000572e  mov     rax, cs:__security_cookie
0x140005735  xor     rax, rsp
0x140005738  mov     [rbp+var_8], rax
0x14000573c  mov     rbx, [rbp+arg_20]
0x140005740  mov     rax, rdx
0x140005743  mov     edx, 2; ContextType
0x140005748  mov     [rsp+70h+ReturnedContext], rbx; ReturnedContext
0x14000574d  mov     r14, r9
0x140005750  mov     r15, r8
0x140005753  mov     rdi, rcx
0x140005756  mov     r8d, 140h; ContextSize
0x14000575c  mov     rcx, rax; Filter
0x14000575f  lea     r12d, [rdx-1]
0x140005763  mov     r9d, r12d; PoolType
0x140005766  call    cs:__imp_FltAllocateContext
0x14000576d  nop     dword ptr [rax+rax+00h]
0x140005772  mov     esi, eax
0x140005774  test    eax, eax
0x140005776  jns     short loc_14000578D
0x140005778  lea     rcx, [rbp+Iosb]
0x14000577c  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140005781  lea     r8, aInstancecontex; "InstanceContextFactory::CreateContext()"...
0x140005788  jmp     loc_140005AAE
0x14000578d  mov     rcx, [rbx]; void *
0x140005790  xor     edx, edx; Val
0x140005792  mov     r8d, 140h; Size
0x140005798  call    memset
0x14000579d  mov     rax, [rbx]
0x1400057a0  mov     rdx, r14; struct _FLT_VOLUME *
0x1400057a3  mov     rcx, rbx; this
0x1400057a6  mov     [rax+8], rax
0x1400057aa  mov     [rax], rax
0x1400057ad  mov     rax, [rbx]
0x1400057b0  mov     [rax+10h], r15
0x1400057b4  call    ?InitDosName@InstanceContext@Streaming@@QEAAJPEAU_FLT_VOLUME@@@Z; Streaming::InstanceContext::InitDosName(_FLT_VOLUME *)
0x1400057b9  mov     esi, eax
0x1400057bb  test    eax, eax
0x1400057bd  jns     short loc_1400057D4
0x1400057bf  lea     rcx, [rbp+Iosb]
0x1400057c3  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x1400057c8  lea     r8, aInstancecontex_0; "InstanceContextFactory::CreateContext()"...
0x1400057cf  jmp     loc_140005AAE
0x1400057d4  mov     rdx, r14; struct _FLT_VOLUME *
0x1400057d7  mov     rcx, rbx; this
0x1400057da  call    ?InitVolumeName@InstanceContext@Streaming@@QEAAJPEAU_FLT_VOLUME@@@Z; Streaming::InstanceContext::InitVolumeName(_FLT_VOLUME *)
0x1400057df  mov     esi, eax
0x1400057e1  test    eax, eax
0x1400057e3  jns     short loc_1400057FA
0x1400057e5  lea     rcx, [rbp+Iosb]
0x1400057e9  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x1400057ee  lea     r8, aInstancecontex_1; "InstanceContextFactory::CreateContext()"...
0x1400057f5  jmp     loc_140005AAE
0x1400057fa  mov     r14, [rbx]
0x1400057fd  xor     esi, esi
0x1400057ff  mov     edx, 1B0h
0x140005804  mov     dword ptr [rbp+Iosb], esi
0x140005807  mov     r8d, 66736673h
0x14000580d  lea     ecx, [rsi+40h]
0x140005810  call    cs:__imp_ExAllocatePool2
0x140005817  nop     dword ptr [rax+rax+00h]
0x14000581c  test    rax, rax
0x14000581f  jz      short loc_140005835
0x140005821  lea     rdx, [rbp+Iosb]; int *
0x140005825  mov     rcx, rax; StartContext
0x140005828  call    ??0StreamFaultManager@Streaming@@AEAA@AEAJ@Z; Streaming::StreamFaultManager::StreamFaultManager(long &)
0x14000582d  mov     esi, dword ptr [rbp+Iosb]
0x140005830  mov     rcx, rax
0x140005833  jmp     short loc_140005837
0x140005835  xor     ecx, ecx
0x140005837  mov     qword ptr [rbp+Iosb], rcx
0x14000583b  test    esi, esi
0x14000583d  js      short loc_14000585F
0x14000583f  test    rcx, rcx
0x140005842  jnz     short loc_14000584B
0x140005844  mov     esi, 0C000009Ah
0x140005849  jmp     short loc_14000585F
0x14000584b  mov     rax, [r14+0F8h]
0x140005852  xor     esi, esi
0x140005854  mov     qword ptr [rbp+Iosb], rax
0x140005858  mov     [r14+0F8h], rcx
0x14000585f  lea     rcx, [rbp+Iosb]
0x140005863  call    ??1?$auto_ptr@VStreamFaultManager@Streaming@@U?$AllocDelete@VStreamFaultManager@Streaming@@@kernel@shared@appv@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::auto_ptr<Streaming::StreamFaultManager,appv::shared::kernel::AllocDelete<Streaming::StreamFaultManager>>::~auto_ptr<Streaming::StreamFaultManager,appv::shared::kernel::AllocDelete<Streaming::StreamFaultManager>>(void)
0x140005868  test    esi, esi
0x14000586a  jns     short loc_1400058D3
0x14000586c  lea     rcx, [rbp+Iosb]
0x140005870  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140005875  mov     r9d, esi
0x140005878  lea     r8, aInstancecontex_3; "InstanceContextFactory::CreateContext()"...
0x14000587f  mov     ecx, r12d
0x140005882  mov     rdx, [rax]
0x140005885  call    LogWrite
0x14000588a  mov     rdi, [rbp+Iosb.Information]
0x14000588e  test    rdi, rdi
0x140005891  jz      loc_140005AFC
0x140005897  or      ebx, 0FFFFFFFFh
0x14000589a  mov     eax, ebx
0x14000589c  lock xadd [rdi+8], eax
0x1400058a1  add     eax, ebx
0x1400058a3  jnz     loc_140005AFC
0x1400058a9  mov     rax, [rdi]
0x1400058ac  mov     rcx, rdi
0x1400058af  mov     rax, [rax+8]
0x1400058b3  call    _guard_dispatch_icall
0x1400058b8  mov     edx, ebx
0x1400058ba  lock xadd [rdi+0Ch], edx
0x1400058bf  add     edx, ebx
0x1400058c1  jnz     loc_140005AFC
0x1400058c7  mov     rdx, [rdi]
0x1400058ca  mov     rax, [rdx+10h]
0x1400058ce  jmp     loc_140005AF4
0x1400058d3  mov     rcx, [rbx]
0x1400058d6  add     rcx, 100h
0x1400058dd  call    ?GetInstance@StreamFaultWriterWorker@Streaming@@SAJAEAV?$shared_ptr@VStreamFaultWriterWorker@Streaming@@@kernel_std@@@Z; Streaming::StreamFaultWriterWorker::GetInstance(kernel_std::shared_ptr<Streaming::StreamFaultWriterWorker> &)
0x1400058e2  mov     esi, eax
0x1400058e4  test    eax, eax
0x1400058e6  jns     short loc_1400058FD
0x1400058e8  lea     rcx, [rbp+Iosb]
0x1400058ec  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x1400058f1  lea     r8, aInstancecontex_3; "InstanceContextFactory::CreateContext()"...
0x1400058f8  jmp     loc_140005AAE
0x1400058fd  mov     rcx, [rbx]
0x140005900  add     rcx, 120h
0x140005907  call    ?GetInstance@FlushRequestManager@Streaming@@SAJAEAV?$shared_ptr@VFlushRequestManager@Streaming@@@kernel_std@@@Z; Streaming::FlushRequestManager::GetInstance(kernel_std::shared_ptr<Streaming::FlushRequestManager> &)
0x14000590c  mov     esi, eax
0x14000590e  test    eax, eax
0x140005910  js      short loc_1400058E8
0x140005912  mov     rcx, [rbx]
0x140005915  add     rcx, 110h
0x14000591c  call    ?GetInstance@StreamingTargetFileCache@Streaming@@SAJAEAV?$shared_ptr@VStreamingTargetFileCache@Streaming@@@kernel_std@@@Z; Streaming::StreamingTargetFileCache::GetInstance(kernel_std::shared_ptr<Streaming::StreamingTargetFileCache> &)
0x140005921  mov     esi, eax
0x140005923  test    eax, eax
0x140005925  js      short loc_1400058E8
0x140005927  mov     rcx, [rbx]
0x14000592a  add     rcx, 130h
0x140005931  call    ?GetInstance@PackageWriter@Streaming@@SAJAEAV?$shared_ptr@VPackageWriter@Streaming@@@kernel_std@@@Z; Streaming::PackageWriter::GetInstance(kernel_std::shared_ptr<Streaming::PackageWriter> &)
0x140005936  mov     esi, eax
0x140005938  test    eax, eax
0x14000593a  js      short loc_1400058E8
0x14000593c  mov     rcx, [rbx]
0x14000593f  add     rcx, 0E8h
0x140005946  call    ?CreateInstance@PendingQueue@Streaming@@SAJAEAV?$shared_ptr@VPendingQueue@Streaming@@@kernel_std@@@Z; Streaming::PendingQueue::CreateInstance(kernel_std::shared_ptr<Streaming::PendingQueue> &)
0x14000594b  mov     esi, eax
0x14000594d  test    eax, eax
0x14000594f  js      short loc_1400059A8
0x140005951  mov     rcx, [rbx]
0x140005954  lea     rax, ?CsqCompleteCanceledIo@@YAXPEAU_FLT_CALLBACK_DATA_QUEUE@@PEAU_FLT_CALLBACK_DATA@@@Z; CsqCompleteCanceledIo(_FLT_CALLBACK_DATA_QUEUE *,_FLT_CALLBACK_DATA *)
0x14000595b  mov     [rsp+70h+CbdqCompleteCanceledIo], rax; CbdqCompleteCanceledIo
0x140005960  lea     r9, ?CsqRemoveIo@@YAXPEAU_FLT_CALLBACK_DATA_QUEUE@@PEAU_FLT_CALLBACK_DATA@@@Z; CbdqRemoveIo
0x140005967  lea     rax, ?CsqRelease@@YAXPEAU_FLT_CALLBACK_DATA_QUEUE@@E@Z; CsqRelease(_FLT_CALLBACK_DATA_QUEUE *,uchar)
0x14000596e  mov     [rsp+70h+CbdqRelease], rax; CbdqRelease
0x140005973  lea     r8, ?CsqInsertIo@@YAJPEAU_FLT_CALLBACK_DATA_QUEUE@@PEAU_FLT_CALLBACK_DATA@@PEAX@Z; CbdqInsertIo
0x14000597a  lea     rax, ?CsqAcquire@@YAXPEAU_FLT_CALLBACK_DATA_QUEUE@@PEAE@Z; CsqAcquire(_FLT_CALLBACK_DATA_QUEUE *,uchar *)
0x140005981  mov     [rsp+70h+CbdqAcquire], rax; CbdqAcquire
0x140005986  lea     rdx, [rcx+68h]; Cbdq
0x14000598a  mov     rcx, [rcx+10h]; Instance
0x14000598e  lea     rax, ?CsqPeekNextIo@@YAPEAU_FLT_CALLBACK_DATA@@PEAU_FLT_CALLBACK_DATA_QUEUE@@PEAU1@PEAX@Z; CsqPeekNextIo(_FLT_CALLBACK_DATA_QUEUE *,_FLT_CALLBACK_DATA *,void *)
0x140005995  mov     [rsp+70h+ReturnedContext], rax; CbdqPeekNextIo
0x14000599a  call    cs:__imp_FltCbdqInitialize
0x1400059a1  nop     dword ptr [rax+rax+00h]
0x1400059a6  mov     esi, eax
0x1400059a8  test    esi, esi
0x1400059aa  js      loc_1400057E5
0x1400059b0  xor     eax, eax
0x1400059b2  lea     r8, [rbp+FsInformation]; FsInformation
0x1400059b6  xorps   xmm0, xmm0
0x1400059b9  mov     [rbp+var_10], rax
0x1400059bd  xorps   xmm1, xmm1
0x1400059c0  lea     rdx, [rbp+Iosb]; Iosb
0x1400059c4  mov     rcx, r15; Instance
0x1400059c7  lea     r14d, [rax+3]
0x1400059cb  lea     r9d, [rax+18h]; Length
0x1400059cf  mov     dword ptr [rsp+70h+ReturnedContext], r14d; FsInformationClass
0x1400059d4  movups  xmmword ptr [rbp+Iosb], xmm0
0x1400059d8  movups  [rbp+FsInformation], xmm1
0x1400059dc  call    cs:__imp_FltQueryVolumeInformation
0x1400059e3  nop     dword ptr [rax+rax+00h]
0x1400059e8  test    eax, eax
0x1400059ea  mov     rax, [rbx]
0x1400059ed  js      short loc_140005A00
0x1400059ef  mov     ecx, 200h
0x1400059f4  cmp     dword ptr [rbp+var_10+4], ecx
0x1400059f7  cmova   ecx, dword ptr [rbp+var_10+4]
0x1400059fb  mov     [rax+60h], ecx
0x1400059fe  jmp     short loc_140005A07
0x140005a00  mov     dword ptr [rax+60h], 200h
0x140005a07  xor     sil, sil
0x140005a0a  cmp     qword ptr [rdi+18h], 0
0x140005a0f  jz      short loc_140005A3B
0x140005a11  call    cs:__imp_KeEnterCriticalRegion
0x140005a18  nop     dword ptr [rax+rax+00h]
0x140005a1d  mov     rcx, [rdi+18h]; Resource
0x140005a21  mov     dl, r12b; Wait
0x140005a24  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140005a2b  nop     dword ptr [rax+rax+00h]
0x140005a30  cmp     al, r12b
0x140005a33  movzx   esi, sil
0x140005a37  cmovz   esi, r12d
0x140005a3b  mov     rdx, [rdi+8]
0x140005a3f  cmp     [rdx], rdi
0x140005a42  jz      short loc_140005A49
0x140005a44  mov     rcx, r14
0x140005a47  int     29h; Win8: RtlFailFast(ecx)
0x140005a49  mov     rax, [rbx]
0x140005a4c  mov     [rax], rdi
0x140005a4f  mov     [rax+8], rdx
0x140005a53  mov     [rdx], rax
0x140005a56  mov     [rdi+8], rax
0x140005a5a  test    sil, sil
0x140005a5d  jz      short loc_140005A80
0x140005a5f  mov     rcx, [rdi+18h]; Resource
0x140005a63  test    rcx, rcx
0x140005a66  jz      short loc_140005A80
0x140005a68  call    cs:__imp_ExReleaseResourceLite
0x140005a6f  nop     dword ptr [rax+rax+00h]
0x140005a74  call    cs:__imp_KeLeaveCriticalRegion
0x140005a7b  nop     dword ptr [rax+rax+00h]
0x140005a80  mov     r8, [rbx]; NewContext
0x140005a83  xor     r9d, r9d; OldContext
0x140005a86  mov     edx, r12d; Operation
0x140005a89  mov     rcx, r15; Instance
0x140005a8c  call    cs:__imp_FltSetInstanceContext
0x140005a93  nop     dword ptr [rax+rax+00h]
0x140005a98  mov     esi, eax
0x140005a9a  test    eax, eax
0x140005a9c  jns     short loc_140005AFC
0x140005a9e  lea     rcx, [rbp+Iosb]
0x140005aa2  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140005aa7  lea     r8, aInstancecontex_4; "InstanceContextFactory::CreateContext()"...
0x140005aae  mov     rdx, [rax]
0x140005ab1  mov     r9d, esi
0x140005ab4  mov     ecx, r12d
0x140005ab7  call    LogWrite
0x140005abc  mov     rdi, [rbp+Iosb.Information]
0x140005ac0  test    rdi, rdi
0x140005ac3  jz      short loc_140005AFC
0x140005ac5  or      ebx, 0FFFFFFFFh
0x140005ac8  mov     eax, ebx
0x140005aca  lock xadd [rdi+8], eax
0x140005acf  add     eax, ebx
0x140005ad1  jnz     short loc_140005AFC
0x140005ad3  mov     rax, [rdi]
0x140005ad6  mov     rcx, rdi
0x140005ad9  mov     rax, [rax+8]
0x140005add  call    _guard_dispatch_icall
0x140005ae2  mov     eax, ebx
0x140005ae4  lock xadd [rdi+0Ch], eax
0x140005ae9  add     eax, ebx
0x140005aeb  jnz     short loc_140005AFC
0x140005aed  mov     rax, [rdi]
0x140005af0  mov     rax, [rax+10h]
0x140005af4  mov     rcx, rdi
0x140005af7  call    _guard_dispatch_icall
0x140005afc  mov     eax, esi
0x140005afe  mov     rcx, [rbp+var_8]
0x140005b02  xor     rcx, rsp; StackCookie
0x140005b05  call    __security_check_cookie
0x140005b0a  add     rsp, 70h
0x140005b0e  pop     r15
0x140005b10  pop     r14
0x140005b12  pop     r12
0x140005b14  pop     rdi
0x140005b15  pop     rsi
0x140005b16  pop     rbx
0x140005b17  pop     rbp
0x140005b18  retn
```
