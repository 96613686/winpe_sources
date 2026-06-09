# AslDoesFileExistNtPath

- ea: `0x14003c0c8`
- end: `0x14003c338`
- name: `AslDoesFileExistNtPath`
- size: `624`
- prototype: `__int64 __fastcall(PWSTR FileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14003e294`

## callees

- `0x14003bf18`
- `0x14003c0c8`
- `0x14003c368`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x14003c26c`
- `msvcrt!_wcsnicmp` at `0x14003c26c`
- `ntdll!RtlInitUnicodeString` at `0x14003c10e`
- `ntdll!RtlInitUnicodeString` at `0x14003c10e`
- `ntdll!RtlFreeUnicodeString` at `0x14003c1fe`
- `ntdll!RtlFreeUnicodeString` at `0x14003c1fe`
- `ntdll!ZwClose` at `0x14003c307`
- `ntdll!ZwClose` at `0x14003c307`
- `ntdll!RtlAllocateHeap` at `0x14003c1c9`
- `ntdll!RtlAllocateHeap` at `0x14003c1c9`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14003c283`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14003c283`
- `ntdll!ZwOpenFile` at `0x14003c2e2`
- `ntdll!ZwOpenFile` at `0x14003c2e2`
- `ntdll!RtlGetFullPathName_UEx` at `0x14003c171`
- `ntdll!RtlGetFullPathName_UEx` at `0x14003c171`

## string_xrefs

- `0x14003c312`: `Failed to get full path [%x]`
- `0x14003c1e6`: `AslDoesFileExistNtPath`
- `0x14003c249`: `AslDoesFileExistNtPath`
- `0x14003c31f`: `AslDoesFileExistNtPath`
- `0x14003c28d`: `RtlDosPathNameToNtPathName_U_WithStatus failed [%x]`
- `0x14003c23c`: `RtlGetFullPathName_UEx failed to get full path with larger buffer.`

## pseudocode

```c
__int64 __fastcall AslDoesFileExistNtPath(PWSTR FileName)
{
  WCHAR *Heap; // rdi
  RTL_PATH_TYPE v3; // ebx
  char v4; // r14
  SIZE_T i; // r8
  NTSTATUS FullPathName_UEx; // eax
  bool v7; // cf
  unsigned int v8; // ebx
  const char *v10; // r9
  __int64 v11; // r8
  NTSTATUS v12; // eax
  RTL_PATH_TYPE *InputPathType; // [rsp+20h] [rbp-60h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  RTL_PATH_TYPE v17; // [rsp+B0h] [rbp+30h] BYREF
  void *FileHandle; // [rsp+B8h] [rbp+38h] BYREF

  FileHandle = 0;
  v17 = RtlPathTypeUnknown;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  IoStatusBlock = 0;
  RtlInitUnicodeString(&DestinationString, FileName);
  if ( DestinationString.Length <= 8u
    || *DestinationString.Buffer != 92
    || DestinationString.Buffer[1] != 92 && DestinationString.Buffer[1] != 63
    || DestinationString.Buffer[2] != 63
    || (Heap = 0, DestinationString.Buffer[3] != 92) )
  {
    v3 = 520;
    v4 = 0;
    for ( i = 520; ; i = (unsigned int)v3 )
    {
      Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, i);
      if ( !Heap )
      {
        v8 = 0;
        AslLogCallPrintf(1, "AslDoesFileExistNtPath", 658, "Out of memory");
        goto LABEL_16;
      }
      FullPathName_UEx = RtlGetFullPathName_UEx(FileName, v3, Heap, 0, &v17);
      if ( FullPathName_UEx < 0 )
      {
        v10 = "Failed to get full path [%x]";
        v11 = 669;
        goto LABEL_31;
      }
      v7 = v17 < (unsigned int)v3;
      if ( v17 > (unsigned int)v3 )
      {
        if ( v4 )
        {
          AslLogCallPrintf(
            1,
            "AslDoesFileExistNtPath",
            678,
            "RtlGetFullPathName_UEx failed to get full path with larger buffer.");
          goto LABEL_32;
        }
        AslFree(NtCurrentPeb()->ProcessHeap, Heap);
        Heap = 0;
        v3 = v17;
        v7 = 0;
      }
      if ( v7 )
        break;
      v4 = 1;
    }
    if ( _wcsnicmp(Heap, L"\\SystemRoot\\", 0xCu) )
    {
      FullPathName_UEx = RtlDosPathNameToNtPathName_U_WithStatus(Heap, &DestinationString, 0, 0);
      if ( FullPathName_UEx < 0 )
      {
        v10 = "RtlDosPathNameToNtPathName_U_WithStatus failed [%x]";
        v11 = 701;
LABEL_31:
        LODWORD(InputPathType) = FullPathName_UEx;
        AslLogCallPrintf(1, "AslDoesFileExistNtPath", v11, v10, InputPathType);
        goto LABEL_32;
      }
    }
  }
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v12 = ZwOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 1u, 0);
  if ( v12 >= 0 )
  {
    v8 = 1;
    ZwClose(FileHandle);
  }
  else if ( v12 == -1073741757 || v12 == -1073741790 )
  {
    v8 = 1;
  }
  else
  {
LABEL_32:
    v8 = 0;
  }
