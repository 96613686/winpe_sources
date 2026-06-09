# AslTelemetry::Initialize(char const *)

- ea: `0x18000aaf4`
- end: `0x18000ae0d`
- name: `?Initialize@AslTelemetry@@QEAAHPEBD@Z`
- size: `793`
- prototype: `__int64 __fastcall(AslTelemetry *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001700`

## callees

- `0x180001cf0`
- `0x180002110`
- `0x18000aaf4`
- `0x1800509d0`
- `0x180051904`
- `0x18006a010`

## import_xrefs

- `ntdll!NtClose` at `0x18000ad51`
- `ntdll!NtClose` at `0x18000ad51`
- `ntdll!RtlInitUnicodeString` at `0x18000ab3c`
- `ntdll!RtlInitUnicodeString` at `0x18000aba0`
- `ntdll!RtlInitUnicodeString` at `0x18000ab3c`
- `ntdll!RtlInitUnicodeString` at `0x18000aba0`
- `ntdll!LdrGetDllHandle` at `0x18000ab4e`
- `ntdll!LdrGetDllHandle` at `0x18000abb2`
- `ntdll!LdrGetDllHandle` at `0x18000ab4e`
- `ntdll!LdrGetDllHandle` at `0x18000abb2`
- `ntdll!RtlInitString` at `0x18000ab6e`
- `ntdll!RtlInitString` at `0x18000abcb`
- `ntdll!RtlInitString` at `0x18000ab6e`
- `ntdll!RtlInitString` at `0x18000abcb`
- `ntdll!LdrGetProcedureAddress` at `0x18000ab87`
- `ntdll!LdrGetProcedureAddress` at `0x18000abe4`
- `ntdll!LdrGetProcedureAddress` at `0x18000ab87`
- `ntdll!LdrGetProcedureAddress` at `0x18000abe4`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18000ac78`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18000ac78`
- `ntdll!NtCreateFile` at `0x18000ad0b`
- `ntdll!NtCreateFile` at `0x18000ad0b`
- `ntdll!NtQueryInformationFile` at `0x18000ad46`
- `ntdll!NtQueryInformationFile` at `0x18000ad46`

## string_xrefs

