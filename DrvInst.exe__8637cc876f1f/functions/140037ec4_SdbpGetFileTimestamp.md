# SdbpGetFileTimestamp

- ea: `0x140037ec4`
- end: `0x14003816d`
- name: `SdbpGetFileTimestamp`
- size: `681`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140034d80`
- `0x1400385dc`

## callees

- `0x140037ec4`
- `0x14003bf18`
- `0x140045eea`
- `0x140045f30`
- `0x140047010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x140037f5d`
- `msvcrt!_wcsnicmp` at `0x140037f5d`
- `ntdll!NtQueryInformationFile` at `0x1400380c5`
- `ntdll!NtQueryInformationFile` at `0x1400380c5`
- `ntdll!RtlInitUnicodeString` at `0x140037f47`
- `ntdll!RtlInitUnicodeString` at `0x140037f47`
- `ntdll!ZwClose` at `0x14003811f`
- `ntdll!ZwClose` at `0x14003811f`
- `ntdll!RtlFreeHeap` at `0x140038141`
- `ntdll!RtlFreeHeap` at `0x140038141`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x140037f75`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x140037f75`
- `ntdll!ZwCreateFile` at `0x14003806e`
- `ntdll!ZwCreateFile` at `0x14003806e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140037fb9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140037fb9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140037fd8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140037fd8`

## string_xrefs

- `0x140037f9a`: `ntdll.dll`
- `0x140038085`: `Failed to open file [%x]`

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
  if ( _wcsnicmp(a2, L"\\SystemRoot\\", 0xCu) )
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
0x140037ec4  mov     [rsp-8+arg_10], rbx
0x140037ec9  mov     [rsp-8+arg_18], rsi
0x140037ece  push    rbp
0x140037ecf  push    rdi
0x140037ed0  push    r14
0x140037ed2  lea     rbp, [rsp-50h]
0x140037ed7  sub     rsp, 150h
0x140037ede  mov     rax, cs:__security_cookie
0x140037ee5  xor     rax, rsp
0x140037ee8  mov     [rbp+60h+var_20], rax
0x140037eec  xorps   xmm0, xmm0
0x140037eef  xor     eax, eax
0x140037ef1  xorps   xmm1, xmm1
0x140037ef4  mov     [rbp+60h+var_78], rax
0x140037ef8  mov     esi, r8d
0x140037efb  mov     [rsp+160h+var_F8], rax
0x140037f00  mov     rdi, rdx
0x140037f03  mov     [rsp+160h+FileHandle], rax
0x140037f08  mov     r14, rcx
0x140037f0b  lea     r8d, [rax+48h]; Size
0x140037f0f  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x140037f13  xor     edx, edx; Val
0x140037f15  lea     rcx, [rbp+60h+var_70]; void *
0x140037f19  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x140037f1d  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x140037f21  movups  xmmword ptr [rbp+60h+ObjectAttributes+1Ch], xmm0
0x140037f25  movups  xmmword ptr [rsp+160h+IoStatusBlock], xmm0
0x140037f2a  movups  [rbp+60h+FileInformation], xmm1
0x140037f2e  movups  [rbp+60h+var_88], xmm1
0x140037f32  call    memset_0
0x140037f37  mov     rdx, rdi; SourceString
0x140037f3a  mov     [rsp+160h+P], 0
0x140037f43  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x140037f47  call    cs:__imp_RtlInitUnicodeString
0x140037f4d  mov     r8d, 0Ch; MaxCount
0x140037f53  lea     rdx, aSystemroot_2; "\\SystemRoot\\"
0x140037f5a  mov     rcx, rdi; String1
0x140037f5d  call    cs:__imp__wcsnicmp
0x140037f63  test    eax, eax
0x140037f65  jz      short loc_140037F8C
0x140037f67  xor     r9d, r9d
0x140037f6a  lea     rdx, [rsp+160h+var_F8]
0x140037f6f  xor     r8d, r8d
0x140037f72  mov     rcx, rdi
0x140037f75  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x140037f7b  mov     ebx, eax
0x140037f7d  test    eax, eax
0x140037f7f  js      loc_140038115
0x140037f85  lea     rax, [rsp+160h+var_F8]
0x140037f8a  jmp     short loc_140037F90
0x140037f8c  lea     rax, [rbp+60h+DestinationString]
0x140037f90  xorps   xmm0, xmm0
0x140037f93  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x140037f9a  lea     rcx, LibFileName; "ntdll.dll"
0x140037fa1  mov     [rbp+60h+ObjectAttributes.RootDirectory], 0
0x140037fa9  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x140037fae  mov     [rbp+60h+ObjectAttributes.Attributes], 40h ; '@'
0x140037fb5  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x140037fb9  call    cs:__imp_GetModuleHandleW
0x140037fbf  test    rax, rax
0x140037fc2  jnz     short loc_140037FCE
0x140037fc4  mov     ebx, 0C0000001h
0x140037fc9  jmp     loc_140038115
0x140037fce  lea     rdx, aNtqueryinforma; "NtQueryInformationByName"
0x140037fd5  mov     rcx, rax; hModule
0x140037fd8  call    cs:__imp_GetProcAddress
0x140037fde  test    rax, rax
0x140037fe1  jz      short loc_140038021
0x140037fe3  mov     r9d, 48h ; 'H'
0x140037fe9  mov     dword ptr [rsp+160h+AllocationSize], 44h ; 'D'
0x140037ff1  lea     r8, [rbp+60h+var_70]
0x140037ff5  lea     rdx, [rsp+160h+IoStatusBlock]
0x140037ffa  lea     rcx, [rbp+60h+ObjectAttributes]
0x140037ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038003  mov     ebx, eax
0x140038005  cmp     eax, 0C0000034h
0x14003800a  jz      loc_140038115
0x140038010  test    eax, eax
0x140038012  js      short loc_140038021
0x140038014  mov     rax, qword ptr [rbp+60h+var_58+8]
0x140038018  mov     rcx, qword ptr [rbp+60h+var_58]
0x14003801c  jmp     loc_14003810A
0x140038021  mov     [rsp+160h+EaLength], 0; EaLength
0x140038029  lea     r9, [rsp+160h+IoStatusBlock]; IoStatusBlock
0x14003802e  mov     [rsp+160h+EaBuffer], 0; EaBuffer
0x140038037  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x14003803b  mov     [rsp+160h+CreateOptions], 60h ; '`'; CreateOptions
0x140038043  lea     rcx, [rsp+160h+FileHandle]; FileHandle
0x140038048  mov     [rsp+160h+CreateDisposition], 1; CreateDisposition
0x140038050  mov     edx, 80100080h; DesiredAccess
0x140038055  mov     [rsp+160h+ShareAccess], 1; ShareAccess
0x14003805d  mov     [rsp+160h+FileAttributes], 80h; FileAttributes
0x140038065  mov     [rsp+160h+AllocationSize], 0; AllocationSize
0x14003806e  call    cs:__imp_ZwCreateFile
0x140038074  mov     ebx, eax
0x140038076  test    eax, eax
0x140038078  jns     short loc_1400380A9
0x14003807a  cmp     eax, 0C0000034h
0x14003807f  jz      loc_140038115
0x140038085  lea     r9, aFailedToOpenFi; "Failed to open file [%x]"
0x14003808c  mov     dword ptr [rsp+160h+AllocationSize], eax
0x140038090  mov     r8d, 624h
0x140038096  lea     rdx, aSdbpgetfiletim; "SdbpGetFileTimestamp"
0x14003809d  mov     ecx, 1
0x1400380a2  call    AslLogCallPrintf
0x1400380a7  jmp     short loc_140038115
0x1400380a9  mov     rcx, [rsp+160h+FileHandle]; FileHandle
0x1400380ae  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x1400380b2  mov     r9d, 28h ; '('; Length
0x1400380b8  mov     dword ptr [rsp+160h+AllocationSize], 4; FileInformationClass
0x1400380c0  lea     rdx, [rsp+160h+IoStatusBlock]; IoStatusBlock
0x1400380c5  call    cs:__imp_NtQueryInformationFile
0x1400380cb  mov     ebx, eax
0x1400380cd  test    eax, eax
0x1400380cf  jns     short loc_1400380FA
0x1400380d1  mov     [rsp+160h+FileAttributes], eax
0x1400380d5  lea     r9, aFailedToGetTim; "Failed to get timestamp from %S. [%x]"
0x1400380dc  mov     r8d, 62Fh
0x1400380e2  mov     [rsp+160h+AllocationSize], rdi
0x1400380e7  lea     rdx, aSdbpgetfiletim; "SdbpGetFileTimestamp"
0x1400380ee  mov     ecx, 1
0x1400380f3  call    AslLogCallPrintf
0x1400380f8  jmp     short loc_140038115
0x1400380fa  mov     rcx, qword ptr [rbp+60h+var_88]
0x1400380fe  mov     rax, qword ptr [rbp+60h+var_88+8]
0x140038102  mov     qword ptr [rbp+60h+var_58], rcx
0x140038106  mov     qword ptr [rbp+60h+var_58+8], rax
0x14003810a  test    esi, esi
0x14003810c  cmovnz  rax, rcx
0x140038110  xor     ebx, ebx
0x140038112  mov     [r14], rax
0x140038115  mov     rcx, [rsp+160h+FileHandle]; Handle
0x14003811a  test    rcx, rcx
0x14003811d  jz      short loc_140038125
0x14003811f  call    cs:__imp_ZwClose
0x140038125  cmp     [rsp+160h+P], 0
0x14003812b  jz      short loc_140038147
0x14003812d  mov     rcx, gs:60h
0x140038136  xor     edx, edx; Flags
0x140038138  mov     r8, [rsp+160h+P]; P
0x14003813d  mov     rcx, [rcx+30h]; HeapHandle
0x140038141  call    cs:__imp_RtlFreeHeap
0x140038147  mov     eax, ebx
0x140038149  mov     rcx, [rbp+60h+var_20]
0x14003814d  xor     rcx, rsp; StackCookie
0x140038150  call    __security_check_cookie
0x140038155  lea     r11, [rsp+160h+var_10]
0x14003815d  mov     rbx, [r11+30h]
0x140038161  mov     rsi, [r11+38h]
0x140038165  mov     rsp, r11
0x140038168  pop     r14
0x14003816a  pop     rdi
0x14003816b  pop     rbp
0x14003816c  retn
```
