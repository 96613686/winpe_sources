# OpenGlobalizationUserSettingsKey_ForMua

- ea: `0x18000d164`
- end: `0x18000d457`
- name: `OpenGlobalizationUserSettingsKey_ForMua`
- size: `755`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006740`

## callees

- `0x18000d118`
- `0x18000d140`
- `0x18000d164`
- `0x18000d460`
- `0x18000db40`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x18000d305`
- `ntdll!RtlAppendUnicodeToString` at `0x18000d327`
- `ntdll!RtlAppendUnicodeToString` at `0x18000d305`
- `ntdll!RtlAppendUnicodeToString` at `0x18000d327`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000d347`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000d347`
- `ntdll!RtlSubAuthoritySid` at `0x18000d22a`
- `ntdll!RtlSubAuthoritySid` at `0x18000d240`
- `ntdll!RtlSubAuthoritySid` at `0x18000d22a`
- `ntdll!RtlSubAuthoritySid` at `0x18000d240`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18000d263`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18000d263`
- `ntdll!RtlFreeUnicodeString` at `0x18000d3f7`
- `ntdll!RtlFreeUnicodeString` at `0x18000d3f7`
- `ntdll!RtlGetPersistedStateLocation` at `0x18000d2b1`
- `ntdll!RtlGetPersistedStateLocation` at `0x18000d2b1`
- `ntdll!RtlSubAuthorityCountSid` at `0x18000d204`
- `ntdll!RtlSubAuthorityCountSid` at `0x18000d204`
- `ntdll!ZwQueryInformationToken` at `0x18000d1e8`
- `ntdll!ZwQueryInformationToken` at `0x18000d1e8`
- `ntdll!ZwClose` at `0x18000d3ab`
- `ntdll!ZwClose` at `0x18000d3ab`
- `ntdll!ZwOpenKey` at `0x18000d396`
- `ntdll!ZwOpenKey` at `0x18000d3ca`
- `ntdll!ZwOpenKey` at `0x18000d396`
- `ntdll!ZwOpenKey` at `0x18000d3ca`

## string_xrefs

- `0x18000d288`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\International`
- `0x18000d2a3`: `TargetNtPath`

## pseudocode

```c
__int64 __fastcall OpenGlobalizationUserSettingsKey_ForMua(__int64 a1, __int64 a2, void **a3, _DWORD *a4)
{
  PSID *Memory; // r14
  NTSTATUS PersistedStateLocation; // ebx
  PSID v8; // rbx
  PUCHAR v9; // rax
  __int64 v10; // rcx
  int v11; // r15d
  USHORT v12; // bx
  WCHAR *v13; // rax
  WCHAR *v14; // rdi
  ULONG ResultLength; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+48h] [rbp-B8h] BYREF
  void *KeyHandle; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Source[264]; // [rsp+A0h] [rbp-60h] BYREF

  UnicodeString = 0;
  memset(&ObjectAttributes, 0, 44);
  Memory = (PSID *)AllocateMemory(84);
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
    v8 = *Memory;
    v9 = RtlSubAuthorityCountSid(*Memory);
    if ( *v9 < 2u || (v11 = 0, *v9 == 5) && *RtlSubAuthoritySid(v8, 0) == 21 && *RtlSubAuthoritySid(v8, 4u) == 503 )
    {
      *a4 = 0;
    }
    else
    {
      PersistedStateLocation = RtlConvertSidToUnicodeString(&UnicodeString, v8, 1u);
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
                  ObjectAttributes.Length = 48;
                  ObjectAttributes.ObjectName = &Destination;
                  ObjectAttributes.RootDirectory = 0;
                  ObjectAttributes.Attributes = 576;
                  KeyHandle = 0;
                  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
                  {
                    v11 = 1;
                    *a4 = 1;
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
      if ( !v11 )
        goto LABEL_23;
    }
    PersistedStateLocation = OpenGlobalizationUserSettingsKey_ForSingleUserModel(v10, a3);
  }
LABEL_23:
  FreeMemory(Memory);
  return (unsigned int)PersistedStateLocation;
}

