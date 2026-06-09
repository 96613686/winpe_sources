# ConnectedStorage::UserManager::GetUserInfoFromUserContextToken(unsigned __int64,bool,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *,bool *)

- ea: `0x18002bf30`
- end: `0x18002c1ea`
- name: `?GetUserInfoFromUserContextToken@UserManager@ConnectedStorage@@UEBAX_K_NPEAPEAUHSTRING__@@22PEA_N@Z`
- size: `698`
- prototype: `void __usercall(ConnectedStorage::UserManager *__hidden this@<rcx>, unsigned __int64@<rdx>, bool@<r8b>, HSTRING *@<r9>, HSTRING *, HSTRING *, bool *)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a040`
- `0x18000aae4`
- `0x18000cb9c`
- `0x18000d2f4`
- `0x180012fc0`
- `0x18001c63c`
- `0x180020084`
- `0x180020898`
- `0x180022dec`
- `0x1800284d4`
- `0x180029584`
- `0x18002a714`
- `0x18002a740`
- `0x18002ad94`
- `0x18002bf30`
- `0x18002c358`
- `0x18002d264`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c1cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c1cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c02b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c03d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c0ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c0c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c02b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c03d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c0ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c0c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall ConnectedStorage::UserManager::GetUserInfoFromUserContextToken(
        ConnectedStorage::UserManager *this,
        unsigned __int64 a2,
        char *a3,
        HSTRING *a4,
        HSTRING *a5,
        HSTRING *a6,
        bool *a7)
{
  char v8; // r15
  __int64 v11; // rcx
  _QWORD *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r10
  __int64 v15; // rax
  HSTRING *AddressOf; // rbx
  HSTRING *v17; // rax
  __int64 v18; // rbx
  const unsigned __int16 *v19; // r8
  int v20; // eax
  const unsigned __int16 *v21; // r8
  __int64 v22; // rbx
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, unsigned __int64, __int64 *); // rbx
  int v25; // eax
  const unsigned __int16 *v26; // r8
  int v27; // eax
  const unsigned __int16 *v28; // r8
  bool v29; // bl
  int v30; // eax
  const unsigned __int16 *v31; // r8
  __int64 v32; // [rsp+20h] [rbp-30h] BYREF
  HSTRING v33; // [rsp+28h] [rbp-28h] BYREF
  __int64 v34; // [rsp+30h] [rbp-20h] BYREF
  __int64 v35; // [rsp+38h] [rbp-18h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+40h] [rbp-10h] BYREF
  int v37; // [rsp+80h] [rbp+30h] BYREF
  HSTRING string; // [rsp+88h] [rbp+38h] BYREF

  v8 = (char)a3;
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 168),
    a3);
  ConnectedStorage::UserManager::EnsureUserStatics(this);
  std::vector<ConnectedStorage::BlobRecord>::end((char *)this + 216, &string);
  v12 = (_QWORD *)std::vector<ConnectedStorage::ContextDesc>::begin(v11, &v33);
  std::find_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_ConnectedStorage::UserManager::UserInfo_______lambda_9acd6550c821cab46c34ad19c26fddd7___(
    &v34,
    *v12,
    v13,
    a2);
  v15 = std::vector<ConnectedStorage::BlobRecord>::end(v14, &string);
  if ( (unsigned __int8)std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>>::operator!=(
                          &v34,
                          v15) )
  {
    v33 = 0;
    string = 0;
    AddressOf = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&string);
    v17 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v33);
    ConnectedStorage::UserManager::GetUserSidAndXuidFromContext(a2, v17, AddressOf);
    v18 = v34;
    if ( !(unsigned int)ConnectedStorage::SimpleHStringWrapper::Compare(
                          (ConnectedStorage::SimpleHStringWrapper *)&string,
                          (const struct ConnectedStorage::SimpleHStringWrapper *)(v34 + 24)) )
    {
      *a7 = *(_BYTE *)(v18 + 32);
      ConnectedStorage::SimpleHStringWrapper::DuplicateTo((ConnectedStorage::SimpleHStringWrapper *)(v18 + 8), a4);
      v22 = std::shared_ptr<ConnectedStorage::UploadingContext const>::operator-><ConnectedStorage::UploadingContext const,0>(&v34);
      ConnectedStorage::SimpleHStringWrapper::DuplicateTo((ConnectedStorage::SimpleHStringWrapper *)(v22 + 16), a5);
      ConnectedStorage::SimpleHStringWrapper::DuplicateTo((ConnectedStorage::SimpleHStringWrapper *)(v22 + 24), a6);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v33);
      v33 = 0;
      goto LABEL_23;
    }
    if ( v8 )
      ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x8083000DLL, (int)L"GamerAccount changed", v19);
    ConnectedStorage::UserManager::FireUserSignOut(this, a2);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v33);
  }
  v35 = 0;
  v20 = Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>::As<Windows::System::Internal::ISignInStateManager>(
          (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))this + 36,
          (__int64)&v35);
  if ( v20 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v20,
      (int)L"_userMgrStatics.As(&signInMgr)",
      v21);
  v32 = 0;
  v23 = v35;
  v24 = *(__int64 (__fastcall **)(__int64, unsigned __int64, __int64 *))(*(_QWORD *)v35 + 160LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  v25 = v24(v23, a2, &v32);
  if ( v25 == -2136866037 )
  {
    v25 = -2138890239;
    goto LABEL_12;
  }
  if ( v25 < 0 )
LABEL_12:
    ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)(unsigned int)v25, (int)L"GetUserForContext", v26);
  v37 = 0;
  v27 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v32 + 64LL))(v32, &v37);
  if ( v27 < 0 )
    ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)(unsigned int)v27, (int)L"user->get_Type(&userType)", v28);
  if ( v37 == 2 || (v29 = 0, v37 == 3) )
    v29 = 1;
  v30 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 48LL))(v32, a4);
  if ( v30 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v30,
      (int)L"user->get_NonRoamableId(nonRoamableId)",
      v31);
  ConnectedStorage::UserManager::GetUserSidAndXuidFromContext(a2, a5, a6);
  *a7 = v29;
  if ( !v8 )
    ConnectedStorage::UserManager::OnUserEvent(this, 0, v32);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
