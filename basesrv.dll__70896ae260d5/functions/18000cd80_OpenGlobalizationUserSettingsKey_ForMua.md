# OpenGlobalizationUserSettingsKey_ForMua

- ea: `0x18000cd80`
- end: `0x18000d06d`
- name: `OpenGlobalizationUserSettingsKey_ForMua`
- size: `749`
- prototype: `__int64 __fastcall(__int64, __int64, void **, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800064c0`

## callees

- `0x18000cd34`
- `0x18000cd5c`
- `0x18000cd80`
- `0x18000d074`
- `0x18000d730`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x18000cf22`
- `ntdll!RtlAppendUnicodeToString` at `0x18000cf44`
- `ntdll!RtlAppendUnicodeToString` at `0x18000cf22`
- `ntdll!RtlAppendUnicodeToString` at `0x18000cf44`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000cf64`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000cf64`
- `ntdll!RtlSubAuthoritySid` at `0x18000ce42`
- `ntdll!RtlSubAuthoritySid` at `0x18000ce5a`
- `ntdll!RtlSubAuthoritySid` at `0x18000ce42`
- `ntdll!RtlSubAuthoritySid` at `0x18000ce5a`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18000ce81`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18000ce81`
- `ntdll!RtlFreeUnicodeString` at `0x18000d015`
- `ntdll!RtlFreeUnicodeString` at `0x18000d015`
- `ntdll!RtlGetPersistedStateLocation` at `0x18000cecf`
- `ntdll!RtlGetPersistedStateLocation` at `0x18000cecf`
- `ntdll!RtlSubAuthorityCountSid` at `0x18000ce24`
- `ntdll!RtlSubAuthorityCountSid` at `0x18000ce24`
- `ntdll!ZwQueryInformationToken` at `0x18000ce08`
- `ntdll!ZwQueryInformationToken` at `0x18000ce08`
- `ntdll!ZwClose` at `0x18000cfc8`
- `ntdll!ZwClose` at `0x18000cfc8`
- `ntdll!ZwOpenKey` at `0x18000cfb3`
- `ntdll!ZwOpenKey` at `0x18000cfe7`
- `ntdll!ZwOpenKey` at `0x18000cfb3`
- `ntdll!ZwOpenKey` at `0x18000cfe7`

## string_xrefs

- `0x18000cea6`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\International`
- `0x18000cec1`: `TargetNtPath`

## pseudocode

