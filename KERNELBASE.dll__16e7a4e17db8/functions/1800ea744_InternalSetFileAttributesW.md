# InternalSetFileAttributesW

- ea: `0x1800ea744`
- end: `0x1800ea96d`
- name: `InternalSetFileAttributesW`
- size: `553`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800ea710`

## callees

- `0x1800134a0`
- `0x1800ea744`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlReleaseRelativeName` at `0x1800ea82d`
- `ntdll!RtlReleaseRelativeName` at `0x1800ea8cc`
- `ntdll!RtlReleaseRelativeName` at `0x1800ea82d`
- `ntdll!RtlReleaseRelativeName` at `0x1800ea8cc`
- `ntdll!NtOpenFile` at `0x1800ea819`
- `ntdll!NtOpenFile` at `0x1800ea944`
- `ntdll!NtOpenFile` at `0x1800ea819`
- `ntdll!NtOpenFile` at `0x1800ea944`
- `ntdll!NtSetInformationFile` at `0x1800ea881`
- `ntdll!NtSetInformationFile` at `0x1800ea881`
- `ntdll!RtlSetLastWin32Error` at `0x1800ea965`
- `ntdll!RtlSetLastWin32Error` at `0x1800ea965`
- `ntdll!NtClose` at `0x1800ea88d`
- `ntdll!NtClose` at `0x1800ea88d`
- `ntdll!RtlFreeHeap` at `0x1800ea845`
- `ntdll!RtlFreeHeap` at `0x1800ea8e4`
- `ntdll!RtlFreeHeap` at `0x1800ea845`
- `ntdll!RtlFreeHeap` at `0x1800ea8e4`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1800ea7b0`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1800ea7b0`

## pseudocode

```c
__int64 __fastcall InternalSetFileAttributesW(__int64 a1, int a2)
{
  int v3; // eax
  PVOID v4; // rdi
  HANDLE ContainingDirectory; // rax
  NTSTATUS v6; // ebx
  __int64 v8; // rcx
  HANDLE FileHandle; // [rsp+30h] [rbp-69h] BYREF
  PVOID P[2]; // [rsp+38h] [rbp-61h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+48h] [rbp-51h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-21h] BYREF
  __int128 FileInformation; // [rsp+A8h] [rbp+Fh] BYREF
  __int128 v15; // [rsp+B8h] [rbp+1Fh]
  __int64 v16; // [rsp+C8h] [rbp+2Fh]

  v16 = 0;
  FileHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  *(_OWORD *)P = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  v15 = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  v3 = RtlDosPathNameToRelativeNtPathName_U_WithStatus(a1, P, 0, &RelativeName);
  if ( v3 < 0 )
  {
    if ( v3 != -1073741801 && v3 != -1073741670 )
    {
      RtlSetLastWin32Error(3u);
      return 0;
    }
    v8 = (unsigned int)v3;
  }
  else
  {
    v4 = P[1];
    if ( RelativeName.RelativeName.Length )
    {
      LOWORD(P[0]) = RelativeName.RelativeName.Length;
      *(_DWORD *)((char *)P + 2) = *(_DWORD *)&RelativeName.RelativeName.MaximumLength;
      HIWORD(P[0]) = *(&RelativeName.RelativeName.MaximumLength + 2);
      P[1] = RelativeName.RelativeName.Buffer;
      ContainingDirectory = RelativeName.ContainingDirectory;
    }
    else
    {
      ContainingDirectory = 0;
      RelativeName.ContainingDirectory = 0;
    }
    ObjectAttributes.RootDirectory = ContainingDirectory;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v6 = NtOpenFile(&FileHandle, 0x100100u, &ObjectAttributes, &IoStatusBlock, 7u, 0x204020u);
    if ( v6 >= 0
      || v6 == -1073741811
      && (v6 = NtOpenFile(&FileHandle, 0x100100u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4020u), v6 >= 0) )
    {
      RtlReleaseRelativeName(&RelativeName);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
      v16 = a2 & 0x1A3127 | 0x80u;
      FileInformation = 0;
      v15 = 0;
      v6 = NtSetInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
      NtClose(FileHandle);
      if ( v6 >= 0 )
        return 1;
    }
    else
    {
      RtlReleaseRelativeName(&RelativeName);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    }
    v8 = (unsigned int)v6;
  }
  BaseSetLastNTError(v8);
  return 0;
}

```

## disassembly

