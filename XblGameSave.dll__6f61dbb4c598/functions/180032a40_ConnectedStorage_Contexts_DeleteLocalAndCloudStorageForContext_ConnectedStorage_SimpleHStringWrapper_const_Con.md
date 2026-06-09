# ConnectedStorage::Contexts::DeleteLocalAndCloudStorageForContext(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,std::function<void (long)>)

- ea: `0x180032a40`
- end: `0x180032c74`
- name: `?DeleteLocalAndCloudStorageForContext@Contexts@ConnectedStorage@@QEBAXAEBVSimpleHStringWrapper@2@00V?$function@$$A6AXJ@Z@std@@@Z`
- size: `564`
- prototype: `__int64 __fastcall(ConnectedStorage::Contexts *this, struct ConnectedStorage::SimpleHStringWrapper *, struct ConnectedStorage::SimpleHStringWrapper *, struct ConnectedStorage::SimpleHStringWrapper *, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task`

## callers

- `0x1800145d8`

## callees

- `0x18000aae4`
- `0x18000c218`
- `0x18000cb9c`
- `0x180010e90`
- `0x1800113bc`
- `0x1800125ec`
- `0x18001265c`
- `0x180020e68`
- `0x180022dec`
- `0x18002eeb8`
- `0x180032a40`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032c0b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032c0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032beb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032bfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032beb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032bfb`
- `ntdll!NtQueryInformationToken` at `0x180032b58`
- `ntdll!NtQueryInformationToken` at `0x180032b58`
- `ntdll!RtlIsMultiSessionSku` at `0x180032b04`
- `ntdll!RtlIsMultiSessionSku` at `0x180032b04`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180032b2f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180032b2f`

## string_xrefs

- `0x180032c65`: `UMgrQueryUserToken(userContext, userTokenHandle.GetAddressOf())`
- `0x180032c41`: `DeleteLocalAndCloudStorageForContext No User`
- `0x180032c53`: `DeleteLocalAndCloudStorageForContext No User`
- `0x180032c32`: `HRESULT_FROM_NT(NtQueryInformationToken(userTokenHandle.Get(), TokenSessionId, &sessionId, sizeof(sessionId), &length))`

## pseudocode

