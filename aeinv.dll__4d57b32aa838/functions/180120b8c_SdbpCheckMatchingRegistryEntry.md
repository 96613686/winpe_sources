# SdbpCheckMatchingRegistryEntry

- ea: `0x180120b8c`
- end: `0x180120d6c`
- name: `SdbpCheckMatchingRegistryEntry`
- size: `480`
- prototype: `__int64 __fastcall(__int64, wchar_t *, int, __int64, int, __int64, void *Buf1, size_t Size, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180120a60`

## callees

- `0x1800197d4`
- `0x18001b8ac`
- `0x180059920`
- `0x180120b8c`
- `0x180120d74`

## import_xrefs

- `ntdll!ZwQuerySystemInformation` at `0x180120c96`
- `ntdll!ZwQuerySystemInformation` at `0x180120c96`
- `ntdll!ZwClose` at `0x180120d3d`
- `ntdll!ZwClose` at `0x180120d3d`
- `ntdll!RtlInitUnicodeString` at `0x180120c41`
- `ntdll!RtlInitUnicodeString` at `0x180120c41`
- `ntdll!ZwOpenKey` at `0x180120c7d`
- `ntdll!ZwOpenKey` at `0x180120ce1`
- `ntdll!ZwOpenKey` at `0x180120c7d`
- `ntdll!ZwOpenKey` at `0x180120ce1`

## string_xrefs

- `0x180120c25`: `SdbpCheckMatchingRegistryEntry`
- `0x180120cb1`: `SdbpCheckMatchingRegistryEntry`
- `0x180120bea`: `\REGISTRY\MACHINE\%s`
- `0x180120c18`: `Failed to construct full key path`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SdbpCheckMatchingRegistryEntry(
        __int64 a1,
        wchar_t *a2,
        int a3,
        __int64 a4,
        int a5,
        __int64 a6,
        void *Buf1,
        size_t Size,
        _DWORD *a9)
{
  unsigned int v12; // edi
  void *KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  __int64 SystemInformation; // [rsp+98h] [rbp-68h] BYREF
  int v18; // [rsp+A0h] [rbp-60h]
  WCHAR SourceString[264]; // [rsp+B0h] [rbp-50h] BYREF

  SourceString[0] = 0;
  SystemInformation = 0;
  v18 = 0;
  *a9 = 0;
  KeyHandle = 0;
  v12 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( (int)RtlStringCchPrintfW(SourceString, 260, L"\\REGISTRY\\MACHINE\\%s", a1) < 0 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpCheckMatchingRegistryEntry",
      1538,
      (unsigned int)"Failed to construct full key path");
    goto LABEL_10;
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
    goto LABEL_9;
  if ( ZwQuerySystemInformation(SystemProcessorInformation, &SystemInformation, 0xCu, 0) < 0 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpCheckMatchingRegistryEntry",
      1573,
      (unsigned int)"Failed to get processor architecture [%x]");
    goto LABEL_10;
  }
  if ( (_WORD)SystemInformation == 9 && ZwOpenKey(&KeyHandle, 0x20219u, &ObjectAttributes) >= 0 )
LABEL_9:
    v12 = SdbpCheckMatchingRegistryValue(KeyHandle, a2, a3, a4, a5, a6, Buf1, Size, a9);
  else
    v12 = 1;
LABEL_10:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return v12;
}

