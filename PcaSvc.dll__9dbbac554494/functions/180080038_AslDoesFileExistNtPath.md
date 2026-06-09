# AslDoesFileExistNtPath

- ea: `0x180080038`
- end: `0x18008029d`
- name: `AslDoesFileExistNtPath`
- size: `613`
- prototype: `__int64 __fastcall(PWSTR FileName)`
- caller_count: `4`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180043424`
- `0x1800811a0`
- `0x1800e3f84`
- `0x1800e4254`

## callees

- `0x180012920`
- `0x180019c84`
- `0x180080038`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180080173`
- `msvcrt!_wcsnicmp` at `0x180080173`
- `ntdll!ZwClose` at `0x18008020b`
- `ntdll!ZwClose` at `0x18008020b`
- `ntdll!ZwOpenFile` at `0x1800801e7`
- `ntdll!ZwOpenFile` at `0x1800801e7`
- `ntdll!RtlGetFullPathName_UEx` at `0x180080103`
- `ntdll!RtlGetFullPathName_UEx` at `0x180080103`
- `ntdll!RtlInitUnicodeString` at `0x18008007e`
- `ntdll!RtlInitUnicodeString` at `0x18008007e`
- `ntdll!RtlFreeUnicodeString` at `0x18008025f`
- `ntdll!RtlFreeUnicodeString` at `0x18008025f`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18008018a`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18008018a`
- `ntdll!RtlAllocateHeap` at `0x1800800dd`
- `ntdll!RtlAllocateHeap` at `0x1800800dd`

## string_xrefs

