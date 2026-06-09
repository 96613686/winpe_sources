# CmRegUtilOpenExistingWstrKey

- ea: `0x140018680`
- end: `0x140018705`
- name: `CmRegUtilOpenExistingWstrKey`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140017e48`
- `0x1400181c4`

## callees

- `0x140008c0c`
- `0x140018680`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400186df`
- `ntoskrnl!ZwOpenKey` at `0x1400186df`

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
0x140018680  mov     [rsp-8+arg_0], rbx
0x140018685  push    rbp
0x140018686  mov     rbp, rsp
0x140018689  sub     rsp, 70h
0x14001868d  mov     r11, rcx
0x140018690  xorps   xmm0, xmm0
0x140018693  lea     rcx, [rbp+DestinationString]; DestinationString
0x140018697  mov     rbx, r9
0x14001869a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001869e  mov     r10d, r8d
0x1400186a1  call    WdmlibRtlInitUnicodeStringEx
0x1400186a6  test    eax, eax
0x1400186a8  js      short loc_1400186F6
0x1400186aa  xor     eax, eax
0x1400186ac  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400186b4  mov     [rbp+KeyHandle], rax
0x1400186b8  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400186bc  mov     [rbx], rax
0x1400186bf  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400186c3  lea     rax, [rbp+DestinationString]
0x1400186c7  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x1400186cf  mov     edx, r10d; DesiredAccess
0x1400186d2  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400186d6  mov     [rbp+ObjectAttributes.RootDirectory], r11
0x1400186da  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400186df  call    cs:__imp_ZwOpenKey
0x1400186e6  nop     dword ptr [rax+rax+00h]
0x1400186eb  test    eax, eax
0x1400186ed  js      short loc_1400186F6
0x1400186ef  mov     rcx, [rbp+KeyHandle]
0x1400186f3  mov     [rbx], rcx
0x1400186f6  mov     rbx, [rsp+70h+arg_0]
0x1400186fe  add     rsp, 70h
0x140018702  pop     rbp
0x140018703  retn
```