```c
__int64 __fastcall OpenGlobalizationUserSettingsKey_ForMua(__int64 a1, __int64 a2, void **a3, _DWORD *a4)
{
  int v6; // r15d
  PSID *Memory; // r14
  __int64 v8; // rcx
  NTSTATUS PersistedStateLocation; // ebx
  PSID v10; // rbx
  PUCHAR v11; // rax
  USHORT v12; // bx
  WCHAR *v13; // rax
  WCHAR *v14; // rdi
  ULONG ResultLength; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+48h] [rbp-B8h] BYREF
  void *KeyHandle; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Source[264]; // [rsp+A0h] [rbp-60h] BYREF

  v6 = 0;
  UnicodeString = 0;
  memset(&ObjectAttributes, 0, 44);
  Memory = (PSID *)AllocateMemory(0x54u);
  if ( !Memory )
    return (unsigned int)-1073741801;
  ResultLength = 0;
  PersistedStateLocation = ZwQueryInformationToken(
                             (HANDLE)0xFFFFFFFFFFFFFFFALL,
                             TokenUser,
                             Memory,
                             0x54u,
                             &ResultLength);
  if ( PersistedStateLocation >= 0 )
  {
    v10 = *Memory;
    v11 = RtlSubAuthorityCountSid(*Memory);
    if ( *v11 < 2u || *v11 == 5 && *RtlSubAuthoritySid(v10, 0) == 21 && *RtlSubAuthoritySid(v10, 4u) == 503 )
    {
      *a4 = 0;
LABEL_21:
      PersistedStateLocation = OpenGlobalizationUserSettingsKey_ForSingleUserModel(v8, a3);
      goto LABEL_22;
    }
    PersistedStateLocation = RtlConvertSidToUnicodeString(&UnicodeString, v10, 1u);
    if ( PersistedStateLocation >= 0 )
    {
      ResultLength = 0;
      PersistedStateLocation = RtlGetPersistedStateLocation(
                                 L"GlobalizationUserSettings",
                                 L"TargetNtPath",
                                 L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\International",
                                 0,
                                 Source,
                                 520,
                                 &ResultLength);
      if ( PersistedStateLocation >= 0 )
      {
        v12 = ResultLength + UnicodeString.Length + 4;
        v13 = (WCHAR *)AllocateMemory(v12);
        v14 = v13;
        if ( v13 )
        {
          *(_QWORD *)&Destination.Length = 0;
          Destination.MaximumLength = v12;
          Destination.Buffer = v13;
          PersistedStateLocation = RtlAppendUnicodeToString(&Destination, Source);
          if ( PersistedStateLocation >= 0 )
          {
            PersistedStateLocation = RtlAppendUnicodeToString(&Destination, L"\\");
            if ( PersistedStateLocation >= 0 )
            {
              PersistedStateLocation = RtlAppendUnicodeStringToString(&Destination, &UnicodeString);
              if ( PersistedStateLocation >= 0 )
              {
                ObjectAttributes.RootDirectory = 0;
                KeyHandle = 0;
                ObjectAttributes.ObjectName = &Destination;
                ObjectAttributes.Length = 48;
                ObjectAttributes.Attributes = 576;
                *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
                {
                  *a4 = 1;
                  v6 = 1;
                }
                else
                {
                  ZwClose(KeyHandle);
                  *a4 = 2;
                  PersistedStateLocation = ZwOpenKey(a3, 0x2000000u, &ObjectAttributes);
                }
              }
            }
          }
          FreeMemory(v14);
        }
        else
        {
          PersistedStateLocation = -1073741801;
        }
      }
      RtlFreeUnicodeString(&UnicodeString);
    }
  }
  if ( v6 )
    goto LABEL_21;
LABEL_22:
  FreeMemory(Memory);
  return (unsigned int)PersistedStateLocation;
}

```

## disassembly

