# SdbpCheckMatchingRegistryEntry

- ea: `0x18002dba4`
- end: `0x18002dd93`
- name: `SdbpCheckMatchingRegistryEntry`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002d740`

## callees

- `0x18000f114`
- `0x1800159e0`
- `0x18002dba4`
- `0x18002dd9c`
- `0x180059270`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18002dc8b`
- `ntdll!RtlInitUnicodeString` at `0x18002dc8b`
- `ntdll!ZwOpenKey` at `0x18002dcc7`
- `ntdll!ZwOpenKey` at `0x18002dd00`
- `ntdll!ZwOpenKey` at `0x18002dcc7`
- `ntdll!ZwOpenKey` at `0x18002dd00`
- `ntdll!ZwQuerySystemInformation` at `0x18002dce0`
- `ntdll!ZwQuerySystemInformation` at `0x18002dce0`
- `ntdll!ZwClose` at `0x18002dd88`
- `ntdll!ZwClose` at `0x18002dd88`

## string_xrefs

- `0x18002dc02`: `\REGISTRY\MACHINE\%s`
- `0x18002dc30`: `Failed to construct full key path`
- `0x18002dc3d`: `SdbpCheckMatchingRegistryEntry`
- `0x18002dd72`: `SdbpCheckMatchingRegistryEntry`

## pseudocode

```c
__int64 __fastcall SdbpCheckMatchingRegistryEntry(
        __int64 a1,
        wchar_t *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        void *Buf1,
        size_t Size,
        _DWORD *a9)
{
  unsigned int v10; // edi
  NTSTATUS v12; // eax
  void *KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  __int64 SystemInformation; // [rsp+98h] [rbp-68h] BYREF
  int v17; // [rsp+A0h] [rbp-60h]
  WCHAR SourceString[264]; // [rsp+B0h] [rbp-50h] BYREF

  SourceString[0] = 0;
  SystemInformation = 0;
  v17 = 0;
  *a9 = 0;
  KeyHandle = 0;
  v10 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( (int)RtlStringCchPrintfW(SourceString, 260, L"\\REGISTRY\\MACHINE\\%s", a1) < 0 )
  {
    AslLogCallPrintf(1, "SdbpCheckMatchingRegistryEntry", 1538, "Failed to construct full key path");
    goto LABEL_3;
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
LABEL_11:
    v10 = SdbpCheckMatchingRegistryValue(KeyHandle, a2, a5, a6, Buf1, Size, (__int64)a9);
    goto LABEL_3;
  }
  v12 = ZwQuerySystemInformation(SystemProcessorInformation, &SystemInformation, 0xCu, 0);
  if ( v12 >= 0 )
  {
    if ( (_WORD)SystemInformation != 9 || ZwOpenKey(&KeyHandle, 0x20219u, &ObjectAttributes) < 0 )
    {
      v10 = 1;
      goto LABEL_3;
    }
    goto LABEL_11;
  }
  AslLogCallPrintf(1, "SdbpCheckMatchingRegistryEntry", 1573, "Failed to get processor architecture [%x]", v12);
LABEL_3:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return v10;
}

```

## disassembly

