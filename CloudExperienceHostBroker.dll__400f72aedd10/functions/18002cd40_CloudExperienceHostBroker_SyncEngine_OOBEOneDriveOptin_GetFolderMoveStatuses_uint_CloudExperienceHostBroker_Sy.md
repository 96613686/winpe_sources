# CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin::GetFolderMoveStatuses(uint *,CloudExperienceHostBroker::SyncEngine::OneDriveKnownFolderMoveStatusEntry * *)

- ea: `0x18002cd40`
- end: `0x18002cf31`
- name: `?GetFolderMoveStatuses@OOBEOneDriveOptin@SyncEngine@CloudExperienceHostBroker@@UEAAJPEAIPEAPEAUOneDriveKnownFolderMoveStatusEntry@23@@Z`
- size: `497`
- prototype: `__int64 __fastcall(CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin *__hidden this, unsigned int *, struct CloudExperienceHostBroker::SyncEngine::OneDriveKnownFolderMoveStatusEntry **)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180004760`
- `0x180007df0`
- `0x180008344`
- `0x1800084e8`
- `0x180028a64`
- `0x180029e88`
- `0x180029ea4`
- `0x18002a830`
- `0x18002a848`
- `0x18002a954`
- `0x18002a9a4`
- `0x18002cd40`
- `0x18003026c`
- `0x180030384`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002cd7a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002cd7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ce60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ce60`

## string_xrefs

- `0x18002cdc9`: `shell\cloudexperiencehost\broker\lib\oobesyncengineapi.cpp`
- `0x18002ce2b`: `shell\cloudexperiencehost\broker\lib\oobesyncengineapi.cpp`
- `0x18002ce88`: `shell\cloudexperiencehost\broker\lib\oobesyncengineapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin::GetFolderMoveStatuses(
        RTL_SRWLOCK *this,
        unsigned int *a2,
        struct CloudExperienceHostBroker::SyncEngine::OneDriveKnownFolderMoveStatusEntry **a3)
{
  RTL_SRWLOCK *v6; // rbx
  const struct _GUID *v7; // rcx
  int v8; // eax
  int v9; // ebx
  __int64 v10; // rax
  __int64 v11; // r9
  __int64 (__fastcall *v12)(__int64, __int64, __int64 *); // r10
  unsigned __int64 v13; // rbx
  LPVOID v14; // rax
  unsigned int i; // r10d
  __int128 v16; // xmm0
  unsigned int v17; // r10d
  unsigned int v18; // r10d
  __int64 v19; // rax
  __int64 v20; // r8
  int v21; // r10d
  __int64 v23; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int64 v24; // [rsp+28h] [rbp-18h]
  __int64 v25; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v26; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  void *v28; // [rsp+60h] [rbp+20h] BYREF
  RTL_SRWLOCK *v29; // [rsp+68h] [rbp+28h] BYREF

