# Uev::Util::OpenUserHive(void *)

- ea: `0x14001b6a8`
- end: `0x14001b8a8`
- name: `?OpenUserHive@Util@Uev@@SAPEAUHKEY__@@PEAX@Z`
- size: `512`
- prototype: `HKEY __fastcall(void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x140014da0`

## callees

- `0x140003e50`
- `0x140004ab4`
- `0x14000ac88`
- `0x14000ad1c`
- `0x14000afc0`
- `0x14000ba60`
- `0x14000bae4`
- `0x14000e924`
- `0x140011ab4`
- `0x140018c88`
- `0x14001a634`
- `0x14001b144`
- `0x14001b6a8`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14001b79c`
- `ADVAPI32!RegOpenKeyExW` at `0x14001b79c`
- `KERNEL32!GetLastError` at `0x14001b7e3`
- `KERNEL32!GetLastError` at `0x14001b7e3`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x14001b83d`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x14001b83d`

## string_xrefs

- `0x14001b6c6`: `AgentService.Util::OpenUserHive: Entry`
- `0x14001b860`: `AgentService.Util::OpenUserHive: %s`
- `0x14001b7fa`: `Unable to open the hive for user `
- `0x14001b7a6`: `AgentService.Util::OpenUserHive: Exit`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
HKEY __fastcall Uev::Util::OpenUserHive(void *a1)
{
  __int64 UserSid; // rbx
  const WCHAR *v3; // rdx
  LSTATUS v4; // eax
  HKEY v5; // rbx
  DWORD LastError; // ebx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // rax
  __int64 v12; // r8
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rax
  _BYTE v25[32]; // [rsp+30h] [rbp-1D8h] BYREF
  _QWORD pExceptionObject[8]; // [rsp+50h] [rbp-1B8h] BYREF
  HKEY v27[8]; // [rsp+90h] [rbp-178h] BYREF
  HKEY phkResult; // [rsp+D0h] [rbp-138h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+D8h] [rbp-130h] BYREF
  __m128i si128; // [rsp+E8h] [rbp-120h]
  _BYTE v31[240]; // [rsp+100h] [rbp-108h] BYREF

  DbgTrace<5>(L"AgentService.Util::OpenUserHive: Entry");
  try
  {
    phkResult = 0;
    *(_OWORD *)lpSubKey = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(lpSubKey[0]) = 0;
    UserSid = Uev::Util::GetUserSid((__int64)v25, a1);
    if ( lpSubKey != (LPCWSTR *)UserSid )
    {
      std::wstring::_Tidy_deallocate(lpSubKey);
      *(_OWORD *)lpSubKey = *(_OWORD *)UserSid;
      si128 = *(__m128i *)(UserSid + 16);
      *(_QWORD *)(UserSid + 16) = 0;
      *(_QWORD *)(UserSid + 24) = 7;
      *(_WORD *)UserSid = 0;
    }
    std::wstring::_Tidy_deallocate(v25);
    v3 = (const WCHAR *)lpSubKey;
    if ( si128.m128i_i64[1] > 7uLL )
      v3 = lpSubKey[0];
    v4 = RegOpenKeyExW(HKEY_USERS, v3, 0, 0x20019u, &phkResult);
  }
  catch ( Uev::GetUserSidException )
  {
    std::wostringstream::wostringstream(v31);
    std::operator<<<wchar_t,std::char_traits<wchar_t>>(
      v31,
      L"Unable to open the user hive: An error occurred while getting the SID from the user token");
    v20 = std::wostringstream::str(v31, v25);
    std::wstring::c_str(v20, v21, v22, v23);
    DbgTraceFrmtErr<wchar_t const *>((wchar_t *)L"AgentService.Util::OpenUserHive: %s");
    boost::filesystem::path::~path((boost::filesystem::path *)v25);
    v24 = std::wostringstream::str(v31, v25);
    Uev::OpenUserHiveException::OpenUserHiveException(v27, v24);
    throw (Uev::OpenUserHiveException *)v27;
  }
  if ( v4 )
  {
    LastError = GetLastError();
    std::wostringstream::wostringstream(v31);
    v8 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v31, L"Unable to open the hive for user ");
    v11 = std::wstring::c_str(lpSubKey, v9, v8, v10);
    v13 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v12, v11);
    v14 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v13, L": System error code ");
    std::wostream::operator<<(v14, LastError);
    v15 = std::wostringstream::str(v31, v25);
    std::wstring::c_str(v15, v16, v17, v18);
    DbgTraceFrmtErr<wchar_t const *>((wchar_t *)L"AgentService.Util::OpenUserHive: %s");
    boost::filesystem::path::~path((boost::filesystem::path *)v25);
    v19 = std::wostringstream::str(v31, v25);
    Uev::OpenUserHiveException::OpenUserHiveException(pExceptionObject, v19);
    throw (Uev::OpenUserHiveException *)pExceptionObject;
  }
  DbgTrace<5>(L"AgentService.Util::OpenUserHive: Exit");
  v5 = phkResult;
  std::wstring::_Tidy_deallocate(lpSubKey);
  return v5;
}

```

## disassembly

