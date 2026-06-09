# OpenGlobalizationUserSettingsKey_ForMua

- ea: `0x18007217c`
- end: `0x180072386`
- name: `OpenGlobalizationUserSettingsKey_ForMua`
- size: `522`
- prototype: `__int64 __fastcall(ACCESS_MASK DesiredAccess, PSID Sid, PHANDLE KeyHandle)`
- caller_count: `16`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000dd50`
- `0x1800108d0`
- `0x1800123e0`
- `0x1800181e0`
- `0x180019090`
- `0x18001a230`
- `0x18001b3a0`
- `0x18001d7c0`
- `0x180037730`
- `0x1800709b0`
- `0x180070c90`
- `0x180071550`
- `0x180071b90`
- `0x180071e90`
- `0x180072474`
- `0x18013dae0`

## callees

- `0x180049440`
- `0x18007217c`
- `0x180107ea0`
- `0x180122e60`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x180190b33`
- `ntdll!RtlSubAuthoritySid` at `0x180190b47`
- `ntdll!RtlSubAuthoritySid` at `0x180190b33`
- `ntdll!RtlSubAuthoritySid` at `0x180190b47`
- `ntdll!RtlFreeUnicodeString` at `0x18007236c`
- `ntdll!RtlFreeUnicodeString` at `0x18007236c`
- `ntdll!RtlGetPersistedStateLocation` at `0x18007222f`
- `ntdll!RtlGetPersistedStateLocation` at `0x18007222f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800722af`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800722af`
- `ntdll!RtlAppendUnicodeToString` at `0x18007227d`
- `ntdll!RtlAppendUnicodeToString` at `0x180072299`
- `ntdll!RtlAppendUnicodeToString` at `0x18007227d`
- `ntdll!RtlAppendUnicodeToString` at `0x180072299`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800721e7`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800721e7`
- `ntdll!RtlSubAuthorityCountSid` at `0x180190b13`
- `ntdll!RtlSubAuthorityCountSid` at `0x180190b13`
- `ntdll!ZwQueryInformationToken` at `0x180190afd`
- `ntdll!ZwQueryInformationToken` at `0x180190afd`
- `ntdll!ZwClose` at `0x180072303`
- `ntdll!ZwClose` at `0x180072303`
- `ntdll!ZwOpenKey` at `0x1800722f4`
- `ntdll!ZwOpenKey` at `0x18007231b`
- `ntdll!ZwOpenKey` at `0x1800722f4`
- `ntdll!ZwOpenKey` at `0x18007231b`

## string_xrefs

- `0x180072206`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\International`
- `0x180072221`: `TargetNtPath`

## pseudocode