```

## disassembly

```asm
0x18000d164  mov     [rsp-8+arg_0], rbx
0x18000d169  mov     [rsp-8+arg_8], rsi
0x18000d16e  push    rbp
0x18000d16f  push    rdi
0x18000d170  push    r12
0x18000d172  push    r14
0x18000d174  push    r15
0x18000d176  lea     rbp, [rsp-1C0h]
0x18000d17e  sub     rsp, 2C0h
0x18000d185  mov     rax, cs:__security_cookie
0x18000d18c  xor     rax, rsp
0x18000d18f  mov     [rbp+1E0h+var_30], rax
0x18000d196  xorps   xmm0, xmm0
0x18000d199  xor     eax, eax
0x18000d19b  movups  xmmword ptr [rbp+1E0h+ObjectAttributes.ObjectName], xmm0
0x18000d19f  mov     rsi, r9
0x18000d1a2  mov     r12, r8
0x18000d1a5  movups  xmmword ptr [rsp+2E0h+UnicodeString.Length], xmm0
0x18000d1aa  lea     ebx, [rax+54h]
0x18000d1ad  mov     ecx, ebx
0x18000d1af  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.Length], xmm0
0x18000d1b4  movups  xmmword ptr [rbp+1E0h+ObjectAttributes+1Ch], xmm0
0x18000d1b8  call    AllocateMemory
0x18000d1bd  mov     r14, rax
0x18000d1c0  test    rax, rax
0x18000d1c3  jz      loc_18000D424
0x18000d1c9  lea     rax, [rsp+2E0h+var_2A0]
0x18000d1ce  mov     [rsp+2E0h+var_2A0], 0
0x18000d1d6  mov     r9d, ebx; Length
0x18000d1d9  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x18000d1de  mov     r8, r14; TokenInformation
0x18000d1e1  lea     edx, [rbx-53h]; TokenInformationClass
0x18000d1e4  lea     rcx, [rbx-5Ah]; TokenHandle
0x18000d1e8  call    cs:__imp_ZwQueryInformationToken
0x18000d1ef  nop     dword ptr [rax+rax+00h]
0x18000d1f4  mov     ebx, eax
0x18000d1f6  test    eax, eax
0x18000d1f8  js      loc_18000D41A
0x18000d1fe  mov     rbx, [r14]
0x18000d201  mov     rcx, rbx; Sid
0x18000d204  call    cs:__imp_RtlSubAuthorityCountSid
0x18000d20b  nop     dword ptr [rax+rax+00h]
0x18000d210  cmp     byte ptr [rax], 2
0x18000d213  jb      loc_18000D40A
0x18000d219  xor     r15d, r15d
0x18000d21c  cmp     byte ptr [rax], 5
0x18000d21f  lea     edi, [r15+4]
0x18000d223  jnz     short loc_18000D258
0x18000d225  xor     edx, edx; SubAuthority
0x18000d227  mov     rcx, rbx; Sid
0x18000d22a  call    cs:__imp_RtlSubAuthoritySid
0x18000d231  nop     dword ptr [rax+rax+00h]
0x18000d236  cmp     dword ptr [rax], 15h
0x18000d239  jnz     short loc_18000D258
0x18000d23b  mov     edx, edi; SubAuthority
0x18000d23d  mov     rcx, rbx; Sid
0x18000d240  call    cs:__imp_RtlSubAuthoritySid
0x18000d247  nop     dword ptr [rax+rax+00h]
0x18000d24c  cmp     dword ptr [rax], 1F7h
0x18000d252  jz      loc_18000D40A
0x18000d258  mov     r8b, 1; AllocateDestinationString
0x18000d25b  lea     rcx, [rsp+2E0h+UnicodeString]; UnicodeString
0x18000d260  mov     rdx, rbx; Sid
0x18000d263  call    cs:__imp_RtlConvertSidToUnicodeString
0x18000d26a  nop     dword ptr [rax+rax+00h]
0x18000d26f  mov     ebx, eax
0x18000d271  test    eax, eax
0x18000d273  js      loc_18000D403
0x18000d279  lea     rax, [rsp+2E0h+var_2A0]
0x18000d27e  mov     [rsp+2E0h+var_2A0], r15d
0x18000d283  mov     [rsp+2E0h+var_2B0], rax
0x18000d288  lea     r8, aRegistryMachin_1; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x18000d28f  lea     rax, [rbp+1E0h+Source]
0x18000d293  mov     [rsp+2E0h+var_2B8], 208h
0x18000d29b  xor     r9d, r9d
0x18000d29e  mov     [rsp+2E0h+ResultLength], rax
0x18000d2a3  lea     rdx, aTargetntpath; "TargetNtPath"
0x18000d2aa  lea     rcx, aGlobalizationu; "GlobalizationUserSettings"
0x18000d2b1  call    cs:__imp_RtlGetPersistedStateLocation
0x18000d2b8  nop     dword ptr [rax+rax+00h]
0x18000d2bd  mov     ebx, eax
0x18000d2bf  test    eax, eax
0x18000d2c1  js      loc_18000D3F2
0x18000d2c7  movzx   eax, [rsp+2E0h+UnicodeString.Length]
0x18000d2cc  add     ax, word ptr [rsp+2E0h+var_2A0]
0x18000d2d1  add     ax, di
0x18000d2d4  movzx   ebx, ax
0x18000d2d7  mov     ecx, ebx
0x18000d2d9  call    AllocateMemory
0x18000d2de  mov     rdi, rax
0x18000d2e1  test    rax, rax
0x18000d2e4  jz      loc_18000D3ED
0x18000d2ea  xorps   xmm0, xmm0
0x18000d2ed  lea     rdx, [rbp+1E0h+Source]; Source
0x18000d2f1  movups  xmmword ptr [rsp+2E0h+Destination.Length], xmm0
0x18000d2f6  lea     rcx, [rsp+2E0h+Destination]; Destination
0x18000d2fb  mov     [rsp+2E0h+Destination.MaximumLength], bx
0x18000d300  mov     [rsp+2E0h+Destination.Buffer], rax
0x18000d305  call    cs:__imp_RtlAppendUnicodeToString
0x18000d30c  nop     dword ptr [rax+rax+00h]
0x18000d311  mov     ebx, eax
0x18000d313  test    eax, eax
0x18000d315  js      loc_18000D3E3
0x18000d31b  lea     rdx, asc_180010A08; "\\"
0x18000d322  lea     rcx, [rsp+2E0h+Destination]; Destination
0x18000d327  call    cs:__imp_RtlAppendUnicodeToString
0x18000d32e  nop     dword ptr [rax+rax+00h]
0x18000d333  mov     ebx, eax
0x18000d335  test    eax, eax
0x18000d337  js      loc_18000D3E3
0x18000d33d  lea     rdx, [rsp+2E0h+UnicodeString]; Source
0x18000d342  lea     rcx, [rsp+2E0h+Destination]; Destination
0x18000d347  call    cs:__imp_RtlAppendUnicodeStringToString
0x18000d34e  nop     dword ptr [rax+rax+00h]
0x18000d353  mov     ebx, eax
0x18000d355  test    eax, eax
0x18000d357  js      loc_18000D3E3
0x18000d35d  lea     rax, [rsp+2E0h+Destination]
0x18000d362  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x18000d36a  xorps   xmm0, xmm0
0x18000d36d  mov     [rbp+1E0h+ObjectAttributes.ObjectName], rax
0x18000d371  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x18000d376  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], r15
0x18000d37b  mov     edx, 20019h; DesiredAccess
0x18000d380  mov     [rbp+1E0h+ObjectAttributes.Attributes], 240h
0x18000d387  lea     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x18000d38c  mov     [rsp+2E0h+KeyHandle], r15
0x18000d391  movdqu  xmmword ptr [rbp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000d396  call    cs:__imp_ZwOpenKey
0x18000d39d  nop     dword ptr [rax+rax+00h]
0x18000d3a2  test    eax, eax
0x18000d3a4  js      short loc_18000D3DA
0x18000d3a6  mov     rcx, [rsp+2E0h+KeyHandle]; Handle
0x18000d3ab  call    cs:__imp_ZwClose
0x18000d3b2  nop     dword ptr [rax+rax+00h]
0x18000d3b7  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x18000d3bc  mov     dword ptr [rsi], 2
0x18000d3c2  mov     edx, 2000000h; DesiredAccess
0x18000d3c7  mov     rcx, r12; KeyHandle
0x18000d3ca  call    cs:__imp_ZwOpenKey
0x18000d3d1  nop     dword ptr [rax+rax+00h]
0x18000d3d6  mov     ebx, eax
0x18000d3d8  jmp     short loc_18000D3E3
0x18000d3da  mov     r15d, 1
0x18000d3e0  mov     [rsi], r15d
0x18000d3e3  mov     rcx, rdi
0x18000d3e6  call    FreeMemory
0x18000d3eb  jmp     short loc_18000D3F2
0x18000d3ed  mov     ebx, 0C0000017h
0x18000d3f2  lea     rcx, [rsp+2E0h+UnicodeString]; UnicodeString
0x18000d3f7  call    cs:__imp_RtlFreeUnicodeString
0x18000d3fe  nop     dword ptr [rax+rax+00h]
0x18000d403  test    r15d, r15d
0x18000d406  jz      short loc_18000D41A
0x18000d408  jmp     short loc_18000D410
0x18000d40a  mov     dword ptr [rsi], 0
0x18000d410  mov     rdx, r12
0x18000d413  call    OpenGlobalizationUserSettingsKey_ForSingleUserModel
0x18000d418  mov     ebx, eax
0x18000d41a  mov     rcx, r14
0x18000d41d  call    FreeMemory
0x18000d422  jmp     short loc_18000D429
0x18000d424  mov     ebx, 0C0000017h
0x18000d429  mov     eax, ebx
0x18000d42b  mov     rcx, [rbp+1E0h+var_30]
0x18000d432  xor     rcx, rsp; StackCookie
0x18000d435  call    __security_check_cookie
0x18000d43a  lea     r11, [rsp+2E0h+var_20]
0x18000d442  mov     rbx, [r11+30h]
0x18000d446  mov     rsi, [r11+38h]
0x18000d44a  mov     rsp, r11
0x18000d44d  pop     r15
0x18000d44f  pop     r14
0x18000d451  pop     r12
0x18000d453  pop     rdi
0x18000d454  pop     rbp
0x18000d455  retn
```
