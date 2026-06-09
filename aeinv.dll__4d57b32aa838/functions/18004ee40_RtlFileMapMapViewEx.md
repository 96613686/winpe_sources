# RtlFileMapMapViewEx

- ea: `0x18004ee40`
- end: `0x18004f009`
- name: `RtlFileMapMapViewEx`
- size: `457`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180022c04`
- `0x1800244c0`
- `0x18004f484`
- `0x18006d6b0`

## callees

- `0x18004ee40`
- `0x180059920`

## import_xrefs

- `ntdll!ZwCreateSection` at `0x18004ef27`
- `ntdll!ZwCreateSection` at `0x18004ef27`
- `ntdll!ZwUnmapViewOfSection` at `0x18004efe9`
- `ntdll!ZwUnmapViewOfSection` at `0x18004efe9`
- `ntdll!ZwClose` at `0x18004efd6`
- `ntdll!ZwClose` at `0x18004efd6`
- `ntdll!ZwMapViewOfSection` at `0x18004ef79`
- `ntdll!ZwMapViewOfSection` at `0x18004ef79`
- `ntdll!ZwQueryInformationFile` at `0x18004eeba`
- `ntdll!ZwQueryInformationFile` at `0x18004eeba`

## pseudocode

```c
__int64 __fastcall RtlFileMapMapViewEx(__int64 a1, char a2)
{
  NTSTATUS v4; // ebx
  ULONG_PTR v5; // rcx
  ULONG_PTR v6; // rax
  PVOID v7; // rdx
  void *v8; // rcx
  HANDLE FileHandle; // [rsp+30h] [rbp-69h]
  void *SectionHandle; // [rsp+50h] [rbp-49h] BYREF
  PVOID BaseAddress; // [rsp+58h] [rbp-41h] BYREF
  ULONG_PTR ViewSize; // [rsp+60h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-31h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-1h] BYREF
  __int128 FileInformation; // [rsp+A8h] [rbp+Fh] BYREF
  __int64 v17; // [rsp+B8h] [rbp+1Fh]

  v17 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  SectionHandle = 0;
  BaseAddress = 0;
  ViewSize = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  if ( *(_QWORD *)(a1 + 24) )
  {
    return (unsigned int)-1073741554;
  }
  else
  {
    v4 = ZwQueryInformationFile(*(HANDLE *)a1, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
    if ( v4 < 0
      || (ObjectAttributes.Length = 48,
          memset(&ObjectAttributes.RootDirectory, 0, 20),
          FileHandle = *(HANDLE *)a1,
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0,
          v4 = ZwCreateSection(
                 &SectionHandle,
                 0xF0005u,
                 &ObjectAttributes,
                 0,
                 2u,
                 a2 != 0 ? 285212672 : 0x8000000,
                 FileHandle),
          v4 < 0)
      || (v4 = ZwMapViewOfSection(
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
          v4 < 0) )
    {
      v8 = SectionHandle;
      v7 = BaseAddress;
    }
    else
    {
      v5 = *((_QWORD *)&FileInformation + 1);
      *(_QWORD *)(a1 + 8) = SectionHandle;
      *(_QWORD *)(a1 + 24) = BaseAddress;
      v6 = v5;
      if ( a2 )
        v6 = ViewSize;
      v7 = 0;
      *(_QWORD *)(a1 + 16) = v5;
      v8 = 0;
      SectionHandle = 0;
      v4 = 0;
      BaseAddress = 0;
      *(_BYTE *)(a1 + 44) = 0;
      *(_WORD *)(a1 + 41) = 257;
      *(_QWORD *)(a1 + 32) = v6;
      *(_BYTE *)(a1 + 43) = a2;
    }
    if ( v8 )
    {
      ZwClose(v8);
      v7 = BaseAddress;
    }
    if ( v7 )
      ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, v7);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004ee40  push    rbp
0x18004ee42  push    rbx
0x18004ee43  push    rsi
0x18004ee44  push    rdi
0x18004ee45  lea     rbp, [rsp-3Fh]
0x18004ee4a  sub     rsp, 0D8h
0x18004ee51  mov     rax, cs:__security_cookie
0x18004ee58  xor     rax, rsp
0x18004ee5b  mov     [rbp+57h+var_30], rax
0x18004ee5f  xor     eax, eax
0x18004ee61  xorps   xmm0, xmm0
0x18004ee64  xorps   xmm1, xmm1
0x18004ee67  mov     sil, dl
0x18004ee6a  mov     rdi, rcx
0x18004ee6d  mov     [rbp+57h+var_38], rax
0x18004ee71  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18004ee75  mov     [rbp+57h+SectionHandle], rax
0x18004ee79  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18004ee7d  mov     [rbp+57h+BaseAddress], rax
0x18004ee81  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004ee85  mov     [rbp+57h+ViewSize], rax
0x18004ee89  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18004ee8d  movups  [rbp+57h+FileInformation], xmm1
0x18004ee91  cmp     [rcx+18h], rax
0x18004ee95  jz      short loc_18004EEA1
0x18004ee97  mov     ebx, 0C000010Eh
0x18004ee9c  jmp     loc_18004EFEF
0x18004eea1  mov     rcx, [rcx]; FileHandle
0x18004eea4  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18004eea8  mov     r9d, 18h; Length
0x18004eeae  mov     [rsp+0F0h+FileInformationClass], 5; FileInformationClass
0x18004eeb6  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18004eeba  call    cs:__imp_ZwQueryInformationFile
0x18004eec0  mov     ebx, eax
0x18004eec2  test    eax, eax
0x18004eec4  js      loc_18004EFC9
0x18004eeca  mov     al, sil
0x18004eecd  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18004eed4  neg     al
0x18004eed6  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18004eede  mov     rax, [rdi]
0x18004eee1  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18004eee5  sbb     ecx, ecx
0x18004eee7  mov     [rsp+0F0h+FileHandle], rax; FileHandle
0x18004eeec  and     ecx, 9000000h
0x18004eef2  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x18004eef9  add     ecx, 8000000h
0x18004eeff  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x18004ef07  mov     [rsp+0F0h+AllocationAttributes], ecx; AllocationAttributes
0x18004ef0b  xorps   xmm0, xmm0
0x18004ef0e  lea     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x18004ef12  mov     [rsp+0F0h+FileInformationClass], 2; SectionPageProtection
0x18004ef1a  xor     r9d, r9d; MaximumSize
0x18004ef1d  mov     edx, 0F0005h; DesiredAccess
0x18004ef22  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004ef27  call    cs:__imp_ZwCreateSection
0x18004ef2d  mov     ebx, eax
0x18004ef2f  test    eax, eax
0x18004ef31  js      loc_18004EFC9
0x18004ef37  mov     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x18004ef3b  lea     rax, [rbp+57h+ViewSize]
0x18004ef3f  mov     [rsp+0F0h+Win32Protect], 2; Win32Protect
0x18004ef47  lea     r8, [rbp+57h+BaseAddress]; BaseAddress
0x18004ef4b  mov     [rsp+0F0h+AllocationType], 500000h; AllocationType
0x18004ef53  xor     r9d, r9d; ZeroBits
0x18004ef56  mov     [rsp+0F0h+InheritDisposition], 2; InheritDisposition
0x18004ef5e  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18004ef62  mov     [rsp+0F0h+FileHandle], rax; ViewSize
0x18004ef67  mov     qword ptr [rsp+0F0h+AllocationAttributes], 0; SectionOffset
0x18004ef70  mov     qword ptr [rsp+0F0h+FileInformationClass], 0; CommitSize
0x18004ef79  call    cs:__imp_ZwMapViewOfSection
0x18004ef7f  mov     ebx, eax
0x18004ef81  test    eax, eax
0x18004ef83  js      short loc_18004EFC9
0x18004ef85  mov     rax, [rbp+57h+SectionHandle]
0x18004ef89  test    sil, sil
0x18004ef8c  mov     rcx, qword ptr [rbp+57h+FileInformation+8]
0x18004ef90  mov     [rdi+8], rax
0x18004ef94  mov     rax, [rbp+57h+BaseAddress]
0x18004ef98  mov     [rdi+18h], rax
0x18004ef9c  mov     rax, rcx
0x18004ef9f  cmovnz  rax, [rbp+57h+ViewSize]
0x18004efa4  xor     edx, edx
0x18004efa6  mov     [rdi+10h], rcx
0x18004efaa  xor     ecx, ecx
0x18004efac  mov     [rbp+57h+SectionHandle], rcx
0x18004efb0  xor     ebx, ebx
0x18004efb2  mov     [rbp+57h+BaseAddress], rdx
0x18004efb6  mov     [rdi+2Ch], cl
0x18004efb9  mov     word ptr [rdi+29h], 101h
0x18004efbf  mov     [rdi+20h], rax
0x18004efc3  mov     [rdi+2Bh], sil
0x18004efc7  jmp     short loc_18004EFD1
0x18004efc9  mov     rcx, [rbp+57h+SectionHandle]; Handle
0x18004efcd  mov     rdx, [rbp+57h+BaseAddress]
0x18004efd1  test    rcx, rcx
0x18004efd4  jz      short loc_18004EFE0
0x18004efd6  call    cs:__imp_ZwClose
0x18004efdc  mov     rdx, [rbp+57h+BaseAddress]; BaseAddress
0x18004efe0  test    rdx, rdx
0x18004efe3  jz      short loc_18004EFEF
0x18004efe5  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18004efe9  call    cs:__imp_ZwUnmapViewOfSection
0x18004efef  mov     eax, ebx
0x18004eff1  mov     rcx, [rbp+57h+var_30]
0x18004eff5  xor     rcx, rsp; StackCookie
0x18004eff8  call    __security_check_cookie
0x18004effd  add     rsp, 0D8h
0x18004f004  pop     rdi
0x18004f005  pop     rsi
0x18004f006  pop     rbx
0x18004f007  pop     rbp
0x18004f008  retn
```
