# sih::network::BulkCheckDNSresiliencyAndUpdateSettings(void)

- ea: `0x1400198ac`
- end: `0x140019b18`
- name: `?BulkCheckDNSresiliencyAndUpdateSettings@network@sih@@YAJXZ`
- size: `620`
- prototype: `__int64 __fastcall(sih::network *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140019e4c`

## callees

- `0x1400071c0`
- `0x1400073f0`
- `0x1400101e8`
- `0x1400154b4`
- `0x14001952c`
- `0x140019780`
- `0x1400198ac`
- `0x14001a36c`
- `0x14001bbec`
- `0x14003854c`
- `0x140045dc0`
- `0x140045de4`
- `0x1400460bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400199c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019ad3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400199c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019ad3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019988`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019ae3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019988`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019ae3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1400199b0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1400199b0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140019ac9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140019ac9`

## string_xrefs

- `0x1400199cd`: `Trying to impersonate`
- `0x140019aad`: `sih::network::BulkCheckDNSresiliencyAndUpdateSettings`
- `0x14001992f`: `SkipImpersonation`

## pseudocode

```c
__int64 __fastcall sih::network::BulkCheckDNSresiliencyAndUpdateSettings(sih::network *this)
{
  int MostPreferredLoggedOnSessionId; // esi
  bool v2; // r12
  wchar_t *v3; // rdi
  char DNSConfigTestBoolValue; // bl
  void *const *v5; // rdx
  unsigned int v6; // ecx
  BOOL v7; // eax
  __int64 HostnameList; // r14
  wchar_t *v9; // r15
  wchar_t *v10; // rbx
  wchar_t *v11; // rax
  wchar_t *i; // rbx
  __int64 v14; // [rsp+20h] [rbp-60h]
  unsigned int v15; // [rsp+30h] [rbp-50h] BYREF
  __int128 v16; // [rsp+38h] [rbp-48h] BYREF
  bool v17; // [rsp+48h] [rbp-38h]
  int v18; // [rsp+4Ch] [rbp-34h]
  _OWORD v19[2]; // [rsp+50h] [rbp-30h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-10h]

  MostPreferredLoggedOnSessionId = 0;
  v15 = -1;
  hObject = 0;
  v2 = 0;
  v17 = 0;
  v18 = -2147023728;
  v16 = 0u;
  v3 = (wchar_t *)operator new(0x30u);
  *(_QWORD *)v3 = v3;
  *((_QWORD *)v3 + 1) = v3;
  *(_QWORD *)&v16 = v3;
  memset(v19, 0, sizeof(v19));
  std::wstring::_Construct<1,wchar_t const *>(v19, L"SkipImpersonation", 0x11u);
  DNSConfigTestBoolValue = sih::network::RegQueryDNSConfigTestBoolValue(v19);
  std::wstring::~wstring(v19);
  if ( !DNSConfigTestBoolValue )
  {
    MostPreferredLoggedOnSessionId = GetMostPreferredLoggedOnSessionId(v6, v5, &v15);
    if ( MostPreferredLoggedOnSessionId < 0 )
    {
LABEL_19:
      LODWORD(v14) = MostPreferredLoggedOnSessionId;
      WUTrace("sih::network::BulkCheckDNSresiliencyAndUpdateSettings", 133, 0x400000, 3, v14, &OutputString);
      goto LABEL_20;
    }
    if ( v15 == -1 )
    {
      MostPreferredLoggedOnSessionId = -2147467259;
      goto LABEL_19;
    }
    if ( hObject )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    MostPreferredLoggedOnSessionId = GetUserTokenFromSessionId((WUSystemInterfaceHelper *)v15);
    if ( MostPreferredLoggedOnSessionId < 0 )
      goto LABEL_19;
    v7 = ImpersonateLoggedOnUser(hObject);
    v2 = v7;
    v17 = v7;
    if ( !v7 )
    {
      GetLastError();
      MostPreferredLoggedOnSessionId = -2147023728;
      LODWORD(v14) = -2147023728;
      WUTrace(0, 0, 0x400000, 4, v14, L"Trying to impersonate");
      goto LABEL_19;
    }
  }
  HostnameList = sih::network::GetHostnameList(v19);
  if ( &v16 != (__int128 *)HostnameList )
  {
    **((_QWORD **)v3 + 1) = 0;
    v9 = *(wchar_t **)v3;
    if ( *(_QWORD *)v3 )
    {
      do
      {
        v10 = *(wchar_t **)v9;
        std::wstring::~wstring((_QWORD *)v9 + 2);
        operator delete(v9, (const struct std::nothrow_t *)0x30);
        v9 = v10;
      }
      while ( v10 );
    }
    v11 = v3;
    *(_QWORD *)v3 = v3;
    *((_QWORD *)v3 + 1) = v3;
    v3 = *(wchar_t **)HostnameList;
    *(_QWORD *)&v16 = *(_QWORD *)HostnameList;
    *(_QWORD *)HostnameList = v11;
    *((_QWORD *)&v16 + 1) = *(_QWORD *)(HostnameList + 8);
    *(_QWORD *)(HostnameList + 8) = 0;
  }
  std::list<std::wstring>::~list<std::wstring>(v19);
  for ( i = *(wchar_t **)v3; i != v3; i = *(wchar_t **)i )
  {
    MostPreferredLoggedOnSessionId = sih::network::CheckDNSresiliencyAndUpdateSettings(i + 8);
    if ( MostPreferredLoggedOnSessionId < 0 )
      goto LABEL_19;
  }
LABEL_20:
  std::list<std::wstring>::~list<std::wstring>(&v16);
  if ( v2 && !RevertToSelf() )
    GetLastError();
  if ( hObject )
    CloseHandle(hObject);
  return (unsigned int)MostPreferredLoggedOnSessionId;
}

```