LABEL_23:
  LeaveCriticalSection(lpCriticalSection[0]);
}

```

## disassembly

```asm
0x18002bf30  mov     [rsp-28h+arg_10], rbx
0x18002bf35  mov     [rsp-28h+arg_18], rsi
0x18002bf3a  push    rbp
0x18002bf3b  push    rdi
0x18002bf3c  push    r12
0x18002bf3e  push    r14
0x18002bf40  push    r15
0x18002bf42  mov     rbp, rsp
0x18002bf45  sub     rsp, 50h
0x18002bf49  mov     r12, r9
0x18002bf4c  mov     r15b, r8b
0x18002bf4f  mov     rsi, rdx
0x18002bf52  mov     r14, rcx
0x18002bf55  lea     rdx, [rcx+0A8h]; struct ConnectedStorage::Mutex *
0x18002bf5c  lea     rcx, [rbp+lpCriticalSection]; this
0x18002bf60  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18002bf65  nop
0x18002bf66  mov     rcx, r14; this
0x18002bf69  call    ?EnsureUserStatics@UserManager@ConnectedStorage@@AEBAXXZ; ConnectedStorage::UserManager::EnsureUserStatics(void)
0x18002bf6e  lea     r10, [r14+0D8h]
0x18002bf75  lea     rdx, [rbp+string]
0x18002bf79  mov     rcx, r10
0x18002bf7c  call    ?end@?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::BlobRecord>::end(void)
0x18002bf81  mov     r8, [rax]
0x18002bf84  lea     rdx, [rbp+var_28]
0x18002bf88  call    ?begin@?$vector@VContextDesc@ConnectedStorage@@V?$allocator@VContextDesc@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VContextDesc@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::ContextDesc>::begin(void)
0x18002bf8d  mov     r9, rsi
0x18002bf90  mov     rdx, [rax]
0x18002bf93  lea     rcx, [rbp+var_20]
0x18002bf97  call    std__find_if_std___Vector_iterator_std___Vector_val_std___Simple_types_ConnectedStorage__UserManager__UserInfo_______lambda_9acd6550c821cab46c34ad19c26fddd7___
0x18002bf9c  lea     rdx, [rbp+string]
0x18002bfa0  mov     rcx, r10
0x18002bfa3  call    ?end@?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::BlobRecord>::end(void)
0x18002bfa8  mov     rdx, rax
0x18002bfab  lea     rcx, [rbp+var_20]
0x18002bfaf  call    ??9?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@VNtmTransferWrapper@ConnectedStorage@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>>::operator!=(std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>> const &)
0x18002bfb4  test    al, al
0x18002bfb6  jz      loc_18002C043
0x18002bfbc  mov     [rbp+var_28], 0
0x18002bfc4  mov     [rbp+string], 0
0x18002bfcc  lea     rcx, [rbp+string]; this
0x18002bfd0  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x18002bfd5  mov     rbx, rax
0x18002bfd8  lea     rcx, [rbp+var_28]; this
0x18002bfdc  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x18002bfe1  mov     r8, rbx; HSTRING *
0x18002bfe4  mov     rdx, rax; HSTRING *
0x18002bfe7  mov     rcx, rsi; unsigned __int64
0x18002bfea  call    ?GetUserSidAndXuidFromContext@UserManager@ConnectedStorage@@SAX_KPEAPEAUHSTRING__@@1@Z; ConnectedStorage::UserManager::GetUserSidAndXuidFromContext(unsigned __int64,HSTRING__ * *,HSTRING__ * *)
0x18002bfef  mov     rbx, [rbp+var_20]
0x18002bff3  lea     rdx, [rbx+18h]; struct ConnectedStorage::SimpleHStringWrapper *
0x18002bff7  lea     rcx, [rbp+string]; this
0x18002bffb  call    ?Compare@SimpleHStringWrapper@ConnectedStorage@@QEBAHAEBV12@@Z; ConnectedStorage::SimpleHStringWrapper::Compare(ConnectedStorage::SimpleHStringWrapper const &)
0x18002c000  test    eax, eax
0x18002c002  jz      short loc_18002C06E
0x18002c004  test    r15b, r15b
0x18002c007  jz      short loc_18002C01B
0x18002c009  lea     rdx, aGameraccountCh; "GamerAccount changed"
0x18002c010  mov     ecx, 8083000Dh; this
0x18002c015  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002c01b  mov     rdx, rsi; unsigned __int64
0x18002c01e  mov     rcx, r14; this
0x18002c021  call    ?FireUserSignOut@UserManager@ConnectedStorage@@AEBAX_K@Z; ConnectedStorage::UserManager::FireUserSignOut(unsigned __int64)
0x18002c026  nop
0x18002c027  mov     rcx, [rbp+string]; string
0x18002c02b  call    cs:__imp_WindowsDeleteString
0x18002c031  mov     [rbp+string], 0
0x18002c039  mov     rcx, [rbp+var_28]; string
0x18002c03d  call    cs:__imp_WindowsDeleteString
0x18002c043  mov     [rbp+var_18], 0
0x18002c04b  lea     rcx, [r14+120h]
0x18002c052  lea     rdx, [rbp+var_18]
0x18002c056  call    ??$As@UISignInStateManager@Internal@System@Windows@@@?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>::As<Windows::System::Internal::ISignInStateManager>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>)
0x18002c05b  test    eax, eax
0x18002c05d  jns     short loc_18002C0D3
0x18002c05f  lea     rdx, aUsermgrstatics_0; "_userMgrStatics.As(&signInMgr)"
0x18002c066  mov     ecx, eax; this
0x18002c068  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002c06e  mov     cl, [rbx+20h]
0x18002c071  mov     rax, [rbp+arg_30]
0x18002c075  mov     [rax], cl
0x18002c077  lea     rcx, [rbx+8]; this
0x18002c07b  mov     rdx, r12; HSTRING *
0x18002c07e  call    ?DuplicateTo@SimpleHStringWrapper@ConnectedStorage@@QEBAXPEAPEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::DuplicateTo(HSTRING__ * *)
0x18002c083  lea     rcx, [rbp+var_20]
0x18002c087  call    ??$?C$$CBVUploadingContext@ConnectedStorage@@$0A@@?$shared_ptr@$$CBVUploadingContext@ConnectedStorage@@@std@@QEBAPEBVUploadingContext@ConnectedStorage@@XZ; std::shared_ptr<ConnectedStorage::UploadingContext const>::operator-><ConnectedStorage::UploadingContext const,0>(void)
0x18002c08c  mov     rbx, rax
0x18002c08f  lea     rcx, [rax+10h]; this
0x18002c093  mov     rdx, [rbp+arg_20]; HSTRING *
0x18002c097  call    ?DuplicateTo@SimpleHStringWrapper@ConnectedStorage@@QEBAXPEAPEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::DuplicateTo(HSTRING__ * *)
0x18002c09c  lea     rcx, [rbx+18h]; this
0x18002c0a0  mov     rdx, [rbp+arg_28]; HSTRING *
0x18002c0a4  call    ?DuplicateTo@SimpleHStringWrapper@ConnectedStorage@@QEBAXPEAPEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::DuplicateTo(HSTRING__ * *)
0x18002c0a9  nop
0x18002c0aa  mov     rcx, [rbp+string]; string
0x18002c0ae  call    cs:__imp_WindowsDeleteString
0x18002c0b4  mov     [rbp+string], 0
0x18002c0bc  mov     rcx, [rbp+var_28]; string
0x18002c0c0  call    cs:__imp_WindowsDeleteString
0x18002c0c6  mov     [rbp+var_28], 0
0x18002c0ce  jmp     loc_18002C1C7
0x18002c0d3  mov     [rbp+var_30], 0
0x18002c0db  mov     rdi, [rbp+var_18]
0x18002c0df  mov     rax, [rdi]
0x18002c0e2  mov     rbx, [rax+0A0h]
0x18002c0e9  lea     rcx, [rbp+var_30]
0x18002c0ed  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c0f2  lea     r8, [rbp+var_30]
0x18002c0f6  mov     rdx, rsi
0x18002c0f9  mov     rcx, rdi
0x18002c0fc  mov     rax, rbx
0x18002c0ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c104  cmp     eax, 80A2030Bh
0x18002c109  jnz     short loc_18002C112
0x18002c10b  mov     eax, 80832001h
0x18002c110  jmp     short loc_18002C116
0x18002c112  test    eax, eax
0x18002c114  jns     short loc_18002C125
0x18002c116  lea     rdx, aGetuserforcont; "GetUserForContext"
0x18002c11d  mov     ecx, eax; this
0x18002c11f  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002c125  mov     [rbp+arg_0], 0
0x18002c12c  mov     rcx, [rbp+var_30]
0x18002c130  mov     rax, [rcx]
0x18002c133  lea     rdx, [rbp+arg_0]
0x18002c137  mov     rax, [rax+40h]
0x18002c13b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c140  test    eax, eax
0x18002c142  jns     short loc_18002C153
0x18002c144  lea     rdx, aUserGetTypeUse; "user->get_Type(&userType)"
0x18002c14b  mov     ecx, eax; this
0x18002c14d  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002c153  cmp     [rbp+arg_0], 2
0x18002c157  jz      short loc_18002C161
0x18002c159  xor     bl, bl
0x18002c15b  cmp     [rbp+arg_0], 3
0x18002c15f  jnz     short loc_18002C163
0x18002c161  mov     bl, 1
0x18002c163  mov     rcx, [rbp+var_30]
0x18002c167  mov     rax, [rcx]
0x18002c16a  mov     rdx, r12
0x18002c16d  mov     rax, [rax+30h]
0x18002c171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c176  test    eax, eax
0x18002c178  jns     short loc_18002C189
0x18002c17a  lea     rdx, aUserGetNonroam_0; "user->get_NonRoamableId(nonRoamableId)"
0x18002c181  mov     ecx, eax; this
0x18002c183  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002c189  mov     r8, [rbp+arg_28]; HSTRING *
0x18002c18d  mov     rdx, [rbp+arg_20]; HSTRING *
0x18002c191  mov     rcx, rsi; unsigned __int64
0x18002c194  call    ?GetUserSidAndXuidFromContext@UserManager@ConnectedStorage@@SAX_KPEAPEAUHSTRING__@@1@Z; ConnectedStorage::UserManager::GetUserSidAndXuidFromContext(unsigned __int64,HSTRING__ * *,HSTRING__ * *)
0x18002c199  mov     rax, [rbp+arg_30]
0x18002c19d  mov     [rax], bl
0x18002c19f  test    r15b, r15b
0x18002c1a2  jnz     short loc_18002C1B3
0x18002c1a4  mov     r8, [rbp+var_30]
0x18002c1a8  xor     edx, edx
0x18002c1aa  mov     rcx, r14
0x18002c1ad  call    ?OnUserEvent@UserManager@ConnectedStorage@@AEBAXW4UserSignInOut@2@PEAUIUser@System@Windows@@@Z; ConnectedStorage::UserManager::OnUserEvent(ConnectedStorage::UserSignInOut,Windows::System::IUser *)
0x18002c1b2  nop
0x18002c1b3  lea     rcx, [rbp+var_30]
0x18002c1b7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c1bc  nop
0x18002c1bd  lea     rcx, [rbp+var_18]
0x18002c1c1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002c1c6  nop
0x18002c1c7  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18002c1cb  call    cs:__imp_LeaveCriticalSection
0x18002c1d1  lea     r11, [rsp+50h+var_s0]
0x18002c1d6  mov     rbx, [r11+40h]
0x18002c1da  mov     rsi, [r11+48h]
0x18002c1de  mov     rsp, r11
0x18002c1e1  pop     r15
0x18002c1e3  pop     r14
0x18002c1e5  pop     r12
0x18002c1e7  pop     rdi
0x18002c1e8  pop     rbp
0x18002c1e9  retn
```
