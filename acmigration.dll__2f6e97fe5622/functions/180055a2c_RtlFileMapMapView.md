# RtlFileMapMapView

- ea: `0x180055a2c`
- end: `0x180055bf5`
- name: `RtlFileMapMapView`
- size: `457`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800553b8`
- `0x180055470`
- `0x18005643c`
- `0x1800579c0`

## callees

- `0x180001cf0`
- `0x180055a2c`

## import_xrefs

- `ntdll!ZwClose` at `0x180055bc2`
- `ntdll!ZwClose` at `0x180055bc2`
- `ntdll!ZwQueryInformationFile` at `0x180055aa6`
- `ntdll!ZwQueryInformationFile` at `0x180055aa6`
- `ntdll!ZwCreateSection` at `0x180055b13`
- `ntdll!ZwCreateSection` at `0x180055b13`
- `ntdll!ZwUnmapViewOfSection` at `0x180055bd5`
- `ntdll!ZwUnmapViewOfSection` at `0x180055bd5`
- `ntdll!ZwMapViewOfSection` at `0x180055b65`
- `ntdll!ZwMapViewOfSection` at `0x180055b65`

## pseudocode

```c
__int64 __fastcall RtlFileMapMapView(__int64 a1, char a2)
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
0x180055a2c  push    rbp
0x180055a2e  push    rbx
0x180055a2f  push    rsi
0x180055a30  push    rdi
0x180055a31  lea     rbp, [rsp-3Fh]
0x180055a36  sub     rsp, 0D8h
0x180055a3d  mov     rax, cs:__security_cookie
0x180055a44  xor     rax, rsp
0x180055a47  mov     [rbp+57h+var_30], rax
0x180055a4b  xor     eax, eax
0x180055a4d  xorps   xmm0, xmm0
0x180055a50  xorps   xmm1, xmm1
0x180055a53  mov     sil, dl
0x180055a56  mov     rdi, rcx
0x180055a59  mov     [rbp+57h+var_38], rax
0x180055a5d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180055a61  mov     [rbp+57h+SectionHandle], rax
0x180055a65  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180055a69  mov     [rbp+57h+BaseAddress], rax
0x180055a6d  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180055a71  mov     [rbp+57h+ViewSize], rax
0x180055a75  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180055a79  movups  [rbp+57h+FileInformation], xmm1
0x180055a7d  cmp     [rcx+18h], rax
0x180055a81  jz      short loc_180055A8D
0x180055a83  mov     ebx, 0C000010Eh
0x180055a88  jmp     loc_180055BDB
0x180055a8d  mov     rcx, [rcx]; FileHandle
0x180055a90  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x180055a94  mov     r9d, 18h; Length
0x180055a9a  mov     [rsp+0F0h+FileInformationClass], 5; FileInformationClass
0x180055aa2  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180055aa6  call    cs:__imp_ZwQueryInformationFile
0x180055aac  mov     ebx, eax
0x180055aae  test    eax, eax
0x180055ab0  js      loc_180055BB5
0x180055ab6  mov     al, sil
0x180055ab9  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180055ac0  neg     al
0x180055ac2  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180055aca  mov     rax, [rdi]
0x180055acd  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180055ad1  sbb     ecx, ecx
0x180055ad3  mov     [rsp+0F0h+FileHandle], rax; FileHandle
0x180055ad8  and     ecx, 9000000h
0x180055ade  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x180055ae5  add     ecx, 8000000h
0x180055aeb  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x180055af3  mov     [rsp+0F0h+AllocationAttributes], ecx; AllocationAttributes
0x180055af7  xorps   xmm0, xmm0
0x180055afa  lea     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x180055afe  mov     [rsp+0F0h+FileInformationClass], 2; SectionPageProtection
0x180055b06  xor     r9d, r9d; MaximumSize
0x180055b09  mov     edx, 0F0005h; DesiredAccess
0x180055b0e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180055b13  call    cs:__imp_ZwCreateSection
0x180055b19  mov     ebx, eax
0x180055b1b  test    eax, eax
0x180055b1d  js      loc_180055BB5
0x180055b23  mov     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x180055b27  lea     rax, [rbp+57h+ViewSize]
0x180055b2b  mov     [rsp+0F0h+Win32Protect], 2; Win32Protect
0x180055b33  lea     r8, [rbp+57h+BaseAddress]; BaseAddress
0x180055b37  mov     [rsp+0F0h+AllocationType], 500000h; AllocationType
0x180055b3f  xor     r9d, r9d; ZeroBits
0x180055b42  mov     [rsp+0F0h+InheritDisposition], 2; InheritDisposition
0x180055b4a  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180055b4e  mov     [rsp+0F0h+FileHandle], rax; ViewSize
0x180055b53  mov     qword ptr [rsp+0F0h+AllocationAttributes], 0; SectionOffset
0x180055b5c  mov     qword ptr [rsp+0F0h+FileInformationClass], 0; CommitSize
0x180055b65  call    cs:__imp_ZwMapViewOfSection
0x180055b6b  mov     ebx, eax
0x180055b6d  test    eax, eax
0x180055b6f  js      short loc_180055BB5
0x180055b71  mov     rax, [rbp+57h+SectionHandle]
0x180055b75  test    sil, sil
0x180055b78  mov     rcx, qword ptr [rbp+57h+FileInformation+8]
0x180055b7c  mov     [rdi+8], rax
0x180055b80  mov     rax, [rbp+57h+BaseAddress]
0x180055b84  mov     [rdi+18h], rax
0x180055b88  mov     rax, rcx
0x180055b8b  cmovnz  rax, [rbp+57h+ViewSize]
0x180055b90  xor     edx, edx
0x180055b92  mov     [rdi+10h], rcx
0x180055b96  xor     ecx, ecx
0x180055b98  mov     [rbp+57h+SectionHandle], rcx
0x180055b9c  xor     ebx, ebx
0x180055b9e  mov     [rbp+57h+BaseAddress], rdx
0x180055ba2  mov     [rdi+2Ch], cl
0x180055ba5  mov     word ptr [rdi+29h], 101h
0x180055bab  mov     [rdi+20h], rax
0x180055baf  mov     [rdi+2Bh], sil
0x180055bb3  jmp     short loc_180055BBD
0x180055bb5  mov     rcx, [rbp+57h+SectionHandle]; Handle
0x180055bb9  mov     rdx, [rbp+57h+BaseAddress]
0x180055bbd  test    rcx, rcx
0x180055bc0  jz      short loc_180055BCC
0x180055bc2  call    cs:__imp_ZwClose
0x180055bc8  mov     rdx, [rbp+57h+BaseAddress]; BaseAddress
0x180055bcc  test    rdx, rdx
0x180055bcf  jz      short loc_180055BDB
0x180055bd1  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180055bd5  call    cs:__imp_ZwUnmapViewOfSection
0x180055bdb  mov     eax, ebx
0x180055bdd  mov     rcx, [rbp+57h+var_30]
0x180055be1  xor     rcx, rsp; StackCookie
0x180055be4  call    __security_check_cookie
0x180055be9  add     rsp, 0D8h
0x180055bf0  pop     rdi
0x180055bf1  pop     rsi
0x180055bf2  pop     rbx
0x180055bf3  pop     rbp
0x180055bf4  retn
```
