# AhcpCdbGetFileTimestamp

- ea: `0x1400545a4`
- end: `0x1400547d1`
- name: `AhcpCdbGetFileTimestamp`
- size: `557`
- prototype: `__int64 __fastcall(_QWORD *, const WCHAR *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400591c4`

## callees

- `0x1400079f0`
- `0x140007e40`
- `0x14003e364`
- `0x1400545a4`

## import_xrefs

- `ntoskrnl!ZwQueryInformationFile` at `0x14005476d`
- `ntoskrnl!ZwQueryInformationFile` at `0x14005476d`
- `ntoskrnl!ZwClose` at `0x1400547c0`
- `ntoskrnl!ZwClose` at `0x1400547c0`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14005461d`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14005461d`
- `ntoskrnl!ZwCreateFile` at `0x140054718`
- `ntoskrnl!ZwCreateFile` at `0x140054718`
- `ntoskrnl!ZwQueryInformationByName` at `0x140054672`
- `ntoskrnl!ZwQueryInformationByName` at `0x140054672`

## string_xrefs

- `0x14005472a`: `Failed to open file [%x]`
- `0x140054783`: `Failed to open and get timestamp from %S. [%x]`

## pseudocode

```c
__int64 __fastcall AhcpCdbGetFileTimestamp(_QWORD *a1, const WCHAR *a2, int a3)
{
  NTSTATUS inited; // ebx
  __int64 v7; // rax
  __int64 v8; // rcx
  NTSTATUS v10; // eax
  NTSTATUS v11; // eax
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-58h] BYREF
  __int128 FileInformation; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v17; // [rsp+C8h] [rbp-38h]
  __int64 v18; // [rsp+D8h] [rbp-28h]
  _QWORD v19[10]; // [rsp+E0h] [rbp-20h] BYREF

  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  memset(v19, 0, 0x48u);
  FileInformation = 0;
  v18 = 0;
  v17 = 0;
  FileHandle = 0;
  inited = RtlInitUnicodeStringEx(&DestinationString, a2);
  if ( inited >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( (int)ZwQueryInformationByName(&ObjectAttributes, &IoStatusBlock, v19, 72, 68) < 0 )
    {
      v10 = ZwCreateFile(&FileHandle, 0x80100080, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 1u, 0x60u, 0, 0);
      inited = v10;
      if ( v10 < 0 )
      {
        AslLogCallPrintf(1, "AhcpCdbGetFileTimestamp", 924, "Failed to open file [%x]", v10);
        goto LABEL_7;
      }
      v11 = ZwQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
      inited = v11;
      if ( v11 < 0 )
      {
        AslLogCallPrintf(1, "AhcpCdbGetFileTimestamp", 934, "Failed to open and get timestamp from %S. [%x]", a2, v11);
        goto LABEL_7;
      }
      v7 = *((_QWORD *)&v17 + 1);
      v8 = v17;
      *(_OWORD *)&v19[3] = v17;
    }
    else
    {
      v7 = v19[4];
      v8 = v19[3];
    }
    if ( a3 )
      v7 = v8;
    inited = 0;
    *a1 = v7;
  }
LABEL_7:
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1400545a4  mov     [rsp-8+arg_10], rbx
0x1400545a9  mov     [rsp-8+arg_18], rsi
0x1400545ae  push    rbp
0x1400545af  push    rdi
0x1400545b0  push    r14
0x1400545b2  lea     rbp, [rsp-40h]
0x1400545b7  sub     rsp, 140h
0x1400545be  mov     rax, cs:__security_cookie
0x1400545c5  xor     rax, rsp
0x1400545c8  mov     [rbp+50h+var_20], rax
0x1400545cc  xorps   xmm1, xmm1
0x1400545cf  xorps   xmm0, xmm0
0x1400545d2  mov     rdi, rdx
0x1400545d5  mov     esi, r8d
0x1400545d8  xor     edx, edx; Val
0x1400545da  mov     r14, rcx
0x1400545dd  lea     rcx, [rbp+50h+var_70]; void *
0x1400545e1  movups  xmmword ptr [rbp+50h+DestinationString.Length], xmm0
0x1400545e5  lea     r8d, [rdx+48h]; Size
0x1400545e9  movups  xmmword ptr [rsp+150h+ObjectAttributes.Length], xmm1
0x1400545ee  movups  xmmword ptr [rbp+50h+ObjectAttributes.ObjectName], xmm1
0x1400545f2  movups  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400545f6  movups  xmmword ptr [rsp+150h+IoStatusBlock], xmm0
0x1400545fb  call    memset
0x140054600  xorps   xmm0, xmm0
0x140054603  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x140054607  xor     eax, eax
0x140054609  mov     rdx, rdi; SourceString
0x14005460c  movups  [rbp+50h+FileInformation], xmm0
0x140054610  mov     [rbp+50h+var_78], rax
0x140054614  movups  [rbp+50h+var_88], xmm0
0x140054618  mov     [rsp+150h+FileHandle], rax
0x14005461d  call    cs:__imp_RtlInitUnicodeStringEx
0x140054624  nop     dword ptr [rax+rax+00h]
0x140054629  mov     ebx, eax
0x14005462b  test    eax, eax
0x14005462d  js      short loc_140054695
0x14005462f  lea     rax, [rbp+50h+DestinationString]
0x140054633  mov     [rsp+150h+ObjectAttributes.Length], 30h ; '0'
0x14005463b  xorps   xmm0, xmm0
0x14005463e  mov     [rbp+50h+ObjectAttributes.ObjectName], rax
0x140054642  mov     r9d, 48h ; 'H'
0x140054648  mov     [rbp+50h+ObjectAttributes.RootDirectory], 0
0x140054650  lea     r8, [rbp+50h+var_70]
0x140054654  mov     [rbp+50h+ObjectAttributes.Attributes], 240h
0x14005465b  lea     rdx, [rsp+150h+IoStatusBlock]
0x140054660  mov     dword ptr [rsp+150h+AllocationSize], 44h ; 'D'
0x140054668  lea     rcx, [rsp+150h+ObjectAttributes]
0x14005466d  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x140054672  call    cs:__imp_ZwQueryInformationByName
0x140054679  nop     dword ptr [rax+rax+00h]
0x14005467e  test    eax, eax
0x140054680  js      short loc_1400546CA
0x140054682  mov     rax, qword ptr [rbp+50h+var_58+8]
0x140054686  mov     rcx, qword ptr [rbp+50h+var_58]
0x14005468a  test    esi, esi
0x14005468c  cmovnz  rax, rcx
0x140054690  xor     ebx, ebx
0x140054692  mov     [r14], rax
0x140054695  mov     rcx, [rsp+150h+FileHandle]; Handle
0x14005469a  test    rcx, rcx
0x14005469d  jnz     loc_1400547C0
0x1400546a3  mov     eax, ebx
0x1400546a5  mov     rcx, [rbp+50h+var_20]
0x1400546a9  xor     rcx, rsp; StackCookie
0x1400546ac  call    __security_check_cookie
0x1400546b1  lea     r11, [rsp+150h+var_10]
0x1400546b9  mov     rbx, [r11+30h]
0x1400546bd  mov     rsi, [r11+38h]
0x1400546c1  mov     rsp, r11
0x1400546c4  pop     r14
0x1400546c6  pop     rdi
0x1400546c7  pop     rbp
0x1400546c8  retn
0x1400546ca  mov     [rsp+150h+EaLength], 0; EaLength
0x1400546d2  lea     r9, [rsp+150h+IoStatusBlock]; IoStatusBlock
0x1400546d7  mov     [rsp+150h+EaBuffer], 0; EaBuffer
0x1400546e0  lea     r8, [rsp+150h+ObjectAttributes]; ObjectAttributes
0x1400546e5  mov     [rsp+150h+CreateOptions], 60h ; '`'; CreateOptions
0x1400546ed  lea     rcx, [rsp+150h+FileHandle]; FileHandle
0x1400546f2  mov     [rsp+150h+CreateDisposition], 1; CreateDisposition
0x1400546fa  mov     edx, 80100080h; DesiredAccess
0x1400546ff  mov     [rsp+150h+ShareAccess], 1; ShareAccess
0x140054707  mov     [rsp+150h+FileAttributes], 80h; FileAttributes
0x14005470f  mov     [rsp+150h+AllocationSize], 0; AllocationSize
0x140054718  call    cs:__imp_ZwCreateFile
0x14005471f  nop     dword ptr [rax+rax+00h]
0x140054724  mov     ebx, eax
0x140054726  test    eax, eax
0x140054728  jns     short loc_140054751
0x14005472a  lea     r9, aFailedToOpenFi; "Failed to open file [%x]"
0x140054731  mov     dword ptr [rsp+150h+AllocationSize], eax
0x140054735  mov     r8d, 39Ch
0x14005473b  lea     rdx, aAhcpcdbgetfile; "AhcpCdbGetFileTimestamp"
0x140054742  mov     ecx, 1
0x140054747  call    AslLogCallPrintf
0x14005474c  jmp     loc_140054695
0x140054751  mov     rcx, [rsp+150h+FileHandle]; FileHandle
0x140054756  lea     r8, [rbp+50h+FileInformation]; FileInformation
0x14005475a  mov     r9d, 28h ; '('; Length
0x140054760  mov     dword ptr [rsp+150h+AllocationSize], 4; FileInformationClass
0x140054768  lea     rdx, [rsp+150h+IoStatusBlock]; IoStatusBlock
0x14005476d  call    cs:__imp_ZwQueryInformationFile
0x140054774  nop     dword ptr [rax+rax+00h]
0x140054779  mov     ebx, eax
0x14005477b  test    eax, eax
0x14005477d  jns     short loc_1400547AB
0x14005477f  mov     [rsp+150h+FileAttributes], eax
0x140054783  lea     r9, aFailedToOpenAn; "Failed to open and get timestamp from %"...
0x14005478a  mov     r8d, 3A6h
0x140054790  mov     [rsp+150h+AllocationSize], rdi
0x140054795  lea     rdx, aAhcpcdbgetfile; "AhcpCdbGetFileTimestamp"
0x14005479c  mov     ecx, 1
0x1400547a1  call    AslLogCallPrintf
0x1400547a6  jmp     loc_140054695
0x1400547ab  mov     rcx, qword ptr [rbp+50h+var_88]
0x1400547af  mov     rax, qword ptr [rbp+50h+var_88+8]
0x1400547b3  mov     qword ptr [rbp+50h+var_58], rcx
0x1400547b7  mov     qword ptr [rbp+50h+var_58+8], rax
0x1400547bb  jmp     loc_14005468A
0x1400547c0  call    cs:__imp_ZwClose
0x1400547c7  nop     dword ptr [rax+rax+00h]
0x1400547cc  jmp     loc_1400546A3
```
