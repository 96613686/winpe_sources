# GetDriveTypeW

- ea: `0x180047c90`
- end: `0x1800481db`
- name: `GetDriveTypeW`
- size: `1355`
- prototype: `UINT __stdcall(LPCWSTR lpRootPathName)`
- caller_count: `4`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180045e50`
- `0x180045ec0`
- `0x180046310`
- `0x1800464e0`

## callees

- `0x180047c90`
- `0x1800481f0`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180048044`
- `ntdll!RtlInitUnicodeString` at `0x180048044`
- `ntdll!NtOpenFile` at `0x180047e5f`
- `ntdll!NtOpenFile` at `0x180047f9d`
- `ntdll!NtOpenFile` at `0x180047e5f`
- `ntdll!NtOpenFile` at `0x180047f9d`
- `ntdll!wcslen` at `0x180047d13`
- `ntdll!wcslen` at `0x180047d13`
- `ntdll!RtlUpcaseUnicodeChar` at `0x180047d26`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18004808f`
- `ntdll!RtlUpcaseUnicodeChar` at `0x180047d26`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18004808f`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180047dd7`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180047dd7`
- `ntdll!NtQueryVolumeInformationFile` at `0x180047fe6`
- `ntdll!NtQueryVolumeInformationFile` at `0x180047fe6`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180047ec1`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180047ec1`
- `ntdll!NtQuerySymbolicLinkObject` at `0x180047efe`
- `ntdll!NtQuerySymbolicLinkObject` at `0x180047efe`
- `ntdll!wcsncpy_s` at `0x1800480c0`
- `ntdll!wcsncpy_s` at `0x1800480c0`
- `ntdll!NtClose` at `0x180047f0b`
- `ntdll!NtClose` at `0x180047f30`
- `ntdll!NtClose` at `0x180048016`
- `ntdll!NtClose` at `0x18004802b`
- `ntdll!NtClose` at `0x180048109`
- `ntdll!NtClose` at `0x180047f0b`
- `ntdll!NtClose` at `0x180047f30`
- `ntdll!NtClose` at `0x180048016`
- `ntdll!NtClose` at `0x18004802b`
- `ntdll!NtClose` at `0x180048109`
- `ntdll!NtQueryInformationProcess` at `0x180047d6c`
- `ntdll!NtQueryInformationProcess` at `0x180047d6c`
- `ntdll!RtlFreeHeap` at `0x180047f4a`
- `ntdll!RtlFreeHeap` at `0x180047fb7`
- `ntdll!RtlFreeHeap` at `0x180047f4a`
- `ntdll!RtlFreeHeap` at `0x180047fb7`
- `ntdll!RtlGetCurrentDirectory_U` at `0x180048158`
- `ntdll!RtlGetCurrentDirectory_U` at `0x180048158`

## pseudocode

