# ReadRegistryValue

- ea: `0x1400272dc`
- end: `0x1400274a7`
- name: `ReadRegistryValue`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002709c`

## callees

- `0x140012720`
- `0x1400272dc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140027453`
- `ntoskrnl!ZwClose` at `0x1400274bf`
- `ntoskrnl!ZwClose` at `0x140027453`
- `ntoskrnl!ZwClose` at `0x1400274bf`
- `ntoskrnl!ZwQueryValueKey` at `0x1400273af`
- `ntoskrnl!ZwQueryValueKey` at `0x14002741d`
- `ntoskrnl!ZwQueryValueKey` at `0x1400273af`
- `ntoskrnl!ZwQueryValueKey` at `0x14002741d`
- `ntoskrnl!ZwOpenKey` at `0x140027371`
- `ntoskrnl!ZwOpenKey` at `0x140027371`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002747a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400274e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002747a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400274e5`

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
0x1400272dc  mov     r11, rsp
0x1400272df  mov     [r11+8], rbx
0x1400272e3  mov     [r11+20h], r9
0x1400272e7  mov     [r11+18h], r8d
0x1400272eb  push    rsi
0x1400272ec  push    rdi
0x1400272ed  push    r14
0x1400272ef  sub     rsp, 80h
0x1400272f6  mov     rsi, r9
0x1400272f9  mov     r14, rdx
0x1400272fc  mov     [rsp+98h+var_68], 0C0000001h
0x140027304  mov     qword ptr [r11-60h], 0
0x14002730c  xor     eax, eax
0x14002730e  xorps   xmm0, xmm0
0x140027311  movups  [rsp+98h+var_50], xmm0
0x140027316  movups  [rsp+98h+var_40], xmm0
0x14002731b  movups  [rsp+98h+var_40+0Ch], xmm0
0x140027320  mov     [r11-58h], rax
0x140027324  mov     [r11+18h], eax
0x140027328  test    rcx, rcx
0x14002732b  jz      loc_140027440
0x140027331  test    rdx, rdx
0x140027334  jz      loc_140027440
0x14002733a  test    r9, r9
0x14002733d  jz      loc_140027440
0x140027343  mov     [r9], rax
0x140027346  mov     dword ptr [rsp+98h+var_50], 30h ; '0'
0x14002734e  mov     [r11-48h], rax
0x140027352  mov     dword ptr [rsp+98h+var_40+8], 240h
0x14002735a  mov     [r11-40h], rcx
0x14002735e  movdqu  [rsp+98h+var_30], xmm0
0x140027364  lea     r8, [r11-50h]; ObjectAttributes
0x140027368  mov     edx, 20019h; DesiredAccess
0x14002736d  lea     rcx, [r11-60h]; KeyHandle
0x140027371  call    cs:__imp_ZwOpenKey
0x140027378  nop     dword ptr [rax+rax+00h]
0x14002737d  mov     ebx, eax
0x14002737f  mov     [rsp+98h+var_68], eax
0x140027383  test    eax, eax
0x140027385  js      loc_140027449
0x14002738b  lea     rax, [rsp+98h+arg_10]
0x140027393  mov     [rsp+98h+ResultLength], rax; ResultLength
0x140027398  mov     [rsp+98h+Length], 0; Length
0x1400273a0  xor     r9d, r9d; KeyValueInformation
0x1400273a3  lea     r8d, [r9+1]; KeyValueInformationClass
0x1400273a7  mov     rdx, r14; ValueName
0x1400273aa  mov     rcx, [rsp+98h+KeyHandle]; KeyHandle
0x1400273af  call    cs:__imp_ZwQueryValueKey
0x1400273b6  nop     dword ptr [rax+rax+00h]
0x1400273bb  mov     ebx, eax
0x1400273bd  mov     [rsp+98h+var_68], eax
0x1400273c1  cmp     eax, 0C0000023h
0x1400273c6  jz      short loc_1400273CF
0x1400273c8  cmp     eax, 80000005h
0x1400273cd  jnz     short loc_140027449
0x1400273cf  mov     edx, [rsp+98h+arg_10]
0x1400273d6  lea     r8, [rsp+98h+KeyValueInformation]
0x1400273db  mov     ecx, 100h
0x1400273e0  call    AllocateGenericBuffer
0x1400273e5  mov     ebx, eax
0x1400273e7  mov     [rsp+98h+var_68], eax
0x1400273eb  test    eax, eax
0x1400273ed  js      short loc_140027449
0x1400273ef  mov     eax, [rsp+98h+arg_10]
0x1400273f6  lea     rcx, [rsp+98h+arg_10]
0x1400273fe  mov     [rsp+98h+ResultLength], rcx; ResultLength
0x140027403  mov     [rsp+98h+Length], eax; Length
0x140027407  mov     rdi, [rsp+98h+KeyValueInformation]
0x14002740c  mov     r9, rdi; KeyValueInformation
0x14002740f  mov     r8d, 1; KeyValueInformationClass
0x140027415  mov     rdx, r14; ValueName
0x140027418  mov     rcx, [rsp+98h+KeyHandle]; KeyHandle
0x14002741d  call    cs:__imp_ZwQueryValueKey
0x140027424  nop     dword ptr [rax+rax+00h]
0x140027429  mov     ebx, eax
0x14002742b  mov     [rsp+98h+var_68], eax
0x14002742f  test    eax, eax
0x140027431  js      short loc_140027449
0x140027433  cmp     dword ptr [rdi+4], 4
0x140027437  jz      short loc_140027449
0x140027439  mov     ebx, 0C0000001h
0x14002743e  jmp     short loc_140027445
0x140027440  mov     ebx, 0C000000Dh
0x140027445  mov     [rsp+98h+var_68], ebx
0x140027449  mov     rcx, [rsp+98h+KeyHandle]; Handle
0x14002744e  test    rcx, rcx
0x140027451  jz      short loc_14002745F
0x140027453  call    cs:__imp_ZwClose
0x14002745a  nop     dword ptr [rax+rax+00h]
0x14002745f  mov     rdi, [rsp+98h+KeyValueInformation]
0x140027464  test    rdi, rdi
0x140027467  jz      short loc_140027490
0x140027469  test    ebx, ebx
0x14002746b  jns     short loc_140027488
0x14002746d  test    rdi, rdi
0x140027470  jz      short loc_140027490
0x140027472  mov     edx, 676C6462h; Tag
0x140027477  mov     rcx, rdi; P
0x14002747a  call    cs:__imp_ExFreePoolWithTag
0x140027481  nop     dword ptr [rax+rax+00h]
0x140027486  jmp     short loc_140027490
0x140027488  mov     rax, [rsp+98h+KeyValueInformation]
0x14002748d  mov     [rsi], rax
0x140027490  mov     eax, ebx
0x140027492  mov     rbx, [rsp+98h+arg_0]
0x14002749a  add     rsp, 80h
0x1400274a1  pop     r14
0x1400274a3  pop     rdi
0x1400274a4  pop     rsi
0x1400274a5  retn
0x1400274ad  push    rbp
0x1400274af  sub     rsp, 30h
0x1400274b3  mov     rbp, rdx
0x1400274b6  mov     rcx, [rbp+38h]; Handle
0x1400274ba  test    rcx, rcx
0x1400274bd  jz      short loc_1400274CC
0x1400274bf  call    cs:__imp_ZwClose
0x1400274c6  nop     dword ptr [rax+rax+00h]
0x1400274cb  nop
0x1400274cc  mov     rcx, [rbp+40h]; P
0x1400274d0  test    rcx, rcx
0x1400274d3  jz      short loc_1400274FD
0x1400274d5  cmp     dword ptr [rbp+30h], 0
0x1400274d9  jge     short loc_1400274F3
0x1400274db  test    rcx, rcx
0x1400274de  jz      short loc_1400274FD
0x1400274e0  mov     edx, 676C6462h; Tag
0x1400274e5  call    cs:__imp_ExFreePoolWithTag
0x1400274ec  nop     dword ptr [rax+rax+00h]
0x1400274f1  jmp     short loc_1400274FD
0x1400274f3  mov     rax, [rbp+0B8h]
0x1400274fa  mov     [rax], rcx
0x1400274fd  add     rsp, 30h
0x140027501  pop     rbp
0x140027502  retn
```
