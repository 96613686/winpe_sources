# AslDoesFileExistNtPath

- ea: `0x18003c2d0`
- end: `0x18003c534`
- name: `AslDoesFileExistNtPath`
- size: `612`
- prototype: `__int64 __fastcall(PWSTR FileName)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180034bb0`
- `0x180055890`

## callees

- `0x18000f114`
- `0x180018f20`
- `0x180039a66`
- `0x18003c2d0`

## import_xrefs

- `ntdll!RtlGetFullPathName_UEx` at `0x18003c39b`
- `ntdll!RtlGetFullPathName_UEx` at `0x18003c39b`
- `ntdll!RtlInitUnicodeString` at `0x18003c316`
- `ntdll!RtlInitUnicodeString` at `0x18003c316`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18003c421`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18003c421`
- `ntdll!ZwClose` at `0x18003c4a2`
- `ntdll!ZwClose` at `0x18003c4a2`
- `ntdll!ZwOpenFile` at `0x18003c47e`
- `ntdll!ZwOpenFile` at `0x18003c47e`
- `ntdll!RtlFreeUnicodeString` at `0x18003c4f6`
- `ntdll!RtlFreeUnicodeString` at `0x18003c4f6`
- `ntdll!RtlAllocateHeap` at `0x18003c375`
- `ntdll!RtlAllocateHeap` at `0x18003c375`

## string_xrefs

- `0x18003c3e7`: `AslDoesFileExistNtPath`
- `0x18003c4b7`: `AslDoesFileExistNtPath`
- `0x18003c4dd`: `AslDoesFileExistNtPath`
- `0x18003c4aa`: `Failed to get full path [%x]`
- `0x18003c3da`: `RtlGetFullPathName_UEx failed to get full path with larger buffer.`
- `0x18003c42b`: `RtlDosPathNameToNtPathName_U_WithStatus failed [%x]`

## pseudocode

```c
__int64 __fastcall AslDoesFileExistNtPath(PWSTR FileName)
{
  WCHAR *Heap; // rdi
  char v3; // si
  RTL_PATH_TYPE v4; // ebx
  NTSTATUS FullPathName_UEx; // eax
  bool v6; // cf
  const char *v7; // r9
  __int64 v8; // r8
  NTSTATUS v9; // eax
  unsigned int v10; // ebx
  RTL_PATH_TYPE *InputPathType; // [rsp+20h] [rbp-60h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  RTL_PATH_TYPE v16; // [rsp+B0h] [rbp+30h] BYREF
  void *FileHandle; // [rsp+B8h] [rbp+38h] BYREF

  FileHandle = 0;
  v16 = RtlPathTypeUnknown;
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
    v3 = 0;
    v4 = 520;
    while ( 1 )
    {
      Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)v4);
      if ( !Heap )
      {
        v10 = 0;
        AslLogCallPrintf(1, "AslDoesFileExistNtPath", 658, "Out of memory");
        goto LABEL_28;
      }
      FullPathName_UEx = RtlGetFullPathName_UEx(FileName, v4, Heap, 0, &v16);
      if ( FullPathName_UEx < 0 )
      {
        v7 = "Failed to get full path [%x]";
        v8 = 669;
        goto LABEL_25;
      }
      v6 = v16 < (unsigned int)v4;
      if ( v16 > (unsigned int)v4 )
      {
        if ( v3 )
        {
          AslLogCallPrintf(
            1,
            "AslDoesFileExistNtPath",
            678,
            "RtlGetFullPathName_UEx failed to get full path with larger buffer.");
          goto LABEL_26;
        }
        AslFree(NtCurrentPeb()->ProcessHeap, Heap);
        Heap = 0;
        v4 = v16;
        v6 = 0;
      }
      if ( v6 )
        break;
      v3 = 1;
    }
    if ( wcsnicmp_0(Heap, L"\\SystemRoot\\", 0xCu) )
    {
      FullPathName_UEx = RtlDosPathNameToNtPathName_U_WithStatus(Heap, &DestinationString, 0, 0);
      if ( FullPathName_UEx < 0 )
      {
        v7 = "RtlDosPathNameToNtPathName_U_WithStatus failed [%x]";
        v8 = 701;
LABEL_25:
        LODWORD(InputPathType) = FullPathName_UEx;
        AslLogCallPrintf(1, "AslDoesFileExistNtPath", v8, v7, InputPathType);
        goto LABEL_26;
      }
    }
  }
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = ZwOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 1u, 0);
  if ( v9 >= 0 )
  {
    v10 = 1;
    ZwClose(FileHandle);
  }
  else if ( v9 == -1073741757 || v9 == -1073741790 )
  {
    v10 = 1;
  }
  else
  {
LABEL_26:
    v10 = 0;
  }
LABEL_28:
  if ( DestinationString.Buffer != FileName )
    RtlFreeUnicodeString(&DestinationString);
  if ( Heap )
    AslFree(NtCurrentPeb()->ProcessHeap, Heap);
  return v10;
}

```

