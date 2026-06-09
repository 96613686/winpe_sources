# BampReadProcessThrottlingSettings

- ea: `0x140011c68`
- end: `0x140011e68`
- name: `BampReadProcessThrottlingSettings`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001474c`

## callees

- `0x1400026d0`
- `0x140011c68`
- `0x140011e70`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140011e43`
- `ntoskrnl!ZwClose` at `0x140011e57`
- `ntoskrnl!ZwClose` at `0x140011e43`
- `ntoskrnl!ZwClose` at `0x140011e57`
- `ntoskrnl!ZwOpenKey` at `0x140011d5f`
- `ntoskrnl!ZwOpenKey` at `0x140011d5f`
- `ntoskrnl!ZwQueryValueKey` at `0x140011d95`
- `ntoskrnl!ZwQueryValueKey` at `0x140011de8`
- `ntoskrnl!ZwQueryValueKey` at `0x140011d95`
- `ntoskrnl!ZwQueryValueKey` at `0x140011de8`

## pseudocode

```c
int __fastcall BampReadProcessThrottlingSettings(struct _UNICODE_STRING *a1, _DWORD *a2, __int64 a3)
{
  int v6; // ebx
  __int64 v7; // xmm6_8
  int v8; // esi
  void *v9; // rax
  void *v10; // rdi
  __int64 v11; // rcx
  ULONG ResultLength; // [rsp+38h] [rbp-59h] BYREF
  void *KeyHandle; // [rsp+40h] [rbp-51h] BYREF
  __int64 v15; // [rsp+48h] [rbp-49h]
  int v16; // [rsp+50h] [rbp-41h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-39h] BYREF
  char KeyValueInformation[8]; // [rsp+88h] [rbp-9h] BYREF
  int v19; // [rsp+90h] [rbp-1h]
  __int64 v20; // [rsp+94h] [rbp+3h]
  int v21; // [rsp+9Ch] [rbp+Bh]

  ResultLength = 0;
  KeyHandle = 0;
  *a2 = DWORD2(xmmword_1400075D0);
  memset(&ObjectAttributes, 0, 44);
  *(_QWORD *)a3 = *(_QWORD *)((char *)&xmmword_1400075D0 + 12);
  *(_DWORD *)(a3 + 8) = dword_1400075E4;
  v6 = DWORD2(xmmword_1400075D0);
  v7 = *(_QWORD *)((char *)&xmmword_1400075D0 + 12);
  v8 = dword_1400075E4;
  v9 = (void *)BampOpenThrottlingPolicyKeyHandle();
  v10 = v9;
  if ( v9 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = v9;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = a1;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    LODWORD(v9) = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
    if ( (int)v9 >= 0 )
    {
      LODWORD(v9) = ZwQueryValueKey(
                      KeyHandle,
                      &BampNonExemptImagePolicyValueName,
                      KeyValuePartialInformation,
                      KeyValueInformation,
                      0x14u,
                      &ResultLength);
      if ( (int)v9 < 0 )
      {
        if ( (_DWORD)v9 != -1073741772 )
          goto LABEL_2;
      }
      else
      {
        v6 = v20;
        if ( (unsigned int)v20 >= 8 )
          goto LABEL_2;
      }
      LODWORD(v9) = ZwQueryValueKey(
                      KeyHandle,
                      &BampNonExemptImageExemptionsValueName,
                      KeyValuePartialInformation,
                      KeyValueInformation,
                      0x14u,
                      &ResultLength);
      if ( (int)v9 < 0 )
      {
        if ( (_DWORD)v9 != -1073741772 )
          goto LABEL_2;
      }
      else
      {
        if ( v19 != 12 )
          goto LABEL_2;
        v7 = v20;
        v11 = 0;
        v8 = v21;
        v15 = v20;
        v16 = v21;
        while ( (unsigned int)v11 < 3 )
        {
          if ( *((_DWORD *)&v15 + v11) >= 0x20u )
            goto LABEL_2;
          v11 = (unsigned int)(v11 + 1);
        }
      }
      *a2 = v6;
      *(_QWORD *)a3 = v7;
      *(_DWORD *)(a3 + 8) = v8;
    }
  }
LABEL_2:
  if ( KeyHandle )
    LODWORD(v9) = ZwClose(KeyHandle);
  if ( v10 )
    LODWORD(v9) = ZwClose(v10);
  return (int)v9;
}

```

## disassembly

