# PolicyTaskHelpers::TryDeleteSnapshotCaptureForLoggedInUser(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18002c454`
- end: `0x18002c7b8`
- name: `?TryDeleteSnapshotCaptureForLoggedInUser@PolicyTaskHelpers@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `868`
- prototype: `__int64 __fastcall(_QWORD *, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180028844`

## callees

- `0x180002590`
- `0x180002ba0`
- `0x18000aaf4`
- `0x18000ab14`
- `0x1800122f0`
- `0x180013890`
- `0x1800233ec`
- `0x180026be4`
- `0x180026f3c`
- `0x18002c454`
- `0x18002cbd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c589`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c589`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c576`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c576`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c4cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c5d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c62a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c4cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c5d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c62a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002c6b7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002c6b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c6f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c735`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c764`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c6f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c735`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c764`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c581`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c603`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c711`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c750`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c77f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c581`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c603`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c711`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c750`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c77f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002c553`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002c553`

## string_xrefs

- `0x18002c4a8`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`
- `0x18002c4ff`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`
- `0x18002c5a5`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`
- `0x18002c5e7`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`
- `0x18002c6db`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`

## pseudocode

```c
__int64 __fastcall PolicyTaskHelpers::TryDeleteSnapshotCaptureForLoggedInUser(_QWORD *a1, void **a2)
{
  int LoggedOnUserToken; // eax
  int v4; // ebx
  HANDLE v5; // rcx
  char *v6; // rdi
  int token_information; // eax
  void *v8; // rsi
  int v9; // eax
  const char *v10; // r9
  LPWSTR v11; // r13
  _QWORD *v12; // r15
  HLOCAL v13; // r12
  DWORD LastError; // ebx
  const WCHAR *v16; // rdx
  int value_dword; // ebx
  LSTATUS v18; // eax
  unsigned int v19; // edi
  HANDLE hObject; // [rsp+20h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+28h] [rbp-80h] BYREF
  HLOCAL hMem; // [rsp+30h] [rbp-78h] BYREF
  void *Block; // [rsp+38h] [rbp-70h] BYREF
  HLOCAL *p_hMem; // [rsp+40h] [rbp-68h]
  LPWSTR StringSid; // [rsp+48h] [rbp-60h] BYREF
  char v26; // [rsp+50h] [rbp-58h]
  LPCWSTR lpSubKey[4]; // [rsp+58h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  hMem = 0;
  hObject = 0;
  LoggedOnUserToken = PolicyTaskHelpers::TryGetLoggedOnUserToken((PolicyTaskHelpers *)&hObject, a2);
  v4 = LoggedOnUserToken;
  if ( LoggedOnUserToken < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x365,
      (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
      (const char *)(unsigned int)LoggedOnUserToken,
      (int)hObject);
    v5 = hObject;
    if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x374,
        (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
        (const char *)(unsigned int)v4,
        (int)hObject);
      if ( hMem )
        LocalFree(hMem);
      return (unsigned int)v4;
    }
LABEL_3:
    CloseHandle(v5);
    goto LABEL_19;
  }
  Block = 0;
  v6 = (char *)hObject;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, hObject);
  v4 = token_information;
  if ( token_information < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x367,
      (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
      (const char *)(unsigned int)token_information,
      (int)hObject);
    if ( Block )
      operator delete(Block);
    if ( (unsigned __int64)(v6 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      goto LABEL_19;
    v5 = v6;
    goto LABEL_3;
  }
  p_hMem = &hMem;
  StringSid = 0;
  v26 = 1;
  v8 = Block;
  v9 = ConvertSidToStringSidW(*(PSID *)Block, &StringSid);
  LODWORD(hObject) = v9;
  if ( v26 )
  {
    v11 = StringSid;
    v12 = p_hMem;
    v13 = *p_hMem;
    if ( *p_hMem )
    {
      LastError = GetLastError();
      LocalFree(v13);
      SetLastError(LastError);
      v9 = (int)hObject;
    }
    *v12 = v11;
  }
  if ( v9 )
  {
    if ( v8 )
      operator delete(v8);
    if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v6);
  }
  else
  {
    v4 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x368,
           (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
           v10);
    if ( v8 )
      operator delete(v8);
    if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v6);
    if ( v4 < 0 )
      goto LABEL_19;
  }
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  wil::str_printf<std::wstring>(lpSubKey, L"%s\\%s", hMem, a1);
  hKey = 0;
  v16 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v16 = lpSubKey[0];
  value_dword = wil::reg::open_unique_key_nothrow(HKEY_USERS, v16, &hKey);
  if ( value_dword >= 0 )
  {
    LODWORD(hObject) = 0;
    value_dword = wil::reg::get_value_dword_nothrow<unsigned long,0>(hKey, L"SnapshotCaptureActive", &hObject);
    if ( value_dword >= 0 )
    {
      v18 = RegDeleteValueW(hKey, L"SnapshotCaptureActive");
      v19 = v18;
      if ( v18 > 0 )
        v19 = (unsigned __int16)v18 | 0x80070000;
      if ( (v19 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x380,
          (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
          (const char *)v19,
          (int)hObject);
        if ( hKey )
          RegCloseKey(hKey);
        std::wstring::~wstring(lpSubKey);
        if ( hMem )
          LocalFree(hMem);
        return v19;
      }
      goto LABEL_42;
    }
  }
  if ( value_dword != -2147024894 && value_dword != -2147024893 )
  {
LABEL_42:
    if ( hKey )
      RegCloseKey(hKey);
    std::wstring::~wstring(lpSubKey);
    if ( hMem )
      LocalFree(hMem);
    return (unsigned int)value_dword;
  }
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::~wstring(lpSubKey);
  if ( hMem )
    LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x18002c454  mov     [rsp+arg_8], rbx
0x18002c459  mov     [rsp+arg_10], rsi
0x18002c45e  push    rdi
0x18002c45f  push    r12
0x18002c461  push    r13
0x18002c463  push    r14
0x18002c465  push    r15
0x18002c467  sub     rsp, 80h
0x18002c46e  mov     rax, cs:__security_cookie
0x18002c475  xor     rax, rsp
0x18002c478  mov     [rsp+0A8h+var_30], rax
0x18002c47d  mov     r14, rcx
0x18002c480  xor     r15d, r15d
0x18002c483  mov     [rsp+0A8h+hMem], r15
0x18002c488  mov     [rsp+0A8h+hObject], r15; int
0x18002c48d  lea     rcx, [rsp+0A8h+hObject]; this
0x18002c492  call    ?TryGetLoggedOnUserToken@PolicyTaskHelpers@@YAJPEAPEAX@Z; PolicyTaskHelpers::TryGetLoggedOnUserToken(void * *)
0x18002c497  mov     ebx, eax
0x18002c499  test    eax, eax
0x18002c49b  jns     short loc_18002C4D7
0x18002c49d  mov     rcx, [rsp+0A8h]; this
0x18002c4a5  mov     r9d, eax; char *
0x18002c4a8  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x18002c4af  mov     edx, 365h; void *
0x18002c4b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c4b9  mov     rcx, [rsp+0A8h+hObject]; hObject
0x18002c4be  lea     rax, [rcx-1]
0x18002c4c2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002c4c6  ja      loc_18002C5DC
0x18002c4cc  call    cs:__imp_CloseHandle
0x18002c4d2  jmp     loc_18002C5DC
0x18002c4d7  mov     [rsp+0A8h+Block], r15
0x18002c4dc  mov     rdi, [rsp+0A8h+hObject]
0x18002c4e1  mov     rdx, rdi
0x18002c4e4  lea     rcx, [rsp+0A8h+Block]
0x18002c4e9  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18002c4ee  mov     ebx, eax
0x18002c4f0  test    eax, eax
0x18002c4f2  jns     short loc_18002C532
0x18002c4f4  mov     rcx, [rsp+0A8h]; this
0x18002c4fc  mov     r9d, eax; char *
0x18002c4ff  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x18002c506  mov     edx, 367h; void *
0x18002c50b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c510  mov     rcx, [rsp+0A8h+Block]; Block
0x18002c515  test    rcx, rcx
0x18002c518  jz      short loc_18002C51F
0x18002c51a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c51f  lea     rax, [rdi-1]
0x18002c523  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002c527  ja      loc_18002C5DC
0x18002c52d  mov     rcx, rdi
0x18002c530  jmp     short loc_18002C4CC
0x18002c532  lea     rax, [rsp+0A8h+hMem]
0x18002c537  mov     [rsp+0A8h+var_68], rax
0x18002c53c  mov     [rsp+0A8h+StringSid], r15
0x18002c541  mov     [rsp+0A8h+var_58], 1
0x18002c546  lea     rdx, [rsp+0A8h+StringSid]; StringSid
0x18002c54b  mov     rsi, [rsp+0A8h+Block]
0x18002c550  mov     rcx, [rsi]; Sid
0x18002c553  call    cs:__imp_ConvertSidToStringSidW
0x18002c559  mov     dword ptr [rsp+0A8h+hObject], eax; int
0x18002c55d  cmp     [rsp+0A8h+var_58], r15b
0x18002c562  jz      short loc_18002C599
0x18002c564  mov     r13, [rsp+0A8h+StringSid]
0x18002c569  mov     r15, [rsp+0A8h+var_68]
0x18002c56e  mov     r12, [r15]
0x18002c571  test    r12, r12
0x18002c574  jz      short loc_18002C593
0x18002c576  call    cs:__imp_GetLastError
0x18002c57c  mov     ebx, eax
0x18002c57e  mov     rcx, r12; hMem
0x18002c581  call    cs:__imp_LocalFree
0x18002c587  mov     ecx, ebx; dwErrCode
0x18002c589  call    cs:__imp_SetLastError
0x18002c58f  mov     eax, dword ptr [rsp+0A8h+hObject]
0x18002c593  mov     [r15], r13
0x18002c596  xor     r15d, r15d
0x18002c599  test    eax, eax
0x18002c59b  jnz     short loc_18002C610
0x18002c59d  mov     rcx, [rsp+0A8h]; this
0x18002c5a5  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x18002c5ac  mov     edx, 368h; void *
0x18002c5b1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c5b6  mov     ebx, eax
0x18002c5b8  test    rsi, rsi
0x18002c5bb  jz      short loc_18002C5C5
0x18002c5bd  mov     rcx, rsi; Block
0x18002c5c0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c5c5  lea     rax, [rdi-1]
0x18002c5c9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002c5cd  ja      short loc_18002C5D8
0x18002c5cf  mov     rcx, rdi; hObject
0x18002c5d2  call    cs:__imp_CloseHandle
0x18002c5d8  test    ebx, ebx
0x18002c5da  jns     short loc_18002C630
0x18002c5dc  mov     rcx, [rsp+0A8h]; this
0x18002c5e4  mov     r9d, ebx; char *
0x18002c5e7  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x18002c5ee  mov     edx, 374h; void *
0x18002c5f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c5f8  nop
0x18002c5f9  mov     rcx, [rsp+0A8h+hMem]; hMem
0x18002c5fe  test    rcx, rcx
0x18002c601  jz      short loc_18002C609
0x18002c603  call    cs:__imp_LocalFree
0x18002c609  mov     eax, ebx
0x18002c60b  jmp     loc_18002C78D
0x18002c610  test    rsi, rsi
0x18002c613  jz      short loc_18002C61D
0x18002c615  mov     rcx, rsi; Block
0x18002c618  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c61d  lea     rax, [rdi-1]
0x18002c621  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002c625  ja      short loc_18002C630
0x18002c627  mov     rcx, rdi; hObject
0x18002c62a  call    cs:__imp_CloseHandle
0x18002c630  cmp     qword ptr [r14+18h], 7
0x18002c635  jbe     short loc_18002C63A
0x18002c637  mov     r14, [r14]
0x18002c63a  mov     r9, r14
0x18002c63d  mov     r8, [rsp+0A8h+hMem]
0x18002c642  lea     rdx, aSS; "%s\\%s"
0x18002c649  lea     rcx, [rsp+0A8h+lpSubKey]
0x18002c64e  call    ??$str_printf@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; wil::str_printf<std::wstring>(ushort const *,...)
0x18002c653  mov     [rsp+0A8h+hKey], r15
0x18002c658  lea     rdx, [rsp+0A8h+lpSubKey]
0x18002c65d  cmp     [rsp+0A8h+var_38], 7
0x18002c663  cmova   rdx, [rsp+0A8h+lpSubKey]; lpSubKey
0x18002c669  mov     r9d, 1
0x18002c66f  lea     r8, [rsp+0A8h+hKey]; phkResult
0x18002c674  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18002c67b  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18002c680  mov     ebx, eax
0x18002c682  test    eax, eax
0x18002c684  js      loc_18002C71B
0x18002c68a  mov     dword ptr [rsp+0A8h+hObject], r15d; int
0x18002c68f  lea     r8, [rsp+0A8h+hObject]
0x18002c694  lea     rdx, aSnapshotcaptur; "SnapshotCaptureActive"
0x18002c69b  mov     rcx, [rsp+0A8h+hKey]
0x18002c6a0  call    ??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBGPEAK@Z; wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ulong *)
0x18002c6a5  mov     ebx, eax
0x18002c6a7  test    eax, eax
0x18002c6a9  js      short loc_18002C71B
0x18002c6ab  lea     rdx, aSnapshotcaptur; "SnapshotCaptureActive"
0x18002c6b2  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18002c6b7  call    cs:__imp_RegDeleteValueW
0x18002c6bd  mov     edi, eax
0x18002c6bf  test    eax, eax
0x18002c6c1  jle     short loc_18002C6CC
0x18002c6c3  movzx   edi, ax
0x18002c6c6  or      edi, 80070000h
0x18002c6cc  test    edi, edi
0x18002c6ce  jns     short loc_18002C72B
0x18002c6d0  mov     rcx, [rsp+0A8h]; this
0x18002c6d8  mov     r9d, edi; char *
0x18002c6db  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x18002c6e2  mov     edx, 380h; void *
0x18002c6e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c6ec  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18002c6f1  test    rcx, rcx
0x18002c6f4  jz      short loc_18002C6FC
0x18002c6f6  call    cs:__imp_RegCloseKey
0x18002c6fc  lea     rcx, [rsp+0A8h+lpSubKey]
0x18002c701  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c706  nop
0x18002c707  mov     rcx, [rsp+0A8h+hMem]; hMem
0x18002c70c  test    rcx, rcx
0x18002c70f  jz      short loc_18002C717
0x18002c711  call    cs:__imp_LocalFree
0x18002c717  mov     eax, edi
0x18002c719  jmp     short loc_18002C78D
0x18002c71b  cmp     ebx, 80070002h
0x18002c721  jz      short loc_18002C75A
0x18002c723  cmp     ebx, 80070003h
0x18002c729  jz      short loc_18002C75A
0x18002c72b  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18002c730  test    rcx, rcx
0x18002c733  jz      short loc_18002C73B
0x18002c735  call    cs:__imp_RegCloseKey
0x18002c73b  lea     rcx, [rsp+0A8h+lpSubKey]
0x18002c740  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c745  nop
0x18002c746  mov     rcx, [rsp+0A8h+hMem]; hMem
0x18002c74b  test    rcx, rcx
0x18002c74e  jz      short loc_18002C756
0x18002c750  call    cs:__imp_LocalFree
0x18002c756  mov     eax, ebx
0x18002c758  jmp     short loc_18002C78D
0x18002c75a  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18002c75f  test    rcx, rcx
0x18002c762  jz      short loc_18002C76A
0x18002c764  call    cs:__imp_RegCloseKey
0x18002c76a  lea     rcx, [rsp+0A8h+lpSubKey]
0x18002c76f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c774  nop
0x18002c775  mov     rcx, [rsp+0A8h+hMem]; hMem
0x18002c77a  test    rcx, rcx
0x18002c77d  jz      short loc_18002C785
0x18002c77f  call    cs:__imp_LocalFree
0x18002c785  xor     eax, eax
0x18002c787  jmp     short loc_18002C78D
0x18002c789  mov     eax, dword ptr [rsp+0A8h+hObject]
0x18002c78d  mov     rcx, [rsp+0A8h+var_30]
0x18002c792  xor     rcx, rsp; StackCookie
0x18002c795  call    __security_check_cookie
0x18002c79a  lea     r11, [rsp+0A8h+var_28]
0x18002c7a2  mov     rbx, [r11+38h]
0x18002c7a6  mov     rsi, [r11+40h]
0x18002c7aa  mov     rsp, r11
0x18002c7ad  pop     r15
0x18002c7af  pop     r14
0x18002c7b1  pop     r13
0x18002c7b3  pop     r12
0x18002c7b5  pop     rdi
0x18002c7b6  retn
```
