# TelemetryData_pCreateDumpFile

- ea: `0x140080a44`
- end: `0x140080c7a`
- name: `TelemetryData_pCreateDumpFile`
- size: `566`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400810e8`

## callees

- `0x140045064`
- `0x140059970`
- `0x140080a44`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140080b9c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140080b9c`
- `ntoskrnl!ExSystemTimeToLocalTime` at `0x140080aa4`
- `ntoskrnl!ExSystemTimeToLocalTime` at `0x140080aa4`
- `ntoskrnl!RtlTimeToTimeFields` at `0x140080ab8`
- `ntoskrnl!RtlTimeToTimeFields` at `0x140080ab8`
- `ntoskrnl!IoCreateFile` at `0x140080c18`
- `ntoskrnl!IoCreateFile` at `0x140080c18`

## pseudocode

```c
__int64 __fastcall TelemetryData_pCreateDumpFile(__int64 a1, void **a2)
{
  NTSTATUS v4; // edi
  unsigned int v5; // esi
  _WORD *v6; // rbx
  const wchar_t *v7; // r8
  PLARGE_INTEGER AllocationSize; // [rsp+20h] [rbp-A9h]
  ULONG FileAttributes[2]; // [rsp+28h] [rbp-A1h]
  __int64 ShareAccess; // [rsp+30h] [rbp-99h]
  __int64 Disposition; // [rsp+38h] [rbp-91h]
  __int64 CreateOptions; // [rsp+40h] [rbp-89h]
  PVOID EaBuffer; // [rsp+48h] [rbp-81h]
  union _LARGE_INTEGER SystemTime; // [rsp+70h] [rbp-59h] BYREF
  union _LARGE_INTEGER LocalTime; // [rsp+78h] [rbp-51h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp-9h] BYREF
  _TIME_FIELDS TimeFields; // [rsp+D0h] [rbp+7h] BYREF

  TimeFields = 0;
  LocalTime.QuadPart = 0;
  v4 = -1073741823;
  SystemTime.QuadPart = MEMORY[0xFFFFF78000000014];
  ExSystemTimeToLocalTime(&SystemTime, &LocalTime);
  RtlTimeToTimeFields(&LocalTime, &TimeFields);
  v5 = 0;
  v6 = (_WORD *)(a1 + 736);
  while ( v5 <= 0xA )
  {
    v7 = L"%ws-%04u%02u%02u-%02u%02u-%02u.dmp";
    LODWORD(EaBuffer) = v5;
    if ( !v5 )
      v7 = L"%ws-%04u%02u%02u-%02u%02u.dmp";
    LODWORD(CreateOptions) = TimeFields.Minute;
    LODWORD(Disposition) = TimeFields.Hour;
    LODWORD(ShareAccess) = TimeFields.Day;
    FileAttributes[0] = TimeFields.Month;
    LODWORD(AllocationSize) = TimeFields.Year;
    if ( RtlStringCbPrintfW(
           (NTSTRSAFE_PWSTR)(a1 + 656),
           0x50u,
           v7,
           a1 + 624,
           AllocationSize,
           *(_QWORD *)FileAttributes,
           ShareAccess,
           Disposition,
           CreateOptions,
           EaBuffer) < 0 )
    {
      v4 = -1073741823;
      *(_WORD *)(a1 + 656) = 0;
      v6 = (_WORD *)(a1 + 736);
      break;
    }
    v6 = (_WORD *)(a1 + 736);
    if ( RtlStringCbPrintfW((NTSTRSAFE_PWSTR)(a1 + 736), 0x208u, L"%ws\\%ws\\%ws", a1 + 104, a1 + 624, a1 + 656) < 0 )
      break;
    DestinationString = 0;
    memset(&ObjectAttributes, 0, 44);
    IoStatusBlock = 0;
    RtlInitUnicodeString(&DestinationString, (PCWSTR)(a1 + 736));
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v4 = IoCreateFile(
           a2,
           0x120116u,
           &ObjectAttributes,
           &IoStatusBlock,
           0,
           0x80u,
           0,
           2u,
           0x22u,
           0,
           0,
           CreateFileTypeNone,
           0,
           0x100u);
    if ( v4 >= 0 )
      return (unsigned int)v4;
    ++v5;
  }
  *v6 = 0;
  *a2 = 0;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140080a44  mov     [rsp-8+arg_10], rbx
0x140080a49  push    rbp
0x140080a4a  push    rsi
0x140080a4b  push    rdi
0x140080a4c  push    r12
0x140080a4e  push    r13
0x140080a50  push    r14
0x140080a52  push    r15
0x140080a54  lea     rbp, [rsp-27h]
0x140080a59  sub     rsp, 0F0h
0x140080a60  mov     rax, cs:__security_cookie
0x140080a67  xor     rax, rsp
0x140080a6a  mov     [rbp+57h+var_40], rax
0x140080a6e  xorps   xmm0, xmm0
0x140080a71  xor     r15d, r15d
0x140080a74  mov     qword ptr [rbp+57h+SystemTime], r15
0x140080a78  mov     r12, rdx
0x140080a7b  movups  xmmword ptr [rbp+57h+TimeFields.Year], xmm0
0x140080a7f  mov     qword ptr [rbp+57h+LocalTime], r15
0x140080a83  lea     rdx, [rbp+57h+LocalTime]; LocalTime
0x140080a87  mov     r14, rcx
0x140080a8a  mov     rax, 0FFFFF78000000014h
0x140080a94  lea     rcx, [rbp+57h+SystemTime]; SystemTime
0x140080a98  mov     edi, 0C0000001h
0x140080a9d  mov     rax, [rax]
0x140080aa0  mov     qword ptr [rbp+57h+SystemTime], rax
0x140080aa4  call    cs:__imp_ExSystemTimeToLocalTime
0x140080aab  nop     dword ptr [rax+rax+00h]
0x140080ab0  lea     rdx, [rbp+57h+TimeFields]; TimeFields
0x140080ab4  lea     rcx, [rbp+57h+LocalTime]; Time
0x140080ab8  call    cs:__imp_RtlTimeToTimeFields
0x140080abf  nop     dword ptr [rax+rax+00h]
0x140080ac4  lea     r13, [r14+2E0h]
0x140080acb  mov     esi, r15d
0x140080ace  mov     rbx, r13
0x140080ad1  cmp     esi, 0Ah
0x140080ad4  ja      loc_140080C48
0x140080ada  movsx   ecx, [rbp+57h+TimeFields.Hour]
0x140080ade  lea     r15, [r14+290h]
0x140080ae5  movsx   edx, [rbp+57h+TimeFields.Day]
0x140080ae9  lea     rbx, aWs04u02u02u02u; "%ws-%04u%02u%02u-%02u%02u.dmp"
0x140080af0  movsx   r9d, [rbp+57h+TimeFields.Month]
0x140080af5  lea     r8, aWs04u02u02u02u_0; "%ws-%04u%02u%02u-%02u%02u-%02u.dmp"
0x140080afc  movsx   eax, [rbp+57h+TimeFields.Minute]
0x140080b00  test    esi, esi
0x140080b02  movsx   r10d, [rbp+57h+TimeFields.Year]
0x140080b07  mov     dword ptr [rsp+120h+EaBuffer], esi
0x140080b0b  cmovz   r8, rbx; pszFormat
0x140080b0f  mov     dword ptr [rsp+120h+CreateOptions], eax
0x140080b13  mov     dword ptr [rsp+120h+Disposition], ecx
0x140080b17  mov     rcx, r15; pszDest
0x140080b1a  mov     dword ptr [rsp+120h+ShareAccess], edx
0x140080b1e  mov     edx, 50h ; 'P'; cbDest
0x140080b23  mov     [rsp+120h+FileAttributes], r9d
0x140080b28  lea     r9, [r14+270h]
0x140080b2f  mov     dword ptr [rsp+120h+AllocationSize], r10d
0x140080b34  call    RtlStringCbPrintfW
0x140080b39  test    eax, eax
0x140080b3b  js      loc_140080C37
0x140080b41  lea     rax, [r14+270h]
0x140080b48  mov     qword ptr [rsp+120h+FileAttributes], r15
0x140080b4d  lea     rbx, [r14+2E0h]
0x140080b54  mov     [rsp+120h+AllocationSize], rax
0x140080b59  mov     rcx, rbx; pszDest
0x140080b5c  lea     r9, [r14+68h]
0x140080b60  lea     r8, aWsWsWs; "%ws\\%ws\\%ws"
0x140080b67  mov     edx, 208h; cbDest
0x140080b6c  call    RtlStringCbPrintfW
0x140080b71  xor     r15d, r15d
0x140080b74  test    eax, eax
0x140080b76  js      loc_140080C31
0x140080b7c  xorps   xmm0, xmm0
0x140080b7f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140080b83  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140080b87  xor     eax, eax
0x140080b89  mov     rdx, rbx; SourceString
0x140080b8c  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140080b90  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140080b94  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140080b98  movups  xmmword ptr [rbp+57h+IoStatusBlock.___u0], xmm0
0x140080b9c  call    cs:__imp_RtlInitUnicodeString
0x140080ba3  nop     dword ptr [rax+rax+00h]
0x140080ba8  mov     [rsp+120h+Options], 100h; Options
0x140080bb0  lea     rax, [rbp+57h+DestinationString]
0x140080bb4  mov     [rsp+120h+InternalParameters], r15; InternalParameters
0x140080bb9  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140080bbd  mov     [rsp+120h+CreateFileType], r15d; CreateFileType
0x140080bc2  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140080bc6  mov     [rsp+120h+EaLength], r15d; EaLength
0x140080bcb  xorps   xmm0, xmm0
0x140080bce  mov     [rsp+120h+EaBuffer], r15; EaBuffer
0x140080bd3  mov     edx, 120116h; DesiredAccess
0x140080bd8  mov     dword ptr [rsp+120h+CreateOptions], 22h ; '"'; CreateOptions
0x140080be0  mov     rcx, r12; FileHandle
0x140080be3  mov     dword ptr [rsp+120h+Disposition], 2; Disposition
0x140080beb  mov     dword ptr [rsp+120h+ShareAccess], r15d; ShareAccess
0x140080bf0  mov     [rsp+120h+FileAttributes], 80h; FileAttributes
0x140080bf8  mov     [rsp+120h+AllocationSize], r15; AllocationSize
0x140080bfd  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140080c04  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x140080c08  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140080c0f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140080c13  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140080c18  call    cs:__imp_IoCreateFile
0x140080c1f  nop     dword ptr [rax+rax+00h]
0x140080c24  mov     edi, eax
0x140080c26  test    eax, eax
0x140080c28  jns     short loc_140080C50
0x140080c2a  inc     esi
0x140080c2c  jmp     loc_140080AD1
0x140080c31  test    edi, edi
0x140080c33  jns     short loc_140080C50
0x140080c35  jmp     short loc_140080C48
0x140080c37  xor     eax, eax
0x140080c39  mov     edi, 0C0000001h
0x140080c3e  mov     [r15], ax
0x140080c42  mov     rbx, r13
0x140080c45  xor     r15d, r15d
0x140080c48  mov     [rbx], r15w
0x140080c4c  mov     [r12], r15
0x140080c50  mov     eax, edi
0x140080c52  mov     rcx, [rbp+57h+var_40]
0x140080c56  xor     rcx, rsp; StackCookie
0x140080c59  call    __security_check_cookie
0x140080c5e  mov     rbx, [rsp+120h+arg_10]
0x140080c66  add     rsp, 0F0h
0x140080c6d  pop     r15
0x140080c6f  pop     r14
0x140080c71  pop     r13
0x140080c73  pop     r12
0x140080c75  pop     rdi
0x140080c76  pop     rsi
0x140080c77  pop     rbp
0x140080c78  retn
```
