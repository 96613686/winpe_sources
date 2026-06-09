# ConnectedStorage::UserManager::GetUserInfo(Windows::System::IUser *)

- ea: `0x18002bd64`
- end: `0x18002bf1b`
- name: `?GetUserInfo@UserManager@ConnectedStorage@@AEBA?AUUserInfo@12@PEAUIUser@System@Windows@@@Z`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d264`

## callees

- `0x18000a040`
- `0x18000aae4`
- `0x180010e6c`
- `0x180011b94`
- `0x180022dec`
- `0x1800284d4`
- `0x18002bb94`
- `0x18002bd64`
- `0x18002c358`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bed2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bee4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bef6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bed2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bee4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bef6`

## string_xrefs

- `0x18002be40`: `signInMgr->GetHandleForUser(user, &token)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ConnectedStorage::UserManager::GetUserInfo(__int64 a1, __int64 a2, __int64 a3)
{
  int v5; // eax
  const unsigned __int16 *v6; // r8
  int v7; // eax
  const unsigned __int16 *v8; // r8
  bool v9; // r14
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  HSTRING *AddressOf; // rax
  int v12; // eax
  const unsigned __int16 *v13; // r8
  int v14; // eax
  const unsigned __int16 *v15; // r8
  HSTRING *v16; // rbx
  HSTRING *v17; // rax
  HSTRING string; // [rsp+28h] [rbp-28h] BYREF
  HSTRING v20; // [rsp+30h] [rbp-20h] BYREF
  HSTRING v21; // [rsp+38h] [rbp-18h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-10h] BYREF
  int v23; // [rsp+80h] [rbp+30h] BYREF
  __int64 v24; // [rsp+88h] [rbp+38h]
  unsigned __int64 v25; // [rsp+98h] [rbp+48h] BYREF

  v24 = a2;
  v25 = 0;
  v22[0] = 0;
  v5 = Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>::As<Windows::System::Internal::ISignInStateManager>(
         (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))(a1 + 288),
         (__int64)v22);
  if ( v5 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v5,
      (int)L"_userMgrStatics.As(&signInMgr)",
      v6);
  v23 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a3 + 64LL))(a3, &v23);
  if ( v7 < 0 )
    ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)(unsigned int)v7, (int)L"user->get_Type(&userType)", v8);
  v9 = (unsigned int)(v23 - 2) <= 1;
  v21 = 0;
  v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a3 + 48LL);
  AddressOf = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v21);
  v12 = v10(a3, AddressOf);
  if ( v12 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v12,
      (int)L"user->get_NonRoamableId(nonRoamableId.GetAddressOf())",
      v13);
  v14 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int64 *))(*(_QWORD *)v22[0] + 136LL))(v22[0], a3, &v25);
  if ( v14 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v14,
      (int)L"signInMgr->GetHandleForUser(user, &token)",
      v15);
  v20 = 0;
  string = 0;
  v16 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v20);
  v17 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&string);
  ConnectedStorage::UserManager::GetUserSidAndXuidFromContext(v25, v17, v16);
  LODWORD(v16) = ConnectedStorage::UserManager::GetSessionIdFromContext(v25);
  *(_QWORD *)a2 = v25;
  ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper((HSTRING *)(a2 + 8), &v21);
  ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper((HSTRING *)(a2 + 16), &string);
  ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper((HSTRING *)(a2 + 24), &v20);
  *(_BYTE *)(a2 + 32) = v9;
  std::wstring::wstring(a2 + 40);
  *(_DWORD *)(a2 + 72) = (_DWORD)v16;
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v20);
  v20 = 0;
  WindowsDeleteString(v21);
  v21 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v22);
  return a2;
}

```

## disassembly

