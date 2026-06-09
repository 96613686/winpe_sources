# FveRegistryGetValue

- ea: `0x18006c3a8`
- end: `0x18006c50e`
- name: `FveRegistryGetValue`
- size: `358`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006c148`
- `0x18006c278`

## callees

- `0x1800031e6`
- `0x18006a2ac`
- `0x18006a3f0`
- `0x18006c3a8`

## import_xrefs

- `ntdll!NtClose` at `0x18006c4ed`
- `ntdll!NtClose` at `0x18006c4ed`
- `ntdll!NtOpenKey` at `0x18006c404`
- `ntdll!NtOpenKey` at `0x18006c404`
- `ntdll!NtQueryValueKey` at `0x18006c433`
- `ntdll!NtQueryValueKey` at `0x18006c48a`
- `ntdll!NtQueryValueKey` at `0x18006c433`
- `ntdll!NtQueryValueKey` at `0x18006c48a`

## pseudocode

```c
__int64 __fastcall FveRegistryGetValue(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        int a3,
        void *a4,
        unsigned int *a5)
{
  NTSTATUS v8; // ebx
  ULONG v9; // esi
  int v10; // eax
  _DWORD *v11; // rdi
  unsigned int v12; // eax
  void *KeyHandle; // [rsp+30h] [rbp-40h] BYREF
  PVOID KeyValueInformation; // [rsp+38h] [rbp-38h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  ULONG ResultLength; // [rsp+A0h] [rbp+30h] BYREF

  ObjectAttributes.ObjectName = a1;
  ResultLength = 0;
  KeyHandle = 0;
  KeyValueInformation = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v8 >= 0 )
  {
    v8 = NtQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, 0, 0, &ResultLength);
    if ( (int)(v8 + 0x80000000) < 0 || v8 == -1073741789 )
    {
      v9 = 0;
      v10 = FveLibAllocWithTagZero(ResultLength);
      v11 = KeyValueInformation;
      v8 = v10;
      if ( v10 >= 0 )
      {
        v9 = ResultLength;
        v8 = NtQueryValueKey(
               KeyHandle,
               a2,
               KeyValuePartialInformation,
               KeyValueInformation,
               ResultLength,
               &ResultLength);
        if ( v8 >= 0 )
        {
          if ( v11[1] == a3 )
          {
            if ( a4 && (v12 = v11[2], *a5 >= v12) )
            {
              *a5 = v12;
              memcpy_0(a4, v11 + 3, v12);
              v8 = 0;
            }
            else
            {
              v8 = -1073741789;
              *a5 = v11[2];
            }
          }
          else
          {
            v8 = -1073741438;
          }
        }
      }
      if ( v11 )
        FveLibFreeWithTag(v11, v9, 0);
    }
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18006c3a8  mov     [rsp-28h+arg_8], rbx
0x18006c3ad  mov     [rsp-28h+arg_10], rsi
0x18006c3b2  push    rbp
0x18006c3b3  push    rdi
0x18006c3b4  push    r12
0x18006c3b6  push    r14
0x18006c3b8  push    r15
0x18006c3ba  mov     rbp, rsp
0x18006c3bd  sub     rsp, 70h
0x18006c3c1  xor     eax, eax
0x18006c3c3  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x18006c3c7  mov     r15d, r8d
0x18006c3ca  mov     [rbp+arg_0], eax
0x18006c3cd  mov     r12, rdx
0x18006c3d0  mov     [rbp+KeyHandle], rax
0x18006c3d4  xorps   xmm0, xmm0
0x18006c3d7  mov     [rbp+KeyValueInformation], rax
0x18006c3db  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18006c3df  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x18006c3e3  mov     edx, 20019h; DesiredAccess
0x18006c3e8  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18006c3f0  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18006c3f4  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18006c3fc  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18006c401  mov     r14, r9
0x18006c404  call    cs:__imp_NtOpenKey
0x18006c40a  mov     ebx, eax
0x18006c40c  test    eax, eax
0x18006c40e  js      loc_18006C4E4
0x18006c414  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18006c418  lea     rax, [rbp+arg_0]
0x18006c41c  xor     r9d, r9d; KeyValueInformation
0x18006c41f  mov     [rsp+70h+ResultLength], rax; ResultLength
0x18006c424  mov     rdx, r12; ValueName
0x18006c427  mov     [rsp+70h+Length], 0; Length
0x18006c42f  lea     r8d, [r9+2]; KeyValueInformationClass
0x18006c433  call    cs:__imp_NtQueryValueKey
0x18006c439  mov     ecx, 80000000h
0x18006c43e  mov     ebx, eax
0x18006c440  add     eax, ecx
0x18006c442  test    ecx, eax
0x18006c444  jnz     short loc_18006C452
0x18006c446  cmp     ebx, 0C0000023h
0x18006c44c  jnz     loc_18006C4E4
0x18006c452  mov     ecx, [rbp+arg_0]; Size
0x18006c455  lea     r8, [rbp+KeyValueInformation]
0x18006c459  xor     esi, esi
0x18006c45b  call    FveLibAllocWithTagZero
0x18006c460  mov     rdi, [rbp+KeyValueInformation]
0x18006c464  mov     ebx, eax
0x18006c466  test    eax, eax
0x18006c468  js      short loc_18006C4D2
0x18006c46a  mov     esi, [rbp+arg_0]
0x18006c46d  lea     rax, [rbp+arg_0]
0x18006c471  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18006c475  mov     r9, rdi; KeyValueInformation
0x18006c478  mov     [rsp+70h+ResultLength], rax; ResultLength
0x18006c47d  mov     r8d, 2; KeyValueInformationClass
0x18006c483  mov     rdx, r12; ValueName
0x18006c486  mov     [rsp+70h+Length], esi; Length
0x18006c48a  call    cs:__imp_NtQueryValueKey
0x18006c490  mov     ebx, eax
0x18006c492  test    eax, eax
0x18006c494  js      short loc_18006C4D2
0x18006c496  cmp     [rdi+4], r15d
0x18006c49a  jz      short loc_18006C4A3
0x18006c49c  mov     ebx, 0C0000182h
0x18006c4a1  jmp     short loc_18006C4D2
0x18006c4a3  mov     rcx, [rbp+arg_20]
0x18006c4a7  test    r14, r14
0x18006c4aa  jz      short loc_18006C4C8
0x18006c4ac  mov     eax, [rdi+8]
0x18006c4af  cmp     [rcx], eax
0x18006c4b1  jb      short loc_18006C4C8
0x18006c4b3  mov     [rcx], eax
0x18006c4b5  lea     rdx, [rdi+0Ch]; Src
0x18006c4b9  mov     rcx, r14; void *
0x18006c4bc  mov     r8d, eax; Size
0x18006c4bf  call    memcpy_0
0x18006c4c4  xor     ebx, ebx
0x18006c4c6  jmp     short loc_18006C4D2
0x18006c4c8  mov     eax, [rdi+8]
0x18006c4cb  mov     ebx, 0C0000023h
0x18006c4d0  mov     [rcx], eax
0x18006c4d2  test    rdi, rdi
0x18006c4d5  jz      short loc_18006C4E4
0x18006c4d7  mov     edx, esi
0x18006c4d9  xor     r8d, r8d
0x18006c4dc  mov     rcx, rdi
0x18006c4df  call    FveLibFreeWithTag
0x18006c4e4  mov     rcx, [rbp+KeyHandle]; Handle
0x18006c4e8  test    rcx, rcx
0x18006c4eb  jz      short loc_18006C4F3
0x18006c4ed  call    cs:__imp_NtClose
0x18006c4f3  lea     r11, [rsp+70h+var_s0]
0x18006c4f8  mov     eax, ebx
0x18006c4fa  mov     rbx, [r11+38h]
0x18006c4fe  mov     rsi, [r11+40h]
0x18006c502  mov     rsp, r11
0x18006c505  pop     r15
0x18006c507  pop     r14
0x18006c509  pop     r12
0x18006c50b  pop     rdi
0x18006c50c  pop     rbp
0x18006c50d  retn
```
