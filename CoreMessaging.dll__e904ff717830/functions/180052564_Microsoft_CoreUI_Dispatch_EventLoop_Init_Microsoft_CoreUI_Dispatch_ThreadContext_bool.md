# Microsoft::CoreUI::Dispatch::EventLoop::Init$(Microsoft::CoreUI::Dispatch::ThreadContext *,bool)

- ea: `0x180052564`
- end: `0x1800526c6`
- name: `?Init$@EventLoop@Dispatch@CoreUI@Microsoft@@IEAAXPEAVThreadContext@234@_N@Z`
- size: `354`
- prototype: `void __fastcall(Microsoft::CoreUI::Dispatch::EventLoop *__hidden this, struct Microsoft::CoreUI::Dispatch::ThreadContext *, bool)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800522ac`

## callees

- `0x18000ec10`
- `0x180010ed0`
- `0x180017bc0`
- `0x18001ab10`
- `0x18002eb74`
- `0x18003950c`
- `0x180052564`
- `0x1800526cc`
- `0x180052770`
- `0x1800527f4`
- `0x180052888`
- `0x1800528cc`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005258d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005258d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800526a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800526a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Microsoft::CoreUI::Dispatch::EventLoop::Init$(
        Microsoft::CoreUI::Dispatch::EventLoop *this,
        struct Microsoft::CoreUI::Dispatch::ThreadContext *a2,
        char a3)
{
  HANDLE EventW; // rax
  __int64 *v6; // rax
  __int64 v7; // rdx
  System::Object *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 *v12; // rax
  __int64 v13; // rdx
  System::Object *v14; // rcx
  signed int LastError; // eax
  _BYTE v16[8]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v17; // [rsp+28h] [rbp-20h]
  __int64 v18; // [rsp+30h] [rbp-18h]
  System::Object *v19; // [rsp+50h] [rbp+8h] BYREF

  CFlat::SmartPtr<Microsoft::CoreUI::Registrar::RegistrarPartitionContext>::operator=((char *)this + 48, a2);
  *((_BYTE *)this + 176) = a3;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    CFlat::Abandonment::FailWithHR(LastError, 0, 0);
  }
  *((_QWORD *)this + 18) = EventW;
  v6 = (__int64 *)Microsoft::CoreUI::Dispatch::Dispatcher::Create$(&v19, this);
  v7 = *v6;
  *v6 = 0;
  v8 = (System::Object *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = v7;
  if ( v8 )
    System::Object::ReleaseNotFrozen$(v8);
  if ( v19 )
    System::Object::ReleaseNotFrozen$(v19);
  v9 = Microsoft::CoreUI::Dispatch::OffThreadReceiver::Create$(&v19, this, 9);
  CFlat::SmartPtr<System::Collections::Generic::List$1<CFlat::SmartPtr<System::Object>>>::operator=(
    (char *)this + 104,
    v9);
  if ( v19 )
    System::Object::ReleaseNotFrozen$(v19);
  v10 = CFlat::DelegateImpl<Microsoft::CoreUI::Dispatch::WakeRecordHandler,0,bool (CFlat::Ref<Microsoft::CoreUI::Dispatch::WakeRecord>),void,0>::Bind<CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::EventLoop>,&private: bool Microsoft::CoreUI::Dispatch::EventLoop::DeferWakeCompletion(CFlat::Ref<Microsoft::CoreUI::Dispatch::WakeRecord>)>(
          v16,
          this);
  v11 = CFlat::DelegateImpl<Microsoft::CoreUI::Dispatch::WakeRecordHandler,0,bool (CFlat::Ref<Microsoft::CoreUI::Dispatch::WakeRecord>),void,0>::Create(
          &v19,
          v10);
  CFlat::SmartPtr<System::Action>::operator=((char *)this + 160, v11);
  if ( v19 )
    System::Object::Release$(v19);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(v18 + 8))(v17);
  v12 = (__int64 *)Microsoft::CoreUI::Dispatch::EventLoopBridge::Create(&v19, this);
  v13 = *v12;
  *v12 = 0;
  v14 = (System::Object *)*((_QWORD *)this + 21);
  *((_QWORD *)this + 21) = v13;
  if ( v14 )
    System::Object::ReleaseNotFrozen$(v14);
  if ( v19 )
    System::Object::ReleaseNotFrozen$(v19);
}

