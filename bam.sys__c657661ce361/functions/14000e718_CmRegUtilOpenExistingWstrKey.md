# CmRegUtilOpenExistingWstrKey

- ea: `0x14000e718`
- end: `0x14000e79d`
- name: `CmRegUtilOpenExistingWstrKey`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000dea8`
- `0x14000e224`

## callees

- `0x1400022c0`
- `0x14000e718`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14000e777`
- `ntoskrnl!ZwOpenKey` at `0x14000e777`

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
0x14000e718  mov     [rsp-8+arg_0], rbx
0x14000e71d  push    rbp
0x14000e71e  mov     rbp, rsp
0x14000e721  sub     rsp, 70h
0x14000e725  mov     r11, rcx
0x14000e728  xorps   xmm0, xmm0
0x14000e72b  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000e72f  mov     rbx, r9
0x14000e732  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000e736  mov     r10d, r8d
0x14000e739  call    WdmlibRtlInitUnicodeStringEx
0x14000e73e  test    eax, eax
0x14000e740  js      short loc_14000E78E
0x14000e742  xor     eax, eax
0x14000e744  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000e74c  mov     [rbp+KeyHandle], rax
0x14000e750  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000e754  mov     [rbx], rax
0x14000e757  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14000e75b  lea     rax, [rbp+DestinationString]
0x14000e75f  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14000e767  mov     edx, r10d; DesiredAccess
0x14000e76a  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000e76e  mov     [rbp+ObjectAttributes.RootDirectory], r11
0x14000e772  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000e777  call    cs:__imp_ZwOpenKey
0x14000e77e  nop     dword ptr [rax+rax+00h]
0x14000e783  test    eax, eax
0x14000e785  js      short loc_14000E78E
0x14000e787  mov     rcx, [rbp+KeyHandle]
0x14000e78b  mov     [rbx], rcx
0x14000e78e  mov     rbx, [rsp+70h+arg_0]
0x14000e796  add     rsp, 70h
0x14000e79a  pop     rbp
0x14000e79b  retn
```
