# BfsReadDeleteThresholdFromRegistry

- ea: `0x14000d140`
- end: `0x14000d3f0`
- name: `BfsReadDeleteThresholdFromRegistry`
- size: `688`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001f078`

## callees

- `0x140001008`
- `0x14000d140`
- `0x140013730`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14000d1de`
- `ntoskrnl!ZwOpenKey` at `0x14000d1de`
- `ntoskrnl!ZwQueryValueKey` at `0x14000d249`
- `ntoskrnl!ZwQueryValueKey` at `0x14000d2bb`
- `ntoskrnl!ZwQueryValueKey` at `0x14000d31c`
- `ntoskrnl!ZwQueryValueKey` at `0x14000d37f`
- `ntoskrnl!ZwQueryValueKey` at `0x14000d249`
- `ntoskrnl!ZwQueryValueKey` at `0x14000d2bb`
- `ntoskrnl!ZwQueryValueKey` at `0x14000d31c`
- `ntoskrnl!ZwQueryValueKey` at `0x14000d37f`
- `ntoskrnl!ZwClose` at `0x14000d3b1`
- `ntoskrnl!ZwClose` at `0x14000d3b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d2f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d3c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d2f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d3c7`
- `ntoskrnl!ExAllocatePool2` at `0x14000d26e`
- `ntoskrnl!ExAllocatePool2` at `0x14000d349`
- `ntoskrnl!ExAllocatePool2` at `0x14000d26e`
- `ntoskrnl!ExAllocatePool2` at `0x14000d349`

## string_xrefs

- `0x14000d16c`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\FileSystem`

## pseudocode

```c
__int64 BfsReadDeleteThresholdFromRegistry()
{
  unsigned int v0; // edi
  _DWORD *Pool2; // rbx
  NTSTATUS v2; // ecx
  int v3; // r8d
  int v4; // r9d
  ULONG v5; // esi
  NTSTATUS v6; // eax
  ULONG v7; // esi
  unsigned int v8; // eax
  ULONG Length; // [rsp+20h] [rbp-89h]
  int v11; // [rsp+30h] [rbp-79h] BYREF
  ULONG ResultLength; // [rsp+34h] [rbp-75h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-71h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-69h] BYREF
  struct _UNICODE_STRING v15; // [rsp+50h] [rbp-59h] BYREF
  _QWORD v16[2]; // [rsp+60h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+A0h] [rbp-9h] BYREF
  int *v19; // [rsp+C0h] [rbp+17h]
  __int64 v20; // [rsp+C8h] [rbp+1Fh]

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v16[1] = L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\FileSystem";
  KeyHandle = 0;
  ValueName.Buffer = L"MaximumTunnelEntries";
  ResultLength = 0;
  v15.Buffer = L"MaximumTunnelEntryAgeInSeconds";
  v16[0] = 8126586;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v16;
  v0 = 150000000;
  *(_QWORD *)&ValueName.Length = 2752552;
  Pool2 = 0;
  *(_QWORD *)&v15.Length = 4063292;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v2 < 0 )
    goto LABEL_2;
  v2 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, 0, 0, &ResultLength);
  if ( v2 != -1073741789 )
    goto LABEL_2;
  v5 = ResultLength;
  Pool2 = (_DWORD *)ExAllocatePool2(256, ResultLength, 1985111618);
  if ( !Pool2 )
    goto LABEL_7;
  v6 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, Pool2, v5, &ResultLength);
  if ( v6 < 0 )
  {
    if ( v6 != -1073741772 )
      goto LABEL_22;
  }
  else
  {
    if ( Pool2[1] != 4 )
      goto LABEL_22;
    if ( !Pool2[3] )
    {
      v0 = 0;
      goto LABEL_22;
    }
  }
  ExFreePoolWithTag(Pool2, 0);
  v2 = ZwQueryValueKey(KeyHandle, &v15, KeyValuePartialInformation, 0, 0, &ResultLength);
  if ( v2 != -1073741789 )
  {
    Pool2 = 0;
LABEL_2:
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_22;
    v11 = v2;
    goto LABEL_4;
  }
  v7 = ResultLength;
  Pool2 = (_DWORD *)ExAllocatePool2(256, ResultLength, 1985111618);
  if ( Pool2 )
  {
    if ( ZwQueryValueKey(KeyHandle, &v15, KeyValuePartialInformation, Pool2, v7, &ResultLength) >= 0 && Pool2[1] == 4 )
    {
      v8 = Pool2[3];
      if ( v8 > 0x47 )
        v8 = 71;
      v0 = 10000000 * v8;
    }
    goto LABEL_22;
  }
LABEL_7:
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v11 = -1073741801;
LABEL_4:
    v20 = 4;
    v19 = &v11;
    tlgWriteTransfer_EtwWriteTransfer(v2, (int)&byte_140016D91, v3, v4, Length, &v18);
  }