```c
UINT __stdcall GetDriveTypeW(LPCWSTR lpRootPathName)
{
  WCHAR *v2; // rdi
  WCHAR v3; // ax
  int v4; // esi
  int v5; // eax
  __int64 v6; // rcx
  int v7; // ecx
  UINT result; // eax
  const WCHAR *v9; // rcx
  PWSTR Buffer; // rdi
  NTSTATUS v11; // esi
  NTSTATUS v12; // eax
  USHORT Length; // cx
  NTSTATUS v14; // ebx
  UINT v15; // ebx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  HANDLE FileHandle; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+38h] [rbp-C8h] BYREF
  ULONG DataWritten; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE SymbolicLinkHandle; // [rsp+50h] [rbp-B0h] BYREF
  __int64 FsInformation; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING LinkTarget; // [rsp+A0h] [rbp-60h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-50h] BYREF
  __int128 ProcessInformation; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v29; // [rsp+D0h] [rbp-30h]
  __int64 v30; // [rsp+E0h] [rbp-20h]
  struct _OBJECT_ATTRIBUTES v31; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v32; // [rsp+118h] [rbp+18h]
  wchar_t Destination[2]; // [rsp+130h] [rbp+30h] BYREF
  int v34; // [rsp+134h] [rbp+34h]
  WCHAR SourceString[264]; // [rsp+340h] [rbp+240h] BYREF
  char v36; // [rsp+550h] [rbp+450h] BYREF

  FileHandle = 0;
  FsInformation = 0;
  v30 = 0;
  memset(&ObjectAttributes, 0, 44);
  NtPathName = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  ProcessInformation = 0;
  v29 = 0;
  if ( lpRootPathName )
  {
    if ( lpRootPathName == (LPCWSTR)-1LL )
      return 0;
    v2 = (WCHAR *)lpRootPathName;
    if ( wcslen(lpRootPathName) == 2
      && (unsigned __int16)(RtlUpcaseUnicodeChar(*lpRootPathName) - 65) <= 0x19u
      && lpRootPathName[1] == 58 )
    {
      wcsncpy_s(Destination, 0x104u, lpRootPathName, 2u);
      v2 = Destination;
      v34 = 92;
    }
  }
  else
  {
    v2 = Destination;
    if ( RtlGetCurrentDirectory_U(0x208u, Destination) > 6 )
      HIWORD(v34) = 0;
  }
  v3 = RtlUpcaseUnicodeChar(*v2);
  v4 = v3;
  if ( (unsigned __int16)(v3 - 65) > 0x19u || v2[1] != 58 || v2[2] != 92 || v2[3] )
    goto LABEL_13;
  if ( NtQueryInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessDeviceMap, &ProcessInformation, 0x24u, 0) < 0 )
  {
    ProcessInformation = 0;
    v30 = 0;
    v29 = 0;
  }
  v5 = ProcessInformation;
  v6 = (unsigned int)(v4 - 65);
  if ( !_bittest(&v5, v6) )
    goto LABEL_13;
  v7 = *((unsigned __int8 *)&ProcessInformation + v6 + 4);
  if ( v7 == 3 )
    return 3;
  if ( !v7 )
    return 0;
  v16 = v7 - 2;
  if ( !v16 )
    return 2;
  v17 = v16 - 2;
  if ( !v17 )
    return 4;
  v18 = v17 - 1;
  if ( !v18 )
    return 5;
  if ( v18 == 1 )
    return 6;
LABEL_13:
  v9 = L"\\";
  if ( lpRootPathName )
    v9 = v2;
  if ( !RtlDosPathNameToNtPathName_U(v9, &NtPathName, 0, 0) )
    return 1;
  Buffer = NtPathName.Buffer;
  if ( NtPathName.Buffer[((unsigned __int64)NtPathName.Length >> 1) - 1] != 92 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
    return 1;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  NtPathName.Length -= 2;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtPathName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v11 = NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 3u, 0x60u);
  if ( v11 == -1073741638 )
  {
    if ( (unsigned int)BasepGetVolumeNameFromReparsePoint(lpRootPathName, SourceString, 0x104u) )
    {
      RtlInitUnicodeString(&DestinationString, SourceString);
      DestinationString.Buffer[1] = 63;
      DestinationString.Length -= 2;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    }
  }
  else
  {
    *(_QWORD *)&v31.Length = 48;
    v31.ObjectName = &NtPathName;
    *(_QWORD *)&v31.Attributes = 64;
    v32 = 0;
    SymbolicLinkHandle = 0;
    LinkTarget = 0;
    DataWritten = 0;
    v31.RootDirectory = 0;
    *(_OWORD *)&v31.SecurityDescriptor = 0;
    v12 = NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &v31);
    Length = NtPathName.Length + 2;
    NtPathName.Length += 2;
    if ( v12 >= 0 )
    {
      LinkTarget.Buffer = (PWSTR)&v36;
      *(_DWORD *)&LinkTarget.Length = 68157440;
      DataWritten = 0;
      v14 = NtQuerySymbolicLinkObject(SymbolicLinkHandle, &LinkTarget, &DataWritten);
      NtClose(SymbolicLinkHandle);
      if ( v14 >= 0 )
        goto LABEL_28;
      Length = NtPathName.Length;
    }
    NtPathName.Length = Length - 2;
    if ( v11 >= 0 )
      NtClose(FileHandle);
  }
  v11 = NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
LABEL_28:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( v11 < 0 )
    return 1;
  v15 = 4;
  if ( NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &FsInformation, 8u, FileFsDeviceInformation) < 0 )
  {
LABEL_34:
    NtClose(FileHandle);
    return 0;
  }
  if ( (FsInformation & 0x1000000000LL) != 0 )
  {
LABEL_33:
    NtClose(FileHandle);
    return v15;
  }
  if ( (_DWORD)FsInformation == 8 )
  {
LABEL_32:
    v15 = ((FsInformation & 0x100000000LL) == 0) | 2;
    goto LABEL_33;
  }
  switch ( (int)FsInformation )
  {
    case 2:
    case 3:
      NtClose(FileHandle);
      result = 5;
      break;
    case 7:
      goto LABEL_32;
    case 18:
    case 20:
      goto LABEL_33;
    case 36:
      v15 = 6;
      goto LABEL_33;
    default:
      goto LABEL_34;
  }
  return result;
}

```

