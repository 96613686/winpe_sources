# OpenVmSharedMemorySection2

- ea: `0x180054404`
- end: `0x180054640`
- name: `OpenVmSharedMemorySection2`
- size: `572`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180024e94`

## callees

- `0x180004944`
- `0x180054404`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005448e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005448e`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800544e5`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800544e5`
- `ntdll!NtCreateSection` at `0x1800545ec`
- `ntdll!NtCreateSection` at `0x1800545ec`
- `ntdll!RtlAppendUnicodeToString` at `0x1800544b2`
- `ntdll!RtlAppendUnicodeToString` at `0x1800544b2`
- `ntdll!RtlFreeUnicodeString` at `0x180054620`
- `ntdll!RtlFreeUnicodeString` at `0x180054620`
- `ntdll!NtClose` at `0x180054608`
- `ntdll!NtClose` at `0x180054608`
- `ntdll!RtlStringFromGUIDEx` at `0x1800544cd`
- `ntdll!RtlStringFromGUIDEx` at `0x1800544cd`
- `ntdll!NtCreateFile` at `0x180054597`
- `ntdll!NtCreateFile` at `0x180054597`

## pseudocode

```c
__int64 __fastcall OpenVmSharedMemorySection2(void **a1, ACCESS_MASK a2, __int64 a3, ULONG a4, __int64 a5)
{
  NTSTATUS appended; // ebx
  __int64 v9; // r8
  ACCESS_MASK v10; // edx
  struct _UNICODE_STRING Destination; // [rsp+68h] [rbp-61h] BYREF
  void *SectionHandle; // [rsp+78h] [rbp-51h] BYREF
  UNICODE_STRING Source; // [rsp+80h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES v16; // [rsp+C0h] [rbp-9h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F0h] [rbp+27h] BYREF
  void *FileHandle; // [rsp+138h] [rbp+6Fh] BYREF

  FileHandle = 0;
  SectionHandle = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&v16, 0, 44);
  Source = 0;
  Destination = 0;
  if ( (a2 & 0xFFFFFFF0) != 0 )
  {
    appended = -1073741584;
    goto LABEL_24;
  }
  if ( (a4 & 0xFFFFFF99) != 0 )
  {
    appended = -1073741582;
    goto LABEL_24;
  }
  Destination.MaximumLength = 224;
  Destination.Buffer = (PWSTR)LocalAlloc(0x40u, 0xE0u);
  if ( !Destination.Buffer )
  {
    appended = -1073741670;
    goto LABEL_22;
  }
  appended = RtlAppendUnicodeToString(
               &Destination,
               L"\\Device\\vmsmb\\VSMB-{dcc079ae-60ba-4d07-847c-3493609c0870}\\SharedMemory$\\");
  if ( appended >= 0 )
  {
    LOBYTE(v9) = 1;
    appended = RtlStringFromGUIDEx(a5, &Source, v9);
    if ( appended >= 0 )
    {
      appended = RtlAppendUnicodeStringToString(&Destination, &Source);
      if ( appended >= 0 )
      {
        switch ( a4 )
        {
          case 2u:
            v10 = 1;
            break;
          case 4u:
            v10 = 3;
            break;
          case 0x20u:
            v10 = 33;
            break;
          case 0x40u:
            v10 = 35;
            break;
          default:
            appended = -1073741581;
            goto LABEL_22;
        }
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 64;
        ObjectAttributes.ObjectName = &Destination;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        appended = NtCreateFile(&FileHandle, v10, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 1u, 0, 0, 0);
        if ( appended >= 0 )
        {
          v16.Length = 48;
          memset(&v16.RootDirectory, 0, 20);
          *(_OWORD *)&v16.SecurityDescriptor = 0;
          appended = NtCreateSection(&SectionHandle, a2, &v16, 0, a4, 0x8000000u, FileHandle);
          if ( appended >= 0 )
            *a1 = SectionHandle;
        }
      }
    }
  }
LABEL_22:
  if ( FileHandle )
    NtClose(FileHandle);
LABEL_24:
  if ( Destination.Buffer )
    LocalFree_0(Destination.Buffer);
  RtlFreeUnicodeString(&Source);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180054404  mov     rax, rsp
0x180054407  mov     [rax+8], rbx
0x18005440b  mov     [rax+10h], rsi
0x18005440f  mov     [rax+18h], r8
0x180054413  push    rbp
0x180054414  push    rdi
0x180054415  push    r14
0x180054417  lea     rbp, [rax-57h]
0x18005441b  sub     rsp, 100h
0x180054422  xorps   xmm0, xmm0
0x180054425  xor     eax, eax
0x180054427  mov     [rbp+4Fh+FileHandle], rax
0x18005442b  mov     edi, r9d
0x18005442e  mov     [rbp+4Fh+SectionHandle], rax
0x180054432  mov     r14d, edx
0x180054435  mov     rsi, rcx
0x180054438  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x18005443c  movups  xmmword ptr [rbp+4Fh+var_58.ObjectName], xmm0
0x180054440  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x180054444  movups  xmmword ptr [rbp+4Fh+var_58+1Ch], xmm0
0x180054448  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x18005444c  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x180054450  movups  xmmword ptr [rbp+4Fh+var_58.Length], xmm0
0x180054454  movups  xmmword ptr [rbp+4Fh+Source.Length], xmm0
0x180054458  movups  xmmword ptr [rbp+4Fh+Destination.Length], xmm0
0x18005445c  test    edx, 0FFFFFFF0h
0x180054462  jz      short loc_18005446E
0x180054464  mov     ebx, 0C00000F0h
0x180054469  jmp     loc_18005460E
0x18005446e  test    edi, 0FFFFFF99h
0x180054474  jz      short loc_180054480
0x180054476  mov     ebx, 0C00000F2h
0x18005447b  jmp     loc_18005460E
0x180054480  mov     edx, 0E0h; uBytes
0x180054485  mov     ecx, 40h ; '@'; uFlags
0x18005448a  mov     [rbp+4Fh+Destination.MaximumLength], dx
0x18005448e  call    cs:__imp_LocalAlloc
0x180054494  mov     [rbp+4Fh+Destination.Buffer], rax
0x180054498  test    rax, rax
0x18005449b  jnz     short loc_1800544A7
0x18005449d  mov     ebx, 0C000009Ah
0x1800544a2  jmp     loc_1800545FF
0x1800544a7  lea     rdx, aDeviceVmsmbVsm; "\\Device\\vmsmb\\VSMB-{dcc079ae-60ba-4d"...
0x1800544ae  lea     rcx, [rbp+4Fh+Destination]; Destination
0x1800544b2  call    cs:__imp_RtlAppendUnicodeToString
0x1800544b8  mov     ebx, eax
0x1800544ba  test    eax, eax
0x1800544bc  js      loc_1800545FF
0x1800544c2  mov     rcx, [rbp+4Fh+arg_20]
0x1800544c6  lea     rdx, [rbp+4Fh+Source]
0x1800544ca  mov     r8b, 1
0x1800544cd  call    cs:__imp_RtlStringFromGUIDEx
0x1800544d3  mov     ebx, eax
0x1800544d5  test    eax, eax
0x1800544d7  js      loc_1800545FF
0x1800544dd  lea     rdx, [rbp+4Fh+Source]; Source
0x1800544e1  lea     rcx, [rbp+4Fh+Destination]; Destination
0x1800544e5  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800544eb  mov     ebx, eax
0x1800544ed  test    eax, eax
0x1800544ef  js      loc_1800545FF
0x1800544f5  mov     ecx, 3
0x1800544fa  cmp     edi, 2
0x1800544fd  jz      short loc_18005452A
0x1800544ff  cmp     edi, 4
0x180054502  jz      short loc_180054526
0x180054504  cmp     edi, 20h ; ' '
0x180054507  jz      short loc_18005451F
0x180054509  cmp     edi, 40h ; '@'
0x18005450c  jz      short loc_180054518
0x18005450e  mov     ebx, 0C00000F3h
0x180054513  jmp     loc_1800545FF
0x180054518  mov     edx, 23h ; '#'
0x18005451d  jmp     short loc_18005452F
0x18005451f  mov     edx, 21h ; '!'
0x180054524  jmp     short loc_18005452F
0x180054526  mov     edx, ecx
0x180054528  jmp     short loc_18005452F
0x18005452a  mov     edx, 1; DesiredAccess
0x18005452f  mov     [rsp+110h+EaLength], 0; EaLength
0x180054537  lea     rax, [rbp+4Fh+Destination]
0x18005453b  mov     [rsp+110h+EaBuffer], 0; EaBuffer
0x180054544  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x180054548  mov     [rsp+110h+CreateOptions], 0; CreateOptions
0x180054550  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x180054554  mov     [rsp+110h+CreateDisposition], 1; CreateDisposition
0x18005455c  xorps   xmm0, xmm0
0x18005455f  mov     [rsp+110h+ShareAccess], ecx; ShareAccess
0x180054563  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x180054567  mov     [rsp+110h+FileAttributes], 80h; FileAttributes
0x18005456f  mov     [rsp+110h+AllocationSize], 0; AllocationSize
0x180054578  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18005457f  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], 0
0x180054587  mov     [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x18005458e  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x180054592  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180054597  call    cs:__imp_NtCreateFile
0x18005459d  mov     ebx, eax
0x18005459f  test    eax, eax
0x1800545a1  js      short loc_1800545FF
0x1800545a3  mov     rax, [rbp+4Fh+FileHandle]
0x1800545a7  lea     r8, [rbp+4Fh+var_58]; ObjectAttributes
0x1800545ab  mov     qword ptr [rsp+110h+ShareAccess], rax; FileHandle
0x1800545b0  lea     rcx, [rbp+4Fh+SectionHandle]; SectionHandle
0x1800545b4  xorps   xmm0, xmm0
0x1800545b7  mov     [rsp+110h+FileAttributes], 8000000h; AllocationAttributes
0x1800545bf  xor     r9d, r9d; MaximumSize
0x1800545c2  mov     dword ptr [rsp+110h+AllocationSize], edi; SectionPageProtection
0x1800545c6  mov     edx, r14d; DesiredAccess
0x1800545c9  mov     [rbp+4Fh+var_58.Length], 30h ; '0'
0x1800545d0  mov     [rbp+4Fh+var_58.RootDirectory], 0
0x1800545d8  mov     [rbp+4Fh+var_58.Attributes], 0
0x1800545df  mov     [rbp+4Fh+var_58.ObjectName], 0
0x1800545e7  movdqu  xmmword ptr [rbp+4Fh+var_58.SecurityDescriptor], xmm0
0x1800545ec  call    cs:__imp_NtCreateSection
0x1800545f2  mov     ebx, eax
0x1800545f4  test    eax, eax
0x1800545f6  js      short loc_1800545FF
0x1800545f8  mov     rax, [rbp+4Fh+SectionHandle]
0x1800545fc  mov     [rsi], rax
0x1800545ff  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x180054603  test    rcx, rcx
0x180054606  jz      short loc_18005460E
0x180054608  call    cs:__imp_NtClose
0x18005460e  mov     rcx, [rbp+4Fh+Destination.Buffer]; hMem
0x180054612  test    rcx, rcx
0x180054615  jz      short loc_18005461C
0x180054617  call    LocalFree_0
0x18005461c  lea     rcx, [rbp+4Fh+Source]; UnicodeString
0x180054620  call    cs:__imp_RtlFreeUnicodeString
0x180054626  lea     r11, [rsp+110h+var_10]
0x18005462e  mov     eax, ebx
0x180054630  mov     rbx, [r11+20h]
0x180054634  mov     rsi, [r11+28h]
0x180054638  mov     rsp, r11
0x18005463b  pop     r14
0x18005463d  pop     rdi
0x18005463e  pop     rbp
0x18005463f  retn
```
