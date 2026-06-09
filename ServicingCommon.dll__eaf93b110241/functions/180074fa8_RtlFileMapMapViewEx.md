# RtlFileMapMapViewEx

- ea: `0x180074fa8`
- end: `0x18007517c`
- name: `RtlFileMapMapViewEx`
- size: `468`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000ea30`

## callees

- `0x1800293a0`
- `0x180074fa8`

## import_xrefs

- `ntdll!ZwUnmapViewOfSection` at `0x18007514c`
- `ntdll!ZwUnmapViewOfSection` at `0x18007514c`
- `ntdll!ZwCreateSection` at `0x180075089`
- `ntdll!ZwCreateSection` at `0x180075089`
- `ntdll!ZwMapViewOfSection` at `0x1800750e1`
- `ntdll!ZwMapViewOfSection` at `0x1800750e1`
- `ntdll!ZwQueryInformationFile` at `0x180075025`
- `ntdll!ZwQueryInformationFile` at `0x180075025`
- `ntdll!ZwClose` at `0x180075133`
- `ntdll!ZwClose` at `0x180075133`

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
0x180074fa8  mov     [rsp-8+arg_8], rbx
0x180074fad  mov     [rsp-8+arg_10], rdi
0x180074fb2  push    rbp
0x180074fb3  lea     rbp, [rsp-57h]
0x180074fb8  sub     rsp, 0D0h
0x180074fbf  mov     rax, cs:__security_cookie
0x180074fc6  xor     rax, rsp
0x180074fc9  mov     [rbp+57h+var_10], rax
0x180074fcd  xor     eax, eax
0x180074fcf  xorps   xmm0, xmm0
0x180074fd2  xorps   xmm1, xmm1
0x180074fd5  mov     rbx, rcx
0x180074fd8  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180074fdc  mov     [rbp+57h+var_28], rax
0x180074fe0  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180074fe4  mov     [rbp+57h+SectionHandle], rax
0x180074fe8  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180074fec  mov     [rbp+57h+BaseAddress], rax
0x180074ff0  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180074ff4  mov     [rbp+57h+ViewSize], rax
0x180074ff8  movups  [rbp+57h+FileInformation], xmm1
0x180074ffc  cmp     [rcx+18h], rax
0x180075000  jz      short loc_18007500C
0x180075002  mov     edi, 0C000010Eh
0x180075007  jmp     loc_180075158
0x18007500c  mov     rcx, [rcx]; FileHandle
0x18007500f  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x180075013  mov     r9d, 18h; Length
0x180075019  mov     [rsp+0D0h+FileInformationClass], 5; FileInformationClass
0x180075021  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180075025  call    cs:__imp_ZwQueryInformationFile
0x18007502c  nop     dword ptr [rax+rax+00h]
0x180075031  mov     edi, eax
0x180075033  test    eax, eax
0x180075035  js      loc_180075126
0x18007503b  mov     rax, [rbx]
0x18007503e  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180075042  mov     [rsp+0D0h+FileHandle], rax; FileHandle
0x180075047  lea     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x18007504b  xorps   xmm0, xmm0
0x18007504e  mov     [rsp+0D0h+AllocationAttributes], 8000000h; AllocationAttributes
0x180075056  xor     r9d, r9d; MaximumSize
0x180075059  mov     [rsp+0D0h+FileInformationClass], 2; SectionPageProtection
0x180075061  mov     edx, 0F0005h; DesiredAccess
0x180075066  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18007506d  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180075075  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x18007507c  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x180075084  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180075089  call    cs:__imp_ZwCreateSection
0x180075090  nop     dword ptr [rax+rax+00h]
0x180075095  mov     edi, eax
0x180075097  test    eax, eax
0x180075099  js      loc_180075126
0x18007509f  mov     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x1800750a3  lea     rax, [rbp+57h+ViewSize]
0x1800750a7  mov     [rsp+0D0h+Win32Protect], 2; Win32Protect
0x1800750af  lea     r8, [rbp+57h+BaseAddress]; BaseAddress
0x1800750b3  mov     [rsp+0D0h+AllocationType], 500000h; AllocationType
0x1800750bb  xor     r9d, r9d; ZeroBits
0x1800750be  mov     [rsp+0D0h+InheritDisposition], 2; InheritDisposition
0x1800750c6  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800750ca  mov     [rsp+0D0h+FileHandle], rax; ViewSize
0x1800750cf  mov     qword ptr [rsp+0D0h+AllocationAttributes], 0; SectionOffset
0x1800750d8  mov     qword ptr [rsp+0D0h+FileInformationClass], 0; CommitSize
0x1800750e1  call    cs:__imp_ZwMapViewOfSection
0x1800750e8  nop     dword ptr [rax+rax+00h]
0x1800750ed  mov     edi, eax
0x1800750ef  test    eax, eax
0x1800750f1  js      short loc_180075126
0x1800750f3  mov     rax, [rbp+57h+SectionHandle]
0x1800750f7  xor     ecx, ecx
0x1800750f9  mov     [rbx+8], rax
0x1800750fd  xor     edx, edx
0x1800750ff  mov     rax, [rbp+57h+BaseAddress]
0x180075103  xor     edi, edi
0x180075105  mov     [rbx+18h], rax
0x180075109  mov     rax, qword ptr [rbp+57h+FileInformation+8]
0x18007510d  mov     [rbx+20h], rax
0x180075111  mov     [rbx+10h], rax
0x180075115  mov     dword ptr [rbx+29h], 101h
0x18007511c  mov     [rbp+57h+SectionHandle], rcx
0x180075120  mov     [rbp+57h+BaseAddress], rdx
0x180075124  jmp     short loc_18007512E
0x180075126  mov     rcx, [rbp+57h+SectionHandle]; Handle
0x18007512a  mov     rdx, [rbp+57h+BaseAddress]
0x18007512e  test    rcx, rcx
0x180075131  jz      short loc_180075143
0x180075133  call    cs:__imp_ZwClose
0x18007513a  nop     dword ptr [rax+rax+00h]
0x18007513f  mov     rdx, [rbp+57h+BaseAddress]; BaseAddress
0x180075143  test    rdx, rdx
0x180075146  jz      short loc_180075158
0x180075148  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18007514c  call    cs:__imp_ZwUnmapViewOfSection
0x180075153  nop     dword ptr [rax+rax+00h]
0x180075158  mov     eax, edi
0x18007515a  mov     rcx, [rbp+57h+var_10]
0x18007515e  xor     rcx, rsp; StackCookie
0x180075161  call    __security_check_cookie
0x180075166  lea     r11, [rsp+0D0h+var_s0]
0x18007516e  mov     rbx, [r11+18h]
0x180075172  mov     rdi, [r11+20h]
0x180075176  mov     rsp, r11
0x180075179  pop     rbp
0x18007517a  retn
```
