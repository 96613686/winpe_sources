# PpRegStateUpdateStackCreationSettings

- ea: `0x140025890`
- end: `0x140025a04`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `372`
- prototype: `NTSTATUS __fastcall(unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140024790`

## callees

- `0x1400138e0`
- `0x1400253a8`
- `0x140025890`
- `0x140025b0c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140025974`
- `ntoskrnl!ZwClose` at `0x1400259e5`
- `ntoskrnl!ZwClose` at `0x140025974`
- `ntoskrnl!ZwClose` at `0x1400259e5`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140025988`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140025988`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400258fe`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400258fe`
- `ntoskrnl!ZwSetValueKey` at `0x1400259d3`
- `ntoskrnl!ZwSetValueKey` at `0x1400259d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002591e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002591e`

## string_xrefs

- `0x140025998`: `Security`

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
0x140025890  mov     [rsp-8+arg_0], rbx
0x140025895  mov     [rsp-8+arg_8], rdi
0x14002589a  push    rbp
0x14002589b  mov     rbp, rsp
0x14002589e  sub     rsp, 60h
0x1400258a2  lea     rax, [rbp+Handle]
0x1400258a6  mov     [rbp+P], 0
0x1400258ae  xor     r9d, r9d
0x1400258b1  mov     [rsp+60h+Data], rax
0x1400258b6  xor     r8d, r8d
0x1400258b9  mov     [rbp+KeyHandle], 0
0x1400258c1  mov     rdi, rdx
0x1400258c4  mov     [rbp+Handle], 0
0x1400258cc  call    PiRegStateOpenClassKey
0x1400258d1  test    eax, eax
0x1400258d3  js      loc_1400259F3
0x1400258d9  cmp     cs:PiRegStateDiscriptor, 0
0x1400258e0  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x1400258e7  jnz     short loc_140025936
0x1400258e9  xor     edx, edx
0x1400258eb  lea     rax, [rbp+P]
0x1400258ef  mov     r9b, 1
0x1400258f2  mov     [rsp+60h+Data], rax
0x1400258f7  mov     rcx, rbx
0x1400258fa  lea     r8d, [rdx+1]
0x1400258fe  call    cs:__imp_SeCaptureSecurityDescriptor
0x140025905  nop     dword ptr [rax+rax+00h]
0x14002590a  test    eax, eax
0x14002590c  js      short loc_14002592C
0x14002590e  mov     rcx, [rbp+P]; P
0x140025912  xor     edx, edx; Tag
0x140025914  mov     cs:PiRegStateDiscriptor, 1
0x14002591e  call    cs:__imp_ExFreePoolWithTag
0x140025925  nop     dword ptr [rax+rax+00h]
0x14002592a  jmp     short loc_140025936
0x14002592c  mov     cs:PiRegStateDiscriptor, 2
0x140025936  mov     rcx, [rbp+Handle]
0x14002593a  lea     rdx, aProperties; "Properties"
0x140025941  xor     eax, eax
0x140025943  cmp     cs:PiRegStateDiscriptor, 1
0x14002594a  cmovnz  rbx, rax
0x14002594e  lea     rax, [rbp+KeyHandle]
0x140025952  mov     [rsp+60h+var_30], rax
0x140025957  mov     qword ptr [rsp+60h+DataSize], 0
0x140025960  mov     [rsp+60h+Data], rbx
0x140025965  mov     [rbp+P], rbx
0x140025969  call    CmRegUtilCreateWstrKey
0x14002596e  mov     rcx, [rbp+Handle]; Handle
0x140025972  mov     ebx, eax
0x140025974  call    cs:__imp_ZwClose
0x14002597b  nop     dword ptr [rax+rax+00h]
0x140025980  test    ebx, ebx
0x140025982  js      short loc_1400259F1
0x140025984  mov     rcx, [rdi+8]; SecurityDescriptor
0x140025988  call    cs:__imp_RtlLengthSecurityDescriptor
0x14002598f  nop     dword ptr [rax+rax+00h]
0x140025994  mov     r11, [rdi+8]
0x140025998  lea     rdx, aSecurity; "Security"
0x14002599f  xorps   xmm0, xmm0
0x1400259a2  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400259a6  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400259aa  mov     r10d, eax
0x1400259ad  call    WdmlibRtlInitUnicodeStringEx
0x1400259b2  mov     ebx, eax
0x1400259b4  test    eax, eax
0x1400259b6  js      short loc_1400259E1
0x1400259b8  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400259bc  lea     rdx, [rbp+DestinationString]; ValueName
0x1400259c0  mov     [rsp+60h+DataSize], r10d; DataSize
0x1400259c5  mov     r9d, 3; Type
0x1400259cb  xor     r8d, r8d; TitleIndex
0x1400259ce  mov     [rsp+60h+Data], r11; Data
0x1400259d3  call    cs:__imp_ZwSetValueKey
0x1400259da  nop     dword ptr [rax+rax+00h]
0x1400259df  mov     ebx, eax
0x1400259e1  mov     rcx, [rbp+KeyHandle]; Handle
0x1400259e5  call    cs:__imp_ZwClose
0x1400259ec  nop     dword ptr [rax+rax+00h]
0x1400259f1  mov     eax, ebx
0x1400259f3  mov     rbx, [rsp+60h+arg_0]
0x1400259f8  mov     rdi, [rsp+60h+arg_8]
0x1400259fd  add     rsp, 60h
0x140025a01  pop     rbp
0x140025a02  retn
```
