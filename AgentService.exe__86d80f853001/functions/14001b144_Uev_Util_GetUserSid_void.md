# Uev::Util::GetUserSid(void *)

- ea: `0x14001b144`
- end: `0x14001b485`
- name: `?GetUserSid@Util@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@Z`
- size: `833`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, service_task`

## callers

- `0x14001b6a8`

## callees

- `0x140003e50`
- `0x140003f88`
- `0x140003fcc`
- `0x140004ab4`
- `0x14000ac88`
- `0x14000acb8`
- `0x14000ad1c`
- `0x14000afc0`
- `0x14000ba60`
- `0x14000bae4`
- `0x14000c2b8`
- `0x14000d1d8`
- `0x14000e924`
- `0x14000f01c`
- `0x140011ab4`
- `0x140018c88`
- `0x14001a090`
- `0x14001a5e4`
- `0x14001b144`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x14001b1e2`
- `ADVAPI32!GetTokenInformation` at `0x14001b22c`
- `ADVAPI32!GetTokenInformation` at `0x14001b1e2`
- `ADVAPI32!GetTokenInformation` at `0x14001b22c`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14001b25a`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14001b25a`
- `KERNEL32!GetLastError` at `0x14001b1ec`
- `KERNEL32!GetLastError` at `0x14001b338`
- `KERNEL32!GetLastError` at `0x14001b3fd`
- `KERNEL32!GetLastError` at `0x14001b1ec`
- `KERNEL32!GetLastError` at `0x14001b338`
- `KERNEL32!GetLastError` at `0x14001b3fd`
- `KERNEL32!LocalFree` at `0x14001b2db`
- `KERNEL32!LocalFree` at `0x14001b2db`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x14001b35f`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x14001b424`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x14001b35f`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x14001b424`

## string_xrefs

