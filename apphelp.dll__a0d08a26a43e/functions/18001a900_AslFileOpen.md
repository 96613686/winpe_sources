# AslFileOpen

- ea: `0x18001a900`
- end: `0x18001ab95`
- name: `AslFileOpen`
- size: `661`
- prototype: `__int64 __fastcall(PHANDLE FileHandle, PWSTR FileName)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a714`
- `0x18003ff20`
- `0x18004525c`

## callees

- `0x18000f114`
- `0x180018f20`
- `0x18001a900`
- `0x180039a66`

## import_xrefs

- `ntdll!RtlGetFullPathName_UEx` at `0x18001a9c9`
- `ntdll!RtlGetFullPathName_UEx` at `0x18001a9c9`
- `ntdll!RtlInitUnicodeString` at `0x18001a947`
- `ntdll!RtlInitUnicodeString` at `0x18001a947`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18001aa5d`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18001aa5d`
- `ntdll!ZwCreateFile` at `0x18001aaeb`
- `ntdll!ZwCreateFile` at `0x18001aaeb`
- `ntdll!RtlFreeUnicodeString` at `0x18001ab57`
- `ntdll!RtlFreeUnicodeString` at `0x18001ab57`
- `ntdll!RtlAllocateHeap` at `0x18001a9a3`
- `ntdll!RtlAllocateHeap` at `0x18001a9a3`

## string_xrefs

- `0x18001aa1c`: `AslFileOpen`
- `0x18001ab13`: `AslFileOpen`
- `0x18001ab37`: `AslFileOpen`
- `0x18001ab06`: `Failed to get full path [%x]`
- `0x18001aa0f`: `RtlGetFullPathName_UEx failed to get full path with larger buffer.`
- `0x18001aa69`: `RtlDosPathNameToNtPathName_U_WithStatus failed [%x]`
- `0x18001aaf7`: `NtCreateFile failed [%x]`

## pseudocode

```c
__int64 __fastcall AslFileOpen(PHANDLE FileHandle, PWSTR FileName)
{
  WCHAR *Heap; // rdi
  char v5; // r14
  RTL_PATH_TYPE v6; // esi
  NTSTATUS FullPathName_UEx; // eax
  unsigned int v8; // ebx
  bool v9; // cf
  const char *v10; // r9
  __int64 v11; // r8
  RTL_PATH_TYPE *InputPathType; // [rsp+20h] [rbp-59h]
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+7h] BYREF
  RTL_PATH_TYPE v17; // [rsp+E0h] [rbp+67h] BYREF

  *FileHandle = 0;
  v17 = RtlPathTypeUnknown;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  RtlInitUnicodeString(&DestinationString, FileName);
  if ( DestinationString.Length <= 8u
    || *DestinationString.Buffer != 92
    || DestinationString.Buffer[1] != 92 && DestinationString.Buffer[1] != 63
    || DestinationString.Buffer[2] != 63
    || (Heap = 0, DestinationString.Buffer[3] != 92) )
  {
    v5 = 0;
    v6 = 520;
    while ( 1 )
    {
      Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)v6);
      if ( !Heap )
      {
        AslLogCallPrintf(1, "AslFileOpen", 1843, "Out of memory");
        v8 = -1073741801;
        goto LABEL_24;
      }
      FullPathName_UEx = RtlGetFullPathName_UEx(FileName, v6, Heap, 0, &v17);
      v8 = FullPathName_UEx;
      if ( FullPathName_UEx < 0 )
      {
        v10 = "Failed to get full path [%x]";
        v11 = 1854;
        goto LABEL_22;
      }
      v9 = v17 < (unsigned int)v6;
      if ( v17 > (unsigned int)v6 )
      {
        if ( v5 )
        {
          AslLogCallPrintf(1, "AslFileOpen", 1862, "RtlGetFullPathName_UEx failed to get full path with larger buffer.");
          v8 = -1073741789;
          goto LABEL_24;
        }
        AslFree(NtCurrentPeb()->ProcessHeap, Heap);
        Heap = 0;
        v6 = v17;
        v9 = 0;
      }
      if ( v9 )
        break;
      v5 = 1;
    }
    if ( wcsnicmp_0(Heap, L"\\SystemRoot\\", 0xCu) )
    {
      FullPathName_UEx = RtlDosPathNameToNtPathName_U_WithStatus(Heap, &DestinationString, 0, 0);
      v8 = FullPathName_UEx;
      if ( FullPathName_UEx < 0 )
      {
        v10 = "RtlDosPathNameToNtPathName_U_WithStatus failed [%x]";
        v11 = 1885;
        goto LABEL_22;
      }
    }
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  FullPathName_UEx = ZwCreateFile(
                       FileHandle,
                       0x80100080,
                       &ObjectAttributes,
                       &IoStatusBlock,
                       0,
                       0x80u,
                       1u,
                       1u,
                       0x60u,
                       0,
                       0);
  v8 = FullPathName_UEx;
  if ( FullPathName_UEx < 0 )
  {
    v10 = "NtCreateFile failed [%x]";
    v11 = 1910;
LABEL_22:
    LODWORD(InputPathType) = FullPathName_UEx;
    AslLogCallPrintf(1, "AslFileOpen", v11, v10, InputPathType);
  }
LABEL_24:
  if ( DestinationString.Buffer != FileName )
    RtlFreeUnicodeString(&DestinationString);
  if ( Heap )
    AslFree(NtCurrentPeb()->ProcessHeap, Heap);
  return v8;
}

```

