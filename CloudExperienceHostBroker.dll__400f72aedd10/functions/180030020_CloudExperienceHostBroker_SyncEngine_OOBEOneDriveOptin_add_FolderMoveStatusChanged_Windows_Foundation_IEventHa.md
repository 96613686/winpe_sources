# CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin::add_FolderMoveStatusChanged(Windows::Foundation::IEventHandler<IInspectable *> *,EventRegistrationToken *)

- ea: `0x180030020`
- end: `0x1800301c3`
- name: `?add_FolderMoveStatusChanged@OOBEOneDriveOptin@SyncEngine@CloudExperienceHostBroker@@UEAAJPEAU?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@PEAUEventRegistrationToken@@@Z`
- size: `419`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004760`
- `0x180007df0`
- `0x180008344`
- `0x1800084a8`
- `0x180027d54`
- `0x18002a954`
- `0x18002bd0c`
- `0x18002d8e0`
- `0x180030020`
- `0x180030384`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180030134`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180030134`

## string_xrefs

- `0x1800300ab`: `shell\cloudexperiencehost\broker\lib\oobesyncengineapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin::add_FolderMoveStatusChanged(
        RTL_SRWLOCK *a1,
        __int64 a2,
        __int64 a3)
{
  const struct _GUID *v6; // rcx
  int v7; // eax
  int v8; // ebx
  __int64 v9; // rdx
  unsigned __int64 v10; // r9
  __int64 v11; // rbx
  void *v12; // rdi
  __int64 v14; // [rsp+20h] [rbp-20h] BYREF
  void *v15; // [rsp+28h] [rbp-18h] BYREF
  RTL_SRWLOCK *v16; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  void *v18; // [rsp+78h] [rbp+38h] BYREF

  v18 = 0;
  wil::com_ptr_t<IOneDriveKnownFolderManager,wil::err_exception_policy>::reset(&v18);
  v7 = CloudExperienceHostCreateOOBEUserObjectForceBroker(v6, &GUID_3cbc1a7c_61d0_48a5_aea3_e34114d5cc66, &v18);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 404;
LABEL_5:
    v10 = (unsigned int)v7;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobesyncengineapi.cpp",
      (const char *)v10,
      v14);
    goto LABEL_22;
  }
  v15 = 0;
  v7 = (*(__int64 (__fastcall **)(void *, _QWORD, void **))(*(_QWORD *)v18 + 32LL))(
         v18,
         (unsigned __int64)&a1[1] & ((unsigned __int128)-(__int128)(unsigned __int64)&a1[-6] >> 64),
         &v15);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 406;
    goto LABEL_5;
  }
  if ( !a2 )
  {
    v8 = -2147024809;
LABEL_14:
    v10 = (unsigned int)v8;
    v9 = 407;
    goto LABEL_6;
  }
  v14 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::IEventHandler<IInspectable *>>::InternalRelease(&v14);
  v8 = Microsoft::WRL::Details::CreateAgileHelper<Windows::Foundation::IEventHandler<IInspectable *>>(a2, &v14);
  if ( v8 >= 0 )
  {
    if ( v14 )
      v8 = Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(
             &a1[11],
             v14,
             *(_QWORD *)(*(_QWORD *)a2 + 24LL),
             a3);
    else
      v8 = -2147024809;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IEventHandler<IInspectable *>>::InternalRelease(&v14);
  if ( v8 < 0 )
    goto LABEL_14;
  v11 = 0;
  v14 = 0;
  AcquireSRWLockExclusive(a1 + 14);
  v16 = a1 + 14;
  if ( a1[16].Ptr )
  {
    v12 = v15;
    wil::com_ptr_t<IOneDriveKnownFolderManager,wil::err_exception_policy>::operator=(&v14, &v18);
    v11 = v14;
  }
  else
  {
    v12 = 0;
    a1[16].Ptr = v15;
    wil::com_ptr_t<IOneDriveKnownFolderManager,wil::err_exception_policy>::operator=(&a1[15], &v18);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
  if ( v11 && v12 )
    (*(void (__fastcall **)(__int64, void *))(*(_QWORD *)v11 + 40LL))(v11, v12);
  wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(&v14);
  v8 = 0;
LABEL_22:
  wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(&v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180030020  mov     [rsp-18h+arg_0], rbx
0x180030025  mov     [rsp-18h+arg_8], rsi
0x18003002a  push    rbp
0x18003002b  push    rdi
0x18003002c  push    r14
0x18003002e  mov     rbp, rsp
0x180030031  sub     rsp, 40h
0x180030035  mov     r14, r8
0x180030038  mov     rdi, rdx
0x18003003b  mov     rsi, rcx
0x18003003e  mov     [rbp+arg_18], 0
0x180030046  lea     rcx, [rbp+arg_18]
0x18003004a  call    ?reset@?$com_ptr_t@UIOneDriveKnownFolderManager@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IOneDriveKnownFolderManager,wil::err_exception_policy>::reset(void)
0x18003004f  lea     r8, [rbp+arg_18]; void **
0x180030053  lea     rdx, _GUID_3cbc1a7c_61d0_48a5_aea3_e34114d5cc66; struct _GUID *
0x18003005a  call    ?CloudExperienceHostCreateOOBEUserObjectForceBroker@@YAJAEBU_GUID@@0PEAPEAX@Z; CloudExperienceHostCreateOOBEUserObjectForceBroker(_GUID const &,_GUID const &,void * *)
0x18003005f  mov     ebx, eax
0x180030061  test    eax, eax
0x180030063  jns     short loc_18003006C
0x180030065  mov     edx, 194h
0x18003006a  jmp     short loc_1800300A4
0x18003006c  mov     [rbp+var_18], 0
0x180030074  mov     rcx, [rbp+arg_18]
0x180030078  mov     r9, [rcx]
0x18003007b  lea     rax, [rsi-30h]
0x18003007f  lea     r8, [rsi+8]
0x180030083  neg     rax
0x180030086  sbb     rdx, rdx
0x180030089  and     rdx, r8
0x18003008c  lea     r8, [rbp+var_18]
0x180030090  mov     rax, [r9+20h]
0x180030094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030099  mov     ebx, eax
0x18003009b  test    eax, eax
0x18003009d  jns     short loc_1800300BC
0x18003009f  mov     edx, 196h; void *
0x1800300a4  mov     r9d, eax; char *
0x1800300a7  mov     rcx, [rbp+18h]; this
0x1800300ab  lea     r8, aShellCloudexpe; "shell\\cloudexperiencehost\\broker\\lib"...
0x1800300b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800300b7  jmp     loc_1800301A5
0x1800300bc  test    rdi, rdi
0x1800300bf  jnz     short loc_1800300C8
0x1800300c1  mov     ebx, 80070057h
0x1800300c6  jmp     short loc_18003011D
0x1800300c8  mov     [rbp+var_20], 0
0x1800300d0  lea     rcx, [rbp+var_20]
0x1800300d4  call    ?InternalRelease@?$ComPtr@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IEventHandler<IInspectable *>>::InternalRelease(void)
0x1800300d9  lea     rdx, [rbp+var_20]
0x1800300dd  mov     rcx, rdi
0x1800300e0  call    ??$CreateAgileHelper@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@@Details@WRL@Microsoft@@YAJPEAU?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@PEAPEAU345@@Z; Microsoft::WRL::Details::CreateAgileHelper<Windows::Foundation::IEventHandler<IInspectable *>>(Windows::Foundation::IEventHandler<IInspectable *> *,Windows::Foundation::IEventHandler<IInspectable *> * *)
0x1800300e5  mov     ebx, eax
0x1800300e7  test    eax, eax
0x1800300e9  js      short loc_180030110
0x1800300eb  mov     rdx, [rbp+var_20]
0x1800300ef  test    rdx, rdx
0x1800300f2  jnz     short loc_1800300FB
0x1800300f4  mov     ebx, 80070057h
0x1800300f9  jmp     short loc_180030110
0x1800300fb  mov     r8, [rdi]
0x1800300fe  lea     rcx, [rsi+58h]
0x180030102  mov     r9, r14
0x180030105  mov     r8, [r8+18h]
0x180030109  call    ?AddInternal@?$EventSource@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@AEAAJPEAU?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@PEAXPEAUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(Windows::Foundation::IEventHandler<IInspectable *> *,void *,EventRegistrationToken *)
0x18003010e  mov     ebx, eax
0x180030110  lea     rcx, [rbp+var_20]
0x180030114  call    ?InternalRelease@?$ComPtr@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IEventHandler<IInspectable *>>::InternalRelease(void)
0x180030119  test    ebx, ebx
0x18003011b  jns     short loc_180030127
0x18003011d  mov     r9d, ebx
0x180030120  mov     edx, 197h
0x180030125  jmp     short loc_1800300A7
0x180030127  xor     ebx, ebx
0x180030129  mov     [rbp+var_20], rbx
0x18003012d  lea     rdi, [rsi+70h]
0x180030131  mov     rcx, rdi; SRWLock
0x180030134  call    cs:__imp_AcquireSRWLockExclusive
0x18003013a  mov     [rbp+var_10], rdi
0x18003013e  lea     rdx, [rbp+arg_18]
0x180030142  cmp     [rsi+80h], rbx
0x180030149  jz      short loc_18003015E
0x18003014b  mov     rdi, [rbp+var_18]
0x18003014f  lea     rcx, [rbp+var_20]
0x180030153  call    ??4?$com_ptr_t@UIOneDriveKnownFolderManager@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<IOneDriveKnownFolderManager,wil::err_exception_policy>::operator=(wil::com_ptr_t<IOneDriveKnownFolderManager,wil::err_exception_policy> const &)
0x180030158  mov     rbx, [rbp+var_20]
0x18003015c  jmp     short loc_180030174
0x18003015e  xor     edi, edi
0x180030160  mov     rax, [rbp+var_18]
0x180030164  mov     [rsi+80h], rax
0x18003016b  lea     rcx, [rsi+78h]
0x18003016f  call    ??4?$com_ptr_t@UIOneDriveKnownFolderManager@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<IOneDriveKnownFolderManager,wil::err_exception_policy>::operator=(wil::com_ptr_t<IOneDriveKnownFolderManager,wil::err_exception_policy> const &)
0x180030174  lea     rcx, [rbp+var_10]
0x180030178  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003017d  test    rbx, rbx
0x180030180  jz      short loc_18003019A
0x180030182  test    rdi, rdi
0x180030185  jz      short loc_18003019A
0x180030187  mov     rax, [rbx]
0x18003018a  mov     rdx, rdi
0x18003018d  mov     rcx, rbx
0x180030190  mov     rax, [rax+28h]
0x180030194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030199  nop
0x18003019a  lea     rcx, [rbp+var_20]
0x18003019e  call    ??1?$com_ptr_t@UISystemSetupInfoStatics@Profile@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(void)
0x1800301a3  xor     ebx, ebx
0x1800301a5  lea     rcx, [rbp+arg_18]
0x1800301a9  call    ??1?$com_ptr_t@UISystemSetupInfoStatics@Profile@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(void)
0x1800301ae  mov     eax, ebx
0x1800301b0  mov     rbx, [rsp+40h+arg_0]
0x1800301b5  mov     rsi, [rsp+40h+arg_8]
0x1800301ba  add     rsp, 40h
0x1800301be  pop     r14
0x1800301c0  pop     rdi
0x1800301c1  pop     rbp
0x1800301c2  retn
```
