# TrustLabelAceHelpers::IsTrustLabelPresentOnReparsePoint(ushort const *,bool *)

- ea: `0x180009020`
- end: `0x1800092e0`
- name: `?IsTrustLabelPresentOnReparsePoint@TrustLabelAceHelpers@@SAJPEBGPEA_N@Z`
- size: `704`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180028aa4`

## callees

- `0x180007c78`
- `0x180009020`
- `0x18000f8b0`
- `0x180018150`
- `0x1800181cc`
- `0x180018280`
- `0x18001bd43`
- `0x180042950`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009279`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009279`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800091a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000924b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800091a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000924b`
- `ntdll!RtlEqualSid` at `0x18000922f`
- `ntdll!RtlEqualSid` at `0x18000922f`
- `ntdll!RtlFindAceByType` at `0x180009207`
- `ntdll!RtlFindAceByType` at `0x180009207`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800090ce`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800090ce`
- `ntdll!RtlFreeSid` at `0x18000911c`
- `ntdll!RtlFreeSid` at `0x1800091dc`
- `ntdll!RtlFreeSid` at `0x180009260`
- `ntdll!RtlFreeSid` at `0x18000911c`
- `ntdll!RtlFreeSid` at `0x1800091dc`
- `ntdll!RtlFreeSid` at `0x180009260`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180009174`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180009174`

## pseudocode

```c
__int64 __fastcall TrustLabelAceHelpers::IsTrustLabelPresentOnReparsePoint(const unsigned __int16 *a1, bool *a2)
{
  char *FileW_0; // rbx
  const char *v4; // r9
  NTSTATUS v5; // eax
  int v6; // eax
  unsigned int v7; // edi
  PSID v8; // rdi
  DWORD SecurityInfo; // eax
  __int64 AceByType; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-29h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-29h]
  unsigned int dwCreationDispositionb; // [rsp+20h] [rbp-29h]
  int dwCreationDispositionc; // [rsp+20h] [rbp-29h]
  PSID Sid1; // [rsp+60h] [rbp+17h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+68h] [rbp+1Fh] BYREF
  PACL ppSacl; // [rsp+70h] [rbp+27h] BYREF
  char *v19; // [rsp+78h] [rbp+2Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+80h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  FileW_0 = (char *)CreateFileW_0(a1, 0x20000u, 0, 0, 3u, 0x2200000u, 0);
  v19 = FileW_0;
  if ( (unsigned __int64)(FileW_0 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return (unsigned int)wil::details::in1diag3::Return_GetLastError(
                           retaddr,
                           (void *)0x88,
                           (unsigned int)"onecore\\base\\appmodel\\trust\\trustlabelhelpersbase.cpp",
                           v4);
  Sid1 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 4864;
  v5 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x200u, 0x1000u, 0, 0, 0, 0, 0, 0, &Sid1);
  if ( v5 < 0 )
  {
    v6 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x4B,
           (unsigned int)"onecore\\base\\appmodel\\trust\\trustlabelhelpersbase.cpp",
           (const char *)(unsigned int)v5,
           dwCreationDisposition);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"onecore\\base\\appmodel\\trust\\trustlabelhelpersbase.cpp",
        (const char *)(unsigned int)v6,
        dwCreationDispositiona);
      if ( Sid1 )
        RtlFreeSid(Sid1);
      if ( (unsigned __int64)(FileW_0 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(FileW_0);
      return v7;
    }
  }
  v8 = Sid1;
  *a2 = 0;
  ppSacl = 0;
  ppSecurityDescriptor = 0;
  SecurityInfo = GetSecurityInfo(FileW_0, SE_FILE_OBJECT, 0x80u, 0, 0, 0, &ppSacl, &ppSecurityDescriptor);
  if ( SecurityInfo )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x24,
           (unsigned int)"onecore\\base\\appmodel\\trust\\trustlabelhelpersbase.cpp",
           (const char *)SecurityInfo,
           dwCreationDispositionb);
    if ( ppSecurityDescriptor )
      LocalFree(ppSecurityDescriptor);
    if ( (v7 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecore\\base\\appmodel\\trust\\trustlabelhelpersbase.cpp",
        (const char *)v7,
        dwCreationDispositionc);
      if ( Sid1 )
        RtlFreeSid(Sid1);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
      return v7;
    }
  }
  else
  {
    *(_DWORD *)IdentifierAuthority.Value = 0;
    while ( 1 )
    {
      AceByType = RtlFindAceByType(ppSacl, 20, &IdentifierAuthority);
      if ( AceByType )
      {
        if ( (*(_BYTE *)(AceByType + 1) & 8) == 0 )
          break;
      }
      ++*(_DWORD *)IdentifierAuthority.Value;
      if ( !AceByType )
        goto LABEL_22;
    }
    if ( RtlEqualSid(v8, (PSID)(AceByType + 8)) )
      *a2 = 1;
LABEL_22:
    if ( ppSecurityDescriptor )
      LocalFree(ppSecurityDescriptor);
  }
  if ( Sid1 )
    RtlFreeSid(Sid1);
  if ( (unsigned __int64)(FileW_0 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW_0);
  return 0;
}

```

