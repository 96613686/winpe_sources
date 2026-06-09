# SdbUnregisterDatabase

- ea: `0x180061b4c`
- end: `0x180061d09`
- name: `SdbUnregisterDatabase`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800392b4`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x1800543c0`
- `0x18005453c`
- `0x1800546b8`
- `0x180061b4c`

## import_xrefs

- `ntdll!NtClose` at `0x180061ce6`
- `ntdll!NtClose` at `0x180061ce6`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180061c25`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180061c25`
- `ntdll!RtlAppendUnicodeToString` at `0x180061c03`
- `ntdll!RtlAppendUnicodeToString` at `0x180061c15`
- `ntdll!RtlAppendUnicodeToString` at `0x180061c03`
- `ntdll!RtlAppendUnicodeToString` at `0x180061c15`
- `ntdll!NtOpenKey` at `0x180061c6c`
- `ntdll!NtOpenKey` at `0x180061c6c`
- `ntdll!NtDeleteKey` at `0x180061cbe`
- `ntdll!NtDeleteKey` at `0x180061cbe`

## string_xrefs

- `0x180061c8b`: `Failed to open key "%ws" [%x]`
- `0x180061bf2`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\InstalledSDB`
- `0x180061cc8`: `Failed to delete key "%ws" [%x]`

## pseudocode

```c
__int64 __fastcall SdbUnregisterDatabase(__int64 a1)
{
  unsigned int v2; // edi
  int v3; // eax
  NTSTATUS v4; // eax
  const char *v5; // r9
  __int64 v6; // r8
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+40h] [rbp-C0h] BYREF
  UNICODE_STRING Source; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v12[528]; // [rsp+90h] [rbp-70h] BYREF

  Destination = 0;
  v2 = 0;
  Source = 0;
  memset_0(v12, 0, 0x208u);
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  v3 = AslGuidToString_UStr(&Source, a1);
  if ( v3 < 0 )
  {
    AslLogCallPrintf(1, "SdbUnregisterDatabase", 1259, "Cannot convert guid to unicode string [%x]", v3);
    goto LABEL_12;
  }
  *(_DWORD *)&Destination.Length = 34078720;
  Destination.Buffer = (PWSTR)v12;
  RtlAppendUnicodeToString(
    &Destination,
    L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\InstalledSDB");
  RtlAppendUnicodeToString(&Destination, L"\\");
  RtlAppendUnicodeStringToString(&Destination, &Source);
  AslAnsiStringFree(&Source);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &Destination;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = NtOpenKey(&KeyHandle, 0x10100u, &ObjectAttributes);
  if ( v4 < 0 && v4 != -1073741766 && v4 != -1073741772 && v4 != -1073741620 )
  {
    v5 = "Failed to open key \"%ws\" [%x]";
    v6 = 1288;
LABEL_8:
    AslLogCallPrintf(1, "SdbUnregisterDatabase", v6, v5, Destination.Buffer, v4);
    goto LABEL_12;
  }
  v4 = NtDeleteKey(KeyHandle);
  if ( v4 < 0 )
  {
    v5 = "Failed to delete key \"%ws\" [%x]";
    v6 = 1298;
    goto LABEL_8;
  }
  v2 = 1;
LABEL_12:
  if ( KeyHandle )
    NtClose(KeyHandle);
  return v2;
}

