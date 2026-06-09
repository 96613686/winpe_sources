# ConnectedStorage::UserManager::OnUserEvent(ConnectedStorage::UserSignInOut,Windows::System::IUser *)

- ea: `0x18002d264`
- end: `0x18002d582`
- name: `?OnUserEvent@UserManager@ConnectedStorage@@AEBAXW4UserSignInOut@2@PEAUIUser@System@Windows@@@Z`
- size: `798`
- prototype: ``
- caller_count: `3`
- callee_count: `21`
- tags: ``

## callers

- `0x18002ad94`
- `0x18002bf30`
- `0x18002ce30`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x18000cb9c`
- `0x18000d2b8`
- `0x180011b94`
- `0x180012ed8`
- `0x180012f7c`
- `0x180014980`
- `0x180019128`
- `0x180022dec`
- `0x180028bbc`
- `0x1800290a0`
- `0x1800299a8`
- `0x180029a08`
- `0x180029c04`
- `0x180029f78`
- `0x18002bd64`
- `0x18002d264`
- `0x18002e2f0`
- `0x18002e468`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d546`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d546`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d527`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d537`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d527`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d537`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall ConnectedStorage::UserManager::OnUserEvent(__int64 a1, int a2, char *a3)
{
  __int64 (__fastcall *v6)(char *, HSTRING *); // rbx
  HSTRING *AddressOf; // rax
  int v8; // eax
  const unsigned __int16 *v9; // r8
  const struct ConnectedStorage::UserManager::UserInfo *v10; // rbx
  const struct ConnectedStorage::UserManager::UserInfo *v11; // rsi
  HSTRING *v12; // rsi
  HSTRING *i; // rax
  __int64 v14; // rbx
  __int64 v15; // r12
  HSTRING *v16; // rax
  HSTRING v17; // [rsp+20h] [rbp-99h] BYREF
  HSTRING string; // [rsp+28h] [rbp-91h] BYREF
  _BYTE v19[8]; // [rsp+30h] [rbp-89h] BYREF
  __int128 v20; // [rsp+38h] [rbp-81h] BYREF
  int v21; // [rsp+48h] [rbp-71h]
  HSTRING newString; // [rsp+50h] [rbp-69h] BYREF
  HSTRING v23; // [rsp+58h] [rbp-61h] BYREF
  __int64 v24; // [rsp+60h] [rbp-59h] BYREF
  std::_Ref_count_base *v25; // [rsp+68h] [rbp-51h]
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+70h] [rbp-49h] BYREF
  HSTRING v27; // [rsp+80h] [rbp-39h] BYREF
  __int128 v28; // [rsp+88h] [rbp-31h] BYREF
  int v29; // [rsp+98h] [rbp-21h] BYREF
  HSTRING v30; // [rsp+A0h] [rbp-19h]
  HSTRING v31; // [rsp+A8h] [rbp-11h]
  HSTRING *v32; // [rsp+B8h] [rbp-1h]

  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)(a1 + 168),
    a3);
  v17 = 0;
  string = 0;
  v6 = *(__int64 (__fastcall **)(char *, HSTRING *))(*(_QWORD *)a3 + 48LL);
  AddressOf = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v17);
  v8 = v6(a3, AddressOf);
  if ( v8 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v8,
      (int)L"user->get_NonRoamableId(nonRoamableId.GetAddressOf())",
      v9);
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      v10 = *(const struct ConnectedStorage::UserManager::UserInfo **)(a1 + 216);
      v11 = *(const struct ConnectedStorage::UserManager::UserInfo **)(a1 + 224);
      while ( v10 != v11 && !(unsigned __int8)ConnectedStorage::SimpleHStringWrapper::operator==((char *)v10 + 8, &v17) )
        v10 = (const struct ConnectedStorage::UserManager::UserInfo *)((char *)v10 + 80);
      if ( v10 != *(const struct ConnectedStorage::UserManager::UserInfo **)(a1 + 224) )
      {
        ConnectedStorage::SimpleHStringWrapper::operator=(&v17);
        ConnectedStorage::SimpleHStringWrapper::operator=(&string);
        if ( *(_QWORD *)(a1 + 248) == *(_QWORD *)(a1 + 256) )
        {
          std::vector<ConnectedStorage::UserManager::UserInfo>::_Emplace_reallocate<ConnectedStorage::UserManager::UserInfo const &>(
            a1 + 240,
            *(_QWORD *)(a1 + 248),
            v10);
        }
        else
        {
          ConnectedStorage::UserManager::UserInfo::UserInfo(
            *(ConnectedStorage::UserManager::UserInfo **)(a1 + 248),
            v10);
          *(_QWORD *)(a1 + 248) += 80LL;
        }
        std::vector<ConnectedStorage::UserManager::UserInfo>::erase(a1 + 216, v19, v10);
      }
    }
  }
  else
  {
    ConnectedStorage::UserManager::GetUserInfo(a1, (__int64)&v27, (__int64)a3);
    ConnectedStorage::SimpleHStringWrapper::operator=(&string);
    v12 = *(HSTRING **)(a1 + 216);
    for ( i = *(HSTRING **)(a1 + 224); v12 != i; v12 += 10 )
    {
      if ( *v12 == v27 )
        break;
    }
    v14 = *(_QWORD *)(a1 + 240);
    v15 = *(_QWORD *)(a1 + 248);
    while ( v14 != v15
         && (!(unsigned __int8)ConnectedStorage::SimpleHStringWrapper::operator==(&v28, v14 + 8)
          || !(unsigned __int8)ConnectedStorage::SimpleHStringWrapper::operator==(&v29, v14 + 24)) )
      v14 += 80;
    if ( v14 != *(_QWORD *)(a1 + 248) )
      std::vector<ConnectedStorage::UserManager::UserInfo>::erase(a1 + 240, v19, v14);
    v16 = *(HSTRING **)(a1 + 224);
    if ( v12 == v16 )
    {
      if ( v16 == *(HSTRING **)(a1 + 232) )
      {
        std::vector<ConnectedStorage::UserManager::UserInfo>::_Emplace_reallocate<ConnectedStorage::UserManager::UserInfo>(
          a1 + 216,
          *(_QWORD *)(a1 + 224),
          &v27);
      }
      else
      {
        ConnectedStorage::UserManager::UserInfo::UserInfo(*(_QWORD *)(a1 + 224), &v27);
        *(_QWORD *)(a1 + 224) += 80LL;
      }
    }
    ConnectedStorage::UserManager::UserInfo::~UserInfo(&v27);
  }
  if ( *(_QWORD *)(a1 + 80) )
  {
    ConnectedStorage::UserManager::weak_from_this(a1, &v24);
    std::weak_ptr<ConnectedStorage::Context>::weak_ptr<ConnectedStorage::Context>(&v20, &v24);
    v21 = a2;
    ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&newString, &v17);
    ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v23, &string);
    v27 = (HSTRING)off_180090008;
    v28 = v20;
    v20 = 0;
    v29 = v21;
    v30 = newString;
    newString = 0;
    v31 = v23;
    v23 = 0;
    v32 = &v27;
    ConnectedStorage::ExecuteQueue::Enqueue((ConnectedStorage::ExecuteQueue *)(a1 + 336));
    lambda_b932c5694bc3fc5d357785cd48396a70_::__lambda_b932c5694bc3fc5d357785cd48396a70_(&v20);
    if ( v25 )
      std::_Ref_count_base::_Decwref(v25);
  }
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v17);
  v17 = 0;
  LeaveCriticalSection(lpCriticalSection[0]);
}

```

