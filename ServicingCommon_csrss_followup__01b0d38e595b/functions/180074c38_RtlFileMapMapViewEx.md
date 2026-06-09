# RtlFileMapMapViewEx

- ea: `0x180074c38`
- end: `0x180074e0c`
- name: `RtlFileMapMapViewEx`
- size: `468`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180018de4`

## callees

- `0x18002d2b0`
- `0x180074c38`

## import_xrefs

- `ntdll!ZwUnmapViewOfSection` at `0x180074ddc`
- `ntdll!ZwUnmapViewOfSection` at `0x180074ddc`
- `ntdll!ZwCreateSection` at `0x180074d19`
- `ntdll!ZwCreateSection` at `0x180074d19`
- `ntdll!ZwMapViewOfSection` at `0x180074d71`
- `ntdll!ZwMapViewOfSection` at `0x180074d71`
- `ntdll!ZwQueryInformationFile` at `0x180074cb5`
- `ntdll!ZwQueryInformationFile` at `0x180074cb5`
- `ntdll!ZwClose` at `0x180074dc3`
- `ntdll!ZwClose` at `0x180074dc3`

## pseudocode

```c
__int64 __fastcall RtlFileMapMapViewEx(__int64 a1)
{
  NTSTATUS v2; // edi
  void *v3; // rcx
  PVOID v4; // rdx
  __int64 v5; // rax
  HANDLE FileHandle; // [rsp+30h] [rbp-49h]
  void *SectionHandle; // [rsp+50h] [rbp-29h] BYREF
  PVOID BaseAddress; // [rsp+58h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-19h] BYREF
  ULONG_PTR ViewSize; // [rsp+90h] [rbp+17h] BYREF
  __int128 FileInformation; // [rsp+98h] [rbp+1Fh] BYREF
  __int64 v13; // [rsp+A8h] [rbp+2Fh]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp+37h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v13 = 0;
  SectionHandle = 0;
  BaseAddress = 0;
  IoStatusBlock = 0;
  ViewSize = 0;
  FileInformation = 0;
  if ( *(_QWORD *)(a1 + 24) )
  {
    return (unsigned int)-1073741554;
  }
  else
  {
    v2 = ZwQueryInformationFile(*(HANDLE *)a1, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
    if ( v2 < 0
      || (FileHandle = *(HANDLE *)a1,
          ObjectAttributes.Length = 48,
          memset(&ObjectAttributes.RootDirectory, 0, 20),
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0,
          v2 = ZwCreateSection(&SectionHandle, 0xF0005u, &ObjectAttributes, 0, 2u, 0x8000000u, FileHandle),
          v2 < 0)
      || (v2 = ZwMapViewOfSection(
                 SectionHandle,
                 (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                 &BaseAddress,
                 0,
                 0,
                 0,
                 &ViewSize,
                 ViewUnmap,
                 0x500000u,
                 2u),
          v2 < 0) )
    {
      v3 = SectionHandle;
      v4 = BaseAddress;
    }
    else
    {
      v3 = 0;
      *(_QWORD *)(a1 + 8) = SectionHandle;
      v4 = 0;
      v2 = 0;
      *(_QWORD *)(a1 + 24) = BaseAddress;
      v5 = *((_QWORD *)&FileInformation + 1);
      *(_QWORD *)(a1 + 32) = *((_QWORD *)&FileInformation + 1);
      *(_QWORD *)(a1 + 16) = v5;
      *(_DWORD *)(a1 + 41) = 257;
      SectionHandle = 0;
      BaseAddress = 0;
    }
    if ( v3 )
    {
      ZwClose(v3);
      v4 = BaseAddress;
    }
    if ( v4 )
      ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, v4);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180074c38  mov     [rsp-8+arg_8], rbx
0x180074c3d  mov     [rsp-8+arg_10], rdi
0x180074c42  push    rbp
0x180074c43  lea     rbp, [rsp-57h]
0x180074c48  sub     rsp, 0D0h
0x180074c4f  mov     rax, cs:__security_cookie
0x180074c56  xor     rax, rsp
0x180074c59  mov     [rbp+57h+var_10], rax
0x180074c5d  xor     eax, eax
0x180074c5f  xorps   xmm0, xmm0
0x180074c62  xorps   xmm1, xmm1
0x180074c65  mov     rbx, rcx
0x180074c68  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180074c6c  mov     [rbp+57h+var_28], rax
0x180074c70  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180074c74  mov     [rbp+57h+SectionHandle], rax
0x180074c78  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180074c7c  mov     [rbp+57h+BaseAddress], rax
0x180074c80  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180074c84  mov     [rbp+57h+ViewSize], rax
0x180074c88  movups  [rbp+57h+FileInformation], xmm1
0x180074c8c  cmp     [rcx+18h], rax
0x180074c90  jz      short loc_180074C9C
0x180074c92  mov     edi, 0C000010Eh
0x180074c97  jmp     loc_180074DE8
0x180074c9c  mov     rcx, [rcx]; FileHandle
0x180074c9f  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x180074ca3  mov     r9d, 18h; Length
0x180074ca9  mov     [rsp+0D0h+FileInformationClass], 5; FileInformationClass
0x180074cb1  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180074cb5  call    cs:__imp_ZwQueryInformationFile
0x180074cbc  nop     dword ptr [rax+rax+00h]
0x180074cc1  mov     edi, eax
0x180074cc3  test    eax, eax
0x180074cc5  js      loc_180074DB6
0x180074ccb  mov     rax, [rbx]
0x180074cce  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180074cd2  mov     [rsp+0D0h+FileHandle], rax; FileHandle
0x180074cd7  lea     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x180074cdb  xorps   xmm0, xmm0
0x180074cde  mov     [rsp+0D0h+AllocationAttributes], 8000000h; AllocationAttributes
0x180074ce6  xor     r9d, r9d; MaximumSize
0x180074ce9  mov     [rsp+0D0h+FileInformationClass], 2; SectionPageProtection
0x180074cf1  mov     edx, 0F0005h; DesiredAccess
0x180074cf6  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180074cfd  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180074d05  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x180074d0c  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x180074d14  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180074d19  call    cs:__imp_ZwCreateSection
0x180074d20  nop     dword ptr [rax+rax+00h]
0x180074d25  mov     edi, eax
0x180074d27  test    eax, eax
0x180074d29  js      loc_180074DB6
0x180074d2f  mov     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x180074d33  lea     rax, [rbp+57h+ViewSize]
0x180074d37  mov     [rsp+0D0h+Win32Protect], 2; Win32Protect
0x180074d3f  lea     r8, [rbp+57h+BaseAddress]; BaseAddress
0x180074d43  mov     [rsp+0D0h+AllocationType], 500000h; AllocationType
0x180074d4b  xor     r9d, r9d; ZeroBits
0x180074d4e  mov     [rsp+0D0h+InheritDisposition], 2; InheritDisposition
0x180074d56  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180074d5a  mov     [rsp+0D0h+FileHandle], rax; ViewSize
0x180074d5f  mov     qword ptr [rsp+0D0h+AllocationAttributes], 0; SectionOffset
0x180074d68  mov     qword ptr [rsp+0D0h+FileInformationClass], 0; CommitSize
0x180074d71  call    cs:__imp_ZwMapViewOfSection
0x180074d78  nop     dword ptr [rax+rax+00h]
0x180074d7d  mov     edi, eax
0x180074d7f  test    eax, eax
0x180074d81  js      short loc_180074DB6
0x180074d83  mov     rax, [rbp+57h+SectionHandle]
0x180074d87  xor     ecx, ecx
0x180074d89  mov     [rbx+8], rax
0x180074d8d  xor     edx, edx
0x180074d8f  mov     rax, [rbp+57h+BaseAddress]
0x180074d93  xor     edi, edi
0x180074d95  mov     [rbx+18h], rax
0x180074d99  mov     rax, qword ptr [rbp+57h+FileInformation+8]
0x180074d9d  mov     [rbx+20h], rax
0x180074da1  mov     [rbx+10h], rax
0x180074da5  mov     dword ptr [rbx+29h], 101h
0x180074dac  mov     [rbp+57h+SectionHandle], rcx
0x180074db0  mov     [rbp+57h+BaseAddress], rdx
0x180074db4  jmp     short loc_180074DBE
0x180074db6  mov     rcx, [rbp+57h+SectionHandle]; Handle
0x180074dba  mov     rdx, [rbp+57h+BaseAddress]
0x180074dbe  test    rcx, rcx
0x180074dc1  jz      short loc_180074DD3
0x180074dc3  call    cs:__imp_ZwClose
0x180074dca  nop     dword ptr [rax+rax+00h]
0x180074dcf  mov     rdx, [rbp+57h+BaseAddress]; BaseAddress
0x180074dd3  test    rdx, rdx
0x180074dd6  jz      short loc_180074DE8
0x180074dd8  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180074ddc  call    cs:__imp_ZwUnmapViewOfSection
0x180074de3  nop     dword ptr [rax+rax+00h]
0x180074de8  mov     eax, edi
0x180074dea  mov     rcx, [rbp+57h+var_10]
0x180074dee  xor     rcx, rsp; StackCookie
0x180074df1  call    __security_check_cookie
0x180074df6  lea     r11, [rsp+0D0h+var_s0]
0x180074dfe  mov     rbx, [r11+18h]
0x180074e02  mov     rdi, [r11+20h]
0x180074e06  mov     rsp, r11
0x180074e09  pop     rbp
0x180074e0a  retn
```
