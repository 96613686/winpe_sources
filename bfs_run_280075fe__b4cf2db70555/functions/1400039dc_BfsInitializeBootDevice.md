# BfsInitializeBootDevice

- ea: `0x1400039dc`
- end: `0x140003b7a`
- name: `BfsInitializeBootDevice`
- size: `414`
- prototype: `__int64 __fastcall(PUNICODE_STRING LinkTarget)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001f078`

## callees

- `0x140001008`
- `0x1400039dc`
- `0x140013730`

## import_xrefs

- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140003aa4`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140003b11`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140003aa4`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140003b11`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x140003a70`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x140003a70`
- `ntoskrnl!RtlInitUnicodeString` at `0x140003a31`
- `ntoskrnl!RtlInitUnicodeString` at `0x140003a31`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003ac8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003ac8`
- `ntoskrnl!ExAllocatePool2` at `0x140003ae2`
- `ntoskrnl!ExAllocatePool2` at `0x140003ae2`

## pseudocode

```c
__int64 __fastcall BfsInitializeBootDevice(PUNICODE_STRING LinkTarget)
{
  NTSTATUS v2; // eax
  int v3; // r8d
  int v4; // r9d
  unsigned int v5; // ebx
  int v6; // ecx
  PWSTR Buffer; // rcx
  WCHAR *Pool2; // rax
  void *v9; // rcx
  int v11; // [rsp+20h] [rbp-49h]
  unsigned int v12; // [rsp+30h] [rbp-39h] BYREF
  ULONG ReturnedLength; // [rsp+34h] [rbp-35h] BYREF
  void *LinkHandle; // [rsp+38h] [rbp-31h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-29h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-19h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+80h] [rbp+17h] BYREF
  unsigned int *v18; // [rsp+A0h] [rbp+37h]
  __int64 v19; // [rsp+A8h] [rbp+3Fh]

  LinkHandle = 0;
  ReturnedLength = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\BootDevice");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwOpenSymbolicLinkObject(&LinkHandle, 1u, &ObjectAttributes);
  v5 = v2;
  if ( v2 < 0 )
  {
    v6 = dword_140019000;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v12 = v2;
LABEL_13:
      v19 = 4;
      v18 = &v12;
      tlgWriteTransfer_EtwWriteTransfer(v6, (int)&byte_140016D91, v3, v4, v11, &v17);
      return v5;
    }
    return v5;
  }
  v5 = ZwQuerySymbolicLinkObject(LinkHandle, LinkTarget, &ReturnedLength);
  if ( v5 != -1073741789 )
    goto LABEL_10;
  Buffer = LinkTarget->Buffer;
  if ( Buffer )
  {
    *(_DWORD *)&LinkTarget->Length = 0;
    ExFreePoolWithTag(Buffer, 0);
  }
  Pool2 = (WCHAR *)ExAllocatePool2(256, ReturnedLength, 1181967938);
  LinkTarget->Buffer = Pool2;
  if ( Pool2 )
  {
    v9 = LinkHandle;
    LinkTarget->MaximumLength = ReturnedLength;
    v5 = ZwQuerySymbolicLinkObject(v9, LinkTarget, &ReturnedLength);
LABEL_10:
    if ( (v5 & 0x80000000) == 0 )
      return v5;
    goto LABEL_11;
  }
  v5 = -1073741801;
LABEL_11:
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v12 = v5;
    goto LABEL_13;
  }
  return v5;
}