## disassembly

```asm
0x18003c2d0  mov     [rsp-28h+arg_10], rbx
0x18003c2d5  mov     [rsp-28h+arg_18], rsi
0x18003c2da  push    rbp
0x18003c2db  push    rdi
0x18003c2dc  push    r12
0x18003c2de  push    r13
0x18003c2e0  push    r14
0x18003c2e2  mov     rbp, rsp
0x18003c2e5  sub     rsp, 80h
0x18003c2ec  xorps   xmm0, xmm0
0x18003c2ef  xor     eax, eax
0x18003c2f1  mov     r14, rcx
0x18003c2f4  mov     [rbp+FileHandle], rax
0x18003c2f8  mov     rdx, rcx; SourceString
0x18003c2fb  mov     [rbp+arg_0], eax
0x18003c2fe  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18003c302  lea     rcx, [rbp+DestinationString]; DestinationString
0x18003c306  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18003c30a  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18003c30e  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18003c312  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x18003c316  call    cs:__imp_RtlInitUnicodeString
0x18003c31c  mov     r12d, 1
0x18003c322  lea     r13d, [r12+7]
0x18003c327  cmp     [rbp+DestinationString.Length], r13w
0x18003c32c  jbe     short loc_18003C35A
0x18003c32e  mov     rax, [rbp+DestinationString.Buffer]
0x18003c332  cmp     word ptr [rax], 5Ch ; '\'
0x18003c336  jnz     short loc_18003C35A
0x18003c338  cmp     word ptr [rax+2], 5Ch ; '\'
0x18003c33d  jz      short loc_18003C346
0x18003c33f  cmp     word ptr [rax+2], 3Fh ; '?'
0x18003c344  jnz     short loc_18003C35A
0x18003c346  cmp     word ptr [rax+4], 3Fh ; '?'
0x18003c34b  jnz     short loc_18003C35A
0x18003c34d  xor     edi, edi
0x18003c34f  cmp     word ptr [rax+6], 5Ch ; '\'
0x18003c354  jz      loc_18003C43A
0x18003c35a  xor     sil, sil
0x18003c35d  mov     ebx, 208h
0x18003c362  mov     rcx, gs:60h
0x18003c36b  mov     edx, r13d; Flags
0x18003c36e  mov     r8d, ebx; Size
0x18003c371  mov     rcx, [rcx+30h]; HeapHandle
0x18003c375  call    cs:__imp_RtlAllocateHeap
0x18003c37b  mov     rdi, rax
0x18003c37e  test    rax, rax
0x18003c381  jz      loc_18003C4CE
0x18003c387  lea     rax, [rbp+arg_0]
0x18003c38b  xor     r9d, r9d; FilePart
0x18003c38e  mov     r8, rdi; Buffer
0x18003c391  mov     [rsp+80h+InputPathType], rax; InputPathType
0x18003c396  mov     edx, ebx; BufferLength
0x18003c398  mov     rcx, r14; FileName
0x18003c39b  call    cs:__imp_RtlGetFullPathName_UEx
0x18003c3a1  test    eax, eax
0x18003c3a3  js      loc_18003C4AA
0x18003c3a9  mov     eax, [rbp+arg_0]
0x18003c3ac  cmp     eax, ebx
0x18003c3ae  jbe     short loc_18003C3D3
0x18003c3b0  test    sil, sil
0x18003c3b3  jnz     short loc_18003C3DA
0x18003c3b5  mov     rcx, gs:60h
0x18003c3be  mov     rdx, rdi
0x18003c3c1  mov     rcx, [rcx+30h]
0x18003c3c5  call    AslFree
0x18003c3ca  mov     eax, [rbp+arg_0]
0x18003c3cd  xor     edi, edi
0x18003c3cf  mov     ebx, eax
0x18003c3d1  cmp     eax, eax
0x18003c3d3  jb      short loc_18003C3FB
0x18003c3d5  mov     sil, r12b
0x18003c3d8  jmp     short loc_18003C362
0x18003c3da  lea     r9, aRtlgetfullpath; "RtlGetFullPathName_UEx failed to get fu"...
0x18003c3e1  mov     r8d, 2A6h
0x18003c3e7  lea     rdx, aAsldoesfileexi; "AslDoesFileExistNtPath"
0x18003c3ee  mov     ecx, r12d
0x18003c3f1  call    AslLogCallPrintf
0x18003c3f6  jmp     loc_18003C4CA
0x18003c3fb  mov     r8d, 0Ch; MaxCount
0x18003c401  lea     rdx, aSystemroot_2; "\\SystemRoot\\"
0x18003c408  mov     rcx, rdi; String1
0x18003c40b  call    _wcsnicmp_0
0x18003c410  test    eax, eax
0x18003c412  jz      short loc_18003C43A
0x18003c414  xor     r9d, r9d
0x18003c417  lea     rdx, [rbp+DestinationString]
0x18003c41b  xor     r8d, r8d
0x18003c41e  mov     rcx, rdi
0x18003c421  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18003c427  test    eax, eax
0x18003c429  jns     short loc_18003C43A
0x18003c42b  lea     r9, aRtldospathname; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x18003c432  mov     r8d, 2BDh
0x18003c438  jmp     short loc_18003C4B7
0x18003c43a  lea     rax, [rbp+DestinationString]
0x18003c43e  mov     [rsp+80h+OpenOptions], 0; OpenOptions
0x18003c446  xorps   xmm0, xmm0
0x18003c449  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18003c44d  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x18003c451  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18003c458  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18003c45c  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18003c464  mov     edx, 100080h; DesiredAccess
0x18003c469  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18003c470  lea     rcx, [rbp+FileHandle]; FileHandle
0x18003c474  mov     dword ptr [rsp+80h+InputPathType], r12d; ShareAccess
0x18003c479  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18003c47e  call    cs:__imp_ZwOpenFile
0x18003c484  test    eax, eax
0x18003c486  jns     short loc_18003C49B
0x18003c488  cmp     eax, 0C0000043h
0x18003c48d  jz      short loc_18003C496
0x18003c48f  cmp     eax, 0C0000022h
0x18003c494  jnz     short loc_18003C4CA
0x18003c496  mov     ebx, r12d
0x18003c499  jmp     short loc_18003C4EC
0x18003c49b  mov     rcx, [rbp+FileHandle]; Handle
0x18003c49f  mov     ebx, r12d
0x18003c4a2  call    cs:__imp_ZwClose
0x18003c4a8  jmp     short loc_18003C4EC
0x18003c4aa  lea     r9, aFailedToGetFul_0; "Failed to get full path [%x]"
0x18003c4b1  mov     r8d, 29Dh
0x18003c4b7  lea     rdx, aAsldoesfileexi; "AslDoesFileExistNtPath"
0x18003c4be  mov     dword ptr [rsp+80h+InputPathType], eax
0x18003c4c2  mov     ecx, r12d
0x18003c4c5  call    AslLogCallPrintf
0x18003c4ca  xor     ebx, ebx
0x18003c4cc  jmp     short loc_18003C4EC
0x18003c4ce  xor     ebx, ebx
0x18003c4d0  lea     r9, aOutOfMemory; "Out of memory"
0x18003c4d7  mov     r8d, 292h
0x18003c4dd  lea     rdx, aAsldoesfileexi; "AslDoesFileExistNtPath"
0x18003c4e4  mov     ecx, r12d
0x18003c4e7  call    AslLogCallPrintf
0x18003c4ec  cmp     [rbp+DestinationString.Buffer], r14
0x18003c4f0  jz      short loc_18003C4FC
0x18003c4f2  lea     rcx, [rbp+DestinationString]; UnicodeString
0x18003c4f6  call    cs:__imp_RtlFreeUnicodeString
0x18003c4fc  test    rdi, rdi
0x18003c4ff  jz      short loc_18003C516
0x18003c501  mov     rcx, gs:60h
0x18003c50a  mov     rdx, rdi
0x18003c50d  mov     rcx, [rcx+30h]
0x18003c511  call    AslFree
0x18003c516  lea     r11, [rsp+80h+var_s0]
0x18003c51e  mov     eax, ebx
0x18003c520  mov     rbx, [r11+40h]
0x18003c524  mov     rsi, [r11+48h]
0x18003c528  mov     rsp, r11
0x18003c52b  pop     r14
0x18003c52d  pop     r13
0x18003c52f  pop     r12
0x18003c531  pop     rdi
0x18003c532  pop     rbp
0x18003c533  retn
```