LABEL_16:
  if ( DestinationString.Buffer != FileName )
    RtlFreeUnicodeString(&DestinationString);
  if ( Heap )
    AslFree(NtCurrentPeb()->ProcessHeap, Heap);
  return v8;
}

```

## disassembly

```asm
0x14003c0c8  mov     [rsp-28h+arg_10], rbx
0x14003c0cd  mov     [rsp-28h+arg_18], rsi
0x14003c0d2  push    rbp
0x14003c0d3  push    rdi
0x14003c0d4  push    r13
0x14003c0d6  push    r14
0x14003c0d8  push    r15
0x14003c0da  mov     rbp, rsp
0x14003c0dd  sub     rsp, 80h
0x14003c0e4  xorps   xmm0, xmm0
0x14003c0e7  xor     eax, eax
0x14003c0e9  mov     r15, rcx
0x14003c0ec  mov     [rbp+FileHandle], rax
0x14003c0f0  mov     rdx, rcx; SourceString
0x14003c0f3  mov     [rbp+arg_0], eax
0x14003c0f6  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14003c0fa  lea     rcx, [rbp+DestinationString]; DestinationString
0x14003c0fe  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14003c102  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14003c106  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14003c10a  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x14003c10e  call    cs:__imp_RtlInitUnicodeString
0x14003c114  mov     esi, 1
0x14003c119  lea     r13d, [rsi+7]
0x14003c11d  cmp     [rbp+DestinationString.Length], r13w
0x14003c122  jbe     short loc_14003C150
0x14003c124  mov     rax, [rbp+DestinationString.Buffer]
0x14003c128  cmp     word ptr [rax], 5Ch ; '\'
0x14003c12c  jnz     short loc_14003C150
0x14003c12e  cmp     word ptr [rax+2], 5Ch ; '\'
0x14003c133  jz      short loc_14003C13C
0x14003c135  cmp     word ptr [rax+2], 3Fh ; '?'
0x14003c13a  jnz     short loc_14003C150
0x14003c13c  cmp     word ptr [rax+4], 3Fh ; '?'
0x14003c141  jnz     short loc_14003C150
0x14003c143  xor     edi, edi
0x14003c145  cmp     word ptr [rax+6], 5Ch ; '\'
0x14003c14a  jz      loc_14003C29F
0x14003c150  mov     ebx, 208h
0x14003c155  xor     r14b, r14b
0x14003c158  mov     r8d, ebx
0x14003c15b  jmp     short loc_14003C1B9
0x14003c15d  lea     rax, [rbp+arg_0]
0x14003c161  xor     r9d, r9d; FilePart
0x14003c164  mov     r8, rdi; Buffer
0x14003c167  mov     [rsp+80h+InputPathType], rax; InputPathType
0x14003c16c  mov     edx, ebx; BufferLength
0x14003c16e  mov     rcx, r15; FileName
0x14003c171  call    cs:__imp_RtlGetFullPathName_UEx
0x14003c177  test    eax, eax
0x14003c179  js      loc_14003C312
0x14003c17f  mov     eax, [rbp+arg_0]
0x14003c182  cmp     eax, ebx
0x14003c184  jbe     short loc_14003C1AD
0x14003c186  test    r14b, r14b
0x14003c189  jnz     loc_14003C23C
0x14003c18f  mov     rcx, gs:60h
0x14003c198  mov     rdx, rdi
0x14003c19b  mov     rcx, [rcx+30h]
0x14003c19f  call    AslFree
0x14003c1a4  mov     eax, [rbp+arg_0]
0x14003c1a7  xor     edi, edi
0x14003c1a9  mov     ebx, eax
0x14003c1ab  cmp     eax, eax
0x14003c1ad  jb      loc_14003C25C
0x14003c1b3  mov     r14b, sil
0x14003c1b6  mov     r8d, ebx; Size
0x14003c1b9  mov     rcx, gs:60h
0x14003c1c2  mov     edx, r13d; Flags
0x14003c1c5  mov     rcx, [rcx+30h]; HeapHandle
0x14003c1c9  call    cs:__imp_RtlAllocateHeap
0x14003c1cf  mov     rdi, rax
0x14003c1d2  test    rax, rax
0x14003c1d5  jnz     short loc_14003C15D
0x14003c1d7  xor     ebx, ebx
0x14003c1d9  lea     r9, aOutOfMemory; "Out of memory"
0x14003c1e0  mov     r8d, 292h
0x14003c1e6  lea     rdx, aAsldoesfileexi; "AslDoesFileExistNtPath"
0x14003c1ed  mov     ecx, esi
0x14003c1ef  call    AslLogCallPrintf
0x14003c1f4  cmp     [rbp+DestinationString.Buffer], r15
0x14003c1f8  jz      short loc_14003C204
0x14003c1fa  lea     rcx, [rbp+DestinationString]; UnicodeString
0x14003c1fe  call    cs:__imp_RtlFreeUnicodeString
0x14003c204  test    rdi, rdi
0x14003c207  jz      short loc_14003C21E
0x14003c209  mov     rcx, gs:60h
0x14003c212  mov     rdx, rdi
0x14003c215  mov     rcx, [rcx+30h]
0x14003c219  call    AslFree
0x14003c21e  lea     r11, [rsp+80h+var_s0]
0x14003c226  mov     eax, ebx
0x14003c228  mov     rbx, [r11+40h]
0x14003c22c  mov     rsi, [r11+48h]
0x14003c230  mov     rsp, r11
0x14003c233  pop     r15
0x14003c235  pop     r14
0x14003c237  pop     r13
0x14003c239  pop     rdi
0x14003c23a  pop     rbp
0x14003c23b  retn
0x14003c23c  lea     r9, aRtlgetfullpath; "RtlGetFullPathName_UEx failed to get fu"...
0x14003c243  mov     r8d, 2A6h
0x14003c249  lea     rdx, aAsldoesfileexi; "AslDoesFileExistNtPath"
0x14003c250  mov     ecx, esi
0x14003c252  call    AslLogCallPrintf
0x14003c257  jmp     loc_14003C331
0x14003c25c  mov     r8d, 0Ch; MaxCount
0x14003c262  lea     rdx, aSystemroot_3; "\\SystemRoot\\"
0x14003c269  mov     rcx, rdi; String1
0x14003c26c  call    cs:__imp__wcsnicmp
0x14003c272  test    eax, eax
0x14003c274  jz      short loc_14003C29F
0x14003c276  xor     r9d, r9d
0x14003c279  lea     rdx, [rbp+DestinationString]
0x14003c27d  xor     r8d, r8d
0x14003c280  mov     rcx, rdi
0x14003c283  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x14003c289  test    eax, eax
0x14003c28b  jns     short loc_14003C29F
0x14003c28d  lea     r9, aRtldospathname; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x14003c294  mov     r8d, 2BDh
0x14003c29a  jmp     loc_14003C31F
0x14003c29f  lea     rax, [rbp+DestinationString]
0x14003c2a3  mov     [rsp+80h+OpenOptions], 0; OpenOptions
0x14003c2ab  xorps   xmm0, xmm0
0x14003c2ae  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14003c2b2  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x14003c2b6  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14003c2bd  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14003c2c1  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14003c2c9  mov     edx, 100080h; DesiredAccess
0x14003c2ce  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x14003c2d5  lea     rcx, [rbp+FileHandle]; FileHandle
0x14003c2d9  mov     dword ptr [rsp+80h+InputPathType], esi; ShareAccess
0x14003c2dd  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14003c2e2  call    cs:__imp_ZwOpenFile
0x14003c2e8  test    eax, eax
0x14003c2ea  jns     short loc_14003C301
0x14003c2ec  cmp     eax, 0C0000043h
0x14003c2f1  jz      short loc_14003C2FA
0x14003c2f3  cmp     eax, 0C0000022h
0x14003c2f8  jnz     short loc_14003C331
0x14003c2fa  mov     ebx, esi
0x14003c2fc  jmp     loc_14003C1F4
0x14003c301  mov     rcx, [rbp+FileHandle]; Handle
0x14003c305  mov     ebx, esi
0x14003c307  call    cs:__imp_ZwClose
0x14003c30d  jmp     loc_14003C1F4
0x14003c312  lea     r9, aFailedToGetFul_0; "Failed to get full path [%x]"
0x14003c319  mov     r8d, 29Dh
0x14003c31f  lea     rdx, aAsldoesfileexi; "AslDoesFileExistNtPath"
0x14003c326  mov     dword ptr [rsp+80h+InputPathType], eax
0x14003c32a  mov     ecx, esi
0x14003c32c  call    AslLogCallPrintf
0x14003c331  xor     ebx, ebx
0x14003c333  jmp     loc_14003C1F4
```
