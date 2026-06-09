# CmRegUtilOpenExistingWstrKey

- ea: `0x18002c5e0`
- end: `0x18002c665`
- name: `CmRegUtilOpenExistingWstrKey`
- size: `133`
- prototype: `NTSTATUS __fastcall(__int64, const WCHAR *, __int64, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18002bda8`
- `0x18002c124`

## callees

- `0x18001b8ac`
- `0x18002c5e0`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x18002c63f`
- `ntoskrnl!ZwOpenKey` at `0x18002c63f`

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
0x18002c5e0  mov     [rsp-8+arg_0], rbx
0x18002c5e5  push    rbp
0x18002c5e6  mov     rbp, rsp
0x18002c5e9  sub     rsp, 70h
0x18002c5ed  mov     r11, rcx
0x18002c5f0  xorps   xmm0, xmm0
0x18002c5f3  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002c5f7  mov     rbx, r9
0x18002c5fa  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002c5fe  mov     r10d, r8d
0x18002c601  call    WdmlibRtlInitUnicodeStringEx
0x18002c606  test    eax, eax
0x18002c608  js      short loc_18002C656
0x18002c60a  xor     eax, eax
0x18002c60c  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18002c614  mov     [rbp+KeyHandle], rax
0x18002c618  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18002c61c  mov     [rbx], rax
0x18002c61f  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18002c623  lea     rax, [rbp+DestinationString]
0x18002c627  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x18002c62f  mov     edx, r10d; DesiredAccess
0x18002c632  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18002c636  mov     [rbp+ObjectAttributes.RootDirectory], r11
0x18002c63a  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002c63f  call    cs:__imp_ZwOpenKey
0x18002c646  nop     dword ptr [rax+rax+00h]
0x18002c64b  test    eax, eax
0x18002c64d  js      short loc_18002C656
0x18002c64f  mov     rcx, [rbp+KeyHandle]
0x18002c653  mov     [rbx], rcx
0x18002c656  mov     rbx, [rsp+70h+arg_0]
0x18002c65e  add     rsp, 70h
0x18002c662  pop     rbp
0x18002c663  retn
```
