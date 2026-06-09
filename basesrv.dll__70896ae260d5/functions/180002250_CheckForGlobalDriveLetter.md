# CheckForGlobalDriveLetter

- ea: `0x180002250`
- end: `0x180002382`
- name: `CheckForGlobalDriveLetter`
- size: `306`
- prototype: `BOOLEAN __fastcall(__int16)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001010`

## callees

- `0x180001eb0`
- `0x180002250`
- `0x18000d730`

## import_xrefs

- `ntdll!wcsncpy_s` at `0x1800022a1`
- `ntdll!wcsncpy_s` at `0x1800022a1`
- `ntdll!NtClose` at `0x180002347`
- `ntdll!NtClose` at `0x180002347`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180002313`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180002313`
- `ntdll!RtlInitUnicodeString` at `0x1800022c0`
- `ntdll!RtlInitUnicodeString` at `0x1800022c0`
- `CSRSRV!CsrRevertToSelf` at `0x180002321`
- `CSRSRV!CsrRevertToSelf` at `0x180002321`
- `CSRSRV!CsrImpersonateClient` at `0x1800022f6`
- `CSRSRV!CsrImpersonateClient` at `0x1800022f6`

## pseudocode

```c
BOOLEAN __fastcall CheckForGlobalDriveLetter(__int16 a1)
{
  NTSTATUS v2; // ebx
  __int64 v3; // rcx
  int v4; // ebx
  BOOLEAN v6[8]; // [rsp+20h] [rbp-78h] BYREF
  void *SymbolicLinkHandle; // [rsp+28h] [rbp-70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-58h] BYREF
  wchar_t Destination[8]; // [rsp+70h] [rbp-28h] BYREF

  v6[0] = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  SymbolicLinkHandle = 0;
  DestinationString = 0;
  wcsncpy_s(Destination, 8u, L"\\??\\X:", 7u);
  Destination[4] = a1 + 65;
  RtlInitUnicodeString(&DestinationString, Destination);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.Attributes = 64;
  if ( (unsigned __int8)CsrImpersonateClient(0)
    && (v2 = NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &ObjectAttributes), CsrRevertToSelf(v3), v2 >= 0)
    && (v4 = IsGlobalSymbolicLink(SymbolicLinkHandle, v6), NtClose(SymbolicLinkHandle), v4 >= 0) )
  {
    return v6[0];
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180002250  mov     [rsp+arg_0], rbx
0x180002255  push    rdi
0x180002256  sub     rsp, 90h
0x18000225d  mov     rax, cs:__security_cookie
0x180002264  xor     rax, rsp
0x180002267  mov     [rsp+98h+var_18], rax
0x18000226f  xor     eax, eax
0x180002271  lea     r8, Source; "\\??\\X:"
0x180002278  xor     edi, edi
0x18000227a  mov     [rsp+98h+var_78], al
0x18000227e  mov     ebx, ecx
0x180002280  mov     dword ptr [rsp+98h+ObjectAttributes+4], edi
0x180002284  xorps   xmm0, xmm0
0x180002287  mov     dword ptr [rsp+98h+ObjectAttributes+1Ch], edi
0x18000228b  lea     r9d, [rax+7]; MaxCount
0x18000228f  mov     [rsp+98h+SymbolicLinkHandle], rdi
0x180002294  lea     edx, [rax+8]; SizeInWords
0x180002297  lea     rcx, [rsp+98h+Destination]; Destination
0x18000229c  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x1800022a1  call    cs:__imp_wcsncpy_s
0x1800022a8  nop     dword ptr [rax+rax+00h]
0x1800022ad  add     bx, 41h ; 'A'
0x1800022b1  lea     rdx, [rsp+98h+Destination]; SourceString
0x1800022b6  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x1800022bb  mov     [rsp+98h+var_20], bx
0x1800022c0  call    cs:__imp_RtlInitUnicodeString
0x1800022c7  nop     dword ptr [rax+rax+00h]
0x1800022cc  lea     rax, [rsp+98h+DestinationString]
0x1800022d1  mov     [rsp+98h+ObjectAttributes.Length], 30h ; '0'
0x1800022d9  xorps   xmm0, xmm0
0x1800022dc  mov     [rsp+98h+ObjectAttributes.ObjectName], rax
0x1800022e1  xor     ecx, ecx
0x1800022e3  mov     [rsp+98h+ObjectAttributes.RootDirectory], rdi
0x1800022e8  movdqu  xmmword ptr [rsp+98h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800022ee  mov     [rsp+98h+ObjectAttributes.Attributes], 40h ; '@'
0x1800022f6  call    cs:__imp_CsrImpersonateClient
0x1800022fd  nop     dword ptr [rax+rax+00h]
0x180002302  test    al, al
0x180002304  jz      short loc_18000235E
0x180002306  lea     r8, [rsp+98h+ObjectAttributes]; ObjectAttributes
0x18000230b  lea     edx, [rdi+1]; DesiredAccess
0x18000230e  lea     rcx, [rsp+98h+SymbolicLinkHandle]; SymbolicLinkHandle
0x180002313  call    cs:__imp_NtOpenSymbolicLinkObject
0x18000231a  nop     dword ptr [rax+rax+00h]
0x18000231f  mov     ebx, eax
0x180002321  call    cs:__imp_CsrRevertToSelf
0x180002328  nop     dword ptr [rax+rax+00h]
0x18000232d  test    ebx, ebx
0x18000232f  js      short loc_18000235E
0x180002331  mov     rcx, [rsp+98h+SymbolicLinkHandle]; Handle
0x180002336  lea     rdx, [rsp+98h+var_78]
0x18000233b  call    IsGlobalSymbolicLink
0x180002340  mov     rcx, [rsp+98h+SymbolicLinkHandle]; Handle
0x180002345  mov     ebx, eax
0x180002347  call    cs:__imp_NtClose
0x18000234e  nop     dword ptr [rax+rax+00h]
0x180002353  test    ebx, ebx
0x180002355  js      short loc_18000235E
0x180002357  movzx   eax, [rsp+98h+var_78]
0x18000235c  jmp     short loc_180002360
0x18000235e  xor     al, al
0x180002360  mov     rcx, [rsp+98h+var_18]
0x180002368  xor     rcx, rsp; StackCookie
0x18000236b  call    __security_check_cookie
0x180002370  mov     rbx, [rsp+98h+arg_0]
0x180002378  add     rsp, 90h
0x18000237f  pop     rdi
0x180002380  retn
```
