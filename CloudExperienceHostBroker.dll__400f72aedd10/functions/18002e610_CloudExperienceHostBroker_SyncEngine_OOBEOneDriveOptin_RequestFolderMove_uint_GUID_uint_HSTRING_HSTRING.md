# CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin::RequestFolderMove(uint,_GUID *,uint,HSTRING__ *,HSTRING__ *)

- ea: `0x18002e610`
- end: `0x18002e72d`
- name: `?RequestFolderMove@OOBEOneDriveOptin@SyncEngine@CloudExperienceHostBroker@@UEAAJIPEAU_GUID@@IPEAUHSTRING__@@1@Z`
- size: `285`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, unsigned int, struct _GUID *, unsigned int, HSTRING, HSTRING string)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180004760`
- `0x180007df0`
- `0x180008344`
- `0x1800084e8`
- `0x18002a954`
- `0x18002e610`
- `0x180030384`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002e63a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002e63a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e6b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e6c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e6b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e6c7`

## string_xrefs

- `0x18002e6f6`: `shell\cloudexperiencehost\broker\lib\oobesyncengineapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin::RequestFolderMove(
        RTL_SRWLOCK *this,
        unsigned int a2,
        struct _GUID *a3,
        unsigned int a4,
        HSTRING a5,
        HSTRING string)
{
  RTL_SRWLOCK *v10; // rbx
  void *v11; // rbx
  const struct _GUID *v12; // rcx
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // rdx
  __int64 (__fastcall *v16)(void *, _QWORD, struct _GUID *, _QWORD); // rsi
  int StringRawBuffer; // [rsp+20h] [rbp-68h]
  RTL_SRWLOCK *v19; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  void *v21; // [rsp+90h] [rbp+8h] BYREF

  v21 = 0;
  v10 = this + 14;
  AcquireSRWLockShared(this + 14);
  v19 = v10;
  wil::com_ptr_t<IOneDriveKnownFolderManager,wil::err_exception_policy>::operator=(&v21, &this[15]);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v19);
  v11 = v21;
  if ( !v21 )
  {
    wil::com_ptr_t<IOneDriveKnownFolderManager,wil::err_exception_policy>::reset(&v21);
    v13 = CloudExperienceHostCreateOOBEUserObjectForceBroker(v12, &GUID_3cbc1a7c_61d0_48a5_aea3_e34114d5cc66, &v21);
    v14 = v13;
    if ( v13 < 0 )
    {
      v15 = 391;
      goto LABEL_7;
    }
    v11 = v21;
  }
  v16 = *(__int64 (__fastcall **)(void *, _QWORD, struct _GUID *, _QWORD))(*(_QWORD *)v11 + 24LL);
  WindowsGetStringRawBuffer(string, 0);
  StringRawBuffer = (unsigned int)WindowsGetStringRawBuffer(a5, 0);
  v13 = v16(v11, a2, a3, a4);
  v14 = v13;
  if ( v13 >= 0 )
  {
    v14 = 0;
    goto LABEL_9;
  }
  v15 = 393;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobesyncengineapi.cpp",
    (const char *)(unsigned int)v13,
    StringRawBuffer);
LABEL_9:
  wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(&v21);
  return v14;
}

```

## disassembly

