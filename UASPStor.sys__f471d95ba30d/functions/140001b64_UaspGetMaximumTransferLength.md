# UaspGetMaximumTransferLength

- ea: `0x140001b64`
- end: `0x140001c80`
- name: `UaspGetMaximumTransferLength`
- size: `284`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140003460`

## callees

- `0x140001b64`
- `0x1400052b8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140001c64`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001c64`
- `ntoskrnl!ZwClose` at `0x140001c4e`
- `ntoskrnl!ZwClose` at `0x140001c4e`
- `ntoskrnl!ZwQueryValueKey` at `0x140001be4`
- `ntoskrnl!ZwQueryValueKey` at `0x140001c2c`
- `ntoskrnl!ZwQueryValueKey` at `0x140001be4`
- `ntoskrnl!ZwQueryValueKey` at `0x140001c2c`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140001bb6`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140001bb6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001b9a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001b9a`

## pseudocode

```c
__int64 __fastcall UaspGetMaximumTransferLength(PDEVICE_OBJECT DeviceObject)
{
  _DWORD *Pool; // rdi
  unsigned int v3; // esi
  NTSTATUS v4; // eax
  __int64 v5; // rcx
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  ULONG ResultLength; // [rsp+68h] [rbp+28h] BYREF
  void *DeviceRegKey; // [rsp+70h] [rbp+30h] BYREF

  DeviceRegKey = 0;
  Pool = 0;
  DestinationString = 0;
  ResultLength = 0;
  v3 = 0x80000;
  RtlInitUnicodeString(&DestinationString, L"MaximumTransferLength");
  if ( IoOpenDeviceRegistryKey(DeviceObject, 1u, 0x20019u, &DeviceRegKey) >= 0 )
  {
    v4 = ZwQueryValueKey(DeviceRegKey, &DestinationString, KeyValuePartialInformation, 0, 0, &ResultLength);
    if ( v4 == -2147483643 || v4 == -1073741789 )
    {
      Pool = (_DWORD *)UaspAllocatePool(v5, ResultLength);
      if ( Pool )
      {
        if ( ZwQueryValueKey(
               DeviceRegKey,
               &DestinationString,
               KeyValuePartialInformation,
               Pool,
               ResultLength,
               &ResultLength) >= 0
          && Pool[2] == 4 )
        {
          v3 = Pool[3];
        }
      }
    }
  }
  if ( DeviceRegKey )
    ZwClose(DeviceRegKey);
  if ( Pool )
    ExFreePoolWithTag(Pool, 0);
  return v3;
}

```

## disassembly

```asm
0x140001b64  mov     [rsp-18h+arg_0], rbx
0x140001b69  push    rbp
0x140001b6a  push    rsi
0x140001b6b  push    rdi
0x140001b6c  mov     rbp, rsp
0x140001b6f  sub     rsp, 40h
0x140001b73  mov     rbx, rcx
0x140001b76  mov     [rbp+DeviceRegKey], 0
0x140001b7e  xorps   xmm0, xmm0
0x140001b81  lea     rcx, [rbp+DestinationString]; DestinationString
0x140001b85  xor     edi, edi
0x140001b87  lea     rdx, SourceString; "MaximumTransferLength"
0x140001b8e  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140001b92  mov     [rbp+arg_8], edi
0x140001b95  mov     esi, 80000h
0x140001b9a  call    cs:__imp_RtlInitUnicodeString
0x140001ba1  nop     dword ptr [rax+rax+00h]
0x140001ba6  lea     r9, [rbp+DeviceRegKey]; DeviceRegKey
0x140001baa  mov     r8d, 20019h; DesiredAccess
0x140001bb0  lea     edx, [rdi+1]; DevInstKeyType
0x140001bb3  mov     rcx, rbx; DeviceObject
0x140001bb6  call    cs:__imp_IoOpenDeviceRegistryKey
0x140001bbd  nop     dword ptr [rax+rax+00h]
0x140001bc2  test    eax, eax
0x140001bc4  js      short loc_140001C45
0x140001bc6  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x140001bca  lea     rax, [rbp+arg_8]
0x140001bce  mov     [rsp+40h+ResultLength], rax; ResultLength
0x140001bd3  lea     ebx, [rdi+2]
0x140001bd6  mov     r8d, ebx; KeyValueInformationClass
0x140001bd9  mov     [rsp+40h+Length], edi; Length
0x140001bdd  xor     r9d, r9d; KeyValueInformation
0x140001be0  lea     rdx, [rbp+DestinationString]; ValueName
0x140001be4  call    cs:__imp_ZwQueryValueKey
0x140001beb  nop     dword ptr [rax+rax+00h]
0x140001bf0  cmp     eax, 80000005h
0x140001bf5  jz      short loc_140001BFE
0x140001bf7  cmp     eax, 0C0000023h
0x140001bfc  jnz     short loc_140001C45
0x140001bfe  mov     edx, [rbp+arg_8]
0x140001c01  call    UaspAllocatePool
0x140001c06  mov     rdi, rax
0x140001c09  test    rax, rax
0x140001c0c  jz      short loc_140001C45
0x140001c0e  mov     ecx, [rbp+arg_8]
0x140001c11  lea     rax, [rbp+arg_8]
0x140001c15  mov     [rsp+40h+ResultLength], rax; ResultLength
0x140001c1a  lea     rdx, [rbp+DestinationString]; ValueName
0x140001c1e  mov     [rsp+40h+Length], ecx; Length
0x140001c22  mov     r9, rdi; KeyValueInformation
0x140001c25  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x140001c29  mov     r8d, ebx; KeyValueInformationClass
0x140001c2c  call    cs:__imp_ZwQueryValueKey
0x140001c33  nop     dword ptr [rax+rax+00h]
0x140001c38  test    eax, eax
0x140001c3a  js      short loc_140001C45
0x140001c3c  cmp     dword ptr [rdi+8], 4
0x140001c40  jnz     short loc_140001C45
0x140001c42  mov     esi, [rdi+0Ch]
0x140001c45  mov     rcx, [rbp+DeviceRegKey]; Handle
0x140001c49  test    rcx, rcx
0x140001c4c  jz      short loc_140001C5A
0x140001c4e  call    cs:__imp_ZwClose
0x140001c55  nop     dword ptr [rax+rax+00h]
0x140001c5a  test    rdi, rdi
0x140001c5d  jz      short loc_140001C70
0x140001c5f  xor     edx, edx; Tag
0x140001c61  mov     rcx, rdi; P
0x140001c64  call    cs:__imp_ExFreePoolWithTag
0x140001c6b  nop     dword ptr [rax+rax+00h]
0x140001c70  mov     rbx, [rsp+40h+arg_0]
0x140001c75  mov     eax, esi
0x140001c77  add     rsp, 40h
0x140001c7b  pop     rdi
0x140001c7c  pop     rsi
0x140001c7d  pop     rbp
0x140001c7e  retn
```