- `0x14001b188`: `AgentService.Util::GetUserSid: Entry`
- `0x14001b40f`: `::GetTokenInformation failed: System error code `
- `0x14001b37e`: `AgentService.Util::GetUserSid: %s`
- `0x14001b443`: `AgentService.Util::GetUserSid: %s`
- `0x14001b3c0`: `AgentService.Util::GetUserSid: Invalid (null) pointer`
- `0x14001b34a`: `::ConvertSidToStringSidW failed: System error code`
- `0x14001b2f0`: `AgentService.Util::GetUserSid: Exit ['%s']`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Uev::Util::GetUserSid(__int64 a1, void *a2)
{
  PSID *v4; // r14
  PSID *v5; // rbx
  DWORD v6; // edi
  unsigned __int64 v7; // r8
  DWORD v9; // ebx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rax
  DWORD LastError; // ebx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rax
  __int128 v23; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v24; // [rsp+48h] [rbp-B8h]
  PSID *v25; // [rsp+58h] [rbp-A8h]
  _QWORD v26[6]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD pExceptionObject[8]; // [rsp+90h] [rbp-70h] BYREF
  LPWSTR StringSid; // [rsp+D0h] [rbp-30h] BYREF
  DWORD TokenInformationLength; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v30[240]; // [rsp+E0h] [rbp-20h] BYREF

  v26[4] = a1;
  DbgTrace<5>(L"AgentService.Util::GetUserSid: Entry");
  TokenInformationLength = 0;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_WORD *)a1 = 0;
  v4 = (PSID *)operator new[](0x40u);
  v5 = v4;
  v25 = v4;
  if ( !GetTokenInformation(a2, TokenUser, v4, 0x40u, &TokenInformationLength) )
  {
    if ( GetLastError() != 122
      || (v6 = TokenInformationLength,
          v5 = (PSID *)operator new[](TokenInformationLength),
          v25 = v5,
          operator delete(v4),
          !GetTokenInformation(a2, TokenUser, v5, v6, &TokenInformationLength)) )
    {
      LastError = GetLastError();
      std::wostringstream::wostringstream(v30);
      v17 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v30, L"::GetTokenInformation failed: System error code ");
      std::wostream::operator<<(v17, LastError);
      v18 = std::wostringstream::str(v30, v26);
      std::wstring::c_str(v18, v19, v20, v21);
      DbgTraceFrmtErr<wchar_t const *>((wchar_t *)L"AgentService.Util::GetUserSid: %s");
      boost::filesystem::path::~path((boost::filesystem::path *)v26);
      v22 = std::wostringstream::str(v30, v26);
      Uev::GetUserSidException::GetUserSidException(pExceptionObject, v22);
      throw (Uev::GetUserSidException *)pExceptionObject;
    }
    v4 = v5;
  }
  StringSid = 0;
  if ( !v4 || !*v4 )
  {
    DbgTraceErr<wchar_t const *>(L"AgentService.Util::GetUserSid: Invalid (null) pointer");
    std::wstring::wstring(v26, L"Invalid (null) pointer");
    Uev::GetUserSidException::GetUserSidException(pExceptionObject, (__int64)v26);
    throw (Uev::GetUserSidException *)pExceptionObject;
  }
  if ( !ConvertSidToStringSidW(*v4, &StringSid) )
  {
    v9 = GetLastError();
    std::wostringstream::wostringstream(v30);
    v10 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v30, "::ConvertSidToStringSidW failed: System error code");
    std::wostream::operator<<(v10, v9);
    v11 = std::wostringstream::str(v30, v26);
    std::wstring::c_str(v11, v12, v13, v14);
    DbgTraceFrmtErr<wchar_t const *>((wchar_t *)L"AgentService.Util::GetUserSid: %s");
    boost::filesystem::path::~path((boost::filesystem::path *)v26);
    v15 = std::wostringstream::str(v30, v26);
    Uev::GetUserSidException::GetUserSidException(pExceptionObject, v15);
    throw (Uev::GetUserSidException *)pExceptionObject;
  }
  v23 = 0;
  v24 = 0u;
  v7 = -1;
  do
    ++v7;
  while ( StringSid[v7] );
  std::wstring::_Construct<1,wchar_t *>(&v23, StringSid, v7);
  if ( (__int128 *)a1 != &v23 )
  {
    std::wstring::_Tidy_deallocate(a1);
    *(_OWORD *)a1 = v23;
    *(_OWORD *)(a1 + 16) = v24;
    *(_QWORD *)&v24 = 0;
    *((_QWORD *)&v24 + 1) = 7;
    LOWORD(v23) = 0;
  }
  std::wstring::_Tidy_deallocate(&v23);
  LocalFree(StringSid);
  DbgTraceFrmt<5,wchar_t const *>((wchar_t *)L"AgentService.Util::GetUserSid: Exit ['%s']");
  if ( v5 )
    operator delete(v5);
  return a1;
}

