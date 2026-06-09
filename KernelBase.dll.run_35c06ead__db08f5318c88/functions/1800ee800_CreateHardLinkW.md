# CreateHardLinkW

- ea: `0x1800ee800`
- end: `0x1800eea69`
- name: `CreateHardLinkW`
- size: `617`
- prototype: `BOOL __stdcall(LPCWSTR lpFileName, LPCWSTR lpExistingFileName, LPSECURITY_ATTRIBUTES lpSecurityAttributes)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18017fe50`

## callees

- `0x1800134a0`
- `0x1800ee800`
- `0x180188ec5`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1800ee8e6`
- `ntdll!NtOpenFile` at `0x1800ee8e6`
- `ntdll!NtSetInformationFile` at `0x1800ee98d`
- `ntdll!NtSetInformationFile` at `0x1800ee98d`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800ee87a`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800ee902`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800ee87a`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800ee902`
- `ntdll!RtlSetLastWin32Error` at `0x1800ee9ae`
- `ntdll!RtlSetLastWin32Error` at `0x1800eea5f`
- `ntdll!RtlSetLastWin32Error` at `0x1800ee9ae`
- `ntdll!RtlSetLastWin32Error` at `0x1800eea5f`
- `ntdll!NtClose` at `0x1800ee9f9`
- `ntdll!NtClose` at `0x18018c39f`
- `ntdll!NtClose` at `0x1800ee9f9`
- `ntdll!NtClose` at `0x18018c39f`
- `ntdll!RtlFreeHeap` at `0x1800ee9e5`
- `ntdll!RtlFreeHeap` at `0x1800eea1b`
- `ntdll!RtlFreeHeap` at `0x1800eea3d`
- `ntdll!RtlFreeHeap` at `0x18018c38b`
- `ntdll!RtlFreeHeap` at `0x18018c3c0`
- `ntdll!RtlFreeHeap` at `0x18018c3e1`
- `ntdll!RtlFreeHeap` at `0x1800ee9e5`
- `ntdll!RtlFreeHeap` at `0x1800eea1b`
- `ntdll!RtlFreeHeap` at `0x1800eea3d`
- `ntdll!RtlFreeHeap` at `0x18018c38b`
- `ntdll!RtlFreeHeap` at `0x18018c3c0`
- `ntdll!RtlFreeHeap` at `0x18018c3e1`
- `ntdll!RtlAllocateHeap` at `0x1800ee92d`
- `ntdll!RtlAllocateHeap` at `0x1800ee92d`

## pseudocode

```c
BOOL __stdcall CreateHardLinkW(
        LPCWSTR lpFileName,
        LPCWSTR lpExistingFileName,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes)
{
  _QWORD *v5; // rdi
  NTSTATUS v6; // eax
  char *Heap; // rax
  BOOL v8; // ebx
  ULONG v9; // ecx
  struct _UNICODE_STRING NtPathName; // [rsp+38h] [rbp-70h] BYREF
  struct _UNICODE_STRING v12; // [rsp+48h] [rbp-60h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-40h] BYREF
  HANDLE FileHandle; // [rsp+B0h] [rbp+8h] BYREF

  *(_QWORD *)&v12.Length = 0;
  *(_QWORD *)&NtPathName.Length = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  FileHandle = (HANDLE)-1LL;
  if ( !lpFileName || !lpExistingFileName )
  {
    RtlSetLastWin32Error(0x57u);
    return 0;
  }
  v5 = 0;
  v12.Buffer = 0;
  NtPathName.Buffer = 0;
  if ( !RtlDosPathNameToNtPathName_U(lpExistingFileName, &v12, 0, 0) )
    goto LABEL_13;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &v12;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( lpSecurityAttributes )
    ObjectAttributes.SecurityDescriptor = lpSecurityAttributes->lpSecurityDescriptor;
  v6 = NtOpenFile(&FileHandle, 0x100100u, &ObjectAttributes, &IoStatusBlock, 7u, 0x204020u);
  if ( v6 < 0 )
    goto LABEL_11;
  if ( !RtlDosPathNameToNtPathName_U(lpFileName, &NtPathName, 0, 0) )
  {
LABEL_13:
    v9 = 3;
LABEL_14:
    RtlSetLastWin32Error(v9);
    goto LABEL_12;
  }
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, NtPathName.Length + 24LL);
  v5 = Heap;
  if ( !Heap )
  {
    v9 = 8;
    goto LABEL_14;
  }
  memmove_0(Heap + 20, NtPathName.Buffer, NtPathName.Length);
  *(_BYTE *)v5 = 0;
  v5[1] = 0;
  *((_DWORD *)v5 + 4) = NtPathName.Length;
  v6 = NtSetInformationFile(FileHandle, &IoStatusBlock, v5, NtPathName.Length + 24, FileLinkInformation);
  if ( v6 < 0 )
  {
LABEL_11:
    BaseSetLastNTError((unsigned int)v6);
LABEL_12:
    v8 = 0;
    goto LABEL_16;
  }
  v8 = 1;