```

## disassembly

```asm
0x180120b8c  mov     [rsp-8+arg_10], rsi
0x180120b91  push    rbp
0x180120b92  push    rdi
0x180120b93  push    r12
0x180120b95  push    r14
0x180120b97  push    r15
0x180120b99  lea     rbp, [rsp-1D0h]
0x180120ba1  sub     rsp, 2D0h
0x180120ba8  mov     rax, cs:__security_cookie
0x180120baf  xor     rax, rsp
0x180120bb2  mov     [rbp+1F0h+var_30], rax
0x180120bb9  mov     rsi, [rbp+1F0h+arg_40]
0x180120bc0  xor     eax, eax
0x180120bc2  xorps   xmm1, xmm1
0x180120bc5  mov     [rbp+1F0h+SourceString], ax
0x180120bc9  mov     r12, r9
0x180120bcc  mov     [rbp+1F0h+SystemInformation], rax
0x180120bd0  mov     r14d, r8d
0x180120bd3  mov     [rbp+1F0h+var_250], eax
0x180120bd6  mov     r15, rdx
0x180120bd9  mov     dword ptr [rsi], 0
0x180120bdf  xorps   xmm0, xmm0
0x180120be2  mov     [rsp+2F0h+KeyHandle], rax
0x180120be7  mov     r9, rcx
0x180120bea  lea     r8, aRegistryMachin_3; "\\REGISTRY\\MACHINE\\%s"
0x180120bf1  mov     edx, 104h
0x180120bf6  lea     rcx, [rbp+1F0h+SourceString]
0x180120bfa  xor     edi, edi
0x180120bfc  movups  xmmword ptr [rbp+1F0h+DestinationString.Length], xmm0
0x180120c00  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.Length], xmm1
0x180120c05  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.ObjectName], xmm1
0x180120c0a  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.SecurityDescriptor], xmm1
0x180120c0f  call    RtlStringCchPrintfW
0x180120c14  test    eax, eax
0x180120c16  jns     short loc_180120C39
0x180120c18  lea     r9, aFailedToConstr; "Failed to construct full key path"
0x180120c1f  mov     r8d, 602h
0x180120c25  lea     rdx, aSdbpcheckmatch_3; "SdbpCheckMatchingRegistryEntry"
0x180120c2c  lea     ecx, [rdi+1]
0x180120c2f  call    AslLogCallPrintf
0x180120c34  jmp     loc_180120D33
0x180120c39  lea     rdx, [rbp+1F0h+SourceString]; SourceString
0x180120c3d  lea     rcx, [rbp+1F0h+DestinationString]; DestinationString
0x180120c41  call    cs:__imp_RtlInitUnicodeString
0x180120c47  lea     rax, [rbp+1F0h+DestinationString]
0x180120c4b  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x180120c53  xorps   xmm0, xmm0
0x180120c56  mov     [rsp+2F0h+ObjectAttributes.ObjectName], rax
0x180120c5b  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x180120c60  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], rdi
0x180120c65  mov     edx, 20019h; DesiredAccess
0x180120c6a  mov     [rsp+2F0h+ObjectAttributes.Attributes], 40h ; '@'
0x180120c72  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x180120c77  movdqu  xmmword ptr [rsp+2F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180120c7d  call    cs:__imp_ZwOpenKey
0x180120c83  test    eax, eax
0x180120c85  jns     short loc_180120CEB
0x180120c87  xor     r9d, r9d; ReturnLength
0x180120c8a  lea     rdx, [rbp+1F0h+SystemInformation]; SystemInformation
0x180120c8e  lea     r8d, [r9+0Ch]; SystemInformationLength
0x180120c92  lea     ecx, [r9+1]; SystemInformationClass
0x180120c96  call    cs:__imp_ZwQuerySystemInformation
0x180120c9c  test    eax, eax
0x180120c9e  jns     short loc_180120CC4
0x180120ca0  lea     r9, aFailedToGetPro; "Failed to get processor architecture [%"...
0x180120ca7  mov     [rsp+2F0h+var_2D0], eax
0x180120cab  mov     r8d, 625h
0x180120cb1  lea     rdx, aSdbpcheckmatch_3; "SdbpCheckMatchingRegistryEntry"
0x180120cb8  mov     ecx, 1
0x180120cbd  call    AslLogCallPrintf
0x180120cc2  jmp     short loc_180120D33
0x180120cc4  cmp     word ptr [rbp+1F0h+SystemInformation], 9
0x180120cc9  jz      short loc_180120CD2
0x180120ccb  mov     edi, 1
0x180120cd0  jmp     short loc_180120D33
0x180120cd2  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x180120cd7  mov     edx, 20219h; DesiredAccess
0x180120cdc  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x180120ce1  call    cs:__imp_ZwOpenKey
0x180120ce7  test    eax, eax
0x180120ce9  js      short loc_180120CCB
0x180120ceb  mov     rax, [rbp+1F0h+arg_38]
0x180120cf2  mov     r9, r12
0x180120cf5  mov     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x180120cfa  mov     r8d, r14d
0x180120cfd  mov     [rsp+2F0h+var_2B0], rsi; __int64
0x180120d02  mov     rdx, r15; String1
0x180120d05  mov     [rsp+2F0h+Size], rax; Size
0x180120d0a  mov     rax, [rbp+1F0h+arg_30]
0x180120d11  mov     [rsp+2F0h+Buf1], rax; Buf1
0x180120d16  mov     rax, [rbp+1F0h+arg_28]
0x180120d1d  mov     [rsp+2F0h+var_2C8], rax; __int64
0x180120d22  mov     eax, [rbp+1F0h+arg_20]
0x180120d28  mov     [rsp+2F0h+var_2D0], eax; int
0x180120d2c  call    SdbpCheckMatchingRegistryValue
0x180120d31  mov     edi, eax
0x180120d33  mov     rcx, [rsp+2F0h+KeyHandle]; Handle
0x180120d38  test    rcx, rcx
0x180120d3b  jz      short loc_180120D43
0x180120d3d  call    cs:__imp_ZwClose
0x180120d43  mov     eax, edi
0x180120d45  mov     rcx, [rbp+1F0h+var_30]
0x180120d4c  xor     rcx, rsp; StackCookie
0x180120d4f  call    __security_check_cookie
0x180120d54  mov     rsi, [rsp+2F0h+arg_10]
0x180120d5c  add     rsp, 2D0h
0x180120d63  pop     r15
0x180120d65  pop     r14
0x180120d67  pop     r12
0x180120d69  pop     rdi
0x180120d6a  pop     rbp
0x180120d6b  retn
```
