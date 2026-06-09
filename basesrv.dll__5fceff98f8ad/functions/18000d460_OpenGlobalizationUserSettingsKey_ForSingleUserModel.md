# OpenGlobalizationUserSettingsKey_ForSingleUserModel

- ea: `0x18000d460`
- end: `0x18000d6b9`
- name: `OpenGlobalizationUserSettingsKey_ForSingleUserModel`
- size: `601`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006740`
- `0x18000d164`

## callees

- `0x18000d118`
- `0x18000d140`
- `0x18000d460`
- `0x18000d6c0`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x18000d605`
- `ntdll!RtlCopyUnicodeString` at `0x18000d66a`
- `ntdll!RtlCopyUnicodeString` at `0x18000d605`
- `ntdll!RtlCopyUnicodeString` at `0x18000d66a`
- `ntdll!RtlInitUnicodeString` at `0x18000d491`
- `ntdll!RtlInitUnicodeString` at `0x18000d4c7`
- `ntdll!RtlInitUnicodeString` at `0x18000d503`
- `ntdll!RtlInitUnicodeString` at `0x18000d5bd`
- `ntdll!RtlInitUnicodeString` at `0x18000d491`
- `ntdll!RtlInitUnicodeString` at `0x18000d4c7`
- `ntdll!RtlInitUnicodeString` at `0x18000d503`
- `ntdll!RtlInitUnicodeString` at `0x18000d5bd`
- `ntdll!ZwQueryValueKey` at `0x18000d532`
- `ntdll!ZwQueryValueKey` at `0x18000d58a`
- `ntdll!ZwQueryValueKey` at `0x18000d532`
- `ntdll!ZwQueryValueKey` at `0x18000d58a`
- `ntdll!ZwClose` at `0x18000d69a`
- `ntdll!ZwClose` at `0x18000d69a`

## string_xrefs

- `0x18000d4b0`: `\Registry\Machine\System\CurrentControlSet\Control\CommonGlobUserSettings\`

## pseudocode

```c
__int64 __fastcall OpenGlobalizationUserSettingsKey_ForSingleUserModel(ULONG a1, HANDLE *a2)
{
  __int64 v3; // rcx
  NTSTATUS v4; // ebx
  __int64 v5; // rcx
  NTSTATUS v6; // eax
  __int64 Memory; // rdi
  __int64 v8; // rcx
  HANDLE v9; // rax
  UNICODE_STRING SourceString; // [rsp+30h] [rbp-40h] BYREF
  UNICODE_STRING v12; // [rsp+40h] [rbp-30h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-10h] BYREF
  ULONG ResultLength; // [rsp+90h] [rbp+20h] BYREF
  HANDLE KeyHandle; // [rsp+A0h] [rbp+30h] BYREF
  void *v17; // [rsp+A8h] [rbp+38h] BYREF

  ResultLength = a1;
  if ( dword_1800136A4 )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, &word_1800136B0);
    return (unsigned int)OpenRegistryKey(v3, &DestinationString, a2);
  }
  KeyHandle = 0;
  v12 = 0;
  RtlInitUnicodeString(&v12, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CommonGlobUserSettings\\");
  v4 = OpenRegistryKey(v5, &v12, &KeyHandle);
  if ( v4 >= 0 )
  {
    ResultLength = 0;
    ValueName = 0;
    RtlInitUnicodeString(&ValueName, L"RedirectedKey");
    v6 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, 0, 0, &ResultLength);
    if ( !ResultLength || v6 != -1073741789 && v6 != -2147483643 )
    {
      *(_QWORD *)&DestinationString.Length = 11141120;
      DestinationString.Buffer = &word_1800136B0;
      if ( v12.Length <= 0xAAu )
      {
        RtlCopyUnicodeString(&DestinationString, &v12);
        dword_1800136A4 = 1;
      }
      v4 = 0;
      *a2 = KeyHandle;
      KeyHandle = 0;
      goto LABEL_21;
    }
    Memory = AllocateMemory(ResultLength);
    if ( Memory )
    {
      v4 = ZwQueryValueKey(
             KeyHandle,
             &ValueName,
             KeyValuePartialInformation,
             (PVOID)Memory,
             ResultLength,
             &ResultLength);
      if ( v4 >= 0 )
      {
        if ( *(_DWORD *)(Memory + 4) != 1 )
        {
          v9 = KeyHandle;
          KeyHandle = 0;
LABEL_15:
          *a2 = v9;
          goto LABEL_16;
        }
        v17 = 0;
        SourceString = 0;
        RtlInitUnicodeString(&SourceString, (PCWSTR)(Memory + 12));
        v4 = OpenRegistryKey(v8, &SourceString, &v17);
        if ( v4 >= 0 )
        {
          *(_QWORD *)&DestinationString.Length = 11141120;
          DestinationString.Buffer = &word_1800136B0;
          if ( SourceString.Length <= 0xAAu )
          {
            RtlCopyUnicodeString(&DestinationString, &SourceString);
            dword_1800136A4 = 1;
          }
          v9 = v17;
          goto LABEL_15;
        }
      }
LABEL_16:
      FreeMemory(Memory);
      goto LABEL_21;
    }
    v4 = -1073741801;
  }
