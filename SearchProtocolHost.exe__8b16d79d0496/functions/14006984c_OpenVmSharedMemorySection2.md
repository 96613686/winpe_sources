# OpenVmSharedMemorySection2

- ea: `0x14006984c`
- end: `0x140069a26`
- name: `OpenVmSharedMemorySection2`
- size: `474`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14004aea0`

## callees

- `0x140006893`
- `0x14006984c`

## import_xrefs

- `ntdll!NtCreateSection` at `0x1400699d5`
- `ntdll!NtCreateSection` at `0x1400699d5`
- `ntdll!RtlAppendUnicodeToString` at `0x1400698cb`
- `ntdll!RtlAppendUnicodeToString` at `0x1400698cb`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1400698fe`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1400698fe`
- `ntdll!RtlFreeUnicodeString` at `0x140069a09`
- `ntdll!RtlFreeUnicodeString` at `0x140069a09`
- `ntdll!NtClose` at `0x1400699f1`
- `ntdll!NtClose` at `0x1400699f1`
- `ntdll!RtlStringFromGUIDEx` at `0x1400698e6`
- `ntdll!RtlStringFromGUIDEx` at `0x1400698e6`
- `ntdll!NtCreateFile` at `0x14006997b`
- `ntdll!NtCreateFile` at `0x14006997b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400698a7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400698a7`

## pseudocode

```c
__int64 __fastcall OpenVmSharedMemorySection2(void **a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  NTSTATUS appended; // ebx
  __int64 v7; // r8
  _UNICODE_STRING Destination; // [rsp+68h] [rbp-51h] BYREF
  void *SectionHandle; // [rsp+78h] [rbp-41h] BYREF
  UNICODE_STRING Source; // [rsp+80h] [rbp-39h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES v13; // [rsp+C0h] [rbp+7h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F0h] [rbp+37h] BYREF
  void *FileHandle; // [rsp+128h] [rbp+6Fh] BYREF

  FileHandle = 0;
  SectionHandle = 0;
  *(_QWORD *)&Destination.Length = 14680064;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&v13, 0, 44);
  Source = 0;
  Destination.Buffer = (PWSTR)LocalAlloc(0x40u, 0xE0u);
  if ( Destination.Buffer )
  {
    appended = RtlAppendUnicodeToString(
                 &Destination,
                 L"\\Device\\vmsmb\\VSMB-{dcc079ae-60ba-4d07-847c-3493609c0870}\\SharedMemory$\\");
    if ( appended >= 0 )
    {
      LOBYTE(v7) = 1;
      appended = RtlStringFromGUIDEx(a5, &Source, v7);
      if ( appended >= 0 )
      {
        appended = RtlAppendUnicodeStringToString(&Destination, &Source);
        if ( appended >= 0 )
        {
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = 64;
          ObjectAttributes.ObjectName = &Destination;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          appended = NtCreateFile(&FileHandle, 3u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 1u, 0, 0, 0);
          if ( appended >= 0 )
          {
            v13.Length = 48;
            memset(&v13.RootDirectory, 0, 20);
            *(_OWORD *)&v13.SecurityDescriptor = 0;
            appended = NtCreateSection(&SectionHandle, 7u, &v13, 0, 4u, 0x8000000u, FileHandle);
            if ( appended >= 0 )
              *a1 = SectionHandle;
          }
        }
      }
    }
  }
  else
  {
    appended = -1073741670;
  }
  if ( FileHandle )
    NtClose(FileHandle);
  if ( Destination.Buffer )
    LocalFree_0(Destination.Buffer);
  RtlFreeUnicodeString(&Source);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14006984c  mov     rax, rsp
