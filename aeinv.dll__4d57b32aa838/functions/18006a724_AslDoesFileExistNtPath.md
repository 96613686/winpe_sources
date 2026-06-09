# AslDoesFileExistNtPath

- ea: `0x18006a724`
- end: `0x18006a988`
- name: `AslDoesFileExistNtPath`
- size: `612`
- prototype: `__int64 __fastcall(PWSTR FileName)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006c020`

## callees

- `0x1800197d4`
- `0x18001cce4`
- `0x18005a7d8`
- `0x18006a724`

## import_xrefs

- `ntdll!RtlGetFullPathName_UEx` at `0x18006a7ef`
- `ntdll!RtlGetFullPathName_UEx` at `0x18006a7ef`
- `ntdll!RtlFreeUnicodeString` at `0x18006a94a`
- `ntdll!RtlFreeUnicodeString` at `0x18006a94a`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18006a875`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18006a875`
- `ntdll!ZwClose` at `0x18006a8f6`
- `ntdll!ZwClose` at `0x18006a8f6`
- `ntdll!RtlAllocateHeap` at `0x18006a7c9`
- `ntdll!RtlAllocateHeap` at `0x18006a7c9`
- `ntdll!RtlInitUnicodeString` at `0x18006a76a`
- `ntdll!RtlInitUnicodeString` at `0x18006a76a`
- `ntdll!ZwOpenFile` at `0x18006a8d2`
- `ntdll!ZwOpenFile` at `0x18006a8d2`

## string_xrefs

- `0x18006a83b`: `AslDoesFileExistNtPath`
- `0x18006a90b`: `AslDoesFileExistNtPath`
- `0x18006a931`: `AslDoesFileExistNtPath`
- `0x18006a8fe`: `Failed to get full path [%x]`
- `0x18006a82e`: `RtlGetFullPathName_UEx failed to get full path with larger buffer.`
- `0x18006a87f`: `RtlDosPathNameToNtPathName_U_WithStatus failed [%x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall AslDoesFileExistNtPath(PWSTR FileName)
{
  WCHAR *Heap; // rdi
  char v3; // si
  RTL_PATH_TYPE v4; // ebx
  bool v5; // cf
  const char *v6; // r9
  int v7; // r8d
  NTSTATUS v8; // eax
  unsigned int v9; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  RTL_PATH_TYPE InputPathType; // [rsp+B0h] [rbp+30h] BYREF
  void *FileHandle; // [rsp+B8h] [rbp+38h] BYREF

  FileHandle = 0;
  InputPathType = RtlPathTypeUnknown;
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
        v9 = 0;
        AslLogCallPrintf(1, (unsigned int)"AslDoesFileExistNtPath", 658, (unsigned int)"Out of memory");
        goto LABEL_28;
      }
      if ( RtlGetFullPathName_UEx(FileName, v4, Heap, 0, &InputPathType) < 0 )
      {
        v6 = "Failed to get full path [%x]";
        v7 = 669;
        goto LABEL_25;
      }
      v5 = InputPathType < (unsigned int)v4;
      if ( InputPathType > (unsigned int)v4 )
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
        v4 = InputPathType;
        v5 = 0;
      }
      if ( v5 )
        break;
      v3 = 1;
    }
    if ( wcsnicmp(Heap, L"\\SystemRoot\\", 0xCu)
      && (int)RtlDosPathNameToNtPathName_U_WithStatus(Heap, &DestinationString, 0, 0) < 0 )
    {
      v6 = "RtlDosPathNameToNtPathName_U_WithStatus failed [%x]";
      v7 = 701;
LABEL_25:
      AslLogCallPrintf(1, (unsigned int)"AslDoesFileExistNtPath", v7, (_DWORD)v6);
      goto LABEL_26;
    }
  }
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = ZwOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 1u, 0);
  if ( v8 >= 0 )
  {
    v9 = 1;
    ZwClose(FileHandle);
  }
  else if ( v8 == -1073741757 || v8 == -1073741790 )
  {
    v9 = 1;
  }
  else
  {
LABEL_26:
    v9 = 0;
  }
LABEL_28:
  if ( DestinationString.Buffer != FileName )
    RtlFreeUnicodeString(&DestinationString);
  if ( Heap )
    AslFree(NtCurrentPeb()->ProcessHeap, Heap);
  return v9;
}

```