```c
__int64 __fastcall ConnectedStorage::Contexts::DeleteLocalAndCloudStorageForContext(
        ConnectedStorage::Contexts *this,
        struct ConnectedStorage::SimpleHStringWrapper *a2,
        struct ConnectedStorage::SimpleHStringWrapper *a3,
        struct ConnectedStorage::SimpleHStringWrapper *a4,
        __int64 a5)
{
  const unsigned __int16 *v9; // r8
  __int64 v10; // rsi
  void (__fastcall *v11)(__int64, struct ConnectedStorage::SimpleHStringWrapper *, HSTRING *, HSTRING *, bool *, __int64 *); // rdi
  HSTRING *AddressOf; // rbx
  HSTRING *v13; // rax
  const unsigned __int16 *v14; // r8
  int v15; // eax
  const unsigned __int16 *v16; // r8
  int v17; // eax
  const unsigned __int16 *v18; // r8
  unsigned int TokenInformation; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v23; // [rsp+58h] [rbp-A8h] BYREF
  ULONG ReturnLength; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+68h] [rbp-98h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v27[48]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v28[48]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v29[128]; // [rsp+E0h] [rbp-20h] BYREF
  bool v30; // [rsp+170h] [rbp+70h] BYREF

  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (ConnectedStorage::Contexts *)((char *)this + 176),
    (char *)a3);
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, struct ConnectedStorage::SimpleHStringWrapper *))(**((_QWORD **)this + 21) + 24LL))(
          *((_QWORD *)this + 21),
          a2) )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)0x80832001LL,
      (int)L"DeleteLocalAndCloudStorageForContext No User",
      v9);
  v23 = 0;
  string = 0;
  v30 = 0;
  v25 = 0;
  v10 = *((_QWORD *)this + 21);
  v11 = *(void (__fastcall **)(__int64, struct ConnectedStorage::SimpleHStringWrapper *, HSTRING *, HSTRING *, bool *, __int64 *))(*(_QWORD *)v10 + 16LL);
  AddressOf = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&string);
  v13 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v23);
  v11(v10, a2, v13, AddressOf, &v30, &v25);
  if ( v30 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)0x80832001LL,
      (int)L"DeleteLocalAndCloudStorageForContext No User",
      v14);
  TokenInformation = 0;
  if ( (unsigned __int8)RtlIsMultiSessionSku() )
  {
    ReturnLength = 0;
    TokenHandle = (HANDLE)-1LL;
    ConnectedStorage::Handle::CloseHandle((ConnectedStorage::Handle *)&TokenHandle);
    v15 = UMgrQueryUserToken(v25, &TokenHandle);
    if ( v15 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v15,
        (int)L"UMgrQueryUserToken(userContext, userTokenHandle.GetAddressOf())",
        v16);
    v17 = NtQueryInformationToken(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength) | 0x10000000;
    if ( v17 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v17,
        (int)L"HRESULT_FROM_NT(NtQueryInformationToken(userTokenHandle.Get(), TokenSessionId, &sessionId, sizeof(sessionId), &length))",
        v18);
    ConnectedStorage::Handle::CloseHandle((ConnectedStorage::Handle *)&TokenHandle);
  }
  ConnectedStorage::ContextDesc::ContextDesc(
    (ConnectedStorage::ContextDesc *)v27,
    (const struct ConnectedStorage::SimpleHStringWrapper *)&v23,
    (const struct ConnectedStorage::SimpleHStringWrapper *)&string,
    a2,
    a3,
    a4,
    TokenInformation,
    v30);
  TokenHandle = v28;
  ConnectedStorage::ContextDesc::ContextDesc(
    (ConnectedStorage::ContextDesc *)v28,
    (const struct ConnectedStorage::ContextDesc *)v27);
  std::function<void (enum ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>::function<void (enum ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>(
    v29,
    a5);
  ConnectedStorage::Contexts::DeactivateContext__lambda_741894f9671aca6d836da54fea2a7c7b___(
    this,
    (struct ConnectedStorage::ContextDesc *)v27,
    (struct ConnectedStorage::ContextDesc *)v28);
  ConnectedStorage::ContextDesc::~ContextDesc((ConnectedStorage::ContextDesc *)v27);
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v23);
  v23 = 0;
  LeaveCriticalSection(lpCriticalSection[0]);
  return std::function<long (void)>::~function<long (void)>(a5);
}

```

## disassembly

