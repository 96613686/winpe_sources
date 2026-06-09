# GetVolumeInformationW

- ea: `0x1800b5770`
- end: `0x1800b5aa0`
- name: `GetVolumeInformationW`
- size: `816`
- prototype: `BOOL __stdcall(LPCWSTR lpRootPathName, LPWSTR lpVolumeNameBuffer, DWORD nVolumeNameSize, LPDWORD lpVolumeSerialNumber, LPDWORD lpMaximumComponentLength, LPDWORD lpFileSystemFlags, LPWSTR lpFileSystemNameBuffer, DWORD nFileSystemNameSize)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800b50b8`
- `0x1800b54d0`

## callees

- `0x1800134a0`
- `0x1800b5770`
- `0x1800b5ab0`
- `0x180188f10`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x1800b59de`
- `ntdll!NtQueryInformationFile` at `0x1800b59de`
- `ntdll!NtOpenFile` at `0x1800b588c`
- `ntdll!NtOpenFile` at `0x1800b588c`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800b5808`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800b5808`
- `ntdll!RtlSetLastWin32Error` at `0x1800b597e`
- `ntdll!RtlSetLastWin32Error` at `0x1800b5a60`
- `ntdll!RtlSetLastWin32Error` at `0x1800b597e`
- `ntdll!RtlSetLastWin32Error` at `0x1800b5a60`
- `ntdll!NtOpenSymbolicLinkObject` at `0x1800b5918`
- `ntdll!NtOpenSymbolicLinkObject` at `0x1800b5918`
- `ntdll!NtQuerySymbolicLinkObject` at `0x1800b5953`
- `ntdll!NtQuerySymbolicLinkObject` at `0x1800b5953`
- `ntdll!NtClose` at `0x1800b5960`
- `ntdll!NtClose` at `0x1800b5973`
- `ntdll!NtClose` at `0x1800b5a4e`
- `ntdll!NtClose` at `0x1800b5960`
- `ntdll!NtClose` at `0x1800b5973`
- `ntdll!NtClose` at `0x1800b5a4e`
- `ntdll!RtlFreeHeap` at `0x1800b5996`
- `ntdll!RtlFreeHeap` at `0x1800b5a11`
- `ntdll!RtlFreeHeap` at `0x1800b5a7f`
- `ntdll!RtlFreeHeap` at `0x1800b5996`
- `ntdll!RtlFreeHeap` at `0x1800b5a11`
- `ntdll!RtlFreeHeap` at `0x1800b5a7f`
- `ntdll!RtlSetThreadErrorMode` at `0x1800b5864`
- `ntdll!RtlSetThreadErrorMode` at `0x1800b589a`
- `ntdll!RtlSetThreadErrorMode` at `0x1800b5864`
- `ntdll!RtlSetThreadErrorMode` at `0x1800b589a`

## pseudocode

```c
BOOL __stdcall GetVolumeInformationW(
        LPCWSTR lpRootPathName,
        LPWSTR lpVolumeNameBuffer,
        DWORD nVolumeNameSize,
        LPDWORD lpVolumeSerialNumber,
        LPDWORD lpMaximumComponentLength,
        LPDWORD lpFileSystemFlags,
        LPWSTR lpFileSystemNameBuffer,
        DWORD nFileSystemNameSize)
{
  bool v10; // zf
  const WCHAR *v13; // rcx
  PWSTR Buffer; // rbx
  NTSTATUS v15; // edi
  NTSTATUS v16; // eax
  NTSTATUS v17; // edi
  BOOL VolumeInformationByHandleW; // ebx
  int v20; // [rsp+40h] [rbp-C0h] BYREF
  ULONG OldMode; // [rsp+44h] [rbp-BCh] BYREF
  ULONG DataWritten; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE FileHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE SymbolicLinkHandle; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING LinkTarget; // [rsp+70h] [rbp-90h] BYREF
  LPWSTR v27; // [rsp+80h] [rbp-80h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES v29; // [rsp+B8h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E8h] [rbp-18h] BYREF
  struct _IO_STATUS_BLOCK v31; // [rsp+F8h] [rbp-8h] BYREF
  _DWORD FileInformation[136]; // [rsp+110h] [rbp+10h] BYREF
  char v33; // [rsp+330h] [rbp+230h] BYREF

  v27 = lpFileSystemNameBuffer;
  FileHandle = 0;
  v10 = lpRootPathName == 0;
  OldMode = 0;
  v20 = 92;
  v13 = (const WCHAR *)&v20;
  if ( !v10 )
    v13 = lpRootPathName;
  memset(&ObjectAttributes, 0, 44);
  NtPathName = 0;
  IoStatusBlock = 0;
  if ( RtlDosPathNameToNtPathName_U(v13, &NtPathName, 0, 0) )
  {
    Buffer = NtPathName.Buffer;
    if ( NtPathName.Buffer[((unsigned __int64)NtPathName.Length >> 1) - 1] != 92 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
      BaseSetLastNTError(3221225523LL);
      return 0;
    }
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &NtPathName;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    RtlSetThreadErrorMode(0x10u, &OldMode);
    v15 = NtOpenFile(&FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 3u, 0x4021u);
    RtlSetThreadErrorMode(OldMode, 0);
    if ( v15 < 0 )
    {
      BaseSetLastNTError((unsigned int)v15);
      goto LABEL_10;
    }
    SymbolicLinkHandle = 0;
    DataWritten = 0;
    v31 = 0;
    memset(&v29, 0, 44);
    LinkTarget = 0;
    if ( !FileHandle
      || NtQueryInformationFile(FileHandle, &v31, FileInformation, 0x218u, FileNameInformation) < 0
      || *((_WORD *)&FileInformation[1] + (unsigned int)((FileInformation[0] >> 1) - 1)) != 92 )
    {
      v29.Length = 48;
      NtPathName.Length -= 2;
      v29.RootDirectory = 0;
      v29.ObjectName = &NtPathName;
      v29.Attributes = 64;
      *(_OWORD *)&v29.SecurityDescriptor = 0;
      v16 = NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &v29);
      NtPathName.Length += 2;
      if ( v16 < 0
        || (LinkTarget.Buffer = (PWSTR)&v33,
            *(_DWORD *)&LinkTarget.Length = 68157440,
            DataWritten = 0,
            v17 = NtQuerySymbolicLinkObject(SymbolicLinkHandle, &LinkTarget, &DataWritten),
            NtClose(SymbolicLinkHandle),
            v17 < 0) )
      {
        NtClose(FileHandle);
        RtlSetLastWin32Error(0x90u);
LABEL_10:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
        return 0;
      }
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    VolumeInformationByHandleW = GetVolumeInformationByHandleW(
                                   FileHandle,
                                   lpVolumeNameBuffer,
                                   nVolumeNameSize,
                                   lpVolumeSerialNumber,
                                   lpMaximumComponentLength,
                                   lpFileSystemFlags,
                                   v27,
                                   nFileSystemNameSize);
    NtClose(FileHandle);
    return VolumeInformationByHandleW;
  }
  else
  {
    RtlSetLastWin32Error(3u);
    return 0;
  }
}

