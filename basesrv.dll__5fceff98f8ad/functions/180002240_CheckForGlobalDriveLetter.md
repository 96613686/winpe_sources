# CheckForGlobalDriveLetter

- ea: `0x180002240`
- end: `0x18000237f`
- name: `CheckForGlobalDriveLetter`
- size: `319`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callers

- `0x180001010`

## callees

- `0x180001ea0`
- `0x180002240`
- `0x18000db40`

## import_xrefs

- `ntdll!wcsncpy_s` at `0x18000229c`
- `ntdll!wcsncpy_s` at `0x18000229c`
- `ntdll!NtClose` at `0x180002344`
- `ntdll!NtClose` at `0x180002344`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180002310`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180002310`
- `ntdll!RtlInitUnicodeString` at `0x1800022bb`
- `ntdll!RtlInitUnicodeString` at `0x1800022bb`
- `CSRSRV!CsrRevertToSelf` at `0x18000231e`
- `CSRSRV!CsrRevertToSelf` at `0x18000231e`
- `CSRSRV!CsrImpersonateClient` at `0x1800022f1`
- `CSRSRV!CsrImpersonateClient` at `0x1800022f1`

## pseudocode

```c
char __fastcall CheckForGlobalDriveLetter(__int16 a1)
{
  NTSTATUS v2; // ebx
  int v3; // ebx
  void *SymbolicLinkHandle; // [rsp+28h] [rbp-70h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-38h] BYREF
  wchar_t Destination[8]; // [rsp+70h] [rbp-28h] BYREF

  SymbolicLinkHandle = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  DestinationString = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  wcsncpy_s(Destination, 8u, L"\\??\\X:", 7u);
  Destination[4] = a1 + 65;
  RtlInitUnicodeString(&DestinationString, Destination);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  if ( (unsigned __int8)CsrImpersonateClient(0)
    && (v2 = NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &ObjectAttributes), CsrRevertToSelf(), v2 >= 0)
    && (v3 = IsGlobalSymbolicLink(SymbolicLinkHandle), NtClose(SymbolicLinkHandle), v3 >= 0) )
  {
    return 0;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180002240  mov     [rsp+arg_0], rbx
0x180002245  push    rdi
0x180002246  sub     rsp, 90h
0x18000224d  mov     rax, cs:__security_cookie
0x180002254  xor     rax, rsp
0x180002257  mov     [rsp+98h+var_18], rax
0x18000225f  xorps   xmm0, xmm0
0x180002262  lea     r8, Source; "\\??\\X:"
0x180002269  mov     ebx, ecx
0x18000226b  xor     eax, eax
0x18000226d  movups  xmmword ptr [rsp+98h+ObjectAttributes.ObjectName], xmm0
0x180002272  xor     edi, edi
0x180002274  mov     [rsp+98h+var_78], al
0x180002278  mov     r9d, 7; MaxCount
0x18000227e  mov     [rsp+98h+SymbolicLinkHandle], rdi
0x180002283  mov     edx, 8; SizeInWords
0x180002288  lea     rcx, [rsp+98h+Destination]; Destination
0x18000228d  movups  xmmword ptr [rsp+98h+ObjectAttributes+1Ch], xmm0
0x180002292  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x180002297  movups  xmmword ptr [rsp+98h+ObjectAttributes.Length], xmm0
0x18000229c  call    cs:__imp_wcsncpy_s
0x1800022a3  nop     dword ptr [rax+rax+00h]
0x1800022a8  add     bx, 41h ; 'A'
0x1800022ac  lea     rdx, [rsp+98h+Destination]; SourceString
0x1800022b1  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x1800022b6  mov     [rsp+98h+var_20], bx
0x1800022bb  call    cs:__imp_RtlInitUnicodeString
0x1800022c2  nop     dword ptr [rax+rax+00h]
0x1800022c7  lea     rax, [rsp+98h+DestinationString]
0x1800022cc  mov     [rsp+98h+ObjectAttributes.Length], 30h ; '0'
0x1800022d4  xorps   xmm0, xmm0
0x1800022d7  mov     [rsp+98h+ObjectAttributes.ObjectName], rax
0x1800022dc  xor     ecx, ecx
0x1800022de  mov     [rsp+98h+ObjectAttributes.RootDirectory], rdi
0x1800022e3  movdqu  xmmword ptr [rsp+98h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800022e9  mov     [rsp+98h+ObjectAttributes.Attributes], 40h ; '@'
0x1800022f1  call    cs:__imp_CsrImpersonateClient
0x1800022f8  nop     dword ptr [rax+rax+00h]
0x1800022fd  test    al, al
0x1800022ff  jz      short loc_18000235B
0x180002301  lea     r8, [rsp+98h+ObjectAttributes]; ObjectAttributes
0x180002306  mov     edx, 1; DesiredAccess
0x18000230b  lea     rcx, [rsp+98h+SymbolicLinkHandle]; SymbolicLinkHandle
0x180002310  call    cs:__imp_NtOpenSymbolicLinkObject
0x180002317  nop     dword ptr [rax+rax+00h]
0x18000231c  mov     ebx, eax
0x18000231e  call    cs:__imp_CsrRevertToSelf
0x180002325  nop     dword ptr [rax+rax+00h]
0x18000232a  test    ebx, ebx
0x18000232c  js      short loc_18000235B
0x18000232e  mov     rcx, [rsp+98h+SymbolicLinkHandle]; Handle
0x180002333  lea     rdx, [rsp+98h+var_78]
0x180002338  call    IsGlobalSymbolicLink
0x18000233d  mov     rcx, [rsp+98h+SymbolicLinkHandle]; Handle
0x180002342  mov     ebx, eax
0x180002344  call    cs:__imp_NtClose
0x18000234b  nop     dword ptr [rax+rax+00h]
0x180002350  test    ebx, ebx
0x180002352  js      short loc_18000235B
0x180002354  movzx   eax, [rsp+98h+var_78]
0x180002359  jmp     short loc_18000235D
0x18000235b  xor     al, al
0x18000235d  mov     rcx, [rsp+98h+var_18]
0x180002365  xor     rcx, rsp; StackCookie
0x180002368  call    __security_check_cookie
0x18000236d  mov     rbx, [rsp+98h+arg_0]
0x180002375  add     rsp, 90h
0x18000237c  pop     rdi
0x18000237d  retn
```