  *a2 = 0;
  *a3 = 0;
  v28 = 0;
  v6 = this + 14;
  AcquireSRWLockShared(this + 14);
  v29 = v6;
  wil::com_ptr_t<IOneDriveKnownFolderManager,wil::err_exception_policy>::operator=(&v28, &this[15]);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v29);
  if ( v28
    || (wil::com_ptr_t<IOneDriveKnownFolderManager,wil::err_exception_policy>::reset(&v28),
        v8 = CloudExperienceHostCreateOOBEUserObjectForceBroker(v7, &GUID_3cbc1a7c_61d0_48a5_aea3_e34114d5cc66, &v28),
        v9 = v8,
        v8 >= 0) )
  {
    wil::unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(&v23);
    v10 = wil::unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::size_address<unsigned int>(
            (__int64)&v23,
            (__int64)&v25);
    v9 = v12(v11, v10 + 8, &v23);
    wil::unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::size_address_ptr<unsigned int>::~size_address_ptr<unsigned int>(&v25);
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DD,
        (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobesyncengineapi.cpp",
        (const char *)(unsigned int)v9,
        v23);
LABEL_6:
      wil::unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(&v23);
      goto LABEL_14;
    }
    v13 = v24;
    if ( v24 )
    {
      v14 = CoTaskMemAlloc(20 * v24);
      wil::unique_any_array_ptr<CloudExperienceHostBroker::SyncEngine::OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<CloudExperienceHostBroker::SyncEngine::OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(
        &v25,
        (__int64)v14,
        v13);
      if ( !v25 )
      {
        v9 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E6,
          (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobesyncengineapi.cpp",
          (const char *)0x8007000ELL,
          v23);
        wil::unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(&v25);
        goto LABEL_6;
      }
      for ( i = 0; i < v13; i = v21 + 1 )
      {
        v16 = *(_OWORD *)wil::unique_any_array_ptr<CloudExperienceHostBroker::SyncEngine::OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator[](
                           &v23,
                           i);
        *(_OWORD *)wil::unique_any_array_ptr<CloudExperienceHostBroker::SyncEngine::OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator[](
                     &v25,
                     v17) = v16;
        v19 = wil::unique_any_array_ptr<CloudExperienceHostBroker::SyncEngine::OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator[](
                &v23,
                v18);
        *(_DWORD *)(v20 + 16) = *(_DWORD *)(v19 + 16);
      }
      *a2 = v26;
      *a3 = (struct CloudExperienceHostBroker::SyncEngine::OneDriveKnownFolderMoveStatusEntry *)wil::unique_any_array_ptr<CloudExperienceHostBroker::SyncEngine::OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::release(&v25);
      wil::unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(&v25);
    }
    wil::unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(&v23);
    v9 = 0;
    goto LABEL_14;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1D8,
    (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobesyncengineapi.cpp",
    (const char *)(unsigned int)v8,
    v23);
LABEL_14:
  wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(&v28);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002cd40  mov     [rsp-18h+arg_10], rbx
