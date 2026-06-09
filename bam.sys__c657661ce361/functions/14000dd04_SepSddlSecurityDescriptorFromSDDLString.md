# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x14000dd04`
- end: `0x14000dea2`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000d52c`

## callees

- `0x140002710`
- `0x140002ac0`
- `0x14000d6e4`
- `0x14000dd04`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000dd30`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000dd30`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000de2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000de40`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000de91`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000de2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000de40`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000de91`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000dd40`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000dd40`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14000ddcb`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14000ddcb`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14000ddec`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14000de79`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14000ddec`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14000de79`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000de04`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000de04`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14000ddb2`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14000ddb2`

## string_xrefs

- `0x14000dd1b`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall SepSddlSecurityDescriptorFromSDDLString(__int64 a1, ULONG a2, __int64 a3)
{
  __int64 (__fastcall *SystemRoutineAddress)(__int64, __int64, __int64); // rax
  __int64 v6; // rdx
  __int64 result; // rax
  void *v8; // rdi
  NTSTATUS v9; // ebx
  PVOID PoolWithTag; // rax
  PACL Dacl; // [rsp+30h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-38h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v14; // [rsp+68h] [rbp-8h]
  ULONG BufferLength; // [rsp+98h] [rbp+28h] BYREF
  int v16; // [rsp+A8h] [rbp+38h] BYREF

  BufferLength = a2;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"SeConvertStringSecurityDescriptorToSecurityDescriptor");
  SystemRoutineAddress = (__int64 (__fastcall *)(__int64, __int64, __int64))MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
  {
    v14 = 0;
    v16 = 0;
    memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
    BufferLength = 0;
    v8 = 0;
    Dacl = 0;
    *(_QWORD *)a3 = 0;
    v9 = SepSddlDaclFromSDDLString(a1, v6, &v16, &Dacl);
    if ( v9 >= 0 )
    {
      RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
      RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, Dacl, 0);
      WORD1(SecurityDescriptor[0]) |= v16;
      BufferLength = 0;
      RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, 0, &BufferLength);
      PoolWithTag = ExAllocatePoolWithTag(PagedPool, BufferLength, 0x64536553u);
      v8 = PoolWithTag;
      if ( PoolWithTag )
      {
        memset(PoolWithTag, 0, BufferLength);
        v9 = RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, v8, &BufferLength);
        if ( v9 >= 0 )
        {
          ExFreePoolWithTag(Dacl, 0);
          *(_QWORD *)a3 = v8;
          return (unsigned int)v9;
        }
      }
      else
      {
        v9 = -1073741670;
      }
    }
    if ( Dacl )
      ExFreePoolWithTag(Dacl, 0);
    if ( v8 )
      ExFreePoolWithTag(v8, 0);
    return (unsigned int)v9;
  }
  result = SystemRoutineAddress(a1, 1, a3);
  if ( (int)result >= 0 )
    *(_WORD *)(*(_QWORD *)a3 + 2LL) |= 8u;
  return result;
}

```

## disassembly

