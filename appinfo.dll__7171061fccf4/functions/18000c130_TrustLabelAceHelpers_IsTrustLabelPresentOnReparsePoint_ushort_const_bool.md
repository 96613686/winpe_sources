# TrustLabelAceHelpers::IsTrustLabelPresentOnReparsePoint(ushort const *,bool *)

- ea: `0x18000c130`
- end: `0x18000c358`
- name: `?IsTrustLabelPresentOnReparsePoint@TrustLabelAceHelpers@@SAJPEBGPEA_N@Z`
- size: `552`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002bc04`

## callees

- `0x18000720c`
- `0x18000c130`
- `0x18000c360`
- `0x18000c410`
- `0x180018dbc`
- `0x18001a0d4`
- `0x18001f59f`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c303`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c340`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c303`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c340`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c23e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c2dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c23e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c2dd`
- `ntdll!RtlEqualSid` at `0x18000c2c6`
- `ntdll!RtlEqualSid` at `0x18000c2c6`
- `ntdll!RtlFindAceByType` at `0x18000c2a0`
- `ntdll!RtlFindAceByType` at `0x18000c2a0`
- `ntdll!RtlFreeSid` at `0x18000c1c0`
- `ntdll!RtlFreeSid` at `0x18000c272`
- `ntdll!RtlFreeSid` at `0x18000c2f0`
- `ntdll!RtlFreeSid` at `0x18000c1c0`
- `ntdll!RtlFreeSid` at `0x18000c272`
- `ntdll!RtlFreeSid` at `0x18000c2f0`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18000c20f`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18000c20f`

## pseudocode

```c
__int64 __fastcall TrustLabelAceHelpers::IsTrustLabelPresentOnReparsePoint(const unsigned __int16 *a1, bool *a2)
{
  char *FileW_0; // rbx
  const char *v4; // r9
  int WindowsPplTrustLabelSid; // eax
  unsigned int v6; // edi
  PSID v7; // rdi
  DWORD SecurityInfo; // eax
  __int64 AceByType; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-58h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-58h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-58h]
  PSECURITY_DESCRIPTOR hMem; // [rsp+40h] [rbp-38h] BYREF
  PACL ppSacl; // [rsp+48h] [rbp-30h] BYREF
  char *v16; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int v18; // [rsp+90h] [rbp+18h] BYREF
  PSID Sid; // [rsp+98h] [rbp+20h] BYREF

  FileW_0 = (char *)CreateFileW_0(a1, 0x20000u, 0, 0, 3u, 0x2200000u, 0);
  v16 = FileW_0;
  if ( (unsigned __int64)(FileW_0 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return (unsigned int)wil::details::in1diag3::Return_GetLastError(
                           retaddr,
                           (void *)0x88,
                           (unsigned int)"onecore\\base\\appmodel\\trust\\trustlabelhelpersbase.cpp",
                           v4);
  Sid = 0;
  WindowsPplTrustLabelSid = TrustLabelAceHelpers::GetWindowsPplTrustLabelSid(&Sid);
  v6 = WindowsPplTrustLabelSid;
  if ( WindowsPplTrustLabelSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecore\\base\\appmodel\\trust\\trustlabelhelpersbase.cpp",
      (const char *)(unsigned int)WindowsPplTrustLabelSid,
      dwCreationDisposition);
    if ( Sid )
      RtlFreeSid(Sid);
    CloseHandle(FileW_0);
    return v6;
  }
  v7 = Sid;
  *a2 = 0;
  ppSacl = 0;
  hMem = 0;
  SecurityInfo = GetSecurityInfo(FileW_0, SE_FILE_OBJECT, 0x80u, 0, 0, 0, &ppSacl, &hMem);
  if ( SecurityInfo )
  {
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x24,
           (unsigned int)"onecore\\base\\appmodel\\trust\\trustlabelhelpersbase.cpp",
           (const char *)SecurityInfo,
           dwCreationDispositiona);
    if ( hMem )
      LocalFree(hMem);
    if ( (v6 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecore\\base\\appmodel\\trust\\trustlabelhelpersbase.cpp",
        (const char *)v6,
        dwCreationDispositionb);
      if ( Sid )
        RtlFreeSid(Sid);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
      return v6;
    }
  }
  else
  {
    v18 = 0;
    while ( 1 )
    {
      AceByType = RtlFindAceByType(ppSacl, 20, &v18);
      if ( AceByType )
      {
        if ( (*(_BYTE *)(AceByType + 1) & 8) == 0 )
          break;
      }
      ++v18;
      if ( !AceByType )
        goto LABEL_19;
    }
    if ( RtlEqualSid(v7, (PSID)(AceByType + 8)) )
      *a2 = 1;
LABEL_19:
    if ( hMem )
      LocalFree(hMem);
  }
  if ( Sid )
    RtlFreeSid(Sid);
  if ( (unsigned __int64)(FileW_0 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW_0);
  return 0;
}

```