```asm
0x1800ea744  mov     [rsp-8+arg_10], rbx
0x1800ea749  mov     [rsp-8+arg_18], rsi
0x1800ea74e  push    rbp
0x1800ea74f  push    rdi
0x1800ea750  push    r14
0x1800ea752  lea     rbp, [rsp-47h]
0x1800ea757  sub     rsp, 0E0h
0x1800ea75e  mov     rax, cs:__security_cookie
0x1800ea765  xor     rax, rsp
0x1800ea768  mov     [rbp+57h+var_20], rax
0x1800ea76c  xorps   xmm0, xmm0
0x1800ea76f  lea     r9, [rbp+57h+RelativeName]
0x1800ea773  mov     esi, edx
0x1800ea775  xor     eax, eax
0x1800ea777  xorps   xmm1, xmm1
0x1800ea77a  mov     [rbp+57h+var_28], rax
0x1800ea77e  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800ea782  xor     r14d, r14d
0x1800ea785  lea     rdx, [rbp+57h+P]
0x1800ea789  xor     r8d, r8d
0x1800ea78c  mov     [rbp+57h+FileHandle], r14
0x1800ea790  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800ea794  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800ea798  movups  xmmword ptr [rbp+57h+P], xmm0
0x1800ea79c  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x1800ea7a0  movups  [rbp+57h+FileInformation], xmm0
0x1800ea7a4  movups  [rbp+57h+var_38], xmm0
0x1800ea7a8  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm0
0x1800ea7ac  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm0
0x1800ea7b0  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x1800ea7b6  test    eax, eax
0x1800ea7b8  js      loc_1800EA8F5
0x1800ea7be  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x1800ea7c2  mov     rdi, [rbp+57h+P+8]
0x1800ea7c6  test    ax, ax
0x1800ea7c9  jnz     loc_1800EA900
0x1800ea7cf  mov     eax, r14d
0x1800ea7d2  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x1800ea7d6  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800ea7da  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800ea7de  lea     rax, [rbp+57h+P]
0x1800ea7e2  mov     [rsp+0F0h+OpenOptions], 204020h; OpenOptions
0x1800ea7ea  xorps   xmm0, xmm0
0x1800ea7ed  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800ea7f1  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800ea7f5  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800ea7fc  mov     edx, 100100h; DesiredAccess
0x1800ea801  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800ea808  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800ea80c  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x1800ea814  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ea819  call    cs:__imp_NtOpenFile
0x1800ea81f  mov     ebx, eax
0x1800ea821  test    eax, eax
0x1800ea823  js      loc_1800EA8C0
0x1800ea829  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1800ea82d  call    cs:__imp_RtlReleaseRelativeName
0x1800ea833  mov     rcx, gs:60h
0x1800ea83c  mov     r8, rdi; P
0x1800ea83f  xor     edx, edx; Flags
0x1800ea841  mov     rcx, [rcx+30h]; HeapHandle
0x1800ea845  call    cs:__imp_RtlFreeHeap
0x1800ea84b  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800ea84f  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x1800ea853  xor     eax, eax
0x1800ea855  mov     [rsp+0F0h+ShareAccess], 4; FileInformationClass
0x1800ea85d  xorps   xmm0, xmm0
0x1800ea860  mov     [rbp+57h+var_28], rax
0x1800ea864  and     esi, 1A3127h
0x1800ea86a  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800ea86e  bts     esi, 7
0x1800ea872  lea     r9d, [rax+28h]; Length
0x1800ea876  mov     dword ptr [rbp+57h+var_28], esi
0x1800ea879  movups  [rbp+57h+FileInformation], xmm0
0x1800ea87d  movups  [rbp+57h+var_38], xmm0
0x1800ea881  call    cs:__imp_NtSetInformationFile
0x1800ea887  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800ea88b  mov     ebx, eax
0x1800ea88d  call    cs:__imp_NtClose
0x1800ea893  test    ebx, ebx
0x1800ea895  js      short loc_1800EA8EA
0x1800ea897  mov     eax, 1
0x1800ea89c  mov     rcx, [rbp+57h+var_20]
0x1800ea8a0  xor     rcx, rsp; StackCookie
0x1800ea8a3  call    __security_check_cookie
0x1800ea8a8  lea     r11, [rsp+0F0h+var_10]
0x1800ea8b0  mov     rbx, [r11+30h]
0x1800ea8b4  mov     rsi, [r11+38h]
0x1800ea8b8  mov     rsp, r11
0x1800ea8bb  pop     r14
0x1800ea8bd  pop     rdi
0x1800ea8be  pop     rbp
0x1800ea8bf  retn
0x1800ea8c0  cmp     ebx, 0C000000Dh
0x1800ea8c6  jz      short loc_1800EA923
0x1800ea8c8  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1800ea8cc  call    cs:__imp_RtlReleaseRelativeName
0x1800ea8d2  mov     rcx, gs:60h
0x1800ea8db  mov     r8, rdi; P
0x1800ea8de  xor     edx, edx; Flags
0x1800ea8e0  mov     rcx, [rcx+30h]; HeapHandle
0x1800ea8e4  call    cs:__imp_RtlFreeHeap
0x1800ea8ea  mov     ecx, ebx
0x1800ea8ec  call    BaseSetLastNTError
0x1800ea8f1  xor     eax, eax
0x1800ea8f3  jmp     short loc_1800EA89C
0x1800ea8f5  cmp     eax, 0C0000017h
0x1800ea8fa  jnz     short loc_1800EA959
0x1800ea8fc  mov     ecx, eax
0x1800ea8fe  jmp     short loc_1800EA8EC
0x1800ea900  mov     word ptr [rbp+57h+P], ax
0x1800ea904  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x1800ea907  mov     dword ptr [rbp+57h+P+2], eax
0x1800ea90a  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x1800ea90e  mov     word ptr [rbp+57h+P+6], ax
0x1800ea912  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x1800ea916  mov     [rbp+57h+P+8], rax
0x1800ea91a  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x1800ea91e  jmp     loc_1800EA7D6
0x1800ea923  mov     [rsp+0F0h+OpenOptions], 4020h; OpenOptions
0x1800ea92b  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800ea92f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800ea933  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x1800ea93b  mov     edx, 100100h; DesiredAccess
0x1800ea940  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800ea944  call    cs:__imp_NtOpenFile
0x1800ea94a  mov     ebx, eax
0x1800ea94c  test    eax, eax
0x1800ea94e  js      loc_1800EA8C8
0x1800ea954  jmp     loc_1800EA829
0x1800ea959  cmp     eax, 0C000009Ah
0x1800ea95e  jz      short loc_1800EA8FC
0x1800ea960  mov     ecx, 3; LastError
0x1800ea965  call    cs:__imp_RtlSetLastWin32Error
0x1800ea96b  jmp     short loc_1800EA8F1
```
