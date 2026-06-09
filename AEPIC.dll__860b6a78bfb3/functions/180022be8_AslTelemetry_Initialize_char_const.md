# AslTelemetry::Initialize(char const *)

- ea: `0x180022be8`
- end: `0x180022f01`
- name: `?Initialize@AslTelemetry@@QEAAHPEBD@Z`
- size: `793`
- prototype: `__int64 __fastcall(AslTelemetry *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800022d0`

## callees

- `0x180005890`
- `0x180005da0`
- `0x180022be8`
- `0x180029614`
- `0x18002ba70`
- `0x1800eb010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180022c30`
- `ntdll!RtlInitUnicodeString` at `0x180022c94`
- `ntdll!RtlInitUnicodeString` at `0x180022c30`
- `ntdll!RtlInitUnicodeString` at `0x180022c94`
- `ntdll!LdrGetDllHandle` at `0x180022c42`
- `ntdll!LdrGetDllHandle` at `0x180022ca6`
- `ntdll!LdrGetDllHandle` at `0x180022c42`
- `ntdll!LdrGetDllHandle` at `0x180022ca6`
- `ntdll!RtlInitString` at `0x180022c62`
- `ntdll!RtlInitString` at `0x180022cbf`
- `ntdll!RtlInitString` at `0x180022c62`
- `ntdll!RtlInitString` at `0x180022cbf`
- `ntdll!LdrGetProcedureAddress` at `0x180022c7b`
- `ntdll!LdrGetProcedureAddress` at `0x180022cd8`
- `ntdll!LdrGetProcedureAddress` at `0x180022c7b`
- `ntdll!LdrGetProcedureAddress` at `0x180022cd8`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x180022d6c`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x180022d6c`
- `ntdll!NtCreateFile` at `0x180022dff`
- `ntdll!NtCreateFile` at `0x180022dff`
- `ntdll!NtQueryInformationFile` at `0x180022e3a`
- `ntdll!NtQueryInformationFile` at `0x180022e3a`
- `ntdll!NtClose` at `0x180022e45`
- `ntdll!NtClose` at `0x180022e45`

## string_xrefs

