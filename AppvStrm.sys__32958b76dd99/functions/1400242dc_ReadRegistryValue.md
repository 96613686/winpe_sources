# ReadRegistryValue

- ea: `0x1400242dc`
- end: `0x1400244a7`
- name: `ReadRegistryValue`
- size: `459`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *, __int64, PVOID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002409c`

## callees

- `0x140015118`
- `0x1400242dc`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140024371`
- `ntoskrnl!ZwOpenKey` at `0x140024371`
- `ntoskrnl!ZwQueryValueKey` at `0x1400243af`
- `ntoskrnl!ZwQueryValueKey` at `0x14002441d`
- `ntoskrnl!ZwQueryValueKey` at `0x1400243af`
- `ntoskrnl!ZwQueryValueKey` at `0x14002441d`
- `ntoskrnl!ZwClose` at `0x140024453`
- `ntoskrnl!ZwClose` at `0x1400244bf`
- `ntoskrnl!ZwClose` at `0x140024453`
- `ntoskrnl!ZwClose` at `0x1400244bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002447a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400244e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002447a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400244e5`

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
0x1400242dc  mov     r11, rsp
0x1400242df  mov     [r11+8], rbx
0x1400242e3  mov     [r11+20h], r9
0x1400242e7  mov     [r11+18h], r8d
0x1400242eb  push    rsi
0x1400242ec  push    rdi
0x1400242ed  push    r14
0x1400242ef  sub     rsp, 80h
0x1400242f6  mov     rsi, r9
0x1400242f9  mov     r14, rdx
0x1400242fc  mov     [rsp+98h+var_68], 0C0000001h
0x140024304  mov     qword ptr [r11-60h], 0
0x14002430c  xor     eax, eax
0x14002430e  xorps   xmm0, xmm0
0x140024311  movups  [rsp+98h+var_50], xmm0
0x140024316  movups  [rsp+98h+var_40], xmm0
0x14002431b  movups  [rsp+98h+var_40+0Ch], xmm0
0x140024320  mov     [r11-58h], rax
0x140024324  mov     [r11+18h], eax
0x140024328  test    rcx, rcx
0x14002432b  jz      loc_140024440
0x140024331  test    rdx, rdx
0x140024334  jz      loc_140024440
0x14002433a  test    r9, r9
0x14002433d  jz      loc_140024440
0x140024343  mov     [r9], rax
0x140024346  mov     dword ptr [rsp+98h+var_50], 30h ; '0'
0x14002434e  mov     [r11-48h], rax
0x140024352  mov     dword ptr [rsp+98h+var_40+8], 240h
0x14002435a  mov     [r11-40h], rcx
0x14002435e  movdqu  [rsp+98h+var_30], xmm0
0x140024364  lea     r8, [r11-50h]; ObjectAttributes
0x140024368  mov     edx, 20019h; DesiredAccess
0x14002436d  lea     rcx, [r11-60h]; KeyHandle
0x140024371  call    cs:__imp_ZwOpenKey
0x140024378  nop     dword ptr [rax+rax+00h]
0x14002437d  mov     ebx, eax
0x14002437f  mov     [rsp+98h+var_68], eax
0x140024383  test    eax, eax
0x140024385  js      loc_140024449
0x14002438b  lea     rax, [rsp+98h+arg_10]
0x140024393  mov     [rsp+98h+ResultLength], rax; ResultLength
0x140024398  mov     [rsp+98h+Length], 0; Length
0x1400243a0  xor     r9d, r9d; KeyValueInformation
0x1400243a3  lea     r8d, [r9+1]; KeyValueInformationClass
0x1400243a7  mov     rdx, r14; ValueName
0x1400243aa  mov     rcx, [rsp+98h+KeyHandle]; KeyHandle
0x1400243af  call    cs:__imp_ZwQueryValueKey
0x1400243b6  nop     dword ptr [rax+rax+00h]
0x1400243bb  mov     ebx, eax
0x1400243bd  mov     [rsp+98h+var_68], eax
0x1400243c1  cmp     eax, 0C0000023h
0x1400243c6  jz      short loc_1400243CF
0x1400243c8  cmp     eax, 80000005h
0x1400243cd  jnz     short loc_140024449
0x1400243cf  mov     edx, [rsp+98h+arg_10]
0x1400243d6  lea     r8, [rsp+98h+KeyValueInformation]
0x1400243db  mov     ecx, 100h
0x1400243e0  call    AllocateGenericBuffer
0x1400243e5  mov     ebx, eax
0x1400243e7  mov     [rsp+98h+var_68], eax
0x1400243eb  test    eax, eax
0x1400243ed  js      short loc_140024449
0x1400243ef  mov     eax, [rsp+98h+arg_10]
0x1400243f6  lea     rcx, [rsp+98h+arg_10]
0x1400243fe  mov     [rsp+98h+ResultLength], rcx; ResultLength
0x140024403  mov     [rsp+98h+Length], eax; Length
0x140024407  mov     rdi, [rsp+98h+KeyValueInformation]
0x14002440c  mov     r9, rdi; KeyValueInformation
0x14002440f  mov     r8d, 1; KeyValueInformationClass
0x140024415  mov     rdx, r14; ValueName
0x140024418  mov     rcx, [rsp+98h+KeyHandle]; KeyHandle
0x14002441d  call    cs:__imp_ZwQueryValueKey
0x140024424  nop     dword ptr [rax+rax+00h]
0x140024429  mov     ebx, eax
0x14002442b  mov     [rsp+98h+var_68], eax
0x14002442f  test    eax, eax
0x140024431  js      short loc_140024449
0x140024433  cmp     dword ptr [rdi+4], 4
0x140024437  jz      short loc_140024449
0x140024439  mov     ebx, 0C0000001h
0x14002443e  jmp     short loc_140024445
0x140024440  mov     ebx, 0C000000Dh
0x140024445  mov     [rsp+98h+var_68], ebx
0x140024449  mov     rcx, [rsp+98h+KeyHandle]; Handle
0x14002444e  test    rcx, rcx
0x140024451  jz      short loc_14002445F
0x140024453  call    cs:__imp_ZwClose
0x14002445a  nop     dword ptr [rax+rax+00h]
0x14002445f  mov     rdi, [rsp+98h+KeyValueInformation]
0x140024464  test    rdi, rdi
0x140024467  jz      short loc_140024490
0x140024469  test    ebx, ebx
0x14002446b  jns     short loc_140024488
0x14002446d  test    rdi, rdi
0x140024470  jz      short loc_140024490
0x140024472  mov     edx, 676C6462h; Tag
0x140024477  mov     rcx, rdi; P
0x14002447a  call    cs:__imp_ExFreePoolWithTag
0x140024481  nop     dword ptr [rax+rax+00h]
0x140024486  jmp     short loc_140024490
0x140024488  mov     rax, [rsp+98h+KeyValueInformation]
0x14002448d  mov     [rsi], rax
0x140024490  mov     eax, ebx
0x140024492  mov     rbx, [rsp+98h+arg_0]
0x14002449a  add     rsp, 80h
0x1400244a1  pop     r14
0x1400244a3  pop     rdi
0x1400244a4  pop     rsi
0x1400244a5  retn
0x1400244ad  push    rbp
0x1400244af  sub     rsp, 30h
0x1400244b3  mov     rbp, rdx
0x1400244b6  mov     rcx, [rbp+38h]; Handle
0x1400244ba  test    rcx, rcx
0x1400244bd  jz      short loc_1400244CC
0x1400244bf  call    cs:__imp_ZwClose
0x1400244c6  nop     dword ptr [rax+rax+00h]
0x1400244cb  nop
0x1400244cc  mov     rcx, [rbp+40h]; P
0x1400244d0  test    rcx, rcx
0x1400244d3  jz      short loc_1400244FD
0x1400244d5  cmp     dword ptr [rbp+30h], 0
0x1400244d9  jge     short loc_1400244F3
0x1400244db  test    rcx, rcx
0x1400244de  jz      short loc_1400244FD
0x1400244e0  mov     edx, 676C6462h; Tag
0x1400244e5  call    cs:__imp_ExFreePoolWithTag
0x1400244ec  nop     dword ptr [rax+rax+00h]
0x1400244f1  jmp     short loc_1400244FD
0x1400244f3  mov     rax, [rbp+0B8h]
0x1400244fa  mov     [rax], rcx
0x1400244fd  add     rsp, 30h
0x140024501  pop     rbp
0x140024502  retn
```
