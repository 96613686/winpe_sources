# Container::Manager::Core::Details::ContainerObject::WorkQueueThread(_TP_CALLBACK_INSTANCE *,_TP_WORK *)

- ea: `0x1800b9b40`
- end: `0x1800b9fa8`
- name: `?WorkQueueThread@ContainerObject@Details@Core@Manager@Container@@AEAAXPEAU_TP_CALLBACK_INSTANCE@@PEAU_TP_WORK@@@Z`
- size: `1128`
- prototype: `void __fastcall(struct _GUID *this, PTP_CALLBACK_INSTANCE pci, struct _TP_WORK *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800b9fb0`

## callees

- `0x180004fc4`
- `0x180008d04`
- `0x18000a10c`
- `0x1800262c4`
- `0x180042b58`
- `0x180077dd8`
- `0x18009cec0`
- `0x18009d108`
- `0x18009d4fc`
- `0x18009f058`
- `0x1800a34a0`
- `0x1800a9908`
- `0x1800aaac0`
- `0x1800ab1c4`
- `0x1800ad564`
- `0x1800b99e0`
- `0x1800b9b40`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x1800b9d63`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x1800b9d63`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b9bee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b9e56`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b9bee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b9e56`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b9c46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b9d46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b9e7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b9ee1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b9f39`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b9c46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b9d46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b9e7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b9ee1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b9f39`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800b9f0b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800b9f0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b9bfa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b9e62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b9bfa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b9e62`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800b9bbf`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800b9bbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b9f57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b9f57`

## pseudocode

```c
void __fastcall Container::Manager::Core::Details::ContainerObject::WorkQueueThread(
        struct _GUID *this,
        PTP_CALLBACK_INSTANCE pci,
        struct _TP_WORK *a3)
{
  char v3; // r12
  const char *v4; // r9
  HANDLE *v7; // rax
  const char *v8; // r9
  unsigned __int8 *v9; // rcx
  int ***v10; // rax
  const char *v11; // r9
  int **v12; // rbx
  void *v13; // rdi
  struct _GUID **v14; // rcx
  int v15; // r8d
  int ***v16; // rax
  void *v17; // rdi
  int *v18; // r14
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  RTL_SRWLOCK *v24; // rcx
  int v25; // edi
  int v26; // eax
  DWORD CurrentThreadId; // eax
  PSRWLOCK v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rcx
  RTL_SRWLOCK *v31; // rcx
  RTL_SRWLOCK *v32; // rcx
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-58h]
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-38h] BYREF
  void *v35; // [rsp+48h] [rbp-30h] BYREF
  __int128 v36; // [rsp+50h] [rbp-28h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-18h] BYREF
  unsigned int v38; // [rsp+68h] [rbp-10h]
  char v39; // [rsp+6Ch] [rbp-Ch]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  void *v41; // [rsp+D8h] [rbp+60h] BYREF

  v3 = 0;
  v38 = 3;
  hObject = 0;
  v36 = 0;
  v39 = 0;
  LODWORD(v4) = 0;
  while ( a3 != *((struct _TP_WORK **)&this[63].Data1 + (unsigned int)v4) )
  {
    v4 = (const char *)(unsigned int)((_DWORD)v4 + 1);
    if ( (unsigned int)v4 >= 3 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1F00,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        v4);
  }
  v38 = (unsigned int)v4;
  v7 = (HANDLE *)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hObject);
  if ( !DuplicateHandle(
          (HANDLE)0xFFFFFFFFFFFFFFFFLL,
          (HANDLE)0xFFFFFFFFFFFFFFFELL,
          (HANDLE)0xFFFFFFFFFFFFFFFFLL,
          v7,
          0x400u,
          0,
          0) )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x1F0B,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      v8);
  AcquireSRWLockExclusive((PSRWLOCK)this[28].Data4);
  SRWLock = (PSRWLOCK)this[28].Data4;
  this[29].Data1 = GetCurrentThreadId();
  v9 = &this[64].Data4[24 * v38];
  if ( *((_DWORD *)v9 + 4) )
  {
    LOBYTE(v41) = 0;
    v16 = (int ***)Csl::List<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>::PopFront(
                     v9,
                     &v35);
    v12 = *v16;
    *v16 = 0;
    v17 = v35;
    v35 = 0;
    if ( v17 )
    {
      Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>::~ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>(v17);
      operator delete(v17, (const struct std::nothrow_t *)0x20);
    }
  }
  else
  {
    if ( !this[70].Data1 )
    {
      if ( this != (struct _GUID *)-456LL )
      {
        this[29].Data1 = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)this[28].Data4);
        SRWLock = 0;
      }
      goto LABEL_67;
    }
    v10 = (int ***)Csl::List<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>::PopFront(
                     &this[69],
                     &v41);
    v12 = *v10;
    *v10 = 0;
    v13 = v41;
    v41 = 0;
    if ( v13 )
    {
      Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>::~ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>(v13);
      operator delete(v13, (const struct std::nothrow_t *)0x20);
    }
    v14 = *(struct _GUID ***)this[71].Data4;
    if ( *v14 != &this[71] )
      goto LABEL_70;
    *((_QWORD *)&v36 + 1) = *(_QWORD *)this[71].Data4;
    *(_QWORD *)&v36 = this + 71;
    *v14 = (struct _GUID *)&v36;
    *(_QWORD *)this[71].Data4 = &v36;
    v15 = *(_DWORD *)this[70].Data4;
    LOBYTE(v41) = 1;
    if ( v38 != v15 )
      Container::Manager::Core::Details::ContainerObject::UpdateWorkQueueThreadPriorityIfNecessary(&v36, &v36);
  }
  v18 = *v12;
  v19 = **v12;
  if ( v19 )
  {
    v20 = v19 - 1;
    if ( v20 )
    {
      v21 = v20 - 1;
      if ( v21 )
      {
        v22 = v21 - 1;
        if ( v22 )
        {
          v23 = v22 - 1;
          if ( v23 )
          {
            if ( (unsigned int)(v23 - 1) > 1 )
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x1F5A,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
                v11);
          }
        }
      }
      else
      {
        v24 = SRWLock;
        if ( SRWLock )
        {
          LODWORD(SRWLock[1].Ptr) = 0;
          ReleaseSRWLockExclusive(v24);
          SRWLock = 0;
        }
        v3 = 1;
      }
    }
  }
  if ( (v18[1] & 1) != 0 && !CallbackMayRunLong(pci) )
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x1F64,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x8007000ELL,
      dwDesiredAccess);
  switch ( *v18 )
  {
    case 0:
      Container::Manager::Core::Details::ContainerObject::DeferredTerminateOnExit((Container::Manager::Core::Details::ContainerObject *)this);
LABEL_53:
      v25 = 0;
      goto LABEL_54;
    case 1:
      if ( *((_BYTE *)v18 + 48) )
        __int2c();
      Container::Manager::Core::Details::ContainerObject::ProcessMirrorNetworkWorkItem(
        this,
        (__int64)(v18 + 2),
        (char *)&SRWLock);
      goto LABEL_53;
    case 2:
      if ( *((_BYTE *)v18 + 48) != 1 )
        __int2c();
      v26 = Container::Manager::Core::Details::ContainerObject::ResizeMemory(
              (Container::Manager::Core::Details::ContainerObject *)this,
              (const struct Container::Manager::Core::Details::ContainerObject::ResizeMemoryWorkItem *)(v18 + 2));
      break;
    case 3:
      if ( *((_BYTE *)v18 + 48) != 2 )
        __int2c();
      v26 = Container::Manager::Core::Details::ContainerObject::ApplyInitialGpuConfiguration((Container::Manager::Core::Details::ContainerObject *)this);
      break;
    case 4:
      v26 = Container::Manager::Core::Details::ContainerObject::CheckUpdateRuntimeFeatureConfigurations(this);
      break;
    case 5:
      v26 = Container::Manager::Core::Details::ContainerObject::CheckUpdateHotPatches(this);
      break;
    case 6:
      v26 = Container::Manager::Core::Details::ContainerObject::MapEdgeToContainer((Container::Manager::Core::Details::ContainerObject *)this);
      break;
    default:
      v25 = -2147418113;
      goto LABEL_54;
  }
  v25 = v26;
