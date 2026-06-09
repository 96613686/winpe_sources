# RtlFileMapMapViewEx

- ea: `0x180030d18`
- end: `0x180030ee1`
- name: `RtlFileMapMapViewEx`
- size: `457`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800304a4`
- `0x18003055c`
- `0x180031ab4`
- `0x180032f08`

## callees

- `0x180005890`
- `0x180030d18`

## import_xrefs

- `ntdll!ZwClose` at `0x180030eae`
- `ntdll!ZwClose` at `0x180030eae`
- `ntdll!ZwQueryInformationFile` at `0x180030d92`
- `ntdll!ZwQueryInformationFile` at `0x180030d92`
- `ntdll!ZwCreateSection` at `0x180030dff`
- `ntdll!ZwCreateSection` at `0x180030dff`
- `ntdll!ZwUnmapViewOfSection` at `0x180030ec1`
- `ntdll!ZwUnmapViewOfSection` at `0x180030ec1`
- `ntdll!ZwMapViewOfSection` at `0x180030e51`
- `ntdll!ZwMapViewOfSection` at `0x180030e51`

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
0x180030d18  push    rbp
0x180030d1a  push    rbx
0x180030d1b  push    rsi
0x180030d1c  push    rdi
0x180030d1d  lea     rbp, [rsp-3Fh]
0x180030d22  sub     rsp, 0D8h
0x180030d29  mov     rax, cs:__security_cookie
0x180030d30  xor     rax, rsp
0x180030d33  mov     [rbp+57h+var_30], rax
0x180030d37  xor     eax, eax
0x180030d39  xorps   xmm0, xmm0
0x180030d3c  xorps   xmm1, xmm1
0x180030d3f  mov     sil, dl
0x180030d42  mov     rdi, rcx
0x180030d45  mov     [rbp+57h+var_38], rax
0x180030d49  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180030d4d  mov     [rbp+57h+SectionHandle], rax
0x180030d51  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180030d55  mov     [rbp+57h+BaseAddress], rax
0x180030d59  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180030d5d  mov     [rbp+57h+ViewSize], rax
0x180030d61  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180030d65  movups  [rbp+57h+FileInformation], xmm1
0x180030d69  cmp     [rcx+18h], rax
0x180030d6d  jz      short loc_180030D79
0x180030d6f  mov     ebx, 0C000010Eh
0x180030d74  jmp     loc_180030EC7
0x180030d79  mov     rcx, [rcx]; FileHandle
0x180030d7c  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x180030d80  mov     r9d, 18h; Length
0x180030d86  mov     [rsp+0F0h+FileInformationClass], 5; FileInformationClass
0x180030d8e  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180030d92  call    cs:__imp_ZwQueryInformationFile
0x180030d98  mov     ebx, eax
0x180030d9a  test    eax, eax
0x180030d9c  js      loc_180030EA1
0x180030da2  mov     al, sil
0x180030da5  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180030dac  neg     al
0x180030dae  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180030db6  mov     rax, [rdi]
0x180030db9  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180030dbd  sbb     ecx, ecx
0x180030dbf  mov     [rsp+0F0h+FileHandle], rax; FileHandle
0x180030dc4  and     ecx, 9000000h
0x180030dca  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x180030dd1  add     ecx, 8000000h
0x180030dd7  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x180030ddf  mov     [rsp+0F0h+AllocationAttributes], ecx; AllocationAttributes
0x180030de3  xorps   xmm0, xmm0
0x180030de6  lea     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x180030dea  mov     [rsp+0F0h+FileInformationClass], 2; SectionPageProtection
0x180030df2  xor     r9d, r9d; MaximumSize
0x180030df5  mov     edx, 0F0005h; DesiredAccess
0x180030dfa  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180030dff  call    cs:__imp_ZwCreateSection
0x180030e05  mov     ebx, eax
0x180030e07  test    eax, eax
0x180030e09  js      loc_180030EA1
0x180030e0f  mov     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x180030e13  lea     rax, [rbp+57h+ViewSize]
0x180030e17  mov     [rsp+0F0h+Win32Protect], 2; Win32Protect
0x180030e1f  lea     r8, [rbp+57h+BaseAddress]; BaseAddress
0x180030e23  mov     [rsp+0F0h+AllocationType], 500000h; AllocationType
0x180030e2b  xor     r9d, r9d; ZeroBits
0x180030e2e  mov     [rsp+0F0h+InheritDisposition], 2; InheritDisposition
0x180030e36  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180030e3a  mov     [rsp+0F0h+FileHandle], rax; ViewSize
0x180030e3f  mov     qword ptr [rsp+0F0h+AllocationAttributes], 0; SectionOffset
0x180030e48  mov     qword ptr [rsp+0F0h+FileInformationClass], 0; CommitSize
0x180030e51  call    cs:__imp_ZwMapViewOfSection
0x180030e57  mov     ebx, eax
0x180030e59  test    eax, eax
0x180030e5b  js      short loc_180030EA1
0x180030e5d  mov     rax, [rbp+57h+SectionHandle]
0x180030e61  test    sil, sil
0x180030e64  mov     rcx, qword ptr [rbp+57h+FileInformation+8]
0x180030e68  mov     [rdi+8], rax
0x180030e6c  mov     rax, [rbp+57h+BaseAddress]
0x180030e70  mov     [rdi+18h], rax
0x180030e74  mov     rax, rcx
0x180030e77  cmovnz  rax, [rbp+57h+ViewSize]
0x180030e7c  xor     edx, edx
0x180030e7e  mov     [rdi+10h], rcx
0x180030e82  xor     ecx, ecx
0x180030e84  mov     [rbp+57h+SectionHandle], rcx
0x180030e88  xor     ebx, ebx
0x180030e8a  mov     [rbp+57h+BaseAddress], rdx
0x180030e8e  mov     [rdi+2Ch], cl
0x180030e91  mov     word ptr [rdi+29h], 101h
0x180030e97  mov     [rdi+20h], rax
0x180030e9b  mov     [rdi+2Bh], sil
0x180030e9f  jmp     short loc_180030EA9
0x180030ea1  mov     rcx, [rbp+57h+SectionHandle]; Handle
0x180030ea5  mov     rdx, [rbp+57h+BaseAddress]
0x180030ea9  test    rcx, rcx
0x180030eac  jz      short loc_180030EB8
0x180030eae  call    cs:__imp_ZwClose
0x180030eb4  mov     rdx, [rbp+57h+BaseAddress]; BaseAddress
0x180030eb8  test    rdx, rdx
0x180030ebb  jz      short loc_180030EC7
0x180030ebd  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180030ec1  call    cs:__imp_ZwUnmapViewOfSection
0x180030ec7  mov     eax, ebx
0x180030ec9  mov     rcx, [rbp+57h+var_30]
0x180030ecd  xor     rcx, rsp; StackCookie
0x180030ed0  call    __security_check_cookie
0x180030ed5  add     rsp, 0D8h
0x180030edc  pop     rdi
0x180030edd  pop     rsi
0x180030ede  pop     rbx
0x180030edf  pop     rbp
0x180030ee0  retn
```