```c
__int64 __fastcall OpenGlobalizationUserSettingsKey_ForMua(
        ACCESS_MASK DesiredAccess,
        PSID Sid,
        PHANDLE KeyHandle,
        _DWORD *a4)
{
  PSID v6; // rbx
  PSID *v8; // rdi
  NTSTATUS PersistedStateLocation; // ebx
  USHORT v10; // bx
  WCHAR *v11; // rax
  WCHAR *v12; // rsi
  int v13; // r14d
  PUCHAR v15; // rax
  ULONG ResultLength; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE KeyHandlea; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Source[264]; // [rsp+A0h] [rbp-60h] BYREF

  v6 = Sid;
  UnicodeString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( Sid )
  {
    v8 = 0;
  }
  else
  {
    v8 = (PSID *)wil::details::heap_allocator::allocate(0x54u);
    if ( !v8 )
      return (unsigned int)-1073741801;
    ResultLength = 0;
    PersistedStateLocation = ZwQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, v8, 0x54u, &ResultLength);
    if ( PersistedStateLocation < 0 )
      goto LABEL_19;
    v6 = *v8;
  }
  v15 = RtlSubAuthorityCountSid(v6);
  if ( *v15 < 2u || (v13 = 0, *v15 == 5) && *RtlSubAuthoritySid(v6, 0) == 21 && *RtlSubAuthoritySid(v6, 4u) == 503 )
  {
    *a4 = 0;
LABEL_28:
    PersistedStateLocation = OpenGlobalizationUserSettingsKey_ForSingleUserModel(DesiredAccess, KeyHandle);
    goto LABEL_13;
  }
  PersistedStateLocation = RtlConvertSidToUnicodeString(&UnicodeString, v6, 1u);
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
      v10 = ResultLength + UnicodeString.Length + 4;
      v11 = (WCHAR *)wil::details::heap_allocator::allocate(v10);
      v12 = v11;
      if ( v11 )
      {
        *(_QWORD *)&Destination.Length = 0;
        Destination.MaximumLength = v10;
        Destination.Buffer = v11;
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
              KeyHandlea = 0;
              *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
              if ( ZwOpenKey(&KeyHandlea, 0x20019u, &ObjectAttributes) < 0 )
              {
                v13 = 1;
                *a4 = 1;
              }
              else
              {
                ZwClose(KeyHandlea);
                *a4 = 2;
                PersistedStateLocation = ZwOpenKey(KeyHandle, DesiredAccess, &ObjectAttributes);
              }
            }
          }
        }
        FreeEnvironmentStringsW(v12);
      }
      else
      {
        PersistedStateLocation = -1073741801;
      }
    }
    RtlFreeUnicodeString(&UnicodeString);
  }
  if ( v13 )
    goto LABEL_28;
LABEL_13:
  if ( v8 )
LABEL_19:
    FreeEnvironmentStringsW((LPWCH)v8);
  return (unsigned int)PersistedStateLocation;
}

```

## disassembly

