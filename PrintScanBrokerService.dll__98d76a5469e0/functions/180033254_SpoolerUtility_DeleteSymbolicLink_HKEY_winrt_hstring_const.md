# SpoolerUtility::DeleteSymbolicLink(HKEY__ *,winrt::hstring const &)

- ea: `0x180033254`
- end: `0x18003347d`
- name: `?DeleteSymbolicLink@SpoolerUtility@@SA_NPEAUHKEY__@@AEBUhstring@winrt@@@Z`
- size: `553`
- prototype: `bool __fastcall(HKEY hSourceHandle, const struct winrt::hstring *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009910`

## callees

- `0x18000fa2c`
- `0x18001255c`
- `0x18001cfd4`
- `0x18001d058`
- `0x18001d0a0`
- `0x180027060`
- `0x18002b28c`
- `0x18002faf8`
- `0x1800331c4`
- `0x180033254`
- `0x1800355f0`
- `0x1800358a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800332ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800332ca`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800332f5`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800332f5`
- `ntdll!RtlInitUnicodeString` at `0x180033372`
- `ntdll!RtlInitUnicodeString` at `0x1800333fb`
- `ntdll!RtlInitUnicodeString` at `0x180033372`
- `ntdll!RtlInitUnicodeString` at `0x1800333fb`
- `ntdll!NtDeleteKey` at `0x18003343f`
- `ntdll!NtDeleteKey` at `0x18003343f`
- `ntdll!NtQueryValueKey` at `0x180033428`
- `ntdll!NtQueryValueKey` at `0x180033428`
- `ntdll!NtOpenKeyEx` at `0x1800333bb`
- `ntdll!NtOpenKeyEx` at `0x1800333bb`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003327b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003327b`

## string_xrefs

- `0x1800332a6`: `onecoreuap\printscan\print\printscanbroker\class\spoolerutility.cpp`
- `0x18003330e`: `onecoreuap\printscan\print\printscanbroker\class\spoolerutility.cpp`
- `0x18003334b`: `onecoreuap\printscan\print\printscanbroker\class\spoolerutility.cpp`
- `0x1800333d8`: `onecoreuap\printscan\print\printscanbroker\class\spoolerutility.cpp`
- `0x1800333c9`: `NtOpenKeyEx failed!`
- `0x1800333f0`: `SymbolicLinkValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall SpoolerUtility::DeleteSymbolicLink(
        PrintScanBrokerUtilities *hSourceHandle,
        const struct winrt::hstring *this)
{
  DWORD CallerProcessId; // eax
  HANDLE CurrentProcess; // rax
  unsigned int v6; // eax
  enum HandleType v7; // r8d
  bool IsValidHandleType; // al
  char v9; // bl
  const WCHAR *v10; // rax
  int v11; // eax
  NTSTATUS v12; // eax
  const char *bInheritHandle; // [rsp+28h] [rbp-31h]
  const char *bInheritHandlea; // [rsp+28h] [rbp-31h]
  const char *bInheritHandleb; // [rsp+28h] [rbp-31h]
  const char *dwOptions; // [rsp+30h] [rbp-29h]
  HANDLE KeyHandle; // [rsp+40h] [rbp-19h] BYREF
  char *v19; // [rsp+48h] [rbp-11h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-9h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+60h] [rbp+7h] BYREF
  _QWORD v22[4]; // [rsp+70h] [rbp+17h] BYREF
  __int128 v23; // [rsp+90h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  ULONG ResultLength; // [rsp+D0h] [rbp+77h] BYREF
  HANDLE TargetHandle; // [rsp+D8h] [rbp+7Fh] BYREF

  CallerProcessId = PrintScanBrokerUtilities::GetCallerProcessId(hSourceHandle);
  v19 = (char *)OpenProcess(0x40u, 0, CallerProcessId);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x78,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
    (const char *)((unsigned __int64)(v19 - 1) > 0xFFFFFFFFFFFFFFFDuLL),
    (bool)"Invalid client process information!",
    bInheritHandle);
  TargetHandle = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &TargetHandle,
    0);
  CurrentProcess = GetCurrentProcess();
  v6 = DuplicateHandle(v19, hSourceHandle, CurrentProcess, &TargetHandle, 0, 0, 2u);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x7B,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
    (const char *)v6,
    (int)"DuplicateHandle failed!",
    bInheritHandlea);
  IsValidHandleType = PrintScanBrokerUtilities::IsValidHandleType(TargetHandle, (void *)2, v7);
  v9 = 1;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x7C,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
    (const char *)0x80070006LL,
    !IsValidHandleType,
    (bool)"Invalid handle type!",
    dwOptions);
  DestinationString = 0;
  v10 = winrt::hstring::c_str(this);
  RtlInitUnicodeString(&DestinationString, v10);
  v22[0] = 48;
  v22[3] = 320;
  v22[1] = TargetHandle;
  v22[2] = &DestinationString;
  v23 = 0;
  KeyHandle = 0;
  v11 = NtOpenKeyEx(&KeyHandle, 0x2000000, v22, 8);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x85,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
    (const char *)(v11 | 0x10000000u),
    (int)"NtOpenKeyEx failed!",
    bInheritHandleb);
  ValueName = 0;
  RtlInitUnicodeString(&ValueName, L"SymbolicLinkValue");
  ResultLength = 0;
  v12 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, 0, 0, &ResultLength);
  if ( !ResultLength || v12 == -1073741772 || NtDeleteKey(KeyHandle) < 0 )
    v9 = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&KeyHandle);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&TargetHandle);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((void **)&v19);
  return v9;
}