LABEL_16:
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  if ( FileHandle != (HANDLE)-1LL )
    NtClose(FileHandle);
  if ( NtPathName.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  if ( v12.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12.Buffer);
  return v8;
}

```

## disassembly

```asm
0x1800ee800  mov     r11, rsp
0x1800ee803  mov     [r11+10h], rbx
0x1800ee807  mov     [r11+18h], rsi
0x1800ee80b  push    rdi
0x1800ee80c  sub     rsp, 0A0h
0x1800ee813  mov     rbx, r8
0x1800ee816  mov     rax, rdx
0x1800ee819  mov     rsi, rcx
0x1800ee81c  mov     qword ptr [r11-60h], 0
0x1800ee824  mov     qword ptr [r11-70h], 0
0x1800ee82c  xor     ecx, ecx
0x1800ee82e  xorps   xmm0, xmm0
0x1800ee831  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.Length], xmm0
0x1800ee836  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.ObjectName], xmm0
0x1800ee83b  movups  xmmword ptr [r11-24h], xmm0
0x1800ee840  movups  xmmword ptr [rsp+0A8h+IoStatusBlock], xmm0
0x1800ee845  mov     qword ptr [r11+8], 0FFFFFFFFFFFFFFFFh
0x1800ee84d  test    rsi, rsi
0x1800ee850  jz      loc_1800EEA5A
0x1800ee856  test    rax, rax
0x1800ee859  jz      loc_1800EEA5A
0x1800ee85f  xor     edi, edi
0x1800ee861  mov     [r11-78h], rdi
0x1800ee865  mov     [r11-58h], rcx
0x1800ee869  mov     [r11-68h], rcx
0x1800ee86d  xor     r9d, r9d; DirectoryInfo
0x1800ee870  xor     r8d, r8d; NtFileNamePart
0x1800ee873  lea     rdx, [r11-60h]; NtPathName
0x1800ee877  mov     rcx, rax; DosPathName
0x1800ee87a  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800ee880  test    al, al
0x1800ee882  jz      loc_1800EE9A9
0x1800ee888  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x1800ee890  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], rdi
0x1800ee895  mov     [rsp+0A8h+ObjectAttributes.Attributes], 40h ; '@'
0x1800ee8a0  lea     rax, [rsp+0A8h+var_60]
0x1800ee8a5  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rax
0x1800ee8aa  xorps   xmm0, xmm0
0x1800ee8ad  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ee8b6  test    rbx, rbx
0x1800ee8b9  jnz     loc_1800EE9B6
0x1800ee8bf  mov     [rsp+0A8h+OpenOptions], 204020h; OpenOptions
0x1800ee8c7  mov     [rsp+0A8h+ShareAccess], 7; ShareAccess
0x1800ee8cf  lea     r9, [rsp+0A8h+IoStatusBlock]; IoStatusBlock
0x1800ee8d4  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x1800ee8d9  mov     edx, 100100h; DesiredAccess
0x1800ee8de  lea     rcx, [rsp+0A8h+FileHandle]; FileHandle
0x1800ee8e6  call    cs:__imp_NtOpenFile
0x1800ee8ec  test    eax, eax
0x1800ee8ee  js      loc_1800EE99E
0x1800ee8f4  xor     r9d, r9d; DirectoryInfo
0x1800ee8f7  xor     r8d, r8d; NtFileNamePart
0x1800ee8fa  lea     rdx, [rsp+0A8h+NtPathName]; NtPathName
0x1800ee8ff  mov     rcx, rsi; DosPathName
0x1800ee902  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800ee908  test    al, al
0x1800ee90a  jz      loc_1800EE9A9
0x1800ee910  mov     edx, cs:KernelBaseGlobalData; Flags
0x1800ee916  movzx   r8d, [rsp+0A8h+NtPathName.Length]
0x1800ee91c  add     r8, 18h; Size
0x1800ee920  mov     rcx, gs:60h
0x1800ee929  mov     rcx, [rcx+30h]; HeapHandle
0x1800ee92d  call    cs:__imp_RtlAllocateHeap
0x1800ee933  mov     rdi, rax
0x1800ee936  mov     [rsp+0A8h+var_78], rax
0x1800ee93b  test    rax, rax
0x1800ee93e  jz      loc_1800EE9C7
0x1800ee944  movzx   r8d, [rsp+0A8h+NtPathName.Length]; Size
0x1800ee94a  lea     rcx, [rax+14h]; void *
0x1800ee94e  mov     rdx, [rsp+0A8h+NtPathName.Buffer]; Src
0x1800ee953  call    memmove_0
0x1800ee958  mov     byte ptr [rdi], 0
0x1800ee95b  mov     qword ptr [rdi+8], 0
0x1800ee963  movzx   eax, [rsp+0A8h+NtPathName.Length]
0x1800ee968  mov     [rdi+10h], eax
0x1800ee96b  movzx   r9d, [rsp+0A8h+NtPathName.Length]
0x1800ee971  add     r9d, 18h; Length
0x1800ee975  mov     [rsp+0A8h+ShareAccess], 0Bh; FileInformationClass
0x1800ee97d  mov     r8, rdi; FileInformation
0x1800ee980  lea     rdx, [rsp+0A8h+IoStatusBlock]; IoStatusBlock
0x1800ee985  mov     rcx, [rsp+0A8h+FileHandle]; FileHandle
0x1800ee98d  call    cs:__imp_NtSetInformationFile
0x1800ee993  test    eax, eax
0x1800ee995  js      short loc_1800EE99E
0x1800ee997  mov     ebx, 1
0x1800ee99c  jmp     short loc_1800EE9CE
0x1800ee99e  mov     ecx, eax
0x1800ee9a0  call    BaseSetLastNTError
0x1800ee9a5  xor     ebx, ebx
0x1800ee9a7  jmp     short loc_1800EE9CE
0x1800ee9a9  mov     ecx, 3; LastError
0x1800ee9ae  call    cs:__imp_RtlSetLastWin32Error
0x1800ee9b4  jmp     short loc_1800EE9A5
0x1800ee9b6  mov     rax, [rbx+8]
0x1800ee9ba  mov     [rsp+0A8h+ObjectAttributes.SecurityDescriptor], rax
0x1800ee9c2  jmp     loc_1800EE8BF
0x1800ee9c7  mov     ecx, 8
0x1800ee9cc  jmp     short loc_1800EE9AE
0x1800ee9ce  test    rdi, rdi
0x1800ee9d1  jz      short loc_1800EE9EB
0x1800ee9d3  mov     rcx, gs:60h
0x1800ee9dc  mov     r8, rdi; P
0x1800ee9df  xor     edx, edx; Flags
0x1800ee9e1  mov     rcx, [rcx+30h]; HeapHandle
0x1800ee9e5  call    cs:__imp_RtlFreeHeap
0x1800ee9eb  mov     rcx, [rsp+0A8h+FileHandle]; Handle
0x1800ee9f3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800ee9f7  jz      short loc_1800EE9FF
0x1800ee9f9  call    cs:__imp_NtClose
0x1800ee9ff  cmp     [rsp+0A8h+NtPathName.Buffer], 0
0x1800eea05  jz      short loc_1800EEA21
0x1800eea07  mov     rcx, gs:60h
0x1800eea10  mov     r8, [rsp+0A8h+NtPathName.Buffer]; P
0x1800eea15  xor     edx, edx; Flags
0x1800eea17  mov     rcx, [rcx+30h]; HeapHandle
0x1800eea1b  call    cs:__imp_RtlFreeHeap
0x1800eea21  cmp     [rsp+0A8h+P], 0
0x1800eea27  jz      short loc_1800EEA43
0x1800eea29  mov     rcx, gs:60h
0x1800eea32  mov     r8, [rsp+0A8h+P]; P
0x1800eea37  xor     edx, edx; Flags
0x1800eea39  mov     rcx, [rcx+30h]; HeapHandle
0x1800eea3d  call    cs:__imp_RtlFreeHeap
0x1800eea43  mov     eax, ebx
0x1800eea45  lea     r11, [rsp+0A8h+var_8]
0x1800eea4d  mov     rbx, [r11+18h]
0x1800eea51  mov     rsi, [r11+20h]
0x1800eea55  mov     rsp, r11
0x1800eea58  pop     rdi
0x1800eea59  retn
0x1800eea5a  mov     ecx, 57h ; 'W'; LastError
0x1800eea5f  call    cs:__imp_RtlSetLastWin32Error
0x1800eea65  xor     eax, eax
0x1800eea67  jmp     short loc_1800EEA45
0x18018c36a  push    rbp
0x18018c36c  sub     rsp, 30h
0x18018c370  mov     rbp, rdx
0x18018c373  mov     r8, [rbp+30h]; P
0x18018c377  test    r8, r8
0x18018c37a  jz      short loc_18018C392
0x18018c37c  mov     rcx, gs:60h
0x18018c385  xor     edx, edx; Flags
0x18018c387  mov     rcx, [rcx+30h]; HeapHandle
0x18018c38b  call    cs:__imp_RtlFreeHeap
0x18018c391  nop
0x18018c392  mov     rcx, [rbp+0B0h]; Handle
0x18018c399  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18018c39d  jz      short loc_18018C3A6
0x18018c39f  call    cs:__imp_NtClose
0x18018c3a5  nop
0x18018c3a6  cmp     qword ptr [rbp+40h], 0
0x18018c3ab  jz      short loc_18018C3C7
0x18018c3ad  mov     rcx, gs:60h
0x18018c3b6  mov     r8, [rbp+40h]; P
0x18018c3ba  xor     edx, edx; Flags
0x18018c3bc  mov     rcx, [rcx+30h]; HeapHandle
0x18018c3c0  call    cs:__imp_RtlFreeHeap
0x18018c3c6  nop
0x18018c3c7  cmp     qword ptr [rbp+50h], 0
0x18018c3cc  jz      short loc_18018C3E8
0x18018c3ce  mov     rcx, gs:60h
0x18018c3d7  mov     r8, [rbp+50h]; P
0x18018c3db  xor     edx, edx; Flags
0x18018c3dd  mov     rcx, [rcx+30h]; HeapHandle
0x18018c3e1  call    cs:__imp_RtlFreeHeap
0x18018c3e7  nop
0x18018c3e8  add     rsp, 30h
0x18018c3ec  pop     rbp
0x18018c3ed  retn
```
