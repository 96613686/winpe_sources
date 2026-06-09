# BamUserSettingsEnumerateSettingsForUser

- ea: `0x14000c9f4`
- end: `0x14000cc4d`
- name: `BamUserSettingsEnumerateSettingsForUser`
- size: `601`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000c0b0`

## callees

- `0x1400026d0`
- `0x14000bea0`
- `0x14000c9f4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000cad0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cb50`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cad0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cb50`
- `ntoskrnl!ExAllocatePool2` at `0x14000ca59`
- `ntoskrnl!ExAllocatePool2` at `0x14000cbeb`
- `ntoskrnl!ExAllocatePool2` at `0x14000ca59`
- `ntoskrnl!ExAllocatePool2` at `0x14000cbeb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cbcb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cc16`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cbcb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cc16`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000cb6d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000cb90`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000cb6d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000cb90`
- `ntoskrnl!ZwQueryKey` at `0x14000ca8e`
- `ntoskrnl!ZwQueryKey` at `0x14000ca8e`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14000cb03`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14000cb03`

## pseudocode

```c
__int64 __fastcall BamUserSettingsEnumerateSettingsForUser(
        HANDLE KeyHandle,
        struct _UNICODE_STRING *a2,
        __int64 a3,
        __int64 a4)
{
  ULONG v6; // r15d
  __int64 Pool2; // rdi
  NTSTATUS v9; // ebx
  ULONG i; // esi
  NTSTATUS v11; // eax
  ULONG v12; // ebx
  ULONG v14; // [rsp+30h] [rbp-D0h] BYREF
  ULONG ResultLength; // [rsp+34h] [rbp-CCh] BYREF
  UNICODE_STRING String1; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE KeyInformation[12]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v19; // [rsp+6Ch] [rbp-94h]
  WCHAR SourceString[192]; // [rsp+70h] [rbp-90h] BYREF

  ResultLength = 0;
  v14 = 0;
  v6 = 520;
  String1 = 0;
  DestinationString = 0;
  Pool2 = ExAllocatePool2(256, 520, 1265459522);
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  if ( a2 )
  {
    DestinationString = *a2;
    goto LABEL_8;
  }
  v9 = ZwQueryKey(KeyHandle, KeyBasicInformation, KeyInformation, 0x190u, &ResultLength);
  if ( v9 >= 0 )
  {
    if ( v19 >= 0x178 )
    {
      v9 = -1073739509;
      goto LABEL_19;
    }
    SourceString[(unsigned __int64)v19 >> 1] = 0;
    RtlInitUnicodeString(&DestinationString, SourceString);
LABEL_8:
    for ( i = 0; ; ++i )
    {
      while ( 1 )
      {
        v11 = ZwEnumerateValueKey(KeyHandle, i, KeyValueBasicInformation, (PVOID)Pool2, v6, &v14);
        v9 = v11;
        if ( v11 != -2147483643 && v11 != -1073741789 )
          break;
        ExFreePoolWithTag((PVOID)Pool2, 0x4B6D6142u);
        v12 = v14 + 2;
        Pool2 = ExAllocatePool2(256, v14 + 2, 1265459522);
        if ( !Pool2 )
          return (unsigned int)-1073741670;
        v6 = v12;
      }
      if ( v11 == -2147483622 )
        break;
      if ( v11 < 0 )
        goto LABEL_19;
      *(_WORD *)(Pool2 + 2 * ((unsigned __int64)*(unsigned int *)(Pool2 + 8) >> 1) + 12) = 0;
      RtlInitUnicodeString(&String1, (PCWSTR)(Pool2 + 12));
      if ( RtlCompareUnicodeString(&String1, &BampUserSettingsVersionValueName, 1u)
        && RtlCompareUnicodeString(&String1, &BampUserSettingsSequenceValueName, 1u) )
      {
        BampScavengeUserSettingsCallback(KeyHandle, &DestinationString, &String1, a4);
      }
    }
    v9 = 0;
  }
LABEL_19:
  ExFreePoolWithTag((PVOID)Pool2, 0x4B6D6142u);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14000c9f4  push    rbp
0x14000c9f6  push    rbx
0x14000c9f7  push    rsi
0x14000c9f8  push    rdi
0x14000c9f9  push    r12
0x14000c9fb  push    r14
0x14000c9fd  push    r15
0x14000c9ff  lea     rbp, [rsp-100h]
0x14000ca07  sub     rsp, 200h
0x14000ca0e  mov     rax, cs:__security_cookie
0x14000ca15  xor     rax, rsp
0x14000ca18  mov     [rbp+130h+var_40], rax
0x14000ca1f  xorps   xmm0, xmm0
0x14000ca22  mov     [rsp+230h+var_1FC], 0
0x14000ca2a  mov     rbx, rdx
0x14000ca2d  mov     [rsp+230h+var_200], 0
0x14000ca35  mov     r14, rcx
0x14000ca38  mov     r15d, 208h
0x14000ca3e  mov     edx, r15d
0x14000ca41  mov     r8d, 4B6D6142h
0x14000ca47  mov     ecx, 100h
0x14000ca4c  mov     r12, r9
0x14000ca4f  movups  xmmword ptr [rsp+230h+String1.Length], xmm0
0x14000ca54  movups  xmmword ptr [rsp+230h+DestinationString.Length], xmm0
0x14000ca59  call    cs:__imp_ExAllocatePool2
0x14000ca60  nop     dword ptr [rax+rax+00h]
0x14000ca65  mov     rdi, rax
0x14000ca68  test    rax, rax
0x14000ca6b  jz      loc_14000CC24
0x14000ca71  test    rbx, rbx
0x14000ca74  jnz     short loc_14000CADE
0x14000ca76  lea     rax, [rsp+230h+var_1FC]
0x14000ca7b  xor     edx, edx; KeyInformationClass
0x14000ca7d  lea     r9d, [r15-78h]; Length
0x14000ca81  mov     [rsp+230h+ResultLength], rax; ResultLength
0x14000ca86  lea     r8, [rsp+230h+KeyInformation]; KeyInformation
0x14000ca8b  mov     rcx, r14; KeyHandle
0x14000ca8e  call    cs:__imp_ZwQueryKey
0x14000ca95  nop     dword ptr [rax+rax+00h]
0x14000ca9a  mov     ebx, eax
0x14000ca9c  test    eax, eax
0x14000ca9e  js      loc_14000CC0E
0x14000caa4  cmp     [rsp+230h+var_1C4], 178h
0x14000caac  jb      short loc_14000CAB8
0x14000caae  mov     ebx, 0C000090Bh
0x14000cab3  jmp     loc_14000CC0E
0x14000cab8  mov     ecx, [rsp+230h+var_1C4]
0x14000cabc  lea     rdx, [rsp+230h+SourceString]; SourceString
0x14000cac1  shr     rcx, 1
0x14000cac4  xor     eax, eax
0x14000cac6  mov     [rsp+rcx*2+230h+SourceString], ax
0x14000cacb  lea     rcx, [rsp+230h+DestinationString]; DestinationString
0x14000cad0  call    cs:__imp_RtlInitUnicodeString
0x14000cad7  nop     dword ptr [rax+rax+00h]
0x14000cadc  jmp     short loc_14000CAE7
0x14000cade  movups  xmm0, xmmword ptr [rbx]
0x14000cae1  movdqu  xmmword ptr [rsp+230h+DestinationString.Length], xmm0
0x14000cae7  xor     esi, esi
0x14000cae9  lea     rax, [rsp+230h+var_200]
0x14000caee  mov     r9, rdi; KeyValueInformation
0x14000caf1  mov     [rsp+230h+var_208], rax; ResultLength
0x14000caf6  xor     r8d, r8d; KeyValueInformationClass
0x14000caf9  mov     edx, esi; Index
0x14000cafb  mov     dword ptr [rsp+230h+ResultLength], r15d; Length
0x14000cb00  mov     rcx, r14; KeyHandle
0x14000cb03  call    cs:__imp_ZwEnumerateValueKey
0x14000cb0a  nop     dword ptr [rax+rax+00h]
0x14000cb0f  mov     ebx, eax
0x14000cb11  cmp     eax, 80000005h
0x14000cb16  jz      loc_14000CBBE
0x14000cb1c  cmp     eax, 0C0000023h
0x14000cb21  jz      loc_14000CBBE
0x14000cb27  cmp     eax, 8000001Ah
0x14000cb2c  jz      loc_14000CC07
0x14000cb32  test    eax, eax
0x14000cb34  js      loc_14000CC09
0x14000cb3a  mov     ecx, [rdi+8]
0x14000cb3d  lea     rdx, [rdi+0Ch]; SourceString
0x14000cb41  shr     rcx, 1
0x14000cb44  xor     eax, eax
0x14000cb46  mov     [rdi+rcx*2+0Ch], ax
0x14000cb4b  lea     rcx, [rsp+230h+String1]; DestinationString
0x14000cb50  call    cs:__imp_RtlInitUnicodeString
0x14000cb57  nop     dword ptr [rax+rax+00h]
0x14000cb5c  mov     r8b, 1; CaseInSensitive
0x14000cb5f  lea     rdx, BampUserSettingsVersionValueName; String2
0x14000cb66  lea     rcx, [rsp+230h+String1]; String1
0x14000cb6b  inc     esi
0x14000cb6d  call    cs:__imp_RtlCompareUnicodeString
0x14000cb74  nop     dword ptr [rax+rax+00h]
0x14000cb79  test    eax, eax
0x14000cb7b  jz      loc_14000CAE9
0x14000cb81  mov     r8b, 1; CaseInSensitive
0x14000cb84  lea     rdx, BampUserSettingsSequenceValueName; String2
0x14000cb8b  lea     rcx, [rsp+230h+String1]; String1
0x14000cb90  call    cs:__imp_RtlCompareUnicodeString
0x14000cb97  nop     dword ptr [rax+rax+00h]
0x14000cb9c  test    eax, eax
0x14000cb9e  jz      loc_14000CAE9
0x14000cba4  mov     r9, r12
0x14000cba7  lea     r8, [rsp+230h+String1]
0x14000cbac  lea     rdx, [rsp+230h+DestinationString]
0x14000cbb1  mov     rcx, r14
0x14000cbb4  call    BampScavengeUserSettingsCallback
0x14000cbb9  jmp     loc_14000CAE9
0x14000cbbe  test    rdi, rdi
0x14000cbc1  jz      short loc_14000CBD7
0x14000cbc3  mov     edx, 4B6D6142h; Tag
0x14000cbc8  mov     rcx, rdi; P
0x14000cbcb  call    cs:__imp_ExFreePoolWithTag
0x14000cbd2  nop     dword ptr [rax+rax+00h]
0x14000cbd7  mov     ebx, [rsp+230h+var_200]
0x14000cbdb  mov     ecx, 100h
0x14000cbe0  add     ebx, 2
0x14000cbe3  mov     r8d, 4B6D6142h
0x14000cbe9  mov     edx, ebx
0x14000cbeb  call    cs:__imp_ExAllocatePool2
0x14000cbf2  nop     dword ptr [rax+rax+00h]
0x14000cbf7  mov     rdi, rax
0x14000cbfa  test    rax, rax
0x14000cbfd  jz      short loc_14000CC24
0x14000cbff  mov     r15d, ebx
0x14000cc02  jmp     loc_14000CAE9
0x14000cc07  xor     ebx, ebx
0x14000cc09  test    rdi, rdi
0x14000cc0c  jz      short loc_14000CC29
0x14000cc0e  mov     edx, 4B6D6142h; Tag
0x14000cc13  mov     rcx, rdi; P
0x14000cc16  call    cs:__imp_ExFreePoolWithTag
0x14000cc1d  nop     dword ptr [rax+rax+00h]
0x14000cc22  jmp     short loc_14000CC29
0x14000cc24  mov     ebx, 0C000009Ah
0x14000cc29  mov     eax, ebx
0x14000cc2b  mov     rcx, [rbp+130h+var_40]
0x14000cc32  xor     rcx, rsp; StackCookie
0x14000cc35  call    __security_check_cookie
0x14000cc3a  add     rsp, 200h
0x14000cc41  pop     r15
0x14000cc43  pop     r14
0x14000cc45  pop     r12
0x14000cc47  pop     rdi
0x14000cc48  pop     rsi
0x14000cc49  pop     rbx
0x14000cc4a  pop     rbp
0x14000cc4b  retn
```
