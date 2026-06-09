# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x18002bc04`
- end: `0x18002bda2`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002b41c`

## callees

- `0x18001bb30`
- `0x18001bf00`
- `0x18002b5d4`
- `0x18002bc04`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18002bd2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002bd40`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002bd91`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002bd2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002bd40`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002bd91`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x18002bc40`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x18002bc40`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x18002bccb`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x18002bccb`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x18002bcec`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x18002bd79`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x18002bcec`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x18002bd79`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18002bd04`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18002bd04`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x18002bcb2`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x18002bcb2`
- `ntoskrnl!RtlInitUnicodeString` at `0x18002bc30`
- `ntoskrnl!RtlInitUnicodeString` at `0x18002bc30`

## string_xrefs

- `0x18002bc1b`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x18002bc04  mov     [rsp-18h+arg_0], rbx
0x18002bc09  mov     [rsp-18h+BufferLength], edx
0x18002bc0d  push    rbp
0x18002bc0e  push    rdi
0x18002bc0f  push    r14
0x18002bc11  mov     rbp, rsp
0x18002bc14  sub     rsp, 70h
0x18002bc18  mov     rbx, rcx
0x18002bc1b  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x18002bc22  xorps   xmm0, xmm0
0x18002bc25  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002bc29  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002bc2d  mov     r14, r8
0x18002bc30  call    cs:__imp_RtlInitUnicodeString
0x18002bc37  nop     dword ptr [rax+rax+00h]
0x18002bc3c  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x18002bc40  call    cs:__imp_MmGetSystemRoutineAddress
0x18002bc47  nop     dword ptr [rax+rax+00h]
0x18002bc4c  mov     rcx, rbx
0x18002bc4f  test    rax, rax
0x18002bc52  jz      short loc_18002BC78
0x18002bc54  xor     r9d, r9d
0x18002bc57  mov     r8, r14
0x18002bc5a  lea     edx, [r9+1]
0x18002bc5e  call    _guard_dispatch_icall
0x18002bc63  test    eax, eax
0x18002bc65  js      loc_18002BD4E
0x18002bc6b  mov     rcx, [r14]
0x18002bc6e  or      word ptr [rcx+2], 8
0x18002bc73  jmp     loc_18002BD4E
0x18002bc78  xor     eax, eax
0x18002bc7a  lea     r9, [rbp+Dacl]
0x18002bc7e  xorps   xmm0, xmm0
0x18002bc81  mov     [rbp+var_8], rax
0x18002bc85  lea     r8, [rbp+arg_18]
0x18002bc89  mov     [rbp+arg_18], eax
0x18002bc8c  movups  [rbp+SecurityDescriptor], xmm0
0x18002bc90  mov     [rbp+BufferLength], eax
0x18002bc93  xor     edi, edi
0x18002bc95  movups  [rbp+var_18], xmm0
0x18002bc99  mov     [rbp+Dacl], rax
0x18002bc9d  mov     [r14], rax
0x18002bca0  call    SepSddlDaclFromSDDLString
0x18002bca5  mov     ebx, eax
0x18002bca7  test    eax, eax
0x18002bca9  js      short loc_18002BD1D
0x18002bcab  lea     edx, [rdi+1]; Revision
0x18002bcae  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18002bcb2  call    cs:__imp_RtlCreateSecurityDescriptor
0x18002bcb9  nop     dword ptr [rax+rax+00h]
0x18002bcbe  mov     r8, [rbp+Dacl]; Dacl
0x18002bcc2  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18002bcc6  xor     r9d, r9d; DaclDefaulted
0x18002bcc9  mov     dl, 1; DaclPresent
0x18002bccb  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18002bcd2  nop     dword ptr [rax+rax+00h]
0x18002bcd7  movzx   eax, word ptr [rbp+arg_18]
0x18002bcdb  lea     r8, [rbp+BufferLength]; BufferLength
0x18002bcdf  or      word ptr [rbp+SecurityDescriptor+2], ax
0x18002bce3  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x18002bce7  xor     edx, edx; SelfRelativeSecurityDescriptor
0x18002bce9  mov     [rbp+BufferLength], edi
0x18002bcec  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x18002bcf3  nop     dword ptr [rax+rax+00h]
0x18002bcf8  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x18002bcfb  lea     ecx, [rdi+1]; PoolType
0x18002bcfe  mov     r8d, 64536553h; Tag
0x18002bd04  call    cs:__imp_ExAllocatePoolWithTag
0x18002bd0b  nop     dword ptr [rax+rax+00h]
0x18002bd10  mov     rdi, rax
0x18002bd13  test    rax, rax
0x18002bd16  jnz     short loc_18002BD60
0x18002bd18  mov     ebx, 0C000009Ah
0x18002bd1d  cmp     [rbp+Dacl], 0
0x18002bd22  jz      short loc_18002BD36
0x18002bd24  mov     rcx, [rbp+Dacl]; P
0x18002bd28  xor     edx, edx; Tag
0x18002bd2a  call    cs:__imp_ExFreePoolWithTag
0x18002bd31  nop     dword ptr [rax+rax+00h]
0x18002bd36  test    rdi, rdi
0x18002bd39  jz      short loc_18002BD4C
0x18002bd3b  xor     edx, edx; Tag
0x18002bd3d  mov     rcx, rdi; P
0x18002bd40  call    cs:__imp_ExFreePoolWithTag
0x18002bd47  nop     dword ptr [rax+rax+00h]
0x18002bd4c  mov     eax, ebx
0x18002bd4e  mov     rbx, [rsp+70h+arg_0]
0x18002bd56  add     rsp, 70h
0x18002bd5a  pop     r14
0x18002bd5c  pop     rdi
0x18002bd5d  pop     rbp
0x18002bd5e  retn
0x18002bd60  mov     r8d, [rbp+BufferLength]; Size
0x18002bd64  xor     edx, edx; Val
0x18002bd66  mov     rcx, rdi; void *
0x18002bd69  call    memset
0x18002bd6e  lea     r8, [rbp+BufferLength]; BufferLength
0x18002bd72  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x18002bd75  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x18002bd79  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x18002bd80  nop     dword ptr [rax+rax+00h]
0x18002bd85  mov     ebx, eax
0x18002bd87  test    eax, eax
0x18002bd89  js      short loc_18002BD1D
0x18002bd8b  mov     rcx, [rbp+Dacl]; P
0x18002bd8f  xor     edx, edx; Tag
0x18002bd91  call    cs:__imp_ExFreePoolWithTag
0x18002bd98  nop     dword ptr [rax+rax+00h]
0x18002bd9d  mov     [r14], rdi
0x18002bda0  jmp     short loc_18002BD4C
```