LABEL_21:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000d460  mov     [rsp-18h+arg_8], rbx
0x18000d465  mov     [rsp-18h+arg_0], ecx
0x18000d469  push    rbp
0x18000d46a  push    rsi
0x18000d46b  push    rdi
0x18000d46c  mov     rbp, rsp
0x18000d46f  sub     rsp, 70h
0x18000d473  cmp     cs:dword_1800136A4, 0
0x18000d47a  mov     rsi, rdx
0x18000d47d  xorps   xmm0, xmm0
0x18000d480  jz      short loc_18000D4B0
0x18000d482  lea     rdx, word_1800136B0; SourceString
0x18000d489  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000d48d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000d491  call    cs:__imp_RtlInitUnicodeString
0x18000d498  nop     dword ptr [rax+rax+00h]
0x18000d49d  mov     r8, rsi
0x18000d4a0  lea     rdx, [rbp+DestinationString]
0x18000d4a4  call    OpenRegistryKey
0x18000d4a9  mov     ebx, eax
0x18000d4ab  jmp     loc_18000D6A6
0x18000d4b0  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x18000d4b7  mov     [rbp+KeyHandle], 0
0x18000d4bf  lea     rcx, [rbp+var_30]; DestinationString
0x18000d4c3  movups  xmmword ptr [rbp+var_30.Length], xmm0
0x18000d4c7  call    cs:__imp_RtlInitUnicodeString
0x18000d4ce  nop     dword ptr [rax+rax+00h]
0x18000d4d3  lea     r8, [rbp+KeyHandle]
0x18000d4d7  lea     rdx, [rbp+var_30]
0x18000d4db  call    OpenRegistryKey
0x18000d4e0  mov     ebx, eax
0x18000d4e2  test    eax, eax
0x18000d4e4  js      loc_18000D691
0x18000d4ea  xorps   xmm0, xmm0
0x18000d4ed  mov     [rbp+arg_0], 0
0x18000d4f4  lea     rdx, aRedirectedkey; "RedirectedKey"
0x18000d4fb  lea     rcx, [rbp+ValueName]; DestinationString
0x18000d4ff  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x18000d503  call    cs:__imp_RtlInitUnicodeString
0x18000d50a  nop     dword ptr [rax+rax+00h]
0x18000d50f  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18000d513  lea     rax, [rbp+arg_0]
0x18000d517  xor     r9d, r9d; KeyValueInformation
0x18000d51a  mov     [rsp+70h+ResultLength], rax; ResultLength
0x18000d51f  lea     rdx, [rbp+ValueName]; ValueName
0x18000d523  mov     [rsp+70h+Length], 0; Length
0x18000d52b  lea     ebx, [r9+2]
0x18000d52f  mov     r8d, ebx; KeyValueInformationClass
0x18000d532  call    cs:__imp_ZwQueryValueKey
0x18000d539  nop     dword ptr [rax+rax+00h]
0x18000d53e  mov     ecx, [rbp+arg_0]
0x18000d541  test    ecx, ecx
0x18000d543  jz      loc_18000D641
0x18000d549  cmp     eax, 0C0000023h
0x18000d54e  jz      short loc_18000D55B
0x18000d550  cmp     eax, 80000005h
0x18000d555  jnz     loc_18000D641
0x18000d55b  call    AllocateMemory
0x18000d560  mov     rdi, rax
0x18000d563  test    rax, rax
0x18000d566  jz      loc_18000D63A
0x18000d56c  mov     ecx, [rbp+arg_0]
0x18000d56f  lea     rax, [rbp+arg_0]
0x18000d573  mov     [rsp+70h+ResultLength], rax; ResultLength
0x18000d578  lea     rdx, [rbp+ValueName]; ValueName
0x18000d57c  mov     [rsp+70h+Length], ecx; Length
0x18000d580  mov     r9, rdi; KeyValueInformation
0x18000d583  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18000d587  mov     r8d, ebx; KeyValueInformationClass
0x18000d58a  call    cs:__imp_ZwQueryValueKey
0x18000d591  nop     dword ptr [rax+rax+00h]
0x18000d596  mov     ebx, eax
0x18000d598  test    eax, eax
0x18000d59a  js      loc_18000D630
0x18000d5a0  cmp     dword ptr [rdi+4], 1
0x18000d5a4  jnz     short loc_18000D621
0x18000d5a6  xorps   xmm0, xmm0
0x18000d5a9  mov     [rbp+arg_18], 0
0x18000d5b1  lea     rdx, [rdi+0Ch]; SourceString
0x18000d5b5  lea     rcx, [rbp+SourceString]; DestinationString
0x18000d5b9  movups  xmmword ptr [rbp+SourceString.Length], xmm0
0x18000d5bd  call    cs:__imp_RtlInitUnicodeString
0x18000d5c4  nop     dword ptr [rax+rax+00h]
0x18000d5c9  lea     r8, [rbp+arg_18]
0x18000d5cd  lea     rdx, [rbp+SourceString]
0x18000d5d1  call    OpenRegistryKey
0x18000d5d6  mov     ebx, eax
0x18000d5d8  test    eax, eax
0x18000d5da  js      short loc_18000D630
0x18000d5dc  mov     eax, 0AAh
0x18000d5e1  lea     rcx, word_1800136B0
0x18000d5e8  xorps   xmm0, xmm0
0x18000d5eb  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000d5ef  mov     [rbp+DestinationString.MaximumLength], ax
0x18000d5f3  mov     [rbp+DestinationString.Buffer], rcx
0x18000d5f7  cmp     ax, [rbp+SourceString.Length]
0x18000d5fb  jb      short loc_18000D61B
0x18000d5fd  lea     rdx, [rbp+SourceString]; SourceString
0x18000d601  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000d605  call    cs:__imp_RtlCopyUnicodeString
0x18000d60c  nop     dword ptr [rax+rax+00h]
0x18000d611  mov     cs:dword_1800136A4, 1
0x18000d61b  mov     rax, [rbp+arg_18]
0x18000d61f  jmp     short loc_18000D62D
0x18000d621  mov     rax, [rbp+KeyHandle]
0x18000d625  mov     [rbp+KeyHandle], 0
0x18000d62d  mov     [rsi], rax
0x18000d630  mov     rcx, rdi
0x18000d633  call    FreeMemory
0x18000d638  jmp     short loc_18000D691
0x18000d63a  mov     ebx, 0C0000017h
0x18000d63f  jmp     short loc_18000D691
0x18000d641  mov     eax, 0AAh
0x18000d646  lea     rcx, word_1800136B0
0x18000d64d  xorps   xmm0, xmm0
0x18000d650  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000d654  mov     [rbp+DestinationString.MaximumLength], ax
0x18000d658  mov     [rbp+DestinationString.Buffer], rcx
0x18000d65c  cmp     ax, [rbp+var_30.Length]
0x18000d660  jb      short loc_18000D680
0x18000d662  lea     rdx, [rbp+var_30]; SourceString
0x18000d666  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000d66a  call    cs:__imp_RtlCopyUnicodeString
0x18000d671  nop     dword ptr [rax+rax+00h]
0x18000d676  mov     cs:dword_1800136A4, 1
0x18000d680  mov     rax, [rbp+KeyHandle]
0x18000d684  xor     ebx, ebx
0x18000d686  mov     [rsi], rax
0x18000d689  mov     [rbp+KeyHandle], 0
0x18000d691  mov     rcx, [rbp+KeyHandle]; Handle
0x18000d695  test    rcx, rcx
0x18000d698  jz      short loc_18000D6A6
0x18000d69a  call    cs:__imp_ZwClose
0x18000d6a1  nop     dword ptr [rax+rax+00h]
0x18000d6a6  mov     eax, ebx
0x18000d6a8  mov     rbx, [rsp+70h+arg_8]
0x18000d6b0  add     rsp, 70h
0x18000d6b4  pop     rdi
0x18000d6b5  pop     rsi
0x18000d6b6  pop     rbp
0x18000d6b7  retn
```
