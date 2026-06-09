# SdbpCheckMatchingRegistryEntry

- ea: `0x14003136c`
- end: `0x14003154c`
- name: `SdbpCheckMatchingRegistryEntry`
- size: `480`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140031240`

## callees

- `0x14002fef4`
- `0x14003136c`
- `0x140031554`
- `0x14003bf18`
- `0x140045f30`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140031421`
- `ntdll!RtlInitUnicodeString` at `0x140031421`
- `ntdll!ZwOpenKey` at `0x14003145d`
- `ntdll!ZwOpenKey` at `0x1400314c1`
- `ntdll!ZwOpenKey` at `0x14003145d`
- `ntdll!ZwOpenKey` at `0x1400314c1`
- `ntdll!ZwQuerySystemInformation` at `0x140031476`
- `ntdll!ZwQuerySystemInformation` at `0x140031476`
- `ntdll!ZwClose` at `0x14003151d`
- `ntdll!ZwClose` at `0x14003151d`

## string_xrefs

- `0x1400313ca`: `\REGISTRY\MACHINE\%s`
- `0x140031405`: `SdbpCheckMatchingRegistryEntry`
- `0x140031491`: `SdbpCheckMatchingRegistryEntry`
- `0x1400313f8`: `Failed to construct full key path`

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
  NTSTATUS v11; // eax
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
  v11 = ZwQuerySystemInformation(SystemProcessorInformation, &SystemInformation, 0xCu, 0);
  if ( v11 < 0 )
  {
    AslLogCallPrintf(1, "SdbpCheckMatchingRegistryEntry", 1573, "Failed to get processor architecture [%x]", v11);
    goto LABEL_10;
  }
  if ( (_WORD)SystemInformation == 9 && ZwOpenKey(&KeyHandle, 0x20219u, &ObjectAttributes) >= 0 )
LABEL_9:
    v10 = SdbpCheckMatchingRegistryValue(KeyHandle, a2, a5, a6, Buf1, Size, (__int64)a9);
  else
    v10 = 1;
LABEL_10:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return v10;
}

