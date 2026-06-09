# CiSetCatalogHintByFilePath

- ea: `0x18012e8e8`
- end: `0x18012ea94`
- name: `CiSetCatalogHintByFilePath`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180124d98`

## callees

- `0x18012e8e8`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18012e933`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18012e933`
- `ntdll!NtSetEaFile` at `0x18012ea08`
- `ntdll!NtSetEaFile` at `0x18012ea08`
- `ntdll!RtlReleaseRelativeName` at `0x18012ea75`
- `ntdll!RtlReleaseRelativeName` at `0x18012ea75`
- `ntdll!NtWaitForSingleObject` at `0x18012ea25`
- `ntdll!NtWaitForSingleObject` at `0x18012ea25`
- `ntdll!RtlFreeHeap` at `0x18012ea65`
- `ntdll!RtlFreeHeap` at `0x18012ea65`
- `ntdll!NtCreateFile` at `0x18012e9dd`
- `ntdll!NtCreateFile` at `0x18012e9dd`
- `ntdll!NtClose` at `0x18012ea42`
- `ntdll!NtClose` at `0x18012ea42`

## pseudocode

```c
__int64 __fastcall CiSetCatalogHintByFilePath(__int64 a1, ULONG *a2)
{
  __int64 result; // rax
  PVOID v4; // rdi
  HANDLE ContainingDirectory; // rax
  NTSTATUS Status; // ebx
  void *v7; // rsi
  ULONG v8; // r9d
  PVOID P[2]; // [rsp+60h] [rbp-59h] BYREF
  struct _IO_STATUS_BLOCK v10; // [rsp+70h] [rbp-49h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-39h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+90h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-9h] BYREF
  void *FileHandle; // [rsp+130h] [rbp+77h] BYREF

  FileHandle = 0;
  *(_OWORD *)P = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&RelativeName, 0, sizeof(RelativeName));
  result = RtlDosPathNameToRelativeNtPathName_U_WithStatus(a1, P, 0, &RelativeName);
  if ( (int)result >= 0 )
  {
    v4 = P[1];
    if ( RelativeName.RelativeName.Length )
    {
      LOWORD(P[0]) = RelativeName.RelativeName.Length;
      *(_DWORD *)((char *)P + 2) = *(_DWORD *)&RelativeName.RelativeName.MaximumLength;
      HIWORD(P[0]) = *(&RelativeName.RelativeName.MaximumLength + 2);
      P[1] = RelativeName.RelativeName.Buffer;
      ContainingDirectory = RelativeName.ContainingDirectory;
    }
    else
    {
      ContainingDirectory = 0;
      RelativeName.ContainingDirectory = 0;
    }
    ObjectAttributes.RootDirectory = ContainingDirectory;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    Status = NtCreateFile(&FileHandle, 0x100010u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x4060u, 0, 0);
    if ( Status >= 0 )
    {
      v7 = FileHandle;
      v8 = *a2;
      v10 = 0;
      Status = NtSetEaFile(FileHandle, &v10, a2 + 1, v8);
      if ( Status == 259 )
      {
        Status = NtWaitForSingleObject(v7, 0, 0);
        if ( Status >= 0 )
          Status = v10.Status;
      }
    }
    if ( FileHandle )
      NtClose(FileHandle);
    if ( v4 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    RtlReleaseRelativeName(&RelativeName);
    return (unsigned int)Status;
  }
  return result;
}

