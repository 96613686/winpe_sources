# Windows::Security::Isolation::FileDialogBroker::Advise(IFileDialogEvents *,ulong *)

- ea: `0x140009bd0`
- end: `0x140009ce9`
- name: `?Advise@FileDialogBroker@Isolation@Security@Windows@@UEAAJPEAUIFileDialogEvents@@PEAK@Z`
- size: `281`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, struct IFileDialogEvents *, unsigned int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140009cf0`
- `0x140009d00`
- `0x140009d10`

## callees

- `0x140007df4`
- `0x140009150`
- `0x140009174`
- `0x140009194`
- `0x140009bd0`
- `0x14000bc30`
- `0x14000bc9c`
- `0x14000f8d0`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009bf3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009bf3`

## string_xrefs

- `0x140009c4a`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`
- `0x140009c01`: `FileDialogBroker::Advise`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBroker::Advise(
        RTL_SRWLOCK *this,
        struct IFileDialogEvents *a2,
        unsigned int *a3)
{
  RTL_SRWLOCK *v6; // rbx
  RTL_SRWLOCK *v7; // rbx
  struct IUnknown *IUnknown; // rax
  __int64 v9; // rdx
  int ImpersonationTokenForClientOfObject_nothrow; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64, unsigned int *); // r15
  __int64 v13; // rax
  unsigned int v14; // ebx
  const char *v15; // r9
  __int64 result; // rax
  int v17[20]; // [rsp+20h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  void *v19; // [rsp+90h] [rbp+8h] BYREF
  RTL_SRWLOCK *v20; // [rsp+A8h] [rbp+20h] BYREF

  v6 = this + 9;
  AcquireSRWLockExclusive(this + 9);
  v20 = v6;
  FileDialogBrokerTraceLogging::WatchCurrentThread(v17, "FileDialogBroker::Advise");
  v19 = 0;
  v7 = this - 1;
  try
  {
    IUnknown = Windows::Security::Isolation::FileDialogBroker::GetIUnknown((Windows::Security::Isolation::FileDialogBroker *)&this[-1]);
    ImpersonationTokenForClientOfObject_nothrow = wil::GetImpersonationTokenForClientOfObject_nothrow(
                                                    (__int64)IUnknown,
                                                    v9,
                                                    &v19);
    if ( ImpersonationTokenForClientOfObject_nothrow < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x298,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
        (const char *)(unsigned int)ImpersonationTokenForClientOfObject_nothrow,
        v17[0]);
    v11 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *))v7->Ptr + 7))(this - 1);
    v12 = *(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v11 + 56LL);
    v13 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, void **, struct IFileDialogEvents *))v7->Ptr + 12))(v7, &v19, a2);
    v14 = v12(v11, v13, a3);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v17);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v20);
    result = v14;
  }
  catch ( ... )
  {
    LODWORD(v19) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x2A2,
                     (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                     v15);
    return (unsigned int)v19;
  }
  return result;
}

```

## disassembly

```asm
0x140009bd0  mov     [rsp+arg_8], rbx
0x140009bd5  mov     [rsp+arg_10], rsi
0x140009bda  push    rdi
0x140009bdb  push    r14
0x140009bdd  push    r15
0x140009bdf  sub     rsp, 70h
0x140009be3  mov     rsi, r8
0x140009be6  mov     r14, rdx
0x140009be9  mov     rdi, rcx
0x140009bec  lea     rbx, [rcx+48h]
0x140009bf0  mov     rcx, rbx; SRWLock
0x140009bf3  call    cs:__imp_AcquireSRWLockExclusive
0x140009bf9  mov     [rsp+88h+arg_18], rbx
0x140009c01  lea     rdx, aFiledialogbrok_0; "FileDialogBroker::Advise"
0x140009c08  lea     rcx, [rsp+88h+var_68]
0x140009c0d  call    ?WatchCurrentThread@FileDialogBrokerTraceLogging@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; FileDialogBrokerTraceLogging::WatchCurrentThread(char const *)
0x140009c12  nop
0x140009c13  mov     [rsp+88h+arg_0], 0
0x140009c1f  lea     rbx, [rdi-8]
0x140009c23  mov     rcx, rbx; this
0x140009c26  call    ?GetIUnknown@FileDialogBroker@Isolation@Security@Windows@@AEAAPEAUIUnknown@@XZ; Windows::Security::Isolation::FileDialogBroker::GetIUnknown(void)
0x140009c2b  lea     r8, [rsp+88h+arg_0]
0x140009c33  mov     rcx, rax
0x140009c36  call    ?GetImpersonationTokenForClientOfObject_nothrow@wil@@YAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@@Z; wil::GetImpersonationTokenForClientOfObject_nothrow(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x140009c3b  mov     rcx, [rsp+88h]; this
0x140009c43  test    eax, eax
0x140009c45  jns     short loc_140009C5B
0x140009c47  mov     r9d, eax; char *
0x140009c4a  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x140009c51  mov     edx, 298h; void *
0x140009c56  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140009c5b  mov     rax, [rbx]
0x140009c5e  mov     rcx, rbx
0x140009c61  mov     rax, [rax+38h]
0x140009c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009c6a  mov     rdi, rax
0x140009c6d  mov     rdx, [rax]
0x140009c70  mov     r15, [rdx+38h]
0x140009c74  mov     rdx, [rbx]
0x140009c77  mov     rax, [rdx+60h]
0x140009c7b  mov     r8, r14
0x140009c7e  lea     rdx, [rsp+88h+arg_0]
0x140009c86  mov     rcx, rbx
0x140009c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009c8e  mov     r8, rsi
0x140009c91  mov     rdx, rax
0x140009c94  mov     rcx, rdi
0x140009c97  mov     rax, r15
0x140009c9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009c9f  mov     ebx, eax
0x140009ca1  lea     rcx, [rsp+88h+arg_0]
0x140009ca9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140009cae  nop
0x140009caf  lea     rcx, [rsp+88h+var_68]; this
0x140009cb4  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x140009cb9  nop
0x140009cba  lea     rcx, [rsp+88h+arg_18]
0x140009cc2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140009cc7  mov     eax, ebx
0x140009cc9  jmp     short loc_140009CD2
0x140009ccb  mov     eax, dword ptr [rsp+88h+arg_0]
0x140009cd2  lea     r11, [rsp+88h+var_18]
0x140009cd7  mov     rbx, [r11+28h]
0x140009cdb  mov     rsi, [r11+30h]
0x140009cdf  mov     rsp, r11
0x140009ce2  pop     r15
0x140009ce4  pop     r14
0x140009ce6  pop     rdi
0x140009ce7  retn
```
