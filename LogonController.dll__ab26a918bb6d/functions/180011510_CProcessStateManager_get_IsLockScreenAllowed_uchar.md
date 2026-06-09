# CProcessStateManager::get_IsLockScreenAllowed(uchar *)

- ea: `0x180011510`
- end: `0x1800117bc`
- name: `?get_IsLockScreenAllowed@CProcessStateManager@@UEAAJPEAE@Z`
- size: `684`
- prototype: `__int64 __fastcall(CProcessStateManager *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180004b70`
- `0x180004c00`
- `0x180010348`
- `0x180011510`
- `0x18004247c`
- `0x18005d4e8`
- `0x18006c000`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180011739`
- `KERNEL32!LocalFree` at `0x180011751`
- `KERNEL32!LocalFree` at `0x180011739`
- `KERNEL32!LocalFree` at `0x180011751`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001156f`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800115cb`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001156f`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800115cb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001160d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001160d`
- `KERNEL32!AcquireSRWLockShared` at `0x180011558`
- `KERNEL32!AcquireSRWLockShared` at `0x180011595`
- `KERNEL32!AcquireSRWLockShared` at `0x180011558`
- `KERNEL32!AcquireSRWLockShared` at `0x180011595`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800115f7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800115f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800115ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011657`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800115ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011657`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001171f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001171f`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800115df`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800115df`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001168e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001168e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180011665`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180011665`

## string_xrefs

- `0x1800116be`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CProcessStateManager::get_IsLockScreenAllowed(RTL_SRWLOCK *this, bool *a2)
{
  unsigned __int8 v4; // r14
  RTL_SRWLOCK *v5; // rbx
  bool v6; // r12
  HSTRING Ptr; // rcx
  bool v8; // r15
  HSTRING v9; // rcx
  PCWSTR v10; // rax
  RTL_SRWLOCK *v11; // rbx
  char v12; // di
  const WCHAR *StringRawBuffer; // rax
  const char *v15; // r9
  signed int v16; // ebx
  LSTATUS ValueW; // eax
  unsigned int LastError; // ebx
  int pvData; // [rsp+40h] [rbp-C0h] BYREF
  PSID Sid; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[268]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v4 = 1;
  *a2 = 1;
  v5 = this + 12;
  AcquireSRWLockShared(this + 12);
  *a2 = BYTE1(this[13].Ptr) != 0;
  if ( v5 )
    ReleaseSRWLockShared(v5);
  v6 = 0;
  Ptr = (HSTRING)this[51].Ptr;
  if ( Ptr )
  {
    Sid = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(Ptr, 0);
    if ( !ConvertStringSidToSidW(StringRawBuffer, &Sid) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1A5,
                    (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\processstatemanager.cpp",
                    v15);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&Sid);
      return LastError;
    }
    pvData = 0;
    StringSid = 0;
    if ( ConvertSidToStringSidW(Sid, &StringSid) || (int)ResultFromKnownLastError() >= 0 )
    {
      v16 = StringCchPrintfW(
              SubKey,
              0x104u,
              L"%s\\%s\\%s\\%s",
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
              StringSid,
              L"AnyoneRead",
              L"RemoteLockScreen");
      if ( v16 >= 0 )
      {
        pcbData = 4;
        ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"Enable", 0x10u, 0, &pvData, &pcbData);
        v16 = ValueW;
        if ( ValueW > 0 )
          v16 = (unsigned __int16)ValueW | 0x80070000;
      }
      LocalFree(StringSid);
      if ( v16 >= 0 )
        v6 = pvData != 0;
    }
    if ( Sid )
      LocalFree(Sid);
  }
  v8 = 0;
  AcquireSRWLockShared(this + 50);
  StringSid = (LPWSTR)&this[50];
  v9 = (HSTRING)this[51].Ptr;
  if ( v9 )
  {
    v10 = WindowsGetStringRawBuffer(v9, 0);
    v8 = (unsigned int)GetAssignedAccessTypeForUser(v10) == 1;
  }
  if ( this != (RTL_SRWLOCK *)-400LL )
    ReleaseSRWLockShared(this + 50);
  if ( !*a2 || GetSystemMetrics(4096) && !v6 )
    goto LABEL_29;
  v11 = this + 67;
  AcquireSRWLockExclusive(this + 67);
  v12 = (char)this[68].Ptr;
  if ( v11 )
    ReleaseSRWLockExclusive(v11);
  if ( v12 && !v8 )