```

## disassembly

```asm
0x180052564  mov     [rsp+arg_8], rbx
0x180052569  push    rdi
0x18005256a  sub     rsp, 40h
0x18005256e  mov     bl, r8b
0x180052571  mov     rdi, rcx
0x180052574  add     rcx, 30h ; '0'
0x180052578  call    ??4?$SmartPtr@VRegistrarPartitionContext@Registrar@CoreUI@Microsoft@@@CFlat@@QEAAAEAV01@PEAVRegistrarPartitionContext@Registrar@CoreUI@Microsoft@@@Z; CFlat::SmartPtr<Microsoft::CoreUI::Registrar::RegistrarPartitionContext>::operator=(Microsoft::CoreUI::Registrar::RegistrarPartitionContext *)
0x18005257d  mov     [rdi+0B0h], bl
0x180052583  xor     r9d, r9d; lpName
0x180052586  xor     r8d, r8d; bInitialState
0x180052589  xor     edx, edx; bManualReset
0x18005258b  xor     ecx, ecx; lpEventAttributes
0x18005258d  call    cs:__imp_CreateEventW
0x180052593  test    rax, rax
0x180052596  jz      loc_1800526A5
0x18005259c  mov     [rdi+90h], rax
0x1800525a3  mov     rdx, rdi
0x1800525a6  lea     rcx, [rsp+48h+arg_0]
0x1800525ab  call    ?Create$@Dispatcher@Dispatch@CoreUI@Microsoft@@SA?AV?$SmartPtr@VDispatcher@Dispatch@CoreUI@Microsoft@@@CFlat@@PEAVEventLoop@234@@Z; Microsoft::CoreUI::Dispatch::Dispatcher::Create$(Microsoft::CoreUI::Dispatch::EventLoop *)
0x1800525b0  mov     rdx, [rax]
0x1800525b3  mov     qword ptr [rax], 0
0x1800525ba  mov     rcx, [rdi+38h]; this
0x1800525be  mov     [rdi+38h], rdx
0x1800525c2  test    rcx, rcx
0x1800525c5  jz      short loc_1800525CC
0x1800525c7  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x1800525cc  mov     rcx, [rsp+48h+arg_0]; this
0x1800525d1  test    rcx, rcx
0x1800525d4  jz      short loc_1800525DB
0x1800525d6  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x1800525db  mov     r8d, 9
0x1800525e1  mov     rdx, rdi
0x1800525e4  lea     rcx, [rsp+48h+arg_0]
0x1800525e9  call    ?Create$@OffThreadReceiver@Dispatch@CoreUI@Microsoft@@SA?AV?$SmartPtr@VOffThreadReceiver@Dispatch@CoreUI@Microsoft@@@CFlat@@PEAVEventLoop@234@W4InternalPriority@234@@Z; Microsoft::CoreUI::Dispatch::OffThreadReceiver::Create$(Microsoft::CoreUI::Dispatch::EventLoop *,Microsoft::CoreUI::Dispatch::InternalPriority)
0x1800525ee  lea     rcx, [rdi+68h]
0x1800525f2  mov     rdx, rax
0x1800525f5  call    ??4?$SmartPtr@V?$List$1@V?$SmartPtr@VObject@System@@@CFlat@@@Generic@Collections@System@@@CFlat@@QEAAAEAV01@$$QEAV01@@Z; CFlat::SmartPtr<System::Collections::Generic::List$1<CFlat::SmartPtr<System::Object>>>::operator=(CFlat::SmartPtr<System::Collections::Generic::List$1<CFlat::SmartPtr<System::Object>>> &&)
0x1800525fa  mov     rcx, [rsp+48h+arg_0]; this
0x1800525ff  test    rcx, rcx
0x180052602  jz      short loc_180052609
0x180052604  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x180052609  mov     rdx, rdi
0x18005260c  lea     rcx, [rsp+48h+var_28]
0x180052611  call    ??$Bind@V?$SmartPtr@VEventLoop@Dispatch@CoreUI@Microsoft@@@CFlat@@$1?DeferWakeCompletion@EventLoop@Dispatch@CoreUI@Microsoft@@AEAA_NU?$Ref@UWakeRecord@Dispatch@CoreUI@Microsoft@@@2@@Z@?$DelegateImpl@VWakeRecordHandler@Dispatch@CoreUI@Microsoft@@$0A@$$A6A_NU?$Ref@UWakeRecord@Dispatch@CoreUI@Microsoft@@@CFlat@@@ZX$0A@@CFlat@@SA?AUDelegateData@1@PEAVEventLoop@Dispatch@CoreUI@Microsoft@@@Z; CFlat::DelegateImpl<Microsoft::CoreUI::Dispatch::WakeRecordHandler,0,bool (CFlat::Ref<Microsoft::CoreUI::Dispatch::WakeRecord>),void,0>::Bind<CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::EventLoop>,&Microsoft::CoreUI::Dispatch::EventLoop::DeferWakeCompletion(CFlat::Ref<Microsoft::CoreUI::Dispatch::WakeRecord>)>(Microsoft::CoreUI::Dispatch::EventLoop *)
0x180052616  nop
0x180052617  mov     rdx, rax
0x18005261a  lea     rcx, [rsp+48h+arg_0]
0x18005261f  call    ?Create@?$DelegateImpl@VWakeRecordHandler@Dispatch@CoreUI@Microsoft@@$0A@$$A6A_NU?$Ref@UWakeRecord@Dispatch@CoreUI@Microsoft@@@CFlat@@@ZX$0A@@CFlat@@SA?AV?$SmartPtr@VWakeRecordHandler@Dispatch@CoreUI@Microsoft@@@2@$$QEAUDelegateData@2@@Z; CFlat::DelegateImpl<Microsoft::CoreUI::Dispatch::WakeRecordHandler,0,bool (CFlat::Ref<Microsoft::CoreUI::Dispatch::WakeRecord>),void,0>::Create(CFlat::DelegateData &&)
0x180052624  lea     rcx, [rdi+0A0h]
0x18005262b  mov     rdx, rax
0x18005262e  call    ??4?$SmartPtr@VAction@System@@@CFlat@@QEAAAEAV01@$$QEAV01@@Z; CFlat::SmartPtr<System::Action>::operator=(CFlat::SmartPtr<System::Action> &&)
0x180052633  mov     rcx, [rsp+48h+arg_0]; this
0x180052638  test    rcx, rcx
0x18005263b  jz      short loc_180052643
0x18005263d  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x180052642  nop
0x180052643  mov     rax, [rsp+48h+var_18]
0x180052648  test    rax, rax
0x18005264b  jz      short loc_18005265C
0x18005264d  mov     rcx, [rsp+48h+var_20]
0x180052652  mov     rax, [rax+8]
0x180052656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005265b  nop
0x18005265c  mov     rdx, rdi
0x18005265f  lea     rcx, [rsp+48h+arg_0]
0x180052664  call    ?Create@EventLoopBridge@Dispatch@CoreUI@Microsoft@@SA?AV?$SmartPtr@VEventLoopBridge@Dispatch@CoreUI@Microsoft@@@CFlat@@PEAVEventLoop@234@@Z; Microsoft::CoreUI::Dispatch::EventLoopBridge::Create(Microsoft::CoreUI::Dispatch::EventLoop *)
0x180052669  mov     rdx, [rax]
0x18005266c  mov     qword ptr [rax], 0
0x180052673  mov     rcx, [rdi+0A8h]; this
0x18005267a  mov     [rdi+0A8h], rdx
0x180052681  test    rcx, rcx
0x180052684  jz      short loc_18005268B
0x180052686  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18005268b  mov     rcx, [rsp+48h+arg_0]; this
0x180052690  test    rcx, rcx
0x180052693  jz      short loc_18005269A
0x180052695  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18005269a  mov     rbx, [rsp+48h+arg_8]
0x18005269f  add     rsp, 40h
0x1800526a3  pop     rdi
0x1800526a4  retn
0x1800526a5  call    cs:__imp_GetLastError
0x1800526ab  test    eax, eax
0x1800526ad  jg      short loc_1800526BC
0x1800526af  xor     r8d, r8d; int
0x1800526b2  xor     edx, edx; void *
0x1800526b4  mov     ecx, eax; int
0x1800526b6  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x1800526bc  movzx   eax, ax
0x1800526bf  or      eax, 80070000h
0x1800526c4  jmp     short loc_1800526AF
```
