# WorkerTaskMigrationSource::DoMemoryTransferSteps(__int64 &)

- ea: `0x1400af5e0`
- end: `0x1400af94f`
- name: `?DoMemoryTransferSteps@WorkerTaskMigrationSource@@AEAAJAEA_J@Z`
- size: `879`
- prototype: `__int64 __fastcall(PVOID pv, __int64 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1400ae810`

## callees

- `0x14001e628`
- `0x14002ecd0`
- `0x14005b0e4`
- `0x14006af38`
- `0x1400945f8`
- `0x1400af5e0`
- `0x1400af958`
- `0x1400b04e0`
- `0x1400b0d40`
- `0x1400b0e40`
- `0x1400cf8a0`
- `0x14010da10`
- `0x140132940`
- `0x14021b7c0`
- `0x1402269b0`
- `0x14022d098`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400af78e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400af78e`
- `vid!VidMemXferConnectOpen` at `0x1400af77a`
- `vid!VidMemXferConnectOpen` at `0x1400af77a`

## string_xrefs

- `0x1400af69e`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x1400af6e7`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x1400af713`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x1400af747`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x1400af84d`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WorkerTaskMigrationSource::DoMemoryTransferSteps(char *pv, __int64 *a2, __int64 a3)
{
  __int64 v5; // r9
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r9
  int v9; // eax
  MigrationManager *v10; // rbx
  int started; // eax
  int v12; // eax
  __int64 (__fastcall ***v13)(_QWORD); // rcx
  __int64 v14; // rax
  signed int LastError; // eax
  unsigned int v16; // r14d
  __int64 v17; // rcx
  __int64 *v18; // rcx
  __int64 v19; // rax
  const char *v20; // r9
  __int64 result; // rax
  int v22; // [rsp+20h] [rbp-A8h]
  int v23; // [rsp+20h] [rbp-A8h]
  void *v24; // [rsp+40h] [rbp-88h] BYREF
  __int64 v25; // [rsp+48h] [rbp-80h] BYREF
  __int64 VmName; // [rsp+50h] [rbp-78h] BYREF
  __int64 v27; // [rsp+58h] [rbp-70h] BYREF
  __int64 (__fastcall *v28)(); // [rsp+60h] [rbp-68h]
  __int64 v29; // [rsp+68h] [rbp-60h]
  char *v30; // [rsp+70h] [rbp-58h]
  __int64 *v31; // [rsp+90h] [rbp-38h]
  __int64 v32[4]; // [rsp+98h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  try
  {
    if ( (*((_DWORD *)pv + 147) & 0x200) != 0 )
    {
      v5 = *((_QWORD *)pv + 104);
      v24 =  IVmLiveMigrationTargetEvents::`vcall'{40,{flat}};
      v6 = std::bind<long (IVirtualDeviceMigration::*)(void),std::_Ph<1> const &>(v32, &v24, a3, v5);
      v31 = 0;
      v27 = (__int64)&std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (IVirtualDeviceMigration::*)(void),std::_Ph<1> const &>,long,IVirtualDeviceMigration *>::`vftable';
      v28 = *(__int64 (__fastcall **)())v6;
      LOBYTE(v29) = *(_BYTE *)(v6 + 8);
      v31 = &v27;
      VirtualDeviceMigrationCollection<VmWorkerTrace::SourceMigrationTask>::Invoke<VmWorkerTrace::PrepareForMigrationBrownoutTransferAtSource,VmWorkerTrace::PrepareForMigrationBrownoutTransferAtSourcePerVdev,>(
        v8,
        v7,
        &v27);
    }
    if ( *((_DWORD *)pv + 128) )
    {
      v9 = GmoMigration::EnableAccessTracking(*((GmoMigration **)pv + 58));
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4E5,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
          (const char *)(unsigned int)v9,
          v22);
    }
    v24 = 0;
    v10 = (MigrationManager *)*((_QWORD *)pv + 54);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &v24,
      0);
    started = MigrationManager::WaitForStartTransfer(v10, &v24);
    if ( started < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4E9,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)(unsigned int)started,
        v22);
    v12 = WorkerTaskMigrationSource::CheckCancel((WorkerTaskMigrationSource *)(pv + 400));
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4EB,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)(unsigned int)v12,
        v22);
    if ( (pv[588] & 8) != 0 )
    {
      if ( !v24 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4EF,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
          (const char *)0x80070006LL,
          v22);
      v13 = (__int64 (__fastcall ***)(_QWORD))(*(_QWORD *)(*((_QWORD *)pv + 2) + 1024LL) + 24LL);
      v14 = (**v13)(v13);
      if ( !(unsigned int)VidMemXferConnectOpen(v14, v24) )
      {
        LastError = GetLastError();
        v16 = LastError;
        if ( LastError > 0 )
          v16 = (unsigned __int16)LastError | 0x80070000;
        _snwprintf_s<16>(&v27, 16, L"%%%%%u", v16 & 0xEFFFFFFF);
        _snwprintf_s<16>(v32, 16, L"0x%08X", v16 & 0xEFFFFFFF);
        v17 = *((_QWORD *)pv + 2);
        v25 = v17 + 1152;
        VmName = (__int64)VirtualMachine::GetVmName((VirtualMachine *)(v17 + 16));
        VmEventWriteAndReport<unsigned short const *,unsigned short const *,unsigned short (&)[16],unsigned short (&)[16]>(
          (struct _EVENT_DESCRIPTOR *)&MSVM_WORKER_MIGRATION_SOURCE_SMB_SHARE_OPEN_FAILED,
          5u,
          (__int64)&VmName,
          (__int64)&v25,
          (__int64)&v27,
          (__int64)v32);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x500,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
          (const char *)v16,
          v23);
      }
      *((_DWORD *)pv + 118) = 1;
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &v24,
      0);
    WorkerTaskMigrationSource::StartStateTransferProgressToSourceVmmsTimer((struct _TP_TIMER **)pv);
    v32[1] = 1;
    v32[0] = (__int64)pv;
    v18 = (__int64 *)*((_QWORD *)pv + 110);
    v19 = *v18;
    v27 = (__int64)&std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (WorkerTaskMigrationSource::*)(void),WorkerTaskMigrationSource *>,long,>::`vftable';
    v28 =  WorkerTaskMigrationSource::`vcall'{0,{flat}};
    v29 = 400;
    v30 = pv;
    v31 = &v27;
    (*(void (__fastcall **)(__int64 *, __int64 *, __int64 *))(v19 + 16))(v18, &v27, a2);
    LODWORD(v25) = 0;
    WorkerAsyncTaskBase::UpdateStatusProgress((WorkerAsyncTaskBase *)pv, 0x5Au, (int *)&v25);
    LOBYTE(v32[1]) = 0;
    lambda_9715fa7f798c717660a61f51426d2a1b_::operator()(v32);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v24);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x529,
                           (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
                           v20);
  }
  return result;
}

```

