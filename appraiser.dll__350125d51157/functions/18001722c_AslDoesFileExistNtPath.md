# AslDoesFileExistNtPath

- ea: `0x18001722c`
- end: `0x1800174aa`
- name: `AslDoesFileExistNtPath`
- size: `638`
- prototype: `__int64 __fastcall(PWSTR FileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001cac8`

## callees

- `0x1800091d4`
- `0x18001722c`
- `0x18001a2f4`

## import_xrefs

- `ntdll!RtlGetFullPathName_UEx` at `0x1800172d5`
- `ntdll!RtlGetFullPathName_UEx` at `0x1800172d5`
- `ntdll!RtlFreeUnicodeString` at `0x18001736e`
- `ntdll!RtlFreeUnicodeString` at `0x18001736e`
- `ntdll!ZwOpenFile` at `0x180017454`
- `ntdll!ZwOpenFile` at `0x180017454`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800173f5`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800173f5`
- `ntdll!ZwClose` at `0x180017479`
- `ntdll!ZwClose` at `0x180017479`
- `ntdll!RtlFreeHeap` at `0x18001730a`
- `ntdll!RtlFreeHeap` at `0x18001738b`
- `ntdll!RtlFreeHeap` at `0x18001730a`
- `ntdll!RtlFreeHeap` at `0x18001738b`
- `ntdll!RtlAllocateHeap` at `0x180017335`
- `ntdll!RtlAllocateHeap` at `0x180017335`
- `ntdll!RtlInitUnicodeString` at `0x180017272`
- `ntdll!RtlInitUnicodeString` at `0x180017272`

## string_xrefs

- `0x180017356`: `AslDoesFileExistNtPath`
- `0x1800173bc`: `AslDoesFileExistNtPath`
- `0x180017491`: `AslDoesFileExistNtPath`
- `0x180017484`: `Failed to get full path [%x]`
- `0x1800173af`: `RtlGetFullPathName_UEx failed to get full path with larger buffer.`
- `0x1800173ff`: `RtlDosPathNameToNtPathName_U_WithStatus failed [%x]`

## pseudocode

```c
__int64 __fastcall AslDoesFileExistNtPath(PWSTR FileName)
{
  WCHAR *Heap; // rbx
  RTL_PATH_TYPE v3; // edi
  char v4; // r14
  SIZE_T i; // r8
  NTSTATUS FullPathName_UEx; // eax
  bool v7; // cf
  unsigned int v8; // edi
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
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        Heap = 0;
        v3 = v17;
        v7 = 0;
      }
      if ( v7 )
        break;
      v4 = 1;
    }
    if ( wcsnicmp(Heap, L"\\SystemRoot\\", 0xCu) )
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
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return v8;
}

```

## disassembly