```

## disassembly

```asm
0x1800b5770  push    rbp
0x1800b5772  push    rsi
0x1800b5773  push    rdi
0x1800b5774  push    r12
0x1800b5776  push    r13
0x1800b5778  push    r14
0x1800b577a  push    r15
0x1800b577c  lea     rbp, [rsp-660h]
0x1800b5784  sub     rsp, 760h
0x1800b578b  mov     rax, cs:__security_cookie
0x1800b5792  xor     rax, rsp
0x1800b5795  mov     [rbp+690h+var_50], rax
0x1800b579c  mov     rax, [rbp+690h+lpFileSystemNameBuffer]
0x1800b57a3  xorps   xmm0, xmm0
0x1800b57a6  mov     r12, [rbp+690h+lpMaximumComponentLength]
0x1800b57ad  mov     rsi, rdx
0x1800b57b0  mov     r13, [rbp+690h+lpFileSystemFlags]
0x1800b57b7  mov     rdx, rcx
0x1800b57ba  xor     edi, edi
0x1800b57bc  mov     [rbp+690h+var_710], rax
0x1800b57c0  xor     eax, eax
0x1800b57c2  mov     [rsp+790h+FileHandle], rdi
0x1800b57c7  test    rdx, rdx
0x1800b57ca  mov     [rsp+790h+OldMode], edi
0x1800b57ce  mov     r15, r9
0x1800b57d1  mov     [rsp+790h+var_750], 5Ch ; '\'
0x1800b57d9  mov     r14d, r8d
0x1800b57dc  lea     rcx, [rsp+790h+var_750]
0x1800b57e1  cmovnz  rcx, rdx; DosPathName
0x1800b57e5  xorps   xmm1, xmm1
0x1800b57e8  movups  xmmword ptr [rbp+690h+ObjectAttributes.ObjectName], xmm0
0x1800b57ec  xor     r9d, r9d; DirectoryInfo
0x1800b57ef  lea     rdx, [rsp+790h+NtPathName]; NtPathName
0x1800b57f4  xor     r8d, r8d; NtFileNamePart
0x1800b57f7  movups  xmmword ptr [rbp+690h+ObjectAttributes.Length], xmm0
0x1800b57fb  movups  xmmword ptr [rbp+690h+ObjectAttributes+1Ch], xmm0
0x1800b57ff  movups  xmmword ptr [rsp+790h+NtPathName.Length], xmm0
0x1800b5804  movups  xmmword ptr [rbp+690h+IoStatusBlock], xmm1
0x1800b5808  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800b580e  test    al, al
0x1800b5810  jz      loc_1800B5A5B
0x1800b5816  movzx   eax, [rsp+790h+NtPathName.Length]
0x1800b581b  mov     [rsp+790h+var_38], rbx
0x1800b5823  mov     rbx, [rsp+790h+NtPathName.Buffer]
0x1800b5828  shr     rax, 1
0x1800b582b  cmp     word ptr [rbx+rax*2-2], 5Ch ; '\'
0x1800b5831  jnz     loc_1800B5A6D
0x1800b5837  lea     rax, [rsp+790h+NtPathName]
0x1800b583c  mov     [rbp+690h+ObjectAttributes.Length], 30h ; '0'
0x1800b5843  xorps   xmm0, xmm0
0x1800b5846  mov     [rbp+690h+ObjectAttributes.ObjectName], rax
0x1800b584a  lea     rdx, [rsp+790h+OldMode]; OldMode
0x1800b584f  mov     [rbp+690h+ObjectAttributes.RootDirectory], rdi
0x1800b5853  mov     ecx, 10h; NewMode
0x1800b5858  mov     [rbp+690h+ObjectAttributes.Attributes], 40h ; '@'
0x1800b585f  movdqu  xmmword ptr [rbp+690h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800b5864  call    cs:__imp_RtlSetThreadErrorMode
0x1800b586a  lea     r9, [rbp+690h+IoStatusBlock]; IoStatusBlock
0x1800b586e  mov     [rsp+790h+OpenOptions], 4021h; OpenOptions
0x1800b5876  lea     r8, [rbp+690h+ObjectAttributes]; ObjectAttributes
0x1800b587a  mov     [rsp+790h+ShareAccess], 3; ShareAccess
0x1800b5882  mov     edx, 100000h; DesiredAccess
0x1800b5887  lea     rcx, [rsp+790h+FileHandle]; FileHandle
0x1800b588c  call    cs:__imp_NtOpenFile
0x1800b5892  mov     ecx, [rsp+790h+OldMode]; NewMode
0x1800b5896  xor     edx, edx; OldMode
0x1800b5898  mov     edi, eax
0x1800b589a  call    cs:__imp_RtlSetThreadErrorMode
0x1800b58a0  test    edi, edi
0x1800b58a2  js      loc_1800B5A94
0x1800b58a8  mov     rcx, [rsp+790h+FileHandle]; FileHandle
0x1800b58ad  xorps   xmm0, xmm0
0x1800b58b0  xor     eax, eax
0x1800b58b2  mov     [rsp+790h+SymbolicLinkHandle], rax
0x1800b58b7  mov     [rsp+790h+DataWritten], eax
0x1800b58bb  movups  xmmword ptr [rbp+690h+var_6D8.ObjectName], xmm0
0x1800b58bf  movups  xmmword ptr [rbp+690h+var_6D8+1Ch], xmm0
0x1800b58c3  movups  xmmword ptr [rbp+690h+var_698], xmm0
0x1800b58c7  movups  xmmword ptr [rbp+690h+var_6D8.Length], xmm0
0x1800b58cb  movups  xmmword ptr [rsp+790h+LinkTarget.Length], xmm0
0x1800b58d0  test    rcx, rcx
0x1800b58d3  jnz     loc_1800B59C8
0x1800b58d9  mov     eax, 0FFFEh
0x1800b58de  mov     [rbp+690h+var_6D8.Length], 30h ; '0'
0x1800b58e5  add     [rsp+790h+NtPathName.Length], ax
0x1800b58ea  lea     r8, [rbp+690h+var_6D8]; ObjectAttributes
0x1800b58ee  lea     rax, [rsp+790h+NtPathName]
0x1800b58f3  mov     [rbp+690h+var_6D8.RootDirectory], 0
0x1800b58fb  xorps   xmm0, xmm0
0x1800b58fe  mov     [rbp+690h+var_6D8.ObjectName], rax
0x1800b5902  mov     edx, 1; DesiredAccess
0x1800b5907  mov     [rbp+690h+var_6D8.Attributes], 40h ; '@'
0x1800b590e  lea     rcx, [rsp+790h+SymbolicLinkHandle]; SymbolicLinkHandle
0x1800b5913  movdqu  xmmword ptr [rbp+690h+var_6D8.SecurityDescriptor], xmm0
0x1800b5918  call    cs:__imp_NtOpenSymbolicLinkObject
0x1800b591e  add     [rsp+790h+NtPathName.Length], 2
0x1800b5924  test    eax, eax
0x1800b5926  js      short loc_1800B596E
0x1800b5928  mov     rcx, [rsp+790h+SymbolicLinkHandle]; SymLinkObjHandle
0x1800b592d  lea     rax, [rbp+690h+var_460]
0x1800b5934  lea     r8, [rsp+790h+DataWritten]; DataWritten
0x1800b5939  mov     [rsp+790h+LinkTarget.Buffer], rax
0x1800b593e  lea     rdx, [rsp+790h+LinkTarget]; LinkTarget
0x1800b5943  mov     dword ptr [rsp+790h+LinkTarget.Length], 4100000h
0x1800b594b  mov     [rsp+790h+DataWritten], 0
0x1800b5953  call    cs:__imp_NtQuerySymbolicLinkObject
0x1800b5959  mov     rcx, [rsp+790h+SymbolicLinkHandle]; Handle
0x1800b595e  mov     edi, eax
0x1800b5960  call    cs:__imp_NtClose
0x1800b5966  test    edi, edi
0x1800b5968  jns     loc_1800B59FF
0x1800b596e  mov     rcx, [rsp+790h+FileHandle]; Handle
0x1800b5973  call    cs:__imp_NtClose
0x1800b5979  mov     ecx, 90h; LastError
0x1800b597e  call    cs:__imp_RtlSetLastWin32Error
0x1800b5984  mov     rcx, gs:60h
0x1800b598d  mov     r8, rbx; P
0x1800b5990  xor     edx, edx; Flags
0x1800b5992  mov     rcx, [rcx+30h]; HeapHandle
0x1800b5996  call    cs:__imp_RtlFreeHeap
0x1800b599c  xor     eax, eax
0x1800b599e  mov     rbx, [rsp+790h+var_38]
0x1800b59a6  mov     rcx, [rbp+690h+var_50]
0x1800b59ad  xor     rcx, rsp; StackCookie
0x1800b59b0  call    __security_check_cookie
0x1800b59b5  add     rsp, 760h
0x1800b59bc  pop     r15
0x1800b59be  pop     r14
0x1800b59c0  pop     r13
0x1800b59c2  pop     r12
0x1800b59c4  pop     rdi
0x1800b59c5  pop     rsi
0x1800b59c6  pop     rbp
0x1800b59c7  retn
0x1800b59c8  mov     r9d, 218h; Length
0x1800b59ce  mov     [rsp+790h+ShareAccess], 9; FileInformationClass
0x1800b59d6  lea     r8, [rbp+690h+FileInformation]; FileInformation
0x1800b59da  lea     rdx, [rbp+690h+var_698]; IoStatusBlock
0x1800b59de  call    cs:__imp_NtQueryInformationFile
0x1800b59e4  test    eax, eax
0x1800b59e6  js      loc_1800B58D9
0x1800b59ec  mov     eax, [rbp+690h+FileInformation]
0x1800b59ef  shr     eax, 1
0x1800b59f1  dec     eax
0x1800b59f3  cmp     [rbp+rax*2+690h+var_67C], 5Ch ; '\'
0x1800b59f9  jnz     loc_1800B58D9
0x1800b59ff  mov     rcx, gs:60h
0x1800b5a08  mov     r8, rbx; P
0x1800b5a0b  xor     edx, edx; Flags
0x1800b5a0d  mov     rcx, [rcx+30h]; HeapHandle
0x1800b5a11  call    cs:__imp_RtlFreeHeap
0x1800b5a17  mov     eax, [rbp+690h+nFileSystemNameSize]
0x1800b5a1d  mov     r9, r15; lpVolumeSerialNumber
0x1800b5a20  mov     rcx, [rsp+790h+FileHandle]; hFile
0x1800b5a25  mov     r8d, r14d; nVolumeNameSize
0x1800b5a28  mov     [rsp+790h+var_758], eax; nFileSystemNameSize
0x1800b5a2c  mov     rdx, rsi; lpVolumeNameBuffer
0x1800b5a2f  mov     rax, [rbp+690h+var_710]
0x1800b5a33  mov     [rsp+790h+var_760], rax; lpFileSystemNameBuffer
0x1800b5a38  mov     qword ptr [rsp+790h+OpenOptions], r13; lpFileSystemFlags
0x1800b5a3d  mov     qword ptr [rsp+790h+ShareAccess], r12; lpMaximumComponentLength
0x1800b5a42  call    GetVolumeInformationByHandleW
0x1800b5a47  mov     rcx, [rsp+790h+FileHandle]; Handle
0x1800b5a4c  mov     ebx, eax
0x1800b5a4e  call    cs:__imp_NtClose
0x1800b5a54  mov     eax, ebx
0x1800b5a56  jmp     loc_1800B599E
0x1800b5a5b  mov     ecx, 3; LastError
0x1800b5a60  call    cs:__imp_RtlSetLastWin32Error
0x1800b5a66  xor     eax, eax
0x1800b5a68  jmp     loc_1800B59A6
0x1800b5a6d  mov     rcx, gs:60h
0x1800b5a76  mov     r8, rbx; P
0x1800b5a79  xor     edx, edx; Flags
0x1800b5a7b  mov     rcx, [rcx+30h]; HeapHandle
0x1800b5a7f  call    cs:__imp_RtlFreeHeap
0x1800b5a85  mov     ecx, 0C0000033h
0x1800b5a8a  call    BaseSetLastNTError
0x1800b5a8f  jmp     loc_1800B599C
0x1800b5a94  mov     ecx, edi
0x1800b5a96  call    BaseSetLastNTError
0x1800b5a9b  jmp     loc_1800B5984
```
