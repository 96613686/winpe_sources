# AslTelemetry::Initialize(char const *)

- ea: `0x180014574`
- end: `0x18001488d`
- name: `?Initialize@AslTelemetry@@QEAAHPEBD@Z`
- size: `793`
- prototype: `__int64 __fastcall(AslTelemetry *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180003bd0`

## callees

- `0x180008570`
- `0x180008b20`
- `0x180014574`
- `0x180016170`
- `0x1800174b0`
- `0x18021f010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800145bc`
- `ntdll!RtlInitUnicodeString` at `0x180014620`
- `ntdll!RtlInitUnicodeString` at `0x1800145bc`
- `ntdll!RtlInitUnicodeString` at `0x180014620`
- `ntdll!LdrGetDllHandle` at `0x1800145ce`
- `ntdll!LdrGetDllHandle` at `0x180014632`
- `ntdll!LdrGetDllHandle` at `0x1800145ce`
- `ntdll!LdrGetDllHandle` at `0x180014632`
- `ntdll!RtlInitString` at `0x1800145ee`
- `ntdll!RtlInitString` at `0x18001464b`
- `ntdll!RtlInitString` at `0x1800145ee`
- `ntdll!RtlInitString` at `0x18001464b`
- `ntdll!LdrGetProcedureAddress` at `0x180014607`
- `ntdll!LdrGetProcedureAddress` at `0x180014664`
- `ntdll!LdrGetProcedureAddress` at `0x180014607`
- `ntdll!LdrGetProcedureAddress` at `0x180014664`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1800146f8`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1800146f8`
- `ntdll!NtCreateFile` at `0x18001478b`
- `ntdll!NtCreateFile` at `0x18001478b`
- `ntdll!NtQueryInformationFile` at `0x1800147c6`
- `ntdll!NtQueryInformationFile` at `0x1800147c6`
- `ntdll!NtClose` at `0x1800147d1`
- `ntdll!NtClose` at `0x1800147d1`

## string_xrefs

