# SdbpGetFileTimestamp

- ea: `0x18005f05c`
- end: `0x18005f304`
- name: `SdbpGetFileTimestamp`
- size: `680`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005f728`

## callees

- `0x180001cf0`
- `0x1800027a8`
- `0x180002874`
- `0x1800543c0`
- `0x18005f05c`
- `0x18006a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18005f150`
- `KERNEL32!GetModuleHandleW` at `0x18005f150`
- `KERNEL32!GetProcAddress` at `0x18005f16f`
- `KERNEL32!GetProcAddress` at `0x18005f16f`
- `ntdll!RtlInitUnicodeString` at `0x18005f0df`
- `ntdll!RtlInitUnicodeString` at `0x18005f0df`
- `ntdll!RtlFreeHeap` at `0x18005f2d8`
- `ntdll!RtlFreeHeap` at `0x18005f2d8`
- `ntdll!ZwClose` at `0x18005f2b6`
- `ntdll!ZwClose` at `0x18005f2b6`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18005f10c`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18005f10c`
- `ntdll!ZwCreateFile` at `0x18005f205`
- `ntdll!ZwCreateFile` at `0x18005f205`
- `ntdll!NtQueryInformationFile` at `0x18005f25c`
- `ntdll!NtQueryInformationFile` at `0x18005f25c`

## string_xrefs

- `0x18005f131`: `ntdll.dll`
- `0x18005f21c`: `Failed to open file [%x]`

## pseudocode

```c
__int64 __fastcall SdbpGetFileTimestamp(_QWORD *a1, const WCHAR *a2, int a3)
{
  int v6; // ebx
  struct _UNICODE_STRING *p_DestinationString; // rax
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rcx
  NTSTATUS v13; // eax
  NTSTATUS v14; // eax
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v17; // [rsp+68h] [rbp-98h] BYREF
  PVOID P; // [rsp+70h] [rbp-90h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-48h] BYREF
  __int128 FileInformation; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v23; // [rsp+D8h] [rbp-28h]
  __int64 v24; // [rsp+E8h] [rbp-18h]
  _BYTE v25[24]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v26; // [rsp+108h] [rbp+8h]

  v24 = 0;
  v17 = 0;
  FileHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  FileInformation = 0;
  v23 = 0;
  memset_0(v25, 0, 0x48u);
  P = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  if ( wcsnicmp(a2, L"\\SystemRoot\\", 0xCu) )
  {
    v6 = RtlDosPathNameToNtPathName_U_WithStatus(a2, &v17, 0, 0);
    if ( v6 < 0 )
      goto LABEL_20;
    p_DestinationString = (struct _UNICODE_STRING *)&v17;
  }
  else
  {
    p_DestinationString = &DestinationString;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = p_DestinationString;
  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  if ( !ModuleHandleW )
  {
    v6 = -1073741823;
    goto LABEL_20;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "NtQueryInformationByName");
  if ( ProcAddress )
  {
    v10 = ((__int64 (__fastcall *)(struct _OBJECT_ATTRIBUTES *, struct _IO_STATUS_BLOCK *, _BYTE *, __int64, int))ProcAddress)(
            &ObjectAttributes,
            &IoStatusBlock,
            v25,
            72,
            68);
    v6 = v10;
    if ( v10 == -1073741772 )
      goto LABEL_20;
    if ( v10 >= 0 )
    {
      v11 = *((_QWORD *)&v26 + 1);
      v12 = v26;
LABEL_17:
      if ( a3 )
        v11 = v12;
      v6 = 0;
      *a1 = v11;
      goto LABEL_20;
    }
  }
  v13 = ZwCreateFile(&FileHandle, 0x80100080, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 1u, 0x60u, 0, 0);
  v6 = v13;
  if ( v13 >= 0 )
  {
    v14 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
    v6 = v14;
    if ( v14 < 0 )
    {
      AslLogCallPrintf(1, "SdbpGetFileTimestamp", 1583, "Failed to get timestamp from %S. [%x]", a2, v14);
      goto LABEL_20;
    }
    v11 = *((_QWORD *)&v23 + 1);
    v12 = v23;
    v26 = v23;
    goto LABEL_17;
  }
  if ( v13 != -1073741772 )
    AslLogCallPrintf(1, "SdbpGetFileTimestamp", 1572, "Failed to open file [%x]", v13);
LABEL_20:
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005f05c  mov     [rsp-8+arg_10], rbx
0x18005f061  mov     [rsp-8+arg_18], rsi
0x18005f066  push    rbp
0x18005f067  push    rdi
0x18005f068  push    r14
0x18005f06a  lea     rbp, [rsp-50h]
0x18005f06f  sub     rsp, 150h
0x18005f076  mov     rax, cs:__security_cookie
0x18005f07d  xor     rax, rsp
0x18005f080  mov     [rbp+60h+var_20], rax
0x18005f084  xorps   xmm0, xmm0
0x18005f087  xor     eax, eax
0x18005f089  xorps   xmm1, xmm1
0x18005f08c  mov     [rbp+60h+var_78], rax
0x18005f090  mov     esi, r8d
0x18005f093  mov     [rsp+160h+var_F8], rax
0x18005f098  mov     rdi, rdx
0x18005f09b  mov     [rsp+160h+FileHandle], rax
0x18005f0a0  mov     r14, rcx
0x18005f0a3  lea     r8d, [rax+48h]; Size
0x18005f0a7  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x18005f0ab  xor     edx, edx; Val
0x18005f0ad  lea     rcx, [rbp+60h+var_70]; void *
0x18005f0b1  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x18005f0b5  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x18005f0b9  movups  xmmword ptr [rbp+60h+ObjectAttributes+1Ch], xmm0
0x18005f0bd  movups  xmmword ptr [rsp+160h+IoStatusBlock], xmm0
0x18005f0c2  movups  [rbp+60h+FileInformation], xmm1
0x18005f0c6  movups  [rbp+60h+var_88], xmm1
0x18005f0ca  call    memset_0
0x18005f0cf  mov     rdx, rdi; SourceString
0x18005f0d2  mov     [rsp+160h+P], 0
0x18005f0db  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x18005f0df  call    cs:__imp_RtlInitUnicodeString
0x18005f0e5  mov     r8d, 0Ch; MaxCount
0x18005f0eb  lea     rdx, aSystemroot_4; "\\SystemRoot\\"
0x18005f0f2  mov     rcx, rdi; String1
0x18005f0f5  call    _wcsnicmp
0x18005f0fa  test    eax, eax
0x18005f0fc  jz      short loc_18005F123
0x18005f0fe  xor     r9d, r9d
0x18005f101  lea     rdx, [rsp+160h+var_F8]
0x18005f106  xor     r8d, r8d
0x18005f109  mov     rcx, rdi
0x18005f10c  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18005f112  mov     ebx, eax
0x18005f114  test    eax, eax
0x18005f116  js      loc_18005F2AC
0x18005f11c  lea     rax, [rsp+160h+var_F8]
0x18005f121  jmp     short loc_18005F127
0x18005f123  lea     rax, [rbp+60h+DestinationString]
0x18005f127  xorps   xmm0, xmm0
0x18005f12a  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x18005f131  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18005f138  mov     [rbp+60h+ObjectAttributes.RootDirectory], 0
0x18005f140  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005f145  mov     [rbp+60h+ObjectAttributes.Attributes], 40h ; '@'
0x18005f14c  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x18005f150  call    cs:__imp_GetModuleHandleW
0x18005f156  test    rax, rax
0x18005f159  jnz     short loc_18005F165
0x18005f15b  mov     ebx, 0C0000001h
0x18005f160  jmp     loc_18005F2AC
0x18005f165  lea     rdx, aNtqueryinforma; "NtQueryInformationByName"
0x18005f16c  mov     rcx, rax; hModule
0x18005f16f  call    cs:__imp_GetProcAddress
0x18005f175  test    rax, rax
0x18005f178  jz      short loc_18005F1B8
0x18005f17a  mov     r9d, 48h ; 'H'
0x18005f180  mov     dword ptr [rsp+160h+AllocationSize], 44h ; 'D'
0x18005f188  lea     r8, [rbp+60h+var_70]
0x18005f18c  lea     rdx, [rsp+160h+IoStatusBlock]
0x18005f191  lea     rcx, [rbp+60h+ObjectAttributes]
0x18005f195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f19a  mov     ebx, eax
0x18005f19c  cmp     eax, 0C0000034h
0x18005f1a1  jz      loc_18005F2AC
0x18005f1a7  test    eax, eax
0x18005f1a9  js      short loc_18005F1B8
0x18005f1ab  mov     rax, qword ptr [rbp+60h+var_58+8]
0x18005f1af  mov     rcx, qword ptr [rbp+60h+var_58]
0x18005f1b3  jmp     loc_18005F2A1
0x18005f1b8  mov     [rsp+160h+EaLength], 0; EaLength
0x18005f1c0  lea     r9, [rsp+160h+IoStatusBlock]; IoStatusBlock
0x18005f1c5  mov     [rsp+160h+EaBuffer], 0; EaBuffer
0x18005f1ce  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x18005f1d2  mov     [rsp+160h+CreateOptions], 60h ; '`'; CreateOptions
0x18005f1da  lea     rcx, [rsp+160h+FileHandle]; FileHandle
0x18005f1df  mov     [rsp+160h+CreateDisposition], 1; CreateDisposition
0x18005f1e7  mov     edx, 80100080h; DesiredAccess
0x18005f1ec  mov     [rsp+160h+ShareAccess], 1; ShareAccess
0x18005f1f4  mov     [rsp+160h+FileAttributes], 80h; FileAttributes
0x18005f1fc  mov     [rsp+160h+AllocationSize], 0; AllocationSize
0x18005f205  call    cs:__imp_ZwCreateFile
0x18005f20b  mov     ebx, eax
0x18005f20d  test    eax, eax
0x18005f20f  jns     short loc_18005F240
0x18005f211  cmp     eax, 0C0000034h
0x18005f216  jz      loc_18005F2AC
0x18005f21c  lea     r9, aFailedToOpenFi_0; "Failed to open file [%x]"
0x18005f223  mov     dword ptr [rsp+160h+AllocationSize], eax
0x18005f227  mov     r8d, 624h
0x18005f22d  lea     rdx, aSdbpgetfiletim; "SdbpGetFileTimestamp"
0x18005f234  mov     ecx, 1
0x18005f239  call    AslLogCallPrintf
0x18005f23e  jmp     short loc_18005F2AC
0x18005f240  mov     rcx, [rsp+160h+FileHandle]; FileHandle
0x18005f245  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x18005f249  mov     r9d, 28h ; '('; Length
0x18005f24f  mov     dword ptr [rsp+160h+AllocationSize], 4; FileInformationClass
0x18005f257  lea     rdx, [rsp+160h+IoStatusBlock]; IoStatusBlock
0x18005f25c  call    cs:__imp_NtQueryInformationFile
0x18005f262  mov     ebx, eax
0x18005f264  test    eax, eax
0x18005f266  jns     short loc_18005F291
0x18005f268  mov     [rsp+160h+FileAttributes], eax
0x18005f26c  lea     r9, aFailedToGetTim; "Failed to get timestamp from %S. [%x]"
0x18005f273  mov     r8d, 62Fh
0x18005f279  mov     [rsp+160h+AllocationSize], rdi
0x18005f27e  lea     rdx, aSdbpgetfiletim; "SdbpGetFileTimestamp"
0x18005f285  mov     ecx, 1
0x18005f28a  call    AslLogCallPrintf
0x18005f28f  jmp     short loc_18005F2AC
0x18005f291  mov     rcx, qword ptr [rbp+60h+var_88]
0x18005f295  mov     rax, qword ptr [rbp+60h+var_88+8]
0x18005f299  mov     qword ptr [rbp+60h+var_58], rcx
0x18005f29d  mov     qword ptr [rbp+60h+var_58+8], rax
0x18005f2a1  test    esi, esi
0x18005f2a3  cmovnz  rax, rcx
0x18005f2a7  xor     ebx, ebx
0x18005f2a9  mov     [r14], rax
0x18005f2ac  mov     rcx, [rsp+160h+FileHandle]; Handle
0x18005f2b1  test    rcx, rcx
0x18005f2b4  jz      short loc_18005F2BC
0x18005f2b6  call    cs:__imp_ZwClose
0x18005f2bc  cmp     [rsp+160h+P], 0
0x18005f2c2  jz      short loc_18005F2DE
0x18005f2c4  mov     rcx, gs:60h
0x18005f2cd  xor     edx, edx; Flags
0x18005f2cf  mov     r8, [rsp+160h+P]; P
0x18005f2d4  mov     rcx, [rcx+30h]; HeapHandle
0x18005f2d8  call    cs:__imp_RtlFreeHeap
0x18005f2de  mov     eax, ebx
0x18005f2e0  mov     rcx, [rbp+60h+var_20]
0x18005f2e4  xor     rcx, rsp; StackCookie
0x18005f2e7  call    __security_check_cookie
0x18005f2ec  lea     r11, [rsp+160h+var_10]
0x18005f2f4  mov     rbx, [r11+30h]
0x18005f2f8  mov     rsi, [r11+38h]
0x18005f2fc  mov     rsp, r11
0x18005f2ff  pop     r14
0x18005f301  pop     rdi
0x18005f302  pop     rbp
0x18005f303  retn
```
