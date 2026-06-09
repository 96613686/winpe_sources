# AslTelemetry::Initialize(char const *)

- ea: `0x18000c300`
- end: `0x18000c619`
- name: `?Initialize@AslTelemetry@@QEAAHPEBD@Z`
- size: `793`
- prototype: `__int64 __fastcall(AslTelemetry *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800025d0`

## callees

- `0x180002bf0`
- `0x180002c30`
- `0x18000c300`
- `0x180014320`
- `0x180015344`
- `0x1800d1010`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18000c517`
- `ntdll!NtCreateFile` at `0x18000c517`
- `ntdll!RtlInitString` at `0x18000c37a`
- `ntdll!RtlInitString` at `0x18000c3d7`
- `ntdll!RtlInitString` at `0x18000c37a`
- `ntdll!RtlInitString` at `0x18000c3d7`
- `ntdll!NtQueryInformationFile` at `0x18000c552`
- `ntdll!NtQueryInformationFile` at `0x18000c552`
- `ntdll!NtClose` at `0x18000c55d`
- `ntdll!NtClose` at `0x18000c55d`
- `ntdll!RtlInitUnicodeString` at `0x18000c348`
- `ntdll!RtlInitUnicodeString` at `0x18000c3ac`
- `ntdll!RtlInitUnicodeString` at `0x18000c348`
- `ntdll!RtlInitUnicodeString` at `0x18000c3ac`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18000c484`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18000c484`
- `ntdll!LdrGetDllHandle` at `0x18000c35a`
- `ntdll!LdrGetDllHandle` at `0x18000c3be`
- `ntdll!LdrGetDllHandle` at `0x18000c35a`
- `ntdll!LdrGetDllHandle` at `0x18000c3be`
- `ntdll!LdrGetProcedureAddress` at `0x18000c393`
- `ntdll!LdrGetProcedureAddress` at `0x18000c3f0`
- `ntdll!LdrGetProcedureAddress` at `0x18000c393`
- `ntdll!LdrGetProcedureAddress` at `0x18000c3f0`

## string_xrefs

- `0x18000c327`: `kernel32.dll`
- `0x18000c3a1`: `ntdll.dll`
- `0x18000c3cc`: `LdrGetDllFullName`

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
  v6 = AslTelemetryCreate(this, "InventorySvc");
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
0x18000c300  push    rbp
0x18000c302  push    rbx
0x18000c303  push    rsi
0x18000c304  push    rdi
0x18000c305  lea     rbp, [rsp-288h]
0x18000c30d  sub     rsp, 388h
0x18000c314  mov     rax, cs:__security_cookie
0x18000c31b  xor     rax, rsp
0x18000c31e  mov     [rbp+2A0h+var_30], rax
0x18000c325  xor     esi, esi
0x18000c327  lea     rdx, SourceString; "kernel32.dll"
0x18000c32e  mov     rdi, rcx
0x18000c331  mov     [rbp+2A0h+DllHandle], rsi
0x18000c335  xorps   xmm0, xmm0
0x18000c338  mov     [rbp+2A0h+BaseAddress], rsi
0x18000c33c  lea     rcx, [rbp+2A0h+DestinationString]; DestinationString
0x18000c340  mov     [rbp+2A0h+var_300], rsi
0x18000c344  movups  xmmword ptr [rbp+2A0h+DestinationString.Length], xmm0
0x18000c348  call    cs:__imp_RtlInitUnicodeString
0x18000c34e  lea     r9, [rbp+2A0h+DllHandle]; DllHandle
0x18000c352  xor     edx, edx; DllCharacteristics
0x18000c354  lea     r8, [rbp+2A0h+DestinationString]; DllName
0x18000c358  xor     ecx, ecx; DllPath
0x18000c35a  call    cs:__imp_LdrGetDllHandle
0x18000c360  test    eax, eax
0x18000c362  js      loc_18000C582
0x18000c368  xorps   xmm0, xmm0
0x18000c36b  lea     rdx, aRtlpctofilehea; "RtlPcToFileHeader"
0x18000c372  lea     rcx, [rbp+2A0h+Name]; DestinationString
0x18000c376  movups  xmmword ptr [rbp+2A0h+Name.Length], xmm0
0x18000c37a  call    cs:__imp_RtlInitString
0x18000c380  mov     rcx, [rbp+2A0h+DllHandle]; BaseAddress
0x18000c384  lea     r9, [rbp+2A0h+ProcedureAddress]; ProcedureAddress
0x18000c388  xor     r8d, r8d; Ordinal
0x18000c38b  mov     [rbp+2A0h+ProcedureAddress], rsi
0x18000c38f  lea     rdx, [rbp+2A0h+Name]; Name
0x18000c393  call    cs:__imp_LdrGetProcedureAddress
0x18000c399  test    eax, eax
0x18000c39b  js      loc_18000C582
0x18000c3a1  lea     rdx, LibFileName; "ntdll.dll"
0x18000c3a8  lea     rcx, [rbp+2A0h+DestinationString]; DestinationString
0x18000c3ac  call    cs:__imp_RtlInitUnicodeString
0x18000c3b2  lea     r9, [rbp+2A0h+BaseAddress]; DllHandle
0x18000c3b6  xor     edx, edx; DllCharacteristics
0x18000c3b8  lea     r8, [rbp+2A0h+DestinationString]; DllName
0x18000c3bc  xor     ecx, ecx; DllPath
0x18000c3be  call    cs:__imp_LdrGetDllHandle
0x18000c3c4  test    eax, eax
0x18000c3c6  js      loc_18000C582
0x18000c3cc  lea     rdx, aLdrgetdllfulln; "LdrGetDllFullName"
0x18000c3d3  lea     rcx, [rbp+2A0h+Name]; DestinationString
0x18000c3d7  call    cs:__imp_RtlInitString
0x18000c3dd  mov     rcx, [rbp+2A0h+BaseAddress]; BaseAddress
0x18000c3e1  lea     r9, [rbp+2A0h+var_2F8]; ProcedureAddress
0x18000c3e5  xor     r8d, r8d; Ordinal
0x18000c3e8  mov     [rbp+2A0h+var_2F8], rsi
0x18000c3ec  lea     rdx, [rbp+2A0h+Name]; Name
0x18000c3f0  call    cs:__imp_LdrGetProcedureAddress
0x18000c3f6  test    eax, eax
0x18000c3f8  js      loc_18000C582
0x18000c3fe  mov     rax, [rbp+2A0h+ProcedureAddress]
0x18000c402  lea     rdx, [rbp+2A0h+var_300]
0x18000c406  lea     rcx, AslTelemetryCreate
0x18000c40d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c412  mov     [rbp+2A0h+var_300], rax
0x18000c416  mov     rcx, rax
0x18000c419  test    rax, rax
0x18000c41c  jz      loc_18000C582
0x18000c422  lea     rax, [rbp+2A0h+var_240]
0x18000c426  mov     [rsp+3A0h+var_328], 2060000h
0x18000c42f  mov     [rbp+2A0h+var_320], rax
0x18000c433  lea     rdx, [rsp+3A0h+var_328]
0x18000c438  mov     rax, [rbp+2A0h+var_2F8]
0x18000c43c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c441  movzx   ecx, word ptr [rsp+3A0h+var_328]
0x18000c446  shr     ecx, 1
0x18000c448  mov     edx, ecx
0x18000c44a  lea     r8, [rcx+rcx]
0x18000c44e  cmp     r8, 208h
0x18000c455  jnb     loc_18000C613
0x18000c45b  mov     [rbp+r8+2A0h+var_240], si
0x18000c461  test    eax, eax
0x18000c463  js      loc_18000C582
0x18000c469  cmp     edx, 103h
0x18000c46f  ja      loc_18000C582
0x18000c475  xor     r9d, r9d
0x18000c478  lea     rdx, [rsp+3A0h+var_328]
0x18000c47d  xor     r8d, r8d
0x18000c480  lea     rcx, [rbp+2A0h+var_240]
0x18000c484  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x18000c48a  test    eax, eax
0x18000c48c  js      loc_18000C582
0x18000c492  mov     [rsp+3A0h+EaLength], esi; EaLength
0x18000c496  lea     ecx, [rsi+1]
0x18000c499  mov     [rsp+3A0h+EaBuffer], rsi; EaBuffer
0x18000c49e  lea     rax, [rsp+3A0h+var_328]
0x18000c4a3  mov     [rsp+3A0h+CreateOptions], 60h ; '`'; CreateOptions
0x18000c4ab  lea     r9, [rbp+2A0h+IoStatusBlock]; IoStatusBlock
0x18000c4af  mov     [rsp+3A0h+CreateDisposition], ecx; CreateDisposition
0x18000c4b3  lea     r8, [rbp+2A0h+ObjectAttributes]; ObjectAttributes
0x18000c4b7  mov     [rsp+3A0h+ShareAccess], ecx; ShareAccess
0x18000c4bb  xorps   xmm0, xmm0
0x18000c4be  mov     [rbp+2A0h+ObjectAttributes.ObjectName], rax
0x18000c4c2  lea     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x18000c4c7  lea     rax, [rbp+2A0h+var_280]
0x18000c4cb  mov     [rsp+3A0h+FileAttributes], 80h; FileAttributes
0x18000c4d3  mov     edx, 80100080h; DesiredAccess
0x18000c4d8  mov     [rsp+3A0h+AllocationSize], rsi; AllocationSize
0x18000c4dd  mov     [rsp+3A0h+FileHandle], rsi
0x18000c4e2  mov     qword ptr [rbp+2A0h+ObjectAttributes.Length], 30h ; '0'
0x18000c4ea  mov     qword ptr [rbp+2A0h+ObjectAttributes.Attributes], 40h ; '@'
0x18000c4f2  movups  xmmword ptr [rbp+2A0h+IoStatusBlock], xmm0
0x18000c4f6  mov     [rbp+2A0h+var_278], 101h
0x18000c4fd  mov     [rbp+2A0h+ObjectAttributes.RootDirectory], rsi
0x18000c501  mov     [rbp+2A0h+ObjectAttributes.SecurityDescriptor], rsi
0x18000c505  mov     [rbp+2A0h+var_280], 0Ch
0x18000c50c  mov     [rbp+2A0h+var_27C], 2
0x18000c513  mov     [rbp+2A0h+ObjectAttributes.SecurityQualityOfService], rax
0x18000c517  call    cs:__imp_NtCreateFile
0x18000c51d  test    eax, eax
0x18000c51f  js      short loc_18000C582
0x18000c521  mov     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x18000c526  lea     r9d, [rsi+28h]; Length
0x18000c52a  xorps   xmm0, xmm0
0x18000c52d  mov     [rbp+2A0h+FileInformation], rsi
0x18000c531  lea     r8, [rbp+2A0h+FileInformation]; FileInformation
0x18000c535  mov     [rbp+2A0h+var_268], rsi
0x18000c539  lea     rdx, [rbp+2A0h+var_290]; IoStatusBlock
0x18000c53d  mov     [rbp+2A0h+var_260], rsi
0x18000c541  movups  xmmword ptr [rbp+2A0h+var_290], xmm0
0x18000c545  mov     dword ptr [rsp+3A0h+AllocationSize], 4; FileInformationClass
0x18000c54d  movdqu  [rbp+2A0h+var_258], xmm0
0x18000c552  call    cs:__imp_NtQueryInformationFile
0x18000c558  mov     rcx, [rsp+3A0h+FileHandle]; Handle
0x18000c55d  call    cs:__imp_NtClose
0x18000c563  mov     eax, 7FFE0014h
0x18000c568  mov     rcx, 0FFFF728E2DA50000h
0x18000c572  mov     rax, [rax]
0x18000c575  add     rax, rcx
0x18000c578  cmp     [rbp+2A0h+var_260], rax
0x18000c57c  jge     short loc_18000C582
0x18000c57e  xor     eax, eax
0x18000c580  jmp     short loc_18000C5F8
0x18000c582  lea     rdx, aInventorysvc_0; "InventorySvc"
0x18000c589  mov     rcx, rdi
0x18000c58c  call    AslTelemetryCreate
0x18000c591  mov     ebx, eax
0x18000c593  test    eax, eax
0x18000c595  js      short loc_18000C5F1
0x18000c597  lea     r9, [rsp+3A0h+var_334]
0x18000c59c  mov     [rsp+3A0h+var_340], esi
0x18000c5a0  lea     r8, [rsp+3A0h+var_338]
0x18000c5a5  mov     [rsp+3A0h+var_33C], esi
0x18000c5a9  lea     rdx, [rsp+3A0h+var_33C]
0x18000c5ae  mov     [rsp+3A0h+var_338], esi
0x18000c5b2  lea     rcx, [rsp+3A0h+var_340]
0x18000c5b7  mov     [rsp+3A0h+var_334], esi
0x18000c5bb  call    AslFileGetLongVersionForCurrentModule
0x18000c5c0  mov     r8, [rdi]
0x18000c5c3  test    r8, r8
0x18000c5c6  jz      short loc_18000C5F1
0x18000c5c8  mov     ecx, [rsp+3A0h+var_338]
0x18000c5cc  mov     edx, [rsp+3A0h+var_340]
0x18000c5d0  mov     eax, [rsp+3A0h+var_33C]
0x18000c5d4  shl     rdx, 10h
0x18000c5d8  or      rdx, rax
0x18000c5db  shl     rdx, 10h
0x18000c5df  or      rdx, rcx
0x18000c5e2  mov     ecx, [rsp+3A0h+var_334]
0x18000c5e6  shl     rdx, 10h
0x18000c5ea  or      rdx, rcx
0x18000c5ed  mov     [r8+40h], rdx
0x18000c5f1  not     ebx
0x18000c5f3  shr     ebx, 1Fh
0x18000c5f6  mov     eax, ebx
0x18000c5f8  mov     rcx, [rbp+2A0h+var_30]
0x18000c5ff  xor     rcx, rsp; StackCookie
0x18000c602  call    __security_check_cookie
0x18000c607  add     rsp, 388h
0x18000c60e  pop     rdi
0x18000c60f  pop     rsi
0x18000c610  pop     rbx
0x18000c611  pop     rbp
0x18000c612  retn
0x18000c613  call    __report_rangecheckfailure
```