```asm
0x14001b6a8  push    rbx
0x14001b6aa  sub     rsp, 200h
0x14001b6b1  mov     rax, cs:__security_cookie
0x14001b6b8  xor     rax, rsp
0x14001b6bb  mov     [rsp+208h+var_18], rax
0x14001b6c3  mov     rbx, rcx
0x14001b6c6  lea     rcx, aAgentserviceUt_32; "AgentService.Util::OpenUserHive: Entry"
0x14001b6cd  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x14001b6d2  mov     [rsp+208h+var_138], 0
0x14001b6de  xorps   xmm0, xmm0
0x14001b6e1  movups  xmmword ptr [rsp+208h+lpSubKey], xmm0
0x14001b6e9  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14001b6f1  movdqu  [rsp+208h+var_120], xmm1
0x14001b6fa  xor     eax, eax
0x14001b6fc  mov     word ptr [rsp+208h+lpSubKey], ax
0x14001b704  mov     rdx, rbx
0x14001b707  lea     rcx, [rsp+208h+var_1D8]
0x14001b70c  call    ?GetUserSid@Util@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@Z; Uev::Util::GetUserSid(void *)
0x14001b711  mov     rbx, rax
0x14001b714  lea     rax, [rsp+208h+lpSubKey]
0x14001b71c  cmp     rax, rbx
0x14001b71f  jz      short loc_14001B75A
0x14001b721  lea     rcx, [rsp+208h+lpSubKey]
0x14001b729  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001b72e  movups  xmm0, xmmword ptr [rbx]
0x14001b731  movups  xmmword ptr [rsp+208h+lpSubKey], xmm0
0x14001b739  movups  xmm1, xmmword ptr [rbx+10h]
0x14001b73d  movups  [rsp+208h+var_120], xmm1
0x14001b745  mov     qword ptr [rbx+10h], 0
0x14001b74d  mov     qword ptr [rbx+18h], 7
0x14001b755  xor     eax, eax
0x14001b757  mov     [rbx], ax
0x14001b75a  lea     rcx, [rsp+208h+var_1D8]
0x14001b75f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001b764  nop
0x14001b765  lea     rdx, [rsp+208h+lpSubKey]
0x14001b76d  cmp     qword ptr [rsp+208h+var_120+8], 7
0x14001b776  cmova   rdx, [rsp+208h+lpSubKey]; lpSubKey
0x14001b77f  lea     rax, [rsp+208h+var_138]
0x14001b787  mov     [rsp+208h+phkResult], rax; phkResult
0x14001b78c  mov     r9d, 20019h; samDesired
0x14001b792  xor     r8d, r8d; ulOptions
0x14001b795  mov     rcx, 0FFFFFFFF80000003h; hKey
0x14001b79c  call    cs:__imp_RegOpenKeyExW
0x14001b7a2  test    eax, eax
0x14001b7a4  jnz     short loc_14001B7E3
0x14001b7a6  lea     rcx, aAgentserviceUt_21; "AgentService.Util::OpenUserHive: Exit"
0x14001b7ad  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x14001b7b2  mov     rbx, [rsp+208h+var_138]
0x14001b7ba  lea     rcx, [rsp+208h+lpSubKey]
0x14001b7c2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001b7c7  mov     rax, rbx
0x14001b7ca  mov     rcx, [rsp+208h+var_18]
0x14001b7d2  xor     rcx, rsp; StackCookie
0x14001b7d5  call    __security_check_cookie
0x14001b7da  add     rsp, 200h
0x14001b7e1  pop     rbx
0x14001b7e2  retn
0x14001b7e3  call    cs:__imp_GetLastError
0x14001b7e9  nop
0x14001b7ea  mov     ebx, eax
0x14001b7ec  lea     rcx, [rsp+208h+var_108]
0x14001b7f4  call    ??0?$basic_ostringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wostringstream::wostringstream(void)
0x14001b7f9  nop
0x14001b7fa  lea     rdx, aUnableToOpenTh_0; "Unable to open the hive for user "
0x14001b801  lea     rcx, [rsp+208h+var_108]
0x14001b809  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x14001b80e  mov     r8, rax
0x14001b811  lea     rcx, [rsp+208h+lpSubKey]
0x14001b819  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x14001b81e  mov     rdx, rax
0x14001b821  mov     rcx, r8
0x14001b824  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x14001b829  mov     rcx, rax
0x14001b82c  lea     rdx, aSystemErrorCod; ": System error code "
0x14001b833  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x14001b838  mov     edx, ebx
0x14001b83a  mov     rcx, rax
0x14001b83d  call    cs:__imp_??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z; std::wostream::operator<<(ulong)
0x14001b843  lea     rdx, [rsp+208h+var_1D8]
0x14001b848  lea     rcx, [rsp+208h+var_108]
0x14001b850  call    ?str@?$basic_ostringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::wostringstream::str(void)
0x14001b855  mov     rcx, rax
0x14001b858  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x14001b85d  mov     rdx, rax
0x14001b860  lea     rcx, aAgentserviceUt_30; "AgentService.Util::OpenUserHive: %s"
0x14001b867  call    ??$DbgTraceFrmtErr@PEB_W@@YAXPEB_W0@Z; DbgTraceFrmtErr<wchar_t const *>(wchar_t const *,wchar_t const *)
0x14001b86c  lea     rcx, [rsp+208h+var_1D8]; this
0x14001b871  call    ??1path@filesystem@boost@@QEAA@XZ; boost::filesystem::path::~path(void)
0x14001b876  lea     rdx, [rsp+208h+var_1D8]
0x14001b87b  lea     rcx, [rsp+208h+var_108]
0x14001b883  call    ?str@?$basic_ostringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::wostringstream::str(void)
0x14001b888  nop
0x14001b889  mov     rdx, rax
0x14001b88c  lea     rcx, [rsp+208h+pExceptionObject]
0x14001b891  call    ??0OpenUserHiveException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::OpenUserHiveException::OpenUserHiveException(std::wstring const &)
0x14001b896  lea     rdx, _TI3?AVOpenUserHiveException@Uev@@; pThrowInfo
0x14001b89d  lea     rcx, [rsp+208h+pExceptionObject]; pExceptionObject
0x14001b8a2  call    _CxxThrowException_0
```