```asm
0x18007217c  push    rbp
0x18007217e  push    rbx
0x18007217f  push    rsi
0x180072180  push    rdi
0x180072181  push    r12
0x180072183  push    r13
0x180072185  push    r14
0x180072187  push    r15
0x180072189  lea     rbp, [rsp-1C8h]
0x180072191  sub     rsp, 2C8h
0x180072198  mov     rax, cs:__security_cookie
0x18007219f  xor     rax, rsp
0x1800721a2  mov     [rbp+200h+var_50], rax
0x1800721a9  xorps   xmm0, xmm0
0x1800721ac  xor     eax, eax
0x1800721ae  mov     r15, r9
0x1800721b1  mov     r13, r8
0x1800721b4  mov     rbx, rdx
0x1800721b7  mov     r12d, ecx
0x1800721ba  movups  xmmword ptr [rbp+200h+ObjectAttributes.ObjectName], xmm0
0x1800721be  movups  xmmword ptr [rbp+200h+ObjectAttributes+1Ch], xmm0
0x1800721c2  movups  xmmword ptr [rsp+300h+UnicodeString.Length], xmm0
0x1800721c7  movups  xmmword ptr [rsp+300h+ObjectAttributes.Length], xmm0
0x1800721cc  test    rdx, rdx
0x1800721cf  jz      loc_180190AC6
0x1800721d5  xor     edi, edi
0x1800721d7  jmp     loc_180190B10
0x1800721dc  mov     r8b, 1; AllocateDestinationString
0x1800721df  lea     rcx, [rsp+300h+UnicodeString]; UnicodeString
0x1800721e4  mov     rdx, rbx; Sid
0x1800721e7  call    cs:__imp_RtlConvertSidToUnicodeString
0x1800721ed  mov     ebx, eax
0x1800721ef  test    eax, eax
0x1800721f1  js      loc_180072372
0x1800721f7  lea     rax, [rsp+300h+var_2C0]
0x1800721fc  mov     [rsp+300h+var_2C0], r14d
0x180072201  mov     [rsp+300h+var_2D0], rax
0x180072206  lea     r8, aRegistryMachin_35; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x18007220d  lea     rax, [rbp+200h+Source]
0x180072211  mov     [rsp+300h+var_2D8], 208h
0x180072219  xor     r9d, r9d
0x18007221c  mov     [rsp+300h+ResultLength], rax
0x180072221  lea     rdx, aTargetntpath; "TargetNtPath"
0x180072228  lea     rcx, aGlobalizationu; "GlobalizationUserSettings"
0x18007222f  call    cs:__imp_RtlGetPersistedStateLocation
0x180072235  mov     ebx, eax
0x180072237  test    eax, eax
0x180072239  js      loc_180072367
0x18007223f  movzx   eax, [rsp+300h+UnicodeString.Length]
0x180072244  add     ax, word ptr [rsp+300h+var_2C0]
0x180072249  add     ax, si
0x18007224c  movzx   ebx, ax
0x18007224f  mov     ecx, ebx; unsigned __int64
0x180072251  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x180072256  mov     rsi, rax
0x180072259  test    rax, rax
0x18007225c  jz      loc_180072362
0x180072262  xorps   xmm0, xmm0
0x180072265  lea     rdx, [rbp+200h+Source]; Source
0x180072269  movups  xmmword ptr [rsp+300h+Destination.Length], xmm0
0x18007226e  lea     rcx, [rsp+300h+Destination]; Destination
0x180072273  mov     [rsp+300h+Destination.MaximumLength], bx
0x180072278  mov     [rsp+300h+Destination.Buffer], rax
0x18007227d  call    cs:__imp_RtlAppendUnicodeToString
0x180072283  mov     ebx, eax
0x180072285  test    eax, eax
0x180072287  js      loc_180072323
0x18007228d  lea     rdx, asc_180290A34; "\\"
0x180072294  lea     rcx, [rsp+300h+Destination]; Destination
0x180072299  call    cs:__imp_RtlAppendUnicodeToString
0x18007229f  mov     ebx, eax
0x1800722a1  test    eax, eax
0x1800722a3  js      short loc_180072323
0x1800722a5  lea     rdx, [rsp+300h+UnicodeString]; Source
0x1800722aa  lea     rcx, [rsp+300h+Destination]; Destination
0x1800722af  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800722b5  mov     ebx, eax
0x1800722b7  test    eax, eax
0x1800722b9  js      short loc_180072323
0x1800722bb  lea     rax, [rsp+300h+Destination]
0x1800722c0  mov     [rsp+300h+ObjectAttributes.Length], 30h ; '0'
0x1800722c8  xorps   xmm0, xmm0
0x1800722cb  mov     [rbp+200h+ObjectAttributes.ObjectName], rax
0x1800722cf  lea     r8, [rsp+300h+ObjectAttributes]; ObjectAttributes
0x1800722d4  mov     [rsp+300h+ObjectAttributes.RootDirectory], r14
0x1800722d9  mov     edx, 20019h; DesiredAccess
0x1800722de  mov     [rbp+200h+ObjectAttributes.Attributes], 240h
0x1800722e5  lea     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x1800722ea  mov     [rsp+300h+KeyHandle], r14
0x1800722ef  movdqu  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800722f4  call    cs:__imp_ZwOpenKey
0x1800722fa  test    eax, eax
0x1800722fc  js      short loc_18007232D
0x1800722fe  mov     rcx, [rsp+300h+KeyHandle]; Handle
0x180072303  call    cs:__imp_ZwClose
0x180072309  lea     r8, [rsp+300h+ObjectAttributes]; ObjectAttributes
0x18007230e  mov     dword ptr [r15], 2
0x180072315  mov     edx, r12d; DesiredAccess
0x180072318  mov     rcx, r13; KeyHandle
0x18007231b  call    cs:__imp_ZwOpenKey
0x180072321  mov     ebx, eax
0x180072323  mov     rcx, rsi; penv
0x180072326  call    FreeEnvironmentStringsW
0x18007232b  jmp     short loc_180072367
0x18007232d  mov     r14d, 1
0x180072333  mov     [r15], r14d
0x180072336  jmp     short loc_180072323
0x180072338  test    rdi, rdi
0x18007233b  jnz     short loc_18007237C
0x18007233d  mov     eax, ebx
0x18007233f  mov     rcx, [rbp+200h+var_50]
0x180072346  xor     rcx, rsp; StackCookie
0x180072349  call    __security_check_cookie
0x18007234e  add     rsp, 2C8h
0x180072355  pop     r15
0x180072357  pop     r14
0x180072359  pop     r13
0x18007235b  pop     r12
0x18007235d  pop     rdi
0x18007235e  pop     rsi
0x18007235f  pop     rbx
0x180072360  pop     rbp
0x180072361  retn
0x180072362  mov     ebx, 0C0000017h
0x180072367  lea     rcx, [rsp+300h+UnicodeString]; UnicodeString
0x18007236c  call    cs:__imp_RtlFreeUnicodeString
0x180072372  test    r14d, r14d
0x180072375  jz      short loc_180072338
0x180072377  jmp     loc_180190B60
0x18007237c  mov     rcx, rdi; penv
0x18007237f  call    FreeEnvironmentStringsW
0x180072384  jmp     short loc_18007233D
0x180190ac6  mov     ebx, 54h ; 'T'
0x180190acb  mov     ecx, ebx; unsigned __int64
0x180190acd  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x180190ad2  mov     rdi, rax
0x180190ad5  test    rax, rax
0x180190ad8  jz      loc_180190B72
0x180190ade  lea     rax, [rsp+300h+var_2C0]
0x180190ae3  mov     [rsp+300h+var_2C0], 0
0x180190aeb  mov     r9d, ebx; Length
0x180190aee  mov     [rsp+300h+ResultLength], rax; ResultLength
0x180190af3  mov     r8, rdi; TokenInformation
0x180190af6  lea     edx, [rbx-53h]; TokenInformationClass
0x180190af9  lea     rcx, [rbx-5Ah]; TokenHandle
0x180190afd  call    cs:__imp_ZwQueryInformationToken
0x180190b03  mov     ebx, eax
0x180190b05  test    eax, eax
0x180190b07  js      loc_18007237C
0x180190b0d  mov     rbx, [rdi]
0x180190b10  mov     rcx, rbx; Sid
0x180190b13  call    cs:__imp_RtlSubAuthorityCountSid
0x180190b19  cmp     byte ptr [rax], 2
0x180190b1c  jb      short loc_180190B59
0x180190b1e  xor     r14d, r14d
0x180190b21  cmp     byte ptr [rax], 5
0x180190b24  lea     esi, [r14+4]
0x180190b28  jnz     loc_1800721DC
0x180190b2e  xor     edx, edx; SubAuthority
0x180190b30  mov     rcx, rbx; Sid
0x180190b33  call    cs:__imp_RtlSubAuthoritySid
0x180190b39  cmp     dword ptr [rax], 15h
0x180190b3c  jnz     loc_1800721DC
0x180190b42  mov     edx, esi; SubAuthority
0x180190b44  mov     rcx, rbx; Sid
0x180190b47  call    cs:__imp_RtlSubAuthoritySid
0x180190b4d  cmp     dword ptr [rax], 1F7h
0x180190b53  jnz     loc_1800721DC
0x180190b59  mov     dword ptr [r15], 0
0x180190b60  mov     rdx, r13; KeyHandle
0x180190b63  mov     ecx, r12d; DesiredAccess
0x180190b66  call    OpenGlobalizationUserSettingsKey_ForSingleUserModel
0x180190b6b  mov     ebx, eax
0x180190b6d  jmp     loc_180072338
0x180190b72  mov     ebx, 0C0000017h
0x180190b77  jmp     loc_18007233D
```