LABEL_54:
  if ( v3 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)this[28].Data4);
    CurrentThreadId = GetCurrentThreadId();
    v28 = SRWLock;
    this[29].Data1 = CurrentThreadId;
    if ( v28 )
    {
      LODWORD(v28[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v28);
    }
    SRWLock = (PSRWLOCK)this[28].Data4;
  }
  Container::Manager::Core::Details::ContainerObject::OnWorkItemCompleted(
    (Container::Manager::Core::Details::ContainerObject *)this,
    (struct Container::Manager::Core::Details::ContainerObject::WorkItem *)v18,
    v25);
  if ( !(_BYTE)v41 )
    goto LABEL_65;
  v29 = v36;
  if ( *(__int128 **)(v36 + 8) != &v36 || (v30 = *((_QWORD *)&v36 + 1), **((__int128 ***)&v36 + 1) != &v36) )
LABEL_70:
    __fastfail(3u);
  **((_QWORD **)&v36 + 1) = v36;
  *(_QWORD *)(v29 + 8) = v30;
  v31 = SRWLock;
  v36 = 0;
  if ( SRWLock )
  {
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v31);
    SRWLock = 0;
  }
  if ( v39 )
    SetThreadPriority(
      (HANDLE)0xFFFFFFFFFFFFFFFELL,
      *((_DWORD *)&Container::Manager::Core::Details::ContainerObject::s_workItemPriorityToWorkQueueThreadPriority + v38));