```

## disassembly

```asm
0x18012e8e8  push    rbp
0x18012e8ea  push    rbx
0x18012e8eb  push    rsi
0x18012e8ec  push    rdi
0x18012e8ed  push    r14
0x18012e8ef  push    r15
0x18012e8f1  lea     rbp, [rsp-2Fh]
0x18012e8f6  sub     rsp, 0E8h
0x18012e8fd  xorps   xmm0, xmm0
0x18012e900  lea     r9, [rbp+57h+RelativeName]
0x18012e904  mov     r14, rdx
0x18012e907  xor     r15d, r15d
0x18012e90a  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18012e90e  xor     eax, eax
0x18012e910  mov     [rbp+57h+FileHandle], r15
0x18012e914  xor     r8d, r8d
0x18012e917  lea     rdx, [rbp+57h+P]
0x18012e91b  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18012e91f  movups  xmmword ptr [rbp+57h+P], xmm0
0x18012e923  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18012e927  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18012e92b  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm0
0x18012e92f  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm0
0x18012e933  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x18012e93a  nop     dword ptr [rax+rax+00h]
0x18012e93f  test    eax, eax
0x18012e941  js      loc_18012EA83
0x18012e947  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x18012e94b  mov     rdi, [rbp+57h+P+8]
0x18012e94f  test    ax, ax
0x18012e952  jz      short loc_18012E974
0x18012e954  mov     word ptr [rbp+57h+P], ax
0x18012e958  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x18012e95b  mov     dword ptr [rbp+57h+P+2], eax
0x18012e95e  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x18012e962  mov     word ptr [rbp+57h+P+6], ax
0x18012e966  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x18012e96a  mov     [rbp+57h+P+8], rax
0x18012e96e  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x18012e972  jmp     short loc_18012E97B
0x18012e974  mov     rax, r15
0x18012e977  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x18012e97b  mov     [rsp+110h+EaLength], r15d; EaLength
0x18012e980  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18012e984  mov     [rsp+110h+EaBuffer], r15; EaBuffer
0x18012e989  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18012e98d  mov     [rsp+110h+CreateOptions], 4060h; CreateOptions
0x18012e995  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18012e999  mov     [rsp+110h+CreateDisposition], 1; CreateDisposition
0x18012e9a1  xorps   xmm0, xmm0
0x18012e9a4  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18012e9a8  mov     edx, 100010h; DesiredAccess
0x18012e9ad  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x18012e9b5  lea     rax, [rbp+57h+P]
0x18012e9b9  mov     [rsp+110h+FileAttributes], 80h; FileAttributes
0x18012e9c1  mov     [rsp+110h+AllocationSize], r15; AllocationSize
0x18012e9c6  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18012e9cd  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18012e9d4  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18012e9d8  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18012e9dd  call    cs:__imp_NtCreateFile
0x18012e9e4  nop     dword ptr [rax+rax+00h]
0x18012e9e9  mov     ebx, eax
0x18012e9eb  test    eax, eax
0x18012e9ed  js      short loc_18012EA39
0x18012e9ef  mov     rsi, [rbp+57h+FileHandle]
0x18012e9f3  lea     r8, [r14+4]; EaBuffer
0x18012e9f7  mov     r9d, [r14]; EaBufferSize
0x18012e9fa  lea     rdx, [rbp+57h+var_A0]; IoStatusBlock
0x18012e9fe  xorps   xmm0, xmm0
0x18012ea01  mov     rcx, rsi; FileHandle
0x18012ea04  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x18012ea08  call    cs:__imp_NtSetEaFile
0x18012ea0f  nop     dword ptr [rax+rax+00h]
0x18012ea14  mov     ebx, eax
0x18012ea16  cmp     eax, 103h
0x18012ea1b  jnz     short loc_18012EA39
0x18012ea1d  xor     r8d, r8d; Timeout
0x18012ea20  xor     edx, edx; Alertable
0x18012ea22  mov     rcx, rsi; Handle
0x18012ea25  call    cs:__imp_NtWaitForSingleObject
0x18012ea2c  nop     dword ptr [rax+rax+00h]
0x18012ea31  test    eax, eax
0x18012ea33  mov     ebx, eax
0x18012ea35  cmovns  ebx, dword ptr [rbp+57h+var_A0]
0x18012ea39  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18012ea3d  test    rcx, rcx
0x18012ea40  jz      short loc_18012EA4E
0x18012ea42  call    cs:__imp_NtClose
0x18012ea49  nop     dword ptr [rax+rax+00h]
0x18012ea4e  test    rdi, rdi
0x18012ea51  jz      short loc_18012EA71
0x18012ea53  mov     rcx, gs:60h
0x18012ea5c  mov     r8, rdi; P
0x18012ea5f  xor     edx, edx; Flags
0x18012ea61  mov     rcx, [rcx+30h]; HeapHandle
0x18012ea65  call    cs:__imp_RtlFreeHeap
0x18012ea6c  nop     dword ptr [rax+rax+00h]
0x18012ea71  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x18012ea75  call    cs:__imp_RtlReleaseRelativeName
0x18012ea7c  nop     dword ptr [rax+rax+00h]
0x18012ea81  mov     eax, ebx
0x18012ea83  add     rsp, 0E8h
0x18012ea8a  pop     r15
0x18012ea8c  pop     r14
0x18012ea8e  pop     rdi
0x18012ea8f  pop     rsi
0x18012ea90  pop     rbx
0x18012ea91  pop     rbp
0x18012ea92  retn
```
