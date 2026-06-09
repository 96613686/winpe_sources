# AslTelemetry::Initialize(char const *)

- ea: `0x180027d08`
- end: `0x180028021`
- name: `?Initialize@AslTelemetry@@QEAAHPEBD@Z`
- size: `793`
- prototype: `__int64 __fastcall(AslTelemetry *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002d30`

## callees

- `0x180027d08`
- `0x18002c140`
- `0x180050550`
- `0x180059920`
- `0x180059d40`
- `0x180130010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180027d50`
- `ntdll!RtlInitUnicodeString` at `0x180027db4`
- `ntdll!RtlInitUnicodeString` at `0x180027d50`
- `ntdll!RtlInitUnicodeString` at `0x180027db4`
- `ntdll!LdrGetDllHandle` at `0x180027d62`
- `ntdll!LdrGetDllHandle` at `0x180027dc6`
- `ntdll!LdrGetDllHandle` at `0x180027d62`
- `ntdll!LdrGetDllHandle` at `0x180027dc6`
- `ntdll!RtlInitString` at `0x180027d82`
- `ntdll!RtlInitString` at `0x180027ddf`
- `ntdll!RtlInitString` at `0x180027d82`
- `ntdll!RtlInitString` at `0x180027ddf`
- `ntdll!LdrGetProcedureAddress` at `0x180027d9b`
- `ntdll!LdrGetProcedureAddress` at `0x180027df8`
- `ntdll!LdrGetProcedureAddress` at `0x180027d9b`
- `ntdll!LdrGetProcedureAddress` at `0x180027df8`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x180027e8c`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x180027e8c`
- `ntdll!NtCreateFile` at `0x180027f1f`
- `ntdll!NtCreateFile` at `0x180027f1f`
- `ntdll!NtQueryInformationFile` at `0x180027f5a`
- `ntdll!NtQueryInformationFile` at `0x180027f5a`
- `ntdll!NtClose` at `0x180027f65`
- `ntdll!NtClose` at `0x180027f65`

## string_xrefs