## disassembly

```asm
0x18000c130  mov     [rsp+arg_0], rbx
0x18000c135  push    rbp
0x18000c136  push    rsi
0x18000c137  push    rdi
0x18000c138  sub     rsp, 60h
0x18000c13c  mov     rsi, rdx
0x18000c13f  xor     ebp, ebp
0x18000c141  mov     [rsp+78h+hTemplateFile], rbp; hTemplateFile
0x18000c146  xor     r9d, r9d; lpSecurityAttributes
0x18000c149  mov     [rsp+78h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18000c151  xor     r8d, r8d; dwShareMode
0x18000c154  mov     edx, 20000h; dwDesiredAccess
0x18000c159  mov     [rsp+78h+dwCreationDisposition], 3; int
0x18000c161  call    CreateFileW_0
0x18000c166  mov     rbx, rax
0x18000c169  mov     [rsp+78h+var_28], rax
0x18000c16e  dec     rax
0x18000c171  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c175  ja      loc_18000C31B
0x18000c17b  lea     rcx, [rsp+78h+Sid]; Sid
0x18000c183  mov     [rsp+78h+Sid], rbp
0x18000c18b  call    ?GetWindowsPplTrustLabelSid@TrustLabelAceHelpers@@SAJPEAPEAX@Z; TrustLabelAceHelpers::GetWindowsPplTrustLabelSid(void * *)
0x18000c190  mov     edi, eax
0x18000c192  test    eax, eax
0x18000c194  jns     short loc_18000C1CB
0x18000c196  mov     rcx, [rsp+78h]; this
0x18000c19b  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\trust\\trustla"...
0x18000c1a2  mov     r9d, eax; char *
0x18000c1a5  mov     edx, 8Bh; void *
0x18000c1aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c1af  mov     rcx, [rsp+78h+Sid]; Sid
0x18000c1b7  test    rcx, rcx
0x18000c1ba  jz      loc_18000C33D
0x18000c1c0  call    cs:__imp_RtlFreeSid
0x18000c1c6  jmp     loc_18000C33D
0x18000c1cb  mov     rdi, [rsp+78h+Sid]
0x18000c1d3  lea     rax, [rsp+78h+hMem]
0x18000c1d8  mov     [rsp+78h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18000c1dd  xor     r9d, r9d; ppsidOwner
0x18000c1e0  lea     rax, [rsp+78h+ppSacl]
0x18000c1e5  mov     [rsi], bpl
0x18000c1e8  mov     [rsp+78h+hTemplateFile], rax; ppSacl
0x18000c1ed  mov     edx, 1; ObjectType
0x18000c1f2  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rbp; ppDacl
0x18000c1f7  mov     r8d, 80h; SecurityInfo
0x18000c1fd  mov     rcx, rbx; handle
0x18000c200  mov     qword ptr [rsp+78h+dwCreationDisposition], rbp; int
0x18000c205  mov     [rsp+78h+ppSacl], rbp
0x18000c20a  mov     [rsp+78h+hMem], rbp
0x18000c20f  call    cs:__imp_GetSecurityInfo
0x18000c215  test    eax, eax
0x18000c217  jz      short loc_18000C287
0x18000c219  mov     rcx, [rsp+78h]; this
0x18000c21e  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\trust\\trustla"...
0x18000c225  mov     r9d, eax; char *
0x18000c228  mov     edx, 24h ; '$'; void *
0x18000c22d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000c232  mov     rcx, [rsp+78h+hMem]; hMem
0x18000c237  mov     edi, eax
0x18000c239  test    rcx, rcx
0x18000c23c  jz      short loc_18000C244
0x18000c23e  call    cs:__imp_LocalFree
0x18000c244  test    edi, edi
0x18000c246  jns     loc_18000C2E3
0x18000c24c  mov     rcx, [rsp+78h]; this
0x18000c251  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\trust\\trustla"...
0x18000c258  mov     r9d, edi; char *
0x18000c25b  mov     edx, 90h; void *
0x18000c260  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c265  mov     rcx, [rsp+78h+Sid]; Sid
0x18000c26d  test    rcx, rcx
0x18000c270  jz      short loc_18000C278
0x18000c272  call    cs:__imp_RtlFreeSid
0x18000c278  lea     rcx, [rsp+78h+var_28]
0x18000c27d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000c282  jmp     loc_18000C346
0x18000c287  mov     [rsp+78h+arg_10], ebp
0x18000c28e  mov     rcx, [rsp+78h+ppSacl]
0x18000c293  lea     r8, [rsp+78h+arg_10]
0x18000c29b  mov     edx, 14h
0x18000c2a0  call    cs:__imp_RtlFindAceByType
0x18000c2a6  test    rax, rax
0x18000c2a9  jz      short loc_18000C2B1
0x18000c2ab  test    byte ptr [rax+1], 8
0x18000c2af  jz      short loc_18000C2BF
0x18000c2b1  inc     [rsp+78h+arg_10]
0x18000c2b8  test    rax, rax
0x18000c2bb  jnz     short loc_18000C28E
0x18000c2bd  jmp     short loc_18000C2D3
0x18000c2bf  lea     rdx, [rax+8]; Sid2
0x18000c2c3  mov     rcx, rdi; Sid1
0x18000c2c6  call    cs:__imp_RtlEqualSid
0x18000c2cc  test    al, al
0x18000c2ce  jz      short loc_18000C2D3
0x18000c2d0  mov     byte ptr [rsi], 1
0x18000c2d3  mov     rcx, [rsp+78h+hMem]; hMem
0x18000c2d8  test    rcx, rcx
0x18000c2db  jz      short loc_18000C2E3
0x18000c2dd  call    cs:__imp_LocalFree
0x18000c2e3  mov     rcx, [rsp+78h+Sid]; Sid
0x18000c2eb  test    rcx, rcx
0x18000c2ee  jz      short loc_18000C2F6
0x18000c2f0  call    cs:__imp_RtlFreeSid
0x18000c2f6  lea     rax, [rbx-1]
0x18000c2fa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c2fe  ja      short loc_18000C309
0x18000c300  mov     rcx, rbx; hObject
0x18000c303  call    cs:__imp_CloseHandle
0x18000c309  xor     eax, eax
0x18000c30b  mov     rbx, [rsp+78h+arg_0]
0x18000c313  add     rsp, 60h
0x18000c317  pop     rdi
0x18000c318  pop     rsi
0x18000c319  pop     rbp
0x18000c31a  retn
0x18000c31b  mov     rcx, [rsp+78h]; this
0x18000c320  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\trust\\trustla"...
0x18000c327  mov     edx, 88h; void *
0x18000c32c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c331  lea     rcx, [rbx-1]
0x18000c335  mov     edi, eax
0x18000c337  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000c33b  ja      short loc_18000C346
0x18000c33d  mov     rcx, rbx; hObject
0x18000c340  call    cs:__imp_CloseHandle
0x18000c346  mov     rbx, [rsp+78h+arg_0]
0x18000c34e  mov     eax, edi
0x18000c350  add     rsp, 60h
0x18000c354  pop     rdi
0x18000c355  pop     rsi
0x18000c356  pop     rbp
0x18000c357  retn
```