0x18002cd45  mov     [rsp-18h+arg_18], rsi
0x18002cd4a  push    rbp
0x18002cd4b  push    rdi
0x18002cd4c  push    r14
0x18002cd4e  mov     rbp, rsp
0x18002cd51  sub     rsp, 40h
0x18002cd55  mov     rsi, r8
0x18002cd58  mov     r14, rdx
0x18002cd5b  mov     rdi, rcx
0x18002cd5e  mov     dword ptr [rdx], 0
0x18002cd64  mov     qword ptr [r8], 0
0x18002cd6b  mov     [rbp+arg_0], 0
0x18002cd73  lea     rbx, [rcx+70h]
0x18002cd77  mov     rcx, rbx; SRWLock
0x18002cd7a  call    cs:__imp_AcquireSRWLockShared
0x18002cd80  mov     [rbp+arg_8], rbx
0x18002cd84  lea     rdx, [rdi+78h]
0x18002cd88  lea     rcx, [rbp+arg_0]
0x18002cd8c  call    ??4?$com_ptr_t@UIOneDriveKnownFolderManager@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<IOneDriveKnownFolderManager,wil::err_exception_policy>::operator=(wil::com_ptr_t<IOneDriveKnownFolderManager,wil::err_exception_policy> const &)
0x18002cd91  lea     rcx, [rbp+arg_8]
0x18002cd95  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002cd9a  mov     r9, [rbp+arg_0]
0x18002cd9e  test    r9, r9
0x18002cda1  jnz     short loc_18002CDE3
0x18002cda3  lea     rcx, [rbp+arg_0]
0x18002cda7  call    ?reset@?$com_ptr_t@UIOneDriveKnownFolderManager@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IOneDriveKnownFolderManager,wil::err_exception_policy>::reset(void)
0x18002cdac  lea     r8, [rbp+arg_0]; void **
0x18002cdb0  lea     rdx, _GUID_3cbc1a7c_61d0_48a5_aea3_e34114d5cc66; struct _GUID *
0x18002cdb7  call    ?CloudExperienceHostCreateOOBEUserObjectForceBroker@@YAJAEBU_GUID@@0PEAPEAX@Z; CloudExperienceHostCreateOOBEUserObjectForceBroker(_GUID const &,_GUID const &,void * *)
0x18002cdbc  mov     ebx, eax
0x18002cdbe  test    eax, eax
0x18002cdc0  jns     short loc_18002CDDF
0x18002cdc2  mov     rcx, [rbp+18h]; this
0x18002cdc6  mov     r9d, eax; char *
0x18002cdc9  lea     r8, aShellCloudexpe; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002cdd0  mov     edx, 1D8h; void *
0x18002cdd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cdda  jmp     loc_18002CF13
0x18002cddf  mov     r9, [rbp+arg_0]
0x18002cde3  lea     rcx, [rbp+var_20]
0x18002cde7  call    ??0?$unique_any_array_ptr@UOneDriveKnownFolderMoveStatusEntry@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)
0x18002cdec  nop
0x18002cded  mov     rax, [r9]
0x18002cdf0  mov     r10, [rax+30h]
0x18002cdf4  lea     rdx, [rbp+var_10]
0x18002cdf8  lea     rcx, [rbp+var_20]
0x18002cdfc  call    ??$size_address@I@?$unique_any_array_ptr@UOneDriveKnownFolderMoveStatusEntry@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA?AU?$size_address_ptr@I@01@XZ; wil::unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::size_address<uint>(void)
0x18002ce01  nop
0x18002ce02  lea     rdx, [rax+8]
0x18002ce06  lea     r8, [rbp+var_20]
0x18002ce0a  mov     rcx, r9
0x18002ce0d  mov     rax, r10
0x18002ce10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce15  mov     ebx, eax
0x18002ce17  lea     rcx, [rbp+var_10]
0x18002ce1b  call    ??1?$size_address_ptr@I@?$unique_any_array_ptr@UOneDriveKnownFolderMoveStatusEntry@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::size_address_ptr<uint>::~size_address_ptr<uint>(void)
0x18002ce20  test    ebx, ebx
0x18002ce22  jns     short loc_18002CE4B
0x18002ce24  mov     rcx, [rbp+18h]; this
0x18002ce28  mov     r9d, ebx; char *
0x18002ce2b  lea     r8, aShellCloudexpe; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002ce32  mov     edx, 1DDh; void *
0x18002ce37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ce3c  nop
0x18002ce3d  lea     rcx, [rbp+var_20]
0x18002ce41  call    ??1?$unique_any_array_ptr@UOneDriveKnownFolderMoveStatusEntry@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)
0x18002ce46  jmp     loc_18002CF13
0x18002ce4b  mov     rbx, [rbp+var_18]
0x18002ce4f  test    rbx, rbx
0x18002ce52  jz      loc_18002CF08
0x18002ce58  lea     rcx, [rbx+rbx*4]
0x18002ce5c  shl     rcx, 2; cb
0x18002ce60  call    cs:__imp_CoTaskMemAlloc
0x18002ce66  mov     rdx, rax
0x18002ce69  mov     r8, rbx
0x18002ce6c  lea     rcx, [rbp+var_10]
0x18002ce70  call    ??0?$unique_any_array_ptr@UOneDriveKnownFolderMoveStatusEntry@SyncEngine@CloudExperienceHostBroker@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@5@_K@wil@@QEAA@PEAUOneDriveKnownFolderMoveStatusEntry@SyncEngine@CloudExperienceHostBroker@@_K@Z; wil::unique_any_array_ptr<CloudExperienceHostBroker::SyncEngine::OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<CloudExperienceHostBroker::SyncEngine::OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(CloudExperienceHostBroker::SyncEngine::OneDriveKnownFolderMoveStatusEntry *,unsigned __int64)
0x18002ce75  cmp     [rbp+var_10], 0
0x18002ce7a  jnz     short loc_18002CEA4
0x18002ce7c  mov     rcx, [rbp+18h]; this
0x18002ce80  mov     ebx, 8007000Eh
0x18002ce85  mov     r9d, ebx; char *
0x18002ce88  lea     r8, aShellCloudexpe; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002ce8f  mov     edx, 1E6h; void *
0x18002ce94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ce99  lea     rcx, [rbp+var_10]
0x18002ce9d  call    ??1?$unique_any_array_ptr@UOneDriveKnownFolderMoveStatusEntry@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)
0x18002cea2  jmp     short loc_18002CE3D
0x18002cea4  xor     r10d, r10d
0x18002cea7  test    rbx, rbx
0x18002ceaa  jz      short loc_18002CEEC
0x18002ceac  mov     edx, r10d
0x18002ceaf  lea     rcx, [rbp+var_20]
0x18002ceb3  call    ??A?$unique_any_array_ptr@UOneDriveKnownFolderMoveStatusEntry@SyncEngine@CloudExperienceHostBroker@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@5@_K@wil@@QEAAAEAUOneDriveKnownFolderMoveStatusEntry@SyncEngine@CloudExperienceHostBroker@@_K@Z; wil::unique_any_array_ptr<CloudExperienceHostBroker::SyncEngine::OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator[](unsigned __int64)
0x18002ceb8  movups  xmm0, xmmword ptr [rax]
0x18002cebb  mov     edx, r10d
0x18002cebe  lea     rcx, [rbp+var_10]
0x18002cec2  call    ??A?$unique_any_array_ptr@UOneDriveKnownFolderMoveStatusEntry@SyncEngine@CloudExperienceHostBroker@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@5@_K@wil@@QEAAAEAUOneDriveKnownFolderMoveStatusEntry@SyncEngine@CloudExperienceHostBroker@@_K@Z; wil::unique_any_array_ptr<CloudExperienceHostBroker::SyncEngine::OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator[](unsigned __int64)
0x18002cec7  mov     r8, rax
0x18002ceca  movdqu  xmmword ptr [rax], xmm0
0x18002cece  mov     edx, r10d
0x18002ced1  lea     rcx, [rbp+var_20]
0x18002ced5  call    ??A?$unique_any_array_ptr@UOneDriveKnownFolderMoveStatusEntry@SyncEngine@CloudExperienceHostBroker@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@5@_K@wil@@QEAAAEAUOneDriveKnownFolderMoveStatusEntry@SyncEngine@CloudExperienceHostBroker@@_K@Z; wil::unique_any_array_ptr<CloudExperienceHostBroker::SyncEngine::OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator[](unsigned __int64)
0x18002ceda  mov     ecx, [rax+10h]
0x18002cedd  mov     [r8+10h], ecx
0x18002cee1  inc     r10d
0x18002cee4  mov     eax, r10d
0x18002cee7  cmp     rax, rbx
0x18002ceea  jb      short loc_18002CEAC
0x18002ceec  mov     eax, [rbp+var_8]
0x18002ceef  mov     [r14], eax
0x18002cef2  lea     rcx, [rbp+var_10]
0x18002cef6  call    ?release@?$unique_any_array_ptr@UOneDriveKnownFolderMoveStatusEntry@SyncEngine@CloudExperienceHostBroker@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@5@_K@wil@@QEAAPEAUOneDriveKnownFolderMoveStatusEntry@SyncEngine@CloudExperienceHostBroker@@XZ; wil::unique_any_array_ptr<CloudExperienceHostBroker::SyncEngine::OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::release(void)
0x18002cefb  mov     [rsi], rax
0x18002cefe  lea     rcx, [rbp+var_10]
0x18002cf02  call    ??1?$unique_any_array_ptr@UOneDriveKnownFolderMoveStatusEntry@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)
0x18002cf07  nop
0x18002cf08  lea     rcx, [rbp+var_20]
0x18002cf0c  call    ??1?$unique_any_array_ptr@UOneDriveKnownFolderMoveStatusEntry@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<OneDriveKnownFolderMoveStatusEntry,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)
0x18002cf11  xor     ebx, ebx
0x18002cf13  lea     rcx, [rbp+arg_0]
0x18002cf17  call    ??1?$com_ptr_t@UISystemSetupInfoStatics@Profile@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(void)
0x18002cf1c  mov     eax, ebx
0x18002cf1e  mov     rbx, [rsp+40h+arg_10]
0x18002cf23  mov     rsi, [rsp+40h+arg_18]
0x18002cf28  add     rsp, 40h
0x18002cf2c  pop     r14
0x18002cf2e  pop     rdi
0x18002cf2f  pop     rbp
0x18002cf30  retn
```