```asm
0x18002dba4  mov     [rsp-8+arg_10], rsi
0x18002dba9  push    rbp
0x18002dbaa  push    rdi
0x18002dbab  push    r12
0x18002dbad  push    r14
0x18002dbaf  push    r15
0x18002dbb1  lea     rbp, [rsp-1D0h]
0x18002dbb9  sub     rsp, 2D0h
0x18002dbc0  mov     rax, cs:__security_cookie
0x18002dbc7  xor     rax, rsp
0x18002dbca  mov     [rbp+1F0h+var_30], rax
0x18002dbd1  mov     rsi, [rbp+1F0h+arg_40]
0x18002dbd8  xor     eax, eax
0x18002dbda  xorps   xmm1, xmm1
0x18002dbdd  mov     [rbp+1F0h+SourceString], ax
0x18002dbe1  mov     r12, r9
0x18002dbe4  mov     [rbp+1F0h+SystemInformation], rax
0x18002dbe8  mov     r14d, r8d
0x18002dbeb  mov     [rbp+1F0h+var_250], eax
0x18002dbee  mov     r15, rdx
0x18002dbf1  mov     dword ptr [rsi], 0
0x18002dbf7  xorps   xmm0, xmm0
0x18002dbfa  mov     [rsp+2F0h+KeyHandle], rax
0x18002dbff  mov     r9, rcx
0x18002dc02  lea     r8, aRegistryMachin_3; "\\REGISTRY\\MACHINE\\%s"
0x18002dc09  mov     edx, 104h
0x18002dc0e  lea     rcx, [rbp+1F0h+SourceString]
0x18002dc12  xor     edi, edi
0x18002dc14  movups  xmmword ptr [rbp+1F0h+DestinationString.Length], xmm0
0x18002dc18  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.Length], xmm1
0x18002dc1d  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.ObjectName], xmm1
0x18002dc22  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.SecurityDescriptor], xmm1
0x18002dc27  call    RtlStringCchPrintfW
0x18002dc2c  test    eax, eax
0x18002dc2e  jns     short loc_18002DC83
0x18002dc30  lea     r9, aFailedToConstr; "Failed to construct full key path"
0x18002dc37  mov     r8d, 602h
0x18002dc3d  lea     rdx, aSdbpcheckmatch_3; "SdbpCheckMatchingRegistryEntry"
0x18002dc44  lea     ecx, [rdi+1]
0x18002dc47  call    AslLogCallPrintf
0x18002dc4c  mov     rcx, [rsp+2F0h+KeyHandle]; Handle
0x18002dc51  test    rcx, rcx
0x18002dc54  jnz     loc_18002DD88
0x18002dc5a  mov     eax, edi
0x18002dc5c  mov     rcx, [rbp+1F0h+var_30]
0x18002dc63  xor     rcx, rsp; StackCookie
0x18002dc66  call    __security_check_cookie
0x18002dc6b  mov     rsi, [rsp+2F0h+arg_10]
0x18002dc73  add     rsp, 2D0h
0x18002dc7a  pop     r15
0x18002dc7c  pop     r14
0x18002dc7e  pop     r12
0x18002dc80  pop     rdi
0x18002dc81  pop     rbp
0x18002dc82  retn
0x18002dc83  lea     rdx, [rbp+1F0h+SourceString]; SourceString
0x18002dc87  lea     rcx, [rbp+1F0h+DestinationString]; DestinationString
0x18002dc8b  call    cs:__imp_RtlInitUnicodeString
0x18002dc91  lea     rax, [rbp+1F0h+DestinationString]
0x18002dc95  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x18002dc9d  xorps   xmm0, xmm0
0x18002dca0  mov     [rsp+2F0h+ObjectAttributes.ObjectName], rax
0x18002dca5  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x18002dcaa  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], rdi
0x18002dcaf  mov     edx, 20019h; DesiredAccess
0x18002dcb4  mov     [rsp+2F0h+ObjectAttributes.Attributes], 40h ; '@'
0x18002dcbc  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x18002dcc1  movdqu  xmmword ptr [rsp+2F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002dcc7  call    cs:__imp_ZwOpenKey
0x18002dccd  test    eax, eax
0x18002dccf  jns     short loc_18002DD14
0x18002dcd1  xor     r9d, r9d; ReturnLength
0x18002dcd4  lea     rdx, [rbp+1F0h+SystemInformation]; SystemInformation
0x18002dcd8  lea     r8d, [r9+0Ch]; SystemInformationLength
0x18002dcdc  lea     ecx, [r9+1]; SystemInformationClass
0x18002dce0  call    cs:__imp_ZwQuerySystemInformation
0x18002dce6  test    eax, eax
0x18002dce8  js      short loc_18002DD61
0x18002dcea  cmp     word ptr [rbp+1F0h+SystemInformation], 9
0x18002dcef  jnz     short loc_18002DD0A
0x18002dcf1  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x18002dcf6  mov     edx, 20219h; DesiredAccess
0x18002dcfb  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x18002dd00  call    cs:__imp_ZwOpenKey
0x18002dd06  test    eax, eax
0x18002dd08  jns     short loc_18002DD14
0x18002dd0a  mov     edi, 1
0x18002dd0f  jmp     loc_18002DC4C
0x18002dd14  mov     rax, [rbp+1F0h+arg_38]
0x18002dd1b  mov     r9, r12
0x18002dd1e  mov     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x18002dd23  mov     r8d, r14d
0x18002dd26  mov     [rsp+2F0h+var_2B0], rsi; __int64
0x18002dd2b  mov     rdx, r15; String1
0x18002dd2e  mov     [rsp+2F0h+Size], rax; Size
0x18002dd33  mov     rax, [rbp+1F0h+arg_30]
0x18002dd3a  mov     [rsp+2F0h+Buf1], rax; Buf1
0x18002dd3f  mov     rax, [rbp+1F0h+arg_28]
0x18002dd46  mov     [rsp+2F0h+var_2C8], rax; __int64
0x18002dd4b  mov     eax, [rbp+1F0h+arg_20]
0x18002dd51  mov     [rsp+2F0h+var_2D0], eax; int
0x18002dd55  call    SdbpCheckMatchingRegistryValue
0x18002dd5a  mov     edi, eax
0x18002dd5c  jmp     loc_18002DC4C
0x18002dd61  lea     r9, aFailedToGetPro; "Failed to get processor architecture [%"...
0x18002dd68  mov     [rsp+2F0h+var_2D0], eax
0x18002dd6c  mov     r8d, 625h
0x18002dd72  lea     rdx, aSdbpcheckmatch_3; "SdbpCheckMatchingRegistryEntry"
0x18002dd79  mov     ecx, 1
0x18002dd7e  call    AslLogCallPrintf
0x18002dd83  jmp     loc_18002DC4C
0x18002dd88  call    cs:__imp_ZwClose
0x18002dd8e  jmp     loc_18002DC5A
```