```

## disassembly

```asm
0x180033254  mov     [rsp-8+arg_0], rbx
0x180033259  push    rbp
0x18003325a  push    rsi
0x18003325b  push    rdi
0x18003325c  lea     rbp, [rsp-47h]
0x180033261  sub     rsp, 0A0h
0x180033268  mov     rsi, rdx
0x18003326b  mov     rdi, rcx
0x18003326e  call    ?GetCallerProcessId@PrintScanBrokerUtilities@@YAKXZ; PrintScanBrokerUtilities::GetCallerProcessId(void)
0x180033273  mov     r8d, eax; dwProcessId
0x180033276  xor     edx, edx; bInheritHandle
0x180033278  lea     ecx, [rdx+40h]; dwDesiredAccess
0x18003327b  call    cs:__imp_OpenProcess
0x180033281  mov     rbx, rax
0x180033284  mov     [rbp+57h+var_68], rax
0x180033288  dec     rax
0x18003328b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003328f  setnbe  al
0x180033292  mov     rcx, [rbp+5Fh]; this
0x180033296  lea     rdx, aInvalidClientP; "Invalid client process information!"
0x18003329d  mov     qword ptr [rsp+0B0h+dwDesiredAccess], rdx; bool
0x1800332a2  movzx   r9d, al; char *
0x1800332a6  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\printscan"...
0x1800332ad  mov     edx, 78h ; 'x'; void *
0x1800332b2  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1800332b7  mov     [rbp+57h+TargetHandle], 0
0x1800332bf  xor     edx, edx
0x1800332c1  lea     rcx, [rbp+57h+TargetHandle]
0x1800332c5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800332ca  call    cs:__imp_GetCurrentProcess
0x1800332d0  mov     [rsp+0B0h+dwOptions], 2; char *
0x1800332d8  mov     [rsp+0B0h+bInheritHandle], 0; char *
0x1800332e0  mov     [rsp+0B0h+dwDesiredAccess], 0; dwDesiredAccess
0x1800332e8  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x1800332ec  mov     r8, rax; hTargetProcessHandle
0x1800332ef  mov     rdx, rdi; hSourceHandle
0x1800332f2  mov     rcx, rbx; hSourceProcessHandle
0x1800332f5  call    cs:__imp_DuplicateHandle
0x1800332fb  mov     rcx, [rbp+5Fh]; this
0x1800332ff  lea     rdx, aDuplicatehandl; "DuplicateHandle failed!"
0x180033306  mov     qword ptr [rsp+0B0h+dwDesiredAccess], rdx; int
0x18003330b  mov     r9d, eax; char *
0x18003330e  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\printscan"...
0x180033315  mov     edx, 7Bh ; '{'; void *
0x18003331a  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18003331f  mov     edx, 2; void *
0x180033324  mov     rcx, [rbp+57h+TargetHandle]; hFile
0x180033328  call    ?IsValidHandleType@PrintScanBrokerUtilities@@YA_NPEAXW4HandleType@1@@Z; PrintScanBrokerUtilities::IsValidHandleType(void *,PrintScanBrokerUtilities::HandleType)
0x18003332d  mov     bl, 1
0x18003332f  xor     al, bl
0x180033331  mov     rcx, [rbp+5Fh]; this
0x180033335  lea     rdx, aInvalidHandleT; "Invalid handle type!"
0x18003333c  mov     qword ptr [rsp+0B0h+bInheritHandle], rdx; char *
0x180033341  mov     byte ptr [rsp+0B0h+dwDesiredAccess], al; char
0x180033345  mov     r9d, 80070006h; char *
0x18003334b  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\printscan"...
0x180033352  mov     edx, 7Ch ; '|'; void *
0x180033357  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18003335c  xorps   xmm0, xmm0
0x18003335f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180033363  mov     rcx, rsi; this
0x180033366  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18003336b  mov     rdx, rax; SourceString
0x18003336e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180033372  call    cs:__imp_RtlInitUnicodeString
0x180033378  mov     [rbp+57h+var_40], 30h ; '0'
0x180033380  mov     [rbp+57h+var_28], 140h
0x180033388  mov     rax, [rbp+57h+TargetHandle]
0x18003338c  mov     [rbp+57h+var_38], rax
0x180033390  lea     rax, [rbp+57h+DestinationString]
0x180033394  mov     [rbp+57h+var_30], rax
0x180033398  xorps   xmm0, xmm0
0x18003339b  movdqu  [rbp+57h+var_20], xmm0
0x1800333a0  mov     [rbp+57h+KeyHandle], 0
0x1800333a8  mov     r9d, 8
0x1800333ae  lea     r8, [rbp+57h+var_40]
0x1800333b2  mov     edx, 2000000h
0x1800333b7  lea     rcx, [rbp+57h+KeyHandle]
0x1800333bb  call    cs:__imp_NtOpenKeyEx
0x1800333c1  bts     eax, 1Ch
0x1800333c5  mov     rcx, [rbp+5Fh]; this
0x1800333c9  lea     rdx, aNtopenkeyexFai; "NtOpenKeyEx failed!"
0x1800333d0  mov     qword ptr [rsp+0B0h+dwDesiredAccess], rdx; int
0x1800333d5  mov     r9d, eax; char *
0x1800333d8  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\printscan"...
0x1800333df  mov     edx, 85h; void *
0x1800333e4  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800333e9  xorps   xmm0, xmm0
0x1800333ec  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x1800333f0  lea     rdx, SourceString; "SymbolicLinkValue"
0x1800333f7  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1800333fb  call    cs:__imp_RtlInitUnicodeString
0x180033401  mov     [rbp+57h+ResultLength], 0
0x180033408  lea     rax, [rbp+57h+ResultLength]
0x18003340c  mov     qword ptr [rsp+0B0h+bInheritHandle], rax; ResultLength
0x180033411  mov     [rsp+0B0h+dwDesiredAccess], 0; Length
0x180033419  xor     r9d, r9d; KeyValueInformation
0x18003341c  lea     r8d, [r9+2]; KeyValueInformationClass
0x180033420  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180033424  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180033428  call    cs:__imp_NtQueryValueKey
0x18003342e  cmp     [rbp+57h+ResultLength], 0
0x180033432  jbe     short loc_180033449
0x180033434  cmp     eax, 0C0000034h
0x180033439  jz      short loc_180033449
0x18003343b  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18003343f  call    cs:__imp_NtDeleteKey
0x180033445  test    eax, eax
0x180033447  jns     short loc_18003344B
0x180033449  xor     ebx, ebx
0x18003344b  lea     rcx, [rbp+57h+KeyHandle]
0x18003344f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180033454  nop
0x180033455  lea     rcx, [rbp+57h+TargetHandle]
0x180033459  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003345e  nop
0x18003345f  lea     rcx, [rbp+57h+var_68]
0x180033463  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180033468  mov     al, bl
0x18003346a  mov     rbx, [rsp+0B0h+arg_0]
0x180033472  add     rsp, 0A0h
0x180033479  pop     rdi
0x18003347a  pop     rsi
0x18003347b  pop     rbp
0x18003347c  retn
```
