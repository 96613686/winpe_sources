# ReadRegistryValue

- ea: `0x18002e2b8`
- end: `0x18002e483`
- name: `ReadRegistryValue`
- size: `459`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *, __int64, PVOID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002e078`

## callees

- `0x18001b120`
- `0x18002e2b8`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x18002e38b`
- `ntoskrnl!ZwQueryValueKey` at `0x18002e3f9`
- `ntoskrnl!ZwQueryValueKey` at `0x18002e38b`
- `ntoskrnl!ZwQueryValueKey` at `0x18002e3f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002e456`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002e4c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002e456`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002e4c1`
- `ntoskrnl!ZwClose` at `0x18002e42f`
- `ntoskrnl!ZwClose` at `0x18002e49b`
- `ntoskrnl!ZwClose` at `0x18002e42f`
- `ntoskrnl!ZwClose` at `0x18002e49b`
- `ntoskrnl!ZwOpenKey` at `0x18002e34d`
- `ntoskrnl!ZwOpenKey` at `0x18002e34d`

## pseudocode

```c
__int64 __fastcall ReadRegistryValue(struct _UNICODE_STRING *a1, struct _UNICODE_STRING *a2, __int64 a3, PVOID *a4)
{
  NTSTATUS v6; // ebx
  NTSTATUS v7; // eax
  _DWORD *v8; // rdi
  HANDLE KeyHandle; // [rsp+38h] [rbp-60h] BYREF
  PVOID KeyValueInformation; // [rsp+40h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES v12; // [rsp+48h] [rbp-50h] BYREF
  ULONG ResultLength; // [rsp+B0h] [rbp+18h] BYREF
  PVOID *v14; // [rsp+B8h] [rbp+20h]

  v14 = a4;
  KeyHandle = 0;
  memset(&v12, 0, 44);
  KeyValueInformation = 0;
  ResultLength = 0;
  if ( a1 && a2 && a4 )
  {
    *a4 = 0;
    v12.Length = 48;
    v12.RootDirectory = 0;
    v12.Attributes = 576;
    v12.ObjectName = a1;
    *(_OWORD *)&v12.SecurityDescriptor = 0;
    v6 = ZwOpenKey(&KeyHandle, 0x20019u, &v12);
    if ( v6 >= 0 )
    {
      v7 = ZwQueryValueKey(KeyHandle, a2, KeyValueFullInformation, 0, 0, &ResultLength);
      v6 = v7;
      if ( v7 == -1073741789 || v7 == -2147483643 )
      {
        v6 = AllocateGenericBuffer(256, ResultLength, &KeyValueInformation);
        if ( v6 >= 0 )
        {
          v8 = KeyValueInformation;
          v6 = ZwQueryValueKey(KeyHandle, a2, KeyValueFullInformation, KeyValueInformation, ResultLength, &ResultLength);
          if ( v6 >= 0 && v8[1] != 4 )
            v6 = -1073741823;
        }
      }
    }
  }
  else
  {
    v6 = -1073741811;
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( KeyValueInformation )
  {
    if ( v6 >= 0 )
      *a4 = KeyValueInformation;
    else
      ExFreePoolWithTag(KeyValueInformation, 0x676C6462u);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002e2b8  mov     r11, rsp
0x18002e2bb  mov     [r11+8], rbx
0x18002e2bf  mov     [r11+20h], r9
0x18002e2c3  mov     [r11+18h], r8d
0x18002e2c7  push    rsi
0x18002e2c8  push    rdi
0x18002e2c9  push    r14
0x18002e2cb  sub     rsp, 80h
0x18002e2d2  mov     rsi, r9
0x18002e2d5  mov     r14, rdx
0x18002e2d8  mov     [rsp+98h+var_68], 0C0000001h
0x18002e2e0  mov     qword ptr [r11-60h], 0
0x18002e2e8  xor     eax, eax
0x18002e2ea  xorps   xmm0, xmm0
0x18002e2ed  movups  [rsp+98h+var_50], xmm0
0x18002e2f2  movups  [rsp+98h+var_40], xmm0
0x18002e2f7  movups  [rsp+98h+var_40+0Ch], xmm0
0x18002e2fc  mov     [r11-58h], rax
0x18002e300  mov     [r11+18h], eax
0x18002e304  test    rcx, rcx
0x18002e307  jz      loc_18002E41C
0x18002e30d  test    rdx, rdx
0x18002e310  jz      loc_18002E41C
0x18002e316  test    r9, r9
0x18002e319  jz      loc_18002E41C
0x18002e31f  mov     [r9], rax
0x18002e322  mov     dword ptr [rsp+98h+var_50], 30h ; '0'
0x18002e32a  mov     [r11-48h], rax
0x18002e32e  mov     dword ptr [rsp+98h+var_40+8], 240h
0x18002e336  mov     [r11-40h], rcx
0x18002e33a  movdqu  [rsp+98h+var_30], xmm0
0x18002e340  lea     r8, [r11-50h]; ObjectAttributes
0x18002e344  mov     edx, 20019h; DesiredAccess
0x18002e349  lea     rcx, [r11-60h]; KeyHandle
0x18002e34d  call    cs:__imp_ZwOpenKey
0x18002e354  nop     dword ptr [rax+rax+00h]
0x18002e359  mov     ebx, eax
0x18002e35b  mov     [rsp+98h+var_68], eax
0x18002e35f  test    eax, eax
0x18002e361  js      loc_18002E425
0x18002e367  lea     rax, [rsp+98h+arg_10]
0x18002e36f  mov     [rsp+98h+ResultLength], rax; ResultLength
0x18002e374  mov     [rsp+98h+Length], 0; Length
0x18002e37c  xor     r9d, r9d; KeyValueInformation
0x18002e37f  lea     r8d, [r9+1]; KeyValueInformationClass
0x18002e383  mov     rdx, r14; ValueName
0x18002e386  mov     rcx, [rsp+98h+KeyHandle]; KeyHandle
0x18002e38b  call    cs:__imp_ZwQueryValueKey
0x18002e392  nop     dword ptr [rax+rax+00h]
0x18002e397  mov     ebx, eax
0x18002e399  mov     [rsp+98h+var_68], eax
0x18002e39d  cmp     eax, 0C0000023h
0x18002e3a2  jz      short loc_18002E3AB
0x18002e3a4  cmp     eax, 80000005h
0x18002e3a9  jnz     short loc_18002E425
0x18002e3ab  mov     edx, [rsp+98h+arg_10]
0x18002e3b2  lea     r8, [rsp+98h+KeyValueInformation]
0x18002e3b7  mov     ecx, 100h
0x18002e3bc  call    AllocateGenericBuffer
0x18002e3c1  mov     ebx, eax
0x18002e3c3  mov     [rsp+98h+var_68], eax
0x18002e3c7  test    eax, eax
0x18002e3c9  js      short loc_18002E425
0x18002e3cb  mov     eax, [rsp+98h+arg_10]
0x18002e3d2  lea     rcx, [rsp+98h+arg_10]
0x18002e3da  mov     [rsp+98h+ResultLength], rcx; ResultLength
0x18002e3df  mov     [rsp+98h+Length], eax; Length
0x18002e3e3  mov     rdi, [rsp+98h+KeyValueInformation]
0x18002e3e8  mov     r9, rdi; KeyValueInformation
0x18002e3eb  mov     r8d, 1; KeyValueInformationClass
0x18002e3f1  mov     rdx, r14; ValueName
0x18002e3f4  mov     rcx, [rsp+98h+KeyHandle]; KeyHandle
0x18002e3f9  call    cs:__imp_ZwQueryValueKey
0x18002e400  nop     dword ptr [rax+rax+00h]
0x18002e405  mov     ebx, eax
0x18002e407  mov     [rsp+98h+var_68], eax
0x18002e40b  test    eax, eax
0x18002e40d  js      short loc_18002E425
0x18002e40f  cmp     dword ptr [rdi+4], 4
0x18002e413  jz      short loc_18002E425
0x18002e415  mov     ebx, 0C0000001h
0x18002e41a  jmp     short loc_18002E421
0x18002e41c  mov     ebx, 0C000000Dh
0x18002e421  mov     [rsp+98h+var_68], ebx
0x18002e425  mov     rcx, [rsp+98h+KeyHandle]; Handle
0x18002e42a  test    rcx, rcx
0x18002e42d  jz      short loc_18002E43B
0x18002e42f  call    cs:__imp_ZwClose
0x18002e436  nop     dword ptr [rax+rax+00h]
0x18002e43b  mov     rdi, [rsp+98h+KeyValueInformation]
0x18002e440  test    rdi, rdi
0x18002e443  jz      short loc_18002E46C
0x18002e445  test    ebx, ebx
0x18002e447  jns     short loc_18002E464
0x18002e449  test    rdi, rdi
0x18002e44c  jz      short loc_18002E46C
0x18002e44e  mov     edx, 676C6462h; Tag
0x18002e453  mov     rcx, rdi; P
0x18002e456  call    cs:__imp_ExFreePoolWithTag
0x18002e45d  nop     dword ptr [rax+rax+00h]
0x18002e462  jmp     short loc_18002E46C
0x18002e464  mov     rax, [rsp+98h+KeyValueInformation]
0x18002e469  mov     [rsi], rax
0x18002e46c  mov     eax, ebx
0x18002e46e  mov     rbx, [rsp+98h+arg_0]
0x18002e476  add     rsp, 80h
0x18002e47d  pop     r14
0x18002e47f  pop     rdi
0x18002e480  pop     rsi
0x18002e481  retn
0x18002e489  push    rbp
0x18002e48b  sub     rsp, 30h
0x18002e48f  mov     rbp, rdx
0x18002e492  mov     rcx, [rbp+38h]; Handle
0x18002e496  test    rcx, rcx
0x18002e499  jz      short loc_18002E4A8
0x18002e49b  call    cs:__imp_ZwClose
0x18002e4a2  nop     dword ptr [rax+rax+00h]
0x18002e4a7  nop
0x18002e4a8  mov     rcx, [rbp+40h]; P
0x18002e4ac  test    rcx, rcx
0x18002e4af  jz      short loc_18002E4D9
0x18002e4b1  cmp     dword ptr [rbp+30h], 0
0x18002e4b5  jge     short loc_18002E4CF
0x18002e4b7  test    rcx, rcx
0x18002e4ba  jz      short loc_18002E4D9
0x18002e4bc  mov     edx, 676C6462h; Tag
0x18002e4c1  call    cs:__imp_ExFreePoolWithTag
0x18002e4c8  nop     dword ptr [rax+rax+00h]
0x18002e4cd  jmp     short loc_18002E4D9
0x18002e4cf  mov     rax, [rbp+0B8h]
0x18002e4d6  mov     [rax], rcx
0x18002e4d9  add     rsp, 30h
0x18002e4dd  pop     rbp
0x18002e4de  retn
```