```

## disassembly

```asm
0x180061b4c  push    rbp
0x180061b4e  push    rbx
0x180061b4f  push    rsi
0x180061b50  push    rdi
0x180061b51  lea     rbp, [rsp-1B8h]
0x180061b59  sub     rsp, 2B8h
0x180061b60  mov     rax, cs:__security_cookie
0x180061b67  xor     rax, rsp
0x180061b6a  mov     [rbp+1D0h+var_30], rax
0x180061b71  mov     rbx, rcx
0x180061b74  xorps   xmm0, xmm0
0x180061b77  xorps   xmm1, xmm1
0x180061b7a  lea     rcx, [rbp+1D0h+var_240]; void *
0x180061b7e  xor     edx, edx; Val
0x180061b80  mov     r8d, 208h; Size
0x180061b86  movups  xmmword ptr [rsp+2D0h+Destination.Length], xmm0
0x180061b8b  xor     edi, edi
0x180061b8d  movups  xmmword ptr [rsp+2D0h+Source.Length], xmm1
0x180061b92  call    memset_0
0x180061b97  xorps   xmm0, xmm0
0x180061b9a  mov     [rsp+2D0h+KeyHandle], rdi
0x180061b9f  movups  xmmword ptr [rsp+2D0h+ObjectAttributes.ObjectName], xmm0
0x180061ba4  xor     eax, eax
0x180061ba6  lea     rcx, [rsp+2D0h+Source]
0x180061bab  mov     rdx, rbx
0x180061bae  movups  xmmword ptr [rsp+2D0h+ObjectAttributes+1Ch], xmm0
0x180061bb3  movups  xmmword ptr [rsp+2D0h+ObjectAttributes.Length], xmm0
0x180061bb8  call    AslGuidToString_UStr
0x180061bbd  test    eax, eax
0x180061bbf  jns     short loc_180061BE6
0x180061bc1  lea     r9, aCannotConvertG; "Cannot convert guid to unicode string ["...
0x180061bc8  mov     dword ptr [rsp+2D0h+var_2B0], eax
0x180061bcc  mov     r8d, 4EBh
0x180061bd2  lea     rdx, aSdbunregisterd; "SdbUnregisterDatabase"
0x180061bd9  lea     ecx, [rdi+1]
0x180061bdc  call    AslLogCallPrintf
0x180061be1  jmp     loc_180061CDC
0x180061be6  lea     rax, [rbp+1D0h+var_240]
0x180061bea  mov     dword ptr [rsp+2D0h+Destination.Length], 2080000h
0x180061bf2  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\Software\\Microsof"...
0x180061bf9  mov     [rsp+2D0h+Destination.Buffer], rax
0x180061bfe  lea     rcx, [rsp+2D0h+Destination]; Destination
0x180061c03  call    cs:__imp_RtlAppendUnicodeToString
0x180061c09  lea     rdx, asc_18006E074; "\\"
0x180061c10  lea     rcx, [rsp+2D0h+Destination]; Destination
0x180061c15  call    cs:__imp_RtlAppendUnicodeToString
0x180061c1b  lea     rdx, [rsp+2D0h+Source]; Source
0x180061c20  lea     rcx, [rsp+2D0h+Destination]; Destination
0x180061c25  call    cs:__imp_RtlAppendUnicodeStringToString
0x180061c2b  lea     rcx, [rsp+2D0h+Source]
0x180061c30  call    AslAnsiStringFree
0x180061c35  lea     rax, [rsp+2D0h+Destination]
0x180061c3a  mov     [rsp+2D0h+ObjectAttributes.Length], 30h ; '0'
0x180061c42  xorps   xmm0, xmm0
0x180061c45  mov     [rsp+2D0h+ObjectAttributes.ObjectName], rax
0x180061c4a  lea     r8, [rsp+2D0h+ObjectAttributes]; ObjectAttributes
0x180061c4f  mov     [rsp+2D0h+ObjectAttributes.RootDirectory], rdi
0x180061c54  mov     edx, 10100h; DesiredAccess
0x180061c59  mov     [rsp+2D0h+ObjectAttributes.Attributes], 40h ; '@'
0x180061c61  lea     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x180061c66  movdqu  xmmword ptr [rsp+2D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180061c6c  call    cs:__imp_NtOpenKey
0x180061c72  test    eax, eax
0x180061c74  jns     short loc_180061CB9
0x180061c76  cmp     eax, 0C000003Ah
0x180061c7b  jz      short loc_180061CB9
0x180061c7d  cmp     eax, 0C0000034h
0x180061c82  jz      short loc_180061CB9
0x180061c84  cmp     eax, 0C00000CCh
0x180061c89  jz      short loc_180061CB9
0x180061c8b  lea     r9, aFailedToOpenKe; "Failed to open key \"%ws\" [%x]"
0x180061c92  mov     r8d, 508h
0x180061c98  mov     [rsp+2D0h+var_2A8], eax
0x180061c9c  lea     rdx, aSdbunregisterd; "SdbUnregisterDatabase"
0x180061ca3  mov     rax, [rsp+2D0h+Destination.Buffer]
0x180061ca8  mov     ecx, 1
0x180061cad  mov     [rsp+2D0h+var_2B0], rax
0x180061cb2  call    AslLogCallPrintf
0x180061cb7  jmp     short loc_180061CDC
0x180061cb9  mov     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x180061cbe  call    cs:__imp_NtDeleteKey
0x180061cc4  test    eax, eax
0x180061cc6  jns     short loc_180061CD7
0x180061cc8  lea     r9, aFailedToDelete; "Failed to delete key \"%ws\" [%x]"
0x180061ccf  mov     r8d, 512h
0x180061cd5  jmp     short loc_180061C98
0x180061cd7  mov     edi, 1
0x180061cdc  mov     rcx, [rsp+2D0h+KeyHandle]; Handle
0x180061ce1  test    rcx, rcx
0x180061ce4  jz      short loc_180061CEC
0x180061ce6  call    cs:__imp_NtClose
0x180061cec  mov     eax, edi
0x180061cee  mov     rcx, [rbp+1D0h+var_30]
0x180061cf5  xor     rcx, rsp; StackCookie
0x180061cf8  call    __security_check_cookie
0x180061cfd  add     rsp, 2B8h
0x180061d04  pop     rdi
0x180061d05  pop     rsi
0x180061d06  pop     rbx
0x180061d07  pop     rbp
0x180061d08  retn
```