## disassembly

```asm
0x1400af5e0  mov     r11, rsp
0x1400af5e3  mov     [r11+18h], rbx
0x1400af5e7  mov     [r11+20h], rdi
0x1400af5eb  push    r14
0x1400af5ed  sub     rsp, 0C0h
0x1400af5f4  mov     rax, cs:__security_cookie
0x1400af5fb  xor     rax, rsp
0x1400af5fe  mov     [rsp+0C8h+var_10], rax
0x1400af606  mov     r14, rdx
0x1400af609  mov     rdi, rcx
0x1400af60c  test    dword ptr [rcx+24Ch], 200h
0x1400af616  jz      short loc_1400AF67A
0x1400af618  mov     r9, [rcx+340h]
0x1400af61f  lea     rax, ??_9IVmLiveMigrationTargetEvents@@$BCI@AA; [thunk]: IVmLiveMigrationTargetEvents::`vcall'{40,{flat}}
0x1400af626  mov     [rsp+0C8h+var_88], rax
0x1400af62b  lea     rdx, [rsp+0C8h+var_88]
0x1400af630  lea     rcx, [r11-30h]
0x1400af634  call    ??$bind@P8IVirtualDeviceMigration@@EAAJXZAEBU?$_Ph@$00@std@@@std@@YA?AV?$_Binder@U_Unforced@std@@P8IVirtualDeviceMigration@@EAAJXZAEBU?$_Ph@$00@2@@0@$$QEAP8IVirtualDeviceMigration@@EAAJXZAEBU?$_Ph@$00@0@@Z; std::bind<long (IVirtualDeviceMigration::*)(void),std::_Ph<1> const &>(long (IVirtualDeviceMigration::*&&)(void),std::_Ph<1> const &)
0x1400af639  mov     [rsp+0C8h+var_38], 0
0x1400af645  lea     rcx, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8IVirtualDeviceMigration@@EAAJXZAEBU?$_Ph@$00@2@@std@@JPEAUIVirtualDeviceMigration@@@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (IVirtualDeviceMigration::*)(void),std::_Ph<1> const &>,long,IVirtualDeviceMigration *>::`vftable'
0x1400af64c  mov     [rsp+0C8h+var_70], rcx
0x1400af651  mov     rcx, [rax]
0x1400af654  mov     [rsp+0C8h+var_68], rcx
0x1400af659  mov     al, [rax+8]
0x1400af65c  mov     byte ptr [rsp+0C8h+var_60], al
0x1400af660  lea     rax, [rsp+0C8h+var_70]
0x1400af665  mov     [rsp+0C8h+var_38], rax
0x1400af66d  lea     r8, [rsp+0C8h+var_70]
0x1400af672  mov     rcx, r9
0x1400af675  call    ??$Invoke@VPrepareForMigrationBrownoutTransferAtSource@VmWorkerTrace@@VPrepareForMigrationBrownoutTransferAtSourcePerVdev@2@$$V@?$VirtualDeviceMigrationCollection@VSourceMigrationTask@VmWorkerTrace@@@@IEAAXW4IVirtualDeviceMigration@Methods@VmMigrationVDevOperationSettings@@V?$function@$$A6AJPEAUIVirtualDeviceMigration@@@Z@std@@@Z; VirtualDeviceMigrationCollection<VmWorkerTrace::SourceMigrationTask>::Invoke<VmWorkerTrace::PrepareForMigrationBrownoutTransferAtSource,VmWorkerTrace::PrepareForMigrationBrownoutTransferAtSourcePerVdev,>(VmMigrationVDevOperationSettings::Methods::IVirtualDeviceMigration,std::function<long (IVirtualDeviceMigration *)>)
0x1400af67a  cmp     dword ptr [rdi+200h], 0
0x1400af681  jz      short loc_1400AF6AF
0x1400af683  mov     rcx, [rdi+1D0h]; this
0x1400af68a  call    ?EnableAccessTracking@GmoMigration@@QEAAJXZ; GmoMigration::EnableAccessTracking(void)
0x1400af68f  mov     rcx, [rsp+0C8h]; this
0x1400af697  test    eax, eax
0x1400af699  jns     short loc_1400AF6AF
0x1400af69b  mov     r9d, eax; char *
0x1400af69e  lea     r8, aOnecoreVmWorke_0; "onecore\\vm\\worker\\migration\\workert"...
0x1400af6a5  mov     edx, 4E5h; void *
0x1400af6aa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400af6af  mov     [rsp+0C8h+var_88], 0
0x1400af6b8  mov     rbx, [rdi+1B0h]
0x1400af6bf  xor     edx, edx
0x1400af6c1  lea     rcx, [rsp+0C8h+var_88]
0x1400af6c6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1400af6cb  lea     rdx, [rsp+0C8h+var_88]; void **
0x1400af6d0  mov     rcx, rbx; this
0x1400af6d3  call    ?WaitForStartTransfer@MigrationManager@@QEAAJPEAPEAX@Z; MigrationManager::WaitForStartTransfer(void * *)
0x1400af6d8  mov     rcx, [rsp+0C8h]; this
0x1400af6e0  test    eax, eax
0x1400af6e2  jns     short loc_1400AF6F8
0x1400af6e4  mov     r9d, eax; char *
0x1400af6e7  lea     r8, aOnecoreVmWorke_0; "onecore\\vm\\worker\\migration\\workert"...
0x1400af6ee  mov     edx, 4E9h; void *
0x1400af6f3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400af6f8  lea     rcx, [rdi+190h]; this
0x1400af6ff  call    ?CheckCancel@WorkerTaskMigrationSource@@UEAAJXZ; WorkerTaskMigrationSource::CheckCancel(void)
0x1400af704  mov     rcx, [rsp+0C8h]; this
0x1400af70c  test    eax, eax
0x1400af70e  jns     short loc_1400AF724
0x1400af710  mov     r9d, eax; char *
0x1400af713  lea     r8, aOnecoreVmWorke_0; "onecore\\vm\\worker\\migration\\workert"...
0x1400af71a  mov     edx, 4EBh; void *
0x1400af71f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400af724  test    byte ptr [rdi+24Ch], 8
0x1400af72b  jz      loc_1400AF868
0x1400af731  mov     rcx, [rsp+0C8h]; this
0x1400af739  cmp     [rsp+0C8h+var_88], 0
0x1400af73f  jnz     short loc_1400AF758
0x1400af741  mov     r9d, 80070006h; char *
0x1400af747  lea     r8, aOnecoreVmWorke_0; "onecore\\vm\\worker\\migration\\workert"...
0x1400af74e  mov     edx, 4EFh; void *
0x1400af753  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400af758  mov     rax, [rdi+10h]
0x1400af75c  mov     rcx, [rax+400h]
0x1400af763  add     rcx, 18h
0x1400af767  mov     rax, [rcx]
0x1400af76a  mov     rax, [rax]
0x1400af76d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400af772  mov     rdx, [rsp+0C8h+var_88]
0x1400af777  mov     rcx, rax
0x1400af77a  call    cs:__imp_VidMemXferConnectOpen
0x1400af781  nop     dword ptr [rax+rax+00h]
0x1400af786  test    eax, eax
0x1400af788  jnz     loc_1400AF85E
0x1400af78e  call    cs:__imp_GetLastError
0x1400af795  nop     dword ptr [rax+rax+00h]
0x1400af79a  mov     r14d, eax
0x1400af79d  test    eax, eax
0x1400af79f  jle     short loc_1400AF7AC
0x1400af7a1  movzx   r14d, ax
0x1400af7a5  or      r14d, 80070000h
0x1400af7ac  mov     ebx, r14d
0x1400af7af  btr     ebx, 1Ch
0x1400af7b3  mov     r9d, ebx
0x1400af7b6  lea     r8, aU_0; "%%%%%u"
0x1400af7bd  mov     edx, 10h
0x1400af7c2  lea     rcx, [rsp+0C8h+var_70]
0x1400af7c7  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x1400af7cc  mov     r9d, ebx
0x1400af7cf  lea     r8, a0x08x; "0x%08X"
0x1400af7d6  mov     edx, 10h
0x1400af7db  lea     rcx, [rsp+0C8h+var_30]
0x1400af7e3  call    ??$_snwprintf_s@$0BA@@@YAHAEAY0BA@G_KPEBGZZ; _snwprintf_s<16>(ushort (&)[16],unsigned __int64,ushort const *,...)
0x1400af7e8  mov     rcx, [rdi+10h]
0x1400af7ec  lea     rax, [rcx+480h]
0x1400af7f3  mov     [rsp+0C8h+var_80], rax
0x1400af7f8  add     rcx, 10h; this
0x1400af7fc  call    ?GetVmName@VirtualMachine@@UEBAPEBGXZ; VirtualMachine::GetVmName(void)
0x1400af801  mov     [rsp+0C8h+var_78], rax
0x1400af806  lea     rax, [rsp+0C8h+var_30]
0x1400af80e  mov     [rsp+0C8h+var_90], rax; __int64
0x1400af813  lea     rax, [rsp+0C8h+var_70]
0x1400af818  mov     [rsp+0C8h+var_98], rax; __int64
0x1400af81d  lea     rax, [rsp+0C8h+var_80]
0x1400af822  mov     [rsp+0C8h+var_A0], rax; __int64
0x1400af827  lea     rax, [rsp+0C8h+var_78]
0x1400af82c  mov     [rsp+0C8h+var_A8], rax; int
0x1400af831  mov     edx, 5; unsigned int
0x1400af836  lea     rcx, MSVM_WORKER_MIGRATION_SOURCE_SMB_SHARE_OPEN_FAILED; struct _EVENT_DESCRIPTOR *
0x1400af83d  call    ??$VmEventWriteAndReport@PEBGPEBGAEAY0BA@GAEAY0BA@G@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@PEBG$$QEAPEBG3AEAY0BA@G4@Z; VmEventWriteAndReport<ushort const *,ushort const *,ushort (&)[16],ushort (&)[16]>(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ushort const *,ushort const * &&,ushort const * &&,ushort (&)[16],ushort (&)[16])
0x1400af842  mov     rcx, [rsp+0C8h]; this
0x1400af84a  mov     r9d, r14d; char *
0x1400af84d  lea     r8, aOnecoreVmWorke_0; "onecore\\vm\\worker\\migration\\workert"...
0x1400af854  mov     edx, 500h; void *
0x1400af859  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400af85e  mov     dword ptr [rdi+1D8h], 1
0x1400af868  xor     edx, edx
0x1400af86a  lea     rcx, [rsp+0C8h+var_88]
0x1400af86f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1400af874  mov     rcx, rdi; pv
0x1400af877  call    ?StartStateTransferProgressToSourceVmmsTimer@WorkerTaskMigrationSource@@AEAAXXZ; WorkerTaskMigrationSource::StartStateTransferProgressToSourceVmmsTimer(void)
0x1400af87c  xorps   xmm0, xmm0
0x1400af87f  movups  xmmword ptr [rsp+0C8h+var_30], xmm0
0x1400af887  mov     [rsp+0C8h+var_30], rdi
0x1400af88f  mov     byte ptr [rsp+0C8h+var_30+8], 1
0x1400af897  mov     rcx, [rdi+370h]
0x1400af89e  mov     rax, [rcx]
0x1400af8a1  lea     rdx, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8WorkerTaskMigrationSource@@EAAJXZPEAV3@@std@@J$$V@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (WorkerTaskMigrationSource::*)(void),WorkerTaskMigrationSource *>,long,>::`vftable'
0x1400af8a8  mov     [rsp+0C8h+var_70], rdx
0x1400af8ad  lea     rdx, ??_9WorkerTaskMigrationSource@@$BA@AA; [thunk]: WorkerTaskMigrationSource::`vcall'{0,{flat}}
0x1400af8b4  mov     [rsp+0C8h+var_68], rdx
0x1400af8b9  mov     [rsp+0C8h+var_60], 190h
0x1400af8c2  mov     [rsp+0C8h+var_58], rdi
0x1400af8c7  lea     rdx, [rsp+0C8h+var_70]
0x1400af8cc  mov     [rsp+0C8h+var_38], rdx
0x1400af8d4  mov     r8, r14
0x1400af8d7  lea     rdx, [rsp+0C8h+var_70]
0x1400af8dc  mov     rax, [rax+10h]
0x1400af8e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400af8e5  mov     dword ptr [rsp+0C8h+var_80], 0
0x1400af8ed  lea     r8, [rsp+0C8h+var_80]; int *
0x1400af8f2  mov     edx, 5Ah ; 'Z'; unsigned int
0x1400af8f7  mov     rcx, rdi; this
0x1400af8fa  call    ?UpdateStatusProgress@WorkerAsyncTaskBase@@MEAAXIAEAH@Z; WorkerAsyncTaskBase::UpdateStatusProgress(uint,int &)
0x1400af8ff  nop
0x1400af900  mov     byte ptr [rsp+0C8h+var_30+8], 0
0x1400af908  lea     rcx, [rsp+0C8h+var_30]
0x1400af910  call    _lambda_9715fa7f798c717660a61f51426d2a1b___operator__
0x1400af915  nop
0x1400af916  lea     rcx, [rsp+0C8h+var_88]
0x1400af91b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400af920  xor     eax, eax
0x1400af922  jmp     short loc_1400AF928
0x1400af924  mov     eax, dword ptr [rsp+0C8h+var_80]
0x1400af928  mov     rcx, [rsp+0C8h+var_10]
0x1400af930  xor     rcx, rsp; StackCookie
0x1400af933  call    __security_check_cookie
0x1400af938  lea     r11, [rsp+0C8h+var_8]
0x1400af940  mov     rbx, [r11+20h]
0x1400af944  mov     rdi, [r11+28h]
0x1400af948  mov     rsp, r11
0x1400af94b  pop     r14
0x1400af94d  retn
```