```asm
0x140011c68  mov     rax, rsp
0x140011c6b  push    rbp
0x140011c6c  push    rbx
0x140011c6d  push    rsi
0x140011c6e  push    rdi
0x140011c6f  push    r12
0x140011c71  push    r14
0x140011c73  push    r15
0x140011c75  lea     rbp, [rax-5Fh]
0x140011c79  sub     rsp, 0B0h
0x140011c80  movaps  xmmword ptr [rax-48h], xmm6
0x140011c84  mov     rax, cs:__security_cookie
0x140011c8b  xor     rax, rsp
0x140011c8e  mov     qword ptr [rbp+57h+var_48], rax
0x140011c92  xorps   xmm0, xmm0
0x140011c95  mov     [rbp+57h+ResultLength], 0
0x140011c9c  xor     eax, eax
0x140011c9e  mov     r14, r8
0x140011ca1  mov     [rbp+57h+KeyHandle], rax
0x140011ca5  mov     r12, rdx
0x140011ca8  mov     eax, dword ptr cs:xmmword_1400075D0+8
0x140011cae  mov     r15, rcx
0x140011cb1  mov     [rdx], eax
0x140011cb3  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140011cb7  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140011cbb  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140011cbf  movsd   xmm0, qword ptr cs:xmmword_1400075D0+0Ch
0x140011cc7  movsd   qword ptr [r8], xmm0
0x140011ccc  mov     eax, cs:dword_1400075E4
0x140011cd2  mov     [r8+8], eax
0x140011cd6  mov     ebx, dword ptr cs:xmmword_1400075D0+8
0x140011cdc  movsd   xmm6, qword ptr cs:xmmword_1400075D0+0Ch
0x140011ce4  mov     esi, cs:dword_1400075E4
0x140011cea  call    BampOpenThrottlingPolicyKeyHandle
0x140011cef  mov     rdi, rax
0x140011cf2  test    rax, rax
0x140011cf5  jnz     short loc_140011D34
0x140011cf7  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140011cfb  test    rcx, rcx
0x140011cfe  jnz     loc_140011E43
0x140011d04  test    rdi, rdi
0x140011d07  jnz     loc_140011E54
0x140011d0d  mov     rcx, qword ptr [rbp+57h+var_48]
0x140011d11  xor     rcx, rsp; StackCookie
0x140011d14  call    __security_check_cookie
0x140011d19  movaps  xmm6, [rsp+0E0h+var_48+8]
0x140011d21  add     rsp, 0B0h
0x140011d28  pop     r15
0x140011d2a  pop     r14
0x140011d2c  pop     r12
0x140011d2e  pop     rdi
0x140011d2f  pop     rsi
0x140011d30  pop     rbx
0x140011d31  pop     rbp
0x140011d32  retn
0x140011d34  xorps   xmm0, xmm0
0x140011d37  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140011d3e  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140011d42  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x140011d46  mov     edx, 1; DesiredAccess
0x140011d4b  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140011d52  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140011d56  mov     [rbp+57h+ObjectAttributes.ObjectName], r15
0x140011d5a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140011d5f  call    cs:__imp_ZwOpenKey
0x140011d66  nop     dword ptr [rax+rax+00h]
0x140011d6b  test    eax, eax
0x140011d6d  js      short loc_140011CF7
0x140011d6f  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140011d73  lea     rax, [rbp+57h+ResultLength]
0x140011d77  mov     [rsp+28h], rax; ResultLength
0x140011d7c  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140011d80  mov     r8d, 2; KeyValueInformationClass
0x140011d86  mov     [rsp+0E0h+Length], 14h; Length
0x140011d8e  lea     rdx, BampNonExemptImagePolicyValueName; ValueName
0x140011d95  call    cs:__imp_ZwQueryValueKey
0x140011d9c  nop     dword ptr [rax+rax+00h]
0x140011da1  mov     r15d, 0C0000034h
0x140011da7  test    eax, eax
0x140011da9  js      short loc_140011DB9
0x140011dab  mov     ebx, dword ptr [rbp+57h+var_54]
0x140011dae  cmp     ebx, 8
0x140011db1  jnb     loc_140011CF7
0x140011db7  jmp     short loc_140011DC2
0x140011db9  cmp     eax, r15d
0x140011dbc  jnz     loc_140011CF7
0x140011dc2  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140011dc6  lea     rax, [rbp+57h+ResultLength]
0x140011dca  mov     [rsp+28h], rax; ResultLength
0x140011dcf  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140011dd3  mov     r8d, 2; KeyValueInformationClass
0x140011dd9  mov     [rsp+0E0h+Length], 14h; Length
0x140011de1  lea     rdx, BampNonExemptImageExemptionsValueName; ValueName
0x140011de8  call    cs:__imp_ZwQueryValueKey
0x140011def  nop     dword ptr [rax+rax+00h]
0x140011df4  test    eax, eax
0x140011df6  js      short loc_140011E28
0x140011df8  cmp     [rbp+57h+var_58], 0Ch
0x140011dfc  jnz     loc_140011CF7
0x140011e02  movsd   xmm6, [rbp+57h+var_54]
0x140011e07  xor     ecx, ecx
0x140011e09  mov     esi, [rbp+57h+var_4C]
0x140011e0c  movsd   [rbp+57h+var_A0], xmm6
0x140011e11  mov     [rbp+57h+var_98], esi
0x140011e14  cmp     ecx, 3
0x140011e17  jnb     short loc_140011E31
0x140011e19  cmp     dword ptr [rbp+rcx*4+57h+var_A0], 20h ; ' '
0x140011e1e  jnb     loc_140011CF7
0x140011e24  inc     ecx
0x140011e26  jmp     short loc_140011E14
0x140011e28  cmp     eax, r15d
0x140011e2b  jnz     loc_140011CF7
0x140011e31  mov     [r12], ebx
0x140011e35  movsd   qword ptr [r14], xmm6
0x140011e3a  mov     [r14+8], esi
0x140011e3e  jmp     loc_140011CF7
0x140011e43  call    cs:__imp_ZwClose
0x140011e4a  nop     dword ptr [rax+rax+00h]
0x140011e4f  jmp     loc_140011D04
0x140011e54  mov     rcx, rdi; Handle
0x140011e57  call    cs:__imp_ZwClose
0x140011e5e  nop     dword ptr [rax+rax+00h]
0x140011e63  jmp     loc_140011D0D
```
