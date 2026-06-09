# AslTelemetry::Initialize(char const *)

- ea: `0x18000a8f0`
- end: `0x18000ac09`
- name: `?Initialize@AslTelemetry@@QEAAHPEBD@Z`
- size: `793`
- prototype: `__int64 __fastcall(AslTelemetry *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002020`

## callees

- `0x180004ea0`
- `0x180004ee0`
- `0x18000a8f0`
- `0x180047ae0`
- `0x18004b534`
- `0x1800ec010`

## import_xrefs

- `ntdll!LdrGetProcedureAddress` at `0x18000a983`
- `ntdll!LdrGetProcedureAddress` at `0x18000a9e0`
- `ntdll!LdrGetProcedureAddress` at `0x18000a983`
- `ntdll!LdrGetProcedureAddress` at `0x18000a9e0`
- `ntdll!LdrGetDllHandle` at `0x18000a94a`
- `ntdll!LdrGetDllHandle` at `0x18000a9ae`
- `ntdll!LdrGetDllHandle` at `0x18000a94a`
- `ntdll!LdrGetDllHandle` at `0x18000a9ae`
- `ntdll!NtCreateFile` at `0x18000ab07`
- `ntdll!NtCreateFile` at `0x18000ab07`
- `ntdll!RtlInitString` at `0x18000a96a`
- `ntdll!RtlInitString` at `0x18000a9c7`
- `ntdll!RtlInitString` at `0x18000a96a`
- `ntdll!RtlInitString` at `0x18000a9c7`
- `ntdll!NtQueryInformationFile` at `0x18000ab42`
- `ntdll!NtQueryInformationFile` at `0x18000ab42`
- `ntdll!NtClose` at `0x18000ab4d`
- `ntdll!NtClose` at `0x18000ab4d`
- `ntdll!RtlInitUnicodeString` at `0x18000a938`
- `ntdll!RtlInitUnicodeString` at `0x18000a99c`
- `ntdll!RtlInitUnicodeString` at `0x18000a938`
- `ntdll!RtlInitUnicodeString` at `0x18000a99c`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18000aa74`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18000aa74`

## string_xrefs

- `0x18000a917`: `kernel32.dll`
- `0x18000a991`: `ntdll.dll`
- `0x18000a9bc`: `LdrGetDllFullName`

## pseudocode