LABEL_29:
    v4 = 0;
  *a2 = v4;
  return 0;
}

```

## disassembly

```asm
0x180011510  mov     [rsp-8+arg_10], rbx
0x180011515  mov     [rsp-8+arg_18], rsi
0x18001151a  push    rbp
0x18001151b  push    rdi
0x18001151c  push    r12
0x18001151e  push    r14
0x180011520  push    r15
0x180011522  lea     rbp, [rsp-180h]
0x18001152a  sub     rsp, 280h
0x180011531  mov     rax, cs:__security_cookie
0x180011538  xor     rax, rsp
0x18001153b  mov     [rbp+1A0h+var_28], rax
0x180011542  mov     rsi, rdx
0x180011545  mov     rdi, rcx
0x180011548  mov     r14d, 1
0x18001154e  mov     [rdx], r14b
0x180011551  lea     rbx, [rcx+60h]
0x180011555  mov     rcx, rbx; SRWLock
0x180011558  call    cs:__imp_AcquireSRWLockShared
0x18001155e  cmp     byte ptr [rdi+69h], 0
0x180011562  setnz   al
0x180011565  mov     [rsi], al
0x180011567  test    rbx, rbx
0x18001156a  jz      short loc_180011575
0x18001156c  mov     rcx, rbx; SRWLock
0x18001156f  call    cs:__imp_ReleaseSRWLockShared
0x180011575  xor     r12b, r12b
0x180011578  mov     rcx, [rdi+198h]; string
0x18001157f  test    rcx, rcx
0x180011582  jnz     loc_18001164C
0x180011588  xor     r15b, r15b
0x18001158b  lea     rbx, [rdi+190h]
0x180011592  mov     rcx, rbx; SRWLock
0x180011595  call    cs:__imp_AcquireSRWLockShared
0x18001159b  mov     [rsp+2A0h+StringSid], rbx
0x1800115a0  mov     rcx, [rdi+198h]; string
0x1800115a7  test    rcx, rcx
0x1800115aa  jz      short loc_1800115C3
0x1800115ac  xor     edx, edx; length
0x1800115ae  call    cs:__imp_WindowsGetStringRawBuffer
0x1800115b4  mov     rcx, rax
0x1800115b7  call    GetAssignedAccessTypeForUser
0x1800115bc  cmp     eax, r14d
0x1800115bf  setz    r15b
0x1800115c3  test    rbx, rbx
0x1800115c6  jz      short loc_1800115D1
0x1800115c8  mov     rcx, rbx; SRWLock
0x1800115cb  call    cs:__imp_ReleaseSRWLockShared
0x1800115d1  cmp     byte ptr [rsi], 0
0x1800115d4  jz      loc_1800117B4
0x1800115da  mov     ecx, 1000h; nIndex
0x1800115df  call    cs:__imp_GetSystemMetrics
0x1800115e5  test    eax, eax
0x1800115e7  jnz     loc_1800117A1
0x1800115ed  lea     rbx, [rdi+218h]
0x1800115f4  mov     rcx, rbx; SRWLock
0x1800115f7  call    cs:__imp_AcquireSRWLockExclusive
0x1800115fd  nop
0x1800115fe  mov     dil, [rdi+220h]
0x180011605  test    rbx, rbx
0x180011608  jz      short loc_180011613
0x18001160a  mov     rcx, rbx; SRWLock
0x18001160d  call    cs:__imp_ReleaseSRWLockExclusive
0x180011613  test    dil, dil
0x180011616  jnz     loc_1800117AB
0x18001161c  mov     [rsi], r14b
0x18001161f  xor     eax, eax
0x180011621  mov     rcx, [rbp+1A0h+var_28]
0x180011628  xor     rcx, rsp; StackCookie
0x18001162b  call    __security_check_cookie
0x180011630  lea     r11, [rsp+2A0h+var_20]
0x180011638  mov     rbx, [r11+40h]
0x18001163c  mov     rsi, [r11+48h]
0x180011640  mov     rsp, r11
0x180011643  pop     r15
0x180011645  pop     r14
0x180011647  pop     r12
0x180011649  pop     rdi
0x18001164a  pop     rbp
0x18001164b  retn
0x18001164c  mov     [rsp+2A0h+Sid], 0
0x180011655  xor     edx, edx; length
0x180011657  call    cs:__imp_WindowsGetStringRawBuffer
0x18001165d  lea     rdx, [rsp+2A0h+Sid]; Sid
0x180011662  mov     rcx, rax; StringSid
0x180011665  call    cs:__imp_ConvertStringSidToSidW
0x18001166b  test    eax, eax
0x18001166d  jz      loc_18001176B
0x180011673  mov     [rsp+2A0h+var_260], 0
0x18001167b  mov     [rsp+2A0h+StringSid], 0
0x180011684  lea     rdx, [rsp+2A0h+StringSid]; StringSid
0x180011689  mov     rcx, [rsp+2A0h+Sid]; Sid
0x18001168e  call    cs:__imp_ConvertSidToStringSidW
0x180011694  test    eax, eax
0x180011696  jz      loc_18001175C
0x18001169c  mov     rcx, [rsp+2A0h+StringSid]
0x1800116a1  lea     rax, aRemotelockscre; "RemoteLockScreen"
0x1800116a8  mov     [rsp+2A0h+pcbData], rax
0x1800116ad  mov     rax, cs:off_18009E008; "AnyoneRead"
0x1800116b4  mov     [rsp+2A0h+pvData], rax
0x1800116b9  mov     [rsp+2A0h+pdwType], rcx
0x1800116be  lea     r9, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800116c5  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x1800116cc  mov     edx, 104h; unsigned __int64
0x1800116d1  lea     rcx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x1800116d6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800116db  mov     ebx, eax
0x1800116dd  test    eax, eax
0x1800116df  js      short loc_180011734
0x1800116e1  mov     [rsp+2A0h+var_248], 4
0x1800116e9  lea     rax, [rsp+2A0h+var_248]
0x1800116ee  mov     [rsp+2A0h+pcbData], rax; pcbData
0x1800116f3  lea     rax, [rsp+2A0h+var_260]
0x1800116f8  mov     [rsp+2A0h+pvData], rax; pvData
0x1800116fd  mov     [rsp+2A0h+pdwType], 0; pdwType
0x180011706  mov     r9d, 10h; dwFlags
0x18001170c  lea     r8, aEnable; "Enable"
0x180011713  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x180011718  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001171f  call    cs:__imp_RegGetValueW
0x180011725  mov     ebx, eax
0x180011727  test    eax, eax
0x180011729  jle     short loc_180011734
0x18001172b  movzx   ebx, ax
0x18001172e  or      ebx, 80070000h
0x180011734  mov     rcx, [rsp+2A0h+StringSid]; hMem
0x180011739  call    cs:__imp_LocalFree
0x18001173f  test    ebx, ebx
0x180011741  jns     short loc_180011796
0x180011743  mov     rcx, [rsp+2A0h+Sid]; hMem
0x180011748  test    rcx, rcx
0x18001174b  jz      loc_180011588
0x180011751  call    cs:__imp_LocalFree
0x180011757  jmp     loc_180011588
0x18001175c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180011761  test    eax, eax
0x180011763  jns     loc_18001169C
0x180011769  jmp     short loc_180011743
0x18001176b  mov     rcx, [rbp+1A8h]; this
0x180011772  lea     r8, aPcshellShellAu_8; "pcshell\\shell\\auth\\authux\\controlle"...
0x180011779  mov     edx, 1A5h; void *
0x18001177e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011783  mov     ebx, eax
0x180011785  lea     rcx, [rsp+2A0h+Sid]
0x18001178a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x18001178f  mov     eax, ebx
0x180011791  jmp     loc_180011621
0x180011796  cmp     [rsp+2A0h+var_260], 0
0x18001179b  setnz   r12b
0x18001179f  jmp     short loc_180011743
0x1800117a1  test    r12b, r12b
0x1800117a4  jz      short loc_1800117B4
0x1800117a6  jmp     loc_1800115ED
0x1800117ab  test    r15b, r15b
0x1800117ae  jnz     loc_18001161C
0x1800117b4  xor     r14b, r14b
0x1800117b7  jmp     loc_18001161C
```
