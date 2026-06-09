# PpRegStateUpdateStackCreationSettings

- ea: `0x18002c290`
- end: `0x18002c404`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `372`
- prototype: `NTSTATUS __fastcall(unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002b190`

## callees

- `0x18001b8ac`
- `0x18002bda8`
- `0x18002c290`
- `0x18002c50c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18002c31e`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002c31e`
- `ntoskrnl!ZwClose` at `0x18002c374`
- `ntoskrnl!ZwClose` at `0x18002c3e5`
- `ntoskrnl!ZwClose` at `0x18002c374`
- `ntoskrnl!ZwClose` at `0x18002c3e5`
- `ntoskrnl!ZwSetValueKey` at `0x18002c3d3`
- `ntoskrnl!ZwSetValueKey` at `0x18002c3d3`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x18002c388`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x18002c388`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x18002c2fe`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x18002c2fe`

## string_xrefs

- `0x18002c398`: `Security`

## pseudocode

```c
NTSTATUS __fastcall PpRegStateUpdateStackCreationSettings(unsigned int *a1, __int64 a2)
{
  NTSTATUS result; // eax
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 *v6; // rbx
  NTSTATUS inited; // ebx
  ULONG DataSize; // r10d
  void *Data; // r11
  HANDLE KeyHandle; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-18h] BYREF
  PVOID P; // [rsp+80h] [rbp+20h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp+28h] BYREF

  P = 0;
  KeyHandle = 0;
  Handle = 0;
  result = PiRegStateOpenClassKey(a1, a2, 0, 0, &Handle);
  if ( result >= 0 )
  {
    v6 = PiRegStateSysAllInherittedSecurityDescriptor;
    if ( !PiRegStateDiscriptor )
    {
      LOBYTE(v5) = 1;
      if ( (int)SeCaptureSecurityDescriptor(PiRegStateSysAllInherittedSecurityDescriptor, 0, 1, v5, &P) < 0 )
      {
        PiRegStateDiscriptor = 2;
      }
      else
      {
        PiRegStateDiscriptor = 1;
        ExFreePoolWithTag(P, 0);
      }
    }
    if ( PiRegStateDiscriptor != 1 )
      v6 = 0;
    P = v6;
    inited = CmRegUtilCreateWstrKey((__int64)Handle, L"Properties", v4, v5, v6, 0, &KeyHandle);
    ZwClose(Handle);
    if ( inited >= 0 )
    {
      RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a2 + 8));
      DestinationString = 0;
      inited = WdmlibRtlInitUnicodeStringEx(&DestinationString, L"Security");
      if ( inited >= 0 )
        inited = ZwSetValueKey(KeyHandle, &DestinationString, 0, 3u, Data, DataSize);
      ZwClose(KeyHandle);
    }
    return inited;
  }
  return result;
}

```

## disassembly

```asm
0x18002c290  mov     [rsp-8+arg_0], rbx
0x18002c295  mov     [rsp-8+arg_8], rdi
0x18002c29a  push    rbp
0x18002c29b  mov     rbp, rsp
0x18002c29e  sub     rsp, 60h
0x18002c2a2  lea     rax, [rbp+Handle]
0x18002c2a6  mov     [rbp+P], 0
0x18002c2ae  xor     r9d, r9d
0x18002c2b1  mov     [rsp+60h+Data], rax
0x18002c2b6  xor     r8d, r8d
0x18002c2b9  mov     [rbp+KeyHandle], 0
0x18002c2c1  mov     rdi, rdx
0x18002c2c4  mov     [rbp+Handle], 0
0x18002c2cc  call    PiRegStateOpenClassKey
0x18002c2d1  test    eax, eax
0x18002c2d3  js      loc_18002C3F3
0x18002c2d9  cmp     cs:PiRegStateDiscriptor, 0
0x18002c2e0  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x18002c2e7  jnz     short loc_18002C336
0x18002c2e9  xor     edx, edx
0x18002c2eb  lea     rax, [rbp+P]
0x18002c2ef  mov     r9b, 1
0x18002c2f2  mov     [rsp+60h+Data], rax
0x18002c2f7  mov     rcx, rbx
0x18002c2fa  lea     r8d, [rdx+1]
0x18002c2fe  call    cs:__imp_SeCaptureSecurityDescriptor
0x18002c305  nop     dword ptr [rax+rax+00h]
0x18002c30a  test    eax, eax
0x18002c30c  js      short loc_18002C32C
0x18002c30e  mov     rcx, [rbp+P]; P
0x18002c312  xor     edx, edx; Tag
0x18002c314  mov     cs:PiRegStateDiscriptor, 1
0x18002c31e  call    cs:__imp_ExFreePoolWithTag
0x18002c325  nop     dword ptr [rax+rax+00h]
0x18002c32a  jmp     short loc_18002C336
0x18002c32c  mov     cs:PiRegStateDiscriptor, 2
0x18002c336  mov     rcx, [rbp+Handle]
0x18002c33a  lea     rdx, aProperties; "Properties"
0x18002c341  xor     eax, eax
0x18002c343  cmp     cs:PiRegStateDiscriptor, 1
0x18002c34a  cmovnz  rbx, rax
0x18002c34e  lea     rax, [rbp+KeyHandle]
0x18002c352  mov     [rsp+60h+var_30], rax
0x18002c357  mov     qword ptr [rsp+60h+DataSize], 0
0x18002c360  mov     [rsp+60h+Data], rbx
0x18002c365  mov     [rbp+P], rbx
0x18002c369  call    CmRegUtilCreateWstrKey
0x18002c36e  mov     rcx, [rbp+Handle]; Handle
0x18002c372  mov     ebx, eax
0x18002c374  call    cs:__imp_ZwClose
0x18002c37b  nop     dword ptr [rax+rax+00h]
0x18002c380  test    ebx, ebx
0x18002c382  js      short loc_18002C3F1
0x18002c384  mov     rcx, [rdi+8]; SecurityDescriptor
0x18002c388  call    cs:__imp_RtlLengthSecurityDescriptor
0x18002c38f  nop     dword ptr [rax+rax+00h]
0x18002c394  mov     r11, [rdi+8]
0x18002c398  lea     rdx, aSecurity; "Security"
0x18002c39f  xorps   xmm0, xmm0
0x18002c3a2  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002c3a6  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002c3aa  mov     r10d, eax
0x18002c3ad  call    WdmlibRtlInitUnicodeStringEx
0x18002c3b2  mov     ebx, eax
0x18002c3b4  test    eax, eax
0x18002c3b6  js      short loc_18002C3E1
0x18002c3b8  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18002c3bc  lea     rdx, [rbp+DestinationString]; ValueName
0x18002c3c0  mov     [rsp+60h+DataSize], r10d; DataSize
0x18002c3c5  mov     r9d, 3; Type
0x18002c3cb  xor     r8d, r8d; TitleIndex
0x18002c3ce  mov     [rsp+60h+Data], r11; Data
0x18002c3d3  call    cs:__imp_ZwSetValueKey
0x18002c3da  nop     dword ptr [rax+rax+00h]
0x18002c3df  mov     ebx, eax
0x18002c3e1  mov     rcx, [rbp+KeyHandle]; Handle
0x18002c3e5  call    cs:__imp_ZwClose
0x18002c3ec  nop     dword ptr [rax+rax+00h]
0x18002c3f1  mov     eax, ebx
0x18002c3f3  mov     rbx, [rsp+60h+arg_0]
0x18002c3f8  mov     rdi, [rsp+60h+arg_8]
0x18002c3fd  add     rsp, 60h
0x18002c401  pop     rbp
0x18002c402  retn
```
