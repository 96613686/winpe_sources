# WimpFSFIsIntegrityMandatory

- ea: `0x14002a750`
- end: `0x14002a88f`
- name: `WimpFSFIsIntegrityMandatory`
- size: `319`
- prototype: `__int64 __fastcall(__int64 Val, _BYTE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400284d8`

## callees

- `0x140011560`
- `0x14002a750`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14002a7c4`
- `ntoskrnl!ZwOpenKey` at `0x14002a7c4`
- `ntoskrnl!ZwClose` at `0x14002a861`
- `ntoskrnl!ZwClose` at `0x14002a861`
- `ntoskrnl!ZwQueryValueKey` at `0x14002a835`
- `ntoskrnl!ZwQueryValueKey` at `0x14002a835`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002a806`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002a806`
- `ntoskrnl!_i64tow_s` at `0x14002a7e7`
- `ntoskrnl!_i64tow_s` at `0x14002a7e7`

## pseudocode

```c
__int64 __fastcall WimpFSFIsIntegrityMandatory(__int64 Val, _BYTE *a2)
{
  NTSTATUS v4; // eax
  unsigned int v5; // edi
  ULONG ResultLength; // [rsp+30h] [rbp-59h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-39h] BYREF
  __int128 KeyValueInformation; // [rsp+80h] [rbp-9h] BYREF
  int v12; // [rsp+90h] [rbp+7h]
  wchar_t DstBuf[20]; // [rsp+98h] [rbp+Fh] BYREF

  KeyHandle = 0;
  v12 = 0;
  ResultLength = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&g_IntegrityFilesKeyName;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  DestinationString = 0;
  KeyValueInformation = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  v5 = v4;
  if ( v4 < 0 )
    goto LABEL_6;
  if ( _i64tow_s(Val, DstBuf, 0x11u, 10) )
  {
    v5 = -1073741675;
    goto LABEL_8;
  }
  RtlInitUnicodeString(&DestinationString, DstBuf);
  v4 = ZwQueryValueKey(
         KeyHandle,
         &DestinationString,
         KeyValuePartialInformation,
         &KeyValueInformation,
         0x14u,
         &ResultLength);
  v5 = v4;
  if ( v4 < 0 )
  {
LABEL_6:
    if ( v4 == -1073741772 )
    {
      v5 = 0;
      *a2 = 0;
    }
  }
  else
  {
    *a2 = 1;
  }
LABEL_8:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return v5;
}

```

## disassembly

```asm
0x14002a750  mov     [rsp-8+arg_10], rbx
0x14002a755  push    rbp
0x14002a756  push    rsi
0x14002a757  push    rdi
0x14002a758  lea     rbp, [rsp-47h]
0x14002a75d  sub     rsp, 0D0h
0x14002a764  mov     rax, cs:__security_cookie
0x14002a76b  xor     rax, rsp
0x14002a76e  mov     [rbp+57h+var_20], rax
0x14002a772  xor     eax, eax
0x14002a774  mov     [rbp+57h+KeyHandle], 0
0x14002a77c  xorps   xmm0, xmm0
0x14002a77f  mov     [rbp+57h+var_50], eax
0x14002a782  mov     [rbp+57h+var_B0], eax
0x14002a785  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14002a789  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14002a78d  mov     rsi, rdx
0x14002a790  lea     rax, g_IntegrityFilesKeyName
0x14002a797  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14002a79f  mov     rbx, rcx
0x14002a7a2  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14002a7a6  mov     edx, 20019h; DesiredAccess
0x14002a7ab  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x14002a7b3  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14002a7b7  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14002a7bb  movups  [rbp+57h+KeyValueInformation], xmm0
0x14002a7bf  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002a7c4  call    cs:__imp_ZwOpenKey
0x14002a7cb  nop     dword ptr [rax+rax+00h]
0x14002a7d0  mov     edi, eax
0x14002a7d2  test    eax, eax
0x14002a7d4  js      short loc_14002A84C
0x14002a7d6  mov     r9d, 0Ah; Radix
0x14002a7dc  lea     rdx, [rbp+57h+DstBuf]; DstBuf
0x14002a7e0  mov     rcx, rbx; Val
0x14002a7e3  lea     r8d, [r9+7]; SizeInWords
0x14002a7e7  call    cs:__imp__i64tow_s
0x14002a7ee  nop     dword ptr [rax+rax+00h]
0x14002a7f3  test    eax, eax
0x14002a7f5  jz      short loc_14002A7FE
0x14002a7f7  mov     edi, 0C0000095h
0x14002a7fc  jmp     short loc_14002A858
0x14002a7fe  lea     rdx, [rbp+57h+DstBuf]; SourceString
0x14002a802  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14002a806  call    cs:__imp_RtlInitUnicodeString
0x14002a80d  nop     dword ptr [rax+rax+00h]
0x14002a812  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14002a816  lea     rax, [rbp+57h+var_B0]
0x14002a81a  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x14002a81f  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14002a823  mov     r8d, 2; KeyValueInformationClass
0x14002a829  mov     [rsp+0E0h+Length], 14h; Length
0x14002a831  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14002a835  call    cs:__imp_ZwQueryValueKey
0x14002a83c  nop     dword ptr [rax+rax+00h]
0x14002a841  mov     edi, eax
0x14002a843  test    eax, eax
0x14002a845  js      short loc_14002A84C
0x14002a847  mov     byte ptr [rsi], 1
0x14002a84a  jmp     short loc_14002A858
0x14002a84c  cmp     eax, 0C0000034h
0x14002a851  jnz     short loc_14002A858
0x14002a853  xor     edi, edi
0x14002a855  mov     [rsi], dil
0x14002a858  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14002a85c  test    rcx, rcx
0x14002a85f  jz      short loc_14002A86D
0x14002a861  call    cs:__imp_ZwClose
0x14002a868  nop     dword ptr [rax+rax+00h]
0x14002a86d  mov     eax, edi
0x14002a86f  mov     rcx, [rbp+57h+var_20]
0x14002a873  xor     rcx, rsp; StackCookie
0x14002a876  call    __security_check_cookie
0x14002a87b  mov     rbx, [rsp+0E0h+arg_10]
0x14002a883  add     rsp, 0D0h
0x14002a88a  pop     rdi
0x14002a88b  pop     rsi
0x14002a88c  pop     rbp
0x14002a88d  retn
```