```

## disassembly

```asm
0x14003136c  mov     [rsp-8+arg_10], rsi
0x140031371  push    rbp
0x140031372  push    rdi
0x140031373  push    r12
0x140031375  push    r14
0x140031377  push    r15
0x140031379  lea     rbp, [rsp-1D0h]
0x140031381  sub     rsp, 2D0h
0x140031388  mov     rax, cs:__security_cookie
0x14003138f  xor     rax, rsp
0x140031392  mov     [rbp+1F0h+var_30], rax
0x140031399  mov     rsi, [rbp+1F0h+arg_40]
0x1400313a0  xor     eax, eax
0x1400313a2  xorps   xmm1, xmm1
0x1400313a5  mov     [rbp+1F0h+SourceString], ax
0x1400313a9  mov     r12, r9
0x1400313ac  mov     [rbp+1F0h+SystemInformation], rax
0x1400313b0  mov     r14d, r8d
0x1400313b3  mov     [rbp+1F0h+var_250], eax
0x1400313b6  mov     r15, rdx
0x1400313b9  mov     dword ptr [rsi], 0
0x1400313bf  xorps   xmm0, xmm0
0x1400313c2  mov     [rsp+2F0h+KeyHandle], rax
0x1400313c7  mov     r9, rcx
0x1400313ca  lea     r8, aRegistryMachin_3; "\\REGISTRY\\MACHINE\\%s"
0x1400313d1  mov     edx, 104h
0x1400313d6  lea     rcx, [rbp+1F0h+SourceString]
0x1400313da  xor     edi, edi
0x1400313dc  movups  xmmword ptr [rbp+1F0h+DestinationString.Length], xmm0
0x1400313e0  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.Length], xmm1
0x1400313e5  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.ObjectName], xmm1
0x1400313ea  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400313ef  call    RtlStringCchPrintfW
0x1400313f4  test    eax, eax
0x1400313f6  jns     short loc_140031419
0x1400313f8  lea     r9, aFailedToConstr; "Failed to construct full key path"
0x1400313ff  mov     r8d, 602h
0x140031405  lea     rdx, aSdbpcheckmatch_3; "SdbpCheckMatchingRegistryEntry"
0x14003140c  lea     ecx, [rdi+1]
0x14003140f  call    AslLogCallPrintf
0x140031414  jmp     loc_140031513
0x140031419  lea     rdx, [rbp+1F0h+SourceString]; SourceString
0x14003141d  lea     rcx, [rbp+1F0h+DestinationString]; DestinationString
0x140031421  call    cs:__imp_RtlInitUnicodeString
0x140031427  lea     rax, [rbp+1F0h+DestinationString]
0x14003142b  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x140031433  xorps   xmm0, xmm0
0x140031436  mov     [rsp+2F0h+ObjectAttributes.ObjectName], rax
0x14003143b  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x140031440  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], rdi
0x140031445  mov     edx, 20019h; DesiredAccess
0x14003144a  mov     [rsp+2F0h+ObjectAttributes.Attributes], 40h ; '@'
0x140031452  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x140031457  movdqu  xmmword ptr [rsp+2F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14003145d  call    cs:__imp_ZwOpenKey
0x140031463  test    eax, eax
0x140031465  jns     short loc_1400314CB
0x140031467  xor     r9d, r9d; ReturnLength
0x14003146a  lea     rdx, [rbp+1F0h+SystemInformation]; SystemInformation
0x14003146e  lea     r8d, [r9+0Ch]; SystemInformationLength
0x140031472  lea     ecx, [r9+1]; SystemInformationClass
0x140031476  call    cs:__imp_ZwQuerySystemInformation
0x14003147c  test    eax, eax
0x14003147e  jns     short loc_1400314A4
0x140031480  lea     r9, aFailedToGetPro; "Failed to get processor architecture [%"...
0x140031487  mov     [rsp+2F0h+var_2D0], eax
0x14003148b  mov     r8d, 625h
0x140031491  lea     rdx, aSdbpcheckmatch_3; "SdbpCheckMatchingRegistryEntry"
0x140031498  mov     ecx, 1
0x14003149d  call    AslLogCallPrintf
0x1400314a2  jmp     short loc_140031513
0x1400314a4  cmp     word ptr [rbp+1F0h+SystemInformation], 9
0x1400314a9  jz      short loc_1400314B2
0x1400314ab  mov     edi, 1
0x1400314b0  jmp     short loc_140031513
0x1400314b2  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x1400314b7  mov     edx, 20219h; DesiredAccess
0x1400314bc  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x1400314c1  call    cs:__imp_ZwOpenKey
0x1400314c7  test    eax, eax
0x1400314c9  js      short loc_1400314AB
0x1400314cb  mov     rax, [rbp+1F0h+arg_38]
0x1400314d2  mov     r9, r12
0x1400314d5  mov     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x1400314da  mov     r8d, r14d
0x1400314dd  mov     [rsp+2F0h+var_2B0], rsi; __int64
0x1400314e2  mov     rdx, r15; String1
0x1400314e5  mov     [rsp+2F0h+Size], rax; Size
0x1400314ea  mov     rax, [rbp+1F0h+arg_30]
0x1400314f1  mov     [rsp+2F0h+Buf1], rax; Buf1
0x1400314f6  mov     rax, [rbp+1F0h+arg_28]
0x1400314fd  mov     [rsp+2F0h+var_2C8], rax; __int64
0x140031502  mov     eax, [rbp+1F0h+arg_20]
0x140031508  mov     [rsp+2F0h+var_2D0], eax; int
0x14003150c  call    SdbpCheckMatchingRegistryValue
0x140031511  mov     edi, eax
0x140031513  mov     rcx, [rsp+2F0h+KeyHandle]; Handle
0x140031518  test    rcx, rcx
0x14003151b  jz      short loc_140031523
0x14003151d  call    cs:__imp_ZwClose
0x140031523  mov     eax, edi
0x140031525  mov     rcx, [rbp+1F0h+var_30]
0x14003152c  xor     rcx, rsp; StackCookie
0x14003152f  call    __security_check_cookie
0x140031534  mov     rsi, [rsp+2F0h+arg_10]
0x14003153c  add     rsp, 2D0h
0x140031543  pop     r15
0x140031545  pop     r14
0x140031547  pop     r12
0x140031549  pop     rdi
0x14003154a  pop     rbp
0x14003154b  retn
```
