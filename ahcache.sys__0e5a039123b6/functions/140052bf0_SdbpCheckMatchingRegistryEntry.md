# SdbpCheckMatchingRegistryEntry

- ea: `0x140052bf0`
- end: `0x140052ddf`
- name: `SdbpCheckMatchingRegistryEntry`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140052770`

## callees

- `0x140001ec4`
- `0x14000440f`
- `0x140004469`
- `0x1400044b1`
- `0x1400079f0`
- `0x14003e364`
- `0x140052bf0`
- `0x140052de8`

## import_xrefs

- `ntoskrnl!ZwQuerySystemInformation` at `0x140052ce4`
- `ntoskrnl!ZwQuerySystemInformation` at `0x140052ce4`

## string_xrefs

- `0x140052c54`: `\REGISTRY\MACHINE\%s`
- `0x140052d58`: `SdbpCheckMatchingRegistryEntry`
- `0x140052d7c`: `SdbpCheckMatchingRegistryEntry`
- `0x140052d4b`: `Failed to construct full key path`

## pseudocode

```c
__int64 __fastcall SdbpCheckMatchingRegistryEntry(
        __int64 a1,
        void *a2,
        unsigned int a3,
        void *a4,
        int a5,
        __int64 a6,
        void *a7,
        size_t a8,
        _DWORD *a9)
{
  unsigned int v12; // edi
  NTSTATUS v13; // eax
  __int64 v15; // [rsp+20h] [rbp-E0h]
  void *KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  __int64 SystemInformation; // [rsp+98h] [rbp-68h] BYREF
  int v20; // [rsp+A0h] [rbp-60h]
  wchar_t pszDest[264]; // [rsp+B0h] [rbp-50h] BYREF

  pszDest[0] = 0;
  SystemInformation = 0;
  *a9 = 0;
  v20 = 0;
  KeyHandle = 0;
  v12 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( RtlStringCchPrintfW(pszDest, 0x104u, L"\\REGISTRY\\MACHINE\\%s", a1) < 0 )
  {
    AslLogCallPrintf(1, "SdbpCheckMatchingRegistryEntry", 1538, "Failed to construct full key path");
    goto LABEL_7;
  }
  RtlInitUnicodeString_0(&DestinationString, pszDest);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey_0(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
  {
    v13 = ZwQuerySystemInformation(SystemProcessorInformation, &SystemInformation, 0xCu, 0);
    if ( v13 < 0 )
    {
      AslLogCallPrintf(1, "SdbpCheckMatchingRegistryEntry", 1573, "Failed to get processor architecture [%x]", v13);
      goto LABEL_7;
    }
    if ( (_WORD)SystemInformation != 9 || ZwOpenKey_0(&KeyHandle, 0x20219u, &ObjectAttributes) < 0 )
    {
      v12 = 1;
      goto LABEL_7;
    }
  }
  LODWORD(v15) = a5;
  v12 = SdbpCheckMatchingRegistryValue((__int64)KeyHandle, a2, a3, a4, v15, a6, a7, a8, a9);
LABEL_7:
  if ( KeyHandle )
    ZwClose_0(KeyHandle);
  return v12;
}

```

## disassembly

```asm
0x140052bf0  push    rbp
0x140052bf2  push    rsi
0x140052bf3  push    rdi
0x140052bf4  push    r12
0x140052bf6  push    r13
0x140052bf8  push    r14
0x140052bfa  push    r15
0x140052bfc  lea     rbp, [rsp-1D0h]
0x140052c04  sub     rsp, 2D0h
0x140052c0b  mov     rax, cs:__security_cookie
0x140052c12  xor     rax, rsp
0x140052c15  mov     [rbp+200h+var_40], rax
0x140052c1c  mov     rsi, [rbp+200h+arg_40]
0x140052c23  xor     eax, eax
0x140052c25  mov     r13, [rbp+200h+arg_30]
0x140052c2c  xorps   xmm1, xmm1
0x140052c2f  mov     r12, r9
0x140052c32  mov     [rbp+200h+pszDest], ax
0x140052c36  mov     r14d, r8d
0x140052c39  mov     [rbp+200h+SystemInformation], rax
0x140052c3d  mov     r15, rdx
0x140052c40  mov     dword ptr [rsi], 0
0x140052c46  xorps   xmm0, xmm0
0x140052c49  mov     [rbp+200h+var_260], eax
0x140052c4c  mov     r9, rcx
0x140052c4f  mov     [rsp+300h+KeyHandle], rax
0x140052c54  lea     r8, aRegistryMachin_7; "\\REGISTRY\\MACHINE\\%s"
0x140052c5b  mov     edx, 104h; cchDest
0x140052c60  lea     rcx, [rbp+200h+pszDest]; pszDest
0x140052c64  xor     edi, edi
0x140052c66  movups  xmmword ptr [rbp+200h+DestinationString.Length], xmm0
0x140052c6a  movups  xmmword ptr [rsp+300h+ObjectAttributes.Length], xmm1
0x140052c6f  movups  xmmword ptr [rsp+300h+ObjectAttributes.ObjectName], xmm1
0x140052c74  movups  xmmword ptr [rsp+300h+ObjectAttributes.SecurityDescriptor], xmm1
0x140052c79  call    RtlStringCchPrintfW
0x140052c7e  test    eax, eax
0x140052c80  js      loc_140052D4B
0x140052c86  lea     rdx, [rbp+200h+pszDest]; SourceString
0x140052c8a  lea     rcx, [rbp+200h+DestinationString]; DestinationString
0x140052c8e  call    RtlInitUnicodeString_0
0x140052c93  lea     rax, [rbp+200h+DestinationString]
0x140052c97  mov     [rsp+300h+ObjectAttributes.Length], 30h ; '0'
0x140052c9f  xorps   xmm0, xmm0
0x140052ca2  mov     [rsp+300h+ObjectAttributes.ObjectName], rax
0x140052ca7  lea     r8, [rsp+300h+ObjectAttributes]; ObjectAttributes
0x140052cac  mov     [rsp+300h+ObjectAttributes.RootDirectory], rdi
0x140052cb1  mov     edx, 20019h; DesiredAccess
0x140052cb6  mov     [rsp+300h+ObjectAttributes.Attributes], 240h
0x140052cbe  lea     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x140052cc3  movdqu  xmmword ptr [rsp+300h+ObjectAttributes.SecurityDescriptor], xmm0
0x140052cc9  call    ZwOpenKey_0
0x140052cce  test    eax, eax
0x140052cd0  jns     loc_140052D8F
0x140052cd6  xor     r9d, r9d; ReturnLength
0x140052cd9  lea     r8d, [rdi+0Ch]; SystemInformationLength
0x140052cdd  lea     rdx, [rbp+200h+SystemInformation]; SystemInformation
0x140052ce1  lea     ecx, [rdi+1]; SystemInformationClass
0x140052ce4  call    cs:__imp_ZwQuerySystemInformation
0x140052ceb  nop     dword ptr [rax+rax+00h]
0x140052cf0  test    eax, eax
0x140052cf2  js      short loc_140052D6B
0x140052cf4  cmp     word ptr [rbp+200h+SystemInformation], 9
0x140052cf9  jnz     short loc_140052D13
0x140052cfb  lea     r8, [rsp+300h+ObjectAttributes]; ObjectAttributes
0x140052d00  mov     edx, 20219h; DesiredAccess
0x140052d05  lea     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x140052d0a  call    ZwOpenKey_0
0x140052d0f  test    eax, eax
0x140052d11  jns     short loc_140052D8F
0x140052d13  mov     edi, 1
0x140052d18  mov     rcx, [rsp+300h+KeyHandle]; Handle
0x140052d1d  test    rcx, rcx
0x140052d20  jnz     loc_140052DD5
0x140052d26  mov     eax, edi
0x140052d28  mov     rcx, [rbp+200h+var_40]
0x140052d2f  xor     rcx, rsp; StackCookie
0x140052d32  call    __security_check_cookie
0x140052d37  add     rsp, 2D0h
0x140052d3e  pop     r15
0x140052d40  pop     r14
0x140052d42  pop     r13
0x140052d44  pop     r12
0x140052d46  pop     rdi
0x140052d47  pop     rsi
0x140052d48  pop     rbp
0x140052d49  retn
0x140052d4b  lea     r9, aFailedToConstr; "Failed to construct full key path"
0x140052d52  mov     r8d, 602h
0x140052d58  lea     rdx, aSdbpcheckmatch_4; "SdbpCheckMatchingRegistryEntry"
0x140052d5f  mov     ecx, 1
0x140052d64  call    AslLogCallPrintf
0x140052d69  jmp     short loc_140052D18
0x140052d6b  lea     r9, aFailedToGetPro; "Failed to get processor architecture [%"...
0x140052d72  mov     dword ptr [rsp+300h+var_2E0], eax
0x140052d76  mov     r8d, 625h
0x140052d7c  lea     rdx, aSdbpcheckmatch_4; "SdbpCheckMatchingRegistryEntry"
0x140052d83  mov     ecx, 1
0x140052d88  call    AslLogCallPrintf
0x140052d8d  jmp     short loc_140052D18
0x140052d8f  mov     rax, [rbp+200h+arg_38]
0x140052d96  mov     r9, r12
0x140052d99  mov     rcx, [rsp+300h+KeyHandle]
0x140052d9e  mov     r8d, r14d
0x140052da1  mov     [rsp+300h+var_2C0], rsi
0x140052da6  mov     rdx, r15
0x140052da9  mov     [rsp+300h+var_2C8], rax
0x140052dae  mov     rax, [rbp+200h+arg_28]
0x140052db5  mov     [rsp+300h+var_2D0], r13
0x140052dba  mov     [rsp+300h+var_2D8], rax
0x140052dbf  mov     eax, [rbp+200h+arg_20]
0x140052dc5  mov     dword ptr [rsp+300h+var_2E0], eax
0x140052dc9  call    SdbpCheckMatchingRegistryValue
0x140052dce  mov     edi, eax
0x140052dd0  jmp     loc_140052D18
0x140052dd5  call    ZwClose_0
0x140052dda  jmp     loc_140052D26
```
