# PpRegStateUpdateStackCreationSettings

- ea: `0x14000e390`
- end: `0x14000e504`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000d2a0`

## callees

- `0x1400022c0`
- `0x14000dea8`
- `0x14000e390`
- `0x14000e6b8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000e41e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e41e`
- `ntoskrnl!ZwClose` at `0x14000e474`
- `ntoskrnl!ZwClose` at `0x14000e4e5`
- `ntoskrnl!ZwClose` at `0x14000e474`
- `ntoskrnl!ZwClose` at `0x14000e4e5`
- `ntoskrnl!ZwSetValueKey` at `0x14000e4d3`
- `ntoskrnl!ZwSetValueKey` at `0x14000e4d3`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14000e488`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14000e488`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14000e3fe`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14000e3fe`

## string_xrefs

- `0x14000e498`: `Security`

## pseudocode

```c
__int64 __fastcall PpRegStateUpdateStackCreationSettings(int a1, __int64 a2)
{
  __int64 result; // rax
  int v4; // r8d
  __int64 v5; // r9
  __int64 *v6; // rbx
  NTSTATUS WstrKey; // ebx
  ULONG DataSize; // r10d
  void *Data; // r11
  HANDLE KeyHandle; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-18h] BYREF
  PVOID P; // [rsp+80h] [rbp+20h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp+28h] BYREF

  P = 0;
  KeyHandle = 0;
  Handle = 0;
  result = PiRegStateOpenClassKey(a1, a2, 0, 0, (__int64)&Handle);
  if ( (int)result >= 0 )
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
    WstrKey = CmRegUtilCreateWstrKey(
                (_DWORD)Handle,
                (unsigned int)L"Properties",
                v4,
                v5,
                (__int64)v6,
                0,
                (__int64)&KeyHandle);
    ZwClose(Handle);
    if ( WstrKey >= 0 )
    {
      RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a2 + 8));
      DestinationString = 0;
      WstrKey = WdmlibRtlInitUnicodeStringEx(&DestinationString, L"Security");
      if ( WstrKey >= 0 )
        WstrKey = ZwSetValueKey(KeyHandle, &DestinationString, 0, 3u, Data, DataSize);
      ZwClose(KeyHandle);
    }
    return (unsigned int)WstrKey;
  }
  return result;
}

```

## disassembly

```asm
0x14000e390  mov     [rsp-8+arg_0], rbx
0x14000e395  mov     [rsp-8+arg_8], rdi
0x14000e39a  push    rbp
0x14000e39b  mov     rbp, rsp
0x14000e39e  sub     rsp, 60h
0x14000e3a2  lea     rax, [rbp+Handle]
0x14000e3a6  mov     [rbp+P], 0
0x14000e3ae  xor     r9d, r9d
0x14000e3b1  mov     [rsp+60h+Data], rax
0x14000e3b6  xor     r8d, r8d
0x14000e3b9  mov     [rbp+KeyHandle], 0
0x14000e3c1  mov     rdi, rdx
0x14000e3c4  mov     [rbp+Handle], 0
0x14000e3cc  call    PiRegStateOpenClassKey
0x14000e3d1  test    eax, eax
0x14000e3d3  js      loc_14000E4F3
0x14000e3d9  cmp     cs:PiRegStateDiscriptor, 0
0x14000e3e0  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x14000e3e7  jnz     short loc_14000E436
0x14000e3e9  xor     edx, edx
0x14000e3eb  lea     rax, [rbp+P]
0x14000e3ef  mov     r9b, 1
0x14000e3f2  mov     [rsp+60h+Data], rax
0x14000e3f7  mov     rcx, rbx
0x14000e3fa  lea     r8d, [rdx+1]
0x14000e3fe  call    cs:__imp_SeCaptureSecurityDescriptor
0x14000e405  nop     dword ptr [rax+rax+00h]
0x14000e40a  test    eax, eax
0x14000e40c  js      short loc_14000E42C
0x14000e40e  mov     rcx, [rbp+P]; P
0x14000e412  xor     edx, edx; Tag
0x14000e414  mov     cs:PiRegStateDiscriptor, 1
0x14000e41e  call    cs:__imp_ExFreePoolWithTag
0x14000e425  nop     dword ptr [rax+rax+00h]
0x14000e42a  jmp     short loc_14000E436
0x14000e42c  mov     cs:PiRegStateDiscriptor, 2
0x14000e436  mov     rcx, [rbp+Handle]
0x14000e43a  lea     rdx, aProperties; "Properties"
0x14000e441  xor     eax, eax
0x14000e443  cmp     cs:PiRegStateDiscriptor, 1
0x14000e44a  cmovnz  rbx, rax
0x14000e44e  lea     rax, [rbp+KeyHandle]
0x14000e452  mov     [rsp+60h+var_30], rax
0x14000e457  mov     qword ptr [rsp+60h+DataSize], 0
0x14000e460  mov     [rsp+60h+Data], rbx
0x14000e465  mov     [rbp+P], rbx
0x14000e469  call    CmRegUtilCreateWstrKey
0x14000e46e  mov     rcx, [rbp+Handle]; Handle
0x14000e472  mov     ebx, eax
0x14000e474  call    cs:__imp_ZwClose
0x14000e47b  nop     dword ptr [rax+rax+00h]
0x14000e480  test    ebx, ebx
0x14000e482  js      short loc_14000E4F1
0x14000e484  mov     rcx, [rdi+8]; SecurityDescriptor
0x14000e488  call    cs:__imp_RtlLengthSecurityDescriptor
0x14000e48f  nop     dword ptr [rax+rax+00h]
0x14000e494  mov     r11, [rdi+8]
0x14000e498  lea     rdx, aSecurity; "Security"
0x14000e49f  xorps   xmm0, xmm0
0x14000e4a2  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000e4a6  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000e4aa  mov     r10d, eax
0x14000e4ad  call    WdmlibRtlInitUnicodeStringEx
0x14000e4b2  mov     ebx, eax
0x14000e4b4  test    eax, eax
0x14000e4b6  js      short loc_14000E4E1
0x14000e4b8  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14000e4bc  lea     rdx, [rbp+DestinationString]; ValueName
0x14000e4c0  mov     [rsp+60h+DataSize], r10d; DataSize
0x14000e4c5  mov     r9d, 3; Type
0x14000e4cb  xor     r8d, r8d; TitleIndex
0x14000e4ce  mov     [rsp+60h+Data], r11; Data
0x14000e4d3  call    cs:__imp_ZwSetValueKey
0x14000e4da  nop     dword ptr [rax+rax+00h]
0x14000e4df  mov     ebx, eax
0x14000e4e1  mov     rcx, [rbp+KeyHandle]; Handle
0x14000e4e5  call    cs:__imp_ZwClose
0x14000e4ec  nop     dword ptr [rax+rax+00h]
0x14000e4f1  mov     eax, ebx
0x14000e4f3  mov     rbx, [rsp+60h+arg_0]
0x14000e4f8  mov     rdi, [rsp+60h+arg_8]
0x14000e4fd  add     rsp, 60h
0x14000e501  pop     rbp
0x14000e502  retn
```
