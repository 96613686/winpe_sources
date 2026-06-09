# BfspBackupCorruptStore

- ea: `0x18004ddb4`
- end: `0x18004df50`
- name: `BfspBackupCorruptStore`
- size: `412`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004d7e4`

## callees

- `0x18001becc`
- `0x18004ddb4`
- `0x180051160`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18004df1c`
- `ntdll!RtlFreeHeap` at `0x18004df1c`
- `ntdll!NtSetInformationFile` at `0x18004deeb`
- `ntdll!NtSetInformationFile` at `0x18004deeb`
- `ntdll!NtOpenFile` at `0x18004de60`
- `ntdll!NtOpenFile` at `0x18004de60`
- `ntdll!NtClose` at `0x18004defc`
- `ntdll!NtClose` at `0x18004defc`
- `ntdll!RtlInitUnicodeString` at `0x18004de0d`
- `ntdll!RtlInitUnicodeString` at `0x18004de0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004df35`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004df35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004de7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004df27`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004de7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004df27`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004de8b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004de8b`
- `bcd!BcdGetSystemStorePath` at `0x18004ddf5`
- `bcd!BcdGetSystemStorePath` at `0x18004ddf5`

## pseudocode

```c
__int64 __fastcall BfspBackupCorruptStore(struct _UNICODE_STRING *a1)
{
  wchar_t *v1; // rbx
  NTSTATUS SystemStorePath; // edi
  size_t v3; // rdi
  ULONG v4; // esi
  HANDLE ProcessHeap; // rax
  wchar_t *v6; // rax
  size_t *v7; // r8
  HANDLE v8; // rax
  size_t ShareAccess; // [rsp+20h] [rbp-60h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  PCWSTR SourceString; // [rsp+A0h] [rbp+20h] BYREF
  void *FileHandle; // [rsp+A8h] [rbp+28h] BYREF

  v1 = 0;
  SourceString = 0;
  FileHandle = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( a1 )
  {
    DestinationString = *a1;
  }
  else
  {
    SystemStorePath = BcdGetSystemStorePath(&SourceString);
    if ( SystemStorePath < 0 )
      goto LABEL_11;
    RtlInitUnicodeString(&DestinationString, SourceString);
  }
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  SystemStorePath = NtOpenFile(&FileHandle, 0x110080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4020u);
  if ( SystemStorePath >= 0 )
  {
    v3 = (unsigned int)DestinationString.Length + 18;
    v4 = DestinationString.Length + 38;
    ProcessHeap = GetProcessHeap();
    v6 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, v4);
    v1 = v6;
    if ( v6 )
    {
      *(_DWORD *)v6 = 1;
      *((_QWORD *)v6 + 1) = 0;
      *((_DWORD *)v6 + 4) = v3 - 2;
      if ( v3 >> 1 )
        StringCopyWorkerW(v6 + 10, v3 >> 1, v7, DestinationString.Buffer, ShareAccess);
      StringCbCatW(v1 + 10, v3, (STRSAFE_LPCWSTR)v7);
      SystemStorePath = NtSetInformationFile(FileHandle, &IoStatusBlock, v1, v4, FileRenameInformation);
    }
    else
    {
      SystemStorePath = -1073741801;
    }
  }
LABEL_11:
  if ( FileHandle )
    NtClose(FileHandle);
  if ( SourceString )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)SourceString);
  if ( v1 )
  {
    v8 = GetProcessHeap();
    HeapFree(v8, 0, v1);
  }
  return (unsigned int)SystemStorePath;
}

