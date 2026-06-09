# Streaming::Messaging::UserCommunication::GetSendMessageTimeOutValue(void)

- ea: `0x140013acc`
- end: `0x140013c6e`
- name: `?GetSendMessageTimeOutValue@UserCommunication@Messaging@Streaming@@CAKXZ`
- size: `418`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140014364`

## callees

- `0x140013acc`
- `0x1400147fc`
- `0x1400153c4`
- `0x140015af0`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140013b65`
- `ntoskrnl!ZwOpenKey` at `0x140013b65`
- `ntoskrnl!ZwQueryValueKey` at `0x140013bb1`
- `ntoskrnl!ZwQueryValueKey` at `0x140013bb1`
- `ntoskrnl!ZwClose` at `0x140013c38`
- `ntoskrnl!ZwClose` at `0x140013c38`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013b24`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013b84`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013b24`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013b84`

## string_xrefs

- `0x140013b01`: `\Registry\Machine\Software\Microsoft\AppV\Client\Streaming`
- `0x140013bdb`: `UserCommunication::GetSendMessageTimeOutValue() - Failed to query the send time out value. the value type or the value size doesn't match the expectation.`

## pseudocode

```c
__int64 Streaming::Messaging::UserCommunication::GetSendMessageTimeOutValue(void)
{
  unsigned int v0; // ebx
  __int64 *CurrentActivityID; // rax
  volatile signed __int32 *v2; // rbx
  ULONG ResultLength; // [rsp+30h] [rbp-39h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-31h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-9h] BYREF
  _BYTE v9[8]; // [rsp+90h] [rbp+27h] BYREF
  volatile signed __int32 *v10; // [rsp+98h] [rbp+2Fh]
  __int128 KeyValueInformation; // [rsp+A0h] [rbp+37h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  ValueName = 0;
  KeyValueInformation = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\Software\\Microsoft\\AppV\\Client\\Streaming");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes) >= 0 )
  {
    RtlInitUnicodeString(&ValueName, L"StreamResponseWaitTimeout");
    if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x10u, &ResultLength) >= 0 )
    {
      if ( *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
      {
        v0 = HIDWORD(KeyValueInformation);
        goto LABEL_10;
      }
      CurrentActivityID = (__int64 *)Streaming::Utils::GetCurrentActivityID(v9);
      LogWrite(
        1,
        *CurrentActivityID,
        L"UserCommunication::GetSendMessageTimeOutValue() - Failed to query the send time out value. the value type or the"
         " value size doesn't match the expectation.");
      v2 = v10;
      if ( v10 )
      {
        if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
          if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 16LL))(v2);
        }
      }
    }
  }
  v0 = 0;
LABEL_10:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( v0 < 5 )
    return 5;
  return v0;
}

```

## disassembly

```asm
0x140013acc  mov     [rsp-8+arg_0], rbx
0x140013ad1  push    rbp
0x140013ad2  lea     rbp, [rsp-57h]
0x140013ad7  sub     rsp, 0C0h
0x140013ade  mov     rax, cs:__security_cookie
0x140013ae5  xor     rax, rsp
0x140013ae8  mov     [rbp+57h+var_10], rax
0x140013aec  xorps   xmm0, xmm0
0x140013aef  mov     [rbp+57h+KeyHandle], 0
0x140013af7  xorps   xmm1, xmm1
0x140013afa  mov     [rbp+57h+var_90], 0
0x140013b01  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\Software\\Microsof"...
0x140013b08  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140013b0c  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140013b10  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140013b14  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140013b18  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140013b1c  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x140013b20  movups  [rbp+57h+KeyValueInformation], xmm0
0x140013b24  call    cs:__imp_RtlInitUnicodeString
0x140013b2b  nop     dword ptr [rax+rax+00h]
0x140013b30  lea     rax, [rbp+57h+DestinationString]
0x140013b34  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140013b3b  xorps   xmm0, xmm0
0x140013b3e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140013b42  mov     ebx, 1
0x140013b47  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140013b4f  mov     edx, ebx; DesiredAccess
0x140013b51  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140013b58  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140013b5c  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140013b60  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140013b65  call    cs:__imp_ZwOpenKey
0x140013b6c  nop     dword ptr [rax+rax+00h]
0x140013b71  test    eax, eax
0x140013b73  js      loc_140013C2D
0x140013b79  lea     rdx, aStreamresponse; "StreamResponseWaitTimeout"
0x140013b80  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x140013b84  call    cs:__imp_RtlInitUnicodeString
0x140013b8b  nop     dword ptr [rax+rax+00h]
0x140013b90  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140013b94  lea     rax, [rbp+57h+var_90]
0x140013b98  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x140013b9d  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140013ba1  lea     r8d, [rbx+1]; KeyValueInformationClass
0x140013ba5  mov     [rsp+0C0h+Length], 10h; Length
0x140013bad  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140013bb1  call    cs:__imp_ZwQueryValueKey
0x140013bb8  nop     dword ptr [rax+rax+00h]
0x140013bbd  test    eax, eax
0x140013bbf  js      short loc_140013C2D
0x140013bc1  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x140013bc5  jnz     short loc_140013BD2
0x140013bc7  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x140013bcb  jnz     short loc_140013BD2
0x140013bcd  mov     ebx, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x140013bd0  jmp     short loc_140013C2F
0x140013bd2  lea     rcx, [rbp+57h+var_30]
0x140013bd6  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140013bdb  lea     r8, aUsercommunicat_4; "UserCommunication::GetSendMessageTimeOu"...
0x140013be2  mov     ecx, ebx
0x140013be4  mov     rdx, [rax]
0x140013be7  call    LogWrite
0x140013bec  mov     rbx, [rbp+57h+var_28]
0x140013bf0  test    rbx, rbx
0x140013bf3  jz      short loc_140013C2D
0x140013bf5  or      eax, 0FFFFFFFFh
0x140013bf8  lock xadd [rbx+8], eax
0x140013bfd  cmp     eax, 1
0x140013c00  jnz     short loc_140013C2D
0x140013c02  mov     rax, [rbx]
0x140013c05  mov     rcx, rbx
0x140013c08  mov     rax, [rax+8]
0x140013c0c  call    _guard_dispatch_icall
0x140013c11  or      eax, 0FFFFFFFFh
0x140013c14  lock xadd [rbx+0Ch], eax
0x140013c19  cmp     eax, 1
0x140013c1c  jnz     short loc_140013C2D
0x140013c1e  mov     rax, [rbx]
0x140013c21  mov     rcx, rbx
0x140013c24  mov     rax, [rax+10h]
0x140013c28  call    _guard_dispatch_icall
0x140013c2d  xor     ebx, ebx
0x140013c2f  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140013c33  test    rcx, rcx
0x140013c36  jz      short loc_140013C44
0x140013c38  call    cs:__imp_ZwClose
0x140013c3f  nop     dword ptr [rax+rax+00h]
0x140013c44  mov     eax, 5
0x140013c49  cmp     ebx, eax
0x140013c4b  cmovb   ebx, eax
0x140013c4e  mov     eax, ebx
0x140013c50  mov     rcx, [rbp+57h+var_10]
0x140013c54  xor     rcx, rsp; StackCookie
0x140013c57  call    __security_check_cookie
0x140013c5c  mov     rbx, [rsp+0C0h+arg_0]
0x140013c64  add     rsp, 0C0h
0x140013c6b  pop     rbp
0x140013c6c  retn
```