0x14006984f  mov     [rax+8], rbx
0x140069853  mov     [rax+10h], rdi
0x140069857  mov     [rax+18h], r8
0x14006985b  push    rbp
0x14006985c  lea     rbp, [rax-57h]
0x140069860  sub     rsp, 100h
0x140069867  xorps   xmm0, xmm0
0x14006986a  xor     eax, eax
0x14006986c  mov     rdi, rcx
0x14006986f  mov     [rbp+4Fh+FileHandle], rax
0x140069873  mov     edx, 0E0h; uBytes
0x140069878  mov     [rbp+4Fh+SectionHandle], rax
0x14006987c  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x140069880  lea     ecx, [rax+40h]; uFlags
0x140069883  movups  xmmword ptr [rbp+4Fh+var_48.ObjectName], xmm0
0x140069887  movups  xmmword ptr [rbp+4Fh+Destination.Length], xmm0
0x14006988b  mov     [rbp+4Fh+Destination.MaximumLength], dx
0x14006988f  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x140069893  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x140069897  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x14006989b  movups  xmmword ptr [rbp+4Fh+var_48.Length], xmm0
0x14006989f  movups  xmmword ptr [rbp+4Fh+var_48+1Ch], xmm0
0x1400698a3  movups  xmmword ptr [rbp+4Fh+Source.Length], xmm0
0x1400698a7  call    cs:__imp_LocalAlloc
0x1400698ad  mov     [rbp+4Fh+Destination.Buffer], rax
0x1400698b1  test    rax, rax
0x1400698b4  jnz     short loc_1400698C0
0x1400698b6  mov     ebx, 0C000009Ah
0x1400698bb  jmp     loc_1400699E8
0x1400698c0  lea     rdx, Source; "\\Device\\vmsmb\\VSMB-{dcc079ae-60ba-4d"...
0x1400698c7  lea     rcx, [rbp+4Fh+Destination]; Destination
0x1400698cb  call    cs:__imp_RtlAppendUnicodeToString
0x1400698d1  mov     ebx, eax
0x1400698d3  test    eax, eax
0x1400698d5  js      loc_1400699E8
0x1400698db  mov     rcx, [rbp+4Fh+arg_20]
0x1400698df  lea     rdx, [rbp+4Fh+Source]
0x1400698e3  mov     r8b, 1
0x1400698e6  call    cs:__imp_RtlStringFromGUIDEx
0x1400698ec  mov     ebx, eax
0x1400698ee  test    eax, eax
0x1400698f0  js      loc_1400699E8
0x1400698f6  lea     rdx, [rbp+4Fh+Source]; Source
0x1400698fa  lea     rcx, [rbp+4Fh+Destination]; Destination
0x1400698fe  call    cs:__imp_RtlAppendUnicodeStringToString
0x140069904  mov     ebx, eax
0x140069906  test    eax, eax
0x140069908  js      loc_1400699E8
0x14006990e  mov     [rsp+100h+EaLength], 0; EaLength
0x140069916  lea     rax, [rbp+4Fh+Destination]
0x14006991a  mov     [rsp+100h+EaBuffer], 0; EaBuffer
0x140069923  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x140069927  mov     [rsp+100h+CreateOptions], 0; CreateOptions
0x14006992f  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x140069933  mov     [rsp+100h+CreateDisposition], 1; CreateDisposition
0x14006993b  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x14006993f  mov     edx, 3; DesiredAccess
0x140069944  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x14006994b  mov     [rsp+100h+ShareAccess], edx; ShareAccess
0x14006994f  xorps   xmm0, xmm0
0x140069952  mov     [rsp+100h+FileAttributes], 80h; FileAttributes
0x14006995a  mov     [rsp+100h+AllocationSize], 0; AllocationSize
0x140069963  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], 0
0x14006996b  mov     [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x140069972  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x140069976  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14006997b  call    cs:__imp_NtCreateFile
0x140069981  mov     ebx, eax
0x140069983  test    eax, eax
0x140069985  js      short loc_1400699E8
0x140069987  mov     rax, [rbp+4Fh+FileHandle]
0x14006998b  lea     r8, [rbp+4Fh+var_48]; ObjectAttributes
0x14006998f  mov     qword ptr [rsp+100h+ShareAccess], rax; FileHandle
0x140069994  lea     rcx, [rbp+4Fh+SectionHandle]; SectionHandle
0x140069998  xor     r9d, r9d; MaximumSize
0x14006999b  mov     [rsp+100h+FileAttributes], 8000000h; AllocationAttributes
0x1400699a3  xorps   xmm0, xmm0
0x1400699a6  mov     [rbp+4Fh+var_48.Length], 30h ; '0'
0x1400699ad  mov     [rbp+4Fh+var_48.RootDirectory], 0
0x1400699b5  mov     [rbp+4Fh+var_48.Attributes], 0
0x1400699bc  lea     edx, [r9+7]; DesiredAccess
0x1400699c0  mov     [rbp+4Fh+var_48.ObjectName], 0
0x1400699c8  movdqu  xmmword ptr [rbp+4Fh+var_48.SecurityDescriptor], xmm0
0x1400699cd  mov     dword ptr [rsp+100h+AllocationSize], 4; SectionPageProtection
0x1400699d5  call    cs:__imp_NtCreateSection
0x1400699db  mov     ebx, eax
0x1400699dd  test    eax, eax
0x1400699df  js      short loc_1400699E8
0x1400699e1  mov     rax, [rbp+4Fh+SectionHandle]
0x1400699e5  mov     [rdi], rax
0x1400699e8  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x1400699ec  test    rcx, rcx
0x1400699ef  jz      short loc_1400699F7
0x1400699f1  call    cs:__imp_NtClose
0x1400699f7  mov     rcx, [rbp+4Fh+Destination.Buffer]; hMem
0x1400699fb  test    rcx, rcx
0x1400699fe  jz      short loc_140069A05
0x140069a00  call    LocalFree_0
0x140069a05  lea     rcx, [rbp+4Fh+Source]; UnicodeString
0x140069a09  call    cs:__imp_RtlFreeUnicodeString
0x140069a0f  lea     r11, [rsp+100h+var_s0]
0x140069a17  mov     eax, ebx
0x140069a19  mov     rbx, [r11+10h]
0x140069a1d  mov     rdi, [r11+18h]
0x140069a21  mov     rsp, r11
0x140069a24  pop     rbp
0x140069a25  retn
```