```c
_BOOL8 __fastcall AslTelemetry::Initialize(AslTelemetry *this, const char *a2)
{
  int v3; // eax
  __int64 v4; // rcx
  int v6; // ebx
  unsigned int v7; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v8; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v9; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v10; // [rsp+6Ch] [rbp-94h] BYREF
  void *FileHandle; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v12[2]; // [rsp+78h] [rbp-88h] BYREF
  PVOID DllHandle; // [rsp+88h] [rbp-78h] BYREF
  PVOID BaseAddress; // [rsp+90h] [rbp-70h] BYREF
  PVOID ProcedureAddress; // [rsp+98h] [rbp-68h] BYREF
  __int64 v16; // [rsp+A0h] [rbp-60h] BYREF
  PVOID v17; // [rsp+A8h] [rbp-58h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-50h] BYREF
  _STRING Name; // [rsp+C0h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+100h] [rbp+0h] BYREF
  struct _IO_STATUS_BLOCK v22; // [rsp+110h] [rbp+10h] BYREF
  _DWORD v23[4]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD FileInformation[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v25; // [rsp+140h] [rbp+40h]
  __int128 v26; // [rsp+148h] [rbp+48h]
  _WORD v27[264]; // [rsp+160h] [rbp+60h] BYREF

  DllHandle = 0;
  BaseAddress = 0;
  v16 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"kernel32.dll");
  if ( LdrGetDllHandle(0, 0, &DestinationString, &DllHandle) >= 0 )
  {
    Name = 0;
    RtlInitString(&Name, "RtlPcToFileHeader");
    ProcedureAddress = 0;
    if ( LdrGetProcedureAddress(DllHandle, &Name, 0, &ProcedureAddress) >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"ntdll.dll");
      if ( LdrGetDllHandle(0, 0, &DestinationString, &BaseAddress) >= 0 )
      {
        RtlInitString(&Name, "LdrGetDllFullName");
        v17 = 0;
        if ( LdrGetProcedureAddress(BaseAddress, &Name, 0, &v17) >= 0 )
        {
          v16 = ((__int64 (__fastcall *)(_QWORD, __int64 *))ProcedureAddress)(AslTelemetryCreate, &v16);
          if ( v16 )
          {
            v12[0] = 33947648;
            v12[1] = v27;
            v3 = ((__int64 (__fastcall *)(__int64, _QWORD *))v17)(v16, v12);
            v4 = LOWORD(v12[0]) >> 1;
            if ( (unsigned __int64)(2 * v4) >= 0x208 )
              _report_rangecheckfailure(v4, v4);
            v27[v4] = 0;
            if ( v3 >= 0
              && (unsigned int)v4 <= 0x103
              && (int)RtlDosPathNameToRelativeNtPathName_U_WithStatus(v27, v12, 0, 0) >= 0 )
            {
              ObjectAttributes.ObjectName = (PUNICODE_STRING)v12;
              FileHandle = 0;
              *(_QWORD *)&ObjectAttributes.Length = 48;
              *(_QWORD *)&ObjectAttributes.Attributes = 64;
              IoStatusBlock = 0;
              v23[2] = 257;
              ObjectAttributes.RootDirectory = 0;
              ObjectAttributes.SecurityDescriptor = 0;
              v23[0] = 12;
              v23[1] = 2;
              ObjectAttributes.SecurityQualityOfService = v23;
              if ( NtCreateFile(
                     &FileHandle,
                     0x80100080,
                     &ObjectAttributes,
                     &IoStatusBlock,
                     0,
                     0x80u,
                     1u,
                     1u,
                     0x60u,
                     0,
                     0) >= 0 )
              {
                FileInformation[0] = 0;
                FileInformation[1] = 0;
                v25 = 0;
                v22 = 0;
                v26 = 0;
                NtQueryInformationFile(FileHandle, &v22, FileInformation, 0x28u, FileBasicInformation);
                NtClose(FileHandle);
                if ( v25 < MEMORY[0x7FFE0014] - 155520000000000LL )
                  return 0;
              }
            }
          }
        }
      }
    }
  }
  v6 = AslTelemetryCreate(this, "AeMareBackup");
  if ( v6 >= 0 )
  {
    v7 = 0;
    v8 = 0;
    v9 = 0;
    v10 = 0;
    AslFileGetLongVersionForCurrentModule(&v7, &v8, &v9, &v10);
    if ( *(_QWORD *)this )
      *(_QWORD *)(*(_QWORD *)this + 64LL) = v10 | ((v9 | ((v8 | ((unsigned __int64)v7 << 16)) << 16)) << 16);
  }
  return v6 >= 0;
}

```

## disassembly