## disassembly

```asm
0x180009020  mov     [rsp-8+arg_10], rbx
0x180009025  mov     [rsp-8+arg_18], rsi
0x18000902a  push    rbp
0x18000902b  push    rdi
0x18000902c  push    r14
0x18000902e  lea     rbp, [rsp-47h]
0x180009033  sub     rsp, 90h
0x18000903a  mov     rax, cs:__security_cookie
0x180009041  xor     rax, rsp
0x180009044  mov     [rbp+57h+var_18], rax
0x180009048  mov     rsi, rdx
0x18000904b  xor     r14d, r14d
0x18000904e  mov     [rsp+0A0h+hTemplateFile], r14; hTemplateFile
0x180009053  xor     r9d, r9d; lpSecurityAttributes
0x180009056  mov     [rsp+0A0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18000905e  xor     r8d, r8d; dwShareMode
0x180009061  mov     edx, 20000h; dwDesiredAccess
0x180009066  mov     [rsp+0A0h+dwCreationDisposition], 3; dwCreationDisposition
0x18000906e  call    CreateFileW_0
0x180009073  mov     rbx, rax
0x180009076  mov     [rbp+57h+var_28], rax
0x18000907a  dec     rax
0x18000907d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009081  ja      loc_180009289
0x180009087  lea     rax, [rbp+57h+Sid1]
0x18000908b  mov     [rbp+57h+Sid1], r14
0x18000908f  mov     [rsp+0A0h+Sid], rax; Sid
0x180009094  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x180009098  mov     [rsp+0A0h+SubAuthority7], r14d; SubAuthority7
0x18000909d  mov     r9d, 1000h; SubAuthority1
0x1800090a3  mov     [rsp+0A0h+SubAuthority6], r14d; SubAuthority6
0x1800090a8  mov     r8d, 200h; SubAuthority0
0x1800090ae  mov     [rsp+0A0h+SubAuthority5], r14d; SubAuthority5
0x1800090b3  mov     dl, 2; SubAuthorityCount
0x1800090b5  mov     dword ptr [rsp+0A0h+hTemplateFile], r14d; SubAuthority4
0x1800090ba  mov     [rsp+0A0h+dwFlagsAndAttributes], r14d; SubAuthority3
0x1800090bf  mov     [rsp+0A0h+dwCreationDisposition], r14d; int
0x1800090c4  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r14d
0x1800090c8  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 1300h
0x1800090ce  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800090d5  nop     dword ptr [rax+rax+00h]
0x1800090da  test    eax, eax
0x1800090dc  jns     short loc_18000913B
0x1800090de  mov     rcx, [rbp+5Fh]; this
0x1800090e2  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\trust\\trustla"...
0x1800090e9  mov     r9d, eax; char *
0x1800090ec  lea     edx, [r14+4Bh]; void *
0x1800090f0  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800090f5  mov     edi, eax
0x1800090f7  test    eax, eax
0x1800090f9  jns     short loc_18000913B
0x1800090fb  mov     rcx, [rbp+5Fh]; this
0x1800090ff  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\trust\\trustla"...
0x180009106  mov     r9d, eax; char *
0x180009109  mov     edx, 8Bh; void *
0x18000910e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009113  mov     rcx, [rbp+57h+Sid1]; Sid
0x180009117  test    rcx, rcx
0x18000911a  jz      short loc_180009128
0x18000911c  call    cs:__imp_RtlFreeSid
0x180009123  nop     dword ptr [rax+rax+00h]
0x180009128  lea     rax, [rbx-1]
0x18000912c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009130  jbe     loc_1800092AA
0x180009136  jmp     loc_1800092B9
0x18000913b  mov     rdi, [rbp+57h+Sid1]
0x18000913f  lea     rax, [rbp+57h+ppSecurityDescriptor]
0x180009143  mov     qword ptr [rsp+0A0h+SubAuthority5], rax; ppSecurityDescriptor
0x180009148  xor     r9d, r9d; ppsidOwner
0x18000914b  lea     rax, [rbp+57h+ppSacl]
0x18000914f  mov     [rsi], r14b
0x180009152  mov     [rsp+0A0h+hTemplateFile], rax; ppSacl
0x180009157  mov     rcx, rbx; handle
0x18000915a  mov     qword ptr [rsp+0A0h+dwFlagsAndAttributes], r14; ppDacl
0x18000915f  lea     edx, [r9+1]; ObjectType
0x180009163  mov     [rbp+57h+ppSacl], r14
0x180009167  lea     r8d, [rdx+7Fh]; SecurityInfo
0x18000916b  mov     [rbp+57h+ppSecurityDescriptor], r14
0x18000916f  mov     qword ptr [rsp+0A0h+dwCreationDisposition], r14; int
0x180009174  call    cs:__imp_GetSecurityInfo
0x18000917b  nop     dword ptr [rax+rax+00h]
0x180009180  test    eax, eax
0x180009182  jz      short loc_1800091F6
0x180009184  mov     rcx, [rbp+5Fh]; this
0x180009188  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\trust\\trustla"...
0x18000918f  mov     r9d, eax; char *
0x180009192  mov     edx, 24h ; '$'; void *
0x180009197  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000919c  mov     rcx, [rbp+57h+ppSecurityDescriptor]; hMem
0x1800091a0  mov     edi, eax
0x1800091a2  test    rcx, rcx
0x1800091a5  jz      short loc_1800091B3
0x1800091a7  call    cs:__imp_LocalFree
0x1800091ae  nop     dword ptr [rax+rax+00h]
0x1800091b3  test    edi, edi
0x1800091b5  jns     loc_180009257
0x1800091bb  mov     rcx, [rbp+5Fh]; this
0x1800091bf  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\trust\\trustla"...
0x1800091c6  mov     r9d, edi; char *
0x1800091c9  mov     edx, 90h; void *
0x1800091ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800091d3  mov     rcx, [rbp+57h+Sid1]; Sid
0x1800091d7  test    rcx, rcx
0x1800091da  jz      short loc_1800091E8
0x1800091dc  call    cs:__imp_RtlFreeSid
0x1800091e3  nop     dword ptr [rax+rax+00h]
0x1800091e8  lea     rcx, [rbp+57h+var_28]
0x1800091ec  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800091f1  jmp     loc_1800092B9
0x1800091f6  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r14d
0x1800091fa  mov     rcx, [rbp+57h+ppSacl]
0x1800091fe  lea     r8, [rbp+57h+IdentifierAuthority]
0x180009202  mov     edx, 14h
0x180009207  call    cs:__imp_RtlFindAceByType
0x18000920e  nop     dword ptr [rax+rax+00h]
0x180009213  test    rax, rax
0x180009216  jz      short loc_18000921E
0x180009218  test    byte ptr [rax+1], 8
0x18000921c  jz      short loc_180009228
0x18000921e  inc     dword ptr [rbp+57h+IdentifierAuthority.Value]
0x180009221  test    rax, rax
0x180009224  jnz     short loc_1800091FA
0x180009226  jmp     short loc_180009242
0x180009228  lea     rdx, [rax+8]; Sid2
0x18000922c  mov     rcx, rdi; Sid1
0x18000922f  call    cs:__imp_RtlEqualSid
0x180009236  nop     dword ptr [rax+rax+00h]
0x18000923b  test    al, al
0x18000923d  jz      short loc_180009242
0x18000923f  mov     byte ptr [rsi], 1
0x180009242  mov     rcx, [rbp+57h+ppSecurityDescriptor]; hMem
0x180009246  test    rcx, rcx
0x180009249  jz      short loc_180009257
0x18000924b  call    cs:__imp_LocalFree
0x180009252  nop     dword ptr [rax+rax+00h]
0x180009257  mov     rcx, [rbp+57h+Sid1]; Sid
0x18000925b  test    rcx, rcx
0x18000925e  jz      short loc_18000926C
0x180009260  call    cs:__imp_RtlFreeSid
0x180009267  nop     dword ptr [rax+rax+00h]
0x18000926c  lea     rax, [rbx-1]
0x180009270  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009274  ja      short loc_180009285
0x180009276  mov     rcx, rbx; hObject
0x180009279  call    cs:__imp_CloseHandle
0x180009280  nop     dword ptr [rax+rax+00h]
0x180009285  xor     eax, eax
0x180009287  jmp     short loc_1800092BB
0x180009289  mov     rcx, [rbp+5Fh]; this
0x18000928d  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\trust\\trustla"...
0x180009294  mov     edx, 88h; void *
0x180009299  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000929e  lea     rcx, [rbx-1]
0x1800092a2  mov     edi, eax
0x1800092a4  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800092a8  ja      short loc_1800092B9
0x1800092aa  mov     rcx, rbx; hObject
0x1800092ad  call    cs:__imp_CloseHandle
0x1800092b4  nop     dword ptr [rax+rax+00h]
0x1800092b9  mov     eax, edi
0x1800092bb  mov     rcx, [rbp+57h+var_18]
0x1800092bf  xor     rcx, rsp; StackCookie
0x1800092c2  call    __security_check_cookie
0x1800092c7  lea     r11, [rsp+0A0h+var_10]
0x1800092cf  mov     rbx, [r11+30h]
0x1800092d3  mov     rsi, [r11+38h]
0x1800092d7  mov     rsp, r11
0x1800092da  pop     r14
0x1800092dc  pop     rdi
0x1800092dd  pop     rbp
0x1800092de  retn
```