```

## disassembly

```asm
0x1400039dc  mov     [rsp-8+arg_8], rbx
0x1400039e1  mov     [rsp-8+arg_10], rdi
0x1400039e6  push    rbp
0x1400039e7  lea     rbp, [rsp-57h]
0x1400039ec  sub     rsp, 0C0h
0x1400039f3  mov     rax, cs:__security_cookie
0x1400039fa  xor     rax, rsp
0x1400039fd  mov     [rbp+57h+var_10], rax
0x140003a01  xorps   xmm0, xmm0
0x140003a04  mov     [rbp+57h+LinkHandle], 0
0x140003a0c  mov     rdi, rcx
0x140003a0f  mov     [rbp+57h+ReturnedLength], 0
0x140003a16  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140003a1a  lea     rdx, SourceString; "\\Device\\BootDevice"
0x140003a21  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140003a25  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140003a29  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140003a2d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140003a31  call    cs:__imp_RtlInitUnicodeString
0x140003a38  nop     dword ptr [rax+rax+00h]
0x140003a3d  lea     rax, [rbp+57h+DestinationString]
0x140003a41  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140003a48  xorps   xmm0, xmm0
0x140003a4b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140003a4f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140003a53  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140003a5b  mov     edx, 1; DesiredAccess
0x140003a60  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140003a67  lea     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x140003a6b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140003a70  call    cs:__imp_ZwOpenSymbolicLinkObject
0x140003a77  nop     dword ptr [rax+rax+00h]
0x140003a7c  mov     ebx, eax
0x140003a7e  test    eax, eax
0x140003a80  jns     short loc_140003A99
0x140003a82  mov     ecx, cs:dword_140019000
0x140003a88  cmp     ecx, 3
0x140003a8b  jbe     loc_140003B56
0x140003a91  mov     [rbp+57h+var_90], eax
0x140003a94  jmp     loc_140003B31
0x140003a99  mov     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x140003a9d  lea     r8, [rbp+57h+ReturnedLength]; ReturnedLength
0x140003aa1  mov     rdx, rdi; LinkTarget
0x140003aa4  call    cs:__imp_ZwQuerySymbolicLinkObject
0x140003aab  nop     dword ptr [rax+rax+00h]
0x140003ab0  mov     ebx, eax
0x140003ab2  cmp     eax, 0C0000023h
0x140003ab7  jnz     short loc_140003B1F
0x140003ab9  mov     rcx, [rdi+8]; P
0x140003abd  test    rcx, rcx
0x140003ac0  jz      short loc_140003AD4
0x140003ac2  xor     eax, eax
0x140003ac4  xor     edx, edx; Tag
0x140003ac6  mov     [rdi], eax
0x140003ac8  call    cs:__imp_ExFreePoolWithTag
0x140003acf  nop     dword ptr [rax+rax+00h]
0x140003ad4  mov     edx, [rbp+57h+ReturnedLength]
0x140003ad7  mov     ecx, 100h
0x140003adc  mov     r8d, 46736642h
0x140003ae2  call    cs:__imp_ExAllocatePool2
0x140003ae9  nop     dword ptr [rax+rax+00h]
0x140003aee  mov     [rdi+8], rax
0x140003af2  test    rax, rax
0x140003af5  jnz     short loc_140003AFE
0x140003af7  mov     ebx, 0C0000017h
0x140003afc  jmp     short loc_140003B23
0x140003afe  movzx   eax, word ptr [rbp+57h+ReturnedLength]
0x140003b02  lea     r8, [rbp+57h+ReturnedLength]; ReturnedLength
0x140003b06  mov     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x140003b0a  mov     rdx, rdi; LinkTarget
0x140003b0d  mov     [rdi+2], ax
0x140003b11  call    cs:__imp_ZwQuerySymbolicLinkObject
0x140003b18  nop     dword ptr [rax+rax+00h]
0x140003b1d  mov     ebx, eax
0x140003b1f  test    ebx, ebx
0x140003b21  jns     short loc_140003B56
0x140003b23  mov     eax, cs:dword_140019000
0x140003b29  cmp     eax, 3
0x140003b2c  jbe     short loc_140003B56
0x140003b2e  mov     [rbp+57h+var_90], ebx
0x140003b31  lea     rax, [rbp+57h+var_90]
0x140003b35  mov     [rbp+57h+var_18], 4
0x140003b3d  mov     [rbp+57h+var_20], rax
0x140003b41  lea     rdx, byte_140016D91; int
0x140003b48  lea     rax, [rbp+57h+var_40]
0x140003b4c  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x140003b51  call    _tlgWriteTransfer_EtwWriteTransfer
0x140003b56  mov     eax, ebx
0x140003b58  mov     rcx, [rbp+57h+var_10]
0x140003b5c  xor     rcx, rsp; StackCookie
0x140003b5f  call    __security_check_cookie
0x140003b64  lea     r11, [rsp+0C0h+var_s0]
0x140003b6c  mov     rbx, [r11+18h]
0x140003b70  mov     rdi, [r11+20h]
0x140003b74  mov     rsp, r11
0x140003b77  pop     rbp
0x140003b78  retn
```
