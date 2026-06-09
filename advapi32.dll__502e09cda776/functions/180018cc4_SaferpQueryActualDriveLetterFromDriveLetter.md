# SaferpQueryActualDriveLetterFromDriveLetter

- ea: `0x180018cc4`
- end: `0x180018ef3`
- name: `SaferpQueryActualDriveLetterFromDriveLetter`
- size: `559`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180018708`
- `0x180018c08`
- `0x180018cc4`

## callees

- `0x180018cc4`
- `0x180018efc`
- `0x1800720b0`

## import_xrefs

- `ntdll!NtClose` at `0x180018df1`
- `ntdll!NtClose` at `0x180018df1`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180018da5`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180018da5`
- `ntdll!NtQuerySymbolicLinkObject` at `0x180018dde`
- `ntdll!NtQuerySymbolicLinkObject` at `0x180018dde`
- `ntdll!RtlPrefixUnicodeString` at `0x180018e24`
- `ntdll!RtlPrefixUnicodeString` at `0x180018e47`
- `ntdll!RtlPrefixUnicodeString` at `0x180018e24`
- `ntdll!RtlPrefixUnicodeString` at `0x180018e47`
- `ntdll!RtlInitUnicodeString` at `0x180018d5e`
- `ntdll!RtlInitUnicodeString` at `0x180018d5e`

## pseudocode

```c
char __fastcall SaferpQueryActualDriveLetterFromDriveLetter(__int64 a1, __int16 a2, _WORD *a3, __int16 a4)
{
  NTSTATUS v8; // ebx
  __int64 v10; // rdx
  ULONG DataWritten; // [rsp+20h] [rbp-E0h] BYREF
  struct _UNICODE_STRING LinkTarget; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE SymbolicLinkHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SourceString[4]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v17; // [rsp+88h] [rbp-78h]
  int v18; // [rsp+8Ah] [rbp-76h]
  char v19; // [rsp+90h] [rbp-70h] BYREF

  v18 = 58;
  SymbolicLinkHandle = 0;
  *(_QWORD *)SourceString = 0x5C003F003F005CLL;
  DataWritten = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  LinkTarget = 0;
  if ( (unsigned __int16)(a2 - 65) > 0x19u && (unsigned __int16)(a2 - 97) > 0x19u )
    return 0;
  v17 = a2;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &ObjectAttributes) < 0 )
    return 0;
  LinkTarget.Buffer = (PWSTR)&v19;
  *(_DWORD *)&LinkTarget.Length = 68157440;
  DataWritten = 0;
  v8 = NtQuerySymbolicLinkObject(SymbolicLinkHandle, &LinkTarget, &DataWritten);
  NtClose(SymbolicLinkHandle);
  if ( v8 < 0 )
    return 0;
  if ( (unsigned __int8)SaferpIsNetworkVolume(a1) )
  {
    *a3 = 0;
    return 1;
  }
  if ( !RtlPrefixUnicodeString(&String1, &LinkTarget, 1u)
    || LinkTarget.Length < 0xCu
    || LinkTarget.Buffer[5] != 58
    || (v10 = LinkTarget.Buffer[4], (unsigned __int16)(v10 - 65) > 0x19u) && (unsigned __int16)(v10 - 97) > 0x19u )
  {
    if ( !RtlPrefixUnicodeString(&stru_180075140, &LinkTarget, 1u) )
      return 0;
    *a3 = a2;
    return 1;
  }
  if ( a4 <= 0 )
    return 0;
  return SaferpQueryActualDriveLetterFromDriveLetter(a1, v10, a3, (unsigned __int16)(a4 - 1));
}

