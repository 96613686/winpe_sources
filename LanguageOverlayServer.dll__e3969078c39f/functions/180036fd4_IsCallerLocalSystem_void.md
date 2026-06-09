# IsCallerLocalSystem(void)

- ea: `0x180036fd4`
- end: `0x18003712b`
- name: `?IsCallerLocalSystem@@YA_NXZ`
- size: `343`
- prototype: `char(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180024788`
- `0x180031a2c`
- `0x180042460`

## callees

- `0x180003a00`
- `0x180011318`
- `0x180012a98`
- `0x1800362a0`
- `0x180036fd4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800370a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800370a6`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180037086`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180037086`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003700e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003700e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800370ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800370ca`

## string_xrefs

- `0x1800370f5`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x180037107`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x180037119`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char IsCallerLocalSystem(void)
{
  const char *v0; // r9
  HANDLE *CallerTokenHandleForIdentification; // rax
  const char *v2; // r9
  char v3; // bl
  int PrivilegeSet; // [rsp+20h] [rbp-19h]
  HANDLE hObject; // [rsp+40h] [rbp+7h] BYREF
  WINBOOL AccessStatus; // [rsp+48h] [rbp+Fh] BYREF
  DWORD GrantedAccess; // [rsp+4Ch] [rbp+13h] BYREF
  DWORD PrivilegeSetLength; // [rsp+50h] [rbp+17h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp+1Fh] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+60h] [rbp+27h] BYREF
  struct _PRIVILEGE_SET v12; // [rsp+70h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"O:SYG:SYD:(A;;0x3;;;SY)", 1u, &SecurityDescriptor, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x193,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
      v0);
  *(_QWORD *)&GenericMapping.GenericRead = 0;
  *(_QWORD *)&GenericMapping.GenericExecute = 3;
  memset(&v12, 0, sizeof(v12));
  PrivilegeSetLength = 20;
  GrantedAccess = 0;
  AccessStatus = 0;
  CallerTokenHandleForIdentification = (HANDLE *)GetCallerTokenHandleForIdentification((__int64)&hObject);
  if ( !AccessCheck(
          SecurityDescriptor,
          *CallerTokenHandleForIdentification,
          3u,
          &GenericMapping,
          &v12,
          &PrivilegeSetLength,
          &GrantedAccess,
          &AccessStatus) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1A8,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
      v2);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  if ( !AccessStatus )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1AA,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
      (const char *)0x80070005LL,
      PrivilegeSet);
  v3 = GrantedAccess & 1;
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v3;
}

```

## disassembly

```asm
0x180036fd4  mov     [rsp-8+arg_0], rbx
0x180036fd9  push    rbp
0x180036fda  lea     rbp, [rsp-57h]
0x180036fdf  sub     rsp, 90h
0x180036fe6  mov     rax, cs:__security_cookie
0x180036fed  xor     rax, rsp
0x180036ff0  mov     [rbp+57h+var_8], rax
0x180036ff4  mov     [rbp+57h+SecurityDescriptor], 0
0x180036ffc  xor     r9d, r9d; SecurityDescriptorSize
0x180036fff  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180037003  lea     edx, [r9+1]; StringSDRevision
0x180037007  lea     rcx, StringSecurityDescriptor; "O:SYG:SYD:(A;;0x3;;;SY)"
0x18003700e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180037014  mov     rcx, [rbp+5Fh]; this
0x180037018  test    eax, eax
0x18003701a  jz      loc_180037107
0x180037020  mov     qword ptr [rbp+57h+GenericMapping.GenericRead], 0
0x180037028  mov     ebx, 3
0x18003702d  mov     qword ptr [rbp+57h+GenericMapping.GenericExecute], rbx
0x180037031  xorps   xmm0, xmm0
0x180037034  xor     eax, eax
0x180037036  movups  xmmword ptr [rbp+57h+var_20.PrivilegeCount], xmm0
0x18003703a  mov     [rbp+57h+var_20.Privilege.Attributes], eax
0x18003703d  mov     [rbp+57h+var_40], 14h
0x180037044  mov     [rbp+57h+var_44], eax
0x180037047  mov     [rbp+57h+var_48], eax
0x18003704a  lea     rcx, [rbp+57h+hObject]
0x18003704e  call    ?GetCallerTokenHandleForIdentification@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; GetCallerTokenHandleForIdentification(void)
0x180037053  nop
0x180037054  lea     rcx, [rbp+57h+var_48]
0x180037058  mov     [rsp+90h+AccessStatus], rcx; AccessStatus
0x18003705d  lea     rcx, [rbp+57h+var_44]
0x180037061  mov     [rsp+90h+GrantedAccess], rcx; GrantedAccess
0x180037066  lea     rcx, [rbp+57h+var_40]
0x18003706a  mov     [rsp+90h+PrivilegeSetLength], rcx; PrivilegeSetLength
0x18003706f  lea     rcx, [rbp+57h+var_20]
0x180037073  mov     [rsp+90h+PrivilegeSet], rcx; int
0x180037078  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18003707c  mov     r8d, ebx; DesiredAccess
0x18003707f  mov     rdx, [rax]; ClientToken
0x180037082  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x180037086  call    cs:__imp_AccessCheck
0x18003708c  mov     rcx, [rbp+5Fh]; this
0x180037090  test    eax, eax
0x180037092  jz      loc_180037119
0x180037098  mov     rcx, [rbp+57h+hObject]; hObject
0x18003709c  lea     rax, [rcx-1]
0x1800370a0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800370a4  ja      short loc_1800370AC
0x1800370a6  call    cs:__imp_CloseHandle
0x1800370ac  cmp     [rbp+57h+var_48], 0
0x1800370b0  setz    al
0x1800370b3  mov     rcx, [rbp+5Fh]; this
0x1800370b7  test    al, al
0x1800370b9  jnz     short loc_1800370EF
0x1800370bb  mov     bl, byte ptr [rbp+57h+var_44]
0x1800370be  and     bl, 1
0x1800370c1  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x1800370c5  test    rcx, rcx
0x1800370c8  jz      short loc_1800370D0
0x1800370ca  call    cs:__imp_LocalFree
0x1800370d0  mov     al, bl
0x1800370d2  mov     rcx, [rbp+57h+var_8]
0x1800370d6  xor     rcx, rsp; StackCookie
0x1800370d9  call    __security_check_cookie
0x1800370de  mov     rbx, [rsp+90h+arg_0]
0x1800370e6  add     rsp, 90h
0x1800370ed  pop     rbp
0x1800370ee  retn
0x1800370ef  mov     r9d, 80070005h; char *
0x1800370f5  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x1800370fc  mov     edx, 1AAh; void *
0x180037101  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180037107  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x18003710e  mov     edx, 193h; void *
0x180037113  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180037119  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180037120  mov     edx, 1A8h; void *
0x180037125  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