- `0x180027da9`: `ntdll.dll`
- `0x180027dd4`: `LdrGetDllFullName`
- `0x180027d2f`: `kernel32.dll`

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
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-50h] BYREF
  _STRING Name; // [rsp+C0h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+100h] [rbp+0h] BYREF
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
  v6 = AslTelemetryCreate(this, "aeinv");
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
0x180027d08  push    rbp
0x180027d0a  push    rbx
0x180027d0b  push    rsi
0x180027d0c  push    rdi
0x180027d0d  lea     rbp, [rsp-288h]
0x180027d15  sub     rsp, 388h
0x180027d1c  mov     rax, cs:__security_cookie
0x180027d23  xor     rax, rsp
0x180027d26  mov     [rbp+2A0h+var_30], rax
0x180027d2d  xor     esi, esi
0x180027d2f  lea     rdx, aKernel32Dll_1; "kernel32.dll"
0x180027d36  mov     rdi, rcx
0x180027d39  mov     [rbp+2A0h+DllHandle], rsi
0x180027d3d  xorps   xmm0, xmm0
0x180027d40  mov     [rbp+2A0h+BaseAddress], rsi
0x180027d44  lea     rcx, [rbp+2A0h+DestinationString]; DestinationString
0x180027d48  mov     [rbp+2A0h+var_300], rsi
0x180027d4c  movups  xmmword ptr [rbp+2A0h+DestinationString.Length], xmm0
0x180027d50  call    cs:__imp_RtlInitUnicodeString
0x180027d56  lea     r9, [rbp+2A0h+DllHandle]; DllHandle
0x180027d5a  xor     edx, edx; DllCharacteristics
0x180027d5c  lea     r8, [rbp+2A0h+DestinationString]; DllName
0x180027d60  xor     ecx, ecx; DllPath
0x180027d62  call    cs:__imp_LdrGetDllHandle
0x180027d68  test    eax, eax
0x180027d6a  js      loc_180027F90
0x180027d70  xorps   xmm0, xmm0
0x180027d73  lea     rdx, aRtlpctofilehea; "RtlPcToFileHeader"
0x180027d7a  lea     rcx, [rbp+2A0h+Name]; DestinationString
0x180027d7e  movups  xmmword ptr [rbp+2A0h+Name.Length], xmm0
0x180027d82  call    cs:__imp_RtlInitString
0x180027d88  mov     rcx, [rbp+2A0h+DllHandle]; BaseAddress
0x180027d8c  lea     r9, [rbp+2A0h+ProcedureAddress]; ProcedureAddress
0x180027d90  xor     r8d, r8d; Ordinal
0x180027d93  mov     [rbp+2A0h+ProcedureAddress], rsi
0x180027d97  lea     rdx, [rbp+2A0h+Name]; Name
0x180027d9b  call    cs:__imp_LdrGetProcedureAddress
0x180027da1  test    eax, eax
0x180027da3  js      loc_180027F90
0x180027da9  lea     rdx, LibFileName; "ntdll.dll"
0x180027db0  lea     rcx, [rbp+2A0h+DestinationString]; DestinationString
0x180027db4  call    cs:__imp_RtlInitUnicodeString
0x180027dba  lea     r9, [rbp+2A0h+BaseAddress]; DllHandle
0x180027dbe  xor     edx, edx; DllCharacteristics
0x180027dc0  lea     r8, [rbp+2A0h+DestinationString]; DllName
0x180027dc4  xor     ecx, ecx; DllPath
0x180027dc6  call    cs:__imp_LdrGetDllHandle
0x180027dcc  test    eax, eax
0x180027dce  js      loc_180027F90
0x180027dd4  lea     rdx, aLdrgetdllfulln; "LdrGetDllFullName"
0x180027ddb  lea     rcx, [rbp+2A0h+Name]; DestinationString
0x180027ddf  call    cs:__imp_RtlInitString
0x180027de5  mov     rcx, [rbp+2A0h+BaseAddress]; BaseAddress
0x180027de9  lea     r9, [rbp+2A0h+var_2F8]; ProcedureAddress
0x180027ded  xor     r8d, r8d; Ordinal
0x180027df0  mov     [rbp+2A0h+var_2F8], rsi
0x180027df4  lea     rdx, [rbp+2A0h+Name]; Name
0x180027df8  call    cs:__imp_LdrGetProcedureAddress
0x180027dfe  test    eax, eax
0x180027e00  js      loc_180027F90
0x180027e06  mov     rax, [rbp+2A0h+ProcedureAddress]
0x180027e0a  lea     rdx, [rbp+2A0h+var_300]
0x180027e0e  lea     rcx, AslTelemetryCreate
0x180027e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e1a  mov     [rbp+2A0h+var_300], rax
0x180027e1e  mov     rcx, rax
0x180027e21  test    rax, rax
0x180027e24  jz      loc_180027F90
0x180027e2a  lea     rax, [rbp+2A0h+var_240]
0x180027e2e  mov     [rsp+3A0h+var_328], 2060000h
0x180027e37  mov     [rbp+2A0h+var_320], rax
0x180027e3b  lea     rdx, [rsp+3A0h+var_328]
0x180027e40  mov     rax, [rbp+2A0h+var_2F8]
0x180027e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e49  movzx   ecx, word ptr [rsp+3A0h+var_328]
0x180027e4e  shr     ecx, 1
0x180027e50  mov     edx, ecx
0x180027e52  lea     r8, [rcx+rcx]
0x180027e56  cmp     r8, 208h
0x180027e5d  jnb     loc_180027F8A
0x180027e63  mov     [rbp+r8+2A0h+var_240], si
0x180027e69  test    eax, eax
0x180027e6b  js      loc_180027F90
0x180027e71  cmp     edx, 103h
0x180027e77  ja      loc_180027F90
0x180027e7d  xor     r9d, r9d
0x180027e80  lea     rdx, [rsp+3A0h+var_328]
0x180027e85  xor     r8d, r8d
0x180027e88  lea     rcx, [rbp+2A0h+var_240]
0x180027e8c  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x180027e92  test    eax, eax
0x180027e94  js      loc_180027F90
0x180027e9a  mov     [rsp+3A0h+EaLength], esi; EaLength
0x180027e9e  lea     ecx, [rsi+1]
0x180027ea1  mov     [rsp+3A0h+EaBuffer], rsi; EaBuffer
0x180027ea6  lea     rax, [rsp+3A0h+var_328]
0x180027eab  mov     [rsp+3A0h+CreateOptions], 60h ; '`'; CreateOptions
0x180027eb3  lea     r9, [rbp+2A0h+IoStatusBlock]; IoStatusBlock
0x180027eb7  mov     [rsp+3A0h+CreateDisposition], ecx; CreateDisposition
0x180027ebb  lea     r8, [rbp+2A0h+ObjectAttributes]; ObjectAttributes
0x180027ebf  mov     [rsp+3A0h+ShareAccess], ecx; ShareAccess
0x180027ec3  xorps   xmm0, xmm0
0x180027ec6  mov     [rbp+2A0h+ObjectAttributes.ObjectName], rax
0x180027eca  lea     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x180027ecf  lea     rax, [rbp+2A0h+var_280]
0x180027ed3  mov     [rsp+3A0h+FileAttributes], 80h; FileAttributes
0x180027edb  mov     edx, 80100080h; DesiredAccess
0x180027ee0  mov     [rsp+3A0h+AllocationSize], rsi; AllocationSize
0x180027ee5  mov     [rsp+3A0h+FileHandle], rsi
0x180027eea  mov     qword ptr [rbp+2A0h+ObjectAttributes.Length], 30h ; '0'
0x180027ef2  mov     qword ptr [rbp+2A0h+ObjectAttributes.Attributes], 40h ; '@'
0x180027efa  movups  xmmword ptr [rbp+2A0h+IoStatusBlock], xmm0
0x180027efe  mov     [rbp+2A0h+var_278], 101h
0x180027f05  mov     [rbp+2A0h+ObjectAttributes.RootDirectory], rsi
0x180027f09  mov     [rbp+2A0h+ObjectAttributes.SecurityDescriptor], rsi
0x180027f0d  mov     [rbp+2A0h+var_280], 0Ch
0x180027f14  mov     [rbp+2A0h+var_27C], 2
0x180027f1b  mov     [rbp+2A0h+ObjectAttributes.SecurityQualityOfService], rax
0x180027f1f  call    cs:__imp_NtCreateFile
0x180027f25  test    eax, eax
0x180027f27  js      short loc_180027F90
0x180027f29  mov     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x180027f2e  lea     r9d, [rsi+28h]; Length
0x180027f32  xorps   xmm0, xmm0
0x180027f35  mov     [rbp+2A0h+FileInformation], rsi
0x180027f39  lea     r8, [rbp+2A0h+FileInformation]; FileInformation
0x180027f3d  mov     [rbp+2A0h+var_268], rsi
0x180027f41  lea     rdx, [rbp+2A0h+var_290]; IoStatusBlock
0x180027f45  mov     [rbp+2A0h+var_260], rsi
0x180027f49  movups  xmmword ptr [rbp+2A0h+var_290], xmm0
0x180027f4d  mov     dword ptr [rsp+3A0h+AllocationSize], 4; FileInformationClass
0x180027f55  movdqu  [rbp+2A0h+var_258], xmm0
0x180027f5a  call    cs:__imp_NtQueryInformationFile
0x180027f60  mov     rcx, [rsp+3A0h+FileHandle]; Handle
0x180027f65  call    cs:__imp_NtClose
0x180027f6b  mov     eax, 7FFE0014h
0x180027f70  mov     rcx, 0FFFF728E2DA50000h
0x180027f7a  mov     rax, [rax]
0x180027f7d  add     rax, rcx
0x180027f80  cmp     [rbp+2A0h+var_260], rax
0x180027f84  jge     short loc_180027F90
0x180027f86  xor     eax, eax
0x180027f88  jmp     short loc_180028006
0x180027f8a  call    __report_rangecheckfailure
0x180027f90  lea     rdx, aAeinv; "aeinv"
0x180027f97  mov     rcx, rdi
0x180027f9a  call    AslTelemetryCreate
0x180027f9f  mov     ebx, eax
0x180027fa1  test    eax, eax
0x180027fa3  js      short loc_180027FFF
0x180027fa5  lea     r9, [rsp+3A0h+var_334]
0x180027faa  mov     [rsp+3A0h+var_340], esi
0x180027fae  lea     r8, [rsp+3A0h+var_338]
0x180027fb3  mov     [rsp+3A0h+var_33C], esi
0x180027fb7  lea     rdx, [rsp+3A0h+var_33C]
0x180027fbc  mov     [rsp+3A0h+var_338], esi
0x180027fc0  lea     rcx, [rsp+3A0h+var_340]
0x180027fc5  mov     [rsp+3A0h+var_334], esi
0x180027fc9  call    AslFileGetLongVersionForCurrentModule
0x180027fce  mov     r8, [rdi]
0x180027fd1  test    r8, r8
0x180027fd4  jz      short loc_180027FFF
0x180027fd6  mov     ecx, [rsp+3A0h+var_338]
0x180027fda  mov     edx, [rsp+3A0h+var_340]
0x180027fde  mov     eax, [rsp+3A0h+var_33C]
0x180027fe2  shl     rdx, 10h
0x180027fe6  or      rdx, rax
0x180027fe9  shl     rdx, 10h
0x180027fed  or      rdx, rcx
0x180027ff0  mov     ecx, [rsp+3A0h+var_334]
0x180027ff4  shl     rdx, 10h
0x180027ff8  or      rdx, rcx
0x180027ffb  mov     [r8+40h], rdx
0x180027fff  not     ebx
0x180028001  shr     ebx, 1Fh
0x180028004  mov     eax, ebx
0x180028006  mov     rcx, [rbp+2A0h+var_30]
0x18002800d  xor     rcx, rsp; StackCookie
0x180028010  call    __security_check_cookie
0x180028015  add     rsp, 388h
0x18002801c  pop     rdi
0x18002801d  pop     rsi
0x18002801e  pop     rbx
0x18002801f  pop     rbp
0x180028020  retn
```