## disassembly

```asm
0x18002d264  mov     [rsp-8+arg_8], rbx
0x18002d269  push    rbp
0x18002d26a  push    rsi
0x18002d26b  push    rdi
0x18002d26c  push    r12
0x18002d26e  push    r13
0x18002d270  push    r14
0x18002d272  push    r15
0x18002d274  lea     rbp, [rsp-27h]
0x18002d279  sub     rsp, 0E0h
0x18002d280  mov     rax, cs:__security_cookie
0x18002d287  xor     rax, rsp
0x18002d28a  mov     [rbp+57h+var_40], rax
0x18002d28e  mov     rsi, r8
0x18002d291  mov     r13d, edx
0x18002d294  mov     rdi, rcx
0x18002d297  lea     rdx, [rcx+0A8h]; struct ConnectedStorage::Mutex *
0x18002d29e  lea     rcx, [rbp+57h+lpCriticalSection]; this
0x18002d2a2  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18002d2a7  nop
0x18002d2a8  xor     r15d, r15d
0x18002d2ab  mov     [rsp+110h+var_F0], r15
0x18002d2b0  mov     [rsp+110h+string], r15
0x18002d2b5  mov     rax, [rsi]
0x18002d2b8  mov     rbx, [rax+30h]
0x18002d2bc  lea     rcx, [rsp+110h+var_F0]; this
0x18002d2c1  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x18002d2c6  mov     rdx, rax
0x18002d2c9  mov     rcx, rsi
0x18002d2cc  mov     rax, rbx
0x18002d2cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2d4  test    eax, eax
0x18002d2d6  js      loc_18002D573
0x18002d2dc  test    r13d, r13d
0x18002d2df  jz      loc_18002D389
0x18002d2e5  cmp     r13d, 1
0x18002d2e9  jnz     loc_18002D464
0x18002d2ef  lea     r14, [rdi+0D8h]
0x18002d2f6  mov     rbx, [r14]
0x18002d2f9  mov     rsi, [r14+8]
0x18002d2fd  jmp     short loc_18002D315
0x18002d2ff  lea     rcx, [rbx+8]
0x18002d303  lea     rdx, [rsp+110h+var_F0]
0x18002d308  call    ??8SimpleHStringWrapper@ConnectedStorage@@QEBA_NAEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator==(ConnectedStorage::SimpleHStringWrapper const &)
0x18002d30d  test    al, al
0x18002d30f  jnz     short loc_18002D31A
0x18002d311  add     rbx, 50h ; 'P'
0x18002d315  cmp     rbx, rsi
0x18002d318  jnz     short loc_18002D2FF
0x18002d31a  cmp     rbx, [rdi+0E0h]
0x18002d321  jz      loc_18002D464
0x18002d327  lea     rdx, [rbx+8]
0x18002d32b  lea     rcx, [rsp+110h+var_F0]; newString
0x18002d330  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x18002d335  lea     rdx, [rbx+18h]
0x18002d339  lea     rcx, [rsp+110h+string]; newString
0x18002d33e  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x18002d343  lea     rsi, [rdi+0F0h]
0x18002d34a  mov     rax, [rsi+8]
0x18002d34e  cmp     rax, [rsi+10h]
0x18002d352  jz      short loc_18002D366
0x18002d354  mov     rdx, rbx; struct ConnectedStorage::UserManager::UserInfo *
0x18002d357  mov     rcx, rax; this
0x18002d35a  call    ??0UserInfo@UserManager@ConnectedStorage@@QEAA@AEBU012@@Z; ConnectedStorage::UserManager::UserInfo::UserInfo(ConnectedStorage::UserManager::UserInfo const &)
0x18002d35f  add     qword ptr [rsi+8], 50h ; 'P'
0x18002d364  jmp     short loc_18002D374
0x18002d366  mov     r8, rbx
0x18002d369  mov     rdx, rax
0x18002d36c  mov     rcx, rsi
0x18002d36f  call    ??$_Emplace_reallocate@AEBUUserInfo@UserManager@ConnectedStorage@@@?$vector@UUserInfo@UserManager@ConnectedStorage@@V?$allocator@UUserInfo@UserManager@ConnectedStorage@@@std@@@std@@AEAAPEAUUserInfo@UserManager@ConnectedStorage@@QEAU234@AEBU234@@Z; std::vector<ConnectedStorage::UserManager::UserInfo>::_Emplace_reallocate<ConnectedStorage::UserManager::UserInfo const &>(ConnectedStorage::UserManager::UserInfo * const,ConnectedStorage::UserManager::UserInfo const &)
0x18002d374  mov     r8, rbx
0x18002d377  lea     rdx, [rsp+110h+var_E0]
0x18002d37c  mov     rcx, r14
0x18002d37f  call    ?erase@?$vector@UUserInfo@UserManager@ConnectedStorage@@V?$allocator@UUserInfo@UserManager@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UUserInfo@UserManager@ConnectedStorage@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UUserInfo@UserManager@ConnectedStorage@@@std@@@std@@@2@@Z; std::vector<ConnectedStorage::UserManager::UserInfo>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ConnectedStorage::UserManager::UserInfo>>>)
0x18002d384  jmp     loc_18002D464
0x18002d389  mov     r8, rsi
0x18002d38c  lea     rdx, [rbp+57h+var_90]
0x18002d390  mov     rcx, rdi
0x18002d393  call    ?GetUserInfo@UserManager@ConnectedStorage@@AEBA?AUUserInfo@12@PEAUIUser@System@Windows@@@Z; ConnectedStorage::UserManager::GetUserInfo(Windows::System::IUser *)
0x18002d398  nop
0x18002d399  lea     rdx, [rbp+57h+var_78]
0x18002d39d  lea     rcx, [rsp+110h+string]; newString
0x18002d3a2  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x18002d3a7  lea     r14, [rdi+0D8h]
0x18002d3ae  mov     rsi, [r14]
0x18002d3b1  mov     rax, [rdi+0E0h]
0x18002d3b8  cmp     rsi, rax
0x18002d3bb  jz      short loc_18002D3CF
0x18002d3bd  mov     rcx, [rbp+57h+var_90]
0x18002d3c1  cmp     [rsi], rcx
0x18002d3c4  jz      short loc_18002D3CF
0x18002d3c6  add     rsi, 50h ; 'P'
0x18002d3ca  cmp     rsi, rax
0x18002d3cd  jnz     short loc_18002D3C1
0x18002d3cf  lea     r15, [rdi+0F0h]
0x18002d3d6  mov     rbx, [r15]
0x18002d3d9  mov     r12, [r15+8]
0x18002d3dd  jmp     short loc_18002D405
0x18002d3df  lea     rdx, [rbx+8]
0x18002d3e3  lea     rcx, [rbp+57h+var_88]
0x18002d3e7  call    ??8SimpleHStringWrapper@ConnectedStorage@@QEBA_NAEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator==(ConnectedStorage::SimpleHStringWrapper const &)
0x18002d3ec  test    al, al
0x18002d3ee  jz      short loc_18002D401
0x18002d3f0  lea     rdx, [rbx+18h]
0x18002d3f4  lea     rcx, [rbp+57h+var_78]
0x18002d3f8  call    ??8SimpleHStringWrapper@ConnectedStorage@@QEBA_NAEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator==(ConnectedStorage::SimpleHStringWrapper const &)
0x18002d3fd  test    al, al
0x18002d3ff  jnz     short loc_18002D40A
0x18002d401  add     rbx, 50h ; 'P'
0x18002d405  cmp     rbx, r12
0x18002d408  jnz     short loc_18002D3DF
0x18002d40a  cmp     rbx, [rdi+0F8h]
0x18002d411  jz      short loc_18002D423
0x18002d413  mov     r8, rbx
0x18002d416  lea     rdx, [rsp+110h+var_E0]
0x18002d41b  mov     rcx, r15
0x18002d41e  call    ?erase@?$vector@UUserInfo@UserManager@ConnectedStorage@@V?$allocator@UUserInfo@UserManager@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UUserInfo@UserManager@ConnectedStorage@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UUserInfo@UserManager@ConnectedStorage@@@std@@@std@@@2@@Z; std::vector<ConnectedStorage::UserManager::UserInfo>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ConnectedStorage::UserManager::UserInfo>>>)
0x18002d423  mov     rax, [rdi+0E0h]
0x18002d42a  cmp     rsi, rax
0x18002d42d  jnz     short loc_18002D458
0x18002d42f  cmp     rax, [r14+10h]
0x18002d433  jz      short loc_18002D448
0x18002d435  lea     rdx, [rbp+57h+var_90]
0x18002d439  mov     rcx, rax
0x18002d43c  call    ??0UserInfo@UserManager@ConnectedStorage@@QEAA@$$QEAU012@@Z; ConnectedStorage::UserManager::UserInfo::UserInfo(ConnectedStorage::UserManager::UserInfo &&)
0x18002d441  add     qword ptr [r14+8], 50h ; 'P'
0x18002d446  jmp     short loc_18002D458
0x18002d448  lea     r8, [rbp+57h+var_90]
0x18002d44c  mov     rdx, rax
0x18002d44f  mov     rcx, r14
0x18002d452  call    ??$_Emplace_reallocate@UUserInfo@UserManager@ConnectedStorage@@@?$vector@UUserInfo@UserManager@ConnectedStorage@@V?$allocator@UUserInfo@UserManager@ConnectedStorage@@@std@@@std@@AEAAPEAUUserInfo@UserManager@ConnectedStorage@@QEAU234@$$QEAU234@@Z; std::vector<ConnectedStorage::UserManager::UserInfo>::_Emplace_reallocate<ConnectedStorage::UserManager::UserInfo>(ConnectedStorage::UserManager::UserInfo * const,ConnectedStorage::UserManager::UserInfo &&)
0x18002d457  nop
0x18002d458  lea     rcx, [rbp+57h+var_90]; this
0x18002d45c  call    ??1UserInfo@UserManager@ConnectedStorage@@QEAA@XZ; ConnectedStorage::UserManager::UserInfo::~UserInfo(void)
0x18002d461  xor     r15d, r15d
0x18002d464  cmp     [rdi+50h], r15
0x18002d468  jz      loc_18002D522
0x18002d46e  lea     rdx, [rbp+57h+var_B0]
0x18002d472  mov     rcx, rdi
0x18002d475  call    ?weak_from_this@UserManager@ConnectedStorage@@AEBA?AV?$weak_ptr@$$CBVUserManager@ConnectedStorage@@@std@@XZ; ConnectedStorage::UserManager::weak_from_this(void)
0x18002d47a  nop
0x18002d47b  lea     rdx, [rbp+57h+var_B0]
0x18002d47f  lea     rcx, [rsp+110h+var_D8]
0x18002d484  call    ??$?0VContext@ConnectedStorage@@$0A@@?$weak_ptr@VContext@ConnectedStorage@@@std@@QEAA@AEBV?$shared_ptr@VContext@ConnectedStorage@@@1@@Z; std::weak_ptr<ConnectedStorage::Context>::weak_ptr<ConnectedStorage::Context>(std::shared_ptr<ConnectedStorage::Context> const &)
0x18002d489  nop
0x18002d48a  mov     [rbp+57h+var_C8], r13d
0x18002d48e  lea     rdx, [rsp+110h+var_F0]; struct ConnectedStorage::SimpleHStringWrapper *
0x18002d493  lea     rcx, [rbp+57h+newString]; newString
0x18002d497  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x18002d49c  nop
0x18002d49d  lea     rdx, [rsp+110h+string]; struct ConnectedStorage::SimpleHStringWrapper *
0x18002d4a2  lea     rcx, [rbp+57h+var_B8]; newString
0x18002d4a6  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x18002d4ab  nop
0x18002d4ac  lea     rax, off_180090008
0x18002d4b3  mov     [rbp+57h+var_90], rax
0x18002d4b7  mov     rax, qword ptr [rsp+110h+var_D8]
0x18002d4bc  mov     qword ptr [rbp+57h+var_88], rax
0x18002d4c0  mov     rax, qword ptr [rbp+57h+var_D8+8]
0x18002d4c4  mov     qword ptr [rbp+57h+var_88+8], rax
0x18002d4c8  xorps   xmm0, xmm0
0x18002d4cb  movdqu  [rsp+110h+var_D8], xmm0
0x18002d4d1  mov     eax, [rbp+57h+var_C8]
0x18002d4d4  mov     [rbp+57h+var_78], eax
0x18002d4d7  mov     rax, [rbp+57h+newString]
0x18002d4db  mov     [rbp+57h+var_70], rax
0x18002d4df  mov     [rbp+57h+newString], r15
0x18002d4e3  mov     rax, [rbp+57h+var_B8]
0x18002d4e7  mov     [rbp+57h+var_68], rax
0x18002d4eb  mov     [rbp+57h+var_B8], r15
0x18002d4ef  lea     rax, [rbp+57h+var_90]
0x18002d4f3  mov     [rbp+57h+var_58], rax
0x18002d4f7  lea     rdx, [rbp+57h+var_90]
0x18002d4fb  lea     rcx, [rdi+150h]; this
0x18002d502  call    ?Enqueue@ExecuteQueue@ConnectedStorage@@QEAAXV?$function@$$A6AXXZ@std@@@Z; ConnectedStorage::ExecuteQueue::Enqueue(std::function<void (void)>)
0x18002d507  nop
0x18002d508  lea     rcx, [rsp+110h+var_D8]
0x18002d50d  call    _lambda_b932c5694bc3fc5d357785cd48396a70_____lambda_b932c5694bc3fc5d357785cd48396a70_
0x18002d512  nop
0x18002d513  mov     rcx, [rbp+57h+var_A8]; this
0x18002d517  test    rcx, rcx
0x18002d51a  jz      short loc_18002D522
0x18002d51c  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18002d521  nop
0x18002d522  mov     rcx, [rsp+110h+string]; string
0x18002d527  call    cs:__imp_WindowsDeleteString
0x18002d52d  mov     [rsp+110h+string], r15
0x18002d532  mov     rcx, [rsp+110h+var_F0]; string
0x18002d537  call    cs:__imp_WindowsDeleteString
0x18002d53d  mov     [rsp+110h+var_F0], r15
0x18002d542  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x18002d546  call    cs:__imp_LeaveCriticalSection
0x18002d54c  mov     rcx, [rbp+57h+var_40]
0x18002d550  xor     rcx, rsp; StackCookie
0x18002d553  call    __security_check_cookie
0x18002d558  mov     rbx, [rsp+110h+arg_8]
0x18002d560  add     rsp, 0E0h
0x18002d567  pop     r15
0x18002d569  pop     r14
0x18002d56b  pop     r13
0x18002d56d  pop     r12
0x18002d56f  pop     rdi
0x18002d570  pop     rsi
0x18002d571  pop     rbp
0x18002d572  retn
0x18002d573  lea     rdx, aUserGetNonroam; "user->get_NonRoamableId(nonRoamableId.G"...
0x18002d57a  mov     ecx, eax; this
0x18002d57c  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
```
