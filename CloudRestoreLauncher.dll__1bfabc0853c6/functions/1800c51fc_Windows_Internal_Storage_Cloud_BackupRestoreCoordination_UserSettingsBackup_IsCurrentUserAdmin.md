# Windows::Internal::Storage::Cloud::BackupRestoreCoordination::UserSettingsBackup::IsCurrentUserAdmin

- ea: `0x1800c51fc`
- end: `0x1800c52e8`
- name: `Windows::Internal::Storage::Cloud::BackupRestoreCoordination::UserSettingsBackup::IsCurrentUserAdmin`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800c57e0`

## callees

- `0x18000c6e0`
- `0x18008cedc`
- `0x1800b456c`
- `0x1800b4684`
- `0x1800c51fc`

## import_xrefs

- `ADVAPI32!CheckTokenMembership` at `0x1800c5292`
- `ADVAPI32!CheckTokenMembership` at `0x1800c5292`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800c5270`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800c5270`

## string_xrefs

- `0x1800c52a8`: `pcshell\shell\cloudrestorelauncher\cloudbackuprestore\manifestdrivenbackuprestorehandler.cpp`

## pseudocode

```c
bool Windows::Internal::Storage::Cloud::BackupRestoreCoordination::UserSettingsBackup::IsCurrentUserAdmin()
{
  BOOL v0; // ebx
  const char *v1; // r9
  bool v2; // bl
  WINBOOL IsMember; // [rsp+68h] [rbp+17h] BYREF
  PSID SidToCheck; // [rsp+70h] [rbp+1Fh] BYREF
  PSID *p_SidToCheck; // [rsp+78h] [rbp+27h] BYREF
  PSID v7; // [rsp+80h] [rbp+2Fh] BYREF
  char v8; // [rsp+88h] [rbp+37h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp+3Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B0h] [rbp+5Fh]

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  p_SidToCheck = &SidToCheck;
  SidToCheck = 0;
  v7 = 0;
  v8 = 1;
  v0 = AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v7);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_SidToCheck);
  if ( v0 && (IsMember = 0, CheckTokenMembership(0, SidToCheck, &IsMember)) )
  {
    v2 = IsMember != 0;
  }
  else
  {
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x120,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\manifestdrivenbackuprestorehandler.cpp",
      v1);
    v2 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&SidToCheck);
  return v2;
}

```

## disassembly

```asm
0x1800c51fc  mov     r11, rsp
0x1800c51ff  mov     [r11+8], rbx
0x1800c5203  mov     [r11+10h], rdi
0x1800c5207  push    rbp
0x1800c5208  lea     rbp, [r11-5Fh]
0x1800c520c  sub     rsp, 0A0h
0x1800c5213  mov     rax, cs:__security_cookie
0x1800c521a  xor     rax, rsp
0x1800c521d  mov     [rbp+57h+var_10], rax
0x1800c5221  xor     edi, edi
0x1800c5223  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800c5229  lea     rax, [rbp+57h+SidToCheck]
0x1800c522d  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x1800c5230  mov     [rbp+57h+var_30], rax
0x1800c5234  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800c5238  lea     rax, [rbp+57h+var_28]
0x1800c523c  mov     [rbp+57h+SidToCheck], rdi
0x1800c5240  mov     [r11-58h], rax
0x1800c5244  lea     r8d, [rdi+20h]; nSubAuthority0
0x1800c5248  mov     [rsp+0A0h+nSubAuthority7], edi; nSubAuthority7
0x1800c524c  mov     r9d, 220h; nSubAuthority1
0x1800c5252  mov     [rsp+0A0h+nSubAuthority6], edi; nSubAuthority6
0x1800c5256  mov     dl, 2; nSubAuthorityCount
0x1800c5258  mov     [rsp+0A0h+nSubAuthority5], edi; nSubAuthority5
0x1800c525c  mov     [rsp+0A0h+nSubAuthority4], edi; nSubAuthority4
0x1800c5260  mov     [rsp+0A0h+nSubAuthority3], edi; nSubAuthority3
0x1800c5264  mov     [rsp+0A0h+nSubAuthority2], edi; nSubAuthority2
0x1800c5268  mov     [rbp+57h+var_28], rdi
0x1800c526c  mov     [rbp+57h+var_20], 1
0x1800c5270  call    cs:__imp_AllocateAndInitializeSid
0x1800c5276  lea     rcx, [rbp+57h+var_30]
0x1800c527a  mov     ebx, eax
0x1800c527c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x1800c5281  test    ebx, ebx
0x1800c5283  jz      short loc_1800C52A4
0x1800c5285  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x1800c5289  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800c528d  xor     ecx, ecx; TokenHandle
0x1800c528f  mov     [rbp+57h+IsMember], edi
0x1800c5292  call    cs:__imp_CheckTokenMembership
0x1800c5298  test    eax, eax
0x1800c529a  jz      short loc_1800C52A4
0x1800c529c  cmp     [rbp+57h+IsMember], edi
0x1800c529f  setnz   bl
0x1800c52a2  jmp     short loc_1800C52BC
0x1800c52a4  mov     rcx, [rbp+5Fh]; this
0x1800c52a8  lea     r8, aPcshellShellCl_3; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800c52af  mov     edx, 120h; void *
0x1800c52b4  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800c52b9  mov     bl, dil
0x1800c52bc  lea     rcx, [rbp+57h+SidToCheck]
0x1800c52c0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800c52c5  mov     al, bl
0x1800c52c7  mov     rcx, [rbp+57h+var_10]
0x1800c52cb  xor     rcx, rsp; StackCookie
0x1800c52ce  call    __security_check_cookie
0x1800c52d3  lea     r11, [rsp+0A0h+var_s0]
0x1800c52db  mov     rbx, [r11+10h]
0x1800c52df  mov     rdi, [r11+18h]
0x1800c52e3  mov     rsp, r11
0x1800c52e6  pop     rbp
0x1800c52e7  retn
```
