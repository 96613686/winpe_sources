# RtlFileMapMapView

- ea: `0x1800515f4`
- end: `0x1800517bd`
- name: `RtlFileMapMapView`
- size: `457`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004ba18`
- `0x18004bad0`
- `0x18004d760`
- `0x18004ece4`

## callees

- `0x180004ea0`
- `0x1800515f4`

## import_xrefs

- `ntdll!ZwQueryInformationFile` at `0x18005166e`
- `ntdll!ZwQueryInformationFile` at `0x18005166e`
- `ntdll!ZwMapViewOfSection` at `0x18005172d`
- `ntdll!ZwMapViewOfSection` at `0x18005172d`
- `ntdll!ZwCreateSection` at `0x1800516db`
- `ntdll!ZwCreateSection` at `0x1800516db`
- `ntdll!ZwUnmapViewOfSection` at `0x18005179d`
- `ntdll!ZwUnmapViewOfSection` at `0x18005179d`
- `ntdll!ZwClose` at `0x18005178a`
- `ntdll!ZwClose` at `0x18005178a`

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
0x1800515f4  push    rbp
0x1800515f6  push    rbx
0x1800515f7  push    rsi
0x1800515f8  push    rdi
0x1800515f9  lea     rbp, [rsp-3Fh]
0x1800515fe  sub     rsp, 0D8h
0x180051605  mov     rax, cs:__security_cookie
0x18005160c  xor     rax, rsp
0x18005160f  mov     [rbp+57h+var_30], rax
0x180051613  xor     eax, eax
0x180051615  xorps   xmm0, xmm0
0x180051618  xorps   xmm1, xmm1
0x18005161b  mov     sil, dl
0x18005161e  mov     rdi, rcx
0x180051621  mov     [rbp+57h+var_38], rax
0x180051625  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180051629  mov     [rbp+57h+SectionHandle], rax
0x18005162d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180051631  mov     [rbp+57h+BaseAddress], rax
0x180051635  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180051639  mov     [rbp+57h+ViewSize], rax
0x18005163d  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180051641  movups  [rbp+57h+FileInformation], xmm1
0x180051645  cmp     [rcx+18h], rax
0x180051649  jz      short loc_180051655
0x18005164b  mov     ebx, 0C000010Eh
0x180051650  jmp     loc_1800517A3
0x180051655  mov     rcx, [rcx]; FileHandle
0x180051658  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18005165c  mov     r9d, 18h; Length
0x180051662  mov     [rsp+0F0h+FileInformationClass], 5; FileInformationClass
0x18005166a  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18005166e  call    cs:__imp_ZwQueryInformationFile
0x180051674  mov     ebx, eax
0x180051676  test    eax, eax
0x180051678  js      loc_18005177D
0x18005167e  mov     al, sil
0x180051681  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180051688  neg     al
0x18005168a  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180051692  mov     rax, [rdi]
0x180051695  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180051699  sbb     ecx, ecx
0x18005169b  mov     [rsp+0F0h+FileHandle], rax; FileHandle
0x1800516a0  and     ecx, 9000000h
0x1800516a6  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x1800516ad  add     ecx, 8000000h
0x1800516b3  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x1800516bb  mov     [rsp+0F0h+AllocationAttributes], ecx; AllocationAttributes
0x1800516bf  xorps   xmm0, xmm0
0x1800516c2  lea     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x1800516c6  mov     [rsp+0F0h+FileInformationClass], 2; SectionPageProtection
0x1800516ce  xor     r9d, r9d; MaximumSize
0x1800516d1  mov     edx, 0F0005h; DesiredAccess
0x1800516d6  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800516db  call    cs:__imp_ZwCreateSection
0x1800516e1  mov     ebx, eax
0x1800516e3  test    eax, eax
0x1800516e5  js      loc_18005177D
0x1800516eb  mov     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x1800516ef  lea     rax, [rbp+57h+ViewSize]
0x1800516f3  mov     [rsp+0F0h+Win32Protect], 2; Win32Protect
0x1800516fb  lea     r8, [rbp+57h+BaseAddress]; BaseAddress
0x1800516ff  mov     [rsp+0F0h+AllocationType], 500000h; AllocationType
0x180051707  xor     r9d, r9d; ZeroBits
0x18005170a  mov     [rsp+0F0h+InheritDisposition], 2; InheritDisposition
0x180051712  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180051716  mov     [rsp+0F0h+FileHandle], rax; ViewSize
0x18005171b  mov     qword ptr [rsp+0F0h+AllocationAttributes], 0; SectionOffset
0x180051724  mov     qword ptr [rsp+0F0h+FileInformationClass], 0; CommitSize
0x18005172d  call    cs:__imp_ZwMapViewOfSection
0x180051733  mov     ebx, eax
0x180051735  test    eax, eax
0x180051737  js      short loc_18005177D
0x180051739  mov     rax, [rbp+57h+SectionHandle]
0x18005173d  test    sil, sil
0x180051740  mov     rcx, qword ptr [rbp+57h+FileInformation+8]
0x180051744  mov     [rdi+8], rax
0x180051748  mov     rax, [rbp+57h+BaseAddress]
0x18005174c  mov     [rdi+18h], rax
0x180051750  mov     rax, rcx
0x180051753  cmovnz  rax, [rbp+57h+ViewSize]
0x180051758  xor     edx, edx
0x18005175a  mov     [rdi+10h], rcx
0x18005175e  xor     ecx, ecx
0x180051760  mov     [rbp+57h+SectionHandle], rcx
0x180051764  xor     ebx, ebx
0x180051766  mov     [rbp+57h+BaseAddress], rdx
0x18005176a  mov     [rdi+2Ch], cl
0x18005176d  mov     word ptr [rdi+29h], 101h
0x180051773  mov     [rdi+20h], rax
0x180051777  mov     [rdi+2Bh], sil
0x18005177b  jmp     short loc_180051785
0x18005177d  mov     rcx, [rbp+57h+SectionHandle]; Handle
0x180051781  mov     rdx, [rbp+57h+BaseAddress]
0x180051785  test    rcx, rcx
0x180051788  jz      short loc_180051794
0x18005178a  call    cs:__imp_ZwClose
0x180051790  mov     rdx, [rbp+57h+BaseAddress]; BaseAddress
0x180051794  test    rdx, rdx
0x180051797  jz      short loc_1800517A3
0x180051799  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18005179d  call    cs:__imp_ZwUnmapViewOfSection
0x1800517a3  mov     eax, ebx
0x1800517a5  mov     rcx, [rbp+57h+var_30]
0x1800517a9  xor     rcx, rsp; StackCookie
0x1800517ac  call    __security_check_cookie
0x1800517b1  add     rsp, 0D8h
0x1800517b8  pop     rdi
0x1800517b9  pop     rsi
0x1800517ba  pop     rbx
0x1800517bb  pop     rbp
0x1800517bc  retn
```