```asm
0x18002e610  mov     rax, rsp
0x18002e613  push    rbx
0x18002e614  push    rbp
0x18002e615  push    rsi
0x18002e616  push    rdi
0x18002e617  push    r14
0x18002e619  push    r15
0x18002e61b  sub     rsp, 58h
0x18002e61f  mov     ebp, r9d
0x18002e622  mov     r14, r8
0x18002e625  mov     r15d, edx
0x18002e628  mov     rdi, rcx
0x18002e62b  mov     qword ptr [rax+8], 0
0x18002e633  lea     rbx, [rcx+70h]
0x18002e637  mov     rcx, rbx; SRWLock
0x18002e63a  call    cs:__imp_AcquireSRWLockShared
0x18002e640  mov     [rsp+88h+var_48], rbx
0x18002e645  lea     rdx, [rdi+78h]
0x18002e649  lea     rcx, [rsp+88h+arg_0]
0x18002e651  call    ??4?$com_ptr_t@UIOneDriveKnownFolderManager@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<IOneDriveKnownFolderManager,wil::err_exception_policy>::operator=(wil::com_ptr_t<IOneDriveKnownFolderManager,wil::err_exception_policy> const &)
0x18002e656  lea     rcx, [rsp+88h+var_48]
0x18002e65b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002e660  mov     rbx, [rsp+88h+arg_0]
0x18002e668  test    rbx, rbx
0x18002e66b  jnz     short loc_18002E6A3
0x18002e66d  lea     rcx, [rsp+88h+arg_0]
0x18002e675  call    ?reset@?$com_ptr_t@UIOneDriveKnownFolderManager@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IOneDriveKnownFolderManager,wil::err_exception_policy>::reset(void)
0x18002e67a  lea     r8, [rsp+88h+arg_0]; void **
0x18002e682  lea     rdx, _GUID_3cbc1a7c_61d0_48a5_aea3_e34114d5cc66; struct _GUID *
0x18002e689  call    ?CloudExperienceHostCreateOOBEUserObjectForceBroker@@YAJAEBU_GUID@@0PEAPEAX@Z; CloudExperienceHostCreateOOBEUserObjectForceBroker(_GUID const &,_GUID const &,void * *)
0x18002e68e  mov     ebx, eax
0x18002e690  test    eax, eax
0x18002e692  jns     short loc_18002E69B
0x18002e694  mov     edx, 187h
0x18002e699  jmp     short loc_18002E6F6
0x18002e69b  mov     rbx, [rsp+88h+arg_0]
0x18002e6a3  mov     rax, [rbx]
0x18002e6a6  mov     rsi, [rax+18h]
0x18002e6aa  xor     edx, edx; length
0x18002e6ac  mov     rcx, [rsp+88h+string]; string
0x18002e6b4  call    cs:__imp_WindowsGetStringRawBuffer
0x18002e6ba  mov     rdi, rax
0x18002e6bd  xor     edx, edx; length
0x18002e6bf  mov     rcx, [rsp+88h+arg_20]; string
0x18002e6c7  call    cs:__imp_WindowsGetStringRawBuffer
0x18002e6cd  mov     [rsp+88h+var_60], rdi
0x18002e6d2  mov     qword ptr [rsp+88h+var_68], rax; int
0x18002e6d7  mov     r9d, ebp
0x18002e6da  mov     r8, r14
0x18002e6dd  mov     edx, r15d
0x18002e6e0  mov     rcx, rbx
0x18002e6e3  mov     rax, rsi
0x18002e6e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6eb  mov     ebx, eax
0x18002e6ed  test    eax, eax
0x18002e6ef  jns     short loc_18002E70F
0x18002e6f1  mov     edx, 189h; void *
0x18002e6f6  lea     r8, aShellCloudexpe; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002e6fd  mov     r9d, eax; char *
0x18002e700  mov     rcx, [rsp+88h]; this
0x18002e708  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e70d  jmp     short loc_18002E711
0x18002e70f  xor     ebx, ebx
0x18002e711  lea     rcx, [rsp+88h+arg_0]
0x18002e719  call    ??1?$com_ptr_t@UISystemSetupInfoStatics@Profile@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>::~com_ptr_t<Windows::System::Profile::ISystemSetupInfoStatics,wil::err_exception_policy>(void)
0x18002e71e  mov     eax, ebx
0x18002e720  add     rsp, 58h
0x18002e724  pop     r15
0x18002e726  pop     r14
0x18002e728  pop     rdi
0x18002e729  pop     rsi
0x18002e72a  pop     rbp
0x18002e72b  pop     rbx
0x18002e72c  retn
```
