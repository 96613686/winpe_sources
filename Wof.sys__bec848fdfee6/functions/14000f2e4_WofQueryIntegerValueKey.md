# WofQueryIntegerValueKey

- ea: `0x14000f2e4`
- end: `0x14000f3ce`
- name: `WofQueryIntegerValueKey`
- size: `234`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140040078`

## callees

- `0x14000f2e4`
- `0x140011560`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14000f350`
- `ntoskrnl!ZwOpenKey` at `0x14000f350`
- `ntoskrnl!ZwClose` at `0x14000f3a8`
- `ntoskrnl!ZwClose` at `0x14000f3a8`
- `ntoskrnl!ZwQueryValueKey` at `0x14000f387`
- `ntoskrnl!ZwQueryValueKey` at `0x14000f387`

## pseudocode

```c
NTSTATUS __fastcall WofQueryIntegerValueKey(struct _UNICODE_STRING *a1, struct _UNICODE_STRING *a2, int a3, _DWORD *a4)
{
  NTSTATUS result; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-19h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-9h] BYREF
  __int128 KeyValueInformation; // [rsp+70h] [rbp+27h] BYREF
  int v11; // [rsp+80h] [rbp+37h]

  *a4 = a3;
  ObjectAttributes.ObjectName = a1;
  v11 = 0;
  ObjectAttributes.RootDirectory = 0;
  KeyHandle = 0;
  ResultLength = 0;
  KeyValueInformation = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    if ( a2 )
    {
      LODWORD(a2) = ZwQueryValueKey(
                      KeyHandle,
                      a2,
                      KeyValuePartialInformation,
                      &KeyValueInformation,
                      0x14u,
                      &ResultLength);
      if ( (int)a2 >= 0 && DWORD1(KeyValueInformation) == 4 )
        *a4 = HIDWORD(KeyValueInformation);
    }
    ZwClose(KeyHandle);
    return (int)a2;
  }
  return result;
}

```

## disassembly

```asm
0x14000f2e4  push    rbp
0x14000f2e6  push    rbx
0x14000f2e7  push    rdi
0x14000f2e8  lea     rbp, [rsp-47h]
0x14000f2ed  sub     rsp, 90h
0x14000f2f4  mov     rax, cs:__security_cookie
0x14000f2fb  xor     rax, rsp
0x14000f2fe  mov     [rbp+57h+var_18], rax
0x14000f302  xor     eax, eax
0x14000f304  mov     [r9], r8d
0x14000f307  xorps   xmm0, xmm0
0x14000f30a  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x14000f30e  mov     rbx, rdx
0x14000f311  mov     [rbp+57h+var_20], eax
0x14000f314  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000f318  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14000f31c  mov     edx, 20019h; DesiredAccess
0x14000f321  mov     [rbp+57h+KeyHandle], 0
0x14000f329  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000f32d  mov     [rbp+57h+var_70], 0
0x14000f334  movups  [rbp+57h+KeyValueInformation], xmm0
0x14000f338  mov     rdi, r9
0x14000f33b  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000f343  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000f348  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x14000f350  call    cs:__imp_ZwOpenKey
0x14000f357  nop     dword ptr [rax+rax+00h]
0x14000f35c  test    eax, eax
0x14000f35e  js      short loc_14000F3B6
0x14000f360  test    rbx, rbx
0x14000f363  jz      short loc_14000F3A4
0x14000f365  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14000f369  lea     rax, [rbp+57h+var_70]
0x14000f36d  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x14000f372  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14000f376  mov     r8d, 2; KeyValueInformationClass
0x14000f37c  mov     [rsp+0A0h+Length], 14h; Length
0x14000f384  mov     rdx, rbx; ValueName
0x14000f387  call    cs:__imp_ZwQueryValueKey
0x14000f38e  nop     dword ptr [rax+rax+00h]
0x14000f393  mov     ebx, eax
0x14000f395  test    eax, eax
0x14000f397  js      short loc_14000F3A4
0x14000f399  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x14000f39d  jnz     short loc_14000F3A4
0x14000f39f  mov     ecx, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x14000f3a2  mov     [rdi], ecx
0x14000f3a4  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14000f3a8  call    cs:__imp_ZwClose
0x14000f3af  nop     dword ptr [rax+rax+00h]
0x14000f3b4  mov     eax, ebx
0x14000f3b6  mov     rcx, [rbp+57h+var_18]
0x14000f3ba  xor     rcx, rsp; StackCookie
0x14000f3bd  call    __security_check_cookie
0x14000f3c2  add     rsp, 90h
0x14000f3c9  pop     rdi
0x14000f3ca  pop     rbx
0x14000f3cb  pop     rbp
0x14000f3cc  retn
```
