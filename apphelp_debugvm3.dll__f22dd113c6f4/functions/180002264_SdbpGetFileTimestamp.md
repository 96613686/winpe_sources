# SdbpGetFileTimestamp

- ea: `0x180002264`
- end: `0x18000250c`
- name: `SdbpGetFileTimestamp`
- size: `680`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003c7c`
- `0x180048668`

## callees

- `0x180002264`
- `0x18000f114`
- `0x180039a66`
- `0x180059175`
- `0x1800591b0`
- `0x18005a010`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x180002464`
- `ntdll!NtQueryInformationFile` at `0x180002464`
- `ntdll!RtlInitUnicodeString` at `0x1800022e7`
- `ntdll!RtlInitUnicodeString` at `0x1800022e7`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180002314`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180002314`
- `ntdll!ZwCreateFile` at `0x18000240d`
- `ntdll!ZwCreateFile` at `0x18000240d`
- `ntdll!ZwClose` at `0x1800024be`
- `ntdll!ZwClose` at `0x1800024be`
- `ntdll!RtlFreeHeap` at `0x1800024e0`
- `ntdll!RtlFreeHeap` at `0x1800024e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002358`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002358`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002377`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002377`

## string_xrefs

- `0x180002339`: `ntdll.dll`
- `0x180002424`: `Failed to open file [%x]`

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
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
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
  if ( wcsnicmp_0(a2, L"\\SystemRoot\\", 0xCu) )
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
    v10 = ((__int64 (__fastcall *)(_OBJECT_ATTRIBUTES *, _IO_STATUS_BLOCK *, _BYTE *, __int64, int))ProcAddress)(
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
0x180002264  mov     [rsp-8+arg_10], rbx
0x180002269  mov     [rsp-8+arg_18], rsi
0x18000226e  push    rbp
0x18000226f  push    rdi
0x180002270  push    r14
0x180002272  lea     rbp, [rsp-50h]
0x180002277  sub     rsp, 150h
0x18000227e  mov     rax, cs:__security_cookie
0x180002285  xor     rax, rsp
0x180002288  mov     [rbp+60h+var_20], rax
0x18000228c  xorps   xmm0, xmm0
0x18000228f  xor     eax, eax
0x180002291  xorps   xmm1, xmm1
0x180002294  mov     [rbp+60h+var_78], rax
0x180002298  mov     esi, r8d
0x18000229b  mov     [rsp+160h+var_F8], rax
0x1800022a0  mov     rdi, rdx
0x1800022a3  mov     [rsp+160h+FileHandle], rax
0x1800022a8  mov     r14, rcx
0x1800022ab  lea     r8d, [rax+48h]; Size
0x1800022af  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x1800022b3  xor     edx, edx; Val
0x1800022b5  lea     rcx, [rbp+60h+var_70]; void *
0x1800022b9  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x1800022bd  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x1800022c1  movups  xmmword ptr [rbp+60h+ObjectAttributes+1Ch], xmm0
0x1800022c5  movups  xmmword ptr [rsp+160h+IoStatusBlock], xmm0
0x1800022ca  movups  [rbp+60h+FileInformation], xmm1
0x1800022ce  movups  [rbp+60h+var_88], xmm1
0x1800022d2  call    memset_0
0x1800022d7  mov     rdx, rdi; SourceString
0x1800022da  mov     [rsp+160h+P], 0
0x1800022e3  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x1800022e7  call    cs:__imp_RtlInitUnicodeString
0x1800022ed  mov     r8d, 0Ch; MaxCount
0x1800022f3  lea     rdx, aSystemroot_4; "\\SystemRoot\\"
0x1800022fa  mov     rcx, rdi; String1
0x1800022fd  call    _wcsnicmp_0
0x180002302  test    eax, eax
0x180002304  jz      short loc_18000232B
0x180002306  xor     r9d, r9d
0x180002309  lea     rdx, [rsp+160h+var_F8]
0x18000230e  xor     r8d, r8d
0x180002311  mov     rcx, rdi
0x180002314  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18000231a  mov     ebx, eax
0x18000231c  test    eax, eax
0x18000231e  js      loc_1800024B4
0x180002324  lea     rax, [rsp+160h+var_F8]
0x180002329  jmp     short loc_18000232F
0x18000232b  lea     rax, [rbp+60h+DestinationString]
0x18000232f  xorps   xmm0, xmm0
0x180002332  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x180002339  lea     rcx, LibFileName; "ntdll.dll"
0x180002340  mov     [rbp+60h+ObjectAttributes.RootDirectory], 0
0x180002348  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000234d  mov     [rbp+60h+ObjectAttributes.Attributes], 40h ; '@'
0x180002354  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x180002358  call    cs:__imp_GetModuleHandleW
0x18000235e  test    rax, rax
0x180002361  jnz     short loc_18000236D
0x180002363  mov     ebx, 0C0000001h
0x180002368  jmp     loc_1800024B4
0x18000236d  lea     rdx, ProcName; "NtQueryInformationByName"
0x180002374  mov     rcx, rax; hModule
0x180002377  call    cs:__imp_GetProcAddress
0x18000237d  test    rax, rax
0x180002380  jz      short loc_1800023C0
0x180002382  mov     r9d, 48h ; 'H'
0x180002388  mov     dword ptr [rsp+160h+AllocationSize], 44h ; 'D'
0x180002390  lea     r8, [rbp+60h+var_70]
0x180002394  lea     rdx, [rsp+160h+IoStatusBlock]
0x180002399  lea     rcx, [rbp+60h+ObjectAttributes]
0x18000239d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023a2  mov     ebx, eax
0x1800023a4  cmp     eax, 0C0000034h
0x1800023a9  jz      loc_1800024B4
0x1800023af  test    eax, eax
0x1800023b1  js      short loc_1800023C0
0x1800023b3  mov     rax, qword ptr [rbp+60h+var_58+8]
0x1800023b7  mov     rcx, qword ptr [rbp+60h+var_58]
0x1800023bb  jmp     loc_1800024A9
0x1800023c0  mov     [rsp+160h+EaLength], 0; EaLength
0x1800023c8  lea     r9, [rsp+160h+IoStatusBlock]; IoStatusBlock
0x1800023cd  mov     [rsp+160h+EaBuffer], 0; EaBuffer
0x1800023d6  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x1800023da  mov     [rsp+160h+CreateOptions], 60h ; '`'; CreateOptions
0x1800023e2  lea     rcx, [rsp+160h+FileHandle]; FileHandle
0x1800023e7  mov     [rsp+160h+CreateDisposition], 1; CreateDisposition
0x1800023ef  mov     edx, 80100080h; DesiredAccess
0x1800023f4  mov     [rsp+160h+ShareAccess], 1; ShareAccess
0x1800023fc  mov     [rsp+160h+FileAttributes], 80h; FileAttributes
0x180002404  mov     [rsp+160h+AllocationSize], 0; AllocationSize
0x18000240d  call    cs:__imp_ZwCreateFile
0x180002413  mov     ebx, eax
0x180002415  test    eax, eax
0x180002417  jns     short loc_180002448
0x180002419  cmp     eax, 0C0000034h
0x18000241e  jz      loc_1800024B4
0x180002424  lea     r9, aFailedToOpenFi; "Failed to open file [%x]"
0x18000242b  mov     dword ptr [rsp+160h+AllocationSize], eax
0x18000242f  mov     r8d, 624h
0x180002435  lea     rdx, aSdbpgetfiletim; "SdbpGetFileTimestamp"
0x18000243c  mov     ecx, 1
0x180002441  call    AslLogCallPrintf
0x180002446  jmp     short loc_1800024B4
0x180002448  mov     rcx, [rsp+160h+FileHandle]; FileHandle
0x18000244d  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x180002451  mov     r9d, 28h ; '('; Length
0x180002457  mov     dword ptr [rsp+160h+AllocationSize], 4; FileInformationClass
0x18000245f  lea     rdx, [rsp+160h+IoStatusBlock]; IoStatusBlock
0x180002464  call    cs:__imp_NtQueryInformationFile
0x18000246a  mov     ebx, eax
0x18000246c  test    eax, eax
0x18000246e  jns     short loc_180002499
0x180002470  mov     [rsp+160h+FileAttributes], eax
0x180002474  lea     r9, aFailedToGetTim; "Failed to get timestamp from %S. [%x]"
0x18000247b  mov     r8d, 62Fh
0x180002481  mov     [rsp+160h+AllocationSize], rdi
0x180002486  lea     rdx, aSdbpgetfiletim; "SdbpGetFileTimestamp"
0x18000248d  mov     ecx, 1
0x180002492  call    AslLogCallPrintf
0x180002497  jmp     short loc_1800024B4
0x180002499  mov     rcx, qword ptr [rbp+60h+var_88]
0x18000249d  mov     rax, qword ptr [rbp+60h+var_88+8]
0x1800024a1  mov     qword ptr [rbp+60h+var_58], rcx
0x1800024a5  mov     qword ptr [rbp+60h+var_58+8], rax
0x1800024a9  test    esi, esi
0x1800024ab  cmovnz  rax, rcx
0x1800024af  xor     ebx, ebx
0x1800024b1  mov     [r14], rax
0x1800024b4  mov     rcx, [rsp+160h+FileHandle]; Handle
0x1800024b9  test    rcx, rcx
0x1800024bc  jz      short loc_1800024C4
0x1800024be  call    cs:__imp_ZwClose
0x1800024c4  cmp     [rsp+160h+P], 0
0x1800024ca  jz      short loc_1800024E6
0x1800024cc  mov     rcx, gs:60h
0x1800024d5  xor     edx, edx; Flags
0x1800024d7  mov     r8, [rsp+160h+P]; P
0x1800024dc  mov     rcx, [rcx+30h]; HeapHandle
0x1800024e0  call    cs:__imp_RtlFreeHeap
0x1800024e6  mov     eax, ebx
0x1800024e8  mov     rcx, [rbp+60h+var_20]
0x1800024ec  xor     rcx, rsp; StackCookie
0x1800024ef  call    __security_check_cookie
0x1800024f4  lea     r11, [rsp+160h+var_10]
0x1800024fc  mov     rbx, [r11+30h]
0x180002500  mov     rsi, [r11+38h]
0x180002504  mov     rsp, r11
0x180002507  pop     r14
0x180002509  pop     rdi
0x18000250a  pop     rbp
0x18000250b  retn
```