LABEL_22:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0);
  return v0;
}

```

## disassembly

```asm
0x14000d140  push    rbp
0x14000d142  push    rbx
0x14000d143  push    rsi
0x14000d144  push    rdi
0x14000d145  push    r14
0x14000d147  lea     rbp, [rsp-37h]
0x14000d14c  sub     rsp, 0E0h
0x14000d153  mov     rax, cs:__security_cookie
0x14000d15a  xor     rax, rsp
0x14000d15d  mov     [rbp+57h+var_30], rax
0x14000d161  xor     r14d, r14d
0x14000d164  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000d16c  lea     rax, aRegistryMachin; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x14000d173  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x14000d17b  mov     [rbp+57h+var_98], rax
0x14000d17f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000d183  lea     rax, aMaximumtunnele_0; "MaximumTunnelEntries"
0x14000d18a  mov     [rbp+57h+KeyHandle], r14
0x14000d18e  mov     [rbp+57h+ValueName.Buffer], rax
0x14000d192  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d196  lea     rax, aMaximumtunnele; "MaximumTunnelEntryAgeInSeconds"
0x14000d19d  mov     [rbp+57h+var_CC], r14d
0x14000d1a1  mov     [rbp+57h+var_B0.Buffer], rax
0x14000d1a5  xorps   xmm0, xmm0
0x14000d1a8  lea     rax, [rbp+57h+var_A0]
0x14000d1ac  mov     [rbp+57h+var_A0], 7C007Ah
0x14000d1b4  mov     edx, 20019h; DesiredAccess
0x14000d1b9  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000d1bd  mov     edi, 8F0D180h
0x14000d1c2  mov     qword ptr [rbp+57h+ValueName.Length], 2A0028h
0x14000d1ca  mov     ebx, r14d
0x14000d1cd  mov     qword ptr [rbp+57h+var_B0.Length], 3E003Ch
0x14000d1d5  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x14000d1d9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000d1de  call    cs:__imp_ZwOpenKey
0x14000d1e5  nop     dword ptr [rax+rax+00h]
0x14000d1ea  mov     ecx, eax; int
0x14000d1ec  test    eax, eax
0x14000d1ee  jns     short loc_14000D22C
0x14000d1f0  mov     eax, cs:dword_140019000
0x14000d1f6  cmp     eax, 3
0x14000d1f9  jbe     loc_14000D3A8
0x14000d1ff  mov     [rbp+57h+var_D0], ecx
0x14000d202  lea     rax, [rbp+57h+var_D0]
0x14000d206  mov     [rbp+57h+var_38], 4
0x14000d20e  mov     [rbp+57h+var_40], rax
0x14000d212  lea     rdx, byte_140016D91; int
0x14000d219  lea     rax, [rbp+57h+var_60]
0x14000d21d  mov     [rsp+100h+ResultLength], rax; PEVENT_DATA_DESCRIPTOR
0x14000d222  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000d227  jmp     loc_14000D3A8
0x14000d22c  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d230  lea     rax, [rbp+57h+var_CC]
0x14000d234  xor     r9d, r9d; KeyValueInformation
0x14000d237  mov     [rsp+100h+ResultLength], rax; ResultLength
0x14000d23c  lea     rdx, [rbp+57h+ValueName]; ValueName
0x14000d240  mov     [rsp+100h+Length], r14d; Length
0x14000d245  lea     r8d, [r9+2]; KeyValueInformationClass
0x14000d249  call    cs:__imp_ZwQueryValueKey
0x14000d250  nop     dword ptr [rax+rax+00h]
0x14000d255  mov     ecx, eax
0x14000d257  cmp     eax, 0C0000023h
0x14000d25c  jnz     short loc_14000D1F0
0x14000d25e  mov     esi, [rbp+57h+var_CC]
0x14000d261  mov     ecx, 100h
0x14000d266  mov     edx, esi
0x14000d268  mov     r8d, 76526642h
0x14000d26e  call    cs:__imp_ExAllocatePool2
0x14000d275  nop     dword ptr [rax+rax+00h]
0x14000d27a  mov     rbx, rax
0x14000d27d  test    rax, rax
0x14000d280  jnz     short loc_14000D29D
0x14000d282  mov     eax, cs:dword_140019000
0x14000d288  cmp     eax, 3
0x14000d28b  jbe     loc_14000D3A8
0x14000d291  mov     [rbp+57h+var_D0], 0C0000017h
0x14000d298  jmp     loc_14000D202
0x14000d29d  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d2a1  lea     rax, [rbp+57h+var_CC]
0x14000d2a5  mov     [rsp+100h+ResultLength], rax; ResultLength
0x14000d2aa  lea     rdx, [rbp+57h+ValueName]; ValueName
0x14000d2ae  mov     r9, rbx; KeyValueInformation
0x14000d2b1  mov     [rsp+100h+Length], esi; Length
0x14000d2b5  mov     r8d, 2; KeyValueInformationClass
0x14000d2bb  call    cs:__imp_ZwQueryValueKey
0x14000d2c2  nop     dword ptr [rax+rax+00h]
0x14000d2c7  test    eax, eax
0x14000d2c9  js      short loc_14000D2E3
0x14000d2cb  cmp     dword ptr [rbx+4], 4
0x14000d2cf  jnz     loc_14000D3A8
0x14000d2d5  cmp     [rbx+0Ch], r14d
0x14000d2d9  jnz     short loc_14000D2EE
0x14000d2db  mov     edi, r14d
0x14000d2de  jmp     loc_14000D3A8
0x14000d2e3  cmp     eax, 0C0000034h
0x14000d2e8  jnz     loc_14000D3A8
0x14000d2ee  xor     edx, edx; Tag
0x14000d2f0  mov     rcx, rbx; P
0x14000d2f3  call    cs:__imp_ExFreePoolWithTag
0x14000d2fa  nop     dword ptr [rax+rax+00h]
0x14000d2ff  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d303  lea     rax, [rbp+57h+var_CC]
0x14000d307  xor     r9d, r9d; KeyValueInformation
0x14000d30a  mov     [rsp+100h+ResultLength], rax; ResultLength
0x14000d30f  lea     rdx, [rbp+57h+var_B0]; ValueName
0x14000d313  mov     [rsp+100h+Length], r14d; Length
0x14000d318  lea     r8d, [r9+2]; KeyValueInformationClass
0x14000d31c  call    cs:__imp_ZwQueryValueKey
0x14000d323  nop     dword ptr [rax+rax+00h]
0x14000d328  mov     ecx, eax
0x14000d32a  cmp     eax, 0C0000023h
0x14000d32f  jz      short loc_14000D339
0x14000d331  mov     rbx, r14
0x14000d334  jmp     loc_14000D1F0
0x14000d339  mov     esi, [rbp+57h+var_CC]
0x14000d33c  mov     ecx, 100h
0x14000d341  mov     edx, esi
0x14000d343  mov     r8d, 76526642h
0x14000d349  call    cs:__imp_ExAllocatePool2
0x14000d350  nop     dword ptr [rax+rax+00h]
0x14000d355  mov     rbx, rax
0x14000d358  test    rax, rax
0x14000d35b  jz      loc_14000D282
0x14000d361  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000d365  lea     rax, [rbp+57h+var_CC]
0x14000d369  mov     [rsp+100h+ResultLength], rax; ResultLength
0x14000d36e  lea     rdx, [rbp+57h+var_B0]; ValueName
0x14000d372  mov     r9, rbx; KeyValueInformation
0x14000d375  mov     [rsp+100h+Length], esi; Length
0x14000d379  mov     r8d, 2; KeyValueInformationClass
0x14000d37f  call    cs:__imp_ZwQueryValueKey
0x14000d386  nop     dword ptr [rax+rax+00h]
0x14000d38b  test    eax, eax
0x14000d38d  js      short loc_14000D3A8
0x14000d38f  cmp     dword ptr [rbx+4], 4
0x14000d393  jnz     short loc_14000D3A8
0x14000d395  mov     eax, [rbx+0Ch]
0x14000d398  mov     ecx, 47h ; 'G'
0x14000d39d  cmp     eax, ecx
0x14000d39f  cmova   eax, ecx
0x14000d3a2  imul    edi, eax, 989680h
0x14000d3a8  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14000d3ac  test    rcx, rcx
0x14000d3af  jz      short loc_14000D3BD
0x14000d3b1  call    cs:__imp_ZwClose
0x14000d3b8  nop     dword ptr [rax+rax+00h]
0x14000d3bd  test    rbx, rbx
0x14000d3c0  jz      short loc_14000D3D3
0x14000d3c2  xor     edx, edx; Tag
0x14000d3c4  mov     rcx, rbx; P
0x14000d3c7  call    cs:__imp_ExFreePoolWithTag
0x14000d3ce  nop     dword ptr [rax+rax+00h]
0x14000d3d3  mov     eax, edi
0x14000d3d5  mov     rcx, [rbp+57h+var_30]
0x14000d3d9  xor     rcx, rsp; StackCookie
0x14000d3dc  call    __security_check_cookie
0x14000d3e1  add     rsp, 0E0h
0x14000d3e8  pop     r14
0x14000d3ea  pop     rdi
0x14000d3eb  pop     rsi
0x14000d3ec  pop     rbx
0x14000d3ed  pop     rbp
0x14000d3ee  retn
```