```asm
0x18000a8f0  push    rbp
0x18000a8f2  push    rbx
0x18000a8f3  push    rsi
0x18000a8f4  push    rdi
0x18000a8f5  lea     rbp, [rsp-288h]
0x18000a8fd  sub     rsp, 388h
0x18000a904  mov     rax, cs:__security_cookie
0x18000a90b  xor     rax, rsp
0x18000a90e  mov     [rbp+2A0h+var_30], rax
0x18000a915  xor     esi, esi
0x18000a917  lea     rdx, SourceString; "kernel32.dll"
0x18000a91e  mov     rdi, rcx
0x18000a921  mov     [rbp+2A0h+DllHandle], rsi
0x18000a925  xorps   xmm0, xmm0
0x18000a928  mov     [rbp+2A0h+BaseAddress], rsi
0x18000a92c  lea     rcx, [rbp+2A0h+DestinationString]; DestinationString
0x18000a930  mov     [rbp+2A0h+var_300], rsi
0x18000a934  movups  xmmword ptr [rbp+2A0h+DestinationString.Length], xmm0
0x18000a938  call    cs:__imp_RtlInitUnicodeString
0x18000a93e  lea     r9, [rbp+2A0h+DllHandle]; DllHandle
0x18000a942  xor     edx, edx; DllCharacteristics
0x18000a944  lea     r8, [rbp+2A0h+DestinationString]; DllName
0x18000a948  xor     ecx, ecx; DllPath
0x18000a94a  call    cs:__imp_LdrGetDllHandle
0x18000a950  test    eax, eax
0x18000a952  js      loc_18000AB72
0x18000a958  xorps   xmm0, xmm0
0x18000a95b  lea     rdx, aRtlpctofilehea; "RtlPcToFileHeader"
0x18000a962  lea     rcx, [rbp+2A0h+Name]; DestinationString
0x18000a966  movups  xmmword ptr [rbp+2A0h+Name.Length], xmm0
0x18000a96a  call    cs:__imp_RtlInitString
0x18000a970  mov     rcx, [rbp+2A0h+DllHandle]; BaseAddress
0x18000a974  lea     r9, [rbp+2A0h+ProcedureAddress]; ProcedureAddress
0x18000a978  xor     r8d, r8d; Ordinal
0x18000a97b  mov     [rbp+2A0h+ProcedureAddress], rsi
0x18000a97f  lea     rdx, [rbp+2A0h+Name]; Name
0x18000a983  call    cs:__imp_LdrGetProcedureAddress
0x18000a989  test    eax, eax
0x18000a98b  js      loc_18000AB72
0x18000a991  lea     rdx, LibFileName; "ntdll.dll"
0x18000a998  lea     rcx, [rbp+2A0h+DestinationString]; DestinationString
0x18000a99c  call    cs:__imp_RtlInitUnicodeString
0x18000a9a2  lea     r9, [rbp+2A0h+BaseAddress]; DllHandle
0x18000a9a6  xor     edx, edx; DllCharacteristics
0x18000a9a8  lea     r8, [rbp+2A0h+DestinationString]; DllName
0x18000a9ac  xor     ecx, ecx; DllPath
0x18000a9ae  call    cs:__imp_LdrGetDllHandle
0x18000a9b4  test    eax, eax
0x18000a9b6  js      loc_18000AB72
0x18000a9bc  lea     rdx, aLdrgetdllfulln; "LdrGetDllFullName"
0x18000a9c3  lea     rcx, [rbp+2A0h+Name]; DestinationString
0x18000a9c7  call    cs:__imp_RtlInitString
0x18000a9cd  mov     rcx, [rbp+2A0h+BaseAddress]; BaseAddress
0x18000a9d1  lea     r9, [rbp+2A0h+var_2F8]; ProcedureAddress
0x18000a9d5  xor     r8d, r8d; Ordinal
0x18000a9d8  mov     [rbp+2A0h+var_2F8], rsi
0x18000a9dc  lea     rdx, [rbp+2A0h+Name]; Name
0x18000a9e0  call    cs:__imp_LdrGetProcedureAddress
0x18000a9e6  test    eax, eax
0x18000a9e8  js      loc_18000AB72
0x18000a9ee  mov     rax, [rbp+2A0h+ProcedureAddress]
0x18000a9f2  lea     rdx, [rbp+2A0h+var_300]
0x18000a9f6  lea     rcx, AslTelemetryCreate
0x18000a9fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa02  mov     [rbp+2A0h+var_300], rax
0x18000aa06  mov     rcx, rax
0x18000aa09  test    rax, rax
0x18000aa0c  jz      loc_18000AB72
0x18000aa12  lea     rax, [rbp+2A0h+var_240]
0x18000aa16  mov     [rsp+3A0h+var_328], 2060000h
0x18000aa1f  mov     [rbp+2A0h+var_320], rax
0x18000aa23  lea     rdx, [rsp+3A0h+var_328]
0x18000aa28  mov     rax, [rbp+2A0h+var_2F8]
0x18000aa2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa31  movzx   ecx, word ptr [rsp+3A0h+var_328]
0x18000aa36  shr     ecx, 1
0x18000aa38  mov     edx, ecx
0x18000aa3a  lea     r8, [rcx+rcx]
0x18000aa3e  cmp     r8, 208h
0x18000aa45  jnb     loc_18000AC03
0x18000aa4b  mov     [rbp+r8+2A0h+var_240], si
0x18000aa51  test    eax, eax
0x18000aa53  js      loc_18000AB72
0x18000aa59  cmp     edx, 103h
0x18000aa5f  ja      loc_18000AB72
0x18000aa65  xor     r9d, r9d
0x18000aa68  lea     rdx, [rsp+3A0h+var_328]
0x18000aa6d  xor     r8d, r8d
0x18000aa70  lea     rcx, [rbp+2A0h+var_240]
0x18000aa74  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x18000aa7a  test    eax, eax
0x18000aa7c  js      loc_18000AB72
0x18000aa82  mov     [rsp+3A0h+EaLength], esi; EaLength
0x18000aa86  lea     ecx, [rsi+1]
0x18000aa89  mov     [rsp+3A0h+EaBuffer], rsi; EaBuffer
0x18000aa8e  lea     rax, [rsp+3A0h+var_328]
0x18000aa93  mov     [rsp+3A0h+CreateOptions], 60h ; '`'; CreateOptions
0x18000aa9b  lea     r9, [rbp+2A0h+IoStatusBlock]; IoStatusBlock
0x18000aa9f  mov     [rsp+3A0h+CreateDisposition], ecx; CreateDisposition
0x18000aaa3  lea     r8, [rbp+2A0h+ObjectAttributes]; ObjectAttributes
0x18000aaa7  mov     [rsp+3A0h+ShareAccess], ecx; ShareAccess
0x18000aaab  xorps   xmm0, xmm0
0x18000aaae  mov     [rbp+2A0h+ObjectAttributes.ObjectName], rax
0x18000aab2  lea     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x18000aab7  lea     rax, [rbp+2A0h+var_280]
0x18000aabb  mov     [rsp+3A0h+FileAttributes], 80h; FileAttributes
0x18000aac3  mov     edx, 80100080h; DesiredAccess
0x18000aac8  mov     [rsp+3A0h+AllocationSize], rsi; AllocationSize
0x18000aacd  mov     [rsp+3A0h+FileHandle], rsi
0x18000aad2  mov     qword ptr [rbp+2A0h+ObjectAttributes.Length], 30h ; '0'
0x18000aada  mov     qword ptr [rbp+2A0h+ObjectAttributes.Attributes], 40h ; '@'
0x18000aae2  movups  xmmword ptr [rbp+2A0h+IoStatusBlock], xmm0
0x18000aae6  mov     [rbp+2A0h+var_278], 101h
0x18000aaed  mov     [rbp+2A0h+ObjectAttributes.RootDirectory], rsi
0x18000aaf1  mov     [rbp+2A0h+ObjectAttributes.SecurityDescriptor], rsi
0x18000aaf5  mov     [rbp+2A0h+var_280], 0Ch
0x18000aafc  mov     [rbp+2A0h+var_27C], 2
0x18000ab03  mov     [rbp+2A0h+ObjectAttributes.SecurityQualityOfService], rax
0x18000ab07  call    cs:__imp_NtCreateFile
0x18000ab0d  test    eax, eax
0x18000ab0f  js      short loc_18000AB72
0x18000ab11  mov     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x18000ab16  lea     r9d, [rsi+28h]; Length
0x18000ab1a  xorps   xmm0, xmm0
0x18000ab1d  mov     [rbp+2A0h+FileInformation], rsi
0x18000ab21  lea     r8, [rbp+2A0h+FileInformation]; FileInformation
0x18000ab25  mov     [rbp+2A0h+var_268], rsi
0x18000ab29  lea     rdx, [rbp+2A0h+var_290]; IoStatusBlock
0x18000ab2d  mov     [rbp+2A0h+var_260], rsi
0x18000ab31  movups  xmmword ptr [rbp+2A0h+var_290], xmm0
0x18000ab35  mov     dword ptr [rsp+3A0h+AllocationSize], 4; FileInformationClass
0x18000ab3d  movdqu  [rbp+2A0h+var_258], xmm0
0x18000ab42  call    cs:__imp_NtQueryInformationFile
0x18000ab48  mov     rcx, [rsp+3A0h+FileHandle]; Handle
0x18000ab4d  call    cs:__imp_NtClose
0x18000ab53  mov     eax, 7FFE0014h
0x18000ab58  mov     rcx, 0FFFF728E2DA50000h
0x18000ab62  mov     rax, [rax]
0x18000ab65  add     rax, rcx
0x18000ab68  cmp     [rbp+2A0h+var_260], rax
0x18000ab6c  jge     short loc_18000AB72
0x18000ab6e  xor     eax, eax
0x18000ab70  jmp     short loc_18000ABE8
0x18000ab72  lea     rdx, aAemarebackup; "AeMareBackup"
0x18000ab79  mov     rcx, rdi
0x18000ab7c  call    AslTelemetryCreate
0x18000ab81  mov     ebx, eax
0x18000ab83  test    eax, eax
0x18000ab85  js      short loc_18000ABE1
0x18000ab87  lea     r9, [rsp+3A0h+var_334]
0x18000ab8c  mov     [rsp+3A0h+var_340], esi
0x18000ab90  lea     r8, [rsp+3A0h+var_338]
0x18000ab95  mov     [rsp+3A0h+var_33C], esi
0x18000ab99  lea     rdx, [rsp+3A0h+var_33C]
0x18000ab9e  mov     [rsp+3A0h+var_338], esi
0x18000aba2  lea     rcx, [rsp+3A0h+var_340]
0x18000aba7  mov     [rsp+3A0h+var_334], esi
0x18000abab  call    AslFileGetLongVersionForCurrentModule
0x18000abb0  mov     r8, [rdi]
0x18000abb3  test    r8, r8
0x18000abb6  jz      short loc_18000ABE1
0x18000abb8  mov     ecx, [rsp+3A0h+var_338]
0x18000abbc  mov     edx, [rsp+3A0h+var_340]
0x18000abc0  mov     eax, [rsp+3A0h+var_33C]
0x18000abc4  shl     rdx, 10h
0x18000abc8  or      rdx, rax
0x18000abcb  shl     rdx, 10h
0x18000abcf  or      rdx, rcx
0x18000abd2  mov     ecx, [rsp+3A0h+var_334]
0x18000abd6  shl     rdx, 10h
0x18000abda  or      rdx, rcx
0x18000abdd  mov     [r8+40h], rdx
0x18000abe1  not     ebx
0x18000abe3  shr     ebx, 1Fh
0x18000abe6  mov     eax, ebx
0x18000abe8  mov     rcx, [rbp+2A0h+var_30]
0x18000abef  xor     rcx, rsp; StackCookie
0x18000abf2  call    __security_check_cookie
0x18000abf7  add     rsp, 388h
0x18000abfe  pop     rdi
0x18000abff  pop     rsi
0x18000ac00  pop     rbx
0x18000ac01  pop     rbp
0x18000ac02  retn
0x18000ac03  call    __report_rangecheckfailure
```
