# CProcessStateManager::get_ShowAccentColorInsteadOfLogonBackgroundImage(uchar *)

- ea: `0x180004520`
- end: `0x1800046be`
- name: `?get_ShowAccentColorInsteadOfLogonBackgroundImage@CProcessStateManager@@UEAAJPEAE@Z`
- size: `414`
- prototype: `__int64 __fastcall(CProcessStateManager *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180004520`
- `0x180004b70`
- `0x180004c00`
- `0x18005d488`
- `0x18006c000`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180004639`
- `KERNEL32!LocalFree` at `0x180004648`
- `KERNEL32!LocalFree` at `0x180004639`
- `KERNEL32!LocalFree` at `0x180004648`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004563`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004563`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000461f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000461f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004592`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004592`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180004571`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180004571`

## string_xrefs

- `0x1800045b1`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`

## pseudocode

```c
__int64 __fastcall CProcessStateManager::get_ShowAccentColorInsteadOfLogonBackgroundImage(
        CProcessStateManager *this,
        bool *a2)
{
  HSTRING v3; // rcx
  const WCHAR *StringRawBuffer; // rax
  signed int v5; // ebx
  LSTATUS ValueW; // eax
  int Error; // eax
  unsigned int v9; // ebx
  int pdwType; // [rsp+20h] [rbp-268h]
  int pvData; // [rsp+40h] [rbp-248h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-244h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-240h] BYREF
  PSID Sid; // [rsp+50h] [rbp-238h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  *a2 = 0;
  v3 = (HSTRING)*((_QWORD *)this + 51);
  if ( !v3 )
    return 0;
  Sid = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(v3, 0);
  if ( ConvertStringSidToSidW(StringRawBuffer, &Sid) || (Error = ResultFromKnownLastError(), v9 = Error, Error >= 0) )
  {
    pvData = 0;
    StringSid = 0;
    if ( ConvertSidToStringSidW(Sid, &StringSid) || (int)ResultFromKnownLastError() >= 0 )
    {
      v5 = StringCchPrintfW(
             SubKey,
             0x104u,
             L"%s\\%s\\%s\\%s",
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
             StringSid,
             L"AnyoneRead",
             L"LockScreen");
      if ( v5 >= 0 )
      {
        pcbData = 4;
        ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"HideLogonBackgroundImage", 0x10u, 0, &pvData, &pcbData);
        v5 = ValueW;
        if ( ValueW > 0 )
          v5 = (unsigned __int16)ValueW | 0x80070000;
      }
      LocalFree(StringSid);
      if ( v5 >= 0 )
        *a2 = pvData != 0;
    }
    LocalFree(Sid);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x236,
    (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\processstatemanager.cpp",
    (const char *)(unsigned int)Error,
    pdwType);
  return v9;
}

```

## disassembly

```asm
0x180004520  mov     [rsp+arg_10], rbx
0x180004525  mov     [rsp+arg_18], rsi
0x18000452a  push    rdi
0x18000452b  sub     rsp, 280h
0x180004532  mov     rax, cs:__security_cookie
0x180004539  xor     rax, rsp
0x18000453c  mov     [rsp+288h+var_18], rax
0x180004544  mov     byte ptr [rdx], 0
0x180004547  mov     rdi, rdx
0x18000454a  mov     rcx, [rcx+198h]; string
0x180004551  test    rcx, rcx
0x180004554  jz      loc_18000464E
0x18000455a  xor     esi, esi
0x18000455c  xor     edx, edx; length
0x18000455e  mov     [rsp+288h+Sid], rsi
0x180004563  call    cs:__imp_WindowsGetStringRawBuffer
0x180004569  mov     rcx, rax; StringSid
0x18000456c  lea     rdx, [rsp+288h+Sid]; Sid
0x180004571  call    cs:__imp_ConvertStringSidToSidW
0x180004577  test    eax, eax
0x180004579  jz      loc_180004675
0x18000457f  mov     rcx, [rsp+288h+Sid]; Sid
0x180004584  lea     rdx, [rsp+288h+StringSid]; StringSid
0x180004589  mov     [rsp+288h+var_248], esi
0x18000458d  mov     [rsp+288h+StringSid], rsi
0x180004592  call    cs:__imp_ConvertSidToStringSidW
0x180004598  test    eax, eax
0x18000459a  jz      loc_1800046AF
0x1800045a0  mov     rcx, [rsp+288h+StringSid]
0x1800045a5  lea     rax, aLockscreen; "LockScreen"
0x1800045ac  mov     [rsp+288h+pcbData], rax
0x1800045b1  lea     r9, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800045b8  mov     rax, cs:off_18009E008; "AnyoneRead"
0x1800045bf  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x1800045c6  mov     [rsp+288h+pvData], rax
0x1800045cb  mov     edx, 104h; unsigned __int64
0x1800045d0  mov     [rsp+288h+pdwType], rcx
0x1800045d5  lea     rcx, [rsp+288h+SubKey]; unsigned __int16 *
0x1800045da  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800045df  mov     ebx, eax
0x1800045e1  test    eax, eax
0x1800045e3  js      short loc_180004634
0x1800045e5  lea     rax, [rsp+288h+var_244]
0x1800045ea  mov     [rsp+288h+var_244], 4
0x1800045f2  mov     [rsp+288h+pcbData], rax; pcbData
0x1800045f7  lea     r8, Value; "HideLogonBackgroundImage"
0x1800045fe  lea     rax, [rsp+288h+var_248]
0x180004603  mov     r9d, 10h; dwFlags
0x180004609  mov     [rsp+288h+pvData], rax; pvData
0x18000460e  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x180004613  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000461a  mov     [rsp+288h+pdwType], rsi; pdwType
0x18000461f  call    cs:__imp_RegGetValueW
0x180004625  mov     ebx, eax
0x180004627  test    eax, eax
0x180004629  jle     short loc_180004634
0x18000462b  movzx   ebx, ax
0x18000462e  or      ebx, 80070000h
0x180004634  mov     rcx, [rsp+288h+StringSid]; hMem
0x180004639  call    cs:__imp_LocalFree
0x18000463f  test    ebx, ebx
0x180004641  jns     short loc_1800046A4
0x180004643  mov     rcx, [rsp+288h+Sid]; hMem
0x180004648  call    cs:__imp_LocalFree
0x18000464e  xor     eax, eax
0x180004650  mov     rcx, [rsp+288h+var_18]
0x180004658  xor     rcx, rsp; StackCookie
0x18000465b  call    __security_check_cookie
0x180004660  lea     r11, [rsp+288h+var_8]
0x180004668  mov     rbx, [r11+20h]
0x18000466c  mov     rsi, [r11+28h]
0x180004670  mov     rsp, r11
0x180004673  pop     rdi
0x180004674  retn
0x180004675  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000467a  mov     ebx, eax
0x18000467c  test    eax, eax
0x18000467e  jns     loc_18000457F
0x180004684  mov     rcx, [rsp+288h]; this
0x18000468c  lea     r8, aPcshellShellAu_8; "pcshell\\shell\\auth\\authux\\controlle"...
0x180004693  mov     r9d, eax; char *
0x180004696  mov     edx, 236h; void *
0x18000469b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800046a0  mov     eax, ebx
0x1800046a2  jmp     short loc_180004650
0x1800046a4  cmp     [rsp+288h+var_248], esi
0x1800046a8  setnz   al
0x1800046ab  mov     [rdi], al
0x1800046ad  jmp     short loc_180004643
0x1800046af  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800046b4  test    eax, eax
0x1800046b6  jns     loc_1800045A0
0x1800046bc  jmp     short loc_180004643
```
