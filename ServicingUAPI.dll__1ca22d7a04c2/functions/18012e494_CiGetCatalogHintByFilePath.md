# CiGetCatalogHintByFilePath

- ea: `0x18012e494`
- end: `0x18012e611`
- name: `CiGetCatalogHintByFilePath`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180124d98`

## callees

- `0x18012e494`
- `0x18012e618`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18012e4e4`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18012e4e4`
- `ntdll!RtlReleaseRelativeName` at `0x18012e5ea`
- `ntdll!RtlReleaseRelativeName` at `0x18012e5ea`
- `ntdll!RtlFreeHeap` at `0x18012e5da`
- `ntdll!RtlFreeHeap` at `0x18012e5da`
- `ntdll!NtCreateFile` at `0x18012e58e`
- `ntdll!NtCreateFile` at `0x18012e58e`
- `ntdll!NtClose` at `0x18012e5b7`
- `ntdll!NtClose` at `0x18012e5b7`

## pseudocode

```c
__int64 __fastcall CiGetCatalogHintByFilePath(__int64 a1)
{
  __int64 result; // rax
  PVOID v2; // rdi
  HANDLE ContainingDirectory; // rax
  NTSTATUS CatalogHintByHandle; // ebx
  PVOID P[2]; // [rsp+60h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-19h] BYREF
  _RTL_RELATIVE_NAME_U RelativeName; // [rsp+80h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp+17h] BYREF
  void *FileHandle; // [rsp+100h] [rbp+77h] BYREF

  FileHandle = 0;
  *(_OWORD *)P = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&RelativeName, 0, sizeof(RelativeName));
  result = RtlDosPathNameToRelativeNtPathName_U_WithStatus(a1, P, 0, &RelativeName);
  if ( (int)result >= 0 )
  {
    v2 = P[1];
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
    CatalogHintByHandle = NtCreateFile(
                            &FileHandle,
                            0x100008u,
                            &ObjectAttributes,
                            &IoStatusBlock,
                            0,
                            0x80u,
                            7u,
                            1u,
                            0x4060u,
                            0,
                            0);
    if ( CatalogHintByHandle >= 0 )
      CatalogHintByHandle = CiGetCatalogHintByHandle(FileHandle);
    if ( FileHandle )
      NtClose(FileHandle);
    if ( v2 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
    RtlReleaseRelativeName(&RelativeName);
    return (unsigned int)CatalogHintByHandle;
  }
  return result;
}

```

## disassembly

```asm
0x18012e494  mov     [rsp-8+arg_0], rbx
0x18012e499  mov     [rsp-8+arg_8], rsi
0x18012e49e  push    rbp
0x18012e49f  push    rdi
0x18012e4a0  push    r14
0x18012e4a2  lea     rbp, [rsp-47h]
0x18012e4a7  sub     rsp, 0D0h
0x18012e4ae  xorps   xmm0, xmm0
0x18012e4b1  lea     r9, [rbp+57h+RelativeName]
0x18012e4b5  mov     rsi, rdx
0x18012e4b8  xor     r14d, r14d
0x18012e4bb  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18012e4bf  xor     eax, eax
0x18012e4c1  mov     [rbp+57h+FileHandle], r14
0x18012e4c5  xor     r8d, r8d
0x18012e4c8  lea     rdx, [rbp+57h+P]
0x18012e4cc  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18012e4d0  movups  xmmword ptr [rbp+57h+P], xmm0
0x18012e4d4  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18012e4d8  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18012e4dc  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm0
0x18012e4e0  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm0
0x18012e4e4  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x18012e4eb  nop     dword ptr [rax+rax+00h]
0x18012e4f0  test    eax, eax
0x18012e4f2  js      loc_18012E5F8
0x18012e4f8  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x18012e4fc  mov     rdi, [rbp+57h+P+8]
0x18012e500  test    ax, ax
0x18012e503  jz      short loc_18012E525
0x18012e505  mov     word ptr [rbp+57h+P], ax
0x18012e509  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x18012e50c  mov     dword ptr [rbp+57h+P+2], eax
0x18012e50f  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x18012e513  mov     word ptr [rbp+57h+P+6], ax
0x18012e517  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x18012e51b  mov     [rbp+57h+P+8], rax
0x18012e51f  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x18012e523  jmp     short loc_18012E52C
0x18012e525  mov     rax, r14
0x18012e528  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x18012e52c  mov     [rsp+0E0h+EaLength], r14d; EaLength
0x18012e531  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18012e535  mov     [rsp+0E0h+EaBuffer], r14; EaBuffer
0x18012e53a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18012e53e  mov     [rsp+0E0h+CreateOptions], 4060h; CreateOptions
0x18012e546  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18012e54a  mov     [rsp+0E0h+CreateDisposition], 1; CreateDisposition
0x18012e552  xorps   xmm0, xmm0
0x18012e555  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18012e559  mov     edx, 100008h; DesiredAccess
0x18012e55e  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x18012e566  lea     rax, [rbp+57h+P]
0x18012e56a  mov     [rsp+0E0h+FileAttributes], 80h; FileAttributes
0x18012e572  mov     [rsp+0E0h+AllocationSize], r14; AllocationSize
0x18012e577  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18012e57e  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18012e585  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18012e589  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18012e58e  call    cs:__imp_NtCreateFile
0x18012e595  nop     dword ptr [rax+rax+00h]
0x18012e59a  mov     ebx, eax
0x18012e59c  test    eax, eax
0x18012e59e  js      short loc_18012E5AE
0x18012e5a0  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18012e5a4  mov     rdx, rsi
0x18012e5a7  call    CiGetCatalogHintByHandle
0x18012e5ac  mov     ebx, eax
0x18012e5ae  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18012e5b2  test    rcx, rcx
0x18012e5b5  jz      short loc_18012E5C3
0x18012e5b7  call    cs:__imp_NtClose
0x18012e5be  nop     dword ptr [rax+rax+00h]
0x18012e5c3  test    rdi, rdi
0x18012e5c6  jz      short loc_18012E5E6
0x18012e5c8  mov     rcx, gs:60h
0x18012e5d1  mov     r8, rdi; P
0x18012e5d4  xor     edx, edx; Flags
0x18012e5d6  mov     rcx, [rcx+30h]; HeapHandle
0x18012e5da  call    cs:__imp_RtlFreeHeap
0x18012e5e1  nop     dword ptr [rax+rax+00h]
0x18012e5e6  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x18012e5ea  call    cs:__imp_RtlReleaseRelativeName
0x18012e5f1  nop     dword ptr [rax+rax+00h]
0x18012e5f6  mov     eax, ebx
0x18012e5f8  lea     r11, [rsp+0E0h+var_10]
0x18012e600  mov     rbx, [r11+20h]
0x18012e604  mov     rsi, [r11+28h]
0x18012e608  mov     rsp, r11
0x18012e60b  pop     r14
0x18012e60d  pop     rdi
0x18012e60e  pop     rbp
0x18012e60f  retn
```