## disassembly

```asm
0x18001a900  mov     [rsp-8+arg_8], rbx
0x18001a905  mov     [rsp-8+arg_10], rsi
0x18001a90a  push    rbp
0x18001a90b  push    rdi
0x18001a90c  push    r12
0x18001a90e  push    r14
0x18001a910  push    r15
0x18001a912  lea     rbp, [rsp-37h]
0x18001a917  sub     rsp, 0B0h
0x18001a91e  xorps   xmm0, xmm0
0x18001a921  xor     eax, eax
0x18001a923  mov     [rcx], rax
0x18001a926  mov     r12, rcx
0x18001a929  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18001a92d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18001a931  mov     [rbp+57h+arg_0], eax
0x18001a934  mov     r15, rdx
0x18001a937  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18001a93b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18001a93f  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18001a943  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18001a947  call    cs:__imp_RtlInitUnicodeString
0x18001a94d  mov     eax, 8
0x18001a952  cmp     [rbp+57h+DestinationString.Length], ax
0x18001a956  jbe     short loc_18001A989
0x18001a958  mov     rax, [rbp+57h+DestinationString.Buffer]
0x18001a95c  cmp     word ptr [rax], 5Ch ; '\'
0x18001a960  jnz     short loc_18001A984
0x18001a962  cmp     word ptr [rax+2], 5Ch ; '\'
0x18001a967  jz      short loc_18001A970
0x18001a969  cmp     word ptr [rax+2], 3Fh ; '?'
0x18001a96e  jnz     short loc_18001A984
0x18001a970  cmp     word ptr [rax+4], 3Fh ; '?'
0x18001a975  jnz     short loc_18001A984
0x18001a977  xor     edi, edi
0x18001a979  cmp     word ptr [rax+6], 5Ch ; '\'
0x18001a97e  jz      loc_18001AA7B
0x18001a984  mov     eax, 8
0x18001a989  xor     r14b, r14b
0x18001a98c  mov     esi, 208h
0x18001a991  mov     rcx, gs:60h
0x18001a99a  mov     edx, eax; Flags
0x18001a99c  mov     r8d, esi; Size
0x18001a99f  mov     rcx, [rcx+30h]; HeapHandle
0x18001a9a3  call    cs:__imp_RtlAllocateHeap
0x18001a9a9  mov     rdi, rax
0x18001a9ac  test    rax, rax
0x18001a9af  jz      loc_18001AB2A
0x18001a9b5  lea     rax, [rbp+57h+arg_0]
0x18001a9b9  xor     r9d, r9d; FilePart
0x18001a9bc  mov     r8, rdi; Buffer
0x18001a9bf  mov     [rsp+0D0h+InputPathType], rax; InputPathType
0x18001a9c4  mov     edx, esi; BufferLength
0x18001a9c6  mov     rcx, r15; FileName
0x18001a9c9  call    cs:__imp_RtlGetFullPathName_UEx
0x18001a9cf  mov     ebx, eax
0x18001a9d1  test    eax, eax
0x18001a9d3  js      loc_18001AB06
0x18001a9d9  mov     eax, [rbp+57h+arg_0]
0x18001a9dc  cmp     eax, esi
0x18001a9de  jbe     short loc_18001AA03
0x18001a9e0  test    r14b, r14b
0x18001a9e3  jnz     short loc_18001AA0F
0x18001a9e5  mov     rcx, gs:60h
0x18001a9ee  mov     rdx, rdi
0x18001a9f1  mov     rcx, [rcx+30h]
0x18001a9f5  call    AslFree
0x18001a9fa  mov     eax, [rbp+57h+arg_0]
0x18001a9fd  xor     edi, edi
0x18001a9ff  mov     esi, eax
0x18001aa01  cmp     eax, eax
0x18001aa03  jb      short loc_18001AA37
0x18001aa05  mov     r14b, 1
0x18001aa08  mov     eax, 8
0x18001aa0d  jmp     short loc_18001A991
0x18001aa0f  lea     r9, aRtlgetfullpath; "RtlGetFullPathName_UEx failed to get fu"...
0x18001aa16  mov     r8d, 746h
0x18001aa1c  lea     rdx, aAslfileopen; "AslFileOpen"
0x18001aa23  mov     ecx, 1
0x18001aa28  call    AslLogCallPrintf
0x18001aa2d  mov     ebx, 0C0000023h
0x18001aa32  jmp     loc_18001AB4D
0x18001aa37  mov     r8d, 0Ch; MaxCount
0x18001aa3d  lea     rdx, aSystemroot_2; "\\SystemRoot\\"
0x18001aa44  mov     rcx, rdi; String1
0x18001aa47  call    _wcsnicmp_0
0x18001aa4c  test    eax, eax
0x18001aa4e  jz      short loc_18001AA7B
0x18001aa50  xor     r9d, r9d
0x18001aa53  lea     rdx, [rbp+57h+DestinationString]
0x18001aa57  xor     r8d, r8d
0x18001aa5a  mov     rcx, rdi
0x18001aa5d  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18001aa63  mov     ebx, eax
0x18001aa65  test    eax, eax
0x18001aa67  jns     short loc_18001AA7B
0x18001aa69  lea     r9, aRtldospathname; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x18001aa70  mov     r8d, 75Dh
0x18001aa76  jmp     loc_18001AB13
0x18001aa7b  mov     [rsp+0D0h+EaLength], 0; EaLength
0x18001aa83  lea     rax, [rbp+57h+DestinationString]
0x18001aa87  mov     [rsp+0D0h+EaBuffer], 0; EaBuffer
0x18001aa90  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18001aa94  mov     [rsp+0D0h+CreateOptions], 60h ; '`'; CreateOptions
0x18001aa9c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001aaa0  mov     [rsp+0D0h+CreateDisposition], 1; CreateDisposition
0x18001aaa8  xorps   xmm0, xmm0
0x18001aaab  mov     [rsp+0D0h+ShareAccess], 1; ShareAccess
0x18001aab3  mov     edx, 80100080h; DesiredAccess
0x18001aab8  mov     [rsp+0D0h+FileAttributes], 80h; FileAttributes
0x18001aac0  mov     rcx, r12; FileHandle
0x18001aac3  mov     [rsp+0D0h+InputPathType], 0; AllocationSize
0x18001aacc  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001aad3  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18001aadb  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18001aae2  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18001aae6  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001aaeb  call    cs:__imp_ZwCreateFile
0x18001aaf1  mov     ebx, eax
0x18001aaf3  test    eax, eax
0x18001aaf5  jns     short loc_18001AB4D
0x18001aaf7  lea     r9, aNtcreatefileFa; "NtCreateFile failed [%x]"
0x18001aafe  mov     r8d, 776h
0x18001ab04  jmp     short loc_18001AB13
0x18001ab06  lea     r9, aFailedToGetFul_0; "Failed to get full path [%x]"
0x18001ab0d  mov     r8d, 73Eh
0x18001ab13  lea     rdx, aAslfileopen; "AslFileOpen"
0x18001ab1a  mov     dword ptr [rsp+0D0h+InputPathType], eax
0x18001ab1e  mov     ecx, 1
0x18001ab23  call    AslLogCallPrintf
0x18001ab28  jmp     short loc_18001AB4D
0x18001ab2a  lea     r9, aOutOfMemory; "Out of memory"
0x18001ab31  mov     r8d, 733h
0x18001ab37  lea     rdx, aAslfileopen; "AslFileOpen"
0x18001ab3e  mov     ecx, 1
0x18001ab43  call    AslLogCallPrintf
0x18001ab48  mov     ebx, 0C0000017h
0x18001ab4d  cmp     [rbp+57h+DestinationString.Buffer], r15
0x18001ab51  jz      short loc_18001AB5D
0x18001ab53  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x18001ab57  call    cs:__imp_RtlFreeUnicodeString
0x18001ab5d  test    rdi, rdi
0x18001ab60  jz      short loc_18001AB77
0x18001ab62  mov     rcx, gs:60h
0x18001ab6b  mov     rdx, rdi
0x18001ab6e  mov     rcx, [rcx+30h]
0x18001ab72  call    AslFree
0x18001ab77  lea     r11, [rsp+0D0h+var_20]
0x18001ab7f  mov     eax, ebx
0x18001ab81  mov     rbx, [r11+38h]
0x18001ab85  mov     rsi, [r11+40h]
0x18001ab89  mov     rsp, r11
0x18001ab8c  pop     r15
0x18001ab8e  pop     r14
0x18001ab90  pop     r12
0x18001ab92  pop     rdi
0x18001ab93  pop     rbp
0x18001ab94  retn
```