```asm
0x14000dd04  mov     [rsp-18h+arg_0], rbx
0x14000dd09  mov     [rsp-18h+BufferLength], edx
0x14000dd0d  push    rbp
0x14000dd0e  push    rdi
0x14000dd0f  push    r14
0x14000dd11  mov     rbp, rsp
0x14000dd14  sub     rsp, 70h
0x14000dd18  mov     rbx, rcx
0x14000dd1b  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x14000dd22  xorps   xmm0, xmm0
0x14000dd25  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000dd29  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000dd2d  mov     r14, r8
0x14000dd30  call    cs:__imp_RtlInitUnicodeString
0x14000dd37  nop     dword ptr [rax+rax+00h]
0x14000dd3c  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000dd40  call    cs:__imp_MmGetSystemRoutineAddress
0x14000dd47  nop     dword ptr [rax+rax+00h]
0x14000dd4c  mov     rcx, rbx
0x14000dd4f  test    rax, rax
0x14000dd52  jz      short loc_14000DD78
0x14000dd54  xor     r9d, r9d
0x14000dd57  mov     r8, r14
0x14000dd5a  lea     edx, [r9+1]
0x14000dd5e  call    _guard_dispatch_icall
0x14000dd63  test    eax, eax
0x14000dd65  js      loc_14000DE4E
0x14000dd6b  mov     rcx, [r14]
0x14000dd6e  or      word ptr [rcx+2], 8
0x14000dd73  jmp     loc_14000DE4E
0x14000dd78  xor     eax, eax
0x14000dd7a  lea     r9, [rbp+Dacl]
0x14000dd7e  xorps   xmm0, xmm0
0x14000dd81  mov     [rbp+var_8], rax
0x14000dd85  lea     r8, [rbp+arg_18]
0x14000dd89  mov     [rbp+arg_18], eax
0x14000dd8c  movups  [rbp+SecurityDescriptor], xmm0
0x14000dd90  mov     [rbp+BufferLength], eax
0x14000dd93  xor     edi, edi
0x14000dd95  movups  [rbp+var_18], xmm0
0x14000dd99  mov     [rbp+Dacl], rax
0x14000dd9d  mov     [r14], rax
0x14000dda0  call    SepSddlDaclFromSDDLString
0x14000dda5  mov     ebx, eax
0x14000dda7  test    eax, eax
0x14000dda9  js      short loc_14000DE1D
0x14000ddab  lea     edx, [rdi+1]; Revision
0x14000ddae  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14000ddb2  call    cs:__imp_RtlCreateSecurityDescriptor
0x14000ddb9  nop     dword ptr [rax+rax+00h]
0x14000ddbe  mov     r8, [rbp+Dacl]; Dacl
0x14000ddc2  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14000ddc6  xor     r9d, r9d; DaclDefaulted
0x14000ddc9  mov     dl, 1; DaclPresent
0x14000ddcb  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14000ddd2  nop     dword ptr [rax+rax+00h]
0x14000ddd7  movzx   eax, word ptr [rbp+arg_18]
0x14000dddb  lea     r8, [rbp+BufferLength]; BufferLength
0x14000dddf  or      word ptr [rbp+SecurityDescriptor+2], ax
0x14000dde3  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x14000dde7  xor     edx, edx; SelfRelativeSecurityDescriptor
0x14000dde9  mov     [rbp+BufferLength], edi
0x14000ddec  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x14000ddf3  nop     dword ptr [rax+rax+00h]
0x14000ddf8  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x14000ddfb  lea     ecx, [rdi+1]; PoolType
0x14000ddfe  mov     r8d, 64536553h; Tag
0x14000de04  call    cs:__imp_ExAllocatePoolWithTag
0x14000de0b  nop     dword ptr [rax+rax+00h]
0x14000de10  mov     rdi, rax
0x14000de13  test    rax, rax
0x14000de16  jnz     short loc_14000DE60
0x14000de18  mov     ebx, 0C000009Ah
0x14000de1d  cmp     [rbp+Dacl], 0
0x14000de22  jz      short loc_14000DE36
0x14000de24  mov     rcx, [rbp+Dacl]; P
0x14000de28  xor     edx, edx; Tag
0x14000de2a  call    cs:__imp_ExFreePoolWithTag
0x14000de31  nop     dword ptr [rax+rax+00h]
0x14000de36  test    rdi, rdi
0x14000de39  jz      short loc_14000DE4C
0x14000de3b  xor     edx, edx; Tag
0x14000de3d  mov     rcx, rdi; P
0x14000de40  call    cs:__imp_ExFreePoolWithTag
0x14000de47  nop     dword ptr [rax+rax+00h]
0x14000de4c  mov     eax, ebx
0x14000de4e  mov     rbx, [rsp+70h+arg_0]
0x14000de56  add     rsp, 70h
0x14000de5a  pop     r14
0x14000de5c  pop     rdi
0x14000de5d  pop     rbp
0x14000de5e  retn
0x14000de60  mov     r8d, [rbp+BufferLength]; Size
0x14000de64  xor     edx, edx; Val
0x14000de66  mov     rcx, rdi; void *
0x14000de69  call    memset
0x14000de6e  lea     r8, [rbp+BufferLength]; BufferLength
0x14000de72  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x14000de75  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x14000de79  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x14000de80  nop     dword ptr [rax+rax+00h]
0x14000de85  mov     ebx, eax
0x14000de87  test    eax, eax
0x14000de89  js      short loc_14000DE1D
0x14000de8b  mov     rcx, [rbp+Dacl]; P
0x14000de8f  xor     edx, edx; Tag
0x14000de91  call    cs:__imp_ExFreePoolWithTag
0x14000de98  nop     dword ptr [rax+rax+00h]
0x14000de9d  mov     [r14], rdi
0x14000dea0  jmp     short loc_14000DE4C
```