```asm
0x18002bd64  mov     [rsp-28h+arg_8], rdx
0x18002bd69  push    rbp
0x18002bd6a  push    rbx
0x18002bd6b  push    rsi
0x18002bd6c  push    rdi
0x18002bd6d  push    r14
0x18002bd6f  mov     rbp, rsp
0x18002bd72  sub     rsp, 50h
0x18002bd76  mov     rdi, r8
0x18002bd79  mov     rsi, rdx
0x18002bd7c  mov     [rbp+arg_18], 0
0x18002bd84  mov     [rbp+var_10], 0
0x18002bd8c  add     rcx, 120h
0x18002bd93  lea     rdx, [rbp+var_10]
0x18002bd97  call    ??$As@UISignInStateManager@Internal@System@Windows@@@?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>::As<Windows::System::Internal::ISignInStateManager>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>)
0x18002bd9c  test    eax, eax
0x18002bd9e  jns     short loc_18002BDAF
0x18002bda0  lea     rdx, aUsermgrstatics_0; "_userMgrStatics.As(&signInMgr)"
0x18002bda7  mov     ecx, eax; this
0x18002bda9  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002bdaf  mov     [rbp+arg_0], 0
0x18002bdb6  mov     rax, [rdi]
0x18002bdb9  lea     rdx, [rbp+arg_0]
0x18002bdbd  mov     rcx, rdi
0x18002bdc0  mov     rax, [rax+40h]
0x18002bdc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdc9  test    eax, eax
0x18002bdcb  jns     short loc_18002BDDC
0x18002bdcd  lea     rdx, aUserGetTypeUse; "user->get_Type(&userType)"
0x18002bdd4  mov     ecx, eax; this
0x18002bdd6  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002bddc  mov     eax, [rbp+arg_0]
0x18002bddf  add     eax, 0FFFFFFFEh
0x18002bde2  cmp     eax, 1
0x18002bde5  setbe   r14b
0x18002bde9  mov     [rbp+var_18], 0
0x18002bdf1  mov     rax, [rdi]
0x18002bdf4  mov     rbx, [rax+30h]
0x18002bdf8  lea     rcx, [rbp+var_18]; this
0x18002bdfc  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x18002be01  mov     rdx, rax
0x18002be04  mov     rcx, rdi
0x18002be07  mov     rax, rbx
0x18002be0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be0f  test    eax, eax
0x18002be11  jns     short loc_18002BE22
0x18002be13  lea     rdx, aUserGetNonroam; "user->get_NonRoamableId(nonRoamableId.G"...
0x18002be1a  mov     ecx, eax; this
0x18002be1c  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002be22  mov     rcx, [rbp+var_10]
0x18002be26  mov     rax, [rcx]
0x18002be29  lea     r8, [rbp+arg_18]
0x18002be2d  mov     rdx, rdi
0x18002be30  mov     rax, [rax+88h]
0x18002be37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be3c  test    eax, eax
0x18002be3e  jns     short loc_18002BE4F
0x18002be40  lea     rdx, aSigninmgrGetha; "signInMgr->GetHandleForUser(user, &toke"...
0x18002be47  mov     ecx, eax; this
0x18002be49  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002be4f  mov     [rbp+var_20], 0
0x18002be57  mov     [rbp+string], 0
0x18002be5f  lea     rcx, [rbp+var_20]; this
0x18002be63  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x18002be68  mov     rbx, rax
0x18002be6b  lea     rcx, [rbp+string]; this
0x18002be6f  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x18002be74  mov     r8, rbx; HSTRING *
0x18002be77  mov     rdx, rax; HSTRING *
0x18002be7a  mov     rcx, [rbp+arg_18]; unsigned __int64
0x18002be7e  call    ?GetUserSidAndXuidFromContext@UserManager@ConnectedStorage@@SAX_KPEAPEAUHSTRING__@@1@Z; ConnectedStorage::UserManager::GetUserSidAndXuidFromContext(unsigned __int64,HSTRING__ * *,HSTRING__ * *)
0x18002be83  mov     rcx, [rbp+arg_18]; unsigned __int64
0x18002be87  call    ?GetSessionIdFromContext@UserManager@ConnectedStorage@@CAI_K@Z; ConnectedStorage::UserManager::GetSessionIdFromContext(unsigned __int64)
0x18002be8c  mov     ebx, eax
0x18002be8e  mov     rcx, [rbp+arg_18]
0x18002be92  mov     [rsi], rcx
0x18002be95  lea     rcx, [rsi+8]; newString
0x18002be99  lea     rdx, [rbp+var_18]; struct ConnectedStorage::SimpleHStringWrapper *
0x18002be9d  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x18002bea2  nop
0x18002bea3  lea     rcx, [rsi+10h]; newString
0x18002bea7  lea     rdx, [rbp+string]; struct ConnectedStorage::SimpleHStringWrapper *
0x18002beab  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x18002beb0  nop
0x18002beb1  lea     rcx, [rsi+18h]; newString
0x18002beb5  lea     rdx, [rbp+var_20]; struct ConnectedStorage::SimpleHStringWrapper *
0x18002beb9  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x18002bebe  mov     [rsi+20h], r14b
0x18002bec2  lea     rcx, [rsi+28h]
0x18002bec6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002becb  mov     [rsi+48h], ebx
0x18002bece  mov     rcx, [rbp+string]; string
0x18002bed2  call    cs:__imp_WindowsDeleteString
0x18002bed8  mov     [rbp+string], 0
0x18002bee0  mov     rcx, [rbp+var_20]; string
0x18002bee4  call    cs:__imp_WindowsDeleteString
0x18002beea  mov     [rbp+var_20], 0
0x18002bef2  mov     rcx, [rbp+var_18]; string
0x18002bef6  call    cs:__imp_WindowsDeleteString
0x18002befc  mov     [rbp+var_18], 0
0x18002bf04  lea     rcx, [rbp+var_10]
0x18002bf08  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bf0d  mov     rax, rsi
0x18002bf10  add     rsp, 50h
0x18002bf14  pop     r14
0x18002bf16  pop     rdi
0x18002bf17  pop     rsi
0x18002bf18  pop     rbx
0x18002bf19  pop     rbp
0x18002bf1a  retn
```