## disassembly

```asm
0x18006a724  mov     [rsp-28h+arg_10], rbx
0x18006a729  mov     [rsp-28h+arg_18], rsi
0x18006a72e  push    rbp
0x18006a72f  push    rdi
0x18006a730  push    r12
0x18006a732  push    r13
0x18006a734  push    r14
0x18006a736  mov     rbp, rsp
0x18006a739  sub     rsp, 80h
0x18006a740  xorps   xmm0, xmm0
0x18006a743  xor     eax, eax
0x18006a745  mov     r14, rcx
0x18006a748  mov     [rbp+FileHandle], rax
0x18006a74c  mov     rdx, rcx; SourceString
0x18006a74f  mov     [rbp+arg_0], eax
0x18006a752  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18006a756  lea     rcx, [rbp+DestinationString]; DestinationString
0x18006a75a  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18006a75e  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18006a762  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18006a766  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x18006a76a  call    cs:__imp_RtlInitUnicodeString
0x18006a770  mov     r12d, 1
0x18006a776  lea     r13d, [r12+7]
0x18006a77b  cmp     [rbp+DestinationString.Length], r13w
0x18006a780  jbe     short loc_18006A7AE
0x18006a782  mov     rax, [rbp+DestinationString.Buffer]
0x18006a786  cmp     word ptr [rax], 5Ch ; '\'
0x18006a78a  jnz     short loc_18006A7AE
0x18006a78c  cmp     word ptr [rax+2], 5Ch ; '\'
0x18006a791  jz      short loc_18006A79A
0x18006a793  cmp     word ptr [rax+2], 3Fh ; '?'
0x18006a798  jnz     short loc_18006A7AE
0x18006a79a  cmp     word ptr [rax+4], 3Fh ; '?'
0x18006a79f  jnz     short loc_18006A7AE
0x18006a7a1  xor     edi, edi
0x18006a7a3  cmp     word ptr [rax+6], 5Ch ; '\'
0x18006a7a8  jz      loc_18006A88E
0x18006a7ae  xor     sil, sil
0x18006a7b1  mov     ebx, 208h
0x18006a7b6  mov     rcx, gs:60h
0x18006a7bf  mov     edx, r13d; Flags
0x18006a7c2  mov     r8d, ebx; Size
0x18006a7c5  mov     rcx, [rcx+30h]; HeapHandle
0x18006a7c9  call    cs:__imp_RtlAllocateHeap
0x18006a7cf  mov     rdi, rax
0x18006a7d2  test    rax, rax
0x18006a7d5  jz      loc_18006A922
0x18006a7db  lea     rax, [rbp+arg_0]
0x18006a7df  xor     r9d, r9d; FilePart
0x18006a7e2  mov     r8, rdi; Buffer
0x18006a7e5  mov     [rsp+80h+InputPathType], rax; InputPathType
0x18006a7ea  mov     edx, ebx; BufferLength
0x18006a7ec  mov     rcx, r14; FileName
0x18006a7ef  call    cs:__imp_RtlGetFullPathName_UEx
0x18006a7f5  test    eax, eax
0x18006a7f7  js      loc_18006A8FE
0x18006a7fd  mov     eax, [rbp+arg_0]
0x18006a800  cmp     eax, ebx
0x18006a802  jbe     short loc_18006A827
0x18006a804  test    sil, sil
0x18006a807  jnz     short loc_18006A82E
0x18006a809  mov     rcx, gs:60h
0x18006a812  mov     rdx, rdi
0x18006a815  mov     rcx, [rcx+30h]
0x18006a819  call    AslFree
0x18006a81e  mov     eax, [rbp+arg_0]
0x18006a821  xor     edi, edi
0x18006a823  mov     ebx, eax
0x18006a825  cmp     eax, eax
0x18006a827  jb      short loc_18006A84F
0x18006a829  mov     sil, r12b
0x18006a82c  jmp     short loc_18006A7B6
0x18006a82e  lea     r9, aRtlgetfullpath; "RtlGetFullPathName_UEx failed to get fu"...
0x18006a835  mov     r8d, 2A6h
0x18006a83b  lea     rdx, aAsldoesfileexi; "AslDoesFileExistNtPath"
0x18006a842  mov     ecx, r12d
0x18006a845  call    AslLogCallPrintf
0x18006a84a  jmp     loc_18006A91E
0x18006a84f  mov     r8d, 0Ch; MaxCount
0x18006a855  lea     rdx, aSystemroot_2; "\\SystemRoot\\"
0x18006a85c  mov     rcx, rdi; String1
0x18006a85f  call    _wcsnicmp
0x18006a864  test    eax, eax
0x18006a866  jz      short loc_18006A88E
0x18006a868  xor     r9d, r9d
0x18006a86b  lea     rdx, [rbp+DestinationString]
0x18006a86f  xor     r8d, r8d
0x18006a872  mov     rcx, rdi
0x18006a875  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18006a87b  test    eax, eax
0x18006a87d  jns     short loc_18006A88E
0x18006a87f  lea     r9, aRtldospathname; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x18006a886  mov     r8d, 2BDh
0x18006a88c  jmp     short loc_18006A90B
0x18006a88e  lea     rax, [rbp+DestinationString]
0x18006a892  mov     [rsp+80h+OpenOptions], 0; OpenOptions
0x18006a89a  xorps   xmm0, xmm0
0x18006a89d  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18006a8a1  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x18006a8a5  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18006a8ac  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18006a8b0  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18006a8b8  mov     edx, 100080h; DesiredAccess
0x18006a8bd  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18006a8c4  lea     rcx, [rbp+FileHandle]; FileHandle
0x18006a8c8  mov     dword ptr [rsp+80h+InputPathType], r12d; ShareAccess
0x18006a8cd  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18006a8d2  call    cs:__imp_ZwOpenFile
0x18006a8d8  test    eax, eax
0x18006a8da  jns     short loc_18006A8EF
0x18006a8dc  cmp     eax, 0C0000043h
0x18006a8e1  jz      short loc_18006A8EA
0x18006a8e3  cmp     eax, 0C0000022h
0x18006a8e8  jnz     short loc_18006A91E
0x18006a8ea  mov     ebx, r12d
0x18006a8ed  jmp     short loc_18006A940
0x18006a8ef  mov     rcx, [rbp+FileHandle]; Handle
0x18006a8f3  mov     ebx, r12d
0x18006a8f6  call    cs:__imp_ZwClose
0x18006a8fc  jmp     short loc_18006A940
0x18006a8fe  lea     r9, aFailedToGetFul_0; "Failed to get full path [%x]"
0x18006a905  mov     r8d, 29Dh
0x18006a90b  lea     rdx, aAsldoesfileexi; "AslDoesFileExistNtPath"
0x18006a912  mov     dword ptr [rsp+80h+InputPathType], eax
0x18006a916  mov     ecx, r12d
0x18006a919  call    AslLogCallPrintf
0x18006a91e  xor     ebx, ebx
0x18006a920  jmp     short loc_18006A940
0x18006a922  xor     ebx, ebx
0x18006a924  lea     r9, aOutOfMemory_0; "Out of memory"
0x18006a92b  mov     r8d, 292h
0x18006a931  lea     rdx, aAsldoesfileexi; "AslDoesFileExistNtPath"
0x18006a938  mov     ecx, r12d
0x18006a93b  call    AslLogCallPrintf
0x18006a940  cmp     [rbp+DestinationString.Buffer], r14
0x18006a944  jz      short loc_18006A950
0x18006a946  lea     rcx, [rbp+DestinationString]; UnicodeString
0x18006a94a  call    cs:__imp_RtlFreeUnicodeString
0x18006a950  test    rdi, rdi
0x18006a953  jz      short loc_18006A96A
0x18006a955  mov     rcx, gs:60h
0x18006a95e  mov     rdx, rdi
0x18006a961  mov     rcx, [rcx+30h]
0x18006a965  call    AslFree
0x18006a96a  lea     r11, [rsp+80h+var_s0]
0x18006a972  mov     eax, ebx
0x18006a974  mov     rbx, [r11+40h]
0x18006a978  mov     rsi, [r11+48h]
0x18006a97c  mov     rsp, r11
0x18006a97f  pop     r14
0x18006a981  pop     r13
0x18006a983  pop     r12
0x18006a985  pop     rdi
0x18006a986  pop     rbp
0x18006a987  retn
```