## disassembly

```asm
0x1400198ac  mov     rax, rsp
0x1400198af  mov     [rax+8], rbx
0x1400198b3  mov     [rax+10h], rsi
0x1400198b7  mov     [rax+18h], rdi
0x1400198bb  mov     [rax+20h], r12
0x1400198bf  push    rbp
0x1400198c0  push    r14
0x1400198c2  push    r15
0x1400198c4  mov     rbp, rsp
0x1400198c7  sub     rsp, 80h
0x1400198ce  mov     rax, cs:__security_cookie
0x1400198d5  xor     rax, rsp
0x1400198d8  mov     [rbp+var_8], rax
0x1400198dc  xor     esi, esi
0x1400198de  or      r15d, 0FFFFFFFFh
0x1400198e2  mov     [rbp+var_50], r15d
0x1400198e6  mov     [rbp+hObject], rsi
0x1400198ea  xor     r12b, r12b
0x1400198ed  mov     [rbp+var_38], r12b
0x1400198f1  mov     r14d, 80070490h
0x1400198f7  mov     [rbp+var_34], r14d
0x1400198fb  xorps   xmm0, xmm0
0x1400198fe  movups  [rbp+var_48], xmm0
0x140019902  mov     qword ptr [rbp+var_48+8], rsi
0x140019906  lea     ecx, [rsi+30h]; Size
0x140019909  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001990e  mov     rdi, rax
0x140019911  mov     [rax], rax
0x140019914  mov     [rax+8], rax
0x140019918  mov     qword ptr [rbp+var_48], rax
0x14001991c  xorps   xmm0, xmm0
0x14001991f  movups  [rbp+var_30], xmm0
0x140019923  xorps   xmm1, xmm1
0x140019926  movdqu  [rbp+var_20], xmm1
0x14001992b  lea     r8d, [rsi+11h]
0x14001992f  lea     rdx, aSkipimpersonat; "SkipImpersonation"
0x140019936  lea     rcx, [rbp+var_30]
0x14001993a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001993f  nop
0x140019940  lea     rcx, [rbp+var_30]
0x140019944  call    ?RegQueryDNSConfigTestBoolValue@network@sih@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; sih::network::RegQueryDNSConfigTestBoolValue(std::wstring const &)
0x140019949  mov     bl, al
0x14001994b  lea     rcx, [rbp+var_30]; void *
0x14001994f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140019954  test    bl, bl
0x140019956  jnz     loc_1400199F6
0x14001995c  lea     r8, [rbp+var_50]; unsigned int *
0x140019960  call    ?GetMostPreferredLoggedOnSessionId@@YAJKPEBQEAXPEAK@Z; GetMostPreferredLoggedOnSessionId(ulong,void * const *,ulong *)
0x140019965  mov     esi, eax
0x140019967  test    eax, eax
0x140019969  js      loc_140019A8C
0x14001996f  cmp     [rbp+var_50], r15d
0x140019973  jnz     short loc_14001997F
0x140019975  mov     esi, 80004005h
0x14001997a  jmp     loc_140019A8C
0x14001997f  mov     rcx, [rbp+hObject]; hObject
0x140019983  test    rcx, rcx
0x140019986  jz      short loc_140019996
0x140019988  call    cs:__imp_CloseHandle
0x14001998e  mov     [rbp+hObject], 0
0x140019996  lea     r8, [rbp+hObject]
0x14001999a  mov     ecx, [rbp+var_50]
0x14001999d  call    GetUserTokenFromSessionId
0x1400199a2  mov     esi, eax
0x1400199a4  test    eax, eax
0x1400199a6  js      loc_140019A8C
0x1400199ac  mov     rcx, [rbp+hObject]; hToken
0x1400199b0  call    cs:__imp_ImpersonateLoggedOnUser
0x1400199b6  test    eax, eax
0x1400199b8  setnz   r12b
0x1400199bc  mov     [rbp+var_38], r12b
0x1400199c0  test    eax, eax
0x1400199c2  jnz     short loc_1400199F6
0x1400199c4  call    cs:__imp_GetLastError
0x1400199ca  mov     esi, r14d
0x1400199cd  lea     rax, aTryingToImpers; "Trying to impersonate"
0x1400199d4  mov     [rsp+80h+var_58], rax
0x1400199d9  mov     dword ptr [rsp+80h+var_60], r14d
0x1400199de  xor     edx, edx
0x1400199e0  xor     ecx, ecx
0x1400199e2  lea     r9d, [rdx+4]
0x1400199e6  mov     r8d, 400000h
0x1400199ec  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400199f1  jmp     loc_140019A8C
0x1400199f6  lea     rcx, [rbp+var_30]
0x1400199fa  call    ?GetHostnameList@network@sih@@YA?AV?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@XZ; sih::network::GetHostnameList(void)
0x1400199ff  mov     r14, rax
0x140019a02  lea     rax, [rbp+var_48]
0x140019a06  cmp     rax, r14
0x140019a09  jz      short loc_140019A63
0x140019a0b  mov     rcx, [rdi+8]
0x140019a0f  mov     qword ptr [rcx], 0
0x140019a16  mov     r15, [rdi]
0x140019a19  test    r15, r15
0x140019a1c  jz      short loc_140019A3F
0x140019a1e  mov     rbx, [r15]
0x140019a21  lea     rcx, [r15+10h]; void *
0x140019a25  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140019a2a  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x140019a2f  mov     rcx, r15; void *
0x140019a32  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140019a37  mov     r15, rbx
0x140019a3a  test    rbx, rbx
0x140019a3d  jnz     short loc_140019A1E
0x140019a3f  mov     rax, rdi
0x140019a42  mov     [rdi], rdi
0x140019a45  mov     [rdi+8], rdi
0x140019a49  mov     rdi, [r14]
0x140019a4c  mov     qword ptr [rbp+var_48], rdi
0x140019a50  mov     [r14], rax
0x140019a53  mov     rax, [r14+8]
0x140019a57  mov     qword ptr [rbp+var_48+8], rax
0x140019a5b  mov     qword ptr [r14+8], 0
0x140019a63  lea     rcx, [rbp+var_30]
0x140019a67  call    ??1?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::~list<std::wstring>(void)
0x140019a6c  mov     rbx, [rdi]
0x140019a6f  jmp     short loc_140019A83
0x140019a71  lea     rcx, [rbx+10h]; S1
0x140019a75  call    ?CheckDNSresiliencyAndUpdateSettings@network@sih@@YAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; sih::network::CheckDNSresiliencyAndUpdateSettings(std::wstring const &)
0x140019a7a  mov     esi, eax
0x140019a7c  test    eax, eax
0x140019a7e  js      short loc_140019A8C
0x140019a80  mov     rbx, [rbx]
0x140019a83  cmp     rbx, rdi
0x140019a86  jnz     short loc_140019A71
0x140019a88  test    esi, esi
0x140019a8a  jns     short loc_140019ABA
0x140019a8c  lea     rax, OutputString
0x140019a93  mov     [rsp+80h+var_58], rax
0x140019a98  mov     dword ptr [rsp+80h+var_60], esi
0x140019a9c  mov     edx, 85h
0x140019aa1  mov     r9d, 3
0x140019aa7  mov     r8d, 400000h
0x140019aad  lea     rcx, aSihNetworkBulk; "sih::network::BulkCheckDNSresiliencyAnd"...
0x140019ab4  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140019ab9  nop
0x140019aba  lea     rcx, [rbp+var_48]
0x140019abe  call    ??1?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::~list<std::wstring>(void)
0x140019ac3  nop
0x140019ac4  test    r12b, r12b
0x140019ac7  jz      short loc_140019ADA
0x140019ac9  call    cs:__imp_RevertToSelf
0x140019acf  test    eax, eax
0x140019ad1  jnz     short loc_140019ADA
0x140019ad3  call    cs:__imp_GetLastError
0x140019ad9  nop
0x140019ada  mov     rcx, [rbp+hObject]; hObject
0x140019ade  test    rcx, rcx
0x140019ae1  jz      short loc_140019AE9
0x140019ae3  call    cs:__imp_CloseHandle
0x140019ae9  mov     eax, esi
0x140019aeb  mov     rcx, [rbp+var_8]
0x140019aef  xor     rcx, rsp; StackCookie
0x140019af2  call    __security_check_cookie
0x140019af7  lea     r11, [rsp+80h+var_s0]
0x140019aff  mov     rbx, [r11+20h]
0x140019b03  mov     rsi, [r11+28h]
0x140019b07  mov     rdi, [r11+30h]
0x140019b0b  mov     r12, [r11+38h]
0x140019b0f  mov     rsp, r11
0x140019b12  pop     r15
0x140019b14  pop     r14
0x140019b16  pop     rbp
0x140019b17  retn
```