- `0x180080213`: `Failed to get full path [%x]`
- `0x18008014f`: `AslDoesFileExistNtPath`
- `0x180080220`: `AslDoesFileExistNtPath`
- `0x180080246`: `AslDoesFileExistNtPath`
- `0x180080142`: `RtlGetFullPathName_UEx failed to get full path with larger buffer.`
- `0x180080194`: `RtlDosPathNameToNtPathName_U_WithStatus failed [%x]`

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
  int v8; // r8d
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
        AslLogCallPrintf(1, (unsigned int)"AslDoesFileExistNtPath", 658, (unsigned int)"Out of memory");
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
            (unsigned int)"AslDoesFileExistNtPath",
            678,
            (unsigned int)"RtlGetFullPathName_UEx failed to get full path with larger buffer.");
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
    if ( _wcsnicmp(Heap, L"\\SystemRoot\\", 0xCu) )
    {
      FullPathName_UEx = RtlDosPathNameToNtPathName_U_WithStatus(Heap, &DestinationString, 0, 0);
      if ( FullPathName_UEx < 0 )
      {
        v7 = "RtlDosPathNameToNtPathName_U_WithStatus failed [%x]";
        v8 = 701;
LABEL_25:
        LODWORD(InputPathType) = FullPathName_UEx;
        AslLogCallPrintf(1, (unsigned int)"AslDoesFileExistNtPath", v8, (_DWORD)v7, InputPathType);
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
0x180080038  mov     [rsp-28h+arg_10], rbx
0x18008003d  mov     [rsp-28h+arg_18], rsi
0x180080042  push    rbp
0x180080043  push    rdi
0x180080044  push    r12
0x180080046  push    r13
0x180080048  push    r14
0x18008004a  mov     rbp, rsp
0x18008004d  sub     rsp, 80h
0x180080054  xorps   xmm0, xmm0
0x180080057  xor     eax, eax
0x180080059  mov     r14, rcx
0x18008005c  mov     [rbp+FileHandle], rax
0x180080060  mov     rdx, rcx; SourceString
0x180080063  mov     [rbp+arg_0], eax
0x180080066  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18008006a  lea     rcx, [rbp+DestinationString]; DestinationString
0x18008006e  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180080072  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180080076  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18008007a  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x18008007e  call    cs:__imp_RtlInitUnicodeString
0x180080084  mov     r12d, 1
0x18008008a  lea     r13d, [r12+7]
0x18008008f  cmp     [rbp+DestinationString.Length], r13w
0x180080094  jbe     short loc_1800800C2
0x180080096  mov     rax, [rbp+DestinationString.Buffer]
0x18008009a  cmp     word ptr [rax], 5Ch ; '\'
0x18008009e  jnz     short loc_1800800C2
0x1800800a0  cmp     word ptr [rax+2], 5Ch ; '\'
0x1800800a5  jz      short loc_1800800AE
0x1800800a7  cmp     word ptr [rax+2], 3Fh ; '?'
0x1800800ac  jnz     short loc_1800800C2
0x1800800ae  cmp     word ptr [rax+4], 3Fh ; '?'
0x1800800b3  jnz     short loc_1800800C2
0x1800800b5  xor     edi, edi
0x1800800b7  cmp     word ptr [rax+6], 5Ch ; '\'
0x1800800bc  jz      loc_1800801A3
0x1800800c2  xor     sil, sil
0x1800800c5  mov     ebx, 208h
0x1800800ca  mov     rcx, gs:60h
0x1800800d3  mov     edx, r13d; Flags
0x1800800d6  mov     r8d, ebx; Size
0x1800800d9  mov     rcx, [rcx+30h]; HeapHandle
0x1800800dd  call    cs:__imp_RtlAllocateHeap
0x1800800e3  mov     rdi, rax
0x1800800e6  test    rax, rax
0x1800800e9  jz      loc_180080237
0x1800800ef  lea     rax, [rbp+arg_0]
0x1800800f3  xor     r9d, r9d; FilePart
0x1800800f6  mov     r8, rdi; Buffer
0x1800800f9  mov     [rsp+80h+InputPathType], rax; InputPathType
0x1800800fe  mov     edx, ebx; BufferLength
0x180080100  mov     rcx, r14; FileName
0x180080103  call    cs:__imp_RtlGetFullPathName_UEx
0x180080109  test    eax, eax
0x18008010b  js      loc_180080213
0x180080111  mov     eax, [rbp+arg_0]
0x180080114  cmp     eax, ebx
0x180080116  jbe     short loc_18008013B
0x180080118  test    sil, sil
0x18008011b  jnz     short loc_180080142
0x18008011d  mov     rcx, gs:60h
0x180080126  mov     rdx, rdi
0x180080129  mov     rcx, [rcx+30h]
0x18008012d  call    AslFree
0x180080132  mov     eax, [rbp+arg_0]
0x180080135  xor     edi, edi
0x180080137  mov     ebx, eax
0x180080139  cmp     eax, eax
0x18008013b  jb      short loc_180080163
0x18008013d  mov     sil, r12b
0x180080140  jmp     short loc_1800800CA
0x180080142  lea     r9, aRtlgetfullpath; "RtlGetFullPathName_UEx failed to get fu"...
0x180080149  mov     r8d, 2A6h
0x18008014f  lea     rdx, aAsldoesfileexi; "AslDoesFileExistNtPath"
0x180080156  mov     ecx, r12d
0x180080159  call    AslLogCallPrintf
0x18008015e  jmp     loc_180080233
0x180080163  mov     r8d, 0Ch; MaxCount
0x180080169  lea     rdx, aSystemroot_5; "\\SystemRoot\\"
0x180080170  mov     rcx, rdi; String1
0x180080173  call    cs:__imp__wcsnicmp
0x180080179  test    eax, eax
0x18008017b  jz      short loc_1800801A3
0x18008017d  xor     r9d, r9d
0x180080180  lea     rdx, [rbp+DestinationString]
0x180080184  xor     r8d, r8d
0x180080187  mov     rcx, rdi
0x18008018a  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180080190  test    eax, eax
0x180080192  jns     short loc_1800801A3
0x180080194  lea     r9, aRtldospathname; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x18008019b  mov     r8d, 2BDh
0x1800801a1  jmp     short loc_180080220
0x1800801a3  lea     rax, [rbp+DestinationString]
0x1800801a7  mov     [rsp+80h+OpenOptions], 0; OpenOptions
0x1800801af  xorps   xmm0, xmm0
0x1800801b2  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800801b6  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x1800801ba  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800801c1  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800801c5  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800801cd  mov     edx, 100080h; DesiredAccess
0x1800801d2  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800801d9  lea     rcx, [rbp+FileHandle]; FileHandle
0x1800801dd  mov     dword ptr [rsp+80h+InputPathType], r12d; ShareAccess
0x1800801e2  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800801e7  call    cs:__imp_ZwOpenFile
0x1800801ed  test    eax, eax
0x1800801ef  jns     short loc_180080204
0x1800801f1  cmp     eax, 0C0000043h
0x1800801f6  jz      short loc_1800801FF
0x1800801f8  cmp     eax, 0C0000022h
0x1800801fd  jnz     short loc_180080233
0x1800801ff  mov     ebx, r12d
0x180080202  jmp     short loc_180080255
0x180080204  mov     rcx, [rbp+FileHandle]; Handle
0x180080208  mov     ebx, r12d
0x18008020b  call    cs:__imp_ZwClose
0x180080211  jmp     short loc_180080255
0x180080213  lea     r9, aFailedToGetFul_0; "Failed to get full path [%x]"
0x18008021a  mov     r8d, 29Dh
0x180080220  lea     rdx, aAsldoesfileexi; "AslDoesFileExistNtPath"
0x180080227  mov     dword ptr [rsp+80h+InputPathType], eax
0x18008022b  mov     ecx, r12d
0x18008022e  call    AslLogCallPrintf
0x180080233  xor     ebx, ebx
0x180080235  jmp     short loc_180080255
0x180080237  xor     ebx, ebx
0x180080239  lea     r9, aOutOfMemory; "Out of memory"
0x180080240  mov     r8d, 292h
0x180080246  lea     rdx, aAsldoesfileexi; "AslDoesFileExistNtPath"
0x18008024d  mov     ecx, r12d
0x180080250  call    AslLogCallPrintf
0x180080255  cmp     [rbp+DestinationString.Buffer], r14
0x180080259  jz      short loc_180080265
0x18008025b  lea     rcx, [rbp+DestinationString]; UnicodeString
0x18008025f  call    cs:__imp_RtlFreeUnicodeString
0x180080265  test    rdi, rdi
0x180080268  jz      short loc_18008027F
0x18008026a  mov     rcx, gs:60h
0x180080273  mov     rdx, rdi
0x180080276  mov     rcx, [rcx+30h]
0x18008027a  call    AslFree
0x18008027f  lea     r11, [rsp+80h+var_s0]
0x180080287  mov     eax, ebx
0x180080289  mov     rbx, [r11+40h]
0x18008028d  mov     rsi, [r11+48h]
0x180080291  mov     rsp, r11
0x180080294  pop     r14
0x180080296  pop     r13
0x180080298  pop     r12
0x18008029a  pop     rdi
0x18008029b  pop     rbp
0x18008029c  retn
```