- `0x18000ab95`: `ntdll.dll`
- `0x18000ab1b`: `kernel32.dll`
- `0x18000abc0`: `LdrGetDllFullName`

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
  v6 = AslTelemetryCreate(this, "acmigration");
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
0x18000aaf4  push    rbp
0x18000aaf6  push    rbx
0x18000aaf7  push    rsi
0x18000aaf8  push    rdi
0x18000aaf9  lea     rbp, [rsp-288h]
0x18000ab01  sub     rsp, 388h
0x18000ab08  mov     rax, cs:__security_cookie
0x18000ab0f  xor     rax, rsp
0x18000ab12  mov     [rbp+2A0h+var_30], rax
0x18000ab19  xor     esi, esi
0x18000ab1b  lea     rdx, SourceString; "kernel32.dll"
0x18000ab22  mov     rdi, rcx
0x18000ab25  mov     [rbp+2A0h+DllHandle], rsi
0x18000ab29  xorps   xmm0, xmm0
0x18000ab2c  mov     [rbp+2A0h+BaseAddress], rsi
0x18000ab30  lea     rcx, [rbp+2A0h+DestinationString]; DestinationString
0x18000ab34  mov     [rbp+2A0h+var_300], rsi
0x18000ab38  movups  xmmword ptr [rbp+2A0h+DestinationString.Length], xmm0
0x18000ab3c  call    cs:__imp_RtlInitUnicodeString
0x18000ab42  lea     r9, [rbp+2A0h+DllHandle]; DllHandle
0x18000ab46  xor     edx, edx; DllCharacteristics
0x18000ab48  lea     r8, [rbp+2A0h+DestinationString]; DllName
0x18000ab4c  xor     ecx, ecx; DllPath
0x18000ab4e  call    cs:__imp_LdrGetDllHandle
0x18000ab54  test    eax, eax
0x18000ab56  js      loc_18000AD76
0x18000ab5c  xorps   xmm0, xmm0
0x18000ab5f  lea     rdx, aRtlpctofilehea; "RtlPcToFileHeader"
0x18000ab66  lea     rcx, [rbp+2A0h+Name]; DestinationString
0x18000ab6a  movups  xmmword ptr [rbp+2A0h+Name.Length], xmm0
0x18000ab6e  call    cs:__imp_RtlInitString
0x18000ab74  mov     rcx, [rbp+2A0h+DllHandle]; BaseAddress
0x18000ab78  lea     r9, [rbp+2A0h+ProcedureAddress]; ProcedureAddress
0x18000ab7c  xor     r8d, r8d; Ordinal
0x18000ab7f  mov     [rbp+2A0h+ProcedureAddress], rsi
0x18000ab83  lea     rdx, [rbp+2A0h+Name]; Name
0x18000ab87  call    cs:__imp_LdrGetProcedureAddress
0x18000ab8d  test    eax, eax
0x18000ab8f  js      loc_18000AD76
0x18000ab95  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18000ab9c  lea     rcx, [rbp+2A0h+DestinationString]; DestinationString
0x18000aba0  call    cs:__imp_RtlInitUnicodeString
0x18000aba6  lea     r9, [rbp+2A0h+BaseAddress]; DllHandle
0x18000abaa  xor     edx, edx; DllCharacteristics
0x18000abac  lea     r8, [rbp+2A0h+DestinationString]; DllName
0x18000abb0  xor     ecx, ecx; DllPath
0x18000abb2  call    cs:__imp_LdrGetDllHandle
0x18000abb8  test    eax, eax
0x18000abba  js      loc_18000AD76
0x18000abc0  lea     rdx, aLdrgetdllfulln; "LdrGetDllFullName"
0x18000abc7  lea     rcx, [rbp+2A0h+Name]; DestinationString
0x18000abcb  call    cs:__imp_RtlInitString
0x18000abd1  mov     rcx, [rbp+2A0h+BaseAddress]; BaseAddress
0x18000abd5  lea     r9, [rbp+2A0h+var_2F8]; ProcedureAddress
0x18000abd9  xor     r8d, r8d; Ordinal
0x18000abdc  mov     [rbp+2A0h+var_2F8], rsi
0x18000abe0  lea     rdx, [rbp+2A0h+Name]; Name
0x18000abe4  call    cs:__imp_LdrGetProcedureAddress
0x18000abea  test    eax, eax
0x18000abec  js      loc_18000AD76
0x18000abf2  mov     rax, [rbp+2A0h+ProcedureAddress]
0x18000abf6  lea     rdx, [rbp+2A0h+var_300]
0x18000abfa  lea     rcx, AslTelemetryCreate
0x18000ac01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac06  mov     [rbp+2A0h+var_300], rax
0x18000ac0a  mov     rcx, rax
0x18000ac0d  test    rax, rax
0x18000ac10  jz      loc_18000AD76
0x18000ac16  lea     rax, [rbp+2A0h+var_240]
0x18000ac1a  mov     [rsp+3A0h+var_328], 2060000h
0x18000ac23  mov     [rbp+2A0h+var_320], rax
0x18000ac27  lea     rdx, [rsp+3A0h+var_328]
0x18000ac2c  mov     rax, [rbp+2A0h+var_2F8]
0x18000ac30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac35  movzx   ecx, word ptr [rsp+3A0h+var_328]
0x18000ac3a  shr     ecx, 1
0x18000ac3c  mov     edx, ecx
0x18000ac3e  lea     r8, [rcx+rcx]
0x18000ac42  cmp     r8, 208h
0x18000ac49  jnb     loc_18000AE07
0x18000ac4f  mov     [rbp+r8+2A0h+var_240], si
0x18000ac55  test    eax, eax
0x18000ac57  js      loc_18000AD76
0x18000ac5d  cmp     edx, 103h
0x18000ac63  ja      loc_18000AD76
0x18000ac69  xor     r9d, r9d
0x18000ac6c  lea     rdx, [rsp+3A0h+var_328]
0x18000ac71  xor     r8d, r8d
0x18000ac74  lea     rcx, [rbp+2A0h+var_240]
0x18000ac78  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x18000ac7e  test    eax, eax
0x18000ac80  js      loc_18000AD76
0x18000ac86  mov     [rsp+3A0h+EaLength], esi; EaLength
0x18000ac8a  lea     ecx, [rsi+1]
0x18000ac8d  mov     [rsp+3A0h+EaBuffer], rsi; EaBuffer
0x18000ac92  lea     rax, [rsp+3A0h+var_328]
0x18000ac97  mov     [rsp+3A0h+CreateOptions], 60h ; '`'; CreateOptions
0x18000ac9f  lea     r9, [rbp+2A0h+IoStatusBlock]; IoStatusBlock
0x18000aca3  mov     [rsp+3A0h+CreateDisposition], ecx; CreateDisposition
0x18000aca7  lea     r8, [rbp+2A0h+ObjectAttributes]; ObjectAttributes
0x18000acab  mov     [rsp+3A0h+ShareAccess], ecx; ShareAccess
0x18000acaf  xorps   xmm0, xmm0
0x18000acb2  mov     [rbp+2A0h+ObjectAttributes.ObjectName], rax
0x18000acb6  lea     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x18000acbb  lea     rax, [rbp+2A0h+var_280]
0x18000acbf  mov     [rsp+3A0h+FileAttributes], 80h; FileAttributes
0x18000acc7  mov     edx, 80100080h; DesiredAccess
0x18000accc  mov     [rsp+3A0h+AllocationSize], rsi; AllocationSize
0x18000acd1  mov     [rsp+3A0h+FileHandle], rsi
0x18000acd6  mov     qword ptr [rbp+2A0h+ObjectAttributes.Length], 30h ; '0'
0x18000acde  mov     qword ptr [rbp+2A0h+ObjectAttributes.Attributes], 40h ; '@'
0x18000ace6  movups  xmmword ptr [rbp+2A0h+IoStatusBlock], xmm0
0x18000acea  mov     [rbp+2A0h+var_278], 101h
0x18000acf1  mov     [rbp+2A0h+ObjectAttributes.RootDirectory], rsi
0x18000acf5  mov     [rbp+2A0h+ObjectAttributes.SecurityDescriptor], rsi
0x18000acf9  mov     [rbp+2A0h+var_280], 0Ch
0x18000ad00  mov     [rbp+2A0h+var_27C], 2
0x18000ad07  mov     [rbp+2A0h+ObjectAttributes.SecurityQualityOfService], rax
0x18000ad0b  call    cs:__imp_NtCreateFile
0x18000ad11  test    eax, eax
0x18000ad13  js      short loc_18000AD76
0x18000ad15  mov     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x18000ad1a  lea     r9d, [rsi+28h]; Length
0x18000ad1e  xorps   xmm0, xmm0
0x18000ad21  mov     [rbp+2A0h+FileInformation], rsi
0x18000ad25  lea     r8, [rbp+2A0h+FileInformation]; FileInformation
0x18000ad29  mov     [rbp+2A0h+var_268], rsi
0x18000ad2d  lea     rdx, [rbp+2A0h+var_290]; IoStatusBlock
0x18000ad31  mov     [rbp+2A0h+var_260], rsi
0x18000ad35  movups  xmmword ptr [rbp+2A0h+var_290], xmm0
0x18000ad39  mov     dword ptr [rsp+3A0h+AllocationSize], 4; FileInformationClass
0x18000ad41  movdqu  [rbp+2A0h+var_258], xmm0
0x18000ad46  call    cs:__imp_NtQueryInformationFile
0x18000ad4c  mov     rcx, [rsp+3A0h+FileHandle]; Handle
0x18000ad51  call    cs:__imp_NtClose
0x18000ad57  mov     eax, 7FFE0014h
0x18000ad5c  mov     rcx, 0FFFF728E2DA50000h
0x18000ad66  mov     rax, [rax]
0x18000ad69  add     rax, rcx
0x18000ad6c  cmp     [rbp+2A0h+var_260], rax
0x18000ad70  jge     short loc_18000AD76
0x18000ad72  xor     eax, eax
0x18000ad74  jmp     short loc_18000ADEC
0x18000ad76  lea     rdx, aAcmigration; "acmigration"
0x18000ad7d  mov     rcx, rdi
0x18000ad80  call    AslTelemetryCreate
0x18000ad85  mov     ebx, eax
0x18000ad87  test    eax, eax
0x18000ad89  js      short loc_18000ADE5
0x18000ad8b  lea     r9, [rsp+3A0h+var_334]
0x18000ad90  mov     [rsp+3A0h+var_340], esi
0x18000ad94  lea     r8, [rsp+3A0h+var_338]
0x18000ad99  mov     [rsp+3A0h+var_33C], esi
0x18000ad9d  lea     rdx, [rsp+3A0h+var_33C]
0x18000ada2  mov     [rsp+3A0h+var_338], esi
0x18000ada6  lea     rcx, [rsp+3A0h+var_340]
0x18000adab  mov     [rsp+3A0h+var_334], esi
0x18000adaf  call    AslFileGetLongVersionForCurrentModule
0x18000adb4  mov     r8, [rdi]
0x18000adb7  test    r8, r8
0x18000adba  jz      short loc_18000ADE5
0x18000adbc  mov     ecx, [rsp+3A0h+var_338]
0x18000adc0  mov     edx, [rsp+3A0h+var_340]
0x18000adc4  mov     eax, [rsp+3A0h+var_33C]
0x18000adc8  shl     rdx, 10h
0x18000adcc  or      rdx, rax
0x18000adcf  shl     rdx, 10h
0x18000add3  or      rdx, rcx
0x18000add6  mov     ecx, [rsp+3A0h+var_334]
0x18000adda  shl     rdx, 10h
0x18000adde  or      rdx, rcx
0x18000ade1  mov     [r8+40h], rdx
0x18000ade5  not     ebx
0x18000ade7  shr     ebx, 1Fh
0x18000adea  mov     eax, ebx
0x18000adec  mov     rcx, [rbp+2A0h+var_30]
0x18000adf3  xor     rcx, rsp; StackCookie
0x18000adf6  call    __security_check_cookie
0x18000adfb  add     rsp, 388h
0x18000ae02  pop     rdi
0x18000ae03  pop     rsi
0x18000ae04  pop     rbx
0x18000ae05  pop     rbp
0x18000ae06  retn
0x18000ae07  call    __report_rangecheckfailure
```