## disassembly

```asm
0x180047c90  mov     [rsp-8+arg_10], rbx
0x180047c95  mov     [rsp-8+arg_18], rsi
0x180047c9a  push    rbp
0x180047c9b  push    rdi
0x180047c9c  push    r14
0x180047c9e  lea     rbp, [rsp-870h]
0x180047ca6  sub     rsp, 970h
0x180047cad  mov     rax, cs:__security_cookie
0x180047cb4  xor     rax, rsp
0x180047cb7  mov     [rbp+880h+var_20], rax
0x180047cbe  xorps   xmm0, xmm0
0x180047cc1  xor     r14d, r14d
0x180047cc4  xorps   xmm1, xmm1
0x180047cc7  mov     [rsp+980h+FileHandle], r14
0x180047ccc  xor     eax, eax
0x180047cce  mov     [rsp+980h+FsInformation], r14
0x180047cd3  mov     [rbp+880h+var_8A0], rax
0x180047cd7  mov     rbx, rcx
0x180047cda  movups  xmmword ptr [rbp+880h+ObjectAttributes.ObjectName], xmm0
0x180047cde  movups  xmmword ptr [rbp+880h+ObjectAttributes+1Ch], xmm0
0x180047ce2  movups  xmmword ptr [rsp+980h+ObjectAttributes.Length], xmm0
0x180047ce7  movups  xmmword ptr [rsp+980h+NtPathName.Length], xmm0
0x180047cec  movups  xmmword ptr [rsp+980h+DestinationString.Length], xmm1
0x180047cf1  movups  xmmword ptr [rbp+880h+IoStatusBlock], xmm0
0x180047cf5  movups  [rbp+880h+ProcessInformation], xmm1
0x180047cf9  movups  [rbp+880h+var_8B0], xmm1
0x180047cfd  test    rcx, rcx
0x180047d00  jz      loc_18004814B
0x180047d06  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180047d0a  jz      loc_180048085
0x180047d10  mov     rdi, rcx
0x180047d13  call    cs:__imp_wcslen
0x180047d19  cmp     rax, 2
0x180047d1d  jz      loc_18004808C
0x180047d23  movzx   ecx, word ptr [rdi]; Source
0x180047d26  call    cs:__imp_RtlUpcaseUnicodeChar
0x180047d2c  movzx   esi, ax
0x180047d2f  lea     ecx, [rsi-41h]
0x180047d32  cmp     cx, 19h
0x180047d36  ja      loc_180047DBE
0x180047d3c  cmp     word ptr [rdi+2], 3Ah ; ':'
0x180047d41  jnz     short loc_180047DBE
0x180047d43  cmp     word ptr [rdi+4], 5Ch ; '\'
0x180047d48  jnz     short loc_180047DBE
0x180047d4a  cmp     [rdi+6], r14w
0x180047d4f  jnz     short loc_180047DBE
0x180047d51  mov     r9d, 24h ; '$'; ProcessInformationLength
0x180047d57  mov     [rsp+980h+ReturnLength], r14; ReturnLength
0x180047d5c  lea     r8, [rbp+880h+ProcessInformation]; ProcessInformation
0x180047d60  mov     edx, 17h; ProcessInformationClass
0x180047d65  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180047d6c  call    cs:__imp_NtQueryInformationProcess
0x180047d72  test    eax, eax
0x180047d74  js      loc_180048171
0x180047d7a  mov     eax, dword ptr [rbp+880h+ProcessInformation]
0x180047d7d  mov     ecx, esi
0x180047d7f  add     ecx, 0FFFFFFBFh
0x180047d82  bt      eax, ecx
0x180047d85  jnb     short loc_180047DBE
0x180047d87  movzx   ecx, byte ptr [rbp+rcx+880h+ProcessInformation+4]
0x180047d8c  cmp     ecx, 3
0x180047d8f  jnz     loc_180048116
0x180047d95  mov     eax, ecx
0x180047d97  mov     rcx, [rbp+880h+var_20]
0x180047d9e  xor     rcx, rsp; StackCookie
0x180047da1  call    __security_check_cookie
0x180047da6  lea     r11, [rsp+980h+var_10]
0x180047dae  mov     rbx, [r11+30h]
0x180047db2  mov     rsi, [r11+38h]
0x180047db6  mov     rsp, r11
0x180047db9  pop     r14
0x180047dbb  pop     rdi
0x180047dbc  pop     rbp
0x180047dbd  retn
0x180047dbe  test    rbx, rbx
0x180047dc1  lea     rcx, asc_180290A34; "\\"
0x180047dc8  lea     rdx, [rsp+980h+NtPathName]; NtPathName
0x180047dcd  cmovnz  rcx, rdi; DosPathName
0x180047dd1  xor     r9d, r9d; DirectoryInfo
0x180047dd4  xor     r8d, r8d; NtFileNamePart
0x180047dd7  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180047ddd  test    al, al
0x180047ddf  jz      loc_180047F50
0x180047de5  movzx   ecx, [rsp+980h+NtPathName.Length]
0x180047dea  mov     rdi, [rsp+980h+NtPathName.Buffer]
0x180047def  mov     eax, ecx
0x180047df1  shr     rax, 1
0x180047df4  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x180047dfa  jnz     loc_180047F38
0x180047e00  lea     rax, [rsp+980h+NtPathName]
0x180047e05  mov     [rsp+980h+arg_8], r15
0x180047e0d  xorps   xmm0, xmm0
0x180047e10  mov     [rsp+980h+OpenOptions], 60h ; '`'; OpenOptions
0x180047e18  mov     r15d, 0FFFEh
0x180047e1e  mov     [rsp+980h+ObjectAttributes.Length], 30h ; '0'
0x180047e26  add     cx, r15w
0x180047e2a  mov     [rsp+980h+ObjectAttributes.RootDirectory], r14
0x180047e2f  mov     [rsp+980h+NtPathName.Length], cx
0x180047e34  lea     r9, [rbp+880h+IoStatusBlock]; IoStatusBlock
0x180047e38  lea     rcx, [rsp+980h+FileHandle]; FileHandle
0x180047e3d  mov     [rbp+880h+ObjectAttributes.Attributes], 40h ; '@'
0x180047e44  lea     r8, [rsp+980h+ObjectAttributes]; ObjectAttributes
0x180047e49  mov     [rbp+880h+ObjectAttributes.ObjectName], rax
0x180047e4d  mov     edx, 100080h; DesiredAccess
0x180047e52  mov     dword ptr [rsp+980h+ReturnLength], 3; ShareAccess
0x180047e5a  movdqu  xmmword ptr [rbp+880h+ObjectAttributes.SecurityDescriptor], xmm0
0x180047e5f  call    cs:__imp_NtOpenFile
0x180047e65  mov     esi, eax
0x180047e67  cmp     eax, 0C00000BAh
0x180047e6c  jz      loc_180047F5A
0x180047e72  movzx   eax, [rsp+980h+NtPathName.Length]
0x180047e77  lea     r8, [rbp+880h+var_898]; ObjectAttributes
0x180047e7b  xorps   xmm0, xmm0
0x180047e7e  mov     [rsp+980h+NtPathName.Length], ax
0x180047e83  lea     rax, [rsp+980h+NtPathName]
0x180047e88  mov     qword ptr [rbp+880h+var_898.Length], 30h ; '0'
0x180047e90  mov     edx, 1; DesiredAccess
0x180047e95  mov     [rbp+880h+var_898.ObjectName], rax
0x180047e99  lea     rcx, [rsp+980h+SymbolicLinkHandle]; SymbolicLinkHandle
0x180047e9e  mov     qword ptr [rbp+880h+var_898.Attributes], 40h ; '@'
0x180047ea6  movups  [rbp+880h+var_868], xmm0
0x180047eaa  mov     [rsp+980h+SymbolicLinkHandle], r14
0x180047eaf  movups  xmmword ptr [rbp+880h+LinkTarget.Length], xmm0
0x180047eb3  mov     [rsp+980h+DataWritten], r14d
0x180047eb8  mov     [rbp+880h+var_898.RootDirectory], r14
0x180047ebc  movdqu  xmmword ptr [rbp+880h+var_898.SecurityDescriptor], xmm0
0x180047ec1  call    cs:__imp_NtOpenSymbolicLinkObject
0x180047ec7  movzx   ecx, [rsp+980h+NtPathName.Length]
0x180047ecc  add     cx, 2
0x180047ed0  mov     [rsp+980h+NtPathName.Length], cx
0x180047ed5  test    eax, eax
0x180047ed7  js      short loc_180047F1E
0x180047ed9  mov     rcx, [rsp+980h+SymbolicLinkHandle]; SymLinkObjHandle
0x180047ede  lea     rax, [rbp+880h+var_430]
0x180047ee5  lea     r8, [rsp+980h+DataWritten]; DataWritten
0x180047eea  mov     [rbp+880h+LinkTarget.Buffer], rax
0x180047eee  lea     rdx, [rbp+880h+LinkTarget]; LinkTarget
0x180047ef2  mov     dword ptr [rbp+880h+LinkTarget.Length], 4100000h
0x180047ef9  mov     [rsp+980h+DataWritten], r14d
0x180047efe  call    cs:__imp_NtQuerySymbolicLinkObject
0x180047f04  mov     rcx, [rsp+980h+SymbolicLinkHandle]; Handle
0x180047f09  mov     ebx, eax
0x180047f0b  call    cs:__imp_NtClose
0x180047f11  test    ebx, ebx
0x180047f13  jns     loc_180047FA5
0x180047f19  movzx   ecx, [rsp+980h+NtPathName.Length]
0x180047f1e  add     cx, r15w
0x180047f22  mov     [rsp+980h+NtPathName.Length], cx
0x180047f27  test    esi, esi
0x180047f29  js      short loc_180047F7A
0x180047f2b  mov     rcx, [rsp+980h+FileHandle]; Handle
0x180047f30  call    cs:__imp_NtClose
0x180047f36  jmp     short loc_180047F7A
0x180047f38  mov     rcx, gs:60h
0x180047f41  mov     r8, rdi; P
0x180047f44  xor     edx, edx; Flags
0x180047f46  mov     rcx, [rcx+30h]; HeapHandle
0x180047f4a  call    cs:__imp_RtlFreeHeap
0x180047f50  mov     eax, 1
0x180047f55  jmp     loc_180047D97
0x180047f5a  xor     r9d, r9d
0x180047f5d  lea     rdx, [rbp+880h+SourceString]; void *
0x180047f64  mov     r8d, 104h; cchFilePath
0x180047f6a  mov     rcx, rbx; lpFileName
0x180047f6d  call    BasepGetVolumeNameFromReparsePoint
0x180047f72  test    eax, eax
0x180047f74  jnz     loc_180048038
0x180047f7a  mov     [rsp+980h+OpenOptions], 20h ; ' '; OpenOptions
0x180047f82  lea     r9, [rbp+880h+IoStatusBlock]; IoStatusBlock
0x180047f86  lea     r8, [rsp+980h+ObjectAttributes]; ObjectAttributes
0x180047f8b  mov     dword ptr [rsp+980h+ReturnLength], 3; ShareAccess
0x180047f93  mov     edx, 100080h; DesiredAccess
0x180047f98  lea     rcx, [rsp+980h+FileHandle]; FileHandle
0x180047f9d  call    cs:__imp_NtOpenFile
0x180047fa3  mov     esi, eax
0x180047fa5  mov     rcx, gs:60h
0x180047fae  mov     r8, rdi; P
0x180047fb1  xor     edx, edx; Flags
0x180047fb3  mov     rcx, [rcx+30h]; HeapHandle
0x180047fb7  call    cs:__imp_RtlFreeHeap
0x180047fbd  mov     r15, [rsp+980h+arg_8]
0x180047fc5  test    esi, esi
0x180047fc7  js      short loc_180047F50
0x180047fc9  mov     rcx, [rsp+980h+FileHandle]; FileHandle
0x180047fce  lea     r8, [rsp+980h+FsInformation]; FsInformation
0x180047fd3  mov     ebx, 4
0x180047fd8  lea     rdx, [rbp+880h+IoStatusBlock]; IoStatusBlock
0x180047fdc  mov     r9d, 8; Length
0x180047fe2  mov     dword ptr [rsp+980h+ReturnLength], ebx; FsInformationClass
0x180047fe6  call    cs:__imp_NtQueryVolumeInformationFile
0x180047fec  test    eax, eax
0x180047fee  js      short def_1800480FD; jumptable 00000001800480FD default case, cases 4-6,8-17,19,21-35
0x180047ff0  mov     edx, dword ptr [rsp+980h+FsInformation+4]
0x180047ff4  test    dl, 10h
0x180047ff7  jnz     short loc_180048011; jumptable 00000001800480FD cases 18,20
0x180047ff9  mov     eax, dword ptr [rsp+980h+FsInformation]
0x180047ffd  cmp     eax, 8
0x180048000  jnz     loc_1800480D6
0x180048006  movzx   ebx, dl; jumptable 00000001800480FD case 7
0x180048009  not     bl
0x18004800b  and     ebx, 1
0x18004800e  or      ebx, 2
0x180048011  mov     rcx, [rsp+980h+FileHandle]; jumptable 00000001800480FD cases 18,20
0x180048016  call    cs:__imp_NtClose
0x18004801c  mov     eax, ebx
0x18004801e  jmp     loc_180047D97
0x180048023  mov     rcx, [rsp+980h+FileHandle]; jumptable 00000001800480FD default case, cases 4-6,8-17,19,21-35
0x180048028  mov     ebx, r14d
0x18004802b  call    cs:__imp_NtClose
0x180048031  mov     eax, ebx
0x180048033  jmp     loc_180047D97
0x180048038  lea     rdx, [rbp+880h+SourceString]; SourceString
0x18004803f  lea     rcx, [rsp+980h+DestinationString]; DestinationString
0x180048044  call    cs:__imp_RtlInitUnicodeString
0x18004804a  mov     rax, [rsp+980h+DestinationString.Buffer]
0x18004804f  xorps   xmm0, xmm0
0x180048052  mov     word ptr [rax+2], 3Fh ; '?'
0x180048058  lea     rax, [rsp+980h+DestinationString]
0x18004805d  add     [rsp+980h+DestinationString.Length], r15w
0x180048063  mov     [rbp+880h+ObjectAttributes.ObjectName], rax
0x180048067  mov     [rsp+980h+ObjectAttributes.Length], 30h ; '0'
0x18004806f  mov     [rsp+980h+ObjectAttributes.RootDirectory], r14
0x180048074  mov     [rbp+880h+ObjectAttributes.Attributes], 40h ; '@'
0x18004807b  movdqu  xmmword ptr [rbp+880h+ObjectAttributes.SecurityDescriptor], xmm0
0x180048080  jmp     loc_180047F7A
0x180048085  xor     eax, eax
0x180048087  jmp     loc_180047D97
0x18004808c  movzx   ecx, word ptr [rbx]; Source
0x18004808f  call    cs:__imp_RtlUpcaseUnicodeChar
0x180048095  sub     ax, 41h ; 'A'
0x180048099  cmp     ax, 19h
0x18004809d  ja      loc_180047D23
0x1800480a3  cmp     word ptr [rbx+2], 3Ah ; ':'
0x1800480a8  jnz     loc_180047D23
0x1800480ae  mov     r9d, 2; MaxCount
0x1800480b4  lea     rcx, [rbp+880h+Destination]; Destination
0x1800480b8  mov     r8, rbx; Source
0x1800480bb  mov     edx, 104h; SizeInWords
0x1800480c0  call    cs:__imp_wcsncpy_s
0x1800480c6  lea     rdi, [rbp+880h+Destination]
0x1800480ca  mov     [rbp+880h+var_84C], 5Ch ; '\'
0x1800480d1  jmp     loc_180047D23
0x1800480d6  add     eax, 0FFFFFFFEh; switch 35 cases
0x1800480d9  cmp     eax, 22h
0x1800480dc  ja      def_1800480FD; jumptable 00000001800480FD default case, cases 4-6,8-17,19,21-35
0x1800480e2  lea     r8, __ImageBase
0x1800480e9  movzx   eax, ds:(byte_1800481B8 - 180000000h)[r8+rax]
0x1800480f2  mov     ecx, ds:(jpt_1800480FD - 180000000h)[r8+rax*4]
0x1800480fa  add     rcx, r8
0x1800480fd  jmp     rcx; switch jump
0x1800480ff  mov     rcx, [rsp+980h+FileHandle]; jumptable 00000001800480FD cases 2,3
0x180048104  mov     ebx, 5
0x180048109  call    cs:__imp_NtClose
0x18004810f  mov     eax, ebx
0x180048111  jmp     loc_180047D97
0x180048116  test    ecx, ecx
0x180048118  jz      loc_180048085
0x18004811e  sub     ecx, 2
0x180048121  jz      short loc_180048132
0x180048123  sub     ecx, 2
0x180048126  jnz     short loc_18004813C
0x180048128  mov     eax, 4
0x18004812d  jmp     loc_180047D97
0x180048132  mov     eax, 2
0x180048137  jmp     loc_180047D97
0x18004813c  sub     ecx, 1
0x18004813f  jnz     short loc_180048187
0x180048141  mov     eax, 5
0x180048146  jmp     loc_180047D97
0x18004814b  lea     rdx, [rbp+880h+Destination]; Buffer
0x18004814f  mov     ecx, 208h; MaximumLength
0x180048154  lea     rdi, [rbp+880h+Destination]
0x180048158  call    cs:__imp_RtlGetCurrentDirectory_U
0x18004815e  cmp     eax, 6
0x180048161  jbe     loc_180047D23
0x180048167  mov     word ptr [rbp+880h+var_84C+2], r14w
0x18004816c  jmp     loc_180047D23
0x180048171  xorps   xmm0, xmm0
0x180048174  xor     eax, eax
0x180048176  movups  [rbp+880h+ProcessInformation], xmm0
0x18004817a  mov     [rbp+880h+var_8A0], rax
0x18004817e  movups  [rbp+880h+var_8B0], xmm0
0x180048182  jmp     loc_180047D7A
0x180048187  cmp     ecx, 1
0x18004818a  jnz     loc_180047DBE
0x180048190  mov     eax, 6
0x180048195  jmp     loc_180047D97
0x18004819a  mov     ebx, 6; jumptable 00000001800480FD case 36
0x18004819f  jmp     loc_180048011; jumptable 00000001800480FD cases 18,20
```