LABEL_65:
  Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>::~ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>(v12);
  operator delete(v12, (const struct std::nothrow_t *)0x20);
  v32 = SRWLock;
  if ( SRWLock )
  {
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v32);
    SRWLock = 0;
  }
LABEL_67:
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x1800b9b40  push    rbp
0x1800b9b42  push    rbx
0x1800b9b43  push    rsi
0x1800b9b44  push    rdi
0x1800b9b45  push    r12
0x1800b9b47  push    r13
0x1800b9b49  push    r14
0x1800b9b4b  push    r15
0x1800b9b4d  mov     rbp, rsp
0x1800b9b50  sub     rsp, 78h
0x1800b9b54  xor     r12d, r12d
0x1800b9b57  mov     [rbp+var_10], 3
0x1800b9b5e  xorps   xmm0, xmm0
0x1800b9b61  mov     [rbp+hObject], r12
0x1800b9b65  movups  [rbp+var_28], xmm0
0x1800b9b69  mov     [rbp+var_C], r12b
0x1800b9b6d  mov     r9d, r12d
0x1800b9b70  mov     r13, rdx
0x1800b9b73  mov     rsi, rcx
0x1800b9b76  mov     eax, r9d
0x1800b9b79  cmp     r8, [rcx+rax*8+3F0h]
0x1800b9b81  jz      short loc_1800B9B92
0x1800b9b83  inc     r9d; char *
0x1800b9b86  cmp     r9d, 3
0x1800b9b8a  jnb     loc_1800B9F7C
0x1800b9b90  jmp     short loc_1800B9B76
0x1800b9b92  lea     rcx, [rbp+hObject]
0x1800b9b96  mov     [rbp+var_10], r9d
0x1800b9b9a  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x1800b9b9f  or      rcx, 0FFFFFFFFFFFFFFFFh; hSourceProcessHandle
0x1800b9ba3  mov     [rsp+78h+dwOptions], r12d; dwOptions
0x1800b9ba8  mov     r9, rax; lpTargetHandle
0x1800b9bab  mov     [rsp+78h+bInheritHandle], r12d; bInheritHandle
0x1800b9bb0  mov     r8, rcx; hTargetProcessHandle
0x1800b9bb3  mov     [rsp+78h+dwDesiredAccess], 400h; int
0x1800b9bbb  lea     rdx, [rcx-1]; hSourceHandle
0x1800b9bbf  call    cs:__imp_DuplicateHandle
0x1800b9bc6  nop     dword ptr [rax+rax+00h]
0x1800b9bcb  test    eax, eax
0x1800b9bcd  jnz     short loc_1800B9BE4
0x1800b9bcf  mov     rcx, [rbp+40h]; this
0x1800b9bd3  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800b9bda  mov     edx, 1F0Bh; void *
0x1800b9bdf  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800b9be4  lea     r15, [rsi+1C8h]
0x1800b9beb  mov     rcx, r15; SRWLock
0x1800b9bee  call    cs:__imp_AcquireSRWLockExclusive
0x1800b9bf5  nop     dword ptr [rax+rax+00h]
0x1800b9bfa  call    cs:__imp_GetCurrentThreadId
0x1800b9c01  nop     dword ptr [rax+rax+00h]
0x1800b9c06  mov     [rbp+SRWLock], r15
0x1800b9c0a  mov     r14d, 20h ; ' '
0x1800b9c10  mov     [r15+8], eax
0x1800b9c14  mov     eax, [rbp+var_10]
0x1800b9c17  add     rax, 2Bh ; '+'
0x1800b9c1b  lea     rax, [rax+rax*2]
0x1800b9c1f  lea     rcx, [rsi+rax*8]
0x1800b9c23  cmp     [rcx+10h], r12d
0x1800b9c27  jnz     loc_1800B9CD8
0x1800b9c2d  cmp     [rsi+460h], r12d
0x1800b9c34  jnz     short loc_1800B9C5B
0x1800b9c36  test    r15, r15
0x1800b9c39  jz      loc_1800B9F49
0x1800b9c3f  mov     rcx, r15; SRWLock
0x1800b9c42  mov     [r15+8], r12d
0x1800b9c46  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b9c4d  nop     dword ptr [rax+rax+00h]
0x1800b9c52  mov     [rbp+SRWLock], r12
0x1800b9c56  jmp     loc_1800B9F49
0x1800b9c5b  lea     rcx, [rsi+450h]
0x1800b9c62  lea     rdx, [rbp+arg_18]
0x1800b9c66  call    ?PopFront@?$List@V?$unique_ptr@UWorkItem@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UWorkItem@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@Csl@@QEAA?AV?$unique_ptr@V?$ListEntry@V?$unique_ptr@UWorkItem@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UWorkItem@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@Csl@@U?$default_delete@V?$ListEntry@V?$unique_ptr@UWorkItem@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UWorkItem@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@Csl@@@wistd@@@wistd@@XZ; Csl::List<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>::PopFront(void)
0x1800b9c6b  mov     rbx, [rax]
0x1800b9c6e  mov     [rax], r12
0x1800b9c71  mov     rdi, [rbp+arg_18]
0x1800b9c75  mov     [rbp+arg_18], r12
0x1800b9c79  test    rdi, rdi
0x1800b9c7c  jz      short loc_1800B9C91
0x1800b9c7e  mov     rcx, rdi
0x1800b9c81  call    ??1?$ListEntry@V?$unique_ptr@UWorkItem@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UWorkItem@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@Csl@@QEAA@XZ; Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>::~ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>(void)
0x1800b9c86  mov     rdx, r14; struct std::nothrow_t *
0x1800b9c89  mov     rcx, rdi; void *
0x1800b9c8c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b9c91  lea     rax, [rsi+470h]
0x1800b9c98  mov     rcx, [rax+8]
0x1800b9c9c  cmp     [rcx], rax
0x1800b9c9f  jnz     loc_1800B9F75
0x1800b9ca5  mov     qword ptr [rbp+var_28+8], rcx
0x1800b9ca9  lea     rdx, [rbp+var_28]
0x1800b9cad  mov     qword ptr [rbp+var_28], rax
0x1800b9cb1  mov     [rcx], rdx
0x1800b9cb4  lea     rcx, [rbp+var_28]
0x1800b9cb8  mov     [rax+8], rcx
0x1800b9cbc  mov     r8d, [rsi+468h]
0x1800b9cc3  mov     byte ptr [rbp+arg_18], 1
0x1800b9cc7  cmp     [rbp+var_10], r8d
0x1800b9ccb  jz      short loc_1800B9D0B
0x1800b9ccd  lea     rdx, [rbp+var_28]
0x1800b9cd1  call    ?UpdateWorkQueueThreadPriorityIfNecessary@ContainerObject@Details@Core@Manager@Container@@AEBAXAEAUWorkQueueThreadControlBlock@12345@W4WorkItemPriority@12345@@Z; Container::Manager::Core::Details::ContainerObject::UpdateWorkQueueThreadPriorityIfNecessary(Container::Manager::Core::Details::ContainerObject::WorkQueueThreadControlBlock &,Container::Manager::Core::Details::ContainerObject::WorkItemPriority)
0x1800b9cd6  jmp     short loc_1800B9D0B
0x1800b9cd8  lea     rdx, [rbp+var_30]
0x1800b9cdc  mov     byte ptr [rbp+arg_18], r12b
0x1800b9ce0  call    ?PopFront@?$List@V?$unique_ptr@UWorkItem@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UWorkItem@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@Csl@@QEAA?AV?$unique_ptr@V?$ListEntry@V?$unique_ptr@UWorkItem@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UWorkItem@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@Csl@@U?$default_delete@V?$ListEntry@V?$unique_ptr@UWorkItem@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UWorkItem@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@Csl@@@wistd@@@wistd@@XZ; Csl::List<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>::PopFront(void)
0x1800b9ce5  mov     rbx, [rax]
0x1800b9ce8  mov     [rax], r12
0x1800b9ceb  mov     rdi, [rbp+var_30]
0x1800b9cef  mov     [rbp+var_30], r12
0x1800b9cf3  test    rdi, rdi
0x1800b9cf6  jz      short loc_1800B9D0B
0x1800b9cf8  mov     rcx, rdi
0x1800b9cfb  call    ??1?$ListEntry@V?$unique_ptr@UWorkItem@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UWorkItem@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@Csl@@QEAA@XZ; Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>::~ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>(void)
0x1800b9d00  mov     rdx, r14; struct std::nothrow_t *
0x1800b9d03  mov     rcx, rdi; void *
0x1800b9d06  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b9d0b  mov     r14, [rbx]
0x1800b9d0e  mov     ecx, [r14]
0x1800b9d11  test    ecx, ecx
0x1800b9d13  jz      short loc_1800B9D59
0x1800b9d15  sub     ecx, 1
0x1800b9d18  jz      short loc_1800B9D59
0x1800b9d1a  sub     ecx, 1
0x1800b9d1d  jz      short loc_1800B9D39
0x1800b9d1f  sub     ecx, 1
0x1800b9d22  jz      short loc_1800B9D59
0x1800b9d24  sub     ecx, 1
0x1800b9d27  jz      short loc_1800B9D59
0x1800b9d29  sub     ecx, 1
0x1800b9d2c  jz      short loc_1800B9D59
0x1800b9d2e  cmp     ecx, 1
0x1800b9d31  jnz     loc_1800B9F92
0x1800b9d37  jmp     short loc_1800B9D59
0x1800b9d39  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800b9d3d  test    rcx, rcx
0x1800b9d40  jz      short loc_1800B9D56
0x1800b9d42  mov     [rcx+8], r12d
0x1800b9d46  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b9d4d  nop     dword ptr [rax+rax+00h]
0x1800b9d52  mov     [rbp+SRWLock], r12
0x1800b9d56  mov     r12b, 1
0x1800b9d59  test    byte ptr [r14+4], 1
0x1800b9d5e  jz      short loc_1800B9D93
0x1800b9d60  mov     rcx, r13; pci
0x1800b9d63  call    cs:__imp_CallbackMayRunLong
0x1800b9d6a  nop     dword ptr [rax+rax+00h]
0x1800b9d6f  xor     r13d, r13d
0x1800b9d72  test    eax, eax
0x1800b9d74  jnz     short loc_1800B9D96
0x1800b9d76  mov     rcx, [rbp+40h]; this
0x1800b9d7a  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800b9d81  mov     r9d, 8007000Eh; char *
0x1800b9d87  mov     edx, 1F64h; void *
0x1800b9d8c  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800b9d91  jmp     short loc_1800B9D96
0x1800b9d93  xor     r13d, r13d
0x1800b9d96  mov     ecx, [r14]
0x1800b9d99  test    ecx, ecx
0x1800b9d9b  jz      loc_1800B9E3F
0x1800b9da1  sub     ecx, 1
0x1800b9da4  jz      short loc_1800B9E25
0x1800b9da6  sub     ecx, 1
0x1800b9da9  jz      short loc_1800B9E0D
0x1800b9dab  sub     ecx, 1
0x1800b9dae  jz      short loc_1800B9DF3
0x1800b9db0  sub     ecx, 1
0x1800b9db3  jz      short loc_1800B9DE5
0x1800b9db5  sub     ecx, 1
0x1800b9db8  jz      short loc_1800B9DD7
0x1800b9dba  cmp     ecx, 1
0x1800b9dbd  jz      short loc_1800B9DC9
0x1800b9dbf  mov     edi, 8000FFFFh
0x1800b9dc4  jmp     loc_1800B9E4E
0x1800b9dc9  lea     rdx, [rbp+SRWLock]
0x1800b9dcd  mov     rcx, rsi; this
0x1800b9dd0  call    ?MapEdgeToContainer@ContainerObject@Details@Core@Manager@Container@@AEAAJAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::MapEdgeToContainer(Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800b9dd5  jmp     short loc_1800B9E21
0x1800b9dd7  lea     rdx, [rbp+SRWLock]
0x1800b9ddb  mov     rcx, rsi; struct _GUID *
0x1800b9dde  call    ?CheckUpdateHotPatches@ContainerObject@Details@Core@Manager@Container@@AEAAJAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::CheckUpdateHotPatches(Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800b9de3  jmp     short loc_1800B9E21
0x1800b9de5  lea     rdx, [rbp+SRWLock]
0x1800b9de9  mov     rcx, rsi; struct _GUID *
0x1800b9dec  call    ?CheckUpdateRuntimeFeatureConfigurations@ContainerObject@Details@Core@Manager@Container@@AEAAJAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::CheckUpdateRuntimeFeatureConfigurations(Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800b9df1  jmp     short loc_1800B9E21
0x1800b9df3  lea     rdx, [r14+8]
0x1800b9df7  cmp     byte ptr [rdx+28h], 2
0x1800b9dfb  jz      short loc_1800B9DFF
0x1800b9dfd  int     2Ch; Windows NT - assertion failure
0x1800b9dff  lea     r8, [rbp+SRWLock]
0x1800b9e03  mov     rcx, rsi
0x1800b9e06  call    ?ApplyInitialGpuConfiguration@ContainerObject@Details@Core@Manager@Container@@AEAAJAEBUApplyInitialGpuConfigurationWorkItem@12345@AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::ApplyInitialGpuConfiguration(Container::Manager::Core::Details::ContainerObject::ApplyInitialGpuConfigurationWorkItem const &,Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800b9e0b  jmp     short loc_1800B9E21
0x1800b9e0d  lea     rdx, [r14+8]; struct Container::Manager::Core::Details::ContainerObject::ResizeMemoryWorkItem *
0x1800b9e11  cmp     byte ptr [rdx+28h], 1
0x1800b9e15  jz      short loc_1800B9E19
0x1800b9e17  int     2Ch; Windows NT - assertion failure
0x1800b9e19  mov     rcx, rsi; this
0x1800b9e1c  call    ?ResizeMemory@ContainerObject@Details@Core@Manager@Container@@AEAAJAEBUResizeMemoryWorkItem@12345@@Z; Container::Manager::Core::Details::ContainerObject::ResizeMemory(Container::Manager::Core::Details::ContainerObject::ResizeMemoryWorkItem const &)
0x1800b9e21  mov     edi, eax
0x1800b9e23  jmp     short loc_1800B9E4E
0x1800b9e25  lea     rdx, [r14+8]
0x1800b9e29  cmp     [rdx+28h], r13b
0x1800b9e2d  jz      short loc_1800B9E31
0x1800b9e2f  int     2Ch; Windows NT - assertion failure
0x1800b9e31  lea     r8, [rbp+SRWLock]
0x1800b9e35  mov     rcx, rsi; struct _GUID *
0x1800b9e38  call    ?ProcessMirrorNetworkWorkItem@ContainerObject@Details@Core@Manager@Container@@AEAAXAEAUMirrorNetworkWorkItem@12345@AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::ProcessMirrorNetworkWorkItem(Container::Manager::Core::Details::ContainerObject::MirrorNetworkWorkItem &,Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800b9e3d  jmp     short loc_1800B9E4B
0x1800b9e3f  lea     rdx, [rbp+SRWLock]
0x1800b9e43  mov     rcx, rsi
0x1800b9e46  call    ?DeferredTerminateOnExit@ContainerObject@Details@Core@Manager@Container@@AEAAXAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::DeferredTerminateOnExit(Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800b9e4b  mov     edi, r13d
0x1800b9e4e  test    r12b, r12b
0x1800b9e51  jz      short loc_1800B9E8F
0x1800b9e53  mov     rcx, r15; SRWLock
0x1800b9e56  call    cs:__imp_AcquireSRWLockExclusive
0x1800b9e5d  nop     dword ptr [rax+rax+00h]
0x1800b9e62  call    cs:__imp_GetCurrentThreadId
0x1800b9e69  nop     dword ptr [rax+rax+00h]
0x1800b9e6e  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800b9e72  mov     [r15+8], eax
0x1800b9e76  test    rcx, rcx
0x1800b9e79  jz      short loc_1800B9E8B
0x1800b9e7b  mov     [rcx+8], r13d
0x1800b9e7f  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b9e86  nop     dword ptr [rax+rax+00h]
0x1800b9e8b  mov     [rbp+SRWLock], r15
0x1800b9e8f  mov     r8d, edi; int
0x1800b9e92  mov     rdx, r14; struct Container::Manager::Core::Details::ContainerObject::WorkItem *
0x1800b9e95  mov     rcx, rsi; this
0x1800b9e98  call    ?OnWorkItemCompleted@ContainerObject@Details@Core@Manager@Container@@AEAAXAEAUWorkItem@12345@J@Z; Container::Manager::Core::Details::ContainerObject::OnWorkItemCompleted(Container::Manager::Core::Details::ContainerObject::WorkItem &,long)
0x1800b9e9d  cmp     byte ptr [rbp+arg_18], r13b
0x1800b9ea1  jz      short loc_1800B9F17
0x1800b9ea3  mov     rax, qword ptr [rbp+var_28]
0x1800b9ea7  lea     rcx, [rbp+var_28]
0x1800b9eab  cmp     [rax+8], rcx
0x1800b9eaf  jnz     loc_1800B9F75
0x1800b9eb5  mov     rcx, qword ptr [rbp+var_28+8]
0x1800b9eb9  lea     rdx, [rbp+var_28]
0x1800b9ebd  cmp     [rcx], rdx
0x1800b9ec0  jnz     loc_1800B9F75
0x1800b9ec6  mov     [rcx], rax
0x1800b9ec9  xorps   xmm0, xmm0
0x1800b9ecc  mov     [rax+8], rcx
0x1800b9ed0  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800b9ed4  movups  [rbp+var_28], xmm0
0x1800b9ed8  test    rcx, rcx
0x1800b9edb  jz      short loc_1800B9EF1
0x1800b9edd  mov     [rcx+8], r13d
0x1800b9ee1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b9ee8  nop     dword ptr [rax+rax+00h]
0x1800b9eed  mov     [rbp+SRWLock], r13
0x1800b9ef1  cmp     [rbp+var_C], r13b
0x1800b9ef5  jz      short loc_1800B9F17
0x1800b9ef7  mov     edx, [rbp+var_10]
0x1800b9efa  lea     rax, ?s_workItemPriorityToWorkQueueThreadPriority@ContainerObject@Details@Core@Manager@Container@@0QBJB; long const near * const Container::Manager::Core::Details::ContainerObject::s_workItemPriorityToWorkQueueThreadPriority
0x1800b9f01  mov     rcx, 0FFFFFFFFFFFFFFFEh; hThread
0x1800b9f08  mov     edx, [rax+rdx*4]; nPriority
0x1800b9f0b  call    cs:__imp_SetThreadPriority
0x1800b9f12  nop     dword ptr [rax+rax+00h]
0x1800b9f17  mov     rcx, rbx
0x1800b9f1a  call    ??1?$ListEntry@V?$unique_ptr@UWorkItem@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UWorkItem@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@Csl@@QEAA@XZ; Csl::ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>::~ListEntry<wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::WorkItem,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::WorkItem>>>(void)
0x1800b9f1f  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x1800b9f24  mov     rcx, rbx; void *
0x1800b9f27  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b9f2c  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800b9f30  test    rcx, rcx
0x1800b9f33  jz      short loc_1800B9F49
0x1800b9f35  mov     [rcx+8], r13d
0x1800b9f39  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b9f40  nop     dword ptr [rax+rax+00h]
0x1800b9f45  mov     [rbp+SRWLock], r13
0x1800b9f49  mov     rcx, [rbp+hObject]; hObject
0x1800b9f4d  lea     rax, [rcx-1]
0x1800b9f51  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800b9f55  ja      short loc_1800B9F63
0x1800b9f57  call    cs:__imp_CloseHandle
0x1800b9f5e  nop     dword ptr [rax+rax+00h]
0x1800b9f63  add     rsp, 78h
0x1800b9f67  pop     r15
0x1800b9f69  pop     r14
0x1800b9f6b  pop     r13
0x1800b9f6d  pop     r12
0x1800b9f6f  pop     rdi
0x1800b9f70  pop     rsi
0x1800b9f71  pop     rbx
0x1800b9f72  pop     rbp
0x1800b9f73  retn
0x1800b9f75  mov     ecx, 3
0x1800b9f7a  int     29h; Win8: RtlFailFast(ecx)
0x1800b9f7c  mov     rcx, [rbp+40h]; this
0x1800b9f80  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800b9f87  mov     edx, 1F00h; void *
0x1800b9f8c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800b9f92  mov     rcx, [rbp+40h]; this
0x1800b9f96  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800b9f9d  mov     edx, 1F5Ah; void *
0x1800b9fa2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