- `0x180022c89`: `ntdll.dll`
- `0x180022c0f`: `kernel32.dll`
- `0x180022cb4`: `LdrGetDllFullName`

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
  v6 = AslTelemetryCreate(this, "aepic");
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
0x180022be8  push    rbp
0x180022bea  push    rbx
0x180022beb  push    rsi
0x180022bec  push    rdi
0x180022bed  lea     rbp, [rsp-288h]
0x180022bf5  sub     rsp, 388h
0x180022bfc  mov     rax, cs:__security_cookie
0x180022c03  xor     rax, rsp
0x180022c06  mov     [rbp+2A0h+var_30], rax
0x180022c0d  xor     esi, esi
0x180022c0f  lea     rdx, SourceString; "kernel32.dll"
0x180022c16  mov     rdi, rcx
0x180022c19  mov     [rbp+2A0h+DllHandle], rsi
0x180022c1d  xorps   xmm0, xmm0
0x180022c20  mov     [rbp+2A0h+BaseAddress], rsi
0x180022c24  lea     rcx, [rbp+2A0h+DestinationString]; DestinationString
0x180022c28  mov     [rbp+2A0h+var_300], rsi
0x180022c2c  movups  xmmword ptr [rbp+2A0h+DestinationString.Length], xmm0
0x180022c30  call    cs:__imp_RtlInitUnicodeString
0x180022c36  lea     r9, [rbp+2A0h+DllHandle]; DllHandle
0x180022c3a  xor     edx, edx; DllCharacteristics
0x180022c3c  lea     r8, [rbp+2A0h+DestinationString]; DllName
0x180022c40  xor     ecx, ecx; DllPath
0x180022c42  call    cs:__imp_LdrGetDllHandle
0x180022c48  test    eax, eax
0x180022c4a  js      loc_180022E70
0x180022c50  xorps   xmm0, xmm0
0x180022c53  lea     rdx, aRtlpctofilehea; "RtlPcToFileHeader"
0x180022c5a  lea     rcx, [rbp+2A0h+Name]; DestinationString
0x180022c5e  movups  xmmword ptr [rbp+2A0h+Name.Length], xmm0
0x180022c62  call    cs:__imp_RtlInitString
0x180022c68  mov     rcx, [rbp+2A0h+DllHandle]; BaseAddress
0x180022c6c  lea     r9, [rbp+2A0h+ProcedureAddress]; ProcedureAddress
0x180022c70  xor     r8d, r8d; Ordinal
0x180022c73  mov     [rbp+2A0h+ProcedureAddress], rsi
0x180022c77  lea     rdx, [rbp+2A0h+Name]; Name
0x180022c7b  call    cs:__imp_LdrGetProcedureAddress
0x180022c81  test    eax, eax
0x180022c83  js      loc_180022E70
0x180022c89  lea     rdx, LibFileName; "ntdll.dll"
0x180022c90  lea     rcx, [rbp+2A0h+DestinationString]; DestinationString
0x180022c94  call    cs:__imp_RtlInitUnicodeString
0x180022c9a  lea     r9, [rbp+2A0h+BaseAddress]; DllHandle
0x180022c9e  xor     edx, edx; DllCharacteristics
0x180022ca0  lea     r8, [rbp+2A0h+DestinationString]; DllName
0x180022ca4  xor     ecx, ecx; DllPath
0x180022ca6  call    cs:__imp_LdrGetDllHandle
0x180022cac  test    eax, eax
0x180022cae  js      loc_180022E70
0x180022cb4  lea     rdx, aLdrgetdllfulln; "LdrGetDllFullName"
0x180022cbb  lea     rcx, [rbp+2A0h+Name]; DestinationString
0x180022cbf  call    cs:__imp_RtlInitString
0x180022cc5  mov     rcx, [rbp+2A0h+BaseAddress]; BaseAddress
0x180022cc9  lea     r9, [rbp+2A0h+var_2F8]; ProcedureAddress
0x180022ccd  xor     r8d, r8d; Ordinal
0x180022cd0  mov     [rbp+2A0h+var_2F8], rsi
0x180022cd4  lea     rdx, [rbp+2A0h+Name]; Name
0x180022cd8  call    cs:__imp_LdrGetProcedureAddress
0x180022cde  test    eax, eax
0x180022ce0  js      loc_180022E70
0x180022ce6  mov     rax, [rbp+2A0h+ProcedureAddress]
0x180022cea  lea     rdx, [rbp+2A0h+var_300]
0x180022cee  lea     rcx, AslTelemetryCreate
0x180022cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022cfa  mov     [rbp+2A0h+var_300], rax
0x180022cfe  mov     rcx, rax
0x180022d01  test    rax, rax
0x180022d04  jz      loc_180022E70
0x180022d0a  lea     rax, [rbp+2A0h+var_240]
0x180022d0e  mov     [rsp+3A0h+var_328], 2060000h
0x180022d17  mov     [rbp+2A0h+var_320], rax
0x180022d1b  lea     rdx, [rsp+3A0h+var_328]
0x180022d20  mov     rax, [rbp+2A0h+var_2F8]
0x180022d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d29  movzx   ecx, word ptr [rsp+3A0h+var_328]
0x180022d2e  shr     ecx, 1
0x180022d30  mov     edx, ecx
0x180022d32  lea     r8, [rcx+rcx]
0x180022d36  cmp     r8, 208h
0x180022d3d  jnb     loc_180022E6A
0x180022d43  mov     [rbp+r8+2A0h+var_240], si
0x180022d49  test    eax, eax
0x180022d4b  js      loc_180022E70
0x180022d51  cmp     edx, 103h
0x180022d57  ja      loc_180022E70
0x180022d5d  xor     r9d, r9d
0x180022d60  lea     rdx, [rsp+3A0h+var_328]
0x180022d65  xor     r8d, r8d
0x180022d68  lea     rcx, [rbp+2A0h+var_240]
0x180022d6c  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x180022d72  test    eax, eax
0x180022d74  js      loc_180022E70
0x180022d7a  mov     [rsp+3A0h+EaLength], esi; EaLength
0x180022d7e  lea     ecx, [rsi+1]
0x180022d81  mov     [rsp+3A0h+EaBuffer], rsi; EaBuffer
0x180022d86  lea     rax, [rsp+3A0h+var_328]
0x180022d8b  mov     [rsp+3A0h+CreateOptions], 60h ; '`'; CreateOptions
0x180022d93  lea     r9, [rbp+2A0h+IoStatusBlock]; IoStatusBlock
0x180022d97  mov     [rsp+3A0h+CreateDisposition], ecx; CreateDisposition
0x180022d9b  lea     r8, [rbp+2A0h+ObjectAttributes]; ObjectAttributes
0x180022d9f  mov     [rsp+3A0h+ShareAccess], ecx; ShareAccess
0x180022da3  xorps   xmm0, xmm0
0x180022da6  mov     [rbp+2A0h+ObjectAttributes.ObjectName], rax
0x180022daa  lea     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x180022daf  lea     rax, [rbp+2A0h+var_280]
0x180022db3  mov     [rsp+3A0h+FileAttributes], 80h; FileAttributes
0x180022dbb  mov     edx, 80100080h; DesiredAccess
0x180022dc0  mov     [rsp+3A0h+AllocationSize], rsi; AllocationSize
0x180022dc5  mov     [rsp+3A0h+FileHandle], rsi
0x180022dca  mov     qword ptr [rbp+2A0h+ObjectAttributes.Length], 30h ; '0'
0x180022dd2  mov     qword ptr [rbp+2A0h+ObjectAttributes.Attributes], 40h ; '@'
0x180022dda  movups  xmmword ptr [rbp+2A0h+IoStatusBlock], xmm0
0x180022dde  mov     [rbp+2A0h+var_278], 101h
0x180022de5  mov     [rbp+2A0h+ObjectAttributes.RootDirectory], rsi
0x180022de9  mov     [rbp+2A0h+ObjectAttributes.SecurityDescriptor], rsi
0x180022ded  mov     [rbp+2A0h+var_280], 0Ch
0x180022df4  mov     [rbp+2A0h+var_27C], 2
0x180022dfb  mov     [rbp+2A0h+ObjectAttributes.SecurityQualityOfService], rax
0x180022dff  call    cs:__imp_NtCreateFile
0x180022e05  test    eax, eax
0x180022e07  js      short loc_180022E70
0x180022e09  mov     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x180022e0e  lea     r9d, [rsi+28h]; Length
0x180022e12  xorps   xmm0, xmm0
0x180022e15  mov     [rbp+2A0h+FileInformation], rsi
0x180022e19  lea     r8, [rbp+2A0h+FileInformation]; FileInformation
0x180022e1d  mov     [rbp+2A0h+var_268], rsi
0x180022e21  lea     rdx, [rbp+2A0h+var_290]; IoStatusBlock
0x180022e25  mov     [rbp+2A0h+var_260], rsi
0x180022e29  movups  xmmword ptr [rbp+2A0h+var_290], xmm0
0x180022e2d  mov     dword ptr [rsp+3A0h+AllocationSize], 4; FileInformationClass
0x180022e35  movdqu  [rbp+2A0h+var_258], xmm0
0x180022e3a  call    cs:__imp_NtQueryInformationFile
0x180022e40  mov     rcx, [rsp+3A0h+FileHandle]; Handle
0x180022e45  call    cs:__imp_NtClose
0x180022e4b  mov     eax, 7FFE0014h
0x180022e50  mov     rcx, 0FFFF728E2DA50000h
0x180022e5a  mov     rax, [rax]
0x180022e5d  add     rax, rcx
0x180022e60  cmp     [rbp+2A0h+var_260], rax
0x180022e64  jge     short loc_180022E70
0x180022e66  xor     eax, eax
0x180022e68  jmp     short loc_180022EE6
0x180022e6a  call    __report_rangecheckfailure
0x180022e70  lea     rdx, aAepic_0; "aepic"
0x180022e77  mov     rcx, rdi
0x180022e7a  call    AslTelemetryCreate
0x180022e7f  mov     ebx, eax
0x180022e81  test    eax, eax
0x180022e83  js      short loc_180022EDF
0x180022e85  lea     r9, [rsp+3A0h+var_334]
0x180022e8a  mov     [rsp+3A0h+var_340], esi
0x180022e8e  lea     r8, [rsp+3A0h+var_338]
0x180022e93  mov     [rsp+3A0h+var_33C], esi
0x180022e97  lea     rdx, [rsp+3A0h+var_33C]
0x180022e9c  mov     [rsp+3A0h+var_338], esi
0x180022ea0  lea     rcx, [rsp+3A0h+var_340]
0x180022ea5  mov     [rsp+3A0h+var_334], esi
0x180022ea9  call    AslFileGetLongVersionForCurrentModule
0x180022eae  mov     r8, [rdi]
0x180022eb1  test    r8, r8
0x180022eb4  jz      short loc_180022EDF
0x180022eb6  mov     ecx, [rsp+3A0h+var_338]
0x180022eba  mov     edx, [rsp+3A0h+var_340]
0x180022ebe  mov     eax, [rsp+3A0h+var_33C]
0x180022ec2  shl     rdx, 10h
0x180022ec6  or      rdx, rax
0x180022ec9  shl     rdx, 10h
0x180022ecd  or      rdx, rcx
0x180022ed0  mov     ecx, [rsp+3A0h+var_334]
0x180022ed4  shl     rdx, 10h
0x180022ed8  or      rdx, rcx
0x180022edb  mov     [r8+40h], rdx
0x180022edf  not     ebx
0x180022ee1  shr     ebx, 1Fh
0x180022ee4  mov     eax, ebx
0x180022ee6  mov     rcx, [rbp+2A0h+var_30]
0x180022eed  xor     rcx, rsp; StackCookie
0x180022ef0  call    __security_check_cookie
0x180022ef5  add     rsp, 388h
0x180022efc  pop     rdi
0x180022efd  pop     rsi
0x180022efe  pop     rbx
0x180022eff  pop     rbp
0x180022f00  retn
```
