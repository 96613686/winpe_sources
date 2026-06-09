# WpnGetPreinstalledOnSystemUserRegistrationInformation(IPlatformConfigurationProvider *,uint *,WPN_REGISTRATION_INFO * *)

- ea: `0x18007a74c`
- end: `0x18007a892`
- name: `?WpnGetPreinstalledOnSystemUserRegistrationInformation@@YAJPEAUIPlatformConfigurationProvider@@PEAIPEAPEAUWPN_REGISTRATION_INFO@@@Z`
- size: `326`
- prototype: `__int64 __fastcall(struct IPlatformConfigurationProvider *, unsigned int *, struct WPN_REGISTRATION_INFO **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000e620`

## callees

- `0x18002db0c`
- `0x18007a74c`
- `0x18007ca90`
- `0x180086bd8`
- `0x18009abf8`
- `0x18009ae68`
- `0x1800b99f0`
- `0x1800ee658`

## import_xrefs

- `ntdll!RtlConvertSidToUnicodeString` at `0x18007a7b3`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18007a7b3`
- `ntdll!RtlFreeUnicodeString` at `0x18007a825`
- `ntdll!RtlFreeUnicodeString` at `0x18007a825`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007a7ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007a7ff`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18007a78b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18007a78b`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18007a7d4`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18007a7d4`

## string_xrefs

- `0x18007a80e`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x18007a850`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x18007a86a`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WpnGetPreinstalledOnSystemUserRegistrationInformation(
        struct IPlatformConfigurationProvider *a1,
        unsigned int *a2,
        struct WPN_REGISTRATION_INFO **a3)
{
  const char *v6; // r9
  NTSTATUS v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // ebx
  HKEY phkResult; // [rsp+20h] [rbp-49h] BYREF
  DWORD cbSid; // [rsp+28h] [rbp-41h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-39h] BYREF
  struct _UNICODE_STRING *p_UnicodeString; // [rsp+40h] [rbp-29h] BYREF
  _BYTE pSid[80]; // [rsp+50h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  cbSid = 68;
  if ( CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
  {
    UnicodeString = 0;
    p_UnicodeString = &UnicodeString;
    v7 = RtlConvertSidToUnicodeString(&UnicodeString, pSid, 1u);
    if ( v7 < 0 )
    {
      v9 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x555,
             (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
             (const char *)(unsigned int)v7,
             (int)phkResult);
    }
    else
    {
      phkResult = 0;
      v8 = RegOpenKeyW(HKEY_USERS, UnicodeString.Buffer, &phkResult);
      if ( v8 )
      {
        v9 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x558,
               (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
               (const char *)v8,
               (unsigned int)phkResult);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        wil::details::unique_storage<wil::details::resource_policy<_UNICODE_STRING *,void (*)(_UNICODE_STRING *),&void RtlFreeUnicodeString(_UNICODE_STRING *),wistd::integral_constant<unsigned __int64,0>,_UNICODE_STRING *,_UNICODE_STRING *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_UNICODE_STRING *,void (*)(_UNICODE_STRING *),&void RtlFreeUnicodeString(_UNICODE_STRING *),wistd::integral_constant<unsigned __int64,0>,_UNICODE_STRING *,_UNICODE_STRING *,0,std::nullptr_t>>(&p_UnicodeString);
        return v9;
      }
      v9 = WpnEnumerateRegistrationInformation(a1, phkResult, a2, a3);
      if ( phkResult )
        RegCloseKey(phkResult);
    }
    RtlFreeUnicodeString(&UnicodeString);
    return v9;
  }
  return wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x550,
           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
           v6);
}

```

## disassembly