```asm
0x18001722c  mov     [rsp-28h+arg_10], rbx
0x180017231  mov     [rsp-28h+arg_18], rsi
0x180017236  push    rbp
0x180017237  push    rdi
0x180017238  push    r13
0x18001723a  push    r14
0x18001723c  push    r15
0x18001723e  mov     rbp, rsp
0x180017241  sub     rsp, 80h
0x180017248  xorps   xmm0, xmm0
0x18001724b  xor     eax, eax
0x18001724d  mov     r15, rcx
0x180017250  mov     [rbp+FileHandle], rax
0x180017254  mov     rdx, rcx; SourceString
0x180017257  mov     [rbp+arg_0], eax
0x18001725a  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18001725e  lea     rcx, [rbp+DestinationString]; DestinationString
0x180017262  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180017266  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18001726a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001726e  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180017272  call    cs:__imp_RtlInitUnicodeString
0x180017278  mov     esi, 1
0x18001727d  lea     r13d, [rsi+7]
0x180017281  cmp     [rbp+DestinationString.Length], r13w
0x180017286  jbe     short loc_1800172B4
0x180017288  mov     rax, [rbp+DestinationString.Buffer]
0x18001728c  cmp     word ptr [rax], 5Ch ; '\'
0x180017290  jnz     short loc_1800172B4
0x180017292  cmp     word ptr [rax+2], 5Ch ; '\'
0x180017297  jz      short loc_1800172A0
0x180017299  cmp     word ptr [rax+2], 3Fh ; '?'
0x18001729e  jnz     short loc_1800172B4
0x1800172a0  cmp     word ptr [rax+4], 3Fh ; '?'
0x1800172a5  jnz     short loc_1800172B4
0x1800172a7  xor     ebx, ebx
0x1800172a9  cmp     word ptr [rax+6], 5Ch ; '\'
0x1800172ae  jz      loc_180017411
0x1800172b4  mov     edi, 208h
0x1800172b9  xor     r14b, r14b
0x1800172bc  mov     r8d, edi
0x1800172bf  jmp     short loc_180017325
0x1800172c1  lea     rax, [rbp+arg_0]
0x1800172c5  xor     r9d, r9d; FilePart
0x1800172c8  mov     r8, rbx; Buffer
0x1800172cb  mov     [rsp+80h+InputPathType], rax; InputPathType
0x1800172d0  mov     edx, edi; BufferLength
0x1800172d2  mov     rcx, r15; FileName
0x1800172d5  call    cs:__imp_RtlGetFullPathName_UEx
0x1800172db  test    eax, eax
0x1800172dd  js      loc_180017484
0x1800172e3  mov     eax, [rbp+arg_0]
0x1800172e6  cmp     eax, edi
0x1800172e8  jbe     short loc_180017319
0x1800172ea  test    r14b, r14b
0x1800172ed  jnz     loc_1800173AF
0x1800172f3  test    rbx, rbx
0x1800172f6  jz      short loc_180017313
0x1800172f8  mov     rcx, gs:60h
0x180017301  mov     r8, rbx; P
0x180017304  xor     edx, edx; Flags
0x180017306  mov     rcx, [rcx+30h]; HeapHandle
0x18001730a  call    cs:__imp_RtlFreeHeap
0x180017310  mov     eax, [rbp+arg_0]
0x180017313  xor     ebx, ebx
0x180017315  mov     edi, eax
0x180017317  cmp     eax, eax
0x180017319  jb      loc_1800173CF
0x18001731f  mov     r14b, sil
0x180017322  mov     r8d, edi; Size
0x180017325  mov     rcx, gs:60h
0x18001732e  mov     edx, r13d; Flags
0x180017331  mov     rcx, [rcx+30h]; HeapHandle
0x180017335  call    cs:__imp_RtlAllocateHeap
0x18001733b  mov     rbx, rax
0x18001733e  test    rax, rax
0x180017341  jnz     loc_1800172C1
0x180017347  xor     edi, edi
0x180017349  lea     r9, aOutOfMemory_0; "Out of memory"
0x180017350  mov     r8d, 292h
0x180017356  lea     rdx, aAsldoesfileexi; "AslDoesFileExistNtPath"
0x18001735d  mov     ecx, esi
0x18001735f  call    AslLogCallPrintf
0x180017364  cmp     [rbp+DestinationString.Buffer], r15
0x180017368  jz      short loc_180017374
0x18001736a  lea     rcx, [rbp+DestinationString]; UnicodeString
0x18001736e  call    cs:__imp_RtlFreeUnicodeString
0x180017374  test    rbx, rbx
0x180017377  jz      short loc_180017391
0x180017379  mov     rcx, gs:60h
0x180017382  mov     r8, rbx; P
0x180017385  xor     edx, edx; Flags
0x180017387  mov     rcx, [rcx+30h]; HeapHandle
0x18001738b  call    cs:__imp_RtlFreeHeap
0x180017391  lea     r11, [rsp+80h+var_s0]
0x180017399  mov     eax, edi
0x18001739b  mov     rbx, [r11+40h]
0x18001739f  mov     rsi, [r11+48h]
0x1800173a3  mov     rsp, r11
0x1800173a6  pop     r15
0x1800173a8  pop     r14
0x1800173aa  pop     r13
0x1800173ac  pop     rdi
0x1800173ad  pop     rbp
0x1800173ae  retn
0x1800173af  lea     r9, aRtlgetfullpath; "RtlGetFullPathName_UEx failed to get fu"...
0x1800173b6  mov     r8d, 2A6h
0x1800173bc  lea     rdx, aAsldoesfileexi; "AslDoesFileExistNtPath"
0x1800173c3  mov     ecx, esi
0x1800173c5  call    AslLogCallPrintf
0x1800173ca  jmp     loc_1800174A3
0x1800173cf  mov     r8d, 0Ch; MaxCount
0x1800173d5  lea     rdx, aSystemroot_3; "\\SystemRoot\\"
0x1800173dc  mov     rcx, rbx; String1
0x1800173df  call    _wcsnicmp
0x1800173e4  test    eax, eax
0x1800173e6  jz      short loc_180017411
0x1800173e8  xor     r9d, r9d
0x1800173eb  lea     rdx, [rbp+DestinationString]
0x1800173ef  xor     r8d, r8d
0x1800173f2  mov     rcx, rbx
0x1800173f5  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1800173fb  test    eax, eax
0x1800173fd  jns     short loc_180017411
0x1800173ff  lea     r9, aRtldospathname; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x180017406  mov     r8d, 2BDh
0x18001740c  jmp     loc_180017491
0x180017411  lea     rax, [rbp+DestinationString]
0x180017415  mov     [rsp+80h+OpenOptions], 0; OpenOptions
0x18001741d  xorps   xmm0, xmm0
0x180017420  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180017424  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x180017428  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18001742f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180017433  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18001743b  mov     edx, 100080h; DesiredAccess
0x180017440  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180017447  lea     rcx, [rbp+FileHandle]; FileHandle
0x18001744b  mov     dword ptr [rsp+80h+InputPathType], esi; ShareAccess
0x18001744f  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180017454  call    cs:__imp_ZwOpenFile
0x18001745a  test    eax, eax
0x18001745c  jns     short loc_180017473
0x18001745e  cmp     eax, 0C0000043h
0x180017463  jz      short loc_18001746C
0x180017465  cmp     eax, 0C0000022h
0x18001746a  jnz     short loc_1800174A3
0x18001746c  mov     edi, esi
0x18001746e  jmp     loc_180017364
0x180017473  mov     rcx, [rbp+FileHandle]; Handle
0x180017477  mov     edi, esi
0x180017479  call    cs:__imp_ZwClose
0x18001747f  jmp     loc_180017364
0x180017484  lea     r9, aFailedToGetFul_1; "Failed to get full path [%x]"
0x18001748b  mov     r8d, 29Dh
0x180017491  lea     rdx, aAsldoesfileexi; "AslDoesFileExistNtPath"
0x180017498  mov     dword ptr [rsp+80h+InputPathType], eax
0x18001749c  mov     ecx, esi
0x18001749e  call    AslLogCallPrintf
0x1800174a3  xor     edi, edi
0x1800174a5  jmp     loc_180017364
```
