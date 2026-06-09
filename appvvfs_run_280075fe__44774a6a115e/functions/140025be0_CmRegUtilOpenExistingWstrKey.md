# CmRegUtilOpenExistingWstrKey

- ea: `0x140025be0`
- end: `0x140025c65`
- name: `CmRegUtilOpenExistingWstrKey`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400253a8`
- `0x140025724`

## callees

- `0x1400138e0`
- `0x140025be0`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140025c3f`
- `ntoskrnl!ZwOpenKey` at `0x140025c3f`

## pseudocode

```c
NTSTATUS __fastcall CmRegUtilOpenExistingWstrKey(__int64 a1, const WCHAR *a2, __int64 a3, void **a4)
{
  NTSTATUS result; // eax
  ACCESS_MASK v6; // r10d
  void *v7; // r11
  void *KeyHandle; // [rsp+20h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-38h] BYREF

  DestinationString = 0;
  result = WdmlibRtlInitUnicodeStringEx(&DestinationString, a2);
  if ( result >= 0 )
  {
    *(_QWORD *)&ObjectAttributes.Length = 48;
    KeyHandle = 0;
    *a4 = 0;
    *(_QWORD *)&ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = v7;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    result = ZwOpenKey(&KeyHandle, v6, &ObjectAttributes);
    if ( result >= 0 )
      *a4 = KeyHandle;
  }
  return result;
}

```

## disassembly

```asm
0x140025be0  mov     [rsp-8+arg_0], rbx
0x140025be5  push    rbp
0x140025be6  mov     rbp, rsp
0x140025be9  sub     rsp, 70h
0x140025bed  mov     r11, rcx
0x140025bf0  xorps   xmm0, xmm0
0x140025bf3  lea     rcx, [rbp+DestinationString]; DestinationString
0x140025bf7  mov     rbx, r9
0x140025bfa  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140025bfe  mov     r10d, r8d
0x140025c01  call    WdmlibRtlInitUnicodeStringEx
0x140025c06  test    eax, eax
0x140025c08  js      short loc_140025C56
0x140025c0a  xor     eax, eax
0x140025c0c  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140025c14  mov     [rbp+KeyHandle], rax
0x140025c18  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140025c1c  mov     [rbx], rax
0x140025c1f  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140025c23  lea     rax, [rbp+DestinationString]
0x140025c27  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x140025c2f  mov     edx, r10d; DesiredAccess
0x140025c32  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140025c36  mov     [rbp+ObjectAttributes.RootDirectory], r11
0x140025c3a  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140025c3f  call    cs:__imp_ZwOpenKey
0x140025c46  nop     dword ptr [rax+rax+00h]
0x140025c4b  test    eax, eax
0x140025c4d  js      short loc_140025C56
0x140025c4f  mov     rcx, [rbp+KeyHandle]
0x140025c53  mov     [rbx], rcx
0x140025c56  mov     rbx, [rsp+70h+arg_0]
0x140025c5e  add     rsp, 70h
0x140025c62  pop     rbp
0x140025c63  retn
```
