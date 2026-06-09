# SdbpGetFileTimestamp

- ea: `0x1801197b0`
- end: `0x180119a58`
- name: `SdbpGetFileTimestamp`
- size: `680`
- prototype: `__int64 __fastcall(_QWORD *, const WCHAR *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180119ec8`
- `0x18011e0b8`

## callees

- `0x1800197d4`
- `0x180059920`
- `0x18005a7d8`
- `0x18005a8bc`
- `0x1801197b0`
- `0x180130010`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180119860`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180119860`
- `ntdll!ZwCreateFile` at `0x180119959`
- `ntdll!ZwCreateFile` at `0x180119959`
- `ntdll!ZwClose` at `0x180119a0a`
- `ntdll!ZwClose` at `0x180119a0a`
- `ntdll!RtlFreeHeap` at `0x180119a2c`
- `ntdll!RtlFreeHeap` at `0x180119a2c`
- `ntdll!RtlInitUnicodeString` at `0x180119833`
- `ntdll!RtlInitUnicodeString` at `0x180119833`
- `ntdll!NtQueryInformationFile` at `0x1801199b0`
- `ntdll!NtQueryInformationFile` at `0x1801199b0`
- `KERNEL32!GetModuleHandleW` at `0x1801198a4`
- `KERNEL32!GetModuleHandleW` at `0x1801198a4`
- `KERNEL32!GetProcAddress` at `0x1801198c3`
- `KERNEL32!GetProcAddress` at `0x1801198c3`

## string_xrefs

- `0x180119885`: `ntdll.dll`
- `0x180119970`: `Failed to open file [%x]`

## pseudocode