```

## disassembly

```asm
0x14001b144  mov     [rsp-8+arg_10], rbx
0x14001b149  mov     [rsp-8+arg_18], rsi
0x14001b14e  push    rbp
0x14001b14f  push    rdi
0x14001b150  push    r12
0x14001b152  push    r14
0x14001b154  push    r15
0x14001b156  lea     rbp, [rsp-0E0h]
0x14001b15e  sub     rsp, 1E0h
0x14001b165  mov     rax, cs:__security_cookie
0x14001b16c  xor     rax, rsp
0x14001b16f  mov     [rbp+100h+var_30], rax
0x14001b176  mov     r15, rdx
0x14001b179  mov     rsi, rcx
0x14001b17c  mov     [rbp+100h+var_180], rcx
0x14001b180  xor     r12d, r12d
0x14001b183  mov     [rsp+200h+var_1D0], r12d
0x14001b188  lea     rcx, aAgentserviceUt_22; "AgentService.Util::GetUserSid: Entry"
0x14001b18f  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x14001b194  mov     [rbp+100h+TokenInformationLength], r12d
0x14001b198  xorps   xmm0, xmm0
0x14001b19b  movups  xmmword ptr [rsi], xmm0
0x14001b19e  mov     [rsi+10h], r12
0x14001b1a2  mov     qword ptr [rsi+18h], 7
0x14001b1aa  mov     [rsi], r12w
0x14001b1ae  mov     [rsp+200h+var_1D0], 1
0x14001b1b6  lea     edi, [r12+40h]
0x14001b1bb  mov     ecx, edi; unsigned __int64
0x14001b1bd  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14001b1c2  mov     r14, rax
0x14001b1c5  mov     rbx, rax
0x14001b1c8  mov     [rsp+200h+var_1A8], rax
0x14001b1cd  lea     rax, [rbp+100h+TokenInformationLength]
0x14001b1d1  mov     [rsp+200h+ReturnLength], rax; ReturnLength
0x14001b1d6  mov     r9d, edi; TokenInformationLength
0x14001b1d9  mov     r8, rbx; TokenInformation
0x14001b1dc  lea     edx, [rdi-3Fh]; TokenInformationClass
0x14001b1df  mov     rcx, r15; TokenHandle
0x14001b1e2  call    cs:__imp_GetTokenInformation
0x14001b1e8  test    eax, eax
0x14001b1ea  jnz     short loc_14001B23D
0x14001b1ec  call    cs:__imp_GetLastError
0x14001b1f2  cmp     eax, 7Ah ; 'z'
0x14001b1f5  jnz     loc_14001B3FD
0x14001b1fb  mov     edi, [rbp+100h+TokenInformationLength]
0x14001b1fe  mov     ecx, edi; unsigned __int64
0x14001b200  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14001b205  mov     rbx, rax
0x14001b208  mov     [rsp+200h+var_1A8], rax
0x14001b20d  mov     rcx, r14; Block
0x14001b210  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001b215  lea     rax, [rbp+100h+TokenInformationLength]
0x14001b219  mov     [rsp+200h+ReturnLength], rax; ReturnLength
0x14001b21e  mov     r9d, edi; TokenInformationLength
0x14001b221  mov     r8, rbx; TokenInformation
0x14001b224  lea     edx, [r12+1]; TokenInformationClass
0x14001b229  mov     rcx, r15; TokenHandle
0x14001b22c  call    cs:__imp_GetTokenInformation
0x14001b232  test    eax, eax
0x14001b234  jz      loc_14001B3FD
0x14001b23a  mov     r14, rbx
0x14001b23d  mov     [rbp+100h+StringSid], r12
0x14001b241  test    r14, r14
0x14001b244  jz      loc_14001B3C0
0x14001b24a  mov     rcx, [r14]; Sid
0x14001b24d  test    rcx, rcx
0x14001b250  jz      loc_14001B3C0
0x14001b256  lea     rdx, [rbp+100h+StringSid]; StringSid
0x14001b25a  call    cs:__imp_ConvertSidToStringSidW
0x14001b260  test    eax, eax
0x14001b262  jz      loc_14001B338
0x14001b268  mov     rdx, [rbp+100h+StringSid]
0x14001b26c  xorps   xmm0, xmm0
0x14001b26f  movups  [rsp+200h+var_1C8], xmm0
0x14001b274  mov     qword ptr [rsp+200h+var_1B8], r12
0x14001b279  mov     qword ptr [rsp+200h+var_1B8+8], r12
0x14001b27e  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001b282  inc     r8
0x14001b285  cmp     [rdx+r8*2], r12w
0x14001b28a  jnz     short loc_14001B282
0x14001b28c  lea     rcx, [rsp+200h+var_1C8]
0x14001b291  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14001b296  lea     rax, [rsp+200h+var_1C8]
0x14001b29b  cmp     rsi, rax
0x14001b29e  jz      short loc_14001B2CD
0x14001b2a0  mov     rcx, rsi
0x14001b2a3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001b2a8  movups  xmm0, [rsp+200h+var_1C8]
0x14001b2ad  movups  xmmword ptr [rsi], xmm0
0x14001b2b0  movups  xmm1, [rsp+200h+var_1B8]
0x14001b2b5  movups  xmmword ptr [rsi+10h], xmm1
0x14001b2b9  mov     qword ptr [rsp+200h+var_1B8], r12
0x14001b2be  mov     qword ptr [rsp+200h+var_1B8+8], 7
0x14001b2c7  mov     word ptr [rsp+200h+var_1C8], r12w
0x14001b2cd  lea     rcx, [rsp+200h+var_1C8]
0x14001b2d2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001b2d7  mov     rcx, [rbp+100h+StringSid]; hMem
0x14001b2db  call    cs:__imp_LocalFree
0x14001b2e1  cmp     qword ptr [rsi+18h], 7
0x14001b2e6  jbe     short loc_14001B2ED
0x14001b2e8  mov     rdx, [rsi]
0x14001b2eb  jmp     short loc_14001B2F0
0x14001b2ed  mov     rdx, rsi
0x14001b2f0  lea     rcx, aAgentserviceUt_9; "AgentService.Util::GetUserSid: Exit ['%"...
0x14001b2f7  call    ??$DbgTraceFrmt@$04PEB_W@@YAXPEB_W0@Z; DbgTraceFrmt<5,wchar_t const *>(wchar_t const *,wchar_t const *)
0x14001b2fc  nop
0x14001b2fd  test    rbx, rbx
0x14001b300  jz      short loc_14001B30A
0x14001b302  mov     rcx, rbx; Block
0x14001b305  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001b30a  mov     rax, rsi
0x14001b30d  mov     rcx, [rbp+100h+var_30]
0x14001b314  xor     rcx, rsp; StackCookie
0x14001b317  call    __security_check_cookie
0x14001b31c  lea     r11, [rsp+200h+var_20]
0x14001b324  mov     rbx, [r11+40h]
0x14001b328  mov     rsi, [r11+48h]
0x14001b32c  mov     rsp, r11
0x14001b32f  pop     r15
0x14001b331  pop     r14
0x14001b333  pop     r12
0x14001b335  pop     rdi
0x14001b336  pop     rbp
0x14001b337  retn
0x14001b338  call    cs:__imp_GetLastError
0x14001b33e  mov     ebx, eax
0x14001b340  lea     rcx, [rbp+100h+var_120]
0x14001b344  call    ??0?$basic_ostringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wostringstream::wostringstream(void)
0x14001b349  nop
0x14001b34a  lea     rdx, aConvertsidtost; "::ConvertSidToStringSidW failed: System"...
0x14001b351  lea     rcx, [rbp+100h+var_120]
0x14001b355  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEBD@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,char const *)
0x14001b35a  mov     edx, ebx
0x14001b35c  mov     rcx, rax
0x14001b35f  call    cs:__imp_??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z; std::wostream::operator<<(ulong)
0x14001b365  lea     rdx, [rsp+200h+var_1A0]
0x14001b36a  lea     rcx, [rbp+100h+var_120]
0x14001b36e  call    ?str@?$basic_ostringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::wostringstream::str(void)
0x14001b373  mov     rcx, rax
0x14001b376  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x14001b37b  mov     rdx, rax
0x14001b37e  lea     rcx, aAgentserviceUt_14; "AgentService.Util::GetUserSid: %s"
0x14001b385  call    ??$DbgTraceFrmtErr@PEB_W@@YAXPEB_W0@Z; DbgTraceFrmtErr<wchar_t const *>(wchar_t const *,wchar_t const *)
0x14001b38a  lea     rcx, [rsp+200h+var_1A0]; this
0x14001b38f  call    ??1path@filesystem@boost@@QEAA@XZ; boost::filesystem::path::~path(void)
0x14001b394  lea     rdx, [rsp+200h+var_1A0]
0x14001b399  lea     rcx, [rbp+100h+var_120]
0x14001b39d  call    ?str@?$basic_ostringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::wostringstream::str(void)
0x14001b3a2  nop
0x14001b3a3  mov     rdx, rax
0x14001b3a6  lea     rcx, [rbp+100h+pExceptionObject]
0x14001b3aa  call    ??0GetUserSidException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::GetUserSidException::GetUserSidException(std::wstring const &)
0x14001b3af  lea     rdx, _TI3?AVGetUserSidException@Uev@@; pThrowInfo
0x14001b3b6  lea     rcx, [rbp+100h+pExceptionObject]; pExceptionObject
0x14001b3ba  call    _CxxThrowException_0
0x14001b3c0  lea     rcx, aAgentserviceUt_37; "AgentService.Util::GetUserSid: Invalid "...
0x14001b3c7  call    ??$DbgTraceErr@PEB_W@@YAXPEB_W@Z; DbgTraceErr<wchar_t const *>(wchar_t const *)
0x14001b3cc  lea     rdx, aInvalidNullPoi; "Invalid (null) pointer"
0x14001b3d3  lea     rcx, [rsp+200h+var_1A0]
0x14001b3d8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14001b3dd  nop
0x14001b3de  lea     rdx, [rsp+200h+var_1A0]
0x14001b3e3  lea     rcx, [rbp+100h+pExceptionObject]
0x14001b3e7  call    ??0GetUserSidException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::GetUserSidException::GetUserSidException(std::wstring const &)
0x14001b3ec  lea     rdx, _TI3?AVGetUserSidException@Uev@@; pThrowInfo
0x14001b3f3  lea     rcx, [rbp+100h+pExceptionObject]; pExceptionObject
0x14001b3f7  call    _CxxThrowException_0
0x14001b3fd  call    cs:__imp_GetLastError
0x14001b403  mov     ebx, eax
0x14001b405  lea     rcx, [rbp+100h+var_120]
0x14001b409  call    ??0?$basic_ostringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wostringstream::wostringstream(void)
0x14001b40e  nop
0x14001b40f  lea     rdx, aGettokeninform_0; "::GetTokenInformation failed: System er"...
0x14001b416  lea     rcx, [rbp+100h+var_120]
0x14001b41a  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x14001b41f  mov     edx, ebx
0x14001b421  mov     rcx, rax
0x14001b424  call    cs:__imp_??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z; std::wostream::operator<<(ulong)
0x14001b42a  lea     rdx, [rsp+200h+var_1A0]
0x14001b42f  lea     rcx, [rbp+100h+var_120]
0x14001b433  call    ?str@?$basic_ostringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::wostringstream::str(void)
0x14001b438  mov     rcx, rax
0x14001b43b  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x14001b440  mov     rdx, rax
0x14001b443  lea     rcx, aAgentserviceUt_14; "AgentService.Util::GetUserSid: %s"
0x14001b44a  call    ??$DbgTraceFrmtErr@PEB_W@@YAXPEB_W0@Z; DbgTraceFrmtErr<wchar_t const *>(wchar_t const *,wchar_t const *)
0x14001b44f  lea     rcx, [rsp+200h+var_1A0]; this
0x14001b454  call    ??1path@filesystem@boost@@QEAA@XZ; boost::filesystem::path::~path(void)
0x14001b459  lea     rdx, [rsp+200h+var_1A0]
0x14001b45e  lea     rcx, [rbp+100h+var_120]
0x14001b462  call    ?str@?$basic_ostringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::wostringstream::str(void)
0x14001b467  nop
0x14001b468  mov     rdx, rax
0x14001b46b  lea     rcx, [rbp+100h+pExceptionObject]
0x14001b46f  call    ??0GetUserSidException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::GetUserSidException::GetUserSidException(std::wstring const &)
0x14001b474  lea     rdx, _TI3?AVGetUserSidException@Uev@@; pThrowInfo
0x14001b47b  lea     rcx, [rbp+100h+pExceptionObject]; pExceptionObject
0x14001b47f  call    _CxxThrowException_0
```