```

## disassembly

```asm
0x18004ddb4  mov     [rsp-18h+arg_10], rbx
0x18004ddb9  push    rbp
0x18004ddba  push    rsi
0x18004ddbb  push    rdi
0x18004ddbc  mov     rbp, rsp
0x18004ddbf  sub     rsp, 80h
0x18004ddc6  xorps   xmm0, xmm0
0x18004ddc9  xor     eax, eax
0x18004ddcb  xor     ebx, ebx
0x18004ddcd  mov     [rbp+SourceString], rax
0x18004ddd1  mov     [rbp+FileHandle], rax
0x18004ddd5  xorps   xmm1, xmm1
0x18004ddd8  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18004dddc  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18004dde0  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18004dde4  movups  xmmword ptr [rbp+IoStatusBlock], xmm1
0x18004dde8  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18004ddec  test    rcx, rcx
0x18004ddef  jnz     short loc_18004DE15
0x18004ddf1  lea     rcx, [rbp+SourceString]
0x18004ddf5  call    cs:__imp_BcdGetSystemStorePath
0x18004ddfb  mov     edi, eax
0x18004ddfd  test    eax, eax
0x18004ddff  js      loc_18004DEF3
0x18004de05  mov     rdx, [rbp+SourceString]; SourceString
0x18004de09  lea     rcx, [rbp+DestinationString]; DestinationString
0x18004de0d  call    cs:__imp_RtlInitUnicodeString
0x18004de13  jmp     short loc_18004DE1D
0x18004de15  movups  xmm0, xmmword ptr [rcx]
0x18004de18  movdqu  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18004de1d  lea     rax, [rbp+DestinationString]
0x18004de21  mov     [rsp+80h+OpenOptions], 4020h; OpenOptions
0x18004de29  xorps   xmm0, xmm0
0x18004de2c  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18004de30  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x18004de34  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18004de3b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18004de3f  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x18004de43  mov     edx, 110080h; DesiredAccess
0x18004de48  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18004de4f  lea     rcx, [rbp+FileHandle]; FileHandle
0x18004de53  mov     dword ptr [rsp+80h+ShareAccess], 7; cchToCopy
0x18004de5b  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18004de60  call    cs:__imp_NtOpenFile
0x18004de66  mov     edi, eax
0x18004de68  test    eax, eax
0x18004de6a  js      loc_18004DEF3
0x18004de70  movzx   edi, [rbp+DestinationString.Length]
0x18004de74  add     edi, 12h
0x18004de77  lea     esi, [rdi+14h]
0x18004de7a  call    cs:__imp_GetProcessHeap
0x18004de80  mov     r8d, esi; dwBytes
0x18004de83  mov     edx, 8; dwFlags
0x18004de88  mov     rcx, rax; hHeap
0x18004de8b  call    cs:__imp_HeapAlloc
0x18004de91  mov     rbx, rax
0x18004de94  test    rax, rax
0x18004de97  jnz     short loc_18004DEA0
0x18004de99  mov     edi, 0C0000017h
0x18004de9e  jmp     short loc_18004DEF3
0x18004dea0  mov     dword ptr [rax], 1
0x18004dea6  mov     rdx, rdi
0x18004dea9  shr     rdx, 1; cchDest
0x18004deac  mov     qword ptr [rax+8], 0
0x18004deb4  lea     eax, [rdi-2]
0x18004deb7  mov     [rbx+10h], eax
0x18004deba  jz      short loc_18004DEC9
0x18004debc  mov     r9, [rbp+DestinationString.Buffer]; pszSrc
0x18004dec0  lea     rcx, [rbx+14h]; pszDest
0x18004dec4  call    StringCopyWorkerW
0x18004dec9  mov     rdx, rdi; cbDest
0x18004decc  lea     rcx, [rbx+14h]; pszDest
0x18004ded0  call    StringCbCatW
0x18004ded5  mov     rcx, [rbp+FileHandle]; FileHandle
0x18004ded9  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x18004dedd  mov     r9d, esi; Length
0x18004dee0  mov     dword ptr [rsp+80h+ShareAccess], 0Ah; FileInformationClass
0x18004dee8  mov     r8, rbx; FileInformation
0x18004deeb  call    cs:__imp_NtSetInformationFile
0x18004def1  mov     edi, eax
0x18004def3  mov     rcx, [rbp+FileHandle]; Handle
0x18004def7  test    rcx, rcx
0x18004defa  jz      short loc_18004DF02
0x18004defc  call    cs:__imp_NtClose
0x18004df02  cmp     [rbp+SourceString], 0
0x18004df07  jz      short loc_18004DF22
0x18004df09  mov     rcx, gs:60h
0x18004df12  xor     edx, edx; Flags
0x18004df14  mov     r8, [rbp+SourceString]; P
0x18004df18  mov     rcx, [rcx+30h]; HeapHandle
0x18004df1c  call    cs:__imp_RtlFreeHeap
0x18004df22  test    rbx, rbx
0x18004df25  jz      short loc_18004DF3B
0x18004df27  call    cs:__imp_GetProcessHeap
0x18004df2d  mov     r8, rbx; lpMem
0x18004df30  xor     edx, edx; dwFlags
0x18004df32  mov     rcx, rax; hHeap
0x18004df35  call    cs:__imp_HeapFree
0x18004df3b  mov     rbx, [rsp+80h+arg_10]
0x18004df43  mov     eax, edi
0x18004df45  add     rsp, 80h
0x18004df4c  pop     rdi
0x18004df4d  pop     rsi
0x18004df4e  pop     rbp
0x18004df4f  retn
```