```asm
0x180032a40  push    rbp
0x180032a42  push    rbx
0x180032a43  push    rsi
0x180032a44  push    rdi
0x180032a45  push    r12
0x180032a47  push    r13
0x180032a49  push    r14
0x180032a4b  push    r15
0x180032a4d  lea     rbp, [rsp-28h]
0x180032a52  sub     rsp, 128h
0x180032a59  mov     r12, r9
0x180032a5c  mov     r13, r8
0x180032a5f  mov     r15, rdx
0x180032a62  mov     r14, rcx
0x180032a65  lea     rdx, [rcx+0B0h]; struct ConnectedStorage::Mutex *
0x180032a6c  lea     rcx, [rsp+160h+lpCriticalSection]; this
0x180032a71  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180032a76  nop
0x180032a77  mov     rcx, [r14+0A8h]
0x180032a7e  mov     rax, [rcx]
0x180032a81  mov     rdx, r15
0x180032a84  mov     rax, [rax+18h]
0x180032a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a8d  xor     ecx, ecx
0x180032a8f  test    al, al
0x180032a91  jz      loc_180032C41
0x180032a97  mov     [rsp+160h+var_108], rcx
0x180032a9c  mov     [rsp+160h+string], rcx
0x180032aa1  mov     [rbp+60h+arg_0], cl
0x180032aa4  mov     [rsp+160h+var_F8], rcx
0x180032aa9  mov     rsi, [r14+0A8h]
0x180032ab0  mov     rax, [rsi]
0x180032ab3  mov     rdi, [rax+10h]
0x180032ab7  lea     rcx, [rsp+160h+string]; this
0x180032abc  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x180032ac1  mov     rbx, rax
0x180032ac4  lea     rcx, [rsp+160h+var_108]; this
0x180032ac9  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x180032ace  lea     rcx, [rsp+160h+var_F8]
0x180032ad3  mov     [rsp+160h+var_138], rcx
0x180032ad8  lea     rcx, [rbp+60h+arg_0]
0x180032adc  mov     [rsp+160h+ReturnLength], rcx
0x180032ae1  mov     r9, rbx
0x180032ae4  mov     r8, rax
0x180032ae7  mov     rdx, r15
0x180032aea  mov     rcx, rsi
0x180032aed  mov     rax, rdi
0x180032af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032af5  xor     ebx, ebx
0x180032af7  cmp     [rbp+60h+arg_0], bl
0x180032afa  jnz     loc_180032C53
0x180032b00  mov     [rsp+160h+TokenInformation], ebx
0x180032b04  call    cs:__imp_RtlIsMultiSessionSku
0x180032b0a  test    al, al
0x180032b0c  jz      short loc_180032B73
0x180032b0e  mov     [rsp+160h+var_100], ebx
0x180032b12  mov     [rsp+160h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180032b1b  lea     rcx, [rsp+160h+TokenHandle]; this
0x180032b20  call    ?CloseHandle@Handle@ConnectedStorage@@AEAAXXZ; ConnectedStorage::Handle::CloseHandle(void)
0x180032b25  lea     rdx, [rsp+160h+TokenHandle]
0x180032b2a  mov     rcx, [rsp+160h+var_F8]
0x180032b2f  call    cs:__imp_UMgrQueryUserToken
0x180032b35  test    eax, eax
0x180032b37  js      loc_180032C65
0x180032b3d  lea     rax, [rsp+160h+var_100]
0x180032b42  mov     [rsp+160h+ReturnLength], rax; ReturnLength
0x180032b47  lea     r9d, [rbx+4]; TokenInformationLength
0x180032b4b  lea     r8, [rsp+160h+TokenInformation]; TokenInformation
0x180032b50  lea     edx, [rbx+0Ch]; TokenInformationClass
0x180032b53  mov     rcx, [rsp+160h+TokenHandle]; TokenHandle
0x180032b58  call    cs:__imp_NtQueryInformationToken
0x180032b5e  or      eax, 10000000h
0x180032b63  jl      loc_180032C32
0x180032b69  lea     rcx, [rsp+160h+TokenHandle]; this
0x180032b6e  call    ?CloseHandle@Handle@ConnectedStorage@@AEAAXXZ; ConnectedStorage::Handle::CloseHandle(void)
0x180032b73  mov     al, [rbp+60h+arg_0]
0x180032b76  mov     [rsp+160h+var_128], al; bool
0x180032b7a  mov     eax, [rsp+160h+TokenInformation]
0x180032b7e  mov     [rsp+160h+var_130], eax; unsigned int
0x180032b82  mov     [rsp+160h+var_138], r12; struct ConnectedStorage::SimpleHStringWrapper *
0x180032b87  mov     [rsp+160h+ReturnLength], r13; struct ConnectedStorage::SimpleHStringWrapper *
0x180032b8c  mov     r9, r15; struct ConnectedStorage::SimpleHStringWrapper *
0x180032b8f  lea     r8, [rsp+160h+string]; struct ConnectedStorage::SimpleHStringWrapper *
0x180032b94  lea     rdx, [rsp+160h+var_108]; struct ConnectedStorage::SimpleHStringWrapper *
0x180032b99  lea     rcx, [rbp+60h+var_E0]; this
0x180032b9d  call    ??0ContextDesc@ConnectedStorage@@QEAA@AEBVSimpleHStringWrapper@1@0000K_N@Z; ConnectedStorage::ContextDesc::ContextDesc(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ulong,bool)
0x180032ba2  nop
0x180032ba3  lea     rax, [rbp+60h+var_B0]
0x180032ba7  mov     [rsp+160h+TokenHandle], rax
0x180032bac  lea     rdx, [rbp+60h+var_E0]; struct ConnectedStorage::ContextDesc *
0x180032bb0  lea     rcx, [rbp+60h+var_B0]; this
0x180032bb4  call    ??0ContextDesc@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::ContextDesc::ContextDesc(ConnectedStorage::ContextDesc const &)
0x180032bb9  nop
0x180032bba  mov     rdx, [rbp+60h+arg_20]
0x180032bc1  lea     rcx, [rbp+60h+var_80]
0x180032bc5  call    ??0?$function@$$A6AXW4Status@WebService@ConnectedStorage@@VAtom@3@@Z@std@@QEAA@AEBV01@@Z; std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)>(std::function<void (ConnectedStorage::WebService::Status,ConnectedStorage::Atom)> const &)
0x180032bca  nop
0x180032bcb  lea     r8, [rbp+60h+var_B0]; struct ConnectedStorage::ContextDesc *
0x180032bcf  lea     rdx, [rbp+60h+var_E0]; struct ConnectedStorage::ContextDesc *
0x180032bd3  mov     rcx, r14; this
0x180032bd6  call    ConnectedStorage__Contexts__DeactivateContext__lambda_741894f9671aca6d836da54fea2a7c7b___
0x180032bdb  nop
0x180032bdc  lea     rcx, [rbp+60h+var_E0]; this
0x180032be0  call    ??1ContextDesc@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContextDesc::~ContextDesc(void)
0x180032be5  nop
0x180032be6  mov     rcx, [rsp+160h+string]; string
0x180032beb  call    cs:__imp_WindowsDeleteString
0x180032bf1  mov     [rsp+160h+string], rbx
0x180032bf6  mov     rcx, [rsp+160h+var_108]; string
0x180032bfb  call    cs:__imp_WindowsDeleteString
0x180032c01  mov     [rsp+160h+var_108], rbx
0x180032c06  mov     rcx, [rsp+160h+lpCriticalSection]; lpCriticalSection
0x180032c0b  call    cs:__imp_LeaveCriticalSection
0x180032c11  nop
0x180032c12  mov     rcx, [rbp+60h+arg_20]
0x180032c19  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x180032c1e  add     rsp, 128h
0x180032c25  pop     r15
0x180032c27  pop     r14
0x180032c29  pop     r13
0x180032c2b  pop     r12
0x180032c2d  pop     rdi
0x180032c2e  pop     rsi
0x180032c2f  pop     rbx
0x180032c30  pop     rbp
0x180032c31  retn
0x180032c32  lea     rdx, aHresultFromNtN; "HRESULT_FROM_NT(NtQueryInformationToken"...
0x180032c39  mov     ecx, eax; this
0x180032c3b  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180032c41  lea     rdx, aDeletelocaland; "DeleteLocalAndCloudStorageForContext No"...
0x180032c48  mov     ecx, 80832001h; this
0x180032c4d  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180032c53  lea     rdx, aDeletelocaland; "DeleteLocalAndCloudStorageForContext No"...
0x180032c5a  mov     ecx, 80832001h; this
0x180032c5f  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180032c65  lea     rdx, aUmgrqueryusert_0; "UMgrQueryUserToken(userContext, userTok"...
0x180032c6c  mov     ecx, eax; this
0x180032c6e  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
```