- `0x180014615`: `ntdll.dll`
- `0x18001459b`: `kernel32.dll`
- `0x180014640`: `LdrGetDllFullName`

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
  v6 = AslTelemetryCreate(this, "Appraiser");
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
0x180014574  push    rbp
0x180014576  push    rbx
0x180014577  push    rsi
0x180014578  push    rdi
0x180014579  lea     rbp, [rsp-288h]
0x180014581  sub     rsp, 388h
0x180014588  mov     rax, cs:__security_cookie
0x18001458f  xor     rax, rsp
0x180014592  mov     [rbp+2A0h+var_30], rax
0x180014599  xor     esi, esi
0x18001459b  lea     rdx, SourceString; "kernel32.dll"
0x1800145a2  mov     rdi, rcx
0x1800145a5  mov     [rbp+2A0h+DllHandle], rsi
0x1800145a9  xorps   xmm0, xmm0
0x1800145ac  mov     [rbp+2A0h+BaseAddress], rsi
0x1800145b0  lea     rcx, [rbp+2A0h+DestinationString]; DestinationString
0x1800145b4  mov     [rbp+2A0h+var_300], rsi
0x1800145b8  movups  xmmword ptr [rbp+2A0h+DestinationString.Length], xmm0
0x1800145bc  call    cs:__imp_RtlInitUnicodeString
0x1800145c2  lea     r9, [rbp+2A0h+DllHandle]; DllHandle
0x1800145c6  xor     edx, edx; DllCharacteristics
0x1800145c8  lea     r8, [rbp+2A0h+DestinationString]; DllName
0x1800145cc  xor     ecx, ecx; DllPath
0x1800145ce  call    cs:__imp_LdrGetDllHandle
0x1800145d4  test    eax, eax
0x1800145d6  js      loc_1800147F6
0x1800145dc  xorps   xmm0, xmm0
0x1800145df  lea     rdx, aRtlpctofilehea; "RtlPcToFileHeader"
0x1800145e6  lea     rcx, [rbp+2A0h+Name]; DestinationString
0x1800145ea  movups  xmmword ptr [rbp+2A0h+Name.Length], xmm0
0x1800145ee  call    cs:__imp_RtlInitString
0x1800145f4  mov     rcx, [rbp+2A0h+DllHandle]; BaseAddress
0x1800145f8  lea     r9, [rbp+2A0h+ProcedureAddress]; ProcedureAddress
0x1800145fc  xor     r8d, r8d; Ordinal
0x1800145ff  mov     [rbp+2A0h+ProcedureAddress], rsi
0x180014603  lea     rdx, [rbp+2A0h+Name]; Name
0x180014607  call    cs:__imp_LdrGetProcedureAddress
0x18001460d  test    eax, eax
0x18001460f  js      loc_1800147F6
0x180014615  lea     rdx, aNtdllDll_2; "ntdll.dll"
0x18001461c  lea     rcx, [rbp+2A0h+DestinationString]; DestinationString
0x180014620  call    cs:__imp_RtlInitUnicodeString
0x180014626  lea     r9, [rbp+2A0h+BaseAddress]; DllHandle
0x18001462a  xor     edx, edx; DllCharacteristics
0x18001462c  lea     r8, [rbp+2A0h+DestinationString]; DllName
0x180014630  xor     ecx, ecx; DllPath
0x180014632  call    cs:__imp_LdrGetDllHandle
0x180014638  test    eax, eax
0x18001463a  js      loc_1800147F6
0x180014640  lea     rdx, aLdrgetdllfulln; "LdrGetDllFullName"
0x180014647  lea     rcx, [rbp+2A0h+Name]; DestinationString
0x18001464b  call    cs:__imp_RtlInitString
0x180014651  mov     rcx, [rbp+2A0h+BaseAddress]; BaseAddress
0x180014655  lea     r9, [rbp+2A0h+var_2F8]; ProcedureAddress
0x180014659  xor     r8d, r8d; Ordinal
0x18001465c  mov     [rbp+2A0h+var_2F8], rsi
0x180014660  lea     rdx, [rbp+2A0h+Name]; Name
0x180014664  call    cs:__imp_LdrGetProcedureAddress
0x18001466a  test    eax, eax
0x18001466c  js      loc_1800147F6
0x180014672  mov     rax, [rbp+2A0h+ProcedureAddress]
0x180014676  lea     rdx, [rbp+2A0h+var_300]
0x18001467a  lea     rcx, AslTelemetryCreate
0x180014681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014686  mov     [rbp+2A0h+var_300], rax
0x18001468a  mov     rcx, rax
0x18001468d  test    rax, rax
0x180014690  jz      loc_1800147F6
0x180014696  lea     rax, [rbp+2A0h+var_240]
0x18001469a  mov     [rsp+3A0h+var_328], 2060000h
0x1800146a3  mov     [rbp+2A0h+var_320], rax
0x1800146a7  lea     rdx, [rsp+3A0h+var_328]
0x1800146ac  mov     rax, [rbp+2A0h+var_2F8]
0x1800146b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146b5  movzx   ecx, word ptr [rsp+3A0h+var_328]
0x1800146ba  shr     ecx, 1
0x1800146bc  mov     edx, ecx
0x1800146be  lea     r8, [rcx+rcx]
0x1800146c2  cmp     r8, 208h
0x1800146c9  jnb     loc_180014887
0x1800146cf  mov     [rbp+r8+2A0h+var_240], si
0x1800146d5  test    eax, eax
0x1800146d7  js      loc_1800147F6
0x1800146dd  cmp     edx, 103h
0x1800146e3  ja      loc_1800147F6
0x1800146e9  xor     r9d, r9d
0x1800146ec  lea     rdx, [rsp+3A0h+var_328]
0x1800146f1  xor     r8d, r8d
0x1800146f4  lea     rcx, [rbp+2A0h+var_240]
0x1800146f8  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x1800146fe  test    eax, eax
0x180014700  js      loc_1800147F6
0x180014706  mov     [rsp+3A0h+EaLength], esi; EaLength
0x18001470a  lea     ecx, [rsi+1]
0x18001470d  mov     [rsp+3A0h+EaBuffer], rsi; EaBuffer
0x180014712  lea     rax, [rsp+3A0h+var_328]
0x180014717  mov     [rsp+3A0h+CreateOptions], 60h ; '`'; CreateOptions
0x18001471f  lea     r9, [rbp+2A0h+IoStatusBlock]; IoStatusBlock
0x180014723  mov     [rsp+3A0h+CreateDisposition], ecx; CreateDisposition
0x180014727  lea     r8, [rbp+2A0h+ObjectAttributes]; ObjectAttributes
0x18001472b  mov     [rsp+3A0h+ShareAccess], ecx; ShareAccess
0x18001472f  xorps   xmm0, xmm0
0x180014732  mov     [rbp+2A0h+ObjectAttributes.ObjectName], rax
0x180014736  lea     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x18001473b  lea     rax, [rbp+2A0h+var_280]
0x18001473f  mov     [rsp+3A0h+FileAttributes], 80h; FileAttributes
0x180014747  mov     edx, 80100080h; DesiredAccess
0x18001474c  mov     [rsp+3A0h+AllocationSize], rsi; AllocationSize
0x180014751  mov     [rsp+3A0h+FileHandle], rsi
0x180014756  mov     qword ptr [rbp+2A0h+ObjectAttributes.Length], 30h ; '0'
0x18001475e  mov     qword ptr [rbp+2A0h+ObjectAttributes.Attributes], 40h ; '@'
0x180014766  movups  xmmword ptr [rbp+2A0h+IoStatusBlock], xmm0
0x18001476a  mov     [rbp+2A0h+var_278], 101h
0x180014771  mov     [rbp+2A0h+ObjectAttributes.RootDirectory], rsi
0x180014775  mov     [rbp+2A0h+ObjectAttributes.SecurityDescriptor], rsi
0x180014779  mov     [rbp+2A0h+var_280], 0Ch
0x180014780  mov     [rbp+2A0h+var_27C], 2
0x180014787  mov     [rbp+2A0h+ObjectAttributes.SecurityQualityOfService], rax
0x18001478b  call    cs:__imp_NtCreateFile
0x180014791  test    eax, eax
0x180014793  js      short loc_1800147F6
0x180014795  mov     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x18001479a  lea     r9d, [rsi+28h]; Length
0x18001479e  xorps   xmm0, xmm0
0x1800147a1  mov     [rbp+2A0h+FileInformation], rsi
0x1800147a5  lea     r8, [rbp+2A0h+FileInformation]; FileInformation
0x1800147a9  mov     [rbp+2A0h+var_268], rsi
0x1800147ad  lea     rdx, [rbp+2A0h+var_290]; IoStatusBlock
0x1800147b1  mov     [rbp+2A0h+var_260], rsi
0x1800147b5  movups  xmmword ptr [rbp+2A0h+var_290], xmm0
0x1800147b9  mov     dword ptr [rsp+3A0h+AllocationSize], 4; FileInformationClass
0x1800147c1  movdqu  [rbp+2A0h+var_258], xmm0
0x1800147c6  call    cs:__imp_NtQueryInformationFile
0x1800147cc  mov     rcx, [rsp+3A0h+FileHandle]; Handle
0x1800147d1  call    cs:__imp_NtClose
0x1800147d7  mov     eax, 7FFE0014h
0x1800147dc  mov     rcx, 0FFFF728E2DA50000h
0x1800147e6  mov     rax, [rax]
0x1800147e9  add     rax, rcx
0x1800147ec  cmp     [rbp+2A0h+var_260], rax
0x1800147f0  jge     short loc_1800147F6
0x1800147f2  xor     eax, eax
0x1800147f4  jmp     short loc_18001486C
0x1800147f6  lea     rdx, aAppraiser; "Appraiser"
0x1800147fd  mov     rcx, rdi
0x180014800  call    AslTelemetryCreate
0x180014805  mov     ebx, eax
0x180014807  test    eax, eax
0x180014809  js      short loc_180014865
0x18001480b  lea     r9, [rsp+3A0h+var_334]
0x180014810  mov     [rsp+3A0h+var_340], esi
0x180014814  lea     r8, [rsp+3A0h+var_338]
0x180014819  mov     [rsp+3A0h+var_33C], esi
0x18001481d  lea     rdx, [rsp+3A0h+var_33C]
0x180014822  mov     [rsp+3A0h+var_338], esi
0x180014826  lea     rcx, [rsp+3A0h+var_340]
0x18001482b  mov     [rsp+3A0h+var_334], esi
0x18001482f  call    AslFileGetLongVersionForCurrentModule
0x180014834  mov     r8, [rdi]
0x180014837  test    r8, r8
0x18001483a  jz      short loc_180014865
0x18001483c  mov     ecx, [rsp+3A0h+var_338]
0x180014840  mov     edx, [rsp+3A0h+var_340]
0x180014844  mov     eax, [rsp+3A0h+var_33C]
0x180014848  shl     rdx, 10h
0x18001484c  or      rdx, rax
0x18001484f  shl     rdx, 10h
0x180014853  or      rdx, rcx
0x180014856  mov     ecx, [rsp+3A0h+var_334]
0x18001485a  shl     rdx, 10h
0x18001485e  or      rdx, rcx
0x180014861  mov     [r8+40h], rdx
0x180014865  not     ebx
0x180014867  shr     ebx, 1Fh
0x18001486a  mov     eax, ebx
0x18001486c  mov     rcx, [rbp+2A0h+var_30]
0x180014873  xor     rcx, rsp; StackCookie
0x180014876  call    __security_check_cookie
0x18001487b  add     rsp, 388h
0x180014882  pop     rdi
0x180014883  pop     rsi
0x180014884  pop     rbx
0x180014885  pop     rbp
0x180014886  retn
0x180014887  call    __report_rangecheckfailure
```