```asm
0x18000cd80  mov     [rsp-8+arg_0], rbx
0x18000cd85  mov     [rsp-8+arg_8], rsi
0x18000cd8a  push    rbp
0x18000cd8b  push    rdi
0x18000cd8c  push    r12
0x18000cd8e  push    r14
0x18000cd90  push    r15
0x18000cd92  lea     rbp, [rsp-1C0h]
0x18000cd9a  sub     rsp, 2C0h
0x18000cda1  mov     rax, cs:__security_cookie
0x18000cda8  xor     rax, rsp
0x18000cdab  mov     [rbp+1E0h+var_30], rax
0x18000cdb2  xorps   xmm0, xmm0
0x18000cdb5  xor     eax, eax
0x18000cdb7  xor     edi, edi
0x18000cdb9  mov     [rbp+1E0h+ObjectAttributes.SecurityDescriptor], rax
0x18000cdbd  mov     rsi, r9
0x18000cdc0  mov     dword ptr [rbp+1E0h+ObjectAttributes.SecurityQualityOfService], eax
0x18000cdc3  mov     r12, r8
0x18000cdc6  xor     r15d, r15d
0x18000cdc9  movups  xmmword ptr [rsp+2E0h+UnicodeString.Length], xmm0
0x18000cdce  lea     ebx, [rdi+54h]
0x18000cdd1  mov     ecx, ebx
0x18000cdd3  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.Length], xmm0
0x18000cdd8  movups  xmmword ptr [rbp+1E0h+ObjectAttributes.ObjectName], xmm0
0x18000cddc  call    AllocateMemory
0x18000cde1  mov     r14, rax
0x18000cde4  test    rax, rax
0x18000cde7  jz      loc_18000D03A
0x18000cded  and     [rsp+2E0h+var_2A0], edi
0x18000cdf1  lea     rax, [rsp+2E0h+var_2A0]
0x18000cdf6  mov     r9d, ebx; Length
0x18000cdf9  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x18000cdfe  mov     r8, r14; TokenInformation
0x18000ce01  lea     edx, [rdi+1]; TokenInformationClass
0x18000ce04  lea     rcx, [rdi-6]; TokenHandle
0x18000ce08  call    cs:__imp_ZwQueryInformationToken
0x18000ce0f  nop     dword ptr [rax+rax+00h]
0x18000ce14  mov     ebx, eax
0x18000ce16  test    eax, eax
0x18000ce18  js      loc_18000D021
0x18000ce1e  mov     rbx, [r14]
0x18000ce21  mov     rcx, rbx; Sid
0x18000ce24  call    cs:__imp_RtlSubAuthorityCountSid
0x18000ce2b  nop     dword ptr [rax+rax+00h]
0x18000ce30  cmp     byte ptr [rax], 2
0x18000ce33  jb      short loc_18000CE6E
0x18000ce35  cmp     byte ptr [rax], 5
0x18000ce38  mov     rdi, rbx
0x18000ce3b  jnz     short loc_18000CE76
0x18000ce3d  xor     edx, edx; SubAuthority
0x18000ce3f  mov     rcx, rbx; Sid
0x18000ce42  call    cs:__imp_RtlSubAuthoritySid
0x18000ce49  nop     dword ptr [rax+rax+00h]
0x18000ce4e  cmp     dword ptr [rax], 15h
0x18000ce51  jnz     short loc_18000CE76
0x18000ce53  lea     edx, [r15+4]; SubAuthority
0x18000ce57  mov     rcx, rbx; Sid
0x18000ce5a  call    cs:__imp_RtlSubAuthoritySid
0x18000ce61  nop     dword ptr [rax+rax+00h]
0x18000ce66  cmp     dword ptr [rax], 1F7h
0x18000ce6c  jnz     short loc_18000CE76
0x18000ce6e  and     [rsi], r15d
0x18000ce71  jmp     loc_18000D026
0x18000ce76  mov     r8b, 1; AllocateDestinationString
0x18000ce79  lea     rcx, [rsp+2E0h+UnicodeString]; UnicodeString
0x18000ce7e  mov     rdx, rdi; Sid
0x18000ce81  call    cs:__imp_RtlConvertSidToUnicodeString
0x18000ce88  nop     dword ptr [rax+rax+00h]
0x18000ce8d  mov     ebx, eax
0x18000ce8f  test    eax, eax
0x18000ce91  js      loc_18000D021
0x18000ce97  and     [rsp+2E0h+var_2A0], r15d
0x18000ce9c  lea     rax, [rsp+2E0h+var_2A0]
0x18000cea1  mov     [rsp+2E0h+var_2B0], rax
0x18000cea6  lea     r8, aRegistryMachin_1; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x18000cead  lea     rax, [rbp+1E0h+Source]
0x18000ceb1  mov     [rsp+2E0h+var_2B8], 208h
0x18000ceb9  xor     r9d, r9d
0x18000cebc  mov     [rsp+2E0h+ResultLength], rax
0x18000cec1  lea     rdx, aTargetntpath; "TargetNtPath"
0x18000cec8  lea     rcx, aGlobalizationu; "GlobalizationUserSettings"
0x18000cecf  call    cs:__imp_RtlGetPersistedStateLocation
0x18000ced6  nop     dword ptr [rax+rax+00h]
0x18000cedb  mov     ebx, eax
0x18000cedd  test    eax, eax
0x18000cedf  js      loc_18000D010
0x18000cee5  movzx   ebx, [rsp+2E0h+UnicodeString.Length]
0x18000ceea  add     bx, 4
0x18000ceee  add     bx, word ptr [rsp+2E0h+var_2A0]
0x18000cef3  movzx   ecx, bx
0x18000cef6  call    AllocateMemory
0x18000cefb  mov     rdi, rax
0x18000cefe  test    rax, rax
0x18000cf01  jz      loc_18000D00B
0x18000cf07  xorps   xmm0, xmm0
0x18000cf0a  lea     rdx, [rbp+1E0h+Source]; Source
0x18000cf0e  movups  xmmword ptr [rsp+2E0h+Destination.Length], xmm0
0x18000cf13  lea     rcx, [rsp+2E0h+Destination]; Destination
0x18000cf18  mov     [rsp+2E0h+Destination.MaximumLength], bx
0x18000cf1d  mov     [rsp+2E0h+Destination.Buffer], rax
0x18000cf22  call    cs:__imp_RtlAppendUnicodeToString
0x18000cf29  nop     dword ptr [rax+rax+00h]
0x18000cf2e  mov     ebx, eax
0x18000cf30  test    eax, eax
0x18000cf32  js      loc_18000D001
0x18000cf38  lea     rdx, asc_180010A08; "\\"
0x18000cf3f  lea     rcx, [rsp+2E0h+Destination]; Destination
0x18000cf44  call    cs:__imp_RtlAppendUnicodeToString
0x18000cf4b  nop     dword ptr [rax+rax+00h]
0x18000cf50  mov     ebx, eax
0x18000cf52  test    eax, eax
0x18000cf54  js      loc_18000D001
0x18000cf5a  lea     rdx, [rsp+2E0h+UnicodeString]; Source
0x18000cf5f  lea     rcx, [rsp+2E0h+Destination]; Destination
0x18000cf64  call    cs:__imp_RtlAppendUnicodeStringToString
0x18000cf6b  nop     dword ptr [rax+rax+00h]
0x18000cf70  mov     ebx, eax
0x18000cf72  test    eax, eax
0x18000cf74  js      loc_18000D001
0x18000cf7a  and     [rsp+2E0h+ObjectAttributes.RootDirectory], r15
0x18000cf7f  lea     rax, [rsp+2E0h+Destination]
0x18000cf84  and     [rsp+2E0h+KeyHandle], r15
0x18000cf89  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x18000cf8e  xorps   xmm0, xmm0
0x18000cf91  mov     [rbp+1E0h+ObjectAttributes.ObjectName], rax
0x18000cf95  mov     edx, 20019h; DesiredAccess
0x18000cf9a  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x18000cfa2  lea     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x18000cfa7  mov     [rbp+1E0h+ObjectAttributes.Attributes], 240h
0x18000cfae  movdqu  xmmword ptr [rbp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000cfb3  call    cs:__imp_ZwOpenKey
0x18000cfba  nop     dword ptr [rax+rax+00h]
0x18000cfbf  test    eax, eax
0x18000cfc1  js      short loc_18000CFF7
0x18000cfc3  mov     rcx, [rsp+2E0h+KeyHandle]; Handle
0x18000cfc8  call    cs:__imp_ZwClose
0x18000cfcf  nop     dword ptr [rax+rax+00h]
0x18000cfd4  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x18000cfd9  mov     dword ptr [rsi], 2
0x18000cfdf  mov     edx, 2000000h; DesiredAccess
0x18000cfe4  mov     rcx, r12; KeyHandle
0x18000cfe7  call    cs:__imp_ZwOpenKey
0x18000cfee  nop     dword ptr [rax+rax+00h]
0x18000cff3  mov     ebx, eax
0x18000cff5  jmp     short loc_18000D001
0x18000cff7  mov     eax, 1
0x18000cffc  mov     [rsi], eax
0x18000cffe  mov     r15d, eax
0x18000d001  mov     rcx, rdi
0x18000d004  call    FreeMemory
0x18000d009  jmp     short loc_18000D010
0x18000d00b  mov     ebx, 0C0000017h
0x18000d010  lea     rcx, [rsp+2E0h+UnicodeString]; UnicodeString
0x18000d015  call    cs:__imp_RtlFreeUnicodeString
0x18000d01c  nop     dword ptr [rax+rax+00h]
0x18000d021  test    r15d, r15d
0x18000d024  jz      short loc_18000D030
0x18000d026  mov     rdx, r12
0x18000d029  call    OpenGlobalizationUserSettingsKey_ForSingleUserModel
0x18000d02e  mov     ebx, eax
0x18000d030  mov     rcx, r14
0x18000d033  call    FreeMemory
0x18000d038  jmp     short loc_18000D03F
0x18000d03a  mov     ebx, 0C0000017h
0x18000d03f  mov     eax, ebx
0x18000d041  mov     rcx, [rbp+1E0h+var_30]
0x18000d048  xor     rcx, rsp; StackCookie
0x18000d04b  call    __security_check_cookie
0x18000d050  lea     r11, [rsp+2E0h+var_20]
0x18000d058  mov     rbx, [r11+30h]
0x18000d05c  mov     rsi, [r11+38h]
0x18000d060  mov     rsp, r11
0x18000d063  pop     r15
0x18000d065  pop     r14
0x18000d067  pop     r12
0x18000d069  pop     rdi
0x18000d06a  pop     rbp
0x18000d06b  retn
```