```

## disassembly

```asm
0x180018cc4  mov     [rsp-8+arg_8], rbx
0x180018cc9  push    rbp
0x180018cca  push    rsi
0x180018ccb  push    rdi
0x180018ccc  push    r12
0x180018cce  push    r13
0x180018cd0  push    r14
0x180018cd2  push    r15
0x180018cd4  lea     rbp, [rsp-3B0h]
0x180018cdc  sub     rsp, 4B0h
0x180018ce3  mov     rax, cs:__security_cookie
0x180018cea  xor     rax, rsp
0x180018ced  mov     [rbp+3E0h+var_40], rax
0x180018cf4  xorps   xmm0, xmm0
0x180018cf7  mov     [rbp+3E0h+var_456], 3Ah ; ':'
0x180018cfe  xor     eax, eax
0x180018d00  xor     r12d, r12d
0x180018d03  mov     rax, 5C003F003F005Ch
0x180018d0d  mov     [rsp+4E0h+SymbolicLinkHandle], r12
0x180018d12  movzx   r14d, dx
0x180018d16  mov     qword ptr [rbp+3E0h+SourceString], rax
0x180018d1a  movups  xmmword ptr [rsp+4E0h+ObjectAttributes.ObjectName], xmm0
0x180018d1f  movzx   edi, r9w
0x180018d23  mov     [rsp+4E0h+DataWritten], r12d
0x180018d28  mov     rsi, r8
0x180018d2b  mov     r15, rcx
0x180018d2e  lea     eax, [r14-41h]
0x180018d32  movups  xmmword ptr [rsp+4E0h+DestinationString.Length], xmm0
0x180018d37  movups  xmmword ptr [rsp+4E0h+ObjectAttributes.Length], xmm0
0x180018d3c  movups  xmmword ptr [rsp+4E0h+ObjectAttributes+1Ch], xmm0
0x180018d41  movups  xmmword ptr [rsp+4E0h+LinkTarget.Length], xmm0
0x180018d46  cmp     ax, 19h
0x180018d4a  ja      loc_180018E89
0x180018d50  lea     rdx, [rbp+3E0h+SourceString]; SourceString
0x180018d54  mov     [rbp+3E0h+var_458], r14w
0x180018d59  lea     rcx, [rsp+4E0h+DestinationString]; DestinationString
0x180018d5e  call    cs:__imp_RtlInitUnicodeString
0x180018d65  nop     dword ptr [rax+rax+00h]
0x180018d6a  lea     rax, [rsp+4E0h+DestinationString]
0x180018d6f  mov     [rsp+4E0h+ObjectAttributes.Length], 30h ; '0'
0x180018d77  xorps   xmm0, xmm0
0x180018d7a  mov     [rsp+4E0h+ObjectAttributes.ObjectName], rax
0x180018d7f  mov     r13d, 1
0x180018d85  mov     [rsp+4E0h+ObjectAttributes.RootDirectory], r12
0x180018d8a  mov     edx, r13d; DesiredAccess
0x180018d8d  mov     [rsp+4E0h+ObjectAttributes.Attributes], 40h ; '@'
0x180018d95  lea     r8, [rsp+4E0h+ObjectAttributes]; ObjectAttributes
0x180018d9a  lea     rcx, [rsp+4E0h+SymbolicLinkHandle]; SymbolicLinkHandle
0x180018d9f  movdqu  xmmword ptr [rsp+4E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180018da5  call    cs:__imp_NtOpenSymbolicLinkObject
0x180018dac  nop     dword ptr [rax+rax+00h]
0x180018db1  test    eax, eax
0x180018db3  js      loc_180018E97
0x180018db9  mov     rcx, [rsp+4E0h+SymbolicLinkHandle]; SymLinkObjHandle
0x180018dbe  lea     rax, [rbp+3E0h+var_450]
0x180018dc2  lea     r8, [rsp+4E0h+DataWritten]; DataWritten
0x180018dc7  mov     [rsp+4E0h+LinkTarget.Buffer], rax
0x180018dcc  lea     rdx, [rsp+4E0h+LinkTarget]; LinkTarget
0x180018dd1  mov     dword ptr [rsp+4E0h+LinkTarget.Length], 4100000h
0x180018dd9  mov     [rsp+4E0h+DataWritten], r12d
0x180018dde  call    cs:__imp_NtQuerySymbolicLinkObject
0x180018de5  nop     dword ptr [rax+rax+00h]
0x180018dea  mov     rcx, [rsp+4E0h+SymbolicLinkHandle]; Handle
0x180018def  mov     ebx, eax
0x180018df1  call    cs:__imp_NtClose
0x180018df8  nop     dword ptr [rax+rax+00h]
0x180018dfd  test    ebx, ebx
0x180018dff  js      loc_180018E97
0x180018e05  mov     rcx, r15
0x180018e08  call    SaferpIsNetworkVolume
0x180018e0d  test    al, al
0x180018e0f  jnz     loc_180018E9B
0x180018e15  mov     r8b, r13b; CaseInsensitive
0x180018e18  lea     rdx, [rsp+4E0h+LinkTarget]; String2
0x180018e1d  lea     rcx, String1; String1
0x180018e24  call    cs:__imp_RtlPrefixUnicodeString
0x180018e2b  nop     dword ptr [rax+rax+00h]
0x180018e30  test    al, al
0x180018e32  jnz     loc_180018ED1
0x180018e38  mov     r8b, r13b; CaseInsensitive
0x180018e3b  lea     rdx, [rsp+4E0h+LinkTarget]; String2
0x180018e40  lea     rcx, stru_180075140; String1
0x180018e47  call    cs:__imp_RtlPrefixUnicodeString
0x180018e4e  nop     dword ptr [rax+rax+00h]
0x180018e53  test    al, al
0x180018e55  jz      short loc_180018E97
0x180018e57  mov     [rsi], r14w
0x180018e5b  mov     al, r13b
0x180018e5e  mov     rcx, [rbp+3E0h+var_40]
0x180018e65  xor     rcx, rsp; StackCookie
0x180018e68  call    __security_check_cookie
0x180018e6d  mov     rbx, [rsp+4E0h+arg_8]
0x180018e75  add     rsp, 4B0h
0x180018e7c  pop     r15
0x180018e7e  pop     r14
0x180018e80  pop     r13
0x180018e82  pop     r12
0x180018e84  pop     rdi
0x180018e85  pop     rsi
0x180018e86  pop     rbp
0x180018e87  retn
0x180018e89  lea     eax, [r14-61h]
0x180018e8d  cmp     ax, 19h
0x180018e91  jbe     loc_180018D50
0x180018e97  xor     al, al
0x180018e99  jmp     short loc_180018E5E
0x180018e9b  mov     [rsi], r12w
0x180018e9f  jmp     short loc_180018E5B
0x180018ea1  movzx   edx, word ptr [rdx+8]
0x180018ea5  lea     eax, [rdx-41h]
0x180018ea8  cmp     ax, 19h
0x180018eac  jbe     short loc_180018EB7
0x180018eae  lea     eax, [rdx-61h]
0x180018eb1  cmp     ax, 19h
0x180018eb5  ja      short loc_180018E38
0x180018eb7  test    di, di
0x180018eba  jle     short loc_180018E97
0x180018ebc  sub     di, r13w
0x180018ec0  mov     r8, rsi
0x180018ec3  movzx   r9d, di
0x180018ec7  mov     rcx, r15
0x180018eca  call    SaferpQueryActualDriveLetterFromDriveLetter
0x180018ecf  jmp     short loc_180018E5E
0x180018ed1  cmp     [rsp+4E0h+LinkTarget.Length], 0Ch
0x180018ed7  jb      loc_180018E38
0x180018edd  mov     rdx, [rsp+4E0h+LinkTarget.Buffer]
0x180018ee2  mov     eax, 3Ah ; ':'
0x180018ee7  cmp     [rdx+0Ah], ax
0x180018eeb  jnz     loc_180018E38
0x180018ef1  jmp     short loc_180018EA1
```
