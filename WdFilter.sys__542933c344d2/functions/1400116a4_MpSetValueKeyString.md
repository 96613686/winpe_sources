# MpSetValueKeyString

- ea: `0x1400116a4`
- end: `0x1400117f8`
- name: `MpSetValueKeyString`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14007cb50`

## callees

- `0x1400116a4`
- `0x1400118d0`
- `0x140038710`
- `0x140066180`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x14001179f`
- `ntoskrnl!ZwSetValueKey` at `0x14001179f`
- `ntoskrnl!ZwOpenKey` at `0x140011731`
- `ntoskrnl!ZwOpenKey` at `0x140011731`
- `ntoskrnl!ZwClose` at `0x1400117c8`
- `ntoskrnl!ZwClose` at `0x1400117c8`

## pseudocode

```c
__int64 __fastcall MpSetValueKeyString(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        const UNICODE_STRING *a3)
{
  NTSTATUS v5; // esi
  void *v6; // r10
  int v7; // eax
  PUNICODE_STRING v8; // rbx
  PUNICODE_STRING v10; // [rsp+30h] [rbp-50h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-40h] BYREF

  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  v10 = 0;
  KeyHandle = 0;
  if ( a1 && a2 && a3 )
  {
    ObjectAttributes.ObjectName = a1;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v5 = ZwOpenKey(&KeyHandle, 2u, &ObjectAttributes);
    if ( v5 < 0 )
    {
LABEL_14:
      if ( KeyHandle )
        ZwClose(KeyHandle);
      return (unsigned int)v5;
    }
    v6 = KeyHandle;
    if ( !KeyHandle )
      return (unsigned int)v5;
    if ( a3->MaximumLength == a3->Length + 2LL )
    {
      v8 = (PUNICODE_STRING)a3;
    }
    else
    {
      v7 = MpDuplicateString(a3, &v10);
      v8 = v10;
      v5 = v7;
      if ( v7 < 0 )
      {
LABEL_11:
        if ( v8 && v8 != a3 )
          MpFreeString(v8);
        goto LABEL_14;
      }
      v6 = KeyHandle;
    }
    v5 = ZwSetValueKey(v6, a2, 0, 1u, v8->Buffer, v8->MaximumLength);
    goto LABEL_11;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x1400116a4  push    rbp
0x1400116a6  push    rbx
0x1400116a7  push    rsi
0x1400116a8  push    rdi
0x1400116a9  push    r14
0x1400116ab  mov     rbp, rsp
0x1400116ae  sub     rsp, 80h
0x1400116b5  mov     rax, cs:__security_cookie
0x1400116bc  xor     rax, rsp
0x1400116bf  mov     [rbp+var_10], rax
0x1400116c3  mov     dword ptr [rbp+ObjectAttributes+4], 0
0x1400116ca  mov     rdi, r8
0x1400116cd  mov     dword ptr [rbp+ObjectAttributes+1Ch], 0
0x1400116d4  mov     r14, rdx
0x1400116d7  mov     [rbp+var_50], 0
0x1400116df  mov     [rbp+KeyHandle], 0
0x1400116e7  test    rcx, rcx
0x1400116ea  jz      loc_1400117D8
0x1400116f0  test    rdx, rdx
0x1400116f3  jz      loc_1400117D8
0x1400116f9  test    r8, r8
0x1400116fc  jz      loc_1400117D8
0x140011702  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x140011706  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14001170a  xorps   xmm0, xmm0
0x14001170d  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140011714  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140011718  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140011720  mov     edx, 2; DesiredAccess
0x140011725  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14001172c  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140011731  call    cs:__imp_ZwOpenKey
0x140011738  nop     dword ptr [rax+rax+00h]
0x14001173d  mov     esi, eax
0x14001173f  test    eax, eax
0x140011741  js      short loc_1400117BF
0x140011743  mov     r10, [rbp+KeyHandle]
0x140011747  test    r10, r10
0x14001174a  jz      loc_1400117D4
0x140011750  movzx   eax, word ptr [rdi]
0x140011753  movzx   ecx, word ptr [rdi+2]
0x140011757  add     rax, 2
0x14001175b  cmp     rcx, rax
0x14001175e  jz      short loc_14001177C
0x140011760  lea     rdx, [rbp+var_50]
0x140011764  mov     rcx, rdi; SourceString
0x140011767  call    MpDuplicateString
0x14001176c  mov     rbx, [rbp+var_50]
0x140011770  mov     esi, eax
0x140011772  test    eax, eax
0x140011774  js      short loc_1400117AD
0x140011776  mov     r10, [rbp+KeyHandle]
0x14001177a  jmp     short loc_14001177F
0x14001177c  mov     rbx, rdi
0x14001177f  movzx   eax, word ptr [rbx+2]
0x140011783  mov     r9d, 1; Type
0x140011789  mov     [rsp+80h+DataSize], eax; DataSize
0x14001178d  xor     r8d, r8d; TitleIndex
0x140011790  mov     rax, [rbx+8]
0x140011794  mov     rdx, r14; ValueName
0x140011797  mov     rcx, r10; KeyHandle
0x14001179a  mov     [rsp+80h+Data], rax; Data
0x14001179f  call    cs:__imp_ZwSetValueKey
0x1400117a6  nop     dword ptr [rax+rax+00h]
0x1400117ab  mov     esi, eax
0x1400117ad  test    rbx, rbx
0x1400117b0  jz      short loc_1400117BF
0x1400117b2  cmp     rbx, rdi
0x1400117b5  jz      short loc_1400117BF
0x1400117b7  mov     rcx, rbx
0x1400117ba  call    MpFreeString
0x1400117bf  mov     rcx, [rbp+KeyHandle]; Handle
0x1400117c3  test    rcx, rcx
0x1400117c6  jz      short loc_1400117D4
0x1400117c8  call    cs:__imp_ZwClose
0x1400117cf  nop     dword ptr [rax+rax+00h]
0x1400117d4  mov     eax, esi
0x1400117d6  jmp     short loc_1400117DD
0x1400117d8  mov     eax, 0C000000Dh
0x1400117dd  mov     rcx, [rbp+var_10]
0x1400117e1  xor     rcx, rsp; StackCookie
0x1400117e4  call    __security_check_cookie
0x1400117e9  add     rsp, 80h
0x1400117f0  pop     r14
0x1400117f2  pop     rdi
0x1400117f3  pop     rsi
0x1400117f4  pop     rbx
0x1400117f5  pop     rbp
0x1400117f6  retn
```