```asm
0x18007a74c  mov     [rsp-8+arg_18], rbx
0x18007a751  push    rbp
0x18007a752  push    rsi
0x18007a753  push    rdi
0x18007a754  lea     rbp, [rsp-47h]
0x18007a759  sub     rsp, 0B0h
0x18007a760  mov     rax, cs:__security_cookie
0x18007a767  xor     rax, rsp
0x18007a76a  mov     [rbp+57h+var_20], rax
0x18007a76e  mov     rsi, r8
0x18007a771  mov     rdi, rdx
0x18007a774  mov     rbx, rcx
0x18007a777  mov     [rbp+57h+cbSid], 44h ; 'D'
0x18007a77e  lea     r9, [rbp+57h+cbSid]; cbSid
0x18007a782  lea     r8, [rbp+57h+pSid]; pSid
0x18007a786  xor     edx, edx; DomainSid
0x18007a788  lea     ecx, [rdx+16h]; WellKnownSidType
0x18007a78b  call    cs:__imp_CreateWellKnownSid
0x18007a791  test    eax, eax
0x18007a793  jz      loc_18007A84C
0x18007a799  xorps   xmm0, xmm0
0x18007a79c  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x18007a7a0  lea     rax, [rbp+57h+UnicodeString]
0x18007a7a4  mov     [rbp+57h+var_80], rax
0x18007a7a8  mov     r8b, 1; AllocateDestinationString
0x18007a7ab  lea     rdx, [rbp+57h+pSid]; Sid
0x18007a7af  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x18007a7b3  call    cs:__imp_RtlConvertSidToUnicodeString
0x18007a7b9  test    eax, eax
0x18007a7bb  js      short loc_18007A807
0x18007a7bd  mov     [rbp+57h+phkResult], 0
0x18007a7c5  lea     r8, [rbp+57h+phkResult]; phkResult
0x18007a7c9  mov     rdx, [rbp+57h+UnicodeString.Buffer]; lpSubKey
0x18007a7cd  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18007a7d4  call    cs:__imp_RegOpenKeyW
0x18007a7da  test    eax, eax
0x18007a7dc  jnz     loc_18007A863
0x18007a7e2  mov     r9, rsi; struct WPN_REGISTRATION_INFO **
0x18007a7e5  mov     r8, rdi; unsigned int *
0x18007a7e8  mov     rdx, [rbp+57h+phkResult]; HKEY
0x18007a7ec  mov     rcx, rbx; struct IPlatformConfigurationProvider *
0x18007a7ef  call    ?WpnEnumerateRegistrationInformation@@YAJPEAUIPlatformConfigurationProvider@@PEAUHKEY__@@PEAIPEAPEAUWPN_REGISTRATION_INFO@@@Z; WpnEnumerateRegistrationInformation(IPlatformConfigurationProvider *,HKEY__ *,uint *,WPN_REGISTRATION_INFO * *)
0x18007a7f4  mov     ebx, eax
0x18007a7f6  mov     rcx, [rbp+57h+phkResult]; hKey
0x18007a7fa  test    rcx, rcx
0x18007a7fd  jz      short loc_18007A821
0x18007a7ff  call    cs:__imp_RegCloseKey
0x18007a805  jmp     short loc_18007A821
0x18007a807  mov     rcx, [rbp+5Fh]; this
0x18007a80b  mov     r9d, eax; char *
0x18007a80e  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007a815  mov     edx, 555h; void *
0x18007a81a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18007a81f  mov     ebx, eax
0x18007a821  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x18007a825  call    cs:__imp_RtlFreeUnicodeString
0x18007a82b  mov     eax, ebx
0x18007a82d  mov     rcx, [rbp+57h+var_20]
0x18007a831  xor     rcx, rsp; StackCookie
0x18007a834  call    __security_check_cookie
0x18007a839  mov     rbx, [rsp+0C0h+arg_18]
0x18007a841  add     rsp, 0B0h
0x18007a848  pop     rdi
0x18007a849  pop     rsi
0x18007a84a  pop     rbp
0x18007a84b  retn
0x18007a84c  mov     rcx, [rbp+5Fh]; this
0x18007a850  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007a857  mov     edx, 550h; void *
0x18007a85c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007a861  jmp     short loc_18007A82D
0x18007a863  mov     rcx, [rbp+5Fh]; this
0x18007a867  mov     r9d, eax; char *
0x18007a86a  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007a871  mov     edx, 558h; void *
0x18007a876  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007a87b  mov     ebx, eax
0x18007a87d  lea     rcx, [rbp+57h+phkResult]
0x18007a881  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007a886  nop
0x18007a887  lea     rcx, [rbp+57h+var_80]
0x18007a88b  call    ??1?$unique_storage@U?$resource_policy@PEAU_UNICODE_STRING@@P6AXPEAU1@@Z$1?RtlFreeUnicodeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_UNICODE_STRING *,void (*)(_UNICODE_STRING *),&RtlFreeUnicodeString(_UNICODE_STRING *),wistd::integral_constant<unsigned __int64,0>,_UNICODE_STRING *,_UNICODE_STRING *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_UNICODE_STRING *,void (*)(_UNICODE_STRING *),&RtlFreeUnicodeString(_UNICODE_STRING *),wistd::integral_constant<unsigned __int64,0>,_UNICODE_STRING *,_UNICODE_STRING *,0,std::nullptr_t>>(void)
0x18007a890  jmp     short loc_18007A82B
```
