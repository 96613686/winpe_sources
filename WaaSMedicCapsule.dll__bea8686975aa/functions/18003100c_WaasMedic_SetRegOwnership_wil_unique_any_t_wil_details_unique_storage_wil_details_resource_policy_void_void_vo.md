# WaasMedic::SetRegOwnership(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18003100c`
- end: `0x18003121b`
- name: `?SetRegOwnership@WaasMedic@@YAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180031224`

## callees

- `0x180009a54`
- `0x18000b308`
- `0x18002543c`
- `0x18002c284`
- `0x18003100c`
- `0x180032408`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031080`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800310cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800311c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031080`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800310cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800311c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800310e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800310e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800310a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800311eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800310a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800311eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003110e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003110e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800310b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800310d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800311fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800310b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800310d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800311fa`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180031070`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800311b3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180031070`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800311b3`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180031184`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180031184`

## string_xrefs

- `0x18003102e`: `SeTakeOwnershipPrivilege`
- `0x180031056`: `onecore\enduser\waasmedic\lib\util\securityutil.cpp`
- `0x180031147`: `onecore\enduser\waasmedic\lib\util\securityutil.cpp`
- `0x180031192`: `onecore\enduser\waasmedic\lib\util\securityutil.cpp`
- `0x18003113b`: `Failed to open reg key for %ws.`
- `0x180031086`: `Failed to revert the thread token: 0%x08X`
- `0x1800311c9`: `Failed to revert the thread token: 0%x08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::SetRegOwnership(PSID *a1, HKEY *a2, const WCHAR *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  DWORD LastError; // eax
  HKEY v10; // rsi
  DWORD v11; // ebx
  bool v12; // cc
  const WCHAR *v13; // rdx
  LSTATUS v14; // eax
  DWORD v15; // eax
  DWORD v16; // eax
  int phkResult; // [rsp+20h] [rbp-30h]
  unsigned int phkResulta; // [rsp+20h] [rbp-30h]
  HANDLE hObject[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  HKEY hKey; // [rsp+98h] [rbp+48h] BYREF

  hKey = 0;
  *(_OWORD *)hObject = 0;
  v6 = WaasMedic::CAutoThreadPrivilegeHelper::EnablePrivilege(
         (WaasMedic::CAutoThreadPrivilegeHelper *)hObject,
         L"SeTakeOwnershipPrivilege");
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44A,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securityutil.cpp",
      (const char *)(unsigned int)v6,
      phkResult);
LABEL_3:
    if ( LOBYTE(hObject[1]) )
    {
      if ( RevertToSelf() )
      {
        LOBYTE(hObject[1]) = 0;
      }
      else
      {
        LastError = GetLastError();
        LogLevelW(2u, L"Failed to revert the thread token: 0%x08X", LastError);
      }
    }
    if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject[0]);
    if ( hKey )
      RegCloseKey(hKey);
    return v7;
  }
  v10 = hKey;
  if ( hKey )
  {
    v11 = GetLastError();
    RegCloseKey(v10);
    SetLastError(v11);
  }
  v12 = *((_QWORD *)a3 + 3) <= 7u;
  hKey = 0;
  if ( v12 )
    v13 = a3;
  else
    v13 = *(const WCHAR **)a3;
  v14 = RegOpenKeyExW(*a2, v13, 0, 0x80000u, &hKey);
  v7 = v14;
  if ( v14 )
  {
    if ( v14 > 0 )
      v7 = (unsigned __int16)v14 | 0x80070000;
    if ( (v7 & 0x80000000) != 0 )
    {
      if ( *((_QWORD *)a3 + 3) > 7u )
        a3 = *(const WCHAR **)a3;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x453,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securityutil.cpp",
        (const char *)v7,
        (int)"Failed to open reg key for %ws.",
        (const char *)a3);
    }
    goto LABEL_3;
  }
  v15 = SetSecurityInfo(hKey, SE_REGISTRY_KEY, 1u, *a1, 0, 0, 0);
  if ( v15 )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x45D,
           (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\securityutil.cpp",
           (const char *)v15,
           phkResulta);
    goto LABEL_3;
  }
  if ( LOBYTE(hObject[1]) )
  {
    if ( RevertToSelf() )
    {
      LOBYTE(hObject[1]) = 0;
    }
    else
    {
      v16 = GetLastError();
      LogLevelW(2u, L"Failed to revert the thread token: 0%x08X", v16);
    }
  }
  if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hObject[0]);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18003100c  mov     [rsp-28h+arg_0], rbx
0x180031011  mov     [rsp-28h+arg_8], rsi
0x180031016  push    rbp
0x180031017  push    rdi
0x180031018  push    r12
0x18003101a  push    r14
0x18003101c  push    r15
0x18003101e  mov     rbp, rsp
0x180031021  sub     rsp, 50h
0x180031025  mov     r15, rdx
0x180031028  mov     r14, rcx
0x18003102b  xorps   xmm0, xmm0
0x18003102e  lea     rdx, aSetakeownershi; "SeTakeOwnershipPrivilege"
0x180031035  xor     r12d, r12d
0x180031038  lea     rcx, [rbp+hObject]; this
0x18003103c  mov     [rbp+hKey], r12
0x180031040  mov     rdi, r8
0x180031043  movups  xmmword ptr [rbp+hObject], xmm0
0x180031047  call    ?EnablePrivilege@CAutoThreadPrivilegeHelper@WaasMedic@@QEAAJPEBG@Z; WaasMedic::CAutoThreadPrivilegeHelper::EnablePrivilege(ushort const *)
0x18003104c  mov     ebx, eax
0x18003104e  test    eax, eax
0x180031050  jns     short loc_1800310C4
0x180031052  mov     rcx, [rbp+28h]; this
0x180031056  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18003105d  mov     r9d, eax; char *
0x180031060  mov     edx, 44Ah; void *
0x180031065  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003106a  cmp     byte ptr [rbp+hObject+8], r12b
0x18003106e  jz      short loc_18003109A
0x180031070  call    cs:__imp_RevertToSelf
0x180031076  test    eax, eax
0x180031078  jz      short loc_180031080
0x18003107a  mov     byte ptr [rbp+hObject+8], r12b
0x18003107e  jmp     short loc_18003109A
0x180031080  call    cs:__imp_GetLastError
0x180031086  lea     rdx, aFailedToRevert; "Failed to revert the thread token: 0%x0"...
0x18003108d  mov     ecx, 2; unsigned __int8
0x180031092  mov     r8d, eax
0x180031095  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003109a  mov     rcx, [rbp+hObject]; hObject
0x18003109e  lea     rax, [rcx-1]
0x1800310a2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800310a6  ja      short loc_1800310AE
0x1800310a8  call    cs:__imp_CloseHandle
0x1800310ae  mov     rcx, [rbp+hKey]; hKey
0x1800310b2  test    rcx, rcx
0x1800310b5  jz      short loc_1800310BD
0x1800310b7  call    cs:__imp_RegCloseKey
0x1800310bd  mov     eax, ebx
0x1800310bf  jmp     loc_180031202
0x1800310c4  mov     rsi, [rbp+hKey]
0x1800310c8  test    rsi, rsi
0x1800310cb  jz      short loc_1800310E6
0x1800310cd  call    cs:__imp_GetLastError
0x1800310d3  mov     rcx, rsi; hKey
0x1800310d6  mov     ebx, eax
0x1800310d8  call    cs:__imp_RegCloseKey
0x1800310de  mov     ecx, ebx; dwErrCode
0x1800310e0  call    cs:__imp_SetLastError
0x1800310e6  cmp     qword ptr [rdi+18h], 7
0x1800310eb  mov     [rbp+hKey], r12
0x1800310ef  jbe     short loc_1800310F6
0x1800310f1  mov     rdx, [rdi]
0x1800310f4  jmp     short loc_1800310F9
0x1800310f6  mov     rdx, rdi; lpSubKey
0x1800310f9  mov     rcx, [r15]; hKey
0x1800310fc  lea     rax, [rbp+hKey]
0x180031100  mov     r9d, 80000h; samDesired
0x180031106  mov     [rsp+50h+phkResult], rax; phkResult
0x18003110b  xor     r8d, r8d; ulOptions
0x18003110e  call    cs:__imp_RegOpenKeyExW
0x180031114  mov     ebx, eax
0x180031116  test    eax, eax
0x180031118  jz      short loc_180031165
0x18003111a  jle     short loc_180031125
0x18003111c  movzx   ebx, ax
0x18003111f  or      ebx, 80070000h
0x180031125  test    ebx, ebx
0x180031127  jns     loc_18003106A
0x18003112d  cmp     qword ptr [rdi+18h], 7
0x180031132  jbe     short loc_180031137
0x180031134  mov     rdi, [rdi]
0x180031137  mov     rcx, [rbp+28h]; this
0x18003113b  lea     rax, aFailedToOpenRe_0; "Failed to open reg key for %ws."
0x180031142  mov     [rsp+50h+pDacl], rdi; char *
0x180031147  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18003114e  mov     r9d, ebx; char *
0x180031151  mov     [rsp+50h+phkResult], rax; int
0x180031156  mov     edx, 453h; void *
0x18003115b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180031160  jmp     loc_18003106A
0x180031165  mov     r9, [r14]; psidOwner
0x180031168  mov     edx, 4; ObjectType
0x18003116d  mov     rcx, [rbp+hKey]; handle
0x180031171  mov     [rsp+50h+pSacl], r12; pSacl
0x180031176  mov     [rsp+50h+pDacl], r12; pDacl
0x18003117b  lea     r8d, [rdx-3]; SecurityInfo
0x18003117f  mov     [rsp+50h+phkResult], r12; unsigned int
0x180031184  call    cs:__imp_SetSecurityInfo
0x18003118a  test    eax, eax
0x18003118c  jz      short loc_1800311AD
0x18003118e  mov     rcx, [rbp+28h]; this
0x180031192  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180031199  mov     r9d, eax; char *
0x18003119c  mov     edx, 45Dh; void *
0x1800311a1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800311a6  mov     ebx, eax
0x1800311a8  jmp     loc_18003106A
0x1800311ad  cmp     byte ptr [rbp+hObject+8], r12b
0x1800311b1  jz      short loc_1800311DD
0x1800311b3  call    cs:__imp_RevertToSelf
0x1800311b9  test    eax, eax
0x1800311bb  jz      short loc_1800311C3
0x1800311bd  mov     byte ptr [rbp+hObject+8], r12b
0x1800311c1  jmp     short loc_1800311DD
0x1800311c3  call    cs:__imp_GetLastError
0x1800311c9  lea     rdx, aFailedToRevert; "Failed to revert the thread token: 0%x0"...
0x1800311d0  mov     ecx, 2; unsigned __int8
0x1800311d5  mov     r8d, eax
0x1800311d8  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800311dd  mov     rcx, [rbp+hObject]; hObject
0x1800311e1  lea     rax, [rcx-1]
0x1800311e5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800311e9  ja      short loc_1800311F1
0x1800311eb  call    cs:__imp_CloseHandle
0x1800311f1  mov     rcx, [rbp+hKey]; hKey
0x1800311f5  test    rcx, rcx
0x1800311f8  jz      short loc_180031200
0x1800311fa  call    cs:__imp_RegCloseKey
0x180031200  xor     eax, eax
0x180031202  lea     r11, [rsp+50h+var_s0]
0x180031207  mov     rbx, [r11+30h]
0x18003120b  mov     rsi, [r11+38h]
0x18003120f  mov     rsp, r11
0x180031212  pop     r15
0x180031214  pop     r14
0x180031216  pop     r12
0x180031218  pop     rdi
0x180031219  pop     rbp
0x18003121a  retn
```
