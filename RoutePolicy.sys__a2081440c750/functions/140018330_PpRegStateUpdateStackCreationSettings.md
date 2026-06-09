# PpRegStateUpdateStackCreationSettings

- ea: `0x140018330`
- end: `0x1400184a4`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140017230`

## callees

- `0x140008c0c`
- `0x140017e48`
- `0x140018330`
- `0x1400185ac`

## import_xrefs

- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140018428`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140018428`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14001839e`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x14001839e`
- `ntoskrnl!ZwSetValueKey` at `0x140018473`
- `ntoskrnl!ZwSetValueKey` at `0x140018473`
- `ntoskrnl!ZwClose` at `0x140018414`
- `ntoskrnl!ZwClose` at `0x140018485`
- `ntoskrnl!ZwClose` at `0x140018414`
- `ntoskrnl!ZwClose` at `0x140018485`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400183be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400183be`

## string_xrefs

- `0x140018438`: `Security`

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
0x140018330  mov     [rsp-8+arg_0], rbx
0x140018335  mov     [rsp-8+arg_8], rdi
0x14001833a  push    rbp
0x14001833b  mov     rbp, rsp
0x14001833e  sub     rsp, 60h
0x140018342  lea     rax, [rbp+Handle]
0x140018346  mov     [rbp+P], 0
0x14001834e  xor     r9d, r9d
0x140018351  mov     [rsp+60h+Data], rax
0x140018356  xor     r8d, r8d
0x140018359  mov     [rbp+KeyHandle], 0
0x140018361  mov     rdi, rdx
0x140018364  mov     [rbp+Handle], 0
0x14001836c  call    PiRegStateOpenClassKey
0x140018371  test    eax, eax
0x140018373  js      loc_140018493
0x140018379  cmp     cs:PiRegStateDiscriptor, 0
0x140018380  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x140018387  jnz     short loc_1400183D6
0x140018389  xor     edx, edx
0x14001838b  lea     rax, [rbp+P]
0x14001838f  mov     r9b, 1
0x140018392  mov     [rsp+60h+Data], rax
0x140018397  mov     rcx, rbx
0x14001839a  lea     r8d, [rdx+1]
0x14001839e  call    cs:__imp_SeCaptureSecurityDescriptor
0x1400183a5  nop     dword ptr [rax+rax+00h]
0x1400183aa  test    eax, eax
0x1400183ac  js      short loc_1400183CC
0x1400183ae  mov     rcx, [rbp+P]; P
0x1400183b2  xor     edx, edx; Tag
0x1400183b4  mov     cs:PiRegStateDiscriptor, 1
0x1400183be  call    cs:__imp_ExFreePoolWithTag
0x1400183c5  nop     dword ptr [rax+rax+00h]
0x1400183ca  jmp     short loc_1400183D6
0x1400183cc  mov     cs:PiRegStateDiscriptor, 2
0x1400183d6  mov     rcx, [rbp+Handle]
0x1400183da  lea     rdx, aProperties; "Properties"
0x1400183e1  xor     eax, eax
0x1400183e3  cmp     cs:PiRegStateDiscriptor, 1
0x1400183ea  cmovnz  rbx, rax
0x1400183ee  lea     rax, [rbp+KeyHandle]
0x1400183f2  mov     [rsp+60h+var_30], rax
0x1400183f7  mov     qword ptr [rsp+60h+DataSize], 0
0x140018400  mov     [rsp+60h+Data], rbx
0x140018405  mov     [rbp+P], rbx
0x140018409  call    CmRegUtilCreateWstrKey
0x14001840e  mov     rcx, [rbp+Handle]; Handle
0x140018412  mov     ebx, eax
0x140018414  call    cs:__imp_ZwClose
0x14001841b  nop     dword ptr [rax+rax+00h]
0x140018420  test    ebx, ebx
0x140018422  js      short loc_140018491
0x140018424  mov     rcx, [rdi+8]; SecurityDescriptor
0x140018428  call    cs:__imp_RtlLengthSecurityDescriptor
0x14001842f  nop     dword ptr [rax+rax+00h]
0x140018434  mov     r11, [rdi+8]
0x140018438  lea     rdx, aSecurity; "Security"
0x14001843f  xorps   xmm0, xmm0
0x140018442  lea     rcx, [rbp+DestinationString]; DestinationString
0x140018446  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001844a  mov     r10d, eax
0x14001844d  call    WdmlibRtlInitUnicodeStringEx
0x140018452  mov     ebx, eax
0x140018454  test    eax, eax
0x140018456  js      short loc_140018481
0x140018458  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14001845c  lea     rdx, [rbp+DestinationString]; ValueName
0x140018460  mov     [rsp+60h+DataSize], r10d; DataSize
0x140018465  mov     r9d, 3; Type
0x14001846b  xor     r8d, r8d; TitleIndex
0x14001846e  mov     [rsp+60h+Data], r11; Data
0x140018473  call    cs:__imp_ZwSetValueKey
0x14001847a  nop     dword ptr [rax+rax+00h]
0x14001847f  mov     ebx, eax
0x140018481  mov     rcx, [rbp+KeyHandle]; Handle
0x140018485  call    cs:__imp_ZwClose
0x14001848c  nop     dword ptr [rax+rax+00h]
0x140018491  mov     eax, ebx
0x140018493  mov     rbx, [rsp+60h+arg_0]
0x140018498  mov     rdi, [rsp+60h+arg_8]
0x14001849d  add     rsp, 60h
0x1400184a1  pop     rbp
0x1400184a2  retn
```
