# AppPrioritizationUserSessionStatics::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180009110`
- end: `0x180009293`
- name: `?CreateInstance@AppPrioritizationUserSessionStatics@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `387`
- prototype: `__int64 __fastcall(AppPrioritizationUserSessionStatics *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180001304`
- `0x180002650`
- `0x180002b38`
- `0x1800032a4`
- `0x180008594`
- `0x180008ea0`
- `0x180009110`
- `0x18000a1f0`
- `0x18000a7f0`
- `0x18000b204`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall AppPrioritizationUserSessionStatics::CreateInstance(
        AppPrioritizationUserSessionStatics *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  AppPrioritizationUserSession *v8; // rax
  AppPrioritizationUserSession *v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rcx
  int Interface; // ebx
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+38h] [rbp-30h] BYREF

  *a4 = 0;
  if ( AppPrioritizationUserSessionStatics::s_instance )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( AppPrioritizationUserSessionStatics::s_instance )
      return 2147500037LL;
  }
  if ( a2 )
    return 2147746064LL;
  v8 = (AppPrioritizationUserSession *)operator new(0x98u, (const struct std::nothrow_t *)std::nothrow);
  v9 = v8;
  if ( v8 )
  {
    memset_0(v8, 0, 0x98u);
    v8 = AppPrioritizationUserSession::AppPrioritizationUserSession(v9);
  }
  v10 = AppPrioritizationUserSessionStatics::s_instance;
  AppPrioritizationUserSessionStatics::s_instance = (__int64)v8;
  if ( v10 )
  {
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IAppPrioritizationUserSessionInternal,IAppPrioritizationUserSession>::Release();
    v8 = (AppPrioritizationUserSession *)AppPrioritizationUserSessionStatics::s_instance;
  }
  if ( !v8 )
    return 2147942414LL;
  v11 = AppPrioritizationUserSession::s_weakReference;
  AppPrioritizationUserSession::s_weakReference = 0;
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  Microsoft::WRL::ComPtr<AppPrioritizationUserSession>::AsWeak(v11, &AppPrioritizationUserSession::s_weakReference);
  Interface = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IAppPrioritizationUserSessionInternal,IAppPrioritizationUserSession>::QueryInterface(
                AppPrioritizationUserSessionStatics::s_instance,
                a3,
                a4);
  if ( Interface >= 0 )
  {
    if ( (unsigned int)dword_180014000 > 4 )
      tlgWriteTransfer_EventWriteTransfer((int)&dword_180014000, (int)&word_180010262, 0, 0, 2u, &v13);
    return 0;
  }
  else
  {
    if ( AppPrioritizationUserSessionStatics::s_instance )
    {
      AppPrioritizationUserSessionStatics::s_instance = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IAppPrioritizationUserSessionInternal,IAppPrioritizationUserSession>::Release();
    }
    return (unsigned int)Interface;
  }
}

```

## disassembly

```asm
0x180009110  mov     [rsp+arg_0], rbx
0x180009115  mov     [rsp+arg_8], rsi
0x18000911a  push    rdi
0x18000911b  sub     rsp, 60h
0x18000911f  mov     rax, cs:__security_cookie
0x180009126  xor     rax, rsp
0x180009129  mov     [rsp+68h+var_10], rax
0x18000912e  mov     rdi, r9
0x180009131  mov     rsi, r8
0x180009134  mov     rbx, rdx
0x180009137  mov     qword ptr [r9], 0
0x18000913e  cmp     cs:?s_instance@AppPrioritizationUserSessionStatics@@0V?$ComPtr@VAppPrioritizationUserSession@@@WRL@Microsoft@@A, 0; Microsoft::WRL::ComPtr<AppPrioritizationUserSession> AppPrioritizationUserSessionStatics::s_instance
0x180009146  jz      short loc_180009161
0x180009148  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000914d  cmp     cs:?s_instance@AppPrioritizationUserSessionStatics@@0V?$ComPtr@VAppPrioritizationUserSession@@@WRL@Microsoft@@A, 0; Microsoft::WRL::ComPtr<AppPrioritizationUserSession> AppPrioritizationUserSessionStatics::s_instance
0x180009155  jz      short loc_180009161
0x180009157  mov     eax, 80004005h
0x18000915c  jmp     loc_180009275
0x180009161  test    rbx, rbx
0x180009164  jz      short loc_180009170
0x180009166  mov     eax, 80040110h
0x18000916b  jmp     loc_180009275
0x180009170  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009177  mov     ecx, 98h; unsigned __int64
0x18000917c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009181  mov     rbx, rax
0x180009184  test    rax, rax
0x180009187  jz      short loc_1800091A1
0x180009189  xor     edx, edx; Val
0x18000918b  mov     r8d, 98h; Size
0x180009191  mov     rcx, rax; void *
0x180009194  call    memset_0
0x180009199  mov     rcx, rbx; this
0x18000919c  call    ??0AppPrioritizationUserSession@@QEAA@XZ; AppPrioritizationUserSession::AppPrioritizationUserSession(void)
0x1800091a1  mov     rcx, cs:?s_instance@AppPrioritizationUserSessionStatics@@0V?$ComPtr@VAppPrioritizationUserSession@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<AppPrioritizationUserSession> AppPrioritizationUserSessionStatics::s_instance
0x1800091a8  mov     cs:?s_instance@AppPrioritizationUserSessionStatics@@0V?$ComPtr@VAppPrioritizationUserSession@@@WRL@Microsoft@@A, rax; Microsoft::WRL::ComPtr<AppPrioritizationUserSession> AppPrioritizationUserSessionStatics::s_instance
0x1800091af  test    rcx, rcx
0x1800091b2  jz      short loc_1800091C0
0x1800091b4  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VFtmBase@23@UIAppPrioritizationUserSessionInternal@@UIAppPrioritizationUserSession@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IAppPrioritizationUserSessionInternal,IAppPrioritizationUserSession>::Release(void)
0x1800091b9  mov     rax, cs:?s_instance@AppPrioritizationUserSessionStatics@@0V?$ComPtr@VAppPrioritizationUserSession@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<AppPrioritizationUserSession> AppPrioritizationUserSessionStatics::s_instance
0x1800091c0  test    rax, rax
0x1800091c3  jnz     short loc_1800091CF
0x1800091c5  mov     eax, 8007000Eh
0x1800091ca  jmp     loc_180009275
0x1800091cf  mov     rcx, cs:?s_weakReference@AppPrioritizationUserSession@@2VWeakRef@WRL@Microsoft@@A; Microsoft::WRL::WeakRef AppPrioritizationUserSession::s_weakReference
0x1800091d6  mov     cs:?s_weakReference@AppPrioritizationUserSession@@2VWeakRef@WRL@Microsoft@@A, 0; Microsoft::WRL::WeakRef AppPrioritizationUserSession::s_weakReference
0x1800091e1  test    rcx, rcx
0x1800091e4  jz      short loc_1800091F3
0x1800091e6  mov     rax, [rcx]
0x1800091e9  mov     rax, [rax+10h]
0x1800091ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091f2  nop
0x1800091f3  lea     rdx, ?s_weakReference@AppPrioritizationUserSession@@2VWeakRef@WRL@Microsoft@@A; Microsoft::WRL::WeakRef AppPrioritizationUserSession::s_weakReference
0x1800091fa  call    ?AsWeak@?$ComPtr@VAppPrioritizationUserSession@@@WRL@Microsoft@@QEBAJPEAVWeakRef@23@@Z; Microsoft::WRL::ComPtr<AppPrioritizationUserSession>::AsWeak(Microsoft::WRL::WeakRef *)
0x1800091ff  mov     r8, rdi
0x180009202  mov     rdx, rsi
0x180009205  mov     rcx, cs:?s_instance@AppPrioritizationUserSessionStatics@@0V?$ComPtr@VAppPrioritizationUserSession@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<AppPrioritizationUserSession> AppPrioritizationUserSessionStatics::s_instance
0x18000920c  call    ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VFtmBase@23@UIAppPrioritizationUserSessionInternal@@UIAppPrioritizationUserSession@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IAppPrioritizationUserSessionInternal,IAppPrioritizationUserSession>::QueryInterface(_GUID const &,void * *)
0x180009211  mov     ebx, eax
0x180009213  test    eax, eax
0x180009215  jns     short loc_180009237
0x180009217  mov     rcx, cs:?s_instance@AppPrioritizationUserSessionStatics@@0V?$ComPtr@VAppPrioritizationUserSession@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<AppPrioritizationUserSession> AppPrioritizationUserSessionStatics::s_instance
0x18000921e  test    rcx, rcx
0x180009221  jz      short loc_180009233
0x180009223  mov     cs:?s_instance@AppPrioritizationUserSessionStatics@@0V?$ComPtr@VAppPrioritizationUserSession@@@WRL@Microsoft@@A, 0; Microsoft::WRL::ComPtr<AppPrioritizationUserSession> AppPrioritizationUserSessionStatics::s_instance
0x18000922e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VFtmBase@23@UIAppPrioritizationUserSessionInternal@@UIAppPrioritizationUserSession@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IAppPrioritizationUserSessionInternal,IAppPrioritizationUserSession>::Release(void)
0x180009233  mov     eax, ebx
0x180009235  jmp     short loc_180009275
0x180009237  mov     eax, cs:dword_180014000
0x18000923d  cmp     eax, 4
0x180009240  jbe     short loc_18000926D
0x180009242  lea     rax, [rsp+68h+var_30]
0x180009247  mov     [rsp+68h+var_40], rax; PEVENT_DATA_DESCRIPTOR
0x18000924c  mov     [rsp+68h+var_48], 2; ULONG
0x180009254  xor     r9d, r9d; int
0x180009257  xor     r8d, r8d; int
0x18000925a  lea     rdx, word_180010262; int
0x180009261  lea     rcx, dword_180014000; int
0x180009268  call    _tlgWriteTransfer_EventWriteTransfer
0x18000926d  xor     eax, eax
0x18000926f  jmp     short loc_180009275
0x180009271  mov     eax, [rsp+68h+var_38]
0x180009275  mov     rcx, [rsp+68h+var_10]
0x18000927a  xor     rcx, rsp; StackCookie
0x18000927d  call    __security_check_cookie
0x180009282  mov     rbx, [rsp+68h+arg_0]
0x180009287  mov     rsi, [rsp+68h+arg_8]
0x18000928c  add     rsp, 60h
0x180009290  pop     rdi
0x180009291  retn
```