```c
__int64 __fastcall SdbpGetFileTimestamp(_QWORD *a1, const WCHAR *a2, int a3)
{
  NTSTATUS v6; // ebx
  struct _UNICODE_STRING *p_DestinationString; // rax
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rcx
  NTSTATUS v13; // eax
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v16; // [rsp+68h] [rbp-98h] BYREF
  PVOID P; // [rsp+70h] [rbp-90h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-48h] BYREF
  __int128 FileInformation; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v22; // [rsp+D8h] [rbp-28h]
  __int64 v23; // [rsp+E8h] [rbp-18h]
  _BYTE v24[24]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v25; // [rsp+108h] [rbp+8h]

  v23 = 0;
  v16 = 0;
  FileHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  FileInformation = 0;
  v22 = 0;
  memset_0(v24, 0, 0x48u);
  P = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  if ( wcsnicmp(a2, L"\\SystemRoot\\", 0xCu) )
  {
    v6 = RtlDosPathNameToNtPathName_U_WithStatus(a2, &v16, 0, 0);
    if ( v6 < 0 )
      goto LABEL_20;
    p_DestinationString = (struct _UNICODE_STRING *)&v16;
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
            v24,
            72,
            68);
    v6 = v10;
    if ( v10 == -1073741772 )
      goto LABEL_20;
    if ( v10 >= 0 )
    {
      v11 = *((_QWORD *)&v25 + 1);
      v12 = v25;
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
    v6 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
    if ( v6 < 0 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"SdbpGetFileTimestamp",
        1583,
        (unsigned int)"Failed to get timestamp from %S. [%x]");
      goto LABEL_20;
    }
    v11 = *((_QWORD *)&v22 + 1);
    v12 = v22;
    v25 = v22;
    goto LABEL_17;
  }
  if ( v13 != -1073741772 )
    AslLogCallPrintf(1, (unsigned int)"SdbpGetFileTimestamp", 1572, (unsigned int)"Failed to open file [%x]");
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
0x1801197b0  mov     [rsp-8+arg_10], rbx
0x1801197b5  mov     [rsp-8+arg_18], rsi
0x1801197ba  push    rbp
0x1801197bb  push    rdi
0x1801197bc  push    r14
0x1801197be  lea     rbp, [rsp-50h]
0x1801197c3  sub     rsp, 150h
0x1801197ca  mov     rax, cs:__security_cookie
0x1801197d1  xor     rax, rsp
0x1801197d4  mov     [rbp+60h+var_20], rax
0x1801197d8  xorps   xmm0, xmm0
0x1801197db  xor     eax, eax
0x1801197dd  xorps   xmm1, xmm1
0x1801197e0  mov     [rbp+60h+var_78], rax
0x1801197e4  mov     esi, r8d
0x1801197e7  mov     [rsp+160h+var_F8], rax
0x1801197ec  mov     rdi, rdx
0x1801197ef  mov     [rsp+160h+FileHandle], rax
0x1801197f4  mov     r14, rcx
0x1801197f7  lea     r8d, [rax+48h]; Size
0x1801197fb  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x1801197ff  xor     edx, edx; Val
0x180119801  lea     rcx, [rbp+60h+var_70]; void *
0x180119805  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x180119809  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x18011980d  movups  xmmword ptr [rbp+60h+ObjectAttributes+1Ch], xmm0
0x180119811  movups  xmmword ptr [rsp+160h+IoStatusBlock], xmm0
0x180119816  movups  [rbp+60h+FileInformation], xmm1
0x18011981a  movups  [rbp+60h+var_88], xmm1
0x18011981e  call    memset_0
0x180119823  mov     rdx, rdi; SourceString
0x180119826  mov     [rsp+160h+P], 0
0x18011982f  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x180119833  call    cs:__imp_RtlInitUnicodeString
0x180119839  mov     r8d, 0Ch; MaxCount
0x18011983f  lea     rdx, aSystemroot_3; "\\SystemRoot\\"
0x180119846  mov     rcx, rdi; String1
0x180119849  call    _wcsnicmp
0x18011984e  test    eax, eax
0x180119850  jz      short loc_180119877
0x180119852  xor     r9d, r9d
0x180119855  lea     rdx, [rsp+160h+var_F8]
0x18011985a  xor     r8d, r8d
0x18011985d  mov     rcx, rdi
0x180119860  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180119866  mov     ebx, eax
0x180119868  test    eax, eax
0x18011986a  js      loc_180119A00
0x180119870  lea     rax, [rsp+160h+var_F8]
0x180119875  jmp     short loc_18011987B
0x180119877  lea     rax, [rbp+60h+DestinationString]
0x18011987b  xorps   xmm0, xmm0
0x18011987e  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x180119885  lea     rcx, LibFileName; "ntdll.dll"
0x18011988c  mov     [rbp+60h+ObjectAttributes.RootDirectory], 0
0x180119894  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x180119899  mov     [rbp+60h+ObjectAttributes.Attributes], 40h ; '@'
0x1801198a0  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x1801198a4  call    cs:__imp_GetModuleHandleW
0x1801198aa  test    rax, rax
0x1801198ad  jnz     short loc_1801198B9
0x1801198af  mov     ebx, 0C0000001h
0x1801198b4  jmp     loc_180119A00
0x1801198b9  lea     rdx, aNtqueryinforma; "NtQueryInformationByName"
0x1801198c0  mov     rcx, rax; hModule
0x1801198c3  call    cs:__imp_GetProcAddress
0x1801198c9  test    rax, rax
0x1801198cc  jz      short loc_18011990C
0x1801198ce  mov     r9d, 48h ; 'H'
0x1801198d4  mov     dword ptr [rsp+160h+AllocationSize], 44h ; 'D'
0x1801198dc  lea     r8, [rbp+60h+var_70]
0x1801198e0  lea     rdx, [rsp+160h+IoStatusBlock]
0x1801198e5  lea     rcx, [rbp+60h+ObjectAttributes]
0x1801198e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801198ee  mov     ebx, eax
0x1801198f0  cmp     eax, 0C0000034h
0x1801198f5  jz      loc_180119A00
0x1801198fb  test    eax, eax
0x1801198fd  js      short loc_18011990C
0x1801198ff  mov     rax, qword ptr [rbp+60h+var_58+8]
0x180119903  mov     rcx, qword ptr [rbp+60h+var_58]
0x180119907  jmp     loc_1801199F5
0x18011990c  mov     [rsp+160h+EaLength], 0; EaLength
0x180119914  lea     r9, [rsp+160h+IoStatusBlock]; IoStatusBlock
0x180119919  mov     [rsp+160h+EaBuffer], 0; EaBuffer
0x180119922  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x180119926  mov     [rsp+160h+CreateOptions], 60h ; '`'; CreateOptions
0x18011992e  lea     rcx, [rsp+160h+FileHandle]; FileHandle
0x180119933  mov     [rsp+160h+CreateDisposition], 1; CreateDisposition
0x18011993b  mov     edx, 80100080h; DesiredAccess
0x180119940  mov     [rsp+160h+ShareAccess], 1; ShareAccess
0x180119948  mov     [rsp+160h+FileAttributes], 80h; FileAttributes
0x180119950  mov     [rsp+160h+AllocationSize], 0; AllocationSize
0x180119959  call    cs:__imp_ZwCreateFile
0x18011995f  mov     ebx, eax
0x180119961  test    eax, eax
0x180119963  jns     short loc_180119994
0x180119965  cmp     eax, 0C0000034h
0x18011996a  jz      loc_180119A00
0x180119970  lea     r9, aFailedToOpenFi; "Failed to open file [%x]"
0x180119977  mov     dword ptr [rsp+160h+AllocationSize], eax
0x18011997b  mov     r8d, 624h
0x180119981  lea     rdx, aSdbpgetfiletim; "SdbpGetFileTimestamp"
0x180119988  mov     ecx, 1
0x18011998d  call    AslLogCallPrintf
0x180119992  jmp     short loc_180119A00
0x180119994  mov     rcx, [rsp+160h+FileHandle]; FileHandle
0x180119999  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x18011999d  mov     r9d, 28h ; '('; Length
0x1801199a3  mov     dword ptr [rsp+160h+AllocationSize], 4; FileInformationClass
0x1801199ab  lea     rdx, [rsp+160h+IoStatusBlock]; IoStatusBlock
0x1801199b0  call    cs:__imp_NtQueryInformationFile
0x1801199b6  mov     ebx, eax
0x1801199b8  test    eax, eax
0x1801199ba  jns     short loc_1801199E5
0x1801199bc  mov     [rsp+160h+FileAttributes], eax
0x1801199c0  lea     r9, aFailedToGetTim; "Failed to get timestamp from %S. [%x]"
0x1801199c7  mov     r8d, 62Fh
0x1801199cd  mov     [rsp+160h+AllocationSize], rdi
0x1801199d2  lea     rdx, aSdbpgetfiletim; "SdbpGetFileTimestamp"
0x1801199d9  mov     ecx, 1
0x1801199de  call    AslLogCallPrintf
0x1801199e3  jmp     short loc_180119A00
0x1801199e5  mov     rcx, qword ptr [rbp+60h+var_88]
0x1801199e9  mov     rax, qword ptr [rbp+60h+var_88+8]
0x1801199ed  mov     qword ptr [rbp+60h+var_58], rcx
0x1801199f1  mov     qword ptr [rbp+60h+var_58+8], rax
0x1801199f5  test    esi, esi
0x1801199f7  cmovnz  rax, rcx
0x1801199fb  xor     ebx, ebx
0x1801199fd  mov     [r14], rax
0x180119a00  mov     rcx, [rsp+160h+FileHandle]; Handle
0x180119a05  test    rcx, rcx
0x180119a08  jz      short loc_180119A10
0x180119a0a  call    cs:__imp_ZwClose
0x180119a10  cmp     [rsp+160h+P], 0
0x180119a16  jz      short loc_180119A32
0x180119a18  mov     rcx, gs:60h
0x180119a21  xor     edx, edx; Flags
0x180119a23  mov     r8, [rsp+160h+P]; P
0x180119a28  mov     rcx, [rcx+30h]; HeapHandle
0x180119a2c  call    cs:__imp_RtlFreeHeap
0x180119a32  mov     eax, ebx
0x180119a34  mov     rcx, [rbp+60h+var_20]
0x180119a38  xor     rcx, rsp; StackCookie
0x180119a3b  call    __security_check_cookie
0x180119a40  lea     r11, [rsp+160h+var_10]
0x180119a48  mov     rbx, [r11+30h]
0x180119a4c  mov     rsi, [r11+38h]
0x180119a50  mov     rsp, r11
0x180119a53  pop     r14
0x180119a55  pop     rdi
0x180119a56  pop     rbp
0x180119a57  retn
```
